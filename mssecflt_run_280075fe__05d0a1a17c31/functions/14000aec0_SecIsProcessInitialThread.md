# SecIsProcessInitialThread

- ea: `0x14000aec0`
- end: `0x14000b097`
- name: `SecIsProcessInitialThread`
- size: `471`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140041fb0`

## callees

- `0x14000aec0`
- `0x140011650`
- `0x140044208`

## import_xrefs

- `ntoskrnl!PsGetThreadProcess` at `0x14000af6d`
- `ntoskrnl!PsGetThreadProcess` at `0x14000af6d`
- `ntoskrnl!PsThreadType` at `0x14000af27`
- `ntoskrnl!PsIsSystemThread` at `0x14000af4e`
- `ntoskrnl!PsIsSystemThread` at `0x14000af4e`
- `ntoskrnl!PsGetThreadTeb` at `0x14000af8f`
- `ntoskrnl!PsGetThreadTeb` at `0x14000af8f`
- `ntoskrnl!PsAcquireProcessExitSynchronization` at `0x14000afaa`
- `ntoskrnl!PsAcquireProcessExitSynchronization` at `0x14000afaa`
- `ntoskrnl!PsReleaseProcessExitSynchronization` at `0x14000b046`
- `ntoskrnl!PsReleaseProcessExitSynchronization` at `0x14000b046`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14000b037`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14000b037`
- `ntoskrnl!KeStackAttachProcess` at `0x14000afcb`
- `ntoskrnl!KeStackAttachProcess` at `0x14000afcb`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b05f`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b05f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000af33`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000af33`
- `ntoskrnl!ProbeForRead` at `0x14000aff6`
- `ntoskrnl!ProbeForRead` at `0x14000aff6`

## pseudocode

