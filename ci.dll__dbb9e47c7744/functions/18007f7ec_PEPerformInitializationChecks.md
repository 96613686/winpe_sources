# PEPerformInitializationChecks

- ea: `0x18007f7ec`
- end: `0x18007f9be`
- name: `PEPerformInitializationChecks`
- size: `466`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18007f9c4`

## callees

- `0x18000ec18`
- `0x1800205a4`
- `0x18007f59c`
- `0x18007f664`
- `0x18007f7ec`
- `0x1800a55e4`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x18007f90c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18007f90c`
- `ntoskrnl!ZwClose` at `0x18007f8e8`
- `ntoskrnl!ZwClose` at `0x18007f8e8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18007f949`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18007f977`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18007f949`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18007f977`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x18007f921`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x18007f921`
- `ntoskrnl!ExReleaseResourceLite` at `0x18007f93d`
- `ntoskrnl!ExReleaseResourceLite` at `0x18007f96b`
- `ntoskrnl!ExReleaseResourceLite` at `0x18007f93d`
- `ntoskrnl!ExReleaseResourceLite` at `0x18007f96b`
- `ntoskrnl!PsCreateSystemThread` at `0x18007f8be`
- `ntoskrnl!PsCreateSystemThread` at `0x18007f8be`

## pseudocode

```c
__int64 __fastcall PEPerformInitializationChecks(__int64 a1, unsigned int a2)
{
  __int64 v4; // r9
  unsigned int v5; // edx
  unsigned int v6; // ecx
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v9; // edi
  __int64 v10; // r8
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *ThreadHandle; // [rsp+90h] [rbp+20h] BYREF

  ThreadHandle = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  if ( a2 >= 0x48
    && (v4 = *(unsigned int *)(a1 + 24), v5 = v4 + 72, (unsigned int)v4 < 0xFFFFFFB8)
    && (v6 = v5 + *(_DWORD *)(a1 + 40), v6 >= v5)
    && v6 <= a2
    && v6 == *(_DWORD *)(a1 + 4)
    && *(_QWORD *)(a1 + 16) == a1 + 72
    && *(_QWORD *)(a1 + 32) == a1 + v4 + 72 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 512;
    ObjectAttributes.ObjectName = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( PsCreateSystemThread(
           &ThreadHandle,
           0x1FFFFFu,
           &ObjectAttributes,
           0,
           0,
           (PKSTART_ROUTINE)PEWorkerThread,
           (PVOID)1) >= 0 )
    {
      ZwClose(ThreadHandle);
    }
    else
    {
      PEAuthStoreParameter(1, 0);
      g_PEAuthStateVariables = 0;
    }
    v9 = PEAuthSetDebugCredentialsData(a1 + 52);
    if ( v9 >= 0 )
    {
      I_PELoadGRL(v8, v7, v10);
      KeEnterCriticalRegion();
      ExAcquireResourceSharedLite(&g_GRLContextLock, 1u);
      if ( g_fGRLLoadFailed )
      {
        ExReleaseResourceLite(&g_GRLContextLock);
        KeLeaveCriticalRegion();
        PEAuthStoreParameter(1, 0);
        g_PEAuthStateVariables = 0;
      }
      else
      {
        ExReleaseResourceLite(&g_GRLContextLock);
        KeLeaveCriticalRegion();
        v9 = I_PESaveCertificates(
               *(void **)(a1 + 16),
               *(unsigned int *)(a1 + 24),
               *(void **)(a1 + 32),
               *(unsigned int *)(a1 + 40));
        if ( v9 >= 0 )
          I_PEVerifyAndLogPEAuthCerts();
      }
    }
  }
  else
  {
    return (unsigned int)-1073741306;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18007f7ec  mov     r11, rsp
0x18007f7ef  mov     [r11+8], rbx
0x18007f7f3  mov     [r11+10h], rdi
0x18007f7f7  push    rbp
0x18007f7f8  mov     rbp, rsp
0x18007f7fb  sub     rsp, 70h
0x18007f7ff  xor     eax, eax
0x18007f801  mov     [rbp+ThreadHandle], 0
0x18007f809  mov     dword ptr [rbp+ObjectAttributes+4], eax
0x18007f80c  mov     r8d, edx
0x18007f80f  mov     dword ptr [rbp+ObjectAttributes+1Ch], eax
0x18007f812  mov     rbx, rcx
0x18007f815  cmp     edx, 48h ; 'H'
0x18007f818  jb      loc_18007F9A4
0x18007f81e  mov     r9d, [rcx+18h]
0x18007f822  lea     edx, [r9+48h]
0x18007f826  cmp     edx, 48h ; 'H'
0x18007f829  jb      loc_18007F9A4
0x18007f82f  mov     ecx, [rcx+28h]
0x18007f832  add     ecx, edx
0x18007f834  cmp     ecx, edx
0x18007f836  jb      loc_18007F9A4
0x18007f83c  cmp     ecx, r8d
0x18007f83f  ja      loc_18007F9A4
0x18007f845  cmp     ecx, [rbx+4]
0x18007f848  jnz     loc_18007F9A4
0x18007f84e  lea     rax, [rbx+48h]
0x18007f852  cmp     [rbx+10h], rax
0x18007f856  jnz     loc_18007F9A4
0x18007f85c  lea     rcx, [r9+48h]
0x18007f860  add     rcx, rbx
0x18007f863  cmp     [rbx+20h], rcx
0x18007f867  jnz     loc_18007F9A4
0x18007f86d  mov     qword ptr [r11-48h], 1
0x18007f875  lea     rax, PEWorkerThread
0x18007f87c  xorps   xmm0, xmm0
0x18007f87f  mov     [r11-50h], rax
0x18007f883  xor     r9d, r9d; ProcessHandle
0x18007f886  mov     qword ptr [r11-58h], 0
0x18007f88e  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18007f892  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18007f899  mov     edx, 1FFFFFh; DesiredAccess
0x18007f89e  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18007f8a6  lea     rcx, [rbp+ThreadHandle]; ThreadHandle
0x18007f8aa  mov     [rbp+ObjectAttributes.Attributes], 200h
0x18007f8b1  mov     [rbp+ObjectAttributes.ObjectName], 0
0x18007f8b9  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18007f8be  call    cs:__imp_PsCreateSystemThread
0x18007f8c5  nop     dword ptr [rax+rax+00h]
0x18007f8ca  test    eax, eax
0x18007f8cc  jns     short loc_18007F8E4
0x18007f8ce  xor     edx, edx
0x18007f8d0  lea     ecx, [rdx+1]
0x18007f8d3  call    PEAuthStoreParameter
0x18007f8d8  mov     cs:g_PEAuthStateVariables, 0
0x18007f8e2  jmp     short loc_18007F8F4
0x18007f8e4  mov     rcx, [rbp+ThreadHandle]; Handle
0x18007f8e8  call    cs:__imp_ZwClose
0x18007f8ef  nop     dword ptr [rax+rax+00h]
0x18007f8f4  lea     rcx, [rbx+34h]
0x18007f8f8  call    PEAuthSetDebugCredentialsData
0x18007f8fd  mov     edi, eax
0x18007f8ff  test    eax, eax
0x18007f901  js      loc_18007F9A9
0x18007f907  call    I_PELoadGRL
0x18007f90c  call    cs:__imp_KeEnterCriticalRegion
0x18007f913  nop     dword ptr [rax+rax+00h]
0x18007f918  mov     dl, 1; Wait
0x18007f91a  lea     rcx, g_GRLContextLock; Resource
0x18007f921  call    cs:__imp_ExAcquireResourceSharedLite
0x18007f928  nop     dword ptr [rax+rax+00h]
0x18007f92d  cmp     cs:g_fGRLLoadFailed, 0
0x18007f934  lea     rcx, g_GRLContextLock; Resource
0x18007f93b  jz      short loc_18007F96B
0x18007f93d  call    cs:__imp_ExReleaseResourceLite
0x18007f944  nop     dword ptr [rax+rax+00h]
0x18007f949  call    cs:__imp_KeLeaveCriticalRegion
0x18007f950  nop     dword ptr [rax+rax+00h]
0x18007f955  xor     edx, edx
0x18007f957  lea     ecx, [rdx+1]
0x18007f95a  call    PEAuthStoreParameter
0x18007f95f  mov     cs:g_PEAuthStateVariables, 0
0x18007f969  jmp     short loc_18007F9A9
0x18007f96b  call    cs:__imp_ExReleaseResourceLite
0x18007f972  nop     dword ptr [rax+rax+00h]
0x18007f977  call    cs:__imp_KeLeaveCriticalRegion
0x18007f97e  nop     dword ptr [rax+rax+00h]
0x18007f983  mov     r9d, [rbx+28h]; size_t
0x18007f987  mov     r8, [rbx+20h]; void *
0x18007f98b  mov     edx, [rbx+18h]; Size
0x18007f98e  mov     rcx, [rbx+10h]; Src
0x18007f992  call    I_PESaveCertificates
0x18007f997  mov     edi, eax
0x18007f999  test    eax, eax
0x18007f99b  js      short loc_18007F9A9
0x18007f99d  call    I_PEVerifyAndLogPEAuthCerts
0x18007f9a2  jmp     short loc_18007F9A9
0x18007f9a4  mov     edi, 0C0000206h
0x18007f9a9  lea     r11, [rsp+70h+var_s0]
0x18007f9ae  mov     eax, edi
0x18007f9b0  mov     rbx, [r11+10h]
0x18007f9b4  mov     rdi, [r11+18h]
0x18007f9b8  mov     rsp, r11
0x18007f9bb  pop     rbp
0x18007f9bc  retn
```
