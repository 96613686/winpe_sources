# CdGetProcessConnection

- ea: `0x14000ac50`
- end: `0x14000ae64`
- name: `CdGetProcessConnection`
- size: `532`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x140009420`
- `0x140009760`
- `0x140009af0`
- `0x14000ab30`
- `0x14000b4d0`
- `0x14000be70`
- `0x14000c690`

## callees

- `0x1400014d0`
- `0x140008128`
- `0x140008164`
- `0x14000ac50`
- `0x14000dc30`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000ade0`
- `ntoskrnl!ObfDereferenceObject` at `0x14000ade0`
- `ntoskrnl!ObfReferenceObject` at `0x14000ae45`
- `ntoskrnl!ObfReferenceObject` at `0x14000ae45`
- `ntoskrnl!PsIsSystemProcess` at `0x14000ac98`
- `ntoskrnl!PsIsSystemProcess` at `0x14000ac98`
- `ntoskrnl!PsGetProcessWow64Process` at `0x14000acdb`
- `ntoskrnl!PsGetProcessWow64Process` at `0x14000acdb`
- `ntoskrnl!PsAcquireProcessExitSynchronization` at `0x14000acaf`
- `ntoskrnl!PsAcquireProcessExitSynchronization` at `0x14000acaf`
- `ntoskrnl!KeStackAttachProcess` at `0x14000accb`
- `ntoskrnl!KeStackAttachProcess` at `0x14000accb`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14000ad2f`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14000ad2f`
- `ntoskrnl!PsGetProcessPeb` at `0x14000acef`
- `ntoskrnl!PsGetProcessPeb` at `0x14000acef`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14000ad4a`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14000ada9`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14000ad4a`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14000ada9`
- `ntoskrnl!PsReleaseProcessExitSynchronization` at `0x14000ad5b`
- `ntoskrnl!PsReleaseProcessExitSynchronization` at `0x14000adb8`
- `ntoskrnl!PsReleaseProcessExitSynchronization` at `0x14000ad5b`
- `ntoskrnl!PsReleaseProcessExitSynchronization` at `0x14000adb8`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000ad96`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000ad96`
- `ntoskrnl!IoFileObjectType` at `0x14000ad87`

## pseudocode

```c
__int64 __fastcall CdGetProcessConnection(_QWORD *a1, __int64 *a2, __int64 a3, void *a4)
{
  __int64 result; // rax
  __int64 ProcessWow64Process; // rax
  __int64 ProcessPeb; // rax
  __int64 ULong64FromUser; // rax
  __int64 v11; // rax
  unsigned int ULongFromUser; // eax
  NTSTATUS v13; // edi
  __int64 v14; // rax
  void *v15; // r8
  __int64 v16; // rcx
  __int64 ConnectionFromFileObject; // rax
  void *v18; // r8
  PVOID Object[2]; // [rsp+30h] [rbp-78h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+40h] [rbp-68h] BYREF

  Object[0] = a4;
  memset(&ApcState, 0, sizeof(ApcState));
  if ( a3 )
  {
    v16 = *(_QWORD *)(*(_QWORD *)(a3 + 184) + 48LL);
    if ( *(_QWORD *)(v16 + 64) )
    {
      ConnectionFromFileObject = CdGetConnectionFromFileObject(*(_QWORD *)(v16 + 64), a4);
      if ( ConnectionFromFileObject )
      {
        *a2 = ConnectionFromFileObject;
        *a1 = v18;
        ObfReferenceObject(v18);
        return 0;
      }
    }
  }
  if ( (unsigned __int8)PsIsSystemProcess(a4) )
    return 3221225659LL;
  result = PsAcquireProcessExitSynchronization(a4);
  if ( (int)result >= 0 )
  {
    KeStackAttachProcess((PRKPROCESS)a4, &ApcState);
    ProcessWow64Process = PsGetProcessWow64Process(a4);
    if ( ProcessWow64Process )
    {
      ULongFromUser = RtlReadULongFromUser(ProcessWow64Process + 16);
      if ( (ULongFromUser & 3) == 0 )
      {
        v11 = (unsigned int)RtlReadULongFromUser(ULongFromUser + 16LL);
        goto LABEL_10;
      }
    }
    else
    {
      ProcessPeb = PsGetProcessPeb(a4);
      ULong64FromUser = RtlReadULong64FromUser(ProcessPeb + 32);
      if ( (ULong64FromUser & 3) == 0 )
      {
        v11 = RtlReadULong64FromUser(ULong64FromUser + 16);
LABEL_10:
        Object[1] = (PVOID)v11;
        Object[0] = 0;
        v13 = ObReferenceObjectByHandle((HANDLE)v11, 0, (POBJECT_TYPE)IoFileObjectType, 1, Object, 0);
        KeUnstackDetachProcess(&ApcState);
        PsReleaseProcessExitSynchronization(a4);
        if ( v13 < 0 )
          return (unsigned int)v13;
        v14 = CdGetConnectionFromFileObject(Object[0], a4);
        if ( v14 )
        {
          *a2 = v14;
          *a1 = v15;
          return 0;
        }
        ObfDereferenceObject(v15);
        return 3221225473LL;
      }
    }
    ExRaiseDatatypeMisalignment();
  }
  return result;
}

```

