# PsmpSetHostIoQos

- ea: `0x180013b40`
- end: `0x180013d60`
- name: `PsmpSetHostIoQos`
- size: `544`
- prototype: `__int64 __usercall@<rax>(PSID Sid2@<rcx>, __int64, int, PVOID JobInformation)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180008cc0`
- `0x180009b40`
- `0x18000a750`
- `0x18000a8d0`
- `0x180013b40`
- `0x18001622c`
- `0x180017fa0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x180013c41`
- `ntdll!RtlReleaseSRWLockShared` at `0x180013c41`
- `ntdll!NtSetInformationJobObject` at `0x180013c64`
- `ntdll!NtSetInformationJobObject` at `0x180013c64`
- `ntdll!RtlValidSid` at `0x180013b61`
- `ntdll!RtlValidSid` at `0x180013b61`
- `ntdll!RtlAcquireSRWLockShared` at `0x180013c25`
- `ntdll!RtlAcquireSRWLockShared` at `0x180013c25`

## pseudocode

```c
__int64 __fastcall PsmpSetHostIoQos(PSID Sid2, int a2, __int64 a3, int a4, __int64 a5, int a6, PVOID JobInformation)
{
  __int64 *v11; // rbp
  __int64 v12; // r9
  int ApplicationByManagerForUser; // eax
  __int64 v14; // rdi
  __int64 *HostJobContext; // rsi
  __int64 v16; // rax
  void *v17; // rcx
  NTSTATUS v18; // ebx
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rax
  __int64 v24[9]; // [rsp+30h] [rbp-48h] BYREF

  v24[0] = 0;
  if ( RtlValidSid(Sid2) )
  {
    v11 = 0;
    v12 = -1;
    do
      ++v12;
    while ( *(_WORD *)(a3 + 2 * v12) );
    ApplicationByManagerForUser = PsmpFindApplicationByManagerForUser(Sid2, a2, a3, 2 * v12 + 2, a6, v24);
    v14 = v24[0];
    if ( ApplicationByManagerForUser < 0 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          78,
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
        v16 = *(_QWORD *)(v24[0] + 6800);
        v17 = *(void **)(v24[0] + 192);
        if ( v16 != a5 && v16 != -1 )
          goto LABEL_22;
        break;
      case 4:
        RtlAcquireSRWLockShared(v24[0] + 328);
        HostJobContext = PsmpFindHostJobContext(v14, a5);
        RtlReleaseSRWLockShared(v14 + 328, v20, v21, v22);
        if ( !HostJobContext )
        {
LABEL_22:
          v18 = -1073741251;
LABEL_11:
          if ( v14 )
            PsmpDereferenceApplicationEx(v14, 0);
          if ( v11 )
            PsmpDereferenceHostContext(v11, 0);
          return (unsigned int)v18;
        }
        v17 = (void *)HostJobContext[6];
        break;
      case 8:
        v23 = *(_QWORD *)(v24[0] + 6808);
        if ( v23 != a5 && v23 != -1 )
          goto LABEL_22;
        v17 = *(void **)(v24[0] + 200);
        break;
      case 6:
        v17 = *(void **)(v24[0] + 184);
        break;
      default:
        v18 = -1073741584;
        goto LABEL_11;
    }
    if ( v17 )
    {
      v18 = NtSetInformationJobObject(
              v17,
              MaxJobObjectInfoClass|JobObjectBasicProcessIdList|0x10,
              JobInformation,
              0x60u);
      v11 = HostJobContext;
      if ( v18 >= 0 )
        v18 = 0;
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_7630e226a175390276defa9bbccaa0fe_Traceguids);
  return (unsigned int)-1073741585;
}

```

## disassembly

