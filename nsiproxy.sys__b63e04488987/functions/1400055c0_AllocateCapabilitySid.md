# AllocateCapabilitySid

- ea: `0x1400055c0`
- end: `0x140005698`
- name: `AllocateCapabilitySid`
- size: `216`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140005320`

## callees

- `0x1400055c0`
- `0x140006530`
- `0x140006680`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000560e`
- `ntoskrnl!ExAllocatePool2` at `0x14000560e`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400055f5`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400055f5`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140005666`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140005666`
- `ntoskrnl!RtlInitializeSid` at `0x14000562e`
- `ntoskrnl!RtlInitializeSid` at `0x14000562e`

## pseudocode

```c
void *__fastcall AllocateCapabilitySid(unsigned __int8 a1, const void *a2)
{
  unsigned int v2; // esi
  unsigned int v4; // edi
  ULONG v5; // eax
  void *result; // rax
  void *v7; // rbx
  __int64 i; // rsi
  PULONG v9; // rax
  ULONG v10; // edx
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+20h] [rbp-58h] BYREF
  int v12; // [rsp+28h] [rbp-50h]
  _BYTE v13[20]; // [rsp+2Ch] [rbp-4Ch] BYREF

  v2 = a1;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 3840;
  v4 = (unsigned __int8)(a1 + 1);
  v5 = RtlLengthRequiredSid(v4);
  result = (void *)ExAllocatePool2(256, v5, 1735414606);
  v7 = result;
  if ( result )
  {
    RtlInitializeSid(result, &IdentifierAuthority, v4);
    v12 = 3;
    if ( (_BYTE)v2 )
      memmove(v13, a2, 4LL * v2);
    for ( i = 0; (unsigned int)i < v4; *v9 = v10 )
    {
      v9 = RtlSubAuthoritySid(v7, i);
      v10 = *(_DWORD *)&v13[4 * i - 4];
      i = (unsigned int)(i + 1);
    }
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x1400055c0  push    rbx
0x1400055c2  push    rbp
0x1400055c3  push    rsi
0x1400055c4  push    rdi
0x1400055c5  sub     rsp, 58h
0x1400055c9  mov     rax, cs:__security_cookie
0x1400055d0  xor     rax, rsp
0x1400055d3  mov     [rsp+78h+var_38], rax
0x1400055d8  movzx   esi, cl
0x1400055db  mov     rbp, rdx
0x1400055de  mov     dword ptr [rsp+78h+IdentifierAuthority.Value], 0
0x1400055e6  mov     word ptr [rsp+78h+IdentifierAuthority.Value+4], 0F00h
0x1400055ed  lea     eax, [rsi+1]
0x1400055f0  movzx   edi, al
0x1400055f3  mov     ecx, edi; SubAuthorityCount
0x1400055f5  call    cs:__imp_RtlLengthRequiredSid
0x1400055fc  nop     dword ptr [rax+rax+00h]
0x140005601  mov     edx, eax
0x140005603  mov     ecx, 100h
0x140005608  mov     r8d, 6770534Eh
0x14000560e  call    cs:__imp_ExAllocatePool2
0x140005615  nop     dword ptr [rax+rax+00h]
0x14000561a  mov     rbx, rax
0x14000561d  test    rax, rax
0x140005620  jz      short loc_140005681
0x140005622  movzx   r8d, dil; SubAuthorityCount
0x140005626  lea     rdx, [rsp+78h+IdentifierAuthority]; IdentifierAuthority
0x14000562b  mov     rcx, rax; Sid
0x14000562e  call    cs:__imp_RtlInitializeSid
0x140005635  nop     dword ptr [rax+rax+00h]
0x14000563a  mov     [rsp+78h+var_50], 3
0x140005642  test    sil, sil
0x140005645  jz      short loc_14000565B
0x140005647  mov     r8d, esi
0x14000564a  lea     rcx, [rsp+78h+var_4C]; void *
0x14000564f  shl     r8, 2; Size
0x140005653  mov     rdx, rbp; Src
0x140005656  call    memmove
0x14000565b  xor     esi, esi
0x14000565d  test    edi, edi
0x14000565f  jz      short loc_14000567E
0x140005661  mov     edx, esi; SubAuthority
0x140005663  mov     rcx, rbx; Sid
0x140005666  call    cs:__imp_RtlSubAuthoritySid
0x14000566d  nop     dword ptr [rax+rax+00h]
0x140005672  mov     edx, [rsp+rsi*4+78h+var_50]
0x140005676  inc     esi
0x140005678  mov     [rax], edx
0x14000567a  cmp     esi, edi
0x14000567c  jb      short loc_140005661
0x14000567e  mov     rax, rbx
0x140005681  mov     rcx, [rsp+78h+var_38]
0x140005686  xor     rcx, rsp; StackCookie
0x140005689  call    __security_check_cookie
0x14000568e  add     rsp, 58h
0x140005692  pop     rdi
0x140005693  pop     rsi
0x140005694  pop     rbp
0x140005695  pop     rbx
0x140005696  retn
```
