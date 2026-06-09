# ChildNodeNames::Initialize(ushort const * *,unsigned __int64)

- ea: `0x180011184`
- end: `0x18001129b`
- name: `?Initialize@ChildNodeNames@@QEAAKPEAPEBG_K@Z`
- size: `279`
- prototype: `unsigned int __fastcall(ChildNodeNames *__hidden this, const unsigned __int16 **, unsigned __int64)`
- caller_count: `10`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b1e0`
- `0x18000f58c`
- `0x18000f7a4`
- `0x18000f954`
- `0x180010480`
- `0x180010f00`
- `0x180011630`
- `0x1800122f0`
- `0x1800170f0`
- `0x180025d40`

## callees

- `0x1800090e0`
- `0x180011184`
- `0x1800112a4`
- `0x18003586a`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800111c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800111c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800111e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800111e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800111d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800111d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800111b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800111b1`
- `OLEAUT32!__imp_SysAllocString` at `0x18001121f`
- `OLEAUT32!__imp_SysAllocString` at `0x18001121f`

## pseudocode

```c
__int64 __fastcall ChildNodeNames::Initialize(ChildNodeNames *this, const unsigned __int16 **a2, unsigned __int64 a3)
{
  LPVOID v6; // rax
  const char *v7; // r9
  void *v8; // r14
  void *v9; // rbp
  DWORD LastError; // ebx
  __int64 v11; // r14
  unsigned __int64 i; // rbx
  BSTR v13; // rax
  const char *v14; // r9
  int v16; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( a3 > 0xFFFFFFFF )
  {
    *((_DWORD *)this + 2) = -1;
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\childnodenames.cpp",
      (const char *)0x80070216LL,
      v16);
  }
  *((_DWORD *)this + 2) = a3;
  v6 = CoTaskMemAlloc(8LL * (unsigned int)a3);
  v8 = *(void **)this;
  v9 = v6;
  if ( *(_QWORD *)this )
  {
    LastError = GetLastError();
    CoTaskMemFree(v8);
    SetLastError(LastError);
  }
  *(_QWORD *)this = v9;
  if ( !v9 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x1F,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\childnodenames.cpp",
      v7);
  memset_0(v9, 0, 8LL * *((unsigned int *)this + 2));
  v11 = *(_QWORD *)this;
  for ( i = 0; i < a3; ++i )
  {
    v13 = SysAllocString(a2[i]);
    *(_QWORD *)(v11 + 8 * i) = v13;
    if ( !v13 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x26,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\childnodenames.cpp",
        v14);
  }
  return *((unsigned int *)this + 2);
}

```

## disassembly

```asm
0x180011184  push    rbx
0x180011186  push    rbp
0x180011187  push    rsi
0x180011188  push    rdi
0x180011189  push    r14
0x18001118b  push    r15
0x18001118d  sub     rsp, 28h
0x180011191  mov     eax, 0FFFFFFFFh
0x180011196  mov     rsi, r8
0x180011199  mov     r15, rdx
0x18001119c  mov     rdi, rcx
0x18001119f  cmp     r8, rax
0x1800111a2  ja      loc_180011264
0x1800111a8  mov     ecx, esi
0x1800111aa  mov     [rdi+8], ecx
0x1800111ad  shl     rcx, 3; cb
0x1800111b1  call    cs:__imp_CoTaskMemAlloc
0x1800111b8  nop     dword ptr [rax+rax+00h]
0x1800111bd  mov     r14, [rdi]
0x1800111c0  mov     rbp, rax
0x1800111c3  test    r14, r14
0x1800111c6  jz      short loc_1800111F3
0x1800111c8  call    cs:__imp_GetLastError
0x1800111cf  nop     dword ptr [rax+rax+00h]
0x1800111d4  mov     rcx, r14; pv
0x1800111d7  mov     ebx, eax
0x1800111d9  call    cs:__imp_CoTaskMemFree
0x1800111e0  nop     dword ptr [rax+rax+00h]
0x1800111e5  mov     ecx, ebx; dwErrCode
0x1800111e7  call    cs:__imp_SetLastError
0x1800111ee  nop     dword ptr [rax+rax+00h]
0x1800111f3  mov     [rdi], rbp
0x1800111f6  test    rbp, rbp
0x1800111f9  jz      loc_180011284
0x1800111ff  mov     r8d, [rdi+8]
0x180011203  xor     edx, edx; Val
0x180011205  shl     r8, 3; Size
0x180011209  mov     rcx, rbp; void *
0x18001120c  call    memset_0
0x180011211  mov     r14, [rdi]
0x180011214  xor     ebx, ebx
0x180011216  test    rsi, rsi
0x180011219  jz      short loc_180011241
0x18001121b  mov     rcx, [r15+rbx*8]; psz
0x18001121f  call    cs:__imp_SysAllocString
0x180011226  nop     dword ptr [rax+rax+00h]
0x18001122b  mov     rcx, [rsp+58h]; this
0x180011230  mov     [r14+rbx*8], rax
0x180011234  test    rax, rax
0x180011237  jz      short loc_180011252
0x180011239  inc     rbx
0x18001123c  cmp     rbx, rsi
0x18001123f  jb      short loc_18001121B
0x180011241  mov     eax, [rdi+8]
0x180011244  add     rsp, 28h
0x180011248  pop     r15
0x18001124a  pop     r14
0x18001124c  pop     rdi
0x18001124d  pop     rsi
0x18001124e  pop     rbp
0x18001124f  pop     rbx
0x180011250  retn
0x180011252  lea     r8, aOnecoreuapAdmi_24; "onecoreuap\\admin\\prov\\provcsp\\child"...
0x180011259  mov     edx, 26h ; '&'; void *
0x18001125e  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180011264  mov     [rcx+8], eax
0x180011267  lea     r8, aOnecoreuapAdmi_24; "onecoreuap\\admin\\prov\\provcsp\\child"...
0x18001126e  mov     rcx, [rsp+58h]; this
0x180011273  mov     r9d, 80070216h; char *
0x180011279  mov     edx, 1Dh; void *
0x18001127e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180011284  mov     rcx, [rsp+58h]; this
0x180011289  lea     r8, aOnecoreuapAdmi_24; "onecoreuap\\admin\\prov\\provcsp\\child"...
0x180011290  mov     edx, 1Fh; void *
0x180011295  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
