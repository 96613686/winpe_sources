# dia::CDiaLoadCallback::getAltDbgInfo(ArrayBufStorage<DiaAddressMapEntry> * *,ArrayBufStorage<DiaAddressMapEntry> * *,ArrayBufStorage<_IMAGE_SECTION_HEADER> * *,ulong &,ArrayBufStorage<_FPO_DATA> * *,ArrayBufStorage<tagXFIXUP_DATA> * *,_iobuf * *)

- ea: `0x180110350`
- end: `0x180110902`
- name: `?getAltDbgInfo@CDiaLoadCallback@dia@@QEAAXPEAPEAV?$ArrayBufStorage@UDiaAddressMapEntry@@@@0PEAPEAV?$ArrayBufStorage@U_IMAGE_SECTION_HEADER@@@@AEAKPEAPEAV?$ArrayBufStorage@U_FPO_DATA@@@@PEAPEAV?$ArrayBufStorage@UtagXFIXUP_DATA@@@@PEAPEAU_iobuf@@@Z`
- size: `1458`
- prototype: `__int64 __usercall@<rax>(dia::CDiaLoadCallback *this@<rcx>, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800ae800`

## callees

- `0x1800269d4`
- `0x180027430`
- `0x18010f6e0`
- `0x18010f8c0`
- `0x180110350`
- `0x1801d6350`
- `0x1801d63b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfsopen` at `0x18011040c`
- `api-ms-win-crt-private-l1-1-0!_o__wfsopen` at `0x18011056c`
- `api-ms-win-crt-private-l1-1-0!_o__wfsopen` at `0x18011040c`
- `api-ms-win-crt-private-l1-1-0!_o__wfsopen` at `0x18011056c`

## pseudocode

