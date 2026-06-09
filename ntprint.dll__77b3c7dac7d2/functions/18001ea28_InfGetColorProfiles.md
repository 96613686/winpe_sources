# InfGetColorProfiles

- ea: `0x18001ea28`
- end: `0x18001ed62`
- name: `InfGetColorProfiles`
- size: `826`
- prototype: `__int64 __usercall@<rax>(HINF InfHandle@<rcx>, PCWSTR Section@<rdx>, __int64, int, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1800217e0`

## callees

- `0x18000d290`
- `0x18000d57c`
- `0x18000d624`
- `0x180019340`
- `0x18001ea28`
- `0x18001ed68`
- `0x18001f5c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eca8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ecc1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ed13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eca8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ecc1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ed13`
- `SETUPAPI!SetupFindFirstLineW` at `0x18001eb2b`
- `SETUPAPI!SetupFindFirstLineW` at `0x18001eb2b`

## string_xrefs

- `0x18001ecf3`: `Invalid Argument: hInf=%p, pszInstallSection=%ws, ppszzColorProfiles=%p, pcchColorProfiles=%p`

## pseudocode

```c
__int64 __fastcall InfGetColorProfiles(
        char *InfHandle,
        PCWSTR Section,
        const WCHAR *a3,
        int a4,
        unsigned int *a5,
        unsigned int a6,
        __int64 a7,
        HLOCAL *a8,
        _DWORD *a9)
{
  char *v9; // r13
  WCHAR *v11; // rsi
  int ColorProfilesFromSection; // ebx
  unsigned int v13; // edx
  __int64 v14; // rcx
  unsigned int v15; // edi
  unsigned __int64 v16; // rdx
  __int64 v17; // r8
  void *v18; // rcx
  unsigned __int64 v19; // r12
  __int16 v20; // r11
  const WCHAR *i; // rdi
  int v22; // edx
  int v24; // [rsp+30h] [rbp-40h] BYREF
  int v25; // [rsp+34h] [rbp-3Ch] BYREF
  unsigned int v26[2]; // [rsp+38h] [rbp-38h] BYREF
  HLOCAL v27; // [rsp+40h] [rbp-30h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-28h] BYREF
  unsigned __int64 v29; // [rsp+50h] [rbp-20h] BYREF
  struct _INFCONTEXT Context; // [rsp+58h] [rbp-18h] BYREF

  v9 = InfHandle;
  v25 = 0;
  hMem = 0;
  v26[0] = 0;
  v29 = 0;
  v11 = 0;
  v27 = 0;
  v24 = 0;
  memset(&Context, 0, sizeof(Context));
  if ( (unsigned __int64)(InfHandle - 1) > 0xFFFFFFFFFFFFFFFDuLL || !Section || !a8 || !a9 )
  {
    ClassInstallerTelemetry::WriteDbgTraceError(
      "InfGetColorProfiles",
      L"Invalid Argument: hInf=%p, pszInstallSection=%ws, ppszzColorProfiles=%p, pcchColorProfiles=%p",
      InfHandle,
      Section,
      a8,
      a9);
    ColorProfilesFromSection = -2147024809;
    goto LABEL_43;
  }
  ClassInstallerTelemetry::WriteDbgTraceInfo("InfGetColorProfiles", L"Building the rest of the color profile list");
  if ( !*a8
    || !*a9
    || (ClassInstallerTelemetry::WriteDbgTraceInfo(
          "InfGetColorProfiles",
          L"Merging existing color profile list into the new list"),
        ColorProfilesFromSection = InfMultiSzMerge(&v27, &v24, *a8, (unsigned int)*a9),
        ColorProfilesFromSection >= 0) )
  {
    if ( !a4 )
    {
      ClassInstallerTelemetry::WriteDbgTraceInfo(
        "InfGetColorProfiles",
        L"Not a package aware inf, searching through sections referenced by the Needs keyword");
      if ( SetupFindFirstLineW(v9, Section, L"Needs", &Context) )
      {
        InfGetMultiSz(&Context, v13, (unsigned __int16 **)&hMem, v26, &v25);
        v11 = (WCHAR *)hMem;
        if ( v25 )
        {
          ColorProfilesFromSection = -2147467259;
          goto LABEL_35;
        }
      }
    }
    ColorProfilesFromSection = InfGetColorProfilesFromSection(v9, Section);
    if ( ColorProfilesFromSection >= 0 )
    {
      if ( !a3 || (ColorProfilesFromSection = InfGetColorProfilesFromSection(v9, a3), ColorProfilesFromSection >= 0) )
      {
        if ( a5 )
        {
          if ( a6 )
          {
            v14 = a7;
            if ( a7 )
            {
              v15 = 0;
              while ( ColorProfilesFromSection >= 0 )
              {
                v16 = v14 + ((unsigned __int64)v15 << 9);
                v17 = *(unsigned __int16 *)(v16 + 510);
                if ( (unsigned int)v17 >= *a5 || (v18 = *(void **)(*((_QWORD *)a5 + 1) + 8 * v17), v18 == (void *)-1LL) )
                  ClassInstallerTelemetry::WriteDbgTraceError(
                    "InfGetColorProfiles",
                    L"Core driver index out of bounds: %d >= %d",
                    v17,
                    *a5);
                else
                  ColorProfilesFromSection = InfGetColorProfilesFromSection(v18, (PCWSTR)v16);
                v14 = a7;
                if ( ++v15 >= a6 )
                {
                  if ( ColorProfilesFromSection < 0 )
                    goto LABEL_35;
                  v9 = InfHandle;
                  goto LABEL_28;
                }
              }
              goto LABEL_35;
            }
          }
          v9 = InfHandle;
        }
LABEL_28:
        if ( !v11 )
        {
LABEL_38:
          v22 = v24;
          if ( v24 )
          {
            if ( *a8 )
            {
              LocalFree(*a8);
              v22 = v24;
            }
            *a8 = v27;
            *a9 = v22;
            goto LABEL_46;
          }
          goto LABEL_43;
        }
        v19 = v26[0];
        v20 = 0;
        if ( v26[0] )
        {
          for ( i = v11; *i != v20; i += v29 + 1 )
          {
            ColorProfilesFromSection = InfGetColorProfilesFromSection(v9, i);
            if ( ColorProfilesFromSection < 0 )
              break;
            ColorProfilesFromSection = StringCchLengthW(i, v19, &v29);
            if ( ColorProfilesFromSection < 0 )
              break;
          }
        }
      }
    }
LABEL_35:
    if ( v11 )
      LocalFree(v11);
    if ( ColorProfilesFromSection < 0 )
      goto LABEL_43;
    goto LABEL_38;
  }
LABEL_43:
  if ( v27 )
  {
    LocalFree(v27);
    v27 = 0;
  }
  v24 = 0;
  if ( ColorProfilesFromSection < 0 )
  {
    ClassInstallerTelemetry::WriteDbgTraceError(
      "InfGetColorProfiles",
      L"Error merging color profile file lists: hr: 0x%x",
      (unsigned int)ColorProfilesFromSection);
    return (unsigned int)ColorProfilesFromSection;
  }
LABEL_46:
  ClassInstallerTelemetry::WriteDbgTraceInfo("InfGetColorProfiles", L"Successfully merged color profile file lists");
  return (unsigned int)ColorProfilesFromSection;
}

```

