# DrIsSystemProcessRequest

- ea: `0x140026f90`
- end: `0x140027186`
- name: `DrIsSystemProcessRequest`
- size: `502`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140025c40`
- `0x14002b698`

## callees

- `0x140003188`
- `0x14000324c`
- `0x14000327c`
- `0x140006480`
- `0x140026f90`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002709f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002715f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002709f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002715f`
- `ntoskrnl!RtlInitializeSid` at `0x14002703f`
- `ntoskrnl!RtlInitializeSid` at `0x14002703f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140027022`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140027022`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140026fea`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400270fb`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140026fea`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400270fb`
- `ntoskrnl!SeQueryInformationToken` at `0x14002706e`
- `ntoskrnl!SeQueryInformationToken` at `0x14002706e`
- `ntoskrnl!RtlEqualSid` at `0x140027089`
- `ntoskrnl!RtlEqualSid` at `0x140027089`

## pseudocode

```c
__int64 __fastcall DrIsSystemProcessRequest(__int64 a1)
{
  BOOLEAN v2; // di
  ULONG v3; // eax
  void *v4; // rax
  void *v5; // rbx
  NTSTATUS v6; // eax
  void *v7; // rcx
  NTSTATUS v8; // eax
  ULONG v9; // eax
  PVOID TokenInformation; // [rsp+20h] [rbp-48h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+28h] [rbp-40h] BYREF

  TokenInformation = 0;
  v2 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 66, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids);
  v3 = RtlLengthRequiredSid(1u);
  v4 = operator new(v3, 0x100u);
  v5 = v4;
  if ( v4 )
  {
    *(_DWORD *)IdentifierAuthority.Value = 0;
    *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
    *RtlSubAuthoritySid(v4, 0) = 18;
    v6 = RtlInitializeSid(v5, &IdentifierAuthority, 1u);
    if ( v6 >= 0 )
    {
      v7 = *(void **)(*(_QWORD *)(a1 + 8) + 48LL);
      if ( v7 )
      {
        v8 = SeQueryInformationToken(v7, TokenUser, &TokenInformation);
        if ( v8 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              68,
              WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids,
              (unsigned int)v8);
        }
        else
        {
          v2 = RtlEqualSid(v5, *(PSID *)TokenInformation);
          ExFreePoolWithTag(TokenInformation, 0);
        }
LABEL_20:
        ExFreePoolWithTag(v5, 0);
        return v2;
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v9 = RtlLengthRequiredSid(1u);
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 67, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids, v9);
    }
    v6 = -1073741670;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 69, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids, (unsigned int)v6);
  if ( v5 )
    goto LABEL_20;
  return v2;
}

