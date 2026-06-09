# NcaServiceHandlerEx(ulong,ulong,void *,void *)

- ea: `0x180004780`
- end: `0x1800048cf`
- name: `?NcaServiceHandlerEx@@YAKKKPEAX0@Z`
- size: `335`
- prototype: `__int64 __fastcall(DWORD dwControl, __int64 dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x1800031f0`
- `0x180004680`
- `0x180004780`
- `0x180004f04`
- `0x180004f78`
- `0x18000e85c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004889`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004889`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180004876`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180004876`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800047e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800047e6`

## pseudocode

```c
__int64 __fastcall NcaServiceHandlerEx(DWORD dwControl, __int64 dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  unsigned int v4; // edi
  PVOID *v6; // rcx
  DWORD v7; // ebx
  DWORD v8; // ebx
  DWORD v9; // ebx
  int v10; // ebx
  __int64 v11; // rcx
  _QWORD *v12; // rcx
  __int64 v13; // rdx

  v4 = dwEventType;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 )
      WPP_SF_L(v6[2], dwEventType, lpEventData, dwControl);
  }
  EnterCriticalSection(&stru_180028AF0);
  v7 = dwControl - 1;
  if ( !v7 || (v8 = v7 - 4) == 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_23;
    v13 = 24;
    goto LABEL_22;
  }
  v9 = v8 - 9;
  if ( !v9 )
  {
    v11 = v4;
    goto LABEL_18;
  }
  v10 = v9 - 18;
  if ( !v10 )
  {
    if ( (unsigned int)NcaIsPolicyPresent() )
      goto LABEL_24;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
LABEL_23:
      NcaServiceChangeState(3u);
      SetEvent(hEvent);
      goto LABEL_24;
    }
    v13 = 25;
LABEL_22:
    WPP_SF_(v12[2], v13, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
    goto LABEL_23;
  }
  if ( v10 == 168 )
  {
    v11 = 8;
LABEL_18:
    NcaWtsSessionChangeIndicate(v11);
  }
LABEL_24:
  LeaveCriticalSection(&stru_180028AF0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x180004780  mov     [rsp+arg_0], rbx
0x180004785  mov     [rsp+arg_8], rsi
0x18000478a  push    rdi
0x18000478b  sub     rsp, 20h
0x18000478f  mov     edi, edx
0x180004791  mov     ebx, ecx
0x180004793  mov     rcx, cs:WPP_GLOBAL_Control
0x18000479a  lea     rsi, WPP_GLOBAL_Control
0x1800047a1  cmp     rcx, rsi
0x1800047a4  jz      short loc_1800047DF
0x1800047a6  test    byte ptr [rcx+1Ch], 8
0x1800047aa  jz      short loc_1800047C8
0x1800047ac  mov     rcx, [rcx+10h]
0x1800047b0  lea     r8, WPP_c5093027d5633495648c95ae523c0e9d_Traceguids
0x1800047b7  mov     edx, 16h
0x1800047bc  call    WPP_SF_
0x1800047c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800047c8  cmp     rcx, rsi
0x1800047cb  jz      short loc_1800047DF
0x1800047cd  test    byte ptr [rcx+1Ch], 4
0x1800047d1  jz      short loc_1800047DF
0x1800047d3  mov     rcx, [rcx+10h]
0x1800047d7  mov     r9d, ebx
0x1800047da  call    WPP_SF_L
0x1800047df  lea     rcx, stru_180028AF0; lpCriticalSection
0x1800047e6  call    cs:__imp_EnterCriticalSection
0x1800047ed  nop     dword ptr [rax+rax+00h]
0x1800047f2  sub     ebx, 1
0x1800047f5  jz      short loc_18000483E
0x1800047f7  sub     ebx, 4
0x1800047fa  jz      short loc_18000483E
0x1800047fc  sub     ebx, 9
0x1800047ff  jz      short loc_180004835
0x180004801  sub     ebx, 12h
0x180004804  jz      short loc_180004815
0x180004806  cmp     ebx, 0A8h
0x18000480c  jnz     short loc_180004882
0x18000480e  mov     ecx, 8
0x180004813  jmp     short loc_180004837
0x180004815  call    ?NcaIsPolicyPresent@@YAHXZ; NcaIsPolicyPresent(void)
0x18000481a  test    eax, eax
0x18000481c  jnz     short loc_180004882
0x18000481e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004825  cmp     rcx, rsi
0x180004828  jz      short loc_180004865
0x18000482a  test    byte ptr [rcx+1Ch], 4
0x18000482e  jz      short loc_180004865
0x180004830  lea     edx, [rax+19h]
0x180004833  jmp     short loc_180004855
0x180004835  mov     ecx, edi
0x180004837  call    NcaWtsSessionChangeIndicate
0x18000483c  jmp     short loc_180004882
0x18000483e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004845  cmp     rcx, rsi
0x180004848  jz      short loc_180004865
0x18000484a  test    byte ptr [rcx+1Ch], 4
0x18000484e  jz      short loc_180004865
0x180004850  mov     edx, 18h
0x180004855  mov     rcx, [rcx+10h]
0x180004859  lea     r8, WPP_c5093027d5633495648c95ae523c0e9d_Traceguids
0x180004860  call    WPP_SF_
0x180004865  mov     ecx, 3; unsigned int
0x18000486a  call    ?NcaServiceChangeState@@YAJK@Z; NcaServiceChangeState(ulong)
0x18000486f  mov     rcx, cs:hEvent; hEvent
0x180004876  call    cs:__imp_SetEvent
0x18000487d  nop     dword ptr [rax+rax+00h]
0x180004882  lea     rcx, stru_180028AF0; lpCriticalSection
0x180004889  call    cs:__imp_LeaveCriticalSection
0x180004890  nop     dword ptr [rax+rax+00h]
0x180004895  mov     rcx, cs:WPP_GLOBAL_Control
0x18000489c  cmp     rcx, rsi
0x18000489f  jz      short loc_1800048BC
0x1800048a1  test    byte ptr [rcx+1Ch], 8
0x1800048a5  jz      short loc_1800048BC
0x1800048a7  mov     rcx, [rcx+10h]
0x1800048ab  lea     r8, WPP_c5093027d5633495648c95ae523c0e9d_Traceguids
0x1800048b2  mov     edx, 1Ah
0x1800048b7  call    WPP_SF_
0x1800048bc  mov     rbx, [rsp+28h+arg_0]
0x1800048c1  xor     eax, eax
0x1800048c3  mov     rsi, [rsp+28h+arg_8]
0x1800048c8  add     rsp, 20h
0x1800048cc  pop     rdi
0x1800048cd  retn
```
