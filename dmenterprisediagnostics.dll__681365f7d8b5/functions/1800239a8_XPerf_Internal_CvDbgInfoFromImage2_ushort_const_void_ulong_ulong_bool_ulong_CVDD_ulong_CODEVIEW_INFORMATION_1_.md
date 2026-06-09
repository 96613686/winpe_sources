# XPerf::Internal::CvDbgInfoFromImage2(ushort const *,void *,ulong,ulong,bool,ulong *,_CVDD *,ulong *,CODEVIEW_INFORMATION_1 *,ulong *,ulong *,ushort *,ulong,bool &,bool,EMBEDDED_PDB_INFORMATION &,bool &,XPerfCore::IErrorMessage *)

- ea: `0x1800239a8`
- end: `0x180023e86`
- name: `?CvDbgInfoFromImage2@Internal@XPerf@@YAJPEBGPEAXKK_NPEAKPEAT_CVDD@@3PEAUCODEVIEW_INFORMATION_1@@33PEAGKAEA_N2AEAUEMBEDDED_PDB_INFORMATION@@7PEAVIErrorMessage@XPerfCore@@@Z`
- size: `1246`
- prototype: `__int64 __fastcall(XPerf::Internal *__hidden this, const unsigned __int16 *, void *, unsigned int, unsigned int, unsigned int *, union _CVDD *, union _CVDD *, struct CODEVIEW_INFORMATION_1 *, struct CODEVIEW_INFORMATION_1 *, unsigned int *, unsigned int *, unsigned __int16 *, unsigned int, BOOLEAN MappedAsImage, struct EMBEDDED_PDB_INFORMATION *, struct EMBEDDED_PDB_INFORMATION *, bool *, struct XPerfCore::IErrorMessage *)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800129cc`
- `0x18002469c`

## callees

