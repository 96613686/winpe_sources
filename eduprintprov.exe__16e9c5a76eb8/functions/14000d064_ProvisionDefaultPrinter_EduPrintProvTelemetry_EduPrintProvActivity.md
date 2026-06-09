# ProvisionDefaultPrinter(EduPrintProvTelemetry::EduPrintProvActivity *)

- ea: `0x14000d064`
- end: `0x14000d205`
- name: `?ProvisionDefaultPrinter@@YAXPEAVEduPrintProvActivity@EduPrintProvTelemetry@@@Z`
- size: `417`
- prototype: `void __fastcall(struct EduPrintProvTelemetry::EduPrintProvActivity *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140011bb0`

## callees

- `0x140002600`
- `0x1400034f8`
- `0x140004e30`
- `0x14000c88c`
- `0x14000d064`
- `0x14000ddb8`
- `0x14000f0cc`
- `0x1400111bc`
- `0x140014010`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z` at `0x14000d1b2`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z` at `0x14000d1b2`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x14000d1a7`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x14000d1a7`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x14000d0b6`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x14000d1c2`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x14000d0b6`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x14000d1c2`
- `msvcp_win!?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A` at `0x14000d0a0`
- `msvcp_win!?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A` at `0x14000d130`
- `msvcp_win!?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A` at `0x14000d16a`
- `msvcp_win!?setbase@std@@YA?AU?$_Smanip@H@1@H@Z` at `0x14000d182`
- `msvcp_win!?setbase@std@@YA?AU?$_Smanip@H@1@H@Z` at `0x14000d182`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000d10e`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000d10e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ProvisionDefaultPrinter(struct EduPrintProvTelemetry::EduPrintProvActivity *this)
{
  const unsigned __int16 *v2; // rdx
  __int64 v3; // rax
  Util *v4; // rcx
  int v5; // edi
  unsigned int v6; // eax
  unsigned int v7; // r8d
  __int64 v8; // rax
  Util **v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rax
  Util **v15; // rdx
  unsigned int lpData; // [rsp+20h] [rbp-58h]
  int Data; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v18[16]; // [rsp+38h] [rbp-40h] BYREF
  Util *v19[3]; // [rsp+48h] [rbp-30h] BYREF
  unsigned __int64 v20; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  MdmStore::_LoadStringPolicy(v19, L"DefaultPrinterName");
  if ( v19[2] )
  {
    v4 = (Util *)v19;
    if ( v20 > 7 )
      v4 = v19[0];
    v5 = Util::ProvisionDefaultPrinter(v4, v2);
    if ( v5 < 0 )
    {
      v12 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
              std::wcout,
              L"ProvisionDefaultPrinter failed, hr = ");
      v13 = std::setbase(v18, 16);
      (*(void (__fastcall **)(__int64, _QWORD))v13)(v12 + *(int *)(*(_QWORD *)v12 + 4LL), *(unsigned int *)(v13 + 8));
      v14 = std::basic_ostream<unsigned short>::operator<<(v12, std::showbase);
      v11 = std::basic_ostream<unsigned short>::operator<<(v14, (unsigned int)v5);
    }
    else
    {
      Data = 1;
      v6 = RegSetKeyValueW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Windows",
             L"LegacyDefaultPrinterMode",
             4u,
             &Data,
             4u);
      if ( v6 )
        wil::details::in1diag3::_Log_Win32(retaddr, (void *)0x130, v7, (const char *)v6, lpData);
      v8 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(std::wcout, L"Printer \"");
      v9 = v19;
      if ( v20 > 7 )
        v9 = (Util **)v19[0];
      v10 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v8, v9);
      v11 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v10, L"\" is now the default printer.");
    }
    std::basic_ostream<unsigned short>::operator<<(v11, std::endl<unsigned short,std::char_traits<unsigned short>>);
    if ( this )
    {
      v15 = v19;
      if ( v20 > 7 )
        v15 = (Util **)v19[0];
      EduPrintProvTelemetry::EduPrintProvActivity::SetDefaultPrinterResult(this, (const unsigned __int16 *)v15, v5);
    }
  }
  else
  {
    v3 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
           std::wcout,
           L"No default printer policy - nothing to do.");
    std::basic_ostream<unsigned short>::operator<<(v3, std::endl<unsigned short,std::char_traits<unsigned short>>);
  }
  std::wstring::~wstring(v19);
}

```

## disassembly

