# Dns_RegisterLocal

- ea: `0x1800aaa24`
- end: `0x1800ab044`
- name: `Dns_RegisterLocal`
- size: `1568`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800568a0`
- `0x180096860`

## callees

- `0x180011d40`
- `0x180014e34`
- `0x180029d80`
- `0x18002b050`
- `0x180034d20`
- `0x18003de30`
- `0x18004e1d0`
- `0x180054880`
- `0x1800550d4`
- `0x1800657e0`
- `0x180068ad0`
- `0x180074624`
- `0x180077394`
- `0x180077638`
- `0x18008b194`
- `0x18008b1e0`
- `0x18008b5f0`
- `0x18008bf98`
- `0x1800aaa24`
- `0x1800b6120`
- `0x1800b8b60`
- `0x1800dc9e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_qsort_s` at `0x1800aabc0`
- `api-ms-win-crt-private-l1-1-0!_o_qsort_s` at `0x1800aabc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aacd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aacd5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800aacc0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800aacc0`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800aad8f`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800aad8f`
- `IPHLPAPI!GetIfEntry2Ex` at `0x1800aaaa3`
- `IPHLPAPI!GetIfEntry2Ex` at `0x1800aaaa3`

## pseudocode

```c
__int64 __fastcall Dns_RegisterLocal(__int64 a1, _QWORD *a2, unsigned int a3, int a4, __int64 a5, void **a6)
{
  _QWORD *v8; // r13
  __int64 v9; // r15
  _QWORD *v10; // r14
  unsigned __int64 v11; // rdx
  _QWORD *j; // r12
  DWORD LastError; // ebx
  _QWORD *v14; // rax
  _QWORD *v15; // rax
  _QWORD *v16; // rax
  __int64 v17; // rbx
  _QWORD *v18; // rcx
  __int64 v19; // rdi
  __int64 v20; // rbx
  unsigned __int16 *v21; // rax
  unsigned int v22; // eax
  DWORD v23; // eax
  __int64 v24; // rax
  __int64 v25; // rdi
  int v26; // esi
  BOOL v27; // r12d
  unsigned int i; // edi
  unsigned __int64 v29; // rax
  int started; // eax
  DWORD v31; // eax
  unsigned int v32; // ebx
  unsigned int v33; // eax
  void *v34; // rbx
  __int64 v35; // rsi
  unsigned __int64 v36; // rdx
  unsigned int v37; // eax
  __int64 v38; // rax
  __int64 v39; // rcx
  __int64 v40; // rdx
  unsigned __int64 v41; // rdx
  __int64 k; // rdi
  BOOL v44; // [rsp+30h] [rbp-D0h]
  int v45; // [rsp+34h] [rbp-CCh]
  int v46; // [rsp+38h] [rbp-C8h]
  __int64 v49; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v50; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v51; // [rsp+58h] [rbp-A8h]
  _QWORD *v52; // [rsp+60h] [rbp-A0h]
  __int64 v53; // [rsp+68h] [rbp-98h]
  void **v54; // [rsp+70h] [rbp-90h]
  _QWORD *v55; // [rsp+78h] [rbp-88h]
  _BYTE v56[192]; // [rsp+80h] [rbp-80h] BYREF
  PVOID pData; // [rsp+140h] [rbp+40h] BYREF
  __int64 v58; // [rsp+148h] [rbp+48h] BYREF
  __int64 v59; // [rsp+150h] [rbp+50h]
  HANDLE Handles; // [rsp+158h] [rbp+58h] BYREF
  __int64 v61; // [rsp+160h] [rbp+60h]
  char v62[8]; // [rsp+170h] [rbp+70h] BYREF
  unsigned int v63; // [rsp+178h] [rbp+78h]
  _OWORD v64[102]; // [rsp+6C0h] [rbp+5C0h] BYREF

  v55 = a2;
  v53 = a1;
  v8 = 0;
  v54 = a6;
  pData = 0;
  LODWORD(v9) = 0;
  v10 = 0;
  memset_0(v62, 0, 0x548u);
  if ( a3 )
  {
    v63 = a3;
    if ( (unsigned int)GetIfEntry2Ex(2, v62) || !(unsigned int)MDns_IsInterfaceEligible(v62) )
    {
      j = 0;
      LastError = 1413;
      goto LABEL_77;
    }
  }
  v14 = (_QWORD *)Dns_RecordListCopyEx(a1, v11, (*(_DWORD *)(a1 + 20) >> 3) & 3, (*(_DWORD *)(a1 + 20) >> 3) & 3);
  v52 = v14;
  j = v14;
  if ( !v14 )
    goto LABEL_76;
  do
  {
    if ( !v14[1] )
      goto LABEL_76;
    v14 = (_QWORD *)*v14;
    v9 = (unsigned int)(v9 + 1);
  }
  while ( v14 );
  if ( !(_DWORD)v9 )
  {
LABEL_76:
    LastError = 87;
    goto LABEL_77;
  }
  v15 = operator new[](saturated_mul((unsigned int)v9, 8u));
  v50 = (unsigned __int64)v15;
  v8 = v15;
  if ( !v15
    || (memset_0(v15, 0, 8 * v9), v16 = operator new[](saturated_mul((unsigned int)v9, 8u)), v51 = v16, (v10 = v16) == 0) )
  {
LABEL_10:
    LastError = 14;
    goto LABEL_77;
  }
  v17 = 0;
  memset_0(v16, 0, 8 * v9);
  v18 = j;
  do
  {
    if ( (unsigned int)v17 >= (unsigned int)v9 )
      break;
    v8[v17] = v18;
    v17 = (unsigned int)(v17 + 1);
    v18 = (_QWORD *)*v18;
  }
  while ( v18 );
  qsort_s(v8, (unsigned int)v9, 8u, DnsRecCompare, 0);
  v19 = 0;
  while ( 1 )
  {
    v20 = v19;
    if ( !(_DWORD)v19
      || (unsigned int)wcsicmp_ThatWorks(*(PCNZWCH *)(v8[v20] + 8LL), *(PCNZWCH *)(v8[(unsigned int)(v19 - 1)] + 8LL)) )
    {
      break;
    }
    v10[v20] = 0;
LABEL_21:
    v19 = (unsigned int)(v19 + 1);
    if ( (unsigned int)v19 >= (unsigned int)v9 )
    {
      v24 = 0;
      v46 = 0;
      do
      {
        v25 = v10[v24];
        v49 = v25;
        if ( v25 )
        {
          v45 = 0;
          while ( 1 )
          {
            memset_0(v56, 0, sizeof(v56));
            memset_0(v64, 0, sizeof(v64));
            v61 = a5;
            v59 = 0;
            Handles = 0;
            LastError = 0;
            v58 = v25;
            Handles = CreateEventW(0, 0, 0, 0);
            if ( !Handles )
              LastError = GetLastError();
            if ( LastError )
              goto LABEL_55;
            v26 = 0;
            v27 = 0;
            for ( i = 0; i < 3; ++i )
            {
              if ( v26 )
                break;
              if ( v27 )
                break;
              v29 = (unsigned __int64)i << 6;
              *(_WORD *)&v56[v29 + 16] = 255;
              *(_QWORD *)&v56[v29 + 48] = &v58;
              *(_QWORD *)&v56[v29 + 8] = v49;
              *(_QWORD *)&v56[v29 + 40] = RegisterLocalParams::callback;
              *(_DWORD *)&v56[v29 + 32] = a3;
              *(_DWORD *)&v56[v29] = 1;
              started = DnsStartMulticastQueryImpl(
                          (struct _MDNS_QUERY_REQUEST *)&v56[v29],
                          (struct _MDNS_QUERY_HANDLE *)&v64[34 * i]);
              v45 = started;
              if ( started == 1222 )
                break;
              if ( !started )
              {
                v31 = WaitForMultipleObjects((v61 != 0) + 1, &Handles, 0, 0xFAu);
                if ( v31 )
                  v27 = v31 == 1;
                else
                  v26 = v59;
              }
            }
            v10 = v51;
            v32 = 0;
            v8 = (_QWORD *)v50;
            v44 = v27;
            for ( j = v52; v32 < i; ++v32 )
            {
              v33 = DnsStopMulticastQuery(&v64[34 * v32]);
              if ( v33 && (BYTE1(xmmword_1801119E0) & 8) != 0 )
                WPP_SF_d(1035, 34, WPP_acb40cfb6d3c3959d374627950e51c28_Traceguids, v33);
            }
            if ( v45 == 1222 )
              break;
            if ( v44 )
            {
              LastError = 1223;
LABEL_55:
              RegisterLocalParams::~RegisterLocalParams((RegisterLocalParams *)&v58);
              goto LABEL_77;
            }
            v25 = v49;
            if ( v26 )
            {
              LastError = MDns_IncrementName(v49, v49);
              if ( LastError )
                goto LABEL_55;
            }
            RegisterLocalParams::~RegisterLocalParams((RegisterLocalParams *)&v58);
            if ( !v26 )
              goto LABEL_49;
          }
          RegisterLocalParams::~RegisterLocalParams((RegisterLocalParams *)&v58);
        }
LABEL_49:
        v24 = (unsigned int)(v46 + 1);
        v46 = v24;
      }
      while ( (unsigned int)v24 < (unsigned int)v9 );
      v34 = 0;
      v35 = 0;
      while ( !v10[v35] )
      {
        if ( v34 )
          goto LABEL_58;
LABEL_63:
        v35 = (unsigned int)(v35 + 1);
        if ( (unsigned int)v35 >= (unsigned int)v9 )
        {
          pData = (PVOID)Dns_RecordListCopyEx(
                           j,
                           v11,
                           (*(_DWORD *)(v53 + 20) >> 3) & 3,
                           (*(_DWORD *)(v53 + 20) >> 3) & 3);
          if ( !pData )
            goto LABEL_76;
          LastError = MarshalDnsRecordListToRpcRecordList(&pData);
          if ( LastError )
            goto LABEL_77;
          v23 = DnsRegisterLocalRpc((struct _DnsRecordRpc *)pData, a3, a4, v54);
          LastError = v23;
          if ( !v23 )
          {
            if ( v55 )
            {
              *v55 = j;
              j = 0;
            }
            goto LABEL_77;
          }
          if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
            goto LABEL_77;
          v40 = 36;
LABEL_73:
          WPP_SF_d(1035, v40, WPP_acb40cfb6d3c3959d374627950e51c28_Traceguids, v23);
          goto LABEL_77;
        }
      }
      DnsApiFree(v34);
      v37 = StringCchLengthW((const unsigned __int16 *)v10[v35], v36, &v50);
      v23 = WX_WIN32_FROM_HR(v37);
      LastError = v23;
      if ( v23 )
      {
        if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
          goto LABEL_77;
        v40 = 35;
        goto LABEL_73;
      }
      v34 = (void *)v10[v35];
LABEL_58:
      v38 = Dns_StringCopyAllocate(v34, 0, 1, 1);
      v10[v35] = v38;
      if ( !v38 )
        goto LABEL_10;
      v39 = v8[v35];
      if ( v39 )
      {
        if ( (*(_DWORD *)(v39 + 20) & 0x2000) != 0 )
          DnsApiFree(*(LPVOID *)(v39 + 8));
        *(_DWORD *)(v8[v35] + 20LL) |= 0x2000u;
        *(_QWORD *)(v8[v35] + 8LL) = v10[v35];
        v10[v35] = 0;
      }
      goto LABEL_63;
    }
  }
  v21 = (unsigned __int16 *)Dns_Allocate(512);
  v10[v20] = v21;
  if ( !v21 )
    goto LABEL_10;
  v22 = StringCchCopyW(v21, 0x100u, *(const unsigned __int16 **)(v8[v20] + 8LL));
  v23 = WX_WIN32_FROM_HR(v22);
  LastError = v23;
  if ( !v23 )
    goto LABEL_21;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
  {
    v40 = 33;
    goto LABEL_73;
  }
LABEL_77:
  operator delete(v8, v11);
  for ( k = 0; (unsigned int)k < (unsigned int)v9; k = (unsigned int)(k + 1) )
    DnsApiFree((LPVOID)v10[k]);
  operator delete(v10, v41);
  DnsFree(pData, DnsFreeRecordList);
  if ( j )
    DnsFree(j, DnsFreeRecordList);
  return LastError;
}