- `0x180006be0`
- `0x180006c6c`
- `0x180009e98`
- `0x1800239a8`
- `0x180023e8c`
- `0x180024308`
- `0x18002441c`
- `0x180024630`
- `0x1800247f4`
- `0x180027010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180023d99`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180023d99`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180023b7a`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180023b7a`

## pseudocode

```c
int __fastcall XPerf::Internal::CvDbgInfoFromImage2(
        XPerf::Internal *this,
        char *a2,
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
  unsigned int *v24; // r10
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
    return ATL::AtlHresultFromWin32(0xC1u);
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
    return ATL::AtlHresultFromWin32(0xDu);
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
  if ( (unsigned int)SymCommonNativeResourceOnlyDll(v24, MappedAsImage) )
    goto LABEL_24;
  v43 = v25->FileHeader.Characteristics & 0x200;
  v42 = SymCommonTlbImpManagedDll(a2, v25, v30);
  Size = 0;
  v31 = RtlImageDirectoryEntryToData(a2, v30, 6u, &Size);
  if ( v31 )
  {
    v51 = v31 - a2;
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
        return ATL::AtlHresultFromWin32(0xC1u);
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
0x1800239a8  mov     [rsp+arg_10], r8d
0x1800239ad  mov     [rsp+BaseAddress], rdx
0x1800239b2  mov     [rsp+arg_0], rcx
0x1800239b7  push    rbx
0x1800239b8  push    rsi
0x1800239b9  push    rdi
0x1800239ba  push    r12
0x1800239bc  push    r13
0x1800239be  push    r14
0x1800239c0  push    r15
0x1800239c2  sub     rsp, 0A0h
0x1800239c9  mov     r10, rdx
0x1800239cc  mov     r12, [rsp+0D8h+arg_28]
0x1800239d4  mov     rbx, [rsp+0D8h+arg_30]
0x1800239dc  xorps   xmm0, xmm0
0x1800239df  xor     eax, eax
0x1800239e1  mov     r13, [rsp+0D8h+arg_78]
0x1800239e9  movups  xmmword ptr [r13+0], xmm0
0x1800239ee  mov     [r13+10h], rax
0x1800239f2  mov     rax, [rsp+0D8h+arg_80]
0x1800239fa  mov     byte ptr [rax], 0
0x1800239fd  mov     r14, [rsp+0D8h+arg_58]
0x180023a05  test    r14, r14
0x180023a08  jz      short loc_180023A10
0x180023a0a  xor     eax, eax
0x180023a0c  mov     [r14], ax
0x180023a10  mov     edx, r8d
0x180023a13  mov     rcx, r10
0x180023a16  call    XPerfCore___SafeImageNtHeader
0x180023a1b  mov     rsi, rax
0x180023a1e  test    rax, rax
0x180023a21  jnz     short loc_180023A52
0x180023a23  mov     rcx, [rsp+0D8h+arg_88]
0x180023a2b  test    rcx, rcx
0x180023a2e  jz      short loc_180023A43
0x180023a30  mov     rax, [rcx]
0x180023a33  lea     rdx, aInvalidExecuta; "Invalid executable format."
0x180023a3a  mov     rax, [rax+8]
0x180023a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a43  mov     ecx, 0C1h; unsigned int
0x180023a48  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180023a4d  jmp     loc_180023E72
0x180023a52  mov     eax, [rax+58h]
0x180023a55  mov     [rsp+0D8h+var_58], eax
0x180023a5c  mov     [rsp+0D8h+var_4C], eax
0x180023a63  mov     edx, [rsi+8]
0x180023a66  mov     [rsp+0D8h+var_54], edx
0x180023a6d  mov     [rsp+0D8h+var_48], edx
0x180023a74  mov     ecx, [rsi+50h]
0x180023a77  mov     [rsp+0D8h+var_50], ecx
0x180023a7e  mov     [rsp+0D8h+var_44], ecx
0x180023a85  test    r9d, r9d
0x180023a88  jz      short loc_180023ABE
0x180023a8a  cmp     eax, r9d
0x180023a8d  jz      short loc_180023ABE
0x180023a8f  mov     rcx, [rsp+0D8h+arg_88]
0x180023a97  test    rcx, rcx
0x180023a9a  jz      short loc_180023AAF
0x180023a9c  mov     rax, [rcx]
0x180023a9f  lea     rdx, aInvalidImageHe; "Invalid image header checksum."
0x180023aa6  mov     rax, [rax+8]
0x180023aaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023aaf  mov     ecx, 0Dh; unsigned int
0x180023ab4  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180023ab9  jmp     loc_180023E72
0x180023abe  mov     rax, [rsp+0D8h+arg_48]
0x180023ac6  test    rax, rax
0x180023ac9  jz      short loc_180023ACD
0x180023acb  mov     [rax], edx
0x180023acd  mov     rax, [rsp+0D8h+arg_50]
0x180023ad5  test    rax, rax
0x180023ad8  jz      short loc_180023ADC
0x180023ada  mov     [rax], ecx
0x180023adc  mov     eax, 10Bh
0x180023ae1  cmp     [rsi+18h], ax
0x180023ae5  jz      short loc_180023B0E
0x180023ae7  mov     eax, 20Bh
0x180023aec  cmp     [rsi+18h], ax
0x180023af0  jz      short loc_180023AFC
0x180023af2  mov     eax, 8000FFFFh
0x180023af7  jmp     loc_180023E72
0x180023afc  mov     edi, 1
0x180023b01  mov     rax, [rsp+0D8h+arg_68]
0x180023b09  mov     [rax], dil
0x180023b0c  jmp     short loc_180023B1E
0x180023b0e  mov     rax, [rsp+0D8h+arg_68]
0x180023b16  mov     byte ptr [rax], 0
0x180023b19  mov     edi, 1
0x180023b1e  mov     r15b, [rsp+0D8h+MappedAsImage]
0x180023b26  mov     dl, r15b
0x180023b29  mov     rcx, r10; BaseAddress
0x180023b2c  call    SymCommonNativeResourceOnlyDll
0x180023b31  test    eax, eax
0x180023b33  jz      short loc_180023B3A
0x180023b35  xor     r13d, r13d
0x180023b38  jmp     short loc_180023B98
0x180023b3a  movzx   eax, word ptr [rsi+16h]
0x180023b3e  and     eax, 200h
0x180023b43  mov     [rsp+0D8h+var_60], eax
0x180023b47  mov     r8b, r15b; MappedAsImage
0x180023b4a  mov     rdx, rsi; NtHeader
0x180023b4d  mov     rsi, [rsp+0D8h+BaseAddress]
0x180023b55  mov     rcx, rsi; BaseAddress
0x180023b58  call    SymCommonTlbImpManagedDll
0x180023b5d  mov     [rsp+0D8h+var_64], eax
0x180023b61  mov     [rsp+0D8h+Size], 0
0x180023b69  mov     r8d, 6; Directory
0x180023b6f  lea     r9, [rsp+0D8h+Size]; Size
0x180023b74  mov     dl, r15b; MappedAsImage
0x180023b77  mov     rcx, rsi; BaseAddress
0x180023b7a  call    cs:__imp_RtlImageDirectoryEntryToData
0x180023b81  nop     dword ptr [rax+rax+00h]
0x180023b86  mov     r9, rax
0x180023b89  test    rax, rax
0x180023b8c  jnz     short loc_180023BDB
0x180023b8e  xor     r13d, r13d
0x180023b91  cmp     [rsp+0D8h+var_60], r13d
0x180023b96  jnz     short loc_180023BB7
0x180023b98  mov     [r12], edi
0x180023b9c  mov     [rbx], r13d
0x180023b9f  mov     eax, r13d
0x180023ba2  mov     rsi, [rsp+0D8h+arg_38]
0x180023baa  mov     r15, [rsp+0D8h+BaseAddress]
0x180023bb2  jmp     loc_180023D14
0x180023bb7  mov     [r12], edi
0x180023bbb  mov     dword ptr [rbx], 2
0x180023bc1  mov     eax, 2
0x180023bc6  mov     rsi, [rsp+0D8h+arg_38]
0x180023bce  mov     r15, [rsp+0D8h+BaseAddress]
0x180023bd6  jmp     loc_180023D14
0x180023bdb  sub     r9, rsi; unsigned int
0x180023bde  mov     [rsp+0D8h+var_40], r9
0x180023be6  mov     [rsp+0D8h+arg_20], 0FFFFFFFFh
0x180023bf1  mov     rax, [rsp+0D8h+arg_80]
0x180023bf9  mov     [rsp+0D8h+var_78], rax; bool *
0x180023bfe  mov     [rsp+0D8h+var_80], r13; struct EMBEDDED_PDB_INFORMATION *
0x180023c03  mov     [rsp+0D8h+var_88], r15b; bool
0x180023c08  mov     rax, [rsp+0D8h+arg_40]
0x180023c10  mov     [rsp+0D8h+var_90], rax; struct CODEVIEW_INFORMATION_1 *
0x180023c15  mov     rsi, [rsp+0D8h+arg_38]
0x180023c1d  mov     [rsp+0D8h+var_98], rsi; unsigned int *
0x180023c22  mov     [rsp+0D8h+var_A0], rbx; union _CVDD *
0x180023c27  mov     [rsp+0D8h+var_A8], r12; unsigned int *
0x180023c2c  lea     rax, [rsp+0D8h+arg_20]
0x180023c34  mov     [rsp+0D8h+var_B0], rax; unsigned int *
0x180023c39  mov     r8d, [rsp+0D8h+Size]; unsigned int
0x180023c3e  mov     edx, [rsp+0D8h+arg_10]; unsigned int
0x180023c45  mov     r15, [rsp+0D8h+BaseAddress]
0x180023c4d  mov     rcx, r15; void *
0x180023c50  call    ?CvInfoFromDbgDir@@YAJPEAXKKK_NPEAK2PEAT_CVDD@@2PEAUCODEVIEW_INFORMATION_1@@1AEAUEMBEDDED_PDB_INFORMATION@@AEA_N@Z; CvInfoFromDbgDir(void *,ulong,ulong,ulong,bool,ulong *,ulong *,_CVDD *,ulong *,CODEVIEW_INFORMATION_1 *,bool,EMBEDDED_PDB_INFORMATION &,bool &)
0x180023c55  xor     r13d, r13d
0x180023c58  test    eax, eax
0x180023c5a  js      loc_180023E72
0x180023c60  mov     ecx, [r12]
0x180023c64  mov     r9d, [rsp+0D8h+var_64]
0x180023c69  cmp     ecx, edi
0x180023c6b  jbe     short loc_180023CE2
0x180023c6d  cmp     r9d, edi
0x180023c70  jnz     short loc_180023CA1
0x180023c72  mov     rcx, [rsp+0D8h+arg_88]
0x180023c7a  test    rcx, rcx
0x180023c7d  jz      short loc_180023C92
0x180023c7f  mov     rax, [rcx]
0x180023c82  lea     rdx, aMultipleCvdbgE; "Multiple CvDbg entries in IL-only image"...
0x180023c89  mov     rax, [rax+8]
0x180023c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c92  mov     ecx, 0C1h; unsigned int
0x180023c97  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180023c9c  jmp     loc_180023E72
0x180023ca1  mov     edx, r13d
0x180023ca4  mov     [rsp+0D8h+var_5C], edx
0x180023ca8  cmp     edx, ecx
0x180023caa  jnb     short loc_180023CE2
0x180023cac  mov     eax, edx
0x180023cae  imul    r8, rax, 628h
0x180023cb5  cmp     dword ptr [r8+rbx], 53445352h
0x180023cbd  jnz     short loc_180023CDE
0x180023cbf  cmp     [rsp+0D8h+arg_20], 0FFFFFFFFh
0x180023cc7  jz      short loc_180023CDE
0x180023cc9  cmp     edx, [rsp+0D8h+arg_20]
0x180023cd0  jz      short loc_180023CDE
0x180023cd2  mov     dword ptr [r8+rbx], 3
0x180023cda  mov     ecx, [r12]
0x180023cde  add     edx, edi
0x180023ce0  jmp     short loc_180023CA4
0x180023ce2  mov     eax, [rbx]
0x180023ce4  cmp     eax, edi
0x180023ce6  jz      short loc_180023D12
0x180023ce8  test    eax, eax
0x180023cea  jnz     short loc_180023D00
0x180023cec  cmp     [rsp+0D8h+var_60], r13d
0x180023cf1  jz      short loc_180023D00
0x180023cf3  mov     dword ptr [rbx], 2
0x180023cf9  mov     eax, 2
0x180023cfe  jmp     short loc_180023D14
0x180023d00  cmp     r9d, edi
0x180023d03  jnz     short loc_180023D10
0x180023d05  mov     dword ptr [rbx], 3
0x180023d0b  mov     eax, 3
0x180023d10  jmp     short loc_180023D14
0x180023d12  mov     eax, edi
0x180023d14  test    eax, eax
0x180023d16  jz      loc_180023DE8
0x180023d1c  sub     eax, 1
0x180023d1f  jz      short loc_180023D2A
0x180023d21  cmp     eax, 1
0x180023d24  jnz     loc_180023DF3
0x180023d2a  mov     eax, [rsp+0D8h+var_58]
0x180023d31  mov     [rbx+4], eax
0x180023d34  mov     eax, [rsp+0D8h+var_54]
0x180023d3b  mov     [rbx+8], eax
0x180023d3e  mov     eax, [rsp+0D8h+var_50]
0x180023d45  mov     [rbx+0Ch], eax
0x180023d48  lea     rdi, [rbx+10h]
0x180023d4c  mov     r9, rdi
0x180023d4f  mov     r8d, 307h
0x180023d55  mov     rdx, r15
0x180023d58  mov     rcx, [rsp+0D8h+arg_0]; unsigned __int16 *
0x180023d60  call    SymGetEstimatedOriginalFilename
0x180023d65  test    eax, eax
0x180023d67  jz      loc_180023E20
0x180023d6d  test    r14, r14
0x180023d70  jz      short loc_180023D8C
0x180023d72  mov     edx, dword ptr [rsp+0D8h+arg_60]; unsigned __int64
0x180023d79  mov     r8, rdi; unsigned __int16 *
0x180023d7c  mov     rcx, r14; unsigned __int16 *
0x180023d7f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180023d84  test    eax, eax
0x180023d86  js      loc_180023E72
0x180023d8c  cmp     dword ptr [rbx], 2
0x180023d8f  jnz     short loc_180023DCA
0x180023d91  mov     edx, 2Eh ; '.'; Ch
0x180023d96  mov     rcx, rdi; Str
0x180023d99  call    cs:__imp_wcsrchr
0x180023da0  nop     dword ptr [rax+rax+00h]
0x180023da5  test    rax, rax
0x180023da8  jz      short loc_180023DAE
0x180023daa  mov     [rax], r13w
0x180023dae  lea     r8, aDbg; ".dbg"
0x180023db5  mov     edx, 30Ch; unsigned __int64
0x180023dba  mov     rcx, rdi; unsigned __int16 *
0x180023dbd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180023dc2  test    eax, eax
0x180023dc4  js      loc_180023E72
0x180023dca  test    rsi, rsi
0x180023dcd  jz      short loc_180023E1C
0x180023dcf  or      rax, 0FFFFFFFFFFFFFFFFh
0x180023dd3  inc     rax
0x180023dd6  cmp     [rdi+rax*2], r13w
0x180023ddb  jnz     short loc_180023DD3
0x180023ddd  lea     eax, ds:12h[rax*2]
0x180023de4  mov     [rsi], eax
0x180023de6  jmp     short loc_180023E1C
0x180023de8  test    rsi, rsi
0x180023deb  jz      short loc_180023DF3
0x180023ded  mov     dword ptr [rsi], 4
0x180023df3  test    r14, r14
0x180023df6  jz      short loc_180023E1C
0x180023df8  mov     r8d, dword ptr [rsp+0D8h+arg_60]
0x180023e00  test    r8d, r8d
0x180023e03  jz      short loc_180023E1C
0x180023e05  mov     r9, r14
0x180023e08  mov     rdx, r15
0x180023e0b  mov     rcx, [rsp+0D8h+arg_0]; unsigned __int16 *
0x180023e13  call    SymGetEstimatedOriginalFilename
0x180023e18  test    eax, eax
0x180023e1a  jz      short loc_180023E20
0x180023e1c  xor     eax, eax
0x180023e1e  jmp     short loc_180023E72
0x180023e20  mov     rcx, [rsp+0D8h+arg_88]
0x180023e28  test    rcx, rcx
0x180023e2b  jz      short loc_180023E40
0x180023e2d  mov     rax, [rcx]
0x180023e30  lea     rdx, aFailedToObtain; "Failed to obtain the original file name"...
0x180023e37  mov     rax, [rax+8]
0x180023e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e40  mov     eax, 80004005h
0x180023e45  jmp     short loc_180023E72
0x180023e47  mov     rcx, [rsp+0D8h+arg_88]
0x180023e4f  test    rcx, rcx
0x180023e52  jz      short loc_180023E67
0x180023e54  mov     rax, [rcx]
0x180023e57  lea     rdx, aPagingExceptio; "Paging exception occurred while process"...
0x180023e5e  mov     rax, [rax+8]
0x180023e62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e67  mov     ecx, 3E7h; unsigned int
0x180023e6c  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180023e71  nop
0x180023e72  add     rsp, 0A0h
0x180023e79  pop     r15
0x180023e7b  pop     r14
0x180023e7d  pop     r13
0x180023e7f  pop     r12
0x180023e81  pop     rdi
0x180023e82  pop     rsi
0x180023e83  pop     rbx
0x180023e84  retn
0x1800269b6  push    rbp
0x1800269b8  sub     rsp, 70h
0x1800269bc  mov     rbp, rdx
  ... truncated ...
```
