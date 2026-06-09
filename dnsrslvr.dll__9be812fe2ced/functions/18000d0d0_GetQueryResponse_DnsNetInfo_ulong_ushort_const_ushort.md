# GetQueryResponse(_DnsNetInfo *,ulong,ushort const *,ushort)

- ea: `0x18000d0d0`
- end: `0x18000d920`
- name: `?GetQueryResponse@@YAPEAU_DnsRecordW@@PEAU_DnsNetInfo@@KPEBGG@Z`
- size: `2128`
- prototype: `struct _DnsRecordW *__fastcall(struct _DnsNetInfo *, unsigned int, const unsigned __int16 *, unsigned __int16)`
- caller_count: `2`
- callee_count: `16`
- tags: ``

## callers

- `0x180015f3c`
- `0x18001623c`

## callees

- `0x18000b430`
- `0x18000cc80`
- `0x18000d0d0`
- `0x18000f390`
- `0x180015760`
- `0x18001af2c`
- `0x18001af4c`
- `0x18001bb00`
- `0x180033ad0`
- `0x180046ec0`
- `0x180047818`
- `0x180085fb8`
- `0x180086010`
- `0x180086384`
- `0x180086b1c`
- `0x180086e44`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18000d4d3`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18000d4fe`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18000d647`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18000d672`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18000d4d3`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18000d4fe`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18000d647`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18000d672`
- `DNSAPI!DnsRecordCopyEx` at `0x18000d22d`
- `DNSAPI!DnsRecordCopyEx` at `0x18000d22d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d351`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d351`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d15e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d15e`

## pseudocode

