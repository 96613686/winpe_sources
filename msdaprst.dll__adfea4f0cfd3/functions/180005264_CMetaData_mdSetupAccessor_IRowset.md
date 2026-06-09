# CMetaData::mdSetupAccessor(IRowset *)

- ea: `0x180005264`
- end: `0x18000561b`
- name: `?mdSetupAccessor@CMetaData@@AEAA_KPEAUIRowset@@@Z`
- size: `951`
- prototype: `unsigned __int64 __fastcall(CMetaData *__hidden this, struct IRowset *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x1800031e4`

## callees

- `0x180001db8`
- `0x180001dd4`
- `0x180002728`
- `0x180002770`
- `0x1800028b8`
- `0x180005264`
- `0x180005624`
- `0x18001b008`
- `0x18002dca4`
- `0x18002f0e0`
- `0x18002f1a0`
- `0x180031010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800055c3`
- `ole32!CoTaskMemFree` at `0x1800055d4`
- `ole32!CoTaskMemFree` at `0x1800055c3`
- `ole32!CoTaskMemFree` at `0x1800055d4`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CMetaData::mdSetupAccessor(CMetaData *this, struct IRowset *a2)
{
  void *v3; // rcx
  __int64 v4; // rbx
  int v5; // eax
  int v6; // ebx
  int v7; // eax
  int v8; // ebx
  unsigned __int8 *v9; // rbx
  unsigned __int64 v10; // rcx
  __int64 v11; // rax
  void *v12; // rsp
  LPVOID *v13; // r13
  unsigned int v14; // eax
  unsigned __int128 v15; // rax
  unsigned __int64 v16; // kr00_8
  __int64 v17; // rcx
  unsigned int v18; // r15d
  unsigned int v19; // r12d
  LPVOID *v20; // rdi
  int v21; // eax
  int v22; // edi
  int v23; // eax
  int v24; // edi
  LPVOID v26; // [rsp+40h] [rbp+0h] BYREF
  unsigned __int64 v27; // [rsp+48h] [rbp+8h] BYREF
  __int64 v28; // [rsp+50h] [rbp+10h] BYREF
  __int64 v29; // [rsp+58h] [rbp+18h] BYREF
  LPVOID pv; // [rsp+60h] [rbp+20h] BYREF
  __int64 v31; // [rsp+68h] [rbp+28h] BYREF
  unsigned __int8 *v32; // [rsp+70h] [rbp+30h]
  tagDBCOLUMNINFO v33; // [rsp+80h] [rbp+40h] BYREF

  v29 = 0;
  v28 = 0;
  v27 = 0;
  v26 = 0;
  v3 = 0;
  pv = 0;
  v4 = 0;
  v31 = 0;
  if ( a2 )
  {
    v5 = ((__int64 (__fastcall *)(struct IRowset *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
           a2,
           &IID_IColumnsInfo,
           &v29);
    v6 = v5;
    if ( v5 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_180049438[0] )
          bidTraceW(off_1800491B8[0], 675840, off_180049438[0], (unsigned int)v5, 660);
      }
      ThrowHR(v6);
    }
    v7 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *, LPVOID *, LPVOID *))(*(_QWORD *)v29 + 24LL))(
           v29,
           &v27,
           &v26,
           &pv);
    v8 = v7;
    if ( v7 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180049430[0] )
        bidTraceW(off_1800491B8[0], 676864, off_180049430[0], (unsigned int)v7, 661);
      ThrowHR(v8);
    }
    v9 = 0;
    v32 = 0;
    if ( (unsigned int)DownsizeToULONGThrow<unsigned __int64>(v27) > 0xB )
    {
      v14 = DownsizeToULONGThrow<unsigned __int64>(v27);
      v16 = v14;
      v15 = v14 * (unsigned __int128)0x58uLL;
      if ( !is_mul_ok(v16, 0x58u) )
        LODWORD(v15) = -1;
      v9 = MMMAlloc(v15, DWORD2(v15));
      v32 = v9;
      v13 = (LPVOID *)v9;
    }
    else
    {
      v10 = 88LL * (unsigned int)DownsizeToULONGThrow<unsigned __int64>(v27);
      v11 = v10 + 15;
      if ( v10 + 15 < v10 )
        v11 = 0xFFFFFFFFFFFFFF0LL;
      v12 = alloca(v11 & 0xFFFFFFFFFFFFFFF0uLL);
      v13 = &v26;
    }
    OnNullThrowOOM(v13);
    v18 = 0;
    v19 = 0;
    if ( v27 )
    {
      do
      {
        v33 = *(tagDBCOLUMNINFO *)((_BYTE *)v26 + v19);
        v20 = &v13[11 * v18];
        if ( (unsigned int)CMetaData::mdSetupColRSDataBuffer((CMetaData *)v17, (struct tagDBBINDING *)v20, &v33) )
        {
          *v20 = (LPVOID)*((_QWORD *)v26 + 10 * v19 + 2);
          v20[9] = (LPVOID)(*((_QWORD *)v26 + 10 * v19 + 4) + 1LL);
          v17 = 130;
          if ( *((_WORD *)v26 + 40 * v19 + 20) == 130 )
            v20[9] = (LPVOID)1028;
          v20[4] = 0;
          v20[5] = 0;
          v20[6] = 0;
          *(LPVOID *)((char *)v20 + 60) = 0;
          *((_DWORD *)v20 + 20) = 0;
          *((_BYTE *)v20 + 86) = *((_BYTE *)v26 + 80 * v19 + 42);
          LOBYTE(v17) = *((_BYTE *)v26 + 80 * v19 + 43);
          *((_BYTE *)v20 + 87) = v17;
          ++v18;
        }
        ++v19;
      }
      while ( v19 < v27 );
      if ( v18 )
      {
        v21 = ((__int64 (__fastcall *)(struct IRowset *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
                a2,
                &IID_IAccessor,
                &v28);
        v22 = v21;
        if ( v21 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180049428[0] )
            bidTraceW(off_1800491B8[0], 710656, off_180049428[0], (unsigned int)v21, 694);
          ThrowHR(v22);
        }
        v23 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, LPVOID *, __int64, __int64 *, _QWORD))(*(_QWORD *)v28 + 32LL))(
                v28,
                2,
                v18,
                v13,
                9648,
                &v31,
                0);
        v24 = v23;
        if ( v23 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180049420[0] )
            bidTraceW(off_1800491B8[0], 711680, off_180049420[0], (unsigned int)v23, 695);
          ThrowHR(v24);
        }
      }
    }
    operator delete(v9);
    v3 = pv;
    v4 = v31;
  }
  CoTaskMemFree(v3);
  CoTaskMemFree(v26);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v28);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v29);
  return v4;
}

