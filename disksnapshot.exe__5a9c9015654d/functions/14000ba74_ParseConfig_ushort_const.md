# ParseConfig(ushort const *)

- ea: `0x14000ba74`
- end: `0x14000c308`
- name: `?ParseConfig@@YAJPEBG@Z`
- size: `2196`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x140009ee0`

## callees

- `0x140001c50`
- `0x140001d10`
- `0x14000265e`
- `0x14000281c`
- `0x140002c84`
- `0x140002fb8`
- `0x1400089ac`
- `0x140009d0c`
- `0x140009d24`
- `0x14000afe8`
- `0x14000b088`
- `0x14000b7dc`
- `0x14000ba74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000baf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000baf2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x14000bae8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x14000bae8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000bace`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000bace`

## string_xrefs

- `0x14000bb18`: `Failed to process config file\n`

## pseudocode

```c
__int64 __fastcall ParseConfig(const unsigned __int16 *a1)
{
  __m128i si128; // xmm6
  HMODULE ModuleHandleW; // rax
  signed int LastError; // eax
  signed int Bucket; // ebx
  FILE *v5; // rax
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  __int64 v10; // rdx
  WCHAR *v11; // rax
  __int64 v12; // r8
  __int64 v13; // rax
  const wchar_t *v14; // rcx
  __int64 v15; // rdi
  WCHAR *v16; // rdx
  wchar_t v17; // r8
  WCHAR *v18; // rcx
  unsigned __int64 v19; // rdi
  unsigned __int64 v20; // rsi
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // rbx
  unsigned __int64 v23; // r14
  unsigned __int64 v24; // r12
  unsigned __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  unsigned __int64 v28; // r15
  __int128 *v29; // rcx
  unsigned __int64 v30; // r8
  __int128 *v31; // rax
  __int64 v32; // r8
  __int128 *v33; // rax
  __int128 *p_Src_8; // rax
  unsigned __int64 v35; // rax
  unsigned __int64 v36; // rdi
  unsigned __int64 v37; // rax
  __int64 v38; // rdx
  unsigned __int64 v39; // r14
  unsigned __int64 v40; // rcx
  __int64 v41; // r8
  __int64 v42; // r8
  __int128 *v43; // rax
  unsigned __int64 v44; // r14
  unsigned __int64 v45; // r8
  __int128 *v46; // rax
  __int128 *v47; // r9
  __int64 v48; // r8
  __int128 *v49; // rax
  int v50; // r15d
  __int64 v51; // r8
  __int128 *v52; // rax
  unsigned __int64 v53; // r14
  unsigned __int64 v54; // rax
  unsigned __int64 v55; // rbx
  __int64 v56; // r8
  __int128 *v57; // rax
  __int64 v58; // r8
  __int128 *v59; // rax
  __int128 *v60; // rax
  __int128 *v61; // r8
  __int128 *v62; // rdx
  __int128 *v63; // rcx
  __int128 *v64; // [rsp+28h] [rbp-E0h]
  int v65; // [rsp+30h] [rbp-D8h]
  __int128 Src_8; // [rsp+50h] [rbp-B8h] BYREF
  __m128i v67; // [rsp+60h] [rbp-A8h]
  __int128 v68; // [rsp+70h] [rbp-98h] BYREF
  __int128 v69; // [rsp+80h] [rbp-88h]
  __int128 v70; // [rsp+90h] [rbp-78h] BYREF
  __int64 v71; // [rsp+A0h] [rbp-68h]
  unsigned __int64 v72; // [rsp+A8h] [rbp-60h]
  __int128 v73; // [rsp+B0h] [rbp-58h] BYREF
  __m128i v74; // [rsp+C0h] [rbp-48h]
  __int128 v75; // [rsp+D0h] [rbp-38h] BYREF
  __m128i v76; // [rsp+E0h] [rbp-28h]
  __int128 v77; // [rsp+F0h] [rbp-18h] BYREF
  __m128i v78; // [rsp+100h] [rbp-8h]
  __int128 v79; // [rsp+110h] [rbp+8h] BYREF
  __m128i v80; // [rsp+120h] [rbp+18h]
  WCHAR Filename[264]; // [rsp+138h] [rbp+30h] BYREF

  Src_8 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v67 = si128;
  LOWORD(Src_8) = 0;
  if ( a1 )
  {
    Bucket = StringCchPrintfW(Filename, 0x104u, a1);
    if ( Bucket < 0 )
      goto LABEL_7;
  }
  else
  {
    ModuleHandleW = GetModuleHandleW(0);
    if ( !ModuleHandleW || !GetModuleFileNameW(ModuleHandleW, Filename, 0x104u) )
    {
      LastError = GetLastError();
      Bucket = LastError;
      if ( LastError > 0 )
        Bucket = (unsigned __int16)LastError | 0x80070000;
      if ( Bucket >= 0 )
        goto LABEL_8;
      goto LABEL_7;
    }
    v7 = 0;
    v8 = 0;
    do
    {
      if ( Filename[v8] == 92 )
      {
        v7 = ++v8;
      }
      else
      {
        if ( !Filename[v8] )
          break;
        ++v8;
      }
    }
    while ( v8 < 0x103 );
    v9 = v7;
    if ( v9 >= 260 )
      _report_rangecheckfailure();
    Filename[v9] = 0;
    v10 = 260;
    v11 = Filename;
    do
    {
      if ( !*v11 )
        break;
      ++v11;
      --v10;
    }
    while ( v10 );
    Bucket = v10 == 0 ? 0x80070057 : 0;
    v12 = (260 - v10) & -(__int64)(v10 != 0);
    if ( !v10 )
      goto LABEL_7;
    v13 = 2147483646;
    v14 = L"DiskSnapshot.conf";
    v15 = 260 - v12;
    v16 = &Filename[v12];
    if ( 260 != v12 )
    {
      do
      {
        if ( !v13 )
          break;
        v17 = *v14;
        if ( !*v14 )
          break;
        ++v14;
        *v16++ = v17;
        --v13;
        --v15;
      }
      while ( v15 );
    }
    Bucket = v15 == 0 ? 0x8007007A : 0;
    v18 = v16 - 1;
    if ( v15 )
      v18 = v16;
    *v18 = 0;
    if ( !v15 )
    {
LABEL_7:
      v5 = o___acrt_iob_func_0(2u);
      fwprintf(v5, L"Failed to process config file\n");
      goto LABEL_8;
    }
  }
  Bucket = LoadTextFile(Filename, &Src_8);
  if ( Bucket < 0 )
    goto LABEL_7;
  v19 = 0;
  while ( 1 )
  {
    v75 = 0;
    v76 = si128;
    LOWORD(v75) = 0;
    v70 = 0;
    v71 = 0;
    v72 = 7;
    LOWORD(v70) = 0;
    v20 = std::wstring::find(&Src_8, L"\n", v19);
    if ( v20 == -1 )
      break;
    v21 = std::wstring::find(&Src_8, L"|", v19);
    v22 = v21;
    if ( v21 == -1 )
      goto LABEL_122;
    if ( v21 > v20 )
      goto LABEL_122;
    if ( v20 - v21 == 1 )
      goto LABEL_122;
    v23 = v21 - v19;
    if ( v21 == v19 )
      goto LABEL_122;
    v24 = v21 + 1;
    v25 = std::wstring::find(&Src_8, L"|", v21 + 1);
    v28 = v25;
    if ( v25 == -1 || v25 > v20 || v20 - v25 == 1 || (v29 = (__int128 *)(v25 - v19), v25 == v19) )
    {
      v29 = &v70;
      if ( v72 > 7 )
        v29 = (__int128 *)v70;
      v71 = 0;
      *(_WORD *)v29 = 0;
      v68 = 0;
      v69 = 0;
      if ( v67.m128i_i64[0] < v19 )
LABEL_127:
        std::_String_val<std::_Simple_types<unsigned short>>::_Xran(v29, v26, v27);
      if ( v67.m128i_i64[0] - v19 < v23 )
        v23 = v67.m128i_i64[0] - v19;
      p_Src_8 = &Src_8;
      if ( v67.m128i_i64[1] > 7uLL )
        p_Src_8 = (__int128 *)Src_8;
      std::wstring::_Construct<1,unsigned short const *>(&v68, (char *)p_Src_8 + 2 * v19, v23);
      std::wstring::operator=(&v75, &v68);
      std::wstring::~wstring(&v68);
    }
    else
    {
      v68 = 0;
      v69 = 0;
      v27 = v67.m128i_i64[0];
      if ( v67.m128i_i64[0] < v19 )
        goto LABEL_127;
      v30 = v67.m128i_i64[0] - v19;
      if ( v67.m128i_i64[0] - v19 >= v23 )
        v30 = v23;
      v31 = &Src_8;
      if ( v67.m128i_i64[1] > 7uLL )
        v31 = (__int128 *)Src_8;
      std::wstring::_Construct<1,unsigned short const *>(&v68, (char *)v31 + 2 * v19, v30);
      std::wstring::operator=(&v70, &v68);
      std::wstring::~wstring(&v68);
      v68 = 0;
      v69 = 0;
      v27 = v67.m128i_i64[0];
      if ( v67.m128i_i64[0] < v24 )
        goto LABEL_127;
      v32 = v67.m128i_i64[0] - v24;
      if ( v67.m128i_i64[0] - v24 >= v28 - v22 - 1 )
        v32 = v28 - v22 - 1;
      v33 = &Src_8;
      if ( v67.m128i_i64[1] > 7uLL )
        v33 = (__int128 *)Src_8;
      std::wstring::_Construct<1,unsigned short const *>(&v68, (char *)v33 + 2 * v24, v32);
      std::wstring::operator=(&v75, &v68);
      std::wstring::~wstring(&v68);
      v22 = v28;
    }
    v73 = 0;
    v74 = si128;
    LOWORD(v73) = 0;
    v77 = 0;
    v78 = si128;
    LOWORD(v77) = 0;
    v79 = 0;
    v80 = si128;
    LOWORD(v79) = 0;
    v35 = std::wstring::find(&Src_8, L"*", v22);
    v36 = v35;
    if ( v35 > v20 || v35 == -1 )
      v36 = v20;
    v37 = std::wstring::find(&Src_8, L"**", v22);
    v39 = v37;
    if ( v37 != -1 && v37 <= v20 )
    {
      v40 = v22 + 1;
      v41 = v67.m128i_i64[0];
      v68 = 0;
      v69 = 0;
      if ( v36 == v37 )
      {
        if ( v67.m128i_i64[0] < v40 )
          goto LABEL_129;
        v48 = v67.m128i_i64[0] - v40;
        if ( v67.m128i_i64[0] - v40 >= v37 - v22 - 1 )
          v48 = v37 - v22 - 1;
        v49 = &Src_8;
        if ( v67.m128i_i64[1] > 7uLL )
          v49 = (__int128 *)Src_8;
        std::wstring::_Construct<1,unsigned short const *>(&v68, (char *)v49 + 2 * v40, v48);
        std::wstring::operator=(&v73, &v68);
        std::wstring::~wstring(&v68);
        v47 = 0;
      }
      else
      {
        if ( v67.m128i_i64[0] < v40 )
          goto LABEL_129;
        v42 = v67.m128i_i64[0] - v40;
        if ( v67.m128i_i64[0] - v40 >= v36 - v22 - 1 )
          v42 = v36 - v22 - 1;
        v43 = &Src_8;
        if ( v67.m128i_i64[1] > 7uLL )
          v43 = (__int128 *)Src_8;
        std::wstring::_Construct<1,unsigned short const *>(&v68, (char *)v43 + 2 * v40, v42);
        std::wstring::operator=(&v73, &v68);
        std::wstring::~wstring(&v68);
        v40 = v36 + 1;
        v68 = 0;
        v69 = 0;
        v41 = v67.m128i_i64[0];
        if ( v67.m128i_i64[0] < v36 + 1 )
          goto LABEL_129;
        v44 = v39 - v36;
        v45 = v67.m128i_i64[0] - v40;
        if ( v67.m128i_i64[0] - v40 >= v44 - 1 )
          v45 = v44 - 1;
        v46 = &Src_8;
        if ( v67.m128i_i64[1] > 7uLL )
          v46 = (__int128 *)Src_8;
        std::wstring::_Construct<1,unsigned short const *>(&v68, (char *)v46 + 2 * v40, v45);
        std::wstring::operator=(&v77, &v68);
        std::wstring::~wstring(&v68);
        v47 = &v77;
        if ( v78.m128i_i64[1] > 7uLL )
          v47 = (__int128 *)v77;
      }
      v65 = 1;
      v64 = 0;
      goto LABEL_114;
    }
    v40 = v22 + 1;
    v68 = 0;
    v69 = 0;
    v41 = v67.m128i_i64[0];
    if ( v67.m128i_i64[0] < v22 + 1 )
      goto LABEL_129;
    v50 = 0;
    v51 = v67.m128i_i64[0] - v40;
    if ( v67.m128i_i64[0] - v40 >= v36 - v22 - 1 )
      v51 = v36 - v22 - 1;
    v52 = &Src_8;
    if ( v67.m128i_i64[1] > 7uLL )
      v52 = (__int128 *)Src_8;
    std::wstring::_Construct<1,unsigned short const *>(&v68, (char *)v52 + 2 * v40, v51);
    std::wstring::operator=(&v73, &v68);
    std::wstring::~wstring(&v68);
    if ( v36 != v20 )
    {
      v53 = v36 + 1;
      v54 = std::wstring::find(&Src_8, L"*", v36 + 1);
      v55 = v54;
      if ( v54 > v20 || v54 == -1 )
        v55 = v20;
      v68 = 0;
      v69 = 0;
      v41 = v67.m128i_i64[0];
      if ( v67.m128i_i64[0] < v53 )
LABEL_129:
        std::_String_val<std::_Simple_types<unsigned short>>::_Xran(v40, v38, v41);
      v50 = 1;
      v56 = v67.m128i_i64[0] - v53;
      if ( v67.m128i_i64[0] - v53 >= v55 - v36 - 1 )
        v56 = v55 - v36 - 1;
      v57 = &Src_8;
      if ( v67.m128i_i64[1] > 7uLL )
        v57 = (__int128 *)Src_8;
      std::wstring::_Construct<1,unsigned short const *>(&v68, (char *)v57 + 2 * v53, v56);
      std::wstring::operator=(&v77, &v68);
      std::wstring::~wstring(&v68);
      if ( v55 != v20 )
      {
        v40 = v55 + 1;
        v68 = 0;
        v69 = 0;
        v41 = v67.m128i_i64[0];
        if ( v67.m128i_i64[0] < v55 + 1 )
          goto LABEL_129;
        v58 = v67.m128i_i64[0] - v40;
        if ( v67.m128i_i64[0] - v40 >= v20 - v55 - 1 )
          v58 = v20 - v55 - 1;
        v59 = &Src_8;
        if ( v67.m128i_i64[1] > 7uLL )
          v59 = (__int128 *)Src_8;
        std::wstring::_Construct<1,unsigned short const *>(&v68, (char *)v59 + 2 * v40, v58);
        std::wstring::operator=(&v79, &v68);
        std::wstring::~wstring(&v68);
        v60 = &v79;
        if ( v80.m128i_i64[1] > 7uLL )
          v60 = (__int128 *)v79;
LABEL_109:
        v47 = &v77;
        if ( v78.m128i_i64[1] > 7uLL )
          v47 = (__int128 *)v77;
        goto LABEL_113;
      }
    }
    v60 = 0;
    if ( v50 )
      goto LABEL_109;
    v47 = 0;
LABEL_113:
    v65 = 0;
    v64 = v60;
LABEL_114:
    v61 = &v73;
    if ( v74.m128i_i64[1] > 7uLL )
      v61 = (__int128 *)v73;
    v62 = &v70;
    if ( v72 > 7 )
      v62 = (__int128 *)v70;
    v63 = &v75;
    if ( v76.m128i_i64[1] > 7uLL )
      v63 = (__int128 *)v75;
    Bucket = CreateBucket(v63, v62, v61, v47, v64, v65);
    if ( Bucket < 0 )
    {
      std::wstring::~wstring(&v79);
      std::wstring::~wstring(&v77);
      std::wstring::~wstring(&v73);
      std::wstring::~wstring(&v70);
      std::wstring::~wstring(&v75);
      goto LABEL_7;
    }
    std::wstring::~wstring(&v79);
    std::wstring::~wstring(&v77);
    std::wstring::~wstring(&v73);
LABEL_122:
    std::wstring::~wstring(&v70);
    v19 = v20 + 1;
    std::wstring::~wstring(&v75);
    if ( v20 == -2 )
      goto LABEL_126;
  }
  std::wstring::~wstring(&v70);
  std::wstring::~wstring(&v75);
LABEL_126:
  Bucket = 0;
LABEL_8:
  std::wstring::~wstring(&Src_8);
  return (unsigned int)Bucket;
}

```

