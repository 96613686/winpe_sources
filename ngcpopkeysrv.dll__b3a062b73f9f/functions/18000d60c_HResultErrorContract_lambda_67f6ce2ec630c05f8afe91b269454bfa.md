# HResultErrorContract__lambda_67f6ce2ec630c05f8afe91b269454bfa_

- ea: `0x18000d60c`
- end: `0x18000d68a`
- name: `HResultErrorContract__lambda_67f6ce2ec630c05f8afe91b269454bfa___`
- size: `126`
- prototype: `__int64 __fastcall(__int64 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010de0`

## callees

- `0x18000b0fc`
- `0x18000d60c`
- `0x180015644`

## string_xrefs

- `0x18000d62f`: `onecore\ds\security\ngc\ngcpopkey\lib\ngcpopkeyrpc.cpp`

## pseudocode

```c
__int64 __fastcall HResultErrorContract__lambda_67f6ce2ec630c05f8afe91b269454bfa_(__int64 **a1)
{
  __int64 v1; // rdx
  __int64 v2; // rdx
  unsigned int v3; // ebx
  __int64 v4; // r9
  __int64 *v5; // rax
  int v6; // eax
  unsigned int v7; // r8d
  const char *v8; // r9
  signed int v10; // ecx
  __int64 v11; // [rsp+0h] [rbp-48h] BYREF
  const win32_exception *v12; // [rsp+20h] [rbp-28h] BYREF
  const hresult_exception *v13; // [rsp+28h] [rbp-20h] BYREF
  const wil::ResultException *v14; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v16; // [rsp+50h] [rbp+8h]

  v1 = **a1;
  if ( !v1 )
  {
    v2 = 1689;
LABEL_3:
    v3 = -2146893785;
    v4 = 2148073511LL;
    goto LABEL_4;
  }
  v5 = a1[1];
  if ( !*v5 )
  {
    v2 = 1690;
    goto LABEL_3;
  }
  try
  {
    v6 = DeleteTokenBindingAik(*(unsigned int *)a1[2], v1, *v5, *a1[3]);
  }
  catch ( std::bad_alloc )
  {
    return (unsigned int)-2147024882;
  }
  catch ( SafeIntException )
  {
    return (unsigned int)-2147024362;
  }
  catch ( const win32_exception *v12 )
  {
    v10 = *((_DWORD *)v12 + 6);
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    v16 = v10;
    if ( v10 >= 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x25,
        (unsigned int)"OneCore\\internal\\DS\\inc\\private\\security\\ngc\\inc\\ec_hresult.h",
        v8);
    return (unsigned int)v16;
  }
  catch ( const hresult_exception *v13 )
  {
    v16 = *((_DWORD *)v13 + 6);
    if ( v16 >= 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x2A,
        (unsigned int)"OneCore\\internal\\DS\\inc\\private\\security\\ngc\\inc\\ec_hresult.h",
        v8);
    return (unsigned int)v16;
  }
  catch ( const wil::ResultException *v14 )
  {
    v16 = *((_DWORD *)v14 + 8);
    if ( v16 >= 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x2F,
        (unsigned int)"OneCore\\internal\\DS\\inc\\private\\security\\ngc\\inc\\ec_hresult.h",
        v8);
    return (unsigned int)v16;
  }
  catch ( ... )
  {
    wil::details::in1diag3::FailFast_CaughtException(retaddr, &v11, v7, v8);
  }
  v3 = v6;
  if ( v6 >= 0 )
    return 0;
  v4 = (unsigned int)v6;
  v2 = 1692;
LABEL_4:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v2,
    (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\ngcpopkeyrpc.cpp",
    (const char *)v4,
    (int)v12);
  return v3;
}

```

## disassembly

```asm
0x18000d60c  push    rbx
0x18000d60e  sub     rsp, 40h
0x18000d612  mov     rax, [rcx]
0x18000d615  mov     rdx, [rax]
0x18000d618  test    rdx, rdx
0x18000d61b  jnz     short loc_18000D63D
0x18000d61d  mov     edx, 699h; void *
0x18000d622  mov     ebx, 80090027h
0x18000d627  mov     r9d, ebx; char *
0x18000d62a  mov     rcx, [rsp+48h]; this
0x18000d62f  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18000d636  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d63b  jmp     short loc_18000D674
0x18000d63d  mov     rax, [rcx+8]
0x18000d641  mov     r8, [rax]
0x18000d644  test    r8, r8
0x18000d647  jnz     short loc_18000D650
0x18000d649  mov     edx, 69Ah
0x18000d64e  jmp     short loc_18000D622
0x18000d650  mov     r9, [rcx+18h]
0x18000d654  mov     rcx, [rcx+10h]
0x18000d658  mov     r9, [r9]
0x18000d65b  mov     ecx, [rcx]
0x18000d65d  call    ?DeleteTokenBindingAik@@YAJW4_NGC_TB_AIK_KEY_TYPE@@PEBG11@Z; DeleteTokenBindingAik(_NGC_TB_AIK_KEY_TYPE,ushort const *,ushort const *,ushort const *)
0x18000d662  mov     ebx, eax
0x18000d664  test    eax, eax
0x18000d666  jns     short loc_18000D672
0x18000d668  mov     r9d, eax
0x18000d66b  mov     edx, 69Ch
0x18000d670  jmp     short loc_18000D62A
0x18000d672  xor     ebx, ebx
0x18000d674  mov     [rsp+48h+arg_0], ebx
0x18000d678  mov     eax, [rsp+48h+arg_0]
0x18000d67c  add     rsp, 40h
0x18000d680  pop     rbx
0x18000d681  retn
0x18000d682  jmp     short loc_18000D678
0x18000d684  jmp     short loc_18000D678
0x18000d686  jmp     short loc_18000D678
0x18000d688  jmp     short loc_18000D678
```
