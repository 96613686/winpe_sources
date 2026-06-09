# PsmpSetHostSwapState

- ea: `0x180007d40`
- end: `0x180007fbb`
- name: `PsmpSetHostSwapState`
- size: `635`
- prototype: `__int64 __usercall@<rax>(PSID Sid2@<rcx>, __int64, int, char)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180007d40`
- `0x180008cc0`
- `0x180009b40`
- `0x18000a750`
- `0x18000a8d0`
- `0x18001622c`
- `0x180017fa0`
- `0x18001b7e0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x180007e7d`
- `ntdll!RtlReleaseSRWLockShared` at `0x180007e7d`
- `ntdll!NtSetInformationJobObject` at `0x180007ebb`
- `ntdll!NtSetInformationJobObject` at `0x180007ebb`
- `ntdll!RtlValidSid` at `0x180007d7b`
- `ntdll!RtlValidSid` at `0x180007d7b`
- `ntdll!RtlAcquireSRWLockShared` at `0x180007e61`
- `ntdll!RtlAcquireSRWLockShared` at `0x180007e61`

## pseudocode

```c
__int64 __fastcall PsmpSetHostSwapState(PSID Sid2, int a2, __int64 a3, int a4, __int64 a5, int a6, char a7)
{
  __int64 *v11; // rbp
  __int64 v12; // r9
  int ApplicationByManagerForUser; // eax
  __int64 v14; // rsi
  __int64 *HostJobContext; // rdi
  __int64 v16; // rax
  void *v17; // rcx
  unsigned int v18; // ebx
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  NTSTATUS v23; // eax
  __int64 v24; // rax
  __int64 v25; // [rsp+30h] [rbp-48h] BYREF
  __int128 JobInformation; // [rsp+38h] [rbp-40h] BYREF

  JobInformation = 0;
  v25 = 0;
  if ( RtlValidSid(Sid2) )
  {
    v11 = 0;
    v12 = -1;
    do
      ++v12;
    while ( *(_WORD *)(a3 + 2 * v12) );
    ApplicationByManagerForUser = PsmpFindApplicationByManagerForUser(Sid2, a2, a3, 2 * v12 + 2, a6, &v25);
    v14 = v25;
    if ( ApplicationByManagerForUser < 0 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          76,
          (unsigned int)&WPP_7630e226a175390276defa9bbccaa0fe_Traceguids,
          a3,
          a2);
      v18 = -1073741772;
      goto LABEL_11;
    }
    HostJobContext = 0;
    switch ( a4 )
    {
      case 2:
        v16 = *(_QWORD *)(v25 + 6800);
        v17 = *(void **)(v25 + 192);
        if ( v16 != a5 && v16 != -1 )
          goto LABEL_24;
        break;
      case 4:
        RtlAcquireSRWLockShared(v25 + 328);
        HostJobContext = PsmpFindHostJobContext(v14, a5);
        RtlReleaseSRWLockShared(v14 + 328, v20, v21, v22);
        if ( !HostJobContext )
        {
LABEL_24:
          v18 = -1073741251;
LABEL_11:
          if ( v14 )
            PsmpDereferenceApplicationEx(v14, 0);
          if ( v11 )
            PsmpDereferenceHostContext(v11, 0);
          return v18;
        }
        v17 = (void *)HostJobContext[6];
        break;
      case 8:
        v24 = *(_QWORD *)(v25 + 6808);
        if ( v24 != a5 && v24 != -1 )
          goto LABEL_24;
        v17 = *(void **)(v25 + 200);
        break;
      case 6:
        v17 = *(void **)(v25 + 184);
        break;
      default:
        v18 = -1073741584;
        goto LABEL_11;
    }
    if ( v17 )
    {
      JobInformation = 0;
      LODWORD(JobInformation) = 4;
      BYTE5(JobInformation) = a7;
      v23 = NtSetInformationJobObject(v17, (JOBOBJECTINFOCLASS)18, &JobInformation, 0x10u);
      v18 = v23;
      if ( v23 == 262 )
      {
        v18 = -1073741671;
      }
      else if ( v23 >= 0 )
      {
        v18 = 0;
      }
      v11 = HostJobContext;
    }
    else
    {
      if ( HostJobContext )
        PsmpDereferenceHostContext(HostJobContext, 0);
      v18 = -1073741275;
    }
    goto LABEL_11;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_7630e226a175390276defa9bbccaa0fe_Traceguids);
  return (unsigned int)-1073741585;
}

```

