# PEPerformInitializationChecks

- ea: `0x180080200`
- end: `0x1800803d2`
- name: `PEPerformInitializationChecks`
- size: `466`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800803d8`

## callees

- `0x18000ec28`
- `0x180020674`
- `0x18007ffb0`
- `0x180080078`
- `0x180080200`
- `0x1800a5238`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x180080320`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180080320`
- `ntoskrnl!ZwClose` at `0x1800802fc`
- `ntoskrnl!ZwClose` at `0x1800802fc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18008035d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18008038b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18008035d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18008038b`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180080335`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180080335`
- `ntoskrnl!ExReleaseResourceLite` at `0x180080351`
- `ntoskrnl!ExReleaseResourceLite` at `0x18008037f`
- `ntoskrnl!ExReleaseResourceLite` at `0x180080351`
- `ntoskrnl!ExReleaseResourceLite` at `0x18008037f`
- `ntoskrnl!PsCreateSystemThread` at `0x1800802d2`
- `ntoskrnl!PsCreateSystemThread` at `0x1800802d2`

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
0x180080200  mov     r11, rsp
0x180080203  mov     [r11+8], rbx
0x180080207  mov     [r11+10h], rdi
0x18008020b  push    rbp
0x18008020c  mov     rbp, rsp
0x18008020f  sub     rsp, 70h
0x180080213  xor     eax, eax
0x180080215  mov     [rbp+ThreadHandle], 0
0x18008021d  mov     dword ptr [rbp+ObjectAttributes+4], eax
0x180080220  mov     r8d, edx
0x180080223  mov     dword ptr [rbp+ObjectAttributes+1Ch], eax
0x180080226  mov     rbx, rcx
0x180080229  cmp     edx, 48h ; 'H'
0x18008022c  jb      loc_1800803B8
0x180080232  mov     r9d, [rcx+18h]
0x180080236  lea     edx, [r9+48h]
0x18008023a  cmp     edx, 48h ; 'H'
0x18008023d  jb      loc_1800803B8
0x180080243  mov     ecx, [rcx+28h]
0x180080246  add     ecx, edx
0x180080248  cmp     ecx, edx
0x18008024a  jb      loc_1800803B8
0x180080250  cmp     ecx, r8d
0x180080253  ja      loc_1800803B8
0x180080259  cmp     ecx, [rbx+4]
0x18008025c  jnz     loc_1800803B8
0x180080262  lea     rax, [rbx+48h]
0x180080266  cmp     [rbx+10h], rax
0x18008026a  jnz     loc_1800803B8
0x180080270  lea     rcx, [r9+48h]
0x180080274  add     rcx, rbx
0x180080277  cmp     [rbx+20h], rcx
0x18008027b  jnz     loc_1800803B8
0x180080281  mov     qword ptr [r11-48h], 1
0x180080289  lea     rax, PEWorkerThread
0x180080290  xorps   xmm0, xmm0
0x180080293  mov     [r11-50h], rax
0x180080297  xor     r9d, r9d; ProcessHandle
0x18008029a  mov     qword ptr [r11-58h], 0
0x1800802a2  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800802a6  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800802ad  mov     edx, 1FFFFFh; DesiredAccess
0x1800802b2  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1800802ba  lea     rcx, [rbp+ThreadHandle]; ThreadHandle
0x1800802be  mov     [rbp+ObjectAttributes.Attributes], 200h
0x1800802c5  mov     [rbp+ObjectAttributes.ObjectName], 0
0x1800802cd  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800802d2  call    cs:__imp_PsCreateSystemThread
0x1800802d9  nop     dword ptr [rax+rax+00h]
0x1800802de  test    eax, eax
0x1800802e0  jns     short loc_1800802F8
0x1800802e2  xor     edx, edx
0x1800802e4  lea     ecx, [rdx+1]
0x1800802e7  call    PEAuthStoreParameter
0x1800802ec  mov     cs:g_PEAuthStateVariables, 0
0x1800802f6  jmp     short loc_180080308
0x1800802f8  mov     rcx, [rbp+ThreadHandle]; Handle
0x1800802fc  call    cs:__imp_ZwClose
0x180080303  nop     dword ptr [rax+rax+00h]
0x180080308  lea     rcx, [rbx+34h]
0x18008030c  call    PEAuthSetDebugCredentialsData
0x180080311  mov     edi, eax
0x180080313  test    eax, eax
0x180080315  js      loc_1800803BD
0x18008031b  call    I_PELoadGRL
0x180080320  call    cs:__imp_KeEnterCriticalRegion
0x180080327  nop     dword ptr [rax+rax+00h]
0x18008032c  mov     dl, 1; Wait
0x18008032e  lea     rcx, g_GRLContextLock; Resource
0x180080335  call    cs:__imp_ExAcquireResourceSharedLite
0x18008033c  nop     dword ptr [rax+rax+00h]
0x180080341  cmp     cs:g_fGRLLoadFailed, 0
0x180080348  lea     rcx, g_GRLContextLock; Resource
0x18008034f  jz      short loc_18008037F
0x180080351  call    cs:__imp_ExReleaseResourceLite
0x180080358  nop     dword ptr [rax+rax+00h]
0x18008035d  call    cs:__imp_KeLeaveCriticalRegion
0x180080364  nop     dword ptr [rax+rax+00h]
0x180080369  xor     edx, edx
0x18008036b  lea     ecx, [rdx+1]
0x18008036e  call    PEAuthStoreParameter
0x180080373  mov     cs:g_PEAuthStateVariables, 0
0x18008037d  jmp     short loc_1800803BD
0x18008037f  call    cs:__imp_ExReleaseResourceLite
0x180080386  nop     dword ptr [rax+rax+00h]
0x18008038b  call    cs:__imp_KeLeaveCriticalRegion
0x180080392  nop     dword ptr [rax+rax+00h]
0x180080397  mov     r9d, [rbx+28h]; size_t
0x18008039b  mov     r8, [rbx+20h]; void *
0x18008039f  mov     edx, [rbx+18h]; Size
0x1800803a2  mov     rcx, [rbx+10h]; Src
0x1800803a6  call    I_PESaveCertificates
0x1800803ab  mov     edi, eax
0x1800803ad  test    eax, eax
0x1800803af  js      short loc_1800803BD
0x1800803b1  call    I_PEVerifyAndLogPEAuthCerts
0x1800803b6  jmp     short loc_1800803BD
0x1800803b8  mov     edi, 0C0000206h
0x1800803bd  lea     r11, [rsp+70h+var_s0]
0x1800803c2  mov     eax, edi
0x1800803c4  mov     rbx, [r11+10h]
0x1800803c8  mov     rdi, [r11+18h]
0x1800803cc  mov     rsp, r11
0x1800803cf  pop     rbp
0x1800803d0  retn
```
