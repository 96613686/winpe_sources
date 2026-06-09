# RadiusExtension::Load(ushort const *)

- ea: `0x180014608`
- end: `0x1800148a9`
- name: `?Load@RadiusExtension@@QEAAKPEBG@Z`
- size: `673`
- prototype: `unsigned int(RadiusExtension *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18001224c`

## callees

- `0x18000342c`
- `0x18000c4a4`
- `0x18000c500`
- `0x18000e754`
- `0x1800145b0`
- `0x180014608`
- `0x1800254a0`
- `0x18002e010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1800146b8`
- `msvcrt!wcscpy_s` at `0x1800146b8`
- `KERNEL32!GetLastError` at `0x1800146d0`
- `KERNEL32!GetLastError` at `0x1800146d0`
- `KERNEL32!GetProcAddress` at `0x18001472f`
- `KERNEL32!GetProcAddress` at `0x180014744`
- `KERNEL32!GetProcAddress` at `0x180014759`
- `KERNEL32!GetProcAddress` at `0x18001476e`
- `KERNEL32!GetProcAddress` at `0x180014783`
- `KERNEL32!GetProcAddress` at `0x180014798`
- `KERNEL32!GetProcAddress` at `0x18001472f`
- `KERNEL32!GetProcAddress` at `0x180014744`
- `KERNEL32!GetProcAddress` at `0x180014759`
- `KERNEL32!GetProcAddress` at `0x18001476e`
- `KERNEL32!GetProcAddress` at `0x180014783`
- `KERNEL32!GetProcAddress` at `0x180014798`
- `KERNEL32!LoadLibraryW` at `0x1800146c1`
- `KERNEL32!LoadLibraryW` at `0x1800146c1`

## string_xrefs

- `0x18001463a`: `Loading extension %S`
- `0x1800146f2`: `LoadLibraryW failed with error: %d`
- `0x180014725`: `RadiusExtensionInit`
- `0x180014739`: `RadiusExtensionTerm`
- `0x18001474e`: `RadiusExtensionProcess`
- `0x180014763`: `RadiusExtensionProcessEx`
- `0x180014778`: `RadiusExtensionFreeAttributes`
- `0x18001478d`: `RadiusExtensionProcess2`
- `0x1800147cb`: `Either RadiusExtensionProcess, RadiusExtensionProcessEx, or RadiusExtensionProcess2 must be defined.`
- `0x180014802`: `RadiusExtensionFreeAttributes must be defined if RadiusExtensionProcessEx is defined.`
- `0x180014866`: `RadiusExtensionInit failed with error: %d`

## pseudocode

