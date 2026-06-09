# UsnThread

- ea: `0x14001e770`
- end: `0x14001ea51`
- name: `UsnThread`
- size: `737`
- prototype: `void __fastcall(char *StartContext)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140005f30`
- `0x1400140b4`
- `0x140017a58`
- `0x14001e770`
- `0x14001ea60`
- `0x14001ed90`
- `0x14001fe20`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14001e7ef`
- `ntoskrnl!KeSetEvent` at `0x14001e7ef`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14001e99a`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14001ea0d`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14001e99a`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14001ea0d`
- `ntoskrnl!PsTerminateSystemThread` at `0x14001e8fd`
- `ntoskrnl!PsTerminateSystemThread` at `0x14001e8fd`
- `FLTMGR!FltReleasePushLockEx` at `0x14001e8ef`
- `FLTMGR!FltReleasePushLockEx` at `0x14001e8ef`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001e8d0`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001e8d0`

## pseudocode

```c
void __fastcall UsnThread(char *StartContext)
{
  ULONG v1; // r14d
  void *v2; // rsi
  NTSTATUS v4; // edi
  int v5; // eax
  NTSTATUS v6; // eax
  PVOID Object[2]; // [rsp+40h] [rbp-29h] BYREF
  union _LARGE_INTEGER Timeout; // [rsp+50h] [rbp-19h] BYREF
  __int128 v9; // [rsp+58h] [rbp-11h] BYREF
  __int128 v10; // [rsp+68h] [rbp-1h] BYREF
  __int128 v11; // [rsp+78h] [rbp+Fh]
  __int128 v12; // [rsp+88h] [rbp+1Fh]

  v1 = *((_DWORD *)StartContext + 60);
  v2 = (void *)*((_QWORD *)StartContext + 29);
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
  v4 = SynchronousFsControl((__int64)StartContext, &v9, 0x900BBu, &v10, 0x30u, v2, v1);
  if ( v4 != 1 )
  {
    while ( v4 >= 0 && v4 != 2 )
    {
      ProcessUsnData(StartContext, v2, *((_QWORD *)&v9 + 1));
LABEL_5:
      *(_QWORD *)&v10 = *((_QWORD *)StartContext + 32);
      *(_QWORD *)&v12 = *((_QWORD *)StartContext + 31);
      v4 = SynchronousFsControl((__int64)StartContext, &v9, 0x900BBu, &v10, 0x30u, v2, v1);
      if ( v4 == 1 )
        goto LABEL_6;
    }
    StartContext[836] = 0;
    _InterlockedIncrement(&dword_14000F2F8);
    LuafvEnumerateFileTable(
      *((_QWORD *)StartContext + 4),
      0,
      0,
      (void (__fastcall *)(__int64, __int64))ClearFileTablePostWorker,
      1);
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
          _InterlockedDecrement(&dword_14000F2F8);
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
0x14001e770  mov     [rsp-8+arg_8], rbx
0x14001e775  mov     [rsp-8+arg_10], rsi
0x14001e77a  push    rbp
0x14001e77b  push    rdi
0x14001e77c  push    r12
0x14001e77e  push    r14
0x14001e780  push    r15
0x14001e782  lea     rbp, [rsp-37h]
0x14001e787  sub     rsp, 0A0h
0x14001e78e  mov     rax, cs:__security_cookie
0x14001e795  xor     rax, rsp
0x14001e798  mov     [rbp+57h+var_28], rax
0x14001e79c  mov     r14d, [rcx+0F0h]
0x14001e7a3  xorps   xmm1, xmm1
0x14001e7a6  mov     rsi, [rcx+0E8h]
0x14001e7ad  xorps   xmm0, xmm0
0x14001e7b0  xor     r15d, r15d
0x14001e7b3  mov     dword ptr [rcx+340h], 1
0x14001e7bd  mov     [rcx+0F4h], r15d
0x14001e7c4  mov     rbx, rcx
0x14001e7c7  mov     byte ptr [rcx+344h], 1
0x14001e7ce  xor     r8d, r8d; Wait
0x14001e7d1  add     rcx, 58h ; 'X'; Event
0x14001e7d5  mov     qword ptr [rbp+57h+var_70], r15
0x14001e7d9  xor     edx, edx; Increment
0x14001e7db  movups  [rbp+57h+var_68], xmm0
0x14001e7df  movups  [rbp+57h+var_58], xmm1
0x14001e7e3  movups  [rbp+57h+var_48], xmm1
0x14001e7e7  movups  [rbp+57h+var_38], xmm1
0x14001e7eb  movups  xmmword ptr [rbp+57h+Object], xmm0
0x14001e7ef  call    cs:__imp_KeSetEvent
0x14001e7f6  nop     dword ptr [rax+rax+00h]
0x14001e7fb  mov     rax, [rbx+100h]
0x14001e802  lea     r9, [rbp+57h+var_58]
0x14001e806  mov     qword ptr [rbp+57h+var_58], rax
0x14001e80a  lea     rdx, [rbp+57h+var_68]
0x14001e80e  mov     rax, [rbx+0F8h]
0x14001e815  mov     r8d, 900BBh
0x14001e81b  mov     dword ptr [rsp+0C0h+Timeout], r14d
0x14001e820  mov     rcx, rbx
0x14001e823  mov     qword ptr [rsp+0C0h+Alertable], rsi
0x14001e828  mov     r12d, 2
0x14001e82e  mov     qword ptr [rbp+57h+var_38], rax
0x14001e832  mov     qword ptr [rbp+57h+var_48], r15
0x14001e836  mov     qword ptr [rbp+57h+var_38+8], 20002h
0x14001e83e  mov     qword ptr [rbp+57h+var_58+8], 1BB00h
0x14001e846  mov     qword ptr [rbp+57h+var_48+8], 1
0x14001e84e  mov     dword ptr [rsp+0C0h+WaitMode], 30h ; '0'
0x14001e856  call    SynchronousFsControl
0x14001e85b  mov     edi, eax
0x14001e85d  cmp     eax, 1
0x14001e860  jz      short loc_14001E8C7
0x14001e862  test    edi, edi
0x14001e864  js      loc_14001E932
0x14001e86a  cmp     edi, r12d
0x14001e86d  jz      loc_14001E932
0x14001e873  mov     r8, qword ptr [rbp+57h+var_68+8]
0x14001e877  mov     rdx, rsi
0x14001e87a  mov     rcx, rbx
0x14001e87d  call    ProcessUsnData
0x14001e882  mov     rax, [rbx+100h]
0x14001e889  lea     r9, [rbp+57h+var_58]
0x14001e88d  mov     qword ptr [rbp+57h+var_58], rax
0x14001e891  lea     rdx, [rbp+57h+var_68]
0x14001e895  mov     rax, [rbx+0F8h]
0x14001e89c  mov     r8d, 900BBh
0x14001e8a2  mov     dword ptr [rsp+0C0h+Timeout], r14d
0x14001e8a7  mov     rcx, rbx
0x14001e8aa  mov     qword ptr [rsp+0C0h+Alertable], rsi
0x14001e8af  mov     qword ptr [rbp+57h+var_38], rax
0x14001e8b3  mov     dword ptr [rsp+0C0h+WaitMode], 30h ; '0'
0x14001e8bb  call    SynchronousFsControl
0x14001e8c0  mov     edi, eax
0x14001e8c2  cmp     eax, 1
0x14001e8c5  jnz     short loc_14001E862
0x14001e8c7  xor     edx, edx
0x14001e8c9  lea     rcx, [rbx+108h]
0x14001e8d0  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001e8d7  nop     dword ptr [rax+rax+00h]
0x14001e8dc  xor     edx, edx
0x14001e8de  mov     dword ptr [rbx+340h], 5
0x14001e8e8  lea     rcx, [rbx+108h]
0x14001e8ef  call    cs:__imp_FltReleasePushLockEx
0x14001e8f6  nop     dword ptr [rax+rax+00h]
0x14001e8fb  xor     ecx, ecx; ExitStatus
0x14001e8fd  call    cs:__imp_PsTerminateSystemThread
0x14001e904  nop     dword ptr [rax+rax+00h]
0x14001e909  mov     rcx, [rbp+57h+var_28]
0x14001e90d  xor     rcx, rsp; StackCookie
0x14001e910  call    __security_check_cookie
0x14001e915  lea     r11, [rsp+0C0h+var_20]
0x14001e91d  mov     rbx, [r11+38h]
0x14001e921  mov     rsi, [r11+40h]
0x14001e925  mov     rsp, r11
0x14001e928  pop     r15
0x14001e92a  pop     r14
0x14001e92c  pop     r12
0x14001e92e  pop     rdi
0x14001e92f  pop     rbp
0x14001e930  retn
0x14001e932  mov     [rbx+344h], r15b
0x14001e939  lock inc cs:dword_14000F2F8
0x14001e940  mov     rcx, [rbx+20h]
0x14001e944  lea     r9, ClearFileTablePostWorker
0x14001e94b  xor     r8d, r8d
0x14001e94e  mov     qword ptr [rsp+0C0h+WaitMode], 1
0x14001e957  xor     edx, edx
0x14001e959  call    LuafvEnumerateFileTable
0x14001e95e  cmp     edi, r12d
0x14001e961  jnz     short loc_14001E9AE
0x14001e963  mov     [rsp+0C0h+WaitBlockArray], r15; WaitBlockArray
0x14001e968  lea     rax, [rbx+70h]
0x14001e96c  mov     [rbp+57h+Object], rax
0x14001e970  lea     rdx, [rbp+57h+Object]; Object
0x14001e974  lea     rax, [rbx+0B8h]
0x14001e97b  mov     [rsp+0C0h+Timeout], r15; Timeout
0x14001e980  mov     [rsp+0C0h+Alertable], r15b; Alertable
0x14001e985  xor     r9d, r9d; WaitReason
0x14001e988  mov     r8d, 1; WaitType
0x14001e98e  mov     [rbp+57h+Object+8], rax
0x14001e992  mov     ecx, r12d; Count
0x14001e995  mov     [rsp+0C0h+WaitMode], r15b; WaitMode
0x14001e99a  call    cs:__imp_KeWaitForMultipleObjects
0x14001e9a1  nop     dword ptr [rax+rax+00h]
0x14001e9a6  test    eax, eax
0x14001e9a8  jz      loc_14001E8C7
0x14001e9ae  mov     rcx, rbx
0x14001e9b1  call    InitializeUsn
0x14001e9b6  mov     edi, eax
0x14001e9b8  cmp     eax, 1
0x14001e9bb  jz      loc_14001E8C7
0x14001e9c1  cmp     eax, r12d
0x14001e9c4  jz      short loc_14001E95E
0x14001e9c6  test    eax, eax
0x14001e9c8  jns     short loc_14001EA3E
0x14001e9ca  mov     [rsp+0C0h+WaitBlockArray], r15; WaitBlockArray
0x14001e9cf  lea     rax, [rbx+70h]
0x14001e9d3  mov     [rbp+57h+Object], rax
0x14001e9d7  lea     rdx, [rbp+57h+Object]; Object
0x14001e9db  lea     rax, [rbx+88h]
0x14001e9e2  mov     qword ptr [rbp+57h+var_70], 0FFFFFFFFFA0A1F00h
0x14001e9ea  mov     [rbp+57h+Object+8], rax
0x14001e9ee  xor     r9d, r9d; WaitReason
0x14001e9f1  lea     rax, [rbp+57h+var_70]
0x14001e9f5  mov     r8d, 1; WaitType
0x14001e9fb  mov     [rsp+0C0h+Timeout], rax; Timeout
0x14001ea00  mov     ecx, r12d; Count
0x14001ea03  mov     [rsp+0C0h+Alertable], r15b; Alertable
0x14001ea08  mov     [rsp+0C0h+WaitMode], r15b; WaitMode
0x14001ea0d  call    cs:__imp_KeWaitForMultipleObjects
0x14001ea14  nop     dword ptr [rax+rax+00h]
0x14001ea19  test    eax, eax
0x14001ea1b  jz      loc_14001E8C7
0x14001ea21  cmp     eax, 1
0x14001ea24  jnz     short loc_14001EA36
0x14001ea26  mov     rcx, rbx
0x14001ea29  call    AcknowledgePauseRequest
0x14001ea2e  mov     edi, r12d
0x14001ea31  jmp     loc_14001E95E
0x14001ea36  mov     edi, r15d
0x14001ea39  jmp     loc_14001E95E
0x14001ea3e  mov     byte ptr [rbx+344h], 1
0x14001ea45  lock dec cs:dword_14000F2F8
0x14001ea4c  jmp     loc_14001E882
```
