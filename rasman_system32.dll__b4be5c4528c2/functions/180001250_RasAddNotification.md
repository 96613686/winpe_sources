# RasAddNotification

- ea: `0x180001250`
- end: `0x18000143b`
- name: `RasAddNotification`
- size: `491`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation`

## callees

- `0x180001250`
- `0x180001c40`
- `0x180001ff0`
- `0x180002200`
- `0x1800022c4`
- `0x1800030d0`
- `0x180021b14`
- `0x1800225fc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000129f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000129f`
- `rtutils!TracePrintfExA` at `0x180001322`
- `rtutils!TracePrintfExA` at `0x18000136c`
- `rtutils!TracePrintfExA` at `0x1800013e9`
- `rtutils!TracePrintfExA` at `0x180001322`
- `rtutils!TracePrintfExA` at `0x18000136c`
- `rtutils!TracePrintfExA` at `0x1800013e9`

## string_xrefs

- `0x18000130a`: `RasAddNotification called, hconn= %d, hevent= 0x%x, dwfFlags= 0x%x, ProcessId= %d`

## pseudocode

```c
__int64 __fastcall RasAddNotification(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // edi
  DWORD CurrentProcessId; // eax
  DWORD v7; // ebx
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
0x180001250  mov     rax, rsp
0x180001253  mov     [rax+8], rbx
0x180001257  mov     [rax+10h], rbp
0x18000125b  push    rsi
0x18000125c  push    rdi
0x18000125d  push    r12
0x18000125f  sub     rsp, 40h
0x180001263  mov     edi, r8d
0x180001266  mov     rsi, rdx
0x180001269  mov     rbp, rcx
0x18000126c  mov     rcx, cs:WPP_GLOBAL_Control
0x180001273  lea     r12, WPP_GLOBAL_Control
0x18000127a  cmp     rcx, r12
0x18000127d  jz      short loc_18000129F
0x18000127f  test    byte ptr [rcx+1Ch], 40h
0x180001283  jz      short loc_18000129F
0x180001285  cmp     byte ptr [rcx+19h], 6
0x180001289  jb      short loc_18000129F
0x18000128b  mov     rcx, [rcx+10h]
0x18000128f  mov     r9, rbp
0x180001292  mov     [rax-30h], r8d
0x180001296  mov     [rax-38h], rdx
0x18000129a  call    WPP_SF_qqD
0x18000129f  call    cs:__imp_GetCurrentProcessId
0x1800012a6  nop     dword ptr [rax+rax+00h]
0x1800012ab  mov     ebx, eax
0x1800012ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800012b4  cmp     rcx, r12
0x1800012b7  jz      short loc_1800012DD
0x1800012b9  test    byte ptr [rcx+1Ch], 40h
0x1800012bd  jz      short loc_1800012DD
0x1800012bf  cmp     byte ptr [rcx+19h], 5
0x1800012c3  jb      short loc_1800012DD
0x1800012c5  mov     rcx, [rcx+10h]
0x1800012c9  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800012d0  mov     edx, 1D7h
0x1800012d5  mov     r9d, eax
0x1800012d8  call    WPP_SF_d
0x1800012dd  lea     rcx, [rsp+58h+arg_18]
0x1800012e2  mov     [rsp+58h+arg_18], 0
0x1800012ea  call    GetProcessLowBoxStatus
0x1800012ef  cmp     [rsp+58h+arg_18], 0
0x1800012f4  jnz     short loc_1800012FB
0x1800012f6  call    DebugInitEx
0x1800012fb  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180001301  cmp     ecx, 0FFFFFFFFh
0x180001304  jz      short loc_18000132E
0x180001306  mov     [rsp+58h+var_28], ebx
0x18000130a  lea     r8, szFormat; "RasAddNotification called, hconn= %d, h"...
0x180001311  mov     [rsp+58h+var_30], edi
0x180001315  mov     r9, rbp
0x180001318  mov     edx, 0Ch; dwFlags
0x18000131d  mov     [rsp+58h+var_38], rsi
0x180001322  call    cs:__imp_TracePrintfExA
0x180001329  nop     dword ptr [rax+rax+00h]
0x18000132e  call    IsRasmanProcess
0x180001333  test    eax, eax
0x180001335  jnz     short loc_18000137A
0x180001337  mov     r9d, ebx
0x18000133a  mov     r8d, edi
0x18000133d  mov     rdx, rsi
0x180001340  mov     rcx, rbp
0x180001343  call    ProcessAddNotification
0x180001348  mov     ebx, eax
0x18000134a  test    eax, eax
0x18000134c  jz      short loc_1800013C6
0x18000134e  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180001354  cmp     ecx, 0FFFFFFFFh
0x180001357  jz      loc_1800013F5
0x18000135d  mov     r9d, eax
0x180001360  lea     r8, aRasaddnotifica_2; "RasAddNotification: ProcessAddNotificat"...
0x180001367  mov     edx, 0Ch; dwFlags
0x18000136c  call    cs:__imp_TracePrintfExA
0x180001373  nop     dword ptr [rax+rax+00h]
0x180001378  jmp     short loc_1800013C6
0x18000137a  mov     ecx, 46h ; 'F'
0x18000137f  mov     dword ptr [rsp+58h+var_38], edi
0x180001383  mov     r9, rsi
0x180001386  mov     r8, rbp
0x180001389  mov     edx, ebx
0x18000138b  call    SubmitLocalRequest
0x180001390  mov     ebx, eax
0x180001392  test    eax, eax
0x180001394  jz      short loc_1800013C6
0x180001396  mov     rcx, cs:WPP_GLOBAL_Control
0x18000139d  cmp     rcx, r12
0x1800013a0  jz      short loc_1800013CD
0x1800013a2  test    byte ptr [rcx+1Ch], 40h
0x1800013a6  jz      short loc_1800013CD
0x1800013a8  cmp     byte ptr [rcx+19h], 2
0x1800013ac  jb      short loc_1800013CD
0x1800013ae  mov     rcx, [rcx+10h]
0x1800013b2  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800013b9  mov     edx, 1D9h
0x1800013be  mov     r9d, eax
0x1800013c1  call    WPP_SF_d
0x1800013c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800013cd  mov     eax, cs:g_dwTraceId
0x1800013d3  cmp     eax, 0FFFFFFFFh
0x1800013d6  jz      short loc_1800013FC
0x1800013d8  mov     r9d, ebx
0x1800013db  lea     r8, aRasaddnotifica_1; "RasAddNotification exiting ... %d"
0x1800013e2  mov     edx, 0Ch; dwFlags
0x1800013e7  mov     ecx, eax; dwTraceID
0x1800013e9  call    cs:__imp_TracePrintfExA
0x1800013f0  nop     dword ptr [rax+rax+00h]
0x1800013f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800013fc  cmp     rcx, r12
0x1800013ff  jz      short loc_180001425
0x180001401  test    byte ptr [rcx+1Ch], 40h
0x180001405  jz      short loc_180001425
0x180001407  cmp     byte ptr [rcx+19h], 6
0x18000140b  jb      short loc_180001425
0x18000140d  mov     rcx, [rcx+10h]
0x180001411  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180001418  mov     edx, 1DAh
0x18000141d  mov     r9d, ebx
0x180001420  call    WPP_SF_d
0x180001425  mov     rbp, [rsp+58h+arg_8]
0x18000142a  mov     eax, ebx
0x18000142c  mov     rbx, [rsp+58h+arg_0]
0x180001431  add     rsp, 40h
0x180001435  pop     r12
0x180001437  pop     rdi
0x180001438  pop     rsi
0x180001439  retn
```
