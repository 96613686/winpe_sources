# CSAMIRead::Info(long,_AMMediaType * *,ulong *,ulong *,ulong *,ushort * *,IUnknown * *,IUnknown * *)

- ea: `0x180123f20`
- end: `0x18012423c`
- name: `?Info@CSAMIRead@@EEAAJJPEAPEAU_AMMediaType@@PEAK11PEAPEAGPEAPEAUIUnknown@@3@Z`
- size: `796`
- prototype: `__int64 __fastcall(CSAMIRead *__hidden this, int, struct _AMMediaType **, unsigned int *, unsigned int *, unsigned int *, unsigned __int16 **, struct IUnknown **, struct IUnknown **)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, loader_planting`

## callees

- `0x1800135b0`
- `0x18002f03c`
- `0x180038498`
- `0x1800384a4`
- `0x18005cc50`
- `0x180123d2c`
- `0x180123f20`
- `0x180125a60`
- `0x18015bb98`
- `0x18015e010`

## import_xrefs

- `KERNEL32!SetErrorMode` at `0x18012406f`
- `KERNEL32!SetErrorMode` at `0x18012409d`
- `KERNEL32!SetErrorMode` at `0x18012406f`
- `KERNEL32!SetErrorMode` at `0x18012409d`
- `KERNEL32!LoadLibraryExW` at `0x18012408c`
- `KERNEL32!LoadLibraryExW` at `0x18012408c`
- `KERNEL32!FreeLibrary` at `0x180124111`
- `KERNEL32!FreeLibrary` at `0x180124111`
- `KERNEL32!LeaveCriticalSection` at `0x180124212`
- `KERNEL32!LeaveCriticalSection` at `0x180124212`
- `KERNEL32!EnterCriticalSection` at `0x180123f4e`
- `KERNEL32!EnterCriticalSection` at `0x180123f4e`
- `KERNEL32!GetProcAddress` at `0x1801240b8`
- `KERNEL32!GetProcAddress` at `0x1801240b8`

## string_xrefs

- `0x18012407d`: `MLANG.DLL`

## pseudocode

```c
__int64 __fastcall CSAMIRead::Info(
        CSAMIRead *this,
        int a2,
        struct _AMMediaType **a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned int *a6,
        unsigned __int16 **a7,
        struct IUnknown **a8,
        struct IUnknown **a9)
{
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  __int64 v14; // rax
  CBaseList *v15; // rcx
  ULONG v16; // r8d
  void *v17; // rcx
  ULONG v18; // esi
  void *v19; // rax
  void *v20; // r13
  unsigned int *v21; // r14
  char *v22; // rcx
  UINT v23; // edi
  HMODULE Library; // r15
  size_t v25; // rdi
  _BYTE *v26; // rax
  _BYTE *v27; // r12
  struct __POSITION *v28; // rax
  unsigned __int16 **v29; // rdi
  char *v30; // rcx
  int v31; // edi
  void *NextI; // rax
  __int64 v33; // r9
  void *Src; // [rsp+20h] [rbp-69h] BYREF
  struct __POSITION *ProcAddress; // [rsp+28h] [rbp-61h] BYREF
  struct _AMMediaType v37; // [rsp+30h] [rbp-59h] BYREF
  __int64 v38; // [rsp+D0h] [rbp+47h]
  int v39; // [rsp+D8h] [rbp+4Fh] BYREF

  v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v14 = (*(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)this - 112) + 56LL))((char *)this - 896, 0);
  v15 = (CBaseList *)*((unsigned int *)this + 246);
  v38 = v14;
  v16 = 1;
  if ( a2 >= (int)v15 )
  {
    v31 = a2 - (_DWORD)v15;
    ProcAddress = (struct __POSITION *)*((_QWORD *)this + 126);
    if ( v31 >= 0 )
    {
      v18 = 0;
      do
      {
        NextI = CBaseList::GetNextI(v15, &ProcAddress);
        v31 -= v16;
      }
      while ( v31 >= 0 );
      if ( NextI )
      {
        if ( a4 )
          *a4 = NextI == *((void **)this + 137);
        if ( a9 )
          *a9 = 0;
        if ( a6 )
          *a6 = v16;
        if ( a3 )
          *a3 = 0;
        if ( a5 )
          *a5 = 0;
        v29 = a7;
        if ( !a7 )
          goto LABEL_41;
        *a7 = 0;
        v30 = (char *)*((_QWORD *)NextI + 1);
        goto LABEL_38;
      }
    }
LABEL_43:
    v18 = v16;
    goto LABEL_44;
  }
  v17 = (void *)*((_QWORD *)this + 121);
  v18 = 0;
  Src = v17;
  if ( a2 < 0 )
    goto LABEL_43;
  do
  {
    v19 = CBaseList::GetNextI((CBaseList *)v17, (struct __POSITION **)&Src);
    a2 -= v16;
    v20 = v19;
  }
  while ( a2 >= 0 );
  if ( !v19 )
    goto LABEL_43;
  if ( a4 )
    *a4 = v19 == *((void **)this + 136);
  if ( a9 )
    *a9 = 0;
  if ( a6 )
    *a6 = 0;
  if ( a3 )
  {
    v37.lSampleSize = v16;
    memset(&v37.subtype, 0, 24);
    v37.majortype = MEDIATYPE_Text;
    memset(&v37.formattype, 0, 44);
    *a3 = CreateMediaType(&v37);
    FreeMediaType(&v37);
  }
  v21 = a5;
  if ( a5 )
  {
    *a5 = 0;
    v22 = (char *)*((_QWORD *)v20 + 1);
    Src = 0;
    v39 = 0;
    if ( FindValueInStyle(v22, "lang", (char **)&Src, &v39) )
    {
      v23 = SetErrorMode(0x8000u);
      Library = LoadLibraryExW(L"MLANG.DLL", 0, 0x800u);
      SetErrorMode(v23);
      if ( Library )
      {
        ProcAddress = (struct __POSITION *)GetProcAddress(Library, "Rfc1766ToLcidA");
        if ( ProcAddress )
        {
          v25 = v39;
          v26 = operator new[](v39 + 1);
          v27 = v26;
          if ( v26 )
          {
            memcpy_0(v26, Src, v25);
            v28 = ProcAddress;
            v27[v25] = 0;
            ((void (__fastcall *)(unsigned int *, _BYTE *))v28)(v21, v27);
            operator delete(v27);
          }
        }
        FreeLibrary(Library);
      }
    }
  }
  v29 = a7;
  if ( !a7 )
    goto LABEL_40;
  *a7 = 0;
  v30 = (char *)*((_QWORD *)v20 + 1);
LABEL_38:
  Src = 0;
  v39 = 0;
  if ( FindValueInStyle(v30, "name", (char **)&Src, &v39) )
    WSTRFromAnsi(v29, (const char *)Src, v39);
LABEL_40:
  v33 = v38;
LABEL_41:
  if ( a8 )
    (**(void (__fastcall ***)(__int64, GUID *))(v33 + 24))(v33 + 24, &IID_IUnknown);
LABEL_44:
  LeaveCriticalSection(v9);
  return v18;
}

```