```asm
0x180013b40  push    rbx
0x180013b42  push    rbp
0x180013b43  push    rsi
0x180013b44  push    rdi
0x180013b45  push    r14
0x180013b47  push    r15
0x180013b49  sub     rsp, 48h
0x180013b4d  xor     r15d, r15d
0x180013b50  mov     ebx, r9d
0x180013b53  mov     [rsp+78h+var_48], r15
0x180013b58  mov     rsi, r8
0x180013b5b  mov     r14d, edx
0x180013b5e  mov     rdi, rcx
0x180013b61  call    cs:__imp_RtlValidSid
0x180013b67  test    al, al
0x180013b69  jz      loc_180013CD6
0x180013b6f  mov     ebp, r15d
0x180013b72  or      r9, 0FFFFFFFFFFFFFFFFh
0x180013b76  inc     r9
0x180013b79  cmp     [rsi+r9*2], r15w
0x180013b7e  jnz     short loc_180013B76
0x180013b80  lea     rax, [rsp+78h+var_48]
0x180013b85  mov     r8, rsi
0x180013b88  mov     [rsp+78h+var_50], rax; __int64
0x180013b8d  lea     r9, ds:2[r9*2]
0x180013b95  mov     eax, [rsp+78h+arg_28]
0x180013b9c  mov     edx, r14d
0x180013b9f  mov     rcx, rdi; Sid2
0x180013ba2  mov     [rsp+78h+var_58], eax; int
0x180013ba6  call    PsmpFindApplicationByManagerForUser
0x180013bab  mov     rdi, [rsp+78h+var_48]
0x180013bb0  test    eax, eax
0x180013bb2  js      loc_180013D08
0x180013bb8  mov     rsi, r15
0x180013bbb  cmp     ebx, 2
0x180013bbe  jnz     short loc_180013C16
0x180013bc0  mov     rax, [rdi+1A90h]
0x180013bc7  mov     rcx, [rdi+0C0h]; JobHandle
0x180013bce  cmp     rax, [rsp+78h+arg_20]
0x180013bd6  jnz     loc_180013C7F
0x180013bdc  test    rcx, rcx
0x180013bdf  jnz     short loc_180013C52
0x180013be1  test    rsi, rsi
0x180013be4  jnz     loc_180013D42
0x180013bea  mov     ebx, 0C0000225h
0x180013bef  test    rdi, rdi
0x180013bf2  jz      short loc_180013BFE
0x180013bf4  xor     edx, edx
0x180013bf6  mov     rcx, rdi
0x180013bf9  call    PsmpDereferenceApplicationEx
0x180013bfe  test    rbp, rbp
0x180013c01  jnz     loc_180013D51
0x180013c07  mov     eax, ebx
0x180013c09  add     rsp, 48h
0x180013c0d  pop     r15
0x180013c0f  pop     r14
0x180013c11  pop     rdi
0x180013c12  pop     rsi
0x180013c13  pop     rbp
0x180013c14  pop     rbx
0x180013c15  retn
0x180013c16  cmp     ebx, 4
0x180013c19  jnz     short loc_180013C93
0x180013c1b  lea     rbx, [rdi+148h]
0x180013c22  mov     rcx, rbx
0x180013c25  call    cs:__imp_RtlAcquireSRWLockShared
0x180013c2b  mov     rdx, [rsp+78h+arg_20]
0x180013c33  mov     rcx, rdi
0x180013c36  call    PsmpFindHostJobContext
0x180013c3b  mov     rcx, rbx
0x180013c3e  mov     rsi, rax
0x180013c41  call    cs:__imp_RtlReleaseSRWLockShared
0x180013c47  test    rsi, rsi
0x180013c4a  jz      short loc_180013C89
0x180013c4c  mov     rcx, [rsi+30h]
0x180013c50  jmp     short loc_180013BDC
0x180013c52  mov     r8, [rsp+78h+JobInformation]; JobInformation
0x180013c5a  mov     r9d, 60h ; '`'; JobInformationLength
0x180013c60  lea     edx, [r9-41h]; JobInformationClass
0x180013c64  call    cs:__imp_NtSetInformationJobObject
0x180013c6a  mov     ebx, eax
0x180013c6c  mov     rbp, rsi
0x180013c6f  test    eax, eax
0x180013c71  js      loc_180013BEF
0x180013c77  mov     ebx, r15d
0x180013c7a  jmp     loc_180013BEF
0x180013c7f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180013c83  jz      loc_180013BDC
0x180013c89  mov     ebx, 0C000023Dh
0x180013c8e  jmp     loc_180013BEF
0x180013c93  cmp     ebx, 8
0x180013c96  jnz     short loc_180013CBB
0x180013c98  mov     rax, [rdi+1A98h]
0x180013c9f  cmp     rax, [rsp+78h+arg_20]
0x180013ca7  jz      short loc_180013CAF
0x180013ca9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180013cad  jnz     short loc_180013C89
0x180013caf  mov     rcx, [rdi+0C8h]
0x180013cb6  jmp     loc_180013BDC
0x180013cbb  cmp     ebx, 6
0x180013cbe  jz      short loc_180013CCA
0x180013cc0  mov     ebx, 0C00000F0h
0x180013cc5  jmp     loc_180013BEF
0x180013cca  mov     rcx, [rdi+0B8h]
0x180013cd1  jmp     loc_180013BDC
0x180013cd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180013cdd  test    byte ptr [rcx+1Ch], 2
0x180013ce1  jz      short loc_180013CFE
0x180013ce3  cmp     byte ptr [rcx+19h], 2
0x180013ce7  jb      short loc_180013CFE
0x180013ce9  mov     rcx, [rcx+10h]
0x180013ced  lea     r8, WPP_7630e226a175390276defa9bbccaa0fe_Traceguids
0x180013cf4  mov     edx, 4Dh ; 'M'
0x180013cf9  call    WPP_SF_
0x180013cfe  mov     ebx, 0C00000EFh
0x180013d03  jmp     loc_180013C07
0x180013d08  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d0f  test    byte ptr [rcx+1Ch], 2
0x180013d13  jz      short loc_180013D38
0x180013d15  cmp     byte ptr [rcx+19h], 2
0x180013d19  jb      short loc_180013D38
0x180013d1b  mov     rcx, [rcx+10h]
0x180013d1f  lea     r8, WPP_7630e226a175390276defa9bbccaa0fe_Traceguids
0x180013d26  mov     edx, 4Eh ; 'N'
0x180013d2b  mov     [rsp+78h+var_58], r14d
0x180013d30  mov     r9, rsi
0x180013d33  call    WPP_SF_Sd
0x180013d38  mov     ebx, 0C0000034h
0x180013d3d  jmp     loc_180013BEF
0x180013d42  xor     edx, edx
0x180013d44  mov     rcx, rsi
0x180013d47  call    PsmpDereferenceHostContext
0x180013d4c  jmp     loc_180013BEA
0x180013d51  xor     edx, edx
0x180013d53  mov     rcx, rbp
0x180013d56  call    PsmpDereferenceHostContext
0x180013d5b  jmp     loc_180013C07
```