```c
__int64 __fastcall SecIsProcessInitialThread(void *a1, bool *a2)
{
  NTSTATUS v3; // esi
  struct _KPROCESS *ThreadProcess; // rdi
  _WORD *ThreadTeb; // rbx
  bool v6; // bl
  PETHREAD Thread; // [rsp+48h] [rbp-60h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+50h] [rbp-58h] BYREF

  memset(&ApcState, 0, sizeof(ApcState));
  Thread = 0;
  *a2 = 0;
  v3 = ObReferenceObjectByHandle(a1, 0, (POBJECT_TYPE)PsThreadType, 0, (PVOID *)&Thread, 0);
  if ( v3 >= 0 )
  {
    if ( PsIsSystemThread(Thread) )
    {
      v3 = -1073741637;
    }
    else
    {
      ThreadProcess = PsGetThreadProcess(Thread);
      if ( ThreadProcess )
      {
        ThreadTeb = (_WORD *)PsGetThreadTeb(Thread);
        if ( ThreadTeb )
        {
          v3 = PsAcquireProcessExitSynchronization(ThreadProcess);
          if ( v3 >= 0 )
          {
            _mm_lfence();
            KeStackAttachProcess(ThreadProcess, &ApcState);
            if ( (BYTE8(xmmword_14001B740) & 0x20) != 0 )
            {
              ProbeForRead(ThreadTeb, 0x1838u, 8u);
              v6 = (ThreadTeb[3063] & 0x400) != 0;
            }
            else
            {
              RtlReadUShortFromUser(ThreadTeb + 3063);
              v6 = 0;
            }
            _mm_lfence();
            KeUnstackDetachProcess(&ApcState);
            PsReleaseProcessExitSynchronization(ThreadProcess);
            *a2 = v6;
          }
        }
      }
    }
  }
  if ( Thread )
    ObfDereferenceObject(Thread);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14000aec0  mov     r11, rsp
0x14000aec3  mov     [r11+18h], rbx
0x14000aec7  mov     [r11+20h], rsi
0x14000aecb  push    rdi
0x14000aecc  push    r14
0x14000aece  push    r15
0x14000aed0  sub     rsp, 90h
0x14000aed7  mov     rax, cs:__security_cookie
0x14000aede  xor     rax, rsp
0x14000aee1  mov     [rsp+0A8h+var_28], rax
0x14000aee9  mov     r15, rdx
0x14000aeec  mov     [rsp+0A8h+var_68], rdx
0x14000aef1  xorps   xmm0, xmm0
0x14000aef4  movups  xmmword ptr [rsp+0A8h+ApcState.ApcListHead.Flink], xmm0
0x14000aef9  movups  xmmword ptr [rsp+0A8h+ApcState.ApcListHead.Flink+10h], xmm0
0x14000aefe  movups  xmmword ptr [rsp+0A8h+ApcState.Process], xmm0
0x14000af03  mov     [rsp+0A8h+var_78], 0
0x14000af08  mov     qword ptr [r11-60h], 0
0x14000af10  mov     byte ptr [rdx], 0
0x14000af13  mov     qword ptr [r11-80h], 0
0x14000af1b  lea     rax, [r11-60h]
0x14000af1f  mov     [rsp+0A8h+Object], rax; Object
0x14000af24  xor     r9d, r9d; AccessMode
0x14000af27  mov     r8, cs:__imp_PsThreadType
0x14000af2e  mov     r8, [r8]; ObjectType
0x14000af31  xor     edx, edx; DesiredAccess
0x14000af33  call    cs:__imp_ObReferenceObjectByHandle
0x14000af3a  nop     dword ptr [rax+rax+00h]
0x14000af3f  mov     esi, eax
0x14000af41  test    eax, eax
0x14000af43  js      loc_14000B055
0x14000af49  mov     rcx, [rsp+0A8h+Thread]; Thread
0x14000af4e  call    cs:__imp_PsIsSystemThread
0x14000af55  nop     dword ptr [rax+rax+00h]
0x14000af5a  test    al, al
0x14000af5c  jz      short loc_14000AF68
0x14000af5e  mov     esi, 0C00000BBh
0x14000af63  jmp     loc_14000B055
0x14000af68  mov     rcx, [rsp+0A8h+Thread]; Thread
0x14000af6d  call    cs:__imp_PsGetThreadProcess
0x14000af74  nop     dword ptr [rax+rax+00h]
0x14000af79  mov     rdi, rax
0x14000af7c  mov     [rsp+0A8h+var_70], rax
0x14000af81  test    rax, rax
0x14000af84  jz      loc_14000B055
0x14000af8a  mov     rcx, [rsp+0A8h+Thread]
0x14000af8f  call    cs:__imp_PsGetThreadTeb
0x14000af96  nop     dword ptr [rax+rax+00h]
0x14000af9b  mov     rbx, rax
0x14000af9e  test    rax, rax
0x14000afa1  jz      loc_14000B055
0x14000afa7  mov     rcx, rdi
0x14000afaa  call    cs:__imp_PsAcquireProcessExitSynchronization
0x14000afb1  nop     dword ptr [rax+rax+00h]
0x14000afb6  mov     esi, eax
0x14000afb8  test    eax, eax
0x14000afba  js      loc_14000B055
0x14000afc0  lfence
0x14000afc3  lea     rdx, [rsp+0A8h+ApcState]; ApcState
0x14000afc8  mov     rcx, rdi; PROCESS
0x14000afcb  call    cs:__imp_KeStackAttachProcess
0x14000afd2  nop     dword ptr [rax+rax+00h]
0x14000afd7  nop
0x14000afd8  lea     r14, [rbx+17EEh]
0x14000afdf  test    byte ptr cs:xmmword_14001B740+8, 20h
0x14000afe6  jz      short loc_14000B00F
0x14000afe8  mov     edx, 1838h; Length
0x14000afed  mov     r8d, 8; Alignment
0x14000aff3  mov     rcx, rbx; Address
0x14000aff6  call    cs:__imp_ProbeForRead
0x14000affd  nop     dword ptr [rax+rax+00h]
0x14000b002  movzx   ebx, word ptr [r14]
0x14000b006  shr     bx, 0Ah
0x14000b00a  and     bl, 1
0x14000b00d  jmp     short loc_14000B019
0x14000b00f  mov     rcx, r14
0x14000b012  call    RtlReadUShortFromUser
0x14000b017  xor     bl, bl
0x14000b019  mov     [rsp+0A8h+var_78], bl
0x14000b01d  jmp     short loc_14000B02F
0x14000b01f  mov     esi, eax
0x14000b021  mov     bl, [rsp+0A8h+var_78]
0x14000b025  mov     rdi, [rsp+0A8h+var_70]
0x14000b02a  mov     r15, [rsp+0A8h+var_68]
0x14000b02f  lfence
0x14000b032  lea     rcx, [rsp+0A8h+ApcState]; ApcState
0x14000b037  call    cs:__imp_KeUnstackDetachProcess
0x14000b03e  nop     dword ptr [rax+rax+00h]
0x14000b043  mov     rcx, rdi
0x14000b046  call    cs:__imp_PsReleaseProcessExitSynchronization
0x14000b04d  nop     dword ptr [rax+rax+00h]
0x14000b052  mov     [r15], bl
0x14000b055  mov     rcx, [rsp+0A8h+Thread]; Object
0x14000b05a  test    rcx, rcx
0x14000b05d  jz      short loc_14000B06B
0x14000b05f  call    cs:__imp_ObfDereferenceObject
0x14000b066  nop     dword ptr [rax+rax+00h]
0x14000b06b  mov     eax, esi
0x14000b06d  mov     rcx, [rsp+0A8h+var_28]
0x14000b075  xor     rcx, rsp; StackCookie
0x14000b078  call    __security_check_cookie
0x14000b07d  lea     r11, [rsp+0A8h+var_18]
0x14000b085  mov     rbx, [r11+30h]
0x14000b089  mov     rsi, [r11+38h]
0x14000b08d  mov     rsp, r11
0x14000b090  pop     r15
0x14000b092  pop     r14
0x14000b094  pop     rdi
0x14000b095  retn
```
