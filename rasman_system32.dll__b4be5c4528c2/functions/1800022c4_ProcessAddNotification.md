# ProcessAddNotification

- ea: `0x1800022c4`
- end: `0x18000240c`
- name: `ProcessAddNotification`
- size: `328`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180001250`

## callees

- `0x1800010e8`
- `0x180001160`
- `0x1800022c4`
- `0x180002414`
- `0x18000254c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800022e4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800022e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800023ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800023ca`
- `rtutils!TracePrintfExA` at `0x180002358`
- `rtutils!TracePrintfExA` at `0x1800023b7`
- `rtutils!TracePrintfExA` at `0x1800023f0`
- `rtutils!TracePrintfExA` at `0x180002358`
- `rtutils!TracePrintfExA` at `0x1800023b7`
- `rtutils!TracePrintfExA` at `0x1800023f0`

## string_xrefs

- `0x180002317`: `ProcessAddNotification: InitializeRasmanMonitorThread failed, Error=%d`
- `0x18000234c`: `Rasman Service Status when ProcessAddNotification called for first time: %d`

## pseudocode

```c
__int64 __fastcall ProcessAddNotification(__int64 a1, __int64 a2, unsigned int a3, unsigned int a4)
{
  DWORD v8; // ecx
  unsigned int v9; // eax
  unsigned int v10; // ebx
  int v11; // eax
  unsigned int v12; // eax

  EnterCriticalSection(&g_RasCriticalSection);
  if ( g_fRasmanMonitorThread )
    goto LABEL_7;
  v9 = InitializeRasmanMonitorThread();
  v10 = v9;
  if ( v9 )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "ProcessAddNotification: InitializeRasmanMonitorThread failed, Error=%d", v9);
    goto LABEL_13;
  }
  g_fRasmanMonitorThread = 1;
  v11 = IsServiceRunning();
  v8 = g_dwTraceId;
  g_fRasmanStarted = v11;
  g_fRCNInitialized = v11;
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(
      g_dwTraceId,
      0xCu,
      "Rasman Service Status when ProcessAddNotification called for first time: %d",
      v11);
LABEL_7:
    v11 = g_fRasmanStarted;
  }
  if ( !v11 || (v10 = RasmanAddNotification(a1, a2, a3, a4)) == 0 )
  {
    v12 = AddNotifierToList(v8, a1, a2, a3, a4);
    v10 = v12;
    if ( v12 )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "ProcessAddNotification: AddNotifierList failed, Error=%d", v12);
    }
  }
LABEL_13:
  LeaveCriticalSection(&g_RasCriticalSection);
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "ProcessAddNotification exiting ... %d", v10);
  return v10;
}

```

## disassembly

```asm
0x1800022c4  push    rbx
0x1800022c6  push    rbp
0x1800022c7  push    rsi
0x1800022c8  push    rdi
0x1800022c9  push    r14
0x1800022cb  push    r15
0x1800022cd  sub     rsp, 38h
0x1800022d1  mov     r14, rcx
0x1800022d4  mov     edi, r9d
0x1800022d7  lea     rcx, g_RasCriticalSection; lpCriticalSection
0x1800022de  mov     esi, r8d
0x1800022e1  mov     rbp, rdx
0x1800022e4  call    cs:__imp_EnterCriticalSection
0x1800022eb  nop     dword ptr [rax+rax+00h]
0x1800022f0  or      r15d, 0FFFFFFFFh
0x1800022f4  cmp     cs:g_fRasmanMonitorThread, 0
0x1800022fb  jnz     short loc_180002364
0x1800022fd  call    InitializeRasmanMonitorThread
0x180002302  mov     ebx, eax
0x180002304  test    eax, eax
0x180002306  jz      short loc_180002323
0x180002308  mov     ecx, cs:g_dwTraceId
0x18000230e  cmp     ecx, r15d
0x180002311  jz      loc_1800023C3
0x180002317  lea     r8, aProcessaddnoti_1; "ProcessAddNotification: InitializeRasma"...
0x18000231e  jmp     loc_1800023AF
0x180002323  mov     cs:g_fRasmanMonitorThread, 1
0x18000232d  call    IsServiceRunning
0x180002332  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180002338  mov     cs:g_fRasmanStarted, eax
0x18000233e  mov     cs:g_fRCNInitialized, eax
0x180002344  cmp     ecx, r15d
0x180002347  jz      short loc_18000236A
0x180002349  mov     r9d, eax
0x18000234c  lea     r8, aRasmanServiceS; "Rasman Service Status when ProcessAddNo"...
0x180002353  mov     edx, 0Ch; dwFlags
0x180002358  call    cs:__imp_TracePrintfExA
0x18000235f  nop     dword ptr [rax+rax+00h]
0x180002364  mov     eax, cs:g_fRasmanStarted
0x18000236a  test    eax, eax
0x18000236c  jz      short loc_180002385
0x18000236e  mov     r9d, edi
0x180002371  mov     r8d, esi
0x180002374  mov     rdx, rbp
0x180002377  mov     rcx, r14
0x18000237a  call    RasmanAddNotification
0x18000237f  mov     ebx, eax
0x180002381  test    eax, eax
0x180002383  jnz     short loc_1800023C3
0x180002385  mov     r9d, esi
0x180002388  mov     [rsp+68h+var_48], edi
0x18000238c  mov     r8, rbp
0x18000238f  mov     rdx, r14
0x180002392  call    AddNotifierToList
0x180002397  mov     ebx, eax
0x180002399  test    eax, eax
0x18000239b  jz      short loc_1800023C3
0x18000239d  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800023a3  cmp     ecx, r15d
0x1800023a6  jz      short loc_1800023C3
0x1800023a8  lea     r8, aProcessaddnoti_0; "ProcessAddNotification: AddNotifierList"...
0x1800023af  mov     r9d, eax
0x1800023b2  mov     edx, 0Ch; dwFlags
0x1800023b7  call    cs:__imp_TracePrintfExA
0x1800023be  nop     dword ptr [rax+rax+00h]
0x1800023c3  lea     rcx, g_RasCriticalSection; lpCriticalSection
0x1800023ca  call    cs:__imp_LeaveCriticalSection
0x1800023d1  nop     dword ptr [rax+rax+00h]
0x1800023d6  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800023dc  cmp     ecx, r15d
0x1800023df  jz      short loc_1800023FC
0x1800023e1  mov     r9d, ebx
0x1800023e4  lea     r8, aProcessaddnoti; "ProcessAddNotification exiting ... %d"
0x1800023eb  mov     edx, 0Ch; dwFlags
0x1800023f0  call    cs:__imp_TracePrintfExA
0x1800023f7  nop     dword ptr [rax+rax+00h]
0x1800023fc  mov     eax, ebx
0x1800023fe  add     rsp, 38h
0x180002402  pop     r15
0x180002404  pop     r14
0x180002406  pop     rdi
0x180002407  pop     rsi
0x180002408  pop     rbp
0x180002409  pop     rbx
0x18000240a  retn
```
