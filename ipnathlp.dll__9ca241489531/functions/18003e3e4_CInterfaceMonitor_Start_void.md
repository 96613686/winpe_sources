# CInterfaceMonitor::Start(void)

- ea: `0x18003e3e4`
- end: `0x18003e6e5`
- name: `?Start@CInterfaceMonitor@@QEAAJXZ`
- size: `769`
- prototype: `__int64 __fastcall(CInterfaceMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180024c90`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18003e3e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e499`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e499`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18003e668`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18003e668`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18003e672`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18003e672`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18003e48a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18003e48a`
- `WINNSI!NsiDisconnectFromServer` at `0x18003e5bf`
- `WINNSI!NsiDisconnectFromServer` at `0x18003e5bf`
- `WINNSI!NsiRpcRegisterChangeNotification` at `0x18003e580`
- `WINNSI!NsiRpcRegisterChangeNotification` at `0x18003e580`
- `WINNSI!NsiConnectToServer` at `0x18003e517`
- `WINNSI!NsiConnectToServer` at `0x18003e517`
- `ntdll!RtlNtStatusToDosError` at `0x18003e5ce`
- `ntdll!RtlNtStatusToDosError` at `0x18003e5ce`

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
0x18003e3e4  push    rbx
0x18003e3e6  push    rsi
0x18003e3e7  push    rdi
0x18003e3e8  push    r12
0x18003e3ea  push    r15
0x18003e3ec  sub     rsp, 40h
0x18003e3f0  mov     rdi, cs:?g_pDnsInterfaceMonitor@@3PEAVCInterfaceMonitor@@EA; CInterfaceMonitor * g_pDnsInterfaceMonitor
0x18003e3f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e3fe  lea     r15, WPP_GLOBAL_Control
0x18003e405  lea     r12, WPP_7d9c591b7bd93107528617e14d5ec105_Traceguids
0x18003e40c  cmp     rcx, r15
0x18003e40f  jz      short loc_18003E42E
0x18003e411  test    byte ptr [rcx+1Ch], 10h
0x18003e415  jz      short loc_18003E42E
0x18003e417  cmp     byte ptr [rcx+19h], 6
0x18003e41b  jb      short loc_18003E42E
0x18003e41d  mov     rcx, [rcx+10h]
0x18003e421  mov     edx, 0Eh
0x18003e426  mov     r8, r12
0x18003e429  call    WPP_SF_
0x18003e42e  lea     r8, [rdi+10h]; pcbe
0x18003e432  xor     edx, edx; pv
0x18003e434  lea     rcx, ?InterfaceChangeBackgroundProcessing@CInterfaceMonitor@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18003e43b  mov     dword ptr [r8], 3
0x18003e442  mov     qword ptr [r8+8], 0
0x18003e44a  mov     qword ptr [r8+10h], 0
0x18003e452  mov     qword ptr [r8+18h], 0
0x18003e45a  mov     qword ptr [r8+20h], 0
0x18003e462  mov     qword ptr [r8+28h], 0
0x18003e46a  mov     qword ptr [r8+30h], 0
0x18003e472  mov     dword ptr [r8+38h], 0
0x18003e47a  mov     dword ptr [r8+3Ch], 1
0x18003e482  mov     dword ptr [r8+40h], 48h ; 'H'
0x18003e48a  call    cs:__imp_CreateThreadpoolWork
0x18003e490  mov     [rdi+8], rax
0x18003e494  test    rax, rax
0x18003e497  jnz     short loc_18003E4DC
0x18003e499  call    cs:__imp_GetLastError
0x18003e49f  mov     ebx, eax
0x18003e4a1  test    eax, eax
0x18003e4a3  jle     short loc_18003E4AE
0x18003e4a5  movzx   ebx, ax
0x18003e4a8  or      ebx, 80070000h
0x18003e4ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e4b5  cmp     rcx, r15
0x18003e4b8  jz      loc_18003E654
0x18003e4be  test    byte ptr [rcx+1Ch], 10h
0x18003e4c2  jz      loc_18003E654
0x18003e4c8  cmp     byte ptr [rcx+19h], 2
0x18003e4cc  jb      loc_18003E654
0x18003e4d2  mov     edx, 0Fh
0x18003e4d7  jmp     loc_18003E63E
0x18003e4dc  xor     ebx, ebx
0x18003e4de  lea     rsi, [rdi+88h]
0x18003e4e5  cmp     [rsi], rbx
0x18003e4e8  jnz     loc_18003E682
0x18003e4ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e4f5  cmp     rcx, r15
0x18003e4f8  jz      short loc_18003E515
0x18003e4fa  test    byte ptr [rcx+1Ch], 10h
0x18003e4fe  jz      short loc_18003E515
0x18003e500  cmp     byte ptr [rcx+19h], 5
0x18003e504  jb      short loc_18003E515
0x18003e506  mov     rcx, [rcx+10h]
0x18003e50a  lea     edx, [rbx+10h]
0x18003e50d  mov     r8, r12
0x18003e510  call    WPP_SF_
0x18003e515  xor     ecx, ecx
0x18003e517  call    cs:__imp_NsiConnectToServer
0x18003e51d  mov     [rdi+80h], rax
0x18003e524  test    rax, rax
0x18003e527  jz      loc_18003E61C
0x18003e52d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e534  cmp     rcx, r15
0x18003e537  jz      short loc_18003E556
0x18003e539  test    byte ptr [rcx+1Ch], 10h
0x18003e53d  jz      short loc_18003E556
0x18003e53f  cmp     byte ptr [rcx+19h], 5
0x18003e543  jb      short loc_18003E556
0x18003e545  mov     rcx, [rcx+10h]
0x18003e549  mov     edx, 11h
0x18003e54e  mov     r8, r12
0x18003e551  call    WPP_SF_
0x18003e556  mov     rcx, [rdi+80h]
0x18003e55d  lea     r9, ?NsiInterfaceChangeCallback@CInterfaceMonitor@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z; CInterfaceMonitor::NsiInterfaceChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)
0x18003e564  mov     [rsp+68h+var_38], rsi
0x18003e569  lea     rdx, NPI_MS_NDIS_MODULEID
0x18003e570  mov     [rsp+68h+var_40], rdi
0x18003e575  mov     r8d, 1
0x18003e57b  mov     [rsp+68h+var_48], 1
0x18003e580  call    cs:__imp_NsiRpcRegisterChangeNotification
0x18003e586  mov     esi, eax
0x18003e588  test    eax, eax
0x18003e58a  jns     short loc_18003E5E5
0x18003e58c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e593  cmp     rcx, r15
0x18003e596  jz      short loc_18003E5B8
0x18003e598  test    byte ptr [rcx+1Ch], 10h
0x18003e59c  jz      short loc_18003E5B8
0x18003e59e  cmp     byte ptr [rcx+19h], 2
0x18003e5a2  jb      short loc_18003E5B8
0x18003e5a4  mov     rcx, [rcx+10h]
0x18003e5a8  mov     edx, 12h
0x18003e5ad  mov     r9d, eax
0x18003e5b0  mov     r8, r12
0x18003e5b3  call    WPP_SF_d
0x18003e5b8  mov     rcx, [rdi+80h]
0x18003e5bf  call    cs:__imp_NsiDisconnectFromServer
0x18003e5c5  mov     ecx, esi; Status
0x18003e5c7  mov     [rdi+80h], rbx
0x18003e5ce  call    cs:__imp_RtlNtStatusToDosError
0x18003e5d4  mov     ebx, eax
0x18003e5d6  test    eax, eax
0x18003e5d8  jle     short loc_18003E64D
0x18003e5da  movzx   ebx, ax
0x18003e5dd  or      ebx, 80070000h
0x18003e5e3  jmp     short loc_18003E64D
0x18003e5e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e5ec  cmp     rcx, r15
0x18003e5ef  jz      loc_18003E6D7
0x18003e5f5  test    byte ptr [rcx+1Ch], 10h
0x18003e5f9  jz      loc_18003E6B2
0x18003e5ff  cmp     byte ptr [rcx+19h], 5
0x18003e603  jb      loc_18003E6B2
0x18003e609  mov     rcx, [rcx+10h]
0x18003e60d  mov     edx, 13h
0x18003e612  mov     r8, r12
0x18003e615  call    WPP_SF_
0x18003e61a  jmp     short loc_18003E64D
0x18003e61c  mov     ebx, 80070006h
0x18003e621  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e628  cmp     rcx, r15
0x18003e62b  jz      short loc_18003E658
0x18003e62d  test    byte ptr [rcx+1Ch], 10h
0x18003e631  jz      short loc_18003E658
0x18003e633  cmp     byte ptr [rcx+19h], 2
0x18003e637  jb      short loc_18003E658
0x18003e639  mov     edx, 14h
0x18003e63e  mov     rcx, [rcx+10h]
0x18003e642  mov     r9d, ebx
0x18003e645  mov     r8, r12
0x18003e648  call    WPP_SF_d
0x18003e64d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e654  test    ebx, ebx
0x18003e656  jns     short loc_18003E6B2
0x18003e658  cmp     qword ptr [rdi+8], 0
0x18003e65d  jz      short loc_18003E6B2
0x18003e65f  mov     rcx, [rdi+8]; pwk
0x18003e663  mov     edx, 1; fCancelPendingCallbacks
0x18003e668  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18003e66e  mov     rcx, [rdi+8]; pwk
0x18003e672  call    cs:__imp_CloseThreadpoolWork
0x18003e678  mov     qword ptr [rdi+8], 0
0x18003e680  jmp     short loc_18003E6AB
0x18003e682  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e689  cmp     rcx, r15
0x18003e68c  jz      short loc_18003E6D7
0x18003e68e  test    byte ptr [rcx+1Ch], 10h
0x18003e692  jz      short loc_18003E6B2
0x18003e694  cmp     byte ptr [rcx+19h], 5
0x18003e698  jb      short loc_18003E6B2
0x18003e69a  mov     rcx, [rcx+10h]
0x18003e69e  mov     edx, 15h
0x18003e6a3  mov     r8, r12
0x18003e6a6  call    WPP_SF_
0x18003e6ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e6b2  cmp     rcx, r15
0x18003e6b5  jz      short loc_18003E6D7
0x18003e6b7  test    byte ptr [rcx+1Ch], 10h
0x18003e6bb  jz      short loc_18003E6D7
0x18003e6bd  cmp     byte ptr [rcx+19h], 6
0x18003e6c1  jb      short loc_18003E6D7
0x18003e6c3  mov     rcx, [rcx+10h]
0x18003e6c7  mov     edx, 16h
0x18003e6cc  mov     r9d, ebx
0x18003e6cf  mov     r8, r12
0x18003e6d2  call    WPP_SF_d
0x18003e6d7  mov     eax, ebx
0x18003e6d9  add     rsp, 40h
0x18003e6dd  pop     r15
0x18003e6df  pop     r12
0x18003e6e1  pop     rdi
0x18003e6e2  pop     rsi
0x18003e6e3  pop     rbx
0x18003e6e4  retn
```