## disassembly

```asm
0x14000ba74  mov     rax, rsp
0x14000ba77  push    rbp
0x14000ba78  push    rbx
0x14000ba79  push    rsi
0x14000ba7a  push    rdi
0x14000ba7b  push    r12
0x14000ba7d  push    r13
0x14000ba7f  push    r14
0x14000ba81  push    r15
0x14000ba83  lea     rbp, [rax-2A8h]
0x14000ba8a  sub     rsp, 368h
0x14000ba91  movaps  xmmword ptr [rax-58h], xmm6
0x14000ba95  mov     rax, cs:__security_cookie
0x14000ba9c  xor     rax, rsp
0x14000ba9f  mov     [rbp+2A0h+var_60], rax
0x14000baa6  xor     r13d, r13d
0x14000baa9  xorps   xmm0, xmm0
0x14000baac  movups  [rsp+3A0h+Src+8], xmm0
0x14000bab1  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x14000bab9  movdqu  [rsp+3A0h+var_350+8], xmm6
0x14000babf  mov     word ptr [rsp+3A0h+Src+8], r13w
0x14000bac5  test    rcx, rcx
0x14000bac8  jnz     loc_14000BC46
0x14000bace  call    cs:__imp_GetModuleHandleW
0x14000bad4  test    rax, rax
0x14000bad7  jz      short loc_14000BAF2
0x14000bad9  mov     edi, 104h
0x14000bade  mov     r8d, edi; nSize
0x14000bae1  lea     rdx, [rbp+2A0h+Filename]; lpFilename
0x14000bae5  mov     rcx, rax; hModule
0x14000bae8  call    cs:__imp_GetModuleFileNameW
0x14000baee  test    eax, eax
0x14000baf0  jnz     short loc_14000BB5C
0x14000baf2  call    cs:__imp_GetLastError
0x14000baf8  test    eax, eax
0x14000bafa  mov     ebx, eax
0x14000bafc  jle     short loc_14000BB07
0x14000bafe  movzx   ebx, ax
0x14000bb01  or      ebx, 80070000h
0x14000bb07  test    ebx, ebx
0x14000bb09  jns     short loc_14000BB25
0x14000bb0b  mov     ecx, 2; Ix
0x14000bb10  call    _o___acrt_iob_func_0
0x14000bb15  mov     rcx, rax; Stream
0x14000bb18  lea     rdx, aFailedToProces; "Failed to process config file\n"
0x14000bb1f  call    fwprintf
0x14000bb24  nop
0x14000bb25  lea     rcx, [rsp+3A0h+Src+8]
0x14000bb2a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000bb2f  mov     eax, ebx
0x14000bb31  mov     rcx, [rbp+2A0h+var_60]
0x14000bb38  xor     rcx, rsp; StackCookie
0x14000bb3b  call    __security_check_cookie
0x14000bb40  movaps  xmm6, [rsp+3A0h+var_58+8]
0x14000bb48  add     rsp, 368h
0x14000bb4f  pop     r15
0x14000bb51  pop     r14
0x14000bb53  pop     r13
0x14000bb55  pop     r12
0x14000bb57  pop     rdi
0x14000bb58  pop     rsi
0x14000bb59  pop     rbx
0x14000bb5a  pop     rbp
0x14000bb5b  retn
0x14000bb5c  mov     rdx, r13
0x14000bb5f  mov     rcx, r13
0x14000bb62  mov     eax, 5Ch ; '\'
0x14000bb67  cmp     ax, [rbp+rcx*2+2A0h+Filename]
0x14000bb6c  jnz     short loc_14000BB77
0x14000bb6e  lea     rdx, [rcx+1]
0x14000bb72  mov     rcx, rdx
0x14000bb75  jmp     short loc_14000BB82
0x14000bb77  cmp     r13w, [rbp+rcx*2+2A0h+Filename]
0x14000bb7d  jz      short loc_14000BB8B
0x14000bb7f  inc     rcx
0x14000bb82  cmp     rcx, 103h
0x14000bb89  jb      short loc_14000BB62
0x14000bb8b  add     rdx, rdx
0x14000bb8e  cmp     rdx, 208h
0x14000bb95  jnb     loc_14000C2FC
0x14000bb9b  mov     [rbp+rdx+2A0h+Filename], r13w
0x14000bba1  mov     rdx, rdi
0x14000bba4  lea     rax, [rbp+2A0h+Filename]
0x14000bba8  cmp     [rax], r13w
0x14000bbac  jz      short loc_14000BBB8
0x14000bbae  add     rax, 2
0x14000bbb2  sub     rdx, 1
0x14000bbb6  jnz     short loc_14000BBA8
0x14000bbb8  mov     rax, rdx
0x14000bbbb  neg     rax
0x14000bbbe  sbb     ebx, ebx
0x14000bbc0  not     ebx
0x14000bbc2  and     ebx, 80070057h
0x14000bbc8  mov     rax, rdx
0x14000bbcb  mov     rcx, rdi
0x14000bbce  sub     rcx, rdx
0x14000bbd1  neg     rax
0x14000bbd4  sbb     r8, r8
0x14000bbd7  and     r8, rcx
0x14000bbda  test    rdx, rdx
0x14000bbdd  jz      loc_14000BB0B
0x14000bbe3  mov     eax, 7FFFFFFEh
0x14000bbe8  lea     rcx, aDisksnapshotCo; "DiskSnapshot.conf"
0x14000bbef  sub     rdi, r8
0x14000bbf2  lea     rdx, [rbp+2A0h+Filename]
0x14000bbf6  lea     rdx, [rdx+r8*2]
0x14000bbfa  jz      short loc_14000BC20
0x14000bbfc  test    rax, rax
0x14000bbff  jz      short loc_14000BC20
0x14000bc01  movzx   r8d, word ptr [rcx]
0x14000bc05  test    r8w, r8w
0x14000bc09  jz      short loc_14000BC20
0x14000bc0b  add     rcx, 2
0x14000bc0f  mov     [rdx], r8w
0x14000bc13  add     rdx, 2
0x14000bc17  dec     rax
0x14000bc1a  sub     rdi, 1
0x14000bc1e  jnz     short loc_14000BBFC
0x14000bc20  mov     rax, rdi
0x14000bc23  neg     rax
0x14000bc26  sbb     ebx, ebx
0x14000bc28  not     ebx
0x14000bc2a  and     ebx, 8007007Ah
0x14000bc30  lea     rcx, [rdx-2]
0x14000bc34  test    rdi, rdi
0x14000bc37  cmovnz  rcx, rdx
0x14000bc3b  mov     [rcx], r13w
0x14000bc3f  jnz     short loc_14000BC61
0x14000bc41  jmp     loc_14000BB0B
0x14000bc46  mov     r8, rcx; unsigned __int16 *
0x14000bc49  mov     edx, 104h; unsigned __int64
0x14000bc4e  lea     rcx, [rbp+2A0h+Filename]; unsigned __int16 *
0x14000bc52  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000bc57  mov     ebx, eax
0x14000bc59  test    eax, eax
0x14000bc5b  js      loc_14000BB0B
0x14000bc61  lea     rdx, [rsp+3A0h+Src+8]; Src
0x14000bc66  lea     rcx, [rbp+2A0h+Filename]; FileName
0x14000bc6a  call    ?LoadTextFile@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LoadTextFile(ushort const *,std::wstring &)
0x14000bc6f  mov     ebx, eax
0x14000bc71  test    eax, eax
0x14000bc73  js      loc_14000BB0B
0x14000bc79  mov     rdi, r13
0x14000bc7c  xorps   xmm0, xmm0
0x14000bc7f  movups  [rbp+2A0h+var_2D8], xmm0
0x14000bc83  movdqu  [rbp+2A0h+var_2C8], xmm6
0x14000bc88  mov     word ptr [rbp+2A0h+var_2D8], r13w
0x14000bc8d  movups  [rbp+2A0h+var_318], xmm0
0x14000bc91  mov     [rbp+2A0h+var_308], r13
0x14000bc95  mov     [rbp+2A0h+var_300], 7
0x14000bc9d  mov     word ptr [rbp+2A0h+var_318], r13w
0x14000bca2  mov     r8, rdi
0x14000bca5  lea     rdx, asc_14000EE8C; "\n"
0x14000bcac  lea     rcx, [rsp+3A0h+Src+8]
0x14000bcb1  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x14000bcb6  mov     rsi, rax
0x14000bcb9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000bcbd  jz      loc_14000C2DB
0x14000bcc3  mov     r8, rdi
0x14000bcc6  lea     rdx, asc_14000FE44; "|"
0x14000bccd  lea     rcx, [rsp+3A0h+Src+8]
0x14000bcd2  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x14000bcd7  mov     rbx, rax
0x14000bcda  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000bcde  jz      loc_14000C286
0x14000bce4  cmp     rax, rsi
0x14000bce7  ja      loc_14000C286
0x14000bced  mov     rcx, rsi
0x14000bcf0  sub     rcx, rax
0x14000bcf3  dec     rcx
0x14000bcf6  cmp     rcx, 1
0x14000bcfa  jb      loc_14000C286
0x14000bd00  mov     r14, rax
0x14000bd03  sub     r14, rdi
0x14000bd06  cmp     r14, 1
0x14000bd0a  jb      loc_14000C286
0x14000bd10  lea     r12, [rax+1]
0x14000bd14  mov     r8, r12
0x14000bd17  lea     rdx, asc_14000FE44; "|"
0x14000bd1e  lea     rcx, [rsp+3A0h+Src+8]
0x14000bd23  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x14000bd28  mov     r15, rax
0x14000bd2b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000bd2f  jz      loc_14000BE2F
0x14000bd35  cmp     rax, rsi
0x14000bd38  ja      loc_14000BE2F
0x14000bd3e  mov     rcx, rsi
0x14000bd41  sub     rcx, rax
0x14000bd44  dec     rcx
0x14000bd47  cmp     rcx, 1
0x14000bd4b  jb      loc_14000BE2F
0x14000bd51  mov     rcx, rax
0x14000bd54  sub     rcx, rdi
0x14000bd57  cmp     rcx, 1
0x14000bd5b  jb      loc_14000BE2F
0x14000bd61  xorps   xmm0, xmm0
0x14000bd64  movups  [rsp+3A0h+var_340+8], xmm0
0x14000bd69  xorps   xmm1, xmm1
0x14000bd6c  movdqu  xmmword ptr [rsp+3A0h+var_330+8], xmm1
0x14000bd72  mov     r8, qword ptr [rsp+3A0h+var_350+8]
0x14000bd77  cmp     r8, rdi
0x14000bd7a  jb      loc_14000C2F6
0x14000bd80  sub     r8, rdi
0x14000bd83  cmp     r8, r14
0x14000bd86  cmovnb  r8, r14
0x14000bd8a  lea     rax, [rsp+3A0h+Src+8]
0x14000bd8f  cmp     qword ptr [rsp+3A0h+var_340], 7
0x14000bd95  cmova   rax, qword ptr [rsp+3A0h+Src+8]
0x14000bd9b  lea     rdx, [rax+rdi*2]
0x14000bd9f  lea     rcx, [rsp+3A0h+var_340+8]
0x14000bda4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14000bda9  lea     rdx, [rsp+3A0h+var_340+8]
0x14000bdae  lea     rcx, [rbp+2A0h+var_318]
0x14000bdb2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14000bdb7  lea     rcx, [rsp+3A0h+var_340+8]
0x14000bdbc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000bdc1  xorps   xmm0, xmm0
0x14000bdc4  movups  [rsp+3A0h+var_340+8], xmm0
0x14000bdc9  xorps   xmm1, xmm1
0x14000bdcc  movdqu  xmmword ptr [rsp+3A0h+var_330+8], xmm1
0x14000bdd2  mov     r8, qword ptr [rsp+3A0h+var_350+8]
0x14000bdd7  cmp     r8, r12
0x14000bdda  jb      loc_14000C2F6
0x14000bde0  mov     rax, r15
0x14000bde3  sub     rax, rbx
0x14000bde6  dec     rax
0x14000bde9  sub     r8, r12
0x14000bdec  cmp     r8, rax
0x14000bdef  cmovnb  r8, rax
0x14000bdf3  lea     rax, [rsp+3A0h+Src+8]
0x14000bdf8  cmp     qword ptr [rsp+3A0h+var_340], 7
0x14000bdfe  cmova   rax, qword ptr [rsp+3A0h+Src+8]
0x14000be04  lea     rdx, [rax+r12*2]
0x14000be08  lea     rcx, [rsp+3A0h+var_340+8]
0x14000be0d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14000be12  lea     rdx, [rsp+3A0h+var_340+8]
0x14000be17  lea     rcx, [rbp+2A0h+var_2D8]
0x14000be1b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14000be20  lea     rcx, [rsp+3A0h+var_340+8]
0x14000be25  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000be2a  mov     rbx, r15
0x14000be2d  jmp     short loc_14000BEA8
0x14000be2f  lea     rcx, [rbp+2A0h+var_318]
0x14000be33  cmp     [rbp+2A0h+var_300], 7
0x14000be38  cmova   rcx, qword ptr [rbp+2A0h+var_318]
0x14000be3d  mov     [rbp+2A0h+var_308], r13
0x14000be41  mov     [rcx], r13w
0x14000be45  xorps   xmm0, xmm0
0x14000be48  movups  [rsp+3A0h+var_340+8], xmm0
0x14000be4d  xorps   xmm1, xmm1
0x14000be50  movdqu  xmmword ptr [rsp+3A0h+var_330+8], xmm1
0x14000be56  mov     rax, qword ptr [rsp+3A0h+var_350+8]
0x14000be5b  cmp     rax, rdi
0x14000be5e  jb      loc_14000C2F6
0x14000be64  sub     rax, rdi
0x14000be67  cmp     rax, r14
0x14000be6a  cmovb   r14, rax
0x14000be6e  lea     rax, [rsp+3A0h+Src+8]
0x14000be73  cmp     qword ptr [rsp+3A0h+var_340], 7
0x14000be79  cmova   rax, qword ptr [rsp+3A0h+Src+8]
0x14000be7f  lea     rdx, [rax+rdi*2]
0x14000be83  mov     r8, r14
0x14000be86  lea     rcx, [rsp+3A0h+var_340+8]
0x14000be8b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14000be90  lea     rdx, [rsp+3A0h+var_340+8]
0x14000be95  lea     rcx, [rbp+2A0h+var_2D8]
0x14000be99  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14000be9e  lea     rcx, [rsp+3A0h+var_340+8]
0x14000bea3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000bea8  xorps   xmm0, xmm0
0x14000beab  movups  [rbp+2A0h+var_2F8], xmm0
0x14000beaf  movdqu  [rbp+2A0h+var_2E8], xmm6
0x14000beb4  mov     word ptr [rbp+2A0h+var_2F8], r13w
0x14000beb9  movups  [rbp+2A0h+var_2B8], xmm0
0x14000bebd  movdqu  [rbp+2A0h+var_2A8], xmm6
0x14000bec2  mov     word ptr [rbp+2A0h+var_2B8], r13w
0x14000bec7  movups  [rbp+2A0h+var_298], xmm0
0x14000becb  movdqu  [rbp+2A0h+var_288], xmm6
0x14000bed0  mov     word ptr [rbp+2A0h+var_298], r13w
0x14000bed5  mov     r8, rbx
0x14000bed8  lea     rdx, asc_14000FDDC; "*"
0x14000bedf  lea     rcx, [rsp+3A0h+Src+8]
0x14000bee4  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x14000bee9  mov     rdi, rax
0x14000beec  cmp     rax, rsi
0x14000beef  ja      short loc_14000BEF7
0x14000bef1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000bef5  jnz     short loc_14000BEFA
0x14000bef7  mov     rdi, rsi
0x14000befa  mov     r8, rbx
0x14000befd  lea     rdx, asc_14000FE48; "**"
0x14000bf04  lea     rcx, [rsp+3A0h+Src+8]
0x14000bf09  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x14000bf0e  mov     r14, rax
0x14000bf11  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000bf15  jz      loc_14000C07B
0x14000bf1b  cmp     rax, rsi
0x14000bf1e  ja      loc_14000C07B
0x14000bf24  lea     rcx, [rbx+1]
0x14000bf28  xorps   xmm0, xmm0
  ... truncated ...
```
