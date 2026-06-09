# RasUnregisterEntryChangeNotification

- ea: `0x180043890`
- end: `0x180043a34`
- name: `RasUnregisterEntryChangeNotification`
- size: `420`
- prototype: `__int64 __fastcall(HGLOBAL hMem)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callees

- `0x180010d10`
- `0x180011084`
- `0x1800111f4`
- `0x180043890`
- `0x18004e580`
- `0x18007f18c`
- `0x1800a7f04`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800439f4`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800439f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800439eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800439eb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800439e1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800439e1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18004399e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18004399e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180043973`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180043973`

## pseudocode

```c
__int64 __fastcall RasUnregisterEntryChangeNotification(unsigned int *hMem)
{
  unsigned int v2; // ebx
  int v3; // esi
  unsigned int RasmanDllAndInit; // eax
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  int IsEnabledDeviceUsageNoInline; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 111, WPP_a576594392393f475090d0b18cfbf556_Traceguids);
  }
  v2 = 0;
  v3 = IsRasmanServiceRunning();
  DebugInit();
  if ( !v3 || (RasmanDllAndInit = LoadRasmanDllAndInit(), (v2 = RasmanDllAndInit) == 0) )
  {
    if ( !hMem )
    {
      v2 = 87;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v2;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_29;
      v6 = 113;
      v7 = 87;
      goto LABEL_12;
    }
    SetThreadpoolWait(*((PTP_WAIT *)hMem + 2), 0, 0);
    if ( (Feature_VPN_BugFixes_25C_RasNotification__private_featureState & 0x10) != 0 )
      IsEnabledDeviceUsageNoInline = Feature_VPN_BugFixes_25C_RasNotification__private_featureState & 1;
    else
      IsEnabledDeviceUsageNoInline = Feature_VPN_BugFixes_25C_RasNotification__private_IsEnabledDeviceUsageNoInline();
    WaitForThreadpoolWaitCallbacks(*((PTP_WAIT *)hMem + 2), IsEnabledDeviceUsageNoInline != 0);
    if ( !v3
      || (RasmanDllAndInit = ((__int64 (__fastcall *)(_QWORD))g_pRasRemoveNotificationEx)(*hMem),
          (v2 = RasmanDllAndInit) == 0) )
    {
      CloseThreadpoolWait(*((PTP_WAIT *)hMem + 2));
      CloseHandle(*((HANDLE *)hMem + 1));
      GlobalFree(hMem);
      goto LABEL_28;
    }
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v2;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_29;
    v6 = 114;
LABEL_11:
    v7 = RasmanDllAndInit;
LABEL_12:
    WPP_SF_d(v5[2], v6, WPP_a576594392393f475090d0b18cfbf556_Traceguids, v7);
LABEL_28:
    v5 = WPP_GLOBAL_Control;
    goto LABEL_29;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v2;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v6 = 112;
    goto LABEL_11;
  }
LABEL_29:
  if ( v5 != &WPP_GLOBAL_Control && (*((_DWORD *)v5 + 7) & 0x800) != 0 && *((_BYTE *)v5 + 25) >= 6u )
    WPP_SF_d(v5[2], 115, WPP_a576594392393f475090d0b18cfbf556_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x180043890  push    rbx
0x180043892  push    rbp
0x180043893  push    rsi
0x180043894  push    rdi
0x180043895  push    r14
0x180043897  push    r15
0x180043899  sub     rsp, 28h
0x18004389d  mov     rdi, rcx
0x1800438a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800438a7  lea     r14, WPP_GLOBAL_Control
0x1800438ae  lea     r15, WPP_a576594392393f475090d0b18cfbf556_Traceguids
0x1800438b5  mov     ebp, 800h
0x1800438ba  cmp     rcx, r14
0x1800438bd  jz      short loc_1800438DE
0x1800438bf  test    [rcx+1Ch], ebp
0x1800438c2  jz      short loc_1800438DE
0x1800438c4  cmp     byte ptr [rcx+19h], 6
0x1800438c8  jb      short loc_1800438DE
0x1800438ca  mov     rcx, [rcx+10h]
0x1800438ce  mov     edx, 6Fh ; 'o'
0x1800438d3  mov     r9, rdi
0x1800438d6  mov     r8, r15
0x1800438d9  call    WPP_SF_q
0x1800438de  xor     ebx, ebx
0x1800438e0  call    IsRasmanServiceRunning
0x1800438e5  mov     esi, eax
0x1800438e7  call    DebugInit
0x1800438ec  test    esi, esi
0x1800438ee  jz      short loc_180043937
0x1800438f0  call    LoadRasmanDllAndInit
0x1800438f5  mov     ebx, eax
0x1800438f7  test    eax, eax
0x1800438f9  jz      short loc_180043937
0x1800438fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180043902  cmp     rcx, r14
0x180043905  jz      loc_180043A25
0x18004390b  test    [rcx+1Ch], ebp
0x18004390e  jz      loc_180043A01
0x180043914  cmp     byte ptr [rcx+19h], 2
0x180043918  jb      loc_180043A01
0x18004391e  mov     edx, 70h ; 'p'
0x180043923  mov     r9d, eax
0x180043926  mov     rcx, [rcx+10h]
0x18004392a  mov     r8, r15
0x18004392d  call    WPP_SF_d
0x180043932  jmp     loc_1800439FA
0x180043937  test    rdi, rdi
0x18004393a  jnz     short loc_18004396A
0x18004393c  lea     ebx, [rdi+57h]
0x18004393f  mov     rcx, cs:WPP_GLOBAL_Control
0x180043946  cmp     rcx, r14
0x180043949  jz      loc_180043A25
0x18004394f  test    [rcx+1Ch], ebp
0x180043952  jz      loc_180043A01
0x180043958  cmp     byte ptr [rcx+19h], 2
0x18004395c  jb      loc_180043A01
0x180043962  lea     edx, [rdi+71h]
0x180043965  mov     r9d, ebx
0x180043968  jmp     short loc_180043926
0x18004396a  mov     rcx, [rdi+10h]; pwa
0x18004396e  xor     r8d, r8d; pftTimeout
0x180043971  xor     edx, edx; h
0x180043973  call    cs:__imp_SetThreadpoolWait
0x180043979  mov     eax, cs:Feature_VPN_BugFixes_25C_RasNotification__private_featureState
0x18004397f  test    al, 10h
0x180043981  jz      short loc_180043988
0x180043983  and     eax, 1
0x180043986  jmp     short loc_18004398D
0x180043988  call    Feature_VPN_BugFixes_25C_RasNotification__private_IsEnabledDeviceUsageNoInline
0x18004398d  mov     rcx, [rdi+10h]; pwa
0x180043991  test    eax, eax
0x180043993  jnz     short loc_180043999
0x180043995  xor     edx, edx
0x180043997  jmp     short loc_18004399E
0x180043999  mov     edx, 1; fCancelPendingCallbacks
0x18004399e  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800439a4  test    esi, esi
0x1800439a6  jz      short loc_1800439DD
0x1800439a8  mov     ecx, [rdi]
0x1800439aa  mov     rax, cs:g_pRasRemoveNotificationEx
0x1800439b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800439b6  mov     ebx, eax
0x1800439b8  test    eax, eax
0x1800439ba  jz      short loc_1800439DD
0x1800439bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800439c3  cmp     rcx, r14
0x1800439c6  jz      short loc_180043A25
0x1800439c8  test    [rcx+1Ch], ebp
0x1800439cb  jz      short loc_180043A01
0x1800439cd  cmp     byte ptr [rcx+19h], 2
0x1800439d1  jb      short loc_180043A01
0x1800439d3  mov     edx, 72h ; 'r'
0x1800439d8  jmp     loc_180043923
0x1800439dd  mov     rcx, [rdi+10h]; pwa
0x1800439e1  call    cs:__imp_CloseThreadpoolWait
0x1800439e7  mov     rcx, [rdi+8]; hObject
0x1800439eb  call    cs:__imp_CloseHandle
0x1800439f1  mov     rcx, rdi; hMem
0x1800439f4  call    cs:__imp_GlobalFree
0x1800439fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180043a01  cmp     rcx, r14
0x180043a04  jz      short loc_180043A25
0x180043a06  test    [rcx+1Ch], ebp
0x180043a09  jz      short loc_180043A25
0x180043a0b  cmp     byte ptr [rcx+19h], 6
0x180043a0f  jb      short loc_180043A25
0x180043a11  mov     rcx, [rcx+10h]
0x180043a15  mov     edx, 73h ; 's'
0x180043a1a  mov     r9d, ebx
0x180043a1d  mov     r8, r15
0x180043a20  call    WPP_SF_d
0x180043a25  mov     eax, ebx
0x180043a27  add     rsp, 28h
0x180043a2b  pop     r15
0x180043a2d  pop     r14
0x180043a2f  pop     rdi
0x180043a30  pop     rsi
0x180043a31  pop     rbp
0x180043a32  pop     rbx
0x180043a33  retn
```
