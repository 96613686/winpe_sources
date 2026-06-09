# AddAllIncludedInf(HWND__ *,void *,ushort const *,PLATFORM,int,_FILE_QUEUE_CONTEXT *,void * *)

- ea: `0x18001785c`
- end: `0x180017c4a`
- name: `?AddAllIncludedInf@@YAHPEAUHWND__@@PEAXPEBGW4PLATFORM@@HPEAU_FILE_QUEUE_CONTEXT@@PEAPEAX@Z`
- size: `1006`
- prototype: `int __high(HWND, void *, const unsigned __int16 *, enum PLATFORM, int, struct _FILE_QUEUE_CONTEXT *, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x1800217e0`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180007944`
- `0x18000d290`
- `0x18000d7f0`
- `0x18001785c`
- `0x18001c978`
- `0x18001eed8`
- `0x180020b60`
- `0x180023318`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800179ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017acf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017b34`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800179ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017acf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017b34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017add`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017b44`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017b59`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017c11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017add`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017b44`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017b59`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017c11`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017bb8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017bb8`
- `SETUPAPI!SetupGetStringFieldW` at `0x180017ba2`
- `SETUPAPI!SetupGetStringFieldW` at `0x180017bdf`
- `SETUPAPI!SetupGetStringFieldW` at `0x180017ba2`
- `SETUPAPI!SetupGetStringFieldW` at `0x180017bdf`
- `SETUPAPI!SetupGetFieldCount` at `0x180017b74`
- `SETUPAPI!SetupGetFieldCount` at `0x180017b74`
- `SETUPAPI!SetupFindFirstLineW` at `0x1800178ca`
- `SETUPAPI!SetupFindFirstLineW` at `0x18001794d`
- `SETUPAPI!SetupFindFirstLineW` at `0x1800178ca`
- `SETUPAPI!SetupFindFirstLineW` at `0x18001794d`
- `SETUPAPI!SetupOpenAppendInfFileW` at `0x180017af4`
- `SETUPAPI!SetupOpenAppendInfFileW` at `0x180017bf2`
- `SETUPAPI!SetupOpenAppendInfFileW` at `0x180017c04`
- `SETUPAPI!SetupOpenAppendInfFileW` at `0x180017af4`
- `SETUPAPI!SetupOpenAppendInfFileW` at `0x180017bf2`
- `SETUPAPI!SetupOpenAppendInfFileW` at `0x180017c04`

## pseudocode

