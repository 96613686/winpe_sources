# XPerf::Internal::CvDbgInfoFromImage2(ushort const *,void *,ulong,ulong,bool,ulong *,_CVDD *,ulong *,CODEVIEW_INFORMATION_1 *,ulong *,ulong *,ushort *,ulong,bool &,bool,EMBEDDED_PDB_INFORMATION &,bool &,XPerfCore::IErrorMessage *)

- ea: `0x180022c08`
- end: `0x1800230d9`
- name: `?CvDbgInfoFromImage2@Internal@XPerf@@YAJPEBGPEAXKK_NPEAKPEAT_CVDD@@3PEAUCODEVIEW_INFORMATION_1@@33PEAGKAEA_N2AEAUEMBEDDED_PDB_INFORMATION@@7PEAVIErrorMessage@XPerfCore@@@Z`
- size: `1233`
- prototype: `int __fastcall(XPerf::Internal *this, unsigned __int16 *, void *, __int64, unsigned int, unsigned int *, union _CVDD *, union _CVDD *, struct CODEVIEW_INFORMATION_1 *, struct CODEVIEW_INFORMATION_1 *, unsigned int *, unsigned __int16 *, unsigned __int16 *, _BYTE *, BOOLEAN MappedAsImage, struct EMBEDDED_PDB_INFORMATION *, struct EMBEDDED_PDB_INFORMATION *, bool *)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800121e8`
- `0x18002389c`

## callees

