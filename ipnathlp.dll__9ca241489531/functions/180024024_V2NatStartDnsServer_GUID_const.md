# V2NatStartDnsServer(_GUID const *)

- ea: `0x180024024`
- end: `0x18002471e`
- name: `?V2NatStartDnsServer@@YAKPEBU_GUID@@@Z`
- size: `1786`
- prototype: `unsigned int __fastcall(const struct _GUID *)`
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x180023420`

## callees

- `0x18000b900`
- `0x18000bad0`
- `0x18000c110`
- `0x18000c750`
- `0x18000fe58`
- `0x18001ec08`
- `0x180024024`
- `0x180024730`
- `0x180024900`
- `0x180024c90`
- `0x180025898`
- `0x180025984`
- `0x180025a80`
- `0x18004215c`
- `0x180043a7c`
- `0x18004b358`
- `0x18004e0c0`
- `0x180061818`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x180024158`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x180024158`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024225`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024225`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024233`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024233`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002417f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002417f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800241a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800241a8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800241c0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800241c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800243c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800243f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800243c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800243f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024713`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024713`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002407f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002407f`

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
  _DWORD v33[4]; // [rsp+70h] [rbp-48h] BYREF
  HANDLE EventW; // [rsp+80h] [rbp-38h]

  v33[0] = 1;
  v33[1] = 1;
  v33[2] = 3;
  v33[3] = 2;
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
    started = DnsRmStartProtocol(0, 0, v33, 1u, 0x18u, 1u);
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
0x180024024  mov     r11, rsp
0x180024027  mov     [r11+10h], rbx
0x18002402b  mov     [r11+18h], rbp
0x18002402f  push    rsi
0x180024030  push    rdi
0x180024031  push    r13
0x180024033  push    r14
0x180024035  push    r15
0x180024037  sub     rsp, 90h
0x18002403e  mov     rax, cs:__security_cookie
0x180024045  xor     rax, rsp
0x180024048  mov     [rsp+0B8h+var_30], rax
0x180024050  mov     r14d, 1
0x180024056  mov     r15, rcx
0x180024059  mov     [r11-48h], r14d
0x18002405d  xor     edx, edx; lpDatabaseName
0x18002405f  mov     [r11-44h], r14d
0x180024063  xor     ecx, ecx; lpMachineName
0x180024065  mov     r8d, 80000000h; dwDesiredAccess
0x18002406b  mov     [rsp+0B8h+var_40], 3
0x180024073  mov     [rsp+0B8h+var_3C], 2
0x18002407b  xor     ebp, ebp
0x18002407d  xor     ebx, ebx
0x18002407f  call    cs:__imp_OpenSCManagerW
0x180024085  lea     r13, WPP_GLOBAL_Control
0x18002408c  mov     esi, 200h
0x180024091  test    rax, rax
0x180024094  jnz     short loc_1800240DD
0x180024096  mov     rcx, cs:WPP_GLOBAL_Control
0x18002409d  cmp     rcx, r13
0x1800240a0  jnz     loc_180024428
0x1800240a6  test    rbp, rbp
0x1800240a9  jnz     loc_180024710
0x1800240af  mov     eax, ebx
0x1800240b1  mov     rcx, [rsp+0B8h+var_30]
0x1800240b9  xor     rcx, rsp; StackCookie
0x1800240bc  call    __security_check_cookie
0x1800240c1  lea     r11, [rsp+0B8h+var_28]
0x1800240c9  mov     rbx, [r11+38h]
0x1800240cd  mov     rbp, [r11+40h]
0x1800240d1  mov     rsp, r11
0x1800240d4  pop     r15
0x1800240d6  pop     r14
0x1800240d8  pop     r13
0x1800240da  pop     rdi
0x1800240db  pop     rsi
0x1800240dc  retn
0x1800240dd  lea     rdx, aDns_1; "DNS"
0x1800240e4  mov     rcx, rax; hSCManager
0x1800240e7  call    ?NhpIsServiceRunningOrGoingToRun@@YAHPEAUSC_HANDLE__@@PEBG@Z; NhpIsServiceRunningOrGoingToRun(SC_HANDLE__ *,ushort const *)
0x1800240ec  xor     edi, edi
0x1800240ee  test    eax, eax
0x1800240f0  setz    dil
0x1800240f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800240fb  cmp     rcx, r13
0x1800240fe  jnz     loc_180024449
0x180024104  test    edi, edi
0x180024106  jz      short loc_1800240A6
0x180024108  cmp     rcx, r13
0x18002410b  jnz     loc_18002423E
0x180024111  movups  xmm0, xmmword ptr [r15]
0x180024115  lea     rcx, [rsp+0B8h+var_58]; struct _GUID
0x18002411a  or      esi, 0FFFFFFFFh
0x18002411d  movdqu  xmmword ptr [rsp+0B8h+var_58.Data1], xmm0
0x180024123  call    ?NatMapGuidToAdapter@@YAKU_GUID@@@Z; NatMapGuidToAdapter(_GUID)
0x180024128  mov     edi, eax
0x18002412a  cmp     eax, esi
0x18002412c  jz      loc_180024390
0x180024132  mov     ecx, eax; unsigned int
0x180024134  call    ?NhQueryBindingInformation@@YAPEAUIP_ADAPTER_BINDING_INFO@@K@Z; NhQueryBindingInformation(ulong)
0x180024139  mov     r14, rax
0x18002413c  test    rax, rax
0x18002413f  jz      loc_1800244A0
0x180024145  mov     edx, [rax]; NumOfElements
0x180024147  lea     rcx, [rax+18h]; Base
0x18002414b  lea     r9, ?NatCompareLocalBindings@@YAHPEBUIP_LOCAL_BINDING@@0@Z; CompareFunction
0x180024152  mov     r8d, 8; SizeOfElements
0x180024158  call    cs:__imp_qsort
0x18002415e  mov     esi, edi
0x180024160  mov     rcx, cs:WPP_GLOBAL_Control
0x180024167  cmp     rcx, r13
0x18002416a  jnz     loc_1800244CE
0x180024170  test    ebx, ebx
0x180024172  jnz     loc_180024366
0x180024178  lea     rcx, ?DnsInterfaceLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002417f  call    cs:__imp_EnterCriticalSection
0x180024185  mov     rax, cs:?DnsInterfaceList@@3U_LIST_ENTRY@@A; _LIST_ENTRY DnsInterfaceList
0x18002418c  lea     rcx, ?DnsInterfaceList@@3U_LIST_ENTRY@@A; _LIST_ENTRY DnsInterfaceList
0x180024193  cmp     rax, rcx
0x180024196  jnz     loc_18002451A
0x18002419c  mov     ebx, 490h
0x1800241a1  lea     rcx, ?DnsInterfaceLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800241a8  call    cs:__imp_LeaveCriticalSection
0x1800241ae  test    ebx, ebx
0x1800241b0  jz      loc_18002453E
0x1800241b6  xor     r9d, r9d; lpName
0x1800241b9  xor     r8d, r8d; bInitialState
0x1800241bc  xor     edx, edx; bManualReset
0x1800241be  xor     ecx, ecx; lpEventAttributes
0x1800241c0  call    cs:__imp_CreateEventW
0x1800241c6  mov     [rsp+0B8h+var_38], rax
0x1800241ce  mov     rdi, rax
0x1800241d1  mov     rbp, rax
0x1800241d4  test    rax, rax
0x1800241d7  jz      loc_180024548
0x1800241dd  mov     r9d, 1; unsigned int
0x1800241e3  lea     r8, [rsp+0B8h+var_48]; void *
0x1800241e8  mov     [rsp+0B8h+var_90], r9d; unsigned int
0x1800241ed  xor     edx, edx; struct _SUPPORT_FUNCTIONS_50 *
0x1800241ef  xor     ecx, ecx; void *
0x1800241f1  mov     dword ptr [rsp+0B8h+var_98], 18h; unsigned int
0x1800241f9  call    ?DnsRmStartProtocol@@YAKPEAXPEAU_SUPPORT_FUNCTIONS_50@@0KKK@Z; DnsRmStartProtocol(void *,_SUPPORT_FUNCTIONS_50 *,void *,ulong,ulong,ulong)
0x1800241fe  mov     ebx, eax
0x180024200  test    eax, eax
0x180024202  jz      short loc_18002426B
0x180024204  mov     rcx, cs:WPP_GLOBAL_Control
0x18002420b  cmp     rcx, r13
0x18002420e  jnz     loc_180024581
0x180024214  mov     rbp, [rsp+0B8h+var_38]
0x18002421c  test    r14, r14
0x18002421f  jz      loc_1800240A6
0x180024225  call    cs:__imp_GetProcessHeap
0x18002422b  mov     r8, r14; lpMem
0x18002422e  xor     edx, edx; dwFlags
0x180024230  mov     rcx, rax; hHeap
0x180024233  call    cs:__imp_HeapFree
0x180024239  jmp     loc_1800240A6
0x18002423e  test    [rcx+1Ch], esi
0x180024241  jz      loc_180024111
0x180024247  cmp     byte ptr [rcx+19h], 6
0x18002424b  jb      loc_180024111
0x180024251  mov     rcx, [rcx+10h]
0x180024255  lea     r8, WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids
0x18002425c  mov     edx, 46h ; 'F'
0x180024261  call    WPP_SF_
0x180024266  jmp     loc_180024111
0x18002426b  mov     rbp, [rsp+0B8h+var_38]
0x180024273  test    rbp, rbp
0x180024276  jnz     short loc_18002427F
0x180024278  mov     cs:?V2NhpStopDnsEvent@@3PEAXEA, rdi; void * V2NhpStopDnsEvent
0x18002427f  call    ?V2DnsFindAvailableIndex@@YAKXZ; V2DnsFindAvailableIndex(void)
0x180024284  mov     edi, eax
0x180024286  mov     rcx, cs:WPP_GLOBAL_Control
0x18002428d  cmp     rcx, r13
0x180024290  jnz     loc_1800245B5
0x180024296  lea     rcx, ?DnsComponentReference@@3U_COMPONENT_REFERENCE@@A; lpCriticalSection
0x18002429d  call    ?AcquireComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; AcquireComponentReference(_COMPONENT_REFERENCE *)
0x1800242a2  test    al, al
0x1800242a4  jz      loc_18002460B
0x1800242aa  xor     r9d, r9d
0x1800242ad  xor     r8d, r8d
0x1800242b0  xor     edx, edx
0x1800242b2  mov     ecx, edi
0x1800242b4  call    ?DnsCreateInterface@@YAKKW4_eIPProtocol@@W4_NET_INTERFACE_TYPE@@PEAU_IP_DNS_PROXY_INTERFACE_INFO@@PEAPEAU_DNS_INTERFACE@@@Z; DnsCreateInterface(ulong,_eIPProtocol,_NET_INTERFACE_TYPE,_IP_DNS_PROXY_INTERFACE_INFO *,_DNS_INTERFACE * *)
0x1800242b9  mov     ebx, eax
0x1800242bb  test    eax, eax
0x1800242bd  jnz     loc_18002463C
0x1800242c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800242ca  cmp     rcx, r13
0x1800242cd  jnz     loc_18002467D
0x1800242d3  lea     rcx, ?DnsComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x1800242da  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x1800242df  test    ebx, ebx
0x1800242e1  jnz     loc_180024610
0x1800242e7  mov     rdx, r14; void *
0x1800242ea  mov     ecx, edi; unsigned int
0x1800242ec  call    ?DnsRmBindInterface@@YAKKPEAX@Z; DnsRmBindInterface(ulong,void *)
0x1800242f1  mov     ebx, eax
0x1800242f3  test    eax, eax
0x1800242f5  jnz     loc_1800246AE
0x1800242fb  mov     r8, r15; struct _GUID *
0x1800242fe  mov     edx, esi; unsigned int
0x180024300  mov     ecx, edi; unsigned int
0x180024302  call    ?V2DnsSetIfIndex@@YAKKKPEBU_GUID@@@Z; V2DnsSetIfIndex(ulong,ulong,_GUID const *)
0x180024307  mov     ebx, eax
0x180024309  test    eax, eax
0x18002430b  jnz     loc_1800246DF
0x180024311  mov     ecx, edi; unsigned int
0x180024313  call    ?DnsRmEnableInterface@@YAKK@Z; DnsRmEnableInterface(ulong)
0x180024318  mov     ebx, eax
0x18002431a  test    eax, eax
0x18002431c  jz      loc_18002421C
0x180024322  mov     rcx, cs:WPP_GLOBAL_Control
0x180024329  cmp     rcx, r13
0x18002432c  jz      loc_18002421C
0x180024332  test    dword ptr [rcx+1Ch], 200h
0x180024339  jz      loc_18002421C
0x18002433f  cmp     byte ptr [rcx+19h], 2
0x180024343  jb      loc_18002421C
0x180024349  mov     edx, 12h
0x18002434e  mov     r9d, eax
0x180024351  mov     rcx, [rcx+10h]
0x180024355  lea     r8, WPP_08734e8991f837002c8edb0c26290ae6_Traceguids
0x18002435c  call    WPP_SF_d
0x180024361  jmp     loc_18002421C
0x180024366  cmp     rcx, r13
0x180024369  jz      loc_18002421C
0x18002436f  test    dword ptr [rcx+1Ch], 200h
0x180024376  jz      loc_18002421C
0x18002437c  cmp     byte ptr [rcx+19h], 2
0x180024380  jb      loc_18002421C
0x180024386  mov     edx, 0Ch
0x18002438b  jmp     loc_180024512
0x180024390  xor     r14d, r14d
0x180024393  mov     ebx, 389h
0x180024398  mov     rcx, cs:WPP_GLOBAL_Control
0x18002439f  cmp     rcx, r13
0x1800243a2  jz      loc_18002421C
0x1800243a8  test    dword ptr [rcx+1Ch], 200h
0x1800243af  jz      loc_180024167
0x1800243b5  cmp     byte ptr [rcx+19h], 2
0x1800243b9  jb      loc_180024167
0x1800243bf  lea     edx, [r14+47h]
0x1800243c3  jmp     loc_180024488
0x1800243c8  call    cs:__imp_GetLastError
0x1800243ce  test    eax, eax
0x1800243d0  jg      short loc_18002443F
0x1800243d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800243d9  lea     r8, WPP_08734e8991f837002c8edb0c26290ae6_Traceguids
0x1800243e0  mov     edx, 0Ah
0x1800243e5  mov     r9d, eax
0x1800243e8  mov     rcx, [rcx+10h]
0x1800243ec  call    WPP_SF_d
0x1800243f1  jmp     loc_1800240F4
0x1800243f6  call    cs:__imp_GetLastError
0x1800243fc  test    eax, eax
0x1800243fe  jg      loc_180024574
0x180024404  mov     rcx, cs:WPP_GLOBAL_Control
0x18002440b  lea     r8, WPP_08734e8991f837002c8edb0c26290ae6_Traceguids
0x180024412  mov     edx, 0Dh
0x180024417  mov     r9d, eax
0x18002441a  mov     rcx, [rcx+10h]
0x18002441e  call    WPP_SF_d
0x180024423  jmp     loc_18002421C
0x180024428  xor     edi, edi
0x18002442a  test    [rcx+1Ch], esi
0x18002442d  jz      loc_1800240FB
0x180024433  cmp     byte ptr [rcx+19h], 3
0x180024437  jb      loc_1800240FB
0x18002443d  jmp     short loc_1800243C8
0x18002443f  movzx   eax, ax
0x180024442  or      eax, 80070000h
0x180024447  jmp     short loc_1800243D2
0x180024449  test    [rcx+1Ch], esi
0x18002444c  jz      loc_180024104
0x180024452  cmp     byte ptr [rcx+19h], 5
0x180024456  jb      loc_180024104
0x18002445c  mov     rcx, [rcx+10h]
0x180024460  lea     r8, WPP_08734e8991f837002c8edb0c26290ae6_Traceguids
0x180024467  mov     r9d, edi
0x18002446a  mov     edx, 0Bh
0x18002446f  xor     r9b, r14b
0x180024472  call    WPP_SF_c
0x180024477  mov     rcx, cs:WPP_GLOBAL_Control
0x18002447e  jmp     loc_180024104
0x180024483  mov     edx, 48h ; 'H'
0x180024488  mov     rcx, [rcx+10h]
0x18002448c  lea     r8, WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids
0x180024493  mov     r9d, ebx
0x180024496  call    WPP_SF_d
0x18002449b  jmp     loc_180024160
0x1800244a0  mov     ebx, 8
0x1800244a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800244ac  cmp     rcx, r13
0x1800244af  jz      loc_18002421C
0x1800244b5  test    dword ptr [rcx+1Ch], 200h
0x1800244bc  jz      loc_180024167
0x1800244c2  cmp     byte ptr [rcx+19h], 2
0x1800244c6  jb      loc_180024167
0x1800244cc  jmp     short loc_180024483
0x1800244ce  test    dword ptr [rcx+1Ch], 200h
0x1800244d5  jz      loc_180024170
0x1800244db  cmp     byte ptr [rcx+19h], 6
0x1800244df  jb      loc_180024170
0x1800244e5  mov     rcx, [rcx+10h]
0x1800244e9  lea     r8, WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids
0x1800244f0  mov     edx, 49h ; 'I'
0x1800244f5  mov     dword ptr [rsp+0B8h+var_98], esi
0x1800244f9  mov     r9d, ebx
0x1800244fc  call    WPP_SF_Dd
0x180024501  mov     rcx, cs:WPP_GLOBAL_Control
0x180024508  jmp     loc_180024170
0x18002450d  mov     edx, 0Fh
0x180024512  mov     r9d, ebx
0x180024515  jmp     loc_180024351
0x18002451a  mov     ecx, [rax+0A8h]
0x180024520  test    esi, esi
0x180024522  jnz     short loc_18002452E
0x180024524  test    ecx, ecx
0x180024526  jnz     loc_1800241A1
0x18002452c  jmp     short loc_180024536
0x18002452e  cmp     ecx, esi
0x180024530  jz      loc_1800241A1
0x180024536  mov     rax, [rax]
0x180024539  jmp     loc_18002418C
0x18002453e  mov     ebx, 34h ; '4'
0x180024543  jmp     loc_18002421C
0x180024548  mov     rax, cs:WPP_GLOBAL_Control
0x18002454f  cmp     rax, r13
0x180024552  jz      loc_18002421C
  ... truncated ...
```
