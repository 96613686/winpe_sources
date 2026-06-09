# CUsnVolume::CUsnVolume(wchar_t const *,uint,wchar_t const *,uint,wchar_t const *)

- ea: `0x1800e7660`
- end: `0x1800e7c78`
- name: `??0CUsnVolume@@QEAA@PEB_WI0I0@Z`
- size: `1560`
- prototype: `CUsnVolume *(CUsnVolume *__hidden this, const wchar_t *, unsigned int, const wchar_t *, unsigned int, const wchar_t *)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800e7468`

## callees

- `0x18000ee60`
- `0x180054cb8`
- `0x180054e14`
- `0x1800555f0`
- `0x180056610`
- `0x18005e788`
- `0x18006a040`
- `0x18006a618`
- `0x1800800f4`
- `0x18008ad80`
- `0x18008d92c`
- `0x18009491c`
- `0x1800afee0`
- `0x1800b0760`
- `0x1800e2374`
- `0x1800e7660`
- `0x1800e95f0`
- `0x1801244c0`
- `0x1801249b0`
- `0x180124d00`
- `0x18021a4fc`
- `0x18021a534`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsupr` at `0x1800e790f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsupr` at `0x1800e790f`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800e78b2`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800e78b2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e7add`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e7add`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e7a43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e7a43`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800e7a9d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800e7a9d`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
CUsnVolume *__fastcall CUsnVolume::CUsnVolume(
        CUsnVolume *this,
        wchar_t *a2,
        int a3,
        const wchar_t *a4,
        unsigned int a5,
        const wchar_t *a6)
{
  wchar_t **v8; // r15
  wchar_t **v9; // r14
  _QWORD *v10; // rdx
  _WORD *v11; // rcx
  unsigned __int64 v12; // rdi
  int v13; // eax
  unsigned __int64 v14; // r9
  wchar_t *v15; // rax
  wchar_t *v16; // r12
  unsigned __int64 i; // rcx
  int v18; // eax
  char v19; // r10
  __int64 v20; // rcx
  char *v21; // rax
  int v22; // eax
  char v23; // r10
  __int64 v24; // r11
  __int64 v25; // rcx
  char *v26; // rax
  wchar_t *v27; // rax
  int v28; // eax
  int v29; // eax
  const char *v30; // r9
  const char *v31; // r9
  const char *v32; // r9
  __int64 v33; // rdx
  char *v34; // rax
  wchar_t *v35; // rcx
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  wchar_t *v39; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 FileW; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE EventW; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v42[3]; // [rsp+58h] [rbp-A8h] BYREF
  char v43[8]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t *v44; // [rsp+78h] [rbp-88h]
  _QWORD v45[4]; // [rsp+D0h] [rbp-30h] BYREF
  __int16 v46; // [rsp+F0h] [rbp-10h] BYREF
  int v47; // [rsp+178h] [rbp+78h]
  __int64 v48; // [rsp+180h] [rbp+80h]
  _BYTE v49[16]; // [rsp+190h] [rbp+90h] BYREF
  wchar_t *v50; // [rsp+1A0h] [rbp+A0h]
  HKEY v51; // [rsp+240h] [rbp+140h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v39 = a2;
  v42[1] = this;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_DWORD *)this + 29) = a3;
  *((_WORD *)this + 110) = 0;
  v8 = (wchar_t **)((char *)this + 224);
  *((_QWORD *)this + 28) = 0;
  *((_DWORD *)this + 58) = a5;
  v9 = (wchar_t **)((char *)this + 240);
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 35) = -1;
  *((_BYTE *)this + 288) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 38) = -1;
  *((_QWORD *)this + 39) = -1;
  *((_QWORD *)this + 40) = -1;
  *((_QWORD *)this + 41) = a6;
  v10 = (_QWORD *)((char *)this + 336);
  v11 = (_WORD *)((char *)this + 360);
  v10[1] = v11;
  v10[2] = 33;
  *v11 = 0;
  *v10 = &TLMString<32,32,1024>::`vftable';
  *((_QWORD *)this + 55) = (char *)this + 456;
  *((_QWORD *)this + 56) = 33;
  *((_WORD *)this + 228) = 0;
  *((_QWORD *)this + 54) = &TLMString<32,32,1024>::`vftable';
  *((_QWORD *)this + 66) = 0;
  *((_BYTE *)this + 536) = 0;
  CSyncReadWrite::CSyncReadWrite((CUsnVolume *)((char *)this + 544), (int)v10);
  *((_QWORD *)this + 82) = 0;
  if ( (unsigned int)(*((_DWORD *)this + 58) - 1) > 0x103 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6D,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\usnmonnotifier\\usnvolume.cxx",
      (const char *)0x80070057LL,
      dwCreationDisposition);
  if ( (unsigned int)(*((_DWORD *)this + 29) - 1) > 0x31 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x71,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\usnmonnotifier\\usnvolume.cxx",
      (const char *)0x80070057LL,
      dwCreationDisposition);
  FileW = 0;
  v12 = a5 + 1;
  v13 = ULongLongMult(v12, 2u, &FileW);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x78,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\usnmonnotifier\\usnvolume.cxx",
      (const char *)(unsigned int)v13,
      dwCreationDisposition);
  v15 = (wchar_t *)operator new[](saturated_mul(v12, v14));
  v16 = v15;
  v42[0] = v15;
  for ( i = FileW; i; --i )
  {
    *(_BYTE *)v15 = 0;
    v15 = (wchar_t *)((char *)v15 + 1);
  }
  v18 = StringCchCopyNW(v16, v12, a4, *((unsigned int *)this + 58));
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7F,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\usnmonnotifier\\usnvolume.cxx",
      (const char *)(unsigned int)v18,
      dwCreationDisposition);
  v20 = 50;
  v21 = (char *)this + 16;
  do
  {
    *v21++ = v19;
    --v20;
  }
  while ( v20 );
  v22 = StringCchCopyNW((wchar_t *)this + 8, 0x32u, v39, *((unsigned int *)this + 29));
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x83,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\usnmonnotifier\\usnvolume.cxx",
      (const char *)(unsigned int)v22,
      dwCreationDisposition);
  v25 = v24;
  v26 = (char *)this + 120;
  do
  {
    *v26++ = v23;
    --v25;
  }
  while ( v25 );
  v27 = wcschr((const wchar_t *)this + 8, 0x7Bu);
  if ( !v27 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x89,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\usnmonnotifier\\usnvolume.cxx",
      (const char *)0x80004005LL,
      dwCreationDisposition);
  v28 = StringCchCopyW((wchar_t *)this + 60, 0x32u, v27);
  if ( v28 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8D,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\usnmonnotifier\\usnvolume.cxx",
      (const char *)(unsigned int)v28,
      dwCreationDisposition);
  _o__wcsupr((char *)this + 120);
  TLMString<32,32,1024>::TLMString<32,32,1024>(v43, L"UsnNotifier");
  CLMString::Append((CLMString *)v43, L"\\", 0xFFFFFFFF);
  CLMString::Append((CLMString *)v43, *((const wchar_t **)this + 41), 0xFFFFFFFF);
  CLMString::Append((CLMString *)v43, L"\\", 0xFFFFFFFF);
  CLMString::Append((CLMString *)v43, L"Volumes", 0xFFFFFFFF);
  CLMString::Append((CLMString *)v43, L"\\", 0xFFFFFFFF);
  TLMString<192,64,32767>::operator=((char *)this + 336, v43);
  CSearchRootRegistry::CSearchRootRegistry((CSearchRootRegistry *)v49, 0, 0xF003Fu);
  v45[2] = &v46;
  v45[3] = 65;
  v46 = 0;
  v45[1] = &CCICommonPathString::`vftable';
  v45[0] = &CRegistry::`vftable';
  v47 = 0;
  v48 = 0;
  v29 = CRegistry::Init((CRegistry *)v45, v51, v44, 0xF003Fu, v50);
  if ( v29 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9E,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\usnmonnotifier\\usnvolume.cxx",
      (const char *)(unsigned int)v29,
      dwCreationDispositiona);
  if ( !(unsigned int)CRegistry::CreateSubKey((CRegistry *)v45, (const wchar_t *)this + 60) && GetLastError() != 183 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\usnmonnotifier\\usnvolume.cxx",
      v30);
  CLMString::Append((CLMString *)v43, (const wchar_t *)this + 60, 0xFFFFFFFF);
  FileW = (unsigned __int64)CreateFileW((LPCWSTR)this + 8, 0xC0000000, 3u, 0, 3u, 0x40000000u, 0);
  if ( ((FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xB4,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\usnmonnotifier\\usnvolume.cxx",
      v31);
  EventW = CreateEventW(0, 1, 0, 0);
  if ( (((unsigned __int64)EventW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xBC,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\usnmonnotifier\\usnvolume.cxx",
      v32);
  TLMString<192,64,32767>::operator=((char *)this + 432, v43);
  v39 = *v9;
  *v9 = 0;
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
    v9,
    &EventW);
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
    &EventW,
    &v39);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v39);
  v33 = 32;
  v34 = (char *)this + 248;
  do
  {
    *v34++ = 0;
    --v33;
  }
  while ( v33 );
  *((_QWORD *)this + 34) = *v9;
  v39 = (wchar_t *)*((_QWORD *)this + 35);
  *((_QWORD *)this + 35) = -1;
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
    (char *)this + 280,
    &FileW);
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
    &FileW,
    &v39);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v39);
  if ( v8 != v42 )
  {
    v42[0] = 0;
    v35 = *v8;
    *v8 = v16;
    if ( v35 )
      operator delete(v35);
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&EventW);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileW);
  CRegistry::~CRegistry((CRegistry *)v45);
  CRegistry::~CRegistry((CRegistry *)v49);
  TLMString<32,32,1024>::~TLMString<32,32,1024>(v43);
  std::unique_ptr<enum gsl::byte [0]>::~unique_ptr<enum gsl::byte [0]>(v42);
  return this;
}

