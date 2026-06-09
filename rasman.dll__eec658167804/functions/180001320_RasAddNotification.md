# RasAddNotification

- ea: `0x180001320`
- end: `0x1800014f2`
- name: `RasAddNotification`
- size: `466`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation`

## callees

- `0x180001320`
- `0x180001c70`
- `0x180001fd0`
- `0x1800021c0`
- `0x180002504`
- `0x180002f80`
- `0x180021000`
- `0x180021a48`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000136f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000136f`
- `rtutils!TracePrintfExA` at `0x1800013ec`
- `rtutils!TracePrintfExA` at `0x180001430`
- `rtutils!TracePrintfExA` at `0x1800014a7`
- `rtutils!TracePrintfExA` at `0x1800013ec`
- `rtutils!TracePrintfExA` at `0x180001430`
- `rtutils!TracePrintfExA` at `0x1800014a7`

## string_xrefs

- `0x1800013d4`: `RasAddNotification called, hconn= %d, hevent= 0x%x, dwfFlags= 0x%x, ProcessId= %d`

## pseudocode

```c
__int64 __fastcall RasAddNotification(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // edi
  DWORD CurrentProcessId; // eax
  unsigned int v7; // ebx
  int v8; // eax
  unsigned int v9; // ebx
  unsigned int v10; // eax
  PVOID *v11; // rcx
  __int64 v13; // [rsp+20h] [rbp-38h]
  int v14; // [rsp+78h] [rbp+20h] BYREF

  v3 = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_qqD(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a1, a2, a3);
  }
  CurrentProcessId = GetCurrentProcessId();
  v7 = CurrentProcessId;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      471,
      &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids,
      CurrentProcessId);
  }
  v14 = 0;
  GetProcessLowBoxStatus(&v14);
  if ( !v14 )
    DebugInitEx();
  if ( g_dwTraceId != -1 )
    TracePrintfExA(
      g_dwTraceId,
      0xCu,
      "RasAddNotification called, hconn= %d, hevent= 0x%x, dwfFlags= 0x%x, ProcessId= %d",
      a1,
      a2,
      v3,
      v7);
  if ( !(unsigned int)IsRasmanProcess() )
  {
    v8 = ProcessAddNotification(a1, a2, v3, v7);
    v9 = v8;
    if ( v8 )
    {
      if ( g_dwTraceId == -1 )
      {
LABEL_25:
        v11 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_26;
      }
      TracePrintfExA(g_dwTraceId, 0xCu, "RasAddNotification: ProcessAddNotification failed, Error=%d", v8);
    }
    goto LABEL_22;
  }
  LODWORD(v13) = v3;
  v10 = SubmitLocalRequest(0x46u, v7, a1, a2, v13);
  v9 = v10;
  if ( !v10 )
  {
LABEL_22:
    v11 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_23;
  }
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 473, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v10);
    goto LABEL_22;
  }
LABEL_23:
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "RasAddNotification exiting ... %d", v9);
    goto LABEL_25;
  }
LABEL_26:
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 0x40) != 0 && *((_BYTE *)v11 + 25) >= 6u )
    WPP_SF_d(v11[2], 474, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x180001320  mov     rax, rsp
0x180001323  mov     [rax+8], rbx
0x180001327  mov     [rax+10h], rbp
0x18000132b  push    rsi
0x18000132c  push    rdi
0x18000132d  push    r12
0x18000132f  sub     rsp, 40h
0x180001333  mov     edi, r8d
0x180001336  mov     rsi, rdx
0x180001339  mov     rbp, rcx
0x18000133c  mov     rcx, cs:WPP_GLOBAL_Control
0x180001343  lea     r12, WPP_GLOBAL_Control
0x18000134a  cmp     rcx, r12
0x18000134d  jz      short loc_18000136F
0x18000134f  test    byte ptr [rcx+1Ch], 40h
0x180001353  jz      short loc_18000136F
0x180001355  cmp     byte ptr [rcx+19h], 6
0x180001359  jb      short loc_18000136F
0x18000135b  mov     rcx, [rcx+10h]
0x18000135f  mov     r9, rbp
0x180001362  mov     [rax-30h], r8d
0x180001366  mov     [rax-38h], rdx
0x18000136a  call    WPP_SF_qqD
0x18000136f  call    cs:__imp_GetCurrentProcessId
0x180001375  mov     ebx, eax
0x180001377  mov     rcx, cs:WPP_GLOBAL_Control
0x18000137e  cmp     rcx, r12
0x180001381  jz      short loc_1800013A7
0x180001383  test    byte ptr [rcx+1Ch], 40h
0x180001387  jz      short loc_1800013A7
0x180001389  cmp     byte ptr [rcx+19h], 5
0x18000138d  jb      short loc_1800013A7
0x18000138f  mov     rcx, [rcx+10h]
0x180001393  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18000139a  mov     edx, 1D7h
0x18000139f  mov     r9d, eax
0x1800013a2  call    WPP_SF_d
0x1800013a7  lea     rcx, [rsp+58h+arg_18]
0x1800013ac  mov     [rsp+58h+arg_18], 0
0x1800013b4  call    GetProcessLowBoxStatus
0x1800013b9  cmp     [rsp+58h+arg_18], 0
0x1800013be  jnz     short loc_1800013C5
0x1800013c0  call    DebugInitEx
0x1800013c5  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800013cb  cmp     ecx, 0FFFFFFFFh
0x1800013ce  jz      short loc_1800013F2
0x1800013d0  mov     [rsp+58h+var_28], ebx
0x1800013d4  lea     r8, aRasaddnotifica_3; "RasAddNotification called, hconn= %d, h"...
0x1800013db  mov     [rsp+58h+var_30], edi
0x1800013df  mov     r9, rbp
0x1800013e2  mov     edx, 0Ch; dwFlags
0x1800013e7  mov     [rsp+58h+var_38], rsi
0x1800013ec  call    cs:__imp_TracePrintfExA
0x1800013f2  call    IsRasmanProcess
0x1800013f7  test    eax, eax
0x1800013f9  jnz     short loc_180001438
0x1800013fb  mov     r9d, ebx
0x1800013fe  mov     r8d, edi
0x180001401  mov     rdx, rsi
0x180001404  mov     rcx, rbp
0x180001407  call    ProcessAddNotification
0x18000140c  mov     ebx, eax
0x18000140e  test    eax, eax
0x180001410  jz      short loc_180001484
0x180001412  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180001418  cmp     ecx, 0FFFFFFFFh
0x18000141b  jz      loc_1800014AD
0x180001421  mov     r9d, eax
0x180001424  lea     r8, aRasaddnotifica_2; "RasAddNotification: ProcessAddNotificat"...
0x18000142b  mov     edx, 0Ch; dwFlags
0x180001430  call    cs:__imp_TracePrintfExA
0x180001436  jmp     short loc_180001484
0x180001438  mov     ecx, 46h ; 'F'
0x18000143d  mov     dword ptr [rsp+58h+var_38], edi
0x180001441  mov     r9, rsi
0x180001444  mov     r8, rbp
0x180001447  mov     edx, ebx
0x180001449  call    SubmitLocalRequest
0x18000144e  mov     ebx, eax
0x180001450  test    eax, eax
0x180001452  jz      short loc_180001484
0x180001454  mov     rcx, cs:WPP_GLOBAL_Control
0x18000145b  cmp     rcx, r12
0x18000145e  jz      short loc_18000148B
0x180001460  test    byte ptr [rcx+1Ch], 40h
0x180001464  jz      short loc_18000148B
0x180001466  cmp     byte ptr [rcx+19h], 2
0x18000146a  jb      short loc_18000148B
0x18000146c  mov     rcx, [rcx+10h]
0x180001470  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180001477  mov     edx, 1D9h
0x18000147c  mov     r9d, eax
0x18000147f  call    WPP_SF_d
0x180001484  mov     rcx, cs:WPP_GLOBAL_Control
0x18000148b  mov     eax, cs:g_dwTraceId
0x180001491  cmp     eax, 0FFFFFFFFh
0x180001494  jz      short loc_1800014B4
0x180001496  mov     r9d, ebx
0x180001499  lea     r8, aRasaddnotifica_1; "RasAddNotification exiting ... %d"
0x1800014a0  mov     edx, 0Ch; dwFlags
0x1800014a5  mov     ecx, eax; dwTraceID
0x1800014a7  call    cs:__imp_TracePrintfExA
0x1800014ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800014b4  cmp     rcx, r12
0x1800014b7  jz      short loc_1800014DD
0x1800014b9  test    byte ptr [rcx+1Ch], 40h
0x1800014bd  jz      short loc_1800014DD
0x1800014bf  cmp     byte ptr [rcx+19h], 6
0x1800014c3  jb      short loc_1800014DD
0x1800014c5  mov     rcx, [rcx+10h]
0x1800014c9  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800014d0  mov     edx, 1DAh
0x1800014d5  mov     r9d, ebx
0x1800014d8  call    WPP_SF_d
0x1800014dd  mov     rbp, [rsp+58h+arg_8]
0x1800014e2  mov     eax, ebx
0x1800014e4  mov     rbx, [rsp+58h+arg_0]
0x1800014e9  add     rsp, 40h
0x1800014ed  pop     r12
0x1800014ef  pop     rdi
0x1800014f0  pop     rsi
0x1800014f1  retn
```
