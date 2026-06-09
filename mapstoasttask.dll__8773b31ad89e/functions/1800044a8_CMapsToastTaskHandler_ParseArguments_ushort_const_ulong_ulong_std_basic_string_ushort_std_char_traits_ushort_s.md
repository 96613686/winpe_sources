# CMapsToastTaskHandler::ParseArguments(ushort const *,ulong *,ulong *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,ulong *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,ulong *,ulong *)

- ea: `0x1800044a8`
- end: `0x1800049df`
- name: `?ParseArguments@CMapsToastTaskHandler@@AEAAJPEBGPEAK1PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@12211@Z`
- size: `1335`
- prototype: `__int64 __fastcall(const void *, _WORD *, _DWORD *, _DWORD *, __int64, _DWORD *, __int64, __int64, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task`

## callers

- `0x180005e60`

## callees

- `0x1800015b0`
- `0x1800015d4`
- `0x180002354`
- `0x1800027e4`
- `0x180002850`
- `0x1800044a8`
- `0x1800063b4`
- `0x1800063dc`
- `0x180006a00`
- `0x180009540`

## import_xrefs

- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800049a2`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800049a2`
- `msvcp_win!??0?$basic_istream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@_N@Z` at `0x180004669`
- `msvcp_win!??0?$basic_istream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@_N@Z` at `0x180004669`
- `msvcp_win!??1?$basic_istream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180004998`
- `msvcp_win!??1?$basic_istream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180004998`
- `msvcp_win!??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x18000464a`
- `msvcp_win!??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x18000464a`
- `msvcp_win!??0?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x1800046a6`
- `msvcp_win!??0?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x1800046a6`
- `msvcp_win!??7ios_base@std@@QEBA_NXZ` at `0x1800047a1`
- `msvcp_win!??7ios_base@std@@QEBA_NXZ` at `0x1800047f2`
- `msvcp_win!??7ios_base@std@@QEBA_NXZ` at `0x18000482d`
- `msvcp_win!??7ios_base@std@@QEBA_NXZ` at `0x18000485a`
- `msvcp_win!??7ios_base@std@@QEBA_NXZ` at `0x180004898`
- `msvcp_win!??7ios_base@std@@QEBA_NXZ` at `0x1800048c6`
- `msvcp_win!??7ios_base@std@@QEBA_NXZ` at `0x1800048f3`
- `msvcp_win!??7ios_base@std@@QEBA_NXZ` at `0x180004930`
- `msvcp_win!??7ios_base@std@@QEBA_NXZ` at `0x1800047a1`
- `msvcp_win!??7ios_base@std@@QEBA_NXZ` at `0x1800047f2`
- `msvcp_win!??7ios_base@std@@QEBA_NXZ` at `0x18000482d`
- `msvcp_win!??7ios_base@std@@QEBA_NXZ` at `0x18000485a`
- `msvcp_win!??7ios_base@std@@QEBA_NXZ` at `0x180004898`
- `msvcp_win!??7ios_base@std@@QEBA_NXZ` at `0x1800048c6`
- `msvcp_win!??7ios_base@std@@QEBA_NXZ` at `0x1800048f3`
- `msvcp_win!??7ios_base@std@@QEBA_NXZ` at `0x180004930`
- `msvcp_win!?_Xbad_alloc@std@@YAXXZ` at `0x1800046ce`
- `msvcp_win!?_Xbad_alloc@std@@YAXXZ` at `0x1800046ce`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x1800047c0`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x1800047c0`

## string_xrefs

- `0x1800047b4`: `CMapsToastTaskHandler::ParseArguments`

## pseudocode

