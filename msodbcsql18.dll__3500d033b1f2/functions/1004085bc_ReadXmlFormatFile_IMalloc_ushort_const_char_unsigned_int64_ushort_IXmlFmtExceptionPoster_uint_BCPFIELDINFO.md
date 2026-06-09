# ReadXmlFormatFile(IMalloc *,ushort const *,char *,unsigned __int64,ushort,IXmlFmtExceptionPoster *,uint *,BCPFIELDINFO * *)

- ea: `0x1004085bc`
- end: `0x100408cc0`
- name: `?ReadXmlFormatFile@@YAJPEAUIMalloc@@PEBGPEAD_KGPEAVIXmlFmtExceptionPoster@@PEAIPEAPEAUBCPFIELDINFO@@@Z`
- size: `1796`
- prototype: `__int64 __usercall@<rax>(struct IMalloc *@<rcx>, const unsigned __int16 *@<rdx>, char *@<r8>, unsigned __int64@<r9>, unsigned __int16, struct IXmlFmtExceptionPoster *, unsigned int *, struct BCPFIELDINFO **)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x10049b4a0`

## callees

- `0x100407820`
- `0x100407830`
- `0x10040799c`
- `0x100407a60`
- `0x100407d68`
- `0x1004082a4`
- `0x1004082e0`
- `0x1004085bc`
- `0x10040965c`
- `0x100409e58`
- `0x10040ab34`
- `0x100410e6c`
- `0x100546a7c`
- `0x10054811c`
- `0x100548140`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x100408b4d`
- `KERNEL32!CloseHandle` at `0x100408b4d`
- `api-ms-win-crt-convert-l1-1-0!wcstombs` at `0x1004086c0`
- `api-ms-win-crt-convert-l1-1-0!wcstombs` at `0x10040897d`
- `api-ms-win-crt-convert-l1-1-0!wcstombs` at `0x1004086c0`
- `api-ms-win-crt-convert-l1-1-0!wcstombs` at `0x10040897d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall ReadXmlFormatFile(
        struct IMalloc *a1,
        const unsigned __int16 *a2,
        char *a3,
        __int64 a4,
        unsigned __int16 a5,
        struct IXmlFmtExceptionPoster *a6,
        unsigned int *a7,
        struct BCPFIELDINFO **a8)
{
  char *v10; // r14
  signed int v11; // esi
  const wchar_t *v12; // rdx
  unsigned __int64 v13; // rax
  size_t v14; // rbx
  size_t v15; // r8
  size_t v16; // rax
  __int64 v17; // r9
  size_t v18; // rcx
  char *v19; // rax
  unsigned int v20; // ecx
  char *v21; // rax
  __int64 v22; // rbx
  __int64 v23; // rdx
  struct BCPFIELDINFO *v24; // rax
  struct BCPFIELDINFO *v25; // r12
  unsigned int i; // ebx
  __int64 Next; // rax
  __int64 v28; // r13
  unsigned __int16 *v29; // rsi
  unsigned __int16 ColumnByID; // ax
  __int64 v31; // rdx
  const wchar_t *v32; // rax
  wchar_t *v33; // rcx
  unsigned __int8 v34; // r11
  unsigned int v35; // eax
  int v36; // ecx
  int v37; // r10d
  __int64 v38; // rcx
  __int64 v39; // rax
  const wchar_t *v40; // rdx
  unsigned __int64 v41; // rax
  size_t v42; // r8
  size_t v43; // rax
  size_t v44; // rcx
  unsigned __int64 v45; // rax
  int v46; // r9d
  const wchar_t *v47; // rdx
  unsigned __int64 v48; // rax
  _WORD *v49; // rcx
  __int64 v50; // r8
  signed __int64 v51; // rdx
  __int16 v52; // ax
  _WORD *v53; // rax
  unsigned __int16 *v54; // rax
  unsigned int v56; // [rsp+30h] [rbp-1B8h]
  unsigned __int8 v57; // [rsp+34h] [rbp-1B4h]
  unsigned int v58; // [rsp+38h] [rbp-1B0h]
  int v59; // [rsp+50h] [rbp-198h]
  struct CBulkColumn *v60; // [rsp+58h] [rbp-190h] BYREF
  unsigned __int64 v61; // [rsp+60h] [rbp-188h]
  void **v62; // [rsp+68h] [rbp-180h] BYREF
  int v63; // [rsp+70h] [rbp-178h]
  HANDLE hObject[2]; // [rsp+78h] [rbp-170h]
  char pExceptionObject[8]; // [rsp+88h] [rbp-160h] BYREF
  char v66[8]; // [rsp+90h] [rbp-158h] BYREF
  char v67[8]; // [rsp+98h] [rbp-150h] BYREF
  char v68[8]; // [rsp+A0h] [rbp-148h] BYREF
  char v69[8]; // [rsp+A8h] [rbp-140h] BYREF
  unsigned __int64 v70; // [rsp+B0h] [rbp-138h]
  char v71[8]; // [rsp+B8h] [rbp-130h] BYREF
  char v72[8]; // [rsp+C0h] [rbp-128h] BYREF
  unsigned __int16 *v73; // [rsp+C8h] [rbp-120h]
  char v74[8]; // [rsp+D0h] [rbp-118h] BYREF
  _QWORD v75[7]; // [rsp+D8h] [rbp-110h] BYREF
  _BYTE v76[72]; // [rsp+110h] [rbp-D8h] BYREF
  char v77[8]; // [rsp+158h] [rbp-90h] BYREF
  char *v78; // [rsp+160h] [rbp-88h]
  const wchar_t *v79; // [rsp+1A0h] [rbp-48h]