```

## disassembly

```asm
0x1800aaa24  push    rbp
0x1800aaa26  push    rbx
0x1800aaa27  push    rsi
0x1800aaa28  push    rdi
0x1800aaa29  push    r12
0x1800aaa2b  push    r13
0x1800aaa2d  push    r14
0x1800aaa2f  push    r15
0x1800aaa31  lea     rbp, [rsp-0C38h]
0x1800aaa39  sub     rsp, 0D38h
0x1800aaa40  mov     rax, cs:__security_cookie
0x1800aaa47  xor     rax, rsp
0x1800aaa4a  mov     [rbp+0C70h+var_50], rax
0x1800aaa51  mov     rax, [rbp+0C70h+arg_28]
0x1800aaa58  mov     ebx, r8d
0x1800aaa5b  mov     [rsp+0D70h+var_CF8], rdx
0x1800aaa60  mov     rdi, rcx
0x1800aaa63  mov     [rsp+0D70h+var_D08], rcx
0x1800aaa68  xor     r13d, r13d
0x1800aaa6b  xor     edx, edx; Val
0x1800aaa6d  mov     [rsp+0D70h+var_D34], ebx
0x1800aaa71  mov     r8d, 548h; Size
0x1800aaa77  mov     [rsp+0D70h+var_D00], rax
0x1800aaa7c  lea     rcx, [rbp+0C70h+var_C00]; void *
0x1800aaa80  mov     [rbp+0C70h+pData], r13
0x1800aaa84  mov     [rsp+0D70h+var_D30], r9d
0x1800aaa89  xor     r15d, r15d
0x1800aaa8c  xor     r14d, r14d
0x1800aaa8f  call    memset_0
0x1800aaa94  test    ebx, ebx
0x1800aaa96  jz      short loc_1800AAACD
0x1800aaa98  lea     rdx, [rbp+0C70h+var_C00]
0x1800aaa9c  mov     [rbp+0C70h+var_BF8], ebx
0x1800aaa9f  lea     ecx, [r15+2]
0x1800aaaa3  call    cs:__imp_GetIfEntry2Ex
0x1800aaaaa  nop     dword ptr [rax+rax+00h]
0x1800aaaaf  test    eax, eax
0x1800aaab1  jnz     short loc_1800AAAC0
0x1800aaab3  lea     rcx, [rbp+0C70h+var_C00]
0x1800aaab7  call    MDns_IsInterfaceEligible
0x1800aaabc  test    eax, eax
0x1800aaabe  jnz     short loc_1800AAACD
0x1800aaac0  xor     r12d, r12d
0x1800aaac3  mov     ebx, 585h
0x1800aaac8  jmp     loc_1800AAFD7
0x1800aaacd  mov     r8d, [rdi+14h]
0x1800aaad1  mov     rcx, rdi
0x1800aaad4  shr     r8d, 3
0x1800aaad8  and     r8d, 3
0x1800aaadc  mov     r9d, r8d
0x1800aaadf  call    Dns_RecordListCopyEx
0x1800aaae4  mov     [rsp+0D70h+var_D10], rax
0x1800aaae9  mov     r12, rax
0x1800aaaec  test    rax, rax
0x1800aaaef  jz      loc_1800AAFD2
0x1800aaaf5  cmp     [rax+8], r13
0x1800aaaf9  jz      loc_1800AAFD2
0x1800aaaff  mov     rax, [rax]
0x1800aab02  inc     r15d
0x1800aab05  test    rax, rax
0x1800aab08  jnz     short loc_1800AAAF5
0x1800aab0a  test    r15d, r15d
0x1800aab0d  jz      loc_1800AAFD2
0x1800aab13  mov     edi, r15d
0x1800aab16  mov     eax, 8
0x1800aab1b  mul     rdi
0x1800aab1e  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800aab25  cmovb   rax, rbx
0x1800aab29  mov     rcx, rax; unsigned __int64
0x1800aab2c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800aab31  mov     [rsp+0D70h+var_D20], rax
0x1800aab36  mov     r13, rax
0x1800aab39  test    rax, rax
0x1800aab3c  jnz     short loc_1800AAB48
0x1800aab3e  mov     ebx, 0Eh
0x1800aab43  jmp     loc_1800AAFD7
0x1800aab48  lea     rsi, ds:0[r15*8]
0x1800aab50  xor     edx, edx; Val
0x1800aab52  mov     r8, rsi; Size
0x1800aab55  mov     rcx, r13; void *
0x1800aab58  call    memset_0
0x1800aab5d  mov     eax, 8
0x1800aab62  mul     rdi
0x1800aab65  cmovb   rax, rbx
0x1800aab69  mov     rcx, rax; unsigned __int64
0x1800aab6c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800aab71  mov     [rsp+0D70h+var_D18], rax
0x1800aab76  mov     r14, rax
0x1800aab79  test    rax, rax
0x1800aab7c  jz      short loc_1800AAB3E
0x1800aab7e  xor     ebx, ebx
0x1800aab80  mov     r8, rsi; Size
0x1800aab83  xor     edx, edx; Val
0x1800aab85  mov     rcx, rax; void *
0x1800aab88  call    memset_0
0x1800aab8d  mov     rcx, r12
0x1800aab90  cmp     ebx, r15d
0x1800aab93  jnb     short loc_1800AABA4
0x1800aab95  mov     [r13+rbx*8+0], rcx
0x1800aab9a  inc     ebx
0x1800aab9c  mov     rcx, [rcx]
0x1800aab9f  test    rcx, rcx
0x1800aaba2  jnz     short loc_1800AAB90
0x1800aaba4  lea     r9, ?DnsRecCompare@@YAHPEAXPEBX1@Z; CompareFunction
0x1800aabab  mov     [rsp+0D70h+Context], 0; Context
0x1800aabb4  mov     r8d, 8; SizeOfElements
0x1800aabba  mov     rdx, rdi; NumOfElements
0x1800aabbd  mov     rcx, r13; Base
0x1800aabc0  call    cs:__imp_qsort_s
0x1800aabc7  nop     dword ptr [rax+rax+00h]
0x1800aabcc  xor     edi, edi
0x1800aabce  test    r15d, r15d
0x1800aabd1  jz      loc_1800AAF27
0x1800aabd7  lea     rbx, ds:0[rdi*8]
0x1800aabdf  test    edi, edi
0x1800aabe1  jz      short loc_1800AAC0A
0x1800aabe3  mov     rcx, [rbx+r13]
0x1800aabe7  lea     eax, [rdi-1]
0x1800aabea  mov     rdx, [r13+rax*8+0]
0x1800aabef  mov     rcx, [rcx+8]; lpString1
0x1800aabf3  mov     rdx, [rdx+8]; lpString2
0x1800aabf7  call    wcsicmp_ThatWorks
0x1800aabfc  test    eax, eax
0x1800aabfe  jnz     short loc_1800AAC0A
0x1800aac00  mov     qword ptr [rbx+r14], 0
0x1800aac08  jmp     short loc_1800AAC47
0x1800aac0a  mov     ecx, 200h
0x1800aac0f  call    Dns_Allocate
0x1800aac14  mov     [rbx+r14], rax
0x1800aac18  test    rax, rax
0x1800aac1b  jz      loc_1800AAB3E
0x1800aac21  mov     r8, [rbx+r13]
0x1800aac25  mov     edx, 100h; unsigned __int64
0x1800aac2a  mov     rcx, rax; unsigned __int16 *
0x1800aac2d  mov     r8, [r8+8]; unsigned __int16 *
0x1800aac31  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800aac36  mov     ecx, eax
0x1800aac38  call    WX_WIN32_FROM_HR
0x1800aac3d  mov     ebx, eax
0x1800aac3f  test    eax, eax
0x1800aac41  jnz     loc_1800AAF9C
0x1800aac47  inc     edi
0x1800aac49  cmp     edi, r15d
0x1800aac4c  jb      short loc_1800AABD7
0x1800aac4e  xor     eax, eax
0x1800aac50  mov     [rsp+0D70h+var_D38], eax
0x1800aac54  mov     rdi, [r14+rax*8]
0x1800aac58  mov     [rsp+0D70h+var_D28], rdi
0x1800aac5d  test    rdi, rdi
0x1800aac60  jz      loc_1800AAE5C
0x1800aac66  xor     eax, eax
0x1800aac68  mov     [rsp+0D70h+var_D3C], eax
0x1800aac6c  mov     [rsp+0D70h+var_D40], eax
0x1800aac70  xor     edx, edx; Val
0x1800aac72  lea     rcx, [rbp+0C70h+var_CF0]; void *
0x1800aac76  mov     r8d, 0C0h; Size
0x1800aac7c  call    memset_0
0x1800aac81  xor     edx, edx; Val
0x1800aac83  lea     rcx, [rbp+0C70h+var_6B0]; void *
0x1800aac8a  mov     r8d, 660h; Size
0x1800aac90  call    memset_0
0x1800aac95  mov     rax, [rbp+0C70h+arg_20]
0x1800aac9c  xor     r9d, r9d; lpName
0x1800aac9f  xor     r8d, r8d; bInitialState
0x1800aaca2  mov     [rbp+0C70h+var_C10], rax
0x1800aaca6  xor     edx, edx; bManualReset
0x1800aaca8  mov     [rbp+0C70h+var_C20], 0
0x1800aacb0  xor     ecx, ecx; lpEventAttributes
0x1800aacb2  mov     [rbp+0C70h+Handles], 0
0x1800aacba  xor     ebx, ebx
0x1800aacbc  mov     [rbp+0C70h+var_C28], rdi
0x1800aacc0  call    cs:__imp_CreateEventW
0x1800aacc7  nop     dword ptr [rax+rax+00h]
0x1800aaccc  mov     [rbp+0C70h+Handles], rax
0x1800aacd0  test    rax, rax
0x1800aacd3  jnz     short loc_1800AACE3
0x1800aacd5  call    cs:__imp_GetLastError
0x1800aacdc  nop     dword ptr [rax+rax+00h]
0x1800aace1  mov     ebx, eax
0x1800aace3  test    ebx, ebx
0x1800aace5  jnz     loc_1800AAE8A
0x1800aaceb  mov     rbx, [rsp+0D70h+var_D28]
0x1800aacf0  xor     esi, esi
0x1800aacf2  mov     r12d, [rsp+0D70h+var_D40]
0x1800aacf7  xor     edi, edi
0x1800aacf9  mov     r14d, [rsp+0D70h+var_D34]
0x1800aacfe  test    esi, esi
0x1800aad00  jnz     loc_1800AADB7
0x1800aad06  test    r12d, r12d
0x1800aad09  jnz     loc_1800AADB7
0x1800aad0f  mov     ecx, 0FFh
0x1800aad14  mov     edx, edi
0x1800aad16  lea     r8, [rbp+0C70h+var_C28]
0x1800aad1a  mov     eax, edi
0x1800aad1c  shl     rax, 6
0x1800aad20  mov     [rbp+rax+0C70h+var_CE0], cx
0x1800aad25  lea     rcx, [rbp+0C70h+var_CF0]
0x1800aad29  mov     [rbp+rax+0C70h+var_CC0], r8
0x1800aad2e  add     rcx, rax; struct _MDNS_QUERY_REQUEST *
0x1800aad31  lea     r8, ?callback@RegisterLocalParams@@SAXPEAXPEAU_MDNS_QUERY_HANDLE@@PEAU_DNS_QUERY_RESULT@@@Z; RegisterLocalParams::callback(void *,_MDNS_QUERY_HANDLE *,_DNS_QUERY_RESULT *)
0x1800aad38  mov     [rbp+rax+0C70h+var_CE8], rbx
0x1800aad3d  mov     [rbp+rax+0C70h+var_CC8], r8
0x1800aad42  xor     r8d, r8d
0x1800aad45  mov     [rbp+rax+0C70h+var_CD0], r14d
0x1800aad4a  imul    rax, rdx, 220h
0x1800aad51  lea     rdx, [rbp+0C70h+var_6B0]
0x1800aad58  mov     dword ptr [rcx], 1
0x1800aad5e  add     rdx, rax; struct _MDNS_QUERY_HANDLE *
0x1800aad61  call    DnsStartMulticastQueryImpl
0x1800aad66  mov     [rsp+0D70h+var_D3C], eax
0x1800aad6a  cmp     eax, 4C6h
0x1800aad6f  jz      short loc_1800AADB7
0x1800aad71  test    eax, eax
0x1800aad73  jnz     short loc_1800AADAC
0x1800aad75  mov     rcx, [rbp+0C70h+var_C10]
0x1800aad79  lea     rdx, [rbp+0C70h+Handles]; lpHandles
0x1800aad7d  neg     rcx
0x1800aad80  mov     r9d, 0FAh; dwMilliseconds
0x1800aad86  sbb     ecx, ecx
0x1800aad88  xor     r8d, r8d; bWaitAll
0x1800aad8b  neg     ecx
0x1800aad8d  inc     ecx; nCount
0x1800aad8f  call    cs:__imp_WaitForMultipleObjects
0x1800aad96  nop     dword ptr [rax+rax+00h]
0x1800aad9b  test    eax, eax
0x1800aad9d  jz      short loc_1800AADA9
0x1800aad9f  cmp     eax, 1
0x1800aada2  jnz     short loc_1800AADAC
0x1800aada4  mov     r12d, eax
0x1800aada7  jmp     short loc_1800AADAC
0x1800aada9  mov     esi, dword ptr [rbp+0C70h+var_C20]
0x1800aadac  inc     edi
0x1800aadae  cmp     edi, 3
0x1800aadb1  jb      loc_1800AACFE
0x1800aadb7  mov     r14, [rsp+0D70h+var_D18]
0x1800aadbc  xor     ebx, ebx
0x1800aadbe  mov     r13, [rsp+0D70h+var_D20]
0x1800aadc3  mov     [rsp+0D70h+var_D40], r12d
0x1800aadc8  mov     r12, [rsp+0D70h+var_D10]
0x1800aadcd  test    edi, edi
0x1800aadcf  jz      short loc_1800AAE15
0x1800aadd1  mov     eax, ebx
0x1800aadd3  imul    rcx, rax, 220h
0x1800aadda  lea     rax, [rbp+0C70h+var_6B0]
0x1800aade1  add     rcx, rax
0x1800aade4  call    DnsStopMulticastQuery
0x1800aade9  test    eax, eax
0x1800aadeb  jz      short loc_1800AAE0F
0x1800aaded  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800aadf4  jz      short loc_1800AAE0F
0x1800aadf6  mov     edx, 22h ; '"'
0x1800aadfb  lea     r8, WPP_acb40cfb6d3c3959d374627950e51c28_Traceguids
0x1800aae02  mov     ecx, 40Bh
0x1800aae07  mov     r9d, eax
0x1800aae0a  call    WPP_SF_d
0x1800aae0f  inc     ebx
0x1800aae11  cmp     ebx, edi
0x1800aae13  jb      short loc_1800AADD1
0x1800aae15  cmp     [rsp+0D70h+var_D3C], 4C6h
0x1800aae1d  jz      short loc_1800AAE53
0x1800aae1f  cmp     [rsp+0D70h+var_D40], 0
0x1800aae24  jnz     short loc_1800AAE85
0x1800aae26  mov     rdi, [rsp+0D70h+var_D28]
0x1800aae2b  test    esi, esi
0x1800aae2d  jz      short loc_1800AAE40
0x1800aae2f  mov     rdx, rdi
0x1800aae32  mov     rcx, rdi
0x1800aae35  call    MDns_IncrementName
0x1800aae3a  mov     ebx, eax
0x1800aae3c  test    eax, eax
0x1800aae3e  jnz     short loc_1800AAE8A
0x1800aae40  lea     rcx, [rbp+0C70h+var_C28]; this
0x1800aae44  call    ??1RegisterLocalParams@@QEAA@XZ; RegisterLocalParams::~RegisterLocalParams(void)
0x1800aae49  test    esi, esi
0x1800aae4b  jnz     loc_1800AAC70
0x1800aae51  jmp     short loc_1800AAE5C
0x1800aae53  lea     rcx, [rbp+0C70h+var_C28]; this
0x1800aae57  call    ??1RegisterLocalParams@@QEAA@XZ; RegisterLocalParams::~RegisterLocalParams(void)
0x1800aae5c  mov     eax, [rsp+0D70h+var_D38]
0x1800aae60  inc     eax
0x1800aae62  mov     [rsp+0D70h+var_D38], eax
0x1800aae66  cmp     eax, r15d
0x1800aae69  jb      loc_1800AAC54
0x1800aae6f  xor     ebx, ebx
0x1800aae71  xor     esi, esi
0x1800aae73  cmp     qword ptr [r14+rsi*8], 0
0x1800aae78  jnz     short loc_1800AAE98
0x1800aae7a  test    rbx, rbx
0x1800aae7d  jz      loc_1800AAF1C
0x1800aae83  jmp     short loc_1800AAEC3
0x1800aae85  mov     ebx, 4C7h
0x1800aae8a  lea     rcx, [rbp+0C70h+var_C28]; this
0x1800aae8e  call    ??1RegisterLocalParams@@QEAA@XZ; RegisterLocalParams::~RegisterLocalParams(void)
0x1800aae93  jmp     loc_1800AAFD7
0x1800aae98  mov     rcx, rbx; lpMem
0x1800aae9b  call    DnsApiFree
0x1800aaea0  mov     rcx, [r14+rsi*8]; unsigned __int16 *
0x1800aaea4  lea     r8, [rsp+0D70h+var_D20]; unsigned __int64 *
0x1800aaea9  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800aaeae  mov     ecx, eax
  ... truncated ...
```
