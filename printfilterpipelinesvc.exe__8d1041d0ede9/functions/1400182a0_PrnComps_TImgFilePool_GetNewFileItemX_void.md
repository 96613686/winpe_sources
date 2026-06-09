# PrnComps::TImgFilePool::GetNewFileItemX(void)

- ea: `0x1400182a0`
- end: `0x14001858c`
- name: `?GetNewFileItemX@TImgFilePool@PrnComps@@UEAAPEAUIImgWriterFileItemX@@XZ`
- size: `748`
- prototype: `struct IImgWriterFileItemX *__fastcall(PrnComps::TImgFilePool *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x1400181e0`

## callees

- `0x140002070`
- `0x1400021c0`
- `0x140002c74`
- `0x140004281`
- `0x140004484`
- `0x140010e58`
- `0x140013250`
- `0x1400172e8`
- `0x1400177f8`
- `0x140017b90`
- `0x1400182a0`
- `0x140018c3c`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x140046314`
- `0x14004650c`
- `0x140063010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14001835e`
- `KERNEL32!LeaveCriticalSection` at `0x14001835e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14001837a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14001837a`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
struct IImgWriterFileItemX *__fastcall PrnComps::TImgFilePool::GetNewFileItemX(PrnComps::TImgFilePool *this)
{
  PrnComps::TImgWriterFileItem *v2; // rbx
  char *v3; // rsi
  _QWORD *v4; // r8
  PrnComps::TImgWriterFileItem *v5; // rdi
  HRESULT v7; // eax
  int v8; // edx
  const char *v9; // r8
  unsigned int v10; // r9d
  int v11; // edi
  unsigned __int8 v12; // r10
  __int64 i; // r11
  unsigned int v14; // r10d
  unsigned int v15; // r8d
  const struct SplException::TSystemException *v16; // r8
  const struct _GUID *v17; // r9
  int v18; // eax
  const char *v19; // rdx
  const char *v20; // r8
  unsigned int v21; // r9d
  PrnComps::TImgWriterFileItem *v22; // rax
  NCoreLibrary::TString *v23; // rcx
  unsigned int v25; // [rsp+20h] [rbp-E0h]
  const struct win_musl::TStringEllipseBase *v26; // [rsp+28h] [rbp-D8h]
  HINSTANCE v27; // [rsp+30h] [rbp-D0h]
  PrnComps::TImgWriterFileItem *v28; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *v29; // [rsp+48h] [rbp-B8h] BYREF
  PrnComps::TImgWriterFileItem *v30; // [rsp+50h] [rbp-B0h] BYREF
  GUID pguid; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v32[160]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+110h] [rbp+10h] BYREF
  _WORD v34[32]; // [rsp+1B0h] [rbp+B0h] BYREF

  v2 = 0;
  v28 = 0;
  v3 = (char *)this + 128;
  v30 = (PrnComps::TImgFilePool *)((char *)this + 128);
  NCoreLibrary::TCriticalSection::Enter((PrnComps::TImgFilePool *)((char *)this + 128));
  v4 = (_QWORD *)*((_QWORD *)this + 15);
  *(_QWORD *)(v4[2] + 24LL) = v4[3];
  *(_QWORD *)(v4[3] + 16LL) = v4[2];
  v4[2] = v4;
  v4[3] = v4;
  if ( v4 == (_QWORD *)((char *)this + 96) )
    v4 = 0;
  v5 = 0;
  if ( v4 )
  {
    PrnExcept::TRefSmartPtr<PrnComps::TImgWriterFileItem>::operator=(&v28, v4[4]);
    v2 = v28;
    v5 = v28;
    (*(void (__fastcall **)(PrnComps::TImgWriterFileItem *))(*(_QWORD *)v28 + 8LL))(v28);
  }
  if ( (*((_DWORD *)v3 + 11))-- == 1 )
    *((_DWORD *)v3 + 10) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)v3);
  if ( !v5 )
  {
    pguid = 0;
    v7 = CoCreateGuid(&pguid);
    if ( v7 < 0 )
      SplException::RealThrowFromHR((SplException *)(unsigned int)v7, v8, v9, v10);
    v11 = 0;
    while ( memcmp_0(&pguid, &GUID_NULL, 0x10u) )
    {
      if ( (unsigned __int64)v11 >= 0x1D )
      {
        SplException::THResultException::THResultException((SplException::THResultException *)v32, "-", 0);
        SplException::TSystemException::InternalInit(
          (SplException::TSystemException *)v32,
          0x8000FFFF,
          v16,
          v17,
          v25,
          v26,
          v27);
        SplException::TSystemException::Message(
          (SplException::TSystemException *)v32,
          "Guid should always translate into string");
        SplException::THResultException::THResultException(
          (SplException::THResultException *)pExceptionObject,
          (const struct SplException::THResultException *)v32);
        throw (SplException::THResultException *)pExceptionObject;
      }
      v12 = 0;
      for ( i = 0; i != 16; ++i )
      {
        v14 = *((unsigned __int8 *)&pguid.Data1 + i) + (v12 << 8);
        v15 = v14 / 0x26;
        v12 = v14 % 0x26;
        *((_BYTE *)&pguid.Data1 + i) = v15;
      }
      v34[v11++] = PrnComps::TImgFilePool::m_gAlphabet[v12];
    }
    if ( (unsigned __int64)(2LL * v11) >= 0x3C )
      _report_rangecheckfailure();
    v34[v11] = 0;
    v29 = (wchar_t *)&NCoreLibrary::TString::gszNullState;
    v18 = NCoreLibrary::TString::Format(
            (NCoreLibrary::TString *)&v29,
            L"%s%s%s",
            *((_QWORD *)this + 3),
            v34,
            *((_QWORD *)this + 4));
    if ( v18 < 0 )
      SplException::RealThrowFromHR((SplException *)(unsigned int)v18, (int)v19, v20, v21);
    v22 = (PrnComps::TImgWriterFileItem *)operator new(0xB0u, v19, (unsigned int)v20);
    v30 = v22;
    if ( v22 )
      v5 = PrnComps::TImgWriterFileItem::TImgWriterFileItem(
             v22,
             (struct NCoreLibrary::TCriticalSection *)v3,
             this,
             v29,
             *((_DWORD *)this + 10),
             *((_BYTE *)this + 256),
             0);
    else
      v5 = 0;
    v30 = v2;
    v28 = v5;
    PrnExcept::SmartRelease<PrnComps::TImgReaderFileItem>(&v30);
    NCoreLibrary::TString::vFree(v23, v29);
  }
  (*(void (__fastcall **)(PrnComps::TImgFilePool *))(*(_QWORD *)this + 8LL))(this);
  v28 = 0;
  PrnExcept::SmartRelease<PrnComps::TImgReaderFileItem>(&v28);
  return (struct IImgWriterFileItemX *)(((unsigned __int64)v5 + 48) & -(__int64)(v5 != 0));
}

```

