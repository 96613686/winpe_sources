# WanConnectionManager::RasEvent(ushort * const)

- ea: `0x180020790`
- end: `0x180020da8`
- name: `?RasEvent@WanConnectionManager@@UEAAJQEAG@Z`
- size: `1560`
- prototype: `int(WanConnectionManager *__hidden this, unsigned __int16 *const)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180002320`
- `0x1800052b4`
- `0x18000538c`
- `0x180014894`
- `0x180019200`
- `0x180019c68`
- `0x18001ade4`
- `0x18001e014`
- `0x18001f920`
- `0x180020224`
- `0x1800206c4`
- `0x180020790`
- `0x180023950`
- `0x180023a18`
- `0x1800318b0`
- `0x180032bac`
- `0x180034e08`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800209f9`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800209f9`
- `KERNEL32!GetLastError` at `0x180020d0a`
- `KERNEL32!GetLastError` at `0x180020d78`
- `KERNEL32!GetLastError` at `0x180020d0a`
- `KERNEL32!GetLastError` at `0x180020d78`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800207d5`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800207d5`
- `RASDLG!RasSrvAllowConnectionsConfig` at `0x180020b77`
- `RASDLG!RasSrvAllowConnectionsConfig` at `0x180020b77`

## pseudocode

```c
__int64 __fastcall WanConnectionManager::RasEvent(WanConnectionManager *this, unsigned __int16 *const a2)
{
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  enum tagNETCON_STATUS v8; // ebx
  CMUtil *v9; // rax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  _DWORD *v13; // rax
  _DWORD *v14; // rbx
  __int64 v15; // rcx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  bool v20; // zf
  __int128 v21; // xmm0
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  __int128 v26; // xmm0
  __int128 v27; // xmm0
  __int128 v28; // xmm0
  int v29; // eax
  __int64 v30; // r9
  __int128 v31; // xmm0
  __int128 v32; // xmm0
  __int128 v33; // xmm0
  __int128 v34; // xmm0
  const char *v35; // rax
  DWORD LastError; // eax
  __int64 v37; // rdx
  const char *v38; // rax
  __int64 v39; // [rsp+20h] [rbp-38h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_d31d59df70993a9dd4981e83321196c3_Traceguids);
  if ( SysStringByteLen(a2) != 3680 )
    return 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      WPP_d31d59df70993a9dd4981e83321196c3_Traceguids,
      *(unsigned int *)a2);
  if ( ServiceStatus.dwCurrentState != 4 )
    return 1;
  v3 = *(_DWORD *)a2;
  if ( *(int *)a2 > 1024 )
  {
    if ( v3 != 2048 )
    {
      switch ( v3 )
      {
        case 0x100000:
          v8 = NCS_ACTION_REQUIRED;
          break;
        case 0x200000:
          v8 = NCS_ACTION_REQUIRED_RETRY;
          break;
        case 0x400000:
          v8 = NCS_CONNECT_FAILED;
          break;
        default:
          goto LABEL_18;
      }
      goto LABEL_17;
    }
    goto LABEL_16;
  }
  if ( v3 == 1024 )
    goto LABEL_16;
  v4 = v3 - 16;
  if ( !v4 )
    goto LABEL_16;
  v5 = v4 - 16;
  if ( !v5 )
  {
    v8 = NCS_CONNECTING;
    goto LABEL_17;
  }
  v6 = v5 - 32;
  if ( !v6 )
  {
    v8 = NCS_DISCONNECTING;
    goto LABEL_17;
  }
  v7 = v6 - 64;
  if ( !v7 )
  {
    v8 = NCS_DISCONNECTED;
    goto LABEL_17;
  }
  if ( v7 == 384 )
  {
LABEL_16:
    v8 = NCS_CONNECTED;
LABEL_17:
    v9 = CMUtil::Instance();
    CMUtil::SetEntry(v9, (const struct _GUID *)(a2 + 10), a2 + 152, v8);
  }
LABEL_18:
  if ( !(unsigned int)ConnectionManager::FHasActiveConnectionPoints()
    || ((*(_DWORD *)a2 - 0x8000) & 0xFFFF7FFF) == 0 && !g_fHandleIncomingEvents )
  {
    return 1;
  }
  if ( (unsigned int)(*(_DWORD *)a2 - 1) <= 1 && (unsigned int)FIsIgnorableCMEvent((const struct _RASEVENT *)a2) )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      return 1;
    v11 = 14;
LABEL_26:
    WPP_SF_(v10[2], v11, WPP_d31d59df70993a9dd4981e83321196c3_Traceguids);
    return 1;
  }
  v13 = MemAlloc(0xE68u);
  v14 = v13;
  if ( !v13 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      return 1;
    v11 = 15;
    goto LABEL_26;
  }
  memset_0(v13, 0, 0xE68u);
  *v14 = 1;
  v14[2] = 3;
  v15 = *(unsigned int *)a2;
  if ( (int)v15 > 2048 )
  {
    if ( (int)v15 > 0x40000 )
    {
      if ( (_DWORD)v15 != 0x80000 )
      {
        switch ( (_DWORD)v15 )
        {
          case 0x100000:
            v14[1] = 6;
            v34 = *(_OWORD *)(a2 + 10);
            v14[8] = 13;
            *((_OWORD *)v14 + 1) = v34;
            break;
          case 0x200000:
            v14[1] = 6;
            v33 = *(_OWORD *)(a2 + 10);
            v14[8] = 14;
            *((_OWORD *)v14 + 1) = v33;
            break;
          case 0x400000:
            v14[1] = 6;
            v32 = *(_OWORD *)(a2 + 10);
            v14[8] = 15;
            *((_OWORD *)v14 + 1) = v32;
            break;
          default:
            goto LABEL_112;
        }
        goto LABEL_95;
      }
    }
    else if ( (_DWORD)v15 != 0x40000 )
    {
      if ( (((_DWORD)v15 - 0x2000) & 0xFFFFDFFF) != 0 )
      {
        switch ( (_DWORD)v15 )
        {
          case 0x8000:
            v14[2] = 1;
            *((_QWORD *)v14 + 4) = *((_QWORD *)a2 + 1);
            *((_OWORD *)v14 + 1) = *(_OWORD *)(a2 + 10);
            v14[10] = RasSrvTypeFromRasDeviceType(*((unsigned int *)a2 + 4));
            v14[1] = 1;
            break;
          case 0x10000:
            v14[2] = 1;
            v31 = *(_OWORD *)(a2 + 10);
            v14[1] = 3;
            *((_OWORD *)v14 + 1) = v31;
            break;
          case 0x20000:
            if ( *((_DWORD *)a2 + 3) != 2 )
            {
              if ( !*((_DWORD *)a2 + 2) )
                ServiceModule::ReferenceRasman(v15, 1);
              goto LABEL_112;
            }
            v14[2] = 1;
            v14[1] = 7;
            v29 = RasSrvAllowConnectionsConfig(&g_fHandleIncomingEvents);
            v30 = (unsigned int)v29;
            if ( v29 > 0 )
              v30 = (unsigned __int16)v29 | 0x80070000;
            if ( (int)v30 < 0
              && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_d31d59df70993a9dd4981e83321196c3_Traceguids, v30);
            }
            break;
          default:
            goto LABEL_112;
        }
        goto LABEL_95;
      }
      v14[1] = 2;
      goto LABEL_54;
    }
    v14[1] = 7;
    goto LABEL_95;
  }
  if ( (_DWORD)v15 == 2048 )
  {
LABEL_65:
    v14[1] = 6;
    v26 = *(_OWORD *)(a2 + 10);
    v14[8] = 2;
    *((_OWORD *)v14 + 1) = v26;
    goto LABEL_95;
  }
  if ( (int)v15 > 32 )
  {
    v22 = v15 - 64;
    if ( !v22 )
    {
      v14[1] = 6;
      v28 = *(_OWORD *)(a2 + 10);
      v14[8] = 3;
      *((_OWORD *)v14 + 1) = v28;
      goto LABEL_95;
    }
    v23 = v22 - 64;
    if ( !v23 )
    {
      v14[1] = 6;
      v27 = *(_OWORD *)(a2 + 10);
      v14[8] = 0;
      *((_OWORD *)v14 + 1) = v27;
      goto LABEL_95;
    }
    v24 = v23 - 128;
    if ( !v24 )
      goto LABEL_66;
    v25 = v24 - 256;
    if ( v25 )
    {
      v20 = v25 == 512;
LABEL_64:
      if ( !v20 )
        goto LABEL_112;
      goto LABEL_65;
    }
    goto LABEL_65;
  }
  if ( (_DWORD)v15 == 32 )
  {
    v14[1] = 6;
    v21 = *(_OWORD *)(a2 + 10);
    v14[8] = 1;
    *((_OWORD *)v14 + 1) = v21;
    goto LABEL_95;
  }
  v16 = v15 - 1;
  if ( !v16 )
  {
    v14[1] = 1;
    memcpy_0(v14 + 4, a2 + 4, 0xE58u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_d31d59df70993a9dd4981e83321196c3_Traceguids, a2 + 409);
    goto LABEL_95;
  }
  v17 = v16 - 1;
  if ( !v17 )
  {
    v14[1] = 3;
LABEL_54:
    *((_OWORD *)v14 + 1) = *(_OWORD *)(a2 + 10);
    goto LABEL_95;
  }
  v18 = v17 - 2;
  if ( v18 )
  {
    v19 = v18 - 4;
    if ( v19 )
    {
      v20 = v19 == 8;
      goto LABEL_64;
    }
    v14[1] = 5;
    *((_OWORD *)v14 + 1) = *(_OWORD *)(a2 + 10);
    _o_wcsncpy_s(v14 + 8, 257, a2 + 152, -1);
    goto LABEL_52;
  }
LABEL_66:
  v14[1] = 4;
  memcpy_0(v14 + 4, a2 + 4, 0xE58u);
LABEL_52:
  _InterlockedAdd(&g_lRasEntryModifiedVersionEra, 1u);
LABEL_95:
  if ( v14[2] != 3 )
  {
    if ( v14[2] != 1 )
      goto LABEL_112;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v38 = DbgEvents(*v14, v14[1]);
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_d31d59df70993a9dd4981e83321196c3_Traceguids, v38, v39);
    }
    if ( (unsigned int)QueueUserWorkItemInThread(
                         (unsigned int (*)(struct NMEVENT_HEADER *))IncomingEventWorkItem,
                         (struct NMEVENT_HEADER *)v14) )
      return 0;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_112;
    LastError = GetLastError();
    v37 = 21;
    goto LABEL_111;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v35 = DbgEvents(*v14, v14[1]);
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_d31d59df70993a9dd4981e83321196c3_Traceguids, v35, v39);
  }
  if ( (unsigned int)QueueUserWorkItemInThread(
                       (unsigned int (*)(struct NMEVENT_HEADER *))RasEventWorkItem,
                       (struct NMEVENT_HEADER *)v14) )
    return 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    LastError = GetLastError();
    v37 = 19;
LABEL_111:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v37, WPP_d31d59df70993a9dd4981e83321196c3_Traceguids, LastError);
  }
LABEL_112:
  FreeConmanEvent((struct CONMAN_EVENT *)v14);
  return 0;
}

```

