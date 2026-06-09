# I_CryptNetGetConnectivity

- ea: `0x180003b40`
- end: `0x180003d24`
- name: `I_CryptNetGetConnectivity`
- size: `484`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`
- `0x180007cc0`

## callees

- `0x180003020`
- `0x180003b40`
- `0x180003d30`
- `0x180003dd8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003b7a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003b7a`
- `CRYPT32!I_CertDiagControl` at `0x180003c4a`
- `CRYPT32!I_CertDiagControl` at `0x180003d05`
- `CRYPT32!I_CertDiagControl` at `0x180003c4a`
- `CRYPT32!I_CertDiagControl` at `0x180003d05`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003bc0`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003cd8`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003bc0`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003cd8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180003b8a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180003b8a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180003baa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180003baa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003c0e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003c63`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003c0e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003c63`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003c2e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003cb4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003c2e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003cb4`
- `IPHLPAPI!NotifyIpInterfaceChange` at `0x180003c96`
- `IPHLPAPI!NotifyIpInterfaceChange` at `0x180003c96`

## pseudocode

```c
__int64 I_CryptNetGetConnectivity()
{
  unsigned int v0; // edi
  int v1; // ebx
  LONG v2; // eax
  struct _FILETIME v3; // rcx
  int v4; // eax
  FILETIME v6; // [rsp+50h] [rbp+20h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp+28h] BYREF
  FILETIME FileTime2; // [rsp+60h] [rbp+30h] BYREF

  FileTime2 = 0;
  SystemTimeAsFileTime = 0;
  _InterlockedIncrement(&dword_180032920);
  if ( !(unsigned int)I_CryptIsAppContainerToken(0) || (unsigned int)I_CryptHasAppContainerNetworkCapability() )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    AcquireSRWLockShared(&SRWLock);
    v0 = dword_180032154;
    v1 = dword_180032150;
    FileTime2 = (FILETIME)qword_180032908;
    ReleaseSRWLockShared(&SRWLock);
    if ( v1 )
    {
      AcquireSRWLockExclusive(&SRWLock);
      _InterlockedExchange(&dword_180032150, 0);
      if ( !NotificationHandle )
      {
        NotifyIpInterfaceChange(0, IpNotifyCallback, 0, 0, &NotificationHandle);
        qword_180032908 = *(_QWORD *)&SystemTimeAsFileTime - 6000000000LL;
      }
      ReleaseSRWLockExclusive(&SRWLock);
    }
    else
    {
      v2 = CompareFileTime(&SystemTimeAsFileTime, &FileTime2);
      v3 = SystemTimeAsFileTime;
      if ( v2 <= 0 || (unsigned int)((*(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&FileTime2) / 0x989680uLL) < 0x12C )
      {
        v6 = (FILETIME)(*(_QWORD *)&SystemTimeAsFileTime + 6000000000LL);
        if ( CompareFileTime(&FileTime2, &v6) <= 0 )
        {
LABEL_11:
          v6.dwLowDateTime = v0 == 2;
          I_CertDiagControl(23, &v6, 0);
          return v0;
        }
      }
    }
    v4 = ((__int64 (__fastcall *)(_QWORD))CheckForUpInterface)(v3);
    if ( v4 )
    {
      v0 = 2;
      if ( v4 <= 0 )
        v0 = 0;
      AcquireSRWLockExclusive(&SRWLock);
      if ( dword_180032154 != v0 )
      {
        _InterlockedIncrement(&dword_180032928);
        dword_180032154 = v0;
      }
      qword_180032908 = (__int64)SystemTimeAsFileTime;
      ReleaseSRWLockExclusive(&SRWLock);
    }
    goto LABEL_11;
  }
  v6.dwLowDateTime = 0;
  I_CertDiagControl(23, &v6, 0);
  return 0;
}

