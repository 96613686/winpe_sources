# UsnThread

- ea: `0x14001e720`
- end: `0x14001ea01`
- name: `UsnThread`
- size: `737`
- prototype: `void __fastcall(char *StartContext)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140005bb0`
- `0x1400140b4`
- `0x140017a08`
- `0x14001e720`
- `0x14001ea10`
- `0x14001ed40`
- `0x14001fdd0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14001e79f`
- `ntoskrnl!KeSetEvent` at `0x14001e79f`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14001e94a`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14001e9bd`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14001e94a`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14001e9bd`
- `ntoskrnl!PsTerminateSystemThread` at `0x14001e8ad`
- `ntoskrnl!PsTerminateSystemThread` at `0x14001e8ad`
- `FLTMGR!FltReleasePushLockEx` at `0x14001e89f`
- `FLTMGR!FltReleasePushLockEx` at `0x14001e89f`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001e880`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001e880`

## pseudocode

```c
void __fastcall UsnThread(char *StartContext)
{
  int v1; // r14d
  __int64 v2; // rsi
  int v4; // edi
  NTSTATUS v5; // eax
  NTSTATUS v6; // eax
  PVOID Object[2]; // [rsp+40h] [rbp-29h] BYREF
  union _LARGE_INTEGER Timeout; // [rsp+50h] [rbp-19h] BYREF
  __int128 v9; // [rsp+58h] [rbp-11h] BYREF
  __int128 v10; // [rsp+68h] [rbp-1h] BYREF
  __int128 v11; // [rsp+78h] [rbp+Fh]
  __int128 v12; // [rsp+88h] [rbp+1Fh]

  v1 = *((_DWORD *)StartContext + 60);
  v2 = *((_QWORD *)StartContext + 29);
  *((_DWORD *)StartContext + 208) = 1;
  *((_DWORD *)StartContext + 61) = 0;
  StartContext[836] = 1;
  Timeout.QuadPart = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  *(_OWORD *)Object = 0;
  KeSetEvent((PRKEVENT)(StartContext + 88), 0, 0);
  *(_QWORD *)&v10 = *((_QWORD *)StartContext + 32);
  *(_QWORD *)&v12 = *((_QWORD *)StartContext + 31);
  *(_QWORD *)&v11 = 0;
  *((_QWORD *)&v12 + 1) = 131074;
  *((_QWORD *)&v10 + 1) = 113408;
  *((_QWORD *)&v11 + 1) = 1;
  v4 = SynchronousFsControl((_DWORD)StartContext, (unsigned int)&v9, 590011, (unsigned int)&v10, 48, v2, v1);
  if ( v4 != 1 )
  {
    while ( v4 >= 0 && v4 != 2 )
    {
      ProcessUsnData(StartContext, v2, *((_QWORD *)&v9 + 1));
LABEL_5:
      *(_QWORD *)&v10 = *((_QWORD *)StartContext + 32);
      *(_QWORD *)&v12 = *((_QWORD *)StartContext + 31);
      v4 = SynchronousFsControl((_DWORD)StartContext, (unsigned int)&v9, 590011, (unsigned int)&v10, 48, v2, v1);
      if ( v4 == 1 )
        goto LABEL_6;
    }
    StartContext[836] = 0;
    _InterlockedIncrement(&dword_14000ECB8);
    LuafvEnumerateFileTable(*((_QWORD *)StartContext + 4), 0, 0, (unsigned int)ClearFileTablePostWorker, 1);
    while ( 1 )
    {
      if ( v4 == 2 )
      {
        Object[0] = StartContext + 112;
        Object[1] = StartContext + 184;
        if ( !KeWaitForMultipleObjects(2u, Object, WaitAny, Executive, 0, 0, 0, 0) )
          break;
      }
      v5 = InitializeUsn((__int64)StartContext);
      v4 = v5;
      if ( v5 == 1 )
        break;
      if ( v5 != 2 )
      {
        if ( v5 >= 0 )
        {
          StartContext[836] = 1;
          _InterlockedDecrement(&dword_14000ECB8);
          goto LABEL_5;
        }
        Object[0] = StartContext + 112;
        Timeout.QuadPart = -100000000;
        Object[1] = StartContext + 136;
        v6 = KeWaitForMultipleObjects(2u, Object, WaitAny, Executive, 0, 0, &Timeout, 0);
        if ( !v6 )
          break;
        if ( v6 == 1 )
        {
          AcknowledgePauseRequest((__int64)StartContext);
          v4 = 2;
        }
        else
        {
          v4 = 0;
        }
      }
    }
  }
LABEL_6:
  FltAcquirePushLockExclusiveEx(StartContext + 264, 0);
  *((_DWORD *)StartContext + 208) = 5;
  FltReleasePushLockEx(StartContext + 264, 0);
  PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x14001e720  mov     [rsp-8+arg_8], rbx
0x14001e725  mov     [rsp-8+arg_10], rsi
0x14001e72a  push    rbp
0x14001e72b  push    rdi
0x14001e72c  push    r12
0x14001e72e  push    r14
0x14001e730  push    r15
0x14001e732  lea     rbp, [rsp-37h]
0x14001e737  sub     rsp, 0A0h
0x14001e73e  mov     rax, cs:__security_cookie
0x14001e745  xor     rax, rsp
0x14001e748  mov     [rbp+57h+var_28], rax
0x14001e74c  mov     r14d, [rcx+0F0h]
0x14001e753  xorps   xmm1, xmm1
0x14001e756  mov     rsi, [rcx+0E8h]
0x14001e75d  xorps   xmm0, xmm0
0x14001e760  xor     r15d, r15d
0x14001e763  mov     dword ptr [rcx+340h], 1
0x14001e76d  mov     [rcx+0F4h], r15d
0x14001e774  mov     rbx, rcx
0x14001e777  mov     byte ptr [rcx+344h], 1
0x14001e77e  xor     r8d, r8d; Wait
0x14001e781  add     rcx, 58h ; 'X'; Event
0x14001e785  mov     qword ptr [rbp+57h+var_70], r15
0x14001e789  xor     edx, edx; Increment
0x14001e78b  movups  [rbp+57h+var_68], xmm0
0x14001e78f  movups  [rbp+57h+var_58], xmm1
0x14001e793  movups  [rbp+57h+var_48], xmm1
0x14001e797  movups  [rbp+57h+var_38], xmm1
0x14001e79b  movups  xmmword ptr [rbp+57h+Object], xmm0
0x14001e79f  call    cs:__imp_KeSetEvent
0x14001e7a6  nop     dword ptr [rax+rax+00h]
0x14001e7ab  mov     rax, [rbx+100h]
0x14001e7b2  lea     r9, [rbp+57h+var_58]
0x14001e7b6  mov     qword ptr [rbp+57h+var_58], rax
0x14001e7ba  lea     rdx, [rbp+57h+var_68]
0x14001e7be  mov     rax, [rbx+0F8h]
0x14001e7c5  mov     r8d, 900BBh
0x14001e7cb  mov     dword ptr [rsp+0C0h+Timeout], r14d
0x14001e7d0  mov     rcx, rbx
0x14001e7d3  mov     qword ptr [rsp+0C0h+Alertable], rsi
0x14001e7d8  mov     r12d, 2
0x14001e7de  mov     qword ptr [rbp+57h+var_38], rax
0x14001e7e2  mov     qword ptr [rbp+57h+var_48], r15
0x14001e7e6  mov     qword ptr [rbp+57h+var_38+8], 20002h
0x14001e7ee  mov     qword ptr [rbp+57h+var_58+8], 1BB00h
0x14001e7f6  mov     qword ptr [rbp+57h+var_48+8], 1
0x14001e7fe  mov     dword ptr [rsp+0C0h+WaitMode], 30h ; '0'
0x14001e806  call    SynchronousFsControl
0x14001e80b  mov     edi, eax
0x14001e80d  cmp     eax, 1
0x14001e810  jz      short loc_14001E877
0x14001e812  test    edi, edi
0x14001e814  js      loc_14001E8E2
0x14001e81a  cmp     edi, r12d
0x14001e81d  jz      loc_14001E8E2
0x14001e823  mov     r8, qword ptr [rbp+57h+var_68+8]
0x14001e827  mov     rdx, rsi
0x14001e82a  mov     rcx, rbx
0x14001e82d  call    ProcessUsnData
0x14001e832  mov     rax, [rbx+100h]
0x14001e839  lea     r9, [rbp+57h+var_58]
0x14001e83d  mov     qword ptr [rbp+57h+var_58], rax
0x14001e841  lea     rdx, [rbp+57h+var_68]
0x14001e845  mov     rax, [rbx+0F8h]
0x14001e84c  mov     r8d, 900BBh
0x14001e852  mov     dword ptr [rsp+0C0h+Timeout], r14d
0x14001e857  mov     rcx, rbx
0x14001e85a  mov     qword ptr [rsp+0C0h+Alertable], rsi
0x14001e85f  mov     qword ptr [rbp+57h+var_38], rax
0x14001e863  mov     dword ptr [rsp+0C0h+WaitMode], 30h ; '0'
0x14001e86b  call    SynchronousFsControl
0x14001e870  mov     edi, eax
0x14001e872  cmp     eax, 1
0x14001e875  jnz     short loc_14001E812
0x14001e877  xor     edx, edx
0x14001e879  lea     rcx, [rbx+108h]
0x14001e880  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001e887  nop     dword ptr [rax+rax+00h]
0x14001e88c  xor     edx, edx
0x14001e88e  mov     dword ptr [rbx+340h], 5
0x14001e898  lea     rcx, [rbx+108h]
0x14001e89f  call    cs:__imp_FltReleasePushLockEx
0x14001e8a6  nop     dword ptr [rax+rax+00h]
0x14001e8ab  xor     ecx, ecx; ExitStatus
0x14001e8ad  call    cs:__imp_PsTerminateSystemThread
0x14001e8b4  nop     dword ptr [rax+rax+00h]
0x14001e8b9  mov     rcx, [rbp+57h+var_28]
0x14001e8bd  xor     rcx, rsp; StackCookie
0x14001e8c0  call    __security_check_cookie
0x14001e8c5  lea     r11, [rsp+0C0h+var_20]
0x14001e8cd  mov     rbx, [r11+38h]
0x14001e8d1  mov     rsi, [r11+40h]
0x14001e8d5  mov     rsp, r11
0x14001e8d8  pop     r15
0x14001e8da  pop     r14
0x14001e8dc  pop     r12
0x14001e8de  pop     rdi
0x14001e8df  pop     rbp
0x14001e8e0  retn
0x14001e8e2  mov     [rbx+344h], r15b
0x14001e8e9  lock inc cs:dword_14000ECB8
0x14001e8f0  mov     rcx, [rbx+20h]
0x14001e8f4  lea     r9, ClearFileTablePostWorker
0x14001e8fb  xor     r8d, r8d
0x14001e8fe  mov     qword ptr [rsp+0C0h+WaitMode], 1
0x14001e907  xor     edx, edx
0x14001e909  call    LuafvEnumerateFileTable
0x14001e90e  cmp     edi, r12d
0x14001e911  jnz     short loc_14001E95E
0x14001e913  mov     [rsp+0C0h+WaitBlockArray], r15; WaitBlockArray
0x14001e918  lea     rax, [rbx+70h]
0x14001e91c  mov     [rbp+57h+Object], rax
0x14001e920  lea     rdx, [rbp+57h+Object]; Object
0x14001e924  lea     rax, [rbx+0B8h]
0x14001e92b  mov     [rsp+0C0h+Timeout], r15; Timeout
0x14001e930  mov     [rsp+0C0h+Alertable], r15b; Alertable
0x14001e935  xor     r9d, r9d; WaitReason
0x14001e938  mov     r8d, 1; WaitType
0x14001e93e  mov     [rbp+57h+Object+8], rax
0x14001e942  mov     ecx, r12d; Count
0x14001e945  mov     [rsp+0C0h+WaitMode], r15b; WaitMode
0x14001e94a  call    cs:__imp_KeWaitForMultipleObjects
0x14001e951  nop     dword ptr [rax+rax+00h]
0x14001e956  test    eax, eax
0x14001e958  jz      loc_14001E877
0x14001e95e  mov     rcx, rbx
0x14001e961  call    InitializeUsn
0x14001e966  mov     edi, eax
0x14001e968  cmp     eax, 1
0x14001e96b  jz      loc_14001E877
0x14001e971  cmp     eax, r12d
0x14001e974  jz      short loc_14001E90E
0x14001e976  test    eax, eax
0x14001e978  jns     short loc_14001E9EE
0x14001e97a  mov     [rsp+0C0h+WaitBlockArray], r15; WaitBlockArray
0x14001e97f  lea     rax, [rbx+70h]
0x14001e983  mov     [rbp+57h+Object], rax
0x14001e987  lea     rdx, [rbp+57h+Object]; Object
0x14001e98b  lea     rax, [rbx+88h]
0x14001e992  mov     qword ptr [rbp+57h+var_70], 0FFFFFFFFFA0A1F00h
0x14001e99a  mov     [rbp+57h+Object+8], rax
0x14001e99e  xor     r9d, r9d; WaitReason
0x14001e9a1  lea     rax, [rbp+57h+var_70]
0x14001e9a5  mov     r8d, 1; WaitType
0x14001e9ab  mov     [rsp+0C0h+Timeout], rax; Timeout
0x14001e9b0  mov     ecx, r12d; Count
0x14001e9b3  mov     [rsp+0C0h+Alertable], r15b; Alertable
0x14001e9b8  mov     [rsp+0C0h+WaitMode], r15b; WaitMode
0x14001e9bd  call    cs:__imp_KeWaitForMultipleObjects
0x14001e9c4  nop     dword ptr [rax+rax+00h]
0x14001e9c9  test    eax, eax
0x14001e9cb  jz      loc_14001E877
0x14001e9d1  cmp     eax, 1
0x14001e9d4  jnz     short loc_14001E9E6
0x14001e9d6  mov     rcx, rbx
0x14001e9d9  call    AcknowledgePauseRequest
0x14001e9de  mov     edi, r12d
0x14001e9e1  jmp     loc_14001E90E
0x14001e9e6  mov     edi, r15d
0x14001e9e9  jmp     loc_14001E90E
0x14001e9ee  mov     byte ptr [rbx+344h], 1
0x14001e9f5  lock dec cs:dword_14000ECB8
0x14001e9fc  jmp     loc_14001E832
```
