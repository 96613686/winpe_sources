# BATCHCTX::ReadPacket(void *,ulong)

- ea: `0x1004565e8`
- end: `0x100456b7f`
- name: `?ReadPacket@BATCHCTX@@AEAAJPEAXK@Z`
- size: `1431`
- prototype: `__int64 __fastcall(BATCHCTX *__hidden this, void *, unsigned int)`
- caller_count: `4`
- callee_count: `16`
- tags: ``

## callers

- `0x10044d30c`
- `0x10044dca4`
- `0x10046393c`
- `0x1004644c0`

## callees

- `0x100418398`
- `0x10041847c`
- `0x100418608`
- `0x10041866c`
- `0x100418678`
- `0x100450e44`
- `0x1004565e8`
- `0x100458a00`
- `0x1004655f4`
- `0x10046562c`
- `0x100467174`
- `0x100467208`
- `0x1004673b4`
- `0x100546a24`
- `0x100546aa8`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x10045661e`
- `KERNEL32!GetTickCount` at `0x100456778`
- `KERNEL32!GetTickCount` at `0x1004567f1`
- `KERNEL32!GetTickCount` at `0x100456892`
- `KERNEL32!GetTickCount` at `0x10045661e`
- `KERNEL32!GetTickCount` at `0x100456778`
- `KERNEL32!GetTickCount` at `0x1004567f1`
- `KERNEL32!GetTickCount` at `0x100456892`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x100456a91`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x100456a91`

## pseudocode

```c
__int64 __fastcall BATCHCTX::ReadPacket(BATCHCTX *this, void *a2, unsigned int a3)
{
  struct SNI_Packet *v3; // r13
  DWORD TickCount; // r15d
  int v8; // eax
  __int64 v9; // r9
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  DWORD v14; // eax
  DWORD v15; // ecx
  __int64 v16; // rdx
  __int64 v17; // r8
  int v18; // eax
  int v19; // eax
  unsigned int v20; // r12d
  int v21; // eax
  DWORD v22; // eax
  __int64 v23; // rax
  void *v24; // rsi
  unsigned int v26; // ebx
  __int64 v27; // rax
  __int64 v28; // rcx
  __int64 v29; // r8
  unsigned int v30; // [rsp+40h] [rbp-20h] BYREF
  struct SNI_Packet *v31; // [rsp+48h] [rbp-18h] BYREF
  struct TDSBuff *v32; // [rsp+50h] [rbp-10h] BYREF
  void *Destination; // [rsp+58h] [rbp-8h] BYREF
  unsigned int v34; // [rsp+A0h] [rbp+40h] BYREF
  void *v35; // [rsp+A8h] [rbp+48h]
  unsigned int v36; // [rsp+B8h] [rbp+58h] BYREF

  v35 = a2;
  v31 = (struct SNI_Packet *)*((_QWORD *)this + 10);
  v3 = 0;
  v32 = 0;
  v34 = 0;
  v36 = 0;
  TickCount = GetTickCount();
  if ( !v31 )
  {
    v31 = (struct SNI_Packet *)*((_QWORD *)this + 11);
    *((_QWORD *)this + 11) = 0;
    v8 = BATCHCTX::SNIRead(this, &v31, a3);
    v10 = v8;
    if ( v8 >= 0 )
    {
      if ( a3 == -1 )
        goto LABEL_25;
      v14 = GetTickCount();
      v15 = v14 - TickCount;
      if ( v14 - TickCount >= a3 )
      {
        v10 = -2147023436;
        if ( (bidGblFlags & 2) != 0 )
        {
          v16 = 1332233;
          goto LABEL_22;
        }
        goto LABEL_68;
      }
      goto LABEL_24;
    }
    if ( v8 == -2147023436 || *((_DWORD *)this + 8) != 1 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        v12 = (unsigned int)v8;
        v13 = 1326089;
        goto LABEL_17;
      }
      goto LABEL_51;
    }
    _mm_lfence();
    _InterlockedExchange((volatile __int32 *)this + 8, 16);
    _InterlockedExchange((volatile __int32 *)this + 9, 0);
    if ( *((_QWORD *)this + 9) )
    {
      _mm_lfence();
      *(_BYTE *)(*((_QWORD *)this + 9) + 4672LL) = 1;
      _mm_lfence();
      *(_BYTE *)(*((_QWORD *)this + 9) + 4673LL) = 1;
    }
    if ( (bidGblFlags & 2) != 0 && off_1005E67B0[0] )
    {
      _mm_lfence();
      bidTraceW(0, 1315840, off_1005E67B0[0], this);
    }
    CTdsParser::PostParserErrorEx(*((_QWORD *)this + 13), a2, 1, 40117, 26);
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_67;
    if ( off_1005E67B8[0] )
    {
      _mm_lfence();
      bidTraceW(0, 1319936, off_1005E67B8[0], this);
    }
    if ( (bidGblFlags & 2) == 0 )
    {
LABEL_67:
      v10 = -2147418113;
      goto LABEL_68;
    }
    v11 = 1320969;
LABEL_66:
    v10 = bidTraceHR(0, v11, 2147549183LL, v9);
    goto LABEL_68;
  }