  v75[2] = -2;
  v60 = 0;
  v10 = 0;
  *a7 = 0;
  *a8 = 0;
  v62 = &CFileReadStream::`vftable';
  v63 = 1;
  *(__m128i *)hObject = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v11 = CFileReadStream::Open((CFileReadStream *)&v62, a2);
  if ( v11 >= 0 )
  {
    CBulkFormat::CBulkFormat((CBulkFormat *)v76, a1);
    CBulkFormat::ParseFormatFile((CBulkFormat *)v76, hObject[0]);
    v12 = v79;
    if ( v79 )
    {
      v13 = -1;
      do
        ++v13;
      while ( v79[v13] );
    }
    else
    {
      v13 = 0;
      v12 = &szDefault;
    }
    v14 = a4 - 1;
    v15 = a4 - 1;
    if ( v13 < a4 - 1 )
      v15 = v13;
    v16 = wcstombs(a3, v12, v15);
    v18 = 0;
    if ( v16 )
      v18 = v16;
    if ( v18 < v14 )
      v14 = v18;
    a3[v14] = 0;
    v75[0] = v77;
    v19 = 0;
    if ( v78 != v77 )
      v19 = v78;
    v75[1] = (unsigned __int64)(v19 - 48) & -(__int64)(v19 != 0);
    v20 = 0;
    v21 = 0;
    if ( v78 != v77 )
      v21 = v78;
    do
    {
      if ( !v21 )
        break;
      ++v20;
      v21 = (char *)*((_QWORD *)v21 + 1);
    }
    while ( v21 != v77 );
    v58 = v20;
    if ( v20 - 1 > 0xFFF )
    {
      CBcpFmtException::CBcpFmtException(v74, 2, v77, v17);
      throw (CBcpFmtException *)v74;
    }
    _mm_lfence();
    v22 = v20;
    v23 = 288LL * v20;
    if ( !is_mul_ok(v20, 0x120u) )
      v23 = -1;
    v24 = (struct BCPFIELDINFO *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Free)(g_pMO, v23);
    v25 = v24;
    if ( v24 )
    {
      memset_0(v24, 0, 288 * v22);
      for ( i = 0; i < v58; ++i )
      {
        Next = SEListEnum<CBulkField,48>::GetNext(v75);
        v28 = Next;
        if ( !Next )
          break;
        v60 = 0;
        v29 = (unsigned __int16 *)((char *)v25 + 288 * i);
        v73 = v29;
        ColumnByID = CBulkFormat::GetColumnByID((CBulkFormat *)v76, (const struct CWStr *)(Next + 8), &v60);
        if ( ColumnByID > a5 )
        {
          CBcpFmtException::CBcpFmtException(pExceptionObject, 9, i + 1);
          throw (CBcpFmtException *)pExceptionObject;
        }
        *v29 = ColumnByID;
        switch ( *(_DWORD *)(v28 + 24) )
        {
          case 1:
            v33 = (wchar_t *)L"SQLCHAR";
            break;
          case 2:
            v33 = L"SQLNCHAR";
            break;
          case 3:
            if ( !ColumnByID )
              goto LABEL_40;
            v31 = *((_QWORD *)v60 + 4);
            v32 = &szDefault;
            if ( v31 )
              v32 = (const wchar_t *)*((_QWORD *)v60 + 4);
            if ( *v32 )
            {
              v33 = (wchar_t *)&szDefault;
              if ( v31 )
                v33 = (wchar_t *)*((_QWORD *)v60 + 4);
            }
            else
            {
LABEL_40:
              v33 = L"SQLBINARY";
            }
            break;
          default:
            CBcpFmtException::CBcpFmtException(v66, 5, i + 1);
            throw (CBcpFmtException *)v66;
        }
        v34 = FieldNameToTDSType(v33);
        v57 = v34;
        if ( !v34 )
        {
          CBcpFmtException::CBcpFmtException(v67, 5, i + 1);
          throw (CBcpFmtException *)v67;
        }
        if ( *(_DWORD *)(v28 + 28) == 2 )
        {
          v35 = *(_DWORD *)(v28 + 36);
          v56 = v35;
          if ( v35 > 8 || (v36 = 278, !_bittest(&v36, v35)) )
          {
            CBcpFmtException::CBcpFmtException(v68, 6, i + 1);
            throw (CBcpFmtException *)v68;
          }
        }
        else
        {
          v56 = 0;
        }
        v37 = *(_DWORD *)(v28 + 32);
        v59 = v37;
        if ( v37 < 0 )
        {
          CBcpFmtException::CBcpFmtException(v69, 7, i + 1);
          throw (CBcpFmtException *)v69;
        }
        if ( *(_DWORD *)(v28 + 28) == 3 )
        {
          v38 = *(_QWORD *)(v28 + 40);
          if ( v38 )
          {
            v39 = -1;
            do
              ++v39;
            while ( *(_WORD *)(v38 + 2 * v39) );
          }
          else
          {
            v39 = 0;
          }
          v61 = 4 * v39;
          v70 = 4 * v39 + 1;
          v10 = (char *)((__int64 (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Free)(g_pMO);
          if ( !v10 )
          {
            v11 = -2147024882;
            CBulkFormat::~CBulkFormat((CBulkFormat *)v76);
            goto LABEL_92;
          }
          v40 = *(const wchar_t **)(v28 + 40);
          if ( v40 )
          {
            v41 = -1;
            do
              ++v41;
            while ( v40[v41] );
          }
          else
          {
            v41 = 0;
            v40 = &szDefault;
          }
          v42 = v61;
          if ( v41 < v61 )
            v42 = v41;
          v43 = wcstombs(v10, v40, v42);
          v44 = 0;
          if ( v43 )
            v44 = v43;
          v45 = v61;
          if ( v44 < v61 )
            v45 = v44;
          v10[v45] = 0;
          v46 = ConvertTerminatorToBinary((const unsigned __int8 *)v10, (unsigned __int8 *)v10, v70);
          if ( v46 == -1 )
          {
            CBcpFmtException::CBcpFmtException(v71, 8, i + 1);
            throw (CBcpFmtException *)v71;
          }
          v37 = v59;
          v34 = v57;
        }
        else
        {
          v10 = 0;
          v46 = 0;
        }
        v47 = *(const wchar_t **)(v28 + 16);
        if ( v47 )
        {
          v48 = -1;
          do
            ++v48;
          while ( v47[v48] );
          if ( v48 > 0x80 )
          {
            CBcpFmtException::CBcpFmtException(v72, 10, i + 1);
            throw (CBcpFmtException *)v72;
          }
        }
        else
        {
          v47 = &szDefault;
        }
        v49 = v29 + 12;
        v50 = 129;
        v51 = (char *)v47 - (char *)(v29 + 12);
        do
        {
          if ( v50 == -2147483517 )
            break;
          v52 = *(_WORD *)((char *)v49 + v51);
          if ( !v52 )
            break;
          *v49++ = v52;
          --v50;
        }
        while ( v50 );
        v53 = v49 - 1;
        if ( v50 )
          v53 = v49;
        *v53 = 0;
        v11 = v50 == 0 ? 0x8007007A : 0;
        if ( !v50 )
        {
          if ( (bidGblFlags & 2) != 0 )
            bidTraceMark(0, 1393673);
          CBulkFormat::~CBulkFormat((CBulkFormat *)v76);
          goto LABEL_90;
        }
        v54 = v73;
        *((_BYTE *)v73 + 2) = v34;
        *((_DWORD *)v54 + 1) = v56;
        *((_DWORD *)v54 + 2) = v37;
        *((_DWORD *)v54 + 3) = v46;
        *((_QWORD *)v54 + 2) = v10;
        v10 = 0;
      }
      CBulkFormat::~CBulkFormat((CBulkFormat *)v76);
      if ( v11 >= 0 )
      {
        *a7 = v58;
        *a8 = v25;
        goto LABEL_94;
      }
LABEL_90:
      if ( v10 )
        ((void (__fastcall *)(struct IMalloc *, char *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO, v10);
    }
    else
    {
      v11 = -2147024882;
      CBulkFormat::~CBulkFormat((CBulkFormat *)v76);
    }
LABEL_92:
    CleanReadXmlFormatFile(v25, v58);
  }
  else
  {
    _mm_lfence();
  }
LABEL_94:
  v62 = &CFileReadStream::`vftable';
  if ( hObject[0] != (HANDLE)-1LL )
    CloseHandle(hObject[0]);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1004085bc  mov     rax, rsp
0x1004085bf  mov     [rax+20h], r9
0x1004085c3  push    rdi
0x1004085c4  push    r12
0x1004085c6  push    r13
0x1004085c8  push    r14
0x1004085ca  push    r15
0x1004085cc  sub     rsp, 1C0h
0x1004085d3  mov     qword ptr [rax-100h], 0FFFFFFFFFFFFFFFEh
0x1004085de  mov     [rax+8], rbx
0x1004085e2  mov     [rax+10h], rsi
0x1004085e6  mov     r12, r8
0x1004085e9  mov     rbx, rcx
0x1004085ec  xor     edi, edi
0x1004085ee  mov     [rsp+1E8h+var_1B0], edi
0x1004085f2  mov     [rsp+1E8h+var_1A0], rdi
0x1004085f7  mov     [rsp+1E8h+var_190], rdi
0x1004085fc  mov     r14d, edi
0x1004085ff  mov     [rsp+1E8h+var_1A8], rdi
0x100408604  mov     rax, [rsp+1E8h+arg_30]
0x10040860c  mov     [rax], edi
0x10040860e  mov     rax, [rsp+1E8h+arg_38]
0x100408616  mov     [rax], rdi
0x100408619  lea     r13, ??_7CFileReadStream@@6B@; const CFileReadStream::`vftable'
0x100408620  mov     [rsp+1E8h+var_180], r13
0x100408625  mov     [rsp+1E8h+var_178], 1
0x10040862d  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x100408635  movdqu  xmmword ptr [rsp+1E8h+hObject], xmm0
0x10040863b  lea     rcx, [rsp+1E8h+var_180]; this
0x100408640  call    ?Open@CFileReadStream@@UEAAJPEBG@Z; CFileReadStream::Open(ushort const *)
0x100408645  mov     esi, eax
0x100408647  test    eax, eax
0x100408649  jns     short loc_100408657
0x10040864b  lfence
0x10040864e  or      r15, 0FFFFFFFFFFFFFFFFh
0x100408652  jmp     loc_100408B3E
0x100408657  mov     rdx, rbx; struct IMalloc *
0x10040865a  lea     rcx, [rsp+1E8h+var_D8]; this
0x100408662  call    ??0CBulkFormat@@QEAA@PEAUIMalloc@@@Z; CBulkFormat::CBulkFormat(IMalloc *)
0x100408667  nop
0x100408668  mov     rdx, [rsp+1E8h+hObject]; void *
0x10040866d  lea     rcx, [rsp+1E8h+var_D8]; this
0x100408675  call    ?ParseFormatFile@CBulkFormat@@QEAAXPEAX@Z; CBulkFormat::ParseFormatFile(void *)
0x10040867a  mov     rdx, [rsp+1E8h+var_48]
0x100408682  or      r15, 0FFFFFFFFFFFFFFFFh
0x100408686  test    rdx, rdx
0x100408689  jz      short loc_10040869E
0x10040868b  mov     rax, r15
0x10040868e  inc     rax
0x100408691  cmp     [rdx+rax*2], di
0x100408695  jnz     short loc_10040868E
0x100408697  test    rdx, rdx
0x10040869a  jz      short loc_1004086A1
0x10040869c  jmp     short loc_1004086A8
0x10040869e  mov     rax, rdi
0x1004086a1  lea     rdx, szDefault; Source
0x1004086a8  mov     rbx, [rsp+1E8h+arg_18]
0x1004086b0  dec     rbx
0x1004086b3  mov     r8, rbx
0x1004086b6  cmp     rax, rbx
0x1004086b9  cmovb   r8, rax; MaxCount
0x1004086bd  mov     rcx, r12; Dest
0x1004086c0  call    cs:__imp_wcstombs
0x1004086c6  mov     rcx, rdi
0x1004086c9  test    rax, rax
0x1004086cc  cmovnz  rcx, rax
0x1004086d0  cmp     rcx, rbx
0x1004086d3  cmovb   rbx, rcx
0x1004086d7  mov     [rbx+r12], dil
0x1004086db  lea     rax, [rsp+1E8h+var_90]
0x1004086e3  mov     [rsp+1E8h+var_110], rax
0x1004086eb  lea     rax, [rsp+1E8h+var_90]
0x1004086f3  mov     rdx, [rsp+1E8h+var_88]
0x1004086fb  cmp     rdx, rax
0x1004086fe  mov     rax, rdi
0x100408701  jz      short loc_100408706
0x100408703  mov     rax, rdx
0x100408706  lea     rcx, [rax-30h]
0x10040870a  neg     rax
0x10040870d  sbb     rax, rax
0x100408710  and     rax, rcx
0x100408713  mov     [rsp+1E8h+var_108], rax
0x10040871b  mov     ecx, edi
0x10040871d  mov     rax, rdi
0x100408720  lea     r8, [rsp+1E8h+var_90]
0x100408728  cmp     rdx, r8
0x10040872b  cmovnz  rax, rdx
0x10040872f  jmp     short loc_100408744
0x100408731  inc     ecx
0x100408733  mov     rax, [rax+8]
0x100408737  lea     rdx, [rsp+1E8h+var_90]
0x10040873f  cmp     rax, rdx
0x100408742  jz      short loc_100408749
0x100408744  test    rax, rax
0x100408747  jnz     short loc_100408731
0x100408749  mov     [rsp+1E8h+var_1B0], ecx
0x10040874d  lea     eax, [rcx-1]
0x100408750  cmp     eax, 0FFFh
0x100408755  ja      loc_100408C98
0x10040875b  lfence
0x10040875e  mov     ebx, ecx
0x100408760  mov     eax, 120h
0x100408765  mul     rbx
0x100408768  mov     rdx, rax
0x10040876b  cmovo   rdx, r15
0x10040876f  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x100408776  mov     rax, [rcx]
0x100408779  mov     rax, [rax+70h]
0x10040877d  call    cs:__guard_dispatch_icall_fptr
0x100408783  mov     r12, rax
0x100408786  mov     [rsp+1E8h+var_1A0], rax
0x10040878b  test    rax, rax
0x10040878e  jnz     short loc_1004087A8
0x100408790  mov     esi, 8007000Eh
0x100408795  lea     rcx, [rsp+1E8h+var_D8]; this
0x10040879d  call    ??1CBulkFormat@@QEAA@XZ; CBulkFormat::~CBulkFormat(void)
0x1004087a2  nop
0x1004087a3  jmp     loc_100408AF8
0x1004087a8  lea     r8, [rbx+rbx*8]
0x1004087ac  shl     r8, 5; Size
0x1004087b0  xor     edx, edx; Val
0x1004087b2  mov     rcx, r12; void *
0x1004087b5  call    memset_0
0x1004087ba  mov     ebx, edi
0x1004087bc  cmp     ebx, [rsp+1E8h+var_1B0]
0x1004087c0  jnb     loc_100408AAC
0x1004087c6  lea     rcx, [rsp+1E8h+var_110]
0x1004087ce  call    ?GetNext@?$SEListEnum@VCBulkField@@$0DA@@@QEAAPEAVCBulkField@@XZ; SEListEnum<CBulkField,48>::GetNext(void)
0x1004087d3  mov     r13, rax
0x1004087d6  test    rax, rax
0x1004087d9  jz      loc_100408AAC
0x1004087df  mov     [rsp+1E8h+var_190], rdi
0x1004087e4  mov     ecx, ebx
0x1004087e6  lea     rsi, [rcx+rcx*8]
0x1004087ea  shl     rsi, 5
0x1004087ee  add     rsi, r12
0x1004087f1  mov     [rsp+1E8h+var_120], rsi
0x1004087f9  lea     rdx, [rax+8]; struct CWStr *
0x1004087fd  lea     r8, [rsp+1E8h+var_190]; struct CBulkColumn **
0x100408802  lea     rcx, [rsp+1E8h+var_D8]; this
0x10040880a  call    ?GetColumnByID@CBulkFormat@@QEAAJAEBVCWStr@@PEAPEAVCBulkColumn@@@Z; CBulkFormat::GetColumnByID(CWStr const &,CBulkColumn * *)
0x10040880f  cmp     ax, [rsp+1E8h+arg_20]
0x100408817  ja      loc_100408B72
0x10040881d  mov     [rsi], ax
0x100408820  mov     ecx, [r13+18h]
0x100408824  sub     ecx, 1
0x100408827  jz      short loc_10040887A
0x100408829  sub     ecx, 1
0x10040882c  jz      short loc_100408871
0x10040882e  cmp     ecx, 1
0x100408831  jnz     loc_100408B9C
0x100408837  test    ax, ax
0x10040883a  jz      short loc_100408868
0x10040883c  mov     rax, [rsp+1E8h+var_190]
0x100408841  mov     rdx, [rax+20h]
0x100408845  lea     rax, szDefault
0x10040884c  test    rdx, rdx
0x10040884f  cmovnz  rax, rdx
0x100408853  cmp     [rax], di
0x100408856  jz      short loc_100408868
0x100408858  lea     rcx, szDefault
0x10040885f  test    rdx, rdx
0x100408862  cmovnz  rcx, rdx
0x100408866  jmp     short loc_100408881
0x100408868  lea     rcx, aSqlbinary_0; "SQLBINARY"
0x10040886f  jmp     short loc_100408881
0x100408871  lea     rcx, aSqlnchar; "SQLNCHAR"
0x100408878  jmp     short loc_100408881
0x10040887a  lea     rcx, aSqlchar; "SQLCHAR"
0x100408881  call    ?FieldNameToTDSType@@YAEPEBG@Z; FieldNameToTDSType(ushort const *)
0x100408886  mov     r11b, al
0x100408889  mov     [rsp+1E8h+var_1B4], al
0x10040888d  test    al, al
0x10040888f  jz      loc_100408BC6
0x100408895  cmp     dword ptr [r13+1Ch], 2
0x10040889a  jnz     short loc_1004088BD
0x10040889c  mov     eax, [r13+24h]
0x1004088a0  mov     [rsp+1E8h+var_1B8], eax
0x1004088a4  cmp     eax, 8
0x1004088a7  ja      loc_100408BF0
0x1004088ad  mov     ecx, 116h
0x1004088b2  bt      ecx, eax
0x1004088b5  jnb     loc_100408BF0
0x1004088bb  jmp     short loc_1004088C1
0x1004088bd  mov     [rsp+1E8h+var_1B8], edi
0x1004088c1  mov     r10d, [r13+20h]
0x1004088c5  mov     [rsp+1E8h+var_198], r10d
0x1004088ca  test    r10d, r10d
0x1004088cd  js      loc_100408C1A
0x1004088d3  cmp     dword ptr [r13+1Ch], 3
0x1004088d8  jnz     loc_1004089BE
0x1004088de  mov     rcx, [r13+28h]
0x1004088e2  test    rcx, rcx
0x1004088e5  jz      short loc_1004088F5
0x1004088e7  mov     rax, r15
0x1004088ea  inc     rax
0x1004088ed  cmp     [rcx+rax*2], di
0x1004088f1  jnz     short loc_1004088EA
0x1004088f3  jmp     short loc_1004088F8
0x1004088f5  mov     rax, rdi
0x1004088f8  shl     rax, 2
0x1004088fc  mov     [rsp+1E8h+var_188], rax
0x100408901  lea     rdx, [rax+1]
0x100408905  mov     [rsp+1E8h+var_138], rdx
0x10040890d  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x100408914  mov     rax, [rcx]
0x100408917  mov     rax, [rax+70h]
0x10040891b  call    cs:__guard_dispatch_icall_fptr
0x100408921  mov     r14, rax
0x100408924  mov     [rsp+1E8h+var_1A8], rax
0x100408929  test    rax, rax
0x10040892c  jnz     short loc_10040894D
0x10040892e  mov     esi, 8007000Eh
0x100408933  lea     rcx, [rsp+1E8h+var_D8]; this
0x10040893b  call    ??1CBulkFormat@@QEAA@XZ; CBulkFormat::~CBulkFormat(void)
0x100408940  nop
0x100408941  lea     r13, ??_7CFileReadStream@@6B@; const CFileReadStream::`vftable'
0x100408948  jmp     loc_100408AF8
0x10040894d  mov     rdx, [r13+28h]
0x100408951  test    rdx, rdx
0x100408954  jz      short loc_100408964
0x100408956  mov     rax, r15
0x100408959  inc     rax
0x10040895c  cmp     [rdx+rax*2], di
0x100408960  jnz     short loc_100408959
0x100408962  jmp     short loc_10040896E
0x100408964  mov     rax, rdi
0x100408967  lea     rdx, szDefault; Source
0x10040896e  mov     r8, [rsp+1E8h+var_188]
0x100408973  cmp     rax, r8
0x100408976  cmovb   r8, rax; MaxCount
0x10040897a  mov     rcx, r14; Dest
0x10040897d  call    cs:__imp_wcstombs
0x100408983  mov     rcx, rdi
0x100408986  test    rax, rax
0x100408989  cmovnz  rcx, rax
0x10040898d  mov     rax, [rsp+1E8h+var_188]
0x100408992  cmp     rcx, rax
0x100408995  cmovb   rax, rcx
0x100408999  mov     [rax+r14], dil
0x10040899d  mov     r8, [rsp+1E8h+var_138]; unsigned __int64
0x1004089a5  mov     rdx, r14; unsigned __int8 *
0x1004089a8  mov     rcx, r14; unsigned __int8 *
0x1004089ab  call    ?ConvertTerminatorToBinary@@YAHPEBEPEAE_K@Z; ConvertTerminatorToBinary(uchar const *,uchar *,unsigned __int64)
0x1004089b0  mov     r9d, eax
0x1004089b3  cmp     eax, r15d
0x1004089b6  jz      loc_100408C44
0x1004089bc  jmp     short loc_1004089CB
0x1004089be  mov     r14, rdi
0x1004089c1  mov     [rsp+1E8h+var_1A8], rdi
0x1004089c6  mov     r9d, edi
0x1004089c9  jmp     short loc_1004089D5
0x1004089cb  mov     r10d, [rsp+1E8h+var_198]
0x1004089d0  mov     r11b, [rsp+1E8h+var_1B4]
0x1004089d5  mov     rdx, [r13+10h]
0x1004089d9  test    rdx, rdx
0x1004089dc  jz      short loc_1004089F8
0x1004089de  mov     rax, r15
0x1004089e1  inc     rax
0x1004089e4  cmp     [rdx+rax*2], di
0x1004089e8  jnz     short loc_1004089E1
0x1004089ea  cmp     rax, 80h
0x1004089f0  ja      loc_100408C6E
0x1004089f6  jmp     short loc_1004089FF
0x1004089f8  lea     rdx, szDefault
0x1004089ff  lea     rcx, [rsi+18h]
0x100408a03  mov     r8d, 81h
0x100408a09  sub     rdx, rcx
0x100408a0c  lea     rax, [r8+7FFFFF7Dh]
0x100408a13  test    rax, rax
0x100408a16  jz      short loc_100408A2E
0x100408a18  movzx   eax, word ptr [rdx+rcx]
0x100408a1c  test    ax, ax
0x100408a1f  jz      short loc_100408A2E
0x100408a21  mov     [rcx], ax
0x100408a24  add     rcx, 2
0x100408a28  sub     r8, 1
0x100408a2c  jnz     short loc_100408A0C
0x100408a2e  lea     rax, [rcx-2]
0x100408a32  test    r8, r8
0x100408a35  cmovnz  rax, rcx
0x100408a39  mov     [rax], di
0x100408a3c  mov     rax, r8
0x100408a3f  neg     rax
0x100408a42  sbb     esi, esi
0x100408a44  not     esi
0x100408a46  and     esi, 8007007Ah
0x100408a4c  test    r8, r8
0x100408a4f  jnz     short loc_100408A7E
0x100408a51  test    byte ptr cs:_bidGblFlags, 2
0x100408a58  jz      short loc_100408A67
0x100408a5a  mov     edx, 154409h
0x100408a5f  xor     ecx, ecx
0x100408a61  call    _bidTraceMark
0x100408a66  nop
0x100408a67  lea     rcx, [rsp+1E8h+var_D8]; this
0x100408a6f  call    ??1CBulkFormat@@QEAA@XZ; CBulkFormat::~CBulkFormat(void)
0x100408a74  nop
0x100408a75  lea     r13, ??_7CFileReadStream@@6B@; const CFileReadStream::`vftable'
0x100408a7c  jmp     short loc_100408AD9
  ... truncated ...
```
