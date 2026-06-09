# V2NatStartDnsServer(_GUID const *)

- ea: `0x180026500`
- end: `0x180026c3a`
- name: `?V2NatStartDnsServer@@YAKPEBU_GUID@@@Z`
- size: `1850`
- prototype: `unsigned int __fastcall(const struct _GUID *)`
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x180025510`

## callees

- `0x18000c1e0`
- `0x18000c3c0`
- `0x18000ca20`
- `0x18000d090`
- `0x180010ac8`
- `0x1800202e0`
- `0x180026500`
- `0x180026c40`
- `0x180026e10`
- `0x1800271d0`
- `0x180027cec`
- `0x180027df0`
- `0x180027eec`
- `0x18004561c`
- `0x180047418`
- `0x18004f0a0`
- `0x180051f30`
- `0x180066398`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18002663b`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18002663b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026720`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026720`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026734`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026734`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026668`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026668`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026697`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026697`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800266b5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800266b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800268cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026903`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800268cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026903`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026c29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026c29`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002655b`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002655b`

## pseudocode

```c
__int64 __fastcall V2NatStartDnsServer(const struct _GUID *a1)
{
  void *v2; // rbp
  unsigned int v3; // ebx
  SC_HANDLE v4; // rax
  PVOID *v5; // rcx
  BOOL v7; // edi
  unsigned int v8; // esi
  unsigned int v9; // eax
  unsigned int v10; // edi
  struct IP_ADAPTER_BINDING_INFO *BindingInformation; // rax
  struct IP_ADAPTER_BINDING_INFO *v12; // r14
  PVOID *v13; // rcx
  struct _DNS_INTERFACE *i; // rax
  void *v15; // rdi
  unsigned int started; // eax
  HANDLE ProcessHeap; // rax
  __int64 v18; // rdx
  unsigned int AvailableIndex; // edi
  __int64 v20; // r8
  unsigned int Interface; // eax
  PVOID *v22; // rcx
  unsigned int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // r9
  __int64 v26; // rdx
  signed int LastError; // eax
  signed int v28; // eax
  _BOOL8 v29; // r9
  int v30; // ecx
  __int64 v31; // [rsp+20h] [rbp-98h]
  struct _GUID v32; // [rsp+60h] [rbp-58h] BYREF
  __int64 v33; // [rsp+70h] [rbp-48h] BYREF
  int v34; // [rsp+78h] [rbp-40h]
  int v35; // [rsp+7Ch] [rbp-3Ch]
  HANDLE EventW; // [rsp+80h] [rbp-38h]

  v33 = 0x100000001LL;
  v34 = 3;
  v35 = 2;
  v2 = 0;
  v3 = 0;
  v4 = OpenSCManagerW(0, 0, 0x80000000);
  if ( v4 )
  {
    v7 = !NhpIsServiceRunningOrGoingToRun(v4, L"DNS");
LABEL_7:
    v5 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_8;
  }
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_3;
  v7 = 0;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_08734e8991f837002c8edb0c26290ae6_Traceguids,
      (unsigned int)LastError);
    goto LABEL_7;
  }
LABEL_8:
  if ( v5 != &WPP_GLOBAL_Control && (*((_DWORD *)v5 + 7) & 0x200) != 0 && *((_BYTE *)v5 + 25) >= 5u )
  {
    v29 = v7;
    LOBYTE(v29) = !v7;
    WPP_SF_c(v5[2], 11, WPP_08734e8991f837002c8edb0c26290ae6_Traceguids, v29);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 )
  {
    if ( v5 != &WPP_GLOBAL_Control && (*((_DWORD *)v5 + 7) & 0x200) != 0 && *((_BYTE *)v5 + 25) >= 6u )
      WPP_SF_(v5[2], 70, &WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids);
    v8 = -1;
    v32 = *a1;
    v9 = NatMapGuidToAdapter(&v32);
    v10 = v9;
    if ( v9 == -1 )
    {
      v12 = 0;
      v3 = 905;
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_25;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v26 = 71;
LABEL_67:
        WPP_SF_d(v13[2], v26, &WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids, v3);
        goto LABEL_14;
      }
    }
    else
    {
      BindingInformation = NhQueryBindingInformation(v9);
      v12 = BindingInformation;
      if ( BindingInformation )
      {
        qsort(BindingInformation->Address, BindingInformation->AddressCount, 8u, NatCompareLocalBindings);
        v8 = v10;
LABEL_14:
        v13 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_15;
      }
      v3 = 8;
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_25;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v26 = 72;
        goto LABEL_67;
      }
    }
