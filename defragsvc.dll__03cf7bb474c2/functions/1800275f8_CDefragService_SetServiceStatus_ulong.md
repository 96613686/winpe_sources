# CDefragService::_SetServiceStatus(ulong)

- ea: `0x1800275f8`
- end: `0x1800276d2`
- name: `?_SetServiceStatus@CDefragService@@AEAAJK@Z`
- size: `218`
- prototype: `__int64 __fastcall(CDefragService *this, DWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800271f8`
- `0x1800273cc`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001a630`
- `0x1800275f8`
- `0x180046494`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002765c`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002765c`

## string_xrefs

- `0x18002760c`: `CDefragService::_SetServiceStatus`

## pseudocode

```c
__int64 __fastcall CDefragService::_SetServiceStatus(CDefragService *this, DWORD a2)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  unsigned int LastFailureAsHRESULT; // ebx
  unsigned int v9; // [rsp+20h] [rbp-48h] BYREF
  __int16 v10; // [rsp+24h] [rbp-44h]
  __int16 v11; // [rsp+26h] [rbp-42h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v9, "CDefragService::_SetServiceStatus", 321, 1);
  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_9dfa55146e94391ee67982bf00c934b1_Traceguids, a2);
  }
  if ( hServiceStatus )
  {
    v9 = 0;
    v10 = 326;
    ServiceStatus.dwCurrentState = a2;
    if ( !SetServiceStatus(hServiceStatus, &ServiceStatus) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v4, v3, v5, v6);
      v9 = LastFailureAsHRESULT;
      v11 = 330;
      goto LABEL_6;
    }
    LastFailureAsHRESULT = 0;
    v10 = 330;
  }
  else
  {
    LastFailureAsHRESULT = -2147418113;
    v11 = 326;
  }
  v9 = LastFailureAsHRESULT;
LABEL_6:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v9);
  return LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x1800275f8  push    rbx
0x1800275fa  sub     rsp, 60h
0x1800275fe  mov     ebx, edx
0x180027600  mov     r9d, 1; unsigned __int16
0x180027606  mov     r8d, 141h; unsigned __int16
0x18002760c  lea     rdx, aCdefragservice_13; "CDefragService::_SetServiceStatus"
0x180027613  lea     rcx, [rsp+68h+var_48]; this
0x180027618  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002761d  nop
0x18002761e  lea     rax, WPP_GLOBAL_Control
0x180027625  mov     rcx, cs:WPP_GLOBAL_Control
0x18002762c  cmp     rcx, rax
0x18002762f  jnz     short loc_180027694
0x180027631  mov     rcx, cs:hServiceStatus; hServiceStatus
0x180027638  mov     eax, 146h
0x18002763d  test    rcx, rcx
0x180027640  jz      short loc_180027688
0x180027642  mov     [rsp+68h+var_48], 0
0x18002764a  mov     [rsp+68h+var_44], ax
0x18002764f  mov     cs:ServiceStatus.dwCurrentState, ebx
0x180027655  lea     rdx, ServiceStatus; lpServiceStatus
0x18002765c  call    cs:__imp_SetServiceStatus
0x180027662  test    eax, eax
0x180027664  jz      short loc_1800276BA
0x180027666  xor     ebx, ebx
0x180027668  mov     eax, 14Ah
0x18002766d  mov     [rsp+68h+var_44], ax
0x180027672  mov     [rsp+68h+var_48], ebx
0x180027676  lea     rcx, [rsp+68h+var_48]; this
0x18002767b  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180027680  mov     eax, ebx
0x180027682  add     rsp, 60h
0x180027686  pop     rbx
0x180027687  retn
0x180027688  mov     ebx, 8000FFFFh
0x18002768d  mov     [rsp+68h+var_42], ax
0x180027692  jmp     short loc_180027672
0x180027694  test    dword ptr [rcx+1Ch], 8000000h
0x18002769b  jz      short loc_180027631
0x18002769d  mov     edx, 0Ch
0x1800276a2  mov     r9d, ebx
0x1800276a5  lea     r8, WPP_9dfa55146e94391ee67982bf00c934b1_Traceguids
0x1800276ac  mov     rcx, [rcx+10h]
0x1800276b0  call    WPP_SF_d
0x1800276b5  jmp     loc_180027631
0x1800276ba  call    GetLastFailureAsHRESULT
0x1800276bf  mov     ebx, eax
0x1800276c1  mov     [rsp+68h+var_48], eax
0x1800276c5  mov     eax, 14Ah
0x1800276ca  mov     [rsp+68h+var_42], ax
0x1800276cf  jmp     short loc_180027676
```
