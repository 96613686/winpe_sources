# CDriverVerifierPlugin::EnableDriverVerifier(void *)

- ea: `0x180033aec`
- end: `0x180033d27`
- name: `?EnableDriverVerifier@CDriverVerifierPlugin@@AEAAJPEAX@Z`
- size: `571`
- prototype: `__int64 __fastcall(const WCHAR ***this, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180033de0`

## callees

- `0x180002890`
- `0x180009ed8`
- `0x180009f00`
- `0x180009f8c`
- `0x180033aec`
- `0x180034498`

## import_xrefs

- `ntdll!NtSetSystemInformation` at `0x180033bd9`
- `ntdll!NtSetSystemInformation` at `0x180033c30`
- `ntdll!NtSetSystemInformation` at `0x180033c9c`
- `ntdll!NtSetSystemInformation` at `0x180033bd9`
- `ntdll!NtSetSystemInformation` at `0x180033c30`
- `ntdll!NtSetSystemInformation` at `0x180033c9c`
- `ntdll!RtlInitUnicodeString` at `0x180033c88`
- `ntdll!RtlInitUnicodeString` at `0x180033c88`
- `ntdll!RtlAdjustPrivilege` at `0x180033b74`
- `ntdll!RtlAdjustPrivilege` at `0x180033cfc`
- `ntdll!RtlAdjustPrivilege` at `0x180033b74`
- `ntdll!RtlAdjustPrivilege` at `0x180033cfc`

## pseudocode

```c
__int64 __fastcall CDriverVerifierPlugin::EnableDriverVerifier(const WCHAR ***this, void *a2)
{
  unsigned int v3; // ebx
  unsigned int v4; // ebx
  unsigned int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  const WCHAR **v8; // rbx
  const WCHAR **v9; // rdi
  const WCHAR *v10; // rdx
  NTSTATUS v11; // eax
  unsigned __int8 OldValue[8]; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-48h] BYREF
  _OWORD SystemInformation[2]; // [rsp+48h] [rbp-38h] BYREF
  __int64 v16; // [rsp+68h] [rbp-18h]

  OldValue[0] = 0;
  memset(SystemInformation, 0, sizeof(SystemInformation));
  v16 = 0;
  if ( !(unsigned int)CDriverVerifierPlugin::PromptForEnableDriverVerifier((CDriverVerifierPlugin *)this, a2) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_9294ba3b0f9d339286b8307f84055942_Traceguids);
    v3 = -2147467259;
    goto LABEL_30;
  }
  v4 = RtlAdjustPrivilege(0x14u, 1u, 0, OldValue);
  if ( (v4 & 0xC0000000) != 0xC0000000 )
  {
    LODWORD(SystemInformation[0]) = 1;
    v5 = NtSetSystemInformation(SystemVerifierInformationEx, SystemInformation, 0x28u);
    if ( (v5 & 0xC0000000) == 0xC0000000 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_16;
      v7 = 29;
    }
    else
    {
      v5 = NtSetSystemInformation(SystemVerifierInformation, this + 5, 4u);
      if ( (v5 & 0xC0000000) != 0xC0000000 )
      {
        v8 = this[2];
        v9 = this[3];
        while ( v8 != v9 )
        {
          v10 = *v8;
          DestinationString = 0;
          if ( v10 != v8[1] )
          {
            RtlInitUnicodeString(&DestinationString, v10);
            v11 = NtSetSystemInformation(SystemPlugPlayBusInformation, &DestinationString, 0x10u);
            if ( (v11 & 0xC0000000) == 0xC0000000
              && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                31,
                (unsigned int)WPP_9294ba3b0f9d339286b8307f84055942_Traceguids,
                (unsigned int)*v8,
                v11);
            }
          }
          v8 += 4;
        }
        *((_DWORD *)this + 11) = 1;
        v3 = 0;
        goto LABEL_30;
      }
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_16;
      v7 = 30;
    }
    WPP_SF_d(v6[2], v7, WPP_9294ba3b0f9d339286b8307f84055942_Traceguids, v5);
LABEL_16:
    v3 = v5 | 0x10000000;
LABEL_30:
    if ( OldValue[0] )
      RtlAdjustPrivilege(0x14u, 0, 0, OldValue);
    return v3;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_9294ba3b0f9d339286b8307f84055942_Traceguids, v4);
  return v4 | 0x10000000;
}

```

