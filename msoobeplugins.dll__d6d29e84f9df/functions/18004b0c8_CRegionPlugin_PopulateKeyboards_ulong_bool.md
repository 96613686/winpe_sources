# CRegionPlugin::_PopulateKeyboards(ulong,bool)

- ea: `0x18004b0c8`
- end: `0x18004b2ef`
- name: `?_PopulateKeyboards@CRegionPlugin@@AEAAJK_N@Z`
- size: `551`
- prototype: `__int64 __fastcall(CRegionPlugin *__hidden this, unsigned int, bool)`
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004af84`
- `0x18004b444`

## callees

- `0x180003470`
- `0x1800098cc`
- `0x18000bdf4`
- `0x1800418d8`
- `0x180048d88`
- `0x18004a7d4`
- `0x18004a868`
- `0x18004a95c`
- `0x18004ab3c`
- `0x18004b0c8`
- `0x18004b8b0`
- `0x1800b8834`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b125`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b15f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b193`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b125`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b15f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b193`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004b173`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004b1a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004b1e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004b1f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004b266`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004b173`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004b1a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004b1e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004b1f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004b266`
- `Bcp47Langs!Bcp47FromLcid` at `0x18004b139`
- `Bcp47Langs!Bcp47FromLcid` at `0x18004b139`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CRegionPlugin::_PopulateKeyboards(COOBEItemCollection **this, unsigned int a2, char a3)
{
  int DefaultKeyboardForLocale; // ebx
  const unsigned __int16 *StringRawBuffer; // rax
  CRegionPlugin *v8; // rcx
  const unsigned __int16 *v9; // rdi
  const unsigned __int16 (*v10)[1]; // rdx
  HSTRING v11; // rbx
  const unsigned __int16 *v12; // rbx
  const unsigned __int16 *v13; // rax
  const unsigned __int16 *v14; // rdx
  bool v15; // al
  int v16; // eax
  __int64 (__fastcall *v17)(COOBEItemCollection **, PCWSTR); // rbx
  PCWSTR v18; // rdx
  int v19; // eax
  bool v21; // [rsp+20h] [rbp-29h] BYREF
  HSTRING v22; // [rsp+28h] [rbp-21h] BYREF
  HSTRING v23; // [rsp+30h] [rbp-19h] BYREF
  HSTRING string; // [rsp+38h] [rbp-11h] BYREF
  _QWORD v25[4]; // [rsp+40h] [rbp-9h] BYREF
  HSTRING v26; // [rsp+60h] [rbp+17h] BYREF

  SafeRelease<IOOBETimeZoneItem>(this + 10);
  COOBEItemCollection::Clear(this[7]);
  if ( ((a2 - 3072) & 0xFFFFFBFF) != 0 )
  {
    WindowsDeleteString(0);
    string = 0;
    DefaultKeyboardForLocale = Bcp47FromLcid(a2, &string);
    if ( DefaultKeyboardForLocale < 0 )
    {
LABEL_14:
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
      return (unsigned int)DefaultKeyboardForLocale;
    }
    v21 = 0;
    v22 = 0;
    WindowsDeleteString(0);
    v23 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    DefaultKeyboardForLocale = CRegionPlugin::_GetDefaultKeyboardForLocale(v8, StringRawBuffer, &v23);
    if ( DefaultKeyboardForLocale < 0 )
      goto LABEL_13;
    WindowsDeleteString(v22);
    v22 = 0;
    v9 = WindowsGetStringRawBuffer(string, 0);
    v11 = *Windows::Internal::StringReference::StringReference(&v26, v10);
    Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v25, v9);
    DefaultKeyboardForLocale = GetCompatibleInputMethodsForLanguage(v25[0], v11, &v22);
    if ( DefaultKeyboardForLocale < 0 )
      goto LABEL_13;
    v12 = WindowsGetStringRawBuffer(v22, 0);
    v13 = WindowsGetStringRawBuffer(v23, 0);
    DefaultKeyboardForLocale = CRegionPlugin::_CreateAndAddKeyboardItems((CRegionPlugin *)this, v13, v12, &v21);
    if ( DefaultKeyboardForLocale < 0 )
      goto LABEL_13;
    v14 = (const unsigned __int16 *)this[12];
    v15 = v21;
    if ( v14 )
    {
      if ( v21 )
        goto LABEL_17;
      v16 = CRegionPlugin::_CreateAndAddKeyboardItem((CRegionPlugin *)this, v14, 0);
      DefaultKeyboardForLocale = v16;
      if ( v16 < 0 )
      {
        UnattendLogW(2, L"Failed to retrieve OEM keyboard [%s] with hr=0x%08X", this[12], (unsigned int)v16);
        DefaultKeyboardForLocale = 0;
        goto LABEL_10;
      }
      v15 = 1;
    }
    if ( !v15 )
    {
LABEL_10:
      if ( a3 )
      {
        v17 = (__int64 (__fastcall *)(COOBEItemCollection **, PCWSTR))*((_QWORD *)this[4] + 17);
        v18 = WindowsGetStringRawBuffer(v23, 0);
        v19 = v17(this + 4, v18);
LABEL_12:
        DefaultKeyboardForLocale = v19;
      }
LABEL_13:
      Windows::Internal::String::~String((Windows::Internal::String *)&v22);
      Windows::Internal::String::~String((Windows::Internal::String *)&v23);
      goto LABEL_14;
    }
LABEL_17:
    v19 = (*((__int64 (__fastcall **)(char *, COOBEItemCollection *))this[4] + 17))((char *)this + 32, this[12]);
    goto LABEL_12;
  }
  UnattendLogW(0, L"Leaving empty keyboard list for non-LCID-backed locale (0x%04X)", a2);
  return 0;
}

```

