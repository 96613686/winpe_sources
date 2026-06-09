# CFileListener::GetCryptoFromFile(ushort *,IIS_CRYPTO_STORAGE * *,_IIS_CRYPTO_BLOB * *,int *)

- ea: `0x18000ab6c`
- end: `0x18000aec9`
- name: `?GetCryptoFromFile@CFileListener@@AEAAJPEAGPEAPEAVIIS_CRYPTO_STORAGE@@PEAPEFAU_IIS_CRYPTO_BLOB@@PEAH@Z`
- size: `861`
- prototype: `int(CFileListener *__hidden this, unsigned __int16 *, struct IIS_CRYPTO_STORAGE **, struct _IIS_CRYPTO_BLOB **, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18000b3a0`

## callees

- `0x180008a14`
- `0x180009bd0`
- `0x18000ab6c`
- `0x18001ea74`
- `0x18001f8e4`
- `0x18003098e`
- `0x180031010`

## import_xrefs

- `KERNEL32!Sleep` at `0x18000ace4`
- `KERNEL32!Sleep` at `0x18000ace4`
- `KERNEL32!lstrlenW` at `0x18000ac75`
- `KERNEL32!lstrlenW` at `0x18000aca4`
- `KERNEL32!lstrlenW` at `0x18000ac75`
- `KERNEL32!lstrlenW` at `0x18000aca4`
- `IisRTL!PuDbgPrintW` at `0x18000ac4d`
- `IisRTL!PuDbgPrintW` at `0x18000ad7d`
- `IisRTL!PuDbgPrintW` at `0x18000ae0b`
- `IisRTL!PuDbgPrintW` at `0x18000ac4d`
- `IisRTL!PuDbgPrintW` at `0x18000ad7d`
- `IisRTL!PuDbgPrintW` at `0x18000ae0b`
- `IISCFG!DllGetSimpleObjectByIDEx` at `0x18000ac09`
- `IISCFG!DllGetSimpleObjectByIDEx` at `0x18000ac09`

## string_xrefs

- `0x18000ac3b`: `[GetVersionNumber] DllGetSimpleObjectByIDEx failed with hr = 0x%x.\n`
- `0x18000adf4`: `[GetCryptoFromFile] Unable to read %s. GetGlobalValue failed with hr = 0x%x.\n`

## pseudocode