```

## disassembly

```asm
0x180005264  push    rbp
0x180005266  push    rbx
0x180005267  push    rsi
0x180005268  push    rdi
0x180005269  push    r12
0x18000526b  push    r13
0x18000526d  push    r14
0x18000526f  push    r15
0x180005271  sub     rsp, 0E8h
0x180005278  lea     rbp, [rsp+40h]
0x18000527d  mov     rax, cs:__security_cookie
0x180005284  xor     rax, rbp
0x180005287  mov     [rbp+0E0h+var_50], rax
0x18000528e  mov     r14, rdx
0x180005291  xor     edi, edi
0x180005293  mov     [rbp+0E0h+var_C8], rdi
0x180005297  mov     [rbp+0E0h+var_D0], rdi
0x18000529b  mov     [rbp+0E0h+var_D8], rdi
0x18000529f  mov     [rbp+0E0h+var_E0], rdi
0x1800052a3  mov     ecx, edi
0x1800052a5  mov     [rbp+0E0h+pv], rcx
0x1800052a9  mov     ebx, edi
0x1800052ab  mov     [rbp+0E0h+var_B8], rbx
0x1800052af  test    rdx, rdx
0x1800052b2  jz      loc_1800055C3
0x1800052b8  mov     rax, [rdx]
0x1800052bb  lea     r8, [rbp+0E0h+var_C8]
0x1800052bf  lea     rdx, IID_IColumnsInfo
0x1800052c6  mov     rcx, r14
0x1800052c9  mov     rax, [rax]
0x1800052cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052d1  mov     ebx, eax
0x1800052d3  test    eax, eax
0x1800052d5  jns     short loc_180005317
0x1800052d7  test    byte ptr cs:_bidGblFlags, 2
0x1800052de  jz      short loc_18000530F
0x1800052e0  mov     rcx, cs:off_180049438; "<CMetaData::mdSetupAccessor|ADO|ERR>  H"...
0x1800052e7  test    rcx, rcx
0x1800052ea  jz      short loc_18000530F
0x1800052ec  mov     dword ptr [rsp+120h+var_100], 294h
0x1800052f4  mov     r9d, eax
0x1800052f7  mov     r8, cs:off_180049438; "<CMetaData::mdSetupAccessor|ADO|ERR>  H"...
0x1800052fe  mov     edx, 0A5000h
0x180005303  mov     rcx, cs:off_1800491B8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000530a  call    _bidTraceW
0x18000530f  mov     ecx, ebx; int
0x180005311  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180005317  mov     rcx, [rbp+0E0h+var_C8]
0x18000531b  mov     rax, [rcx]
0x18000531e  lea     r9, [rbp+0E0h+pv]
0x180005322  lea     r8, [rbp+0E0h+var_E0]
0x180005326  lea     rdx, [rbp+0E0h+var_D8]
0x18000532a  mov     rax, [rax+18h]
0x18000532e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005333  mov     ebx, eax
0x180005335  test    eax, eax
0x180005337  jns     short loc_180005379
0x180005339  test    byte ptr cs:_bidGblFlags, 2
0x180005340  jz      short loc_180005371
0x180005342  mov     rcx, cs:off_180049430; "<CMetaData::mdSetupAccessor|ADO|ERR>  H"...
0x180005349  test    rcx, rcx
0x18000534c  jz      short loc_180005371
0x18000534e  mov     dword ptr [rsp+120h+var_100], 295h
0x180005356  mov     r9d, eax
0x180005359  mov     r8, cs:off_180049430; "<CMetaData::mdSetupAccessor|ADO|ERR>  H"...
0x180005360  mov     edx, 0A5400h
0x180005365  mov     rcx, cs:off_1800491B8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000536c  call    _bidTraceW
0x180005371  mov     ecx, ebx; int
0x180005373  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180005379  mov     rbx, rdi
0x18000537c  mov     [rbp+0E0h+var_B0], rbx
0x180005380  mov     rcx, [rbp+0E0h+var_D8]
0x180005384  call    ??$DownsizeToULONGThrow@_K@@YAK_KJ@Z; DownsizeToULONGThrow<unsigned __int64>(unsigned __int64,long)
0x180005389  mov     rcx, [rbp+0E0h+var_D8]
0x18000538d  cmp     eax, 0Bh
0x180005390  ja      short loc_1800053C3
0x180005392  call    ??$DownsizeToULONGThrow@_K@@YAK_KJ@Z; DownsizeToULONGThrow<unsigned __int64>(unsigned __int64,long)
0x180005397  mov     eax, eax
0x180005399  imul    rcx, rax, 58h ; 'X'
0x18000539d  lea     rax, [rcx+0Fh]
0x1800053a1  cmp     rax, rcx
0x1800053a4  ja      short loc_1800053B0
0x1800053a6  mov     rax, 0FFFFFFFFFFFFFF0h
0x1800053b0  and     rax, 0FFFFFFFFFFFFFFF0h
0x1800053b4  call    _alloca_probe
0x1800053b9  sub     rsp, rax
0x1800053bc  lea     r13, [rsp+120h+var_E0]
0x1800053c1  jmp     short loc_1800053EE
0x1800053c3  call    ??$DownsizeToULONGThrow@_K@@YAK_KJ@Z; DownsizeToULONGThrow<unsigned __int64>(unsigned __int64,long)
0x1800053c8  mov     ecx, eax
0x1800053ca  mov     eax, 58h ; 'X'
0x1800053cf  mul     rcx
0x1800053d2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800053d9  cmovb   rax, rcx
0x1800053dd  mov     ecx, eax; unsigned int
0x1800053df  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x1800053e4  mov     rbx, rax
0x1800053e7  mov     [rbp+0E0h+var_B0], rax
0x1800053eb  mov     r13, rax
0x1800053ee  mov     rcx, r13; void *
0x1800053f1  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x1800053f6  mov     r15d, edi
0x1800053f9  mov     r12d, edi
0x1800053fc  cmp     [rbp+0E0h+var_D8], rdi
0x180005400  jbe     loc_1800055B3
0x180005406  mov     eax, r12d
0x180005409  lea     rsi, [rax+rax*4]
0x18000540d  add     rsi, rsi
0x180005410  mov     rax, [rbp+0E0h+var_E0]
0x180005414  movups  xmm0, xmmword ptr [rax+rsi*8]
0x180005418  movaps  xmmword ptr [rbp+0E0h+var_A0.pwszName], xmm0
0x18000541c  movups  xmm1, xmmword ptr [rax+rsi*8+10h]
0x180005421  movaps  xmmword ptr [rbp+0E0h+var_A0.iOrdinal], xmm1
0x180005425  movups  xmm0, xmmword ptr [rax+rsi*8+20h]
0x18000542a  movaps  xmmword ptr [rbp+0E0h+var_A0.ulColumnSize], xmm0
0x18000542e  movups  xmm1, xmmword ptr [rax+rsi*8+30h]
0x180005433  movaps  xmmword ptr [rbp+0E0h+var_A0.columnid.uGuid], xmm1
0x180005437  movups  xmm0, xmmword ptr [rax+rsi*8+40h]
0x18000543c  movaps  xmmword ptr [rbp+0E0h+var_A0.columnid.eKind], xmm0
0x180005443  mov     eax, r15d
0x180005446  imul    rdi, rax, 58h ; 'X'
0x18000544a  add     rdi, r13
0x18000544d  lea     r8, [rbp+0E0h+var_A0]; struct tagDBCOLUMNINFO
0x180005451  mov     rdx, rdi; struct tagDBBINDING *
0x180005454  call    ?mdSetupColRSDataBuffer@CMetaData@@AEAAHPEAUtagDBBINDING@@UtagDBCOLUMNINFO@@@Z; CMetaData::mdSetupColRSDataBuffer(tagDBBINDING *,tagDBCOLUMNINFO)
0x180005459  xor     edx, edx
0x18000545b  test    eax, eax
0x18000545d  jz      short loc_1800054BF
0x18000545f  mov     rax, [rbp+0E0h+var_E0]
0x180005463  mov     rcx, [rax+rsi*8+10h]
0x180005468  mov     [rdi], rcx
0x18000546b  mov     rax, [rbp+0E0h+var_E0]
0x18000546f  mov     rcx, [rax+rsi*8+20h]
0x180005474  inc     rcx
0x180005477  mov     [rdi+48h], rcx
0x18000547b  mov     ecx, 82h
0x180005480  mov     rax, [rbp+0E0h+var_E0]
0x180005484  cmp     [rax+rsi*8+28h], cx
0x180005489  jnz     short loc_180005493
0x18000548b  mov     qword ptr [rdi+48h], 404h
0x180005493  mov     [rdi+20h], rdx
0x180005497  mov     [rdi+28h], rdx
0x18000549b  mov     [rdi+30h], rdx
0x18000549f  mov     [rdi+3Ch], rdx
0x1800054a3  mov     [rdi+50h], edx
0x1800054a6  mov     rax, [rbp+0E0h+var_E0]
0x1800054aa  mov     cl, [rax+rsi*8+2Ah]
0x1800054ae  mov     [rdi+56h], cl
0x1800054b1  mov     rax, [rbp+0E0h+var_E0]
0x1800054b5  mov     cl, [rax+rsi*8+2Bh]
0x1800054b9  mov     [rdi+57h], cl
0x1800054bc  inc     r15d
0x1800054bf  inc     r12d
0x1800054c2  mov     eax, r12d
0x1800054c5  cmp     rax, [rbp+0E0h+var_D8]
0x1800054c9  jb      loc_180005406
0x1800054cf  test    r15d, r15d
0x1800054d2  jz      loc_1800055B3
0x1800054d8  mov     rax, [r14]
0x1800054db  lea     r8, [rbp+0E0h+var_D0]
0x1800054df  lea     rdx, IID_IAccessor
0x1800054e6  mov     rcx, r14
0x1800054e9  mov     rax, [rax]
0x1800054ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054f1  mov     edi, eax
0x1800054f3  test    eax, eax
0x1800054f5  jns     short loc_180005537
0x1800054f7  test    byte ptr cs:_bidGblFlags, 2
0x1800054fe  jz      short loc_18000552F
0x180005500  mov     rcx, cs:off_180049428; "<CMetaData::mdSetupAccessor|ADO|ERR>  H"...
0x180005507  test    rcx, rcx
0x18000550a  jz      short loc_18000552F
0x18000550c  mov     dword ptr [rsp+120h+var_100], 2B6h
0x180005514  mov     r9d, eax
0x180005517  mov     r8, cs:off_180049428; "<CMetaData::mdSetupAccessor|ADO|ERR>  H"...
0x18000551e  mov     edx, 0AD800h
0x180005523  mov     rcx, cs:off_1800491B8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000552a  call    _bidTraceW
0x18000552f  mov     ecx, edi; int
0x180005531  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180005537  mov     rcx, [rbp+0E0h+var_D0]
0x18000553b  mov     rax, [rcx]
0x18000553e  mov     r8d, r15d
0x180005541  mov     [rsp+120h+var_F0], 0
0x18000554a  lea     rdx, [rbp+0E0h+var_B8]
0x18000554e  mov     [rsp+120h+var_F8], rdx
0x180005553  mov     [rsp+120h+var_100], 25B0h
0x18000555c  mov     r9, r13
0x18000555f  mov     edx, 2
0x180005564  mov     rax, [rax+20h]
0x180005568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000556d  mov     edi, eax
0x18000556f  test    eax, eax
0x180005571  jns     short loc_1800055B3
0x180005573  test    byte ptr cs:_bidGblFlags, 2
0x18000557a  jz      short loc_1800055AB
0x18000557c  mov     rcx, cs:off_180049420; "<CMetaData::mdSetupAccessor|ADO|ERR>  H"...
0x180005583  test    rcx, rcx
0x180005586  jz      short loc_1800055AB
0x180005588  mov     dword ptr [rsp+120h+var_100], 2B7h
0x180005590  mov     r9d, eax
0x180005593  mov     r8, cs:off_180049420; "<CMetaData::mdSetupAccessor|ADO|ERR>  H"...
0x18000559a  mov     edx, 0ADC00h
0x18000559f  mov     rcx, cs:off_1800491B8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800055a6  call    _bidTraceW
0x1800055ab  mov     ecx, edi; int
0x1800055ad  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800055b3  mov     rcx, rbx; void *
0x1800055b6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800055bb  mov     rcx, [rbp+0E0h+pv]; pv
0x1800055bf  mov     rbx, [rbp+0E0h+var_B8]
0x1800055c3  call    cs:__imp_CoTaskMemFree
0x1800055ca  nop     dword ptr [rax+rax+00h]
0x1800055cf  nop
0x1800055d0  mov     rcx, [rbp+0E0h+var_E0]; pv
0x1800055d4  call    cs:__imp_CoTaskMemFree
0x1800055db  nop     dword ptr [rax+rax+00h]
0x1800055e0  nop
0x1800055e1  lea     rcx, [rbp+0E0h+var_D0]
0x1800055e5  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x1800055ea  nop
0x1800055eb  lea     rcx, [rbp+0E0h+var_C8]
0x1800055ef  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x1800055f4  mov     rax, rbx
0x1800055f7  mov     rcx, [rbp+0E0h+var_50]
0x1800055fe  xor     rcx, rbp; StackCookie
0x180005601  call    __security_check_cookie
0x180005606  lea     rsp, [rbp+0A8h]
0x18000560d  pop     r15
0x18000560f  pop     r14
0x180005611  pop     r13
0x180005613  pop     r12
0x180005615  pop     rdi
0x180005616  pop     rsi
0x180005617  pop     rbx
0x180005618  pop     rbp
0x180005619  retn
```
