# MSChapDomain::insert(IASTL::IASRequest &,uchar,ushort const *)

- ea: `0x18001126c`
- end: `0x180011375`
- name: `?insert@MSChapDomain@@SAXAEAVIASRequest@IASTL@@EPEBG@Z`
- size: `265`
- prototype: `static void(struct IASTL::IASRequest *, unsigned __int8, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ec4c`
- `0x18000eea8`

## callees

- `0x18000acf4`
- `0x18000c28c`
- `0x18000c808`
- `0x18000d55c`
- `0x18001126c`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x1800112c0`
- `KERNEL32!WideCharToMultiByte` at `0x180011325`
- `KERNEL32!WideCharToMultiByte` at `0x1800112c0`
- `KERNEL32!WideCharToMultiByte` at `0x180011325`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800112e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800112e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall MSChapDomain::insert(struct IAttributesRaw **a1, bool a2, const unsigned __int16 *a3)
{
  int v6; // eax
  int cbMultiByte; // esi
  _BYTE *v8; // rax
  _BYTE *v9; // rdi
  _DWORD *v10; // rbx
  LPVOID pv; // [rsp+78h] [rbp+20h] BYREF

  IASTL::IASAttribute::IASAttribute((IASTL::IASAttribute *)&pv, a2);
  v6 = WideCharToMultiByte(0, 0, a3, -1, 0, 0, 0, 0);
  cbMultiByte = v6;
  if ( v6 + 1LL < (unsigned __int64)v6 )
    _com_issue_error(534);
  v8 = CoTaskMemAlloc(v6 + 1LL);
  v9 = v8;
  if ( !v8 )
    _com_issue_error(-2147024882);
  *v8 = a2;
  WideCharToMultiByte(0, 0, a3, -1, v8 + 1, cbMultiByte, 0, 0);
  v10 = pv;
  *((_DWORD *)pv + 2) = 4120;
  v10[4] = 6;
  *((_QWORD *)v10 + 4) = v9;
  v10[6] = cbMultiByte;
  v10[1] = 1;
  IASTL::IASAttribute::store((IASTL::IASAttribute *)&pv, a1[1]);
  IASAttributeRelease(v10);
}

```

## disassembly

```asm
0x18001126c  mov     [rsp+arg_0], rbx
0x180011271  mov     [rsp+arg_8], rbp
0x180011276  push    rsi
0x180011277  push    rdi
0x180011278  push    r14
0x18001127a  sub     rsp, 40h
0x18001127e  mov     rbx, r8
0x180011281  mov     bpl, dl
0x180011284  mov     r14, rcx
0x180011287  lea     rcx, [rsp+58h+pv]; this
0x18001128c  call    ??0IASAttribute@IASTL@@QEAA@_N@Z; IASTL::IASAttribute::IASAttribute(bool)
0x180011291  nop
0x180011292  mov     [rsp+58h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18001129b  mov     [rsp+58h+lpDefaultChar], 0; lpDefaultChar
0x1800112a4  mov     [rsp+58h+cbMultiByte], 0; cbMultiByte
0x1800112ac  mov     [rsp+58h+lpMultiByteStr], 0; lpMultiByteStr
0x1800112b5  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800112b9  mov     r8, rbx; lpWideCharStr
0x1800112bc  xor     edx, edx; dwFlags
0x1800112be  xor     ecx, ecx; CodePage
0x1800112c0  call    cs:__imp_WideCharToMultiByte
0x1800112c6  movsxd  rsi, eax
0x1800112c9  lea     rdx, [rsi+1]
0x1800112cd  cmp     rdx, rsi
0x1800112d0  jnb     short loc_1800112DD
0x1800112d2  mov     ecx, 216h; int
0x1800112d7  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800112dd  mov     rcx, rdx; cb
0x1800112e0  call    cs:__imp_CoTaskMemAlloc
0x1800112e6  mov     rdi, rax
0x1800112e9  test    rax, rax
0x1800112ec  jnz     short loc_1800112F9
0x1800112ee  mov     ecx, 8007000Eh; int
0x1800112f3  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800112f9  mov     [rax], bpl
0x1800112fc  inc     rax
0x1800112ff  mov     [rsp+58h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180011308  mov     [rsp+58h+lpDefaultChar], 0; lpDefaultChar
0x180011311  mov     [rsp+58h+cbMultiByte], esi; cbMultiByte
0x180011315  mov     [rsp+58h+lpMultiByteStr], rax; lpMultiByteStr
0x18001131a  or      r9d, 0FFFFFFFFh; cchWideChar
0x18001131e  mov     r8, rbx; lpWideCharStr
0x180011321  xor     edx, edx; dwFlags
0x180011323  xor     ecx, ecx; CodePage
0x180011325  call    cs:__imp_WideCharToMultiByte
0x18001132b  mov     rbx, [rsp+58h+pv]
0x180011330  mov     dword ptr [rbx+8], 1018h
0x180011337  mov     dword ptr [rbx+10h], 6
0x18001133e  mov     [rbx+20h], rdi
0x180011342  mov     [rbx+18h], esi
0x180011345  mov     dword ptr [rbx+4], 1
0x18001134c  mov     rdx, [r14+8]; struct IAttributesRaw *
0x180011350  lea     rcx, [rsp+58h+pv]; this
0x180011355  call    ?store@IASAttribute@IASTL@@QEBAXPEAUIAttributesRaw@@@Z; IASTL::IASAttribute::store(IAttributesRaw *)
0x18001135a  nop
0x18001135b  mov     rcx, rbx; pv
0x18001135e  mov     rbx, [rsp+58h+arg_0]
0x180011363  mov     rbp, [rsp+58h+arg_8]
0x180011368  add     rsp, 40h
0x18001136c  pop     r14
0x18001136e  pop     rdi
0x18001136f  pop     rsi
0x180011370  jmp     IASAttributeRelease
```
