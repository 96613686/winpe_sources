# CInterfaceMonitor::Start(void)

- ea: `0x180041848`
- end: `0x180041b7a`
- name: `?Start@CInterfaceMonitor@@QEAAJXZ`
- size: `818`
- prototype: `__int64 __fastcall(CInterfaceMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800271d0`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x180041848`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041903`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041903`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180041af0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180041af0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180041b00`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180041b00`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800418ee`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800418ee`
- `WINNSI!NsiDisconnectFromServer` at `0x180041a3b`
- `WINNSI!NsiDisconnectFromServer` at `0x180041a3b`
- `WINNSI!NsiRpcRegisterChangeNotification` at `0x1800419f6`
- `WINNSI!NsiRpcRegisterChangeNotification` at `0x1800419f6`
- `WINNSI!NsiConnectToServer` at `0x180041987`
- `WINNSI!NsiConnectToServer` at `0x180041987`
- `ntdll!RtlNtStatusToDosError` at `0x180041a50`
- `ntdll!RtlNtStatusToDosError` at `0x180041a50`

## pseudocode

```c
__int64 __fastcall CInterfaceMonitor::Start(CInterfaceMonitor *this)
{
  CInterfaceMonitor *v1; // rdi
  PTP_WORK ThreadpoolWork; // rax
  signed int LastError; // eax
  unsigned int v4; // ebx
  PVOID *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rax
  int v8; // eax
  NTSTATUS v9; // esi
  signed int v10; // eax

  v1 = g_pDnsInterfaceMonitor;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_7d9c591b7bd93107528617e14d5ec105_Traceguids);
  }
  *((_DWORD *)v1 + 4) = 3;
  *((_QWORD *)v1 + 3) = 0;
  *((_QWORD *)v1 + 4) = 0;
  *((_QWORD *)v1 + 5) = 0;
  *((_QWORD *)v1 + 6) = 0;
  *((_QWORD *)v1 + 7) = 0;
  *((_QWORD *)v1 + 8) = 0;
  *((_DWORD *)v1 + 18) = 0;
  *((_DWORD *)v1 + 19) = 1;
  *((_DWORD *)v1 + 20) = 72;
  ThreadpoolWork = CreateThreadpoolWork(
                     CInterfaceMonitor::InterfaceChangeBackgroundProcessing,
                     0,
                     (PTP_CALLBACK_ENVIRON)((char *)v1 + 16));
  *((_QWORD *)v1 + 1) = ThreadpoolWork;
  if ( !ThreadpoolWork )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_39:
      if ( (v4 & 0x80000000) == 0 )
        goto LABEL_47;
      goto LABEL_40;
    }
    v6 = 15;
    goto LABEL_37;
  }
  v4 = 0;
  if ( *((_QWORD *)v1 + 17) )
  {
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v4;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      goto LABEL_47;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_7d9c591b7bd93107528617e14d5ec105_Traceguids);
    goto LABEL_46;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_7d9c591b7bd93107528617e14d5ec105_Traceguids);
  }
  v7 = NsiConnectToServer(0);
  *((_QWORD *)v1 + 16) = v7;
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_7d9c591b7bd93107528617e14d5ec105_Traceguids);
    }
    v8 = NsiRpcRegisterChangeNotification(
           *((_QWORD *)v1 + 16),
           &NPI_MS_NDIS_MODULEID,
           1,
           &CInterfaceMonitor::NsiInterfaceChangeCallback,
           1,
           v1,
           (char *)v1 + 136);
    v9 = v8;
    if ( v8 >= 0 )
    {
      v5 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v4;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
        goto LABEL_47;
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_7d9c591b7bd93107528617e14d5ec105_Traceguids);
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          &WPP_7d9c591b7bd93107528617e14d5ec105_Traceguids,
          (unsigned int)v8);
      }
      NsiDisconnectFromServer(*((_QWORD *)v1 + 16));
      *((_QWORD *)v1 + 16) = 0;
      v10 = RtlNtStatusToDosError(v9);
      v4 = v10;
      if ( v10 > 0 )
        v4 = (unsigned __int16)v10 | 0x80070000;
    }
    goto LABEL_38;
  }
  v4 = -2147024890;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v6 = 20;