LABEL_25:
  while ( 1 )
  {
    SNIPacketGetData(v31, &v32, &v34);
    if ( v34 >= 8 )
      break;
    v18 = BATCHCTX::SNIPartialRead(this, v31, 8 - v34, a3);
    v10 = v18;
    if ( v18 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        v12 = (unsigned int)v18;
        v13 = 1344521;
        goto LABEL_17;
      }
      goto LABEL_51;
    }
    if ( a3 != -1 )
    {
      v14 = GetTickCount();
      v15 = v14 - TickCount;
      if ( v14 - TickCount >= a3 )
      {
        v10 = -2147023436;
        if ( (bidGblFlags & 2) != 0 )
        {
          v16 = 1347593;
          goto LABEL_22;
        }
        goto LABEL_68;
      }
LABEL_24:
      a3 -= v15;
      TickCount = v14;
      continue;
    }
  }
  v19 = BATCHCTX::ValidatePacketHeader(this, a2, v32, &v36);
  v10 = v19;
  if ( v19 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v17 = (unsigned int)v19;
      v16 = 1355785;
      goto LABEL_23;
    }
    goto LABEL_68;
  }
  _mm_lfence();
  v20 = v36;
  while ( 1 )
  {
    if ( v34 >= v20 )
    {
      if ( v34 > v20 )
      {
        _mm_lfence();
        Destination = 0;
        v3 = BATCHCTX::SNIPacketAllocEx(this, 0, 0, (unsigned __int8 **)&Destination, &v30);
        if ( !v3 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            v10 = bidTraceHR(0, 1379337, 2147942414LL, v9);
            goto LABEL_51;
          }
          v10 = -2147024882;
          goto LABEL_57;
        }
        if ( v30 < v34 - v36 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_67;
          v11 = 1383433;
          goto LABEL_66;
        }
        _mm_lfence();
        v26 = v36;
        memcpy_s(Destination, v34 - v36, (char *)v32 + v36, v34 - v36);
        SNIPacketSetBufferSize(v3, v34 - v26);
        SNIPacketSetBufferSize(v31, v26);
        SNIPacketSetKey(v3, this);
      }
      _mm_lfence();
      v27 = *((_QWORD *)this + 5);
      *((_QWORD *)this + 10) = v3;
      if ( *(_QWORD *)(v27 + 32) )
      {
        _mm_lfence();
        if ( *((_QWORD *)this + 11) )
        {
          _mm_lfence();
          SNIPacketRelease(*((SNI_Packet **)this + 11));
        }
        v28 = *((_QWORD *)this + 12);
        v29 = *(_QWORD *)(*((_QWORD *)this + 5) + 32LL);
        *((_QWORD *)this + 11) = v29;
        SNIPacketReset(v28, 0, v29, 0);
      }
      *(_QWORD *)(*((_QWORD *)this + 5) + 32LL) = v31;
      SNIPacketGetData(*(_QWORD *)(*((_QWORD *)this + 5) + 32LL), *((_QWORD *)this + 5), *((_QWORD *)this + 5) + 8LL);
      BATCHCTX::ParsePacketHeader(this);
      if ( (bidGblFlags & 2) != 0 && off_1005E67C0[0] )
      {
        _mm_lfence();
        bidTraceW(0, 1420288, off_1005E67C0[0], *(_QWORD *)(*((_QWORD *)this + 5) + 8LL));
      }
      return 0;
    }
    v21 = BATCHCTX::SNIPartialRead(this, v31, v20 - v34, a3);
    v10 = v21;
    if ( v21 < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_51;
      v12 = (unsigned int)v21;
      v13 = 1361929;
LABEL_17:
      _mm_lfence();
      bidTraceHR(0, v13, v12, v9);
LABEL_51:
      if ( v10 == -2147023436 )
      {
        if ( (bidGblFlags & 2) != 0 && off_1005E67C8[0] && bidID != -1 )
          ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0)(
            bidID,
            0,
            1428480,
            off_1005E67C8[0],
            0);
        goto LABEL_68;
      }
