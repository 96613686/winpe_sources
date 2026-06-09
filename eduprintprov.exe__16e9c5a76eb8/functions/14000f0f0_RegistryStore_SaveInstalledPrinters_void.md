# RegistryStore::_SaveInstalledPrinters(void)

- ea: `0x14000f0f0`
- end: `0x14000f2dd`
- name: `?_SaveInstalledPrinters@RegistryStore@@AEBAXXZ`
- size: `493`
- prototype: `void __fastcall(RegistryStore *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000e9a8`

## callees

- `0x140002600`
- `0x1400034f8`
- `0x140004e30`
- `0x14000e56c`
- `0x14000e870`
- `0x14000f0cc`
- `0x14000f0f0`
- `0x14000f930`

## import_xrefs

- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x14000f2b4`
- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x14000f2b4`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x14000f2be`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x14000f2be`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z` at `0x14000f1b4`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z` at `0x14000f1b4`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x14000f25e`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x14000f25e`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x14000f184`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x14000f1d3`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x14000f26e`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x14000f184`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x14000f1d3`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x14000f26e`
- `msvcp_win!?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A` at `0x14000f1a1`
- `msvcp_win!?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A` at `0x14000f24d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000f226`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000f226`

## string_xrefs

- `0x14000f1bd`: ` printer(s) to save to the registry:`
- `0x14000f246`: `Error writing printer names to registry: `
- `0x14000f211`: `InstalledPrinters`

## pseudocode

```c
void __fastcall RegistryStore::_SaveInstalledPrinters(RegistryStore *this)
{
  _QWORD *v2; // rbx
  _QWORD *v3; // rdi
  _QWORD *v4; // rdx
  __int64 v5; // rax
  __int64 v6; // rax
  _QWORD *v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  LPCVOID *v14; // rdx
  LPCVOID *v15; // rcx
  unsigned int v16; // eax
  unsigned int v17; // r8d
  unsigned int v18; // ebx
  __int64 v19; // rax
  __int64 v20; // rax
  unsigned int lpData; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  _QWORD v23[2]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v24[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v25[8]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v26[120]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v27[104]; // [rsp+C8h] [rbp-38h] BYREF
  LPCVOID v28[2]; // [rsp+130h] [rbp+30h] BYREF
  int v29; // [rsp+140h] [rbp+40h]
  unsigned __int64 v30; // [rsp+148h] [rbp+48h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v23);
  v2 = *(_QWORD **)this;
  v3 = (_QWORD *)*((_QWORD *)this + 2);
  while ( 1 )
  {
    v3 = (_QWORD *)*v3;
    v2 = (_QWORD *)*v2;
    if ( v2 == *(_QWORD **)this )
      break;
    v4 = v2 + 2;
    if ( v2[5] > 7u )
      v4 = (_QWORD *)*v4;
    v5 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v24, v4);
    v6 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v5, &dword_140016F64);
    v7 = v3 + 2;
    if ( v3[5] > 7u )
      v7 = (_QWORD *)*v7;
    v8 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v6, v7);
    v9 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v8, "\n");
    std::basic_ostream<unsigned short>::operator<<(v9, std::endl<unsigned short,std::char_traits<unsigned short>>);
  }
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(v23, v28);
  v10 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(std::wcout, L"Found ");
  v11 = std::basic_ostream<unsigned short>::operator<<(v10, *((_QWORD *)this + 1));
  v12 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v11, L" printer(s) to save to the registry:");
  v13 = std::basic_ostream<unsigned short>::operator<<(v12, std::endl<unsigned short,std::char_traits<unsigned short>>);
  v14 = v28;
  if ( v30 > 7 )
    v14 = (LPCVOID *)v28[0];
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v13, v14);
  v15 = v28;
  if ( v30 > 7 )
    v15 = (LPCVOID *)v28[0];
  v16 = RegSetKeyValueW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Print\\EDU",
          L"InstalledPrinters",
          1u,
          v15,
          2 * v29);
  v18 = v16;
  if ( v16 )
  {
    wil::details::in1diag3::_Log_Win32(retaddr, (void *)0xF6, v17, (const char *)v16, lpData);
    v19 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
            std::wcout,
            L"Error writing printer names to registry: ");
    v20 = std::basic_ostream<unsigned short>::operator<<(v19, v18);
    std::basic_ostream<unsigned short>::operator<<(v20, std::endl<unsigned short,std::char_traits<unsigned short>>);
  }
  std::wstring::~wstring(v28);
  *(_QWORD *)((char *)v23 + *(int *)(v23[0] + 4LL)) = &std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vftable';
  *(int *)((char *)&v22 + *(int *)(v23[0] + 4LL)) = *(_DWORD *)(v23[0] + 4LL) - 152;
  std::basic_stringbuf<unsigned short>::~basic_stringbuf<unsigned short>(v25);
  std::basic_iostream<unsigned short>::~basic_iostream<unsigned short,std::char_traits<unsigned short>>(v26);
  std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v27);
}