## disassembly

```asm
0x180123f20  mov     [rsp-8+arg_10], rbx
0x180123f25  push    rbp
0x180123f26  push    rsi
0x180123f27  push    rdi
0x180123f28  push    r12
0x180123f2a  push    r13
0x180123f2c  push    r14
0x180123f2e  push    r15
0x180123f30  lea     rbp, [rsp-7]
0x180123f35  sub     rsp, 90h
0x180123f3c  lea     rbx, [rcx+8]
0x180123f40  mov     r14, rcx
0x180123f43  mov     rcx, rbx; lpCriticalSection
0x180123f46  mov     r15, r9
0x180123f49  mov     r12, r8
0x180123f4c  mov     edi, edx
0x180123f4e  call    cs:__imp_EnterCriticalSection
0x180123f55  nop     dword ptr [rax+rax+00h]
0x180123f5a  lea     rcx, [r14-380h]
0x180123f61  xor     edx, edx
0x180123f63  mov     rax, [rcx]
0x180123f66  mov     rax, [rax+38h]
0x180123f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180123f6f  mov     ecx, [r14+3D8h]; this
0x180123f76  mov     r9, rax
0x180123f79  mov     [rbp+37h+arg_0], rax
0x180123f7d  mov     r8d, 1
0x180123f83  cmp     edi, ecx
0x180123f85  jge     loc_180124136
0x180123f8b  mov     rcx, [r14+3C8h]; this
0x180123f92  xor     esi, esi
0x180123f94  mov     [rbp+37h+Src], rcx
0x180123f98  test    edi, edi
0x180123f9a  js      loc_18012420C
0x180123fa0  lea     rdx, [rbp+37h+Src]; struct __POSITION **
0x180123fa4  call    ?GetNextI@CBaseList@@IEBAPEAXAEAPEAU__POSITION@@@Z; CBaseList::GetNextI(__POSITION * &)
0x180123fa9  sub     edi, r8d
0x180123fac  mov     r13, rax
0x180123faf  jns     short loc_180123FA0
0x180123fb1  test    rax, rax
0x180123fb4  jz      loc_18012420C
0x180123fba  test    r15, r15
0x180123fbd  jz      short loc_180123FCE
0x180123fbf  cmp     rax, [r14+440h]
0x180123fc6  mov     ecx, esi
0x180123fc8  setz    cl
0x180123fcb  mov     [r15], ecx
0x180123fce  mov     rax, [rbp+37h+arg_40]
0x180123fd5  test    rax, rax
0x180123fd8  jz      short loc_180123FDD
0x180123fda  mov     [rax], rsi
0x180123fdd  mov     rax, [rbp+37h+arg_28]
0x180123fe1  test    rax, rax
0x180123fe4  jz      short loc_180123FE8
0x180123fe6  mov     [rax], esi
0x180123fe8  test    r12, r12
0x180123feb  jz      short loc_180124033
0x180123fed  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x180123ff4  mov     [rbp+37h+var_90.lSampleSize], r8d
0x180123ff8  lea     rcx, [rbp+37h+var_90]; struct _AMMediaType *
0x180123ffc  xorps   xmm0, xmm0
0x180123fff  mov     qword ptr [rbp+37h+var_90.bFixedSizeSamples], rsi
0x180124003  movups  xmmword ptr [rbp+37h+var_90+3Ch], xmm0
0x180124007  movups  xmmword ptr [rbp+37h+var_90.cbFormat], xmm0
0x18012400b  movups  xmm0, xmmword ptr cs:MEDIATYPE_Text.Data1
0x180124012  movdqu  xmmword ptr [rbp+37h+var_90.subtype.Data1], xmm1
0x180124017  movdqu  xmmword ptr [rbp+37h+var_90.majortype.Data1], xmm0
0x18012401c  movdqu  xmmword ptr [rbp+37h+var_90.formattype.Data1], xmm1
0x180124021  call    ?CreateMediaType@@YAPEAU_AMMediaType@@PEBU1@@Z; CreateMediaType(_AMMediaType const *)
0x180124026  lea     rcx, [rbp+37h+var_90]; struct _AMMediaType *
0x18012402a  mov     [r12], rax
0x18012402e  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x180124033  mov     r14, [rbp+37h+arg_20]
0x180124037  test    r14, r14
0x18012403a  jz      loc_18012411D
0x180124040  mov     [r14], esi
0x180124043  lea     r9, [rbp+37h+arg_8]; int *
0x180124047  mov     rcx, [r13+8]; char *
0x18012404b  lea     r8, [rbp+37h+Src]; char **
0x18012404f  lea     rdx, aLang; "lang"
0x180124056  mov     [rbp+37h+Src], rsi
0x18012405a  mov     [rbp+37h+arg_8], esi
0x18012405d  call    ?FindValueInStyle@@YAHPEAD0AEAPEADAEAH@Z; FindValueInStyle(char *,char *,char * &,int &)
0x180124062  test    eax, eax
0x180124064  jz      loc_18012411D
0x18012406a  mov     ecx, 8000h; uMode
0x18012406f  call    cs:__imp_SetErrorMode
0x180124076  nop     dword ptr [rax+rax+00h]
0x18012407b  xor     edx, edx; hFile
0x18012407d  lea     rcx, aMlangDll; "MLANG.DLL"
0x180124084  mov     r8d, 800h; dwFlags
0x18012408a  mov     edi, eax
0x18012408c  call    cs:__imp_LoadLibraryExW
0x180124093  nop     dword ptr [rax+rax+00h]
0x180124098  mov     ecx, edi; uMode
0x18012409a  mov     r15, rax
0x18012409d  call    cs:__imp_SetErrorMode
0x1801240a4  nop     dword ptr [rax+rax+00h]
0x1801240a9  test    r15, r15
0x1801240ac  jz      short loc_18012411D
0x1801240ae  lea     rdx, aRfc1766tolcida; "Rfc1766ToLcidA"
0x1801240b5  mov     rcx, r15; hModule
0x1801240b8  call    cs:__imp_GetProcAddress
0x1801240bf  nop     dword ptr [rax+rax+00h]
0x1801240c4  mov     [rbp+37h+var_98], rax
0x1801240c8  test    rax, rax
0x1801240cb  jz      short loc_18012410E
0x1801240cd  movsxd  rdi, [rbp+37h+arg_8]
0x1801240d1  lea     ecx, [rdi+1]
0x1801240d4  movsxd  rcx, ecx; unsigned __int64
0x1801240d7  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1801240dc  mov     r12, rax
0x1801240df  test    rax, rax
0x1801240e2  jz      short loc_18012410E
0x1801240e4  mov     rdx, [rbp+37h+Src]; Src
0x1801240e8  mov     r8, rdi; Size
0x1801240eb  mov     rcx, rax; void *
0x1801240ee  call    memcpy_0
0x1801240f3  mov     rax, [rbp+37h+var_98]
0x1801240f7  mov     rdx, r12
0x1801240fa  mov     rcx, r14
0x1801240fd  mov     [rdi+r12], sil
0x180124101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180124106  mov     rcx, r12; Block
0x180124109  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18012410e  mov     rcx, r15; hLibModule
0x180124111  call    cs:__imp_FreeLibrary
0x180124118  nop     dword ptr [rax+rax+00h]
0x18012411d  mov     rdi, [rbp+37h+arg_30]
0x180124121  test    rdi, rdi
0x180124124  jz      loc_1801241E7
0x18012412a  mov     [rdi], rsi
0x18012412d  mov     rcx, [r13+8]
0x180124131  jmp     loc_1801241B8
0x180124136  sub     edi, ecx
0x180124138  mov     rax, [r14+3F0h]
0x18012413f  mov     [rbp+37h+var_98], rax
0x180124143  js      loc_18012420C
0x180124149  xor     esi, esi
0x18012414b  lea     rdx, [rbp+37h+var_98]; struct __POSITION **
0x18012414f  call    ?GetNextI@CBaseList@@IEBAPEAXAEAPEAU__POSITION@@@Z; CBaseList::GetNextI(__POSITION * &)
0x180124154  sub     edi, r8d
0x180124157  mov     r10, rax
0x18012415a  jns     short loc_18012414B
0x18012415c  test    rax, rax
0x18012415f  jz      loc_18012420C
0x180124165  test    r15, r15
0x180124168  jz      short loc_180124179
0x18012416a  cmp     rax, [r14+448h]
0x180124171  mov     ecx, esi
0x180124173  setz    cl
0x180124176  mov     [r15], ecx
0x180124179  mov     rax, [rbp+37h+arg_40]
0x180124180  test    rax, rax
0x180124183  jz      short loc_180124188
0x180124185  mov     [rax], rsi
0x180124188  mov     rax, [rbp+37h+arg_28]
0x18012418c  test    rax, rax
0x18012418f  jz      short loc_180124194
0x180124191  mov     [rax], r8d
0x180124194  test    r12, r12
0x180124197  jz      short loc_18012419D
0x180124199  mov     [r12], rsi
0x18012419d  mov     rax, [rbp+37h+arg_20]
0x1801241a1  test    rax, rax
0x1801241a4  jz      short loc_1801241A8
0x1801241a6  mov     [rax], esi
0x1801241a8  mov     rdi, [rbp+37h+arg_30]
0x1801241ac  test    rdi, rdi
0x1801241af  jz      short loc_1801241EB
0x1801241b1  mov     [rdi], rsi
0x1801241b4  mov     rcx, [r10+8]; char *
0x1801241b8  lea     r9, [rbp+37h+arg_8]; int *
0x1801241bc  mov     [rbp+37h+Src], rsi
0x1801241c0  lea     r8, [rbp+37h+Src]; char **
0x1801241c4  mov     [rbp+37h+arg_8], esi
0x1801241c7  lea     rdx, aName; "name"
0x1801241ce  call    ?FindValueInStyle@@YAHPEAD0AEAPEADAEAH@Z; FindValueInStyle(char *,char *,char * &,int &)
0x1801241d3  test    eax, eax
0x1801241d5  jz      short loc_1801241E7
0x1801241d7  mov     r8d, [rbp+37h+arg_8]; int
0x1801241db  mov     rcx, rdi; unsigned __int16 **
0x1801241de  mov     rdx, [rbp+37h+Src]; char *
0x1801241e2  call    ?WSTRFromAnsi@@YAJPEAPEAGPEBDH@Z; WSTRFromAnsi(ushort * *,char const *,int)
0x1801241e7  mov     r9, [rbp+37h+arg_0]
0x1801241eb  mov     r8, [rbp+37h+arg_38]
0x1801241ef  test    r8, r8
0x1801241f2  jz      short loc_18012420F
0x1801241f4  lea     rcx, [r9+18h]
0x1801241f8  mov     rax, [rcx]
0x1801241fb  lea     rdx, IID_IUnknown
0x180124202  mov     rax, [rax]
0x180124205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012420a  jmp     short loc_18012420F
0x18012420c  mov     esi, r8d
0x18012420f  mov     rcx, rbx; lpCriticalSection
0x180124212  call    cs:__imp_LeaveCriticalSection
0x180124219  nop     dword ptr [rax+rax+00h]
0x18012421e  mov     rbx, [rsp+0C0h+arg_10]
0x180124226  mov     eax, esi
0x180124228  add     rsp, 90h
0x18012422f  pop     r15
0x180124231  pop     r14
0x180124233  pop     r13
0x180124235  pop     r12
0x180124237  pop     rdi
0x180124238  pop     rsi
0x180124239  pop     rbp
0x18012423a  retn
```