```

## disassembly

```asm
0x1800e7660  mov     [rsp-8+arg_10], rbx
0x1800e7665  push    rbp
0x1800e7666  push    rsi
0x1800e7667  push    rdi
0x1800e7668  push    r12
0x1800e766a  push    r13
0x1800e766c  push    r14
0x1800e766e  push    r15
0x1800e7670  lea     rbp, [rsp-160h]
0x1800e7678  sub     rsp, 260h
0x1800e767f  mov     rax, cs:__security_cookie
0x1800e7686  xor     rax, rsp
0x1800e7689  mov     [rbp+190h+var_40], rax
0x1800e7690  mov     rsi, r9
0x1800e7693  mov     [rsp+290h+var_250], rdx
0x1800e7698  mov     rbx, rcx
0x1800e769b  mov     [rsp+290h+var_230], rcx
0x1800e76a0  mov     edi, [rbp+190h+arg_20]
0x1800e76a6  xor     r12d, r12d
0x1800e76a9  mov     [rcx], r12
0x1800e76ac  mov     [rcx+8], r12
0x1800e76b0  mov     [rcx+74h], r8d
0x1800e76b4  mov     [rcx+0DCh], r12w
0x1800e76bc  lea     r15, [rcx+0E0h]
0x1800e76c3  mov     [r15], r12
0x1800e76c6  mov     [rcx+0E8h], edi
0x1800e76cc  lea     r14, [rcx+0F0h]
0x1800e76d3  mov     [r14], r12
0x1800e76d6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800e76da  mov     [rcx+118h], rax
0x1800e76e1  mov     [rcx+120h], r12b
0x1800e76e8  mov     [rcx+128h], r12
0x1800e76ef  mov     [rcx+130h], rax
0x1800e76f6  mov     [rcx+138h], rax
0x1800e76fd  mov     [rcx+140h], rax
0x1800e7704  mov     rax, [rbp+190h+arg_28]
0x1800e770b  mov     [rcx+148h], rax
0x1800e7712  lea     rdx, [rcx+150h]; int
0x1800e7719  lea     rcx, [rdx+18h]
0x1800e771d  mov     [rdx+8], rcx
0x1800e7721  mov     qword ptr [rdx+10h], 21h ; '!'
0x1800e7729  mov     [rcx], r12w
0x1800e772d  lea     r9, ??_7?$TLMString@$0CA@$0CA@$0EAA@@@6B@; const TLMString<32,32,1024>::`vftable'
0x1800e7734  mov     [rdx], r9
0x1800e7737  lea     r13, [rbx+1B0h]
0x1800e773e  lea     rcx, [r13+18h]
0x1800e7742  mov     [r13+8], rcx
0x1800e7746  mov     qword ptr [r13+10h], 21h ; '!'
0x1800e774e  mov     [rcx], r12w
0x1800e7752  mov     [r13+0], r9
0x1800e7756  mov     [rbx+210h], r12
0x1800e775d  mov     [rbx+218h], r12b
0x1800e7764  lea     rcx, [rbx+220h]; this
0x1800e776b  call    ??0CSyncReadWrite@@QEAA@H@Z; CSyncReadWrite::CSyncReadWrite(int)
0x1800e7770  nop
0x1800e7771  mov     [rbx+290h], r12
0x1800e7778  mov     eax, [rbx+0E8h]
0x1800e777e  dec     eax
0x1800e7780  cmp     eax, 103h
0x1800e7785  ja      loc_1800E7C59
0x1800e778b  mov     eax, [rbx+74h]
0x1800e778e  dec     eax
0x1800e7790  cmp     eax, 31h ; '1'
0x1800e7793  ja      loc_1800E7C3A
0x1800e7799  mov     [rsp+290h+var_248], r12
0x1800e779e  lea     eax, [rdi+1]
0x1800e77a1  mov     edi, eax
0x1800e77a3  lea     r8, [rsp+290h+var_248]; unsigned __int64 *
0x1800e77a8  lea     r9d, [r12+2]
0x1800e77ad  mov     edx, r9d; unsigned __int64
0x1800e77b0  mov     ecx, eax; unsigned __int64
0x1800e77b2  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800e77b7  mov     rcx, [rbp+198h]; this
0x1800e77be  test    eax, eax
0x1800e77c0  jns     short loc_1800E77D7
0x1800e77c2  mov     r9d, eax; char *
0x1800e77c5  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e77cc  lea     edx, [r12+78h]; void *
0x1800e77d1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e77d7  mov     rax, r9
0x1800e77da  mul     rdi
0x1800e77dd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800e77e4  cmovb   rax, rcx
0x1800e77e8  mov     rcx, rax; unsigned __int64
0x1800e77eb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800e77f0  mov     r12, rax
0x1800e77f3  mov     [rsp+290h+var_238], rax
0x1800e77f8  mov     rcx, [rsp+290h+var_248]
0x1800e77fd  xor     r10d, r10d
0x1800e7800  test    rcx, rcx
0x1800e7803  jz      short loc_1800E7811
0x1800e7805  mov     [rax], r10b
0x1800e7808  inc     rax
0x1800e780b  sub     rcx, 1
0x1800e780f  jnz     short loc_1800E7805
0x1800e7811  mov     r9d, [rbx+0E8h]; unsigned __int64
0x1800e7818  mov     r8, rsi; wchar_t *
0x1800e781b  mov     rdx, rdi; unsigned __int64
0x1800e781e  mov     rcx, r12; wchar_t *
0x1800e7821  call    ?StringCchCopyNW@@YAJPEA_W_KPEB_W1@Z; StringCchCopyNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)
0x1800e7826  mov     rcx, [rbp+198h]; this
0x1800e782d  test    eax, eax
0x1800e782f  jns     short loc_1800E7846
0x1800e7831  mov     r9d, eax; char *
0x1800e7834  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e783b  mov     edx, 7Fh; void *
0x1800e7840  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e7846  mov     r11d, 32h ; '2'
0x1800e784c  mov     ecx, r11d
0x1800e784f  lea     rsi, [rbx+10h]
0x1800e7853  mov     rax, rsi
0x1800e7856  mov     [rax], r10b
0x1800e7859  inc     rax
0x1800e785c  sub     rcx, 1
0x1800e7860  jnz     short loc_1800E7856
0x1800e7862  mov     r9d, [rbx+74h]; unsigned __int64
0x1800e7866  mov     r8, [rsp+290h+var_250]; wchar_t *
0x1800e786b  mov     rdx, r11; unsigned __int64
0x1800e786e  mov     rcx, rsi; wchar_t *
0x1800e7871  call    ?StringCchCopyNW@@YAJPEA_W_KPEB_W1@Z; StringCchCopyNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)
0x1800e7876  mov     rcx, [rbp+198h]; this
0x1800e787d  test    eax, eax
0x1800e787f  jns     short loc_1800E7896
0x1800e7881  mov     r9d, eax; char *
0x1800e7884  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e788b  mov     edx, 83h; void *
0x1800e7890  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e7896  mov     rcx, r11
0x1800e7899  lea     rdi, [rbx+78h]
0x1800e789d  mov     rax, rdi
0x1800e78a0  mov     [rax], r10b
0x1800e78a3  inc     rax
0x1800e78a6  sub     rcx, 1
0x1800e78aa  jnz     short loc_1800E78A0
0x1800e78ac  lea     edx, [rcx+7Bh]; Ch
0x1800e78af  mov     rcx, rsi; Str
0x1800e78b2  call    cs:__imp_wcschr
0x1800e78b8  test    rax, rax
0x1800e78bb  jnz     short loc_1800E78DC
0x1800e78bd  mov     rcx, [rbp+198h]; this
0x1800e78c4  mov     r9d, 80004005h; char *
0x1800e78ca  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e78d1  mov     edx, 89h; void *
0x1800e78d6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e78dc  mov     r8, rax; wchar_t *
0x1800e78df  mov     edx, 32h ; '2'; unsigned __int64
0x1800e78e4  mov     rcx, rdi; wchar_t *
0x1800e78e7  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800e78ec  mov     rcx, [rbp+198h]; this
0x1800e78f3  test    eax, eax
0x1800e78f5  jns     short loc_1800E790C
0x1800e78f7  mov     r9d, eax; char *
0x1800e78fa  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e7901  mov     edx, 8Dh; void *
0x1800e7906  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e790c  mov     rcx, rdi
0x1800e790f  call    cs:__imp__o__wcsupr
0x1800e7915  lea     rdx, aUsnnotifier; "UsnNotifier"
0x1800e791c  lea     rcx, [rsp+290h+var_220]
0x1800e7921  call    ??0?$TLMString@$0CA@$0CA@$0EAA@@@QEAA@PEB_W@Z; TLMString<32,32,1024>::TLMString<32,32,1024>(wchar_t const *)
0x1800e7926  nop
0x1800e7927  or      r8d, 0FFFFFFFFh; unsigned int
0x1800e792b  lea     rdx, StringValue; "\\"
0x1800e7932  lea     rcx, [rsp+290h+var_220]; this
0x1800e7937  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x1800e793c  or      r8d, 0FFFFFFFFh; unsigned int
0x1800e7940  mov     rdx, [rbx+148h]; wchar_t *
0x1800e7947  lea     rcx, [rsp+290h+var_220]; this
0x1800e794c  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x1800e7951  or      r8d, 0FFFFFFFFh; unsigned int
0x1800e7955  lea     rdx, StringValue; "\\"
0x1800e795c  lea     rcx, [rsp+290h+var_220]; this
0x1800e7961  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x1800e7966  or      r8d, 0FFFFFFFFh; unsigned int
0x1800e796a  lea     rdx, aVolumes; "Volumes"
0x1800e7971  lea     rcx, [rsp+290h+var_220]; this
0x1800e7976  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x1800e797b  or      r8d, 0FFFFFFFFh; unsigned int
0x1800e797f  lea     rdx, StringValue; "\\"
0x1800e7986  lea     rcx, [rsp+290h+var_220]; this
0x1800e798b  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x1800e7990  lea     rdx, [rsp+290h+var_220]
0x1800e7995  lea     rcx, [rbx+150h]
0x1800e799c  call    ??4?$TLMString@$0MA@$0EA@$0HPPP@@@QEAAXAEBV0@@Z; TLMString<192,64,32767>::operator=(TLMString<192,64,32767> const &)
0x1800e79a1  xor     edx, edx; wchar_t *
0x1800e79a3  mov     r8d, 0F003Fh; unsigned int
0x1800e79a9  lea     rcx, [rbp+190h+var_100]; this
0x1800e79b0  call    ??0CSearchRootRegistry@@QEAA@PEB_WK@Z; CSearchRootRegistry::CSearchRootRegistry(wchar_t const *,ulong)
0x1800e79b5  nop
0x1800e79b6  lea     rax, [rbp+190h+var_1A0]
0x1800e79ba  mov     [rbp+190h+var_1B0], rax
0x1800e79be  mov     [rbp+190h+var_1A8], 41h ; 'A'
0x1800e79c6  xor     ecx, ecx
0x1800e79c8  mov     [rbp+190h+var_1A0], cx
0x1800e79cc  lea     rax, ??_7CCICommonPathString@@6B@; const CCICommonPathString::`vftable'
0x1800e79d3  mov     [rbp+190h+var_1B8], rax
0x1800e79d7  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x1800e79de  mov     [rbp+190h+var_1C0], rax
0x1800e79e2  mov     [rbp+190h+var_118], ecx
0x1800e79e5  mov     [rbp+190h+var_110], rcx
0x1800e79ec  mov     rax, [rbp+190h+var_F0]
0x1800e79f3  mov     qword ptr [rsp+290h+dwCreationDisposition], rax; int
0x1800e79f8  mov     r9d, 0F003Fh; unsigned int
0x1800e79fe  mov     r8, [rsp+290h+var_218]; wchar_t *
0x1800e7a03  mov     rdx, [rbp+190h+var_50]; HKEY
0x1800e7a0a  lea     rcx, [rbp+190h+var_1C0]; this
0x1800e7a0e  call    ?Init@CRegistry@@QEAAJPEAUHKEY__@@PEB_WK1@Z; CRegistry::Init(HKEY__ *,wchar_t const *,ulong,wchar_t const *)
0x1800e7a13  mov     rcx, [rbp+198h]; this
0x1800e7a1a  test    eax, eax
0x1800e7a1c  jns     short loc_1800E7A33
0x1800e7a1e  mov     r9d, eax; char *
0x1800e7a21  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e7a28  mov     edx, 9Eh; void *
0x1800e7a2d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e7a33  mov     rdx, rdi; wchar_t *
0x1800e7a36  lea     rcx, [rbp+190h+var_1C0]; this
0x1800e7a3a  call    ?CreateSubKey@CRegistry@@UEAAHPEB_W@Z; CRegistry::CreateSubKey(wchar_t const *)
0x1800e7a3f  test    eax, eax
0x1800e7a41  jnz     short loc_1800E7A69
0x1800e7a43  call    cs:__imp_GetLastError
0x1800e7a49  cmp     eax, 0B7h
0x1800e7a4e  jz      short loc_1800E7A69
0x1800e7a50  mov     rcx, [rbp+198h]; this
0x1800e7a57  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e7a5e  mov     edx, 0A5h; void *
0x1800e7a63  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800e7a69  or      r8d, 0FFFFFFFFh; unsigned int
0x1800e7a6d  mov     rdx, rdi; wchar_t *
0x1800e7a70  lea     rcx, [rsp+290h+var_220]; this
0x1800e7a75  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x1800e7a7a  xor     edi, edi
0x1800e7a7c  mov     [rsp+290h+hTemplateFile], rdi; hTemplateFile
0x1800e7a81  mov     [rsp+290h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x1800e7a89  lea     r8d, [rdi+3]; dwShareMode
0x1800e7a8d  mov     [rsp+290h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800e7a92  xor     r9d, r9d; lpSecurityAttributes
0x1800e7a95  mov     edx, 0C0000000h; dwDesiredAccess
0x1800e7a9a  mov     rcx, rsi; lpFileName
0x1800e7a9d  call    cs:__imp_CreateFileW
0x1800e7aa3  mov     [rsp+290h+var_248], rax
0x1800e7aa8  inc     rax
0x1800e7aab  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800e7ab1  setz    al
0x1800e7ab4  mov     rcx, [rbp+198h]; this
0x1800e7abb  test    al, al
0x1800e7abd  jz      short loc_1800E7AD1
0x1800e7abf  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e7ac6  mov     edx, 0B4h; void *
0x1800e7acb  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800e7ad1  xor     r9d, r9d; lpName
0x1800e7ad4  xor     r8d, r8d; bInitialState
0x1800e7ad7  lea     edx, [r9+1]; bManualReset
0x1800e7adb  xor     ecx, ecx; lpEventAttributes
0x1800e7add  call    cs:__imp_CreateEventW
0x1800e7ae3  mov     [rsp+290h+var_240], rax
0x1800e7ae8  inc     rax
0x1800e7aeb  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800e7af1  setz    al
0x1800e7af4  mov     rcx, [rbp+198h]; this
0x1800e7afb  test    al, al
0x1800e7afd  jz      short loc_1800E7B11
0x1800e7aff  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e7b06  mov     edx, 0BCh; void *
0x1800e7b0b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800e7b11  lea     rdx, [rsp+290h+var_220]
0x1800e7b16  mov     rcx, r13
0x1800e7b19  call    ??4?$TLMString@$0MA@$0EA@$0HPPP@@@QEAAXAEBV0@@Z; TLMString<192,64,32767>::operator=(TLMString<192,64,32767> const &)
0x1800e7b1e  mov     rax, [r14]
0x1800e7b21  mov     [rsp+290h+var_250], rax
0x1800e7b26  mov     [r14], rdi
0x1800e7b29  lea     rdx, [rsp+290h+var_240]
0x1800e7b2e  mov     rcx, r14
0x1800e7b31  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1800e7b36  lea     rdx, [rsp+290h+var_250]
0x1800e7b3b  lea     rcx, [rsp+290h+var_240]
0x1800e7b40  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1800e7b45  lea     rcx, [rsp+290h+var_250]
0x1800e7b4a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e7b4f  mov     edx, 20h ; ' '
0x1800e7b54  lea     rax, [rbx+0F8h]
0x1800e7b5b  mov     [rax], dil
0x1800e7b5e  inc     rax
0x1800e7b61  sub     rdx, 1
0x1800e7b65  jnz     short loc_1800E7B5B
0x1800e7b67  mov     rax, [r14]
0x1800e7b6a  mov     [rbx+110h], rax
0x1800e7b71  lea     rcx, [rbx+118h]
0x1800e7b78  mov     rax, [rcx]
0x1800e7b7b  mov     [rsp+290h+var_250], rax
0x1800e7b80  mov     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x1800e7b87  lea     rdx, [rsp+290h+var_248]
0x1800e7b8c  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1800e7b91  lea     rdx, [rsp+290h+var_250]
0x1800e7b96  lea     rcx, [rsp+290h+var_248]
0x1800e7b9b  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1800e7ba0  lea     rcx, [rsp+290h+var_250]
0x1800e7ba5  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e7baa  lea     rax, [rsp+290h+var_238]
0x1800e7baf  cmp     r15, rax
0x1800e7bb2  jz      short loc_1800E7BCA
  ... truncated ...
```
