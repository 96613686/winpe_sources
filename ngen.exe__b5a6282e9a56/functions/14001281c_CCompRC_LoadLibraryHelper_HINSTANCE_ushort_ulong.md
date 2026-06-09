# CCompRC::LoadLibraryHelper(HINSTANCE__ * *,ushort *,ulong)

- ea: `0x14001281c`
- end: `0x140012c81`
- name: `?LoadLibraryHelper@CCompRC@@AEAAJPEAPEAUHINSTANCE__@@PEAGK@Z`
- size: `1125`
- prototype: `__int64 __fastcall(CCompRC *this, HINSTANCE *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140012c84`

## callees

- `0x14000aa04`
- `0x14000b010`
- `0x14000c51c`
- `0x140011e90`
- `0x1400120d8`
- `0x1400121ec`
- `0x1400127b4`
- `0x14001281c`
- `0x140013200`
- `0x140013f30`

## import_xrefs

- `ucrtbase_clr0400!wcscpy_s` at `0x140012a76`
- `ucrtbase_clr0400!wcscpy_s` at `0x140012a95`
- `ucrtbase_clr0400!wcscpy_s` at `0x140012b15`
- `ucrtbase_clr0400!wcscpy_s` at `0x140012b67`
- `ucrtbase_clr0400!wcscpy_s` at `0x140012bfd`
- `ucrtbase_clr0400!wcscpy_s` at `0x140012a76`
- `ucrtbase_clr0400!wcscpy_s` at `0x140012a95`
- `ucrtbase_clr0400!wcscpy_s` at `0x140012b15`
- `ucrtbase_clr0400!wcscpy_s` at `0x140012b67`
- `ucrtbase_clr0400!wcscpy_s` at `0x140012bfd`

## pseudocode