LABEL_57:
      _InterlockedExchange((volatile __int32 *)this + 8, 16);
      _InterlockedExchange((volatile __int32 *)this + 9, 0);
      v23 = *((_QWORD *)this + 9);
      if ( v23 )
      {
        *(_BYTE *)(v23 + 4672) = 1;
        *(_BYTE *)(*((_QWORD *)this + 9) + 4673LL) = 1;
      }
      v24 = v35;
      if ( (bidGblFlags & 2) != 0 && off_1005E67D0[0] )
        bidTraceW(0, 1433600, off_1005E67D0[0], *((_QWORD *)this + 9));
      CTdsParser::PostSNIErrorEx(*((CTdsParser **)this + 13), *((struct CConnection **)this + 9), v24, 0x9CB7u);
      goto LABEL_68;
    }
    if ( a3 == -1 )
      goto LABEL_42;
    v22 = GetTickCount();
    if ( v22 - TickCount >= a3 )
      break;
    a3 -= v22 - TickCount;
    TickCount = v22;
LABEL_42:
    SNIPacketGetData(v31, &v32, &v34);
  }
  v10 = -2147023436;
  if ( (bidGblFlags & 2) == 0 )
    goto LABEL_68;
  v16 = 1365001;
LABEL_22:
  v17 = 2147943860LL;
LABEL_23:
  _mm_lfence();
  bidTraceHR(0, v16, v17, v9);
LABEL_68:
  *((_QWORD *)this + 10) = v31;
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(0, 1441801, v10, v9);
  return v10;
}

