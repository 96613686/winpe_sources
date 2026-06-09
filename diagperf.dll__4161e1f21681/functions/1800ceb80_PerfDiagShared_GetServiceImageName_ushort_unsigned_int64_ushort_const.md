# PerfDiagShared::GetServiceImageName(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800ceb80`
- end: `0x1800ced43`
- name: `?GetServiceImageName@PerfDiagShared@@YAJPEAG_KPEBG@Z`
- size: `451`
- prototype: `__int64 __fastcall(LPWSTR lpDst, unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x1800c41b4`

## callees

- `0x18001a50c`
- `0x18001a56c`
- `0x180041bb4`
- `0x1800ceb80`
- `0x1800cee94`
- `0x1800cf080`

## import_xrefs

- `msvcrt!wcsstr` at `0x1800cec3b`
- `msvcrt!wcsstr` at `0x1800cec3b`
- `msvcrt!_wcslwr` at `0x1800cec29`
- `msvcrt!_wcslwr` at `0x1800cec29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cecea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cecea`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800cece0`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800cece0`

## string_xrefs

- `0x1800cecaa`: `ServiceDll`
- `0x1800cec04`: `ImagePath`

## pseudocode

```c
__int64 __fastcall PerfDiagShared::GetServiceImageName(
        LPWSTR lpDst,
        unsigned __int16 *a2,
        struct ATL::CRegKey *a3,
        const unsigned __int16 *a4)
{
  signed int v5; // ebx
  signed int LastError; // eax
  bool v7; // cc
  signed int v8; // eax
  bool v9; // cc
  unsigned int v11; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v12[3]; // [rsp+28h] [rbp-D8h] BYREF
  HKEY hKey[4]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t String[259]; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v15; // [rsp+266h] [rbp+166h]

  if ( !a3 || !lpDst )
    return 2147500035LL;
  memset(hKey, 0, 24);
  v5 = PerfDiagShared::openServiceKey((PerfDiagShared *)hKey, a3, (const unsigned __int16 *)a3);
  if ( v5 < 0 )
  {
LABEL_17:
    ATL::CRegKey::Close((ATL::CRegKey *)hKey);
    return (unsigned int)v5;
  }
  v11 = 260;
  LastError = ATL::CRegKey::QueryStringValue((ATL::CRegKey *)hKey, L"ImagePath", String, &v11);
  v7 = LastError <= 0;
  if ( LastError )
  {
LABEL_14:
    if ( !v7 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v5 = LastError;
    goto LABEL_17;
  }
  v15 = 0;
  _wcslwr(String);
  if ( !wcsstr(String, L"svchost.exe -k ") )
    goto LABEL_12;
  memset(v12, 0, sizeof(v12));
  v8 = ATL::CRegKey::Open((ATL::CRegKey *)v12, hKey[0], L"Parameters");
  v5 = v8;
  v9 = v8 <= 0;
  if ( v8
    || (v11 = 260,
        v8 = ATL::CRegKey::QueryStringValue((ATL::CRegKey *)v12, L"ServiceDll", String, &v11),
        v5 = v8,
        v9 = v8 <= 0,
        v8) )
  {
    if ( !v9 )
      v5 = (unsigned __int16)v8 | 0x80070000;
    ATL::CRegKey::Close((ATL::CRegKey *)v12);
    goto LABEL_17;
  }
  v15 = 0;
  ATL::CRegKey::Close((ATL::CRegKey *)v12);
LABEL_12:
  if ( !ExpandEnvironmentStringsW(String, lpDst, 0x100u) )
  {
    LastError = GetLastError();
    v7 = LastError <= 0;
    goto LABEL_14;
  }
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  return 0;
}

```

## disassembly

