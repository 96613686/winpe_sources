# CScriptHostContext::ConvertMetaDataFilePathsToMetaDataImports(ulong,HSTRING__ * const *,ulong *,IUnknown * * *)

- ea: `0x18059c5f0`
- end: `0x18059c76d`
- name: `?ConvertMetaDataFilePathsToMetaDataImports@CScriptHostContext@@AEAAJKPEBQEAUHSTRING__@@PEAKPEAPEAPEAUIUnknown@@@Z`
- size: `381`
- prototype: `__int64 __fastcall(CScriptHostContext *__hidden this, unsigned int, HSTRING *, unsigned int *, struct IUnknown ***)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18059cc10`

## callees

- `0x1803e5a74`
- `0x180401df0`
- `0x18059c5f0`
- `0x18059cbb0`
- `0x1805cd010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18059c6a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18059c6a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18059c62c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18059c62c`

## pseudocode

```c
__int64 __fastcall CScriptHostContext::ConvertMetaDataFilePathsToMetaDataImports(
        CScriptHostContext *this,
        unsigned int a2,
        HSTRING *a3,
        unsigned int *a4,
        struct IUnknown ***a5)
{
  SIZE_T v6; // rdi
  struct IUnknown **v7; // rax
  struct IUnknown **v8; // r14
  unsigned int i; // ebx
  int v10; // r15d
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, PCWSTR, __int64, GUID *); // rbx
  PCWSTR StringRawBuffer; // rax
  int v14; // eax
  __int64 v16; // rdx
  int v17[2]; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v18; // [rsp+38h] [rbp-20h] BYREF
  struct IUnknown **v19; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]

  v18 = 0;
  v6 = 8LL * a2;
  v19 = 0;
  v7 = (struct IUnknown **)CoTaskMemAlloc(v6);
  v8 = v7;
  if ( v7 )
  {
    for ( i = 0; v6; --v6 )
    {
      *(_BYTE *)v7 = 0;
      v7 = (struct IUnknown **)((char *)v7 + 1);
    }
    AutoDeepArray<IUnknown *,unsigned long,&void CoTaskMemFreeDeallocate<IUnknown * *>(IUnknown * *),&void ReleaseDeallocate<IUnknown *>(IUnknown *)>::Deallocate(&v18);
    v19 = v8;
    v10 = 0;
    v18 = a2;
    if ( a2 )
    {
      while ( 1 )
      {
        *(_QWORD *)v17 = 0;
        v11 = *((_QWORD *)this + 3);
        v12 = *(__int64 (__fastcall **)(__int64, PCWSTR, __int64, GUID *))(*(_QWORD *)v11 + 32LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncAction>::InternalRelease(v17);
        StringRawBuffer = WindowsGetStringRawBuffer(a3[v10], 0);
        v14 = v12(v11, StringRawBuffer, 16, &IID_IMetaDataImport);
        i = v14;
        if ( v14 < 0 )
          break;
        v14 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64))v17)(
                *(_QWORD *)v17,
                &GUID_00000000_0000_0000_c000_000000000046,
                (__int64)&v8[v10]);
        i = v14;
        if ( v14 < 0 )
        {
          v16 = 349;
          goto LABEL_13;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncAction>::InternalRelease(v17);
        if ( ++v10 >= a2 )
          goto LABEL_9;
      }
      v16 = 348;
LABEL_13:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecoreuap\\inetcore\\lib\\scriptprojectionhost\\scripthostcontext.cxx",
        (const char *)(unsigned int)v14,
        (int)v17);
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncAction>::InternalRelease(v17);
    }
    else
    {
LABEL_9:
      v18 = 0;
      v19 = 0;
      *a4 = a2;
      *a5 = v8;
    }
  }
  else
  {
    i = -2147024882;
  }
  AutoDeepArray<IUnknown *,unsigned long,&void CoTaskMemFreeDeallocate<IUnknown * *>(IUnknown * *),&void ReleaseDeallocate<IUnknown *>(IUnknown *)>::Deallocate(&v18);
  return i;
}

```

## disassembly