```c
__int64 __fastcall CFileListener::GetCryptoFromFile(
        CFileListener *this,
        unsigned __int16 *a2,
        struct IIS_CRYPTO_STORAGE **a3,
        struct _IIS_CRYPTO_BLOB **a4,
        int *a5)
{
  unsigned int v5; // r15d
  IIS_CRYPTO_STORAGE *v9; // rdi
  int *v10; // rsi
  int SimpleObjectByIDEx; // eax
  int inited; // ebx
  int v13; // eax
  int Value; // eax
  struct _IIS_CRYPTO_BLOB *v15; // rax
  struct _IIS_CRYPTO_BLOB *v16; // rbx
  struct IIS_CRYPTO_STORAGE *v17; // rax
  __int64 v19; // [rsp+30h] [rbp-51h]
  __int64 v20; // [rsp+38h] [rbp-49h]
  struct IIS_CRYPTO_STORAGE *v21; // [rsp+50h] [rbp-31h] BYREF
  struct ISimpleTableRead2 *v22; // [rsp+58h] [rbp-29h] BYREF
  __int64 v23; // [rsp+60h] [rbp-21h] BYREF
  void *Src; // [rsp+68h] [rbp-19h] BYREF
  unsigned __int16 *v25; // [rsp+70h] [rbp-11h] BYREF
  __int128 v26; // [rsp+78h] [rbp-9h]
  __int128 v27; // [rsp+88h] [rbp+7h]
  __int64 v28; // [rsp+98h] [rbp+17h]
  unsigned int Size; // [rsp+E0h] [rbp+5Fh] BYREF
  int Size_4; // [rsp+E4h] [rbp+63h]
  int v31; // [rsp+E8h] [rbp+67h] BYREF

  Size_4 = HIDWORD(this);
  v5 = 0;
  v31 = 2;
  v23 = 0;
  v22 = 0;
  v25 = 0;
  v28 = 0;
  Size = 0;
  Src = 0;
  v9 = 0;
  v21 = 0;
  v26 = 0;
  v27 = 0;
  if ( !a2 || !a3 || !a4 || (v10 = a5) == 0 )
  {
    inited = -2147024809;
    goto LABEL_30;
  }
  SimpleObjectByIDEx = DllGetSimpleObjectByIDEx(1, &IID_ISimpleTableDispenser2, &v23, L"IIS");
  inited = SimpleObjectByIDEx;
  if ( SimpleObjectByIDEx < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\listener.cpp",
        4624,
        "CFileListener::GetCryptoFromFile",
        L"[GetVersionNumber] DllGetSimpleObjectByIDEx failed with hr = 0x%x.\n",
        SimpleObjectByIDEx);
    goto LABEL_30;
  }
  v25 = a2;
  LODWORD(v26) = 2;
  *(_QWORD *)((char *)&v26 + 4) = 0x82F0000001LL;
  v13 = lstrlenW(a2);
  *((_QWORD *)&v27 + 1) = 0x400000002LL;
  LODWORD(v28) = 130;
  HIDWORD(v26) = 2 * v13 + 2;
  *(_QWORD *)&v27 = L".";
  inited = -2145318902;
  HIDWORD(v28) = 2 * lstrlenW(L".") + 2;
  while ( (inited == -2147024864 || (unsigned int)(inited + 2147024894) <= 1 || inited == -2145318902) && v5 < 0xA )
  {
    if ( v5 )
      Sleep(0x7D0u);
    inited = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *, unsigned __int16 **, int *, int, _DWORD, struct ISimpleTableRead2 **))(*(_QWORD *)v23 + 24LL))(
               v23,
               L"METABASE",
               L"MBProperty",
               &v25,
               &v31,
               3,
               0,
               &v22);
    ++v5;
  }
  if ( inited >= 0 )
  {
    Value = GetValue(v22, L".", 0x34u, L"SessionKey", &Size, &Src);
    inited = Value;
    if ( Value >= 0 )
    {
      inited = InitStorageHelper((unsigned __int8 *)Src, Size, &v21);
      if ( inited >= 0 )
      {
        v15 = (struct _IIS_CRYPTO_BLOB *)operator new[](Size);
        v16 = v15;
        if ( v15 )
        {
          memcpy_0(v15, Src, Size);
          v17 = v21;
          *a4 = v16;
          inited = 0;
          *a3 = v17;
          goto LABEL_30;
        }
        inited = -2147024882;
      }
      v9 = v21;
      goto LABEL_30;
    }
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v19) = Value;
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\listener.cpp",
        4704,
        "CFileListener::GetCryptoFromFile",
        L"[GetCryptoFromFile] Unable to read %s. GetGlobalValue failed with hr = 0x%x.\n",
        L"SessionKey",
        v19);
    }
LABEL_20:
    *v10 = 1;
    goto LABEL_30;
  }
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    LODWORD(v20) = inited;
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\listener.cpp",
      4680,
      "CFileListener::GetCryptoFromFile",
      L"[GetVersionNumber] GetTable on %s from %s failed with hr = 0x%x.\n",
      L"MBProperty",
      a2,
      v20);
  }
  if ( inited != -2147024894 )
    goto LABEL_20;
LABEL_30:
  if ( v22 )
  {
    (*(void (__fastcall **)(struct ISimpleTableRead2 *))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v23 = 0;
  }
  if ( v9 )
    IIS_CRYPTO_STORAGE::`scalar deleting destructor'(v9, (unsigned int)a2);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18000ab6c  mov     [rsp-8+arg_10], rbx
