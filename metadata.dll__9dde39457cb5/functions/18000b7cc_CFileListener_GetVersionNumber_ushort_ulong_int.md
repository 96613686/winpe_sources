# CFileListener::GetVersionNumber(ushort *,ulong *,int *)

- ea: `0x18000b7cc`
- end: `0x18000ba90`
- name: `?GetVersionNumber@CFileListener@@AEAAJPEAGPEAKPEAH@Z`
- size: `708`
- prototype: `__int64 __fastcall(CFileListener *this, unsigned __int16 *, unsigned int *, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000aff8`
- `0x18000b4d0`

## callees

- `0x18000b7cc`
- `0x18001ea74`
- `0x180031010`

## import_xrefs

- `KERNEL32!Sleep` at `0x18000b906`
- `KERNEL32!Sleep` at `0x18000b906`
- `KERNEL32!lstrlenW` at `0x18000b899`
- `KERNEL32!lstrlenW` at `0x18000b8c8`
- `KERNEL32!lstrlenW` at `0x18000b899`
- `KERNEL32!lstrlenW` at `0x18000b8c8`
- `IisRTL!PuDbgPrintW` at `0x18000b86f`
- `IisRTL!PuDbgPrintW` at `0x18000b99f`
- `IisRTL!PuDbgPrintW` at `0x18000ba36`
- `IisRTL!PuDbgPrintW` at `0x18000b86f`
- `IisRTL!PuDbgPrintW` at `0x18000b99f`
- `IisRTL!PuDbgPrintW` at `0x18000ba36`
- `IISCFG!DllGetSimpleObjectByIDEx` at `0x18000b82b`
- `IISCFG!DllGetSimpleObjectByIDEx` at `0x18000b82b`

## string_xrefs

- `0x18000b85d`: `[GetVersionNumber] DllGetSimpleObjectByIDEx failed with hr = 0x%x.\n`
- `0x18000ba1f`: `[GetVersionNumber] Unable to read %s. GetGlobalValue failed with hr = 0x%x.\n`

## pseudocode

