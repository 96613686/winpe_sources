# PEPerformInitializationChecks

- ea: `0x18007e1c0`
- end: `0x18007e392`
- name: `PEPerformInitializationChecks`
- size: `466`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18007e398`

## callees

- `0x18000ec18`
- `0x180020634`
- `0x18007df70`
- `0x18007e038`
- `0x18007e1c0`
- `0x1800a3fb4`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x18007e2e0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18007e2e0`
- `ntoskrnl!ZwClose` at `0x18007e2bc`
- `ntoskrnl!ZwClose` at `0x18007e2bc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18007e31d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18007e34b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18007e31d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18007e34b`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x18007e2f5`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x18007e2f5`
- `ntoskrnl!ExReleaseResourceLite` at `0x18007e311`
- `ntoskrnl!ExReleaseResourceLite` at `0x18007e33f`
- `ntoskrnl!ExReleaseResourceLite` at `0x18007e311`
- `ntoskrnl!ExReleaseResourceLite` at `0x18007e33f`
- `ntoskrnl!PsCreateSystemThread` at `0x18007e292`
- `ntoskrnl!PsCreateSystemThread` at `0x18007e292`

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
0x18007e1c0  mov     r11, rsp
0x18007e1c3  mov     [r11+8], rbx
0x18007e1c7  mov     [r11+10h], rdi
0x18007e1cb  push    rbp
0x18007e1cc  mov     rbp, rsp
0x18007e1cf  sub     rsp, 70h
0x18007e1d3  xor     eax, eax
0x18007e1d5  mov     [rbp+ThreadHandle], 0
0x18007e1dd  mov     dword ptr [rbp+ObjectAttributes+4], eax
0x18007e1e0  mov     r8d, edx
0x18007e1e3  mov     dword ptr [rbp+ObjectAttributes+1Ch], eax
0x18007e1e6  mov     rbx, rcx
0x18007e1e9  cmp     edx, 48h ; 'H'
0x18007e1ec  jb      loc_18007E378
0x18007e1f2  mov     r9d, [rcx+18h]
0x18007e1f6  lea     edx, [r9+48h]
0x18007e1fa  cmp     edx, 48h ; 'H'
0x18007e1fd  jb      loc_18007E378
0x18007e203  mov     ecx, [rcx+28h]
0x18007e206  add     ecx, edx
0x18007e208  cmp     ecx, edx
0x18007e20a  jb      loc_18007E378
0x18007e210  cmp     ecx, r8d
0x18007e213  ja      loc_18007E378
0x18007e219  cmp     ecx, [rbx+4]
0x18007e21c  jnz     loc_18007E378
0x18007e222  lea     rax, [rbx+48h]
0x18007e226  cmp     [rbx+10h], rax
0x18007e22a  jnz     loc_18007E378
0x18007e230  lea     rcx, [r9+48h]
0x18007e234  add     rcx, rbx
0x18007e237  cmp     [rbx+20h], rcx
0x18007e23b  jnz     loc_18007E378
0x18007e241  mov     qword ptr [r11-48h], 1
0x18007e249  lea     rax, PEWorkerThread
0x18007e250  xorps   xmm0, xmm0
0x18007e253  mov     [r11-50h], rax
0x18007e257  xor     r9d, r9d; ProcessHandle
0x18007e25a  mov     qword ptr [r11-58h], 0
0x18007e262  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18007e266  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18007e26d  mov     edx, 1FFFFFh; DesiredAccess
0x18007e272  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18007e27a  lea     rcx, [rbp+ThreadHandle]; ThreadHandle
0x18007e27e  mov     [rbp+ObjectAttributes.Attributes], 200h
0x18007e285  mov     [rbp+ObjectAttributes.ObjectName], 0
0x18007e28d  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18007e292  call    cs:__imp_PsCreateSystemThread
0x18007e299  nop     dword ptr [rax+rax+00h]
0x18007e29e  test    eax, eax
0x18007e2a0  jns     short loc_18007E2B8
0x18007e2a2  xor     edx, edx
0x18007e2a4  lea     ecx, [rdx+1]
0x18007e2a7  call    PEAuthStoreParameter
0x18007e2ac  mov     cs:g_PEAuthStateVariables, 0
0x18007e2b6  jmp     short loc_18007E2C8
0x18007e2b8  mov     rcx, [rbp+ThreadHandle]; Handle
0x18007e2bc  call    cs:__imp_ZwClose
0x18007e2c3  nop     dword ptr [rax+rax+00h]
0x18007e2c8  lea     rcx, [rbx+34h]
0x18007e2cc  call    PEAuthSetDebugCredentialsData
0x18007e2d1  mov     edi, eax
0x18007e2d3  test    eax, eax
0x18007e2d5  js      loc_18007E37D
0x18007e2db  call    I_PELoadGRL
0x18007e2e0  call    cs:__imp_KeEnterCriticalRegion
0x18007e2e7  nop     dword ptr [rax+rax+00h]
0x18007e2ec  mov     dl, 1; Wait
0x18007e2ee  lea     rcx, g_GRLContextLock; Resource
0x18007e2f5  call    cs:__imp_ExAcquireResourceSharedLite
0x18007e2fc  nop     dword ptr [rax+rax+00h]
0x18007e301  cmp     cs:g_fGRLLoadFailed, 0
0x18007e308  lea     rcx, g_GRLContextLock; Resource
0x18007e30f  jz      short loc_18007E33F
0x18007e311  call    cs:__imp_ExReleaseResourceLite
0x18007e318  nop     dword ptr [rax+rax+00h]
0x18007e31d  call    cs:__imp_KeLeaveCriticalRegion
0x18007e324  nop     dword ptr [rax+rax+00h]
0x18007e329  xor     edx, edx
0x18007e32b  lea     ecx, [rdx+1]
0x18007e32e  call    PEAuthStoreParameter
0x18007e333  mov     cs:g_PEAuthStateVariables, 0
0x18007e33d  jmp     short loc_18007E37D
0x18007e33f  call    cs:__imp_ExReleaseResourceLite
0x18007e346  nop     dword ptr [rax+rax+00h]
0x18007e34b  call    cs:__imp_KeLeaveCriticalRegion
0x18007e352  nop     dword ptr [rax+rax+00h]
0x18007e357  mov     r9d, [rbx+28h]; size_t
0x18007e35b  mov     r8, [rbx+20h]; void *
0x18007e35f  mov     edx, [rbx+18h]; Size
0x18007e362  mov     rcx, [rbx+10h]; Src
0x18007e366  call    I_PESaveCertificates
0x18007e36b  mov     edi, eax
0x18007e36d  test    eax, eax
0x18007e36f  js      short loc_18007E37D
0x18007e371  call    I_PEVerifyAndLogPEAuthCerts
0x18007e376  jmp     short loc_18007E37D
0x18007e378  mov     edi, 0C0000206h
0x18007e37d  lea     r11, [rsp+70h+var_s0]
0x18007e382  mov     eax, edi
0x18007e384  mov     rbx, [r11+10h]
0x18007e388  mov     rdi, [r11+18h]
0x18007e38c  mov     rsp, r11
0x18007e38f  pop     rbp
0x18007e390  retn
```
