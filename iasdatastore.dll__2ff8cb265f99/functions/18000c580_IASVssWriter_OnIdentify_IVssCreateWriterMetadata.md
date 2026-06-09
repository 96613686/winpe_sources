# IASVssWriter::OnIdentify(IVssCreateWriterMetadata *)

- ea: `0x18000c580`
- end: `0x18000c902`
- name: `?OnIdentify@IASVssWriter@@UEAA_NPEAVIVssCreateWriterMetadata@@@Z`
- size: `898`
- prototype: `bool __fastcall(IASVssWriter *__hidden this, struct IVssCreateWriterMetadata *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001938`
- `0x18000c580`
- `0x18000ca54`
- `0x18000cb14`
- `0x18000d990`
- `0x18000dce6`
- `0x18000dd10`
- `0x180010010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000c791`
- `msvcrt!wcscat_s` at `0x18000c791`
- `KERNEL32!GetSystemDirectoryW` at `0x18000c6d0`
- `KERNEL32!GetSystemDirectoryW` at `0x18000c6d0`
- `KERNEL32!GetLastError` at `0x18000c6de`
- `KERNEL32!GetLastError` at `0x18000c6de`

## string_xrefs

- `0x18000c649`: `IVssCreateWriterMetadata::AddComponent`
- `0x18000c65f`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s`
- `0x18000c747`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s`
- `0x18000c831`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s`
- `0x18000c8cd`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s`
- `0x18000c731`: `GetSystemDirectory`
- `0x18000c81b`: `IVssCreateWriterMetadata::AddFilesToFileGroup`
- `0x18000c8b7`: `IVssCreateWriterMetadata::SetRestoreMethod`
- `0x18000c79a`: `ias*.xml`

## pseudocode

```c
bool __fastcall IASVssWriter::OnIdentify(IASVssWriter *this, struct IVssCreateWriterMetadata *a2)
{
  signed int v3; // eax
  unsigned int v4; // eax
  const char *v5; // rbx
  signed int LastError; // eax
  signed int v8; // ebx
  unsigned int v9; // eax
  signed int v10; // eax
  unsigned int v11; // eax
  signed int v12; // eax
  unsigned int v13; // eax
  int v14; // [rsp+28h] [rbp-D8h]
  char v15; // [rsp+38h] [rbp-C8h]
  char v16; // [rsp+40h] [rbp-C0h]
  char v17; // [rsp+48h] [rbp-B8h]
  char v18; // [rsp+50h] [rbp-B0h]
  char v19[256]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[264]; // [rsp+170h] [rbp+70h] BYREF

  if ( !a2 )
    return 0;
  v18 = 0;
  v17 = 0;
  v16 = 0;
  v15 = 0;
  v3 = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, __int64, _QWORD, const wchar_t *, const wchar_t *, _QWORD, _DWORD, char, char, char, char, _DWORD))(*(_QWORD *)a2 + 16LL))(
         a2,
         2,
         0,
         L"NPS Database",
         L"NPS Database",
         0,
         0,
         v15,
         v16,
         v17,
         v18,
         0);
  if ( v3 < 0 )
  {
    v4 = IASFormatSysErr(v3, v19);
    if ( v4 >= 0x100uLL )
      _report_rangecheckfailure();
    v19[v4] = 0;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
    {
      return 0;
    }
    v5 = "IVssCreateWriterMetadata::AddComponent";
    WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s");
    goto LABEL_8;
  }
  memset_0(Buffer, 0, 0x208u);
  if ( GetSystemDirectoryW(Buffer, 0x104u) )
  {
    wcscat_s(Buffer, 0x104u, L"\\ias");
    LOBYTE(v14) = 0;
    v10 = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, _QWORD, const wchar_t *, WCHAR *, const wchar_t *, int, _QWORD, int))(*(_QWORD *)a2 + 40LL))(
            a2,
            0,
            L"NPS Database",
            Buffer,
            L"ias*.xml",
            v14,
            0,
            3855);
    if ( v10 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, __int64, _QWORD))(*(_QWORD *)a2 + 48LL))(
              a2,
              5,
              0);
      if ( v12 >= 0 )
        return 1;
      v13 = IASFormatSysErr(v12, v19);
      if ( v13 >= 0x100uLL )
        _report_rangecheckfailure();
      v19[v13] = 0;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      {
        return 0;
      }
      v5 = "IVssCreateWriterMetadata::SetRestoreMethod";
      WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s");
    }
    else
    {
      v11 = IASFormatSysErr(v10, v19);
      if ( v11 >= 0x100uLL )
        _report_rangecheckfailure();
      v19[v11] = 0;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      {
        return 0;
      }
      v5 = "IVssCreateWriterMetadata::AddFilesToFileGroup";
      WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s");
    }
LABEL_8:
    WPP_SF_sss(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v5, (__int64)v19);
    return 0;
  }
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError > 0 )
    v8 = (unsigned __int16)LastError | 0x80070000;
  v9 = IASFormatSysErr(v8, v19);
  if ( v9 >= 0x100uLL )
    _report_rangecheckfailure();
  v19[v9] = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s");
    WPP_SF_sss(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"GetSystemDirectory", (__int64)v19);
  }
  return v8 >= 0;
}

```