```c
char __fastcall dia::CDiaLoadCallback::getAltDbgInfo(
        dia::CDiaLoadCallback *this,
        struct BufferStorage **a2,
        __int64 *a3,
        __int64 *a4,
        _DWORD *a5,
        __int64 *a6,
        struct BufferStorage **a7,
        __int64 *a8)
{
  bool v8; // zf
  const wchar_t *v13; // rcx
  __int64 v14; // rax
  int v15; // eax
  struct BufferStorage *v16; // rdi
  __int64 v17; // rcx
  const wchar_t *v18; // rcx
  __int64 v19; // rdx
  int v20; // r8d
  struct BufferStorage *v21; // rdi
  struct BufferStorage *v22; // rax
  int v23; // r8d
  unsigned int v24; // edx
  struct BufferStorage *v25; // rdi
  __int64 v26; // rdx
  int v27; // r8d
  struct BufferStorage *v28; // rdi
  __int64 v29; // rdx
  int v30; // r8d
  struct BufferStorage *v31; // rdi
  struct BufferStorage *v32; // rax
  struct BufferStorage *v34; // [rsp+20h] [rbp-E0h] BYREF
  struct BufferStorage **v35; // [rsp+28h] [rbp-D8h]
  __int128 v36; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v37; // [rsp+40h] [rbp-C0h]
  __int128 v38; // [rsp+50h] [rbp-B0h]
  int v39[4]; // [rsp+60h] [rbp-A0h]
  int v40; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v41; // [rsp+76h] [rbp-8Ah]
  unsigned __int16 v42; // [rsp+84h] [rbp-7Ch]

  v8 = *((_BYTE *)this + 212) == 0;
  v35 = a7;
  if ( !v8 || *((_BYTE *)this + 228) || *((_BYTE *)this + 244) || *((_BYTE *)this + 260) )
  {
    if ( *((_QWORD *)this + 14) || *((_QWORD *)this + 15) )
      goto LABEL_26;
    v18 = (const wchar_t *)*((_QWORD *)this + 24);
    v14 = -1;
    do
      ++v14;
    while ( v18[v14] );
    if ( v14 )
    {
      v14 = (__int64)_wfsopen(v18, L"rb", 64);
      *((_QWORD *)this + 33) = v14;
    }
    if ( *((_QWORD *)this + 33) )
    {
LABEL_26:
      v36 = 0;
      v37 = 0;
      v38 = 0;
      *(_OWORD *)v39 = 0;
      dia::CDiaLoadCallback::Fread(this, &v36, 0, 0x40u);
      memset_0(&v40, 0, 0xF8u);
      LOBYTE(v14) = dia::CDiaLoadCallback::Fread(this, &v40, v39[3], 0xF8u);
      if ( v40 != 17744 )
        goto LABEL_31;
      if ( !v41 )
        goto LABEL_31;
      v34 = 0;
      LOBYTE(v14) = dia::CDiaLoadCallback::LoadBytes(this, 40 * v41, v42 + 24 + v39[3], &v34);
      v16 = v34;
      if ( !v34 )
        goto LABEL_31;
      v14 = (__int64)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
      v34 = (struct BufferStorage *)v14;
      v17 = v14;
      if ( v14 )
        goto LABEL_17;
      *a4 = 0;
      goto LABEL_31;
    }
  }
  else
  {
    v13 = (const wchar_t *)*((_QWORD *)this + 20);
    v14 = -1;
    do
      ++v14;
    while ( v13[v14] );
    if ( v14 )
    {
      v14 = (__int64)_wfsopen(v13, L"rb", 64);
      *((_QWORD *)this + 33) = v14;
    }
    if ( *((_QWORD *)this + 33) )
    {
      v36 = 0;
      v37 = 0;
      v38 = 0;
      dia::CDiaLoadCallback::Fread(this, &v36, 0, 0x30u);
      LOBYTE(v14) = 68;
      if ( (_WORD)v36 != 18756 )
        goto LABEL_31;
      v15 = DWORD2(v38);
      *a5 = 0;
      if ( v15 || (v15 = DWORD1(v38)) != 0 )
        *a5 = v15;
      LOBYTE(v14) = BYTE8(v37);
      if ( !DWORD2(v37) )
        goto LABEL_31;
      v34 = 0;
      LOBYTE(v14) = dia::CDiaLoadCallback::LoadBytes(this, 40 * DWORD2(v37), 48, &v34);
      v16 = v34;
      if ( !v34 )
        goto LABEL_31;
      v14 = (__int64)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
      v34 = (struct BufferStorage *)v14;
      v17 = v14;
      if ( v14 )
      {
LABEL_17:
        *(_DWORD *)(v14 + 8) = 0;
        *(_QWORD *)v14 = &CDiaBase::`vftable';
        _InterlockedIncrement(&CDiaBase::m_objects);
        *(_QWORD *)(v14 + 16) = v16;
        *(_QWORD *)v17 = &ArrayBufStorage<tagXFIXUP_DATA>::`vftable';
        *a4 = v17;
        LOBYTE(v14) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
        goto LABEL_31;
      }
      *a4 = 0;
      LOBYTE(v14) = (*(__int64 (__fastcall **)(struct BufferStorage *, __int64))(*(_QWORD *)v16 + 16LL))(v16, 1);
LABEL_31:
      v19 = *((_QWORD *)this + 25);
      if ( v19 && *((_QWORD *)this + 27) )
      {
        v20 = *((_DWORD *)this + 52);
        v34 = 0;
        dia::CDiaLoadCallback::LoadBytes(this, v19, v20, &v34);
        v21 = v34;
        if ( v34 )
        {
          v22 = (struct BufferStorage *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
          v34 = v22;
          if ( v22 )
          {
            *((_DWORD *)v22 + 2) = 0;
            *(_QWORD *)v22 = &CDiaBase::`vftable';
            _InterlockedIncrement(&CDiaBase::m_objects);
            *((_QWORD *)v22 + 2) = v21;
            *(_QWORD *)v22 = &ArrayBufStorage<tagXFIXUP_DATA>::`vftable';
            *a2 = v22;
            (*(void (__fastcall **)(struct BufferStorage *))(*(_QWORD *)v22 + 8LL))(v22);
          }
          else
          {
            *a2 = 0;
          }
        }
        v23 = *((_DWORD *)this + 56);
        v24 = *((_DWORD *)this + 54);
        v34 = 0;
        LOBYTE(v14) = dia::CDiaLoadCallback::LoadBytes(this, v24, v23, &v34);
        v25 = v34;
        if ( v34 )
        {
          v14 = (__int64)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
          v34 = (struct BufferStorage *)v14;
          if ( v14 )
          {
            *(_QWORD *)v14 = &CDiaBase::`vftable';
            *(_DWORD *)(v14 + 8) = 0;
            _InterlockedIncrement(&CDiaBase::m_objects);
            *(_QWORD *)(v14 + 16) = v25;
            *(_QWORD *)v14 = &ArrayBufStorage<tagXFIXUP_DATA>::`vftable';
            *a3 = v14;
            LOBYTE(v14) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
          }
          else
          {
            *a3 = 0;
          }
        }
      }
      v26 = *((_QWORD *)this + 29);
      if ( v26 )
      {
        v27 = *((_DWORD *)this + 60);
        v34 = 0;
        LOBYTE(v14) = dia::CDiaLoadCallback::LoadBytes(this, v26, v27, &v34);
        v28 = v34;
        if ( v34 )
        {
          v14 = (__int64)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
          v34 = (struct BufferStorage *)v14;
          if ( v14 )
          {
            *(_QWORD *)v14 = &CDiaBase::`vftable';
            *(_DWORD *)(v14 + 8) = 0;
            _InterlockedIncrement(&CDiaBase::m_objects);
            *(_QWORD *)(v14 + 16) = v28;
            *(_QWORD *)v14 = &ArrayBufStorage<tagXFIXUP_DATA>::`vftable';
            *a6 = v14;
            LOBYTE(v14) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
          }
          else
          {
            *a6 = 0;
          }
        }
      }
      v29 = *((_QWORD *)this + 31);
      if ( v29 )
      {
        v30 = *((_DWORD *)this + 64);
        v34 = 0;
        LOBYTE(v14) = dia::CDiaLoadCallback::LoadBytes(this, v29, v30, &v34);
        v31 = v34;
        if ( v34 )
        {
          v32 = (struct BufferStorage *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
          v34 = v32;
          if ( v32 )
          {
            *(_QWORD *)v32 = &CDiaBase::`vftable';
            *((_DWORD *)v32 + 2) = 0;
            _InterlockedIncrement(&CDiaBase::m_objects);
            *((_QWORD *)v32 + 2) = v31;
            *(_QWORD *)v32 = &ArrayBufStorage<tagXFIXUP_DATA>::`vftable';
            *v35 = v32;
            LOBYTE(v14) = (*(__int64 (__fastcall **)(struct BufferStorage *))(*(_QWORD *)v32 + 8LL))(v32);
          }
          else
          {
            LOBYTE(v14) = (_BYTE)v35;
            *v35 = 0;
          }
        }
      }
      if ( a8 )
      {
        v14 = *((_QWORD *)this + 33);
        if ( v14 )
          *a8 = v14;
      }
    }
  }
  return v14;
}

```