LABEL_15:
    if ( v13 != &WPP_GLOBAL_Control && (*((_DWORD *)v13 + 7) & 0x200) != 0 && *((_BYTE *)v13 + 25) >= 6u )
    {
      WPP_SF_Dd(v13[2], 73, &WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids, v3, v8);
      v13 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v3 )
    {
      if ( v13 == &WPP_GLOBAL_Control || (*((_DWORD *)v13 + 7) & 0x200) == 0 || *((_BYTE *)v13 + 25) < 2u )
        goto LABEL_25;
      v24 = 12;
LABEL_75:
      v25 = v3;
      goto LABEL_46;
    }
    EnterCriticalSection(&DnsInterfaceLock);
    for ( i = DnsInterfaceList; i != (struct _DNS_INTERFACE *)&DnsInterfaceList; i = *(struct _DNS_INTERFACE **)i )
    {
      v30 = *((_DWORD *)i + 42);
      if ( v8 )
      {
        if ( v30 == v8 )
          goto LABEL_20;
      }
      else if ( v30 )
      {
        goto LABEL_20;
      }
    }
    v3 = 1168;
LABEL_20:
    LeaveCriticalSection(&DnsInterfaceLock);
    if ( !v3 )
    {
      v3 = 52;
      goto LABEL_25;
    }
    EventW = CreateEventW(0, 0, 0, 0);
    v15 = EventW;
    v2 = EventW;
    if ( !EventW )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v28 = GetLastError();
        if ( v28 > 0 )
          v28 = (unsigned __int16)v28 | 0x80070000;
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_08734e8991f837002c8edb0c26290ae6_Traceguids,
          (unsigned int)v28);
      }
      goto LABEL_25;
    }
    LODWORD(v31) = 24;
    started = DnsRmStartProtocol(0, 0, &v33);
    v3 = started;
    if ( started )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_08734e8991f837002c8edb0c26290ae6_Traceguids, started);
      }
      v2 = EventW;
      goto LABEL_25;
    }
    v2 = EventW;
    if ( !EventW )
      V2NhpStopDnsEvent = v15;
    AvailableIndex = V2DnsFindAvailableIndex();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      LODWORD(v31) = 0;
      WPP_SF_dddddddd(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, v20, AvailableIndex);
    }
    if ( !AcquireComponentReference(&DnsComponentReference) )
    {
      v3 = 1003;
LABEL_93:
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_25;
      }
      v24 = 15;
      goto LABEL_75;
    }
    Interface = DnsCreateInterface(AvailableIndex, 0, 0, 0, v31);
    v3 = Interface;
    if ( Interface )
    {
      v22 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_37;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_36:
        if ( v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 0x10) != 0 && *((_BYTE *)v22 + 25) >= 6u )
          WPP_SF_d(v22[2], 59, &WPP_6532b2ce8588302729379dde0e1b157e_Traceguids, v3);
LABEL_37:
        ReleaseComponentReference((struct _COMPONENT_REFERENCE *)&DnsComponentReference);
        if ( !v3 )
        {
          v23 = DnsRmBindInterface(AvailableIndex, v12);
          v3 = v23;
          if ( v23 )
          {
            v13 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v24 = 16;
              goto LABEL_45;
            }
          }
          else
          {
            v23 = V2DnsSetIfIndex(AvailableIndex, v8, a1);
            v3 = v23;
            if ( v23 )
            {
              v13 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v24 = 17;
                goto LABEL_45;
              }
            }
            else
            {
              v23 = DnsRmEnableInterface(AvailableIndex);
              v3 = v23;
              if ( v23 )
              {
                v13 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v24 = 18;
LABEL_45:
                  v25 = v23;
LABEL_46:
                  WPP_SF_d(v13[2], v24, WPP_08734e8991f837002c8edb0c26290ae6_Traceguids, v25);
                }
              }
            }
          }
LABEL_25:
          if ( v12 )
          {
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, v12);
          }
          goto LABEL_3;
        }
        goto LABEL_93;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_6532b2ce8588302729379dde0e1b157e_Traceguids, Interface);
    }
    v22 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_36;
  }
LABEL_3:
  if ( v2 )
    CloseHandle(v2);
  return v3;
}

