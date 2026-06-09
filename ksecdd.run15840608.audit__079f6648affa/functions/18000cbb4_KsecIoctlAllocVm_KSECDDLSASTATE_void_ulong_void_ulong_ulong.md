# KsecIoctlAllocVm(_KSECDDLSASTATE *,void *,ulong,void *,ulong,ulong *)

- ea: `0x18000cbb4`
- end: `0x18000d013`
- name: `?KsecIoctlAllocVm@@YAJPEAU_KSECDDLSASTATE@@PEAXK1KPEAK@Z`
- size: `1119`
- prototype: `__int64 __usercall@<rax>(struct _KSECDDLSASTATE *@<rcx>, void *@<rdx>, unsigned int@<r8d>, void *@<r9>, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800053e0`

## callees

- `0x180005b58`
- `0x180007a64`
- `0x180007bd8`
- `0x18000c7a0`
- `0x18000cbb4`
- `0x18000ded4`
- `0x18000df18`
- `0x18000e044`
- `0x180010208`
- `0x18001f5c0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x18000cd55`
- `ntoskrnl!ObfDereferenceObject` at `0x18000cda6`
- `ntoskrnl!ObfDereferenceObject` at `0x18000cd55`
- `ntoskrnl!ObfDereferenceObject` at `0x18000cda6`
- `ntoskrnl!ObOpenObjectByPointer` at `0x18000cd95`
- `ntoskrnl!ObOpenObjectByPointer` at `0x18000cd95`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x18000cf16`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x18000cfa8`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x18000cf16`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x18000cfa8`
- `ntoskrnl!ZwAllocateVirtualMemory` at `0x18000ce24`
- `ntoskrnl!ZwAllocateVirtualMemory` at `0x18000ce24`
- `ntoskrnl!PsIsProtectedProcess` at `0x18000cd10`
- `ntoskrnl!PsIsProtectedProcess` at `0x18000cd10`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x18000cc54`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x18000cc54`
- `ntoskrnl!ProbeForRead` at `0x18000cc7b`
- `ntoskrnl!ProbeForRead` at `0x18000cc7b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18000ccb8`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18000ccb8`
- `ntoskrnl!PsProcessType` at `0x18000cca7`
- `ntoskrnl!PsProcessType` at `0x18000cd78`
- `ntoskrnl!ZwClose` at `0x18000ce73`
- `ntoskrnl!ZwClose` at `0x18000cf2a`
- `ntoskrnl!ZwClose` at `0x18000cfb7`
- `ntoskrnl!ZwClose` at `0x18000ce73`
- `ntoskrnl!ZwClose` at `0x18000cf2a`
- `ntoskrnl!ZwClose` at `0x18000cfb7`

## pseudocode

```c
__int64 __fastcall KsecIoctlAllocVm(
        struct _KSECDDLSASTATE *a1,
        void *a2,
        __int64 a3,
        PVOID *a4,
        unsigned int a5,
        unsigned int *a6)
{
  NTSTATUS inserted; // ebx
  __int64 v10; // r8
  PVOID v11; // rbx
  NTSTATUS v12; // esi
  __int64 v13; // r8
  __int64 v14; // r8
  __int64 v15; // r8
  PVOID BaseAddress; // [rsp+40h] [rbp-58h] BYREF
  ULONG_PTR RegionSize; // [rsp+48h] [rbp-50h] BYREF
  PVOID Object[2]; // [rsp+50h] [rbp-48h] BYREF
  __int128 Handle; // [rsp+60h] [rbp-38h] BYREF
  HANDLE ProcessHandle; // [rsp+A8h] [rbp+10h] BYREF

  Handle = 0;
  BaseAddress = 0;
  ProcessHandle = 0;
  RegionSize = 0;
  if ( !a2 || !a4 || (_DWORD)a3 != 16 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_qqL(*((_QWORD *)WPP_GLOBAL_Control + 3), 41, a3, a2, a4, a3);
    return 3221225485LL;
  }
  if ( a5 >= 8 )
  {
    if ( ((unsigned __int8)a2 & 7) != 0 )
      ExRaiseDatatypeMisalignment();
    RtlCopyFromUser(&Handle, a2, 0x10u);
    ProbeForRead(a4, 8u, 8u);
    Object[0] = 0;
    inserted = ObReferenceObjectByHandle((HANDLE)Handle, 0, (POBJECT_TYPE)PsProcessType, 0, Object, 0);
    if ( inserted < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_qL(*((_QWORD *)WPP_GLOBAL_Control + 3), 43, v10, Handle, inserted);
      return (unsigned int)inserted;
    }
    v11 = Object[0];
    Object[1] = Object[0];
    if ( (unsigned int)PsIsProtectedProcess(Object[0]) )
    {
      v12 = ObOpenObjectByPointer(v11, 0x200u, 0, 0, (POBJECT_TYPE)PsProcessType, 0, &ProcessHandle);
      ObfDereferenceObject(v11);
      if ( v12 >= 0 )
      {
        BaseAddress = 0;
        RegionSize = DWORD2(Handle);
        v12 = ZwAllocateVirtualMemory(ProcessHandle, &BaseAddress, 0, &RegionSize, 0x1000u, 4u);
        if ( v12 >= 0 )
        {
          inserted = KsecInsertValidVm(
                       a1,
                       ProcessHandle,
                       (struct _EPROCESS *)v11,
                       (unsigned __int8 *)BaseAddress,
                       DWORD2(Handle),
                       0);
          if ( inserted >= 0 )
          {
            RtlWriteULong64ToUser(a4, BaseAddress);
            *a4 = BaseAddress;
            *a6 = 8;
            return 0;
          }
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
            WPP_SF_qqL(*((_QWORD *)WPP_GLOBAL_Control + 3), 47, v15, ProcessHandle, BaseAddress, inserted);
          RegionSize = DWORD2(Handle);
          ZwFreeVirtualMemory(ProcessHandle, &BaseAddress, &RegionSize, 0x8000u);
          ZwClose(ProcessHandle);
          return (unsigned int)inserted;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
          WPP_SF_qL(*((_QWORD *)WPP_GLOBAL_Control + 3), 46, v14, ProcessHandle, v12);
        ZwClose(ProcessHandle);
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      {
        WPP_SF_qL(*((_QWORD *)WPP_GLOBAL_Control + 3), 45, v13, v11, v12);
      }
      return (unsigned int)v12;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 3), 44, WPP_aba6cc221655371604011c64d2fbf4cc_Traceguids, v11);
    ObfDereferenceObject(v11);
    return 3221225485LL;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 3), 42, WPP_aba6cc221655371604011c64d2fbf4cc_Traceguids, a5);
  return 3221225507LL;
}