```c
struct _DnsRecordW *__fastcall GetQueryResponse(
        struct _DnsNetInfo *a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        unsigned __int16 a4)
{
  __int64 *appended; // r15
  int v7; // r14d
  unsigned int v8; // r8d
  const unsigned __int16 *v9; // rdx
  MDnsTree *v10; // r13
  struct MDnsTree *v11; // rdi
  __int64 v12; // rcx
  __int64 v13; // r8
  wchar_t *v14; // r9
  wchar_t *v15; // rcx
  DNS_RECORDA *v16; // rcx
  PDNS_RECORD v17; // rax
  struct MDnsTree *v18; // r13
  __int64 v19; // rcx
  const unsigned __int16 *v20; // rdx
  __int64 v21; // r8
  wchar_t *v22; // r9
  wchar_t *v23; // rcx
  __int64 v24; // rdi
  __int64 v25; // rbx
  MDnsTree *v26; // rsi
  int v27; // ecx
  unsigned __int16 v29; // r9
  _QWORD *v30; // r14
  struct MDnsTree *NodeUp; // rax
  struct _DnsRecordW *v32; // rcx
  struct _DnsRecordW **p_pNext; // r8
  __int64 *v34; // rdx
  __int64 *v35; // rcx
  unsigned int v36; // ebx
  wchar_t *v37; // rax
  __int64 v38; // rcx
  unsigned __int16 *v39; // rdi
  __int64 v40; // rsi
  unsigned __int64 v41; // rdx
  __int64 v42; // r8
  unsigned __int16 *v43; // r9
  unsigned __int16 *v44; // r10
  __int64 v45; // r11
  unsigned __int16 *v46; // rcx
  int v47; // ecx
  __int64 v48; // rax
  unsigned int LocalAandAAAARecords; // eax
  unsigned int v50; // ebx
  wchar_t *v51; // rax
  __int64 v52; // rcx
  unsigned __int16 *v53; // rdi
  __int64 v54; // rsi
  unsigned __int64 v55; // r9
  __int64 v56; // rdx
  unsigned __int16 *v57; // r8
  unsigned __int16 *v58; // r10
  __int64 v59; // r11
  unsigned __int16 *v60; // rcx
  int v61; // ecx
  __int64 v62; // rax
  MDnsTree *v63; // rcx
  int v64; // eax
  __int64 PtrTypeRecord; // rax
  struct MDnsTree *Node; // rax
  unsigned int v67; // [rsp+28h] [rbp-E0h]
  struct _DnsRecordW *v69; // [rsp+50h] [rbp-B8h] BYREF
  MDnsTree *v70; // [rsp+58h] [rbp-B0h]
  wchar_t *Context; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD v72[26]; // [rsp+68h] [rbp-A0h] BYREF
  wchar_t String[256]; // [rsp+138h] [rbp+30h] BYREF
  unsigned __int16 v74[256]; // [rsp+338h] [rbp+230h] BYREF
  unsigned __int16 v75[256]; // [rsp+538h] [rbp+430h] BYREF

  appended = 0;
  v7 = a4;
  v8 = a2;
  v69 = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    WPP_SF_dSd(1035, 78, (unsigned int)WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids, a2, (__int64)a3, a4);
    v8 = a2;
  }
  if ( a1 )
  {
    if ( v7 == 1 )
    {
      v29 = 2;
    }
    else if ( v7 == 28 )
    {
      v29 = 23;
    }
    else
    {
      if ( (_WORD)v7 != 255 )
        goto LABEL_6;
      v29 = 0;
    }
    LocalAandAAAARecords = MDnsGetLocalAandAAAARecords(a1, a3, v8, v29, v67, &v69);
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_d(1035, 79, WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids, LocalAandAAAARecords);
  }
  if ( v7 != 1 && v7 != 28 )
  {
LABEL_6:
    EnterCriticalSection(&g_csMdnsTree);
    v10 = g_MDnsTree;
    v70 = g_MDnsTree;
    if ( !g_MDnsTree )
    {
LABEL_44:
      LeaveCriticalSection(&g_csMdnsTree);
      goto LABEL_45;
    }
    v11 = 0;
    v74[0] = 0;
    if ( a3 )
    {
      Context = 0;
      memset_0(v72, 0, 0xC8u);
      v12 = 2147483646;
      String[0] = 0;
      v9 = a3;
      v74[1] = 0;
      v13 = 256;
      v14 = String;
      do
      {
        if ( !v12 )
          break;
        if ( !*v9 )
          break;
        *v14++ = *v9++;
        --v12;
        --v13;
      }
      while ( v13 );
      v15 = v14 - 1;
      if ( v13 )
        v15 = v14;
      *v15 = 0;
      if ( v13 )
      {
        v36 = 0;
        v37 = wcstok_s(String, L".", &Context);
        if ( v37 )
        {
          do
          {
            if ( v36 >= 0x19 )
              break;
            v38 = v36++;
            v72[v38] = v37;
            v37 = wcstok_s(0, L".", &Context);
          }
          while ( v37 );
          if ( v36 )
          {
            v39 = v74;
            v40 = 1;
            while ( v36 )
            {
              v41 = 256 - v40;
              if ( v40 == 256 )
                goto LABEL_69;
              if ( v41 > 0x7FFFFFFF )
              {
                *v39 = 0;
LABEL_69:
                appended = 0;
                goto LABEL_24;
              }
              v42 = 2147483646;
              v43 = (unsigned __int16 *)v72[v36 - 1];
              v44 = v39;
              v45 = 0;
              do
              {
                if ( !v42 )
                  break;
                if ( !*v43 )
                  break;
                *v44++ = *v43++;
                --v42;
                ++v45;
                --v41;
              }
              while ( v41 );
              v46 = v44 - 1;
              if ( v41 )
                v46 = v44;
              *v46 = 0;
              v47 = -2147024774;
              if ( v41 )
                v47 = 0;
              v48 = v45 - 1;
              if ( v41 )
                v48 = v45;
              if ( v47 < 0 )
                goto LABEL_69;
              v39 += v48 + 1;
              v40 += ((2 * v48) >> 1) + 1;
              --v36;
            }
            *v39 = 0;
            v11 = MDnsTree::InternalLookup(v10, v74, a2);
          }
        }
      }
    }
    appended = 0;
    if ( v11 )
    {
      v16 = (DNS_RECORDA *)*((_QWORD *)v11 + 2);
      if ( (_WORD)v7 == 255 )
      {
        if ( !v16 )
        {
LABEL_49:
          v25 = 0;
          if ( (_WORD)v7 != 255 )
          {
LABEL_42:
            if ( g_fVelocityDnsKernelApi )
            {
              appended = (__int64 *)Dns_RecordListAppend_New(appended, v25);
            }
            else if ( v25 )
            {
              if ( appended )
              {
                v34 = (__int64 *)*appended;
                v35 = appended;
                if ( *appended )
                {
                  do
                  {
                    v35 = v34;
                    v34 = (__int64 *)*v34;
                  }
                  while ( v34 );
                }
                *v35 = v25;
              }
              else
              {
                appended = (__int64 *)v25;
              }
            }
            goto LABEL_44;
          }
LABEL_25:
          if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
            WPP_SF_SD(1035, 16, (unsigned int)WPP_9bfce7e00caf33ebc3e9c882382e7196_Traceguids, (_DWORD)a3, a2);
          v75[0] = 0;
          v18 = 0;
          if ( !a3 )
            goto LABEL_35;
          Context = 0;
          memset_0(v72, 0, 0xC8u);
          v19 = 2147483646;
          String[0] = 0;
          v20 = a3;
          v75[1] = 0;
          v21 = 256;
          v22 = String;
          do
          {
            if ( !v19 )
              break;
            if ( !*v20 )
              break;
            *v22++ = *v20++;
            --v19;
            --v21;
          }
          while ( v21 );
          v23 = v22 - 1;
          if ( v21 )
            v23 = v22;
          *v23 = 0;
          if ( !v21 )
            goto LABEL_35;
          v50 = 0;
          v51 = wcstok_s(String, L".", &Context);
          if ( !v51 )
            goto LABEL_35;
          do
          {
            if ( v50 >= 0x19 )
              break;
            v52 = v50++;
            v72[v52] = v51;
            v51 = wcstok_s(0, L".", &Context);
          }
          while ( v51 );
          if ( v50 )
          {
            v53 = v75;
            v54 = 1;
            while ( 1 )
            {
              if ( !v50 )
              {
                v63 = v70;
                *v53 = 0;
                v18 = MDnsTree::InternalLookup(v63, v75, a2);
                goto LABEL_35;
              }
              v55 = 256 - v54;
              if ( v54 == 256 )
                break;
              if ( v55 > 0x7FFFFFFF )
              {
                *v53 = 0;
                break;
              }
              v56 = 2147483646;
              v57 = (unsigned __int16 *)v72[v50 - 1];
              v58 = v53;
              v59 = 0;
              do
              {
                if ( !v56 )
                  break;
                if ( !*v57 )
                  break;
                *v58++ = *v57++;
                --v56;
                ++v59;
                --v55;
              }
              while ( v55 );
              v60 = v58 - 1;
              if ( v55 )
                v60 = v58;
              *v60 = 0;
              v61 = -2147024774;
              if ( v55 )
                v61 = 0;
              v62 = v59 - 1;
              if ( v55 )
                v62 = v59;
              if ( v61 < 0 )
                break;
              v53 += v62 + 1;
              v54 += ((2 * v62) >> 1) + 1;
              --v50;
            }
            v24 = 0;
            v25 = 0;
          }
          else
          {
LABEL_35:
            if ( v18 )
            {
              v30 = 0;
              v26 = (MDnsTree *)*((_QWORD *)v18 + 5);
              if ( !v26 )
              {
                v26 = (MDnsTree *)*((_QWORD *)v18 + 4);
                if ( !v26 )
                {
                  NodeUp = MDnsTree::NextNodeUp(v18, v18);
                  goto LABEL_72;
                }
              }
              do
              {
                NodeUp = (struct MDnsTree *)*((_QWORD *)v26 + 5);
                if ( !NodeUp )
                  break;
LABEL_72:
                v26 = NodeUp;
              }
              while ( NodeUp );
              v24 = 0;
              while ( 1 )
              {
                if ( !v26 )
                {
                  v25 = v24;
                  v24 = 0;
                  goto LABEL_40;
                }
                if ( !a2 || (v64 = *((_DWORD *)v26 + 14)) == 0 || v64 == a2 )
                {
                  v25 = 0;
                  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
                    WPP_SF_S(1035, 18, WPP_9bfce7e00caf33ebc3e9c882382e7196_Traceguids, *(_QWORD *)v26);
                  if ( *((_QWORD *)v26 + 2) && *((_DWORD *)v26 + 19) )
                  {
                    PtrTypeRecord = Dns_CreatePtrTypeRecord(a3, 4500);
                    if ( !PtrTypeRecord )
                    {
                      LODWORD(v26) = 14;
                      goto LABEL_40;
                    }
                    *(_DWORD *)(PtrTypeRecord + 20) &= 0xFFFFFFED;
                    *(_DWORD *)(PtrTypeRecord + 20) |= 9u;
                    if ( v24 && v30 )
                      *v30 = PtrTypeRecord;
                    else
                      v24 = PtrTypeRecord;
                    v30 = (_QWORD *)PtrTypeRecord;
                  }
                }
                Node = (struct MDnsTree *)*((_QWORD *)v26 + 5);
                if ( !Node )
                {
                  Node = (struct MDnsTree *)*((_QWORD *)v26 + 4);
                  if ( !Node )
                    Node = MDnsTree::NextNodeUp(v26, v18);
                }
                while ( 1 )
                {
                  v26 = Node;
                  if ( !Node || !*((_QWORD *)Node + 5) )
                    break;
                  Node = MDnsTree::NextNode(Node, v18);
                }
              }
            }
            v24 = 0;
            v25 = 0;
          }
          if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
            WPP_SF_S(1035, 17, WPP_9bfce7e00caf33ebc3e9c882382e7196_Traceguids, a3);
          LODWORD(v26) = 1168;
LABEL_40:
          Dns_RecordFree(v24);
          if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
            WPP_SF_Dq(v27, 19, (unsigned int)WPP_9bfce7e00caf33ebc3e9c882382e7196_Traceguids, (_DWORD)v26, v25);
          goto LABEL_42;
        }
        v17 = (PDNS_RECORD)Dns_RecordListCopyEx(v16, v9, 1);
LABEL_22:
        if ( v17 )
        {
          v17->Flags.DW &= 0xFFFFFFED;
          appended = (__int64 *)v17;
          v17->Flags.DW |= 9u;
          v17->pNext = 0;
        }
      }
      else
      {
        while ( v16 )
        {
          if ( (_WORD)v7 == v16->wType )
          {
            v17 = DnsRecordCopyEx(v16, DnsCharSetUnicode, DnsCharSetUnicode);
            goto LABEL_22;
          }
          v16 = v16->pNext;
        }
      }
    }
LABEL_24:
    if ( v7 == 12 )
      goto LABEL_25;
    goto LABEL_49;
  }
LABEL_45:
  if ( g_fVelocityDnsKernelApi )
    return (struct _DnsRecordW *)Dns_RecordListAppend_New(appended, v69);
  if ( !v69 )
    return (struct _DnsRecordW *)appended;
  if ( appended )
  {
    v32 = (struct _DnsRecordW *)*appended;
    if ( *appended )
    {
      do
      {
        p_pNext = &v32->pNext;
        v32 = v32->pNext;
      }
      while ( v32 );
    }
    else
    {
      p_pNext = (struct _DnsRecordW **)appended;
    }
    *p_pNext = v69;
    return (struct _DnsRecordW *)appended;
  }
  return v69;
}

```

