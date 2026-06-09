# DfspServiceMain(ulong,ushort * *)

- ea: `0x140057640`
- end: `0x14005780c`
- name: `?DfspServiceMain@@YAXKPEAPEAG@Z`
- size: `460`
- prototype: `void __fastcall(unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callees

- `0x140005a94`
- `0x1400096ac`
- `0x140018e88`
- `0x14005744c`
- `0x1400574ec`
- `0x140057640`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400576d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400576d7`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x1400576bf`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x1400576bf`

## string_xrefs

- `0x14005769c`: `DfsService`

## pseudocode

```c
void __fastcall DfspServiceMain(__int64 a1, unsigned __int16 **a2)
{
  DWORD LastError; // eax
  unsigned int *v3; // r10
  unsigned int v4; // eax
  unsigned int v5; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_(*((_QWORD *)pWppControl + 2), 14, WPP_d1f9623494693a705a20c05ce9b3cd4d_Traceguids);
  }
  g_DfspServiceStatus.dwControlsAccepted = 0;
  g_DfspServiceStatus.dwWin32ExitCode = 0;
  g_DfspServiceStatus.dwServiceSpecificExitCode = 0;
  g_DfspServiceStatus.dwServiceType = 16;
  g_DfspServiceStatus.dwCurrentState = 1;
  g_DfspServiceStatusHandle = RegisterServiceCtrlHandlerW(L"DfsService", DfspServiceControlHandler);
  if ( g_DfspServiceStatusHandle )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0x20) != 0
      && *((_BYTE *)pWppControl + 25) >= 3u )
    {
      WPP_SF_(*((_QWORD *)pWppControl + 2), 16, WPP_d1f9623494693a705a20c05ce9b3cd4d_Traceguids);
    }
    DfsSetServiceState(2u);
    DfsScmCheckpoint(0x65u, 0x7530u, 0);
    v4 = DfsServerInitialize();
    v5 = v4;
    if ( !v4 )
      g_DfspServiceStatus.dwControlsAccepted = 1;
    DfsSetServiceState(v4 != 0 ? 1 : 4);
    DfsScmCheckpoint(0x66u, 0, v5);
    goto LABEL_20;
  }
  LastError = GetLastError();
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return;
  v3 = pWppControl;
  if ( pWppControl && (((1 << (LastError != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) != 0 && *((_BYTE *)pWppControl + 25) )
  {
    WPP_SF_D(*((_QWORD *)pWppControl + 2), 15, WPP_d1f9623494693a705a20c05ce9b3cd4d_Traceguids, LastError);
LABEL_20:
    v3 = pWppControl;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && v3 && (v3[7] & 0x20) != 0 && *((_BYTE *)v3 + 25) >= 3u )
    WPP_SF_(*((_QWORD *)v3 + 2), 17, WPP_d1f9623494693a705a20c05ce9b3cd4d_Traceguids);
}

```

## disassembly

