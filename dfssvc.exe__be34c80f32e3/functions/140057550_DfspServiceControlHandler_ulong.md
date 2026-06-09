# DfspServiceControlHandler(ulong)

- ea: `0x140057550`
- end: `0x140057635`
- name: `?DfspServiceControlHandler@@YAXK@Z`
- size: `229`
- prototype: `void __stdcall(DWORD dwControl)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140005a94`
- `0x1400096ac`
- `0x140019b88`
- `0x14005744c`
- `0x1400574ec`
- `0x140057550`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400575e7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400575e7`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1400575bb`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1400575bb`

## pseudocode

```c
void __fastcall DfspServiceControlHandler(DWORD dwControl)
{
  unsigned int *v2; // rcx
  DWORD v3; // ebx

  v2 = pWppControl;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_D(*((_QWORD *)pWppControl + 2), 18, WPP_d1f9623494693a705a20c05ce9b3cd4d_Traceguids, dwControl);
    v2 = pWppControl;
  }
  v3 = dwControl - 1;
  if ( !v3 )
  {
    DfsServerStop();
    DfsSetServiceState(1u);
    DfsScmCheckpoint(0xC9u, 0, 0);
    CoUninitialize();
    goto LABEL_10;
  }
  if ( v3 == 127 )
  {
    SetServiceStatus(g_DfspServiceStatusHandle, &g_DfspServiceStatus);
LABEL_10:
    v2 = pWppControl;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && v2 && (v2[7] & 0x20) != 0 && *((_BYTE *)v2 + 25) >= 3u )
    WPP_SF_(*((_QWORD *)v2 + 2), 19, WPP_d1f9623494693a705a20c05ce9b3cd4d_Traceguids);
}

```

## disassembly

```asm
0x140057550  mov     [rsp+arg_0], rbx
0x140057555  push    rdi
0x140057556  sub     rsp, 20h
0x14005755a  mov     ebx, ecx
0x14005755c  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140057563  lea     rdi, WPP_GLOBAL_Control
0x14005756a  cmp     cs:WPP_GLOBAL_Control, rdi
0x140057571  jz      short loc_1400575A3
0x140057573  test    rcx, rcx
0x140057576  jz      short loc_1400575A3
0x140057578  test    byte ptr [rcx+1Ch], 20h
0x14005757c  jz      short loc_1400575A3
0x14005757e  cmp     byte ptr [rcx+19h], 3
0x140057582  jb      short loc_1400575A3
0x140057584  mov     rcx, [rcx+10h]
0x140057588  lea     r8, WPP_d1f9623494693a705a20c05ce9b3cd4d_Traceguids
0x14005758f  mov     edx, 12h
0x140057594  mov     r9d, ebx
0x140057597  call    WPP_SF_D
0x14005759c  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400575a3  sub     ebx, 1
0x1400575a6  jz      short loc_1400575C9
0x1400575a8  cmp     ebx, 7Fh
0x1400575ab  jnz     short loc_1400575FA
0x1400575ad  mov     rcx, cs:?g_DfspServiceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x1400575b4  lea     rdx, ?g_DfspServiceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x1400575bb  call    cs:__imp_SetServiceStatus
0x1400575c2  nop     dword ptr [rax+rax+00h]
0x1400575c7  jmp     short loc_1400575F3
0x1400575c9  call    ?DfsServerStop@@YAKXZ; DfsServerStop(void)
0x1400575ce  mov     ecx, 1; unsigned int
0x1400575d3  call    ?DfsSetServiceState@@YAXK@Z; DfsSetServiceState(ulong)
0x1400575d8  xor     r8d, r8d; unsigned int
0x1400575db  xor     edx, edx; unsigned int
0x1400575dd  mov     ecx, 0C9h; unsigned int
0x1400575e2  call    ?DfsScmCheckpoint@@YAXKKK@Z; DfsScmCheckpoint(ulong,ulong,ulong)
0x1400575e7  call    cs:__imp_CoUninitialize
0x1400575ee  nop     dword ptr [rax+rax+00h]
0x1400575f3  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400575fa  cmp     cs:WPP_GLOBAL_Control, rdi
0x140057601  jz      short loc_140057629
0x140057603  test    rcx, rcx
0x140057606  jz      short loc_140057629
0x140057608  test    byte ptr [rcx+1Ch], 20h
0x14005760c  jz      short loc_140057629
0x14005760e  cmp     byte ptr [rcx+19h], 3
0x140057612  jb      short loc_140057629
0x140057614  mov     rcx, [rcx+10h]
0x140057618  lea     r8, WPP_d1f9623494693a705a20c05ce9b3cd4d_Traceguids
0x14005761f  mov     edx, 13h
0x140057624  call    WPP_SF_
0x140057629  mov     rbx, [rsp+28h+arg_0]
0x14005762e  add     rsp, 20h
0x140057632  pop     rdi
0x140057633  retn
```