## disassembly

```asm
0x18000d0d0  mov     r11, rsp
0x18000d0d3  push    rbp
0x18000d0d4  push    r15
0x18000d0d6  lea     rbp, [r11-678h]
0x18000d0dd  sub     rsp, 768h
0x18000d0e4  mov     rax, cs:__security_cookie
0x18000d0eb  xor     rax, rsp
0x18000d0ee  mov     [rbp+670h+var_40], rax
0x18000d0f5  mov     [r11+20h], rbx
0x18000d0f9  mov     rbx, rcx
0x18000d0fc  mov     [r11-18h], rsi
0x18000d100  xor     esi, esi
0x18000d102  mov     [r11-28h], r12
0x18000d106  mov     r15d, esi
0x18000d109  mov     [r11-38h], r14
0x18000d10d  mov     r12, r8
0x18000d110  movzx   r14d, r9w
0x18000d114  mov     r8d, edx; unsigned int
0x18000d117  mov     [rsp+770h+var_728], rsi
0x18000d11c  mov     [rsp+770h+var_730], edx
0x18000d120  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18000d127  jnz     loc_18000D85E
0x18000d12d  mov     eax, 0FFh
0x18000d132  test    rbx, rbx
0x18000d135  jnz     loc_18000D3D1
0x18000d13b  cmp     r14d, 1
0x18000d13f  jz      loc_18000D35F
0x18000d145  cmp     r14d, 1Ch
0x18000d149  jz      loc_18000D35F
0x18000d14f  lea     rcx, ?g_csMdnsTree@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d156  mov     [rsp+770h+var_28], r13
0x18000d15e  call    cs:__imp_EnterCriticalSection
0x18000d164  mov     r13, cs:?g_MDnsTree@@3PEAVMDnsTree@@EA; MDnsTree * g_MDnsTree
0x18000d16b  mov     [rsp+770h+var_720], r13
0x18000d170  test    r13, r13
0x18000d173  jz      loc_18000D34A
0x18000d179  mov     [rsp+770h+var_18], rdi
0x18000d181  mov     rdi, rsi
0x18000d184  mov     [rbp+670h+var_440], si
0x18000d18b  test    r12, r12
0x18000d18e  jz      short loc_18000D1FA
0x18000d190  xor     edx, edx; Val
0x18000d192  mov     [rsp+770h+Context], rsi
0x18000d197  mov     r8d, 0C8h; Size
0x18000d19d  lea     rcx, [rsp+770h+var_710]; void *
0x18000d1a2  call    memset_0
0x18000d1a7  mov     ecx, 7FFFFFFEh
0x18000d1ac  mov     [rbp+670h+String], si
0x18000d1b0  mov     rdx, r12
0x18000d1b3  mov     [rbp+670h+var_43E], si
0x18000d1ba  mov     r8d, 100h
0x18000d1c0  lea     r9, [rbp+670h+String]
0x18000d1c4  test    rcx, rcx
0x18000d1c7  jz      short loc_18000D1E6
0x18000d1c9  movzx   eax, word ptr [rdx]
0x18000d1cc  test    ax, ax
0x18000d1cf  jz      short loc_18000D1E6
0x18000d1d1  mov     [r9], ax
0x18000d1d5  add     rdx, 2
0x18000d1d9  add     r9, 2
0x18000d1dd  dec     rcx
0x18000d1e0  sub     r8, 1
0x18000d1e4  jnz     short loc_18000D1C4
0x18000d1e6  test    r8, r8
0x18000d1e9  lea     rcx, [r9-2]
0x18000d1ed  cmovnz  rcx, r9
0x18000d1f1  mov     [rcx], si
0x18000d1f4  jnz     loc_18000D4C1
0x18000d1fa  mov     r15, rsi
0x18000d1fd  test    rdi, rdi
0x18000d200  jz      loc_18000D49B
0x18000d206  mov     rcx, [rdi+10h]; pRecord
0x18000d20a  mov     edi, 0FFh
0x18000d20f  cmp     r14w, di
0x18000d213  jz      short loc_18000D235
0x18000d215  test    rcx, rcx
0x18000d218  jz      short loc_18000D25C
0x18000d21a  cmp     r14w, [rcx+10h]
0x18000d21f  jnz     loc_18000D3B7
0x18000d225  mov     edx, 1; CharSetIn
0x18000d22a  mov     r8d, edx; CharSetOut
0x18000d22d  call    cs:__imp_DnsRecordCopyEx
0x18000d233  jmp     short loc_18000D249
0x18000d235  test    rcx, rcx
0x18000d238  jz      loc_18000D3BF
0x18000d23e  mov     r8d, 1
0x18000d244  call    Dns_RecordListCopyEx
0x18000d249  test    rax, rax
0x18000d24c  jz      short loc_18000D25C
0x18000d24e  and     dword ptr [rax+14h], 0FFFFFFEDh
0x18000d252  mov     r15, rax
0x18000d255  or      dword ptr [rax+14h], 9
0x18000d259  mov     [rax], rsi
0x18000d25c  cmp     r14d, 0Ch
0x18000d260  jnz     loc_18000D3BF
0x18000d266  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18000d26d  mov     r14d, [rsp+770h+var_730]
0x18000d272  jnz     loc_18000D8B3
0x18000d278  mov     [rbp+670h+var_240], si
0x18000d27f  mov     r13, rsi
0x18000d282  test    r12, r12
0x18000d285  jz      short loc_18000D2F6
0x18000d287  xor     edx, edx; Val
0x18000d289  mov     [rsp+770h+Context], rsi
0x18000d28e  mov     r8d, 0C8h; Size
0x18000d294  lea     rcx, [rsp+770h+var_710]; void *
0x18000d299  call    memset_0
0x18000d29e  mov     ecx, 7FFFFFFEh
0x18000d2a3  mov     [rbp+670h+String], si
0x18000d2a7  mov     rdx, r12
0x18000d2aa  mov     [rbp+670h+var_23E], si
0x18000d2b1  mov     r8d, 100h
0x18000d2b7  lea     r9, [rbp+670h+String]
0x18000d2bb  nop     dword ptr [rax+rax+00h]
0x18000d2c0  test    rcx, rcx
0x18000d2c3  jz      short loc_18000D2E2
0x18000d2c5  movzx   eax, word ptr [rdx]
0x18000d2c8  test    ax, ax
0x18000d2cb  jz      short loc_18000D2E2
0x18000d2cd  mov     [r9], ax
0x18000d2d1  add     rdx, 2
0x18000d2d5  add     r9, 2
0x18000d2d9  dec     rcx
0x18000d2dc  sub     r8, 1
0x18000d2e0  jnz     short loc_18000D2C0
0x18000d2e2  test    r8, r8
0x18000d2e5  lea     rcx, [r9-2]
0x18000d2e9  cmovnz  rcx, r9
0x18000d2ed  mov     [rcx], si
0x18000d2f0  jnz     loc_18000D635
0x18000d2f6  test    r13, r13
0x18000d2f9  jnz     loc_18000D3F7
0x18000d2ff  mov     rdi, rsi
0x18000d302  mov     rbx, rsi
0x18000d305  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18000d30c  jnz     loc_18000D88B
0x18000d312  mov     esi, 490h
0x18000d317  mov     rcx, rdi
0x18000d31a  call    Dns_RecordFree
0x18000d31f  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18000d326  jnz     loc_18000D902
0x18000d32c  cmp     cs:g_fVelocityDnsKernelApi, 0
0x18000d333  mov     rdi, [rsp+770h+var_18]
0x18000d33b  jnz     loc_18000D820
0x18000d341  test    rbx, rbx
0x18000d344  jnz     loc_18000D466
0x18000d34a  lea     rcx, ?g_csMdnsTree@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d351  call    cs:__imp_LeaveCriticalSection
0x18000d357  mov     r13, [rsp+770h+var_28]
0x18000d35f  cmp     cs:g_fVelocityDnsKernelApi, 0
0x18000d366  mov     rdx, [rsp+770h+var_728]
0x18000d36b  mov     r14, [rsp+770h+var_30]
0x18000d373  mov     r12, [rsp+770h+var_20]
0x18000d37b  mov     rsi, [rsp+760h]
0x18000d383  mov     rbx, [rsp+770h+arg_18]
0x18000d38b  jnz     loc_18000D813
0x18000d391  test    rdx, rdx
0x18000d394  jnz     loc_18000D432
0x18000d39a  mov     rax, r15
0x18000d39d  mov     rcx, [rbp+670h+var_40]
0x18000d3a4  xor     rcx, rsp; StackCookie
0x18000d3a7  call    __security_check_cookie
0x18000d3ac  add     rsp, 768h
0x18000d3b3  pop     r15
0x18000d3b5  pop     rbp
0x18000d3b6  retn
0x18000d3b7  mov     rcx, [rcx]
0x18000d3ba  jmp     loc_18000D215
0x18000d3bf  mov     rbx, rsi
0x18000d3c2  cmp     r14w, di
0x18000d3c6  jnz     loc_18000D32C
0x18000d3cc  jmp     loc_18000D266
0x18000d3d1  cmp     r14d, 1
0x18000d3d5  jz      loc_18000D5C6
0x18000d3db  cmp     r14d, 1Ch
0x18000d3df  jz      loc_18000D60C
0x18000d3e5  cmp     r14w, ax
0x18000d3e9  jnz     loc_18000D14F
0x18000d3ef  mov     r9d, esi
0x18000d3f2  jmp     loc_18000D5CC
0x18000d3f7  mov     r14, rsi
0x18000d3fa  mov     rsi, [r13+28h]
0x18000d3fe  test    rsi, rsi
0x18000d401  jnz     short loc_18000D410
0x18000d403  mov     rsi, [r13+20h]
0x18000d407  test    rsi, rsi
0x18000d40a  jz      loc_18000D4A5
0x18000d410  mov     rax, [rsi+28h]
0x18000d414  test    rax, rax
0x18000d417  jnz     loc_18000D4B0
0x18000d41d  xor     edi, edi
0x18000d41f  test    rsi, rsi
0x18000d422  jnz     loc_18000D770
0x18000d428  mov     rbx, rdi
0x18000d42b  xor     edi, edi
0x18000d42d  jmp     loc_18000D317
0x18000d432  test    r15, r15
0x18000d435  jz      loc_18000D758
0x18000d43b  mov     rcx, [r15]
0x18000d43e  test    rcx, rcx
0x18000d441  jz      loc_18000D768
0x18000d447  nop     word ptr [rax+rax+00000000h]
0x18000d450  mov     rax, [rcx]
0x18000d453  mov     r8, rcx
0x18000d456  mov     rcx, rax
0x18000d459  test    rax, rax
0x18000d45c  jnz     short loc_18000D450
0x18000d45e  mov     [r8], rdx
0x18000d461  jmp     loc_18000D39A
0x18000d466  test    r15, r15
0x18000d469  jz      loc_18000D760
0x18000d46f  mov     rdx, [r15]
0x18000d472  mov     rcx, r15
0x18000d475  test    rdx, rdx
0x18000d478  jz      short loc_18000D48E
0x18000d47a  nop     word ptr [rax+rax+00h]
0x18000d480  mov     rax, [rdx]
0x18000d483  mov     rcx, rdx
0x18000d486  mov     rdx, rax
0x18000d489  test    rax, rax
0x18000d48c  jnz     short loc_18000D480
0x18000d48e  mov     [rcx], rbx
0x18000d491  jmp     loc_18000D34A
0x18000d496  xor     esi, esi
0x18000d498  mov     r15, rsi
0x18000d49b  mov     edi, 0FFh
0x18000d4a0  jmp     loc_18000D25C
0x18000d4a5  mov     rdx, r13; struct MDnsTree *
0x18000d4a8  mov     rcx, r13; this
0x18000d4ab  call    ?NextNodeUp@MDnsTree@@AEAAPEAV1@PEAV1@@Z; MDnsTree::NextNodeUp(MDnsTree *)
0x18000d4b0  mov     rsi, rax
0x18000d4b3  test    rsi, rsi
0x18000d4b6  jnz     loc_18000D410
0x18000d4bc  jmp     loc_18000D41D
0x18000d4c1  lea     r8, [rsp+770h+Context]; Context
0x18000d4c6  mov     ebx, esi
0x18000d4c8  lea     rdx, pszSrc; "."
0x18000d4cf  lea     rcx, [rbp+670h+String]; String
0x18000d4d3  call    cs:__imp_wcstok_s
0x18000d4d9  test    rax, rax
0x18000d4dc  jz      loc_18000D1FA
0x18000d4e2  cmp     ebx, 19h
0x18000d4e5  jnb     short loc_18000D509
0x18000d4e7  mov     ecx, ebx
0x18000d4e9  lea     r8, [rsp+770h+Context]; Context
0x18000d4ee  lea     rdx, pszSrc; "."
0x18000d4f5  inc     ebx
0x18000d4f7  mov     [rsp+rcx*8+770h+var_710], rax
0x18000d4fc  xor     ecx, ecx; String
0x18000d4fe  call    cs:__imp_wcstok_s
0x18000d504  test    rax, rax
0x18000d507  jnz     short loc_18000D4E2
0x18000d509  test    ebx, ebx
0x18000d50b  jz      loc_18000D1FA
0x18000d511  lea     rdi, [rbp+670h+var_440]
0x18000d518  mov     esi, 1
0x18000d51d  nop     dword ptr [rax]
0x18000d520  test    ebx, ebx
0x18000d522  jz      loc_18000D614
0x18000d528  mov     edx, 100h
0x18000d52d  sub     rdx, rsi
0x18000d530  jz      loc_18000D496
0x18000d536  cmp     rdx, 7FFFFFFFh
0x18000d53d  ja      loc_18000D8A9
0x18000d543  lea     eax, [rbx-1]
0x18000d546  mov     r8d, 7FFFFFFEh
0x18000d54c  mov     r9, [rsp+rax*8+770h+var_710]
0x18000d551  mov     r10, rdi
0x18000d554  xor     r11d, r11d
0x18000d557  test    r8, r8
0x18000d55a  jz      short loc_18000D57D
0x18000d55c  movzx   eax, word ptr [r9]
0x18000d560  test    ax, ax
0x18000d563  jz      short loc_18000D57D
0x18000d565  mov     [r10], ax
0x18000d569  add     r9, 2
0x18000d56d  add     r10, 2
0x18000d571  dec     r8
0x18000d574  inc     r11
0x18000d577  sub     rdx, 1
0x18000d57b  jnz     short loc_18000D557
0x18000d57d  test    rdx, rdx
0x18000d580  lea     rcx, [r10-2]
0x18000d584  cmovnz  rcx, r10
0x18000d588  xor     eax, eax
0x18000d58a  test    rdx, rdx
0x18000d58d  mov     [rcx], ax
0x18000d590  mov     ecx, 8007007Ah
0x18000d595  cmovnz  ecx, eax
0x18000d598  lea     rax, [r11-1]
0x18000d59c  cmovnz  rax, r11
0x18000d5a0  lea     rdx, [rdi+rax*2]
0x18000d5a4  test    ecx, ecx
0x18000d5a6  js      loc_18000D496
0x18000d5ac  inc     rsi
0x18000d5af  mov     rax, rdx
0x18000d5b2  sub     rax, rdi
0x18000d5b5  lea     rdi, [rdx+2]
0x18000d5b9  sar     rax, 1
0x18000d5bc  add     rsi, rax
  ... truncated ...
```
