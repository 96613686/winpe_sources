# DnsNbt_Open

- ea: `0x18002625c`
- end: `0x180026923`
- name: `DnsNbt_Open`
- size: `1735`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800241a4`
- `0x180068b34`

## callees

- `0x180024554`
- `0x180024a10`
- `0x18002625c`
- `0x18002692c`
- `0x180026950`
- `0x180029d80`
- `0x18002b050`
- `0x18003ce84`
- `0x18008b5f0`
- `0x18008bf98`
- `0x1800ce078`
- `0x1800d3d48`
- `0x1800d40f8`
- `0x1800dbb48`
- `0x1800dbfe0`
- `0x1800de650`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800265dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800265dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800263a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026912`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800263a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026912`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002633d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002638f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002633d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002638f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026303`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026303`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180026409`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180026409`
- `ntdll!RtlInitUnicodeString` at `0x1800266d1`
- `ntdll!RtlInitUnicodeString` at `0x1800266d1`
- `ntdll!RtlNtStatusToDosError` at `0x180026743`
- `ntdll!RtlNtStatusToDosError` at `0x180026743`
- `ntdll!NtCreateFile` at `0x180026735`
- `ntdll!NtCreateFile` at `0x180026735`

## string_xrefs

- `0x1800262f5`: `SYSTEM\CurrentControlSet\Services\NetBT\Linkage`

## pseudocode

```c
char *__fastcall DnsNbt_Open(int a1, __int64 a2)
{
  BYTE *v4; // r14
  char *v5; // rdi
  LSTATUS v6; // ebx
  LSTATUS v7; // eax
  unsigned int v8; // esi
  char *v9; // rax
  char *v10; // rbx
  unsigned int v11; // r12d
  __int64 v12; // r13
  int v13; // eax
  int v14; // edx
  int v15; // r8d
  __int64 v16; // rcx
  wchar_t *v17; // r8
  __int64 v18; // rdx
  _WORD *v19; // rax
  _WORD *v20; // rcx
  WCHAR *v21; // r15
  int v22; // ebx
  unsigned int j; // r12d
  BYTE *i; // r15
  __int64 v26; // rcx
  _WORD *v27; // rax
  BYTE *v28; // r8
  __int64 v29; // rdx
  _WORD *v30; // rcx
  __int64 v31; // rax
  NTSTATUS v32; // eax
  ULONG v33; // eax
  int v34; // edx
  int v35; // ecx
  int v36; // r8d
  BYTE *v37; // rax
  __int64 v38; // rcx
  int v39; // [rsp+60h] [rbp-A0h]
  int v40; // [rsp+64h] [rbp-9Ch]
  int v41; // [rsp+6Ch] [rbp-94h]
  int v42; // [rsp+70h] [rbp-90h]
  BYTE *v43; // [rsp+78h] [rbp-88h]
  DWORD cbData; // [rsp+80h] [rbp-80h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-78h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-70h] BYREF
  DWORD Type; // [rsp+C0h] [rbp-40h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+C8h] [rbp-38h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D8h] [rbp-28h] BYREF
  wchar_t pszDest[72]; // [rsp+F0h] [rbp-10h] BYREF

  hKey = 0;
  v42 = dword_180111854;
  cbData = 0;
  v4 = 0;
  Type = 0;
  IoStatusBlock = 0;
  v5 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_dqd(a1, 15, (unsigned int)WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids, a1, a2);
  if ( !a1 && !a2 )
  {
    v6 = 87;
    goto LABEL_38;
  }
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\NetBT\\Linkage", 0, 0x20019u, &hKey);
  if ( v6 )
    goto LABEL_38;
  cbData = 0;
  v7 = RegQueryValueExW(hKey, L"Export", 0, &Type, 0, &cbData);
  v6 = v7;
  if ( v7 != 234 )
  {
    if ( v7 )
      goto LABEL_38;
  }
  v43 = (BYTE *)Dns_Allocate(cbData);
  v4 = v43;
  if ( !v43 )
  {
LABEL_79:
    v6 = 14;
    goto LABEL_38;
  }
  v6 = RegQueryValueExW(hKey, L"Export", 0, &Type, v43, &cbData);
  if ( v6 )
    goto LABEL_38;
  RegCloseKey(hKey);
  hKey = 0;
  if ( a1 )
  {
    v8 = 0;
    v37 = v43;
    if ( !*(_WORD *)v43 )
      goto LABEL_41;
    do
    {
      ++v8;
      v38 = -1;
      do
        ++v38;
      while ( *(_WORD *)&v37[2 * v38] );
      v37 += 2 * v38 + 2;
    }
    while ( *(_WORD *)v37 );
  }
  else
  {
    v8 = *(_DWORD *)(a2 + 68);
  }
  if ( v8 )
  {
    v9 = (char *)Dns_Allocate(1784 * v8 + 2400);
    v5 = v9;
    if ( v9 )
    {
      memset_0(v9, 0, 1784 * v8 + 2400);
      v10 = v5 + 624;
      InitializeCriticalSection((LPCRITICAL_SECTION)(v5 + 568));
      *((_DWORD *)v5 + 11) = 1;
      if ( a1 )
      {
        for ( i = v43; *(_WORD *)i; i += 2 * v31 + 2 )
        {
          v26 = 2147483646;
          v27 = v10 + 8;
          v28 = i;
          v29 = 261;
          do
          {
            if ( !v26 )
              break;
            if ( !*(_WORD *)v28 )
              break;
            *v27 = *(_WORD *)v28;
            v28 += 2;
            ++v27;
            --v26;
            --v29;
          }
          while ( v29 );
          v30 = v27 - 1;
          if ( v29 )
            v30 = v27;
          *v30 = 0;
          if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
            WPP_SF_S(1035, 16, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids, v10 + 8);
          *((_QWORD *)v10 + 71) = v5;
          v10 += 1776;
          v31 = -1;
          do
            ++v31;
          while ( *(_WORD *)&i[2 * v31] );
        }
      }
      else
      {
        v11 = 0;
        if ( *(_DWORD *)(a2 + 68) )
        {
          do
          {
            v12 = 160LL * v11;
            StringCchPrintfW(pszDest, 0x41u, L"\\Device\\NetBT_Tcpip_%s", *(_QWORD *)(a2 + v12 + 104));
            v39 = *(_DWORD *)(a2 + v12 + 200);
            v40 = IsInterfaceWWANPPP(*(unsigned int *)(a2 + v12 + 164));
            v13 = DnsNbt_CheckDeviceNameExists((PCNZWCH)v43);
            v41 = v13;
            if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
            {
              WPP_SF_Sdlll(
                *(_DWORD *)(a2 + v12 + 164),
                v14,
                v15,
                (unsigned int)pszDest,
                *(_DWORD *)(a2 + v12 + 164),
                v40,
                v39 == 0,
                v13);
              v13 = v41;
            }
            if ( v42 == 2 && !v39 || v40 || !v13 )
            {
              --v8;
              if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
                WPP_SF_S(1035, 18, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids, pszDest);
            }
            else
            {
              v16 = 2147483646;
              v17 = pszDest;
              v18 = 261;
              v19 = v10 + 8;
              do
              {
                if ( !v16 )
                  break;
                if ( !*v17 )
                  break;
                *v19++ = *v17++;
                --v16;
                --v18;
              }
              while ( v18 );
              v20 = v19 - 1;
              if ( v18 )
                v20 = v19;
              *v20 = 0;
              if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
                WPP_SF_S(1035, 19, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids, v10 + 8);
              *((_QWORD *)v10 + 71) = v5;
              *((_DWORD *)v10 + 147) = (v39 != 0) + 1;
              v10 += 1776;
            }
            ++v11;
          }
          while ( v11 < *(_DWORD *)(a2 + 68) );
          if ( !v8 )
          {
            v6 = 4312;
            if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
              WPP_SF_(1035, 20, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids);
            goto LABEL_38;
          }
        }
      }
      v21 = (WCHAR *)(v5 + 624);
      v22 = 0;
      for ( j = 0; j < v8; ++j )
      {
        RtlInitUnicodeString(&DestinationString, v21 + 4);
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v32 = NtCreateFile((PHANDLE)v21, 0x80000000, &ObjectAttributes, &IoStatusBlock, 0, 0, 3u, 3u, 0, 0, 0);
        v33 = RtlNtStatusToDosError(v32);
        if ( v33 || !*(_QWORD *)v21 )
        {
          if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
            WPP_SF_SD(v35, 22, (unsigned int)WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids, (_DWORD)v21 + 8, v33);
        }
        else
        {
          if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
            WPP_SF_S(1035, 21, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids, v21 + 4);
          ++v22;
        }
        v21 += 888;
      }
      v4 = v43;
      if ( v22 )
      {
        *((_DWORD *)v5 + 2) = v22;
        *((_DWORD *)v5 + 3) = v8;
        *((_QWORD *)v5 + 2) = v43;
        if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
          WPP_SF_qSdq(v35, v34, v36, (_DWORD)v5, (__int64)v43, v22, (__int64)(v5 + 624));
        AddRefNbtLookupContext(v5);
        return v5;
      }
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
        WPP_SF_(1035, 23, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids);
      v6 = 4312;
LABEL_38:
      if ( hKey )
        RegCloseKey(hKey);
      if ( !v4 )
        goto LABEL_42;
      goto LABEL_41;
    }
    goto LABEL_79;
  }
LABEL_41:
  DnsApiFree(v4);
LABEL_42:
  if ( v6 )
    SetLastError(v6);
  DnsNbt_Close(v5);
  return 0;
}

