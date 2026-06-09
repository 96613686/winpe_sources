# CWorkManager::WorkManagerThread(void *)

- ea: `0x18004a8e0`
- end: `0x18004aa88`
- name: `?WorkManagerThread@CWorkManager@@CAIPEAX@Z`
- size: `424`
- prototype: `unsigned int __stdcall(void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x18001ad48`
- `0x18001ad74`
- `0x180049824`
- `0x180049cb8`
- `0x18004a8e0`

## import_xrefs

- `msvcrt!_endthreadex` at `0x18004aa5e`
- `msvcrt!_endthreadex` at `0x18004aa5e`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18004a969`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18004a969`
- `KERNEL32!GenerateConsoleCtrlEvent` at `0x18004aa50`
- `KERNEL32!GenerateConsoleCtrlEvent` at `0x18004aa50`
- `KERNEL32!ResetEvent` at `0x18004a9ea`
- `KERNEL32!ResetEvent` at `0x18004a9ea`

## pseudocode

```c
__int64 __fastcall CWorkManager::WorkManagerThread(HANDLE *a1)
{
  unsigned int TimeToNextJob; // esi
  unsigned int v3; // ebx
  PVOID *v4; // rcx
  DWORD v5; // ebp
  HANDLE Handles[3]; // [rsp+30h] [rbp-18h] BYREF

  Handles[0] = a1[18];
  TimeToNextJob = -1;
  Handles[1] = a1[17];
  v3 = 0;
LABEL_2:
  v4 = (PVOID *)WPP_GLOBAL_Control;
  while ( !v3 )
  {
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
      WPP_SF_D(v4[2], 28, &WPP_0ce7f016aabd318d7b95e346aacd31e1_Traceguids, TimeToNextJob);
    v5 = WaitForMultipleObjectsEx(2u, Handles, 0, 1000 * TimeToNextJob, 1);
    switch ( v5 )
    {
      case 0u:
        v3 = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_0ce7f016aabd318d7b95e346aacd31e1_Traceguids);
        goto LABEL_25;
      case 1u:
        ResetEvent(a1[17]);
        goto LABEL_15;
      case 0x102u:
        v3 = CWorkManager::ProcessScheduledJob((CWorkManager *)a1);
LABEL_15:
        TimeToNextJob = CWorkManager::GetTimeToNextJob((CWorkManager *)a1);
        goto LABEL_2;
    }
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_0ce7f016aabd318d7b95e346aacd31e1_Traceguids, 0);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    v3 = -1071579136;
  }
  if ( v3 != 1075904514 )
  {
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 )
      WPP_SF_D(v4[2], 31, &WPP_0ce7f016aabd318d7b95e346aacd31e1_Traceguids, v3);
    GenerateConsoleCtrlEvent(0, 0);
  }
LABEL_25:
  _endthreadex(v3);
  return v3;
}

```

## disassembly