0x18000ab71  mov     [rsp-8+Size], rcx
0x18000ab76  push    rbp
0x18000ab77  push    rsi
0x18000ab78  push    rdi
0x18000ab79  push    r12
0x18000ab7b  push    r13
0x18000ab7d  push    r14
0x18000ab7f  push    r15
0x18000ab81  lea     rbp, [rsp-1Fh]
0x18000ab86  sub     rsp, 0A0h
0x18000ab8d  xor     r15d, r15d
0x18000ab90  mov     [rbp+4Fh+arg_8], 2
0x18000ab97  xor     eax, eax
0x18000ab99  mov     [rbp+4Fh+var_70], r15
0x18000ab9d  mov     [rbp+4Fh+var_78], r15
0x18000aba1  xorps   xmm0, xmm0
0x18000aba4  mov     [rbp+4Fh+var_60], r15
0x18000aba8  mov     r12, r9
0x18000abab  mov     [rbp+4Fh+var_38], rax
0x18000abaf  mov     r13, r8
0x18000abb2  mov     dword ptr [rbp+4Fh+Size], r15d
0x18000abb6  mov     r14, rdx
0x18000abb9  mov     [rbp+4Fh+Src], r15
0x18000abbd  mov     edi, r15d
0x18000abc0  mov     [rbp+4Fh+var_80], r15
0x18000abc4  movups  [rbp+4Fh+var_58], xmm0
0x18000abc8  movups  [rbp+4Fh+var_48], xmm0
0x18000abcc  test    rdx, rdx
0x18000abcf  jz      loc_18000AE68
0x18000abd5  test    r8, r8
0x18000abd8  jz      loc_18000AE68
0x18000abde  test    r9, r9
0x18000abe1  jz      loc_18000AE68
0x18000abe7  mov     rsi, [rbp+4Fh+arg_20]
0x18000abeb  test    rsi, rsi
0x18000abee  jz      loc_18000AE68
0x18000abf4  lea     r9, aIis; "IIS"
0x18000abfb  lea     r8, [rbp+4Fh+var_70]
0x18000abff  lea     rdx, IID_ISimpleTableDispenser2
0x18000ac06  lea     ecx, [rax+1]
0x18000ac09  call    cs:__imp_DllGetSimpleObjectByIDEx
0x18000ac0f  mov     ebx, eax
0x18000ac11  test    eax, eax
0x18000ac13  jns     short loc_18000AC58
0x18000ac15  test    byte ptr cs:g_dwDebugFlags, 3
0x18000ac1c  jz      loc_18000AE6D
0x18000ac22  mov     rcx, cs:g_pDebug
0x18000ac29  lea     r9, aCfilelistenerG; "CFileListener::GetCryptoFromFile"
0x18000ac30  mov     dword ptr [rsp+0D0h+var_A8], eax
0x18000ac34  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000ac3b  lea     rax, aGetversionnumb_0; "[GetVersionNumber] DllGetSimpleObjectBy"...
0x18000ac42  mov     r8d, 1210h
0x18000ac48  mov     [rsp+0D0h+var_B0], rax
0x18000ac4d  call    cs:__imp_PuDbgPrintW
0x18000ac53  jmp     loc_18000AE6D
0x18000ac58  mov     ebx, 82h
0x18000ac5d  mov     [rbp+4Fh+var_60], r14
0x18000ac61  mov     rcx, r14; lpString
0x18000ac64  mov     dword ptr [rbp+4Fh+var_58+8], ebx
0x18000ac67  mov     dword ptr [rbp+4Fh+var_58], 2
0x18000ac6e  mov     dword ptr [rbp+4Fh+var_58+4], 0F0000001h
0x18000ac75  call    cs:__imp_lstrlenW
0x18000ac7b  mov     dword ptr [rbp+4Fh+var_48+8], 2
0x18000ac82  mov     dword ptr [rbp+4Fh+var_48+0Ch], 4
0x18000ac89  mov     dword ptr [rbp+4Fh+var_38], ebx
0x18000ac8c  lea     eax, ds:2[rax*2]
0x18000ac93  mov     dword ptr [rbp+4Fh+var_58+0Ch], eax
0x18000ac96  lea     rax, String; "."
0x18000ac9d  mov     rcx, rax; lpString
0x18000aca0  mov     qword ptr [rbp+4Fh+var_48], rax
0x18000aca4  call    cs:__imp_lstrlenW
0x18000acaa  mov     ebx, 8021080Ah
0x18000acaf  lea     eax, ds:2[rax*2]
0x18000acb6  mov     dword ptr [rbp+4Fh+var_38+4], eax
0x18000acb9  cmp     ebx, 80070020h
0x18000acbf  jz      short loc_18000ACD4
0x18000acc1  lea     eax, [rbx+7FF8FFFEh]
0x18000acc7  cmp     eax, 1
0x18000acca  jbe     short loc_18000ACD4
0x18000accc  cmp     ebx, 8021080Ah
0x18000acd2  jnz     short loc_18000AD31
0x18000acd4  cmp     r15d, 0Ah
0x18000acd8  jnb     short loc_18000AD31
0x18000acda  test    r15d, r15d
0x18000acdd  jz      short loc_18000ACEA
0x18000acdf  mov     ecx, 7D0h; dwMilliseconds
0x18000ace4  call    cs:__imp_Sleep
0x18000acea  mov     rcx, [rbp+4Fh+var_70]
0x18000acee  lea     rdx, [rbp+4Fh+var_78]
0x18000acf2  mov     [rsp+0D0h+var_98], rdx
0x18000acf7  lea     r9, [rbp+4Fh+var_60]
0x18000acfb  mov     dword ptr [rsp+0D0h+var_A0], edi
0x18000acff  lea     rdx, [rbp+4Fh+arg_8]
0x18000ad03  mov     dword ptr [rsp+0D0h+var_A8], 3
0x18000ad0b  lea     r8, aMbproperty_0; "MBProperty"
0x18000ad12  mov     rax, [rcx]
0x18000ad15  mov     [rsp+0D0h+var_B0], rdx
0x18000ad1a  lea     rdx, aMetabase; "METABASE"
0x18000ad21  mov     rax, [rax+18h]
0x18000ad25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad2a  mov     ebx, eax
0x18000ad2c  inc     r15d
0x18000ad2f  jmp     short loc_18000ACB9
0x18000ad31  xor     r15d, r15d
0x18000ad34  test    ebx, ebx
0x18000ad36  jns     short loc_18000AD9A
0x18000ad38  test    byte ptr cs:g_dwDebugFlags, 3
0x18000ad3f  jz      short loc_18000AD83
0x18000ad41  mov     rcx, cs:g_pDebug
0x18000ad48  lea     rax, aMbproperty_0; "MBProperty"
0x18000ad4f  mov     dword ptr [rsp+0D0h+var_98], ebx
0x18000ad53  lea     r9, aCfilelistenerG; "CFileListener::GetCryptoFromFile"
0x18000ad5a  mov     [rsp+0D0h+var_A0], r14
0x18000ad5f  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000ad66  mov     [rsp+0D0h+var_A8], rax
0x18000ad6b  mov     r8d, 1248h
0x18000ad71  lea     rax, aGetversionnumb; "[GetVersionNumber] GetTable on %s from "...
0x18000ad78  mov     [rsp+0D0h+var_B0], rax
0x18000ad7d  call    cs:__imp_PuDbgPrintW
0x18000ad83  cmp     ebx, 80070002h
0x18000ad89  jz      loc_18000AE6D
0x18000ad8f  mov     dword ptr [rsi], 1
0x18000ad95  jmp     loc_18000AE6D
0x18000ad9a  mov     rcx, [rbp+4Fh+var_78]; struct ISimpleTableRead2 *
0x18000ad9e  lea     rax, [rbp+4Fh+Src]
0x18000ada2  mov     [rsp+0D0h+var_A8], rax; void **
0x18000ada7  lea     r14, aSessionkey; "SessionKey"
0x18000adae  lea     rax, [rbp+4Fh+Size]
0x18000adb2  mov     r9, r14; unsigned __int16 *
0x18000adb5  mov     r8d, 34h ; '4'; unsigned int
0x18000adbb  mov     [rsp+0D0h+var_B0], rax; unsigned int *
0x18000adc0  lea     rdx, String; "."
0x18000adc7  call    ?GetValue@@YAJPEAUISimpleTableRead2@@PEBGK1PEAKPEAPEAX@Z; GetValue(ISimpleTableRead2 *,ushort const *,ulong,ushort const *,ulong *,void * *)
0x18000adcc  mov     ebx, eax
0x18000adce  test    eax, eax
0x18000add0  jns     short loc_18000AE16
0x18000add2  test    byte ptr cs:g_dwDebugFlags, 3
0x18000add9  jz      short loc_18000AD8F
0x18000addb  mov     rcx, cs:g_pDebug
0x18000ade2  lea     r9, aCfilelistenerG; "CFileListener::GetCryptoFromFile"
0x18000ade9  mov     dword ptr [rsp+0D0h+var_A0], eax
0x18000aded  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000adf4  lea     rax, aGetcryptofromf; "[GetCryptoFromFile] Unable to read %s. "...
0x18000adfb  mov     [rsp+0D0h+var_A8], r14
0x18000ae00  mov     r8d, 1260h
0x18000ae06  mov     [rsp+0D0h+var_B0], rax
0x18000ae0b  call    cs:__imp_PuDbgPrintW
0x18000ae11  jmp     loc_18000AD8F
0x18000ae16  mov     edx, dword ptr [rbp+4Fh+Size]; unsigned int
0x18000ae19  lea     r8, [rbp+4Fh+var_80]; struct IIS_CRYPTO_STORAGE **
0x18000ae1d  mov     rcx, [rbp+4Fh+Src]; unsigned __int8 *
0x18000ae21  call    ?InitStorageHelper@@YAJPEAEKPEAPEAVIIS_CRYPTO_STORAGE@@@Z; InitStorageHelper(uchar *,ulong,IIS_CRYPTO_STORAGE * *)
0x18000ae26  mov     ebx, eax
0x18000ae28  test    eax, eax
0x18000ae2a  js      short loc_18000AE41
0x18000ae2c  mov     ecx, dword ptr [rbp+4Fh+Size]; unsigned __int64
0x18000ae2f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000ae34  mov     rbx, rax
0x18000ae37  test    rax, rax
0x18000ae3a  jnz     short loc_18000AE47
0x18000ae3c  mov     ebx, 8007000Eh
0x18000ae41  mov     rdi, [rbp+4Fh+var_80]
0x18000ae45  jmp     short loc_18000AE6D
0x18000ae47  mov     r8d, dword ptr [rbp+4Fh+Size]; Size
0x18000ae4b  mov     rcx, rbx; void *
0x18000ae4e  mov     rdx, [rbp+4Fh+Src]; Src
0x18000ae52  call    memcpy_0
0x18000ae57  mov     rax, [rbp+4Fh+var_80]
0x18000ae5b  mov     [r12], rbx
0x18000ae5f  mov     ebx, r15d
0x18000ae62  mov     [r13+0], rax
0x18000ae66  jmp     short loc_18000AE6D
0x18000ae68  mov     ebx, 80070057h
0x18000ae6d  mov     rcx, [rbp+4Fh+var_78]
0x18000ae71  test    rcx, rcx
0x18000ae74  jz      short loc_18000AE86
0x18000ae76  mov     rax, [rcx]
0x18000ae79  mov     rax, [rax+10h]
0x18000ae7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae82  mov     [rbp+4Fh+var_78], r15
0x18000ae86  mov     rcx, [rbp+4Fh+var_70]
0x18000ae8a  test    rcx, rcx
0x18000ae8d  jz      short loc_18000AE9F
0x18000ae8f  mov     rax, [rcx]
0x18000ae92  mov     rax, [rax+10h]
0x18000ae96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae9b  mov     [rbp+4Fh+var_70], r15
0x18000ae9f  test    rdi, rdi
0x18000aea2  jz      short loc_18000AEAC
0x18000aea4  mov     rcx, rdi; this
0x18000aea7  call    ??_GIIS_CRYPTO_STORAGE@@QEAAPEAXI@Z; IIS_CRYPTO_STORAGE::`scalar deleting destructor'(uint)
0x18000aeac  mov     eax, ebx
0x18000aeae  mov     rbx, [rsp+0D0h+arg_10]
0x18000aeb6  add     rsp, 0A0h
0x18000aebd  pop     r15
0x18000aebf  pop     r14
0x18000aec1  pop     r13
0x18000aec3  pop     r12
0x18000aec5  pop     rdi
0x18000aec6  pop     rsi
0x18000aec7  pop     rbp
0x18000aec8  retn
```