## disassembly

```asm
0x180110350  push    rbp
0x180110352  push    rbx
0x180110353  push    rsi
0x180110354  push    rdi
0x180110355  push    r12
0x180110357  push    r13
0x180110359  push    r14
0x18011035b  push    r15
0x18011035d  lea     rbp, [rsp-88h]
0x180110365  sub     rsp, 188h
0x18011036c  mov     rax, cs:__security_cookie
0x180110373  xor     rax, rsp
0x180110376  mov     [rbp+0C0h+var_50], rax
0x18011037a  cmp     byte ptr [rcx+0D4h], 0
0x180110381  mov     rsi, r9
0x180110384  mov     rax, [rbp+0C0h+arg_30]
0x18011038b  mov     r15, r8
0x18011038e  mov     rdi, [rbp+0C0h+arg_20]
0x180110395  mov     r14, rdx
0x180110398  mov     r13, [rbp+0C0h+arg_28]
0x18011039f  mov     rbx, rcx
0x1801103a2  mov     r12, [rbp+0C0h+arg_38]
0x1801103a9  mov     [rsp+1C0h+var_198], rax
0x1801103ae  jnz     loc_18011052D
0x1801103b4  cmp     byte ptr [rcx+0E4h], 0
0x1801103bb  jnz     loc_18011052D
0x1801103c1  cmp     byte ptr [rcx+0F4h], 0
0x1801103c8  jnz     loc_18011052D
0x1801103ce  cmp     byte ptr [rcx+104h], 0
0x1801103d5  jnz     loc_18011052D
0x1801103db  mov     rcx, [rcx+0A0h]; FileName
0x1801103e2  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1801103e9  nop     dword ptr [rax+00000000h]
0x1801103f0  inc     rax
0x1801103f3  cmp     word ptr [rcx+rax*2], 0
0x1801103f8  jnz     short loc_1801103F0
0x1801103fa  test    rax, rax
0x1801103fd  jz      short loc_180110419
0x1801103ff  mov     r8d, 40h ; '@'; ShFlag
0x180110405  lea     rdx, aRb; "rb"
0x18011040c  call    cs:__imp__wfsopen
0x180110412  mov     [rbx+108h], rax
0x180110419  cmp     qword ptr [rbx+108h], 0
0x180110421  jz      loc_1801108E2
0x180110427  xorps   xmm0, xmm0
0x18011042a  lea     rdx, [rsp+1C0h+var_190]; void *
0x18011042f  mov     r9d, 30h ; '0'; unsigned __int64
0x180110435  xor     r8d, r8d; int
0x180110438  mov     rcx, rbx; this
0x18011043b  movups  [rsp+1C0h+var_190], xmm0
0x180110440  movups  [rsp+1C0h+var_180], xmm0
0x180110445  movups  [rsp+1C0h+var_170], xmm0
0x18011044a  call    ?Fread@CDiaLoadCallback@dia@@IEAA_NPEAXJ_K@Z; dia::CDiaLoadCallback::Fread(void *,long,unsigned __int64)
0x18011044f  mov     eax, 4944h
0x180110454  cmp     word ptr [rsp+1C0h+var_190], ax
0x180110459  jnz     loc_180110691
0x18011045f  mov     eax, dword ptr [rsp+1C0h+var_170+8]
0x180110463  xor     ecx, ecx
0x180110465  mov     [rdi], ecx
0x180110467  test    eax, eax
0x180110469  jnz     short loc_180110473
0x18011046b  mov     eax, dword ptr [rsp+1C0h+var_170+4]
0x18011046f  test    eax, eax
0x180110471  jz      short loc_180110475
0x180110473  mov     [rdi], eax
0x180110475  mov     eax, dword ptr [rsp+1C0h+var_180+8]
0x180110479  test    rax, rax
0x18011047c  jz      loc_180110691
0x180110482  lea     edx, [rax+rax*4]
0x180110485  mov     [rsp+1C0h+var_1A0], rcx
0x18011048a  shl     edx, 3; unsigned int
0x18011048d  lea     r9, [rsp+1C0h+var_1A0]; struct BufferStorage **
0x180110492  mov     r8d, 30h ; '0'; int
0x180110498  mov     rcx, rbx; this
0x18011049b  call    ?LoadBytes@CDiaLoadCallback@dia@@IEAA_NKJPEAPEAVBufferStorage@@@Z; dia::CDiaLoadCallback::LoadBytes(ulong,long,BufferStorage * *)
0x1801104a0  mov     rdi, [rsp+1C0h+var_1A0]
0x1801104a5  test    rdi, rdi
0x1801104a8  jz      loc_180110691
0x1801104ae  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801104b5  mov     ecx, 18h; unsigned __int64
0x1801104ba  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1801104bf  mov     [rsp+1C0h+var_1A0], rax
0x1801104c4  mov     rcx, rax
0x1801104c7  test    rax, rax
0x1801104ca  jz      short loc_18011050C
0x1801104cc  lea     rax, ??_7CDiaBase@@6B@; const CDiaBase::`vftable'
0x1801104d3  mov     dword ptr [rcx+8], 0
0x1801104da  mov     [rcx], rax
0x1801104dd  lock inc cs:?m_objects@CDiaBase@@2JA; long CDiaBase::m_objects
0x1801104e4  mov     [rcx+10h], rdi
0x1801104e8  lea     rax, ??_7?$ArrayBufStorage@UtagXFIXUP_DATA@@@@6B@; const ArrayBufStorage<tagXFIXUP_DATA>::`vftable'
0x1801104ef  mov     [rcx], rax
0x1801104f2  mov     [rsi], rcx
0x1801104f5  test    rcx, rcx
0x1801104f8  jz      short loc_180110513
0x1801104fa  mov     rax, [rcx]
0x1801104fd  mov     rax, [rax+8]
0x180110501  call    cs:__guard_dispatch_icall_fptr
0x180110507  jmp     loc_180110691
0x18011050c  mov     qword ptr [rsi], 0
0x180110513  mov     rax, [rdi]
0x180110516  mov     edx, 1
0x18011051b  mov     rcx, rdi
0x18011051e  mov     rax, [rax+10h]
0x180110522  call    cs:__guard_dispatch_icall_fptr
0x180110528  jmp     loc_180110691
0x18011052d  cmp     qword ptr [rcx+70h], 0
0x180110532  jnz     short loc_180110587
0x180110534  cmp     qword ptr [rcx+78h], 0
0x180110539  jnz     short loc_180110587
0x18011053b  mov     rcx, [rcx+0C0h]; FileName
0x180110542  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180110549  nop     dword ptr [rax+00000000h]
0x180110550  inc     rax
0x180110553  cmp     word ptr [rcx+rax*2], 0
0x180110558  jnz     short loc_180110550
0x18011055a  test    rax, rax
0x18011055d  jz      short loc_180110579
0x18011055f  mov     r8d, 40h ; '@'; ShFlag
0x180110565  lea     rdx, aRb; "rb"
0x18011056c  call    cs:__imp__wfsopen
0x180110572  mov     [rbx+108h], rax
0x180110579  cmp     qword ptr [rbx+108h], 0
0x180110581  jz      loc_1801108E2
0x180110587  xorps   xmm0, xmm0
0x18011058a  lea     rdx, [rsp+1C0h+var_190]; void *
0x18011058f  mov     r9d, 40h ; '@'; unsigned __int64
0x180110595  xor     r8d, r8d; int
0x180110598  mov     rcx, rbx; this
0x18011059b  movups  [rsp+1C0h+var_190], xmm0
0x1801105a0  movups  [rsp+1C0h+var_180], xmm0
0x1801105a5  movups  [rsp+1C0h+var_170], xmm0
0x1801105aa  movups  xmmword ptr [rsp+1C0h+var_160], xmm0
0x1801105af  call    ?Fread@CDiaLoadCallback@dia@@IEAA_NPEAXJ_K@Z; dia::CDiaLoadCallback::Fread(void *,long,unsigned __int64)
0x1801105b4  xor     edx, edx; Val
0x1801105b6  lea     rcx, [rsp+1C0h+var_150]; void *
0x1801105bb  mov     r8d, 0F8h; Size
0x1801105c1  call    memset_0
0x1801105c6  mov     r8d, [rsp+1C0h+var_160+0Ch]; int
0x1801105cb  lea     rdx, [rsp+1C0h+var_150]; void *
0x1801105d0  mov     r9d, 0F8h; unsigned __int64
0x1801105d6  mov     rcx, rbx; this
0x1801105d9  call    ?Fread@CDiaLoadCallback@dia@@IEAA_NPEAXJ_K@Z; dia::CDiaLoadCallback::Fread(void *,long,unsigned __int64)
0x1801105de  cmp     [rsp+1C0h+var_150], 4550h
0x1801105e6  jnz     loc_180110691
0x1801105ec  movzx   edx, [rsp+1C0h+var_14A]
0x1801105f1  test    rdx, rdx
0x1801105f4  jz      loc_180110691
0x1801105fa  movzx   ecx, [rbp+0C0h+var_13C]
0x1801105fe  lea     edx, [rdx+rdx*4]
0x180110601  mov     r8d, [rsp+1C0h+var_160+0Ch]
0x180110606  lea     r9, [rsp+1C0h+var_1A0]; struct BufferStorage **
0x18011060b  add     ecx, 18h
0x18011060e  shl     edx, 3; unsigned int
0x180110611  add     r8d, ecx; int
0x180110614  mov     [rsp+1C0h+var_1A0], 0
0x18011061d  mov     rcx, rbx; this
0x180110620  call    ?LoadBytes@CDiaLoadCallback@dia@@IEAA_NKJPEAPEAVBufferStorage@@@Z; dia::CDiaLoadCallback::LoadBytes(ulong,long,BufferStorage * *)
0x180110625  mov     rdi, [rsp+1C0h+var_1A0]
0x18011062a  test    rdi, rdi
0x18011062d  jz      short loc_180110691
0x18011062f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180110636  mov     ecx, 18h; unsigned __int64
0x18011063b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180110640  mov     [rsp+1C0h+var_1A0], rax
0x180110645  mov     rcx, rax
0x180110648  test    rax, rax
0x18011064b  jz      short loc_18011068A
0x18011064d  lea     rax, ??_7CDiaBase@@6B@; const CDiaBase::`vftable'
0x180110654  mov     dword ptr [rcx+8], 0
0x18011065b  mov     [rcx], rax
0x18011065e  lock inc cs:?m_objects@CDiaBase@@2JA; long CDiaBase::m_objects
0x180110665  mov     [rcx+10h], rdi
0x180110669  lea     rax, ??_7?$ArrayBufStorage@UtagXFIXUP_DATA@@@@6B@; const ArrayBufStorage<tagXFIXUP_DATA>::`vftable'
0x180110670  mov     [rcx], rax
0x180110673  mov     [rsi], rcx
0x180110676  test    rcx, rcx
0x180110679  jz      short loc_180110691
0x18011067b  mov     rax, [rcx]
0x18011067e  mov     rax, [rax+8]
0x180110682  call    cs:__guard_dispatch_icall_fptr
0x180110688  jmp     short loc_180110691
0x18011068a  mov     qword ptr [rsi], 0
0x180110691  mov     rdx, [rbx+0C8h]; unsigned int
0x180110698  xor     esi, esi
0x18011069a  test    rdx, rdx
0x18011069d  jz      loc_1801107B2
0x1801106a3  cmp     [rbx+0D8h], rsi
0x1801106aa  jz      loc_1801107B2
0x1801106b0  mov     r8d, [rbx+0D0h]; int
0x1801106b7  lea     r9, [rsp+1C0h+var_1A0]; struct BufferStorage **
0x1801106bc  mov     rcx, rbx; this
0x1801106bf  mov     [rsp+1C0h+var_1A0], rsi
0x1801106c4  call    ?LoadBytes@CDiaLoadCallback@dia@@IEAA_NKJPEAPEAVBufferStorage@@@Z; dia::CDiaLoadCallback::LoadBytes(ulong,long,BufferStorage * *)
0x1801106c9  mov     rdi, [rsp+1C0h+var_1A0]
0x1801106ce  test    rdi, rdi
0x1801106d1  jz      short loc_18011072D
0x1801106d3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801106da  mov     ecx, 18h; unsigned __int64
0x1801106df  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1801106e4  mov     [rsp+1C0h+var_1A0], rax
0x1801106e9  mov     rcx, rax
0x1801106ec  test    rax, rax
0x1801106ef  jz      short loc_18011072A
0x1801106f1  lea     rax, ??_7CDiaBase@@6B@; const CDiaBase::`vftable'
0x1801106f8  mov     [rcx+8], esi
0x1801106fb  mov     [rcx], rax
0x1801106fe  lock inc cs:?m_objects@CDiaBase@@2JA; long CDiaBase::m_objects
0x180110705  mov     [rcx+10h], rdi
0x180110709  lea     rax, ??_7?$ArrayBufStorage@UtagXFIXUP_DATA@@@@6B@; const ArrayBufStorage<tagXFIXUP_DATA>::`vftable'
0x180110710  mov     [rcx], rax
0x180110713  mov     [r14], rcx
0x180110716  test    rcx, rcx
0x180110719  jz      short loc_18011072D
0x18011071b  mov     rax, [rcx]
0x18011071e  mov     rax, [rax+8]
0x180110722  call    cs:__guard_dispatch_icall_fptr
0x180110728  jmp     short loc_18011072D
0x18011072a  mov     [r14], rsi
0x18011072d  mov     r8d, [rbx+0E0h]; int
0x180110734  lea     r9, [rsp+1C0h+var_1A0]; struct BufferStorage **
0x180110739  mov     edx, [rbx+0D8h]; unsigned int
0x18011073f  mov     rcx, rbx; this
0x180110742  mov     [rsp+1C0h+var_1A0], rsi
0x180110747  call    ?LoadBytes@CDiaLoadCallback@dia@@IEAA_NKJPEAPEAVBufferStorage@@@Z; dia::CDiaLoadCallback::LoadBytes(ulong,long,BufferStorage * *)
0x18011074c  mov     rdi, [rsp+1C0h+var_1A0]
0x180110751  test    rdi, rdi
0x180110754  jz      short loc_1801107B2
0x180110756  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18011075d  mov     ecx, 18h; unsigned __int64
0x180110762  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180110767  mov     [rsp+1C0h+var_1A0], rax
0x18011076c  mov     rcx, rax
0x18011076f  lea     r14, ??_7CDiaBase@@6B@; const CDiaBase::`vftable'
0x180110776  test    rax, rax
0x180110779  jz      short loc_1801107AD
0x18011077b  mov     [rax], r14
0x18011077e  mov     [rax+8], esi
0x180110781  lock inc cs:?m_objects@CDiaBase@@2JA; long CDiaBase::m_objects
0x180110788  mov     [rcx+10h], rdi
0x18011078c  lea     rax, ??_7?$ArrayBufStorage@UtagXFIXUP_DATA@@@@6B@; const ArrayBufStorage<tagXFIXUP_DATA>::`vftable'
0x180110793  mov     [rcx], rax
0x180110796  mov     [r15], rcx
0x180110799  test    rcx, rcx
0x18011079c  jz      short loc_1801107B9
0x18011079e  mov     rax, [rcx]
0x1801107a1  mov     rax, [rax+8]
0x1801107a5  call    cs:__guard_dispatch_icall_fptr
0x1801107ab  jmp     short loc_1801107B9
0x1801107ad  mov     [r15], rsi
0x1801107b0  jmp     short loc_1801107B9
0x1801107b2  lea     r14, ??_7CDiaBase@@6B@; const CDiaBase::`vftable'
0x1801107b9  mov     rdx, [rbx+0E8h]; unsigned int
0x1801107c0  test    rdx, rdx
0x1801107c3  jz      short loc_18011083D
0x1801107c5  mov     r8d, [rbx+0F0h]; int
0x1801107cc  lea     r9, [rsp+1C0h+var_1A0]; struct BufferStorage **
0x1801107d1  mov     rcx, rbx; this
0x1801107d4  mov     [rsp+1C0h+var_1A0], rsi
0x1801107d9  call    ?LoadBytes@CDiaLoadCallback@dia@@IEAA_NKJPEAPEAVBufferStorage@@@Z; dia::CDiaLoadCallback::LoadBytes(ulong,long,BufferStorage * *)
0x1801107de  mov     rdi, [rsp+1C0h+var_1A0]
0x1801107e3  test    rdi, rdi
0x1801107e6  jz      short loc_18011083D
0x1801107e8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801107ef  mov     ecx, 18h; unsigned __int64
0x1801107f4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1801107f9  mov     [rsp+1C0h+var_1A0], rax
0x1801107fe  mov     rcx, rax
0x180110801  test    rax, rax
0x180110804  jz      short loc_180110839
0x180110806  mov     [rax], r14
0x180110809  mov     [rax+8], esi
0x18011080c  lock inc cs:?m_objects@CDiaBase@@2JA; long CDiaBase::m_objects
0x180110813  mov     [rcx+10h], rdi
0x180110817  lea     rax, ??_7?$ArrayBufStorage@UtagXFIXUP_DATA@@@@6B@; const ArrayBufStorage<tagXFIXUP_DATA>::`vftable'
0x18011081e  mov     [rcx], rax
0x180110821  mov     [r13+0], rcx
0x180110825  test    rcx, rcx
0x180110828  jz      short loc_18011083D
0x18011082a  mov     rax, [rcx]
0x18011082d  mov     rax, [rax+8]
0x180110831  call    cs:__guard_dispatch_icall_fptr
0x180110837  jmp     short loc_18011083D
0x180110839  mov     [r13+0], rsi
0x18011083d  mov     rdx, [rbx+0F8h]; unsigned int
0x180110844  test    rdx, rdx
0x180110847  jz      loc_1801108CD
0x18011084d  mov     r8d, [rbx+100h]; int
0x180110854  lea     r9, [rsp+1C0h+var_1A0]; struct BufferStorage **
0x180110859  mov     rcx, rbx; this
0x18011085c  mov     [rsp+1C0h+var_1A0], rsi
0x180110861  call    ?LoadBytes@CDiaLoadCallback@dia@@IEAA_NKJPEAPEAVBufferStorage@@@Z; dia::CDiaLoadCallback::LoadBytes(ulong,long,BufferStorage * *)
0x180110866  mov     rdi, [rsp+1C0h+var_1A0]
0x18011086b  test    rdi, rdi
0x18011086e  jz      short loc_1801108CD
0x180110870  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180110877  mov     ecx, 18h; unsigned __int64
0x18011087c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180110881  mov     [rsp+1C0h+var_1A0], rax
0x180110886  mov     rcx, rax
  ... truncated ...
```