## disassembly

```asm
0x180007d40  mov     [rsp+arg_8], rbx
0x180007d45  push    rbp
0x180007d46  push    rsi
0x180007d47  push    rdi
0x180007d48  push    r14
0x180007d4a  push    r15
0x180007d4c  sub     rsp, 50h
0x180007d50  mov     rax, cs:__security_cookie
0x180007d57  xor     rax, rsp
0x180007d5a  mov     [rsp+78h+var_30], rax
0x180007d5f  xorps   xmm0, xmm0
0x180007d62  xor     r15d, r15d
0x180007d65  movups  [rsp+78h+JobInformation], xmm0
0x180007d6a  mov     [rsp+78h+var_48], r15
0x180007d6f  mov     ebx, r9d
0x180007d72  mov     rdi, r8
0x180007d75  mov     r14d, edx
0x180007d78  mov     rsi, rcx
0x180007d7b  call    cs:__imp_RtlValidSid
0x180007d81  test    al, al
0x180007d83  jz      loc_180007F36
0x180007d89  mov     ebp, r15d
0x180007d8c  or      r9, 0FFFFFFFFFFFFFFFFh
0x180007d90  inc     r9
0x180007d93  cmp     [rdi+r9*2], r15w
0x180007d98  jnz     short loc_180007D90
0x180007d9a  lea     rax, [rsp+78h+var_48]
0x180007d9f  mov     r8, rdi
0x180007da2  mov     [rsp+78h+var_50], rax; __int64
0x180007da7  lea     r9, ds:2[r9*2]
0x180007daf  mov     eax, [rsp+78h+arg_28]
0x180007db6  mov     edx, r14d
0x180007db9  mov     rcx, rsi; Sid2
0x180007dbc  mov     [rsp+78h+var_58], eax; int
0x180007dc0  call    PsmpFindApplicationByManagerForUser
0x180007dc5  mov     rsi, [rsp+78h+var_48]
0x180007dca  test    eax, eax
0x180007dcc  js      loc_180007F68
0x180007dd2  mov     rdi, r15
0x180007dd5  cmp     ebx, 2
0x180007dd8  jnz     short loc_180007E4E
0x180007dda  mov     rax, [rsi+1A90h]
0x180007de1  mov     rcx, [rsi+0C0h]; JobHandle
0x180007de8  cmp     rax, [rsp+78h+arg_20]
0x180007df0  jnz     loc_180007EDA
0x180007df6  test    rcx, rcx
0x180007df9  jnz     loc_180007E91
0x180007dff  test    rdi, rdi
0x180007e02  jnz     loc_180007FA2
0x180007e08  mov     ebx, 0C0000225h
0x180007e0d  test    rsi, rsi
0x180007e10  jz      short loc_180007E1C
0x180007e12  xor     edx, edx
0x180007e14  mov     rcx, rsi
0x180007e17  call    PsmpDereferenceApplicationEx
0x180007e1c  test    rbp, rbp
0x180007e1f  jz      short loc_180007E2B
0x180007e21  xor     edx, edx
0x180007e23  mov     rcx, rbp
0x180007e26  call    PsmpDereferenceHostContext
0x180007e2b  mov     eax, ebx
0x180007e2d  mov     rcx, [rsp+78h+var_30]
0x180007e32  xor     rcx, rsp; StackCookie
0x180007e35  call    __security_check_cookie
0x180007e3a  mov     rbx, [rsp+78h+arg_8]
0x180007e42  add     rsp, 50h
0x180007e46  pop     r15
0x180007e48  pop     r14
0x180007e4a  pop     rdi
0x180007e4b  pop     rsi
0x180007e4c  pop     rbp
0x180007e4d  retn
0x180007e4e  cmp     ebx, 4
0x180007e51  jnz     loc_180007EF3
0x180007e57  lea     rbx, [rsi+148h]
0x180007e5e  mov     rcx, rbx
0x180007e61  call    cs:__imp_RtlAcquireSRWLockShared
0x180007e67  mov     rdx, [rsp+78h+arg_20]
0x180007e6f  mov     rcx, rsi
0x180007e72  call    PsmpFindHostJobContext
0x180007e77  mov     rcx, rbx
0x180007e7a  mov     rdi, rax
0x180007e7d  call    cs:__imp_RtlReleaseSRWLockShared
0x180007e83  test    rdi, rdi
0x180007e86  jz      short loc_180007EE4
0x180007e88  mov     rcx, [rdi+30h]
0x180007e8c  jmp     loc_180007DF6
0x180007e91  mov     al, [rsp+78h+arg_30]
0x180007e98  lea     r8, [rsp+78h+JobInformation]; JobInformation
0x180007e9d  mov     r9d, 10h; JobInformationLength
0x180007ea3  xorps   xmm0, xmm0
0x180007ea6  movups  [rsp+78h+JobInformation], xmm0
0x180007eab  mov     dword ptr [rsp+78h+JobInformation], 4
0x180007eb3  mov     byte ptr [rsp+78h+JobInformation+5], al
0x180007eb7  lea     edx, [r9+2]; JobInformationClass
0x180007ebb  call    cs:__imp_NtSetInformationJobObject
0x180007ec1  mov     ebx, eax
0x180007ec3  cmp     eax, 106h
0x180007ec8  jz      loc_180007FB1
0x180007ece  test    eax, eax
0x180007ed0  jns     short loc_180007EEE
0x180007ed2  mov     rbp, rdi
0x180007ed5  jmp     loc_180007E0D
0x180007eda  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007ede  jz      loc_180007DF6
0x180007ee4  mov     ebx, 0C000023Dh
0x180007ee9  jmp     loc_180007E0D
0x180007eee  mov     ebx, r15d
0x180007ef1  jmp     short loc_180007ED2
0x180007ef3  cmp     ebx, 8
0x180007ef6  jnz     short loc_180007F1B
0x180007ef8  mov     rax, [rsi+1A98h]
0x180007eff  cmp     rax, [rsp+78h+arg_20]
0x180007f07  jz      short loc_180007F0F
0x180007f09  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007f0d  jnz     short loc_180007EE4
0x180007f0f  mov     rcx, [rsi+0C8h]
0x180007f16  jmp     loc_180007DF6
0x180007f1b  cmp     ebx, 6
0x180007f1e  jz      short loc_180007F2A
0x180007f20  mov     ebx, 0C00000F0h
0x180007f25  jmp     loc_180007E0D
0x180007f2a  mov     rcx, [rsi+0B8h]
0x180007f31  jmp     loc_180007DF6
0x180007f36  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f3d  test    byte ptr [rcx+1Ch], 2
0x180007f41  jz      short loc_180007F5E
0x180007f43  cmp     byte ptr [rcx+19h], 2
0x180007f47  jb      short loc_180007F5E
0x180007f49  mov     rcx, [rcx+10h]
0x180007f4d  lea     r8, WPP_7630e226a175390276defa9bbccaa0fe_Traceguids
0x180007f54  mov     edx, 4Bh ; 'K'
0x180007f59  call    WPP_SF_
0x180007f5e  mov     ebx, 0C00000EFh
0x180007f63  jmp     loc_180007E2B
0x180007f68  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f6f  test    byte ptr [rcx+1Ch], 2
0x180007f73  jz      short loc_180007F98
0x180007f75  cmp     byte ptr [rcx+19h], 2
0x180007f79  jb      short loc_180007F98
0x180007f7b  mov     rcx, [rcx+10h]
0x180007f7f  lea     r8, WPP_7630e226a175390276defa9bbccaa0fe_Traceguids
0x180007f86  mov     edx, 4Ch ; 'L'
0x180007f8b  mov     [rsp+78h+var_58], r14d
0x180007f90  mov     r9, rdi
0x180007f93  call    WPP_SF_Sd
0x180007f98  mov     ebx, 0C0000034h
0x180007f9d  jmp     loc_180007E0D
0x180007fa2  xor     edx, edx
0x180007fa4  mov     rcx, rdi
0x180007fa7  call    PsmpDereferenceHostContext
0x180007fac  jmp     loc_180007E08
0x180007fb1  mov     ebx, 0C0000099h
0x180007fb6  jmp     loc_180007ED2
```