```asm
0x18059c5f0  mov     rax, rsp
0x18059c5f3  mov     [rax+20h], r9
0x18059c5f7  mov     [rax+18h], r8
0x18059c5fb  mov     [rax+10h], edx
0x18059c5fe  mov     [rax+8], rcx
0x18059c602  push    rbp
0x18059c603  push    rbx
0x18059c604  push    rsi
0x18059c605  push    rdi
0x18059c606  push    r12
0x18059c608  push    r13
0x18059c60a  push    r14
0x18059c60c  push    r15
0x18059c60e  mov     rbp, rsp
0x18059c611  sub     rsp, 58h
0x18059c615  mov     esi, [rbp+arg_8]
0x18059c618  xor     r12d, r12d
0x18059c61b  mov     edi, esi
0x18059c61d  mov     [rbp+var_20], r12d
0x18059c621  shl     rdi, 3
0x18059c625  mov     rcx, rdi; cb
0x18059c628  mov     [rbp+var_18], r12
0x18059c62c  call    cs:__imp_CoTaskMemAlloc
0x18059c633  nop     dword ptr [rax+rax+00h]
0x18059c638  mov     r14, rax
0x18059c63b  test    rax, rax
0x18059c63e  jnz     short loc_18059C64A
0x18059c640  mov     ebx, 8007000Eh
0x18059c645  jmp     loc_18059C726
0x18059c64a  mov     r13, [rbp+arg_10]
0x18059c64e  mov     ebx, r12d
0x18059c651  test    rdi, rdi
0x18059c654  jz      short loc_18059C662
0x18059c656  mov     [rax], r12b
0x18059c659  inc     rax
0x18059c65c  sub     rdi, 1
0x18059c660  jnz     short loc_18059C656
0x18059c662  lea     rcx, [rbp+var_20]
0x18059c666  call    ?Deallocate@?$AutoDeepArray@PEAUIUnknown@@K$1??$CoTaskMemFreeDeallocate@PEAPEAUIUnknown@@@@YAXPEAPEAU1@@Z$1??$ReleaseDeallocate@PEAUIUnknown@@@@YAXPEAU1@@Z@@QEAAXXZ; AutoDeepArray<IUnknown *,ulong,&CoTaskMemFreeDeallocate<IUnknown * *>(IUnknown * *),&ReleaseDeallocate<IUnknown *>(IUnknown *)>::Deallocate(void)
0x18059c66b  mov     [rbp+var_18], r14
0x18059c66f  mov     r15d, r12d
0x18059c672  mov     [rbp+var_20], esi
0x18059c675  test    esi, esi
0x18059c677  jz      loc_18059C711
0x18059c67d  mov     rax, [rbp+arg_0]
0x18059c681  lea     rcx, [rbp+var_28]
0x18059c685  mov     qword ptr [rbp+var_28], r12
0x18059c689  mov     rdi, [rax+18h]
0x18059c68d  mov     rax, [rdi]
0x18059c690  mov     rbx, [rax+20h]
0x18059c694  call    ?InternalRelease@?$ComPtr@UIAsyncAction@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncAction>::InternalRelease(void)
0x18059c699  mov     r12d, r15d
0x18059c69c  xor     edx, edx; length
0x18059c69e  mov     rcx, [r13+r12*8+0]; string
0x18059c6a3  call    cs:__imp_WindowsGetStringRawBuffer
0x18059c6aa  nop     dword ptr [rax+rax+00h]
0x18059c6af  lea     rcx, [rbp+var_28]
0x18059c6b3  mov     r8d, 10h
0x18059c6b9  mov     qword ptr [rsp+58h+var_38], rcx; int
0x18059c6be  lea     r9, IID_IMetaDataImport
0x18059c6c5  mov     rdx, rax
0x18059c6c8  mov     rcx, rdi
0x18059c6cb  mov     rax, rbx
0x18059c6ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18059c6d3  mov     ebx, eax
0x18059c6d5  test    eax, eax
0x18059c6d7  js      short loc_18059C74A
0x18059c6d9  mov     rcx, qword ptr [rbp+var_28]
0x18059c6dd  lea     r8, [r14+r12*8]
0x18059c6e1  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18059c6e8  mov     rax, [rcx]
0x18059c6eb  mov     rax, [rax]
0x18059c6ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18059c6f3  xor     r12d, r12d
0x18059c6f6  mov     ebx, eax
0x18059c6f8  test    eax, eax
0x18059c6fa  js      short loc_18059C743
0x18059c6fc  lea     rcx, [rbp+var_28]
0x18059c700  call    ?InternalRelease@?$ComPtr@UIAsyncAction@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncAction>::InternalRelease(void)
0x18059c705  inc     r15d
0x18059c708  cmp     r15d, esi
0x18059c70b  jb      loc_18059C67D
0x18059c711  mov     rax, [rbp+arg_18]
0x18059c715  mov     [rbp+var_20], r12d
0x18059c719  mov     [rbp+var_18], r12
0x18059c71d  mov     [rax], esi
0x18059c71f  mov     rax, [rbp+arg_20]
0x18059c723  mov     [rax], r14
0x18059c726  lea     rcx, [rbp+var_20]
0x18059c72a  call    ?Deallocate@?$AutoDeepArray@PEAUIUnknown@@K$1??$CoTaskMemFreeDeallocate@PEAPEAUIUnknown@@@@YAXPEAPEAU1@@Z$1??$ReleaseDeallocate@PEAUIUnknown@@@@YAXPEAU1@@Z@@QEAAXXZ; AutoDeepArray<IUnknown *,ulong,&CoTaskMemFreeDeallocate<IUnknown * *>(IUnknown * *),&ReleaseDeallocate<IUnknown *>(IUnknown *)>::Deallocate(void)
0x18059c72f  mov     eax, ebx
0x18059c731  add     rsp, 58h
0x18059c735  pop     r15
0x18059c737  pop     r14
0x18059c739  pop     r13
0x18059c73b  pop     r12
0x18059c73d  pop     rdi
0x18059c73e  pop     rsi
0x18059c73f  pop     rbx
0x18059c740  pop     rbp
0x18059c741  retn
0x18059c743  mov     edx, 15Dh
0x18059c748  jmp     short loc_18059C74F
0x18059c74a  mov     edx, 15Ch; void *
0x18059c74f  mov     rcx, [rbp+40h]; this
0x18059c753  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\lib\\scriptprojec"...
0x18059c75a  mov     r9d, eax; char *
0x18059c75d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18059c762  lea     rcx, [rbp+var_28]
0x18059c766  call    ?InternalRelease@?$ComPtr@UIAsyncAction@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncAction>::InternalRelease(void)
0x18059c76b  jmp     short loc_18059C726
```