```

## disassembly

```asm
0x1004565e8  mov     [rsp-38h+arg_8], rdx
0x1004565ed  push    rbp
0x1004565ee  push    rbx
0x1004565ef  push    rsi
0x1004565f0  push    rdi
0x1004565f1  push    r12
0x1004565f3  push    r13
0x1004565f5  push    r15
0x1004565f7  mov     rbp, rsp
0x1004565fa  sub     rsp, 60h
0x1004565fe  mov     rax, [rcx+50h]
0x100456602  xor     ebx, ebx
0x100456604  mov     [rbp+var_18], rax
0x100456608  mov     r13d, ebx
0x10045660b  mov     [rbp+var_10], rbx
0x10045660f  mov     esi, r8d
0x100456612  mov     [rbp+arg_0], ebx
0x100456615  mov     r12, rdx
0x100456618  mov     [rbp+arg_18], ebx
0x10045661b  mov     rdi, rcx
0x10045661e  call    cs:__imp_GetTickCount
0x100456624  mov     r15d, eax
0x100456627  cmp     [rbp+var_18], rbx
0x10045662b  jnz     loc_1004567B5
0x100456631  mov     rax, [rdi+58h]
0x100456635  lea     rdx, [rbp+var_18]; struct SNI_Packet **
0x100456639  mov     r8d, esi; unsigned int
0x10045663c  mov     [rbp+var_18], rax
0x100456640  mov     rcx, rdi; this
0x100456643  mov     [rdi+58h], rbx
0x100456647  call    ?SNIRead@BATCHCTX@@AEAAJPEAPEAVSNI_Packet@@K@Z; BATCHCTX::SNIRead(SNI_Packet * *,ulong)
0x10045664c  mov     ebx, eax
0x10045664e  test    eax, eax
0x100456650  jns     loc_100456773
0x100456656  cmp     eax, 800705B4h
0x10045665b  jz      loc_10045674F
0x100456661  lea     esi, [r13+1]
0x100456665  cmp     [rdi+20h], esi
0x100456668  jnz     loc_10045674F
0x10045666e  lfence
0x100456671  lea     eax, [rsi+0Fh]
0x100456674  xchg    eax, [rdi+20h]
0x100456677  xor     eax, eax
0x100456679  xchg    eax, [rdi+24h]
0x10045667c  cmp     [rdi+48h], r13
0x100456680  jz      short loc_10045669E
0x100456682  lfence
0x100456685  mov     rax, [rdi+48h]
0x100456689  mov     [rax+1240h], sil
0x100456690  lfence
0x100456693  mov     rax, [rdi+48h]
0x100456697  mov     [rax+1241h], sil
0x10045669e  test    byte ptr cs:_bidGblFlags, 2
0x1004566a5  mov     r15d, 9CB5h
0x1004566ab  jz      short loc_1004566E8
0x1004566ad  mov     rax, cs:off_1005E67B0; "<BATCHCTX::ReadPacket|TDS|ERR> %p{BATCH"...
0x1004566b4  test    rax, rax
0x1004566b7  jz      short loc_1004566E8
0x1004566b9  lfence
0x1004566bc  mov     r8, cs:off_1005E67B0; "<BATCHCTX::ReadPacket|TDS|ERR> %p{BATCH"...
0x1004566c3  mov     r9, rdi
0x1004566c6  mov     [rsp+60h+var_28], 1Ah
0x1004566ce  mov     edx, 141400h
0x1004566d3  mov     dword ptr [rsp+60h+var_30], r15d
0x1004566d8  xor     ecx, ecx
0x1004566da  mov     [rsp+60h+var_38], esi
0x1004566de  mov     [rsp+60h+var_40], r12
0x1004566e3  call    _bidTraceW
0x1004566e8  mov     rcx, [rdi+68h]
0x1004566ec  mov     r9d, r15d
0x1004566ef  mov     r8d, esi
0x1004566f2  mov     dword ptr [rsp+60h+var_40], 1Ah
0x1004566fa  mov     rdx, r12
0x1004566fd  call    ?PostParserErrorEx@CTdsParser@@AEAAJPEAXW4_PARSE_ERR_TYPE@@GK@Z; CTdsParser::PostParserErrorEx(void *,_PARSE_ERR_TYPE,ushort,ulong)
0x100456702  test    byte ptr cs:_bidGblFlags, 2
0x100456709  jz      loc_100456A48
0x10045670f  mov     rax, cs:off_1005E67B8; "<BATCHCTX::ReadPacket|TDS|LOGIN|ERR> %p"...
0x100456716  test    rax, rax
0x100456719  jz      short loc_100456738
0x10045671b  lfence
0x10045671e  mov     r8, cs:off_1005E67B8; "<BATCHCTX::ReadPacket|TDS|LOGIN|ERR> %p"...
0x100456725  mov     r9, rdi
0x100456728  mov     edx, 142400h
0x10045672d  mov     dword ptr [rsp+60h+var_40], ebx
0x100456731  xor     ecx, ecx
0x100456733  call    _bidTraceW
0x100456738  test    byte ptr cs:_bidGblFlags, 2
0x10045673f  jz      loc_100456A48
0x100456745  mov     edx, 142809h
0x10045674a  jmp     loc_100456A37
0x10045674f  test    byte ptr cs:_bidGblFlags, 2
0x100456756  jz      loc_10045693B
0x10045675c  mov     r8d, ebx
0x10045675f  mov     edx, 143C09h
0x100456764  lfence
0x100456767  xor     ecx, ecx
0x100456769  call    _bidTraceHR
0x10045676e  jmp     loc_10045693B
0x100456773  cmp     esi, 0FFFFFFFFh
0x100456776  jz      short loc_1004567B5
0x100456778  call    cs:__imp_GetTickCount
0x10045677e  mov     ecx, eax
0x100456780  sub     ecx, r15d
0x100456783  cmp     ecx, esi
0x100456785  jb      short loc_1004567B0
0x100456787  test    byte ptr cs:_bidGblFlags, 2
0x10045678e  mov     ebx, 800705B4h
0x100456793  jz      loc_100456A4D
0x100456799  mov     edx, 145409h
0x10045679e  mov     r8d, ebx
0x1004567a1  lfence
0x1004567a4  xor     ecx, ecx
0x1004567a6  call    _bidTraceHR
0x1004567ab  jmp     loc_100456A4D
0x1004567b0  sub     esi, ecx
0x1004567b2  mov     r15d, eax
0x1004567b5  mov     rcx, [rbp+var_18]
0x1004567b9  lea     r8, [rbp+arg_0]
0x1004567bd  lea     rdx, [rbp+var_10]
0x1004567c1  call    SNIPacketGetData
0x1004567c6  mov     eax, [rbp+arg_0]
0x1004567c9  mov     rcx, rdi; this
0x1004567cc  cmp     eax, 8
0x1004567cf  jnb     short loc_100456833
0x1004567d1  mov     rdx, [rbp+var_18]; struct SNI_Packet *
0x1004567d5  mov     r8d, 8
0x1004567db  sub     r8d, eax; unsigned int
0x1004567de  mov     r9d, esi; unsigned int
0x1004567e1  call    ?SNIPartialRead@BATCHCTX@@AEAAJPEAVSNI_Packet@@KK@Z; BATCHCTX::SNIPartialRead(SNI_Packet *,ulong,ulong)
0x1004567e6  mov     ebx, eax
0x1004567e8  test    eax, eax
0x1004567ea  js      short loc_100456819
0x1004567ec  cmp     esi, 0FFFFFFFFh
0x1004567ef  jz      short loc_1004567B5
0x1004567f1  call    cs:__imp_GetTickCount
0x1004567f7  mov     ecx, eax
0x1004567f9  sub     ecx, r15d
0x1004567fc  cmp     ecx, esi
0x1004567fe  jb      short loc_1004567B0
0x100456800  test    byte ptr cs:_bidGblFlags, 2
0x100456807  mov     ebx, 800705B4h
0x10045680c  jz      loc_100456A4D
0x100456812  mov     edx, 149009h
0x100456817  jmp     short loc_10045679E
0x100456819  test    byte ptr cs:_bidGblFlags, 2
0x100456820  jz      loc_10045693B
0x100456826  mov     r8d, eax
0x100456829  mov     edx, 148409h
0x10045682e  jmp     loc_100456764
0x100456833  mov     r8, [rbp+var_10]; struct TDSBuff *
0x100456837  lea     r9, [rbp+arg_18]; unsigned int *
0x10045683b  mov     rdx, r12; void *
0x10045683e  call    ?ValidatePacketHeader@BATCHCTX@@AEAAJPEAXPEFAUTDSBuff@@PEAK@Z; BATCHCTX::ValidatePacketHeader(void *,TDSBuff *,ulong *)
0x100456843  mov     ebx, eax
0x100456845  test    eax, eax
0x100456847  jns     short loc_100456863
0x100456849  test    byte ptr cs:_bidGblFlags, 2
0x100456850  jz      loc_100456A4D
0x100456856  mov     r8d, eax
0x100456859  mov     edx, 14B009h
0x10045685e  jmp     loc_1004567A1
0x100456863  lfence
0x100456866  mov     r12d, [rbp+arg_18]
0x10045686a  mov     eax, [rbp+arg_0]
0x10045686d  cmp     eax, r12d
0x100456870  jnb     short loc_1004568EB
0x100456872  mov     rdx, [rbp+var_18]; struct SNI_Packet *
0x100456876  mov     r8d, r12d
0x100456879  sub     r8d, eax; unsigned int
0x10045687c  mov     r9d, esi; unsigned int
0x10045687f  mov     rcx, rdi; this
0x100456882  call    ?SNIPartialRead@BATCHCTX@@AEAAJPEAVSNI_Packet@@KK@Z; BATCHCTX::SNIPartialRead(SNI_Packet *,ulong,ulong)
0x100456887  mov     ebx, eax
0x100456889  test    eax, eax
0x10045688b  js      short loc_1004568D5
0x10045688d  cmp     esi, 0FFFFFFFFh
0x100456890  jz      short loc_1004568A6
0x100456892  call    cs:__imp_GetTickCount
0x100456898  mov     ecx, eax
0x10045689a  sub     ecx, r15d
0x10045689d  cmp     ecx, esi
0x10045689f  jnb     short loc_1004568B9
0x1004568a1  sub     esi, ecx
0x1004568a3  mov     r15d, eax
0x1004568a6  mov     rcx, [rbp+var_18]
0x1004568aa  lea     r8, [rbp+arg_0]
0x1004568ae  lea     rdx, [rbp+var_10]
0x1004568b2  call    SNIPacketGetData
0x1004568b7  jmp     short loc_10045686A
0x1004568b9  test    byte ptr cs:_bidGblFlags, 2
0x1004568c0  mov     ebx, 800705B4h
0x1004568c5  jz      loc_100456A4D
0x1004568cb  mov     edx, 14D409h
0x1004568d0  jmp     loc_10045679E
0x1004568d5  test    byte ptr cs:_bidGblFlags, 2
0x1004568dc  jz      short loc_10045693B
0x1004568de  mov     r8d, eax
0x1004568e1  mov     edx, 14C809h
0x1004568e6  jmp     loc_100456764
0x1004568eb  jbe     loc_100456ABA
0x1004568f1  lfence
0x1004568f4  and     [rbp+Destination], r13
0x1004568f8  lea     rax, [rbp+var_20]
0x1004568fc  lea     r9, [rbp+Destination]; unsigned __int8 **
0x100456900  mov     [rsp+60h+var_40], rax; unsigned int *
0x100456905  xor     r8d, r8d; int
0x100456908  xor     edx, edx; unsigned int
0x10045690a  mov     rcx, rdi; this
0x10045690d  call    ?SNIPacketAllocEx@BATCHCTX@@AEAAPEAVSNI_Packet@@KHPEAPEAEPEAK@Z; BATCHCTX::SNIPacketAllocEx(ulong,int,uchar * *,ulong *)
0x100456912  mov     r13, rax
0x100456915  test    rax, rax
0x100456918  jnz     loc_100456A1E
0x10045691e  test    byte ptr cs:_bidGblFlags, 2
0x100456925  jz      short loc_10045699C
0x100456927  mov     edx, 150C09h
0x10045692c  xor     ecx, ecx
0x10045692e  mov     r8d, 8007000Eh
0x100456934  call    _bidTraceHR
0x100456939  mov     ebx, eax
0x10045693b  cmp     ebx, 800705B4h
0x100456941  jnz     short loc_1004569A1
0x100456943  test    byte ptr cs:_bidGblFlags, 2
0x10045694a  jz      loc_100456A4D
0x100456950  mov     rax, cs:off_1005E67C8; "<BATCHCTX::ReadPacket|TDS|ERR> SNI ERRO"...
0x100456957  test    rax, rax
0x10045695a  jz      loc_100456A4D
0x100456960  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x100456968  jz      loc_100456A4D
0x10045696e  mov     r9, cs:off_1005E67C8; "<BATCHCTX::ReadPacket|TDS|ERR> SNI ERRO"...
0x100456975  xor     edx, edx
0x100456977  mov     rcx, cs:_bidID
0x10045697e  mov     r8d, 15CC00h
0x100456984  mov     rax, cs:off_1005D39E0
0x10045698b  and     [rsp+60h+var_40], 0
0x100456991  call    cs:__guard_dispatch_icall_fptr
0x100456997  jmp     loc_100456A4D
0x10045699c  mov     ebx, 8007000Eh
0x1004569a1  mov     eax, 10h
0x1004569a6  xchg    eax, [rdi+20h]
0x1004569a9  xor     eax, eax
0x1004569ab  xchg    eax, [rdi+24h]
0x1004569ae  mov     rax, [rdi+48h]
0x1004569b2  test    rax, rax
0x1004569b5  jz      short loc_1004569C9
0x1004569b7  mov     byte ptr [rax+1240h], 1
0x1004569be  mov     rax, [rdi+48h]
0x1004569c2  mov     byte ptr [rax+1241h], 1
0x1004569c9  test    byte ptr cs:_bidGblFlags, 2
0x1004569d0  mov     rsi, [rbp+arg_8]
0x1004569d4  jz      short loc_100456A06
0x1004569d6  mov     rax, cs:off_1005E67D0; "<BATCHCTX::ReadPacket|TDS|ERR> %p{HCONN"...
0x1004569dd  test    rax, rax
0x1004569e0  jz      short loc_100456A06
0x1004569e2  mov     r9, [rdi+48h]
0x1004569e6  mov     edx, 15E000h
0x1004569eb  mov     r8, cs:off_1005E67D0; "<BATCHCTX::ReadPacket|TDS|ERR> %p{HCONN"...
0x1004569f2  xor     ecx, ecx
0x1004569f4  mov     [rsp+60h+var_38], 9CB7h
0x1004569fc  mov     [rsp+60h+var_40], rsi
0x100456a01  call    _bidTraceW
0x100456a06  mov     rdx, [rdi+48h]; struct CConnection *
0x100456a0a  mov     r9d, 9CB7h; unsigned __int16
0x100456a10  mov     rcx, [rdi+68h]; this
0x100456a14  mov     r8, rsi; void *
0x100456a17  call    ?PostSNIErrorEx@CTdsParser@@AEAAJPEAVCConnection@@PEAXG@Z; CTdsParser::PostSNIErrorEx(CConnection *,void *,ushort)
0x100456a1c  jmp     short loc_100456A4D
0x100456a1e  mov     eax, [rbp+arg_0]
0x100456a21  sub     eax, [rbp+arg_18]
0x100456a24  cmp     [rbp+var_20], eax
0x100456a27  jnb     short loc_100456A76
0x100456a29  test    byte ptr cs:_bidGblFlags, 2
0x100456a30  jz      short loc_100456A48
0x100456a32  mov     edx, 151C09h
0x100456a37  mov     r8d, 8000FFFFh
0x100456a3d  xor     ecx, ecx
0x100456a3f  call    _bidTraceHR
0x100456a44  mov     ebx, eax
0x100456a46  jmp     short loc_100456A4D
0x100456a48  mov     ebx, 8000FFFFh
0x100456a4d  mov     rax, [rbp+var_18]
0x100456a51  mov     [rdi+50h], rax
0x100456a55  test    byte ptr cs:_bidGblFlags, 2
0x100456a5c  jz      short loc_100456A6F
0x100456a5e  mov     r8d, ebx
0x100456a61  mov     edx, 160009h
0x100456a66  xor     ecx, ecx
0x100456a68  call    _bidTraceHR
0x100456a6d  mov     ebx, eax
0x100456a6f  mov     eax, ebx
0x100456a71  jmp     loc_100456B70
0x100456a76  lfence
0x100456a79  mov     eax, [rbp+arg_0]
0x100456a7c  mov     ebx, [rbp+arg_18]
0x100456a7f  mov     rcx, [rbp+Destination]; Destination
0x100456a83  sub     eax, ebx
0x100456a85  mov     r8d, ebx
0x100456a88  mov     edx, eax; DestinationSize
0x100456a8a  add     r8, [rbp+var_10]; Source
0x100456a8e  mov     r9d, eax; SourceSize
0x100456a91  call    cs:__imp_memcpy_s
  ... truncated ...
```