```asm
0x18004a8e0  mov     r11, rsp
0x18004a8e3  mov     [r11+8], rbx
0x18004a8e7  mov     [r11+10h], rbp
0x18004a8eb  mov     [r11+18h], rsi
0x18004a8ef  mov     [r11+20h], rdi
0x18004a8f3  push    r14
0x18004a8f5  sub     rsp, 40h
0x18004a8f9  mov     rax, [rcx+90h]
0x18004a900  lea     r14, WPP_GLOBAL_Control
0x18004a907  mov     [r11-18h], rax
0x18004a90b  or      esi, 0FFFFFFFFh
0x18004a90e  mov     rax, [rcx+88h]
0x18004a915  mov     rdi, rcx
0x18004a918  mov     [r11-10h], rax
0x18004a91c  xor     ebx, ebx
0x18004a91e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a925  test    ebx, ebx
0x18004a927  jnz     loc_18004AA21
0x18004a92d  cmp     rcx, r14
0x18004a930  jz      short loc_18004A94E
0x18004a932  test    byte ptr [rcx+1Ch], 20h
0x18004a936  jz      short loc_18004A94E
0x18004a938  mov     rcx, [rcx+10h]
0x18004a93c  lea     edx, [rbx+1Ch]
0x18004a93f  mov     r9d, esi
0x18004a942  lea     r8, WPP_0ce7f016aabd318d7b95e346aacd31e1_Traceguids
0x18004a949  call    WPP_SF_D
0x18004a94e  xor     r8d, r8d; bWaitAll
0x18004a951  imul    r9d, esi, 3E8h; dwMilliseconds
0x18004a958  lea     rdx, [rsp+48h+Handles]; lpHandles
0x18004a95d  mov     [rsp+48h+bAlertable], 1; bAlertable
0x18004a965  lea     ecx, [r8+2]; nCount
0x18004a969  call    cs:__imp_WaitForMultipleObjectsEx
0x18004a970  nop     dword ptr [rax+rax+00h]
0x18004a975  mov     ebp, eax
0x18004a977  mov     ecx, eax
0x18004a979  test    eax, eax
0x18004a97b  jz      short loc_18004A9F8
0x18004a97d  sub     ecx, 1
0x18004a980  jz      short loc_18004A9E3
0x18004a982  cmp     ecx, 101h
0x18004a988  jz      short loc_18004A9CA
0x18004a98a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a991  cmp     rcx, r14
0x18004a994  jz      short loc_18004A9BB
0x18004a996  test    byte ptr [rcx+1Ch], 40h
0x18004a99a  jz      short loc_18004A9BB
0x18004a99c  mov     rcx, [rcx+10h]
0x18004a9a0  lea     r8, WPP_0ce7f016aabd318d7b95e346aacd31e1_Traceguids
0x18004a9a7  mov     edx, 1Eh
0x18004a9ac  xor     r9d, r9d
0x18004a9af  call    WPP_SF_D
0x18004a9b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a9bb  mov     ebx, 0C0210000h
0x18004a9c0  test    ebp, ebp
0x18004a9c2  jnz     loc_18004A925
0x18004a9c8  jmp     short loc_18004AA29
0x18004a9ca  mov     rcx, rdi; this
0x18004a9cd  call    ?ProcessScheduledJob@CWorkManager@@AEAAKXZ; CWorkManager::ProcessScheduledJob(void)
0x18004a9d2  mov     ebx, eax
0x18004a9d4  mov     rcx, rdi; this
0x18004a9d7  call    ?GetTimeToNextJob@CWorkManager@@AEAAKXZ; CWorkManager::GetTimeToNextJob(void)
0x18004a9dc  mov     esi, eax
0x18004a9de  jmp     loc_18004A91E
0x18004a9e3  mov     rcx, [rdi+88h]; hEvent
0x18004a9ea  call    cs:__imp_ResetEvent
0x18004a9f1  nop     dword ptr [rax+rax+00h]
0x18004a9f6  jmp     short loc_18004A9D4
0x18004a9f8  xor     ebx, ebx
0x18004a9fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18004aa01  cmp     rcx, r14
0x18004aa04  jz      short loc_18004AA5C
0x18004aa06  test    byte ptr [rcx+1Ch], 40h
0x18004aa0a  jz      short loc_18004AA5C
0x18004aa0c  mov     rcx, [rcx+10h]
0x18004aa10  lea     edx, [rbx+1Dh]
0x18004aa13  lea     r8, WPP_0ce7f016aabd318d7b95e346aacd31e1_Traceguids
0x18004aa1a  call    WPP_SF_
0x18004aa1f  jmp     short loc_18004AA5C
0x18004aa21  cmp     ebx, 40210002h
0x18004aa27  jz      short loc_18004AA5C
0x18004aa29  cmp     rcx, r14
0x18004aa2c  jz      short loc_18004AA4C
0x18004aa2e  test    byte ptr [rcx+1Ch], 40h
0x18004aa32  jz      short loc_18004AA4C
0x18004aa34  mov     rcx, [rcx+10h]
0x18004aa38  lea     r8, WPP_0ce7f016aabd318d7b95e346aacd31e1_Traceguids
0x18004aa3f  mov     edx, 1Fh
0x18004aa44  mov     r9d, ebx
0x18004aa47  call    WPP_SF_D
0x18004aa4c  xor     edx, edx; dwProcessGroupId
0x18004aa4e  xor     ecx, ecx; dwCtrlEvent
0x18004aa50  call    cs:__imp_GenerateConsoleCtrlEvent
0x18004aa57  nop     dword ptr [rax+rax+00h]
0x18004aa5c  mov     ecx, ebx; ReturnCode
0x18004aa5e  call    cs:__imp__endthreadex
0x18004aa65  nop     dword ptr [rax+rax+00h]
0x18004aa6a  mov     rbp, [rsp+48h+arg_8]
0x18004aa6f  mov     eax, ebx
0x18004aa71  mov     rbx, [rsp+48h+arg_0]
0x18004aa76  mov     rsi, [rsp+48h+arg_10]
0x18004aa7b  mov     rdi, [rsp+48h+arg_18]
0x18004aa80  add     rsp, 40h
0x18004aa84  pop     r14
0x18004aa86  retn
```
