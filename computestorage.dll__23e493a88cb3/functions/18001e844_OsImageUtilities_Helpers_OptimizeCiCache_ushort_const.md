# OsImageUtilities::Helpers::OptimizeCiCache(ushort const *)

- ea: `0x18001e844`
- end: `0x18001e957`
- name: `?OptimizeCiCache@Helpers@OsImageUtilities@@YAXPEBG@Z`
- size: `275`
- prototype: `void __fastcall(OsImageUtilities::Helpers *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001ea88`

## callees

- `0x180002690`
- `0x1800127bc`
- `0x18001bd7c`
- `0x18001e844`
- `0x180027668`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x18001e8c2`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x18001e8c2`

## string_xrefs

- `0x18001e933`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x18001e945`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall OsImageUtilities::Helpers::OptimizeCiCache(const WCHAR *this, const unsigned __int16 *a2)
{
  int v2; // eax
  _QWORD *v3; // rbx
  unsigned __int64 v4; // rcx
  bool v5; // cf
  unsigned __int64 v6; // rax
  const char *v7; // r9
  unsigned int v8; // [rsp+20h] [rbp-30h] BYREF
  _QWORD **v9; // [rsp+28h] [rbp-28h] BYREF
  char v10; // [rsp+30h] [rbp-20h]
  _QWORD *v11; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int64 CompareAddress; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]

  v8 = 0;
  v11 = 0;
  v2 = ContainerCiCacheStart(this, &v8, &v11);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8F,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
      (const char *)(unsigned int)v2,
      v8);
  v9 = &v11;
  v10 = 1;
  do
  {
    v3 = v11;
    if ( v11[10] < (unsigned __int64)((__int64)(v11[8] - v11[7]) >> 5) )
    {
      while ( 1 )
      {
        v4 = v3[12];
        v5 = v3[10] < v4;
        CompareAddress = v4;
        if ( v5 )
          break;
        WaitOnAddress(v3 + 12, &CompareAddress, 8u, 0xFFFFFFFF);
      }
      v6 = (__int64)(v3[8] - v3[7]) >> 5;
      if ( v4 < v6 )
        v6 = v4;
      v3[10] = v6;
    }
    v7 = (const char *)*((unsigned int *)v3 + 26);
    if ( (int)v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x95,
        (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
        v7,
        v8);
  }
  while ( *((_DWORD *)v3 + 20) < v8 );
  wil::details::lambda_call__lambda_45899ff1aa57813e3793f05c71c01394___::_lambda_call__lambda_45899ff1aa57813e3793f05c71c01394___(&v9);
}

```

## disassembly

```asm
0x18001e844  mov     [rsp-8+arg_8], rbx
0x18001e849  mov     [rsp-8+arg_10], rdi
0x18001e84e  push    rbp
0x18001e84f  mov     rbp, rsp
0x18001e852  sub     rsp, 50h
0x18001e856  mov     rax, cs:__security_cookie
0x18001e85d  xor     rax, rsp
0x18001e860  mov     [rbp+var_8], rax
0x18001e864  mov     [rbp+var_30], 0
0x18001e86b  mov     [rbp+var_18], 0
0x18001e873  lea     r8, [rbp+var_18]
0x18001e877  lea     rdx, [rbp+var_30]
0x18001e87b  call    ContainerCiCacheStart
0x18001e880  mov     rcx, [rbp+8]; this
0x18001e884  test    eax, eax
0x18001e886  js      loc_18001E930
0x18001e88c  lea     rax, [rbp+var_18]
0x18001e890  mov     [rbp+var_28], rax
0x18001e894  mov     [rbp+var_20], 1
0x18001e898  mov     rbx, [rbp+var_18]
0x18001e89c  mov     rax, [rbx+40h]
0x18001e8a0  sub     rax, [rbx+38h]
0x18001e8a4  sar     rax, 5
0x18001e8a8  cmp     [rbx+50h], rax
0x18001e8ac  jnb     short loc_18001E8F4
0x18001e8ae  jmp     short loc_18001E8CE
0x18001e8b0  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001e8b4  mov     r8d, 8; AddressSize
0x18001e8ba  lea     rdx, [rbp+CompareAddress]; CompareAddress
0x18001e8be  lea     rcx, [rbx+60h]; Address
0x18001e8c2  call    cs:__imp_WaitOnAddress
0x18001e8c9  nop     dword ptr [rax+rax+00h]
0x18001e8ce  mov     rcx, [rbx+60h]
0x18001e8d2  nop
0x18001e8d3  cmp     [rbx+50h], rcx
0x18001e8d7  mov     [rbp+CompareAddress], rcx
0x18001e8db  jnb     short loc_18001E8B0
0x18001e8dd  mov     rax, [rbx+40h]
0x18001e8e1  sub     rax, [rbx+38h]
0x18001e8e5  sar     rax, 5
0x18001e8e9  cmp     rcx, rax
0x18001e8ec  cmovb   rax, rcx
0x18001e8f0  mov     [rbx+50h], rax
0x18001e8f4  mov     eax, [rbx+50h]
0x18001e8f7  mov     r9d, [rbx+68h]; char *
0x18001e8fb  nop
0x18001e8fc  mov     rcx, [rbp+8]; this
0x18001e900  test    r9d, r9d
0x18001e903  js      short loc_18001E945
0x18001e905  cmp     eax, [rbp+var_30]
0x18001e908  jb      short loc_18001E898
0x18001e90a  lea     rcx, [rbp+var_28]
0x18001e90e  call    wil__details__lambda_call__lambda_45899ff1aa57813e3793f05c71c01394______lambda_call__lambda_45899ff1aa57813e3793f05c71c01394___
0x18001e913  mov     rcx, [rbp+var_8]
0x18001e917  xor     rcx, rsp; StackCookie
0x18001e91a  call    __security_check_cookie
0x18001e91f  mov     rbx, [rsp+50h+arg_8]
0x18001e924  mov     rdi, [rsp+50h+arg_10]
0x18001e929  add     rsp, 50h
0x18001e92d  pop     rbp
0x18001e92e  retn
0x18001e930  mov     r9d, eax; char *
0x18001e933  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x18001e93a  mov     edx, 8Fh; void *
0x18001e93f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001e945  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x18001e94c  mov     edx, 95h; void *
0x18001e951  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