LABEL_37:
    WPP_SF_d(v5[2], v6, &WPP_7d9c591b7bd93107528617e14d5ec105_Traceguids, v4);
LABEL_38:
    v5 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_39;
  }
LABEL_40:
  if ( *((_QWORD *)v1 + 1) )
  {
    WaitForThreadpoolWorkCallbacks(*((PTP_WORK *)v1 + 1), 1);
    CloseThreadpoolWork(*((PTP_WORK *)v1 + 1));
    *((_QWORD *)v1 + 1) = 0;
LABEL_46:
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_47:
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x10) != 0 && *((_BYTE *)v5 + 25) >= 6u )
    WPP_SF_d(v5[2], 22, &WPP_7d9c591b7bd93107528617e14d5ec105_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x180041848  push    rbx
0x18004184a  push    rsi
0x18004184b  push    rdi
0x18004184c  push    r12
0x18004184e  push    r15
0x180041850  sub     rsp, 40h
0x180041854  mov     rdi, cs:?g_pDnsInterfaceMonitor@@3PEAVCInterfaceMonitor@@EA; CInterfaceMonitor * g_pDnsInterfaceMonitor
0x18004185b  mov     rcx, cs:WPP_GLOBAL_Control
0x180041862  lea     r15, WPP_GLOBAL_Control
0x180041869  lea     r12, WPP_7d9c591b7bd93107528617e14d5ec105_Traceguids
0x180041870  cmp     rcx, r15
0x180041873  jz      short loc_180041892
0x180041875  test    byte ptr [rcx+1Ch], 10h
0x180041879  jz      short loc_180041892
0x18004187b  cmp     byte ptr [rcx+19h], 6
0x18004187f  jb      short loc_180041892
0x180041881  mov     rcx, [rcx+10h]
0x180041885  mov     edx, 0Eh
0x18004188a  mov     r8, r12
0x18004188d  call    WPP_SF_
0x180041892  lea     r8, [rdi+10h]; pcbe
0x180041896  xor     edx, edx; pv
0x180041898  lea     rcx, ?InterfaceChangeBackgroundProcessing@CInterfaceMonitor@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18004189f  mov     dword ptr [r8], 3
0x1800418a6  mov     qword ptr [r8+8], 0
0x1800418ae  mov     qword ptr [r8+10h], 0
0x1800418b6  mov     qword ptr [r8+18h], 0
0x1800418be  mov     qword ptr [r8+20h], 0
0x1800418c6  mov     qword ptr [r8+28h], 0
0x1800418ce  mov     qword ptr [r8+30h], 0
0x1800418d6  mov     dword ptr [r8+38h], 0
0x1800418de  mov     dword ptr [r8+3Ch], 1
0x1800418e6  mov     dword ptr [r8+40h], 48h ; 'H'
0x1800418ee  call    cs:__imp_CreateThreadpoolWork
0x1800418f5  nop     dword ptr [rax+rax+00h]
0x1800418fa  mov     [rdi+8], rax
0x1800418fe  test    rax, rax
0x180041901  jnz     short loc_18004194C
0x180041903  call    cs:__imp_GetLastError
0x18004190a  nop     dword ptr [rax+rax+00h]
0x18004190f  mov     ebx, eax
0x180041911  test    eax, eax
0x180041913  jle     short loc_18004191E
0x180041915  movzx   ebx, ax
0x180041918  or      ebx, 80070000h
0x18004191e  mov     rcx, cs:WPP_GLOBAL_Control
0x180041925  cmp     rcx, r15
0x180041928  jz      loc_180041ADC
0x18004192e  test    byte ptr [rcx+1Ch], 10h
0x180041932  jz      loc_180041ADC
0x180041938  cmp     byte ptr [rcx+19h], 2
0x18004193c  jb      loc_180041ADC
0x180041942  mov     edx, 0Fh
0x180041947  jmp     loc_180041AC6
0x18004194c  xor     ebx, ebx
0x18004194e  lea     rsi, [rdi+88h]
0x180041955  cmp     [rsi], rbx
0x180041958  jnz     loc_180041B16
0x18004195e  mov     rcx, cs:WPP_GLOBAL_Control
0x180041965  cmp     rcx, r15
0x180041968  jz      short loc_180041985
0x18004196a  test    byte ptr [rcx+1Ch], 10h
0x18004196e  jz      short loc_180041985
0x180041970  cmp     byte ptr [rcx+19h], 5
0x180041974  jb      short loc_180041985
0x180041976  mov     rcx, [rcx+10h]
0x18004197a  lea     edx, [rbx+10h]
0x18004197d  mov     r8, r12
0x180041980  call    WPP_SF_
0x180041985  xor     ecx, ecx
0x180041987  call    cs:__imp_NsiConnectToServer
0x18004198e  nop     dword ptr [rax+rax+00h]
0x180041993  mov     [rdi+80h], rax
0x18004199a  test    rax, rax
0x18004199d  jz      loc_180041AA4
0x1800419a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800419aa  cmp     rcx, r15
0x1800419ad  jz      short loc_1800419CC
0x1800419af  test    byte ptr [rcx+1Ch], 10h
0x1800419b3  jz      short loc_1800419CC
0x1800419b5  cmp     byte ptr [rcx+19h], 5
0x1800419b9  jb      short loc_1800419CC
0x1800419bb  mov     rcx, [rcx+10h]
0x1800419bf  mov     edx, 11h
0x1800419c4  mov     r8, r12
0x1800419c7  call    WPP_SF_
0x1800419cc  mov     rcx, [rdi+80h]
0x1800419d3  lea     r9, ?NsiInterfaceChangeCallback@CInterfaceMonitor@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z; CInterfaceMonitor::NsiInterfaceChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)
0x1800419da  mov     [rsp+68h+var_38], rsi
0x1800419df  lea     rdx, NPI_MS_NDIS_MODULEID
0x1800419e6  mov     [rsp+68h+var_40], rdi
0x1800419eb  mov     r8d, 1
0x1800419f1  mov     [rsp+68h+var_48], 1
0x1800419f6  call    cs:__imp_NsiRpcRegisterChangeNotification
0x1800419fd  nop     dword ptr [rax+rax+00h]
0x180041a02  mov     esi, eax
0x180041a04  test    eax, eax
0x180041a06  jns     short loc_180041A6D
0x180041a08  mov     rcx, cs:WPP_GLOBAL_Control
0x180041a0f  cmp     rcx, r15
0x180041a12  jz      short loc_180041A34
0x180041a14  test    byte ptr [rcx+1Ch], 10h
0x180041a18  jz      short loc_180041A34
0x180041a1a  cmp     byte ptr [rcx+19h], 2
0x180041a1e  jb      short loc_180041A34
0x180041a20  mov     rcx, [rcx+10h]
0x180041a24  mov     edx, 12h
0x180041a29  mov     r9d, eax
0x180041a2c  mov     r8, r12
0x180041a2f  call    WPP_SF_d
0x180041a34  mov     rcx, [rdi+80h]
0x180041a3b  call    cs:__imp_NsiDisconnectFromServer
0x180041a42  nop     dword ptr [rax+rax+00h]
0x180041a47  mov     ecx, esi; Status
0x180041a49  mov     [rdi+80h], rbx
0x180041a50  call    cs:__imp_RtlNtStatusToDosError
0x180041a57  nop     dword ptr [rax+rax+00h]
0x180041a5c  mov     ebx, eax
0x180041a5e  test    eax, eax
0x180041a60  jle     short loc_180041AD5
0x180041a62  movzx   ebx, ax
0x180041a65  or      ebx, 80070000h
0x180041a6b  jmp     short loc_180041AD5
0x180041a6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180041a74  cmp     rcx, r15
0x180041a77  jz      loc_180041B6B
0x180041a7d  test    byte ptr [rcx+1Ch], 10h
0x180041a81  jz      loc_180041B46
0x180041a87  cmp     byte ptr [rcx+19h], 5
0x180041a8b  jb      loc_180041B46
0x180041a91  mov     rcx, [rcx+10h]
0x180041a95  mov     edx, 13h
0x180041a9a  mov     r8, r12
0x180041a9d  call    WPP_SF_
0x180041aa2  jmp     short loc_180041AD5
0x180041aa4  mov     ebx, 80070006h
0x180041aa9  mov     rcx, cs:WPP_GLOBAL_Control
0x180041ab0  cmp     rcx, r15
0x180041ab3  jz      short loc_180041AE0
0x180041ab5  test    byte ptr [rcx+1Ch], 10h
0x180041ab9  jz      short loc_180041AE0
0x180041abb  cmp     byte ptr [rcx+19h], 2
0x180041abf  jb      short loc_180041AE0
0x180041ac1  mov     edx, 14h
0x180041ac6  mov     rcx, [rcx+10h]
0x180041aca  mov     r9d, ebx
0x180041acd  mov     r8, r12
0x180041ad0  call    WPP_SF_d
0x180041ad5  mov     rcx, cs:WPP_GLOBAL_Control
0x180041adc  test    ebx, ebx
0x180041ade  jns     short loc_180041B46
0x180041ae0  cmp     qword ptr [rdi+8], 0
0x180041ae5  jz      short loc_180041B46
0x180041ae7  mov     rcx, [rdi+8]; pwk
0x180041aeb  mov     edx, 1; fCancelPendingCallbacks
0x180041af0  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180041af7  nop     dword ptr [rax+rax+00h]
0x180041afc  mov     rcx, [rdi+8]; pwk
0x180041b00  call    cs:__imp_CloseThreadpoolWork
0x180041b07  nop     dword ptr [rax+rax+00h]
0x180041b0c  mov     qword ptr [rdi+8], 0
0x180041b14  jmp     short loc_180041B3F
0x180041b16  mov     rcx, cs:WPP_GLOBAL_Control
0x180041b1d  cmp     rcx, r15
0x180041b20  jz      short loc_180041B6B
0x180041b22  test    byte ptr [rcx+1Ch], 10h
0x180041b26  jz      short loc_180041B46
0x180041b28  cmp     byte ptr [rcx+19h], 5
0x180041b2c  jb      short loc_180041B46
0x180041b2e  mov     rcx, [rcx+10h]
0x180041b32  mov     edx, 15h
0x180041b37  mov     r8, r12
0x180041b3a  call    WPP_SF_
0x180041b3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180041b46  cmp     rcx, r15
0x180041b49  jz      short loc_180041B6B
0x180041b4b  test    byte ptr [rcx+1Ch], 10h
0x180041b4f  jz      short loc_180041B6B
0x180041b51  cmp     byte ptr [rcx+19h], 6
0x180041b55  jb      short loc_180041B6B
0x180041b57  mov     rcx, [rcx+10h]
0x180041b5b  mov     edx, 16h
0x180041b60  mov     r9d, ebx
0x180041b63  mov     r8, r12
0x180041b66  call    WPP_SF_d
0x180041b6b  mov     eax, ebx
0x180041b6d  add     rsp, 40h
0x180041b71  pop     r15
0x180041b73  pop     r12
0x180041b75  pop     rdi
0x180041b76  pop     rsi
0x180041b77  pop     rbx
0x180041b78  retn
```
