# EnumResourceNamesInternal

- ea: `0x18007d490`
- end: `0x18007ea3d`
- name: `EnumResourceNamesInternal`
- size: `5549`
- prototype: `__int64 __usercall@<rax>(PVOID BaseAddress@<rcx>, ULONG ResultSize, __int16, int)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x18007cfb0`
- `0x180110740`
- `0x180180490`

## callees

- `0x18004b9d0`
- `0x18007d490`
- `0x18007ebd0`
- `0x18007ed30`
- `0x18007ed68`
- `0x18007fa14`
- `0x180194eb9`
- `0x1801a4010`

## import_xrefs

- `ntdll!wcslen` at `0x18007e084`
- `ntdll!wcslen` at `0x18007e084`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18007e313`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18007e313`
- `ntdll!RtlFreeHeap` at `0x18007d91c`
- `ntdll!RtlFreeHeap` at `0x18007dd0d`
- `ntdll!RtlFreeHeap` at `0x18007dfce`
- `ntdll!RtlFreeHeap` at `0x18007e0c9`
- `ntdll!RtlFreeHeap` at `0x18007e15e`
- `ntdll!RtlFreeHeap` at `0x18007e3da`
- `ntdll!RtlFreeHeap` at `0x18007e413`
- `ntdll!RtlFreeHeap` at `0x18007e438`
- `ntdll!RtlFreeHeap` at `0x18007e45d`
- `ntdll!RtlFreeHeap` at `0x1801955ca`
- `ntdll!RtlFreeHeap` at `0x1801955f6`
- `ntdll!RtlFreeHeap` at `0x180195626`
- `ntdll!RtlFreeHeap` at `0x180195655`
- `ntdll!RtlFreeHeap` at `0x18007d91c`
- `ntdll!RtlFreeHeap` at `0x18007dd0d`
- `ntdll!RtlFreeHeap` at `0x18007dfce`
- `ntdll!RtlFreeHeap` at `0x18007e0c9`
- `ntdll!RtlFreeHeap` at `0x18007e15e`
- `ntdll!RtlFreeHeap` at `0x18007e3da`
- `ntdll!RtlFreeHeap` at `0x18007e413`
- `ntdll!RtlFreeHeap` at `0x18007e438`
- `ntdll!RtlFreeHeap` at `0x18007e45d`
- `ntdll!RtlFreeHeap` at `0x1801955ca`
- `ntdll!RtlFreeHeap` at `0x1801955f6`
- `ntdll!RtlFreeHeap` at `0x180195626`
- `ntdll!RtlFreeHeap` at `0x180195655`
- `ntdll!LdrResGetRCConfig` at `0x18007e727`
- `ntdll!LdrResGetRCConfig` at `0x18007e7c3`
- `ntdll!LdrResGetRCConfig` at `0x18007e8a5`
- `ntdll!LdrResGetRCConfig` at `0x18007e8c6`
- `ntdll!LdrResGetRCConfig` at `0x18007e727`
- `ntdll!LdrResGetRCConfig` at `0x18007e7c3`
- `ntdll!LdrResGetRCConfig` at `0x18007e8a5`
- `ntdll!LdrResGetRCConfig` at `0x18007e8c6`
- `ntdll!LdrpResGetResourceDirectory` at `0x18007e56e`
- `ntdll!LdrpResGetResourceDirectory` at `0x18007e679`
- `ntdll!LdrpResGetResourceDirectory` at `0x18007e991`
- `ntdll!LdrpResGetResourceDirectory` at `0x18007e9c9`
- `ntdll!LdrpResGetResourceDirectory` at `0x18007e56e`
- `ntdll!LdrpResGetResourceDirectory` at `0x18007e679`
- `ntdll!LdrpResGetResourceDirectory` at `0x18007e991`
- `ntdll!LdrpResGetResourceDirectory` at `0x18007e9c9`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18007e842`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18007e906`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18007e842`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18007e906`
- `ntdll!LdrLoadAlternateResourceModule` at `0x18007e4c4`
- `ntdll!LdrLoadAlternateResourceModule` at `0x18007e611`
- `ntdll!LdrLoadAlternateResourceModule` at `0x18007e4c4`
- `ntdll!LdrLoadAlternateResourceModule` at `0x18007e611`
- `ntdll!LdrRscIsTypeExist` at `0x18007e75c`
- `ntdll!LdrRscIsTypeExist` at `0x18007e7fe`
- `ntdll!LdrRscIsTypeExist` at `0x18007e75c`
- `ntdll!LdrRscIsTypeExist` at `0x18007e7fe`
- `ntdll!LdrLoadAlternateResourceModuleEx` at `0x18007e93e`
- `ntdll!LdrLoadAlternateResourceModuleEx` at `0x18007e93e`
- `ntdll!LdrpResGetMappingSize` at `0x18007e502`
- `ntdll!LdrpResGetMappingSize` at `0x18007e87e`
- `ntdll!LdrpResGetMappingSize` at `0x18007e502`
- `ntdll!LdrpResGetMappingSize` at `0x18007e87e`
- `ntdll!RtlAllocateHeap` at `0x18007dd6d`
- `ntdll!RtlAllocateHeap` at `0x18007e02b`
- `ntdll!RtlAllocateHeap` at `0x18007e112`
- `ntdll!RtlAllocateHeap` at `0x18007dd6d`
- `ntdll!RtlAllocateHeap` at `0x18007e02b`
- `ntdll!RtlAllocateHeap` at `0x18007e112`

## pseudocode