```c
__int64 __fastcall CFileListener::GetVersionNumber(
        CFileListener *this,
        unsigned __int16 *a2,
        unsigned int *a3,
        int *a4)
{
  int SimpleObjectByIDEx; // eax
  int v8; // ebx
  unsigned int v9; // esi
  int v10; // eax
  int Value; // eax
  int v13; // [rsp+28h] [rbp-51h]
  __int64 v14; // [rsp+30h] [rbp-49h]
  __int64 v15; // [rsp+38h] [rbp-41h]
  unsigned int v16; // [rsp+50h] [rbp-29h] BYREF
  struct ISimpleTableRead2 *v17; // [rsp+58h] [rbp-21h] BYREF
  __int64 v18; // [rsp+60h] [rbp-19h] BYREF
  void *v19; // [rsp+68h] [rbp-11h] BYREF
  unsigned __int16 *v20; // [rsp+70h] [rbp-9h] BYREF
  int v21; // [rsp+78h] [rbp-1h]
  int v22; // [rsp+7Ch] [rbp+3h]
  int v23; // [rsp+80h] [rbp+7h]
  int v24; // [rsp+84h] [rbp+Bh]
  const WCHAR *v25; // [rsp+88h] [rbp+Fh]
  int v26; // [rsp+90h] [rbp+17h]
  int v27; // [rsp+94h] [rbp+1Bh]
  int v28; // [rsp+98h] [rbp+1Fh]
  int v29; // [rsp+9Ch] [rbp+23h]
  int v30; // [rsp+E0h] [rbp+67h] BYREF
  int v31; // [rsp+E4h] [rbp+6Bh]

  v31 = HIDWORD(this);
  v18 = 0;
  v17 = 0;
  v30 = 2;
  v16 = 0;
  v19 = 0;
  SimpleObjectByIDEx = DllGetSimpleObjectByIDEx(1, &IID_ISimpleTableDispenser2, &v18, L"IIS");
  v8 = SimpleObjectByIDEx;
  if ( SimpleObjectByIDEx < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      v13 = SimpleObjectByIDEx;
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\listener.cpp",
        4461,
        "CFileListener::GetVersionNumber",
        L"[GetVersionNumber] DllGetSimpleObjectByIDEx failed with hr = 0x%x.\n",
        v13);
    }
    goto LABEL_22;
  }
  v20 = a2;
  v23 = 130;
  v9 = 0;
  v21 = 2;
  v22 = -268435455;
  v10 = lstrlenW(a2);
  v26 = 2;
  v27 = 4;
  v28 = 130;
  v24 = 2 * v10 + 2;
  v25 = L".";
  v8 = -2145318902;
  v29 = 2 * lstrlenW(L".") + 2;
  while ( (v8 == -2147024864 || (unsigned int)(v8 + 2147024894) <= 1 || v8 == -2145318902) && v9 < 0xA )
  {
    if ( v9 )
      Sleep(0x7D0u);
    v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *, unsigned __int16 **, int *, int, _DWORD, struct ISimpleTableRead2 **))(*(_QWORD *)v18 + 24LL))(
           v18,
           L"METABASE",
           L"MBProperty",
           &v20,
           &v30,
           3,
           0,
           &v17);
    ++v9;
  }
  if ( v8 >= 0 )
  {
    Value = GetValue(v17, L".", 0x34u, L"HistoryMajorVersionNumber", &v16, &v19);
    v8 = Value;
    if ( Value >= 0 )
    {
      v8 = 0;
      *a3 = *(_DWORD *)v19;
      goto LABEL_22;
    }
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v14) = Value;
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\listener.cpp",
        4543,
        "CFileListener::GetVersionNumber",
        L"[GetVersionNumber] Unable to read %s. GetGlobalValue failed with hr = 0x%x.\n",
        L"HistoryMajorVersionNumber",
        v14);
    }
    goto LABEL_16;
  }
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    LODWORD(v15) = v8;
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\listener.cpp",
      4516,
      "CFileListener::GetVersionNumber",
      L"[GetVersionNumber] GetTable on %s from %s failed with hr = 0x%x.\n",
      L"MBProperty",
      a2,
      v15);
  }
  if ( v8 != -2147024894 )
  {
LABEL_16:
    if ( a4 )
      *a4 = 1;
  }
LABEL_22:
  if ( v17 )
  {
    (*(void (__fastcall **)(struct ISimpleTableRead2 *))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000b7cc  mov     [rsp-8+arg_0], rcx
0x18000b7d1  push    rbp
0x18000b7d2  push    rbx
0x18000b7d3  push    rsi
0x18000b7d4  push    rdi
0x18000b7d5  push    r14
0x18000b7d7  push    r15
0x18000b7d9  lea     rbp, [rsp-2Fh]
0x18000b7de  sub     rsp, 0A8h
0x18000b7e5  mov     rdi, r9
0x18000b7e8  mov     [rbp+57h+var_70], 0
0x18000b7f0  mov     r15, r8
0x18000b7f3  mov     [rbp+57h+var_78], 0
0x18000b7fb  mov     r14, rdx
0x18000b7fe  mov     dword ptr [rbp+57h+arg_0], 2
0x18000b805  lea     r9, aIis; "IIS"
0x18000b80c  mov     [rbp+57h+var_80], 0
0x18000b813  lea     r8, [rbp+57h+var_70]
0x18000b817  mov     [rbp+57h+var_68], 0
0x18000b81f  lea     rdx, IID_ISimpleTableDispenser2
0x18000b826  mov     ecx, 1
0x18000b82b  call    cs:__imp_DllGetSimpleObjectByIDEx
0x18000b831  mov     ebx, eax
0x18000b833  test    eax, eax
0x18000b835  jns     short loc_18000B87A
0x18000b837  test    byte ptr cs:g_dwDebugFlags, 3
0x18000b83e  jz      loc_18000BA4C
0x18000b844  mov     rcx, cs:g_pDebug
0x18000b84b  lea     r9, aCfilelistenerG_7; "CFileListener::GetVersionNumber"
0x18000b852  mov     dword ptr [rsp+0D0h+var_A8], eax
0x18000b856  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000b85d  lea     rax, aGetversionnumb_0; "[GetVersionNumber] DllGetSimpleObjectBy"...
0x18000b864  mov     r8d, 116Dh
0x18000b86a  mov     [rsp+0D0h+var_B0], rax
0x18000b86f  call    cs:__imp_PuDbgPrintW
0x18000b875  jmp     loc_18000BA4C
0x18000b87a  mov     ebx, 82h
0x18000b87f  mov     [rbp+57h+var_60], r14
0x18000b883  mov     rcx, r14; lpString
0x18000b886  mov     [rbp+57h+var_50], ebx
0x18000b889  xor     esi, esi
0x18000b88b  mov     [rbp+57h+var_58], 2
0x18000b892  mov     [rbp+57h+var_54], 0F0000001h
0x18000b899  call    cs:__imp_lstrlenW
0x18000b89f  mov     [rbp+57h+var_40], 2
0x18000b8a6  mov     [rbp+57h+var_3C], 4
0x18000b8ad  mov     [rbp+57h+var_38], ebx
0x18000b8b0  lea     eax, ds:2[rax*2]
0x18000b8b7  mov     [rbp+57h+var_4C], eax
0x18000b8ba  lea     rax, String; "."
0x18000b8c1  mov     rcx, rax; lpString
0x18000b8c4  mov     [rbp+57h+var_48], rax
0x18000b8c8  call    cs:__imp_lstrlenW
0x18000b8ce  mov     ebx, 8021080Ah
0x18000b8d3  lea     eax, ds:2[rax*2]
0x18000b8da  mov     [rbp+57h+var_34], eax
0x18000b8dd  cmp     ebx, 80070020h
0x18000b8e3  jz      short loc_18000B8F8
0x18000b8e5  lea     eax, [rbx+7FF8FFFEh]
0x18000b8eb  cmp     eax, 1
0x18000b8ee  jbe     short loc_18000B8F8
0x18000b8f0  cmp     ebx, 8021080Ah
0x18000b8f6  jnz     short loc_18000B956
0x18000b8f8  cmp     esi, 0Ah
0x18000b8fb  jnb     short loc_18000B956
0x18000b8fd  test    esi, esi
0x18000b8ff  jz      short loc_18000B90C
0x18000b901  mov     ecx, 7D0h; dwMilliseconds
0x18000b906  call    cs:__imp_Sleep
0x18000b90c  mov     rcx, [rbp+57h+var_70]
0x18000b910  lea     rdx, [rbp+57h+var_78]
0x18000b914  mov     [rsp+0D0h+var_98], rdx
0x18000b919  lea     r9, [rbp+57h+var_60]
0x18000b91d  mov     dword ptr [rsp+0D0h+var_A0], 0
0x18000b925  lea     rdx, [rbp+57h+arg_0]
0x18000b929  mov     dword ptr [rsp+0D0h+var_A8], 3
0x18000b931  lea     r8, aMbproperty_0; "MBProperty"
0x18000b938  mov     rax, [rcx]
0x18000b93b  mov     [rsp+0D0h+var_B0], rdx
0x18000b940  lea     rdx, aMetabase; "METABASE"
0x18000b947  mov     rax, [rax+18h]
0x18000b94b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b950  mov     ebx, eax
0x18000b952  inc     esi
0x18000b954  jmp     short loc_18000B8DD
0x18000b956  test    ebx, ebx
0x18000b958  jns     short loc_18000B9C5
0x18000b95a  test    byte ptr cs:g_dwDebugFlags, 3
0x18000b961  jz      short loc_18000B9A5
0x18000b963  mov     rcx, cs:g_pDebug
0x18000b96a  lea     rax, aMbproperty_0; "MBProperty"
0x18000b971  mov     dword ptr [rsp+0D0h+var_98], ebx
0x18000b975  lea     r9, aCfilelistenerG_7; "CFileListener::GetVersionNumber"
0x18000b97c  mov     [rsp+0D0h+var_A0], r14
0x18000b981  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000b988  mov     [rsp+0D0h+var_A8], rax
0x18000b98d  mov     r8d, 11A4h
0x18000b993  lea     rax, aGetversionnumb; "[GetVersionNumber] GetTable on %s from "...
0x18000b99a  mov     [rsp+0D0h+var_B0], rax
0x18000b99f  call    cs:__imp_PuDbgPrintW
0x18000b9a5  cmp     ebx, 80070002h
0x18000b9ab  jz      loc_18000BA4C
0x18000b9b1  test    rdi, rdi
0x18000b9b4  jz      loc_18000BA4C
0x18000b9ba  mov     dword ptr [rdi], 1
0x18000b9c0  jmp     loc_18000BA4C
0x18000b9c5  mov     rcx, [rbp+57h+var_78]; struct ISimpleTableRead2 *
0x18000b9c9  lea     rax, [rbp+57h+var_68]
0x18000b9cd  mov     [rsp+0D0h+var_A8], rax; void **
0x18000b9d2  lea     rsi, aHistorymajorve; "HistoryMajorVersionNumber"
0x18000b9d9  lea     rax, [rbp+57h+var_80]
0x18000b9dd  mov     r9, rsi; unsigned __int16 *
0x18000b9e0  mov     r8d, 34h ; '4'; unsigned int
0x18000b9e6  mov     [rsp+0D0h+var_B0], rax; unsigned int *
0x18000b9eb  lea     rdx, String; "."
0x18000b9f2  call    ?GetValue@@YAJPEAUISimpleTableRead2@@PEBGK1PEAKPEAPEAX@Z; GetValue(ISimpleTableRead2 *,ushort const *,ulong,ushort const *,ulong *,void * *)
0x18000b9f7  mov     ebx, eax
0x18000b9f9  test    eax, eax
0x18000b9fb  jns     short loc_18000BA41
0x18000b9fd  test    byte ptr cs:g_dwDebugFlags, 3
0x18000ba04  jz      short loc_18000B9B1
0x18000ba06  mov     rcx, cs:g_pDebug
0x18000ba0d  lea     r9, aCfilelistenerG_7; "CFileListener::GetVersionNumber"
0x18000ba14  mov     dword ptr [rsp+0D0h+var_A0], eax
0x18000ba18  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000ba1f  lea     rax, aGetversionnumb_1; "[GetVersionNumber] Unable to read %s. G"...
0x18000ba26  mov     [rsp+0D0h+var_A8], rsi
0x18000ba2b  mov     r8d, 11BFh
0x18000ba31  mov     [rsp+0D0h+var_B0], rax
0x18000ba36  call    cs:__imp_PuDbgPrintW
0x18000ba3c  jmp     loc_18000B9B1
0x18000ba41  mov     rax, [rbp+57h+var_68]
0x18000ba45  xor     ebx, ebx
0x18000ba47  mov     ecx, [rax]
0x18000ba49  mov     [r15], ecx
0x18000ba4c  mov     rcx, [rbp+57h+var_78]
0x18000ba50  test    rcx, rcx
0x18000ba53  jz      short loc_18000BA69
0x18000ba55  mov     rax, [rcx]
0x18000ba58  mov     rax, [rax+10h]
0x18000ba5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba61  mov     [rbp+57h+var_78], 0
0x18000ba69  mov     rcx, [rbp+57h+var_70]
0x18000ba6d  test    rcx, rcx
0x18000ba70  jz      short loc_18000BA7E
0x18000ba72  mov     rax, [rcx]
0x18000ba75  mov     rax, [rax+10h]
0x18000ba79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba7e  mov     eax, ebx
0x18000ba80  add     rsp, 0A8h
0x18000ba87  pop     r15
0x18000ba89  pop     r14
0x18000ba8b  pop     rdi
0x18000ba8c  pop     rsi
0x18000ba8d  pop     rbx
0x18000ba8e  pop     rbp
0x18000ba8f  retn
```
