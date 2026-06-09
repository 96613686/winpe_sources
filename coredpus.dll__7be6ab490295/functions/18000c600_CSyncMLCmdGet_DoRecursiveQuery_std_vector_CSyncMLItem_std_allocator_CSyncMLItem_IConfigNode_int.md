# CSyncMLCmdGet::DoRecursiveQuery(std::vector<CSyncMLItem *,std::allocator<CSyncMLItem *>> &,IConfigNode *,int)

- ea: `0x18000c600`
- end: `0x18000cf9f`
- name: `?DoRecursiveQuery@CSyncMLCmdGet@@AEAAJAEAV?$vector@PEAVCSyncMLItem@@V?$allocator@PEAVCSyncMLItem@@@std@@@std@@PEAUIConfigNode@@H@Z`
- size: `2463`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000b560`

## callees

- `0x180003f70`
- `0x18000a760`
- `0x18000c600`
- `0x1800128a0`
- `0x180014330`
- `0x1800146e4`
- `0x180014c60`
- `0x180015c87`
- `0x18001d670`
- `0x180020114`
- `0x180030010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000cb70`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000cb70`
- `OLEAUT32!__imp_VariantInit` at `0x18000c6c3`
- `OLEAUT32!__imp_VariantInit` at `0x18000c6d7`
- `OLEAUT32!__imp_VariantInit` at `0x18000c7ef`
- `OLEAUT32!__imp_VariantInit` at `0x18000c6c3`
- `OLEAUT32!__imp_VariantInit` at `0x18000c6d7`
- `OLEAUT32!__imp_VariantInit` at `0x18000c7ef`
- `OLEAUT32!__imp_VariantClear` at `0x18000c84a`
- `OLEAUT32!__imp_VariantClear` at `0x18000c9e1`
- `OLEAUT32!__imp_VariantClear` at `0x18000c9f5`
- `OLEAUT32!__imp_VariantClear` at `0x18000ce99`
- `OLEAUT32!__imp_VariantClear` at `0x18000cead`
- `OLEAUT32!__imp_VariantClear` at `0x18000c84a`
- `OLEAUT32!__imp_VariantClear` at `0x18000c9e1`
- `OLEAUT32!__imp_VariantClear` at `0x18000c9f5`
- `OLEAUT32!__imp_VariantClear` at `0x18000ce99`
- `OLEAUT32!__imp_VariantClear` at `0x18000cead`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000c95b`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000c95b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ca09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ce7d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ca09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ce7d`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000c6e3`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000c6e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c720`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c720`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c761`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c761`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c790`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c790`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000cf35`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000cf35`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSyncMLCmdGet::DoRecursiveQuery(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  int v5; // esi
  LONG lVal; // r15d
  char IsStateSeparationEnabled; // al
  const WCHAR *v8; // rdx
  int appended; // edi
  LONGLONG llVal; // rbx
  int v11; // ecx
  int v12; // eax
  struct IConfigNode **v13; // rbx
  struct IConfigNode **i; // rsi
  const struct std::nothrow_t *v15; // rdx
  void *v16; // rax
  const OLECHAR *v17; // rax
  void *v18; // rsi
  signed __int64 v19; // rdi
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // r14
  char *v24; // rbx
  void *v25; // rax
  const void *v26; // rdx
  char *v27; // rcx
  char *v28; // r8
  const struct std::nothrow_t *v29; // rdx
  void *v30; // rcx
  char *v31; // rbx
  size_t v32; // rdi
  unsigned int v33; // ebx
  unsigned __int16 *lpcbData; // [rsp+28h] [rbp-130h]
  int v36; // [rsp+40h] [rbp-118h] BYREF
  int v37; // [rsp+44h] [rbp-114h] BYREF
  LONG v38; // [rsp+48h] [rbp-110h]
  int v39[2]; // [rsp+50h] [rbp-108h] BYREF
  BYTE Data[4]; // [rsp+58h] [rbp-100h] BYREF
  int v41; // [rsp+5Ch] [rbp-FCh]
  __int64 v42; // [rsp+60h] [rbp-F8h] BYREF
  __int64 v43; // [rsp+68h] [rbp-F0h] BYREF
  void *Src[2]; // [rsp+70h] [rbp-E8h]
  char *v45; // [rsp+80h] [rbp-D8h]
  DWORD Type; // [rsp+88h] [rbp-D0h] BYREF
  HLOCAL hMem; // [rsp+90h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+98h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+A0h] [rbp-B8h] BYREF
  int v50[2]; // [rsp+A8h] [rbp-B0h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+B0h] [rbp-A8h] BYREF
  VARIANTARG pvarSrc; // [rsp+C0h] [rbp-98h] BYREF
  VARIANTARG pvarg; // [rsp+D8h] [rbp-80h] BYREF
  VARIANTARG v54; // [rsp+F0h] [rbp-68h] BYREF
  int v55; // [rsp+108h] [rbp-50h]
  int v56; // [rsp+10Ch] [rbp-4Ch]
  int *v57; // [rsp+110h] [rbp-48h]
  __int64 v58; // [rsp+118h] [rbp-40h]

  v36 = a4;
  *(_QWORD *)v50 = a2;
  v42 = 0;
  v43 = 0;
  hMem = 0;
  v37 = 0;
  v41 = 0;
  Type = 0;
  cbData = 4;
  *(_DWORD *)Data = 0;
  v5 = 1;
  lVal = 1;
  v38 = 1;
  *(_QWORD *)v39 = 0;
  *(_OWORD *)Src = 0;
  v45 = 0;
  memset(&pvarSrc, 0, sizeof(pvarSrc));
  memset(&pvarg, 0, sizeof(pvarg));
  hKey = 0;
  VariantInit(&pvarSrc);
  VariantInit(&pvarg);
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v8 = L"OSData\\Software\\Microsoft\\Provisioning\\OMADM";
  if ( !IsStateSeparationEnabled )
    v8 = L"Software\\Microsoft\\Provisioning\\OMADM";
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, v8, 0, 0x20019u, &hKey)
    || RegQueryValueExW(hKey, L"RecursiveQueryDelayThreshold", 0, &Type, Data, &cbData)
    || Type != 4 )
  {
    *(_DWORD *)Data = 16;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  *(_QWORD *)&EventDescriptor.Id = a3;
  if ( a3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 8LL))(a3);
  while ( 1 )
  {
    appended = 0;
    if ( !a3 )
      break;
    memset(&v54, 0, sizeof(v54));
    VariantInit(&v54);
    appended = (*(__int64 (__fastcall **)(__int64, __int64 *, VARIANTARG *))(*(_QWORD *)a3 + 160LL))(
                 a3,
                 CFGMGR_PROPERTY_DATATYPE,
                 &v54);
    if ( appended >= 0 )
    {
      if ( v54.vt == 3 )
      {
        lVal = v54.lVal;
        v38 = v54.lVal;
      }
      else
      {
        appended = -2147467259;
      }
    }
    VariantClear(&v54);
    if ( v5 || appended != -2147024891 )
    {
      if ( appended < 0 )
        break;
      appended = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a3 + 120LL))(a3, v39);
      if ( appended < 0 )
        break;
      appended = (*(__int64 (__fastcall **)(__int64, __int128 *, VARIANTARG *))(*(_QWORD *)a3 + 160LL))(
                   a3,
                   &CFGMGR_PROPERTY_SEMANTICTYPE,
                   &pvarg);
      if ( ((appended + 0x80000000) & 0x80000000) == 0 && appended != -2147023728 )
        break;
      llVal = 0;
      v11 = 8;
      if ( pvarg.vt == 8 )
        llVal = pvarg.llVal;
      if ( lVal == 8 )
      {
        v17 = &word_180032B28;
        if ( llVal )
          v17 = (const OLECHAR *)llVal;
        appended = CSyncMLCmdGet::AppendResultItem(8, v50[0], v39[0], 8, (__int64)v17, 0, 0);
        if ( appended < 0 )
          break;
        appended = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a3 + 192LL))(a3, &v42);
        if ( appended < 0 )
          break;
        appended = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v42 + 24LL))(
                     v42,
                     1,
                     &v43,
                     &v37);
        if ( appended < 0 )
          break;
        while ( v37 == 1 )
        {
          try
          {
            v18 = Src[1];
            if ( Src[1] == v45 )
            {
              v19 = ((char *)Src[1] - (char *)Src[0]) >> 3;
              if ( v19 == 0x1FFFFFFFFFFFFFFFLL )
                std::vector<CSyncMLCmd *>::_Xlength();
              v20 = (v45 - (char *)Src[0]) >> 3;
              if ( v20 > 0x1FFFFFFFFFFFFFFFLL - (v20 >> 1) )
LABEL_104:
                std::_Throw_bad_array_new_length();
              v21 = (v20 >> 1) + v20;
              v22 = v19 + 1;
              if ( v21 >= v19 + 1 )
                v22 = v21;
              if ( v22 > 0x1FFFFFFFFFFFFFFFLL )
                std::_Throw_bad_array_new_length();
              v23 = 8 * v22;
              if ( 8 * v22 )
              {
                if ( v23 < 0x1000 )
                {
                  v24 = (char *)operator new(8 * v22);
                }
                else
                {
                  if ( v23 + 39 < v23 )
                    goto LABEL_104;
                  v25 = operator new(v23 + 39);
                  if ( !v25 )
LABEL_82:
                    __fastfail(5u);
                  v24 = (char *)(((unsigned __int64)v25 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
                  *((_QWORD *)v24 - 1) = v25;
                }
              }
              else
              {
                v24 = 0;
              }
              *(_QWORD *)&v24[8 * v19] = v43;
              v26 = Src[0];
              v27 = v24;
              if ( v18 == Src[1] )
              {
                v28 = (char *)((char *)Src[1] - (char *)Src[0]);
              }
              else
              {
                memmove_0(v24, Src[0], (size_t)v18 - (unsigned __int64)Src[0]);
                v28 = (char *)((char *)Src[1] - (char *)v18);
                v27 = &v24[8 * v19 + 8];
                v26 = v18;
              }
              memmove_0(v27, v26, (size_t)v28);
              if ( Src[0] )
              {
                v29 = (const struct std::nothrow_t *)(8 * ((v45 - (char *)Src[0]) >> 3));
                if ( (unsigned __int64)v29 < 0x1000 )
                {
                  v30 = Src[0];
                }
                else
                {
                  v30 = (void *)*((_QWORD *)Src[0] - 1);
                  if ( (unsigned __int64)((char *)Src[0] - (char *)v30 - 8) > 0x1F )
                    goto LABEL_82;
                  v29 = (const struct std::nothrow_t *)((char *)v29 + 39);
                }
                operator delete(v30, v29);
              }
              Src[0] = v24;
              Src[1] = &v24[8 * v19 + 8];
              v45 = &v24[v23];
            }
            else
            {
              *(_QWORD *)Src[1] = v43;
              Src[1] = (char *)Src[1] + 8;
            }
          }
          catch ( std::bad_alloc )
          {
            v36 = -2147024882;
            appended = -2147024882;
            a3 = *(_QWORD *)&EventDescriptor.Id;
            goto LABEL_38;
          }
          v37 = 0;
          appended = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v42 + 24LL))(
                       v42,
                       1,
                       &v43,
                       &v37);
          if ( appended < 0 )
            goto LABEL_38;
        }
        lVal = v38;
      }
      else
      {
        if ( v36 )
        {
          v12 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)a3 + 104LL))(a3, &pvarSrc);
          appended = v12;
          if ( !v5 && (v12 == -2147467263 || v12 == -2046820335 || v12 == -2046820329) )
            goto LABEL_89;
          if ( v12 < 0 )
            break;
          if ( pvarSrc.vt == 1 )
          {
            appended = VariantChangeType(&pvarSrc, &pvarSrc, 0, 8u);
            if ( appended < 0 )
              break;
            lpcbData = pvarSrc.bstrVal;
          }
          else
          {
            appended = ConformVariantToData(&pvarSrc, lVal, 0, (unsigned __int16 **)&hMem);
            if ( appended < 0 )
              break;
            lpcbData = (unsigned __int16 *)hMem;
          }
        }
        else
        {
          lpcbData = 0;
        }
        appended = CSyncMLCmdGet::AppendResultItem(v11, v50[0], v39[0], lVal, llVal, lpcbData, 0);
        if ( appended < 0 )
          break;
      }
    }
LABEL_89:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 16LL))(a3);
    if ( v42 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
      v42 = 0;
    }
    if ( *(_QWORD *)v39 )
    {
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v39 + 16LL))(*(_QWORD *)v39);
      *(_QWORD *)v39 = 0;
    }
    LocalFree(hMem);
    hMem = 0;
    VariantClear(&pvarSrc);
    VariantClear(&pvarg);
    v43 = 0;
    v5 = 0;
    a3 = 0;
    *(_QWORD *)&EventDescriptor.Id = 0;
    v31 = (char *)Src[0];
    if ( ((char *)Src[1] - (char *)Src[0]) >> 3 )
    {
      a3 = *(_QWORD *)Src[0];
      *(_QWORD *)&EventDescriptor.Id = *(_QWORD *)Src[0];
      v32 = (char *)Src[1] - ((char *)Src[0] + 8);
      memmove_0(Src[0], (char *)Src[0] + 8, v32);
      Src[1] = &v31[v32];
    }
    v33 = ++v41;
    if ( *(_DWORD *)Data && *(_DWORD *)Data < v33 )
    {
      Sleep(0);
      v41 = 0;
    }
  }
LABEL_38:
  VariantClear(&pvarSrc);
  VariantClear(&pvarg);
  LocalFree(hMem);
  v13 = (struct IConfigNode **)Src[1];
  for ( i = (struct IConfigNode **)Src[0]; i != v13; ++i )
    CSyncMLCmdGet::DeallocConfigNode(*i);
  if ( v42 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    v42 = 0;
  }
  if ( a3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 16LL))(a3);
  if ( v43 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    v43 = 0;
  }
  if ( *(_QWORD *)v39 )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v39 + 16LL))(*(_QWORD *)v39);
    *(_QWORD *)v39 = 0;
  }
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v36 = appended;
    v57 = &v36;
    v58 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 5;
    EventDescriptor.Keyword = 0;
    *(_QWORD *)&v54.vt = off_18003E050;
    v54.llVal = (unsigned __int16)*off_18003E050 | 0x200000000LL;
    v54.pRecInfo = (IRecordInfo *)byte_180036973;
    v55 = 29;
    v56 = 1;
    v38 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, (PEVENT_DATA_DESCRIPTOR)&v54);
  }
  if ( Src[0] )
  {
    v15 = (const struct std::nothrow_t *)(8 * ((v45 - (char *)Src[0]) >> 3));
    if ( (unsigned __int64)v15 < 0x1000 )
    {
      v16 = Src[0];
    }
    else
    {
      v16 = (void *)*((_QWORD *)Src[0] - 1);
      if ( (unsigned __int64)((char *)Src[0] - (char *)v16 - 8) > 0x1F )
        __fastfail(5u);
      v15 = (const struct std::nothrow_t *)((char *)v15 + 39);
    }
    operator delete(v16, v15);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18000c600  mov     r11, rsp
0x18000c603  mov     [r11+8], rbx
0x18000c607  mov     [r11+20h], rsi
0x18000c60b  push    rdi
0x18000c60c  push    r12
0x18000c60e  push    r13
0x18000c610  push    r14
0x18000c612  push    r15
0x18000c614  sub     rsp, 130h
0x18000c61b  mov     rax, cs:__security_cookie
0x18000c622  xor     rax, rsp
0x18000c625  mov     [rsp+158h+var_38], rax
0x18000c62d  mov     [rsp+158h+var_118], r9d
0x18000c632  mov     r13, r8
0x18000c635  mov     qword ptr [rsp+158h+var_B0], rdx
0x18000c63d  xor     r12d, r12d
0x18000c640  mov     [rsp+158h+var_F8], r12
0x18000c645  mov     [rsp+158h+var_F0], r12
0x18000c64a  mov     [r11-0C8h], r12
0x18000c651  mov     [rsp+158h+var_114], r12d
0x18000c656  mov     [rsp+158h+var_FC], r12d
0x18000c65b  mov     [r11-0D0h], r12d
0x18000c662  mov     [rsp+158h+cbData], 4
0x18000c66d  mov     dword ptr [rsp+158h+Data], r12d
0x18000c672  mov     r14d, 1
0x18000c678  mov     esi, r14d
0x18000c67b  mov     r15d, r14d
0x18000c67e  mov     [rsp+158h+var_110], r14d
0x18000c683  mov     qword ptr [rsp+158h+var_108], r12
0x18000c688  xorps   xmm0, xmm0
0x18000c68b  movdqu  xmmword ptr [rsp+158h+Src], xmm0
0x18000c691  mov     [r11-0D8h], r12
0x18000c698  xor     eax, eax
0x18000c69a  movups  xmmword ptr [rsp+158h+pvarSrc], xmm0
0x18000c6a2  mov     [r11-88h], rax
0x18000c6a9  xorps   xmm1, xmm1
0x18000c6ac  movups  xmmword ptr [r11-80h], xmm1
0x18000c6b1  mov     [r11-70h], rax
0x18000c6b5  mov     [r11-0C0h], r12
0x18000c6bc  lea     rcx, [r11-98h]; pvarg
0x18000c6c3  call    cs:__imp_VariantInit
0x18000c6ca  nop     dword ptr [rax+rax+00h]
0x18000c6cf  lea     rcx, [rsp+158h+pvarg]; pvarg
0x18000c6d7  call    cs:__imp_VariantInit
0x18000c6de  nop     dword ptr [rax+rax+00h]
0x18000c6e3  call    cs:__imp_RtlIsStateSeparationEnabled
0x18000c6ea  nop     dword ptr [rax+rax+00h]
0x18000c6ef  lea     rcx, SubKey; "Software\\Microsoft\\Provisioning\\OMAD"...
0x18000c6f6  lea     rdx, aOsdataSoftware_0; "OSData\\Software\\Microsoft\\Provisioni"...
0x18000c6fd  test    al, al
0x18000c6ff  cmovz   rdx, rcx; lpSubKey
0x18000c703  lea     rax, [rsp+158h+hKey]
0x18000c70b  mov     [rsp+158h+phkResult], rax; phkResult
0x18000c710  mov     r9d, 20019h; samDesired
0x18000c716  xor     r8d, r8d; ulOptions
0x18000c719  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c720  call    cs:__imp_RegOpenKeyExW
0x18000c727  nop     dword ptr [rax+rax+00h]
0x18000c72c  test    eax, eax
0x18000c72e  jnz     short loc_18000C77B
0x18000c730  lea     rax, [rsp+158h+cbData]
0x18000c738  mov     [rsp+158h+lpcbData], rax; lpcbData
0x18000c73d  lea     rax, [rsp+158h+Data]
0x18000c742  mov     [rsp+158h+phkResult], rax; lpData
0x18000c747  lea     r9, [rsp+158h+Type]; lpType
0x18000c74f  xor     r8d, r8d; lpReserved
0x18000c752  lea     rdx, ValueName; "RecursiveQueryDelayThreshold"
0x18000c759  mov     rcx, [rsp+158h+hKey]; hKey
0x18000c761  call    cs:__imp_RegQueryValueExW
0x18000c768  nop     dword ptr [rax+rax+00h]
0x18000c76d  test    eax, eax
0x18000c76f  jnz     short loc_18000C77B
0x18000c771  cmp     [rsp+158h+Type], 4
0x18000c779  jz      short loc_18000C783
0x18000c77b  mov     dword ptr [rsp+158h+Data], 10h
0x18000c783  mov     rcx, [rsp+158h+hKey]; hKey
0x18000c78b  test    rcx, rcx
0x18000c78e  jz      short loc_18000C7A4
0x18000c790  call    cs:__imp_RegCloseKey
0x18000c797  nop     dword ptr [rax+rax+00h]
0x18000c79c  mov     [rsp+158h+hKey], r12
0x18000c7a4  mov     qword ptr [rsp+158h+EventDescriptor.Id], r13
0x18000c7ac  test    r13, r13
0x18000c7af  jz      short loc_18000C7C1
0x18000c7b1  mov     rax, [r13+0]
0x18000c7b5  mov     rcx, r13
0x18000c7b8  mov     rax, [rax+8]
0x18000c7bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7c1  mov     ebx, 80000000h
0x18000c7c6  mov     edi, r12d
0x18000c7c9  test    r13, r13
0x18000c7cc  jz      loc_18000C9D9
0x18000c7d2  xorps   xmm0, xmm0
0x18000c7d5  xor     eax, eax
0x18000c7d7  movups  xmmword ptr [rsp+158h+var_68], xmm0
0x18000c7df  mov     qword ptr [rsp+158h+var_68+10h], rax
0x18000c7e7  lea     rcx, [rsp+158h+var_68]; pvarg
0x18000c7ef  call    cs:__imp_VariantInit
0x18000c7f6  nop     dword ptr [rax+rax+00h]
0x18000c7fb  mov     rax, [r13+0]
0x18000c7ff  lea     r8, [rsp+158h+var_68]
0x18000c807  lea     rdx, CFGMGR_PROPERTY_DATATYPE
0x18000c80e  mov     rcx, r13
0x18000c811  mov     rax, [rax+0A0h]
0x18000c818  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c81d  mov     edi, eax
0x18000c81f  test    eax, eax
0x18000c821  js      short loc_18000C842
0x18000c823  cmp     word ptr [rsp+158h+var_68], 3
0x18000c82c  jz      short loc_18000C835
0x18000c82e  mov     edi, 80004005h
0x18000c833  jmp     short loc_18000C842
0x18000c835  mov     r15d, dword ptr [rsp+158h+var_68+8]
0x18000c83d  mov     [rsp+158h+var_110], r15d
0x18000c842  lea     rcx, [rsp+158h+var_68]; pvarg
0x18000c84a  call    cs:__imp_VariantClear
0x18000c851  nop     dword ptr [rax+rax+00h]
0x18000c856  test    esi, esi
0x18000c858  jnz     short loc_18000C866
0x18000c85a  cmp     edi, 80070005h
0x18000c860  jz      loc_18000CE2F
0x18000c866  test    edi, edi
0x18000c868  js      loc_18000C9D9
0x18000c86e  mov     rax, [r13+0]
0x18000c872  lea     rdx, [rsp+158h+var_108]
0x18000c877  mov     rcx, r13
0x18000c87a  mov     rax, [rax+78h]
0x18000c87e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c883  mov     edi, eax
0x18000c885  test    eax, eax
0x18000c887  js      loc_18000C9D9
0x18000c88d  mov     rax, [r13+0]
0x18000c891  lea     r8, [rsp+158h+pvarg]
0x18000c899  lea     rdx, CFGMGR_PROPERTY_SEMANTICTYPE
0x18000c8a0  mov     rcx, r13
0x18000c8a3  mov     rax, [rax+0A0h]
0x18000c8aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8af  mov     edi, eax
0x18000c8b1  add     eax, ebx
0x18000c8b3  test    ebx, eax
0x18000c8b5  jnz     short loc_18000C8C3
0x18000c8b7  cmp     edi, 80070490h
0x18000c8bd  jnz     loc_18000C9D9
0x18000c8c3  mov     rbx, r12
0x18000c8c6  mov     ecx, 8; int
0x18000c8cb  cmp     cx, word ptr [rsp+158h+pvarg]
0x18000c8d3  cmovz   rbx, qword ptr [rsp+158h+pvarg+8]
0x18000c8dc  cmp     r15d, ecx
0x18000c8df  jz      loc_18000CBCD
0x18000c8e5  cmp     [rsp+158h+var_118], 0
0x18000c8ea  jz      loc_18000C9AB
0x18000c8f0  mov     rax, [r13+0]
0x18000c8f4  lea     rdx, [rsp+158h+pvarSrc]
0x18000c8fc  mov     rcx, r13
0x18000c8ff  mov     rax, [rax+68h]
0x18000c903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c908  mov     edi, eax
0x18000c90a  test    esi, esi
0x18000c90c  jnz     short loc_18000C92F
0x18000c90e  cmp     eax, 80004001h
0x18000c913  jz      loc_18000CE2F
0x18000c919  cmp     eax, 86000011h
0x18000c91e  jz      loc_18000CE2F
0x18000c924  cmp     eax, 86000017h
0x18000c929  jz      loc_18000CE2F
0x18000c92f  test    eax, eax
0x18000c931  js      loc_18000C9D9
0x18000c937  xor     r8d, r8d; wFlags
0x18000c93a  lea     rcx, [rsp+158h+pvarSrc]; pvargDest
0x18000c942  cmp     r14w, word ptr [rsp+158h+pvarSrc]
0x18000c94b  jnz     short loc_18000C981
0x18000c94d  mov     r9d, 8; vt
0x18000c953  lea     rdx, [rsp+158h+pvarSrc]; pvarSrc
0x18000c95b  call    cs:__imp_VariantChangeType
0x18000c962  nop     dword ptr [rax+rax+00h]
0x18000c967  mov     edi, eax
0x18000c969  test    eax, eax
0x18000c96b  js      short loc_18000C9D9
0x18000c96d  mov     rax, qword ptr [rsp+158h+pvarSrc+8]
0x18000c975  mov     [rsp+158h+var_128], r12d
0x18000c97a  mov     [rsp+158h+lpcbData], rax
0x18000c97f  jmp     short loc_18000C9B5
0x18000c981  lea     r9, [rsp+158h+hMem]
0x18000c989  mov     edx, r15d
0x18000c98c  call    ?ConformVariantToData@@YAJPEAUtagVARIANT@@W4ConfigDataType@@KPEAPEAG@Z; ConformVariantToData(tagVARIANT *,ConfigDataType,ulong,ushort * *)
0x18000c991  mov     edi, eax
0x18000c993  test    eax, eax
0x18000c995  js      short loc_18000C9D9
0x18000c997  mov     rax, [rsp+158h+hMem]
0x18000c99f  mov     [rsp+158h+var_128], r12d
0x18000c9a4  mov     [rsp+158h+lpcbData], rax
0x18000c9a9  jmp     short loc_18000C9B5
0x18000c9ab  mov     [rsp+158h+var_128], r12d; int
0x18000c9b0  mov     [rsp+158h+lpcbData], r12; unsigned __int16 *
0x18000c9b5  mov     [rsp+158h+phkResult], rbx; __int64
0x18000c9ba  mov     r9d, r15d; int
0x18000c9bd  mov     r8, qword ptr [rsp+158h+var_108]; int
0x18000c9c2  mov     rdx, qword ptr [rsp+158h+var_B0]; int
0x18000c9ca  call    ?AppendResultItem@CSyncMLCmdGet@@AEAAJAEAV?$vector@PEAVCSyncMLItem@@V?$allocator@PEAVCSyncMLItem@@@std@@@std@@PEAUIConfigManager2URI@@W4ConfigDataType@@PEBG3H@Z; CSyncMLCmdGet::AppendResultItem(std::vector<CSyncMLItem *> &,IConfigManager2URI *,ConfigDataType,ushort const *,ushort const *,int)
0x18000c9cf  mov     edi, eax
0x18000c9d1  test    eax, eax
0x18000c9d3  jns     loc_18000CE2F
0x18000c9d9  lea     rcx, [rsp+158h+pvarSrc]; pvarg
0x18000c9e1  call    cs:__imp_VariantClear
0x18000c9e8  nop     dword ptr [rax+rax+00h]
0x18000c9ed  lea     rcx, [rsp+158h+pvarg]; pvarg
0x18000c9f5  call    cs:__imp_VariantClear
0x18000c9fc  nop     dword ptr [rax+rax+00h]
0x18000ca01  mov     rcx, [rsp+158h+hMem]; hMem
0x18000ca09  call    cs:__imp_LocalFree
0x18000ca10  nop     dword ptr [rax+rax+00h]
0x18000ca15  mov     rbx, [rsp+158h+Src+8]
0x18000ca1a  mov     rsi, [rsp+158h+Src]
0x18000ca1f  cmp     rsi, rbx
0x18000ca22  jz      short loc_18000CA35
0x18000ca24  mov     rcx, [rsi]; struct IConfigNode *
0x18000ca27  call    ?DeallocConfigNode@CSyncMLCmdGet@@CAXPEAUIConfigNode@@@Z; CSyncMLCmdGet::DeallocConfigNode(IConfigNode *)
0x18000ca2c  add     rsi, 8
0x18000ca30  cmp     rsi, rbx
0x18000ca33  jnz     short loc_18000CA24
0x18000ca35  mov     rcx, [rsp+158h+var_F8]
0x18000ca3a  test    rcx, rcx
0x18000ca3d  jz      short loc_18000CA50
0x18000ca3f  mov     rax, [rcx]
0x18000ca42  mov     rax, [rax+10h]
0x18000ca46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca4b  mov     [rsp+158h+var_F8], r12
0x18000ca50  test    r13, r13
0x18000ca53  jz      short loc_18000CA65
0x18000ca55  mov     rax, [r13+0]
0x18000ca59  mov     rcx, r13
0x18000ca5c  mov     rax, [rax+10h]
0x18000ca60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca65  mov     rcx, [rsp+158h+var_F0]
0x18000ca6a  test    rcx, rcx
0x18000ca6d  jz      short loc_18000CA80
0x18000ca6f  mov     rax, [rcx]
0x18000ca72  mov     rax, [rax+10h]
0x18000ca76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca7b  mov     [rsp+158h+var_F0], r12
0x18000ca80  mov     rcx, qword ptr [rsp+158h+var_108]
0x18000ca85  test    rcx, rcx
0x18000ca88  jz      short loc_18000CA9B
0x18000ca8a  mov     rax, [rcx]
0x18000ca8d  mov     rax, [rax+10h]
0x18000ca91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca96  mov     qword ptr [rsp+158h+var_108], r12
0x18000ca9b  mov     eax, cs:dword_18003E048
0x18000caa1  cmp     eax, 5
0x18000caa4  jbe     loc_18000CB7D
0x18000caaa  mov     [rsp+158h+var_118], edi
0x18000caae  lea     rax, [rsp+158h+var_118]
0x18000cab3  mov     [rsp+158h+var_48], rax
0x18000cabb  mov     [rsp+158h+var_40], 4
0x18000cac7  mov     dword ptr [rsp+158h+EventDescriptor.Id], 0B000000h
0x18000cad2  movzx   eax, cs:word_180036969
0x18000cad9  mov     dword ptr [rsp+158h+EventDescriptor.Level], eax
0x18000cae0  mov     [rsp+158h+EventDescriptor.Keyword], r12
0x18000cae8  mov     rax, cs:off_18003E050
0x18000caef  mov     qword ptr [rsp+158h+var_68], rax
0x18000caf7  movzx   eax, word ptr [rax]
0x18000cafa  mov     dword ptr [rsp+158h+var_68+8], eax
0x18000cb01  mov     dword ptr [rsp+158h+var_68+0Ch], 2
0x18000cb0c  lea     rax, byte_180036973
0x18000cb13  mov     qword ptr [rsp+158h+var_68+10h], rax
0x18000cb1b  mov     [rsp+158h+var_50], 1Dh
0x18000cb26  mov     [rsp+158h+var_4C], r14d
0x18000cb2e  lea     rax, _TraceLoggingMetadataEnd
0x18000cb35  lea     rcx, _TraceLoggingMetadata
0x18000cb3c  sub     eax, ecx
0x18000cb3e  mov     [rsp+158h+var_110], eax
0x18000cb42  mov     eax, [rsp+158h+var_110]
0x18000cb46  lea     rax, [rsp+158h+var_68]
0x18000cb4e  mov     [rsp+158h+lpcbData], rax; UserData
0x18000cb53  mov     dword ptr [rsp+158h+phkResult], 3; UserDataCount
0x18000cb5b  xor     r9d, r9d; RelatedActivityId
0x18000cb5e  xor     r8d, r8d; ActivityId
0x18000cb61  lea     rdx, [rsp+158h+EventDescriptor]; EventDescriptor
0x18000cb69  mov     rcx, cs:RegHandle; RegHandle
0x18000cb70  call    cs:__imp_EventWriteTransfer
0x18000cb77  nop     dword ptr [rax+rax+00h]
0x18000cb7c  nop
0x18000cb7d  mov     rcx, [rsp+158h+Src]
0x18000cb82  test    rcx, rcx
0x18000cb85  jz      loc_18000CF5D
0x18000cb8b  mov     rax, [rsp+158h+var_D8]
0x18000cb93  sub     rax, rcx
0x18000cb96  sar     rax, 3
0x18000cb9a  lea     rdx, ds:0[rax*8]; struct std::nothrow_t *
0x18000cba2  cmp     rdx, 1000h
0x18000cba9  jb      loc_18000CF52
0x18000cbaf  mov     rax, [rcx-8]
0x18000cbb3  sub     rcx, rax
0x18000cbb6  sub     rcx, 8
0x18000cbba  cmp     rcx, 1Fh
0x18000cbbe  ja      loc_18000CF4B
0x18000cbc4  add     rdx, 27h ; '''
0x18000cbc8  jmp     loc_18000CF55
0x18000cbcd  lea     rax, word_180032B28
0x18000cbd4  test    rbx, rbx
  ... truncated ...
```
