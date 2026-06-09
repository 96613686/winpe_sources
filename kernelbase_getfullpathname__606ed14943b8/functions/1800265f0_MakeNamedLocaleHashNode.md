# MakeNamedLocaleHashNode

- ea: `0x1800265f0`
- end: `0x1800273f7`
- name: `MakeNamedLocaleHashNode`
- size: `3591`
- prototype: ``
- caller_count: `22`
- callee_count: `19`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001cd50`
- `0x180021e08`
- `0x180022a60`
- `0x180023c10`
- `0x180024cf0`
- `0x180024ed0`
- `0x180027400`
- `0x180028630`
- `0x180029770`
- `0x180029ec0`
- `0x180046ac0`
- `0x1800486a0`
- `0x180048920`
- `0x180048f20`
- `0x18004a820`
- `0x180080e30`
- `0x180085c7c`
- `0x180085d40`
- `0x1800862d8`
- `0x180086360`
- `0x180086ff0`
- `0x180087370`

## callees

- `0x180024c80`
- `0x1800265f0`
- `0x180028360`
- `0x18002a560`
- `0x1800486a0`
- `0x180076778`
- `0x180086360`
- `0x180086ff0`
- `0x180097228`
- `0x1800b4b38`
- `0x1800b5090`
- `0x1800c8cf8`
- `0x1800ea2ac`
- `0x1800ea4b0`
- `0x1800ea584`
- `0x1800ee4a4`
- `0x1801369c9`
- `0x180142ba0`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18002694e`
- `ntdll!RtlInitUnicodeString` at `0x180026b98`
- `ntdll!RtlInitUnicodeString` at `0x1800270c8`
- `ntdll!RtlInitUnicodeString` at `0x18002720d`
- `ntdll!RtlInitUnicodeString` at `0x18002694e`
- `ntdll!RtlInitUnicodeString` at `0x180026b98`
- `ntdll!RtlInitUnicodeString` at `0x1800270c8`
- `ntdll!RtlInitUnicodeString` at `0x18002720d`
- `ntdll!NtOpenKey` at `0x18002698b`
- `ntdll!NtOpenKey` at `0x180027105`
- `ntdll!NtOpenKey` at `0x18002698b`
- `ntdll!NtOpenKey` at `0x180027105`
- `ntdll!NtQueryValueKey` at `0x180026bd9`
- `ntdll!NtQueryValueKey` at `0x18002724e`
- `ntdll!NtQueryValueKey` at `0x180026bd9`
- `ntdll!NtQueryValueKey` at `0x18002724e`
- `ntdll!NtClose` at `0x180026c37`
- `ntdll!NtClose` at `0x1800272a8`
- `ntdll!NtClose` at `0x180026c37`
- `ntdll!NtClose` at `0x1800272a8`
- `ntdll!RtlFreeHeap` at `0x180026fca`
- `ntdll!RtlFreeHeap` at `0x1800271d4`
- `ntdll!RtlFreeHeap` at `0x180026fca`
- `ntdll!RtlFreeHeap` at `0x1800271d4`
- `ntdll!RtlAllocateHeap` at `0x180026e10`
- `ntdll!RtlAllocateHeap` at `0x180026e10`

## string_xrefs

- `0x1800267f8`: `\Registry\Machine\System\CurrentControlSet\Control`

## pseudocode