## disassembly

```asm
0x1400182a0  mov     [rsp-8+arg_8], rbx
0x1400182a5  mov     [rsp-8+arg_10], rsi
0x1400182aa  push    rbp
0x1400182ab  push    rdi
0x1400182ac  push    r14
0x1400182ae  lea     rbp, [rsp-100h]
0x1400182b6  sub     rsp, 200h
0x1400182bd  mov     rax, cs:__security_cookie
0x1400182c4  xor     rax, rsp
0x1400182c7  mov     [rbp+110h+var_20], rax
0x1400182ce  mov     r14, rcx
0x1400182d1  xor     ebx, ebx
0x1400182d3  mov     [rsp+210h+var_1D0], rbx
0x1400182d8  lea     rsi, [rcx+80h]
0x1400182df  mov     [rsp+210h+var_1C0], rsi
0x1400182e4  mov     rcx, rsi; this
0x1400182e7  call    ?Enter@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Enter(void)
0x1400182ec  nop
0x1400182ed  lea     rdx, [r14+60h]
0x1400182f1  mov     r8, [rdx+18h]
0x1400182f5  mov     rcx, [r8+10h]
0x1400182f9  mov     rax, [r8+18h]
0x1400182fd  mov     [rcx+18h], rax
0x140018301  mov     rcx, [r8+18h]
0x140018305  mov     rax, [r8+10h]
0x140018309  mov     [rcx+10h], rax
0x14001830d  mov     [r8+10h], r8
0x140018311  mov     [r8+18h], r8
0x140018315  xor     eax, eax
0x140018317  cmp     r8, rdx
0x14001831a  cmovz   r8, rax
0x14001831e  xor     edi, edi
0x140018320  test    r8, r8
0x140018323  jz      short loc_14001834B
0x140018325  mov     rdx, [r8+20h]
0x140018329  lea     rcx, [rsp+210h+var_1D0]
0x14001832e  call    ??4?$TRefSmartPtr@VTImgWriterFileItem@PrnComps@@@PrnExcept@@QEAAAEAV01@PEAVTImgWriterFileItem@PrnComps@@@Z; PrnExcept::TRefSmartPtr<PrnComps::TImgWriterFileItem>::operator=(PrnComps::TImgWriterFileItem *)
0x140018333  mov     rbx, [rsp+210h+var_1D0]
0x140018338  mov     rdi, rbx
0x14001833b  mov     rax, [rbx]
0x14001833e  mov     rcx, rbx
0x140018341  mov     rax, [rax+8]
0x140018345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001834a  nop
0x14001834b  add     dword ptr [rsi+2Ch], 0FFFFFFFFh
0x14001834f  mov     eax, [rsi+2Ch]
0x140018352  jnz     short loc_14001835B
0x140018354  mov     dword ptr [rsi+28h], 0
0x14001835b  mov     rcx, rsi; lpCriticalSection
0x14001835e  call    cs:__imp_LeaveCriticalSection
0x140018364  test    rdi, rdi
0x140018367  jnz     loc_14001852D
0x14001836d  xorps   xmm0, xmm0
0x140018370  movups  xmmword ptr [rsp+210h+pguid.Data1], xmm0
0x140018375  lea     rcx, [rsp+210h+pguid]; pguid
0x14001837a  call    cs:__imp_CoCreateGuid
0x140018380  test    eax, eax
0x140018382  jns     short loc_14001838C
0x140018384  mov     ecx, eax; this
0x140018386  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14001838c  xor     edi, edi
0x14001838e  mov     r8d, 10h; Size
0x140018394  lea     rdx, GUID_NULL; Buf2
0x14001839b  lea     rcx, [rsp+210h+pguid]; Buf1
0x1400183a0  call    memcmp_0
0x1400183a5  test    eax, eax
0x1400183a7  jz      loc_140018470
0x1400183ad  movsxd  r9, edi
0x1400183b0  cmp     r9, 1Dh
0x1400183b4  jnb     short loc_14001841C
0x1400183b6  xor     r10b, r10b
0x1400183b9  xor     r11d, r11d
0x1400183bc  movzx   r10d, r10b
0x1400183c0  shl     r10d, 8
0x1400183c4  movzx   eax, byte ptr [rsp+r11+210h+pguid.Data1]
0x1400183ca  add     r10d, eax
0x1400183cd  mov     eax, 0AF286BCBh
0x1400183d2  mul     r10d
0x1400183d5  mov     r8d, r10d
0x1400183d8  sub     r8d, edx
0x1400183db  shr     r8d, 1
0x1400183de  add     r8d, edx
0x1400183e1  shr     r8d, 5
0x1400183e5  movzx   eax, r8b
0x1400183e9  imul    ecx, eax, 26h ; '&'
0x1400183ec  sub     r10b, cl
0x1400183ef  mov     byte ptr [rsp+r11+210h+pguid.Data1], r8b
0x1400183f4  inc     r11
0x1400183f7  cmp     r11, 10h
0x1400183fb  jnz     short loc_1400183BC
0x1400183fd  movzx   eax, r10b
0x140018401  lea     rcx, ?m_gAlphabet@TImgFilePool@PrnComps@@0QB_WB; "abcdefghijklmnopqrstuvwxyz_01234567890"
0x140018408  movzx   eax, word ptr [rcx+rax*2]
0x14001840c  mov     [rbp+r9*2+110h+var_60], ax
0x140018415  inc     edi
0x140018417  jmp     loc_14001838E
0x14001841c  xor     r8d, r8d; unsigned int
0x14001841f  lea     rdx, asc_1400696D8; "-"
0x140018426  lea     rcx, [rsp+210h+var_1A0]; this
0x14001842b  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140018430  nop
0x140018431  mov     edx, 8000FFFFh; unsigned int
0x140018436  lea     rcx, [rsp+210h+var_1A0]; this
0x14001843b  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140018440  lea     rdx, aGuidShouldAlwa; "Guid should always translate into strin"...
0x140018447  lea     rcx, [rsp+210h+var_1A0]; this
0x14001844c  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140018451  lea     rdx, [rsp+210h+var_1A0]; struct SplException::THResultException *
0x140018456  lea     rcx, [rbp+110h+pExceptionObject]; this
0x14001845a  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x14001845f  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140018466  lea     rcx, [rbp+110h+pExceptionObject]; pExceptionObject
0x14001846a  call    _CxxThrowException_0
0x140018470  movsxd  rax, edi
0x140018473  lea     rcx, [rax+rax]
0x140018477  cmp     rcx, 3Ch ; '<'
0x14001847b  jnb     loc_140018586
0x140018481  xor     eax, eax
0x140018483  mov     [rbp+rcx+110h+var_60], ax
0x14001848b  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PA_WA; wchar_t near * NCoreLibrary::TString::gszNullState
0x140018492  mov     [rsp+210h+var_1C8], rax
0x140018497  mov     rax, [r14+20h]
0x14001849b  mov     qword ptr [rsp+210h+var_1F0], rax
0x1400184a0  lea     r9, [rbp+110h+var_60]
0x1400184a7  mov     r8, [r14+18h]
0x1400184ab  lea     rdx, aSSS_0; "%s%s%s"
0x1400184b2  lea     rcx, [rsp+210h+var_1C8]; this
0x1400184b7  call    ?Format@TString@NCoreLibrary@@QEAAJPEB_WZZ; NCoreLibrary::TString::Format(wchar_t const *,...)
0x1400184bc  test    eax, eax
0x1400184be  jns     short loc_1400184C8
0x1400184c0  mov     ecx, eax; this
0x1400184c2  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1400184c8  mov     ecx, 0B0h; unsigned __int64
0x1400184cd  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x1400184d2  mov     [rsp+210h+var_1C0], rax
0x1400184d7  test    rax, rax
0x1400184da  jz      short loc_14001850C
0x1400184dc  mov     byte ptr [rsp+210h+var_1E0], 0; bool
0x1400184e1  mov     cl, [r14+100h]
0x1400184e8  mov     byte ptr [rsp+210h+var_1E8], cl; bool
0x1400184ec  mov     ecx, [r14+28h]
0x1400184f0  mov     [rsp+210h+var_1F0], ecx; unsigned int
0x1400184f4  mov     r9, [rsp+210h+var_1C8]; wchar_t *
0x1400184f9  mov     r8, r14; struct PrnComps::TImgFilePool *
0x1400184fc  mov     rdx, rsi; struct NCoreLibrary::TCriticalSection *
0x1400184ff  mov     rcx, rax; this
0x140018502  call    ??0TImgWriterFileItem@PrnComps@@QEAA@AEAVTCriticalSection@NCoreLibrary@@PEAVTImgFilePool@1@PEB_WK_N3@Z; PrnComps::TImgWriterFileItem::TImgWriterFileItem(NCoreLibrary::TCriticalSection &,PrnComps::TImgFilePool *,wchar_t const *,ulong,bool,bool)
0x140018507  mov     rdi, rax
0x14001850a  jmp     short loc_14001850E
0x14001850c  xor     edi, edi
0x14001850e  mov     [rsp+210h+var_1C0], rbx
0x140018513  mov     [rsp+210h+var_1D0], rdi
0x140018518  lea     rcx, [rsp+210h+var_1C0]
0x14001851d  call    ??$SmartRelease@VTImgReaderFileItem@PrnComps@@@PrnExcept@@YAXPEAPEAVTImgReaderFileItem@PrnComps@@@Z; PrnExcept::SmartRelease<PrnComps::TImgReaderFileItem>(PrnComps::TImgReaderFileItem * *)
0x140018522  nop
0x140018523  mov     rdx, [rsp+210h+var_1C8]; void *
0x140018528  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x14001852d  mov     rax, [r14]
0x140018530  mov     rcx, r14
0x140018533  mov     rax, [rax+8]
0x140018537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001853c  mov     [rsp+210h+var_1D0], 0
0x140018545  lea     rcx, [rdi+30h]
0x140018549  neg     rdi
0x14001854c  sbb     rbx, rbx
0x14001854f  and     rbx, rcx
0x140018552  lea     rcx, [rsp+210h+var_1D0]
0x140018557  call    ??$SmartRelease@VTImgReaderFileItem@PrnComps@@@PrnExcept@@YAXPEAPEAVTImgReaderFileItem@PrnComps@@@Z; PrnExcept::SmartRelease<PrnComps::TImgReaderFileItem>(PrnComps::TImgReaderFileItem * *)
0x14001855c  mov     rax, rbx
0x14001855f  mov     rcx, [rbp+110h+var_20]
0x140018566  xor     rcx, rsp; StackCookie
0x140018569  call    __security_check_cookie
0x14001856e  lea     r11, [rsp+210h+var_10]
0x140018576  mov     rbx, [r11+28h]
0x14001857a  mov     rsi, [r11+30h]
0x14001857e  mov     rsp, r11
0x140018581  pop     r14
0x140018583  pop     rdi
0x140018584  pop     rbp
0x140018585  retn
0x140018586  call    __report_rangecheckfailure
```