## disassembly

```asm
0x18001ea28  mov     rax, rsp
0x18001ea2b  mov     [rax+10h], rbx
0x18001ea2f  mov     [rax+20h], r9d
0x18001ea33  mov     [rax+18h], r8
0x18001ea37  mov     [rax+8], rcx
0x18001ea3b  push    rbp
0x18001ea3c  push    rsi
0x18001ea3d  push    rdi
0x18001ea3e  push    r12
0x18001ea40  push    r13
0x18001ea42  push    r14
0x18001ea44  push    r15
0x18001ea46  mov     rbp, rsp
0x18001ea49  sub     rsp, 70h
0x18001ea4d  mov     r15, [rbp+arg_38]
0x18001ea51  xor     eax, eax
0x18001ea53  mov     r12, [rbp+arg_40]
0x18001ea5a  mov     r13, rcx
0x18001ea5d  xor     ecx, ecx
0x18001ea5f  mov     qword ptr [rbp+Context.Section], rax
0x18001ea63  xorps   xmm0, xmm0
0x18001ea66  mov     [rbp+var_3C], ecx
0x18001ea69  mov     rdi, rdx
0x18001ea6c  mov     [rbp+hMem], rcx
0x18001ea70  lea     rax, [r13-1]
0x18001ea74  mov     [rbp+var_38], ecx
0x18001ea77  mov     [rbp+var_20], rcx
0x18001ea7b  mov     esi, ecx
0x18001ea7d  mov     [rbp+var_30], rcx
0x18001ea81  mov     [rbp+var_40], ecx
0x18001ea84  movups  xmmword ptr [rbp+Context.Inf], xmm0
0x18001ea88  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001ea8c  ja      loc_18001ECDC
0x18001ea92  test    rdx, rdx
0x18001ea95  jz      loc_18001ECDC
0x18001ea9b  test    r15, r15
0x18001ea9e  jz      loc_18001ECDC
0x18001eaa4  test    r12, r12
0x18001eaa7  jz      loc_18001ECDC
0x18001eaad  mov     ebx, ecx
0x18001eaaf  lea     r14, aInfgetcolorpro_0; "InfGetColorProfiles"
0x18001eab6  mov     rcx, r14; char *
0x18001eab9  lea     rdx, aBuildingTheRes; "Building the rest of the color profile "...
0x18001eac0  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001eac5  cmp     [r15], rbx
0x18001eac8  jz      short loc_18001EB02
0x18001eaca  cmp     [r12], ebx
0x18001eace  jz      short loc_18001EB02
0x18001ead0  lea     rdx, aMergingExistin; "Merging existing color profile list int"...
0x18001ead7  mov     rcx, r14; char *
0x18001eada  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001eadf  mov     r9d, [r12]
0x18001eae3  lea     rdx, [rbp+var_40]
0x18001eae7  mov     r8, [r15]
0x18001eaea  lea     rcx, [rbp+var_30]
0x18001eaee  call    InfMultiSzMerge
0x18001eaf3  xor     r12d, r12d
0x18001eaf6  mov     ebx, eax
0x18001eaf8  test    eax, eax
0x18001eafa  js      loc_18001ED0A
0x18001eb00  jmp     short loc_18001EB05
0x18001eb02  xor     r12d, r12d
0x18001eb05  cmp     [rbp+arg_18], r12d
0x18001eb09  jnz     short loc_18001EB63
0x18001eb0b  lea     rdx, aNotAPackageAwa; "Not a package aware inf, searching thro"...
0x18001eb12  mov     rcx, r14; char *
0x18001eb15  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001eb1a  lea     r9, [rbp+Context]; Context
0x18001eb1e  mov     rdx, rdi; Section
0x18001eb21  lea     r8, aNeeds; "Needs"
0x18001eb28  mov     rcx, r13; InfHandle
0x18001eb2b  call    cs:__imp_SetupFindFirstLineW
0x18001eb31  test    eax, eax
0x18001eb33  jz      short loc_18001EB63
0x18001eb35  lea     rax, [rbp+var_3C]
0x18001eb39  lea     r9, [rbp+var_38]; unsigned int *
0x18001eb3d  mov     [rsp+70h+var_50], rax; int *
0x18001eb42  lea     r8, [rbp+hMem]; unsigned __int16 **
0x18001eb46  lea     rcx, [rbp+Context]; Context
0x18001eb4a  call    ?InfGetMultiSz@@YAXPEAU_INFCONTEXT@@KPEAPEAGPEAKPEAH@Z; InfGetMultiSz(_INFCONTEXT *,ulong,ushort * *,ulong *,int *)
0x18001eb4f  mov     rsi, [rbp+hMem]
0x18001eb53  cmp     [rbp+var_3C], r12d
0x18001eb57  jz      short loc_18001EB63
0x18001eb59  mov     ebx, 80004005h
0x18001eb5e  jmp     loc_18001ECA0
0x18001eb63  test    ebx, ebx
0x18001eb65  js      loc_18001ECA0
0x18001eb6b  lea     r9, [rbp+var_40]
0x18001eb6f  mov     rdx, rdi; Section
0x18001eb72  lea     r8, [rbp+var_30]
0x18001eb76  mov     rcx, r13; InfHandle
0x18001eb79  call    InfGetColorProfilesFromSection
0x18001eb7e  mov     ebx, eax
0x18001eb80  test    eax, eax
0x18001eb82  js      loc_18001ECA0
0x18001eb88  mov     rax, [rbp+Section]
0x18001eb8c  test    rax, rax
0x18001eb8f  jz      short loc_18001EBAE
0x18001eb91  lea     r9, [rbp+var_40]
0x18001eb95  mov     rdx, rax; Section
0x18001eb98  lea     r8, [rbp+var_30]
0x18001eb9c  mov     rcx, r13; InfHandle
0x18001eb9f  call    InfGetColorProfilesFromSection
0x18001eba4  mov     ebx, eax
0x18001eba6  test    eax, eax
0x18001eba8  js      loc_18001ECA0
0x18001ebae  mov     r12, [rbp+arg_20]
0x18001ebb2  xor     edx, edx
0x18001ebb4  test    r12, r12
0x18001ebb7  jz      loc_18001EC41
0x18001ebbd  mov     r13d, [rbp+arg_28]
0x18001ebc1  test    r13d, r13d
0x18001ebc4  jz      short loc_18001EC3D
0x18001ebc6  mov     rcx, [rbp+arg_30]
0x18001ebca  test    rcx, rcx
0x18001ebcd  jz      short loc_18001EC3D
0x18001ebcf  mov     edi, edx
0x18001ebd1  test    ebx, ebx
0x18001ebd3  js      loc_18001EC9D
0x18001ebd9  mov     edx, edi
0x18001ebdb  shl     rdx, 9
0x18001ebdf  add     rdx, rcx; Section
0x18001ebe2  movzx   r8d, word ptr [rdx+1FEh]
0x18001ebea  cmp     r8d, [r12]
0x18001ebee  jnb     short loc_18001EC10
0x18001ebf0  mov     rax, [r12+8]
0x18001ebf5  mov     rcx, [rax+r8*8]; InfHandle
0x18001ebf9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001ebfd  jz      short loc_18001EC10
0x18001ebff  lea     r9, [rbp+var_40]
0x18001ec03  lea     r8, [rbp+var_30]
0x18001ec07  call    InfGetColorProfilesFromSection
0x18001ec0c  mov     ebx, eax
0x18001ec0e  jmp     short loc_18001EC23
0x18001ec10  mov     r9d, [r12]
0x18001ec14  lea     rdx, aCoreDriverInde; "Core driver index out of bounds: %d >= "...
0x18001ec1b  mov     rcx, r14; char *
0x18001ec1e  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18001ec23  mov     rcx, [rbp+arg_30]
0x18001ec27  inc     edi
0x18001ec29  mov     eax, ebx
0x18001ec2b  cmp     edi, r13d
0x18001ec2e  jb      short loc_18001EBD1
0x18001ec30  xor     r12d, r12d
0x18001ec33  test    eax, eax
0x18001ec35  js      short loc_18001ECA0
0x18001ec37  mov     r13, [rbp+InfHandle]
0x18001ec3b  jmp     short loc_18001EC44
0x18001ec3d  mov     r13, [rbp+InfHandle]
0x18001ec41  xor     r12d, r12d
0x18001ec44  test    rsi, rsi
0x18001ec47  jz      short loc_18001ECB2
0x18001ec49  mov     r12d, [rbp+var_38]
0x18001ec4d  xor     r11d, r11d
0x18001ec50  test    r12d, r12d
0x18001ec53  jz      short loc_18001EC9D
0x18001ec55  mov     rdi, rsi
0x18001ec58  cmp     [rdi], r11w
0x18001ec5c  jz      short loc_18001EC9D
0x18001ec5e  lea     r9, [rbp+var_40]
0x18001ec62  mov     rdx, rdi; Section
0x18001ec65  lea     r8, [rbp+var_30]
0x18001ec69  mov     rcx, r13; InfHandle
0x18001ec6c  call    InfGetColorProfilesFromSection
0x18001ec71  xor     r11d, r11d
0x18001ec74  mov     ebx, eax
0x18001ec76  test    eax, eax
0x18001ec78  js      short loc_18001EC9D
0x18001ec7a  mov     rdx, r12; unsigned __int64
0x18001ec7d  lea     r8, [rbp+var_20]; unsigned __int64 *
0x18001ec81  mov     rcx, rdi; unsigned __int16 *
0x18001ec84  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001ec89  mov     ebx, eax
0x18001ec8b  test    eax, eax
0x18001ec8d  js      short loc_18001EC9D
0x18001ec8f  mov     rax, [rbp+var_20]
0x18001ec93  lea     rdi, [rdi+rax*2]
0x18001ec97  add     rdi, 2
0x18001ec9b  jmp     short loc_18001EC58
0x18001ec9d  xor     r12d, r12d
0x18001eca0  test    rsi, rsi
0x18001eca3  jz      short loc_18001ECAE
0x18001eca5  mov     rcx, rsi; hMem
0x18001eca8  call    cs:__imp_LocalFree
0x18001ecae  test    ebx, ebx
0x18001ecb0  js      short loc_18001ED0A
0x18001ecb2  mov     edx, [rbp+var_40]
0x18001ecb5  test    edx, edx
0x18001ecb7  jz      short loc_18001ED0A
0x18001ecb9  mov     rcx, [r15]; hMem
0x18001ecbc  test    rcx, rcx
0x18001ecbf  jz      short loc_18001ECCA
0x18001ecc1  call    cs:__imp_LocalFree
0x18001ecc7  mov     edx, [rbp+var_40]
0x18001ecca  mov     rax, [rbp+var_30]
0x18001ecce  mov     [r15], rax
0x18001ecd1  mov     rax, [rbp+arg_40]
0x18001ecd8  mov     [rax], edx
0x18001ecda  jmp     short loc_18001ED25
0x18001ecdc  lea     r14, aInfgetcolorpro_0; "InfGetColorProfiles"
0x18001ece3  mov     [rsp+70h+var_48], r12
0x18001ece8  mov     rcx, r14; char *
0x18001eceb  mov     [rsp+70h+var_50], r15
0x18001ecf0  mov     r9, rdi
0x18001ecf3  lea     rdx, aInvalidArgumen_7; "Invalid Argument: hInf=%p, pszInstallSe"...
0x18001ecfa  mov     r8, r13
0x18001ecfd  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18001ed02  xor     r12d, r12d
0x18001ed05  mov     ebx, 80070057h
0x18001ed0a  mov     rcx, [rbp+var_30]; hMem
0x18001ed0e  test    rcx, rcx
0x18001ed11  jz      short loc_18001ED1D
0x18001ed13  call    cs:__imp_LocalFree
0x18001ed19  mov     [rbp+var_30], r12
0x18001ed1d  mov     [rbp+var_40], r12d
0x18001ed21  test    ebx, ebx
0x18001ed23  js      short loc_18001ED36
0x18001ed25  lea     rdx, aSuccessfullyMe; "Successfully merged color profile file "...
0x18001ed2c  mov     rcx, r14; char *
0x18001ed2f  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001ed34  jmp     short loc_18001ED48
0x18001ed36  mov     r8d, ebx
0x18001ed39  lea     rdx, aErrorMergingCo; "Error merging color profile file lists:"...
0x18001ed40  mov     rcx, r14; char *
0x18001ed43  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18001ed48  mov     eax, ebx
0x18001ed4a  mov     rbx, [rsp+70h+arg_8]
0x18001ed52  add     rsp, 70h
0x18001ed56  pop     r15
0x18001ed58  pop     r14
0x18001ed5a  pop     r13
0x18001ed5c  pop     r12
0x18001ed5e  pop     rdi
0x18001ed5f  pop     rsi
0x18001ed60  pop     rbp
0x18001ed61  retn
```
