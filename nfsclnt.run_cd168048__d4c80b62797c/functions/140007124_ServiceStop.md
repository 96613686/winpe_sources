# ServiceStop

- ea: `0x140007124`
- end: `0x1400072b0`
- name: `ServiceStop`
- size: `396`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x140005850`
- `0x14000a0b0`

## callees

- `0x140002bd8`
- `0x140002c00`
- `0x1400053e0`
- `0x140005960`
- `0x140007124`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1400071ae`
- `KERNEL32!EnterCriticalSection` at `0x1400071ae`
- `KERNEL32!GlobalFree` at `0x140007205`
- `KERNEL32!GlobalFree` at `0x140007205`
- `KERNEL32!LeaveCriticalSection` at `0x140007221`
- `KERNEL32!LeaveCriticalSection` at `0x140007221`
- `KERNEL32!SetEvent` at `0x14000722e`
- `KERNEL32!SetEvent` at `0x14000722e`
- `RPCRT4!RpcMgmtStopServerListening` at `0x140007236`
- `RPCRT4!RpcMgmtStopServerListening` at `0x140007236`

## pseudocode

```c
unsigned int __fastcall ServiceStop(int a1)
{
  _QWORD *v2; // rcx
  _QWORD *v3; // r9
  __int64 v4; // r8
  _QWORD *v5; // rdx
  unsigned int result; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids);
  if ( !a1 && CheckForOpenHandles() )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids);
    return ReportStatusToSCMgr(4u, 0, 0xBB8u);
  }
  NfsClntGlobals = 1;
  EnterCriticalSection(&DeviceListCS);
  if ( !a1 )
  {
    v2 = pDeviceList;
    if ( pDeviceList )
    {
      v3 = pDeviceList;
      do
      {
        v4 = v2[9];
        v5 = v2 + 8;
        if ( v4 )
          *(_QWORD *)(v4 + 64) = *v5;
        if ( *v5 )
          *(_QWORD *)(*v5 + 72LL) = v2[9];
        pDeviceList = (HGLOBAL)v3[8];
        v2[9] = 0;
        *v5 = 0;
        GlobalFree(v2);
        v2 = pDeviceList;
        v3 = pDeviceList;
      }
      while ( pDeviceList );
    }
  }
  LeaveCriticalSection(&DeviceListCS);
  SetEvent(g_hShutdownEvent);
  result = RpcMgmtStopServerListening(0);
  if ( !a1 && result )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids, result);
    return ReportStatusToSCMgr(4u, 0, 0xBB8u);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    return WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids);
  return result;
}

```

## disassembly

```asm
0x140007124  mov     [rsp+arg_0], rbx
0x140007129  push    rdi
0x14000712a  sub     rsp, 20h
0x14000712e  mov     ebx, ecx
0x140007130  mov     rcx, cs:WPP_GLOBAL_Control
0x140007137  lea     rdi, WPP_GLOBAL_Control
0x14000713e  cmp     rcx, rdi
0x140007141  jz      short loc_14000715E
0x140007143  test    byte ptr [rcx+1Ch], 1
0x140007147  jz      short loc_14000715E
0x140007149  mov     rcx, [rcx+10h]
0x14000714d  lea     r8, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids
0x140007154  mov     edx, 30h ; '0'
0x140007159  call    WPP_SF_
0x14000715e  test    ebx, ebx
0x140007160  jnz     short loc_14000719D
0x140007162  call    CheckForOpenHandles
0x140007167  test    eax, eax
0x140007169  jz      short loc_14000719D
0x14000716b  mov     rcx, cs:WPP_GLOBAL_Control
0x140007172  cmp     rcx, rdi
0x140007175  jz      loc_14000726C
0x14000717b  test    byte ptr [rcx+1Ch], 10h
0x14000717f  jz      loc_14000726C
0x140007185  mov     rcx, [rcx+10h]
0x140007189  lea     edx, [rbx+31h]
0x14000718c  lea     r8, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids
0x140007193  call    WPP_SF_
0x140007198  jmp     loc_14000726C
0x14000719d  lea     rcx, DeviceListCS; lpCriticalSection
0x1400071a4  mov     cs:NfsClntGlobals, 1
0x1400071ae  call    cs:__imp_EnterCriticalSection
0x1400071b4  test    ebx, ebx
0x1400071b6  jnz     short loc_14000721A
0x1400071b8  mov     rcx, cs:pDeviceList; hMem
0x1400071bf  test    rcx, rcx
0x1400071c2  jz      short loc_14000721A
0x1400071c4  mov     r9, rcx
0x1400071c7  mov     r8, [rcx+48h]
0x1400071cb  lea     rdx, [rcx+40h]
0x1400071cf  test    r8, r8
0x1400071d2  jz      short loc_1400071DB
0x1400071d4  mov     rax, [rdx]
0x1400071d7  mov     [r8+40h], rax
0x1400071db  mov     r8, [rdx]
0x1400071de  test    r8, r8
0x1400071e1  jz      short loc_1400071EB
0x1400071e3  mov     rax, [rcx+48h]
0x1400071e7  mov     [r8+48h], rax
0x1400071eb  mov     rax, [r9+40h]
0x1400071ef  mov     cs:pDeviceList, rax
0x1400071f6  mov     qword ptr [rcx+48h], 0
0x1400071fe  mov     qword ptr [rdx], 0
0x140007205  call    cs:__imp_GlobalFree
0x14000720b  mov     rcx, cs:pDeviceList
0x140007212  mov     r9, rcx
0x140007215  test    rcx, rcx
0x140007218  jnz     short loc_1400071C7
0x14000721a  lea     rcx, DeviceListCS; lpCriticalSection
0x140007221  call    cs:__imp_LeaveCriticalSection
0x140007227  mov     rcx, cs:g_hShutdownEvent; hEvent
0x14000722e  call    cs:__imp_SetEvent
0x140007234  xor     ecx, ecx; Binding
0x140007236  call    cs:__imp_RpcMgmtStopServerListening
0x14000723c  test    ebx, ebx
0x14000723e  jnz     short loc_14000727E
0x140007240  test    eax, eax
0x140007242  jz      short loc_14000727E
0x140007244  mov     rcx, cs:WPP_GLOBAL_Control
0x14000724b  cmp     rcx, rdi
0x14000724e  jz      short loc_14000726C
0x140007250  test    byte ptr [rcx+1Ch], 2
0x140007254  jz      short loc_14000726C
0x140007256  mov     rcx, [rcx+10h]
0x14000725a  lea     edx, [rbx+32h]
0x14000725d  mov     r9d, eax
0x140007260  lea     r8, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids
0x140007267  call    WPP_SF_d
0x14000726c  xor     edx, edx
0x14000726e  mov     r8d, 0BB8h
0x140007274  lea     ecx, [rdx+4]
0x140007277  call    ReportStatusToSCMgr
0x14000727c  jmp     short loc_1400072A5
0x14000727e  mov     rcx, cs:WPP_GLOBAL_Control
0x140007285  cmp     rcx, rdi
0x140007288  jz      short loc_1400072A5
0x14000728a  test    byte ptr [rcx+1Ch], 1
0x14000728e  jz      short loc_1400072A5
0x140007290  mov     rcx, [rcx+10h]
0x140007294  lea     r8, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids
0x14000729b  mov     edx, 33h ; '3'
0x1400072a0  call    WPP_SF_
0x1400072a5  mov     rbx, [rsp+28h+arg_0]
0x1400072aa  add     rsp, 20h
0x1400072ae  pop     rdi
0x1400072af  retn
```