```c
__int64 __fastcall CCompRC::LoadLibraryHelper(CCompRC *this, HINSTANCE *a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // r13
  CCompRC *v4; // r14
  int ResourceFile; // ebx
  __int64 v6; // r12
  __int64 v7; // r15
  __int64 (__fastcall *v8)(unsigned int *); // rax
  int v9; // r8d
  char v10; // si
  __int64 v12; // r8
  unsigned int i; // r13d
  unsigned int v14; // ecx
  __int64 *v15; // rsi
  unsigned int j; // eax
  unsigned int *v17; // rsi
  unsigned int v18; // eax
  wchar_t *v19; // rbx
  wchar_t *v20; // rbx
  unsigned int v21; // edx
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  wchar_t *v25; // rcx
  IErrorInfo *v26; // rax
  IErrorInfo *v27; // rdi
  int v28; // [rsp+20h] [rbp-358h]
  unsigned __int16 *v29; // [rsp+28h] [rbp-350h]
  unsigned __int64 v30; // [rsp+30h] [rbp-348h]
  unsigned __int16 *v31; // [rsp+38h] [rbp-340h]
  unsigned __int64 v32; // [rsp+40h] [rbp-338h]
  __int64 v33; // [rsp+50h] [rbp-328h]
  int v34; // [rsp+50h] [rbp-328h]
  unsigned __int16 *Destination; // [rsp+60h] [rbp-318h]
  HINSTANCE *v36; // [rsp+68h] [rbp-310h]
  wchar_t *v38; // [rsp+80h] [rbp-2F8h]
  __int64 v40; // [rsp+90h] [rbp-2E8h]
  int v41; // [rsp+98h] [rbp-2E0h] BYREF
  __int64 v42; // [rsp+A0h] [rbp-2D8h]
  _QWORD v43[3]; // [rsp+A8h] [rbp-2D0h] BYREF
  CCompRC *v44; // [rsp+C0h] [rbp-2B8h]
  unsigned int v45; // [rsp+D0h] [rbp-2A8h] BYREF
  __int64 v46; // [rsp+D8h] [rbp-2A0h] BYREF
  int v47; // [rsp+E0h] [rbp-298h]
  __int64 v48; // [rsp+110h] [rbp-268h] BYREF
  wchar_t Source[4]; // [rsp+118h] [rbp-260h] BYREF
  wchar_t v50[264]; // [rsp+120h] [rbp-258h] BYREF

  v3 = a3;
  Destination = a3;
  v36 = a2;
  v4 = this;
  v44 = this;
  ResourceFile = -2147467259;
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(*((_QWORD *)this + 6) + 2 * v7) );
  SString::Startup();
  v45 = 0;
  v46 = 0;
  v47 = 5;
  v8 = (__int64 (__fastcall *)(unsigned int *))*((_QWORD *)v4 + 8);
  if ( v8 )
  {
    ResourceFile = v8(&v45);
  }
  else
  {
    v10 = 0;
    v41 = 0;
    v42 = 0;
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      if ( __eh34_try(0, 1) )
      {
        __eh34_scope_strut(1);
        StringArrayList::Append((StringArrayList *)&v45, *(const struct SString **)&SString::s_Empty);
      }
      if ( __eh34_catch(1) )
      {
        if ( __eh34_catch_type(1, &Exception * `RTTI Type Descriptor', (Exception **)&v48) )
        {
          Exception::HandlerState::SetCaughtCxx((Exception::HandlerState *)&v41);
          v42 = v48;
          throw;
        }
      }
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_ellipsis(0) )
      {
        v43[1] = 0;
        v43[0] = &DelegatingException::`vftable';
        v43[2] = -1;
        ((void (__fastcall *)(Exception::HandlerState *, int, bool))Exception::HandlerState::SetupCatch)(
          (Exception::HandlerState *)&v41,
          919,
          v9);
        v34 = (*(__int64 (__fastcall **)(_QWORD *))(v43[0] + 16LL))(v43);
        v26 = (IErrorInfo *)(*(__int64 (__fastcall **)(_QWORD *))(v43[0] + 32LL))(v43);
        v27 = v26;
        if ( v26 )
        {
          SetErrorInfo(0, v26);
          ((void (__fastcall *)(IErrorInfo *))v27->lpVtbl->Release)(v27);
        }
        DelegatingException::~DelegatingException((DelegatingException *)v43);
        v6 = -1;
        ResourceFile = v34;
        v10 = v41;
        v4 = v44;
        v3 = a3;
        Destination = a3;
        v36 = a2;
        __eh34_try_continuation(0, &loc_1400128FC);
      }
    }
    if ( (v10 & 2) != 0 && g_fpHandleStackOverflowAfterCatch )
      g_fpHandleStackOverflowAfterCatch();
  }
  if ( ResourceFile == -2147024882 )
  {
    StringArrayList::~StringArrayList((StringArrayList *)&v45);
    return 2147942414LL;
  }
  else
  {
    v50[0] = 0;
    Source[0] = 0;
    v3[259] = 0;
    ((void (__stdcall *)(const unsigned __int16 *, unsigned __int16 *, int, unsigned __int16 *, int, unsigned __int16 *, unsigned __int64, unsigned __int16 *, unsigned __int64))SplitPath)(
      v3,
      Source,
      v9,
      v50,
      v28,
      v29,
      v30,
      v31,
      v32);
    v12 = -1;
    do
      ++v12;
    while ( Source[v12] );
    v33 = v12;
    do
      ++v6;
    while ( v50[v6] );
    v40 = v7 + v6 + v12 + 1;
    for ( i = 0; i < v45; v12 = v33 )
    {
      v14 = i;
      v15 = &v46;
      for ( j = v47; v14 >= j; j = *((_DWORD *)v15 + 2) )
      {
        v14 -= j;
        v15 = (__int64 *)*v15;
      }
      v17 = (unsigned int *)v15[v14 + 2];
      v18 = v17[2];
      if ( (v18 & 2) != 0 && ((v18 & 7) != 7 || SString::s_IsANSIMultibyte) )
      {
        if ( !(unsigned int)SString::ScanASCII((SString *)v17) )
          SString::ConvertToUnicode((SString *)v17);
        v12 = v33;
      }
      if ( v40 + (unsigned __int64)((*v17 >> ((v17[2] & 1) == 0)) - 1) > 0x104 )
      {
        ResourceFile = -2147467259;
      }
      else
      {
        wcscpy_s(Destination, v12 + 1, Source);
        v19 = &Destination[v33];
        wcscpy_s(v19, v6 + 1, v50);
        v20 = &v19[v6];
        v21 = v17[2];
        if ( *v17 >> ((v21 & 1) == 0) == 1 )
        {
          if ( (v21 & 2) != 0
            && ((v21 & 7) != 7 || SString::s_IsANSIMultibyte)
            && !(unsigned int)SString::ScanASCII((SString *)v17) )
          {
            SString::ConvertToUnicode((SString *)v17);
          }
          v25 = &v20[(*v17 >> ((v17[2] & 1) == 0)) - 1];
        }
        else
        {
          SString::ConvertToUnicode((SString *)v17);
          v38 = (wchar_t *)*((_QWORD *)v17 + 2);
          v22 = v17[2];
          if ( (v22 & 2) != 0
            && ((v22 & 7) != 7 || SString::s_IsANSIMultibyte)
            && !(unsigned int)SString::ScanASCII((SString *)v17) )
          {
            SString::ConvertToUnicode((SString *)v17);
          }
          wcscpy_s(v20, (unsigned __int64)*v17 >> ((v17[2] & 1) == 0), v38);
          v23 = v17[2];
          if ( (v23 & 2) != 0
            && ((v23 & 7) != 7 || SString::s_IsANSIMultibyte)
            && !(unsigned int)SString::ScanASCII((SString *)v17) )
          {
            SString::ConvertToUnicode((SString *)v17);
          }
          wcscpy_s(&v20[(*v17 >> ((v17[2] & 1) == 0)) - 1], v7 + 1, L"\\");
          v24 = v17[2];
          if ( (v24 & 2) != 0
            && ((v24 & 7) != 7 || SString::s_IsANSIMultibyte)
            && !(unsigned int)SString::ScanASCII((SString *)v17) )
          {
            SString::ConvertToUnicode((SString *)v17);
          }
          v25 = &v20[*v17 >> ((v17[2] & 1) == 0)];
        }
        wcscpy_s(v25, v7 + 1, *((const wchar_t **)v4 + 6));
        ResourceFile = ((int (__stdcall *)(CCompRC *, HINSTANCE *, const unsigned __int16 *))CCompRC::LoadResourceFile)(
                         v4,
                         v36,
                         Destination);
        if ( ResourceFile >= 0 )
          goto LABEL_54;
      }
      ++i;
    }
    if ( ResourceFile < 0 )
      ResourceFile = ((int (__stdcall *)(CCompRC *, HINSTANCE *, const unsigned __int16 *))CCompRC::LoadResourceFile)(
                       v4,
                       v36,
                       *((const unsigned __int16 **)v4 + 6));
LABEL_54:
    StringArrayList::~StringArrayList((StringArrayList *)&v45);
    return (unsigned int)ResourceFile;
  }
}

```

## disassembly

```asm
0x14001281c  push    rbx
0x14001281e  push    rsi
0x14001281f  push    rdi
0x140012820  push    r12
0x140012822  push    r13
0x140012824  push    r14
0x140012826  push    r15
0x140012828  sub     rsp, 340h
0x14001282f  mov     rax, cs:__security_cookie
0x140012836  xor     rax, rsp
0x140012839  mov     [rsp+378h+var_48], rax
0x140012841  mov     r13, r8
0x140012844  mov     [rsp+378h+Destination], r8
0x140012849  mov     [rsp+378h+var_310], rdx
0x14001284e  mov     r14, rcx
0x140012851  mov     [rsp+378h+var_2B8], rcx
0x140012859  mov     [rsp+378h+var_2E8], rdx
0x140012861  mov     [rsp+378h+var_2F8], r8
0x140012869  mov     ebx, 80004005h
0x14001286e  mov     rax, [rcx+30h]
0x140012872  or      r12, 0FFFFFFFFFFFFFFFFh
0x140012876  mov     r15, r12
0x140012879  xor     edi, edi
0x14001287b  inc     r15
0x14001287e  cmp     [rax+r15*2], di
0x140012883  jnz     short loc_14001287B
0x140012885  mov     [rsp+378h+var_320], r15
0x14001288a  call    ?Startup@SString@@SAXXZ; SString::Startup(void)
0x14001288f  mov     [rsp+378h+var_2A8], edi
0x140012896  mov     [rsp+378h+var_2A0], rdi
0x14001289e  mov     [rsp+378h+var_298], 5
0x1400128a9  mov     rax, [r14+40h]
0x1400128ad  test    rax, rax
0x1400128b0  jz      short loc_1400128C7
0x1400128b2  lea     rcx, [rsp+378h+var_2A8]
0x1400128ba  call    cs:__guard_dispatch_icall_fptr
0x1400128c0  mov     ebx, eax
0x1400128c2  jmp     loc_14001294C
0x1400128c7  mov     esi, edi
0x1400128c9  mov     [rsp+378h+var_2E0], edi
0x1400128d0  mov     [rsp+378h+var_2D8], rdi
0x1400128d8  lea     rax, [rsp+378h+var_2E0]
0x1400128e0  mov     [rsp+378h+var_328], rax
0x1400128e5  mov     rdx, cs:?s_Empty@SString@@0PEAV1@EA; struct SString *
0x1400128ec  lea     rcx, [rsp+378h+var_2A8]; this
0x1400128f4  call    ?Append@StringArrayList@@QEAAXAEBVSString@@@Z; StringArrayList::Append(SString const &)
0x1400128f9  nop
0x1400128fa  jmp     short loc_140012934
0x1400128fc  or      r12, 0FFFFFFFFFFFFFFFFh
0x140012900  xor     edi, edi
0x140012902  mov     ebx, dword ptr [rsp+378h+var_328]
0x140012906  mov     r15, [rsp+378h+var_320]
0x14001290b  mov     esi, [rsp+378h+var_2E0]
0x140012912  mov     r14, [rsp+378h+var_2B8]
0x14001291a  mov     r13, [rsp+378h+var_2F8]
0x140012922  mov     [rsp+378h+Destination], r13
0x140012927  mov     rax, [rsp+378h+var_2E8]
0x14001292f  mov     [rsp+378h+var_310], rax
0x140012934  test    sil, 2
0x140012938  jz      short loc_14001294C
0x14001293a  mov     rax, cs:?g_fpHandleStackOverflowAfterCatch@@3P6AXXZEA; void (*g_fpHandleStackOverflowAfterCatch)(void)
0x140012941  test    rax, rax
0x140012944  jz      short loc_14001294C
0x140012946  call    cs:__guard_dispatch_icall_fptr
0x14001294c  mov     esi, 8007000Eh
0x140012951  cmp     ebx, esi
0x140012953  jnz     short loc_140012969
0x140012955  lea     rcx, [rsp+378h+var_2A8]; this
0x14001295d  call    ??1StringArrayList@@QEAA@XZ; StringArrayList::~StringArrayList(void)
0x140012962  mov     eax, esi
0x140012964  jmp     loc_140012C5E
0x140012969  mov     [rsp+378h+var_258], di
0x140012971  mov     [rsp+378h+Source], di
0x140012979  mov     [r13+206h], di
0x140012981  lea     r9, [rsp+378h+var_258]; unsigned __int16 *
0x140012989  lea     rdx, [rsp+378h+Source]; unsigned __int16 *
0x140012991  mov     rcx, r13; unsigned __int16 *
0x140012994  call    ?SplitPath@@YAXPEBGPEAGH1H1_K12@Z; SplitPath(ushort const *,ushort *,int,ushort *,int,ushort *,unsigned __int64,ushort *,unsigned __int64)
0x140012999  lea     rax, [rsp+378h+Source]
0x1400129a1  mov     r8, r12
0x1400129a4  inc     r8
0x1400129a7  cmp     [rax+r8*2], di
0x1400129ac  jnz     short loc_1400129A4
0x1400129ae  mov     [rsp+378h+var_328], r8
0x1400129b3  lea     rax, [rsp+378h+var_258]
0x1400129bb  inc     r12
0x1400129be  cmp     [rax+r12*2], di
0x1400129c3  jnz     short loc_1400129BB
0x1400129c5  lea     rax, [r8+1]
0x1400129c9  add     rax, r12
0x1400129cc  add     rax, r15
0x1400129cf  mov     [rsp+378h+var_2E8], rax
0x1400129d7  mov     r13d, edi
0x1400129da  cmp     [rsp+378h+var_2A8], edi
0x1400129e1  jbe     loc_140012C38
0x1400129e7  mov     ecx, r13d
0x1400129ea  lea     rsi, [rsp+378h+var_2A0]
0x1400129f2  mov     eax, [rsp+378h+var_298]
0x1400129f9  cmp     r13d, eax
0x1400129fc  jb      short loc_140012A0A
0x1400129fe  sub     ecx, eax
0x140012a00  mov     rsi, [rsi]
0x140012a03  mov     eax, [rsi+8]
0x140012a06  cmp     ecx, eax
0x140012a08  jnb     short loc_1400129FE
0x140012a0a  mov     eax, ecx
0x140012a0c  mov     rsi, [rsi+rax*8+10h]
0x140012a11  mov     eax, [rsi+8]
0x140012a14  test    al, 2
0x140012a16  jz      short loc_140012A40
0x140012a18  and     eax, 7
0x140012a1b  cmp     al, 7
0x140012a1d  jnz     short loc_140012A27
0x140012a1f  cmp     cs:?s_IsANSIMultibyte@SString@@0HA, edi; int SString::s_IsANSIMultibyte
0x140012a25  jz      short loc_140012A40
0x140012a27  mov     rcx, rsi; this
0x140012a2a  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x140012a2f  test    eax, eax
0x140012a31  jnz     short loc_140012A3B
0x140012a33  mov     rcx, rsi; this
0x140012a36  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x140012a3b  mov     r8, [rsp+378h+var_328]
0x140012a40  mov     ecx, [rsi+8]
0x140012a43  not     ecx
0x140012a45  and     ecx, 1
0x140012a48  mov     eax, [rsi]
0x140012a4a  shr     eax, cl
0x140012a4c  dec     eax
0x140012a4e  add     rax, [rsp+378h+var_2E8]
0x140012a56  cmp     rax, 104h
0x140012a5c  ja      loc_140012C1D
0x140012a62  lea     rdx, [r8+1]; SizeInWords
0x140012a66  lea     r8, [rsp+378h+Source]; Source
0x140012a6e  mov     rbx, [rsp+378h+Destination]
0x140012a73  mov     rcx, rbx; Destination
0x140012a76  call    cs:__imp_wcscpy_s
0x140012a7c  mov     rax, [rsp+378h+var_328]
0x140012a81  lea     rbx, [rbx+rax*2]
0x140012a85  lea     rdx, [r12+1]; SizeInWords
0x140012a8a  lea     r8, [rsp+378h+var_258]; Source
0x140012a92  mov     rcx, rbx; Destination
0x140012a95  call    cs:__imp_wcscpy_s
0x140012a9b  lea     rbx, [rbx+r12*2]
0x140012a9f  mov     [rsp+378h+var_320], rbx
0x140012aa4  mov     edx, [rsi+8]
0x140012aa7  mov     ecx, edx
0x140012aa9  not     ecx
0x140012aab  and     ecx, 1
0x140012aae  mov     eax, [rsi]
0x140012ab0  shr     eax, cl
0x140012ab2  cmp     eax, 1
0x140012ab5  jz      loc_140012BB7
0x140012abb  mov     rcx, rsi; this
0x140012abe  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x140012ac3  mov     rax, [rsi+10h]
0x140012ac7  mov     [rsp+378h+var_2F8], rax
0x140012acf  mov     eax, [rsi+8]
0x140012ad2  mov     bl, 2
0x140012ad4  test    bl, al
0x140012ad6  jz      short loc_140012AFB
0x140012ad8  and     eax, 7
0x140012adb  cmp     al, 7
0x140012add  jnz     short loc_140012AE7
0x140012adf  cmp     cs:?s_IsANSIMultibyte@SString@@0HA, edi; int SString::s_IsANSIMultibyte
0x140012ae5  jz      short loc_140012AFB
0x140012ae7  mov     rcx, rsi; this
0x140012aea  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x140012aef  test    eax, eax
0x140012af1  jnz     short loc_140012AFB
0x140012af3  mov     rcx, rsi; this
0x140012af6  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x140012afb  mov     ecx, [rsi+8]
0x140012afe  not     ecx
0x140012b00  and     cl, 1
0x140012b03  mov     edx, [rsi]
0x140012b05  shr     rdx, cl; SizeInWords
0x140012b08  mov     r8, [rsp+378h+var_2F8]; Source
0x140012b10  mov     rcx, [rsp+378h+var_320]; Destination
0x140012b15  call    cs:__imp_wcscpy_s
0x140012b1b  mov     eax, [rsi+8]
0x140012b1e  test    bl, al
0x140012b20  jz      short loc_140012B45
0x140012b22  and     eax, 7
0x140012b25  cmp     al, 7
0x140012b27  jnz     short loc_140012B31
0x140012b29  cmp     cs:?s_IsANSIMultibyte@SString@@0HA, edi; int SString::s_IsANSIMultibyte
0x140012b2f  jz      short loc_140012B45
0x140012b31  mov     rcx, rsi; this
0x140012b34  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x140012b39  test    eax, eax
0x140012b3b  jnz     short loc_140012B45
0x140012b3d  mov     rcx, rsi; this
0x140012b40  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x140012b45  mov     ecx, [rsi+8]
0x140012b48  not     ecx
0x140012b4a  and     ecx, 1
0x140012b4d  mov     edx, [rsi]
0x140012b4f  shr     edx, cl
0x140012b51  dec     edx
0x140012b53  mov     rcx, [rsp+378h+var_320]
0x140012b58  lea     rcx, [rcx+rdx*2]; Destination
0x140012b5c  lea     r8, asc_14001F158; "\\"
0x140012b63  lea     rdx, [r15+1]; SizeInWords
0x140012b67  call    cs:__imp_wcscpy_s
0x140012b6d  mov     eax, [rsi+8]
0x140012b70  test    bl, al
0x140012b72  jz      short loc_140012B97
0x140012b74  and     eax, 7
0x140012b77  cmp     al, 7
0x140012b79  jnz     short loc_140012B83
0x140012b7b  cmp     cs:?s_IsANSIMultibyte@SString@@0HA, edi; int SString::s_IsANSIMultibyte
0x140012b81  jz      short loc_140012B97
0x140012b83  mov     rcx, rsi; this
0x140012b86  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x140012b8b  test    eax, eax
0x140012b8d  jnz     short loc_140012B97
0x140012b8f  mov     rcx, rsi; this
0x140012b92  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x140012b97  mov     ecx, [rsi+8]
0x140012b9a  not     ecx
0x140012b9c  and     ecx, 1
0x140012b9f  mov     r8d, [rsi]
0x140012ba2  shr     r8d, cl
0x140012ba5  dec     r8d
0x140012ba8  mov     rcx, [rsp+378h+var_320]
0x140012bad  lea     rcx, [rcx+r8*2]
0x140012bb1  add     rcx, 2
0x140012bb5  jmp     short loc_140012BF5
0x140012bb7  test    dl, 2
0x140012bba  jz      short loc_140012BE0
0x140012bbc  and     edx, 7
0x140012bbf  cmp     dl, 7
0x140012bc2  jnz     short loc_140012BCC
0x140012bc4  cmp     cs:?s_IsANSIMultibyte@SString@@0HA, edi; int SString::s_IsANSIMultibyte
0x140012bca  jz      short loc_140012BE0
0x140012bcc  mov     rcx, rsi; this
0x140012bcf  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x140012bd4  test    eax, eax
0x140012bd6  jnz     short loc_140012BE0
0x140012bd8  mov     rcx, rsi; this
0x140012bdb  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x140012be0  mov     ecx, [rsi+8]
0x140012be3  not     ecx
0x140012be5  and     ecx, 1
0x140012be8  mov     r8d, [rsi]
0x140012beb  shr     r8d, cl
0x140012bee  dec     r8d
0x140012bf1  lea     rcx, [rbx+r8*2]; Destination
0x140012bf5  mov     r8, [r14+30h]; Source
0x140012bf9  lea     rdx, [r15+1]; SizeInWords
0x140012bfd  call    cs:__imp_wcscpy_s
0x140012c03  mov     r8, [rsp+378h+Destination]; unsigned __int16 *
0x140012c08  mov     rdx, [rsp+378h+var_310]; HINSTANCE *
0x140012c0d  mov     rcx, r14; this
0x140012c10  call    ?LoadResourceFile@CCompRC@@AEAAJPEAPEAUHINSTANCE__@@PEBG@Z; CCompRC::LoadResourceFile(HINSTANCE__ * *,ushort const *)
0x140012c15  mov     ebx, eax
0x140012c17  test    eax, eax
0x140012c19  jns     short loc_140012C4F
0x140012c1b  jmp     short loc_140012C22
0x140012c1d  mov     ebx, 80004005h
0x140012c22  inc     r13d
0x140012c25  cmp     r13d, [rsp+378h+var_2A8]
0x140012c2d  mov     r8, [rsp+378h+var_328]
0x140012c32  jb      loc_1400129E7
0x140012c38  test    ebx, ebx
0x140012c3a  jns     short loc_140012C4F
0x140012c3c  mov     r8, [r14+30h]; unsigned __int16 *
0x140012c40  mov     rdx, [rsp+378h+var_310]; HINSTANCE *
0x140012c45  mov     rcx, r14; this
0x140012c48  call    ?LoadResourceFile@CCompRC@@AEAAJPEAPEAUHINSTANCE__@@PEBG@Z; CCompRC::LoadResourceFile(HINSTANCE__ * *,ushort const *)
0x140012c4d  mov     ebx, eax
0x140012c4f  lea     rcx, [rsp+378h+var_2A8]; this
0x140012c57  call    ??1StringArrayList@@QEAA@XZ; StringArrayList::~StringArrayList(void)
0x140012c5c  mov     eax, ebx
0x140012c5e  mov     rcx, [rsp+378h+var_48]
0x140012c66  xor     rcx, rsp; StackCookie
0x140012c69  call    __security_check_cookie
0x140012c6e  add     rsp, 340h
0x140012c75  pop     r15
0x140012c77  pop     r14
0x140012c79  pop     r13
0x140012c7b  pop     r12
0x140012c7d  pop     rdi
0x140012c7e  pop     rsi
0x140012c7f  pop     rbx
0x140012c80  retn
```
