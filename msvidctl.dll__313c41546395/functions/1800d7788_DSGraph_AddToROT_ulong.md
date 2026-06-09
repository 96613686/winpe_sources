# DSGraph::AddToROT(ulong *)

- ea: `0x1800d7788`
- end: `0x1800d787f`
- name: `?AddToROT@DSGraph@@QEAAJPEAK@Z`
- size: `247`
- prototype: `__int64 __fastcall(DSGraph *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800cc904`

## callees

- `0x180004640`
- `0x180006b38`
- `0x18000bda8`
- `0x1800d7788`
- `0x1800f8010`

## import_xrefs

- `ole32!GetRunningObjectTable` at `0x1800d77cb`
- `ole32!GetRunningObjectTable` at `0x1800d77cb`
- `ole32!CreateItemMoniker` at `0x1800d7811`
- `ole32!CreateItemMoniker` at `0x1800d7811`
- `KERNEL32!GetCurrentProcessId` at `0x1800d77dc`
- `KERNEL32!GetCurrentProcessId` at `0x1800d77dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DSGraph::AddToROT(DSGraph *this, unsigned int *a2)
{
  HRESULT v4; // ebx
  DWORD CurrentProcessId; // [rsp+20h] [rbp-238h]
  LPRUNNINGOBJECTTABLE pprot; // [rsp+30h] [rbp-228h] BYREF
  LPMONIKER ppmk; // [rsp+38h] [rbp-220h] BYREF
  OLECHAR szItem[256]; // [rsp+40h] [rbp-218h] BYREF

  ppmk = 0;
  pprot = 0;
  if ( GetRunningObjectTable(0, &pprot) >= 0 )
  {
    CurrentProcessId = GetCurrentProcessId();
    StringCchPrintfW(szItem, 0x100u, L"FilterGraph %p  pid %08lx", *((_QWORD *)this + 1), CurrentProcessId);
    v4 = CreateItemMoniker(L"!", szItem, &ppmk);
    if ( v4 >= 0 )
      v4 = ((__int64 (__fastcall *)(LPRUNNINGOBJECTTABLE, __int64, _QWORD, LPMONIKER, unsigned int *))pprot->lpVtbl->Register)(
             pprot,
             1,
             *((_QWORD *)this + 1),
             ppmk,
             a2);
  }
  else
  {
    v4 = -2147418113;
  }
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&pprot);
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppmk);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800d7788  mov     [rsp+arg_10], rbx
0x1800d778d  mov     [rsp+arg_18], rsi
0x1800d7792  push    rdi
0x1800d7793  sub     rsp, 250h
0x1800d779a  mov     rax, cs:__security_cookie
0x1800d77a1  xor     rax, rsp
0x1800d77a4  mov     [rsp+258h+var_18], rax
0x1800d77ac  mov     rsi, rdx
0x1800d77af  mov     rdi, rcx
0x1800d77b2  mov     [rsp+258h+ppmk], 0
0x1800d77bb  mov     [rsp+258h+pprot], 0
0x1800d77c4  lea     rdx, [rsp+258h+pprot]; pprot
0x1800d77c9  xor     ecx, ecx; reserved
0x1800d77cb  call    cs:__imp_GetRunningObjectTable
0x1800d77d1  test    eax, eax
0x1800d77d3  jns     short loc_1800D77DC
0x1800d77d5  mov     ebx, 8000FFFFh
0x1800d77da  jmp     short loc_1800D7843
0x1800d77dc  call    cs:__imp_GetCurrentProcessId
0x1800d77e2  mov     [rsp+258h+var_238], eax
0x1800d77e6  mov     r9, [rdi+8]
0x1800d77ea  lea     r8, aFiltergraphPPi; "FilterGraph %p  pid %08lx"
0x1800d77f1  mov     edx, 100h; unsigned __int64
0x1800d77f6  lea     rcx, [rsp+258h+szItem]; unsigned __int16 *
0x1800d77fb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800d7800  lea     r8, [rsp+258h+ppmk]; ppmk
0x1800d7805  lea     rdx, [rsp+258h+szItem]; lpszItem
0x1800d780a  lea     rcx, szDelim; "!"
0x1800d7811  call    cs:__imp_CreateItemMoniker
0x1800d7817  mov     ebx, eax
0x1800d7819  test    eax, eax
0x1800d781b  js      short loc_1800D7843
0x1800d781d  mov     rcx, [rsp+258h+pprot]
0x1800d7822  mov     rax, [rcx]
0x1800d7825  mov     qword ptr [rsp+258h+var_238], rsi
0x1800d782a  mov     r9, [rsp+258h+ppmk]
0x1800d782f  mov     r8, [rdi+8]
0x1800d7833  mov     edx, 1
0x1800d7838  mov     rax, [rax+18h]
0x1800d783c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7841  mov     ebx, eax
0x1800d7843  lea     rcx, [rsp+258h+pprot]
0x1800d7848  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800d784d  nop
0x1800d784e  lea     rcx, [rsp+258h+ppmk]
0x1800d7853  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800d7858  mov     eax, ebx
0x1800d785a  mov     rcx, [rsp+258h+var_18]
0x1800d7862  xor     rcx, rsp; StackCookie
0x1800d7865  call    __security_check_cookie
0x1800d786a  lea     r11, [rsp+258h+var_8]
0x1800d7872  mov     rbx, [r11+20h]
0x1800d7876  mov     rsi, [r11+28h]
0x1800d787a  mov     rsp, r11
0x1800d787d  pop     rdi
0x1800d787e  retn
```