## disassembly

```asm
0x14000ac50  push    rbx
0x14000ac52  push    rsi
0x14000ac53  push    rdi
0x14000ac54  push    r14
0x14000ac56  sub     rsp, 88h
0x14000ac5d  mov     rax, cs:__security_cookie
0x14000ac64  xor     rax, rsp
0x14000ac67  mov     [rsp+0A8h+var_38], rax
0x14000ac6c  mov     rbx, r9
0x14000ac6f  mov     r14, rdx
0x14000ac72  mov     rsi, rcx
0x14000ac75  mov     [rsp+0A8h+var_78], rbx
0x14000ac7a  xorps   xmm0, xmm0
0x14000ac7d  movups  xmmword ptr [rsp+0A8h+ApcState.ApcListHead.Flink], xmm0
0x14000ac82  movups  xmmword ptr [rsp+0A8h+ApcState.ApcListHead.Flink+10h], xmm0
0x14000ac87  movups  xmmword ptr [rsp+0A8h+ApcState.Process], xmm0
0x14000ac8c  test    r8, r8
0x14000ac8f  jnz     loc_14000AE10
0x14000ac95  mov     rcx, rbx
0x14000ac98  call    cs:__imp_PsIsSystemProcess
0x14000ac9f  nop     dword ptr [rax+rax+00h]
0x14000aca4  test    al, al
0x14000aca6  jnz     loc_14000AE53
0x14000acac  mov     rcx, rbx
0x14000acaf  call    cs:__imp_PsAcquireProcessExitSynchronization
0x14000acb6  nop     dword ptr [rax+rax+00h]
0x14000acbb  test    eax, eax
0x14000acbd  js      loc_14000ADF1
0x14000acc3  lea     rdx, [rsp+0A8h+ApcState]; ApcState
0x14000acc8  mov     rcx, rbx; PROCESS
0x14000accb  call    cs:__imp_KeStackAttachProcess
0x14000acd2  nop     dword ptr [rax+rax+00h]
0x14000acd7  nop
0x14000acd8  mov     rcx, rbx
0x14000acdb  call    cs:__imp_PsGetProcessWow64Process
0x14000ace2  nop     dword ptr [rax+rax+00h]
0x14000ace7  test    rax, rax
0x14000acea  jnz     short loc_14000AD13
0x14000acec  mov     rcx, rbx
0x14000acef  call    cs:__imp_PsGetProcessPeb
0x14000acf6  nop     dword ptr [rax+rax+00h]
0x14000acfb  lea     rcx, [rax+20h]
0x14000acff  call    RtlReadULong64FromUser
0x14000ad04  test    al, 3
0x14000ad06  jnz     short loc_14000AD2F
0x14000ad08  lea     rcx, [rax+10h]
0x14000ad0c  call    RtlReadULong64FromUser
0x14000ad11  jmp     short loc_14000AD3C
0x14000ad13  lea     rcx, [rax+10h]
0x14000ad17  call    RtlReadULongFromUser
0x14000ad1c  test    al, 3
0x14000ad1e  jnz     short loc_14000AD2F
0x14000ad20  mov     ecx, eax
0x14000ad22  add     rcx, 10h
0x14000ad26  call    RtlReadULongFromUser
0x14000ad2b  mov     eax, eax
0x14000ad2d  jmp     short loc_14000AD3C
0x14000ad2f  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14000ad36  nop     dword ptr [rax+rax+00h]
0x14000ad3b  int     3; Trap to Debugger
0x14000ad3c  mov     [rsp+0A8h+var_70], rax
0x14000ad41  jmp     short loc_14000AD6E
0x14000ad43  mov     ebx, eax
0x14000ad45  lea     rcx, [rsp+0A8h+ApcState]; ApcState
0x14000ad4a  call    cs:__imp_KeUnstackDetachProcess
0x14000ad51  nop     dword ptr [rax+rax+00h]
0x14000ad56  mov     rcx, [rsp+0A8h+var_78]
0x14000ad5b  call    cs:__imp_PsReleaseProcessExitSynchronization
0x14000ad62  nop     dword ptr [rax+rax+00h]
0x14000ad67  mov     eax, ebx
0x14000ad69  jmp     loc_14000ADF1
0x14000ad6e  xor     ecx, ecx
0x14000ad70  mov     [rsp+0A8h+var_78], rcx
0x14000ad75  mov     [rsp+0A8h+HandleInformation], rcx; HandleInformation
0x14000ad7a  lea     rcx, [rsp+0A8h+var_78]
0x14000ad7f  mov     [rsp+0A8h+Object], rcx; Object
0x14000ad84  mov     r9b, 1; AccessMode
0x14000ad87  mov     r8, cs:__imp_IoFileObjectType
0x14000ad8e  mov     r8, [r8]; ObjectType
0x14000ad91  xor     edx, edx; DesiredAccess
0x14000ad93  mov     rcx, rax; Handle
0x14000ad96  call    cs:__imp_ObReferenceObjectByHandle
0x14000ad9d  nop     dword ptr [rax+rax+00h]
0x14000ada2  mov     edi, eax
0x14000ada4  lea     rcx, [rsp+0A8h+ApcState]; ApcState
0x14000ada9  call    cs:__imp_KeUnstackDetachProcess
0x14000adb0  nop     dword ptr [rax+rax+00h]
0x14000adb5  mov     rcx, rbx
0x14000adb8  call    cs:__imp_PsReleaseProcessExitSynchronization
0x14000adbf  nop     dword ptr [rax+rax+00h]
0x14000adc4  test    edi, edi
0x14000adc6  js      short loc_14000AE0C
0x14000adc8  mov     r8, [rsp+0A8h+var_78]
0x14000adcd  mov     rdx, rbx
0x14000add0  mov     rcx, r8
0x14000add3  call    CdGetConnectionFromFileObject
0x14000add8  test    rax, rax
0x14000addb  jnz     short loc_14000AE5A
0x14000addd  mov     rcx, r8; Object
0x14000ade0  call    cs:__imp_ObfDereferenceObject
0x14000ade7  nop     dword ptr [rax+rax+00h]
0x14000adec  mov     eax, 0C0000001h
0x14000adf1  mov     rcx, [rsp+0A8h+var_38]
0x14000adf6  xor     rcx, rsp; StackCookie
0x14000adf9  call    __security_check_cookie
0x14000adfe  add     rsp, 88h
0x14000ae05  pop     r14
0x14000ae07  pop     rdi
0x14000ae08  pop     rsi
0x14000ae09  pop     rbx
0x14000ae0a  retn
0x14000ae0c  mov     eax, edi
0x14000ae0e  jmp     short loc_14000ADF1
0x14000ae10  mov     rax, [r8+0B8h]
0x14000ae17  mov     rcx, [rax+30h]
0x14000ae1b  mov     r8, [rcx+40h]
0x14000ae1f  test    r8, r8
0x14000ae22  jz      loc_14000AC95
0x14000ae28  mov     rdx, rbx
0x14000ae2b  mov     rcx, r8
0x14000ae2e  call    CdGetConnectionFromFileObject
0x14000ae33  test    rax, rax
0x14000ae36  jz      loc_14000AC95
0x14000ae3c  mov     [r14], rax
0x14000ae3f  mov     [rsi], r8
0x14000ae42  mov     rcx, r8; Object
0x14000ae45  call    cs:__imp_ObfReferenceObject
0x14000ae4c  nop     dword ptr [rax+rax+00h]
0x14000ae51  jmp     short loc_14000AE60
0x14000ae53  mov     eax, 0C00000BBh
0x14000ae58  jmp     short loc_14000ADF1
0x14000ae5a  mov     [r14], rax
0x14000ae5d  mov     [rsi], r8
0x14000ae60  xor     eax, eax
0x14000ae62  jmp     short loc_14000ADF1
```
