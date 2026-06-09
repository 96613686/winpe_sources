# ConvertContainerSecurityDescriptor

- ea: `0x18004679c`
- end: `0x180046894`
- name: `ConvertContainerSecurityDescriptor`
- size: `248`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR AbsoluteSecurityDescriptor)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180004f8c`
- `0x180047254`

## callees

- `0x18000af80`
- `0x18000def0`
- `0x1800398b0`
- `0x18004679c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180046855`
- `ntdll!RtlNtStatusToDosError` at `0x180046855`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x1800467cc`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x1800467cc`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x180046877`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x180046877`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800467fe`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800467fe`

## string_xrefs

- `0x1800467ed`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`

## pseudocode

```c
ULONG __fastcall ConvertContainerSecurityDescriptor(
        PSECURITY_DESCRIPTOR AbsoluteSecurityDescriptor,
        _QWORD *a2,
        _DWORD *a3)
{
  NTSTATUS ControlSecurityDescriptor; // eax
  NTSTATUS v7; // ebx
  __int64 v8; // r9
  __int64 v9; // rcx
  void *v10; // rax
  size_t Size[7]; // [rsp+20h] [rbp-38h] BYREF
  WORD Control; // [rsp+78h] [rbp+20h] BYREF

  Size[0] = 0;
  Control = 0;
  ControlSecurityDescriptor = RtlGetControlSecurityDescriptor(AbsoluteSecurityDescriptor, &Control, (PULONG)Size + 1);
  v7 = ControlSecurityDescriptor;
  if ( ControlSecurityDescriptor >= 0 )
  {
    LODWORD(Size[0]) = GetSecurityDescriptorLength(AbsoluteSecurityDescriptor);
    v10 = (void *)SafeAllocaAllocateFromHeap(LODWORD(Size[0]));
    *a2 = v10;
    if ( !v10 )
    {
      v7 = -1073741801;
      v8 = 4397;
      v9 = 3221225495LL;
      goto LABEL_4;
    }
    if ( (Control & 0x8000u) == 0 )
    {
      ControlSecurityDescriptor = RtlAbsoluteToSelfRelativeSD(AbsoluteSecurityDescriptor, v10, (PULONG)Size);
      v7 = ControlSecurityDescriptor;
      if ( ControlSecurityDescriptor < 0 )
      {
        v8 = 4415;
        goto LABEL_3;
      }
    }
    else
    {
      memcpy_0(v10, AbsoluteSecurityDescriptor, LODWORD(Size[0]));
    }
    v7 = 0;
    *a3 = Size[0];
    return RtlNtStatusToDosError(v7);
  }
  v8 = 4387;
LABEL_3:
  v9 = (unsigned int)ControlSecurityDescriptor;
LABEL_4:
  DebugTraceError(v9, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c", v8);
  return RtlNtStatusToDosError(v7);
}

```

## disassembly

```asm
0x18004679c  push    rbx
0x18004679e  push    rsi
0x18004679f  push    rdi
0x1800467a0  push    r14
0x1800467a2  sub     rsp, 38h
0x1800467a6  xor     eax, eax
0x1800467a8  mov     dword ptr [rsp+58h+Size], 0
0x1800467b0  mov     rsi, r8
0x1800467b3  mov     [rsp+58h+Control], ax
0x1800467b8  mov     r14, rdx
0x1800467bb  mov     dword ptr [rsp+58h+Size+4], eax
0x1800467bf  lea     r8, [rsp+58h+Size+4]; Revision
0x1800467c4  mov     rdi, rcx
0x1800467c7  lea     rdx, [rsp+58h+Control]; Control
0x1800467cc  call    cs:__imp_RtlGetControlSecurityDescriptor
0x1800467d3  nop     dword ptr [rax+rax+00h]
0x1800467d8  mov     ebx, eax
0x1800467da  test    eax, eax
0x1800467dc  jns     short loc_1800467FB
0x1800467de  mov     r9d, 1123h
0x1800467e4  mov     ecx, eax
0x1800467e6  lea     rdx, aStatus; "Status"
0x1800467ed  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800467f4  call    DebugTraceError
0x1800467f9  jmp     short loc_180046853
0x1800467fb  mov     rcx, rdi; pSecurityDescriptor
0x1800467fe  call    cs:__imp_GetSecurityDescriptorLength
0x180046805  nop     dword ptr [rax+rax+00h]
0x18004680a  mov     ecx, eax
0x18004680c  mov     dword ptr [rsp+58h+Size], ecx
0x180046810  call    SafeAllocaAllocateFromHeap
0x180046815  mov     [r14], rax
0x180046818  test    rax, rax
0x18004681b  jnz     short loc_18004682F
0x18004681d  mov     ebx, 0C0000017h
0x180046822  mov     r9d, 112Dh
0x180046828  mov     ecx, 0C0000017h
0x18004682d  jmp     short loc_1800467E6
0x18004682f  mov     ecx, 8000h
0x180046834  test    [rsp+58h+Control], cx
0x180046839  jz      short loc_18004686C
0x18004683b  mov     r8d, dword ptr [rsp+58h+Size]; Size
0x180046840  mov     rdx, rdi; Src
0x180046843  mov     rcx, rax; void *
0x180046846  call    memcpy_0
0x18004684b  mov     eax, dword ptr [rsp+58h+Size]
0x18004684f  xor     ebx, ebx
0x180046851  mov     [rsi], eax
0x180046853  mov     ecx, ebx; Status
0x180046855  call    cs:__imp_RtlNtStatusToDosError
0x18004685c  nop     dword ptr [rax+rax+00h]
0x180046861  add     rsp, 38h
0x180046865  pop     r14
0x180046867  pop     rdi
0x180046868  pop     rsi
0x180046869  pop     rbx
0x18004686a  retn
0x18004686c  lea     r8, [rsp+58h+Size]; BufferLength
0x180046871  mov     rdx, rax; SelfRelativeSecurityDescriptor
0x180046874  mov     rcx, rdi; AbsoluteSecurityDescriptor
0x180046877  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x18004687e  nop     dword ptr [rax+rax+00h]
0x180046883  mov     ebx, eax
0x180046885  test    eax, eax
0x180046887  jns     short loc_18004684B
0x180046889  mov     r9d, 113Fh
0x18004688f  jmp     loc_1800467E4
```
