# ConvertQMSAFromBfeToSpd

- ea: `0x18002e0e0`
- end: `0x18002e6c7`
- name: `ConvertQMSAFromBfeToSpd`
- size: `1511`
- prototype: `__int64 __fastcall(int *, __int64, void *, _OWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002efbc`

## callees

- `0x18000e510`
- `0x18002e0e0`
- `0x180045f38`
- `0x18004d05e`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e626`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e626`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e685`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e685`
- `fwpuclnt!IkeextSaDestroyEnumHandle0` at `0x18002e6a7`
- `fwpuclnt!IkeextSaDestroyEnumHandle0` at `0x18002e6a7`
- `fwpuclnt!FwpmFreeMemory0` at `0x18002e695`
- `fwpuclnt!FwpmFreeMemory0` at `0x18002e695`
- `fwpuclnt!IkeextSaCreateEnumHandle0` at `0x18002e4b0`
- `fwpuclnt!IkeextSaCreateEnumHandle0` at `0x18002e4b0`
- `fwpuclnt!IkeextSaEnum0` at `0x18002e542`
- `fwpuclnt!IkeextSaEnum0` at `0x18002e542`
- `WS2_32!__imp_ntohl` at `0x18002e2e0`
- `WS2_32!__imp_ntohl` at `0x18002e31c`
- `WS2_32!__imp_ntohl` at `0x18002e2e0`
- `WS2_32!__imp_ntohl` at `0x18002e31c`

## pseudocode