```c
__int64 EnumResourceNamesInternal(
        PVOID BaseAddress,
        WCHAR *a2,
        unsigned int (__fastcall *a3)(PVOID, PVOID, __int64, __int64),
        __int64 a4,
        ...)
{
  int ResourceDirectory; // r15d
  unsigned int v6; // ebx
  int v7; // r14d
  int v8; // edi
  __int64 v9; // r12
  PVOID ImageBaseAddress; // r13
  int Resource; // edx
  __int64 v12; // rcx
  unsigned __int16 *v13; // rdi
  __int64 v14; // rsi
  void *v15; // r15
  const wchar_t *v16; // r13
  unsigned int v17; // r10d
  unsigned int v18; // r11d
  unsigned __int64 v19; // rbx
  unsigned __int64 v20; // r9
  unsigned int v21; // ebx
  unsigned __int64 v22; // r14
  __int64 v23; // rdx
  __int64 v24; // rcx
  int v25; // eax
  unsigned __int64 v26; // r8
  ULONG v27; // r10d
  __int64 v28; // rcx
  unsigned int v29; // r12d
  unsigned __int16 v30; // ax
  bool v31; // zf
  int v32; // r15d
  const wchar_t *v33; // r15
  __int64 v34; // rax
  unsigned __int64 v35; // r8
  __int64 v36; // r15
  char *v37; // r15
  unsigned __int64 v38; // rcx
  unsigned __int64 v39; // rdx
  unsigned __int64 v40; // rdx
  unsigned __int64 v41; // r8
  unsigned __int64 v42; // rdx
  PVOID v43; // rax
  const wchar_t *v44; // r10
  int v45; // eax
  unsigned __int64 v46; // rcx
  __int64 v47; // rax
  unsigned __int64 v48; // kr10_8
  int v49; // eax
  NTSTATUS v50; // eax
  __int64 v51; // r15
  char *v52; // r15
  unsigned __int64 v53; // rcx
  unsigned __int64 v54; // rdx
  unsigned __int64 v55; // rdx
  unsigned __int64 v56; // r8
  unsigned __int64 v57; // rdx
  unsigned __int16 v58; // ax
  const wchar_t *v59; // rcx
  int v60; // edx
  int v61; // r8d
  PVOID Heap; // rax
  int v63; // eax
  __int64 v64; // rcx
  ULONG v65; // eax
  ULONG v66; // r15d
  PVOID v67; // rcx
  __int64 v68; // rax
  unsigned __int64 v69; // r8
  unsigned __int16 v70; // ax
  __int64 v72; // r9
  __int64 v73; // r12
  int v74; // eax
  __int64 v75; // r9
  __int64 v76; // rdi
  __int64 v77; // r12
  int RCConfig; // eax
  int IsTypeExist; // eax
  int v80; // eax
  int UnicodeSize; // [rsp+20h] [rbp-158h]
  WCHAR *v82; // [rsp+38h] [rbp-140h]
  PVOID v83; // [rsp+40h] [rbp-138h]
  __int64 v84; // [rsp+48h] [rbp-130h]
  ULONG Size; // [rsp+58h] [rbp-120h] BYREF
  int v86; // [rsp+5Ch] [rbp-11Ch]
  unsigned int *v87; // [rsp+60h] [rbp-118h] BYREF
  PVOID P; // [rsp+68h] [rbp-110h]
  WCHAR Buffer[4]; // [rsp+70h] [rbp-108h] BYREF
  WCHAR v90[4]; // [rsp+78h] [rbp-100h] BYREF
  int v91; // [rsp+80h] [rbp-F8h] BYREF
  unsigned __int64 v92; // [rsp+88h] [rbp-F0h] BYREF
  unsigned __int64 v93; // [rsp+90h] [rbp-E8h] BYREF
  SIZE_T v94; // [rsp+98h] [rbp-E0h] BYREF
  unsigned __int64 v95; // [rsp+A0h] [rbp-D8h]
  __int64 v96; // [rsp+A8h] [rbp-D0h] BYREF
  __int64 v97; // [rsp+B0h] [rbp-C8h] BYREF
  unsigned int v98; // [rsp+B8h] [rbp-C0h]
  PVOID v99; // [rsp+C0h] [rbp-B8h]
  unsigned int *v100; // [rsp+C8h] [rbp-B0h] BYREF
  ULONG v101; // [rsp+D0h] [rbp-A8h]
  char *v102; // [rsp+D8h] [rbp-A0h] BYREF
  char *v103; // [rsp+E0h] [rbp-98h] BYREF
  ULONG v104; // [rsp+E8h] [rbp-90h]
  unsigned int *v105; // [rsp+F0h] [rbp-88h]
  unsigned __int16 *v106; // [rsp+F8h] [rbp-80h]
  unsigned int v107; // [rsp+100h] [rbp-78h]
  unsigned int v108; // [rsp+104h] [rbp-74h]
  const wchar_t *v109; // [rsp+108h] [rbp-70h]
  __int64 v110; // [rsp+110h] [rbp-68h]
  __int64 v111; // [rsp+118h] [rbp-60h]
  __int64 v112; // [rsp+120h] [rbp-58h]
  __int64 v113; // [rsp+128h] [rbp-50h]
  __int64 v114; // [rsp+130h] [rbp-48h]
  __int64 ResultSize; // [rsp+1A0h] [rbp+28h] BYREF
  va_list ResultSizea; // [rsp+1A0h] [rbp+28h]
  __int64 v121; // [rsp+1A8h] [rbp+30h]
  __int64 v122; // [rsp+1B0h] [rbp+38h]
  va_list va1; // [rsp+1B8h] [rbp+40h] BYREF

  va_start(va1, a4);
  va_start(ResultSizea, a4);
  ResultSize = va_arg(va1, _QWORD);
  v121 = va_arg(va1, _QWORD);
  v122 = va_arg(va1, _QWORD);
  ResourceDirectory = 0;
  v92 = 0;
  v93 = 0;
  v103 = 0;
  v102 = 0;
  v82 = 0;
  v104 = 0;
  v101 = 0;
  *(_QWORD *)v90 = 0;
  Size = 0;
  v97 = 0;
  v96 = 0;
  v100 = 0;
  v91 = 0;
  v6 = ResultSize;
  if ( (ResultSize & 0xFFFFFFE4) != 0 )
    goto LABEL_208;
  v7 = ResultSize & 8;
  v8 = ResultSize & 0x10;
  if ( (ResultSize & 0x17) == 0 )
    v6 = ResultSize | 3;
  if ( (ResultSize & 6) == 6 )
    goto LABEL_208;
  if ( (ResultSize & 0x10) != 0 )
  {
    if ( (ResultSize & 7) != 0 )
      goto LABEL_208;
    v6 = v6 & 0xFFFFFFEE | 1;
  }
  v9 = BaseDllMapResourceIdW(a2);
  v84 = v9;
  if ( v9 == -1 )
  {
LABEL_208:
    v12 = 3221225485LL;
LABEL_209:
    BaseSetLastNTError(v12);
    return 0;
  }
  if ( BaseAddress )
    ImageBaseAddress = BaseAddress;
  else
    ImageBaseAddress = NtCurrentPeb()->ImageBaseAddress;
  v95 = (unsigned __int64)ImageBaseAddress;
  if ( v8 )
    goto LABEL_10;
  if ( !v7 )
  {
    RCConfig = LdrResGetRCConfig(ImageBaseAddress, 0, &v100, 0x2000, 1);
    goto LABEL_247;
  }
  RCConfig = LdrResGetRCConfig(ImageBaseAddress, 0, &v100, 0, 1);
  if ( RCConfig != -1073020925 )
  {
LABEL_247:
    if ( RCConfig >= 0 )
    {
      IsTypeExist = LdrRscIsTypeExist(v100, v9, 0, &v91);
      if ( IsTypeExist < 0 )
      {
        BaseSetLastNTError((unsigned int)IsTypeExist);
        return 0;
      }
    }
  }
LABEL_10:
  if ( (v6 & 2) == 0 )
    goto LABEL_11;
  if ( !v100 || (v100[4] & 1) == 0 )
    goto LABEL_250;
  if ( (v91 & 0x20000) != 0 )
  {
    ResourceDirectory = -1073741686;
    goto LABEL_11;
  }
  v74 = (_WORD)v121
      ? LdrLoadAlternateResourceModuleEx(ImageBaseAddress, (unsigned __int16)v121, v90, 0, 128)
      : LdrLoadAlternateResourceModule(ImageBaseAddress, v90);
  if ( v74 < 0 )
  {
LABEL_250:
    ResourceDirectory = -1073020927;
    goto LABEL_11;
  }
  if ( v7 )
  {
    LOBYTE(v75) = 1;
    if ( (int)LdrpResGetMappingSize(*(_QWORD *)v90, &v97, 256, v75) < 0 )
      v97 = 0;
  }
  v76 = *(_QWORD *)v90;
  *(_QWORD *)Buffer = 0;
  if ( !*(_QWORD *)v90 )
  {
    ResourceDirectory = -1073741811;
    goto LABEL_11;
  }
  if ( (v6 & 8) != 0 )
  {
    v77 = v97;
    if ( !v97 )
    {
      ResourceDirectory = -1073741811;
      v9 = v84;
      goto LABEL_11;
    }
    ResourceDirectory = LdrpResGetResourceDirectory(*(_QWORD *)v90, v97, 4096, &v102, Buffer);
    if ( ResourceDirectory == -1073741686 )
      ResourceDirectory = LdrpResGetResourceDirectory(v76, v77, 0, &v102, Buffer);
    v9 = v84;
  }
  else
  {
    v102 = (char *)RtlImageDirectoryEntryToData(*(PVOID *)v90, 1u, 2u, &Size);
    ResourceDirectory = -1073741687;
    if ( v102 )
      ResourceDirectory = 0;
  }
  if ( ResourceDirectory >= 0 )
    ResourceDirectory = EnumFindResource(*(_DWORD *)v90, v9, 0, 0, v6 | 0x200, (__int64)&v93);
LABEL_11:
  Resource = 0;
  if ( (v6 & 1) == 0 )
    goto LABEL_12;
  *(_QWORD *)Buffer = 0;
  v87 = 0;
  LODWORD(ResultSize) = 0;
  if ( LdrLoadAlternateResourceModule(ImageBaseAddress, Buffer) >= 0 )
  {
    ImageBaseAddress = *(PVOID *)Buffer;
    v95 = *(_QWORD *)Buffer;
    if ( !*(_QWORD *)Buffer )
    {
      ImageBaseAddress = NtCurrentPeb()->ImageBaseAddress;
      v95 = (unsigned __int64)ImageBaseAddress;
    }
    if ( (v6 & 0x10) == 0 )
    {
      LOBYTE(UnicodeSize) = 1;
      if ( (v6 & 8) != 0 )
      {
        v80 = LdrResGetRCConfig(ImageBaseAddress, 0, &v87, 0, UnicodeSize);
        if ( v80 == -1073020925 )
          goto LABEL_211;
      }
      else
      {
        v80 = LdrResGetRCConfig(ImageBaseAddress, 0, &v87, 0x2000, UnicodeSize);
      }
      if ( v80 >= 0 )
      {
        if ( v9 )
        {
          if ( (int)LdrRscIsTypeExist(v87, v9, 0, (__int64 *)ResultSizea) >= 0 )
          {
            v100 = v87;
            v91 = ResultSize;
          }
        }
        else
        {
          v100 = v87;
        }
      }
    }
  }
LABEL_211:
  if ( (v91 & 0x40000) != 0 )
  {
    Resource = -1073741686;
  }
  else
  {
    if ( v7 )
    {
      LOBYTE(v72) = 1;
      if ( (int)LdrpResGetMappingSize(ImageBaseAddress, &v96, 256, v72) < 0 )
        v96 = 0;
    }
    v94 = 0;
    if ( ImageBaseAddress )
    {
      if ( (v6 & 8) != 0 )
      {
        v73 = v96;
        if ( !v96 )
        {
          Resource = -1073741811;
          v9 = v84;
          goto LABEL_12;
        }
        Resource = LdrpResGetResourceDirectory(ImageBaseAddress, v96, 4096, &v103, &v94);
        if ( Resource == -1073741686 )
          Resource = LdrpResGetResourceDirectory(ImageBaseAddress, v73, 0, &v103, &v94);
      }
      else
      {
        v103 = (char *)RtlImageDirectoryEntryToData(ImageBaseAddress, 1u, 2u, &Size);
        Resource = -1073741687;
        if ( v103 )
          Resource = 0;
      }
      v9 = v84;
      if ( Resource >= 0 )
        Resource = EnumFindResource((_DWORD)ImageBaseAddress, v84, 0, 0, v6 | 0x200, (__int64)&v92);
    }
    else
    {
      Resource = -1073741811;
    }
  }
LABEL_12:
  if ( (v6 & 1) != 0 && (v6 & 2) != 0 && ResourceDirectory < 0 && Resource < 0 )
  {
    v12 = (unsigned int)Resource;
  }
  else
  {
    v12 = 0;
    if ( (v6 & 1) != 0 && (~(_BYTE)v6 & 2) != 0 && Resource < 0 )
      v12 = (unsigned int)Resource;
  }
  if ( (v6 & 1) == 0 && (v6 & 2) != 0 && ResourceDirectory < 0 )
    v12 = (unsigned int)ResourceDirectory;
  if ( (int)v12 < 0 )
    goto LABEL_209;
  v13 = 0;
  v87 = 0;
  v14 = 0;
  P = 0;
  v15 = 0;
  v83 = 0;
  v16 = 0;
  v17 = 0;
  *(_QWORD *)Buffer = 0;
  v18 = 0;
  v94 = 0;
  v99 = 0;
  v19 = 0;
  v20 = v93;
  if ( v93 )
  {
    if ( v7 )
    {
      v19 = v93 + 16;
      if ( v93 + 16 < v93
        || v19 < (*(_QWORD *)v90 & 0xFFFFFFFFFFFFFFFCuLL)
        || v19 > v97 + (*(_QWORD *)v90 & 0xFFFFFFFFFFFFFFFCuLL) )
      {
        goto LABEL_21;
      }
    }
    v87 = (unsigned int *)(v93 + 16);
    v105 = (unsigned int *)(v93 + 16);
  }
  v26 = v92;
  if ( v92 )
  {
    if ( v7 )
    {
      v19 = v92 + 16;
      if ( v92 + 16 < v92 || v19 < (v95 & 0xFFFFFFFFFFFFFFFCuLL) || v19 > v96 + (v95 & 0xFFFFFFFFFFFFFFFCuLL) )
      {
LABEL_21:
        BaseSetLastNTError(3221225595LL);
        v21 = 0;
        v22 = 0;
        goto LABEL_199;
      }
    }
    v13 = (unsigned __int16 *)(v92 + 16);
    v106 = (unsigned __int16 *)(v92 + 16);
  }
  Size = 0;
  v29 = 0;
  v98 = 0;
  if ( v7 )
  {
    if ( v93 )
    {
      v58 = *(_WORD *)(v93 + 12);
      if ( v58 )
      {
        v111 = 0;
        v19 = 8LL * v58;
        if ( !is_mul_ok(v58, 8u)
          || v19 + v93 < (*(_QWORD *)v90 & 0xFFFFFFFFFFFFFFFCuLL)
          || v19 + v93 > (*(_QWORD *)v90 & 0xFFFFFFFFFFFFFFFCuLL) + v97 )
        {
          goto LABEL_117;
        }
        v17 = *(_DWORD *)Buffer;
      }
    }
    if ( v92 )
    {
      v30 = *(_WORD *)(v92 + 12);
      if ( v30 )
      {
        v112 = 0;
        v48 = v30;
        v47 = 8LL * v30;
        v19 = v47;
        if ( !is_mul_ok(v48, 8u)
          || v47 + v92 < (v95 & 0xFFFFFFFFFFFFFFFCuLL)
          || v47 + v92 > v96 + (v95 & 0xFFFFFFFFFFFFFFFCuLL) )
        {
LABEL_117:
          BaseSetLastNTError(3221225595LL);
          v21 = 0;
          v9 = v84;
          v22 = 0;
          goto LABEL_199;
        }
      }
    }
  }
  v31 = (v122 & 1) == 0;
  v32 = v122 & 1;
  LODWORD(v122) = v32;
  if ( v31 )
    goto LABEL_65;
  if ( ((unsigned __int64)a2 & 0xFFFFFFFFFFFF0000uLL) != 0 )
  {
    v50 = ConverStringWithHeapAlloc(a2);
    if ( v50 >= 0 )
      goto LABEL_126;
    goto LABEL_129;
  }
  v82 = a2;
  while ( 1 )
  {
LABEL_65:
    if ( (!v20 || Size >= *(unsigned __int16 *)(v20 + 12)) && (!v26 || v29 >= *(unsigned __int16 *)(v26 + 12)) )
      goto LABEL_102;
    if ( v20 && Size < *(unsigned __int16 *)(v20 + 12) )
    {
      if ( v7 )
      {
        v68 = *v87;
        LODWORD(v68) = v68 & 0x7FFFFFFF;
        v19 = (unsigned __int64)&v102[v68 + 4];
        if ( v19 < (unsigned __int64)v102
          || (v69 = (unsigned __int64)&v102[v68 + 4], v69 < (*(_QWORD *)v90 & 0xFFFFFFFFFFFFFFFCuLL))
          || v69 > v97 + (*(_QWORD *)v90 & 0xFFFFFFFFFFFFFFFCuLL) )
        {
LABEL_169:
          BaseSetLastNTError(3221225595LL);
          v21 = 0;
          v15 = v83;
          v9 = v84;
          v22 = (unsigned __int64)v82;
          goto LABEL_199;
        }
      }
      v51 = *v87;
      LODWORD(v51) = v51 & 0x7FFFFFFF;
      v52 = &v102[v51];
      if ( v7 )
      {
        v53 = *(unsigned __int16 *)v52;
        v54 = v53 + 1;
        if ( v53 + 1 < v53
          || (v113 = 0, v19 = 2 * v54, !is_mul_ok(v54, 2u))
          || (v55 = Size & 0xFFFFFFFC, v56 = Size + v53, v56 < v55)
          || v56 > v55 + 260 )
        {
LABEL_125:
          BaseSetLastNTError(3221225595LL);
          goto LABEL_53;
        }
        v57 = (unsigned __int64)&v52[v19 + 2];
        if ( v57 < (*(_QWORD *)v90 & 0xFFFFFFFFFFFFFFFCuLL) )
          goto LABEL_140;
        if ( v57 > v97 + (*(_QWORD *)v90 & 0xFFFFFFFFFFFFFFFCuLL) )
        {
          v28 = 3221225595LL;
          goto LABEL_52;
        }
      }
      Heap = P;
      if ( 2 * (unsigned int)*(unsigned __int16 *)v52 + 2 >= v17 )
      {
        if ( P )
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
          P = 0;
        }
        if ( v7 )
        {
          if ( v19 + 64 < v19 )
            goto LABEL_169;
          v19 += 64LL;
        }
        v63 = *(unsigned __int16 *)v52;
        *(_QWORD *)Buffer = (2 * v63 + 64) & 0xFFFFFFC0;
        v108 = (2 * v63 + 64) & 0xFFFFFFC0;
        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, *(SIZE_T *)Buffer);
        P = Heap;
        if ( !Heap )
        {
          v28 = 3221225495LL;
          goto LABEL_52;
        }
      }
      memcpy_0(Heap, v52 + 2, 2LL * *(unsigned __int16 *)v52);
      v64 = *(unsigned __int16 *)v52;
      v33 = (const wchar_t *)P;
      *((_WORD *)P + v64) = 0;
      goto LABEL_71;
    }
    v33 = (const wchar_t *)P;
    if ( P )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
      v33 = 0;
      P = 0;
LABEL_71:
      v18 = v94;
      v20 = v93;
      v26 = v92;
    }
    if ( v26 && v29 < *(unsigned __int16 *)(v26 + 12) )
      break;
    v44 = (const wchar_t *)v83;
    if ( v83 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v83);
      v44 = 0;
      v83 = 0;
LABEL_87:
      v20 = v93;
      v26 = v92;
    }
    if ( !v33 )
    {
      if ( v44 )
      {
LABEL_90:
        v45 = 2;
LABEL_91:
        v86 = v45;
        goto LABEL_92;
      }
      v32 = v122;
LABEL_102:
      v27 = 0;
      Size = 0;
      v21 = 0;
      v98 = 0;
      if ( v7 )
      {
        if ( v20
          && (v70 = *(_WORD *)(v20 + 14)) != 0
          && ((*(_QWORD *)Buffer = 0, !is_mul_ok(v70, 8u))
           || v20 + 16 < (*(_QWORD *)v90 & 0xFFFFFFFFFFFFFFFCuLL)
           || v20 + 16 > v97 + (*(_QWORD *)v90 & 0xFFFFFFFFFFFFFFFCuLL))
          || v26
          && (v46 = *(unsigned __int16 *)(v26 + 14), (_WORD)v46)
          && ((v94 = 0, !is_mul_ok(v46, 8u))
           || v26 + 16 < (v95 & 0xFFFFFFFFFFFFFFFCuLL)
           || v26 + 16 > v96 + (v95 & 0xFFFFFFFFFFFFFFFCuLL)) )
        {
          BaseSetLastNTError(3221225595LL);
          v15 = v83;
          v9 = v84;
          v22 = (unsigned __int64)v82;
          goto LABEL_199;
        }
      }
      while ( 1 )
      {
        if ( (!v20 || v27 >= *(unsigned __int16 *)(v20 + 14)) && (!v26 || v21 >= *(unsigned __int16 *)(v26 + 14)) )
        {
LABEL_50:
          v21 = 1;
          goto LABEL_54;
        }
        v23 = v20 && v27 < *(unsigned __int16 *)(v20 + 14) ? *(unsigned __int16 *)v87 : -1LL;
        v24 = v26 && v21 < *(unsigned __int16 *)(v26 + 14) ? *v13 : -1LL;
        if ( v23 == -1 )
          break;
        if ( v24 == -1 )
        {
          v25 = 1;
          goto LABEL_33;
        }
        LOBYTE(v25) = 1;
        v86 = 1;
        if ( (int)v23 - (int)v24 > 0 )
          goto LABEL_32;
        if ( (_DWORD)v23 == (_DWORD)v24 )
        {
          v25 = 3;
          goto LABEL_33;
        }
LABEL_34:
        if ( (v25 & 1) != 0 )
        {
          v14 = v23;
          v110 = v23;
          v87 += 2;
          v105 = v87;
          Size = v27 + 1;
        }
        if ( (v25 & 2) != 0 )
        {
          v14 = v24;
          v110 = v24;
          v13 += 4;
          v106 = v13;
          v98 = ++v21;
        }
        if ( v32 )
        {
          v22 = (unsigned __int64)v82;
          if ( !a3(BaseAddress, v82, v14, a4) )
          {
            BaseSetLastNTError(3221946375LL);
            v21 = 0;
            v15 = v83;
            v9 = v84;
            goto LABEL_199;
          }
        }
        else if ( !a3(BaseAddress, a2, v14, a4) )
        {
          BaseSetLastNTError(3221946375LL);
          goto LABEL_53;
        }
        v26 = v92;
        v20 = v93;
        v27 = Size;
      }
      if ( v24 == -1 )
        goto LABEL_50;
LABEL_32:
      v25 = 2;
LABEL_33:
      v86 = v25;
      goto LABEL_34;
    }
    if ( !v44 )
    {
      v45 = 1;
      goto LABEL_91;
    }
    LOBYTE(v45) = 1;
    v86 = 1;
    v59 = v33;
    do
    {
      v60 = *(const wchar_t *)((char *)v59 + (char *)v44 - (char *)v33);
      v61 = *v59 - v60;
      if ( v61 )
        break;
      ++v59;
    }
    while ( v60 );
    if ( v61 > 0 )
      goto LABEL_90;
    if ( !v61 )
    {
      v45 = 3;
      goto LABEL_91;
    }
LABEL_92:
    if ( (v45 & 1) != 0 )
    {
      v16 = v33;
      v109 = v33;
      v87 += 2;
      v105 = v87;
      ++Size;
    }
    if ( (v45 & 2) != 0 )
    {
      v16 = v44;
      v109 = v44;
      v13 += 4;
      v106 = v13;
      v98 = ++v29;
    }
    v32 = v122;
    if ( (_DWORD)v122 )
    {
      LODWORD(ResultSize) = 0;
      if ( !v16 )
      {
        v28 = 3221225485LL;
        goto LABEL_52;
      }
      v65 = wcslen(v16) + 1;
      LODWORD(ResultSize) = v65;
      v66 = v101;
      if ( v101 >= v65 )
      {
        v67 = v99;
      }
      else
      {
        if ( v99 )
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v99);
          v99 = 0;
          v65 = ResultSize;
        }
        v66 = v65 + 16;
        v101 = v65 + 16;
        v104 = v65 + 16;
        v67 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, v65 + 16);
        v99 = v67;
        if ( !v67 )
        {
          v28 = 3221225495LL;
          goto LABEL_52;
        }
        v65 = ResultSize;
      }
      if ( !v67 )
      {
        v50 = -1073741801;
LABEL_129:
        v28 = (unsigned int)v50;
        goto LABEL_52;
      }
      v50 = RtlUnicodeToMultiByteN((PCHAR)v67, v66, (PULONG)ResultSizea, v16, 2 * v65);
      if ( v50 < 0 )
        goto LABEL_129;
      if ( !a3(BaseAddress, v82, (__int64)v99, a4) )
      {
        v28 = 3221946375LL;
        goto LABEL_52;
      }
      v32 = v122;
    }
    else if ( !a3(BaseAddress, a2, (__int64)v16, a4) )
    {
      v28 = 3221946375LL;
      goto LABEL_52;
    }
LABEL_126:
    v26 = v92;
    v20 = v93;
    v18 = v94;
    v17 = *(_DWORD *)Buffer;
  }
  if ( v7 )
  {
    v34 = *(unsigned int *)v13;
    LODWORD(v34) = v34 & 0x7FFFFFFF;
    v19 = (unsigned __int64)&v103[v34 + 4];
    if ( v19 < (unsigned __int64)v103 )
      goto LABEL_51;
    v35 = (unsigned __int64)&v103[v34 + 4];
    if ( v35 < (v95 & 0xFFFFFFFFFFFFFFFCuLL) || v35 > v96 + (v95 & 0xFFFFFFFFFFFFFFFCuLL) )
    {
LABEL_140:
      v28 = 3221225595LL;
      goto LABEL_52;
    }
  }
  v36 = *(unsigned int *)v13;
  LODWORD(v36) = v36 & 0x7FFFFFFF;
  v37 = &v103[v36];
  if ( !v7 )
    goto LABEL_85;
  v38 = *(unsigned __int16 *)v37;
  v39 = v38 + 1;
  if ( v38 + 1 < v38 )
    goto LABEL_125;
  v114 = 0;
  v19 = 2 * v39;
  if ( !is_mul_ok(v39, 2u) )
    goto LABEL_125;
  v40 = Size & 0xFFFFFFFC;
  v41 = v38 + Size;
  if ( v41 < v40 || v41 > v40 + 260 )
    goto LABEL_125;
  v42 = (unsigned __int64)&v37[v19 + 2];
  if ( v42 < (v95 & 0xFFFFFFFFFFFFFFFCuLL) )
    goto LABEL_140;
  if ( v42 <= v96 + (v95 & 0xFFFFFFFFFFFFFFFCuLL) )
  {
LABEL_85:
    v43 = v83;
    if ( 2 * (unsigned int)*(unsigned __int16 *)v37 + 2 >= v18 )
    {
      if ( v83 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v83);
        v83 = 0;
      }
      if ( v7 )
      {
        if ( v19 + 64 < v19 )
        {
LABEL_51:
          v28 = 3221225595LL;
          goto LABEL_52;
        }
        v19 += 64LL;
      }
      v49 = *(unsigned __int16 *)v37;
      v94 = (2 * v49 + 64) & 0xFFFFFFC0;
      v107 = (2 * v49 + 64) & 0xFFFFFFC0;
      v43 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, v94);
      v83 = v43;
      if ( !v43 )
      {
        v28 = 3221225495LL;
        goto LABEL_52;
      }
    }
    memcpy_0(v43, v37 + 2, 2LL * *(unsigned __int16 *)v37);
    v44 = (const wchar_t *)v83;
    *((_WORD *)v83 + *(unsigned __int16 *)v37) = 0;
    v33 = (const wchar_t *)P;
    goto LABEL_87;
  }
  v28 = 3221225595LL;
LABEL_52:
  BaseSetLastNTError(v28);
LABEL_53:
  v21 = 0;
LABEL_54:
  v15 = v83;
  v9 = v84;
  v22 = (unsigned __int64)v82;
LABEL_199:
  BaseDllFreeResourceId(v9);
  if ( P )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
    P = 0;
  }
  if ( v15 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
  if ( (v22 & 0xFFFFFFFFFFFF0000uLL) != 0 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)v22);
  if ( v99 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v99);
  return v21;
}

```