```c
__int64 __fastcall RadiusExtension::Load(RadiusExtension *this, const unsigned __int16 *a2)
{
  int v4; // r9d
  const wchar_t *FileNameFromPath; // rsi
  __int64 v6; // rax
  unsigned __int64 v7; // rbp
  unsigned __int128 v8; // rax
  wchar_t *v9; // rax
  HMODULE LibraryW; // rax
  DWORD LastError; // ebx
  FARPROC ProcAddress; // rax
  __int64 v14; // rdx
  __int64 (*v15)(void); // rax
  unsigned int v16; // edi

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("Loading extension %S");
    WPP_SF_sS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)WPP_b461da539d613e66bfc4a53e3ac78614_Traceguids,
      v4,
      (__int64)a2);
  }
  FileNameFromPath = ExtractFileNameFromPath(a2);
  v6 = -1;
  do
    ++v6;
  while ( FileNameFromPath[v6] );
  v7 = (unsigned int)(v6 + 1);
  v8 = (unsigned int)(v6 + 1) * (unsigned __int128)2uLL;
  if ( !is_mul_ok(v7, 2u) )
    *(_QWORD *)&v8 = -1;
  v9 = (wchar_t *)operator new[](v8, *((const struct std::nothrow_t **)&v8 + 1));
  *(_QWORD *)this = v9;
  if ( !v9 )
    return 8;
  wcscpy_s(v9, v7, FileNameFromPath);
  LibraryW = LoadLibraryW(a2);
  *((_QWORD *)this + 1) = LibraryW;
  if ( !LibraryW )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("LoadLibraryW failed with error: %d");
      WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_b461da539d613e66bfc4a53e3ac78614_Traceguids);
    }
    return LastError;
  }
  *((_QWORD *)this + 3) = GetProcAddress(LibraryW, "RadiusExtensionInit");
  *((_QWORD *)this + 4) = GetProcAddress(*((HMODULE *)this + 1), "RadiusExtensionTerm");
  *((_QWORD *)this + 5) = GetProcAddress(*((HMODULE *)this + 1), "RadiusExtensionProcess");
  *((_QWORD *)this + 6) = GetProcAddress(*((HMODULE *)this + 1), "RadiusExtensionProcessEx");
  *((_QWORD *)this + 7) = GetProcAddress(*((HMODULE *)this + 1), "RadiusExtensionFreeAttributes");
  ProcAddress = GetProcAddress(*((HMODULE *)this + 1), "RadiusExtensionProcess2");
  *((_QWORD *)this + 8) = ProcAddress;
  if ( *((_QWORD *)this + 5) )
    goto LABEL_24;
  if ( !*((_QWORD *)this + 6) )
  {
    if ( !ProcAddress )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        return 127;
      }
      WppDbgPrint("Either RadiusExtensionProcess, RadiusExtensionProcessEx, or RadiusExtensionProcess2 must be defined.");
      v14 = 12;
LABEL_30:
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, WPP_b461da539d613e66bfc4a53e3ac78614_Traceguids, "NPSSVC");
      return 127;
    }
LABEL_24:
    if ( !*((_QWORD *)this + 6) )
      goto LABEL_32;
  }
  if ( !*((_QWORD *)this + 7) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      return 127;
    }
    WppDbgPrint("RadiusExtensionFreeAttributes must be defined if RadiusExtensionProcessEx is defined.");
    v14 = 13;
    goto LABEL_30;
  }
LABEL_32:
  v15 = (__int64 (*)(void))*((_QWORD *)this + 3);
  if ( v15 && (v16 = v15()) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("RadiusExtensionInit failed with error: %d");
      WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_b461da539d613e66bfc4a53e3ac78614_Traceguids);
    }
    return v16;
  }
  else
  {
    *((_BYTE *)this + 16) = 1;
    return 0;
  }
}

```

## disassembly