```

## disassembly

```asm
0x140026f90  push    rbx
0x140026f92  push    rbp
0x140026f93  push    rsi
0x140026f94  push    rdi
0x140026f95  sub     rsp, 48h
0x140026f99  mov     rax, cs:__security_cookie
0x140026fa0  xor     rax, rsp
0x140026fa3  mov     [rsp+68h+var_38], rax
0x140026fa8  mov     rsi, rcx
0x140026fab  mov     [rsp+68h+TokenInformation], 0
0x140026fb4  xor     dil, dil
0x140026fb7  mov     rcx, cs:WPP_GLOBAL_Control
0x140026fbe  lea     rbp, WPP_GLOBAL_Control
0x140026fc5  cmp     rcx, rbp
0x140026fc8  jz      short loc_140026FE5
0x140026fca  cmp     byte ptr [rcx+29h], 4
0x140026fce  jb      short loc_140026FE5
0x140026fd0  mov     rcx, [rcx+18h]
0x140026fd4  lea     r8, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids
0x140026fdb  mov     edx, 42h ; 'B'
0x140026fe0  call    WPP_SF_
0x140026fe5  mov     ecx, 1; SubAuthorityCount
0x140026fea  call    cs:__imp_RtlLengthRequiredSid
0x140026ff1  nop     dword ptr [rax+rax+00h]
0x140026ff6  mov     ecx, eax; unsigned __int64
0x140026ff8  mov     edx, 100h; unsigned __int64
0x140026ffd  call    ??2@YAPEAX_K0@Z; operator new(unsigned __int64,unsigned __int64)
0x140027002  mov     rbx, rax
0x140027005  test    rax, rax
0x140027008  jz      loc_1400270E4
0x14002700e  xor     edx, edx; SubAuthority
0x140027010  mov     dword ptr [rsp+68h+IdentifierAuthority.Value], 0
0x140027018  mov     rcx, rax; Sid
0x14002701b  mov     word ptr [rsp+68h+IdentifierAuthority.Value+4], 500h
0x140027022  call    cs:__imp_RtlSubAuthoritySid
0x140027029  nop     dword ptr [rax+rax+00h]
0x14002702e  mov     r8b, 1; SubAuthorityCount
0x140027031  lea     rdx, [rsp+68h+IdentifierAuthority]; IdentifierAuthority
0x140027036  mov     rcx, rbx; Sid
0x140027039  mov     dword ptr [rax], 12h
0x14002703f  call    cs:__imp_RtlInitializeSid
0x140027046  nop     dword ptr [rax+rax+00h]
0x14002704b  test    eax, eax
0x14002704d  js      loc_14002712B
0x140027053  mov     rcx, [rsi+8]
0x140027057  mov     rcx, [rcx+30h]; Token
0x14002705b  test    rcx, rcx
0x14002705e  jz      loc_14002712B
0x140027064  lea     r8, [rsp+68h+TokenInformation]; TokenInformation
0x140027069  mov     edx, 1; TokenInformationClass
0x14002706e  call    cs:__imp_SeQueryInformationToken
0x140027075  nop     dword ptr [rax+rax+00h]
0x14002707a  test    eax, eax
0x14002707c  js      short loc_1400270B0
0x14002707e  mov     rdx, [rsp+68h+TokenInformation]
0x140027083  mov     rcx, rbx; Sid1
0x140027086  mov     rdx, [rdx]; Sid2
0x140027089  call    cs:__imp_RtlEqualSid
0x140027090  nop     dword ptr [rax+rax+00h]
0x140027095  mov     rcx, [rsp+68h+TokenInformation]; P
0x14002709a  xor     edx, edx; Tag
0x14002709c  movzx   edi, al
0x14002709f  call    cs:__imp_ExFreePoolWithTag
0x1400270a6  nop     dword ptr [rax+rax+00h]
0x1400270ab  jmp     loc_14002715A
0x1400270b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400270b7  cmp     rcx, rbp
0x1400270ba  jz      loc_14002715A
0x1400270c0  cmp     byte ptr [rcx+29h], 2
0x1400270c4  jb      loc_14002715A
0x1400270ca  mov     rcx, [rcx+18h]
0x1400270ce  lea     r8, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids
0x1400270d5  mov     edx, 44h ; 'D'
0x1400270da  mov     r9d, eax
0x1400270dd  call    WPP_SF_d
0x1400270e2  jmp     short loc_14002715A
0x1400270e4  mov     rax, cs:WPP_GLOBAL_Control
0x1400270eb  cmp     rax, rbp
0x1400270ee  jz      short loc_140027126
0x1400270f0  cmp     byte ptr [rax+29h], 2
0x1400270f4  jb      short loc_140027126
0x1400270f6  mov     ecx, 1; SubAuthorityCount
0x1400270fb  call    cs:__imp_RtlLengthRequiredSid
0x140027102  nop     dword ptr [rax+rax+00h]
0x140027107  mov     rcx, cs:WPP_GLOBAL_Control
0x14002710e  lea     r8, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids
0x140027115  mov     edx, 43h ; 'C'
0x14002711a  mov     r9d, eax
0x14002711d  mov     rcx, [rcx+18h]
0x140027121  call    WPP_SF_d
0x140027126  mov     eax, 0C000009Ah
0x14002712b  mov     rcx, cs:WPP_GLOBAL_Control
0x140027132  cmp     rcx, rbp
0x140027135  jz      short loc_140027155
0x140027137  cmp     byte ptr [rcx+29h], 2
0x14002713b  jb      short loc_140027155
0x14002713d  mov     rcx, [rcx+18h]
0x140027141  lea     r8, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids
0x140027148  mov     edx, 45h ; 'E'
0x14002714d  mov     r9d, eax
0x140027150  call    WPP_SF_d
0x140027155  test    rbx, rbx
0x140027158  jz      short loc_14002716B
0x14002715a  xor     edx, edx; Tag
0x14002715c  mov     rcx, rbx; P
0x14002715f  call    cs:__imp_ExFreePoolWithTag
0x140027166  nop     dword ptr [rax+rax+00h]
0x14002716b  movzx   eax, dil
0x14002716f  mov     rcx, [rsp+68h+var_38]
0x140027174  xor     rcx, rsp; StackCookie
0x140027177  call    __security_check_cookie
0x14002717c  add     rsp, 48h
0x140027180  pop     rdi
0x140027181  pop     rsi
0x140027182  pop     rbp
0x140027183  pop     rbx
0x140027184  retn
```