```c
__int64 __fastcall ConvertQMSAFromBfeToSpd(int *a1, __int64 a2, void *a3, _OWORD *a4)
{
  int v7; // r14d
  int v8; // ecx
  int v9; // edx
  int v10; // edx
  int v11; // edx
  int v12; // edx
  int v13; // eax
  unsigned int v14; // esi
  __int64 v15; // r10
  _DWORD *v16; // r11
  __int64 v17; // rcx
  int *v18; // r9
  int v19; // edx
  int v20; // eax
  bool v21; // zf
  u_long v22; // eax
  __int128 v23; // xmm0
  u_long v24; // eax
  __int128 v25; // xmm0
  __int64 v26; // rdx
  __int64 v27; // r8
  unsigned int v28; // r15d
  __int64 v29; // r14
  __int64 v30; // r9
  __int64 v31; // r10
  __int64 v32; // r11
  __int64 v33; // rsi
  __int64 v34; // rax
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // rdx
  int v38; // edx
  int v39; // edx
  __int64 v40; // rax
  DWORD v41; // eax
  DWORD v42; // esi
  _QWORD *v43; // rcx
  __int64 v44; // rdx
  __int64 v45; // r9
  DWORD v46; // eax
  unsigned int i; // edx
  _WORD *v48; // rax
  __int16 v49; // cx
  __int64 v50; // r8
  _QWORD *j; // r9
  __int64 v52; // r8
  __int64 v53; // r9
  __int64 v54; // r10
  _OWORD *v55; // rax
  IKEEXT_SA_DETAILS0 **entries; // [rsp+70h] [rbp+40h] BYREF
  __int64 numEntriesReturned; // [rsp+78h] [rbp+48h] BYREF
  HANDLE enumHandle; // [rsp+88h] [rbp+58h] BYREF

  numEntriesReturned = a2;
  enumHandle = 0;
  entries = 0;
  memset_0(a4, 0, 0x170u);
  v7 = *a1;
  v8 = 0;
  *(_OWORD *)((char *)a4 + 116) = *(_OWORD *)*((_QWORD *)a1 + 20);
  *((_DWORD *)a4 + 4) = a1[17];
  *((_DWORD *)a4 + 5) = a1[18];
  *((_DWORD *)a4 + 6) = a1[16];
  *((_DWORD *)a4 + 7) = a1[36] != 0;
  v9 = a1[36];
  if ( v9 )
  {
    v10 = v9 - 1;
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( v11 )
      {
        v12 = v11 - 1;
        if ( v12 )
        {
          if ( v12 == 3 )
            *((_DWORD *)a4 + 8) = 0x80000000;
        }
        else
        {
          *((_DWORD *)a4 + 8) = 268435457;
        }
      }
      else
      {
        *((_DWORD *)a4 + 8) = 2;
      }
    }
    else
    {
      *((_DWORD *)a4 + 8) = 1;
    }
  }
  v13 = a1[26];
  v14 = 0;
  *((_DWORD *)a4 + 9) = v13;
  if ( v13 )
  {
    while ( 1 )
    {
      v15 = *((_QWORD *)a1 + 14);
      v16 = 0;
      v17 = 9LL * v14;
      if ( *(_DWORD *)(v15 + 16LL * v14 + 4) == 1 )
        break;
      switch ( *(_DWORD *)(v15 + 16LL * v14 + 4) )
      {
        case 2:
          *((_DWORD *)a4 + 9 * v14 + 10) = 2;
LABEL_19:
          v18 = *(int **)(v15 + 16LL * v14 + 8);
          goto LABEL_20;
        case 3:
          *((_DWORD *)a4 + 9 * v14 + 10) = 2;
          v16 = *(_DWORD **)(v15 + 16LL * v14 + 8);
          goto LABEL_34;
        case 4:
          *((_DWORD *)a4 + 9 * v14 + 10) = 2;
          v16 = *(_DWORD **)(v15 + 16LL * v14 + 8);
          v18 = v16 + 8;
LABEL_20:
          if ( v18 )
          {
            v19 = *v18;
            if ( *(_DWORD *)(v15 + 16LL * v14 + 4) == 1 )
            {
              if ( v19 )
              {
                if ( v19 == 1 )
                  *((_DWORD *)a4 + 9 * v14 + 11) = 2;
                else
                  *((_DWORD *)a4 + 9 * v14 + 11) = 0;
              }
              else
              {
                *((_DWORD *)a4 + 9 * v14 + 11) = 1;
              }
              *((_DWORD *)a4 + 9 * v14 + 13) = v18[4];
            }
            else
            {
              if ( v19 )
              {
                if ( v19 == 1 )
                  *((_DWORD *)a4 + 9 * v14 + 12) = 2;
                else
                  *((_DWORD *)a4 + 9 * v14 + 12) = 0;
              }
              else
              {
                *((_DWORD *)a4 + 9 * v14 + 12) = 1;
              }
              *((_DWORD *)a4 + 9 * v14 + 14) = v18[4];
            }
          }
LABEL_34:
          if ( v16 )
          {
            if ( *v16 == 1 )
            {
              *((_DWORD *)a4 + 9 * v14 + 11) = 1;
            }
            else if ( *v16 == 2 )
            {
              *((_DWORD *)a4 + 9 * v14 + 11) = 3;
            }
            else
            {
              *((_DWORD *)a4 + 9 * v14 + 11) = 0;
            }
            *((_DWORD *)a4 + 9 * v14 + 13) = v16[4];
          }
          break;
      }
      v20 = *(_DWORD *)(v15 + 16LL * v14++);
      *((_DWORD *)a4 + v17 + 17) = v20;
      if ( v14 >= *((_DWORD *)a4 + 9) )
      {
        v8 = *((_DWORD *)a4 + 74);
        goto LABEL_43;
      }
    }
    *((_DWORD *)a4 + 9 * v14 + 10) = 1;
    goto LABEL_19;
  }
LABEL_43:
  v21 = *a1 == 0;
  *((_DWORD *)a4 + 35) = 1;
  *((_DWORD *)a4 + 34) = !v21;
  *((_DWORD *)a4 + 36) = 1;
  if ( v7 )
  {
    v23 = *(_OWORD *)(a1 + 3);
    *((_BYTE *)a4 + 164) = 0x80;
    *(_OWORD *)((char *)a4 + 148) = v23;
  }
  else
  {
    v22 = ntohl(a1[3]);
    v8 = *((_DWORD *)a4 + 74);
    *((_DWORD *)a4 + 37) = v22;
    *((_DWORD *)a4 + 38) = -1;
  }
  *((_DWORD *)a4 + 44) = 1;
  if ( v7 )
  {
    v25 = *(_OWORD *)(a1 + 7);
    *((_BYTE *)a4 + 196) = 0x80;
    *(_OWORD *)((char *)a4 + 180) = v25;
  }
  else
  {
    v24 = ntohl(a1[7]);
    v8 = *((_DWORD *)a4 + 74);
    *((_DWORD *)a4 + 45) = v24;
    *((_DWORD *)a4 + 46) = -1;
  }
  v26 = *((_QWORD *)a1 + 20);
  if ( *(_DWORD *)(v26 + 112) )
  {
    v27 = *(_QWORD *)FWPM_CONDITION_IP_LOCAL_PORT.Data4;
    v28 = 0;
    v29 = *(_QWORD *)&FWPM_CONDITION_IP_LOCAL_PORT.Data1;
    v30 = *(_QWORD *)FWPM_CONDITION_IP_REMOTE_PORT.Data4;
    v31 = *(_QWORD *)&FWPM_CONDITION_IP_REMOTE_PORT.Data1;
    v32 = *(_QWORD *)FWPM_CONDITION_IP_PROTOCOL.Data4;
    v33 = *(_QWORD *)&FWPM_CONDITION_IP_PROTOCOL.Data1;
    while ( 1 )
    {
      v34 = *(_QWORD *)(v26 + 120);
      v35 = *(_QWORD *)(v34 + 40LL * v28) - v29;
      if ( !v35 )
        v35 = *(_QWORD *)(v34 + 40LL * v28 + 8) - v27;
      if ( v35 )
      {
        v36 = *(_QWORD *)(v34 + 40LL * v28) - v31;
        if ( !v36 )
          v36 = *(_QWORD *)(v34 + 40LL * v28 + 8) - v30;
        if ( v36 )
        {
          v37 = *(_QWORD *)(v34 + 40LL * v28) - v33;
          if ( !v37 )
            v37 = *(_QWORD *)(v34 + 40LL * v28 + 8) - v32;
          if ( v37 )
            goto LABEL_64;
          *((_DWORD *)a4 + 52) = 1;
          *((_DWORD *)a4 + 53) = *(unsigned __int8 *)(v34 + 40LL * v28 + 32);
        }
        else
        {
          *((_DWORD *)a4 + 56) = 1;
          *((_WORD *)a4 + 114) = *(_WORD *)(v34 + 40LL * v28 + 32);
        }
      }
      else
      {
        *((_DWORD *)a4 + 54) = 1;
        *((_WORD *)a4 + 110) = *(_WORD *)(v34 + 40LL * v28 + 32);
      }
      v27 = *(_QWORD *)FWPM_CONDITION_IP_LOCAL_PORT.Data4;
      v29 = *(_QWORD *)&FWPM_CONDITION_IP_LOCAL_PORT.Data1;
      v30 = *(_QWORD *)FWPM_CONDITION_IP_REMOTE_PORT.Data4;
      v31 = *(_QWORD *)&FWPM_CONDITION_IP_REMOTE_PORT.Data1;
      v32 = *(_QWORD *)FWPM_CONDITION_IP_PROTOCOL.Data4;
      v33 = *(_QWORD *)&FWPM_CONDITION_IP_PROTOCOL.Data1;
LABEL_64:
      v26 = *((_QWORD *)a1 + 20);
      if ( ++v28 >= *(_DWORD *)(v26 + 112) )
      {
        v8 = *((_DWORD *)a4 + 74);
        break;
      }
    }
  }
  v38 = a1[1];
  if ( v38 )
  {
    v39 = v38 - 1;
    if ( v39 )
    {
      if ( v39 != 1 )
        goto LABEL_73;
      *((_DWORD *)a4 + 74) |= 0xCu;
    }
    else
    {
      *((_DWORD *)a4 + 74) |= 4u;
    }
  }
  else
  {
    *((_DWORD *)a4 + 74) |= 8u;
  }
  v8 = *((_DWORD *)a4 + 74);
LABEL_73:
  v40 = *((_QWORD *)a1 + 20);
  LODWORD(numEntriesReturned) = 0;
  *((_DWORD *)a4 + 74) = *(_DWORD *)(v40 + 32) | v8;
  v41 = IkeextSaCreateEnumHandle0(a3, 0, &enumHandle);
  v42 = v41;
  if ( v41 )
  {
    v43 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids, v41);
        v43 = WPP_GLOBAL_Control;
      }
      if ( v43 != &WPP_GLOBAL_Control && (*((_BYTE *)v43 + 28) & 0x10) != 0 )
      {
        v44 = 32;
        v45 = v42;
LABEL_80:
        WPP_SF_d(v43[2], v44, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids, v45);
      }
    }
  }
  else
  {
    v46 = IkeextSaEnum0(a3, enumHandle, 0x7FFFFFFFu, &entries, (UINT32 *)&numEntriesReturned);
    v42 = v46;
    if ( v46 )
    {
      v43 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v44 = 33;
        v45 = v46;
        goto LABEL_80;
      }
    }
    else
    {
      for ( i = 0; i < (unsigned int)numEntriesReturned; ++i )
      {
        if ( *((_QWORD *)a1 + 17) == entries[i]->saId )
        {
          _mm_lfence();
          *((IKEEXT_COOKIE_PAIR0 *)a4 + 19) = entries[i]->cookiePair;
          break;
        }
      }
      *((_DWORD *)a4 + 80) = 1;
      if ( *((_QWORD *)a1 + 19) )
      {
        *((_DWORD *)a4 + 80) = 3;
        v48 = (_WORD *)*((_QWORD *)a1 + 19);
        if ( a1[1] )
        {
          *((_WORD *)a4 + 162) = v48[1];
          v49 = **((_WORD **)a1 + 19);
        }
        else
        {
          *((_WORD *)a4 + 162) = *v48;
          v49 = *(_WORD *)(*((_QWORD *)a1 + 19) + 2LL);
        }
        *((_WORD *)a4 + 163) = v49;
      }
      EnterCriticalSection(&gcSPDSection);
      v50 = *((_QWORD *)a1 + 20);
      for ( j = gpIniTxSFilter; j; j = *(_QWORD **)(v53 + 208) )
      {
        if ( (unsigned int)LipsApiMatchTransportFilter(j[25], 4, v50)
          || (unsigned int)LipsApiMatchTransportFilter(v54, 8, v52) )
        {
          v55 = *(_OWORD **)(v53 + 184);
          if ( v55 )
            *a4 = *v55;
          break;
        }
      }
      LeaveCriticalSection(&gcSPDSection);
    }
  }
  if ( entries )
    FwpmFreeMemory0((void **)&entries);
  if ( enumHandle )
    IkeextSaDestroyEnumHandle0(a3, enumHandle);
  return v42;
}

```