```

## disassembly

```asm
0x18000cbb4  mov     rax, rsp
0x18000cbb7  push    rbx
0x18000cbb8  push    rsi
0x18000cbb9  push    rdi
0x18000cbba  push    r14
0x18000cbbc  sub     rsp, 78h
0x18000cbc0  mov     rdi, r9
0x18000cbc3  mov     r9, rdx
0x18000cbc6  mov     r14, rcx
0x18000cbc9  xorps   xmm0, xmm0
0x18000cbcc  movups  xmmword ptr [rax-38h], xmm0
0x18000cbd0  mov     qword ptr [rax-58h], 0
0x18000cbd8  mov     qword ptr [rax+10h], 0
0x18000cbe0  mov     qword ptr [rax-50h], 0
0x18000cbe8  test    rdx, rdx
0x18000cbeb  jz      loc_18000CFD1
0x18000cbf1  test    rdi, rdi
0x18000cbf4  jz      loc_18000CFD1
0x18000cbfa  cmp     r8d, 10h
0x18000cbfe  jnz     loc_18000CFD1
0x18000cc04  cmp     [rsp+98h+arg_20], 8
0x18000cc0c  jnb     short loc_18000CC4E
0x18000cc0e  lea     rax, WPP_GLOBAL_Control
0x18000cc15  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc1c  cmp     rcx, rax
0x18000cc1f  jz      short loc_18000CC44
0x18000cc21  mov     eax, [rcx+2Ch]
0x18000cc24  test    al, 1
0x18000cc26  jz      short loc_18000CC44
0x18000cc28  lea     edx, [r8+1Ah]
0x18000cc2c  mov     r9d, [rsp+98h+arg_20]
0x18000cc34  lea     r8, WPP_aba6cc221655371604011c64d2fbf4cc_Traceguids
0x18000cc3b  mov     rcx, [rcx+18h]
0x18000cc3f  call    WPP_SF_D
0x18000cc44  mov     eax, 0C0000023h
0x18000cc49  jmp     loc_18000D008
0x18000cc4e  test    r9b, 7
0x18000cc52  jz      short loc_18000CC60
0x18000cc54  call    cs:__imp_ExRaiseDatatypeMisalignment
0x18000cc5b  nop     dword ptr [rax+rax+00h]
0x18000cc60  mov     r8d, 10h; Size
0x18000cc66  lea     rcx, [rsp+98h+Handle]; void *
0x18000cc6b  call    RtlCopyFromUser
0x18000cc70  mov     edx, 8; Length
0x18000cc75  mov     r8d, edx; Alignment
0x18000cc78  mov     rcx, rdi; Address
0x18000cc7b  call    cs:__imp_ProbeForRead
0x18000cc82  nop     dword ptr [rax+rax+00h]
0x18000cc87  nop
0x18000cc88  mov     [rsp+98h+var_48], 0
0x18000cc91  mov     [rsp+98h+HandleInformation], 0; HandleInformation
0x18000cc9a  lea     rax, [rsp+98h+var_48]
0x18000cc9f  mov     [rsp+98h+Object], rax; Object
0x18000cca4  xor     r9d, r9d; AccessMode
0x18000cca7  mov     r8, cs:__imp_PsProcessType
0x18000ccae  mov     r8, [r8]; ObjectType
0x18000ccb1  xor     edx, edx; DesiredAccess
0x18000ccb3  mov     rcx, [rsp+98h+Handle]; Handle
0x18000ccb8  call    cs:__imp_ObReferenceObjectByHandle
0x18000ccbf  nop     dword ptr [rax+rax+00h]
0x18000ccc4  mov     ebx, eax
0x18000ccc6  test    eax, eax
0x18000ccc8  jns     short loc_18000CD03
0x18000ccca  lea     rax, WPP_GLOBAL_Control
0x18000ccd1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ccd8  cmp     rcx, rax
0x18000ccdb  jz      short loc_18000CCFC
0x18000ccdd  mov     edx, [rcx+2Ch]
0x18000cce0  test    dl, 1
0x18000cce3  jz      short loc_18000CCFC
0x18000cce5  mov     edx, 2Bh ; '+'
0x18000ccea  mov     dword ptr [rsp+98h+Object], ebx
0x18000ccee  mov     r9, [rsp+98h+Handle]
0x18000ccf3  mov     rcx, [rcx+18h]
0x18000ccf7  call    WPP_SF_qL
0x18000ccfc  mov     eax, ebx
0x18000ccfe  jmp     loc_18000D008
0x18000cd03  mov     rbx, [rsp+98h+var_48]
0x18000cd08  mov     [rsp+98h+var_40], rbx
0x18000cd0d  mov     rcx, rbx
0x18000cd10  call    cs:__imp_PsIsProtectedProcess
0x18000cd17  nop     dword ptr [rax+rax+00h]
0x18000cd1c  test    eax, eax
0x18000cd1e  jnz     short loc_18000CD66
0x18000cd20  lea     rax, WPP_GLOBAL_Control
0x18000cd27  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cd2e  cmp     rcx, rax
0x18000cd31  jz      short loc_18000CD52
0x18000cd33  mov     eax, [rcx+2Ch]
0x18000cd36  test    al, 1
0x18000cd38  jz      short loc_18000CD52
0x18000cd3a  mov     edx, 2Ch ; ','
0x18000cd3f  mov     r9, rbx
0x18000cd42  lea     r8, WPP_aba6cc221655371604011c64d2fbf4cc_Traceguids
0x18000cd49  mov     rcx, [rcx+18h]
0x18000cd4d  call    WPP_SF_q
0x18000cd52  mov     rcx, rbx; Object
0x18000cd55  call    cs:__imp_ObfDereferenceObject
0x18000cd5c  nop     dword ptr [rax+rax+00h]
0x18000cd61  jmp     loc_18000D003
0x18000cd66  lea     rax, [rsp+98h+ProcessHandle]
0x18000cd6e  mov     [rsp+98h+var_68], rax; Handle
0x18000cd73  mov     byte ptr [rsp+98h+HandleInformation], 0; AccessMode
0x18000cd78  mov     rax, cs:__imp_PsProcessType
0x18000cd7f  mov     rcx, [rax]
0x18000cd82  mov     [rsp+98h+Object], rcx; ObjectType
0x18000cd87  xor     r9d, r9d; DesiredAccess
0x18000cd8a  xor     r8d, r8d; PassedAccessState
0x18000cd8d  mov     edx, 200h; HandleAttributes
0x18000cd92  mov     rcx, rbx; Object
0x18000cd95  call    cs:__imp_ObOpenObjectByPointer
0x18000cd9c  nop     dword ptr [rax+rax+00h]
0x18000cda1  mov     esi, eax
0x18000cda3  mov     rcx, rbx; Object
0x18000cda6  call    cs:__imp_ObfDereferenceObject
0x18000cdad  nop     dword ptr [rax+rax+00h]
0x18000cdb2  test    esi, esi
0x18000cdb4  jns     short loc_18000CDED
0x18000cdb6  lea     rax, WPP_GLOBAL_Control
0x18000cdbd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cdc4  cmp     rcx, rax
0x18000cdc7  jz      short loc_18000CDE6
0x18000cdc9  mov     edx, [rcx+2Ch]
0x18000cdcc  test    dl, 1
0x18000cdcf  jz      short loc_18000CDE6
0x18000cdd1  mov     edx, 2Dh ; '-'
0x18000cdd6  mov     dword ptr [rsp+98h+Object], esi
0x18000cdda  mov     r9, rbx
0x18000cddd  mov     rcx, [rcx+18h]
0x18000cde1  call    WPP_SF_qL
0x18000cde6  mov     eax, esi
0x18000cde8  jmp     loc_18000D008
0x18000cded  mov     [rsp+98h+BaseAddress], 0
0x18000cdf6  mov     eax, [rsp+98h+var_30]
0x18000cdfa  mov     [rsp+98h+RegionSize], rax
0x18000cdff  mov     dword ptr [rsp+98h+HandleInformation], 4; Protect
0x18000ce07  mov     dword ptr [rsp+98h+Object], 1000h; AllocationType
0x18000ce0f  lea     r9, [rsp+98h+RegionSize]; RegionSize
0x18000ce14  xor     r8d, r8d; ZeroBits
0x18000ce17  lea     rdx, [rsp+98h+BaseAddress]; BaseAddress
0x18000ce1c  mov     rcx, [rsp+98h+ProcessHandle]; ProcessHandle
0x18000ce24  call    cs:__imp_ZwAllocateVirtualMemory
0x18000ce2b  nop     dword ptr [rax+rax+00h]
0x18000ce30  mov     esi, eax
0x18000ce32  test    eax, eax
0x18000ce34  jns     short loc_18000CE84
0x18000ce36  lea     rax, WPP_GLOBAL_Control
0x18000ce3d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce44  cmp     rcx, rax
0x18000ce47  jz      short loc_18000CE6B
0x18000ce49  mov     edx, [rcx+2Ch]
0x18000ce4c  test    dl, 1
0x18000ce4f  jz      short loc_18000CE6B
0x18000ce51  mov     edx, 2Eh ; '.'
0x18000ce56  mov     dword ptr [rsp+98h+Object], esi
0x18000ce5a  mov     r9, [rsp+98h+ProcessHandle]
0x18000ce62  mov     rcx, [rcx+18h]
0x18000ce66  call    WPP_SF_qL
0x18000ce6b  mov     rcx, [rsp+98h+ProcessHandle]; Handle
0x18000ce73  call    cs:__imp_ZwClose
0x18000ce7a  nop     dword ptr [rax+rax+00h]
0x18000ce7f  jmp     loc_18000CDE6
0x18000ce84  mov     dword ptr [rsp+98h+HandleInformation], 0; unsigned int
0x18000ce8c  mov     eax, [rsp+98h+var_30]
0x18000ce90  mov     dword ptr [rsp+98h+Object], eax; unsigned int
0x18000ce94  mov     r9, [rsp+98h+BaseAddress]; unsigned __int8 *
0x18000ce99  mov     r8, rbx; struct _EPROCESS *
0x18000ce9c  mov     rdx, [rsp+98h+ProcessHandle]; void *
0x18000cea4  mov     rcx, r14; struct _KSECDDLSASTATE *
0x18000cea7  call    ?KsecInsertValidVm@@YAJPEAU_KSECDDLSASTATE@@PEAXPEAU_EPROCESS@@PEAEKK@Z; KsecInsertValidVm(_KSECDDLSASTATE *,void *,_EPROCESS *,uchar *,ulong,ulong)
0x18000ceac  mov     ebx, eax
0x18000ceae  test    eax, eax
0x18000ceb0  jns     loc_18000CF3B
0x18000ceb6  lea     rax, WPP_GLOBAL_Control
0x18000cebd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cec4  cmp     rcx, rax
0x18000cec7  jz      short loc_18000CEF5
0x18000cec9  mov     edx, [rcx+2Ch]
0x18000cecc  test    dl, 1
0x18000cecf  jz      short loc_18000CEF5
0x18000ced1  mov     edx, 2Fh ; '/'
0x18000ced6  mov     dword ptr [rsp+98h+HandleInformation], ebx
0x18000ceda  mov     rax, [rsp+98h+BaseAddress]
0x18000cedf  mov     [rsp+98h+Object], rax
0x18000cee4  mov     r9, [rsp+98h+ProcessHandle]
0x18000ceec  mov     rcx, [rcx+18h]
0x18000cef0  call    WPP_SF_qqL
0x18000cef5  mov     eax, [rsp+98h+var_30]
0x18000cef9  mov     [rsp+98h+RegionSize], rax
0x18000cefe  mov     r9d, 8000h; FreeType
0x18000cf04  lea     r8, [rsp+98h+RegionSize]; RegionSize
0x18000cf09  lea     rdx, [rsp+98h+BaseAddress]; BaseAddress
0x18000cf0e  mov     rcx, [rsp+98h+ProcessHandle]; ProcessHandle
0x18000cf16  call    cs:__imp_ZwFreeVirtualMemory
0x18000cf1d  nop     dword ptr [rax+rax+00h]
0x18000cf22  mov     rcx, [rsp+98h+ProcessHandle]; Handle
0x18000cf2a  call    cs:__imp_ZwClose
0x18000cf31  nop     dword ptr [rax+rax+00h]
0x18000cf36  jmp     loc_18000CCFC
0x18000cf3b  mov     rdx, [rsp+98h+BaseAddress]
0x18000cf40  mov     rcx, rdi
0x18000cf43  call    RtlWriteULong64ToUser
0x18000cf48  nop
0x18000cf49  mov     rax, [rsp+98h+BaseAddress]
0x18000cf4e  mov     [rdi], rax
0x18000cf51  mov     rax, [rsp+98h+arg_28]
0x18000cf59  mov     dword ptr [rax], 8
0x18000cf5f  xor     eax, eax
0x18000cf61  jmp     loc_18000D008
0x18000cf66  mov     rdx, [rsp+98h+BaseAddress]; unsigned __int8 *
0x18000cf6b  mov     rcx, [rsp+98h+var_40]; struct _EPROCESS *
0x18000cf70  call    KsecRemoveValidVm
0x18000cf75  mov     rbx, rax
0x18000cf78  cmp     rax, [rsp+98h+ProcessHandle]
0x18000cf80  jz      short loc_18000CF87
0x18000cf82  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x18000cf87  test    rbx, rbx
0x18000cf8a  jz      short loc_18000CFC3
0x18000cf8c  mov     ecx, [rsp+98h+var_30]
0x18000cf90  mov     [rsp+98h+RegionSize], rcx
0x18000cf95  mov     r9d, 8000h; FreeType
0x18000cf9b  lea     r8, [rsp+98h+RegionSize]; RegionSize
0x18000cfa0  lea     rdx, [rsp+98h+BaseAddress]; BaseAddress
0x18000cfa5  mov     rcx, rbx; ProcessHandle
0x18000cfa8  call    cs:__imp_ZwFreeVirtualMemory
0x18000cfaf  nop     dword ptr [rax+rax+00h]
0x18000cfb4  mov     rcx, rbx; Handle
0x18000cfb7  call    cs:__imp_ZwClose
0x18000cfbe  nop     dword ptr [rax+rax+00h]
0x18000cfc3  mov     eax, 0C0000005h
0x18000cfc8  jmp     short loc_18000D008
0x18000cfca  mov     eax, 0C0000005h
0x18000cfcf  jmp     short loc_18000D008
0x18000cfd1  lea     rax, WPP_GLOBAL_Control
0x18000cfd8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cfdf  cmp     rcx, rax
0x18000cfe2  jz      short loc_18000D003
0x18000cfe4  mov     eax, [rcx+2Ch]
0x18000cfe7  test    al, 1
0x18000cfe9  jz      short loc_18000D003
0x18000cfeb  mov     edx, 29h ; ')'
0x18000cff0  mov     dword ptr [rsp+98h+HandleInformation], r8d
0x18000cff5  mov     [rsp+98h+Object], rdi
0x18000cffa  mov     rcx, [rcx+18h]
0x18000cffe  call    WPP_SF_qqL
0x18000d003  mov     eax, 0C000000Dh
0x18000d008  add     rsp, 78h
0x18000d00c  pop     r14
0x18000d00e  pop     rdi
0x18000d00f  pop     rsi
0x18000d010  pop     rbx
0x18000d011  retn
```