## disassembly

```asm
0x180020790  push    rbx
0x180020792  push    rsi
0x180020793  push    rdi
0x180020794  push    r13
0x180020796  push    r14
0x180020798  push    r15
0x18002079a  sub     rsp, 28h
0x18002079e  mov     rdi, rdx
0x1800207a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800207a8  lea     r14, WPP_GLOBAL_Control
0x1800207af  lea     r15, WPP_d31d59df70993a9dd4981e83321196c3_Traceguids
0x1800207b6  cmp     rcx, r14
0x1800207b9  jz      short loc_1800207D2
0x1800207bb  test    byte ptr [rcx+1Ch], 8
0x1800207bf  jz      short loc_1800207D2
0x1800207c1  mov     rcx, [rcx+10h]
0x1800207c5  mov     edx, 0Ch
0x1800207ca  mov     r8, r15
0x1800207cd  call    WPP_SF_
0x1800207d2  mov     rcx, rdi; bstr
0x1800207d5  call    cs:__imp_SysStringByteLen
0x1800207db  mov     esi, 1
0x1800207e0  cmp     eax, 0E60h
0x1800207e5  jnz     loc_1800208D4
0x1800207eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800207f2  cmp     rcx, r14
0x1800207f5  jz      short loc_18002080F
0x1800207f7  test    byte ptr [rcx+1Ch], 8
0x1800207fb  jz      short loc_18002080F
0x1800207fd  mov     r9d, [rdi]
0x180020800  lea     edx, [rsi+0Ch]
0x180020803  mov     rcx, [rcx+10h]
0x180020807  mov     r8, r15
0x18002080a  call    WPP_SF_d
0x18002080f  cmp     cs:ServiceStatus.dwCurrentState, 4
0x180020816  jnz     loc_1800208D4
0x18002081c  mov     ecx, [rdi]
0x18002081e  mov     eax, 400h
0x180020823  cmp     ecx, eax
0x180020825  jg      loc_1800208FC
0x18002082b  jz      short loc_180020855
0x18002082d  sub     ecx, 10h
0x180020830  jz      short loc_180020855
0x180020832  sub     ecx, 10h
0x180020835  jz      loc_1800208F5
0x18002083b  sub     ecx, 20h ; ' '
0x18002083e  jz      loc_1800208EB
0x180020844  sub     ecx, 40h ; '@'
0x180020847  jz      loc_1800208E4
0x18002084d  cmp     ecx, 180h
0x180020853  jnz     short loc_180020875
0x180020855  mov     ebx, 2
0x18002085a  call    ?Instance@CMUtil@@SAAEAV1@XZ; CMUtil::Instance(void)
0x18002085f  lea     r8, [rdi+130h]; unsigned __int16 *
0x180020866  mov     r9d, ebx; enum tagNETCON_STATUS
0x180020869  lea     rdx, [rdi+14h]; struct _GUID *
0x18002086d  mov     rcx, rax; this
0x180020870  call    ?SetEntry@CMUtil@@QEAAXAEBU_GUID@@PEBGW4tagNETCON_STATUS@@@Z; CMUtil::SetEntry(_GUID const &,ushort const *,tagNETCON_STATUS)
0x180020875  call    ?FHasActiveConnectionPoints@ConnectionManager@@SAHXZ; ConnectionManager::FHasActiveConnectionPoints(void)
0x18002087a  test    eax, eax
0x18002087c  jz      short loc_1800208D4
0x18002087e  mov     ecx, [rdi]
0x180020880  lea     eax, [rcx-8000h]
0x180020886  test    eax, 0FFFF7FFFh
0x18002088b  jnz     short loc_180020896
0x18002088d  cmp     cs:?g_fHandleIncomingEvents@@3HA, 0; int g_fHandleIncomingEvents
0x180020894  jz      short loc_1800208D4
0x180020896  lea     eax, [rcx-1]
0x180020899  cmp     eax, esi
0x18002089b  ja      loc_180020942
0x1800208a1  mov     rcx, rdi; struct _RASEVENT *
0x1800208a4  call    ?FIsIgnorableCMEvent@@YAHPEBU_RASEVENT@@@Z; FIsIgnorableCMEvent(_RASEVENT const *)
0x1800208a9  test    eax, eax
0x1800208ab  jz      loc_180020942
0x1800208b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800208b8  cmp     rcx, r14
0x1800208bb  jz      short loc_1800208D4
0x1800208bd  test    byte ptr [rcx+1Ch], 8
0x1800208c1  jz      short loc_1800208D4
0x1800208c3  mov     edx, 0Eh
0x1800208c8  mov     rcx, [rcx+10h]
0x1800208cc  mov     r8, r15
0x1800208cf  call    WPP_SF_
0x1800208d4  mov     eax, esi
0x1800208d6  add     rsp, 28h
0x1800208da  pop     r15
0x1800208dc  pop     r14
0x1800208de  pop     r13
0x1800208e0  pop     rdi
0x1800208e1  pop     rsi
0x1800208e2  pop     rbx
0x1800208e3  retn
0x1800208e4  xor     ebx, ebx
0x1800208e6  jmp     loc_18002085A
0x1800208eb  mov     ebx, 3
0x1800208f0  jmp     loc_18002085A
0x1800208f5  mov     ebx, esi
0x1800208f7  jmp     loc_18002085A
0x1800208fc  cmp     ecx, 800h
0x180020902  jz      loc_180020855
0x180020908  cmp     ecx, 100000h
0x18002090e  jz      short loc_180020938
0x180020910  cmp     ecx, 200000h
0x180020916  jz      short loc_18002092E
0x180020918  cmp     ecx, 400000h
0x18002091e  jnz     loc_180020875
0x180020924  mov     ebx, 0Fh
0x180020929  jmp     loc_18002085A
0x18002092e  mov     ebx, 0Eh
0x180020933  jmp     loc_18002085A
0x180020938  mov     ebx, 0Dh
0x18002093d  jmp     loc_18002085A
0x180020942  mov     r13d, 0E68h
0x180020948  mov     ecx, r13d; unsigned __int64
0x18002094b  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x180020950  mov     rbx, rax
0x180020953  test    rax, rax
0x180020956  jnz     short loc_18002097A
0x180020958  mov     rcx, cs:WPP_GLOBAL_Control
0x18002095f  cmp     rcx, r14
0x180020962  jz      loc_1800208D4
0x180020968  test    byte ptr [rcx+1Ch], 8
0x18002096c  jz      loc_1800208D4
0x180020972  lea     edx, [rax+0Fh]
0x180020975  jmp     loc_1800208C8
0x18002097a  mov     r8, r13; Size
0x18002097d  xor     edx, edx; Val
0x18002097f  mov     rcx, rbx; void *
0x180020982  call    memset_0
0x180020987  mov     r13d, 3
0x18002098d  mov     [rbx], esi
0x18002098f  mov     [rbx+8], r13d
0x180020993  mov     eax, 800h
0x180020998  mov     ecx, [rdi]
0x18002099a  cmp     ecx, eax
0x18002099c  jg      loc_180020B18
0x1800209a2  jz      loc_180020AA8
0x1800209a8  cmp     ecx, 20h ; ' '
0x1800209ab  jg      loc_180020A82
0x1800209b1  jz      loc_180020A6A
0x1800209b7  sub     ecx, esi
0x1800209b9  jz      short loc_180020A1D
0x1800209bb  sub     ecx, esi
0x1800209bd  jz      short loc_180020A0B
0x1800209bf  sub     ecx, 2
0x1800209c2  jz      loc_180020AC4
0x1800209c8  sub     ecx, 4
0x1800209cb  jz      short loc_1800209D5
0x1800209cd  cmp     ecx, 8
0x1800209d0  jmp     loc_180020AA2
0x1800209d5  mov     dword ptr [rbx+4], 5
0x1800209dc  lea     r8, [rdi+130h]
0x1800209e3  movups  xmm0, xmmword ptr [rdi+14h]
0x1800209e7  lea     rcx, [rbx+20h]
0x1800209eb  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800209ef  mov     edx, 101h
0x1800209f4  movdqu  xmmword ptr [rbx+10h], xmm0
0x1800209f9  call    cs:__imp__o_wcsncpy_s
0x1800209ff  lock add cs:?g_lRasEntryModifiedVersionEra@@3JA, esi; long g_lRasEntryModifiedVersionEra
0x180020a06  jmp     loc_180020C9C
0x180020a0b  mov     [rbx+4], r13d
0x180020a0f  movups  xmm0, xmmword ptr [rdi+14h]
0x180020a13  movdqu  xmmword ptr [rbx+10h], xmm0
0x180020a18  jmp     loc_180020C9C
0x180020a1d  lea     rcx, [rbx+10h]; void *
0x180020a21  mov     [rbx+4], esi
0x180020a24  lea     rdx, [rdi+8]; Src
0x180020a28  mov     r8d, 0E58h; Size
0x180020a2e  call    memcpy_0
0x180020a33  mov     rax, cs:WPP_GLOBAL_Control
0x180020a3a  cmp     rax, r14
0x180020a3d  jz      loc_180020C9C
0x180020a43  test    byte ptr [rax+1Ch], 8
0x180020a47  jz      loc_180020C9C
0x180020a4d  mov     rcx, [rax+10h]
0x180020a51  lea     r9, [rdi+332h]
0x180020a58  mov     edx, 10h
0x180020a5d  mov     r8, r15
0x180020a60  call    WPP_SF_S
0x180020a65  jmp     loc_180020C9C
0x180020a6a  mov     dword ptr [rbx+4], 6
0x180020a71  movups  xmm0, xmmword ptr [rdi+14h]
0x180020a75  mov     [rbx+20h], esi
0x180020a78  movdqu  xmmword ptr [rbx+10h], xmm0
0x180020a7d  jmp     loc_180020C9C
0x180020a82  sub     ecx, 40h ; '@'
0x180020a85  jz      short loc_180020AFF
0x180020a87  sub     ecx, 40h ; '@'
0x180020a8a  jz      short loc_180020AE3
0x180020a8c  sub     ecx, 80h
0x180020a92  jz      short loc_180020AC4
0x180020a94  sub     ecx, 100h
0x180020a9a  jz      short loc_180020AA8
0x180020a9c  cmp     ecx, 200h
0x180020aa2  jnz     loc_180020D99
0x180020aa8  mov     dword ptr [rbx+4], 6
0x180020aaf  movups  xmm0, xmmword ptr [rdi+14h]
0x180020ab3  mov     dword ptr [rbx+20h], 2
0x180020aba  movdqu  xmmword ptr [rbx+10h], xmm0
0x180020abf  jmp     loc_180020C9C
0x180020ac4  lea     rcx, [rbx+10h]; void *
0x180020ac8  mov     dword ptr [rbx+4], 4
0x180020acf  lea     rdx, [rdi+8]; Src
0x180020ad3  mov     r8d, 0E58h; Size
0x180020ad9  call    memcpy_0
0x180020ade  jmp     loc_1800209FF
0x180020ae3  mov     dword ptr [rbx+4], 6
0x180020aea  movups  xmm0, xmmword ptr [rdi+14h]
0x180020aee  mov     dword ptr [rbx+20h], 0
0x180020af5  movdqu  xmmword ptr [rbx+10h], xmm0
0x180020afa  jmp     loc_180020C9C
0x180020aff  mov     dword ptr [rbx+4], 6
0x180020b06  movups  xmm0, xmmword ptr [rdi+14h]
0x180020b0a  mov     [rbx+20h], r13d
0x180020b0e  movdqu  xmmword ptr [rbx+10h], xmm0
0x180020b13  jmp     loc_180020C9C
0x180020b18  mov     eax, 40000h
0x180020b1d  cmp     ecx, eax
0x180020b1f  jg      loc_180020C26
0x180020b25  jz      loc_180020C95
0x180020b2b  lea     eax, [rcx-2000h]
0x180020b31  test    eax, 0FFFFDFFFh
0x180020b36  jz      loc_180020C1A
0x180020b3c  cmp     ecx, 8000h
0x180020b42  jz      loc_180020BF3
0x180020b48  cmp     ecx, 10000h
0x180020b4e  jz      loc_180020BDE
0x180020b54  cmp     ecx, 20000h
0x180020b5a  jnz     loc_180020D99
0x180020b60  cmp     dword ptr [rdi+0Ch], 2
0x180020b64  jnz     short loc_180020BC8
0x180020b66  lea     rcx, ?g_fHandleIncomingEvents@@3HA; int g_fHandleIncomingEvents
0x180020b6d  mov     [rbx+8], esi
0x180020b70  mov     dword ptr [rbx+4], 7
0x180020b77  call    cs:__imp_RasSrvAllowConnectionsConfig
0x180020b7d  mov     r9d, eax
0x180020b80  test    eax, eax
0x180020b82  jle     short loc_180020B8F
0x180020b84  movzx   r9d, ax
0x180020b88  or      r9d, 80070000h
0x180020b8f  test    r9d, r9d
0x180020b92  jns     loc_180020C9C
0x180020b98  mov     rax, cs:WPP_GLOBAL_Control
0x180020b9f  cmp     rax, r14
0x180020ba2  jz      loc_180020C9C
0x180020ba8  test    [rax+1Ch], sil
0x180020bac  jz      loc_180020C9C
0x180020bb2  mov     rcx, [rax+10h]
0x180020bb6  mov     edx, 11h
0x180020bbb  mov     r8, r15
0x180020bbe  call    WPP_SF_d
0x180020bc3  jmp     loc_180020C9C
0x180020bc8  cmp     dword ptr [rdi+8], 0
0x180020bcc  jnz     loc_180020D99
0x180020bd2  mov     edx, esi
0x180020bd4  call    ?ReferenceRasman@ServiceModule@@QEAAXW4RASREFTYPE@@@Z; ServiceModule::ReferenceRasman(RASREFTYPE)
0x180020bd9  jmp     loc_180020D99
0x180020bde  mov     [rbx+8], esi
0x180020be1  movups  xmm0, xmmword ptr [rdi+14h]
0x180020be5  mov     [rbx+4], r13d
0x180020be9  movdqu  xmmword ptr [rbx+10h], xmm0
0x180020bee  jmp     loc_180020C9C
0x180020bf3  mov     [rbx+8], esi
0x180020bf6  mov     rax, [rdi+8]
0x180020bfa  mov     [rbx+20h], rax
0x180020bfe  movups  xmm0, xmmword ptr [rdi+14h]
0x180020c02  movdqu  xmmword ptr [rbx+10h], xmm0
0x180020c07  mov     ecx, [rdi+10h]
0x180020c0a  call    ?RasSrvTypeFromRasDeviceType@@YAKW4_RASDEVICETYPE@@@Z; RasSrvTypeFromRasDeviceType(_RASDEVICETYPE)
0x180020c0f  mov     [rbx+28h], eax
0x180020c12  mov     [rbx+4], esi
0x180020c15  jmp     loc_180020C9C
0x180020c1a  mov     dword ptr [rbx+4], 2
0x180020c21  jmp     loc_180020A0F
0x180020c26  cmp     ecx, 80000h
0x180020c2c  jz      short loc_180020C95
0x180020c2e  cmp     ecx, 100000h
0x180020c34  jz      short loc_180020C7C
0x180020c36  cmp     ecx, 200000h
0x180020c3c  jz      short loc_180020C63
0x180020c3e  cmp     ecx, 400000h
0x180020c44  jnz     loc_180020D99
0x180020c4a  mov     dword ptr [rbx+4], 6
0x180020c51  movups  xmm0, xmmword ptr [rdi+14h]
0x180020c55  mov     dword ptr [rbx+20h], 0Fh
0x180020c5c  movdqu  xmmword ptr [rbx+10h], xmm0
0x180020c61  jmp     short loc_180020C9C
0x180020c63  mov     dword ptr [rbx+4], 6
0x180020c6a  movups  xmm0, xmmword ptr [rdi+14h]
0x180020c6e  mov     dword ptr [rbx+20h], 0Eh
0x180020c75  movdqu  xmmword ptr [rbx+10h], xmm0
0x180020c7a  jmp     short loc_180020C9C
0x180020c7c  mov     dword ptr [rbx+4], 6
0x180020c83  movups  xmm0, xmmword ptr [rdi+14h]
0x180020c87  mov     dword ptr [rbx+20h], 0Dh
0x180020c8e  movdqu  xmmword ptr [rbx+10h], xmm0
0x180020c93  jmp     short loc_180020C9C
0x180020c95  mov     dword ptr [rbx+4], 7
0x180020c9c  cmp     [rbx+8], r13d
0x180020ca0  jnz     short loc_180020D17
  ... truncated ...
```