```asm
0x180014608  push    rbx
0x18001460a  push    rbp
0x18001460b  push    rsi
0x18001460c  push    rdi
0x18001460d  push    r12
0x18001460f  push    r14
0x180014611  sub     rsp, 38h
0x180014615  mov     rdi, rdx
0x180014618  mov     rbx, rcx
0x18001461b  lea     r12, WPP_GLOBAL_Control
0x180014622  mov     rax, cs:WPP_GLOBAL_Control
0x180014629  cmp     rax, r12
0x18001462c  jz      short loc_180014667
0x18001462e  cmp     byte ptr [rax+19h], 4
0x180014632  jb      short loc_180014667
0x180014634  test    byte ptr [rax+1Ch], 4
0x180014638  jz      short loc_180014667
0x18001463a  lea     rcx, aLoadingExtensi; "Loading extension %S"
0x180014641  call    WppDbgPrint
0x180014646  mov     edx, 0Ah
0x18001464b  mov     [rsp+68h+var_48], rdi
0x180014650  lea     r8, WPP_b461da539d613e66bfc4a53e3ac78614_Traceguids
0x180014657  mov     rcx, cs:WPP_GLOBAL_Control
0x18001465e  mov     rcx, [rcx+10h]
0x180014662  call    WPP_SF_sS
0x180014667  mov     rcx, rdi; unsigned __int16 *
0x18001466a  call    ?ExtractFileNameFromPath@@YAPEBGPEBG@Z; ExtractFileNameFromPath(ushort const *)
0x18001466f  mov     rsi, rax
0x180014672  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180014676  mov     rax, rcx
0x180014679  xor     r14d, r14d
0x18001467c  inc     rax
0x18001467f  cmp     [rsi+rax*2], r14w
0x180014684  jnz     short loc_18001467C
0x180014686  lea     ebp, [rax+1]
0x180014689  mov     eax, 2
0x18001468e  mul     rbp
0x180014691  cmovb   rax, rcx
0x180014695  mov     rcx, rax; Size
0x180014698  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001469d  mov     [rbx], rax
0x1800146a0  test    rax, rax
0x1800146a3  jnz     short loc_1800146AF
0x1800146a5  mov     eax, 8
0x1800146aa  jmp     loc_18001489C
0x1800146af  mov     r8, rsi; Source
0x1800146b2  mov     rdx, rbp; SizeInWords
0x1800146b5  mov     rcx, rax; Destination
0x1800146b8  call    cs:__imp_wcscpy_s
0x1800146be  mov     rcx, rdi; lpLibFileName
0x1800146c1  call    cs:__imp_LoadLibraryW
0x1800146c7  mov     [rbx+8], rax
0x1800146cb  test    rax, rax
0x1800146ce  jnz     short loc_180014725
0x1800146d0  call    cs:__imp_GetLastError
0x1800146d6  mov     ebx, eax
0x1800146d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800146df  cmp     rcx, r12
0x1800146e2  jz      short loc_18001471E
0x1800146e4  cmp     byte ptr [rcx+19h], 2
0x1800146e8  jb      short loc_18001471E
0x1800146ea  test    byte ptr [rcx+1Ch], 4
0x1800146ee  jz      short loc_18001471E
0x1800146f0  mov     edx, eax
0x1800146f2  lea     rcx, aLoadlibrarywFa; "LoadLibraryW failed with error: %d"
0x1800146f9  call    WppDbgPrint
0x1800146fe  mov     edx, 0Bh
0x180014703  mov     dword ptr [rsp+68h+var_48], ebx
0x180014707  lea     r8, WPP_b461da539d613e66bfc4a53e3ac78614_Traceguids
0x18001470e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014715  mov     rcx, [rcx+10h]
0x180014719  call    WPP_SF_sd
0x18001471e  mov     eax, ebx
0x180014720  jmp     loc_18001489C
0x180014725  lea     rdx, aRadiusextensio_7; "RadiusExtensionInit"
0x18001472c  mov     rcx, rax; hModule
0x18001472f  call    cs:__imp_GetProcAddress
0x180014735  mov     [rbx+18h], rax
0x180014739  lea     rdx, aRadiusextensio; "RadiusExtensionTerm"
0x180014740  mov     rcx, [rbx+8]; hModule
0x180014744  call    cs:__imp_GetProcAddress
0x18001474a  mov     [rbx+20h], rax
0x18001474e  lea     rdx, aRadiusextensio_0; "RadiusExtensionProcess"
0x180014755  mov     rcx, [rbx+8]; hModule
0x180014759  call    cs:__imp_GetProcAddress
0x18001475f  mov     [rbx+28h], rax
0x180014763  lea     rdx, aRadiusextensio_8; "RadiusExtensionProcessEx"
0x18001476a  mov     rcx, [rbx+8]; hModule
0x18001476e  call    cs:__imp_GetProcAddress
0x180014774  mov     [rbx+30h], rax
0x180014778  lea     rdx, aRadiusextensio_6; "RadiusExtensionFreeAttributes"
0x18001477f  mov     rcx, [rbx+8]; hModule
0x180014783  call    cs:__imp_GetProcAddress
0x180014789  mov     [rbx+38h], rax
0x18001478d  lea     rdx, aRadiusextensio_4; "RadiusExtensionProcess2"
0x180014794  mov     rcx, [rbx+8]; hModule
0x180014798  call    cs:__imp_GetProcAddress
0x18001479e  mov     [rbx+40h], rax
0x1800147a2  cmp     [rbx+28h], r14
0x1800147a6  jnz     short loc_1800147DE
0x1800147a8  cmp     [rbx+30h], r14
0x1800147ac  jnz     short loc_1800147E4
0x1800147ae  test    rax, rax
0x1800147b1  jnz     short loc_1800147DE
0x1800147b3  mov     rax, cs:WPP_GLOBAL_Control
0x1800147ba  cmp     rax, r12
0x1800147bd  jz      short loc_180014831
0x1800147bf  cmp     byte ptr [rax+19h], 2
0x1800147c3  jb      short loc_180014831
0x1800147c5  test    byte ptr [rax+1Ch], 4
0x1800147c9  jz      short loc_180014831
0x1800147cb  lea     rcx, aEitherRadiusex; "Either RadiusExtensionProcess, RadiusEx"...
0x1800147d2  call    WppDbgPrint
0x1800147d7  mov     edx, 0Ch
0x1800147dc  jmp     short loc_180014813
0x1800147de  cmp     [rbx+30h], r14
0x1800147e2  jz      short loc_180014838
0x1800147e4  cmp     [rbx+38h], r14
0x1800147e8  jnz     short loc_180014838
0x1800147ea  mov     rax, cs:WPP_GLOBAL_Control
0x1800147f1  cmp     rax, r12
0x1800147f4  jz      short loc_180014831
0x1800147f6  cmp     byte ptr [rax+19h], 2
0x1800147fa  jb      short loc_180014831
0x1800147fc  test    byte ptr [rax+1Ch], 4
0x180014800  jz      short loc_180014831
0x180014802  lea     rcx, aRadiusextensio_2; "RadiusExtensionFreeAttributes must be d"...
0x180014809  call    WppDbgPrint
0x18001480e  mov     edx, 0Dh
0x180014813  mov     rcx, cs:WPP_GLOBAL_Control
0x18001481a  lea     r9, aNpssvc; "NPSSVC"
0x180014821  lea     r8, WPP_b461da539d613e66bfc4a53e3ac78614_Traceguids
0x180014828  mov     rcx, [rcx+10h]
0x18001482c  call    WPP_SF_s
0x180014831  mov     eax, 7Fh
0x180014836  jmp     short loc_18001489C
0x180014838  mov     rax, [rbx+18h]
0x18001483c  test    rax, rax
0x18001483f  jz      short loc_180014896
0x180014841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014846  mov     edi, eax
0x180014848  test    eax, eax
0x18001484a  jz      short loc_180014896
0x18001484c  mov     rax, cs:WPP_GLOBAL_Control
0x180014853  cmp     rax, r12
0x180014856  jz      short loc_180014892
0x180014858  cmp     byte ptr [rax+19h], 2
0x18001485c  jb      short loc_180014892
0x18001485e  test    byte ptr [rax+1Ch], 4
0x180014862  jz      short loc_180014892
0x180014864  mov     edx, edi
0x180014866  lea     rcx, aRadiusextensio_1; "RadiusExtensionInit failed with error: "...
0x18001486d  call    WppDbgPrint
0x180014872  mov     edx, 0Eh
0x180014877  mov     dword ptr [rsp+68h+var_48], edi
0x18001487b  lea     r8, WPP_b461da539d613e66bfc4a53e3ac78614_Traceguids
0x180014882  mov     rcx, cs:WPP_GLOBAL_Control
0x180014889  mov     rcx, [rcx+10h]
0x18001488d  call    WPP_SF_sd
0x180014892  mov     eax, edi
0x180014894  jmp     short loc_18001489C
0x180014896  mov     byte ptr [rbx+10h], 1
0x18001489a  xor     eax, eax
0x18001489c  add     rsp, 38h
0x1800148a0  pop     r14
0x1800148a2  pop     r12
0x1800148a4  pop     rdi
0x1800148a5  pop     rsi
0x1800148a6  pop     rbp
0x1800148a7  pop     rbx
0x1800148a8  retn
```