## disassembly

```asm
0x18007d490  mov     rax, rsp
0x18007d493  mov     [rax+20h], r9
0x18007d497  mov     [rax+18h], r8
0x18007d49b  mov     [rax+10h], rdx
0x18007d49f  mov     [rax+8], rcx
0x18007d4a3  push    rbx
0x18007d4a4  push    rsi
0x18007d4a5  push    rdi
0x18007d4a6  push    r12
0x18007d4a8  push    r13
0x18007d4aa  push    r14
0x18007d4ac  push    r15
0x18007d4ae  sub     rsp, 140h
0x18007d4b5  mov     rsi, rcx
0x18007d4b8  xor     r15d, r15d
0x18007d4bb  mov     [rax-0F0h], r15
0x18007d4c2  mov     [rax-0E8h], r15
0x18007d4c9  mov     [rax-98h], r15
0x18007d4d0  mov     [rax-0A0h], r15
0x18007d4d7  mov     [rsp+178h+var_140], r15
0x18007d4dc  mov     [rax-90h], r15d
0x18007d4e3  mov     [rax-0A8h], r15d
0x18007d4ea  mov     qword ptr [rsp+178h+var_100], r15
0x18007d4ef  mov     [rsp+178h+Size], r15d
0x18007d4f4  mov     [rax-0C8h], r15
0x18007d4fb  mov     [rax-0D0h], r15
0x18007d502  mov     [rax-0B0h], r15
0x18007d509  mov     [rax-0F8h], r15d
0x18007d510  mov     ebx, dword ptr [rsp+178h+ResultSize]
0x18007d517  test    ebx, 0FFFFFFE4h
0x18007d51d  jnz     loc_18007E494
0x18007d523  mov     r14d, ebx
0x18007d526  and     r14d, 8
0x18007d52a  mov     edi, ebx
0x18007d52c  and     edi, 10h
0x18007d52f  mov     ecx, ebx
0x18007d531  test    bl, 17h
0x18007d534  jz      loc_18007EA02
0x18007d53a  mov     eax, ecx
0x18007d53c  and     eax, 6
0x18007d53f  cmp     al, 6
0x18007d541  jz      loc_18007E494
0x18007d547  test    edi, edi
0x18007d549  jnz     loc_18007E8E2
0x18007d54f  mov     rcx, rdx
0x18007d552  call    BaseDllMapResourceIdW
0x18007d557  mov     r12, rax
0x18007d55a  mov     [rsp+178h+var_130], rax
0x18007d55f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007d563  jz      loc_18007E494
0x18007d569  test    rsi, rsi
0x18007d56c  jz      loc_18007E94F
0x18007d572  mov     r13, rsi
0x18007d575  mov     [rsp+178h+var_D8], r13
0x18007d57d  test    edi, edi
0x18007d57f  jz      loc_18007E709
0x18007d585  mov     esi, ebx
0x18007d587  and     esi, 2
0x18007d58a  jnz     loc_18007E5C3
0x18007d590  xor     edx, edx
0x18007d592  mov     edi, ebx
0x18007d594  and     edi, 1
0x18007d597  jnz     loc_18007E4A2
0x18007d59d  test    edi, edi
0x18007d59f  jnz     loc_18007E6D3
0x18007d5a5  xor     ecx, ecx
0x18007d5a7  test    edi, edi
0x18007d5a9  jnz     loc_18007E6F3
0x18007d5af  not     ebx
0x18007d5b1  test    bl, 1
0x18007d5b4  jnz     loc_18007EA29
0x18007d5ba  test    ecx, ecx
0x18007d5bc  js      loc_18007E499
0x18007d5c2  xor     edx, edx
0x18007d5c4  mov     edi, edx
0x18007d5c6  mov     [rsp+178h+var_118], rdx
0x18007d5cb  mov     esi, edx
0x18007d5cd  mov     [rsp+178h+P], rdx
0x18007d5d2  mov     r15d, edx
0x18007d5d5  mov     [rsp+178h+var_138], rdx
0x18007d5da  mov     r13d, edx
0x18007d5dd  mov     r10d, edx
0x18007d5e0  mov     qword ptr [rsp+178h+Buffer], r10
0x18007d5e5  mov     r11d, edx
0x18007d5e8  mov     [rsp+178h+var_E0], r11
0x18007d5f0  mov     [rsp+178h+var_B8], rdx
0x18007d5f8  mov     ebx, edx
0x18007d5fa  mov     r9, [rsp+178h+var_E8]
0x18007d602  test    r9, r9
0x18007d605  jz      loc_18007D87D
0x18007d60b  test    r14d, r14d
0x18007d60e  jz      loc_18007D86C
0x18007d614  lea     rbx, [r9+10h]
0x18007d618  cmp     rbx, r9
0x18007d61b  jb      loc_18007D845
0x18007d621  mov     [rsp+178h+var_128], rbx
0x18007d626  mov     rcx, qword ptr [rsp+178h+var_100]
0x18007d62b  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18007d62f  cmp     rbx, rcx
0x18007d632  jb      short loc_18007D648
0x18007d634  mov     rax, [rsp+178h+var_C8]
0x18007d63c  add     rcx, rax
0x18007d63f  cmp     rbx, rcx
0x18007d642  jbe     loc_18007D86C
0x18007d648  mov     ecx, 0C000007Bh
0x18007d64d  call    BaseSetLastNTError
0x18007d652  xor     r13d, r13d
0x18007d655  mov     ebx, r13d
0x18007d658  mov     [rsp+178h+var_148], ebx
0x18007d65c  mov     r14, [rsp+178h+var_140]
0x18007d661  jmp     loc_18007E3AD
0x18007d666  test    r9, r9
0x18007d669  jnz     loc_18007D7AD
0x18007d66f  test    r8, r8
0x18007d672  jz      loc_18007D7F2
0x18007d678  movzx   eax, word ptr [r8+0Eh]
0x18007d67d  cmp     ebx, eax
0x18007d67f  jnb     loc_18007D7F2
0x18007d685  test    r9, r9
0x18007d688  jnz     loc_18007D82A
0x18007d68e  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18007d695  test    r8, r8
0x18007d698  jz      loc_18007D7A1
0x18007d69e  movzx   eax, word ptr [r8+0Eh]
0x18007d6a3  cmp     ebx, eax
0x18007d6a5  jnb     loc_18007D7A1
0x18007d6ab  movzx   ecx, word ptr [rdi]
0x18007d6ae  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18007d6b2  jnz     loc_18007D7C0
0x18007d6b8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18007d6bc  jz      loc_18007D7F2
0x18007d6c2  mov     eax, 2
0x18007d6c7  mov     [rsp+178h+var_11C], eax
0x18007d6cb  test    al, 1
0x18007d6cd  jnz     short loc_18007D742
0x18007d6cf  test    al, 2
0x18007d6d1  jz      short loc_18007D6F3
0x18007d6d3  mov     rsi, rcx
0x18007d6d6  mov     [rsp+178h+var_68], rcx
0x18007d6de  add     rdi, 8
0x18007d6e2  mov     [rsp+178h+var_80], rdi
0x18007d6ea  inc     ebx
0x18007d6ec  mov     [rsp+178h+var_C0], ebx
0x18007d6f3  mov     r9, [rsp+178h+arg_18]
0x18007d6fb  mov     r8, rsi
0x18007d6fe  mov     rcx, [rsp+178h+arg_0]
0x18007d706  mov     rax, [rsp+178h+arg_10]
0x18007d70e  test    r15d, r15d
0x18007d711  jnz     short loc_18007D770
0x18007d713  mov     rdx, [rsp+178h+UnicodeString]
0x18007d71b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d720  test    eax, eax
0x18007d722  jz      loc_18007E39E
0x18007d728  mov     r8, [rsp+178h+var_F0]
0x18007d730  mov     r9, [rsp+178h+var_E8]
0x18007d738  mov     r10d, [rsp+178h+Size]
0x18007d73d  jmp     loc_18007D666
0x18007d742  mov     rsi, rdx
0x18007d745  mov     [rsp+178h+var_68], rdx
0x18007d74d  mov     rdx, [rsp+178h+var_118]
0x18007d752  add     rdx, 8
0x18007d756  mov     [rsp+178h+var_118], rdx
0x18007d75b  mov     [rsp+178h+var_88], rdx
0x18007d763  inc     r10d
0x18007d766  mov     [rsp+178h+Size], r10d
0x18007d76b  jmp     loc_18007D6CF
0x18007d770  mov     r14, [rsp+178h+var_140]
0x18007d775  mov     rdx, r14
0x18007d778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d77d  test    eax, eax
0x18007d77f  jnz     short loc_18007D728
0x18007d781  mov     ecx, 0C00B0007h
0x18007d786  call    BaseSetLastNTError
0x18007d78b  mov     ebx, r13d
0x18007d78e  mov     [rsp+178h+var_148], ebx
0x18007d792  mov     r15, [rsp+178h+var_138]
0x18007d797  mov     r12, [rsp+178h+var_130]
0x18007d79c  jmp     loc_18007E3AD
0x18007d7a1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18007d7a8  jmp     loc_18007D6AE
0x18007d7ad  movzx   eax, word ptr [r9+0Eh]
0x18007d7b2  cmp     r10d, eax
0x18007d7b5  jb      loc_18007D685
0x18007d7bb  jmp     loc_18007D66F
0x18007d7c0  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18007d7c4  jz      loc_18007E2DB
0x18007d7ca  mov     eax, 1
0x18007d7cf  mov     [rsp+178h+var_11C], eax
0x18007d7d3  mov     r8d, edx
0x18007d7d6  sub     r8d, ecx
0x18007d7d9  test    r8d, r8d
0x18007d7dc  jg      loc_18007D6C2
0x18007d7e2  jnz     loc_18007D6CB
0x18007d7e8  mov     eax, 3
0x18007d7ed  jmp     loc_18007D6C7
0x18007d7f2  mov     ebx, 1
0x18007d7f7  jmp     short loc_18007D816
0x18007d7f9  mov     [rsp+178h+var_128], 0FFFFFFFFFFFFFFFFh
0x18007d802  mov     ecx, 0C000007Bh
0x18007d807  call    BaseSetLastNTError
0x18007d80c  xor     r13d, r13d
0x18007d80f  mov     ebx, r13d
0x18007d812  mov     [rsp+178h+var_148], ebx
0x18007d816  mov     r15, [rsp+178h+var_138]
0x18007d81b  mov     r12, [rsp+178h+var_130]
0x18007d820  mov     r14, [rsp+178h+var_140]
0x18007d825  jmp     loc_18007E3AD
0x18007d82a  movzx   eax, word ptr [r9+0Eh]
0x18007d82f  cmp     r10d, eax
0x18007d832  jnb     loc_18007D68E
0x18007d838  mov     rax, [rsp+178h+var_118]
0x18007d83d  movzx   edx, word ptr [rax]
0x18007d840  jmp     loc_18007D695
0x18007d845  mov     [rsp+178h+var_128], 0FFFFFFFFFFFFFFFFh
0x18007d84e  mov     ecx, 0C000007Bh
0x18007d853  call    BaseSetLastNTError
0x18007d858  xor     r13d, r13d
0x18007d85b  mov     ebx, r13d
0x18007d85e  mov     [rsp+178h+var_148], ebx
0x18007d862  mov     r14, [rsp+178h+var_140]
0x18007d867  jmp     loc_18007E3AD
0x18007d86c  lea     rax, [r9+10h]
0x18007d870  mov     [rsp+178h+var_118], rax
0x18007d875  mov     [rsp+178h+var_88], rax
0x18007d87d  mov     r8, [rsp+178h+var_F0]
0x18007d885  test    r8, r8
0x18007d888  jnz     loc_18007DB68
0x18007d88e  mov     [rsp+178h+Size], edx
0x18007d892  mov     r12d, edx
0x18007d895  mov     [rsp+178h+var_C0], edx
0x18007d89c  test    r14d, r14d
0x18007d89f  jz      short loc_18007D8BD
0x18007d8a1  test    r9, r9
0x18007d8a4  jnz     loc_18007DED0
0x18007d8aa  test    r8, r8
0x18007d8ad  jz      short loc_18007D8BD
0x18007d8af  movzx   eax, word ptr [r8+0Ch]
0x18007d8b4  test    ax, ax
0x18007d8b7  jnz     loc_18007DC86
0x18007d8bd  mov     r15d, dword ptr [rsp+178h+arg_30]
0x18007d8c5  and     r15d, 1
0x18007d8c9  mov     dword ptr [rsp+178h+arg_30], r15d
0x18007d8d1  jnz     loc_18007DDCD
0x18007d8d7  test    r9, r9
0x18007d8da  jnz     loc_18007DE01
0x18007d8e0  test    r8, r8
0x18007d8e3  jz      loc_18007DB8A
0x18007d8e9  movzx   eax, word ptr [r8+0Ch]
0x18007d8ee  cmp     r12d, eax
0x18007d8f1  jnb     loc_18007DB8A
0x18007d8f7  test    r9, r9
0x18007d8fa  jnz     loc_18007DE15
0x18007d900  mov     r15, [rsp+178h+P]
0x18007d905  test    r15, r15
0x18007d908  jz      short loc_18007D948
0x18007d90a  mov     rcx, gs:60h
0x18007d913  mov     r8, r15; P
0x18007d916  xor     edx, edx; Flags
0x18007d918  mov     rcx, [rcx+30h]; HeapHandle
0x18007d91c  call    cs:__imp_RtlFreeHeap
0x18007d923  nop     dword ptr [rax+rax+00h]
0x18007d928  xor     r15d, r15d
0x18007d92b  mov     [rsp+178h+P], r15
0x18007d930  mov     r11, [rsp+178h+var_E0]
0x18007d938  mov     r9, [rsp+178h+var_E8]
0x18007d940  mov     r8, [rsp+178h+var_F0]
0x18007d948  test    r8, r8
0x18007d94b  jz      loc_18007E13E
0x18007d951  movzx   eax, word ptr [r8+0Ch]
0x18007d956  cmp     r12d, eax
0x18007d959  jnb     loc_18007E13E
0x18007d95f  test    r14d, r14d
0x18007d962  jz      short loc_18007D9B7
0x18007d964  mov     eax, [rdi]
0x18007d966  btr     eax, 1Fh
0x18007d96a  mov     rdx, [rsp+178h+var_98]
0x18007d972  lea     rbx, [rdx+4]
0x18007d976  add     rbx, rax
0x18007d979  cmp     rbx, rdx
0x18007d97c  jb      loc_18007D7F9
0x18007d982  mov     [rsp+178h+var_128], rbx
0x18007d987  mov     rcx, [rsp+178h+var_D8]
0x18007d98f  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18007d993  lea     r8, [rdx+4]
0x18007d997  add     r8, rax
0x18007d99a  cmp     r8, rcx
0x18007d99d  jb      loc_18007DEC6
0x18007d9a3  mov     rax, [rsp+178h+var_D0]
0x18007d9ab  add     rcx, rax
0x18007d9ae  cmp     r8, rcx
0x18007d9b1  ja      loc_18007DEC6
0x18007d9b7  mov     r15d, [rdi]
0x18007d9ba  btr     r15d, 1Fh
0x18007d9bf  add     r15, [rsp+178h+var_98]
0x18007d9c7  test    r14d, r14d
0x18007d9ca  jz      loc_18007DA62
0x18007d9d0  movzx   ecx, word ptr [r15]
0x18007d9d4  lea     rdx, [rcx+1]
0x18007d9d8  cmp     rdx, rcx
0x18007d9db  jb      loc_18007DD93
  ... truncated ...
```
