# CscSeGetTokenUserInformation

- ea: `0x14006d6d0`
- end: `0x14006d864`
- name: `CscSeGetTokenUserInformation`
- size: `404`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140011ad0`
- `0x1400254b8`
- `0x14006c560`

## callees

- `0x1400169d4`
- `0x140018930`
- `0x14001a5b4`
- `0x14006d6d0`

## import_xrefs

- `ntoskrnl!SeQueryInformationToken` at `0x14006d749`
- `ntoskrnl!SeQueryInformationToken` at `0x14006d749`
- `ntoskrnl!SeTokenType` at `0x14006d712`
- `ntoskrnl!SeTokenType` at `0x14006d712`

## pseudocode

```c
__int64 __fastcall CscSeGetTokenUserInformation(__int64 a1, PVOID *a2)
{
  void *v4; // rbx
  NTSTATUS v5; // eax
  unsigned int v6; // ebx
  int v7; // r8d
  PVOID v8; // r9
  PVOID TokenInformation; // [rsp+50h] [rbp+8h] BYREF

  TokenInformation = 0;
  if ( !a1 )
  {
    v7 = 273;
LABEL_14:
    v6 = -1073740768;
    goto LABEL_9;
  }
  v4 = *(void **)a1;
  if ( !*(_QWORD *)a1 )
  {
    v4 = *(void **)(a1 + 16);
    if ( !v4 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_b962e7aed4c23ff725fe1cd6d4eafe8c_Traceguids);
      }
      v7 = 282;
      goto LABEL_14;
    }
  }
  if ( SeTokenType(v4) == TokenImpersonation
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_b962e7aed4c23ff725fe1cd6d4eafe8c_Traceguids);
  }
  v5 = SeQueryInformationToken(v4, TokenUser, &TokenInformation);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        18,
        WPP_b962e7aed4c23ff725fe1cd6d4eafe8c_Traceguids,
        (unsigned int)v5);
    }
    v7 = 297;
  }
  else
  {
    v7 = 0;
  }
LABEL_9:
  v8 = TokenInformation;
  *a2 = TokenInformation;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_qqDD(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_b962e7aed4c23ff725fe1cd6d4eafe8c_Traceguids, a1, v8, v6, v7);
  return v6;
}

```

## disassembly

```asm
0x14006d6d0  mov     [rsp+arg_18], rbx
0x14006d6d5  push    rdi
0x14006d6d6  sub     rsp, 40h
0x14006d6da  mov     [rsp+48h+arg_8], rbp
0x14006d6df  mov     rdi, rcx
0x14006d6e2  mov     [rsp+48h+arg_10], rsi
0x14006d6e7  mov     rsi, rdx
0x14006d6ea  mov     [rsp+48h+TokenInformation], 0
0x14006d6f3  lea     rbp, WPP_GLOBAL_Control
0x14006d6fa  test    rcx, rcx
0x14006d6fd  jz      loc_14006D79B
0x14006d703  mov     rbx, [rcx]
0x14006d706  test    rbx, rbx
0x14006d709  jz      loc_14006D7A8
0x14006d70f  mov     rcx, rbx; Token
0x14006d712  call    cs:__imp_SeTokenType
0x14006d719  nop     dword ptr [rax+rax+00h]
0x14006d71e  cmp     eax, 2
0x14006d721  jnz     short loc_14006D73C
0x14006d723  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d72a  cmp     rcx, rbp
0x14006d72d  jz      short loc_14006D73C
0x14006d72f  test    dword ptr [rcx+2Ch], 40000h
0x14006d736  jnz     loc_14006D7E7
0x14006d73c  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x14006d741  mov     edx, 1; TokenInformationClass
0x14006d746  mov     rcx, rbx; Token
0x14006d749  call    cs:__imp_SeQueryInformationToken
0x14006d750  nop     dword ptr [rax+rax+00h]
0x14006d755  mov     ebx, eax
0x14006d757  test    eax, eax
0x14006d759  js      loc_14006D801
0x14006d75f  xor     r8d, r8d
0x14006d762  mov     r9, [rsp+48h+TokenInformation]
0x14006d767  mov     [rsi], r9
0x14006d76a  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d771  mov     rsi, [rsp+48h+arg_10]
0x14006d776  cmp     rcx, rbp
0x14006d779  mov     rbp, [rsp+48h+arg_8]
0x14006d77e  jz      short loc_14006D78D
0x14006d780  test    dword ptr [rcx+2Ch], 40000h
0x14006d787  jnz     loc_14006D839
0x14006d78d  mov     eax, ebx
0x14006d78f  mov     rbx, [rsp+48h+arg_18]
0x14006d794  add     rsp, 40h
0x14006d798  pop     rdi
0x14006d799  retn
0x14006d79b  mov     r8d, 111h
0x14006d7a1  mov     ebx, 0C0000420h
0x14006d7a6  jmp     short loc_14006D762
0x14006d7a8  mov     rbx, [rcx+10h]
0x14006d7ac  test    rbx, rbx
0x14006d7af  jnz     loc_14006D70F
0x14006d7b5  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d7bc  cmp     rcx, rbp
0x14006d7bf  jz      short loc_14006D7DF
0x14006d7c1  test    dword ptr [rcx+2Ch], 10000h
0x14006d7c8  jz      short loc_14006D7DF
0x14006d7ca  mov     rcx, [rcx+18h]
0x14006d7ce  lea     r8, WPP_b962e7aed4c23ff725fe1cd6d4eafe8c_Traceguids
0x14006d7d5  mov     edx, 10h
0x14006d7da  call    WPP_SF_
0x14006d7df  mov     r8d, 11Ah
0x14006d7e5  jmp     short loc_14006D7A1
0x14006d7e7  mov     rcx, [rcx+18h]
0x14006d7eb  lea     r8, WPP_b962e7aed4c23ff725fe1cd6d4eafe8c_Traceguids
0x14006d7f2  mov     edx, 11h
0x14006d7f7  call    WPP_SF_
0x14006d7fc  jmp     loc_14006D73C
0x14006d801  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d808  cmp     rcx, rbp
0x14006d80b  jz      short loc_14006D82E
0x14006d80d  test    dword ptr [rcx+2Ch], 10000h
0x14006d814  jz      short loc_14006D82E
0x14006d816  mov     rcx, [rcx+18h]
0x14006d81a  lea     r8, WPP_b962e7aed4c23ff725fe1cd6d4eafe8c_Traceguids
0x14006d821  mov     edx, 12h
0x14006d826  mov     r9d, eax
0x14006d829  call    WPP_SF_d
0x14006d82e  mov     r8d, 129h
0x14006d834  jmp     loc_14006D762
0x14006d839  mov     rcx, [rcx+18h]
0x14006d83d  mov     edx, 13h
0x14006d842  mov     [rsp+48h+var_18], r8d
0x14006d847  lea     r8, WPP_b962e7aed4c23ff725fe1cd6d4eafe8c_Traceguids
0x14006d84e  mov     [rsp+48h+var_20], ebx
0x14006d852  mov     [rsp+48h+var_28], r9
0x14006d857  mov     r9, rdi
0x14006d85a  call    WPP_SF_qqDD
0x14006d85f  jmp     loc_14006D78D
```