```c
__int64 __fastcall CMapsToastTaskHandler::ParseArguments(
        const void *a1,
        _WORD *a2,
        _DWORD *a3,
        _DWORD *a4,
        __int64 a5,
        _DWORD *a6,
        __int64 a7,
        __int64 a8,
        _DWORD *a9,
        _DWORD *a10)
{
  _QWORD *v13; // rsi
  unsigned __int64 v14; // rdi
  unsigned __int64 v15; // r15
  size_t v16; // rcx
  void *v17; // rax
  void **v18; // r12
  size_t v19; // rdi
  _QWORD *v20; // rbx
  void *v21; // rax
  int v22; // eax
  __int64 v23; // rax
  int v24; // r8d
  unsigned int v25; // ebx
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  int v33; // eax
  _DWORD *v36; // [rsp+58h] [rbp-A8h]
  _QWORD v37[2]; // [rsp+60h] [rbp-A0h] BYREF
  void **v38; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v39[16]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD *v40; // [rsp+88h] [rbp-78h]
  _QWORD *v41; // [rsp+A8h] [rbp-58h]
  _DWORD *v42; // [rsp+C0h] [rbp-40h]
  char *v43; // [rsp+D8h] [rbp-28h]
  int v44; // [rsp+E0h] [rbp-20h]
  _BYTE v45[96]; // [rsp+F0h] [rbp-10h] BYREF
  void ***v46; // [rsp+150h] [rbp+50h]
  void *Src[2]; // [rsp+158h] [rbp+58h] BYREF
  unsigned __int64 v48; // [rsp+168h] [rbp+68h]
  __int64 v49; // [rsp+170h] [rbp+70h]
  wchar_t String[8]; // [rsp+178h] [rbp+78h] BYREF
  __int64 v51; // [rsp+188h] [rbp+88h]
  __int64 v52; // [rsp+190h] [rbp+90h]

  v36 = a10;
  v13 = 0;
  *(_OWORD *)Src = 0;
  v48 = 0;
  v49 = 0;
  v14 = -1;
  do
    ++v14;
  while ( a2[v14] );
  v15 = 0x7FFFFFFFFFFFFFFELL;
  if ( v14 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( v14 <= 7 )
  {
    v48 = v14;
    v49 = 7;
    memcpy_0(Src, a2, 2 * v14);
    *((_WORD *)Src + v14) = 0;
    v15 = v49;
    v14 = v48;
    v13 = Src[0];
    goto LABEL_19;
  }
  if ( (v14 | 7) <= 0x7FFFFFFFFFFFFFFELL )
  {
    v15 = v14 | 7;
    if ( (v14 | 7) < 0xA )
      v15 = 10;
    if ( v15 + 1 > 0x7FFFFFFFFFFFFFFFLL )
      goto LABEL_54;
    v16 = 2 * (v15 + 1);
    if ( !v16 )
      goto LABEL_18;
  }
  else
  {
    v16 = -2;
  }
  if ( v16 >= 0x1000 )
  {
    if ( v16 + 39 >= v16 )
    {
      v17 = operator new(v16 + 39);
      if ( !v17 )
        __fastfail(5u);
      v13 = (_QWORD *)(((unsigned __int64)v17 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *(v13 - 1) = v17;
      goto LABEL_18;
    }
LABEL_54:
    __scrt_throw_std_bad_array_new_length();
  }
  v13 = operator new(v16);
LABEL_18:
  Src[0] = v13;
  v48 = v14;
  v49 = v15;
  memcpy_0(v13, a2, 2 * v14);
  *((_WORD *)v13 + v14) = 0;
LABEL_19:
  v37[0] = &std::basic_istringstream<unsigned short>::`vbtable';
  std::basic_ios<unsigned short>::basic_ios<unsigned short>(v45);
  std::basic_istream<unsigned short>::basic_istream<unsigned short>(v37, &v38, 0, 0, 1);
  *(_QWORD *)((char *)v37 + *(int *)(v37[0] + 4LL)) = &std::basic_istringstream<unsigned short>::`vftable';
  *(_DWORD *)((char *)&v36 + *(int *)(v37[0] + 4LL) + 4) = *(_DWORD *)(v37[0] + 4LL) - 144;
  v46 = &v38;
  std::basic_streambuf<unsigned short>::basic_streambuf<unsigned short>(&v38);
  v38 = &std::basic_stringbuf<unsigned short>::`vftable';
  v18 = Src;
  if ( v15 > 7 )
    v18 = (void **)v13;
  if ( v14 > 0x7FFFFFFF )
  {
    std::_Xbad_alloc();
    __debugbreak();
  }
  if ( v14 )
  {
    v19 = 2 * v14;
    if ( v19 )
    {
      if ( v19 < 0x1000 )
      {
        v20 = operator new(v19);
      }
      else
      {
        if ( v19 + 39 < v19 )
          __scrt_throw_std_bad_array_new_length();
        v21 = operator new(v19 + 39);
        if ( !v21 )
          __fastfail(5u);
        v20 = (_QWORD *)(((unsigned __int64)v21 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v20 - 1) = v21;
      }
    }
    else
    {
      v20 = 0;
    }
    memcpy_0(v20, v18, v19);
    v43 = (char *)v20 + v19;
    *v40 = v20;
    *v41 = v20;
    *v42 = (__int64)v19 >> 1;
    v22 = 3;
  }
  else
  {
    v22 = 2;
    v43 = 0;
  }
  v44 = v22;
  std::wstring::~wstring(Src);
  *(_OWORD *)String = 0;
  v51 = 0;
  v52 = 7;
  String[0] = 0;
  v23 = std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v37, String);
  if ( (unsigned __int8)std::ios_base::operator!(v23 + *(int *)(*(_QWORD *)v23 + 4LL)) )
  {
    v24 = 165;
  }
  else
  {
    *a3 = std::stoi(String);
    v26 = std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v37, String);
    if ( (unsigned __int8)std::ios_base::operator!(v26 + *(int *)(*(_QWORD *)v26 + 4LL)) )
    {
      v24 = 168;
    }
    else
    {
      *a4 = std::stoi(String);
      v27 = std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v37, a5);
      if ( (unsigned __int8)std::ios_base::operator!(v27 + *(int *)(*(_QWORD *)v27 + 4LL)) )
      {
        v24 = 171;
      }
      else
      {
        v28 = std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v37, String);
        if ( (unsigned __int8)std::ios_base::operator!(v28 + *(int *)(*(_QWORD *)v28 + 4LL)) )
        {
          v24 = 173;
        }
        else
        {
          *a6 = std::stoi(String);
          v29 = std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v37, a7);
          if ( (unsigned __int8)std::ios_base::operator!(v29 + *(int *)(*(_QWORD *)v29 + 4LL)) )
          {
            v24 = 176;
          }
          else
          {
            v30 = std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v37, a8);
            if ( (unsigned __int8)std::ios_base::operator!(v30 + *(int *)(*(_QWORD *)v30 + 4LL)) )
            {
              v24 = 178;
            }
            else
            {
              v31 = std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(
                      v37,
                      String);
              if ( (unsigned __int8)std::ios_base::operator!(v31 + *(int *)(*(_QWORD *)v31 + 4LL)) )
              {
                v24 = 180;
              }
              else
              {
                *a9 = std::stoi(String);
                v32 = std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(
                        v37,
                        String);
                if ( !(unsigned __int8)std::ios_base::operator!(v32 + *(int *)(*(_QWORD *)v32 + 4LL)) )
                {
                  v25 = 0;
                  v33 = std::stoi(String);
                  *v36 = v33;
                  goto LABEL_52;
                }
                v24 = 183;
              }
            }
          }
        }
      }
    }
  }
  v25 = ZTraceReportOrigination(-2147024809, "CMapsToastTaskHandler::ParseArguments", v24, a1);