```

## disassembly

```asm
0x180026500  mov     r11, rsp
0x180026503  mov     [r11+10h], rbx
0x180026507  mov     [r11+18h], rbp
0x18002650b  push    rsi
0x18002650c  push    rdi
0x18002650d  push    r13
0x18002650f  push    r14
0x180026511  push    r15
0x180026513  sub     rsp, 90h
0x18002651a  mov     rax, cs:__security_cookie
0x180026521  xor     rax, rsp
0x180026524  mov     [rsp+0B8h+var_30], rax
0x18002652c  mov     r14d, 1
0x180026532  mov     r15, rcx
0x180026535  mov     [r11-48h], r14d
0x180026539  xor     edx, edx; lpDatabaseName
0x18002653b  mov     [r11-44h], r14d
0x18002653f  xor     ecx, ecx; lpMachineName
0x180026541  mov     r8d, 80000000h; dwDesiredAccess
0x180026547  mov     [rsp+0B8h+var_40], 3
0x18002654f  mov     [rsp+0B8h+var_3C], 2
0x180026557  xor     ebp, ebp
0x180026559  xor     ebx, ebx
0x18002655b  call    cs:__imp_OpenSCManagerW
0x180026562  nop     dword ptr [rax+rax+00h]
0x180026567  lea     r13, WPP_GLOBAL_Control
0x18002656e  mov     esi, 200h
0x180026573  test    rax, rax
0x180026576  jnz     short loc_1800265C0
0x180026578  mov     rcx, cs:WPP_GLOBAL_Control
0x18002657f  cmp     rcx, r13
0x180026582  jnz     loc_18002693B
0x180026588  test    rbp, rbp
0x18002658b  jnz     loc_180026C26
0x180026591  mov     eax, ebx
0x180026593  mov     rcx, [rsp+0B8h+var_30]
0x18002659b  xor     rcx, rsp; StackCookie
0x18002659e  call    __security_check_cookie
0x1800265a3  lea     r11, [rsp+0B8h+var_28]
0x1800265ab  mov     rbx, [r11+38h]
0x1800265af  mov     rbp, [r11+40h]
0x1800265b3  mov     rsp, r11
0x1800265b6  pop     r15
0x1800265b8  pop     r14
0x1800265ba  pop     r13
0x1800265bc  pop     rdi
0x1800265bd  pop     rsi
0x1800265be  retn
0x1800265c0  lea     rdx, aDns_1; "DNS"
0x1800265c7  mov     rcx, rax; hSCManager
0x1800265ca  call    ?NhpIsServiceRunningOrGoingToRun@@YAHPEAUSC_HANDLE__@@PEBG@Z; NhpIsServiceRunningOrGoingToRun(SC_HANDLE__ *,ushort const *)
0x1800265cf  xor     edi, edi
0x1800265d1  test    eax, eax
0x1800265d3  setz    dil
0x1800265d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800265de  cmp     rcx, r13
0x1800265e1  jnz     loc_18002695F
0x1800265e7  test    edi, edi
0x1800265e9  jz      short loc_180026588
0x1800265eb  cmp     rcx, r13
0x1800265ee  jnz     loc_180026745
0x1800265f4  movups  xmm0, xmmword ptr [r15]
0x1800265f8  lea     rcx, [rsp+0B8h+var_58]; struct _GUID
0x1800265fd  or      esi, 0FFFFFFFFh
0x180026600  movdqu  xmmword ptr [rsp+0B8h+var_58.Data1], xmm0
0x180026606  call    ?NatMapGuidToAdapter@@YAKU_GUID@@@Z; NatMapGuidToAdapter(_GUID)
0x18002660b  mov     edi, eax
0x18002660d  cmp     eax, esi
0x18002660f  jz      loc_180026897
0x180026615  mov     ecx, eax; unsigned int
0x180026617  call    ?NhQueryBindingInformation@@YAPEAUIP_ADAPTER_BINDING_INFO@@K@Z; NhQueryBindingInformation(ulong)
0x18002661c  mov     r14, rax
0x18002661f  test    rax, rax
0x180026622  jz      loc_1800269B6
0x180026628  mov     edx, [rax]; NumOfElements
0x18002662a  lea     rcx, [rax+18h]; Base
0x18002662e  lea     r9, ?NatCompareLocalBindings@@YAHPEBUIP_LOCAL_BINDING@@0@Z; CompareFunction
0x180026635  mov     r8d, 8; SizeOfElements
0x18002663b  call    cs:__imp_qsort
0x180026642  nop     dword ptr [rax+rax+00h]
0x180026647  mov     esi, edi
0x180026649  mov     rcx, cs:WPP_GLOBAL_Control
0x180026650  cmp     rcx, r13
0x180026653  jnz     loc_1800269E4
0x180026659  test    ebx, ebx
0x18002665b  jnz     loc_18002686D
0x180026661  lea     rcx, ?DnsInterfaceLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180026668  call    cs:__imp_EnterCriticalSection
0x18002666f  nop     dword ptr [rax+rax+00h]
0x180026674  mov     rax, cs:?DnsInterfaceList@@3U_LIST_ENTRY@@A; _LIST_ENTRY DnsInterfaceList
0x18002667b  lea     rcx, ?DnsInterfaceList@@3U_LIST_ENTRY@@A; _LIST_ENTRY DnsInterfaceList
0x180026682  cmp     rax, rcx
0x180026685  jnz     loc_180026A30
0x18002668b  mov     ebx, 490h
0x180026690  lea     rcx, ?DnsInterfaceLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180026697  call    cs:__imp_LeaveCriticalSection
0x18002669e  nop     dword ptr [rax+rax+00h]
0x1800266a3  test    ebx, ebx
0x1800266a5  jz      loc_180026A54
0x1800266ab  xor     r9d, r9d; lpName
0x1800266ae  xor     r8d, r8d; bInitialState
0x1800266b1  xor     edx, edx; bManualReset
0x1800266b3  xor     ecx, ecx; lpEventAttributes
0x1800266b5  call    cs:__imp_CreateEventW
0x1800266bc  nop     dword ptr [rax+rax+00h]
0x1800266c1  mov     [rsp+0B8h+var_38], rax
0x1800266c9  mov     rdi, rax
0x1800266cc  mov     rbp, rax
0x1800266cf  test    rax, rax
0x1800266d2  jz      loc_180026A5E
0x1800266d8  mov     r9d, 1; unsigned int
0x1800266de  lea     r8, [rsp+0B8h+var_48]; void *
0x1800266e3  mov     [rsp+0B8h+var_90], r9d; unsigned int
0x1800266e8  xor     edx, edx; struct _SUPPORT_FUNCTIONS_50 *
0x1800266ea  xor     ecx, ecx; void *
0x1800266ec  mov     dword ptr [rsp+0B8h+var_98], 18h; unsigned int
0x1800266f4  call    ?DnsRmStartProtocol@@YAKPEAXPEAU_SUPPORT_FUNCTIONS_50@@0KKK@Z; DnsRmStartProtocol(void *,_SUPPORT_FUNCTIONS_50 *,void *,ulong,ulong,ulong)
0x1800266f9  mov     ebx, eax
0x1800266fb  test    eax, eax
0x1800266fd  jz      short loc_180026772
0x1800266ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180026706  cmp     rcx, r13
0x180026709  jnz     loc_180026A97
0x18002670f  mov     rbp, [rsp+0B8h+var_38]
0x180026717  test    r14, r14
0x18002671a  jz      loc_180026588
0x180026720  call    cs:__imp_GetProcessHeap
0x180026727  nop     dword ptr [rax+rax+00h]
0x18002672c  mov     r8, r14; lpMem
0x18002672f  xor     edx, edx; dwFlags
0x180026731  mov     rcx, rax; hHeap
0x180026734  call    cs:__imp_HeapFree
0x18002673b  nop     dword ptr [rax+rax+00h]
0x180026740  jmp     loc_180026588
0x180026745  test    [rcx+1Ch], esi
0x180026748  jz      loc_1800265F4
0x18002674e  cmp     byte ptr [rcx+19h], 6
0x180026752  jb      loc_1800265F4
0x180026758  mov     rcx, [rcx+10h]
0x18002675c  lea     r8, WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids
0x180026763  mov     edx, 46h ; 'F'
0x180026768  call    WPP_SF_
0x18002676d  jmp     loc_1800265F4
0x180026772  mov     rbp, [rsp+0B8h+var_38]
0x18002677a  test    rbp, rbp
0x18002677d  jnz     short loc_180026786
0x18002677f  mov     cs:?V2NhpStopDnsEvent@@3PEAXEA, rdi; void * V2NhpStopDnsEvent
0x180026786  call    ?V2DnsFindAvailableIndex@@YAKXZ; V2DnsFindAvailableIndex(void)
0x18002678b  mov     edi, eax
0x18002678d  mov     rcx, cs:WPP_GLOBAL_Control
0x180026794  cmp     rcx, r13
0x180026797  jnz     loc_180026ACB
0x18002679d  lea     rcx, ?DnsComponentReference@@3U_COMPONENT_REFERENCE@@A; lpCriticalSection
0x1800267a4  call    ?AcquireComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; AcquireComponentReference(_COMPONENT_REFERENCE *)
0x1800267a9  test    al, al
0x1800267ab  jz      loc_180026B21
0x1800267b1  xor     r9d, r9d
0x1800267b4  xor     r8d, r8d
0x1800267b7  xor     edx, edx
0x1800267b9  mov     ecx, edi
0x1800267bb  call    ?DnsCreateInterface@@YAKKW4_eIPProtocol@@W4_NET_INTERFACE_TYPE@@PEAU_IP_DNS_PROXY_INTERFACE_INFO@@PEAPEAU_DNS_INTERFACE@@@Z; DnsCreateInterface(ulong,_eIPProtocol,_NET_INTERFACE_TYPE,_IP_DNS_PROXY_INTERFACE_INFO *,_DNS_INTERFACE * *)
0x1800267c0  mov     ebx, eax
0x1800267c2  test    eax, eax
0x1800267c4  jnz     loc_180026B52
0x1800267ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800267d1  cmp     rcx, r13
0x1800267d4  jnz     loc_180026B93
0x1800267da  lea     rcx, ?DnsComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x1800267e1  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x1800267e6  test    ebx, ebx
0x1800267e8  jnz     loc_180026B26
0x1800267ee  mov     rdx, r14; void *
0x1800267f1  mov     ecx, edi; unsigned int
0x1800267f3  call    ?DnsRmBindInterface@@YAKKPEAX@Z; DnsRmBindInterface(ulong,void *)
0x1800267f8  mov     ebx, eax
0x1800267fa  test    eax, eax
0x1800267fc  jnz     loc_180026BC4
0x180026802  mov     r8, r15; struct _GUID *
0x180026805  mov     edx, esi; unsigned int
0x180026807  mov     ecx, edi; unsigned int
0x180026809  call    ?V2DnsSetIfIndex@@YAKKKPEBU_GUID@@@Z; V2DnsSetIfIndex(ulong,ulong,_GUID const *)
0x18002680e  mov     ebx, eax
0x180026810  test    eax, eax
0x180026812  jnz     loc_180026BF5
0x180026818  mov     ecx, edi; unsigned int
0x18002681a  call    ?DnsRmEnableInterface@@YAKK@Z; DnsRmEnableInterface(ulong)
0x18002681f  mov     ebx, eax
0x180026821  test    eax, eax
0x180026823  jz      loc_180026717
0x180026829  mov     rcx, cs:WPP_GLOBAL_Control
0x180026830  cmp     rcx, r13
0x180026833  jz      loc_180026717
0x180026839  test    dword ptr [rcx+1Ch], 200h
0x180026840  jz      loc_180026717
0x180026846  cmp     byte ptr [rcx+19h], 2
0x18002684a  jb      loc_180026717
0x180026850  mov     edx, 12h
0x180026855  mov     r9d, eax
0x180026858  mov     rcx, [rcx+10h]
0x18002685c  lea     r8, WPP_08734e8991f837002c8edb0c26290ae6_Traceguids
0x180026863  call    WPP_SF_d
0x180026868  jmp     loc_180026717
0x18002686d  cmp     rcx, r13
0x180026870  jz      loc_180026717
0x180026876  test    dword ptr [rcx+1Ch], 200h
0x18002687d  jz      loc_180026717
0x180026883  cmp     byte ptr [rcx+19h], 2
0x180026887  jb      loc_180026717
0x18002688d  mov     edx, 0Ch
0x180026892  jmp     loc_180026A28
0x180026897  xor     r14d, r14d
0x18002689a  mov     ebx, 389h
0x18002689f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800268a6  cmp     rcx, r13
0x1800268a9  jz      loc_180026717
0x1800268af  test    dword ptr [rcx+1Ch], 200h
0x1800268b6  jz      loc_180026650
0x1800268bc  cmp     byte ptr [rcx+19h], 2
0x1800268c0  jb      loc_180026650
0x1800268c6  lea     edx, [r14+47h]
0x1800268ca  jmp     loc_18002699E
0x1800268cf  call    cs:__imp_GetLastError
0x1800268d6  nop     dword ptr [rax+rax+00h]
0x1800268db  test    eax, eax
0x1800268dd  jg      short loc_180026955
0x1800268df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800268e6  lea     r8, WPP_08734e8991f837002c8edb0c26290ae6_Traceguids
0x1800268ed  mov     edx, 0Ah
0x1800268f2  mov     r9d, eax
0x1800268f5  mov     rcx, [rcx+10h]
0x1800268f9  call    WPP_SF_d
0x1800268fe  jmp     loc_1800265D7
0x180026903  call    cs:__imp_GetLastError
0x18002690a  nop     dword ptr [rax+rax+00h]
0x18002690f  test    eax, eax
0x180026911  jg      loc_180026A8A
0x180026917  mov     rcx, cs:WPP_GLOBAL_Control
0x18002691e  lea     r8, WPP_08734e8991f837002c8edb0c26290ae6_Traceguids
0x180026925  mov     edx, 0Dh
0x18002692a  mov     r9d, eax
0x18002692d  mov     rcx, [rcx+10h]
0x180026931  call    WPP_SF_d
0x180026936  jmp     loc_180026717
0x18002693b  xor     edi, edi
0x18002693d  test    [rcx+1Ch], esi
0x180026940  jz      loc_1800265DE
0x180026946  cmp     byte ptr [rcx+19h], 3
0x18002694a  jb      loc_1800265DE
0x180026950  jmp     loc_1800268CF
0x180026955  movzx   eax, ax
0x180026958  or      eax, 80070000h
0x18002695d  jmp     short loc_1800268DF
0x18002695f  test    [rcx+1Ch], esi
0x180026962  jz      loc_1800265E7
0x180026968  cmp     byte ptr [rcx+19h], 5
0x18002696c  jb      loc_1800265E7
0x180026972  mov     rcx, [rcx+10h]
0x180026976  lea     r8, WPP_08734e8991f837002c8edb0c26290ae6_Traceguids
0x18002697d  mov     r9d, edi
0x180026980  mov     edx, 0Bh
0x180026985  xor     r9b, r14b
0x180026988  call    WPP_SF_c
0x18002698d  mov     rcx, cs:WPP_GLOBAL_Control
0x180026994  jmp     loc_1800265E7
0x180026999  mov     edx, 48h ; 'H'
0x18002699e  mov     rcx, [rcx+10h]
0x1800269a2  lea     r8, WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids
0x1800269a9  mov     r9d, ebx
0x1800269ac  call    WPP_SF_d
0x1800269b1  jmp     loc_180026649
0x1800269b6  mov     ebx, 8
0x1800269bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800269c2  cmp     rcx, r13
0x1800269c5  jz      loc_180026717
0x1800269cb  test    dword ptr [rcx+1Ch], 200h
0x1800269d2  jz      loc_180026650
0x1800269d8  cmp     byte ptr [rcx+19h], 2
0x1800269dc  jb      loc_180026650
0x1800269e2  jmp     short loc_180026999
0x1800269e4  test    dword ptr [rcx+1Ch], 200h
0x1800269eb  jz      loc_180026659
0x1800269f1  cmp     byte ptr [rcx+19h], 6
0x1800269f5  jb      loc_180026659
0x1800269fb  mov     rcx, [rcx+10h]
0x1800269ff  lea     r8, WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids
0x180026a06  mov     edx, 49h ; 'I'
0x180026a0b  mov     dword ptr [rsp+0B8h+var_98], esi
0x180026a0f  mov     r9d, ebx
0x180026a12  call    WPP_SF_Dd
0x180026a17  mov     rcx, cs:WPP_GLOBAL_Control
0x180026a1e  jmp     loc_180026659
0x180026a23  mov     edx, 0Fh
0x180026a28  mov     r9d, ebx
0x180026a2b  jmp     loc_180026858
0x180026a30  mov     ecx, [rax+0A8h]
0x180026a36  test    esi, esi
0x180026a38  jnz     short loc_180026A44
0x180026a3a  test    ecx, ecx
0x180026a3c  jnz     loc_180026690
0x180026a42  jmp     short loc_180026A4C
  ... truncated ...
```