```c
__int64 __fastcall MakeNamedLocaleHashNode(const WCHAR *a1, int a2)
{
  const WCHAR *v2; // r9
  const WCHAR *v3; // r8
  __int64 v4; // r10
  unsigned __int64 v5; // rcx
  int v6; // edx
  int v7; // edi
  __int64 v8; // r13
  int v9; // r11d
  int v10; // r8d
  int v11; // ebx
  unsigned __int16 *v12; // rsi
  unsigned __int16 *i; // r10
  WCHAR v14; // ax
  unsigned __int16 v15; // dx
  int v16; // edx
  int v17; // ebx
  unsigned int v18; // r12d
  unsigned int *v19; // r14
  int v20; // ecx
  const wchar_t *v21; // rsi
  WCHAR *v22; // rax
  __int64 v23; // rcx
  WCHAR *v24; // r8
  __int64 v25; // rdx
  WCHAR *v26; // rcx
  unsigned int *v27; // r15
  __int64 v28; // rcx
  unsigned __int64 v29; // rdx
  WCHAR *v30; // rax
  WCHAR *v31; // rcx
  __int64 v32; // rcx
  WCHAR *v33; // rax
  __int64 v34; // rdi
  __int64 v35; // rcx
  WCHAR *v36; // rcx
  NTSTATUS v37; // eax
  HANDLE v38; // rdi
  __int64 LocaleHashNode; // rax
  __int64 v40; // rdi
  _DWORD *v41; // rsi
  char *v42; // r8
  char *v43; // r9
  int v44; // r15d
  unsigned int *v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // r8
  __int64 v48; // rax
  bool v49; // zf
  __int64 LocaleNullStringFromArrayInPool; // rax
  int v51; // eax
  __int16 v52; // ax
  void *v53; // rcx
  __int64 result; // rax
  unsigned int *WindowsLocaleData; // rax
  PCWSTR v56; // rsi
  NTSTATUS v57; // edi
  __int64 v58; // r10
  WCHAR *v59; // rax
  __int64 v60; // rcx
  WCHAR *v61; // rcx
  WCHAR *v62; // rax
  __int64 v63; // rcx
  WCHAR *v64; // rax
  const wchar_t *v65; // rcx
  unsigned __int64 v66; // r9
  WCHAR *v67; // rcx
  int v68; // r9d
  __int64 v69; // rax
  unsigned int *v70; // rdi
  int v71; // eax
  const WCHAR *v72; // rbx
  __int64 v73; // rax
  _QWORD *Heap; // rax
  _QWORD *v75; // rbx
  __int64 v76; // r10
  __int64 v77; // rdx
  __int64 v78; // rax
  __int64 v79; // rax
  __int16 v80; // r8
  __int64 NamedLocaleHashNode; // rax
  __int64 v82; // r9
  const wchar_t *v83; // rdx
  __int64 v84; // rcx
  WCHAR *v85; // r9
  WCHAR *v86; // rcx
  WCHAR *v87; // rax
  __int64 v88; // rcx
  WCHAR *v89; // rcx
  int v90; // edx
  int v91; // r9d
  __int64 v92; // rax
  HANDLE v93; // rbx
  NTSTATUS v94; // ebx
  PCWSTR v95; // rbx
  WCHAR *v96; // rax
  __int64 v97; // rcx
  __int64 v98; // rdx
  WCHAR *v99; // rcx
  __int64 v100; // rcx
  WCHAR *v101; // rax
  __int64 v102; // r9
  const wchar_t *v103; // rdx
  WCHAR *v104; // r9
  __int64 v105; // rcx
  HANDLE KeyHandle; // [rsp+38h] [rbp-D0h] BYREF
  ULONG DestinationString; // [rsp+40h] [rbp-C8h] BYREF
  int DestinationString_4; // [rsp+44h] [rbp-C4h]
  struct _UNICODE_STRING DestinationString_8; // [rsp+48h] [rbp-C0h] BYREF
  struct _UNICODE_STRING NtPathName_8; // [rsp+58h] [rbp-B0h] BYREF
  PCWSTR v111; // [rsp+68h] [rbp-A0h]
  union _LARGE_INTEGER FileSize; // [rsp+70h] [rbp-98h] BYREF
  const WCHAR *v113; // [rsp+78h] [rbp-90h]
  __int64 v114; // [rsp+80h] [rbp-88h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-80h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+B8h] [rbp-50h] BYREF
  int v117; // [rsp+BCh] [rbp-4Ch]
  unsigned int v118; // [rsp+C0h] [rbp-48h]
  unsigned int v119; // [rsp+C4h] [rbp-44h]
  wchar_t pszSrc[512]; // [rsp+2D8h] [rbp+1D0h] BYREF
  WCHAR SourceString[512]; // [rsp+6D8h] [rbp+5D0h] BYREF

  v2 = a1;
  v3 = a1;
  v4 = 0x43FFFFFF01FF9LL;
  v113 = a1;
  v5 = 0;
  DestinationString_4 = a2;
  NtPathName_8 = 0;
  FileSize.QuadPart = 0;
  while ( 1 )
  {
    if ( v5 >= 0x55 )
      return 0;
    v6 = *v3;
    if ( !(_WORD)v6 )
      break;
    if ( ((unsigned __int16)(v6 - 45) > 0x32u || !_bittest64(&v4, (unsigned int)(v6 - 45)))
      && (unsigned __int16)(v6 - 97) > 0x19u )
    {
      return 0;
    }
    ++v3;
    ++v5;
  }
  if ( BasepIsSecureProcess )
    return 0;
  v7 = 0;
  v8 = qword_1803A6BD0;
  v9 = (unsigned __int16)word_1803A6BAA - 1;
  v111 = v2;
LABEL_9:
  while ( 2 )
  {
    if ( v7 > v9 )
    {
      v17 = 0;
      v18 = 4096;
      v114 = 0;
      v19 = 0;
    }
    else
    {
      v10 = 85;
      v11 = (v9 + v7) / 2;
      v12 = (unsigned __int16 *)(qword_1803A6BC8 + 8LL * v11);
      v114 = qword_1803A6BD0 + 2 + 2LL * *v12;
      for ( i = (unsigned __int16 *)v114; v10 > 0; ++i )
      {
        v14 = *v2;
        if ( !*v2 )
          break;
        v15 = *i;
        if ( !*i )
          goto LABEL_164;
        if ( (unsigned __int16)(v14 - 65) <= 0x19u )
          v14 |= 0x20u;
        if ( (unsigned __int16)(v15 - 65) <= 0x19u )
          v15 |= 0x20u;
        if ( v14 == 95 )
          v14 = 45;
        if ( v15 == 95 )
          v15 = 45;
        v16 = v14 - v15;
        if ( v16 )
        {
          if ( v16 < 0 )
            goto LABEL_14;
LABEL_164:
          v2 = v113;
          v7 = v11 + 1;
          goto LABEL_9;
        }
        --v10;
        ++v2;
      }
      if ( *v2 )
        goto LABEL_164;
      if ( *i )
      {
LABEL_14:
        v2 = v113;
        v9 = v11 - 1;
        continue;
      }
      v20 = *((_DWORD *)v12 + 1);
      v18 = v20 & 0x7FFFFFFF;
      if ( v20 < 0 || (v20 & 0xF0000) != 0 || v20 == 1034 )
      {
        v17 = 0;
      }
      else
      {
        v17 = 0;
        v114 = 0;
      }
      v19 = (unsigned int *)(qword_1803A6BB8 + (unsigned __int16)word_1803A6BB0 * v12[1]);
      if ( v19 )
      {
        if ( (v18 & 0xF0000) != 0 )
        {
          WindowsLocaleData = (unsigned int *)GetWindowsLocaleData((unsigned __int16)v20);
          if ( WindowsLocaleData )
            v111 = (PCWSTR)(v8 + 2LL * *WindowsLocaleData + 2);
        }
      }
    }
    break;
  }
  if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
    || v18 != 4096
    || DestinationString_4
    || !(unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
    && !(unsigned int)CreateTransientLocales()
    || (result = FindNamedLocaleHashNode(v113)) == 0 )
  {
    KeyHandle = 0;
    v21 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control";
    v22 = pszSrc;
    v23 = 2147483646;
    v24 = (WCHAR *)L"\\Registry\\Machine\\System\\CurrentControlSet\\Control";
    v25 = 512;
    memset(&ObjectAttributes, 0, 44);
    DestinationString_8 = 0;
    do
    {
      if ( !v23 )
        break;
      if ( !*v24 )
        break;
      *v22++ = *v24++;
      --v23;
      --v25;
    }
    while ( v25 );
    v26 = v22 - 1;
    if ( v25 )
      v26 = v22;
    *v26 = 0;
    if ( !v25 )
      goto LABEL_41;
    v88 = 512;
    v87 = pszSrc;
    do
    {
      if ( !*v87 )
        break;
      ++v87;
      --v88;
    }
    while ( v88 );
    v82 = 512 - v88;
    if ( !v88 )
      goto LABEL_41;
    v83 = L"\\Nls\\CustomLocale";
    v24 = (WCHAR *)v88;
    v49 = v82 == 512;
    v84 = 2147483646;
    v85 = &pszSrc[v82];
    if ( !v49 )
    {
      do
      {
        if ( !v84 )
          break;
        if ( !*v83 )
          break;
        *v85++ = *v83++;
        --v84;
        v24 = (WCHAR *)((char *)v24 - 1);
      }
      while ( v24 );
    }
    v86 = v85 - 1;
    if ( v24 )
      v86 = v85;
    *v86 = 0;
    if ( v24 )
    {
      RtlInitUnicodeString(&DestinationString_8, pszSrc);
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString_8;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v27 = 0;
      if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
      {
        v93 = KeyHandle;
        DestinationString_8 = 0;
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString_8, v111);
        memset_0(KeyValueInformation, 0, 0x214u);
        v94 = NtQueryValueKey(
                v93,
                &DestinationString_8,
                KeyValueFullInformation,
                KeyValueInformation,
                0x214u,
                &DestinationString);
        if ( v117 == 1 )
        {
          if ( v94 >= 0 )
          {
            if ( (v119 & 1) != 0
              || v119 < 2
              || *(_WORD *)&KeyValueInformation[2 * ((unsigned __int64)v119 >> 1) - 2 + v118] )
            {
              v94 = -1073741492;
            }
            else
            {
              v94 = 0;
            }
          }
        }
        else
        {
          v94 = -1073741492;
        }
        if ( KeyHandle )
          NtClose(KeyHandle);
        if ( v94 < 0 )
          goto LABEL_197;
        v95 = v111;
        v96 = pszSrc;
        v97 = 2147483646;
        v24 = (WCHAR *)v111;
        v98 = 260;
        do
        {
          if ( !v97 )
            break;
          if ( !*v24 )
            break;
          *v96++ = *v24++;
          --v97;
          --v98;
        }
        while ( v98 );
        v99 = v96 - 1;
        if ( v98 )
          v99 = v96;
        v27 = 0;
        *v99 = 0;
        if ( !v98 )
          goto LABEL_197;
        v100 = 260;
        v101 = pszSrc;
        do
        {
          if ( !*v101 )
            break;
          ++v101;
          --v100;
        }
        while ( v100 );
        v102 = 260 - v100;
        if ( !v100 )
          goto LABEL_197;
        v24 = (WCHAR *)v100;
        v49 = v102 == 260;
        v103 = L".nlp";
        v104 = &pszSrc[v102];
        v105 = 2147483646;
        v27 = 0;
        if ( !v49 )
        {
          do
          {
            v27 = 0;
            if ( !v105 )
              break;
            if ( !*v103 )
              break;
            *v104++ = *v103++;
            --v105;
            v24 = (WCHAR *)((char *)v24 - 1);
          }
          while ( v24 );
        }
        v89 = v104 - 1;
        if ( v24 )
          v89 = v104;
        *v89 = 0;
        if ( v24 )
        {
          if ( (unsigned int)GetNTFileName(pszSrc, &NtPathName_8)
            || (v92 = CreateAndMapFileSection((int)&NtPathName_8, v90, (int)v24, v91, &FileSize),
                (v27 = (unsigned int *)v92) == 0)
            || (unsigned int)ValidateLocaleFile(v92, v95, &FileSize) )
          {
            v17 = 0;
          }
          else
          {
            UnmapViewOfFile2((HANDLE)0xFFFFFFFFFFFFFFFFLL, v27, 0);
            v17 = 0;
            v27 = 0;
          }
          if ( NtPathName_8.Buffer )
          {
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName_8.Buffer);
            NtPathName_8.Buffer = 0;
          }
        }
        else
        {
LABEL_197:
          v17 = 0;
        }
      }
      else
      {
        KeyHandle = 0;
      }
    }
    else
    {
LABEL_41:
      v27 = 0;
    }
    KeyHandle = 0;
    v28 = 2147483646;
    v29 = 512;
    v30 = SourceString;
    memset(&ObjectAttributes, 0, 44);
    DestinationString_8 = 0;
    do
    {
      if ( !v28 )
        break;
      v24 = (WCHAR *)*v21;
      if ( !(_WORD)v24 )
        break;
      *v30 = (unsigned __int16)v24;
      ++v21;
      ++v30;
      --v28;
      --v29;
    }
    while ( v29 );
    v31 = v30 - 1;
    if ( v29 )
      v31 = v30;
    *v31 = 0;
    if ( !v29 )
      goto LABEL_64;
    v32 = 512;
    v33 = SourceString;
    do
    {
      if ( !*v33 )
        break;
      ++v33;
      --v32;
    }
    while ( v32 );
    if ( !v32 )
    {
      v24 = 0;
      goto LABEL_64;
    }
    v34 = v32;
    v29 = (unsigned __int64)L"\\Nls\\ExtendedLocale";
    v24 = &SourceString[512 - v32];
    v35 = 2147483646;
    do
    {
      if ( !v35 )
        break;
      if ( !*(_WORD *)v29 )
        break;
      *v24 = *(_WORD *)v29;
      v29 += 2LL;
      ++v24;
      --v35;
      --v34;
    }
    while ( v34 );
    v36 = v24 - 1;
    if ( v34 )
      v36 = v24;
    *v36 = 0;
    if ( !v34 )
      goto LABEL_64;
    RtlInitUnicodeString(&DestinationString_8, SourceString);
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString_8;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v37 = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    if ( v37 >= 0 )
    {
      v38 = KeyHandle;
    }
    else
    {
      v38 = 0;
      KeyHandle = 0;
    }
    if ( v37 < 0 )
      goto LABEL_64;
    v56 = v111;
    DestinationString = 0;
    DestinationString_8 = 0;
    RtlInitUnicodeString(&DestinationString_8, v111);
    memset_0(KeyValueInformation, 0, 0x214u);
    v57 = NtQueryValueKey(
            v38,
            &DestinationString_8,
            KeyValueFullInformation,
            KeyValueInformation,
            0x214u,
            &DestinationString);
    if ( v117 == 1 )
    {
      if ( v57 >= 0 )
      {
        if ( (v119 & 1) != 0
          || v119 < 2
          || (v29 = (unsigned __int64)v119 >> 1, *(_WORD *)&KeyValueInformation[2 * v29 - 2 + v118]) )
        {
          v57 = -1073741492;
        }
        else
        {
          v57 = 0;
        }
      }
    }
    else
    {
      v57 = -1073741492;
    }
    if ( KeyHandle )
      NtClose(KeyHandle);
    if ( v57 < 0 )
      goto LABEL_64;
    v58 = 2147483646;
    v59 = pszSrc;
    v60 = 2147483646;
    v24 = (WCHAR *)v56;
    v29 = 260;
    do
    {
      if ( !v60 )
        break;
      if ( !*v24 )
        break;
      *v59++ = *v24++;
      --v60;
      --v29;
    }
    while ( v29 );
    v61 = v59 - 1;
    if ( v29 )
      v61 = v59;
    v17 = 0;
    *v61 = 0;
    if ( !v29 )
      goto LABEL_64;
    v62 = pszSrc;
    v63 = 260;
    do
    {
      if ( !*v62 )
        break;
      ++v62;
      --v63;
    }
    while ( v63 );
    v29 = 260 - v63;
    if ( !v63 )
    {
      v29 = 0;
      goto LABEL_64;
    }
    v64 = &pszSrc[v29];
    v65 = L".nlx";
    v66 = 260 - v29;
    if ( 260 != v29 )
    {
      do
      {
        v17 = 0;
        if ( !v58 )
          break;
        v29 = *v65;
        if ( !(_WORD)v29 )
          break;
        *v64 = v29;
        ++v65;
        ++v64;
        --v58;
        --v66;
      }
      while ( v66 );
    }
    v67 = v64 - 1;
    if ( v66 )
      v67 = v64;
    *v67 = 0;
    if ( !v66 )
    {
LABEL_64:
      if ( v27 )
      {
        LocaleHashNode = CreateLocaleHashNode(0, v29, v24);
        v40 = LocaleHashNode;
        if ( LocaleHashNode )
        {
          v41 = (unsigned int *)((char *)v27 + *v27);
          v42 = (char *)v27 + (unsigned int)v41[7];
          *(_QWORD *)(LocaleHashNode + 40) = v42;
          *(_QWORD *)(LocaleHashNode + 56) = v42;
          v43 = (char *)v27 + (unsigned int)v41[14];
          v44 = 1;
          *(_QWORD *)(LocaleHashNode + 48) = v43;
          *(_QWORD *)(LocaleHashNode + 64) = v43;
          *(_DWORD *)(LocaleHashNode + 72) = *v41;
          if ( (v42[24] & 1) != 0 )
          {
            *(_DWORD *)(LocaleHashNode + 76) = 32;
LABEL_68:
            *(_QWORD *)(v40 + 104) = v40;
            goto LABEL_69;
          }
          *(_DWORD *)(LocaleHashNode + 76) = 16;
          NamedLocaleHashNode = GetNamedLocaleHashNode(&v43[2 * *((unsigned int *)v42 + 73) + 2], 1);
          *(_QWORD *)(v40 + 104) = NamedLocaleHashNode;
          if ( !NamedLocaleHashNode )
          {
            if ( *v41 >= 3u )
              goto LABEL_68;
            *(_QWORD *)(v40 + 104) = GetNamedLocaleHashNode(&word_18029DECC, 1);
          }
LABEL_69:
          v45 = *(unsigned int **)(v40 + 40);
          v46 = *(_QWORD *)(v40 + 48);
          v47 = v46 + 2 * (*v45 + 1LL);
          v48 = v114;
          v49 = v114 == 0;
          *(_QWORD *)(v40 + 16) = v47;
          if ( v49 )
            v48 = v47;
          *(_QWORD *)(v40 + 8) = v48;
          *(_QWORD *)(v40 + 24) = v46 + 2LL * v45[46] + 2;
          if ( !v19 || v18 == 4096 )
          {
            if ( *((_WORD *)v45 + 4) == 4096 )
              *(_DWORD *)v40 = GetTransientLCID(v47);
            if ( !v19 )
              goto LABEL_75;
          }
          else
          {
            *(_DWORD *)v40 = v18;
          }
          v80 = *(_WORD *)(v40 + 2);
          if ( (v80 & 0xF) != 0 )
          {
            LocaleNullStringFromArrayInPool = GetLocaleNullStringFromArrayInPool(
                                                qword_1803A6BD0,
                                                v19[54],
                                                (v80 & 0xFu) - 1);
LABEL_76:
            *(_QWORD *)(v40 + 32) = LocaleNullStringFromArrayInPool;
            v51 = *(_DWORD *)(v40 + 76);
            if ( v17 )
            {
              if ( !v19 )
                v44 = 32769;
              *(_DWORD *)(v40 + 76) = v51 | v44;
              if ( v19 )
                goto LABEL_80;
            }
            else
            {
              if ( v19 )
              {
                *(_DWORD *)(v40 + 76) = v51 | 9;
LABEL_80:
                *(_WORD *)(v40 + 80) = *((_WORD *)v19 + 5);
                *(_WORD *)(v40 + 82) = (unsigned __int8)*((_WORD *)v19 + 61);
                v52 = *((unsigned __int8 *)v19 + 123);
LABEL_81:
                *(_WORD *)(v40 + 84) = v52;
                v53 = (void *)v40;
                return InsertLocaleHashNode(v53);
              }
              *(_DWORD *)(v40 + 76) = v51 | 2;
            }
            *(_WORD *)(v40 + 80) = 4096;
            *(_WORD *)(v40 + 82) = 6;
            v52 = 22;
            goto LABEL_81;
          }
LABEL_75:
          LocaleNullStringFromArrayInPool = *(_QWORD *)(v40 + 16);
          goto LABEL_76;
        }
        return 0;
      }
      if ( !v19 )
      {
        if ( !DestinationString_4 )
        {
          v72 = v113;
          if ( !(unsigned int)IsBadLocaleName(v113) )
          {
            v73 = ResolveLocaleHashNode(v72, 1, 1);
            return MakeConstructedLocaleFromHashNode(v72, v73);
          }
        }
        return 0;
      }
      if ( BasepIsSecureProcess )
        return 0;
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x70u);
      v75 = Heap;
      if ( !Heap )
        return 0;
      *(_DWORD *)Heap = v18;
      Heap[5] = v19;
      Heap[7] = v19;
      v76 = qword_1803A6BD0;
      Heap[6] = qword_1803A6BD0;
      Heap[8] = qword_1803A6BD0;
      *((_DWORD *)Heap + 18) = dword_1803A6BB4;
      v77 = v76 + 2 * (*v19 + 1LL);
      Heap[2] = v77;
      Heap[3] = v76 + 2 * (v19[46] + 1LL);
      *((_WORD *)Heap + 40) = *((_WORD *)v19 + 5);
      *((_WORD *)Heap + 41) = (unsigned __int8)*((_WORD *)v19 + 61);
      *((_WORD *)Heap + 42) = *((unsigned __int8 *)v19 + 123);
      if ( (v18 & 0xF0000) != 0 )
        v77 = GetLocaleNullStringFromArrayInPool(qword_1803A6BD0, v19[54], (HIWORD(v18) & 0xF) - 1);
      v78 = v114;
      v49 = v114 == 0;
      v75[4] = v77;
      if ( v49 )
        v78 = v77;
      v75[1] = v78;
      if ( (v19[6] & 1) != 0 )
      {
        *((_DWORD *)v75 + 19) = 33;
      }
      else
      {
        *((_DWORD *)v75 + 19) = 17;
        v79 = GetNamedLocaleHashNode(v76 + 2 + 2LL * v19[73], 2);
        v75[13] = v79;
        if ( v79 )
          goto LABEL_140;
      }
      v75[13] = v75;
LABEL_140:
      if ( v18 == 4096 )
        *(_DWORD *)v75 = GetTransientLCID(v75[2]);
      v53 = v75;
      return InsertLocaleHashNode(v53);
    }
    if ( !(unsigned int)GetNTFileName(pszSrc, &NtPathName_8) )
    {
      v69 = CreateAndMapFileSection((int)&NtPathName_8, v29, (int)v24, v68, &FileSize);
      v70 = (unsigned int *)v69;
      if ( v69 )
      {
        v71 = ValidateLocaleFile(v69, v56, &FileSize);
        v17 = v71;
        if ( v71 == 1 )
        {
          if ( v27 )
          {
            v17 = 0;
LABEL_124:
            UnmapViewOfFile2((HANDLE)0xFFFFFFFFFFFFFFFFLL, v70, 0);
            goto LABEL_156;
          }
        }
        else if ( !v71 )
        {
          goto LABEL_124;
        }
        v27 = v70;
      }
    }
LABEL_156:
    if ( NtPathName_8.Buffer )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName_8.Buffer);
      NtPathName_8.Buffer = 0;
    }
    goto LABEL_64;
  }
  return result;
}

```

