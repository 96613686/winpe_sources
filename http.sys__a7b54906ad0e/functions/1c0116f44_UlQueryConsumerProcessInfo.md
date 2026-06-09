# UlQueryConsumerProcessInfo

- ea: `0x1c0116f44`
- end: `0x1c01170be`
- name: `UlQueryConsumerProcessInfo`
- size: `378`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1c002e754`
- `0x1c0117bc4`

## callees

- `0x1c001a4b0`
- `0x1c001b900`
- `0x1c0059024`
- `0x1c008f374`
- `0x1c008f3ec`
- `0x1c0116f44`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x1c0116fdf`
- `ntoskrnl!PsGetThreadId` at `0x1c0117030`
- `ntoskrnl!PsGetThreadId` at `0x1c0116fdf`
- `ntoskrnl!PsGetThreadId` at `0x1c0117030`
- `ntoskrnl!ZwQueryInformationProcess` at `0x1c0117011`
- `ntoskrnl!ZwQueryInformationProcess` at `0x1c0117011`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1c0117058`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1c0117058`
- `ntoskrnl!PsGetProcessId` at `0x1c0116fc6`
- `ntoskrnl!PsGetProcessId` at `0x1c0117044`
- `ntoskrnl!PsGetProcessId` at `0x1c0116fc6`
- `ntoskrnl!PsGetProcessId` at `0x1c0117044`

## pseudocode

```c
__int64 __fastcall UlQueryConsumerProcessInfo(__int64 a1, __int64 a2)
{
  NTSTATUS InformationProcess; // edi
  struct _KPROCESS *v5; // rcx
  ULONG ReturnLength[4]; // [rsp+30h] [rbp-88h] BYREF
  _QWORD ProcessInformation[12]; // [rsp+40h] [rbp-78h] BYREF

  InformationProcess = 0;
  memset(ProcessInformation, 0, 0x58u);
  ReturnLength[0] = 0;
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_qq(220, WPP_95173837b5773721cd51a44381a2b960_Traceguids, a1, a2);
  if ( !*(_BYTE *)(a2 + 92) )
  {
    if ( a1 )
    {
      InformationProcess = ZwQueryInformationProcess(
                             *(HANDLE *)(a1 + 80),
                             ProcessVmCounters,
                             ProcessInformation,
                             0x58u,
                             ReturnLength);
      if ( InformationProcess < 0 )
        goto LABEL_9;
      *(_QWORD *)(a2 + 80) = ProcessInformation[4];
      *(_QWORD *)(a2 + 64) = PsGetThreadId(*(PETHREAD *)(a1 + 88));
      *(_QWORD *)(a2 + 56) = PsGetProcessId(*(PEPROCESS *)(a1 + 72));
      *(_QWORD *)(a2 + 72) = PsGetProcessImageFileName(*(_QWORD *)(a1 + 72));
      *(_DWORD *)(a2 + 88) = GetProcessActiveThreadCount(*(_QWORD *)(a1 + 72));
    }
    else
    {
      v5 = UxSystemProcess;
      *(_QWORD *)(a2 + 72) = "SYSTEM";
      *(_QWORD *)(a2 + 56) = PsGetProcessId(v5);
      *(_QWORD *)(a2 + 64) = PsGetThreadId(KeGetCurrentThread());
    }
    *(_BYTE *)(a2 + 92) = 1;
  }
LABEL_9:
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_D(221, WPP_95173837b5773721cd51a44381a2b960_Traceguids);
  return (unsigned int)InformationProcess;
}

```

## disassembly