- `0x180006960`
- `0x1800069ec`
- `0x1800099b8`
- `0x180022c08`
- `0x1800230e0`
- `0x180023550`
- `0x18002364c`
- `0x180023830`
- `0x1800239f4`
- `0x180026010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180022ff3`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180022ff3`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180022dda`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180022dda`

## pseudocode

```c
int __fastcall XPerf::Internal::CvDbgInfoFromImage2(
        XPerf::Internal *this,
        unsigned __int16 *a2,
        void *a3,
        __int64 a4,
        unsigned int a5,
        unsigned int *a6,
        union _CVDD *a7,
        union _CVDD *a8,
        struct CODEVIEW_INFORMATION_1 *a9,
        struct CODEVIEW_INFORMATION_1 *a10,
        unsigned int *a11,
        unsigned __int16 *a12,
        unsigned __int16 *a13,
        _BYTE *a14,
        BOOLEAN MappedAsImage,
        struct EMBEDDED_PDB_INFORMATION *a16,
        struct EMBEDDED_PDB_INFORMATION *a17,
        bool *a18)
{
  unsigned int *v18; // r12
  union _CVDD *v19; // rbx
  struct EMBEDDED_PDB_INFORMATION *v20; // r13
  unsigned __int16 *v21; // r14
  __int64 v22; // rax
  int v23; // r9d
  void *v24; // r10
  struct _IMAGE_NT_HEADERS64 *v25; // rsi
  int result; // eax
  int v27; // eax
  DWORD TimeDateStamp; // edx
  unsigned int SizeOfImage; // ecx
  BOOLEAN v30; // r15
  _BYTE *v31; // rax
  int v32; // eax
  union _CVDD *v33; // rsi
  unsigned int v34; // ecx
  int v35; // r9d
  unsigned int i; // edx
  __int64 v37; // r8
  wchar_t *v38; // rax
  __int64 v39; // rax
  bool v40; // [rsp+20h] [rbp-B8h]
  ULONG Size; // [rsp+70h] [rbp-68h] BYREF
  int v42; // [rsp+74h] [rbp-64h]
  int v43; // [rsp+78h] [rbp-60h]
  unsigned int v44; // [rsp+7Ch] [rbp-5Ch]
  int v45; // [rsp+80h] [rbp-58h]
  DWORD v46; // [rsp+84h] [rbp-54h]
  unsigned int v47; // [rsp+88h] [rbp-50h]
  int v48; // [rsp+8Ch] [rbp-4Ch]
  DWORD v49; // [rsp+90h] [rbp-48h]
  unsigned int v50; // [rsp+94h] [rbp-44h]
  signed __int64 v51; // [rsp+98h] [rbp-40h]
  unsigned int v54; // [rsp+F0h] [rbp+18h]

  v54 = (unsigned int)a3;
  v18 = a6;
  v19 = a7;
  v20 = a16;
  *(_OWORD *)a16 = 0;
  *((_QWORD *)v20 + 2) = 0;
  *(_BYTE *)a17 = 0;
  v21 = a12;
  if ( a12 )
    *a12 = 0;
  v22 = XPerfCore::_SafeImageNtHeader(a2, (unsigned int)a3);
  v25 = (struct _IMAGE_NT_HEADERS64 *)v22;
  if ( !v22 )
  {
    if ( a18 )
      (*(void (__fastcall **)(bool *, const wchar_t *))(*(_QWORD *)a18 + 8LL))(a18, L"Invalid executable format.");
    return ATL::AtlHresultFromWin32(193);
  }
  v27 = *(_DWORD *)(v22 + 88);
  v45 = v27;
  v48 = v27;
  TimeDateStamp = v25->FileHeader.TimeDateStamp;
  v46 = TimeDateStamp;
  v49 = TimeDateStamp;
  SizeOfImage = v25->OptionalHeader.SizeOfImage;
  v47 = SizeOfImage;
  v50 = SizeOfImage;
  if ( v23 && v27 != v23 )
  {
    if ( a18 )
      (*(void (__fastcall **)(bool *, const wchar_t *))(*(_QWORD *)a18 + 8LL))(a18, L"Invalid image header checksum.");
    return ATL::AtlHresultFromWin32(13);
  }
  if ( a10 )
    *(_DWORD *)a10 = TimeDateStamp;
  if ( a11 )
    *a11 = SizeOfImage;
  if ( v25->OptionalHeader.Magic == 267 )
  {
    *a14 = 0;
  }
  else
  {
    if ( v25->OptionalHeader.Magic != 523 )
      return -2147418113;
    *a14 = 1;
  }
  v30 = MappedAsImage;
  if ( (unsigned int)SymCommonNativeResourceOnlyDll(v24) )
    goto LABEL_24;
  v43 = v25->FileHeader.Characteristics & 0x200;
  v42 = SymCommonTlbImpManagedDll(a2, v25, v30);
  Size = 0;
  v31 = RtlImageDirectoryEntryToData(a2, v30, 6u, &Size);
  if ( v31 )
  {
    v51 = v31 - (_BYTE *)a2;
    a5 = -1;
    v33 = a8;
    result = CvInfoFromDbgDir(
               a2,
               v54,
               Size,
               (int)v31 - (int)a2,
               v40,
               &a5,
               v18,
               v19,
               (unsigned int *)a8,
               a9,
               v30,
               v20,
               (bool *)a17);
    if ( result < 0 )
      return result;
    v34 = *v18;
    v35 = v42;
    if ( *v18 > 1 )
    {
      if ( v42 == 1 )
      {
        if ( a18 )
          (*(void (__fastcall **)(bool *, const wchar_t *))(*(_QWORD *)a18 + 8LL))(
            a18,
            L"Multiple CvDbg entries in IL-only image.");
        return ATL::AtlHresultFromWin32(193);
      }
      for ( i = 0; ; ++i )
      {
        v44 = i;
        if ( i >= v34 )
          break;
        v37 = 1576LL * i;
        if ( *(_DWORD *)((char *)v19 + v37) == 1396986706 && a5 != -1 && i != a5 )
        {
          *(_DWORD *)((char *)v19 + v37) = 3;
          v34 = *v18;
        }
      }
    }
    v32 = *(_DWORD *)v19;
    if ( *(_DWORD *)v19 == 1 )
    {
      v32 = 1;
    }
    else if ( v32 || !v43 )
    {
      if ( v35 == 1 )
      {
        *(_DWORD *)v19 = 3;
        v32 = 3;
      }
    }
    else
    {
      *(_DWORD *)v19 = 2;
      v32 = 2;
    }
  }
  else
  {
    if ( !v43 )
    {
LABEL_24:
      *v18 = 1;
      *(_DWORD *)v19 = 0;
      v32 = 0;
      v33 = a8;
      goto LABEL_47;
    }
    *v18 = 1;
    *(_DWORD *)v19 = 2;
    v32 = 2;
    v33 = a8;
  }
LABEL_47:
  if ( !v32 )
  {
    if ( v33 )
      *(_DWORD *)v33 = 4;
LABEL_62:
    if ( !v21 || !(_DWORD)a13 || (unsigned int)SymGetEstimatedOriginalFilename((unsigned __int16 *)this) )
      return 0;
    goto LABEL_66;
  }
  if ( (unsigned int)(v32 - 1) > 1 )
    goto LABEL_62;
  *((_DWORD *)v19 + 1) = v45;
  *((_DWORD *)v19 + 2) = v46;
  *((_DWORD *)v19 + 3) = v47;
  if ( !(unsigned int)SymGetEstimatedOriginalFilename((unsigned __int16 *)this) )
  {
LABEL_66:
    if ( a18 )
      (*(void (__fastcall **)(bool *, const wchar_t *))(*(_QWORD *)a18 + 8LL))(
        a18,
        L"Failed to obtain the original file name.");
    return -2147467259;
  }
  if ( !v21 || (result = StringCchCopyW(v21, (unsigned int)a13, (const unsigned __int16 *)v19 + 8), result >= 0) )
  {
    if ( *(_DWORD *)v19 != 2 )
      goto LABEL_56;
    v38 = wcsrchr((const wchar_t *)v19 + 8, 0x2Eu);
    if ( v38 )
      *v38 = 0;
    result = StringCchCatW((unsigned __int16 *)v19 + 8, 0x30Cu, L".dbg");
    if ( result >= 0 )
    {
LABEL_56:
      if ( v33 )
      {
        v39 = -1;
        do
          ++v39;
        while ( *((_WORD *)v19 + v39 + 8) );
        *(_DWORD *)v33 = 2 * v39 + 18;
      }
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180022c08  mov     [rsp+arg_10], r8d
0x180022c0d  mov     [rsp+BaseAddress], rdx
0x180022c12  mov     [rsp+arg_0], rcx
0x180022c17  push    rbx
0x180022c18  push    rsi
0x180022c19  push    rdi
0x180022c1a  push    r12
0x180022c1c  push    r13
0x180022c1e  push    r14
0x180022c20  push    r15
0x180022c22  sub     rsp, 0A0h
0x180022c29  mov     r10, rdx
0x180022c2c  mov     r12, [rsp+0D8h+arg_28]
0x180022c34  mov     rbx, [rsp+0D8h+arg_30]
0x180022c3c  xorps   xmm0, xmm0
0x180022c3f  xor     eax, eax
0x180022c41  mov     r13, [rsp+0D8h+arg_78]
0x180022c49  movups  xmmword ptr [r13+0], xmm0
0x180022c4e  mov     [r13+10h], rax
0x180022c52  mov     rax, [rsp+0D8h+arg_80]
0x180022c5a  mov     byte ptr [rax], 0
0x180022c5d  mov     r14, [rsp+0D8h+arg_58]
0x180022c65  test    r14, r14
0x180022c68  jz      short loc_180022C70
0x180022c6a  xor     eax, eax
0x180022c6c  mov     [r14], ax
0x180022c70  mov     edx, r8d
0x180022c73  mov     rcx, r10
0x180022c76  call    XPerfCore___SafeImageNtHeader
0x180022c7b  mov     rsi, rax
0x180022c7e  test    rax, rax
0x180022c81  jnz     short loc_180022CB2
0x180022c83  mov     rcx, [rsp+0D8h+arg_88]
0x180022c8b  test    rcx, rcx
0x180022c8e  jz      short loc_180022CA3
0x180022c90  mov     rax, [rcx]
0x180022c93  lea     rdx, aInvalidExecuta; "Invalid executable format."
0x180022c9a  mov     rax, [rax+8]
0x180022c9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ca3  mov     ecx, 0C1h; unsigned int
0x180022ca8  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180022cad  jmp     loc_1800230C6
0x180022cb2  mov     eax, [rax+58h]
0x180022cb5  mov     [rsp+0D8h+var_58], eax
0x180022cbc  mov     [rsp+0D8h+var_4C], eax
0x180022cc3  mov     edx, [rsi+8]
0x180022cc6  mov     [rsp+0D8h+var_54], edx
0x180022ccd  mov     [rsp+0D8h+var_48], edx
0x180022cd4  mov     ecx, [rsi+50h]
0x180022cd7  mov     [rsp+0D8h+var_50], ecx
0x180022cde  mov     [rsp+0D8h+var_44], ecx
0x180022ce5  test    r9d, r9d
0x180022ce8  jz      short loc_180022D1E
0x180022cea  cmp     eax, r9d
0x180022ced  jz      short loc_180022D1E
0x180022cef  mov     rcx, [rsp+0D8h+arg_88]
0x180022cf7  test    rcx, rcx
0x180022cfa  jz      short loc_180022D0F
0x180022cfc  mov     rax, [rcx]
0x180022cff  lea     rdx, aInvalidImageHe; "Invalid image header checksum."
0x180022d06  mov     rax, [rax+8]
0x180022d0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d0f  mov     ecx, 0Dh; unsigned int
0x180022d14  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180022d19  jmp     loc_1800230C6
0x180022d1e  mov     rax, [rsp+0D8h+arg_48]
0x180022d26  test    rax, rax
0x180022d29  jz      short loc_180022D2D
0x180022d2b  mov     [rax], edx
0x180022d2d  mov     rax, [rsp+0D8h+arg_50]
0x180022d35  test    rax, rax
0x180022d38  jz      short loc_180022D3C
0x180022d3a  mov     [rax], ecx
0x180022d3c  mov     eax, 10Bh
0x180022d41  cmp     [rsi+18h], ax
0x180022d45  jz      short loc_180022D6E
0x180022d47  mov     eax, 20Bh
0x180022d4c  cmp     [rsi+18h], ax
0x180022d50  jz      short loc_180022D5C
0x180022d52  mov     eax, 8000FFFFh
0x180022d57  jmp     loc_1800230C6
0x180022d5c  mov     edi, 1
0x180022d61  mov     rax, [rsp+0D8h+arg_68]
0x180022d69  mov     [rax], dil
0x180022d6c  jmp     short loc_180022D7E
0x180022d6e  mov     rax, [rsp+0D8h+arg_68]
0x180022d76  mov     byte ptr [rax], 0
0x180022d79  mov     edi, 1
0x180022d7e  mov     r15b, [rsp+0D8h+MappedAsImage]
0x180022d86  mov     dl, r15b
0x180022d89  mov     rcx, r10; BaseAddress
0x180022d8c  call    SymCommonNativeResourceOnlyDll
0x180022d91  test    eax, eax
0x180022d93  jz      short loc_180022D9A
0x180022d95  xor     r13d, r13d
0x180022d98  jmp     short loc_180022DF2
0x180022d9a  movzx   eax, word ptr [rsi+16h]
0x180022d9e  and     eax, 200h
0x180022da3  mov     [rsp+0D8h+var_60], eax
0x180022da7  mov     r8b, r15b; MappedAsImage
0x180022daa  mov     rdx, rsi; NtHeader
0x180022dad  mov     rsi, [rsp+0D8h+BaseAddress]
0x180022db5  mov     rcx, rsi; BaseAddress
0x180022db8  call    SymCommonTlbImpManagedDll
0x180022dbd  mov     [rsp+0D8h+var_64], eax
0x180022dc1  mov     [rsp+0D8h+Size], 0
0x180022dc9  mov     r8d, 6; Directory
0x180022dcf  lea     r9, [rsp+0D8h+Size]; Size
0x180022dd4  mov     dl, r15b; MappedAsImage
0x180022dd7  mov     rcx, rsi; BaseAddress
0x180022dda  call    cs:__imp_RtlImageDirectoryEntryToData
0x180022de0  mov     r9, rax
0x180022de3  test    rax, rax
0x180022de6  jnz     short loc_180022E35
0x180022de8  xor     r13d, r13d
0x180022deb  cmp     [rsp+0D8h+var_60], r13d
0x180022df0  jnz     short loc_180022E11
0x180022df2  mov     [r12], edi
0x180022df6  mov     [rbx], r13d
0x180022df9  mov     eax, r13d
0x180022dfc  mov     rsi, [rsp+0D8h+arg_38]
0x180022e04  mov     r15, [rsp+0D8h+BaseAddress]
0x180022e0c  jmp     loc_180022F6E
0x180022e11  mov     [r12], edi
0x180022e15  mov     dword ptr [rbx], 2
0x180022e1b  mov     eax, 2
0x180022e20  mov     rsi, [rsp+0D8h+arg_38]
0x180022e28  mov     r15, [rsp+0D8h+BaseAddress]
0x180022e30  jmp     loc_180022F6E
0x180022e35  sub     r9, rsi; unsigned int
0x180022e38  mov     [rsp+0D8h+var_40], r9
0x180022e40  mov     [rsp+0D8h+arg_20], 0FFFFFFFFh
0x180022e4b  mov     rax, [rsp+0D8h+arg_80]
0x180022e53  mov     [rsp+0D8h+var_78], rax; bool *
0x180022e58  mov     [rsp+0D8h+var_80], r13; struct EMBEDDED_PDB_INFORMATION *
0x180022e5d  mov     [rsp+0D8h+var_88], r15b; bool
0x180022e62  mov     rax, [rsp+0D8h+arg_40]
0x180022e6a  mov     [rsp+0D8h+var_90], rax; struct CODEVIEW_INFORMATION_1 *
0x180022e6f  mov     rsi, [rsp+0D8h+arg_38]
0x180022e77  mov     [rsp+0D8h+var_98], rsi; unsigned int *
0x180022e7c  mov     [rsp+0D8h+var_A0], rbx; union _CVDD *
0x180022e81  mov     [rsp+0D8h+var_A8], r12; unsigned int *
0x180022e86  lea     rax, [rsp+0D8h+arg_20]
0x180022e8e  mov     [rsp+0D8h+var_B0], rax; unsigned int *
0x180022e93  mov     r8d, [rsp+0D8h+Size]; unsigned int
0x180022e98  mov     edx, [rsp+0D8h+arg_10]; unsigned int
0x180022e9f  mov     r15, [rsp+0D8h+BaseAddress]
0x180022ea7  mov     rcx, r15; void *
0x180022eaa  call    ?CvInfoFromDbgDir@@YAJPEAXKKK_NPEAK2PEAT_CVDD@@2PEAUCODEVIEW_INFORMATION_1@@1AEAUEMBEDDED_PDB_INFORMATION@@AEA_N@Z; CvInfoFromDbgDir(void *,ulong,ulong,ulong,bool,ulong *,ulong *,_CVDD *,ulong *,CODEVIEW_INFORMATION_1 *,bool,EMBEDDED_PDB_INFORMATION &,bool &)
0x180022eaf  xor     r13d, r13d
0x180022eb2  test    eax, eax
0x180022eb4  js      loc_1800230C6
0x180022eba  mov     ecx, [r12]
0x180022ebe  mov     r9d, [rsp+0D8h+var_64]
0x180022ec3  cmp     ecx, edi
0x180022ec5  jbe     short loc_180022F3C
0x180022ec7  cmp     r9d, edi
0x180022eca  jnz     short loc_180022EFB
0x180022ecc  mov     rcx, [rsp+0D8h+arg_88]
0x180022ed4  test    rcx, rcx
0x180022ed7  jz      short loc_180022EEC
0x180022ed9  mov     rax, [rcx]
0x180022edc  lea     rdx, aMultipleCvdbgE; "Multiple CvDbg entries in IL-only image"...
0x180022ee3  mov     rax, [rax+8]
0x180022ee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022eec  mov     ecx, 0C1h; unsigned int
0x180022ef1  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180022ef6  jmp     loc_1800230C6
0x180022efb  mov     edx, r13d
0x180022efe  mov     [rsp+0D8h+var_5C], edx
0x180022f02  cmp     edx, ecx
0x180022f04  jnb     short loc_180022F3C
0x180022f06  mov     eax, edx
0x180022f08  imul    r8, rax, 628h
0x180022f0f  cmp     dword ptr [r8+rbx], 53445352h
0x180022f17  jnz     short loc_180022F38
0x180022f19  cmp     [rsp+0D8h+arg_20], 0FFFFFFFFh
0x180022f21  jz      short loc_180022F38
0x180022f23  cmp     edx, [rsp+0D8h+arg_20]
0x180022f2a  jz      short loc_180022F38
0x180022f2c  mov     dword ptr [r8+rbx], 3
0x180022f34  mov     ecx, [r12]
0x180022f38  add     edx, edi
0x180022f3a  jmp     short loc_180022EFE
0x180022f3c  mov     eax, [rbx]
0x180022f3e  cmp     eax, edi
0x180022f40  jz      short loc_180022F6C
0x180022f42  test    eax, eax
0x180022f44  jnz     short loc_180022F5A
0x180022f46  cmp     [rsp+0D8h+var_60], r13d
0x180022f4b  jz      short loc_180022F5A
0x180022f4d  mov     dword ptr [rbx], 2
0x180022f53  mov     eax, 2
0x180022f58  jmp     short loc_180022F6E
0x180022f5a  cmp     r9d, edi
0x180022f5d  jnz     short loc_180022F6A
0x180022f5f  mov     dword ptr [rbx], 3
0x180022f65  mov     eax, 3
0x180022f6a  jmp     short loc_180022F6E
0x180022f6c  mov     eax, edi
0x180022f6e  test    eax, eax
0x180022f70  jz      loc_18002303C
0x180022f76  sub     eax, 1
0x180022f79  jz      short loc_180022F84
0x180022f7b  cmp     eax, 1
0x180022f7e  jnz     loc_180023047
0x180022f84  mov     eax, [rsp+0D8h+var_58]
0x180022f8b  mov     [rbx+4], eax
0x180022f8e  mov     eax, [rsp+0D8h+var_54]
0x180022f95  mov     [rbx+8], eax
0x180022f98  mov     eax, [rsp+0D8h+var_50]
0x180022f9f  mov     [rbx+0Ch], eax
0x180022fa2  lea     rdi, [rbx+10h]
0x180022fa6  mov     r9, rdi
0x180022fa9  mov     r8d, 307h
0x180022faf  mov     rdx, r15
0x180022fb2  mov     rcx, [rsp+0D8h+arg_0]; unsigned __int16 *
0x180022fba  call    SymGetEstimatedOriginalFilename
0x180022fbf  test    eax, eax
0x180022fc1  jz      loc_180023074
0x180022fc7  test    r14, r14
0x180022fca  jz      short loc_180022FE6
0x180022fcc  mov     edx, dword ptr [rsp+0D8h+arg_60]; unsigned __int64
0x180022fd3  mov     r8, rdi; unsigned __int16 *
0x180022fd6  mov     rcx, r14; unsigned __int16 *
0x180022fd9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180022fde  test    eax, eax
0x180022fe0  js      loc_1800230C6
0x180022fe6  cmp     dword ptr [rbx], 2
0x180022fe9  jnz     short loc_18002301E
0x180022feb  mov     edx, 2Eh ; '.'; Ch
0x180022ff0  mov     rcx, rdi; Str
0x180022ff3  call    cs:__imp_wcsrchr
0x180022ff9  test    rax, rax
0x180022ffc  jz      short loc_180023002
0x180022ffe  mov     [rax], r13w
0x180023002  lea     r8, aDbg; ".dbg"
0x180023009  mov     edx, 30Ch; unsigned __int64
0x18002300e  mov     rcx, rdi; unsigned __int16 *
0x180023011  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180023016  test    eax, eax
0x180023018  js      loc_1800230C6
0x18002301e  test    rsi, rsi
0x180023021  jz      short loc_180023070
0x180023023  or      rax, 0FFFFFFFFFFFFFFFFh
0x180023027  inc     rax
0x18002302a  cmp     [rdi+rax*2], r13w
0x18002302f  jnz     short loc_180023027
0x180023031  lea     eax, ds:12h[rax*2]
0x180023038  mov     [rsi], eax
0x18002303a  jmp     short loc_180023070
0x18002303c  test    rsi, rsi
0x18002303f  jz      short loc_180023047
0x180023041  mov     dword ptr [rsi], 4
0x180023047  test    r14, r14
0x18002304a  jz      short loc_180023070
0x18002304c  mov     r8d, dword ptr [rsp+0D8h+arg_60]
0x180023054  test    r8d, r8d
0x180023057  jz      short loc_180023070
0x180023059  mov     r9, r14
0x18002305c  mov     rdx, r15
0x18002305f  mov     rcx, [rsp+0D8h+arg_0]; unsigned __int16 *
0x180023067  call    SymGetEstimatedOriginalFilename
0x18002306c  test    eax, eax
0x18002306e  jz      short loc_180023074
0x180023070  xor     eax, eax
0x180023072  jmp     short loc_1800230C6
0x180023074  mov     rcx, [rsp+0D8h+arg_88]
0x18002307c  test    rcx, rcx
0x18002307f  jz      short loc_180023094
0x180023081  mov     rax, [rcx]
0x180023084  lea     rdx, aFailedToObtain; "Failed to obtain the original file name"...
0x18002308b  mov     rax, [rax+8]
0x18002308f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023094  mov     eax, 80004005h
0x180023099  jmp     short loc_1800230C6
0x18002309b  mov     rcx, [rsp+0D8h+arg_88]
0x1800230a3  test    rcx, rcx
0x1800230a6  jz      short loc_1800230BB
0x1800230a8  mov     rax, [rcx]
0x1800230ab  lea     rdx, aPagingExceptio; "Paging exception occurred while process"...
0x1800230b2  mov     rax, [rax+8]
0x1800230b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230bb  mov     ecx, 3E7h; unsigned int
0x1800230c0  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800230c5  nop
0x1800230c6  add     rsp, 0A0h
0x1800230cd  pop     r15
0x1800230cf  pop     r14
0x1800230d1  pop     r13
0x1800230d3  pop     r12
0x1800230d5  pop     rdi
0x1800230d6  pop     rsi
0x1800230d7  pop     rbx
0x1800230d8  retn
0x180025af8  push    rbp
0x180025afa  sub     rsp, 70h
0x180025afe  mov     rbp, rdx
0x180025b01  mov     rax, [rcx]
0x180025b04  xor     ecx, ecx
  ... truncated ...
```
