# DpspValidateSession

- ea: `0x1800057b0`
- end: `0x180005dac`
- name: `DpspValidateSession`
- size: `1532`
- prototype: `__int64 __fastcall(struct __SESSIONINFO *, struct INSTANCEINFO *, _DWORD *, unsigned int)`
- caller_count: `4`
- callee_count: `11`
- tags: ``

## callers

- `0x180001ff0`
- `0x180002090`
- `0x180003830`
- `0x180006360`

## callees

- `0x1800057b0`
- `0x180006e70`
- `0x180007360`
- `0x180009090`
- `0x18000a856`
- `0x18000ba14`
- `0x180011580`
- `0x180011714`
- `0x1800118f0`
- `0x180011b88`
- `0x180011c6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800059c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005a27`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005d23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005d34`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800059c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005a27`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005d23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005d34`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800057e4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000597a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005d03`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800057e4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000597a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005d03`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800058b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000592c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800059fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005a3b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800058b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000592c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800059fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005a3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800058a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800058cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000591e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800059ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800058a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800058cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000591e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800059ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a2d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800058e1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800058e1`

## pseudocode

```c
__int64 __fastcall DpspValidateSession(struct __SESSIONINFO *a1, struct INSTANCEINFO *a2, _DWORD *a3, unsigned int a4)
{
  int v8; // edi
  int v9; // r8d
  HANDLE ProcessHeap; // rax
  HANDLE v11; // rax
  _DWORD *v12; // rax
  _DWORD *v13; // r15
  HANDLE v14; // rax
  int Args; // esi
  __int64 v16; // rcx
  void *v17; // r9
  __int64 v18; // rcx
  HANDLE v19; // rax
  __int64 v20; // rcx
  HANDLE v21; // rax
  __int64 v22; // r8
  int v23; // eax
  int v24; // esi
  unsigned int v25; // r15d
  unsigned int v26; // r15d
  int v27; // eax
  int v28; // r8d
  int v29; // eax
  int v30; // eax
  int v31; // eax
  __int64 v32; // rcx
  __int64 v33; // rcx

  if ( a1 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 64));
    if ( !a2 )
    {
      v8 = -2147024809;
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
        (int)L"DpspValidateSession",
        1081,
        (int)L"Error = %d",
        87);
      goto LABEL_61;
    }
    v8 = DpspValidateHost(a2, a4, a3, a1);
    if ( v8 < 0 )
    {
LABEL_61:
      if ( (*((_BYTE *)a1 + 152) & 8) != 0 )
      {
        v32 = *((_QWORD *)a1 + 22);
        if ( v32 )
          EnterCriticalSection((LPCRITICAL_SECTION)(v32 + 72));
        --*(_DWORD *)(*((_QWORD *)a1 + 22) + 44LL);
        v33 = *((_QWORD *)a1 + 22);
        if ( v33 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v33 + 72));
        *((_DWORD *)a1 + 38) &= ~8u;
      }
      goto LABEL_67;
    }
    if ( !*a3 )
    {
LABEL_67:
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 64));
      return (unsigned int)v8;
    }
    if ( a1 == (struct __SESSIONINFO *)-112LL )
    {
      v8 = -2147467259;
      v9 = 1093;
LABEL_60:
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
        (int)L"DpspValidateSession",
        v9,
        (int)L"Error = %d",
        5);
      goto LABEL_61;
    }
    *((_DWORD *)a2 + 51) = a4;
    switch ( *((_DWORD *)a1 + 6) )
    {
      case 0:
        if ( !*((_QWORD *)a1 + 22) )
        {
          v8 = -2147024809;
          WdipTraceError(
            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpscli.cpp",
            (int)L"DpspLoadDM",
            756,
            (int)L"Error = %d",
            87);
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, 0);
          WdipTraceError(
            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
            (int)L"DpspValidateSession",
            1103,
            (int)L"Error = %d",
            87);
          goto LABEL_61;
        }
        v11 = GetProcessHeap();
        v12 = HeapAlloc(v11, 8u, 0xF8u);
        v13 = v12;
        if ( !v12 )
        {
          v8 = -2147024882;
          WdipTraceError(
            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpscli.cpp",
            (int)L"DpspLoadDM",
            759,
            (int)L"Error = %d",
            14);
          v14 = GetProcessHeap();
          HeapFree(v14, 0, 0);
          WdipTraceError(
            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
            (int)L"DpspValidateSession",
            1103,
            (int)L"Error = %d",
            14);
          goto LABEL_61;
        }
        Args = 0;
        memset_0(v12, 0, 0xF8u);
        v13[11] = 5;
        if ( v13 != (_DWORD *)-80LL )
          *((_OWORD *)v13 + 5) = *(_OWORD *)a1;
        v16 = *((_QWORD *)a1 + 22);
        if ( v16 )
          EnterCriticalSection((LPCRITICAL_SECTION)(v16 + 72));
        v17 = *(void **)(*((_QWORD *)a1 + 22) + 128LL);
        if ( v17 )
        {
          Args = DpspSendASyncMessage((struct _DPS_MESSAGE *)v13, 0, 0x10000u, v17, 0xF8u);
          if ( Args < 0 )
          {
            v18 = *((_QWORD *)a1 + 22);
            if ( v18 )
              LeaveCriticalSection((LPCRITICAL_SECTION)(v18 + 72));
            WdipTraceError(
              (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpscli.cpp",
              (int)L"DpspLoadDM",
              783,
              (int)L"Error = %d",
              Args);
            v19 = GetProcessHeap();
            HeapFree(v19, 0, v13);
            v8 = Args;
            WdipTraceError(
              (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
              (int)L"DpspValidateSession",
              1103,
              (int)L"Error = %d",
              Args);
            goto LABEL_61;
          }
        }
        v20 = *((_QWORD *)a1 + 22);
        if ( v20 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v20 + 72));
        v21 = GetProcessHeap();
        HeapFree(v21, 0, v13);
        *((_DWORD *)a1 + 38) &= ~8u;
        *((_DWORD *)a1 + 6) = 1;
        if ( (*((_DWORD *)a2 + 26) & 0x10) != 0 )
        {
          _InterlockedAnd((volatile signed __int32 *)a2 + 26, 0xFFFFFFEF);
          --*((_DWORD *)a1 + 11);
          v22 = 0;
        }
        else
        {
          if ( *((_DWORD *)a1 + 9) >= (unsigned int)(*((_DWORD *)a1 + 10) - *((_DWORD *)a1 + 11)) )
          {
            v8 = -2147467259;
            *((_DWORD *)a2 + 33) = -2147467259;
            DpspRaiseScenarioDMFailedEvent(a2, WDI_DPS_EVENT_SCENARIO_DM_DROPPED);
            v9 = 1151;
            goto LABEL_59;
          }
          v22 = 1;
        }
        DpspQueueInstance((char *)a1 + 112, a2, v22);
        ++*((_DWORD *)a1 + 9);
        v8 = Args;
        *a3 = 1;
        goto LABEL_67;
      case 1:
      case 3:
      case 4:
        if ( (*((_DWORD *)a2 + 26) & 0x10) == 0 )
        {
          if ( *((_DWORD *)a1 + 9) < (unsigned int)(*((_DWORD *)a1 + 10) - *((_DWORD *)a1 + 11)) )
            goto LABEL_35;
          v8 = -2147467259;
          *((_DWORD *)a2 + 33) = -2147467259;
          DpspRaiseScenarioDMFailedEvent(a2, WDI_DPS_EVENT_SCENARIO_DM_DROPPED);
          v9 = 1286;
          goto LABEL_59;
        }
        _InterlockedAnd((volatile signed __int32 *)a2 + 26, 0xFFFFFFEF);
        --*((_DWORD *)a1 + 11);
        DpspQueueInstance((char *)a1 + 112, a2, 0);
        ++*((_DWORD *)a1 + 9);
        *a3 = 1;
        goto LABEL_67;
      case 2:
        v23 = *((_DWORD *)a1 + 8) - *((_DWORD *)a1 + 11);
        *((_DWORD *)a1 + 38) |= 4u;
        if ( *((_DWORD *)a1 + 7) == v23 && (*((_DWORD *)a2 + 26) & 0x10) == 0 )
        {
          if ( *((_DWORD *)a2 + 51) == 3 )
          {
            DpspQueueInstance((char *)a1 + 112, a2, 0);
            ++*((_DWORD *)a1 + 9);
            *a3 = 1;
          }
          else
          {
            if ( *((_DWORD *)a1 + 9) >= (unsigned int)(*((_DWORD *)a1 + 10) - *((_DWORD *)a1 + 11)) )
            {
              v8 = -2147467259;
              *((_DWORD *)a2 + 33) = -2147467259;
              DpspRaiseScenarioDMFailedEvent(a2, WDI_DPS_EVENT_SCENARIO_DM_DROPPED);
              v9 = 1207;
              goto LABEL_59;
            }
LABEL_35:
            DpspQueueInstance((char *)a1 + 112, a2, 1);
            ++*((_DWORD *)a1 + 9);
            *a3 = 1;
          }
          goto LABEL_67;
        }
        if ( (*((_DWORD *)a2 + 26) & 0x10) != 0 )
        {
          _InterlockedAnd((volatile signed __int32 *)a2 + 26, 0xFFFFFFEF);
          --*((_DWORD *)a1 + 11);
        }
        v24 = 0;
        if ( a4 )
        {
          v25 = a4 - 1;
          if ( !v25 )
          {
            v30 = DpspTroubleshoot(a2, a1);
            LOBYTE(v24) = v30;
            v8 = v30;
            if ( v30 < 0 )
            {
              v28 = 704;
              goto LABEL_51;
            }
            goto LABEL_53;
          }
          v26 = v25 - 1;
          if ( !v26 )
          {
            v29 = DpspResolve(a2, a1);
            LOBYTE(v24) = v29;
            v8 = v29;
            if ( v29 < 0 )
            {
              v28 = 711;
              goto LABEL_51;
            }
            goto LABEL_53;
          }
          if ( v26 == 1 )
          {
            v27 = DpspNotifyDM(a2, a1);
            LOBYTE(v24) = v27;
            v8 = v27;
            if ( v27 < 0 )
            {
              v28 = 718;
LABEL_51:
              WdipTraceError(
                (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpscli.cpp",
                (int)L"DpspSendDiagnosticMessage",
                v28,
                (int)L"Error = %d",
                v24);
              WdipTraceError(
                (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
                (int)L"DpspValidateSession",
                1228,
                (int)L"Error = %d",
                v24);
              goto LABEL_61;
            }
            goto LABEL_53;
          }
        }
        else
        {
          v31 = DpspProblemDetect(a2, a1);
          v24 = v31;
          if ( v31 < 0 )
          {
            v8 = v31;
            v28 = 697;
            goto LABEL_51;
          }
        }
        v8 = v24;
LABEL_53:
        ++*((_DWORD *)a1 + 7);
        *a3 = 3;
        goto LABEL_67;
      case 5:
        v8 = -2147467259;
        *((_DWORD *)a2 + 33) = -2147467259;
        DpspRaiseScenarioDMFailedEvent(a2, WDI_DPS_EVENT_SCENARIO_DM_DROPPED);
        v9 = 1304;
LABEL_59:
        ++*((_DWORD *)a1 + 12);
        goto LABEL_60;
      default:
        goto LABEL_67;
    }
  }
  WdipTraceError(
    (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
    (int)L"DpspValidateSession",
    1080,
    (int)L"Error = %d",
    87);
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800057b0  push    rbx
0x1800057b2  push    rbp
0x1800057b3  push    rdi
0x1800057b4  push    r12
0x1800057b6  push    r15
0x1800057b8  sub     rsp, 30h
0x1800057bc  mov     r15d, r9d
0x1800057bf  mov     r12, r8
0x1800057c2  mov     rbp, rdx
0x1800057c5  mov     rbx, rcx
0x1800057c8  test    rcx, rcx
0x1800057cb  jz      loc_180005D57
0x1800057d1  mov     [rsp+58h+arg_10], r14
0x1800057d6  add     rcx, 40h ; '@'; lpCriticalSection
0x1800057da  mov     [rsp+58h+arg_0], rsi
0x1800057df  mov     [rsp+58h+arg_8], r13
0x1800057e4  call    cs:__imp_EnterCriticalSection
0x1800057ea  test    rbp, rbp
0x1800057ed  jnz     short loc_180005807
0x1800057ef  mov     edi, 80070057h
0x1800057f4  mov     dword ptr [rsp+58h+Args], 57h ; 'W'
0x1800057fc  mov     r8d, 439h
0x180005802  jmp     loc_180005CD0
0x180005807  mov     r9, rbx
0x18000580a  mov     r8, r12
0x18000580d  mov     edx, r15d
0x180005810  mov     rcx, rbp
0x180005813  call    ?DpspValidateHost@@YAJPEAUINSTANCEINFO@@W4SCENARIOSTATE@@PEAW4INSTANCESTATE@@PEAU__SESSIONINFO@@@Z; DpspValidateHost(INSTANCEINFO *,SCENARIOSTATE,INSTANCESTATE *,__SESSIONINFO *)
0x180005818  mov     edi, eax
0x18000581a  test    eax, eax
0x18000581c  js      loc_180005CEA
0x180005822  cmp     dword ptr [r12], 0
0x180005827  jz      def_18000586A; jumptable 000000018000586A default case
0x18000582d  lea     r13, [rbx+70h]
0x180005831  test    r13, r13
0x180005834  jnz     short loc_180005846
0x180005836  mov     edi, 80004005h
0x18000583b  mov     r8d, 445h
0x180005841  jmp     loc_180005CC8
0x180005846  mov     [rbp+0CCh], r15d
0x18000584d  mov     eax, [rbx+18h]
0x180005850  cmp     eax, 5; switch 6 cases
0x180005853  ja      def_18000586A; jumptable 000000018000586A default case
0x180005859  lea     rcx, __ImageBase
0x180005860  mov     eax, ds:(jpt_18000586A - 180000000h)[rcx+rax*4]
0x180005867  add     rax, rcx
0x18000586a  jmp     rax; switch jump
0x18000586c  cmp     qword ptr [rbx+0B0h], 0; jumptable 000000018000586A case 0
0x180005874  jnz     short loc_1800058CB
0x180005876  mov     edi, 80070057h
0x18000587b  mov     dword ptr [rsp+58h+Args], 57h ; 'W'; Args
0x180005883  lea     r9, aErrorD; "Error = %d"
0x18000588a  mov     r8d, 2F4h; int
0x180005890  lea     rdx, aDpsploaddm; "DpspLoadDM"
0x180005897  mov     esi, edi
0x180005899  lea     rcx, aClientcoreBase_12; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800058a0  call    WdipTraceError
0x1800058a5  call    cs:__imp_GetProcessHeap
0x1800058ab  xor     r8d, r8d; lpMem
0x1800058ae  xor     edx, edx; dwFlags
0x1800058b0  mov     rcx, rax; hHeap
0x1800058b3  call    cs:__imp_HeapFree
0x1800058b9  movzx   eax, si
0x1800058bc  mov     r8d, 44Fh
0x1800058c2  mov     dword ptr [rsp+58h+Args], eax
0x1800058c6  jmp     loc_180005CD0
0x1800058cb  call    cs:__imp_GetProcessHeap
0x1800058d1  mov     edi, 0F8h
0x1800058d6  mov     edx, 8; dwFlags
0x1800058db  mov     rcx, rax; hHeap
0x1800058de  mov     r8d, edi; dwBytes
0x1800058e1  call    cs:__imp_HeapAlloc
0x1800058e7  mov     r15, rax
0x1800058ea  test    rax, rax
0x1800058ed  jnz     short loc_180005944
0x1800058ef  mov     edi, 8007000Eh
0x1800058f4  mov     dword ptr [rsp+58h+Args], 0Eh; Args
0x1800058fc  lea     r9, aErrorD; "Error = %d"
0x180005903  mov     r8d, 2F7h; int
0x180005909  lea     rdx, aDpsploaddm; "DpspLoadDM"
0x180005910  mov     esi, edi
0x180005912  lea     rcx, aClientcoreBase_12; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180005919  call    WdipTraceError
0x18000591e  call    cs:__imp_GetProcessHeap
0x180005924  mov     r8, r15; lpMem
0x180005927  xor     edx, edx; dwFlags
0x180005929  mov     rcx, rax; hHeap
0x18000592c  call    cs:__imp_HeapFree
0x180005932  movzx   eax, si
0x180005935  mov     r8d, 44Fh
0x18000593b  mov     dword ptr [rsp+58h+Args], eax
0x18000593f  jmp     loc_180005CD0
0x180005944  mov     r8, rdi; Size
0x180005947  xor     edx, edx; Val
0x180005949  mov     rcx, r15; void *
0x18000594c  xor     esi, esi
0x18000594e  call    memset_0
0x180005953  lea     rax, [r15+50h]
0x180005957  mov     dword ptr [r15+2Ch], 5
0x18000595f  test    rax, rax
0x180005962  jz      short loc_18000596A
0x180005964  movups  xmm0, xmmword ptr [rbx]
0x180005967  movups  xmmword ptr [rax], xmm0
0x18000596a  mov     rcx, [rbx+0B0h]
0x180005971  test    rcx, rcx
0x180005974  jz      short loc_180005980
0x180005976  add     rcx, 48h ; 'H'; lpCriticalSection
0x18000597a  call    cs:__imp_EnterCriticalSection
0x180005980  mov     rax, [rbx+0B0h]
0x180005987  mov     r9, [rax+80h]; void *
0x18000598e  test    r9, r9
0x180005991  jz      loc_180005A17
0x180005997  xor     edx, edx; struct _ALPC_MESSAGE_ATTRIBUTES *
0x180005999  mov     word ptr [rsp+58h+Args], di; unsigned __int16
0x18000599e  mov     r8d, 10000h; unsigned int
0x1800059a4  mov     rcx, r15; struct _DPS_MESSAGE *
0x1800059a7  call    ?DpspSendASyncMessage@@YAJPEAU_DPS_MESSAGE@@PEAU_ALPC_MESSAGE_ATTRIBUTES@@KPEAXG@Z; DpspSendASyncMessage(_DPS_MESSAGE *,_ALPC_MESSAGE_ATTRIBUTES *,ulong,void *,ushort)
0x1800059ac  mov     esi, eax
0x1800059ae  test    eax, eax
0x1800059b0  jns     short loc_180005A17
0x1800059b2  mov     rcx, [rbx+0B0h]
0x1800059b9  test    rcx, rcx
0x1800059bc  jz      short loc_1800059C8
0x1800059be  add     rcx, 48h ; 'H'; lpCriticalSection
0x1800059c2  call    cs:__imp_LeaveCriticalSection
0x1800059c8  movzx   eax, si
0x1800059cb  lea     r9, aErrorD; "Error = %d"
0x1800059d2  mov     r8d, 30Fh; int
0x1800059d8  mov     dword ptr [rsp+58h+Args], eax; Args
0x1800059dc  lea     rdx, aDpsploaddm; "DpspLoadDM"
0x1800059e3  lea     rcx, aClientcoreBase_12; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800059ea  call    WdipTraceError
0x1800059ef  call    cs:__imp_GetProcessHeap
0x1800059f5  mov     r8, r15; lpMem
0x1800059f8  xor     edx, edx; dwFlags
0x1800059fa  mov     rcx, rax; hHeap
0x1800059fd  call    cs:__imp_HeapFree
0x180005a03  movzx   eax, si
0x180005a06  mov     edi, esi
0x180005a08  mov     dword ptr [rsp+58h+Args], eax
0x180005a0c  mov     r8d, 44Fh
0x180005a12  jmp     loc_180005CD0
0x180005a17  mov     rcx, [rbx+0B0h]
0x180005a1e  test    rcx, rcx
0x180005a21  jz      short loc_180005A2D
0x180005a23  add     rcx, 48h ; 'H'; lpCriticalSection
0x180005a27  call    cs:__imp_LeaveCriticalSection
0x180005a2d  call    cs:__imp_GetProcessHeap
0x180005a33  mov     r8, r15; lpMem
0x180005a36  xor     edx, edx; dwFlags
0x180005a38  mov     rcx, rax; hHeap
0x180005a3b  call    cs:__imp_HeapFree
0x180005a41  and     dword ptr [rbx+98h], 0FFFFFFF7h
0x180005a48  mov     r15d, 1
0x180005a4e  mov     [rbx+18h], r15d
0x180005a52  mov     eax, [rbp+68h]
0x180005a55  test    al, 10h
0x180005a57  jz      short loc_180005A66
0x180005a59  lock and dword ptr [rbp+68h], 0FFFFFFEFh
0x180005a5e  dec     dword ptr [rbx+2Ch]
0x180005a61  xor     r8d, r8d
0x180005a64  jmp     short loc_180005A74
0x180005a66  mov     eax, [rbx+28h]
0x180005a69  sub     eax, [rbx+2Ch]
0x180005a6c  cmp     [rbx+24h], eax
0x180005a6f  jnb     short loc_180005A8D
0x180005a71  mov     r8d, r15d
0x180005a74  mov     rdx, rbp
0x180005a77  mov     rcx, r13
0x180005a7a  call    DpspQueueInstance
0x180005a7f  inc     dword ptr [rbx+24h]
0x180005a82  mov     edi, esi
0x180005a84  mov     [r12], r15d
0x180005a88  jmp     def_18000586A; jumptable 000000018000586A default case
0x180005a8d  mov     edi, 80004005h
0x180005a92  lea     rdx, WDI_DPS_EVENT_SCENARIO_DM_DROPPED
0x180005a99  mov     rcx, rbp
0x180005a9c  mov     [rbp+84h], edi
0x180005aa2  call    DpspRaiseScenarioDMFailedEvent
0x180005aa7  mov     r8d, 47Fh
0x180005aad  jmp     loc_180005CC5
0x180005ab2  mov     eax, [rbx+20h]; jumptable 000000018000586A case 2
0x180005ab5  sub     eax, [rbx+2Ch]
0x180005ab8  or      dword ptr [rbx+98h], 4
0x180005abf  cmp     [rbx+1Ch], eax
0x180005ac2  jnz     loc_180005B48
0x180005ac8  mov     eax, [rbp+68h]
0x180005acb  test    al, 10h
0x180005acd  jnz     short loc_180005B48
0x180005acf  cmp     dword ptr [rbp+0CCh], 3
0x180005ad6  jnz     short loc_180005AF8
0x180005ad8  xor     r8d, r8d
0x180005adb  mov     rdx, rbp
0x180005ade  mov     rcx, r13
0x180005ae1  call    DpspQueueInstance
0x180005ae6  inc     dword ptr [rbx+24h]
0x180005ae9  mov     r15d, 1
0x180005aef  mov     [r12], r15d
0x180005af3  jmp     def_18000586A; jumptable 000000018000586A default case
0x180005af8  mov     eax, [rbx+28h]
0x180005afb  sub     eax, [rbx+2Ch]
0x180005afe  cmp     [rbx+24h], eax
0x180005b01  jnb     short loc_180005B23
0x180005b03  mov     r15d, 1
0x180005b09  mov     rdx, rbp
0x180005b0c  mov     r8d, r15d
0x180005b0f  mov     rcx, r13
0x180005b12  call    DpspQueueInstance
0x180005b17  inc     dword ptr [rbx+24h]
0x180005b1a  mov     [r12], r15d
0x180005b1e  jmp     def_18000586A; jumptable 000000018000586A default case
0x180005b23  mov     edi, 80004005h
0x180005b28  lea     rdx, WDI_DPS_EVENT_SCENARIO_DM_DROPPED
0x180005b2f  mov     rcx, rbp
0x180005b32  mov     [rbp+84h], edi
0x180005b38  call    DpspRaiseScenarioDMFailedEvent
0x180005b3d  mov     r8d, 4B7h
0x180005b43  jmp     loc_180005CC5
0x180005b48  mov     eax, [rbp+68h]
0x180005b4b  test    al, 10h
0x180005b4d  jz      short loc_180005B57
0x180005b4f  lock and dword ptr [rbp+68h], 0FFFFFFEFh
0x180005b54  dec     dword ptr [rbx+2Ch]
0x180005b57  xor     esi, esi
0x180005b59  test    r15d, r15d
0x180005b5c  jz      short loc_180005BC9
0x180005b5e  sub     r15d, 1
0x180005b62  jz      short loc_180005BAE
0x180005b64  sub     r15d, 1
0x180005b68  jz      short loc_180005B93
0x180005b6a  cmp     r15d, 1
0x180005b6e  jnz     loc_180005C15
0x180005b74  mov     rdx, rbx; struct __SESSIONINFO *
0x180005b77  mov     rcx, rbp; struct INSTANCEINFO *
0x180005b7a  call    ?DpspNotifyDM@@YAJPEAUINSTANCEINFO@@PEAU__SESSIONINFO@@@Z; DpspNotifyDM(INSTANCEINFO *,__SESSIONINFO *)
0x180005b7f  mov     esi, eax
0x180005b81  mov     edi, eax
0x180005b83  test    eax, eax
0x180005b85  jns     loc_180005C17
0x180005b8b  mov     r8d, 2CEh
0x180005b91  jmp     short loc_180005BE2
0x180005b93  mov     rdx, rbx; struct __SESSIONINFO *
0x180005b96  mov     rcx, rbp; struct INSTANCEINFO *
0x180005b99  call    ?DpspResolve@@YAKPEAUINSTANCEINFO@@PEAU__SESSIONINFO@@@Z; DpspResolve(INSTANCEINFO *,__SESSIONINFO *)
0x180005b9e  mov     esi, eax
0x180005ba0  mov     edi, eax
0x180005ba2  test    eax, eax
0x180005ba4  jns     short loc_180005C17
0x180005ba6  mov     r8d, 2C7h
0x180005bac  jmp     short loc_180005BE2
0x180005bae  mov     rdx, rbx; struct __SESSIONINFO *
0x180005bb1  mov     rcx, rbp; struct INSTANCEINFO *
0x180005bb4  call    ?DpspTroubleshoot@@YAJPEAUINSTANCEINFO@@PEAU__SESSIONINFO@@@Z; DpspTroubleshoot(INSTANCEINFO *,__SESSIONINFO *)
0x180005bb9  mov     esi, eax
0x180005bbb  mov     edi, eax
0x180005bbd  test    eax, eax
0x180005bbf  jns     short loc_180005C17
0x180005bc1  mov     r8d, 2C0h
0x180005bc7  jmp     short loc_180005BE2
0x180005bc9  mov     rdx, rbx; struct __SESSIONINFO *
0x180005bcc  mov     rcx, rbp; struct INSTANCEINFO *
0x180005bcf  call    ?DpspProblemDetect@@YAJPEAUINSTANCEINFO@@PEAU__SESSIONINFO@@@Z; DpspProblemDetect(INSTANCEINFO *,__SESSIONINFO *)
0x180005bd4  mov     esi, eax
0x180005bd6  test    eax, eax
0x180005bd8  jns     short loc_180005C15
0x180005bda  mov     edi, eax
0x180005bdc  mov     r8d, 2B9h; int
0x180005be2  movzx   eax, si
0x180005be5  lea     rdx, aDpspsenddiagno; "DpspSendDiagnosticMessage"
0x180005bec  lea     rcx, aClientcoreBase_12; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180005bf3  mov     dword ptr [rsp+58h+Args], eax; Args
0x180005bf7  lea     r9, aErrorD; "Error = %d"
0x180005bfe  call    WdipTraceError
0x180005c03  movzx   eax, si
0x180005c06  mov     r8d, 4CCh
0x180005c0c  mov     dword ptr [rsp+58h+Args], eax
0x180005c10  jmp     loc_180005CD0
0x180005c15  mov     edi, esi
0x180005c17  inc     dword ptr [rbx+1Ch]
0x180005c1a  mov     r15d, 3
0x180005c20  mov     [r12], r15d
0x180005c24  jmp     def_18000586A; jumptable 000000018000586A default case
0x180005c29  mov     eax, [rbp+68h]; jumptable 000000018000586A cases 1,3,4
0x180005c2c  test    al, 10h
0x180005c2e  jz      short loc_180005C58
0x180005c30  lock and dword ptr [rbp+68h], 0FFFFFFEFh
0x180005c35  dec     dword ptr [rbx+2Ch]
0x180005c38  xor     r8d, r8d
0x180005c3b  mov     rdx, rbp
0x180005c3e  mov     rcx, r13
0x180005c41  call    DpspQueueInstance
0x180005c46  inc     dword ptr [rbx+24h]
0x180005c49  mov     r15d, 1
0x180005c4f  mov     [r12], r15d
0x180005c53  jmp     def_18000586A; jumptable 000000018000586A default case
0x180005c58  mov     eax, [rbx+28h]
0x180005c5b  sub     eax, [rbx+2Ch]
0x180005c5e  cmp     [rbx+24h], eax
0x180005c61  jnb     short loc_180005C83
0x180005c63  mov     r15d, 1
  ... truncated ...
```