```asm
0x1c0116f44  mov     [rsp+arg_10], rbx
0x1c0116f49  mov     [rsp+arg_18], rsi
0x1c0116f4e  push    rdi
0x1c0116f4f  sub     rsp, 0B0h
0x1c0116f56  mov     rax, cs:__security_cookie
0x1c0116f5d  xor     rax, rsp
0x1c0116f60  mov     [rsp+0B8h+var_18], rax
0x1c0116f68  mov     rbx, rdx
0x1c0116f6b  mov     rsi, rcx
0x1c0116f6e  xor     edi, edi
0x1c0116f70  lea     rcx, [rsp+0B8h+ProcessInformation]; void *
0x1c0116f75  xor     edx, edx; Val
0x1c0116f77  lea     r8d, [rdi+58h]; Size
0x1c0116f7b  call    memset
0x1c0116f80  and     [rsp+0B8h+var_88], edi
0x1c0116f84  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c0116f8a  test    al, al
0x1c0116f8c  jns     short loc_1C0116FA5
0x1c0116f8e  mov     ecx, 0DCh
0x1c0116f93  lea     rdx, WPP_95173837b5773721cd51a44381a2b960_Traceguids
0x1c0116f9a  mov     r9, rbx
0x1c0116f9d  mov     r8, rsi
0x1c0116fa0  call    WPP_SF_qq
0x1c0116fa5  cmp     [rbx+5Ch], dil
0x1c0116fa9  jnz     loc_1C0117078
0x1c0116faf  test    rsi, rsi
0x1c0116fb2  jnz     short loc_1C0116FF4
0x1c0116fb4  mov     rcx, cs:UxSystemProcess; Process
0x1c0116fbb  lea     rax, aSystem_0; "SYSTEM"
0x1c0116fc2  mov     [rbx+48h], rax
0x1c0116fc6  call    cs:__imp_PsGetProcessId
0x1c0116fcd  nop     dword ptr [rax+rax+00h]
0x1c0116fd2  mov     [rbx+38h], rax
0x1c0116fd6  mov     rcx, gs:188h; Thread
0x1c0116fdf  call    cs:__imp_PsGetThreadId
0x1c0116fe6  nop     dword ptr [rax+rax+00h]
0x1c0116feb  mov     [rbx+40h], rax
0x1c0116fef  jmp     loc_1C0117074
0x1c0116ff4  mov     rcx, [rsi+50h]; ProcessHandle
0x1c0116ff8  lea     rax, [rsp+0B8h+var_88]
0x1c0116ffd  mov     r9d, 58h ; 'X'; ProcessInformationLength
0x1c0117003  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x1c0117008  lea     r8, [rsp+0B8h+ProcessInformation]; ProcessInformation
0x1c011700d  lea     edx, [r9-55h]; ProcessInformationClass
0x1c0117011  call    cs:__imp_ZwQueryInformationProcess
0x1c0117018  nop     dword ptr [rax+rax+00h]
0x1c011701d  mov     edi, eax
0x1c011701f  test    eax, eax
0x1c0117021  js      short loc_1C0117078
0x1c0117023  mov     rcx, [rsp+0B8h+var_58]
0x1c0117028  mov     [rbx+50h], rcx
0x1c011702c  mov     rcx, [rsi+58h]; Thread
0x1c0117030  call    cs:__imp_PsGetThreadId
0x1c0117037  nop     dword ptr [rax+rax+00h]
0x1c011703c  mov     [rbx+40h], rax
0x1c0117040  mov     rcx, [rsi+48h]; Process
0x1c0117044  call    cs:__imp_PsGetProcessId
0x1c011704b  nop     dword ptr [rax+rax+00h]
0x1c0117050  mov     [rbx+38h], rax
0x1c0117054  mov     rcx, [rsi+48h]
0x1c0117058  call    cs:__imp_PsGetProcessImageFileName
0x1c011705f  nop     dword ptr [rax+rax+00h]
0x1c0117064  mov     [rbx+48h], rax
0x1c0117068  mov     rcx, [rsi+48h]
0x1c011706c  call    GetProcessActiveThreadCount
0x1c0117071  mov     [rbx+58h], eax
0x1c0117074  mov     byte ptr [rbx+5Ch], 1
0x1c0117078  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c011707e  test    al, al
0x1c0117080  jns     short loc_1C0117096
0x1c0117082  mov     ecx, 0DDh
0x1c0117087  lea     rdx, WPP_95173837b5773721cd51a44381a2b960_Traceguids
0x1c011708e  mov     r8d, edi
0x1c0117091  call    WPP_SF_D
0x1c0117096  mov     eax, edi
0x1c0117098  mov     rcx, [rsp+0B8h+var_18]
0x1c01170a0  xor     rcx, rsp; StackCookie
0x1c01170a3  call    __security_check_cookie
0x1c01170a8  lea     r11, [rsp+0B8h+var_8]
0x1c01170b0  mov     rbx, [r11+20h]
0x1c01170b4  mov     rsi, [r11+28h]
0x1c01170b8  mov     rsp, r11
0x1c01170bb  pop     rdi
0x1c01170bc  retn
```