LABEL_52:
  std::wstring::~wstring(String);
  *(_QWORD *)((char *)v37 + *(int *)(v37[0] + 4LL)) = &std::basic_istringstream<unsigned short>::`vftable';
  *(_DWORD *)((char *)&v36 + *(int *)(v37[0] + 4LL) + 4) = *(_DWORD *)(v37[0] + 4LL) - 144;
  std::basic_stringbuf<unsigned short>::~basic_stringbuf<unsigned short>(&v38);
  std::basic_istream<unsigned short>::~basic_istream<unsigned short,std::char_traits<unsigned short>>(v39);
  std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v45);
  return v25;
}

```

## disassembly

```asm
0x1800044a8  push    rbp
0x1800044aa  push    rbx
0x1800044ab  push    rsi
0x1800044ac  push    rdi
0x1800044ad  push    r12
0x1800044af  push    r13
0x1800044b1  push    r14
0x1800044b3  push    r15
0x1800044b5  lea     rbp, [rsp-0A8h]
0x1800044bd  sub     rsp, 1A8h
0x1800044c4  mov     rax, cs:__security_cookie
0x1800044cb  xor     rax, rsp
0x1800044ce  mov     [rbp+0E0h+var_48], rax
0x1800044d5  mov     [rsp+1E0h+var_1B8], r9
0x1800044da  mov     r13, r8
0x1800044dd  mov     r12, rdx
0x1800044e0  mov     r14, rcx
0x1800044e3  mov     rax, [rbp+0E0h+arg_20]
0x1800044ea  mov     [rsp+1E0h+var_1B0], rax
0x1800044ef  mov     rax, [rbp+0E0h+arg_28]
0x1800044f6  mov     [rsp+1E0h+var_1A8], rax
0x1800044fb  mov     rax, [rbp+0E0h+arg_30]
0x180004502  mov     [rsp+1E0h+var_1A0], rax
0x180004507  mov     rax, [rbp+0E0h+arg_38]
0x18000450e  mov     [rsp+1E0h+var_198], rax
0x180004513  mov     rax, [rbp+0E0h+arg_40]
0x18000451a  mov     [rsp+1E0h+var_190], rax
0x18000451f  mov     rax, [rbp+0E0h+arg_48]
0x180004526  mov     [rsp+1E0h+var_188], rax
0x18000452b  xor     esi, esi
0x18000452d  mov     [rsp+1E0h+var_1C0], esi
0x180004531  xorps   xmm0, xmm0
0x180004534  movups  xmmword ptr [rbp+0E0h+Src], xmm0
0x180004538  mov     [rbp+0E0h+var_78], rsi
0x18000453c  mov     [rbp+0E0h+var_70], rsi
0x180004540  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180004544  inc     rdi
0x180004547  cmp     [rdx+rdi*2], si
0x18000454b  jnz     short loc_180004544
0x18000454d  mov     r15, 7FFFFFFFFFFFFFFEh
0x180004557  cmp     rdi, r15
0x18000455a  ja      loc_1800049D9
0x180004560  cmp     rdi, 7
0x180004564  ja      short loc_180004598
0x180004566  mov     [rbp+0E0h+var_78], rdi
0x18000456a  mov     [rbp+0E0h+var_70], 7
0x180004572  lea     rbx, [rdi+rdi]
0x180004576  mov     r8, rbx; Size
0x180004579  lea     rcx, [rbp+0E0h+Src]; void *
0x18000457d  call    memcpy_0
0x180004582  mov     word ptr [rbp+rbx+0E0h+Src], si
0x180004587  mov     r15, [rbp+0E0h+var_70]
0x18000458b  mov     rdi, [rbp+0E0h+var_78]
0x18000458f  mov     rsi, [rbp+0E0h+Src]
0x180004593  jmp     loc_18000463A
0x180004598  mov     rax, rdi
0x18000459b  or      rax, 7
0x18000459f  cmp     rax, r15
0x1800045a2  jbe     short loc_1800045AD
0x1800045a4  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x1800045ab  jmp     short loc_1800045D8
0x1800045ad  mov     r15, rax
0x1800045b0  mov     ecx, 0Ah
0x1800045b5  cmp     rax, rcx
0x1800045b8  cmovb   r15, rcx
0x1800045bc  lea     rcx, [r15+1]
0x1800045c0  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800045ca  cmp     rcx, rax
0x1800045cd  ja      loc_1800049D3
0x1800045d3  add     rcx, rcx; Size
0x1800045d6  jz      short loc_180004616
0x1800045d8  cmp     rcx, 1000h
0x1800045df  jb      short loc_18000460E
0x1800045e1  lea     rax, [rcx+27h]
0x1800045e5  cmp     rax, rcx
0x1800045e8  jbe     loc_1800049D3
0x1800045ee  mov     rcx, rax; Size
0x1800045f1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800045f6  test    rax, rax
0x1800045f9  jnz     short loc_180004600
0x1800045fb  lea     ecx, [rax+5]
0x1800045fe  int     29h; Win8: RtlFailFast(ecx)
0x180004600  lea     rsi, [rax+27h]
0x180004604  and     rsi, 0FFFFFFFFFFFFFFE0h
0x180004608  mov     [rsi-8], rax
0x18000460c  jmp     short loc_180004616
0x18000460e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004613  mov     rsi, rax
0x180004616  mov     [rbp+0E0h+Src], rsi
0x18000461a  mov     [rbp+0E0h+var_78], rdi
0x18000461e  mov     [rbp+0E0h+var_70], r15
0x180004622  lea     rbx, [rdi+rdi]
0x180004626  mov     r8, rbx; Size
0x180004629  mov     rdx, r12; Src
0x18000462c  mov     rcx, rsi; void *
0x18000462f  call    memcpy_0
0x180004634  xor     ecx, ecx
0x180004636  mov     [rsi+rbx], cx
0x18000463a  lea     rax, ??_8?$basic_istringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@7B@; const std::basic_istringstream<ushort>::`vbtable'
0x180004641  mov     [rsp+1E0h+var_180], rax
0x180004646  lea     rcx, [rbp+0E0h+var_F0]
0x18000464a  call    cs:__imp_??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ; std::basic_ios<ushort>::basic_ios<ushort>(void)
0x180004650  nop
0x180004651  mov     [rsp+1E0h+var_1C0], 1
0x180004659  xor     r9d, r9d
0x18000465c  xor     r8d, r8d
0x18000465f  lea     rdx, [rsp+1E0h+var_170]
0x180004664  lea     rcx, [rsp+1E0h+var_180]
0x180004669  call    cs:__imp_??0?$basic_istream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@_N@Z; std::basic_istream<ushort>::basic_istream<ushort>(std::basic_streambuf<ushort> *,bool)
0x18000466f  nop
0x180004670  mov     rax, [rsp+1E0h+var_180]
0x180004675  movsxd  rcx, dword ptr [rax+4]
0x180004679  lea     rax, ??_7?$basic_istringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_istringstream<ushort>::`vftable'
0x180004680  mov     [rsp+rcx+1E0h+var_180], rax
0x180004685  mov     rax, [rsp+1E0h+var_180]
0x18000468a  movsxd  rcx, dword ptr [rax+4]
0x18000468e  lea     edx, [rcx-90h]
0x180004694  mov     dword ptr [rsp+rcx+1E0h+var_188+4], edx
0x180004698  lea     rax, [rsp+1E0h+var_170]
0x18000469d  mov     [rbp+0E0h+var_90], rax
0x1800046a1  lea     rcx, [rsp+1E0h+var_170]
0x1800046a6  call    cs:__imp_??0?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAA@XZ; std::basic_streambuf<ushort>::basic_streambuf<ushort>(void)
0x1800046ac  nop
0x1800046ad  lea     rax, ??_7?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringbuf<ushort>::`vftable'
0x1800046b4  mov     [rsp+1E0h+var_170], rax
0x1800046b9  lea     r12, [rbp+0E0h+Src]
0x1800046bd  cmp     r15, 7
0x1800046c1  cmova   r12, rsi
0x1800046c5  cmp     rdi, 7FFFFFFFh
0x1800046cc  jbe     short loc_1800046D5
0x1800046ce  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800046d4  int     3; Trap to Debugger
0x1800046d5  xor     esi, esi
0x1800046d7  test    rdi, rdi
0x1800046da  jz      short loc_180004757
0x1800046dc  add     rdi, rdi
0x1800046df  jnz     short loc_1800046E5
0x1800046e1  mov     ebx, esi
0x1800046e3  jmp     short loc_180004723
0x1800046e5  cmp     rdi, 1000h
0x1800046ec  jb      short loc_180004718
0x1800046ee  lea     rcx, [rdi+27h]; Size
0x1800046f2  cmp     rcx, rdi
0x1800046f5  jbe     loc_1800049CD
0x1800046fb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004700  test    rax, rax
0x180004703  jnz     short loc_18000470A
0x180004705  lea     ecx, [rax+5]
0x180004708  int     29h; Win8: RtlFailFast(ecx)
0x18000470a  lea     rbx, [rax+27h]
0x18000470e  and     rbx, 0FFFFFFFFFFFFFFE0h
0x180004712  mov     [rbx-8], rax
0x180004716  jmp     short loc_180004723
0x180004718  mov     rcx, rdi; Size
0x18000471b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004720  mov     rbx, rax
0x180004723  mov     r8, rdi; Size
0x180004726  mov     rdx, r12; Src
0x180004729  mov     rcx, rbx; void *
0x18000472c  call    memcpy_0
0x180004731  lea     rcx, [rbx+rdi]
0x180004735  mov     [rbp+0E0h+var_108], rcx
0x180004739  mov     rcx, [rbp+0E0h+var_158]
0x18000473d  mov     [rcx], rbx
0x180004740  mov     rcx, [rbp+0E0h+var_138]
0x180004744  mov     [rcx], rbx
0x180004747  sar     rdi, 1
0x18000474a  mov     rax, [rbp+0E0h+var_120]
0x18000474e  mov     [rax], edi
0x180004750  mov     eax, 3
0x180004755  jmp     short loc_180004760
0x180004757  mov     eax, 2
0x18000475c  mov     [rbp+0E0h+var_108], rsi
0x180004760  mov     [rbp+0E0h+var_100], eax
0x180004763  lea     rcx, [rbp+0E0h+Src]
0x180004767  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000476c  xorps   xmm0, xmm0
0x18000476f  movups  xmmword ptr [rbp+0E0h+String], xmm0
0x180004773  mov     [rbp+0E0h+var_58], rsi
0x18000477a  mov     [rbp+0E0h+var_50], 7
0x180004785  mov     [rbp+0E0h+String], si
0x180004789  lea     rdx, [rbp+0E0h+String]
0x18000478d  lea     rcx, [rsp+1E0h+var_180]
0x180004792  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@$$QEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@G@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &&,std::wstring &,ushort)
0x180004797  mov     rcx, [rax]
0x18000479a  movsxd  rcx, dword ptr [rcx+4]
0x18000479e  add     rcx, rax
0x1800047a1  call    cs:__imp_??7ios_base@std@@QEBA_NXZ; std::ios_base::operator!(void)
0x1800047a7  test    al, al
0x1800047a9  jz      short loc_1800047CD
0x1800047ab  mov     r8d, 0A5h
0x1800047b1  mov     r9, r14
0x1800047b4  lea     rdx, aCmapstoasttask_7; "CMapsToastTaskHandler::ParseArguments"
0x1800047bb  mov     ecx, 80070057h
0x1800047c0  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x1800047c6  mov     ebx, eax
0x1800047c8  jmp     loc_180004957
0x1800047cd  lea     rcx, [rbp+0E0h+String]; String
0x1800047d1  call    ?stoi@std@@YAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@PEA_KH@Z; std::stoi(std::wstring const &,unsigned __int64 *,int)
0x1800047d6  mov     [r13+0], eax
0x1800047da  lea     rdx, [rbp+0E0h+String]
0x1800047de  lea     rcx, [rsp+1E0h+var_180]
0x1800047e3  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@$$QEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@G@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &&,std::wstring &,ushort)
0x1800047e8  mov     rcx, [rax]
0x1800047eb  movsxd  rcx, dword ptr [rcx+4]
0x1800047ef  add     rcx, rax
0x1800047f2  call    cs:__imp_??7ios_base@std@@QEBA_NXZ; std::ios_base::operator!(void)
0x1800047f8  test    al, al
0x1800047fa  jz      short loc_180004804
0x1800047fc  mov     r8d, 0A8h
0x180004802  jmp     short loc_1800047B1
0x180004804  lea     rcx, [rbp+0E0h+String]; String
0x180004808  call    ?stoi@std@@YAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@PEA_KH@Z; std::stoi(std::wstring const &,unsigned __int64 *,int)
0x18000480d  mov     rcx, [rsp+1E0h+var_1B8]
0x180004812  mov     [rcx], eax
0x180004814  mov     rdx, [rsp+1E0h+var_1B0]
0x180004819  lea     rcx, [rsp+1E0h+var_180]
0x18000481e  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@$$QEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@G@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &&,std::wstring &,ushort)
0x180004823  mov     rcx, [rax]
0x180004826  movsxd  rcx, dword ptr [rcx+4]
0x18000482a  add     rcx, rax
0x18000482d  call    cs:__imp_??7ios_base@std@@QEBA_NXZ; std::ios_base::operator!(void)
0x180004833  test    al, al
0x180004835  jz      short loc_180004842
0x180004837  mov     r8d, 0ABh
0x18000483d  jmp     loc_1800047B1
0x180004842  lea     rdx, [rbp+0E0h+String]
0x180004846  lea     rcx, [rsp+1E0h+var_180]
0x18000484b  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@$$QEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@G@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &&,std::wstring &,ushort)
0x180004850  mov     rcx, [rax]
0x180004853  movsxd  rcx, dword ptr [rcx+4]
0x180004857  add     rcx, rax
0x18000485a  call    cs:__imp_??7ios_base@std@@QEBA_NXZ; std::ios_base::operator!(void)
0x180004860  test    al, al
0x180004862  jz      short loc_18000486F
0x180004864  mov     r8d, 0ADh
0x18000486a  jmp     loc_1800047B1
0x18000486f  lea     rcx, [rbp+0E0h+String]; String
0x180004873  call    ?stoi@std@@YAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@PEA_KH@Z; std::stoi(std::wstring const &,unsigned __int64 *,int)
0x180004878  mov     rcx, [rsp+1E0h+var_1A8]
0x18000487d  mov     [rcx], eax
0x18000487f  mov     rdx, [rsp+1E0h+var_1A0]
0x180004884  lea     rcx, [rsp+1E0h+var_180]
0x180004889  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@$$QEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@G@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &&,std::wstring &,ushort)
0x18000488e  mov     rcx, [rax]
0x180004891  movsxd  rcx, dword ptr [rcx+4]
0x180004895  add     rcx, rax
0x180004898  call    cs:__imp_??7ios_base@std@@QEBA_NXZ; std::ios_base::operator!(void)
0x18000489e  test    al, al
0x1800048a0  jz      short loc_1800048AD
0x1800048a2  mov     r8d, 0B0h
0x1800048a8  jmp     loc_1800047B1
0x1800048ad  mov     rdx, [rsp+1E0h+var_198]
0x1800048b2  lea     rcx, [rsp+1E0h+var_180]
0x1800048b7  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@$$QEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@G@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &&,std::wstring &,ushort)
0x1800048bc  mov     rcx, [rax]
0x1800048bf  movsxd  rcx, dword ptr [rcx+4]
0x1800048c3  add     rcx, rax
0x1800048c6  call    cs:__imp_??7ios_base@std@@QEBA_NXZ; std::ios_base::operator!(void)
0x1800048cc  test    al, al
0x1800048ce  jz      short loc_1800048DB
0x1800048d0  mov     r8d, 0B2h
0x1800048d6  jmp     loc_1800047B1
0x1800048db  lea     rdx, [rbp+0E0h+String]
0x1800048df  lea     rcx, [rsp+1E0h+var_180]
0x1800048e4  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@$$QEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@G@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &&,std::wstring &,ushort)
0x1800048e9  mov     rcx, [rax]
0x1800048ec  movsxd  rcx, dword ptr [rcx+4]
0x1800048f0  add     rcx, rax
0x1800048f3  call    cs:__imp_??7ios_base@std@@QEBA_NXZ; std::ios_base::operator!(void)
0x1800048f9  test    al, al
0x1800048fb  jz      short loc_180004908
0x1800048fd  mov     r8d, 0B4h
0x180004903  jmp     loc_1800047B1
0x180004908  lea     rcx, [rbp+0E0h+String]; String
0x18000490c  call    ?stoi@std@@YAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@PEA_KH@Z; std::stoi(std::wstring const &,unsigned __int64 *,int)
0x180004911  mov     rcx, [rsp+1E0h+var_190]
0x180004916  mov     [rcx], eax
0x180004918  lea     rdx, [rbp+0E0h+String]
0x18000491c  lea     rcx, [rsp+1E0h+var_180]
0x180004921  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@$$QEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@G@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &&,std::wstring &,ushort)
0x180004926  mov     rcx, [rax]
0x180004929  movsxd  rcx, dword ptr [rcx+4]
0x18000492d  add     rcx, rax
0x180004930  call    cs:__imp_??7ios_base@std@@QEBA_NXZ; std::ios_base::operator!(void)
0x180004936  test    al, al
0x180004938  jz      short loc_180004945
0x18000493a  mov     r8d, 0B7h
0x180004940  jmp     loc_1800047B1
0x180004945  mov     ebx, esi
0x180004947  lea     rcx, [rbp+0E0h+String]; String
0x18000494b  call    ?stoi@std@@YAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@PEA_KH@Z; std::stoi(std::wstring const &,unsigned __int64 *,int)
0x180004950  mov     rcx, [rsp+1E0h+var_188]
0x180004955  mov     [rcx], eax
0x180004957  lea     rcx, [rbp+0E0h+String]
0x18000495b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180004960  nop
0x180004961  mov     rax, [rsp+1E0h+var_180]
0x180004966  movsxd  rcx, dword ptr [rax+4]
0x18000496a  lea     rax, ??_7?$basic_istringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_istringstream<ushort>::`vftable'
  ... truncated ...
```