## disassembly

```asm
0x180033aec  mov     [rsp-28h+arg_10], rbx
0x180033af1  push    rbp
0x180033af2  push    rsi
0x180033af3  push    rdi
0x180033af4  push    r12
0x180033af6  push    r14
0x180033af8  mov     rbp, rsp
0x180033afb  sub     rsp, 80h
0x180033b02  mov     rax, cs:__security_cookie
0x180033b09  xor     rax, rsp
0x180033b0c  mov     [rbp+var_10], rax
0x180033b10  xorps   xmm0, xmm0
0x180033b13  mov     [rbp+OldValue], 0
0x180033b17  xor     eax, eax
0x180033b19  mov     r14, rcx
0x180033b1c  movups  [rbp+SystemInformation], xmm0
0x180033b20  mov     [rbp+var_18], rax
0x180033b24  movups  [rbp+var_28], xmm0
0x180033b28  call    ?PromptForEnableDriverVerifier@CDriverVerifierPlugin@@AEAAHPEAX@Z; CDriverVerifierPlugin::PromptForEnableDriverVerifier(void *)
0x180033b2d  test    eax, eax
0x180033b2f  jnz     short loc_180033B67
0x180033b31  mov     rcx, cs:WPP_GLOBAL_Control
0x180033b38  lea     rsi, WPP_GLOBAL_Control
0x180033b3f  cmp     rcx, rsi
0x180033b42  jz      short loc_180033B5D
0x180033b44  test    byte ptr [rcx+1Ch], 4
0x180033b48  jz      short loc_180033B5D
0x180033b4a  mov     rcx, [rcx+10h]
0x180033b4e  lea     edx, [rax+1Bh]
0x180033b51  lea     r8, WPP_9294ba3b0f9d339286b8307f84055942_Traceguids
0x180033b58  call    WPP_SF_
0x180033b5d  mov     ebx, 80004005h
0x180033b62  jmp     loc_180033CEA
0x180033b67  xor     r8d, r8d; ForThread
0x180033b6a  lea     r9, [rbp+OldValue]; OldValue
0x180033b6e  mov     dl, 1; NewValue
0x180033b70  lea     ecx, [r8+14h]; Privilege
0x180033b74  call    cs:__imp_RtlAdjustPrivilege
0x180033b7a  mov     r12d, 0C0000000h
0x180033b80  mov     ebx, eax
0x180033b82  and     eax, r12d
0x180033b85  cmp     eax, r12d
0x180033b88  jnz     short loc_180033BC4
0x180033b8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180033b91  lea     rsi, WPP_GLOBAL_Control
0x180033b98  cmp     rcx, rsi
0x180033b9b  jz      short loc_180033BBB
0x180033b9d  test    byte ptr [rcx+1Ch], 1
0x180033ba1  jz      short loc_180033BBB
0x180033ba3  mov     rcx, [rcx+10h]
0x180033ba7  lea     r8, WPP_9294ba3b0f9d339286b8307f84055942_Traceguids
0x180033bae  mov     edx, 1Ch
0x180033bb3  mov     r9d, ebx
0x180033bb6  call    WPP_SF_d
0x180033bbb  bts     ebx, 1Ch
0x180033bbf  jmp     loc_180033D02
0x180033bc4  mov     r8d, 28h ; '('; SystemInformationLength
0x180033bca  mov     dword ptr [rbp+SystemInformation], 1
0x180033bd1  lea     rdx, [rbp+SystemInformation]; SystemInformation
0x180033bd5  lea     ecx, [r8+34h]; SystemInformationClass
0x180033bd9  call    cs:__imp_NtSetSystemInformation
0x180033bdf  mov     ebx, eax
0x180033be1  and     eax, r12d
0x180033be4  cmp     eax, r12d
0x180033be7  jnz     short loc_180033C23
0x180033be9  mov     rcx, cs:WPP_GLOBAL_Control
0x180033bf0  lea     rsi, WPP_GLOBAL_Control
0x180033bf7  cmp     rcx, rsi
0x180033bfa  jz      short loc_180033C1A
0x180033bfc  test    byte ptr [rcx+1Ch], 1
0x180033c00  jz      short loc_180033C1A
0x180033c02  mov     edx, 1Dh
0x180033c07  mov     rcx, [rcx+10h]
0x180033c0b  lea     r8, WPP_9294ba3b0f9d339286b8307f84055942_Traceguids
0x180033c12  mov     r9d, ebx
0x180033c15  call    WPP_SF_d
0x180033c1a  bts     ebx, 1Ch
0x180033c1e  jmp     loc_180033CEA
0x180033c23  mov     ecx, 33h ; '3'; SystemInformationClass
0x180033c28  lea     rdx, [r14+28h]; SystemInformation
0x180033c2c  lea     r8d, [rcx-2Fh]; SystemInformationLength
0x180033c30  call    cs:__imp_NtSetSystemInformation
0x180033c36  mov     ebx, eax
0x180033c38  and     eax, r12d
0x180033c3b  cmp     eax, r12d
0x180033c3e  jnz     short loc_180033C60
0x180033c40  mov     rcx, cs:WPP_GLOBAL_Control
0x180033c47  lea     rsi, WPP_GLOBAL_Control
0x180033c4e  cmp     rcx, rsi
0x180033c51  jz      short loc_180033C1A
0x180033c53  test    byte ptr [rcx+1Ch], 1
0x180033c57  jz      short loc_180033C1A
0x180033c59  mov     edx, 1Eh
0x180033c5e  jmp     short loc_180033C07
0x180033c60  mov     rbx, [r14+10h]
0x180033c64  lea     rsi, WPP_GLOBAL_Control
0x180033c6b  mov     rdi, [r14+18h]
0x180033c6f  cmp     rbx, rdi
0x180033c72  jz      short loc_180033CE0
0x180033c74  mov     rdx, [rbx]; SourceString
0x180033c77  xorps   xmm0, xmm0
0x180033c7a  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180033c7e  cmp     rdx, [rbx+8]
0x180033c82  jz      short loc_180033CDA
0x180033c84  lea     rcx, [rbp+DestinationString]; DestinationString
0x180033c88  call    cs:__imp_RtlInitUnicodeString
0x180033c8e  mov     r8d, 10h; SystemInformationLength
0x180033c94  lea     rdx, [rbp+DestinationString]; SystemInformation
0x180033c98  lea     ecx, [r8+18h]; SystemInformationClass
0x180033c9c  call    cs:__imp_NtSetSystemInformation
0x180033ca2  mov     ecx, eax
0x180033ca4  and     ecx, r12d
0x180033ca7  cmp     ecx, r12d
0x180033caa  jnz     short loc_180033CDA
0x180033cac  mov     rcx, cs:WPP_GLOBAL_Control
0x180033cb3  cmp     rcx, rsi
0x180033cb6  jz      short loc_180033CDA
0x180033cb8  test    byte ptr [rcx+1Ch], 1
0x180033cbc  jz      short loc_180033CDA
0x180033cbe  mov     r9, [rbx]
0x180033cc1  lea     r8, WPP_9294ba3b0f9d339286b8307f84055942_Traceguids
0x180033cc8  mov     rcx, [rcx+10h]
0x180033ccc  mov     edx, 1Fh
0x180033cd1  mov     [rsp+80h+var_60], eax
0x180033cd5  call    WPP_SF_Sd
0x180033cda  add     rbx, 20h ; ' '
0x180033cde  jmp     short loc_180033C6F
0x180033ce0  mov     dword ptr [r14+2Ch], 1
0x180033ce8  xor     ebx, ebx
0x180033cea  cmp     [rbp+OldValue], 0
0x180033cee  jz      short loc_180033D02
0x180033cf0  xor     edx, edx; NewValue
0x180033cf2  lea     r9, [rbp+OldValue]; OldValue
0x180033cf6  xor     r8d, r8d; ForThread
0x180033cf9  lea     ecx, [rdx+14h]; Privilege
0x180033cfc  call    cs:__imp_RtlAdjustPrivilege
0x180033d02  mov     eax, ebx
0x180033d04  mov     rcx, [rbp+var_10]
0x180033d08  xor     rcx, rsp; StackCookie
0x180033d0b  call    __security_check_cookie
0x180033d10  mov     rbx, [rsp+80h+arg_10]
0x180033d18  add     rsp, 80h
0x180033d1f  pop     r14
0x180033d21  pop     r12
0x180033d23  pop     rdi
0x180033d24  pop     rsi
0x180033d25  pop     rbp
0x180033d26  retn
```