```asm
0x14000d064  push    rbp
0x14000d066  push    rbx
0x14000d067  push    rsi
0x14000d068  push    rdi
0x14000d069  mov     rbp, rsp
0x14000d06c  sub     rsp, 78h
0x14000d070  mov     rax, cs:__security_cookie
0x14000d077  xor     rax, rsp
0x14000d07a  mov     [rbp+var_10], rax
0x14000d07e  mov     rsi, rcx
0x14000d081  lea     rdx, aDefaultprinter; "DefaultPrinterName"
0x14000d088  lea     rcx, [rbp+var_30]
0x14000d08c  call    ?_LoadStringPolicy@MdmStore@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; MdmStore::_LoadStringPolicy(ushort const *)
0x14000d091  nop
0x14000d092  cmp     [rbp+var_20], 0
0x14000d097  jnz     short loc_14000D0C1
0x14000d099  lea     rdx, aNoDefaultPrint; "No default printer policy - nothing to "...
0x14000d0a0  mov     rcx, cs:__imp_?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A; std::basic_ostream<ushort> std::wcout
0x14000d0a7  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000d0ac  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x14000d0b3  mov     rcx, rax
0x14000d0b6  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x14000d0bc  jmp     loc_14000D1E7
0x14000d0c1  lea     rcx, [rbp+var_30]
0x14000d0c5  cmp     [rbp+var_18], 7
0x14000d0ca  cmova   rcx, [rbp+var_30]; this
0x14000d0cf  call    ?ProvisionDefaultPrinter@Util@@YAJPEBG@Z; Util::ProvisionDefaultPrinter(ushort const *)
0x14000d0d4  mov     edi, eax
0x14000d0d6  test    eax, eax
0x14000d0d8  js      loc_14000D163
0x14000d0de  mov     [rbp+Data], 1
0x14000d0e5  mov     r9d, 4; dwType
0x14000d0eb  mov     [rsp+78h+cbData], r9d; cbData
0x14000d0f0  lea     rax, [rbp+Data]
0x14000d0f4  mov     [rsp+78h+lpData], rax; unsigned int
0x14000d0f9  lea     r8, ValueName; "LegacyDefaultPrinterMode"
0x14000d100  lea     rdx, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x14000d107  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14000d10e  call    cs:__imp_RegSetKeyValueW
0x14000d114  mov     rcx, [rbp+20h]; this
0x14000d118  test    eax, eax
0x14000d11a  jz      short loc_14000D129
0x14000d11c  mov     r9d, eax; char *
0x14000d11f  mov     edx, 130h; void *
0x14000d124  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x14000d129  lea     rdx, aPrinter; "Printer \""
0x14000d130  mov     rcx, cs:__imp_?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A; std::basic_ostream<ushort> std::wcout
0x14000d137  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000d13c  lea     rdx, [rbp+var_30]
0x14000d140  cmp     [rbp+var_18], 7
0x14000d145  cmova   rdx, [rbp+var_30]
0x14000d14a  mov     rcx, rax
0x14000d14d  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000d152  mov     rcx, rax
0x14000d155  lea     rdx, aIsNowTheDefaul; "\" is now the default printer."
0x14000d15c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000d161  jmp     short loc_14000D1B8
0x14000d163  lea     rdx, aProvisiondefau; "ProvisionDefaultPrinter failed, hr = "
0x14000d16a  mov     rcx, cs:__imp_?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A; std::basic_ostream<ushort> std::wcout
0x14000d171  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000d176  mov     rbx, rax
0x14000d179  mov     edx, 10h
0x14000d17e  lea     rcx, [rbp+var_40]
0x14000d182  call    cs:__imp_?setbase@std@@YA?AU?$_Smanip@H@1@H@Z; std::setbase(int)
0x14000d188  mov     rcx, [rbx]
0x14000d18b  movsxd  rcx, dword ptr [rcx+4]
0x14000d18f  add     rcx, rbx
0x14000d192  mov     edx, [rax+8]
0x14000d195  mov     rax, [rax]
0x14000d198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d19d  lea     rdx, ?showbase@std@@YAAEAVios_base@1@AEAV21@@Z; std::showbase(std::ios_base &)
0x14000d1a4  mov     rcx, rbx
0x14000d1a7  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::basic_ostream<ushort>::operator<<(std::ios_base & (*)(std::ios_base &))
0x14000d1ad  mov     edx, edi
0x14000d1af  mov     rcx, rax
0x14000d1b2  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z; std::basic_ostream<ushort>::operator<<(long)
0x14000d1b8  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x14000d1bf  mov     rcx, rax
0x14000d1c2  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x14000d1c8  test    rsi, rsi
0x14000d1cb  jz      short loc_14000D1E7
0x14000d1cd  lea     rdx, [rbp+var_30]
0x14000d1d1  cmp     [rbp+var_18], 7
0x14000d1d6  cmova   rdx, [rbp+var_30]; unsigned __int16 *
0x14000d1db  mov     r8d, edi; int
0x14000d1de  mov     rcx, rsi; this
0x14000d1e1  call    ?SetDefaultPrinterResult@EduPrintProvActivity@EduPrintProvTelemetry@@QEAAXPEBGJ@Z; EduPrintProvTelemetry::EduPrintProvActivity::SetDefaultPrinterResult(ushort const *,long)
0x14000d1e6  nop
0x14000d1e7  lea     rcx, [rbp+var_30]
0x14000d1eb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000d1f0  mov     rcx, [rbp+var_10]
0x14000d1f4  xor     rcx, rsp; StackCookie
0x14000d1f7  call    __security_check_cookie
0x14000d1fc  add     rsp, 78h
0x14000d200  pop     rdi
0x14000d201  pop     rsi
0x14000d202  pop     rbx
0x14000d203  pop     rbp
0x14000d204  retn
```
