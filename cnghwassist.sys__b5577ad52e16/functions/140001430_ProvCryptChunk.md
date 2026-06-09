# ProvCryptChunk

- ea: `0x140001430`
- end: `0x140001abd`
- name: `ProvCryptChunk`
- size: `1677`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1400012d4`

## callees

- `0x140001064`
- `0x140001430`
- `0x140002784`
- `0x140002970`
- `0x140002a2c`
- `0x140003268`
- `0x1400037ec`
- `0x140003dc0`
- `0x140003ec0`
- `0x1400041c0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14000187f`
- `ntoskrnl!KeInitializeEvent` at `0x14000187f`
- `ntoskrnl!ExAcquireFastMutex` at `0x140001626`
- `ntoskrnl!ExAcquireFastMutex` at `0x140001626`
- `ntoskrnl!MmIsKernelAddress` at `0x1400015a5`
- `ntoskrnl!MmIsKernelAddress` at `0x1400015c1`
- `ntoskrnl!MmIsKernelAddress` at `0x1400015d8`
- `ntoskrnl!MmIsKernelAddress` at `0x1400015f3`
- `ntoskrnl!MmIsKernelAddress` at `0x1400015a5`
- `ntoskrnl!MmIsKernelAddress` at `0x1400015c1`
- `ntoskrnl!MmIsKernelAddress` at `0x1400015d8`
- `ntoskrnl!MmIsKernelAddress` at `0x1400015f3`
- `ntoskrnl!IoFreeMdl` at `0x140001a62`
- `ntoskrnl!IoFreeMdl` at `0x140001a8b`
- `ntoskrnl!IoFreeMdl` at `0x140001a62`
- `ntoskrnl!IoFreeMdl` at `0x140001a8b`
- `ntoskrnl!IoAllocateMdl` at `0x140001696`
- `ntoskrnl!IoAllocateMdl` at `0x1400016fd`
- `ntoskrnl!IoAllocateMdl` at `0x140001696`
- `ntoskrnl!IoAllocateMdl` at `0x1400016fd`
- `ntoskrnl!ExReleaseFastMutex` at `0x140001643`
- `ntoskrnl!ExReleaseFastMutex` at `0x140001643`
- `ntoskrnl!KeGetCurrentIrql` at `0x140001545`
- `ntoskrnl!KeGetCurrentIrql` at `0x140001545`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400016d6`
- `ntoskrnl!MmProbeAndLockPages` at `0x140001739`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400016d6`
- `ntoskrnl!MmProbeAndLockPages` at `0x140001739`
- `ntoskrnl!MmUnlockPages` at `0x140001a53`
- `ntoskrnl!MmUnlockPages` at `0x140001a7c`
- `ntoskrnl!MmUnlockPages` at `0x140001a53`
- `ntoskrnl!MmUnlockPages` at `0x140001a7c`
- `cng!BCryptDecrypt` at `0x140001a13`
- `cng!BCryptDecrypt` at `0x140001a13`
- `cng!BCryptEncrypt` at `0x140001a21`
- `cng!BCryptEncrypt` at `0x140001a21`

## pseudocode

```c
__int64 __fastcall ProvCryptChunk(
        __int64 a1,
        UCHAR *a2,
        unsigned int a3,
        void *a4,
        UCHAR *Src,
        ULONG Size,
        UCHAR *VirtualAddress,
        ULONG cbOutput,
        ULONG *a9,
        ULONG a10)
{
  __int64 v10; // r12
  struct _MDL *v13; // r13
  int *v14; // r8
  KIRQL CurrentIrql; // al
  unsigned int v16; // eax
  ULONG dwFlags; // eax
  struct _MDL *Mdl; // rax
  ULONG *pcbResult; // r8
  void *v20; // r9
  int v21; // r11d
  struct _MDL *v22; // rax
  __int128 v23; // xmm0
  unsigned int v24; // esi
  UCHAR *v25; // rcx
  ULONG cbIV; // edx
  void *v27; // rcx
  NTSTATUS v28; // eax
  UCHAR *Irp; // [rsp+20h] [rbp-198h]
  int v31; // [rsp+50h] [rbp-168h]
  char v32; // [rsp+54h] [rbp-164h]
  char v33; // [rsp+55h] [rbp-163h]
  int *v35; // [rsp+78h] [rbp-140h]
  struct _MDL *MemoryDescriptorList; // [rsp+88h] [rbp-130h]
  _QWORD v37[20]; // [rsp+C0h] [rbp-F8h] BYREF
  __int128 v38; // [rsp+160h] [rbp-58h] BYREF
  ULONG v39; // [rsp+208h] [rbp+50h]

  v10 = a3;
  memset(&v37[1], 0, 0x98u);
  MemoryDescriptorList = 0;
  v13 = 0;
  v33 = 0;
  v32 = 0;
  v31 = a10 & 0x8000;
  v39 = a10 & 0xFFFF7FFF;
  *(_BYTE *)(a1 + 13) = 1;
  v14 = g_config;
  if ( (unsigned int)g_config[16 * (unsigned __int64)(unsigned int)g_currentConfig + 11] >= (unsigned __int64)g_nBytesInQueues )
    v14 = &g_config[16 * (unsigned __int64)(unsigned int)g_currentConfig];
  v35 = v14;
  v37[0] = v14;
  CurrentIrql = KeGetCurrentIrql();
  if ( (unsigned int)v10 < v35[10]
    || CurrentIrql >= 2u
    || (((unsigned __int8)a2 | (unsigned __int8)((unsigned __int8)VirtualAddress | v10)) & 0x3F) != 0 )
  {
    goto LABEL_50;
  }
  if ( a2 != VirtualAddress )
  {
    v16 = (_DWORD)VirtualAddress - (_DWORD)a2;
    if ( (int)VirtualAddress - (int)a2 < 0 )
      v16 = (_DWORD)a2 - (_DWORD)VirtualAddress;
    if ( v16 < (unsigned int)v10 )
      goto LABEL_50;
  }
  dwFlags = v39;
  if ( (v39 & 1) != 0 )
  {
LABEL_51:
    pcbResult = a9;
    v20 = a4;
    v21 = v31;
LABEL_52:
    if ( Src )
    {
      v25 = Src;
      cbIV = Size;
    }
    else
    {
      v25 = *(UCHAR **)(a1 + 96);
      cbIV = *(_DWORD *)(a1 + 104);
    }
    Irp = v25;
    v27 = *(void **)(a1 + 16);
    if ( v21 )
      v28 = BCryptDecrypt(v27, a2, v10, v20, Irp, cbIV, VirtualAddress, cbOutput, pcbResult, dwFlags);
    else
      v28 = BCryptEncrypt(v27, a2, v10, v20, Irp, cbIV, VirtualAddress, cbOutput, pcbResult, dwFlags);
    v24 = v28;
    if ( Src )
      *(_OWORD *)(a1 + 40) = *(_OWORD *)Src;
    goto LABEL_60;
  }
  if ( !(unsigned __int8)MmIsKernelAddress(a2)
    || !(unsigned __int8)MmIsKernelAddress(&a2[v10 - 1])
    || !(unsigned __int8)MmIsKernelAddress(VirtualAddress)
    || !(unsigned __int8)MmIsKernelAddress(&VirtualAddress[v10 - 1])
    || !*(_QWORD *)(a1 + 24)
    && (((*(_BYTE *)(a1 + 108) == 0) & (unsigned __int8)g_fHwProvAvailable) == 0
     || (ExAcquireFastMutex(&g_mutexAddHardwareKey),
         AddHardwareKey(a1, 0),
         ExReleaseFastMutex(&g_mutexAddHardwareKey),
         !*(_QWORD *)(a1 + 24))) )
  {
LABEL_50:
    dwFlags = v39;
    goto LABEL_51;
  }
  HIDWORD(v37[11]) = 0;
  if ( (unsigned int)v10 >= v35[2] && *v35 )
  {
    if ( (v39 & 0x40) == 0 )
    {
      Mdl = IoAllocateMdl(VirtualAddress, v10, 0, 0, 0);
      v13 = Mdl;
      if ( !Mdl )
      {
        dwFlags = v39;
        pcbResult = a9;
        v20 = a4;
        v21 = v31;
        goto LABEL_52;
      }
      MmProbeAndLockPages(Mdl, 0, IoWriteAccess);
      v33 = 1;
      if ( a2 != VirtualAddress )
      {
        v22 = IoAllocateMdl(a2, v10, 0, 0, 0);
        MemoryDescriptorList = v22;
        if ( !v22 )
        {
          dwFlags = v39;
          pcbResult = a9;
          v20 = a4;
          v21 = v31;
          goto LABEL_52;
        }
        MmProbeAndLockPages(v22, 0, IoReadAccess);
        v32 = 1;
      }
    }
  }
  else
  {
    HIDWORD(v37[11]) = 1;
  }
  v37[1] = a1;
  LOBYTE(v37[2]) = v31 != 0;
  v37[3] = a2;
  LODWORD(v37[4]) = v10;
  if ( Src )
  {
    memmove(&v38, Src, Size);
    v37[5] = &v38;
    LODWORD(v37[6]) = 16;
  }
  else
  {
    v37[5] = *(_QWORD *)(a1 + 96);
    LODWORD(v37[6]) = *(_DWORD *)(a1 + 104);
  }
  v37[7] = VirtualAddress;
  LODWORD(v37[8]) = cbOutput;
  v37[9] = a9;
  LODWORD(v37[10]) = 0;
  HIDWORD(v37[10]) = v39;
  LODWORD(v37[11]) = 0;
  LODWORD(v37[19]) = 4;
  v37[12] = KeGetCurrentThread();
  KeInitializeEvent((PRKEVENT)&v37[13], NotificationEvent, 0);
  HIDWORD(v37[19]) = _InterlockedIncrement(&g_ulUnique);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_DD(WPP_GLOBAL_Control->AttachedDevice, 13);
  if ( ScheduleRequestNew((__int64)v37) )
    WaitForRequestEvent((__int64)v37);
  if ( LODWORD(v37[19]) != 3 )
  {
    if ( LODWORD(v37[19]) != 1 )
    {
      while ( 1 )
        ;
    }
LABEL_41:
    SoftwareCryptPiece(v37);
    if ( ScheduleRequestAfterSoftwarePiece((__int64)v37) )
      WaitForRequestEvent((__int64)v37);
    while ( LODWORD(v37[19]) != 3 )
    {
      if ( LODWORD(v37[19]) == 1 )
        goto LABEL_41;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_DD(WPP_GLOBAL_Control->AttachedDevice, 14);
  if ( Src )
  {
    v23 = v38;
    *(_OWORD *)(a1 + 40) = v38;
    *(_OWORD *)Src = v23;
  }
  v24 = v37[11];
  *(_DWORD *)v37[9] = v37[10];
LABEL_60:
  if ( MemoryDescriptorList )
  {
    if ( v32 )
      MmUnlockPages(MemoryDescriptorList);
    IoFreeMdl(MemoryDescriptorList);
  }
  if ( v13 )
  {
    if ( v33 )
      MmUnlockPages(v13);
    IoFreeMdl(v13);
  }
  return v24;
}

```

## disassembly

```asm
0x140001430  push    rbx
0x140001432  push    rsi
0x140001433  push    rdi
0x140001434  push    r12
0x140001436  push    r13
0x140001438  push    r14
0x14000143a  push    r15
0x14000143c  sub     rsp, 180h
0x140001443  mov     rax, cs:__security_cookie
0x14000144a  xor     rax, rsp
0x14000144d  mov     [rsp+1B8h+var_48], rax
0x140001455  mov     [rsp+1B8h+pPaddingInfo], r9
0x14000145a  mov     r12d, r8d
0x14000145d  mov     rsi, rdx
0x140001460  mov     rdi, rcx
0x140001463  mov     [rsp+1B8h+var_128], rcx
0x14000146b  mov     [rsp+1B8h+var_120], rdx
0x140001473  mov     [rsp+1B8h+var_150], r12d
0x140001478  mov     [rsp+1B8h+var_118], r9
0x140001480  mov     r15, [rsp+1B8h+Src]
0x140001488  mov     [rsp+1B8h+var_110], r15
0x140001490  mov     r14, [rsp+1B8h+VirtualAddress]
0x140001498  mov     [rsp+1B8h+var_108], r14
0x1400014a0  mov     rax, [rsp+1B8h+arg_40]
0x1400014a8  mov     [rsp+1B8h+var_160], rax
0x1400014ad  mov     [rsp+1B8h+var_100], rax
0x1400014b5  xor     edx, edx; Val
0x1400014b7  mov     r8d, 98h; Size
0x1400014bd  lea     rcx, [rsp+1B8h+var_F0]; void *
0x1400014c5  call    memset
0x1400014ca  xor     ebx, ebx
0x1400014cc  mov     [rsp+1B8h+MemoryDescriptorList], rbx
0x1400014d4  mov     r13d, ebx
0x1400014d7  mov     [rsp+1B8h+var_138], rbx
0x1400014df  mov     [rsp+1B8h+var_163], bl
0x1400014e3  mov     [rsp+1B8h+var_164], bl
0x1400014e7  mov     eax, [rsp+1B8h+arg_48]
0x1400014ee  mov     ecx, eax
0x1400014f0  and     ecx, 8000h
0x1400014f6  mov     [rsp+1B8h+var_168], ecx
0x1400014fa  mov     [rsp+1B8h+var_148], ecx
0x1400014fe  setnz   [rsp+1B8h+var_162]
0x140001503  btr     eax, 0Fh
0x140001507  mov     [rsp+1B8h+arg_48], eax
0x14000150e  mov     [rsp+1B8h+var_144], eax
0x140001512  mov     byte ptr [rdi+0Dh], 1
0x140001516  mov     edx, cs:g_currentConfig
0x14000151c  shl     rdx, 6
0x140001520  lea     r8, g_config
0x140001527  add     rdx, r8
0x14000152a  mov     ecx, [rdx+2Ch]
0x14000152d  cmp     rcx, cs:g_nBytesInQueues
0x140001534  cmovnb  r8, rdx
0x140001538  mov     [rsp+1B8h+var_140], r8
0x14000153d  mov     [rsp+1B8h+var_F8], r8
0x140001545  call    cs:__imp_KeGetCurrentIrql
0x14000154c  nop     dword ptr [rax+rax+00h]
0x140001551  mov     rcx, [rsp+1B8h+var_140]
0x140001556  cmp     r12d, [rcx+28h]
0x14000155a  jb      loc_1400019B1
0x140001560  cmp     al, 2
0x140001562  jnb     loc_1400019B1
0x140001568  mov     eax, r12d
0x14000156b  or      al, r14b
0x14000156e  or      al, sil
0x140001571  test    al, 3Fh
0x140001573  jnz     loc_1400019B1
0x140001579  cmp     rsi, r14
0x14000157c  jz      short loc_140001593
0x14000157e  mov     ecx, esi
0x140001580  sub     ecx, r14d
0x140001583  mov     eax, ecx
0x140001585  neg     eax
0x140001587  cmovs   eax, ecx
0x14000158a  cmp     eax, r12d
0x14000158d  jb      loc_1400019B1
0x140001593  mov     eax, [rsp+1B8h+arg_48]
0x14000159a  test    al, 1
0x14000159c  jnz     loc_1400019B8
0x1400015a2  mov     rcx, rsi
0x1400015a5  call    cs:__imp_MmIsKernelAddress
0x1400015ac  nop     dword ptr [rax+rax+00h]
0x1400015b1  test    al, al
0x1400015b3  jz      loc_1400019B1
0x1400015b9  lea     rcx, [r12-1]
0x1400015be  add     rcx, rsi
0x1400015c1  call    cs:__imp_MmIsKernelAddress
0x1400015c8  nop     dword ptr [rax+rax+00h]
0x1400015cd  test    al, al
0x1400015cf  jz      loc_1400019B1
0x1400015d5  mov     rcx, r14
0x1400015d8  call    cs:__imp_MmIsKernelAddress
0x1400015df  nop     dword ptr [rax+rax+00h]
0x1400015e4  test    al, al
0x1400015e6  jz      loc_1400019B1
0x1400015ec  lea     rcx, [r14-1]
0x1400015f0  add     rcx, r12
0x1400015f3  call    cs:__imp_MmIsKernelAddress
0x1400015fa  nop     dword ptr [rax+rax+00h]
0x1400015ff  test    al, al
0x140001601  jz      loc_1400019B1
0x140001607  cmp     [rdi+18h], rbx
0x14000160b  jnz     short loc_140001659
0x14000160d  cmp     [rdi+6Ch], bl
0x140001610  setz    cl
0x140001613  test    cs:g_fHwProvAvailable, cl
0x140001619  jz      loc_1400019B1
0x14000161f  lea     rcx, g_mutexAddHardwareKey; FastMutex
0x140001626  call    cs:__imp_ExAcquireFastMutex
0x14000162d  nop     dword ptr [rax+rax+00h]
0x140001632  xor     edx, edx
0x140001634  mov     rcx, rdi
0x140001637  call    AddHardwareKey
0x14000163c  lea     rcx, g_mutexAddHardwareKey; FastMutex
0x140001643  call    cs:__imp_ExReleaseFastMutex
0x14000164a  nop     dword ptr [rax+rax+00h]
0x14000164f  cmp     [rdi+18h], rbx
0x140001653  jz      loc_1400019B1
0x140001659  mov     [rsp+1B8h+var_9C], ebx
0x140001660  mov     rax, [rsp+1B8h+var_140]
0x140001665  cmp     r12d, [rax+8]
0x140001669  jb      loc_140001799
0x14000166f  cmp     [rax], ebx
0x140001671  jz      loc_140001799
0x140001677  test    byte ptr [rsp+1B8h+arg_48], 40h
0x14000167f  jnz     loc_1400017A4
0x140001685  mov     [rsp+1B8h+Irp], rbx; Irp
0x14000168a  xor     r9d, r9d; ChargeQuota
0x14000168d  xor     r8d, r8d; SecondaryBuffer
0x140001690  mov     edx, r12d; Length
0x140001693  mov     rcx, r14; VirtualAddress
0x140001696  call    cs:__imp_IoAllocateMdl
0x14000169d  nop     dword ptr [rax+rax+00h]
0x1400016a2  mov     r13, rax
0x1400016a5  mov     [rsp+1B8h+var_138], rax
0x1400016ad  test    rax, rax
0x1400016b0  jnz     short loc_1400016CD
0x1400016b2  mov     eax, [rsp+1B8h+arg_48]
0x1400016b9  mov     r8, [rsp+1B8h+var_160]
0x1400016be  mov     r9, [rsp+1B8h+pPaddingInfo]
0x1400016c3  mov     r11d, [rsp+1B8h+var_168]
0x1400016c8  jmp     loc_1400019C7
0x1400016cd  xor     edx, edx; AccessMode
0x1400016cf  lea     r8d, [rdx+1]; Operation
0x1400016d3  mov     rcx, rax; MemoryDescriptorList
0x1400016d6  call    cs:__imp_MmProbeAndLockPages
0x1400016dd  nop     dword ptr [rax+rax+00h]
0x1400016e2  mov     [rsp+1B8h+var_163], 1
0x1400016e7  cmp     rsi, r14
0x1400016ea  jz      short loc_14000174A
0x1400016ec  mov     [rsp+1B8h+Irp], rbx; Irp
0x1400016f1  xor     r9d, r9d; ChargeQuota
0x1400016f4  xor     r8d, r8d; SecondaryBuffer
0x1400016f7  mov     edx, r12d; Length
0x1400016fa  mov     rcx, rsi; VirtualAddress
0x1400016fd  call    cs:__imp_IoAllocateMdl
0x140001704  nop     dword ptr [rax+rax+00h]
0x140001709  mov     [rsp+1B8h+MemoryDescriptorList], rax
0x140001711  test    rax, rax
0x140001714  jnz     short loc_140001731
0x140001716  mov     eax, [rsp+1B8h+arg_48]
0x14000171d  mov     r8, [rsp+1B8h+var_160]
0x140001722  mov     r9, [rsp+1B8h+pPaddingInfo]
0x140001727  mov     r11d, [rsp+1B8h+var_168]
0x14000172c  jmp     loc_1400019C7
0x140001731  xor     r8d, r8d; Operation
0x140001734  xor     edx, edx; AccessMode
0x140001736  mov     rcx, rax; MemoryDescriptorList
0x140001739  call    cs:__imp_MmProbeAndLockPages
0x140001740  nop     dword ptr [rax+rax+00h]
0x140001745  mov     [rsp+1B8h+var_164], 1
0x14000174a  jmp     short loc_1400017A4
0x14000174c  xor     ebx, ebx
0x14000174e  mov     r13, [rsp+1B8h+var_138]
0x140001756  mov     rdi, [rsp+1B8h+var_128]
0x14000175e  mov     rsi, [rsp+1B8h+var_120]
0x140001766  mov     r12d, [rsp+1B8h+var_150]
0x14000176b  mov     r9, [rsp+1B8h+var_118]
0x140001773  mov     r15, [rsp+1B8h+var_110]
0x14000177b  mov     r14, [rsp+1B8h+var_108]
0x140001783  mov     r8, [rsp+1B8h+var_100]
0x14000178b  mov     r11d, [rsp+1B8h+var_148]
0x140001790  mov     eax, [rsp+1B8h+var_144]
0x140001794  jmp     loc_1400019C7
0x140001799  mov     [rsp+1B8h+var_9C], 1
0x1400017a4  mov     [rsp+1B8h+var_F0], rdi
0x1400017ac  mov     al, [rsp+1B8h+var_162]
0x1400017b0  mov     [rsp+1B8h+var_E8], al
0x1400017b7  mov     [rsp+1B8h+var_E0], rsi
0x1400017bf  mov     [rsp+1B8h+var_D8], r12d
0x1400017c7  test    r15, r15
0x1400017ca  jz      short loc_140001801
0x1400017cc  mov     r8d, dword ptr [rsp+1B8h+Size]; Size
0x1400017d4  mov     rdx, r15; Src
0x1400017d7  lea     rcx, [rsp+1B8h+var_58]; void *
0x1400017df  call    memmove
0x1400017e4  lea     rax, [rsp+1B8h+var_58]
0x1400017ec  mov     [rsp+1B8h+var_D0], rax
0x1400017f4  mov     [rsp+1B8h+var_C8], 10h
0x1400017ff  jmp     short loc_140001817
0x140001801  mov     rax, [rdi+60h]
0x140001805  mov     [rsp+1B8h+var_D0], rax
0x14000180d  mov     eax, [rdi+68h]
0x140001810  mov     [rsp+1B8h+var_C8], eax
0x140001817  mov     [rsp+1B8h+var_C0], r14
0x14000181f  mov     eax, [rsp+1B8h+arg_38]
0x140001826  mov     [rsp+1B8h+var_B8], eax
0x14000182d  mov     rax, [rsp+1B8h+var_160]
0x140001832  mov     [rsp+1B8h+var_B0], rax
0x14000183a  mov     [rsp+1B8h+var_A8], ebx
0x140001841  mov     eax, [rsp+1B8h+arg_48]
0x140001848  mov     [rsp+1B8h+var_A4], eax
0x14000184f  mov     [rsp+1B8h+var_A0], ebx
0x140001856  mov     [rsp+1B8h+var_60], 4
0x140001861  mov     rax, gs:188h
0x14000186a  mov     [rsp+1B8h+var_98], rax
0x140001872  xor     r8d, r8d; State
0x140001875  xor     edx, edx; Type
0x140001877  lea     rcx, [rsp+1B8h+Event]; Event
0x14000187f  call    cs:__imp_KeInitializeEvent
0x140001886  nop     dword ptr [rax+rax+00h]
0x14000188b  mov     esi, 1
0x140001890  mov     r9d, esi
0x140001893  lock xadd cs:g_ulUnique, r9d
0x14000189c  add     r9d, esi
0x14000189f  mov     [rsp+1B8h+var_5C], r9d
0x1400018a7  lea     r14, WPP_GLOBAL_Control
0x1400018ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400018b5  cmp     rcx, r14
0x1400018b8  jz      short loc_1400018D8
0x1400018ba  mov     eax, [rcx+2Ch]
0x1400018bd  test    al, 4
0x1400018bf  jz      short loc_1400018D8
0x1400018c1  lea     edx, [rsi+0Ch]
0x1400018c4  mov     eax, [rsp+1B8h+var_D8]
0x1400018cb  mov     dword ptr [rsp+1B8h+Irp], eax
0x1400018cf  mov     rcx, [rcx+18h]
0x1400018d3  call    WPP_SF_DD
0x1400018d8  lea     rcx, [rsp+1B8h+var_F8]
0x1400018e0  call    ScheduleRequestNew
0x1400018e5  test    al, al
0x1400018e7  jz      short loc_1400018F6
0x1400018e9  lea     rcx, [rsp+1B8h+var_F8]
0x1400018f1  call    WaitForRequestEvent
0x1400018f6  cmp     [rsp+1B8h+var_60], 3
0x1400018fe  jz      short loc_140001949
0x140001900  cmp     [rsp+1B8h+var_60], esi
0x140001907  jz      short loc_140001914
0x140001909  jmp     short loc_140001909
0x14000190b  cmp     [rsp+1B8h+var_60], esi
0x140001912  jnz     short loc_14000193F
0x140001914  lea     rcx, [rsp+1B8h+var_F8]
0x14000191c  call    SoftwareCryptPiece
0x140001921  lea     rcx, [rsp+1B8h+var_F8]
0x140001929  call    ScheduleRequestAfterSoftwarePiece
0x14000192e  test    al, al
0x140001930  jz      short loc_14000193F
0x140001932  lea     rcx, [rsp+1B8h+var_F8]
0x14000193a  call    WaitForRequestEvent
0x14000193f  cmp     [rsp+1B8h+var_60], 3
0x140001947  jnz     short loc_14000190B
0x140001949  mov     rcx, cs:WPP_GLOBAL_Control
0x140001950  cmp     rcx, r14
0x140001953  jz      short loc_14000197D
0x140001955  mov     eax, [rcx+2Ch]
0x140001958  test    al, 4
0x14000195a  jz      short loc_14000197D
0x14000195c  mov     edx, 0Eh
0x140001961  mov     eax, [rsp+1B8h+var_D8]
0x140001968  mov     dword ptr [rsp+1B8h+Irp], eax
0x14000196c  mov     r9d, [rsp+1B8h+var_5C]
0x140001974  mov     rcx, [rcx+18h]
0x140001978  call    WPP_SF_DD
0x14000197d  test    r15, r15
0x140001980  jz      short loc_140001994
0x140001982  movups  xmm0, [rsp+1B8h+var_58]
0x14000198a  movdqu  xmmword ptr [rdi+28h], xmm0
0x14000198f  movdqu  xmmword ptr [r15], xmm0
0x140001994  mov     esi, [rsp+1B8h+var_A0]
0x14000199b  mov     ecx, [rsp+1B8h+var_A8]
0x1400019a2  mov     rax, [rsp+1B8h+var_B0]
0x1400019aa  mov     [rax], ecx
0x1400019ac  jmp     loc_140001A3D
0x1400019b1  mov     eax, [rsp+1B8h+arg_48]
0x1400019b8  mov     r8, [rsp+1B8h+var_160]
0x1400019bd  mov     r9, [rsp+1B8h+pPaddingInfo]; pPaddingInfo
0x1400019c2  mov     r11d, [rsp+1B8h+var_168]
0x1400019c7  test    r15, r15
0x1400019ca  jz      short loc_1400019D8
0x1400019cc  mov     rcx, r15
0x1400019cf  mov     edx, dword ptr [rsp+1B8h+Size]
0x1400019d6  jmp     short loc_1400019DF
0x1400019d8  mov     rcx, [rdi+60h]
0x1400019dc  mov     edx, [rdi+68h]
0x1400019df  mov     r10, [rdi+10h]
0x1400019e3  mov     [rsp+1B8h+dwFlags], eax; dwFlags
0x1400019e7  mov     [rsp+1B8h+pcbResult], r8; pcbResult
0x1400019ec  mov     eax, [rsp+1B8h+arg_38]
0x1400019f3  mov     r8d, r12d; cbInput
0x1400019f6  mov     [rsp+1B8h+cbOutput], eax; cbOutput
  ... truncated ...
```