## disassembly

```asm
0x18002e0e0  mov     [rsp-38h+arg_10], rbx
0x18002e0e5  mov     [rsp-38h+arg_8], rdx
0x18002e0ea  push    rbp
0x18002e0eb  push    rsi
0x18002e0ec  push    rdi
0x18002e0ed  push    r12
0x18002e0ef  push    r13
0x18002e0f1  push    r14
0x18002e0f3  push    r15
0x18002e0f5  mov     rbp, rsp
0x18002e0f8  sub     rsp, 30h
0x18002e0fc  mov     r12, r8
0x18002e0ff  mov     rdi, rcx
0x18002e102  xor     r13d, r13d
0x18002e105  mov     r8d, 170h; Size
0x18002e10b  mov     rcx, r9; void *
0x18002e10e  mov     [rbp+enumHandle], r13
0x18002e112  xor     edx, edx; Val
0x18002e114  mov     [rbp+entries], r13
0x18002e118  mov     rbx, r9
0x18002e11b  call    memset_0
0x18002e120  mov     rax, [rdi+0A0h]
0x18002e127  lea     r15d, [r13+1]
0x18002e12b  mov     r14d, [rdi]
0x18002e12e  mov     ecx, r13d
0x18002e131  movups  xmm0, xmmword ptr [rax]
0x18002e134  movdqu  xmmword ptr [rbx+74h], xmm0
0x18002e139  mov     eax, [rdi+44h]
0x18002e13c  mov     [rbx+10h], eax
0x18002e13f  mov     eax, [rdi+48h]
0x18002e142  mov     [rbx+14h], eax
0x18002e145  mov     eax, [rdi+40h]
0x18002e148  mov     [rbx+18h], eax
0x18002e14b  mov     eax, r13d
0x18002e14e  cmp     [rdi+90h], r13d
0x18002e155  setnz   al
0x18002e158  mov     [rbx+1Ch], eax
0x18002e15b  mov     edx, [rdi+90h]
0x18002e161  test    edx, edx
0x18002e163  jz      short loc_18002E198
0x18002e165  sub     edx, r15d
0x18002e168  jz      short loc_18002E194
0x18002e16a  sub     edx, r15d
0x18002e16d  jz      short loc_18002E18B
0x18002e16f  sub     edx, r15d
0x18002e172  jz      short loc_18002E182
0x18002e174  cmp     edx, 3
0x18002e177  jnz     short loc_18002E198
0x18002e179  mov     dword ptr [rbx+20h], 80000000h
0x18002e180  jmp     short loc_18002E198
0x18002e182  mov     dword ptr [rbx+20h], 10000001h
0x18002e189  jmp     short loc_18002E198
0x18002e18b  mov     dword ptr [rbx+20h], 2
0x18002e192  jmp     short loc_18002E198
0x18002e194  mov     [rbx+20h], r15d
0x18002e198  mov     eax, [rdi+68h]
0x18002e19b  mov     esi, r13d
0x18002e19e  mov     [rbx+24h], eax
0x18002e1a1  test    eax, eax
0x18002e1a3  jz      loc_18002E2B8
0x18002e1a9  mov     r10, [rdi+70h]
0x18002e1ad  mov     r11, r13
0x18002e1b0  mov     r8d, esi
0x18002e1b3  add     r8, r8
0x18002e1b6  mov     eax, esi
0x18002e1b8  mov     edx, [r10+r8*8+4]
0x18002e1bd  lea     rcx, [rax+rax*8]
0x18002e1c1  sub     edx, r15d
0x18002e1c4  jz      short loc_18002E205
0x18002e1c6  sub     edx, r15d
0x18002e1c9  jz      short loc_18002E1FB
0x18002e1cb  sub     edx, r15d
0x18002e1ce  jz      short loc_18002E1EC
0x18002e1d0  cmp     edx, r15d
0x18002e1d3  jnz     loc_18002E29E
0x18002e1d9  mov     dword ptr [rbx+rcx*4+28h], 2
0x18002e1e1  mov     r11, [r10+r8*8+8]
0x18002e1e6  lea     r9, [r11+20h]
0x18002e1ea  jmp     short loc_18002E20F
0x18002e1ec  mov     dword ptr [rbx+rcx*4+28h], 2
0x18002e1f4  mov     r11, [r10+r8*8+8]
0x18002e1f9  jmp     short loc_18002E26E
0x18002e1fb  mov     dword ptr [rbx+rcx*4+28h], 2
0x18002e203  jmp     short loc_18002E20A
0x18002e205  mov     [rbx+rcx*4+28h], r15d
0x18002e20a  mov     r9, [r10+r8*8+8]
0x18002e20f  test    r9, r9
0x18002e212  jz      short loc_18002E26E
0x18002e214  mov     edx, [r9]
0x18002e217  cmp     [r10+r8*8+4], r15d
0x18002e21c  jnz     short loc_18002E247
0x18002e21e  test    edx, edx
0x18002e220  jz      short loc_18002E238
0x18002e222  cmp     edx, r15d
0x18002e225  jz      short loc_18002E22E
0x18002e227  mov     [rbx+rcx*4+2Ch], r13d
0x18002e22c  jmp     short loc_18002E23D
0x18002e22e  mov     dword ptr [rbx+rcx*4+2Ch], 2
0x18002e236  jmp     short loc_18002E23D
0x18002e238  mov     [rbx+rcx*4+2Ch], r15d
0x18002e23d  mov     eax, [r9+10h]
0x18002e241  mov     [rbx+rcx*4+34h], eax
0x18002e245  jmp     short loc_18002E26E
0x18002e247  test    edx, edx
0x18002e249  jz      short loc_18002E261
0x18002e24b  cmp     edx, r15d
0x18002e24e  jz      short loc_18002E257
0x18002e250  mov     [rbx+rcx*4+30h], r13d
0x18002e255  jmp     short loc_18002E266
0x18002e257  mov     dword ptr [rbx+rcx*4+30h], 2
0x18002e25f  jmp     short loc_18002E266
0x18002e261  mov     [rbx+rcx*4+30h], r15d
0x18002e266  mov     eax, [r9+10h]
0x18002e26a  mov     [rbx+rcx*4+38h], eax
0x18002e26e  test    r11, r11
0x18002e271  jz      short loc_18002E29E
0x18002e273  mov     edx, [r11]
0x18002e276  sub     edx, r15d
0x18002e279  jz      short loc_18002E291
0x18002e27b  cmp     edx, r15d
0x18002e27e  jz      short loc_18002E287
0x18002e280  mov     [rbx+rcx*4+2Ch], r13d
0x18002e285  jmp     short loc_18002E296
0x18002e287  mov     dword ptr [rbx+rcx*4+2Ch], 3
0x18002e28f  jmp     short loc_18002E296
0x18002e291  mov     [rbx+rcx*4+2Ch], r15d
0x18002e296  mov     eax, [r11+10h]
0x18002e29a  mov     [rbx+rcx*4+34h], eax
0x18002e29e  mov     eax, [r10+r8*8]
0x18002e2a2  add     esi, r15d
0x18002e2a5  mov     [rbx+rcx*4+44h], eax
0x18002e2a9  cmp     esi, [rbx+24h]
0x18002e2ac  jb      loc_18002E1A9
0x18002e2b2  mov     ecx, [rbx+128h]
0x18002e2b8  cmp     [rdi], r13d
0x18002e2bb  mov     eax, r13d
0x18002e2be  mov     [rbx+8Ch], r15d
0x18002e2c5  setnz   al
0x18002e2c8  or      esi, 0FFFFFFFFh
0x18002e2cb  mov     [rbx+88h], eax
0x18002e2d1  mov     [rbx+90h], r15d
0x18002e2d8  test    r14d, r14d
0x18002e2db  jnz     short loc_18002E2FA
0x18002e2dd  mov     ecx, [rdi+0Ch]; netlong
0x18002e2e0  call    cs:__imp_ntohl
0x18002e2e6  mov     ecx, [rbx+128h]
0x18002e2ec  mov     [rbx+94h], eax
0x18002e2f2  mov     [rbx+98h], esi
0x18002e2f8  jmp     short loc_18002E30D
0x18002e2fa  movups  xmm0, xmmword ptr [rdi+0Ch]
0x18002e2fe  mov     byte ptr [rbx+0A4h], 80h
0x18002e305  movdqu  xmmword ptr [rbx+94h], xmm0
0x18002e30d  mov     [rbx+0B0h], r15d
0x18002e314  test    r14d, r14d
0x18002e317  jnz     short loc_18002E336
0x18002e319  mov     ecx, [rdi+1Ch]; netlong
0x18002e31c  call    cs:__imp_ntohl
0x18002e322  mov     ecx, [rbx+128h]
0x18002e328  mov     [rbx+0B4h], eax
0x18002e32e  mov     [rbx+0B8h], esi
0x18002e334  jmp     short loc_18002E349
0x18002e336  movups  xmm0, xmmword ptr [rdi+1Ch]
0x18002e33a  mov     byte ptr [rbx+0C4h], 80h
0x18002e341  movdqu  xmmword ptr [rbx+0B4h], xmm0
0x18002e349  mov     rdx, [rdi+0A0h]
0x18002e350  cmp     [rdx+70h], r13d
0x18002e354  jbe     loc_18002E463
0x18002e35a  mov     r8, qword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data4
0x18002e361  mov     r15d, r13d
0x18002e364  mov     r14, qword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data1
0x18002e36b  mov     r9, qword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data4
0x18002e372  mov     r10, qword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data1
0x18002e379  mov     r11, qword ptr cs:FWPM_CONDITION_IP_PROTOCOL.Data4
0x18002e380  mov     rsi, qword ptr cs:FWPM_CONDITION_IP_PROTOCOL.Data1
0x18002e387  mov     eax, r15d
0x18002e38a  lea     rcx, [rax+rax*4]
0x18002e38e  mov     rax, [rdx+78h]
0x18002e392  mov     rdx, [rax+rcx*8]
0x18002e396  sub     rdx, r14
0x18002e399  jnz     short loc_18002E3A3
0x18002e39b  mov     rdx, [rax+rcx*8+8]
0x18002e3a0  sub     rdx, r8
0x18002e3a3  test    rdx, rdx
0x18002e3a6  jnz     short loc_18002E3C0
0x18002e3a8  mov     dword ptr [rbx+0D8h], 1
0x18002e3b2  movzx   eax, word ptr [rax+rcx*8+20h]
0x18002e3b7  mov     [rbx+0DCh], ax
0x18002e3be  jmp     short loc_18002E419
0x18002e3c0  mov     rdx, [rax+rcx*8]
0x18002e3c4  sub     rdx, r10
0x18002e3c7  jnz     short loc_18002E3D1
0x18002e3c9  mov     rdx, [rax+rcx*8+8]
0x18002e3ce  sub     rdx, r9
0x18002e3d1  test    rdx, rdx
0x18002e3d4  jnz     short loc_18002E3EE
0x18002e3d6  mov     dword ptr [rbx+0E0h], 1
0x18002e3e0  movzx   eax, word ptr [rax+rcx*8+20h]
0x18002e3e5  mov     [rbx+0E4h], ax
0x18002e3ec  jmp     short loc_18002E419
0x18002e3ee  mov     rdx, [rax+rcx*8]
0x18002e3f2  sub     rdx, rsi
0x18002e3f5  jnz     short loc_18002E3FF
0x18002e3f7  mov     rdx, [rax+rcx*8+8]
0x18002e3fc  sub     rdx, r11
0x18002e3ff  test    rdx, rdx
0x18002e402  jnz     short loc_18002E443
0x18002e404  mov     dword ptr [rbx+0D0h], 1
0x18002e40e  movzx   eax, byte ptr [rax+rcx*8+20h]
0x18002e413  mov     [rbx+0D4h], eax
0x18002e419  mov     r8, qword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data4
0x18002e420  mov     r14, qword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data1
0x18002e427  mov     r9, qword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data4
0x18002e42e  mov     r10, qword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data1
0x18002e435  mov     r11, qword ptr cs:FWPM_CONDITION_IP_PROTOCOL.Data4
0x18002e43c  mov     rsi, qword ptr cs:FWPM_CONDITION_IP_PROTOCOL.Data1
0x18002e443  mov     rdx, [rdi+0A0h]
0x18002e44a  inc     r15d
0x18002e44d  cmp     r15d, [rdx+70h]
0x18002e451  jb      loc_18002E387
0x18002e457  mov     ecx, [rbx+128h]
0x18002e45d  mov     r15d, 1
0x18002e463  mov     edx, [rdi+4]
0x18002e466  test    edx, edx
0x18002e468  jz      short loc_18002E486
0x18002e46a  sub     edx, 1
0x18002e46d  jz      short loc_18002E47D
0x18002e46f  cmp     edx, 1
0x18002e472  jnz     short loc_18002E493
0x18002e474  or      dword ptr [rbx+128h], 0Ch
0x18002e47b  jmp     short loc_18002E48D
0x18002e47d  or      dword ptr [rbx+128h], 4
0x18002e484  jmp     short loc_18002E48D
0x18002e486  or      dword ptr [rbx+128h], 8
0x18002e48d  mov     ecx, [rbx+128h]
0x18002e493  mov     rax, [rdi+0A0h]
0x18002e49a  lea     r8, [rbp+enumHandle]; enumHandle
0x18002e49e  xor     edx, edx; enumTemplate
0x18002e4a0  mov     dword ptr [rbp+arg_8], r13d
0x18002e4a4  or      ecx, [rax+20h]
0x18002e4a7  mov     [rbx+128h], ecx
0x18002e4ad  mov     rcx, r12; engineHandle
0x18002e4b0  call    cs:__imp_IkeextSaCreateEnumHandle0
0x18002e4b6  mov     esi, eax
0x18002e4b8  test    eax, eax
0x18002e4ba  jz      short loc_18002E528
0x18002e4bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e4c3  lea     rbx, WPP_GLOBAL_Control
0x18002e4ca  cmp     rcx, rbx
0x18002e4cd  jz      loc_18002E68B
0x18002e4d3  test    byte ptr [rcx+1Ch], 10h
0x18002e4d7  jz      short loc_18002E4F8
0x18002e4d9  mov     rcx, [rcx+10h]
0x18002e4dd  lea     r8, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids
0x18002e4e4  mov     edx, 1Fh
0x18002e4e9  mov     r9d, eax
0x18002e4ec  call    WPP_SF_d
0x18002e4f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e4f8  cmp     rcx, rbx
0x18002e4fb  jz      loc_18002E68B
0x18002e501  test    byte ptr [rcx+1Ch], 10h
0x18002e505  jz      loc_18002E68B
0x18002e50b  mov     edx, 20h ; ' '
0x18002e510  mov     r9d, esi
0x18002e513  mov     rcx, [rcx+10h]
0x18002e517  lea     r8, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids
0x18002e51e  call    WPP_SF_d
0x18002e523  jmp     loc_18002E68B
0x18002e528  mov     rdx, [rbp+enumHandle]; enumHandle
0x18002e52c  lea     rax, [rbp+arg_8]
0x18002e530  lea     r9, [rbp+entries]; entries
0x18002e534  mov     [rsp+30h+numEntriesReturned], rax; numEntriesReturned
0x18002e539  mov     r8d, 7FFFFFFFh; numEntriesRequested
0x18002e53f  mov     rcx, r12; engineHandle
0x18002e542  call    cs:__imp_IkeextSaEnum0
0x18002e548  mov     esi, eax
0x18002e54a  test    eax, eax
0x18002e54c  jz      short loc_18002E579
0x18002e54e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e555  lea     rbx, WPP_GLOBAL_Control
0x18002e55c  cmp     rcx, rbx
0x18002e55f  jz      loc_18002E68B
0x18002e565  test    byte ptr [rcx+1Ch], 10h
0x18002e569  jz      loc_18002E68B
0x18002e56f  mov     edx, 21h ; '!'
0x18002e574  mov     r9d, eax
0x18002e577  jmp     short loc_18002E513
0x18002e579  mov     r9, [rbp+entries]
0x18002e57d  mov     edx, r13d
0x18002e580  cmp     edx, dword ptr [rbp+arg_8]
0x18002e583  jnb     short loc_18002E5C2
0x18002e585  mov     r8d, edx
0x18002e588  mov     rax, [r9+r8*8]
0x18002e58c  mov     rcx, [rax]
0x18002e58f  cmp     [rdi+88h], rcx
0x18002e596  jz      short loc_18002E59D
0x18002e598  add     edx, r15d
0x18002e59b  jmp     short loc_18002E580
0x18002e59d  lfence
0x18002e5a0  mov     rdx, [rbp+entries]
0x18002e5a4  mov     rax, [rdx+r8*8]
  ... truncated ...
```