```asm
0x1800ceb80  mov     [rsp-8+arg_8], rbx
0x1800ceb85  mov     [rsp-8+arg_18], rdi
0x1800ceb8a  push    rbp
0x1800ceb8b  lea     rbp, [rsp-180h]
0x1800ceb93  sub     rsp, 280h
0x1800ceb9a  mov     rax, cs:__security_cookie
0x1800ceba1  xor     rax, rsp
0x1800ceba4  mov     [rbp+180h+var_10], rax
0x1800cebab  mov     rdi, rcx
0x1800cebae  test    r8, r8
0x1800cebb1  jz      loc_1800CED1A
0x1800cebb7  test    rcx, rcx
0x1800cebba  jz      loc_1800CED1A
0x1800cebc0  mov     rdx, r8; struct ATL::CRegKey *
0x1800cebc3  mov     [rsp+280h+hKey], 0
0x1800cebcc  lea     rcx, [rsp+280h+hKey]; this
0x1800cebd1  mov     [rsp+280h+var_238], 0
0x1800cebda  mov     [rsp+280h+var_230], 0
0x1800cebe3  call    ?openServiceKey@PerfDiagShared@@YAJAEAVCRegKey@ATL@@PEBG@Z; PerfDiagShared::openServiceKey(ATL::CRegKey &,ushort const *)
0x1800cebe8  mov     ebx, eax
0x1800cebea  test    eax, eax
0x1800cebec  js      loc_1800CECFE
0x1800cebf2  lea     r9, [rsp+280h+var_260]; unsigned int *
0x1800cebf7  mov     [rsp+280h+var_260], 104h
0x1800cebff  lea     r8, [rsp+280h+String]; unsigned __int16 *
0x1800cec04  lea     rdx, aImagepath; "ImagePath"
0x1800cec0b  lea     rcx, [rsp+280h+hKey]; this
0x1800cec10  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x1800cec15  test    eax, eax
0x1800cec17  jnz     loc_1800CECF2
0x1800cec1d  lea     rcx, [rsp+280h+String]; String
0x1800cec22  mov     [rbp+180h+var_1A], ax
0x1800cec29  call    cs:__imp__wcslwr
0x1800cec2f  lea     rdx, aSvchostExeK; "svchost.exe -k "
0x1800cec36  lea     rcx, [rsp+280h+String]; Str
0x1800cec3b  call    cs:__imp_wcsstr
0x1800cec41  test    rax, rax
0x1800cec44  jz      loc_1800CECD2
0x1800cec4a  mov     rdx, [rsp+280h+hKey]; hKey
0x1800cec4f  lea     r8, aParameters; "Parameters"
0x1800cec56  lea     rcx, [rsp+280h+var_258]; this
0x1800cec5b  mov     [rsp+280h+var_258], 0
0x1800cec64  mov     [rsp+280h+var_250], 0
0x1800cec6d  mov     [rsp+280h+var_248], 0
0x1800cec76  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800cec7b  mov     ebx, eax
0x1800cec7d  test    eax, eax
0x1800cec7f  jz      short loc_1800CEC98
0x1800cec81  jle     short loc_1800CEC8C
0x1800cec83  movzx   ebx, ax
0x1800cec86  or      ebx, 80070000h
0x1800cec8c  lea     rcx, [rsp+280h+var_258]; this
0x1800cec91  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800cec96  jmp     short loc_1800CECFE
0x1800cec98  lea     r9, [rsp+280h+var_260]; unsigned int *
0x1800cec9d  mov     [rsp+280h+var_260], 104h
0x1800ceca5  lea     r8, [rsp+280h+String]; unsigned __int16 *
0x1800cecaa  lea     rdx, aServicedll; "ServiceDll"
0x1800cecb1  lea     rcx, [rsp+280h+var_258]; this
0x1800cecb6  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x1800cecbb  mov     ebx, eax
0x1800cecbd  test    eax, eax
0x1800cecbf  jnz     short loc_1800CEC81
0x1800cecc1  lea     rcx, [rsp+280h+var_258]; this
0x1800cecc6  mov     [rbp+180h+var_1A], ax
0x1800ceccd  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800cecd2  mov     r8d, 100h; nSize
0x1800cecd8  lea     rcx, [rsp+280h+String]; lpSrc
0x1800cecdd  mov     rdx, rdi; lpDst
0x1800cece0  call    cs:__imp_ExpandEnvironmentStringsW
0x1800cece6  test    eax, eax
0x1800cece8  jnz     short loc_1800CED0C
0x1800cecea  call    cs:__imp_GetLastError
0x1800cecf0  test    eax, eax
0x1800cecf2  jle     short loc_1800CECFC
0x1800cecf4  movzx   eax, ax
0x1800cecf7  or      eax, 80070000h
0x1800cecfc  mov     ebx, eax
0x1800cecfe  lea     rcx, [rsp+280h+hKey]; this
0x1800ced03  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800ced08  mov     eax, ebx
0x1800ced0a  jmp     short loc_1800CED1F
0x1800ced0c  lea     rcx, [rsp+280h+hKey]; this
0x1800ced11  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800ced16  xor     eax, eax
0x1800ced18  jmp     short loc_1800CED1F
0x1800ced1a  mov     eax, 80004003h
0x1800ced1f  mov     rcx, [rbp+180h+var_10]
0x1800ced26  xor     rcx, rsp; StackCookie
0x1800ced29  call    __security_check_cookie
0x1800ced2e  lea     r11, [rsp+280h+var_s0]
0x1800ced36  mov     rbx, [r11+18h]
0x1800ced3a  mov     rdi, [r11+28h]
0x1800ced3e  mov     rsp, r11
0x1800ced41  pop     rbp
0x1800ced42  retn
```
