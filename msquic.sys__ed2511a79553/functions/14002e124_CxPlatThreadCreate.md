# CxPlatThreadCreate

- ea: `0x14002e124`
- end: `0x14002e378`
- name: `CxPlatThreadCreate`
- size: `596`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140001510`

## callees

- `0x14002e124`
- `0x14003c8e0`
- `0x14003ce00`

## import_xrefs

- `ntoskrnl!strnlen` at `0x14002e2f2`
- `ntoskrnl!strnlen` at `0x14002e2f2`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14002e1df`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14002e1df`
- `ntoskrnl!KeSetBasePriorityThread` at `0x14002e2be`
- `ntoskrnl!KeSetBasePriorityThread` at `0x14002e2be`
- `ntoskrnl!PsCreateSystemThread` at `0x14002e178`
- `ntoskrnl!PsCreateSystemThread` at `0x14002e178`
- `ntoskrnl!RtlUTF8ToUnicodeN` at `0x14002e312`
- `ntoskrnl!RtlUTF8ToUnicodeN` at `0x14002e312`
- `ntoskrnl!PsThreadType` at `0x14002e193`
- `ntoskrnl!ZwSetInformationThread` at `0x14002e26e`
- `ntoskrnl!ZwSetInformationThread` at `0x14002e29b`
- `ntoskrnl!ZwSetInformationThread` at `0x14002e338`
- `ntoskrnl!ZwSetInformationThread` at `0x14002e26e`
- `ntoskrnl!ZwSetInformationThread` at `0x14002e29b`
- `ntoskrnl!ZwSetInformationThread` at `0x14002e338`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002e1b4`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002e1b4`
- `ntoskrnl!KeQueryLogicalProcessorRelationship` at `0x14002e246`
- `ntoskrnl!KeQueryLogicalProcessorRelationship` at `0x14002e246`
- `ntoskrnl!ZwClose` at `0x14002e34a`
- `ntoskrnl!ZwClose` at `0x14002e34a`

## pseudocode

```c
__int64 __fastcall CxPlatThreadCreate(__int64 a1, PVOID *a2)
{
  void *StartContext; // rax
  NTSTATUS v5; // ebx
  ULONG v6; // ecx
  bool v7; // zf
  void *GroupInfo; // r8
  const char *v9; // rcx
  ULONG v10; // eax
  _PROCESSOR_NUMBER ProcNumber; // [rsp+40h] [rbp-79h] BYREF
  ULONG Length; // [rsp+44h] [rbp-75h] BYREF
  void *ThreadHandle; // [rsp+48h] [rbp-71h] BYREF
  _PROCESSOR_NUMBER ThreadInformation; // [rsp+50h] [rbp-69h] BYREF
  PWSTR UnicodeStringDestination[2]; // [rsp+58h] [rbp-61h] BYREF
  _SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX Information; // [rsp+70h] [rbp-49h] BYREF

  StartContext = *(void **)(a1 + 24);
  ThreadHandle = 0;
  v5 = PsCreateSystemThread(&ThreadHandle, 0x1FFFFFu, 0, 0, 0, *(PKSTART_ROUTINE *)(a1 + 16), StartContext);
  if ( v5 >= 0 )
  {
    v5 = ObReferenceObjectByHandle(ThreadHandle, 0x1FFFFFu, (POBJECT_TYPE)PsThreadType, 0, a2, 0);
    if ( v5 < 0 )
    {
      *a2 = 0;
LABEL_18:
      ZwClose(ThreadHandle);
      return (unsigned int)v5;
    }
    v6 = *(unsigned __int16 *)(a1 + 2);
    ProcNumber = 0;
    ThreadInformation = 0;
    if ( KeGetProcessorNumberFromIndex(v6, &ProcNumber) >= 0 )
    {
      v7 = (*(_BYTE *)a1 & 2) == 0;
      ThreadInformation = ProcNumber;
      if ( v7 )
      {
        memset(&Information, 0, sizeof(Information));
        Length = 80;
        v5 = KeQueryLogicalProcessorRelationship(&ProcNumber, RelationNumaNode, &Information, &Length);
        if ( v5 < 0 )
          goto LABEL_18;
        GroupInfo = Information.Group.GroupInfo;
      }
      else
      {
        GroupInfo = UnicodeStringDestination;
        UnicodeStringDestination[1] = (PWSTR)ProcNumber.Group;
        UnicodeStringDestination[0] = (PWSTR)(1LL << ProcNumber.Number);
      }
      v5 = ZwSetInformationThread(ThreadHandle, MaxThreadInfoClass|ThreadPriority, GroupInfo, 0x10u);
      if ( v5 < 0 )
        goto LABEL_18;
      if ( (*(_BYTE *)a1 & 1) != 0 )
      {
        v5 = ZwSetInformationThread(ThreadHandle, (THREADINFOCLASS)33, &ThreadInformation, 4u);
        if ( v5 < 0 )
          goto LABEL_18;
      }
    }
    else
    {
      v5 = 0;
    }
    if ( (*(_BYTE *)a1 & 4) != 0 )
      KeSetBasePriorityThread((PKTHREAD)*a2, 3);
    v9 = *(const char **)(a1 + 8);
    if ( v9 )
    {
      Length = 0;
      WORD1(UnicodeStringDestination[0]) = 128;
      HIDWORD(UnicodeStringDestination[0]) = 0;
      UnicodeStringDestination[1] = (PWSTR)&Information;
      v10 = strnlen(v9, 0x40u);
      RtlUTF8ToUnicodeN(
        UnicodeStringDestination[1],
        WORD1(UnicodeStringDestination[0]),
        &Length,
        *(PCCH *)(a1 + 8),
        v10);
      LOWORD(UnicodeStringDestination[0]) = Length;
      ZwSetInformationThread(ThreadHandle, ThreadDescriptorTableEntry|0x20, UnicodeStringDestination, 0x10u);
      v5 = 0;
    }
    goto LABEL_18;
  }
  *a2 = 0;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14002e124  mov     [rsp-8+arg_10], rbx
0x14002e129  push    rbp
0x14002e12a  push    rsi
0x14002e12b  push    rdi
0x14002e12c  lea     rbp, [rsp-47h]
0x14002e131  sub     rsp, 100h
0x14002e138  mov     rax, cs:__security_cookie
0x14002e13f  xor     rax, rsp
0x14002e142  mov     [rbp+57h+var_20], rax
0x14002e146  mov     rax, [rcx+18h]
0x14002e14a  mov     rsi, rdx
0x14002e14d  and     [rbp+57h+ThreadHandle], 0
0x14002e152  mov     rdi, rcx
0x14002e155  mov     [rsp+110h+StartContext], rax; StartContext
0x14002e15a  xor     r9d, r9d; ProcessHandle
0x14002e15d  mov     rax, [rcx+10h]
0x14002e161  xor     r8d, r8d; ObjectAttributes
0x14002e164  mov     [rsp+110h+StartRoutine], rax; HandleInformation
0x14002e169  lea     rcx, [rbp+57h+ThreadHandle]; ThreadHandle
0x14002e16d  and     [rsp+110h+Object], 0
0x14002e173  mov     edx, 1FFFFFh; DesiredAccess
0x14002e178  call    cs:__imp_PsCreateSystemThread
0x14002e17f  nop     dword ptr [rax+rax+00h]
0x14002e184  mov     ebx, eax
0x14002e186  test    eax, eax
0x14002e188  jns     short loc_14002E193
0x14002e18a  and     qword ptr [rsi], 0
0x14002e18e  jmp     loc_14002E356
0x14002e193  mov     r8, cs:__imp_PsThreadType
0x14002e19a  xor     r9d, r9d; AccessMode
0x14002e19d  and     [rsp+110h+StartRoutine], 0
0x14002e1a3  mov     edx, 1FFFFFh; DesiredAccess
0x14002e1a8  mov     rcx, [rbp+57h+ThreadHandle]; Handle
0x14002e1ac  mov     [rsp+110h+Object], rsi; Object
0x14002e1b1  mov     r8, [r8]; ObjectType
0x14002e1b4  call    cs:__imp_ObReferenceObjectByHandle
0x14002e1bb  nop     dword ptr [rax+rax+00h]
0x14002e1c0  mov     ebx, eax
0x14002e1c2  test    eax, eax
0x14002e1c4  jns     short loc_14002E1CF
0x14002e1c6  and     qword ptr [rsi], 0
0x14002e1ca  jmp     loc_14002E346
0x14002e1cf  movzx   ecx, word ptr [rdi+2]; ProcIndex
0x14002e1d3  lea     rdx, [rbp+57h+ProcNumber]; ProcNumber
0x14002e1d7  and     dword ptr [rbp+57h+ProcNumber.Group], 0
0x14002e1db  and     [rbp+57h+ThreadInformation], 0
0x14002e1df  call    cs:__imp_KeGetProcessorNumberFromIndex
0x14002e1e6  nop     dword ptr [rax+rax+00h]
0x14002e1eb  test    eax, eax
0x14002e1ed  jns     short loc_14002E1F6
0x14002e1ef  xor     ebx, ebx
0x14002e1f1  jmp     loc_14002E2B1
0x14002e1f6  test    byte ptr [rdi], 2
0x14002e1f9  mov     eax, dword ptr [rbp+57h+ProcNumber.Group]
0x14002e1fc  mov     [rbp+57h+ThreadInformation], eax
0x14002e1ff  jz      short loc_14002E221
0x14002e201  mov     cl, [rbp+57h+ProcNumber.Number]
0x14002e204  lea     r8, [rbp+57h+UnicodeStringDestination]
0x14002e208  xorps   xmm0, xmm0
0x14002e20b  movups  xmmword ptr [rbp+57h+UnicodeStringDestination], xmm0
0x14002e20f  mov     word ptr [rbp+57h+UnicodeStringDestination+8], ax
0x14002e213  mov     eax, 1
0x14002e218  shl     rax, cl
0x14002e21b  mov     [rbp+57h+UnicodeStringDestination], rax
0x14002e21f  jmp     short loc_14002E260
0x14002e221  mov     ebx, 50h ; 'P'
0x14002e226  lea     rcx, [rbp+57h+Information]; void *
0x14002e22a  mov     r8d, ebx; Size
0x14002e22d  xor     edx, edx; Val
0x14002e22f  call    memset
0x14002e234  lea     r9, [rbp+57h+Length]; Length
0x14002e238  mov     [rbp+57h+Length], ebx
0x14002e23b  lea     r8, [rbp+57h+Information]; Information
0x14002e23f  lea     edx, [rbx-4Fh]; RelationshipType
0x14002e242  lea     rcx, [rbp+57h+ProcNumber]; ProcessorNumber
0x14002e246  call    cs:__imp_KeQueryLogicalProcessorRelationship
0x14002e24d  nop     dword ptr [rax+rax+00h]
0x14002e252  mov     ebx, eax
0x14002e254  test    eax, eax
0x14002e256  js      loc_14002E346
0x14002e25c  lea     r8, [rbp+57h+Information.8+18h]; ThreadInformation
0x14002e260  mov     rcx, [rbp+57h+ThreadHandle]; ThreadHandle
0x14002e264  mov     r9d, 10h; ThreadInformationLength
0x14002e26a  lea     edx, [r9+0Eh]; ThreadInformationClass
0x14002e26e  call    cs:__imp_ZwSetInformationThread
0x14002e275  nop     dword ptr [rax+rax+00h]
0x14002e27a  mov     ebx, eax
0x14002e27c  test    eax, eax
0x14002e27e  js      loc_14002E346
0x14002e284  test    byte ptr [rdi], 1
0x14002e287  jz      short loc_14002E2B1
0x14002e289  mov     rcx, [rbp+57h+ThreadHandle]; ThreadHandle
0x14002e28d  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x14002e291  mov     r9d, 4; ThreadInformationLength
0x14002e297  lea     edx, [r9+1Dh]; ThreadInformationClass
0x14002e29b  call    cs:__imp_ZwSetInformationThread
0x14002e2a2  nop     dword ptr [rax+rax+00h]
0x14002e2a7  mov     ebx, eax
0x14002e2a9  test    eax, eax
0x14002e2ab  js      loc_14002E346
0x14002e2b1  test    byte ptr [rdi], 4
0x14002e2b4  jz      short loc_14002E2CA
0x14002e2b6  mov     rcx, [rsi]; Thread
0x14002e2b9  mov     edx, 3; Increment
0x14002e2be  call    cs:__imp_KeSetBasePriorityThread
0x14002e2c5  nop     dword ptr [rax+rax+00h]
0x14002e2ca  mov     rcx, [rdi+8]; Str
0x14002e2ce  test    rcx, rcx
0x14002e2d1  jz      short loc_14002E346
0x14002e2d3  and     [rbp+57h+Length], 0
0x14002e2d7  mov     eax, 80h
0x14002e2dc  mov     word ptr [rbp+57h+UnicodeStringDestination+2], ax
0x14002e2e0  mov     edx, 40h ; '@'; MaxCount
0x14002e2e5  xor     eax, eax
0x14002e2e7  mov     dword ptr [rbp+57h+UnicodeStringDestination+4], eax
0x14002e2ea  lea     rax, [rbp+57h+Information]
0x14002e2ee  mov     [rbp+57h+UnicodeStringDestination+8], rax
0x14002e2f2  call    cs:__imp_strnlen
0x14002e2f9  nop     dword ptr [rax+rax+00h]
0x14002e2fe  movzx   edx, word ptr [rbp+57h+UnicodeStringDestination+2]; UnicodeStringMaxByteCount
0x14002e302  lea     r8, [rbp+57h+Length]; UnicodeStringActualByteCount
0x14002e306  mov     r9, [rdi+8]; UTF8StringSource
0x14002e30a  mov     rcx, [rbp+57h+UnicodeStringDestination+8]; UnicodeStringDestination
0x14002e30e  mov     dword ptr [rsp+110h+Object], eax; UTF8StringByteCount
0x14002e312  call    cs:__imp_RtlUTF8ToUnicodeN
0x14002e319  nop     dword ptr [rax+rax+00h]
0x14002e31e  movzx   eax, word ptr [rbp+57h+Length]
0x14002e322  lea     r8, [rbp+57h+UnicodeStringDestination]; ThreadInformation
0x14002e326  mov     rcx, [rbp+57h+ThreadHandle]; ThreadHandle
0x14002e32a  mov     r9d, 10h; ThreadInformationLength
0x14002e330  mov     word ptr [rbp+57h+UnicodeStringDestination], ax
0x14002e334  lea     edx, [r9+16h]; ThreadInformationClass
0x14002e338  call    cs:__imp_ZwSetInformationThread
0x14002e33f  nop     dword ptr [rax+rax+00h]
0x14002e344  xor     ebx, ebx
0x14002e346  mov     rcx, [rbp+57h+ThreadHandle]; Handle
0x14002e34a  call    cs:__imp_ZwClose
0x14002e351  nop     dword ptr [rax+rax+00h]
0x14002e356  mov     eax, ebx
0x14002e358  mov     rcx, [rbp+57h+var_20]
0x14002e35c  xor     rcx, rsp; StackCookie
0x14002e35f  call    __security_check_cookie
0x14002e364  mov     rbx, [rsp+110h+arg_10]
0x14002e36c  add     rsp, 100h
0x14002e373  pop     rdi
0x14002e374  pop     rsi
0x14002e375  pop     rbp
0x14002e376  retn
```
