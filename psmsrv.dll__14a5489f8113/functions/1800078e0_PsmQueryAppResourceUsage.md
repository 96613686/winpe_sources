# PsmQueryAppResourceUsage

- ea: `0x1800078e0`
- end: `0x180007ba9`
- name: `PsmQueryAppResourceUsage`
- size: `713`
- prototype: `__int64 __usercall@<rax>(PSID pSid@<rcx>, __int64, int, __int64)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000772c`
- `0x1800078e0`
- `0x180007bb0`
- `0x180008cc0`
- `0x180009b40`
- `0x18000a750`
- `0x18000a8d0`
- `0x1800149b0`
- `0x18001720c`
- `0x18001b7e0`
- `0x18001c10c`
- `0x18001ea9c`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x1800079ca`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800079ca`
- `ntdll!NtQueryInformationJobObject` at `0x180007a74`
- `ntdll!NtQueryInformationJobObject` at `0x180007a74`
- `ntdll!RtlAcquireSRWLockShared` at `0x180007971`
- `ntdll!RtlAcquireSRWLockShared` at `0x180007971`

## pseudocode

```c
__int64 __fastcall PsmQueryAppResourceUsage(
        PSID pSid,
        int a2,
        const wchar_t *a3,
        unsigned int a4,
        __int64 a5,
        int a6,
        _OWORD *a7)
{
  __int64 v8; // r9
  int ApplicationByManagerForUser; // eax
  __int64 v12; // r8
  int v13; // edi
  _QWORD *v14; // rbx
  __int64 v15; // r12
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 *v19; // rdi
  __int64 v20; // rax
  void *v21; // rcx
  __int64 *HostJobContext; // rax
  __int32 HostWorkItemCount; // eax
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int64 v29; // rax
  char v30[8]; // [rsp+28h] [rbp-99h]
  __int128 v31; // [rsp+30h] [rbp-91h] BYREF
  __m256i v32; // [rsp+40h] [rbp-81h]
  __m256i v33; // [rsp+60h] [rbp-61h]
  __int128 v34; // [rsp+80h] [rbp-41h] BYREF
  __int128 v35; // [rsp+90h] [rbp-31h]
  __int128 v36; // [rsp+A0h] [rbp-21h]
  __int64 v37; // [rsp+B0h] [rbp-11h]
  __int128 JobInformation; // [rsp+B8h] [rbp-9h] BYREF

  *(_QWORD *)&JobInformation = 0;
  v8 = -1;
  do
    ++v8;
  while ( a3[v8] );
  ApplicationByManagerForUser = PsmpFindApplicationByManagerForUser(
                                  pSid,
                                  a2,
                                  (__int64)a3,
                                  2 * v8 + 2,
                                  a6,
                                  (__int64 *)&JobInformation);
  v13 = ApplicationByManagerForUser;
  if ( ApplicationByManagerForUser >= 0 )
  {
    memset_0(&v31, 0, 0x50u);
    v14 = (_QWORD *)JobInformation;
    v15 = JobInformation + 328;
    RtlAcquireSRWLockShared(JobInformation + 328);
    PsmpQueryAppResourceUsage(v14, a4, a5, &v31);
    v19 = 0;
    JobInformation = 0;
    switch ( a4 )
    {
      case 2u:
        v20 = v14[850];
        v21 = (void *)v14[24];
        if ( v20 != a5 && v20 != -1 )
          goto LABEL_22;
        break;
      case 4u:
        HostJobContext = PsmpFindHostJobContext((__int64)v14, a5);
        v19 = HostJobContext;
        if ( !HostJobContext )
          goto LABEL_22;
        v21 = (void *)HostJobContext[6];
        break;
      case 6u:
        v21 = (void *)v14[23];
        break;
      case 8u:
        v29 = v14[851];
        if ( v29 != a5 && v29 != -1 )
        {
LABEL_22:
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_ii(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              51,
              &WPP_7630e226a175390276defa9bbccaa0fe_Traceguids,
              v14[12],
              a5);
          goto LABEL_10;
        }
        v21 = (void *)v14[25];
        break;
      default:
LABEL_10:
        RtlReleaseSRWLockShared(v15, v16, v17, v18);
        PsmpDereferenceApplicationEx((__int64)v14, 0);
        v34 = 0;
        v37 = 0;
        v35 = 0;
        v36 = 0;
        v13 = PsmpQueryVolumeIoTimes(&v34);
        if ( v13 >= 0 )
        {
          *(_OWORD *)&v32.m256i_u64[1] = v35;
          HostWorkItemCount = PsmpQueryHostWorkItemCount(v14, a4, a5);
          v25 = *(_OWORD *)v32.m256i_i8;
          *a7 = v31;
          v33.m256i_i32[6] = HostWorkItemCount;
          v26 = *(_OWORD *)&v32.m256i_u64[2];
          a7[1] = v25;
          v27 = *(_OWORD *)v33.m256i_i8;
          a7[2] = v26;
          v28 = *(_OWORD *)&v33.m256i_u64[2];
          a7[3] = v27;
          a7[4] = v28;
        }
        return (unsigned int)v13;
    }
    if ( v21 )
    {
      NtQueryInformationJobObject(v21, MaxJobObjectInfoClass|0x10, &JobInformation, 0x10u, 0);
      *(_OWORD *)&v33.m256i_u64[1] = JobInformation;
    }
    if ( v19 )
      PsmpDereferenceHostContext(v19, 0);
    goto LABEL_10;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    *(_DWORD *)v30 = ApplicationByManagerForUser;
    WPP_SF_S_sid_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x31u, v12, a3, (char *)pSid, *(_QWORD *)v30);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800078e0  mov     [rsp-8+arg_8], rbx
0x1800078e5  push    rbp
0x1800078e6  push    rsi
0x1800078e7  push    rdi
0x1800078e8  push    r12
0x1800078ea  push    r13
0x1800078ec  push    r14
0x1800078ee  push    r15
0x1800078f0  lea     rbp, [rsp-0Fh]
0x1800078f5  sub     rsp, 0D0h
0x1800078fc  mov     rax, cs:__security_cookie
0x180007903  xor     rax, rsp
0x180007906  mov     [rbp+3Fh+var_38], rax
0x18000790a  mov     r15, [rbp+3Fh+arg_30]
0x18000790e  xor     r13d, r13d
0x180007911  mov     r14d, r9d
0x180007914  mov     qword ptr [rbp+3Fh+JobInformation], r13
0x180007918  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000791c  mov     rbx, r8
0x18000791f  mov     rsi, rcx
0x180007922  inc     r9
0x180007925  cmp     [r8+r9*2], r13w
0x18000792a  jnz     short loc_180007922
0x18000792c  lea     rax, [rbp+3Fh+JobInformation]
0x180007930  mov     qword ptr [rsp+100h+var_D8], rax; __int64
0x180007935  lea     r9, ds:2[r9*2]
0x18000793d  mov     eax, [rbp+3Fh+arg_28]
0x180007940  mov     dword ptr [rsp+100h+ReturnLength], eax; int
0x180007944  call    PsmpFindApplicationByManagerForUser
0x180007949  mov     edi, eax
0x18000794b  test    eax, eax
0x18000794d  js      loc_180007B63
0x180007953  xor     edx, edx; Val
0x180007955  lea     rcx, [rsp+100h+var_D0]; void *
0x18000795a  lea     r8d, [rdx+50h]; Size
0x18000795e  call    memset_0
0x180007963  mov     rbx, qword ptr [rbp+3Fh+JobInformation]
0x180007967  lea     r12, [rbx+148h]
0x18000796e  mov     rcx, r12
0x180007971  call    cs:__imp_RtlAcquireSRWLockShared
0x180007977  mov     rsi, [rbp+3Fh+arg_20]
0x18000797b  lea     r9, [rsp+100h+var_D0]
0x180007980  mov     r8, rsi
0x180007983  mov     edx, r14d
0x180007986  mov     rcx, rbx
0x180007989  call    PsmpQueryAppResourceUsage
0x18000798e  xorps   xmm0, xmm0
0x180007991  mov     rdi, r13
0x180007994  movups  [rbp+3Fh+JobInformation], xmm0
0x180007998  cmp     r14d, 2
0x18000799c  jnz     loc_180007A37
0x1800079a2  mov     rax, [rbx+1A90h]
0x1800079a9  mov     rcx, [rbx+0C0h]; JobHandle
0x1800079b0  cmp     rax, rsi
0x1800079b3  jnz     loc_180007AE3
0x1800079b9  test    rcx, rcx
0x1800079bc  jnz     loc_180007A61
0x1800079c2  test    rdi, rdi
0x1800079c5  jnz     short loc_180007A2B
0x1800079c7  mov     rcx, r12
0x1800079ca  call    cs:__imp_RtlReleaseSRWLockShared
0x1800079d0  xor     edx, edx
0x1800079d2  mov     rcx, rbx
0x1800079d5  call    PsmpDereferenceApplicationEx
0x1800079da  xorps   xmm0, xmm0
0x1800079dd  lea     rcx, [rbp+3Fh+var_80]
0x1800079e1  xor     eax, eax
0x1800079e3  movups  [rbp+3Fh+var_80], xmm0
0x1800079e7  mov     [rbp+3Fh+var_50], rax
0x1800079eb  movups  [rbp+3Fh+var_70], xmm0
0x1800079ef  movups  [rbp+3Fh+var_60], xmm0
0x1800079f3  call    PsmpQueryVolumeIoTimes
0x1800079f8  mov     edi, eax
0x1800079fa  test    eax, eax
0x1800079fc  jns     loc_180007A8F
0x180007a02  mov     eax, edi
0x180007a04  mov     rcx, [rbp+3Fh+var_38]
0x180007a08  xor     rcx, rsp; StackCookie
0x180007a0b  call    __security_check_cookie
0x180007a10  mov     rbx, [rsp+100h+arg_8]
0x180007a18  add     rsp, 0D0h
0x180007a1f  pop     r15
0x180007a21  pop     r14
0x180007a23  pop     r13
0x180007a25  pop     r12
0x180007a27  pop     rdi
0x180007a28  pop     rsi
0x180007a29  pop     rbp
0x180007a2a  retn
0x180007a2b  xor     edx, edx
0x180007a2d  mov     rcx, rdi
0x180007a30  call    PsmpDereferenceHostContext
0x180007a35  jmp     short loc_1800079C7
0x180007a37  cmp     r14d, 4
0x180007a3b  jnz     loc_180007AEF
0x180007a41  mov     rdx, rsi
0x180007a44  mov     rcx, rbx
0x180007a47  call    PsmpFindHostJobContext
0x180007a4c  mov     rdi, rax
0x180007a4f  test    rax, rax
0x180007a52  jz      loc_180007B19
0x180007a58  mov     rcx, [rax+30h]
0x180007a5c  jmp     loc_1800079B9
0x180007a61  mov     r9d, 10h; JobInformationLength
0x180007a67  mov     [rsp+100h+ReturnLength], r13; ReturnLength
0x180007a6c  lea     r8, [rbp+3Fh+JobInformation]; JobInformation
0x180007a70  lea     edx, [r9+0Ch]; JobInformationClass
0x180007a74  call    cs:__imp_NtQueryInformationJobObject
0x180007a7a  mov     rax, qword ptr [rbp+3Fh+JobInformation]
0x180007a7e  mov     [rbp+3Fh+var_98], rax
0x180007a82  mov     rax, qword ptr [rbp+3Fh+JobInformation+8]
0x180007a86  mov     qword ptr [rbp+3Fh+var_90], rax
0x180007a8a  jmp     loc_1800079C2
0x180007a8f  mov     rax, qword ptr [rbp+3Fh+var_70]
0x180007a93  mov     r8, rsi
0x180007a96  mov     [rbp+3Fh+var_B8], rax
0x180007a9a  mov     edx, r14d
0x180007a9d  mov     rax, qword ptr [rbp+3Fh+var_70+8]
0x180007aa1  mov     rcx, rbx
0x180007aa4  mov     qword ptr [rbp+3Fh+var_B0], rax
0x180007aa8  call    PsmpQueryHostWorkItemCount
0x180007aad  movaps  xmm0, [rsp+100h+var_D0]
0x180007ab2  movaps  xmm1, xmmword ptr [rsp+40h]
0x180007ab7  movups  xmmword ptr [r15], xmm0
0x180007abb  mov     dword ptr [rbp+3Fh+var_90+8], eax
0x180007abe  movaps  xmm0, [rbp+3Fh+var_B0]
0x180007ac2  movups  xmmword ptr [r15+10h], xmm1
0x180007ac7  movaps  xmm1, xmmword ptr [rbp-61h]
0x180007acb  movups  xmmword ptr [r15+20h], xmm0
0x180007ad0  movaps  xmm0, [rbp+3Fh+var_90]
0x180007ad4  movups  xmmword ptr [r15+30h], xmm1
0x180007ad9  movups  xmmword ptr [r15+40h], xmm0
0x180007ade  jmp     loc_180007A02
0x180007ae3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007ae7  jz      loc_1800079B9
0x180007aed  jmp     short loc_180007B19
0x180007aef  cmp     r14d, 6
0x180007af3  jz      short loc_180007B57
0x180007af5  cmp     r14d, 8
0x180007af9  jnz     loc_1800079C7
0x180007aff  mov     rax, [rbx+1A98h]
0x180007b06  cmp     rax, rsi
0x180007b09  jz      loc_180007B9D
0x180007b0f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007b13  jz      loc_180007B9D
0x180007b19  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b20  test    byte ptr [rcx+1Ch], 2
0x180007b24  jz      loc_1800079C7
0x180007b2a  cmp     byte ptr [rcx+19h], 2
0x180007b2e  jb      loc_1800079C7
0x180007b34  mov     r9, [rbx+60h]
0x180007b38  lea     r8, WPP_7630e226a175390276defa9bbccaa0fe_Traceguids
0x180007b3f  mov     rcx, [rcx+10h]
0x180007b43  mov     edx, 33h ; '3'
0x180007b48  mov     [rsp+100h+ReturnLength], rsi
0x180007b4d  call    WPP_SF_ii
0x180007b52  jmp     loc_1800079C7
0x180007b57  mov     rcx, [rbx+0B8h]
0x180007b5e  jmp     loc_1800079B9
0x180007b63  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b6a  test    byte ptr [rcx+1Ch], 2
0x180007b6e  jz      loc_180007A02
0x180007b74  cmp     byte ptr [rcx+19h], 2
0x180007b78  jb      loc_180007A02
0x180007b7e  mov     rcx, [rcx+10h]; LoggerHandle
0x180007b82  mov     edx, 31h ; '1'
0x180007b87  mov     dword ptr [rsp+100h+var_D8], eax; char
0x180007b8b  mov     r9, rbx
0x180007b8e  mov     [rsp+100h+ReturnLength], rsi; pSid
0x180007b93  call    WPP_SF_S_sid_d
0x180007b98  jmp     loc_180007A02
0x180007b9d  mov     rcx, [rbx+0C8h]
0x180007ba4  jmp     loc_1800079B9
```