```asm
0x140057640  mov     [rsp+arg_0], rbx
0x140057645  push    rsi
0x140057646  sub     rsp, 20h
0x14005764a  lea     rsi, WPP_GLOBAL_Control
0x140057651  cmp     cs:WPP_GLOBAL_Control, rsi
0x140057658  jz      short loc_140057687
0x14005765a  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140057661  test    rcx, rcx
0x140057664  jz      short loc_140057687
0x140057666  test    byte ptr [rcx+1Ch], 20h
0x14005766a  jz      short loc_140057687
0x14005766c  cmp     byte ptr [rcx+19h], 3
0x140057670  jb      short loc_140057687
0x140057672  mov     rcx, [rcx+10h]
0x140057676  lea     r8, WPP_d1f9623494693a705a20c05ce9b3cd4d_Traceguids
0x14005767d  mov     edx, 0Eh
0x140057682  call    WPP_SF_
0x140057687  and     cs:?g_DfspServiceStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 0; _SERVICE_STATUS g_DfspServiceStatus ...
0x14005768e  lea     rdx, ?DfspServiceControlHandler@@YAXK@Z; lpHandlerProc
0x140057695  and     cs:?g_DfspServiceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, 0; _SERVICE_STATUS g_DfspServiceStatus ...
0x14005769c  lea     rcx, aDfsservice; "DfsService"
0x1400576a3  and     cs:?g_DfspServiceStatus@@3U_SERVICE_STATUS@@A.dwServiceSpecificExitCode, 0; _SERVICE_STATUS g_DfspServiceStatus ...
0x1400576aa  mov     ebx, 10h
0x1400576af  mov     cs:?g_DfspServiceStatus@@3U_SERVICE_STATUS@@A.dwServiceType, ebx; _SERVICE_STATUS g_DfspServiceStatus ...
0x1400576b5  mov     cs:?g_DfspServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 1; _SERVICE_STATUS g_DfspServiceStatus ...
0x1400576bf  call    cs:__imp_RegisterServiceCtrlHandlerW
0x1400576c6  nop     dword ptr [rax+rax+00h]
0x1400576cb  mov     cs:?g_DfspServiceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * g_DfspServiceStatusHandle
0x1400576d2  test    rax, rax
0x1400576d5  jnz     short loc_140057742
0x1400576d7  call    cs:__imp_GetLastError
0x1400576de  nop     dword ptr [rax+rax+00h]
0x1400576e3  mov     r9d, eax
0x1400576e6  cmp     cs:WPP_GLOBAL_Control, rsi
0x1400576ed  jz      loc_140057800
0x1400576f3  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400576fa  test    r10, r10
0x1400576fd  jz      loc_1400577CF
0x140057703  mov     ecx, eax
0x140057705  lea     eax, [rbx+10h]
0x140057708  neg     ecx
0x14005770a  sbb     edx, edx
0x14005770c  and     edx, 0FFFFFFECh
0x14005770f  add     edx, 1Fh
0x140057712  bts     eax, edx
0x140057715  test    [r10+1Ch], eax
0x140057719  jz      loc_1400577CF
0x14005771f  cmp     byte ptr [r10+19h], 1
0x140057724  jb      loc_1400577CF
0x14005772a  mov     rcx, [r10+10h]
0x14005772e  lea     edx, [rbx-1]
0x140057731  lea     r8, WPP_d1f9623494693a705a20c05ce9b3cd4d_Traceguids
0x140057738  call    WPP_SF_D
0x14005773d  jmp     loc_1400577C8
0x140057742  cmp     cs:WPP_GLOBAL_Control, rsi
0x140057749  jz      short loc_140057775
0x14005774b  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140057752  test    rcx, rcx
0x140057755  jz      short loc_140057775
0x140057757  test    byte ptr [rcx+1Ch], 20h
0x14005775b  jz      short loc_140057775
0x14005775d  cmp     byte ptr [rcx+19h], 3
0x140057761  jb      short loc_140057775
0x140057763  mov     rcx, [rcx+10h]
0x140057767  lea     r8, WPP_d1f9623494693a705a20c05ce9b3cd4d_Traceguids
0x14005776e  mov     edx, ebx
0x140057770  call    WPP_SF_
0x140057775  mov     ecx, 2; unsigned int
0x14005777a  call    ?DfsSetServiceState@@YAXK@Z; DfsSetServiceState(ulong)
0x14005777f  xor     r8d, r8d; unsigned int
0x140057782  mov     edx, 7530h; unsigned int
0x140057787  lea     ecx, [r8+65h]; unsigned int
0x14005778b  call    ?DfsScmCheckpoint@@YAXKKK@Z; DfsScmCheckpoint(ulong,ulong,ulong)
0x140057790  mov     ecx, 80h; unsigned int
0x140057795  call    ?DfsServerInitialize@@YAKK@Z; DfsServerInitialize(ulong)
0x14005779a  mov     ebx, eax
0x14005779c  test    eax, eax
0x14005779e  jnz     short loc_1400577AA
0x1400577a0  mov     cs:?g_DfspServiceStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 1; _SERVICE_STATUS g_DfspServiceStatus ...
0x1400577aa  mov     ecx, ebx
0x1400577ac  neg     ecx
0x1400577ae  sbb     ecx, ecx
0x1400577b0  and     ecx, 0FFFFFFFDh
0x1400577b3  add     ecx, 4; unsigned int
0x1400577b6  call    ?DfsSetServiceState@@YAXK@Z; DfsSetServiceState(ulong)
0x1400577bb  xor     edx, edx; unsigned int
0x1400577bd  mov     r8d, ebx; unsigned int
0x1400577c0  lea     ecx, [rdx+66h]; unsigned int
0x1400577c3  call    ?DfsScmCheckpoint@@YAXKKK@Z; DfsScmCheckpoint(ulong,ulong,ulong)
0x1400577c8  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400577cf  cmp     cs:WPP_GLOBAL_Control, rsi
0x1400577d6  jz      short loc_140057800
0x1400577d8  test    r10, r10
0x1400577db  jz      short loc_140057800
0x1400577dd  test    byte ptr [r10+1Ch], 20h
0x1400577e2  jz      short loc_140057800
0x1400577e4  cmp     byte ptr [r10+19h], 3
0x1400577e9  jb      short loc_140057800
0x1400577eb  mov     rcx, [r10+10h]
0x1400577ef  lea     r8, WPP_d1f9623494693a705a20c05ce9b3cd4d_Traceguids
0x1400577f6  mov     edx, 11h
0x1400577fb  call    WPP_SF_
0x140057800  mov     rbx, [rsp+28h+arg_0]
0x140057805  add     rsp, 20h
0x140057809  pop     rsi
0x14005780a  retn
```