```

## disassembly

```asm
0x18002625c  mov     [rsp-8+arg_10], rbx
0x180026261  push    rbp
0x180026262  push    rsi
0x180026263  push    rdi
0x180026264  push    r12
0x180026266  push    r13
0x180026268  push    r14
0x18002626a  push    r15
0x18002626c  lea     rbp, [rsp-90h]
0x180026274  sub     rsp, 190h
0x18002627b  mov     rax, cs:__security_cookie
0x180026282  xor     rax, rsp
0x180026285  mov     [rbp+0C0h+var_40], rax
0x18002628c  xor     r13d, r13d
0x18002628f  xorps   xmm0, xmm0
0x180026292  xor     eax, eax
0x180026294  mov     [rbp+0C0h+hKey], r13
0x180026298  mov     eax, cs:dword_180111854
0x18002629e  xorps   xmm1, xmm1
0x1800262a1  movups  xmmword ptr [rbp+0C0h+ObjectAttributes.ObjectName], xmm0
0x1800262a5  mov     [rsp+1C0h+var_150], eax
0x1800262a9  mov     r15, rdx
0x1800262ac  mov     r12d, ecx
0x1800262af  mov     [rbp+0C0h+cbData], r13d
0x1800262b3  mov     r14d, r13d
0x1800262b6  mov     [rbp+0C0h+Type], r13d
0x1800262ba  movups  xmmword ptr [rbp+0C0h+IoStatusBlock], xmm0
0x1800262be  mov     edi, r13d
0x1800262c1  movups  xmmword ptr [rbp+0C0h+DestinationString.Length], xmm1
0x1800262c5  movups  xmmword ptr [rbp+0C0h+ObjectAttributes.Length], xmm0
0x1800262c9  movups  xmmword ptr [rbp+0C0h+ObjectAttributes+1Ch], xmm0
0x1800262cd  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800262d4  jnz     loc_1800267F0
0x1800262da  test    r12d, r12d
0x1800262dd  jz      loc_18002661D
0x1800262e3  lea     rax, [rbp+0C0h+hKey]
0x1800262e7  mov     r9d, 20019h; samDesired
0x1800262ed  xor     r8d, r8d; ulOptions
0x1800262f0  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1800262f5  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Services\\Ne"...
0x1800262fc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180026303  call    cs:__imp_RegOpenKeyExW
0x18002630a  nop     dword ptr [rax+rax+00h]
0x18002630f  mov     ebx, eax
0x180026311  test    eax, eax
0x180026313  jnz     loc_1800265BC
0x180026319  mov     rcx, [rbp+0C0h+hKey]; hKey
0x18002631d  lea     rax, [rbp+0C0h+cbData]
0x180026321  mov     [rsp+1C0h+lpcbData], rax; lpcbData
0x180026326  lea     r9, [rbp+0C0h+Type]; lpType
0x18002632a  xor     r8d, r8d; lpReserved
0x18002632d  mov     [rsp+1C0h+phkResult], r13; lpData
0x180026332  lea     rdx, ValueName; "Export"
0x180026339  mov     [rbp+0C0h+cbData], r13d
0x18002633d  call    cs:__imp_RegQueryValueExW
0x180026344  nop     dword ptr [rax+rax+00h]
0x180026349  mov     ebx, eax
0x18002634b  cmp     eax, 0EAh
0x180026350  jnz     loc_18002662C
0x180026356  mov     ecx, [rbp+0C0h+cbData]
0x180026359  call    Dns_Allocate
0x18002635e  mov     [rsp+1C0h+var_148], rax
0x180026363  mov     r14, rax
0x180026366  test    rax, rax
0x180026369  jz      loc_180026850
0x18002636f  mov     rcx, [rbp+0C0h+hKey]; hKey
0x180026373  lea     rax, [rbp+0C0h+cbData]
0x180026377  mov     [rsp+1C0h+lpcbData], rax; lpcbData
0x18002637c  lea     r9, [rbp+0C0h+Type]; lpType
0x180026380  xor     r8d, r8d; lpReserved
0x180026383  mov     [rsp+1C0h+phkResult], r14; lpData
0x180026388  lea     rdx, ValueName; "Export"
0x18002638f  call    cs:__imp_RegQueryValueExW
0x180026396  nop     dword ptr [rax+rax+00h]
0x18002639b  mov     ebx, eax
0x18002639d  test    eax, eax
0x18002639f  jnz     loc_1800265BC
0x1800263a5  mov     rcx, [rbp+0C0h+hKey]; hKey
0x1800263a9  call    cs:__imp_RegCloseKey
0x1800263b0  nop     dword ptr [rax+rax+00h]
0x1800263b5  mov     [rbp+0C0h+hKey], r13
0x1800263b9  test    r12d, r12d
0x1800263bc  jnz     loc_1800267BD
0x1800263c2  mov     esi, [r15+44h]
0x1800263c6  test    esi, esi
0x1800263c8  jz      loc_1800265CE
0x1800263ce  imul    eax, esi, 6F8h
0x1800263d4  add     eax, 960h
0x1800263d9  mov     ecx, eax
0x1800263db  mov     ebx, eax
0x1800263dd  call    Dns_Allocate
0x1800263e2  mov     rdi, rax
0x1800263e5  test    rax, rax
0x1800263e8  jz      loc_180026850
0x1800263ee  mov     r8d, ebx; Size
0x1800263f1  xor     edx, edx; Val
0x1800263f3  mov     rcx, rax; void *
0x1800263f6  call    memset_0
0x1800263fb  lea     rcx, [rdi+238h]; lpCriticalSection
0x180026402  lea     rbx, [rdi+270h]
0x180026409  call    cs:__imp_InitializeCriticalSection
0x180026410  nop     dword ptr [rax+rax+00h]
0x180026415  mov     dword ptr [rdi+2Ch], 1
0x18002641c  test    r12d, r12d
0x18002641f  jnz     loc_180026636
0x180026425  mov     r12d, r13d
0x180026428  cmp     [r15+44h], r13d
0x18002642c  jbe     loc_180026548
0x180026432  mov     eax, r12d
0x180026435  lea     r8, aDeviceNetbtTcp; "\\Device\\NetBT_Tcpip_%s"
0x18002643c  mov     edx, 41h ; 'A'; cchDest
0x180026441  lea     rcx, [rbp+0C0h+pszDest]; pszDest
0x180026445  lea     r13, [rax+rax*4]
0x180026449  shl     r13, 5
0x18002644d  mov     r9, [r15+r13+68h]
0x180026452  call    StringCchPrintfW
0x180026457  mov     eax, [r15+r13+0C8h]
0x18002645f  xor     ecx, ecx
0x180026461  test    eax, eax
0x180026463  mov     [rsp+1C0h+var_160], eax
0x180026467  setz    cl
0x18002646a  mov     [rsp+1C0h+var_158], ecx
0x18002646e  mov     ecx, [r15+r13+0A4h]
0x180026476  call    IsInterfaceWWANPPP
0x18002647b  mov     edx, [rbp+0C0h+cbData]
0x18002647e  lea     r8, [rbp+0C0h+pszDest]
0x180026482  mov     rcx, r14; lpString1
0x180026485  mov     [rsp+1C0h+var_15C], eax
0x180026489  call    DnsNbt_CheckDeviceNameExists
0x18002648e  mov     [rsp+1C0h+var_154], eax
0x180026492  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180026499  jnz     loc_18002685A
0x18002649f  mov     r13d, [rsp+1C0h+var_160]
0x1800264a4  xor     r11d, r11d
0x1800264a7  cmp     [rsp+1C0h+var_150], 2
0x1800264ac  jz      loc_18002688C
0x1800264b2  cmp     [rsp+1C0h+var_15C], r11d
0x1800264b7  jnz     loc_180026583
0x1800264bd  test    eax, eax
0x1800264bf  jz      loc_180026583
0x1800264c5  mov     ecx, 7FFFFFFEh
0x1800264ca  lea     r8, [rbp+0C0h+pszDest]
0x1800264ce  mov     edx, 105h
0x1800264d3  lea     rax, [rbx+8]
0x1800264d7  test    rcx, rcx
0x1800264da  jz      short loc_1800264FB
0x1800264dc  movzx   r9d, word ptr [r8]
0x1800264e0  test    r9w, r9w
0x1800264e4  jz      short loc_1800264FB
0x1800264e6  mov     [rax], r9w
0x1800264ea  add     r8, 2
0x1800264ee  add     rax, 2
0x1800264f2  dec     rcx
0x1800264f5  sub     rdx, 1
0x1800264f9  jnz     short loc_1800264D7
0x1800264fb  test    rdx, rdx
0x1800264fe  lea     rcx, [rax-2]
0x180026502  cmovnz  rcx, rax
0x180026506  mov     [rcx], r11w
0x18002650a  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180026511  jnz     loc_180026831
0x180026517  neg     r13d
0x18002651a  mov     [rbx+238h], rdi
0x180026521  sbb     eax, eax
0x180026523  neg     eax
0x180026525  inc     eax
0x180026527  mov     [rbx+24Ch], eax
0x18002652d  add     rbx, 6F0h
0x180026534  inc     r12d
0x180026537  cmp     r12d, [r15+44h]
0x18002653b  jb      loc_180026432
0x180026541  xor     r13d, r13d
0x180026544  test    esi, esi
0x180026546  jz      short loc_1800265AA
0x180026548  lea     r15, [rdi+270h]
0x18002654f  mov     ebx, r13d
0x180026552  mov     r12d, r13d
0x180026555  test    esi, esi
0x180026557  jnz     loc_1800266C3
0x18002655d  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180026564  jz      short loc_18002657C
0x180026566  mov     edx, 17h
0x18002656b  lea     r8, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids
0x180026572  mov     ecx, 40Bh
0x180026577  call    WPP_SF_
0x18002657c  mov     ebx, 10D8h
0x180026581  jmp     short loc_1800265BC
0x180026583  dec     esi
0x180026585  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18002658c  jz      short loc_180026534
0x18002658e  mov     edx, 12h
0x180026593  lea     r9, [rbp+0C0h+pszDest]
0x180026597  mov     ecx, 40Bh
0x18002659c  lea     r8, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids
0x1800265a3  call    WPP_SF_S
0x1800265a8  jmp     short loc_180026534
0x1800265aa  mov     ebx, 10D8h
0x1800265af  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800265b6  jnz     loc_18002689A
0x1800265bc  mov     rcx, [rbp+0C0h+hKey]; hKey
0x1800265c0  test    rcx, rcx
0x1800265c3  jnz     loc_180026912
0x1800265c9  test    r14, r14
0x1800265cc  jz      short loc_1800265D6
0x1800265ce  mov     rcx, r14; lpMem
0x1800265d1  call    DnsApiFree
0x1800265d6  test    ebx, ebx
0x1800265d8  jz      short loc_1800265E8
0x1800265da  mov     ecx, ebx; dwErrCode
0x1800265dc  call    cs:__imp_SetLastError
0x1800265e3  nop     dword ptr [rax+rax+00h]
0x1800265e8  mov     rcx, rdi; lpMem
0x1800265eb  call    DnsNbt_Close
0x1800265f0  xor     eax, eax
0x1800265f2  mov     rcx, [rbp+0C0h+var_40]
0x1800265f9  xor     rcx, rsp; StackCookie
0x1800265fc  call    __security_check_cookie
0x180026601  mov     rbx, [rsp+1C0h+arg_10]
0x180026609  add     rsp, 190h
0x180026610  pop     r15
0x180026612  pop     r14
0x180026614  pop     r13
0x180026616  pop     r12
0x180026618  pop     rdi
0x180026619  pop     rsi
0x18002661a  pop     rbp
0x18002661b  retn
0x18002661d  test    r15, r15
0x180026620  jnz     loc_1800262E3
0x180026626  lea     ebx, [r15+57h]
0x18002662a  jmp     short loc_1800265BC
0x18002662c  test    eax, eax
0x18002662e  jz      loc_180026356
0x180026634  jmp     short loc_1800265BC
0x180026636  mov     r15, r14
0x180026639  cmp     [r14], r13w
0x18002663d  jz      loc_180026548
0x180026643  mov     ecx, 7FFFFFFEh
0x180026648  lea     rax, [rbx+8]
0x18002664c  mov     r8, r15
0x18002664f  mov     edx, 105h
0x180026654  test    rcx, rcx
0x180026657  jz      short loc_180026678
0x180026659  movzx   r9d, word ptr [r8]
0x18002665d  test    r9w, r9w
0x180026661  jz      short loc_180026678
0x180026663  mov     [rax], r9w
0x180026667  add     r8, 2
0x18002666b  add     rax, 2
0x18002666f  dec     rcx
0x180026672  sub     rdx, 1
0x180026676  jnz     short loc_180026654
0x180026678  test    rdx, rdx
0x18002667b  lea     rcx, [rax-2]
0x18002667f  cmovnz  rcx, rax
0x180026683  mov     [rcx], r13w
0x180026687  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18002668e  jnz     loc_180026812
0x180026694  mov     [rbx+238h], rdi
0x18002669b  add     rbx, 6F0h
0x1800266a2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800266a6  inc     rax
0x1800266a9  cmp     [r15+rax*2], r13w
0x1800266ae  jnz     short loc_1800266A6
0x1800266b0  lea     r15, [r15+rax*2]
0x1800266b4  add     r15, 2
0x1800266b8  cmp     [r15], r13w
0x1800266bc  jnz     short loc_180026643
0x1800266be  jmp     loc_180026548
0x1800266c3  xor     r14d, r14d
0x1800266c6  lea     r13, [r15+8]
0x1800266ca  mov     rdx, r13; SourceString
0x1800266cd  lea     rcx, [rbp+0C0h+DestinationString]; DestinationString
0x1800266d1  call    cs:__imp_RtlInitUnicodeString
0x1800266d8  nop     dword ptr [rax+rax+00h]
0x1800266dd  mov     [rsp+1C0h+EaLength], r14d; EaLength
0x1800266e2  lea     rax, [rbp+0C0h+DestinationString]
0x1800266e6  mov     [rsp+1C0h+EaBuffer], r14; EaBuffer
0x1800266eb  lea     r9, [rbp+0C0h+IoStatusBlock]; IoStatusBlock
0x1800266ef  mov     [rsp+1C0h+CreateOptions], r14d; CreateOptions
0x1800266f4  lea     r8, [rbp+0C0h+ObjectAttributes]; ObjectAttributes
0x1800266f8  mov     [rbp+0C0h+ObjectAttributes.ObjectName], rax
0x1800266fc  xorps   xmm0, xmm0
0x1800266ff  mov     eax, 3
0x180026704  mov     [rbp+0C0h+ObjectAttributes.Length], 30h ; '0'
0x18002670b  mov     [rsp+1C0h+CreateDisposition], eax; CreateDisposition
0x18002670f  mov     edx, 80000000h; DesiredAccess
0x180026714  mov     [rsp+1C0h+ShareAccess], eax; ShareAccess
0x180026718  mov     rcx, r15; FileHandle
0x18002671b  mov     dword ptr [rsp+1C0h+lpcbData], r14d; FileAttributes
0x180026720  mov     [rsp+1C0h+phkResult], r14; AllocationSize
0x180026725  mov     [rbp+0C0h+ObjectAttributes.RootDirectory], r14
0x180026729  mov     [rbp+0C0h+ObjectAttributes.Attributes], 40h ; '@'
0x180026730  movdqu  xmmword ptr [rbp+0C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180026735  call    cs:__imp_NtCreateFile
0x18002673c  nop     dword ptr [rax+rax+00h]
0x180026741  mov     ecx, eax; Status
0x180026743  call    cs:__imp_RtlNtStatusToDosError
0x18002674a  nop     dword ptr [rax+rax+00h]
0x18002674f  test    eax, eax
  ... truncated ...
```