## disassembly

```asm
0x18000c580  mov     [rsp-8+arg_0], rbx
0x18000c585  mov     [rsp-8+arg_10], rsi
0x18000c58a  push    rbp
0x18000c58b  push    rdi
0x18000c58c  push    r14
0x18000c58e  lea     rbp, [rsp-290h]
0x18000c596  sub     rsp, 390h
0x18000c59d  mov     rax, cs:__security_cookie
0x18000c5a4  xor     rax, rsp
0x18000c5a7  mov     [rbp+2A0h+var_20], rax
0x18000c5ae  xor     esi, esi
0x18000c5b0  mov     rbx, rdx
0x18000c5b3  test    rdx, rdx
0x18000c5b6  jz      loc_18000C68D
0x18000c5bc  mov     rax, [rdx]
0x18000c5bf  lea     r14, aNpsDatabase; "NPS Database"
0x18000c5c6  mov     [rsp+3A0h+var_348], esi
0x18000c5ca  lea     edi, [rsi+2]
0x18000c5cd  mov     [rsp+3A0h+var_350], sil
0x18000c5d2  mov     r9, r14
0x18000c5d5  mov     [rsp+3A0h+var_358], sil
0x18000c5da  xor     r8d, r8d
0x18000c5dd  mov     rax, [rax+10h]
0x18000c5e1  mov     edx, edi
0x18000c5e3  mov     [rsp+3A0h+var_360], sil
0x18000c5e8  mov     rcx, rbx
0x18000c5eb  mov     [rsp+3A0h+var_368], sil
0x18000c5f0  mov     dword ptr [rsp+3A0h+var_370], esi
0x18000c5f4  mov     [rsp+3A0h+var_378], rsi
0x18000c5f9  mov     [rsp+3A0h+var_380], r14
0x18000c5fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c603  test    eax, eax
0x18000c605  jns     loc_18000C6B6
0x18000c60b  lea     rdx, [rsp+3A0h+var_330]; Buffer
0x18000c610  mov     ecx, eax; dwMessageId
0x18000c612  call    IASFormatSysErr
0x18000c617  mov     eax, eax
0x18000c619  cmp     rax, 100h
0x18000c61f  jnb     loc_18000C8EA
0x18000c625  mov     [rsp+rax+3A0h+var_330], sil
0x18000c62a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c631  lea     rax, WPP_GLOBAL_Control
0x18000c638  cmp     rcx, rax
0x18000c63b  jz      short loc_18000C68D
0x18000c63d  cmp     [rcx+19h], dil
0x18000c641  jb      short loc_18000C68D
0x18000c643  test    byte ptr [rcx+1Ch], 10h
0x18000c647  jz      short loc_18000C68D
0x18000c649  lea     rbx, aIvsscreatewrit_1; "IVssCreateWriterMetadata::AddComponent"
0x18000c650  mov     r8, rbx
0x18000c653  lea     r9, [rsp+3A0h+var_330]
0x18000c658  lea     rdx, aNpsds; "NPSDS"
0x18000c65f  lea     rcx, aCpuPidTidNowSL; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x18000c666  call    WppDbgPrint
0x18000c66b  lea     edx, [rsi+0Ah]
0x18000c66e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c675  lea     rax, [rsp+3A0h+var_330]
0x18000c67a  mov     [rsp+3A0h+var_378], rax; __int64
0x18000c67f  mov     [rsp+3A0h+var_380], rbx; __int64
0x18000c684  mov     rcx, [rcx+10h]; LoggerHandle
0x18000c688  call    WPP_SF_sss
0x18000c68d  xor     al, al
0x18000c68f  mov     rcx, [rbp+2A0h+var_20]
0x18000c696  xor     rcx, rsp; StackCookie
0x18000c699  call    __security_check_cookie
0x18000c69e  lea     r11, [rsp+3A0h+var_10]
0x18000c6a6  mov     rbx, [r11+20h]
0x18000c6aa  mov     rsi, [r11+30h]
0x18000c6ae  mov     rsp, r11
0x18000c6b1  pop     r14
0x18000c6b3  pop     rdi
0x18000c6b4  pop     rbp
0x18000c6b5  retn
0x18000c6b6  xor     edx, edx; Val
0x18000c6b8  lea     rcx, [rbp+2A0h+Buffer]; void *
0x18000c6bc  mov     r8d, 208h; Size
0x18000c6c2  call    memset_0
0x18000c6c7  mov     edx, 104h; uSize
0x18000c6cc  lea     rcx, [rbp+2A0h+Buffer]; lpBuffer
0x18000c6d0  call    cs:__imp_GetSystemDirectoryW
0x18000c6d6  test    eax, eax
0x18000c6d8  jnz     loc_18000C781
0x18000c6de  call    cs:__imp_GetLastError
0x18000c6e4  mov     ebx, eax
0x18000c6e6  test    eax, eax
0x18000c6e8  jle     short loc_18000C6F3
0x18000c6ea  movzx   ebx, ax
0x18000c6ed  or      ebx, 80070000h
0x18000c6f3  lea     rdx, [rsp+3A0h+var_330]; Buffer
0x18000c6f8  mov     ecx, ebx; dwMessageId
0x18000c6fa  call    IASFormatSysErr
0x18000c6ff  mov     eax, eax
0x18000c701  cmp     rax, 100h
0x18000c707  jnb     loc_18000C8F0
0x18000c70d  mov     [rsp+rax+3A0h+var_330], sil
0x18000c712  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c719  lea     rax, WPP_GLOBAL_Control
0x18000c720  cmp     rcx, rax
0x18000c723  jz      short loc_18000C777
0x18000c725  cmp     [rcx+19h], dil
0x18000c729  jb      short loc_18000C777
0x18000c72b  test    byte ptr [rcx+1Ch], 10h
0x18000c72f  jz      short loc_18000C777
0x18000c731  lea     rdi, aGetsystemdirec; "GetSystemDirectory"
0x18000c738  mov     r8, rdi
0x18000c73b  lea     r9, [rsp+3A0h+var_330]
0x18000c740  lea     rdx, aNpsds; "NPSDS"
0x18000c747  lea     rcx, aCpuPidTidNowSL; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x18000c74e  call    WppDbgPrint
0x18000c753  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c75a  lea     rax, [rsp+3A0h+var_330]
0x18000c75f  mov     [rsp+3A0h+var_378], rax; __int64
0x18000c764  mov     edx, 0Bh
0x18000c769  mov     [rsp+3A0h+var_380], rdi; __int64
0x18000c76e  mov     rcx, [rcx+10h]; LoggerHandle
0x18000c772  call    WPP_SF_sss
0x18000c777  test    ebx, ebx
0x18000c779  setns   al
0x18000c77c  jmp     loc_18000C68F
0x18000c781  lea     r8, aIas_0; "\\ias"
0x18000c788  mov     edx, 104h; SizeInWords
0x18000c78d  lea     rcx, [rbp+2A0h+Buffer]; Destination
0x18000c791  call    cs:__imp_wcscat_s
0x18000c797  mov     rax, [rbx]
0x18000c79a  lea     rcx, aIasXml_0; "ias*.xml"
0x18000c7a1  mov     dword ptr [rsp+3A0h+var_368], 0F0Fh
0x18000c7a9  lea     r9, [rbp+2A0h+Buffer]
0x18000c7ad  mov     [rsp+3A0h+var_370], rsi
0x18000c7b2  mov     r8, r14
0x18000c7b5  mov     byte ptr [rsp+3A0h+var_378], sil
0x18000c7ba  xor     edx, edx
0x18000c7bc  mov     rax, [rax+28h]
0x18000c7c0  mov     [rsp+3A0h+var_380], rcx
0x18000c7c5  mov     rcx, rbx
0x18000c7c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7cd  test    eax, eax
0x18000c7cf  jns     short loc_18000C847
0x18000c7d1  lea     rdx, [rsp+3A0h+var_330]; Buffer
0x18000c7d6  mov     ecx, eax; dwMessageId
0x18000c7d8  call    IASFormatSysErr
0x18000c7dd  mov     eax, eax
0x18000c7df  cmp     rax, 100h
0x18000c7e5  jnb     loc_18000C8F6
0x18000c7eb  mov     [rsp+rax+3A0h+var_330], sil
0x18000c7f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c7f7  lea     rax, WPP_GLOBAL_Control
0x18000c7fe  cmp     rcx, rax
0x18000c801  jz      loc_18000C68D
0x18000c807  cmp     [rcx+19h], dil
0x18000c80b  jb      loc_18000C68D
0x18000c811  test    byte ptr [rcx+1Ch], 10h
0x18000c815  jz      loc_18000C68D
0x18000c81b  lea     rbx, aIvsscreatewrit_0; "IVssCreateWriterMetadata::AddFilesToFil"...
0x18000c822  mov     r8, rbx
0x18000c825  lea     r9, [rsp+3A0h+var_330]
0x18000c82a  lea     rdx, aNpsds; "NPSDS"
0x18000c831  lea     rcx, aCpuPidTidNowSL; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x18000c838  call    WppDbgPrint
0x18000c83d  mov     edx, 0Ch
0x18000c842  jmp     loc_18000C66E
0x18000c847  mov     rax, [rbx]
0x18000c84a  xor     r9d, r9d
0x18000c84d  mov     byte ptr [rsp+3A0h+var_378], 1
0x18000c852  xor     r8d, r8d
0x18000c855  mov     rcx, rbx
0x18000c858  mov     dword ptr [rsp+3A0h+var_380], 1
0x18000c860  mov     rax, [rax+30h]
0x18000c864  lea     edx, [r9+5]
0x18000c868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c86d  test    eax, eax
0x18000c86f  jns     short loc_18000C8E3
0x18000c871  lea     rdx, [rsp+3A0h+var_330]; Buffer
0x18000c876  mov     ecx, eax; dwMessageId
0x18000c878  call    IASFormatSysErr
0x18000c87d  mov     eax, eax
0x18000c87f  cmp     rax, 100h
0x18000c885  jnb     short loc_18000C8FC
0x18000c887  mov     [rsp+rax+3A0h+var_330], sil
0x18000c88c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c893  lea     rax, WPP_GLOBAL_Control
0x18000c89a  cmp     rcx, rax
0x18000c89d  jz      loc_18000C68D
0x18000c8a3  cmp     [rcx+19h], dil
0x18000c8a7  jb      loc_18000C68D
0x18000c8ad  test    byte ptr [rcx+1Ch], 10h
0x18000c8b1  jz      loc_18000C68D
0x18000c8b7  lea     rbx, aIvsscreatewrit; "IVssCreateWriterMetadata::SetRestoreMet"...
0x18000c8be  mov     r8, rbx
0x18000c8c1  lea     r9, [rsp+3A0h+var_330]
0x18000c8c6  lea     rdx, aNpsds; "NPSDS"
0x18000c8cd  lea     rcx, aCpuPidTidNowSL; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x18000c8d4  call    WppDbgPrint
0x18000c8d9  mov     edx, 0Dh
0x18000c8de  jmp     loc_18000C66E
0x18000c8e3  mov     al, 1
0x18000c8e5  jmp     loc_18000C68F
0x18000c8ea  call    __report_rangecheckfailure
0x18000c8f0  call    __report_rangecheckfailure
0x18000c8f6  call    __report_rangecheckfailure
0x18000c8fc  call    __report_rangecheckfailure
```