```

## disassembly

```asm
0x14000f0f0  push    rbp
0x14000f0f2  push    rbx
0x14000f0f3  push    rsi
0x14000f0f4  push    rdi
0x14000f0f5  lea     rbp, [rsp-68h]
0x14000f0fa  sub     rsp, 168h
0x14000f101  mov     rax, cs:__security_cookie
0x14000f108  xor     rax, rsp
0x14000f10b  mov     [rbp+80h+var_30], rax
0x14000f10f  mov     rsi, rcx
0x14000f112  lea     rcx, [rsp+180h+var_150]
0x14000f117  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x14000f11c  mov     rbx, [rsi]
0x14000f11f  mov     rdi, [rsi+10h]
0x14000f123  mov     rdi, [rdi]
0x14000f126  mov     rbx, [rbx]
0x14000f129  cmp     rbx, [rsi]
0x14000f12c  jz      short loc_14000F18C
0x14000f12e  lea     rdx, [rbx+10h]
0x14000f132  cmp     qword ptr [rbx+28h], 7
0x14000f137  jbe     short loc_14000F13C
0x14000f139  mov     rdx, [rdx]
0x14000f13c  lea     rcx, [rsp+180h+var_140]
0x14000f141  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000f146  mov     rcx, rax
0x14000f149  lea     rdx, dword_140016F64
0x14000f150  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000f155  lea     rdx, [rdi+10h]
0x14000f159  cmp     qword ptr [rdi+28h], 7
0x14000f15e  jbe     short loc_14000F163
0x14000f160  mov     rdx, [rdx]
0x14000f163  mov     rcx, rax
0x14000f166  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000f16b  mov     rcx, rax
0x14000f16e  lea     rdx, asc_140016EE0; "\n"
0x14000f175  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000f17a  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x14000f181  mov     rcx, rax
0x14000f184  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x14000f18a  jmp     short loc_14000F123
0x14000f18c  lea     rdx, [rbp+80h+var_50]
0x14000f190  lea     rcx, [rsp+180h+var_150]
0x14000f195  call    ?str@?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::str(void)
0x14000f19a  lea     rdx, aFound; "Found "
0x14000f1a1  mov     rcx, cs:__imp_?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A; std::basic_ostream<ushort> std::wcout
0x14000f1a8  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000f1ad  mov     rdx, [rsi+8]
0x14000f1b1  mov     rcx, rax
0x14000f1b4  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z; std::basic_ostream<ushort>::operator<<(unsigned __int64)
0x14000f1ba  mov     rcx, rax
0x14000f1bd  lea     rdx, aPrinterSToSave; " printer(s) to save to the registry:"
0x14000f1c4  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000f1c9  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x14000f1d0  mov     rcx, rax
0x14000f1d3  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x14000f1d9  lea     rdx, [rbp+80h+var_50]
0x14000f1dd  cmp     [rbp+80h+var_38], 7
0x14000f1e2  cmova   rdx, [rbp+80h+var_50]
0x14000f1e7  mov     rcx, rax
0x14000f1ea  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000f1ef  mov     eax, [rbp+80h+var_40]
0x14000f1f2  add     eax, eax
0x14000f1f4  lea     rcx, [rbp+80h+var_50]
0x14000f1f8  cmp     [rbp+80h+var_38], 7
0x14000f1fd  cmova   rcx, [rbp+80h+var_50]
0x14000f202  mov     [rsp+180h+cbData], eax; cbData
0x14000f206  mov     [rsp+180h+lpData], rcx; unsigned int
0x14000f20b  mov     r9d, 1; dwType
0x14000f211  lea     r8, aInstalledprint; "InstalledPrinters"
0x14000f218  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14000f21f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14000f226  call    cs:__imp_RegSetKeyValueW
0x14000f22c  mov     ebx, eax
0x14000f22e  test    eax, eax
0x14000f230  jz      short loc_14000F274
0x14000f232  mov     rcx, [rbp+88h]; this
0x14000f239  mov     r9d, eax; char *
0x14000f23c  mov     edx, 0F6h; void *
0x14000f241  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x14000f246  lea     rdx, aErrorWritingPr; "Error writing printer names to registry"...
0x14000f24d  mov     rcx, cs:__imp_?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A; std::basic_ostream<ushort> std::wcout
0x14000f254  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000f259  mov     edx, ebx
0x14000f25b  mov     rcx, rax
0x14000f25e  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x14000f264  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x14000f26b  mov     rcx, rax
0x14000f26e  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x14000f274  lea     rcx, [rbp+80h+var_50]
0x14000f278  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000f27d  mov     rax, [rsp+180h+var_150]
0x14000f282  movsxd  rcx, dword ptr [rax+4]
0x14000f286  lea     rax, ??_7?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vftable'
0x14000f28d  mov     [rsp+rcx+180h+var_150], rax
0x14000f292  mov     rax, [rsp+180h+var_150]
0x14000f297  movsxd  rcx, dword ptr [rax+4]
0x14000f29b  lea     edx, [rcx-98h]
0x14000f2a1  mov     [rsp+rcx+180h+var_154], edx
0x14000f2a5  lea     rcx, [rsp+180h+var_138]
0x14000f2aa  call    ??1?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_stringbuf<ushort>::~basic_stringbuf<ushort>(void)
0x14000f2af  lea     rcx, [rsp+180h+var_130]
0x14000f2b4  call    cs:__imp_??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_iostream<ushort>::~basic_iostream<ushort,std::char_traits<ushort>>(void)
0x14000f2ba  lea     rcx, [rbp+80h+var_B8]
0x14000f2be  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x14000f2c4  nop
0x14000f2c5  mov     rcx, [rbp+80h+var_30]
0x14000f2c9  xor     rcx, rsp; StackCookie
0x14000f2cc  call    __security_check_cookie
0x14000f2d1  add     rsp, 168h
0x14000f2d8  pop     rdi
0x14000f2d9  pop     rsi
0x14000f2da  pop     rbx
0x14000f2db  pop     rbp
0x14000f2dc  retn
```