## disassembly

```asm
0x18004b0c8  mov     [rsp-8+arg_10], rbx
0x18004b0cd  mov     [rsp-8+arg_18], rsi
0x18004b0d2  push    rbp
0x18004b0d3  push    rdi
0x18004b0d4  push    r14
0x18004b0d6  lea     rbp, [rsp-47h]
0x18004b0db  sub     rsp, 90h
0x18004b0e2  mov     rax, cs:__security_cookie
0x18004b0e9  xor     rax, rsp
0x18004b0ec  mov     [rbp+57h+var_20], rax
0x18004b0f0  mov     r14b, r8b
0x18004b0f3  mov     ebx, edx
0x18004b0f5  mov     rsi, rcx
0x18004b0f8  add     rcx, 50h ; 'P'
0x18004b0fc  call    ??$SafeRelease@UIOOBETimeZoneItem@@@@YAXPEAPEAUIOOBETimeZoneItem@@@Z; SafeRelease<IOOBETimeZoneItem>(IOOBETimeZoneItem * *)
0x18004b101  mov     rcx, [rsi+38h]; this
0x18004b105  call    ?Clear@COOBEItemCollection@@QEAAJXZ; COOBEItemCollection::Clear(void)
0x18004b10a  lea     eax, [rbx-0C00h]
0x18004b110  test    eax, 0FFFFFBFFh
0x18004b115  jz      loc_18004B2B8
0x18004b11b  mov     [rbp+57h+string], 0
0x18004b123  xor     ecx, ecx; string
0x18004b125  call    cs:__imp_WindowsDeleteString
0x18004b12b  mov     [rbp+57h+string], 0
0x18004b133  lea     rdx, [rbp+57h+string]
0x18004b137  mov     ecx, ebx
0x18004b139  call    cs:__imp_Bcp47FromLcid
0x18004b13f  mov     ebx, eax
0x18004b141  test    eax, eax
0x18004b143  js      loc_18004B291
0x18004b149  mov     [rbp+57h+var_80], 0
0x18004b14d  mov     [rbp+57h+var_70], 0
0x18004b155  mov     [rbp+57h+var_78], 0
0x18004b15d  xor     ecx, ecx; string
0x18004b15f  call    cs:__imp_WindowsDeleteString
0x18004b165  mov     [rbp+57h+var_70], 0
0x18004b16d  xor     edx, edx; length
0x18004b16f  mov     rcx, [rbp+57h+string]; string
0x18004b173  call    cs:__imp_WindowsGetStringRawBuffer
0x18004b179  lea     r8, [rbp+57h+var_70]; HSTRING *
0x18004b17d  mov     rdx, rax; unsigned __int16 *
0x18004b180  call    ?_GetDefaultKeyboardForLocale@CRegionPlugin@@AEAAJPEBGPEAPEAUHSTRING__@@@Z; CRegionPlugin::_GetDefaultKeyboardForLocale(ushort const *,HSTRING__ * *)
0x18004b185  mov     ebx, eax
0x18004b187  test    eax, eax
0x18004b189  js      loc_18004B27D
0x18004b18f  mov     rcx, [rbp+57h+var_78]; string
0x18004b193  call    cs:__imp_WindowsDeleteString
0x18004b199  mov     [rbp+57h+var_78], 0
0x18004b1a1  xor     edx, edx; length
0x18004b1a3  mov     rcx, [rbp+57h+string]; string
0x18004b1a7  call    cs:__imp_WindowsGetStringRawBuffer
0x18004b1ad  mov     rdi, rax
0x18004b1b0  lea     rcx, [rbp+57h+var_40]; string
0x18004b1b4  call    ??$?0$00@StringReference@Internal@Windows@@QEAA@AEAY00$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[1])
0x18004b1b9  mov     rbx, [rax]
0x18004b1bc  mov     rdx, rdi; unsigned __int16 *
0x18004b1bf  lea     rcx, [rbp+57h+var_60]; this
0x18004b1c3  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18004b1c8  lea     r8, [rbp+57h+var_78]
0x18004b1cc  mov     rdx, rbx
0x18004b1cf  mov     rcx, [rbp+57h+var_60]
0x18004b1d3  call    GetCompatibleInputMethodsForLanguage
0x18004b1d8  mov     ebx, eax
0x18004b1da  test    eax, eax
0x18004b1dc  js      loc_18004B27D
0x18004b1e2  xor     edx, edx; length
0x18004b1e4  mov     rcx, [rbp+57h+var_78]; string
0x18004b1e8  call    cs:__imp_WindowsGetStringRawBuffer
0x18004b1ee  mov     rbx, rax
0x18004b1f1  xor     edx, edx; length
0x18004b1f3  mov     rcx, [rbp+57h+var_70]; string
0x18004b1f7  call    cs:__imp_WindowsGetStringRawBuffer
0x18004b1fd  lea     r9, [rbp+57h+var_80]; bool *
0x18004b201  mov     r8, rbx; unsigned __int16 *
0x18004b204  mov     rdx, rax; unsigned __int16 *
0x18004b207  mov     rcx, rsi; this
0x18004b20a  call    ?_CreateAndAddKeyboardItems@CRegionPlugin@@AEAAJPEBG0PEA_N@Z; CRegionPlugin::_CreateAndAddKeyboardItems(ushort const *,ushort const *,bool *)
0x18004b20f  mov     ebx, eax
0x18004b211  test    eax, eax
0x18004b213  js      short loc_18004B27D
0x18004b215  mov     rdx, [rsi+60h]; unsigned __int16 *
0x18004b219  mov     al, [rbp+57h+var_80]
0x18004b21c  test    rdx, rdx
0x18004b21f  jz      short loc_18004B2A0
0x18004b221  test    al, al
0x18004b223  jnz     short loc_18004B2A4
0x18004b225  xor     r8d, r8d; bool
0x18004b228  mov     rcx, rsi; this
0x18004b22b  call    ?_CreateAndAddKeyboardItem@CRegionPlugin@@AEAAJPEBG_N@Z; CRegionPlugin::_CreateAndAddKeyboardItem(ushort const *,bool)
0x18004b230  mov     ebx, eax
0x18004b232  test    eax, eax
0x18004b234  jns     short loc_18004B29E
0x18004b236  mov     r9d, eax
0x18004b239  mov     r8, [rsi+60h]
0x18004b23d  lea     rdx, aFailedToRetrie_0; "Failed to retrieve OEM keyboard [%s] wi"...
0x18004b244  mov     ecx, 2
0x18004b249  call    UnattendLogW
0x18004b24e  xor     ebx, ebx
0x18004b250  test    r14b, r14b
0x18004b253  jz      short loc_18004B27D
0x18004b255  mov     rax, [rsi+20h]
0x18004b259  mov     rbx, [rax+88h]
0x18004b260  xor     edx, edx; length
0x18004b262  mov     rcx, [rbp+57h+var_70]; string
0x18004b266  call    cs:__imp_WindowsGetStringRawBuffer
0x18004b26c  mov     rdx, rax
0x18004b26f  lea     rcx, [rsi+20h]
0x18004b273  mov     rax, rbx
0x18004b276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b27b  mov     ebx, eax
0x18004b27d  lea     rcx, [rbp+57h+var_78]; this
0x18004b281  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18004b286  nop
0x18004b287  lea     rcx, [rbp+57h+var_70]; this
0x18004b28b  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18004b290  nop
0x18004b291  lea     rcx, [rbp+57h+string]; this
0x18004b295  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18004b29a  mov     eax, ebx
0x18004b29c  jmp     short loc_18004B2CB
0x18004b29e  mov     al, 1
0x18004b2a0  test    al, al
0x18004b2a2  jz      short loc_18004B250
0x18004b2a4  lea     rcx, [rsi+20h]
0x18004b2a8  mov     rax, [rcx]
0x18004b2ab  mov     rdx, [rsi+60h]
0x18004b2af  mov     rax, [rax+88h]
0x18004b2b6  jmp     short loc_18004B276
0x18004b2b8  mov     r8d, ebx
0x18004b2bb  lea     rdx, aLeavingEmptyKe; "Leaving empty keyboard list for non-LCI"...
0x18004b2c2  xor     ecx, ecx
0x18004b2c4  call    UnattendLogW
0x18004b2c9  xor     eax, eax
0x18004b2cb  mov     rcx, [rbp+57h+var_20]
0x18004b2cf  xor     rcx, rsp; StackCookie
0x18004b2d2  call    __security_check_cookie
0x18004b2d7  lea     r11, [rsp+0A0h+var_10]
0x18004b2df  mov     rbx, [r11+30h]
0x18004b2e3  mov     rsi, [r11+38h]
0x18004b2e7  mov     rsp, r11
0x18004b2ea  pop     r14
0x18004b2ec  pop     rdi
0x18004b2ed  pop     rbp
0x18004b2ee  retn
```