```c
_BOOL8 __fastcall AddAllIncludedInf(
        __int64 a1,
        void *a2,
        const WCHAR *a3,
        unsigned int a4,
        int a5,
        __int64 a6,
        __int64 *a7)
{
  BOOL LatestCoreDrivers; // ebx
  int v12; // eax
  HLOCAL v13; // rdi
  const wchar_t *v14; // r11
  wchar_t *v15; // rax
  DWORD v16; // ecx
  int v17; // edi
  __int64 v18; // rax
  DWORD FieldCount; // r14d
  DWORD i; // edi
  WCHAR *v21; // rsi
  DWORD ReturnBufferSize; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  HLOCAL v25; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL v26; // [rsp+68h] [rbp-98h]
  unsigned __int64 v27; // [rsp+70h] [rbp-90h] BYREF
  struct _INFCONTEXT Context; // [rsp+78h] [rbp-88h] BYREF
  struct _INFCONTEXT v29; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v30[40]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR FileName[264]; // [rsp+100h] [rbp+0h] BYREF

  ReturnBufferSize = 0;
  LatestCoreDrivers = 1;
  memset(&Context, 0, sizeof(Context));
  if ( !SetupFindFirstLineW(a2, a3, L"Include", &Context) )
    return LatestCoreDrivers;
  if ( a4 != MyPlatform )
  {
    memset_0(v30, 0, sizeof(v30));
    LatestCoreDrivers = 0;
    v25 = 0;
    LODWORD(hMem) = 0;
    v26 = 0;
    memset(&v29, 0, sizeof(v29));
    memset_0(FileName, 0, 0x208u);
    if ( (int)StringCchCopyW(v30, 0x27u, L"{D20EA372-DD35-4950-9ED8-A6335AFE79F0}") >= 0 )
    {
      if ( !SetupFindFirstLineW(a2, a3, L"Needs", &v29) )
        goto LABEL_10;
      if ( (int)InfGetMultiSz(&v29) >= 0 )
      {
        LatestCoreDrivers = FindLatestCoreDrivers(v30, a4, 0, 0, (const WCHAR *)v26, &v25, (unsigned int *)&hMem);
        if ( LatestCoreDrivers )
        {
          if ( (_DWORD)hMem == 1 )
          {
            if ( (int)StringCchCopyW(FileName, 0x104u, (const unsigned __int16 *)v25 + 48) >= 0 )
              goto LABEL_28;
            goto LABEL_11;
          }
LABEL_10:
          SetLastError(0xDu);
LABEL_11:
          LatestCoreDrivers = 0;
        }
      }
    }
    if ( !a7 || !a5 || (unsigned __int64)(a1 - 1) > 0xFFFFFFFFFFFFFFFDuLL || !v26 )
      goto LABEL_27;
    hMem = 0;
    v27 = 0;
    v12 = PromptAndRetrieveVerifyVerNtprintInfPath(a1, a4, 1, 0, 0, 0, 0, v26, &hMem);
    v13 = hMem;
    if ( v12 < 0
      || (v12 = StringCchLengthW((const unsigned __int16 *)hMem, 0x104u, &v27), v12 < 0)
      || (v12 = StringCchCopyW(FileName, 0x104u, (const unsigned __int16 *)v13), v12 < 0)
      || (v12 = StringCchCopyW((unsigned __int16 *)(a6 + 572), 0x104u, (const unsigned __int16 *)v13), v12 < 0) )
    {
      v16 = 1223;
      if ( (unsigned __int16)v12 == 1223 )
      {
LABEL_24:
        SetLastError(v16);
LABEL_25:
        if ( v13 )
          LocalFree(v13);
LABEL_27:
        if ( !LatestCoreDrivers )
        {
          v17 = 1;
          if ( a7 )
            SetLastError(0x661u);
          else
            LatestCoreDrivers = 1;
          goto LABEL_34;
        }
LABEL_28:
        v17 = 0;
        LatestCoreDrivers = SetupOpenAppendInfFileW(FileName, a2, 0);
        if ( LatestCoreDrivers && a7 )
        {
          v18 = OpenPrinterInfFile(FileName);
          *a7 = v18;
          LatestCoreDrivers = v18 != -1;
        }
LABEL_34:
        if ( v25 )
        {
          LocalFree(v25);
          v25 = 0;
        }
        if ( v26 )
          LocalFree(v26);
        if ( !v17 || !LatestCoreDrivers )
          return LatestCoreDrivers;
        goto LABEL_40;
      }
    }
    else
    {
      v15 = wcsrchr(v14, 0x5Cu);
      if ( v15 )
      {
        *v15 = 0;
        *(_DWORD *)(a6 + 564) = 1;
        LatestCoreDrivers = 1;
        goto LABEL_25;
      }
    }
    v16 = 1633;
    goto LABEL_24;
  }
LABEL_40:
  FieldCount = SetupGetFieldCount(&Context);
  for ( i = 1; i <= FieldCount; ++i )
  {
    if ( SetupGetStringFieldW(&Context, i, 0, 0, &ReturnBufferSize) )
    {
      v21 = (WCHAR *)LocalAlloc(0x40u, 2 * ReturnBufferSize);
      if ( !v21 )
        return 0;
      if ( SetupGetStringFieldW(&Context, i, v21, ReturnBufferSize, &ReturnBufferSize) )
      {
        if ( SetupOpenAppendInfFileW(v21, a2, 0) )
          SetupOpenAppendInfFileW(0, a2, 0);
        else
          LatestCoreDrivers = 0;
      }
      LocalFree(v21);
    }
    if ( !LatestCoreDrivers )
      return LatestCoreDrivers;
  }
  return LatestCoreDrivers;
}

```

## disassembly