```

## disassembly

```asm
0x180003b40  mov     [rsp-18h+arg_18], rbx
0x180003b45  push    rbp
0x180003b46  push    rdi
0x180003b47  push    r14
0x180003b49  mov     rbp, rsp
0x180003b4c  sub     rsp, 30h
0x180003b50  mov     qword ptr [rbp+FileTime2.dwLowDateTime], 0
0x180003b58  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180003b60  lock inc cs:dword_180032920
0x180003b67  xor     ecx, ecx
0x180003b69  call    I_CryptIsAppContainerToken
0x180003b6e  test    eax, eax
0x180003b70  jnz     loc_180003CEB
0x180003b76  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003b7a  call    cs:__imp_GetSystemTimeAsFileTime
0x180003b80  lea     r14, SRWLock
0x180003b87  mov     rcx, r14; SRWLock
0x180003b8a  call    cs:__imp_AcquireSRWLockShared
0x180003b90  mov     rax, cs:qword_180032908
0x180003b97  mov     rcx, r14; SRWLock
0x180003b9a  mov     edi, cs:dword_180032154
0x180003ba0  mov     ebx, cs:dword_180032150
0x180003ba6  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rax
0x180003baa  call    cs:__imp_ReleaseSRWLockShared
0x180003bb0  test    ebx, ebx
0x180003bb2  jnz     loc_180003C60
0x180003bb8  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x180003bbc  lea     rcx, [rbp+SystemTimeAsFileTime]; lpFileTime1
0x180003bc0  call    cs:__imp_CompareFileTime
0x180003bc6  mov     rcx, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003bca  test    eax, eax
0x180003bcc  jle     loc_180003CBF
0x180003bd2  mov     rdx, rcx
0x180003bd5  mov     rax, 0D6BF94D5E57A42BDh
0x180003bdf  sub     rdx, qword ptr [rbp+FileTime2.dwLowDateTime]
0x180003be3  mul     rdx
0x180003be6  shr     rdx, 17h
0x180003bea  cmp     edx, 12Ch
0x180003bf0  jb      loc_180003CBF
0x180003bf6  call    CheckForUpInterface
0x180003bfb  test    eax, eax
0x180003bfd  jz      short loc_180003C34
0x180003bff  xor     edx, edx
0x180003c01  mov     edi, 2
0x180003c06  test    eax, eax
0x180003c08  mov     rcx, r14; SRWLock
0x180003c0b  cmovle  edi, edx
0x180003c0e  call    cs:__imp_AcquireSRWLockExclusive
0x180003c14  cmp     cs:dword_180032154, edi
0x180003c1a  jnz     loc_180003D12
0x180003c20  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003c24  mov     rcx, r14; SRWLock
0x180003c27  mov     cs:qword_180032908, rax
0x180003c2e  call    cs:__imp_ReleaseSRWLockExclusive
0x180003c34  xor     ecx, ecx
0x180003c36  lea     rdx, [rbp+arg_0]
0x180003c3a  cmp     edi, 2
0x180003c3d  setz    cl
0x180003c40  xor     r8d, r8d
0x180003c43  mov     [rbp+arg_0.dwLowDateTime], ecx
0x180003c46  lea     ecx, [r8+17h]
0x180003c4a  call    cs:__imp_I_CertDiagControl
0x180003c50  mov     eax, edi
0x180003c52  mov     rbx, [rsp+30h+arg_18]
0x180003c57  add     rsp, 30h
0x180003c5b  pop     r14
0x180003c5d  pop     rdi
0x180003c5e  pop     rbp
0x180003c5f  retn
0x180003c60  mov     rcx, r14; SRWLock
0x180003c63  call    cs:__imp_AcquireSRWLockExclusive
0x180003c69  xor     eax, eax
0x180003c6b  xchg    eax, cs:dword_180032150
0x180003c71  cmp     cs:NotificationHandle, 0
0x180003c79  jnz     short loc_180003CB1
0x180003c7b  lea     rax, NotificationHandle
0x180003c82  xor     ecx, ecx; Family
0x180003c84  xor     r9d, r9d; InitialNotification
0x180003c87  mov     [rsp+30h+NotificationHandle], rax; NotificationHandle
0x180003c8c  xor     r8d, r8d; CallerContext
0x180003c8f  lea     rdx, IpNotifyCallback; Callback
0x180003c96  call    cs:__imp_NotifyIpInterfaceChange
0x180003c9c  mov     rcx, 0FFFFFFFE9A5F4400h
0x180003ca6  add     rcx, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003caa  mov     cs:qword_180032908, rcx
0x180003cb1  mov     rcx, r14; SRWLock
0x180003cb4  call    cs:__imp_ReleaseSRWLockExclusive
0x180003cba  jmp     loc_180003BF6
0x180003cbf  mov     rax, 165A0BC00h
0x180003cc9  lea     rdx, [rbp+arg_0]; lpFileTime2
0x180003ccd  add     rax, rcx
0x180003cd0  lea     rcx, [rbp+FileTime2]; lpFileTime1
0x180003cd4  mov     qword ptr [rbp+arg_0.dwLowDateTime], rax
0x180003cd8  call    cs:__imp_CompareFileTime
0x180003cde  test    eax, eax
0x180003ce0  jle     loc_180003C34
0x180003ce6  jmp     loc_180003BF6
0x180003ceb  call    I_CryptHasAppContainerNetworkCapability
0x180003cf0  test    eax, eax
0x180003cf2  jnz     loc_180003B76
0x180003cf8  xor     r8d, r8d
0x180003cfb  mov     [rbp+arg_0.dwLowDateTime], eax
0x180003cfe  lea     rdx, [rbp+arg_0]
0x180003d02  lea     ecx, [rax+17h]
0x180003d05  call    cs:__imp_I_CertDiagControl
0x180003d0b  xor     eax, eax
0x180003d0d  jmp     loc_180003C52
0x180003d12  lock inc cs:dword_180032928
0x180003d19  mov     cs:dword_180032154, edi
0x180003d1f  jmp     loc_180003C20
```