## disassembly

```asm
0x1800265f0  mov     r11, rsp
0x1800265f3  push    rbp
0x1800265f4  push    rbx
0x1800265f5  lea     rbp, [r11-0A08h]
0x1800265fc  sub     rsp, 0AF8h
0x180026603  mov     rax, cs:__security_cookie
0x18002660a  xor     rax, rsp
0x18002660d  mov     [rbp+0A00h+var_30], rax
0x180026614  mov     [r11+10h], rsi
0x180026618  xor     ebx, ebx
0x18002661a  mov     [r11+18h], rdi
0x18002661e  xorps   xmm0, xmm0
0x180026621  mov     [r11+20h], r12
0x180026625  mov     r9, rcx
0x180026628  mov     [r11-18h], r13
0x18002662c  mov     r8, rcx
0x18002662f  mov     [r11-20h], r14
0x180026633  mov     r10, 43FFFFFF01FF9h
0x18002663d  mov     [rsp+0B00h+var_A90], rcx
0x180026642  mov     ecx, ebx
0x180026644  mov     [r11-28h], r15
0x180026648  mov     dword ptr [rsp+0B00h+DestinationString+4], edx
0x18002664c  movups  xmmword ptr [rsp+0B00h+NtPathName.Buffer], xmm0
0x180026651  mov     qword ptr [rsp+0B00h+FileSize], rbx
0x180026656  cmp     rcx, 55h ; 'U'
0x18002665a  jnb     loc_180026DA9
0x180026660  movzx   edx, word ptr [r8]
0x180026664  test    dx, dx
0x180026667  jz      short loc_180026689
0x180026669  lea     eax, [rdx-2Dh]
0x18002666c  cmp     ax, 32h ; '2'
0x180026670  ja      loc_1800273BC
0x180026676  bt      r10, rax
0x18002667a  jnb     loc_1800273BC
0x180026680  add     r8, 2
0x180026684  inc     rcx
0x180026687  jmp     short loc_180026656
0x180026689  cmp     cs:BasepIsSecureProcess, bl
0x18002668f  jnz     loc_180026DA9
0x180026695  movzx   r11d, cs:word_1803A6BAA
0x18002669d  mov     edi, ebx
0x18002669f  mov     r13, cs:qword_1803A6BD0
0x1800266a6  dec     r11d
0x1800266a9  mov     r14, cs:qword_1803A6BC8
0x1800266b0  mov     [rsp+0B00h+var_AA0], r9
0x1800266b5  cmp     edi, r11d
0x1800266b8  jg      loc_180026775
0x1800266be  lea     eax, [r11+rdi]
0x1800266c2  mov     r8d, 55h ; 'U'
0x1800266c8  cdq
0x1800266c9  lea     r15, [r13+2]
0x1800266cd  sub     eax, edx
0x1800266cf  sar     eax, 1
0x1800266d1  movsxd  rbx, eax
0x1800266d4  movzx   ecx, word ptr [r14+rbx*8]
0x1800266d9  lea     rsi, [r14+rbx*8]
0x1800266dd  lea     r15, [r15+rcx*2]
0x1800266e1  mov     [rsp+0B00h+var_A88], r15
0x1800266e6  mov     r10, r15
0x1800266e9  test    r8d, r8d
0x1800266ec  jg      short loc_18002670F
0x1800266ee  cmp     word ptr [r9], 0
0x1800266f3  jnz     loc_18002704C
0x1800266f9  cmp     word ptr [r10], 0
0x1800266fe  jz      loc_18002678A
0x180026704  mov     r9, [rsp+0B00h+var_A90]
0x180026709  lea     r11d, [rbx-1]
0x18002670d  jmp     short loc_1800266B5
0x18002670f  movzx   eax, word ptr [r9]
0x180026713  test    ax, ax
0x180026716  jz      short loc_1800266EE
0x180026718  movzx   edx, word ptr [r10]
0x18002671c  test    dx, dx
0x18002671f  jz      loc_18002704C
0x180026725  lea     ecx, [rax-41h]
0x180026728  cmp     cx, 19h
0x18002672c  ja      short loc_180026732
0x18002672e  or      ax, 20h
0x180026732  lea     ecx, [rdx-41h]
0x180026735  cmp     cx, 19h
0x180026739  jbe     short loc_18002676F
0x18002673b  cmp     ax, 5Fh ; '_'
0x18002673f  jnz     short loc_180026746
0x180026741  mov     eax, 2Dh ; '-'
0x180026746  cmp     dx, 5Fh ; '_'
0x18002674a  jnz     short loc_180026751
0x18002674c  mov     edx, 2Dh ; '-'
0x180026751  movzx   ecx, dx
0x180026754  movzx   edx, ax
0x180026757  sub     edx, ecx
0x180026759  jnz     loc_180027044
0x18002675f  dec     r8d
0x180026762  add     r9, 2
0x180026766  add     r10, 2
0x18002676a  jmp     loc_1800266E9
0x18002676f  or      dx, 20h
0x180026773  jmp     short loc_18002673B
0x180026775  xor     ebx, ebx
0x180026777  mov     r13d, 1000h
0x18002677d  mov     r12d, r13d
0x180026780  mov     [rsp+0B00h+var_A88], rbx
0x180026785  mov     r14d, ebx
0x180026788  jmp     short loc_1800267E1
0x18002678a  mov     ecx, [rsi+4]
0x18002678d  mov     r12d, ecx
0x180026790  btr     r12d, 1Fh
0x180026795  test    ecx, ecx
0x180026797  js      loc_180026DE3
0x18002679d  mov     eax, ecx
0x18002679f  shr     eax, 10h
0x1800267a2  test    al, 0Fh
0x1800267a4  jnz     loc_180026DE3
0x1800267aa  cmp     ecx, 40Ah
0x1800267b0  jz      loc_180026DE3
0x1800267b6  xor     ebx, ebx
0x1800267b8  mov     [rsp+0B00h+var_A88], rbx
0x1800267bd  movzx   ecx, word ptr [rsi+2]
0x1800267c1  movzx   eax, cs:word_1803A6BB0
0x1800267c8  imul    ecx, eax
0x1800267cb  movsxd  r14, ecx
0x1800267ce  add     r14, cs:qword_1803A6BB8
0x1800267d5  jnz     loc_180026B44
0x1800267db  mov     r13d, 1000h
0x1800267e1  call    Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline
0x1800267e6  test    eax, eax
0x1800267e8  jz      loc_180026ABD
0x1800267ee  xorps   xmm0, xmm0
0x1800267f1  mov     [rsp+0B00h+KeyHandle], rbx
0x1800267f6  xor     eax, eax
0x1800267f8  lea     rsi, aRegistryMachin_1; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800267ff  mov     r15d, 7FFFFFFEh
0x180026805  lea     rax, [rbp+0A00h+pszSrc]
0x18002680c  mov     edi, 200h
0x180026811  mov     ecx, r15d
0x180026814  movups  xmmword ptr [rbp+0A00h+ObjectAttributes.ObjectName], xmm0
0x180026818  mov     r8, rsi
0x18002681b  mov     edx, edi
0x18002681d  movups  xmmword ptr [rbp+0A00h+ObjectAttributes+1Ch], xmm0
0x180026821  movups  xmmword ptr [rbp+0A00h+ObjectAttributes.Length], xmm0
0x180026825  movups  xmmword ptr [rsp+0B00h+DestinationString.Buffer], xmm0
0x18002682a  test    rcx, rcx
0x18002682d  jz      short loc_18002684E
0x18002682f  movzx   r9d, word ptr [r8]
0x180026833  test    r9w, r9w
0x180026837  jz      short loc_18002684E
0x180026839  mov     [rax], r9w
0x18002683d  add     r8, 2
0x180026841  add     rax, 2
0x180026845  dec     rcx
0x180026848  sub     rdx, 1
0x18002684c  jnz     short loc_18002682A
0x18002684e  test    rdx, rdx
0x180026851  lea     rcx, [rax-2]
0x180026855  cmovnz  rcx, rax
0x180026859  mov     [rcx], bx
0x18002685c  jnz     loc_1800273CF
0x180026862  mov     r15, rbx
0x180026865  xorps   xmm0, xmm0
0x180026868  mov     [rsp+0B00h+KeyHandle], rbx
0x18002686d  xor     eax, eax
0x18002686f  mov     r9d, 7FFFFFFEh
0x180026875  movups  xmmword ptr [rbp+0A00h+ObjectAttributes.ObjectName], xmm0
0x180026879  mov     ecx, r9d
0x18002687c  mov     rdx, rdi
0x18002687f  movups  xmmword ptr [rbp+0A00h+ObjectAttributes+1Ch], xmm0
0x180026883  lea     rax, [rbp+0A00h+SourceString]
0x18002688a  movups  xmmword ptr [rbp+0A00h+ObjectAttributes.Length], xmm0
0x18002688e  movups  xmmword ptr [rsp+0B00h+DestinationString.Buffer], xmm0
0x180026893  test    rcx, rcx
0x180026896  jz      short loc_1800268B7
0x180026898  movzx   r8d, word ptr [rsi]
0x18002689c  test    r8w, r8w
0x1800268a0  jz      short loc_1800268B7
0x1800268a2  mov     [rax], r8w
0x1800268a6  add     rsi, 2
0x1800268aa  add     rax, 2
0x1800268ae  dec     rcx
0x1800268b1  sub     rdx, 1
0x1800268b5  jnz     short loc_180026893
0x1800268b7  test    rdx, rdx
0x1800268ba  lea     rcx, [rax-2]
0x1800268be  cmovnz  rcx, rax
0x1800268c2  mov     [rcx], bx
0x1800268c5  jz      loc_1800269AF
0x1800268cb  mov     rcx, rdi
0x1800268ce  lea     rax, [rbp+0A00h+SourceString]
0x1800268d5  cmp     word ptr [rax], 0
0x1800268d9  jz      short loc_1800268E5
0x1800268db  add     rax, 2
0x1800268df  sub     rcx, 1
0x1800268e3  jnz     short loc_1800268D5
0x1800268e5  mov     r8, rdi
0x1800268e8  sub     r8, rcx
0x1800268eb  test    rcx, rcx
0x1800268ee  cmovz   r8, rbx
0x1800268f2  jz      loc_1800269AF
0x1800268f8  sub     rdi, r8
0x1800268fb  lea     rdx, aNlsExtendedloc; "\\Nls\\ExtendedLocale"
0x180026902  lea     r8, [rbp+r8*2+0A00h+SourceString]
0x18002690a  mov     rcx, r9
0x18002690d  jz      short loc_180026932
0x18002690f  nop
0x180026910  test    rcx, rcx
0x180026913  jz      short loc_180026932
0x180026915  movzx   eax, word ptr [rdx]
0x180026918  test    ax, ax
0x18002691b  jz      short loc_180026932
0x18002691d  mov     [r8], ax
0x180026921  add     rdx, 2
0x180026925  add     r8, 2
0x180026929  dec     rcx
0x18002692c  sub     rdi, 1
0x180026930  jnz     short loc_180026910
0x180026932  test    rdi, rdi
0x180026935  lea     rcx, [r8-2]
0x180026939  cmovnz  rcx, r8
0x18002693d  mov     [rcx], bx
0x180026940  jz      short loc_1800269AF
0x180026942  lea     rdx, [rbp+0A00h+SourceString]; SourceString
0x180026949  lea     rcx, [rsp+0B00h+DestinationString.Buffer]; DestinationString
0x18002694e  call    cs:__imp_RtlInitUnicodeString
0x180026955  nop     dword ptr [rax+rax+00h]
0x18002695a  lea     rax, [rsp+0B00h+DestinationString.Buffer]
0x18002695f  mov     [rbp+0A00h+ObjectAttributes.Length], 30h ; '0'
0x180026966  xorps   xmm0, xmm0
0x180026969  mov     [rbp+0A00h+ObjectAttributes.ObjectName], rax
0x18002696d  lea     r8, [rbp+0A00h+ObjectAttributes]; ObjectAttributes
0x180026971  mov     [rbp+0A00h+ObjectAttributes.RootDirectory], rbx
0x180026975  mov     edx, 20019h; DesiredAccess
0x18002697a  mov     [rbp+0A00h+ObjectAttributes.Attributes], 40h ; '@'
0x180026981  lea     rcx, [rsp+0B00h+KeyHandle]; KeyHandle
0x180026986  movdqu  xmmword ptr [rbp+0A00h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002698b  call    cs:__imp_NtOpenKey
0x180026992  nop     dword ptr [rax+rax+00h]
0x180026997  test    eax, eax
0x180026999  jns     loc_1800273DE
0x18002699f  mov     rdi, rbx
0x1800269a2  mov     [rsp+0B00h+KeyHandle], rbx
0x1800269a7  test    eax, eax
0x1800269a9  jns     loc_180026B7B
0x1800269af  test    r15, r15
0x1800269b2  jz      loc_180026DEA
0x1800269b8  xor     ecx, ecx
0x1800269ba  call    CreateLocaleHashNode
0x1800269bf  mov     rdi, rax
0x1800269c2  test    rax, rax
0x1800269c5  jz      loc_180026DA9
0x1800269cb  mov     esi, [r15]
0x1800269ce  add     rsi, r15
0x1800269d1  mov     r8d, [rsi+1Ch]
0x1800269d5  add     r8, r15
0x1800269d8  mov     [rax+28h], r8
0x1800269dc  mov     [rax+38h], r8
0x1800269e0  mov     r9d, [rsi+38h]
0x1800269e4  add     r9, r15
0x1800269e7  mov     r15d, 1
0x1800269ed  mov     [rax+30h], r9
0x1800269f1  mov     [rax+40h], r9
0x1800269f5  mov     eax, [rsi]
0x1800269f7  mov     [rdi+48h], eax
0x1800269fa  test    [r8+18h], r15b
0x1800269fe  jz      loc_180026FEF
0x180026a04  mov     dword ptr [rdi+4Ch], 20h ; ' '
0x180026a0b  mov     [rdi+68h], rdi
0x180026a0f  mov     rdx, [rdi+28h]
0x180026a13  mov     rcx, [rdi+30h]
0x180026a17  mov     eax, [rdx]
0x180026a19  inc     rax
0x180026a1c  lea     r8, [rcx+rax*2]
0x180026a20  mov     rax, [rsp+0B00h+var_A88]
0x180026a25  test    rax, rax
0x180026a28  mov     [rdi+10h], r8
0x180026a2c  cmovz   rax, r8
0x180026a30  mov     [rdi+8], rax
0x180026a34  mov     eax, [rdx+0B8h]
0x180026a3a  lea     rcx, [rcx+rax*2]
0x180026a3e  add     rcx, 2
0x180026a42  mov     [rdi+18h], rcx
0x180026a46  test    r14, r14
0x180026a49  jnz     loc_180026F16
0x180026a4f  cmp     [rdx+8], r13w
0x180026a54  jz      loc_1800273E8
0x180026a5a  test    r14, r14
0x180026a5d  jnz     loc_180026F22
0x180026a63  mov     rax, [rdi+10h]
0x180026a67  mov     [rdi+20h], rax
0x180026a6b  mov     eax, [rdi+4Ch]
0x180026a6e  test    ebx, ebx
0x180026a70  jz      loc_180026F50
0x180026a76  test    r14, r14
0x180026a79  mov     ecx, 8001h
0x180026a7e  cmovz   r15d, ecx
0x180026a82  or      r15d, eax
0x180026a85  mov     [rdi+4Ch], r15d
0x180026a89  test    r14, r14
0x180026a8c  jz      loc_180026F5F
0x180026a92  movzx   eax, word ptr [r14+0Ah]
0x180026a97  mov     [rdi+50h], ax
0x180026a9b  movzx   eax, word ptr [r14+7Ah]
0x180026aa0  mov     ecx, 0FFh
  ... truncated ...
```