```asm
0x18001785c  push    rbp
0x18001785e  push    rbx
0x18001785f  push    rsi
0x180017860  push    rdi
0x180017861  push    r12
0x180017863  push    r13
0x180017865  push    r14
0x180017867  push    r15
0x180017869  lea     rbp, [rsp-228h]
0x180017871  sub     rsp, 328h
0x180017878  mov     rax, cs:__security_cookie
0x18001787f  xor     rax, rsp
0x180017882  mov     [rbp+260h+var_50], rax
0x180017889  mov     r12, [rbp+260h+arg_28]
0x180017890  xor     eax, eax
0x180017892  mov     rsi, [rbp+260h+arg_30]
0x180017899  mov     r14, r8
0x18001789c  mov     r15, rdx
0x18001789f  mov     qword ptr [rbp+260h+Context.Section], rax
0x1800178a3  mov     edi, r9d
0x1800178a6  mov     [rsp+360h+ReturnBufferSize], eax
0x1800178aa  mov     r13, rcx
0x1800178ad  lea     r9, [rsp+360h+Context]; Context
0x1800178b2  xorps   xmm0, xmm0
0x1800178b5  lea     r8, aInclude; "Include"
0x1800178bc  mov     rdx, r14; Section
0x1800178bf  lea     ebx, [rax+1]
0x1800178c2  mov     rcx, r15; InfHandle
0x1800178c5  movups  xmmword ptr [rsp+360h+Context.Inf], xmm0
0x1800178ca  call    cs:__imp_SetupFindFirstLineW
0x1800178d0  test    eax, eax
0x1800178d2  jz      loc_180017C25
0x1800178d8  cmp     edi, cs:MyPlatform
0x1800178de  jz      loc_180017B6F
0x1800178e4  xor     edx, edx; Val
0x1800178e6  lea     r8d, [rbx+4Fh]; Size
0x1800178ea  lea     rcx, [rbp+260h+var_2B0]; void *
0x1800178ee  call    memset_0
0x1800178f3  xor     ebx, ebx
0x1800178f5  lea     rcx, [rbp+260h+FileName]; void *
0x1800178f9  xorps   xmm0, xmm0
0x1800178fc  mov     [rsp+360h+var_300], rbx
0x180017901  xor     eax, eax
0x180017903  mov     dword ptr [rsp+360h+hMem], ebx
0x180017907  xor     edx, edx; Val
0x180017909  mov     qword ptr [rbp+260h+var_2D0.Section], rax
0x18001790d  mov     r8d, 208h; Size
0x180017913  mov     [rsp+360h+var_2F8], rbx
0x180017918  movups  xmmword ptr [rbp+260h+var_2D0.Inf], xmm0
0x18001791c  call    memset_0
0x180017921  lea     r8, aD20ea372Dd3549_0; "{D20EA372-DD35-4950-9ED8-A6335AFE79F0}"
0x180017928  lea     edx, [rbx+27h]; unsigned __int64
0x18001792b  lea     rcx, [rbp+260h+var_2B0]; unsigned __int16 *
0x18001792f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017934  test    eax, eax
0x180017936  js      loc_1800179D9
0x18001793c  lea     r9, [rbp+260h+var_2D0]; Context
0x180017940  mov     rdx, r14; Section
0x180017943  lea     r8, aNeeds; "Needs"
0x18001794a  mov     rcx, r15; InfHandle
0x18001794d  call    cs:__imp_SetupFindFirstLineW
0x180017953  xor     r14d, r14d
0x180017956  test    eax, eax
0x180017958  jz      short loc_1800179C9
0x18001795a  lea     r8, [rsp+360h+var_2F8]
0x18001795f  lea     rcx, [rbp+260h+var_2D0]; Context
0x180017963  call    InfGetMultiSz
0x180017968  test    eax, eax
0x18001796a  js      short loc_1800179DC
0x18001796c  lea     rax, [rsp+360h+hMem]
0x180017971  mov     r8d, r14d
0x180017974  mov     [rsp+360h+var_330], rax; __int64
0x180017979  lea     rcx, [rbp+260h+var_2B0]; unsigned __int16 *
0x18001797d  lea     rax, [rsp+360h+var_300]
0x180017982  xor     r9d, r9d
0x180017985  mov     [rsp+360h+var_338], rax; __int64
0x18001798a  mov     edx, edi
0x18001798c  mov     rax, [rsp+360h+var_2F8]
0x180017991  mov     [rsp+360h+RequiredSize], rax; __int64
0x180017996  call    FindLatestCoreDrivers
0x18001799b  mov     ebx, eax
0x18001799d  test    eax, eax
0x18001799f  jz      short loc_1800179DC
0x1800179a1  cmp     dword ptr [rsp+360h+hMem], 1
0x1800179a6  jnz     short loc_1800179C9
0x1800179a8  mov     r8, [rsp+360h+var_300]
0x1800179ad  lea     rcx, [rbp+260h+FileName]; unsigned __int16 *
0x1800179b1  add     r8, 60h ; '`'; unsigned __int16 *
0x1800179b5  mov     edx, 104h; unsigned __int64
0x1800179ba  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800179bf  test    eax, eax
0x1800179c1  jns     loc_180017AE7
0x1800179c7  jmp     short loc_1800179D4
0x1800179c9  mov     ecx, 0Dh; dwErrCode
0x1800179ce  call    cs:__imp_SetLastError
0x1800179d4  mov     ebx, r14d
0x1800179d7  jmp     short loc_1800179DC
0x1800179d9  xor     r14d, r14d
0x1800179dc  test    rsi, rsi
0x1800179df  jz      loc_180017AE3
0x1800179e5  cmp     [rbp+260h+arg_20], r14d
0x1800179ec  jz      loc_180017AE3
0x1800179f2  lea     rax, [r13-1]
0x1800179f6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800179fa  ja      loc_180017AE3
0x180017a00  mov     rcx, [rsp+360h+var_2F8]
0x180017a05  test    rcx, rcx
0x180017a08  jz      loc_180017AE3
0x180017a0e  lea     rdx, [rsp+360h+hMem]
0x180017a13  mov     [rsp+360h+hMem], r14
0x180017a18  mov     [rsp+360h+var_320], rdx
0x180017a1d  xor     r9d, r9d
0x180017a20  mov     [rsp+360h+var_328], rcx
0x180017a25  mov     edx, edi
0x180017a27  mov     [rsp+360h+var_330], r14
0x180017a2c  mov     rcx, r13
0x180017a2f  mov     [rsp+360h+var_338], r14
0x180017a34  lea     r8d, [r9+1]
0x180017a38  mov     [rsp+360h+RequiredSize], r14
0x180017a3d  mov     [rsp+360h+var_2F0], r14
0x180017a42  call    PromptAndRetrieveVerifyVerNtprintInfPath
0x180017a47  mov     rdi, [rsp+360h+hMem]
0x180017a4c  test    eax, eax
0x180017a4e  js      short loc_180017ABE
0x180017a50  mov     r13d, 104h
0x180017a56  lea     r8, [rsp+360h+var_2F0]; unsigned __int64 *
0x180017a5b  mov     edx, r13d; unsigned __int64
0x180017a5e  mov     rcx, rdi; unsigned __int16 *
0x180017a61  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180017a66  test    eax, eax
0x180017a68  js      short loc_180017ABE
0x180017a6a  mov     r8, rdi; unsigned __int16 *
0x180017a6d  lea     rcx, [rbp+260h+FileName]; unsigned __int16 *
0x180017a71  mov     edx, r13d; unsigned __int64
0x180017a74  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017a79  test    eax, eax
0x180017a7b  js      short loc_180017ABE
0x180017a7d  lea     r11, [r12+23Ch]
0x180017a85  mov     r8, rdi; unsigned __int16 *
0x180017a88  mov     rcx, r11; unsigned __int16 *
0x180017a8b  mov     edx, r13d; unsigned __int64
0x180017a8e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017a93  test    eax, eax
0x180017a95  js      short loc_180017ABE
0x180017a97  mov     edx, 5Ch ; '\'; Ch
0x180017a9c  mov     rcx, r11; Str
0x180017a9f  call    ?wcsrchr@@YAPEAGPEAGG@Z; wcsrchr(ushort *,ushort)
0x180017aa4  test    rax, rax
0x180017aa7  jz      short loc_180017ACA
0x180017aa9  mov     [rax], r14w
0x180017aad  mov     eax, 1
0x180017ab2  mov     [r12+234h], eax
0x180017aba  mov     ebx, eax
0x180017abc  jmp     short loc_180017AD5
0x180017abe  movzx   eax, ax
0x180017ac1  mov     ecx, 4C7h
0x180017ac6  cmp     eax, ecx
0x180017ac8  jz      short loc_180017ACF
0x180017aca  mov     ecx, 661h; dwErrCode
0x180017acf  call    cs:__imp_SetLastError
0x180017ad5  test    rdi, rdi
0x180017ad8  jz      short loc_180017AE3
0x180017ada  mov     rcx, rdi; hMem
0x180017add  call    cs:__imp_LocalFree
0x180017ae3  test    ebx, ebx
0x180017ae5  jz      short loc_180017B1F
0x180017ae7  xor     r8d, r8d; ErrorLine
0x180017aea  lea     rcx, [rbp+260h+FileName]; FileName
0x180017aee  mov     rdx, r15; InfHandle
0x180017af1  mov     edi, r14d
0x180017af4  call    cs:__imp_SetupOpenAppendInfFileW
0x180017afa  mov     ebx, eax
0x180017afc  test    eax, eax
0x180017afe  jz      short loc_180017B3A
0x180017b00  test    rsi, rsi
0x180017b03  jz      short loc_180017B3A
0x180017b05  xor     edx, edx
0x180017b07  lea     rcx, [rbp+260h+FileName]; unsigned __int16 *
0x180017b0b  call    OpenPrinterInfFile
0x180017b10  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180017b14  mov     [rsi], rax
0x180017b17  mov     ebx, r14d
0x180017b1a  setnz   bl
0x180017b1d  jmp     short loc_180017B3A
0x180017b1f  mov     eax, 1
0x180017b24  mov     edi, eax
0x180017b26  test    rsi, rsi
0x180017b29  jnz     short loc_180017B2F
0x180017b2b  mov     ebx, eax
0x180017b2d  jmp     short loc_180017B3A
0x180017b2f  mov     ecx, 661h; dwErrCode
0x180017b34  call    cs:__imp_SetLastError
0x180017b3a  mov     rcx, [rsp+360h+var_300]; hMem
0x180017b3f  test    rcx, rcx
0x180017b42  jz      short loc_180017B4F
0x180017b44  call    cs:__imp_LocalFree
0x180017b4a  mov     [rsp+360h+var_300], r14
0x180017b4f  mov     rcx, [rsp+360h+var_2F8]; hMem
0x180017b54  test    rcx, rcx
0x180017b57  jz      short loc_180017B5F
0x180017b59  call    cs:__imp_LocalFree
0x180017b5f  test    edi, edi
0x180017b61  jz      loc_180017C25
0x180017b67  test    ebx, ebx
0x180017b69  jz      loc_180017C25
0x180017b6f  lea     rcx, [rsp+360h+Context]; Context
0x180017b74  call    cs:__imp_SetupGetFieldCount
0x180017b7a  mov     r14d, eax
0x180017b7d  mov     edi, 1
0x180017b82  cmp     edi, r14d
0x180017b85  ja      loc_180017C25
0x180017b8b  lea     rax, [rsp+360h+ReturnBufferSize]
0x180017b90  xor     r9d, r9d; ReturnBufferSize
0x180017b93  xor     r8d, r8d; ReturnBuffer
0x180017b96  mov     [rsp+360h+RequiredSize], rax; RequiredSize
0x180017b9b  mov     edx, edi; FieldIndex
0x180017b9d  lea     rcx, [rsp+360h+Context]; Context
0x180017ba2  call    cs:__imp_SetupGetStringFieldW
0x180017ba8  test    eax, eax
0x180017baa  jz      short loc_180017C17
0x180017bac  mov     eax, [rsp+360h+ReturnBufferSize]
0x180017bb0  mov     ecx, 40h ; '@'; uFlags
0x180017bb5  lea     edx, [rax+rax]; uBytes
0x180017bb8  call    cs:__imp_LocalAlloc
0x180017bbe  mov     rsi, rax
0x180017bc1  test    rax, rax
0x180017bc4  jz      short loc_180017C23
0x180017bc6  mov     r9d, [rsp+360h+ReturnBufferSize]; ReturnBufferSize
0x180017bcb  lea     rax, [rsp+360h+ReturnBufferSize]
0x180017bd0  mov     r8, rsi; ReturnBuffer
0x180017bd3  mov     [rsp+360h+RequiredSize], rax; RequiredSize
0x180017bd8  mov     edx, edi; FieldIndex
0x180017bda  lea     rcx, [rsp+360h+Context]; Context
0x180017bdf  call    cs:__imp_SetupGetStringFieldW
0x180017be5  test    eax, eax
0x180017be7  jz      short loc_180017C0E
0x180017be9  xor     r8d, r8d; ErrorLine
0x180017bec  mov     rdx, r15; InfHandle
0x180017bef  mov     rcx, rsi; FileName
0x180017bf2  call    cs:__imp_SetupOpenAppendInfFileW
0x180017bf8  test    eax, eax
0x180017bfa  jz      short loc_180017C0C
0x180017bfc  xor     r8d, r8d; ErrorLine
0x180017bff  mov     rdx, r15; InfHandle
0x180017c02  xor     ecx, ecx; FileName
0x180017c04  call    cs:__imp_SetupOpenAppendInfFileW
0x180017c0a  jmp     short loc_180017C0E
0x180017c0c  xor     ebx, ebx
0x180017c0e  mov     rcx, rsi; hMem
0x180017c11  call    cs:__imp_LocalFree
0x180017c17  inc     edi
0x180017c19  test    ebx, ebx
0x180017c1b  jnz     loc_180017B82
0x180017c21  jmp     short loc_180017C25
0x180017c23  xor     ebx, ebx
0x180017c25  mov     eax, ebx
0x180017c27  mov     rcx, [rbp+260h+var_50]
0x180017c2e  xor     rcx, rsp; StackCookie
0x180017c31  call    __security_check_cookie
0x180017c36  add     rsp, 328h
0x180017c3d  pop     r15
0x180017c3f  pop     r14
0x180017c41  pop     r13
0x180017c43  pop     r12
0x180017c45  pop     rdi
0x180017c46  pop     rsi
0x180017c47  pop     rbx
0x180017c48  pop     rbp
0x180017c49  retn
```
