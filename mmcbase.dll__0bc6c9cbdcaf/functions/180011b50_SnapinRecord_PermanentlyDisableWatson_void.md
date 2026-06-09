# SnapinRecord::PermanentlyDisableWatson(void)

- ea: `0x180011b50`
- end: `0x180011d37`
- name: `?PermanentlyDisableWatson@SnapinRecord@@QEAAJXZ`
- size: `487`
- prototype: `__int64 __fastcall(SnapinRecord *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e04c`

## callees

- `0x18000715c`
- `0x180007310`
- `0x18000cfbc`
- `0x180011b50`
- `0x1800121b4`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011c39`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011c39`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011d0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011d0c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011cac`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011cac`

## pseudocode

```c
__int64 __fastcall SnapinRecord::PermanentlyDisableWatson(SnapinRecord *this)
{
  __int64 v2; // rax
  signed int v3; // ebx
  int v4; // eax
  int v5; // edx
  int v6; // r9d
  __int64 v7; // rcx
  LPCWSTR v8; // rsi
  LSTATUS v9; // eax
  LSTATUS v10; // edi
  void **v12; // [rsp+30h] [rbp-20h] BYREF
  LPCWSTR lpSubKey; // [rsp+38h] [rbp-18h]
  __int64 v14; // [rsp+40h] [rbp-10h]
  int v15; // [rsp+48h] [rbp-8h]
  HKEY hKey; // [rsp+70h] [rbp+20h] BYREF

  v12 = &CStr::`vftable';
  lpSubKey = (LPCWSTR)&CStr::s_rgwchEmptyStringBuffer;
  v14 = 0;
  v15 = 0;
  hKey = 0;
  v2 = (*(__int64 (__fastcall **)(SnapinRecord *))(*(_QWORD *)this + 8LL))(this);
  v3 = CStr::Format((CStr *)&v12, L"%s\\%s", L"Software\\Microsoft\\MMC\\SnapIns", v2);
  if ( v3 >= 0 )
  {
    v8 = lpSubKey;
    v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20006u, &hKey);
    if ( v9 )
    {
      if ( v9 > 0 )
        v3 = (unsigned __int16)v9 | 0x80070000;
      else
        v3 = v9;
      v7 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
        goto LABEL_20;
      v5 = 99;
      v6 = (int)v8;
      goto LABEL_5;
    }
    v10 = RegSetValueExW(hKey, L"DisableWatson", 0, 1u, Data, 0x12u);
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(unsigned __int8 *)(WPP_GLOBAL_Control + 25LL) >= v10 )
      WPP_SF_SS(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        100,
        (unsigned int)WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids,
        (unsigned int)L"DisableWatson",
        (__int64)v8);
    if ( v10 )
    {
      if ( v10 > 0 )
        v3 = (unsigned __int16)v10 | 0x80070000;
      else
        v3 = v10;
    }
  }
  else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v4 = (*(__int64 (__fastcall **)(SnapinRecord *))(*(_QWORD *)this + 8LL))(this);
    v5 = 98;
    v6 = v4;
    v7 = WPP_GLOBAL_Control;
LABEL_5:
    WPP_SF_Sd(*(_QWORD *)(v7 + 16), v5, (unsigned int)WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids, v6, v3);
  }
LABEL_20:
  if ( hKey )
    RegCloseKey(hKey);
  v12 = &CStr::`vftable';
  CStr::Empty((CStr *)&v12);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180011b50  mov     [rsp-18h+arg_8], rbx
0x180011b55  mov     [rsp-18h+arg_10], rsi
0x180011b5a  push    rbp
0x180011b5b  push    rdi
0x180011b5c  push    r12
0x180011b5e  mov     rbp, rsp
0x180011b61  sub     rsp, 50h
0x180011b65  mov     rdi, rcx
0x180011b68  lea     r12, ??_7CStr@@6B@; const CStr::`vftable'
0x180011b6f  mov     [rbp+var_20], r12
0x180011b73  lea     rax, ?s_rgwchEmptyStringBuffer@CStr@@0PAGA; ushort near * CStr::s_rgwchEmptyStringBuffer
0x180011b7a  mov     [rbp+lpSubKey], rax
0x180011b7e  mov     [rbp+var_10], 0
0x180011b86  mov     [rbp+var_8], 0
0x180011b8d  mov     [rbp+hKey], 0
0x180011b95  mov     rax, [rcx]
0x180011b98  mov     rax, [rax+8]
0x180011b9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ba1  mov     r9, rax
0x180011ba4  lea     r8, aSoftwareMicros; "Software\\Microsoft\\MMC\\SnapIns"
0x180011bab  lea     rdx, aSS; "%s\\%s"
0x180011bb2  lea     rcx, [rbp+var_20]; this
0x180011bb6  call    ?Format@CStr@@QEAAJPEBGZZ; CStr::Format(ushort const *,...)
0x180011bbb  mov     ebx, eax
0x180011bbd  test    eax, eax
0x180011bbf  jns     short loc_180011C19
0x180011bc1  lea     rax, WPP_GLOBAL_Control
0x180011bc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180011bcf  cmp     rcx, rax
0x180011bd2  jz      loc_180011D03
0x180011bd8  cmp     byte ptr [rcx+19h], 2
0x180011bdc  jb      loc_180011D03
0x180011be2  mov     rax, [rdi]
0x180011be5  mov     rcx, rdi
0x180011be8  mov     rax, [rax+8]
0x180011bec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011bf1  mov     edx, 62h ; 'b'
0x180011bf6  mov     r9, rax
0x180011bf9  mov     rcx, cs:WPP_GLOBAL_Control
0x180011c00  lea     r8, WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids
0x180011c07  mov     dword ptr [rsp+50h+phkResult], ebx
0x180011c0b  mov     rcx, [rcx+10h]
0x180011c0f  call    WPP_SF_Sd
0x180011c14  jmp     loc_180011D03
0x180011c19  mov     rsi, [rbp+lpSubKey]
0x180011c1d  lea     rax, [rbp+hKey]
0x180011c21  mov     [rsp+50h+phkResult], rax; phkResult
0x180011c26  mov     r9d, 20006h; samDesired
0x180011c2c  xor     r8d, r8d; ulOptions
0x180011c2f  mov     rdx, rsi; lpSubKey
0x180011c32  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011c39  call    cs:__imp_RegOpenKeyExW
0x180011c3f  test    eax, eax
0x180011c41  jz      short loc_180011C84
0x180011c43  jg      short loc_180011C49
0x180011c45  mov     ebx, eax
0x180011c47  jmp     short loc_180011C52
0x180011c49  movzx   ebx, ax
0x180011c4c  or      ebx, 80070000h
0x180011c52  test    ebx, ebx
0x180011c54  jns     short loc_180011C84
0x180011c56  lea     rax, WPP_GLOBAL_Control
0x180011c5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180011c64  cmp     rcx, rax
0x180011c67  jz      loc_180011D03
0x180011c6d  cmp     byte ptr [rcx+19h], 2
0x180011c71  jb      loc_180011D03
0x180011c77  mov     edx, 63h ; 'c'
0x180011c7c  mov     r9, rsi
0x180011c7f  jmp     loc_180011C00
0x180011c84  mov     [rsp+50h+cbData], 12h; cbData
0x180011c8c  lea     rax, Data; "Disabled"
0x180011c93  mov     [rsp+50h+phkResult], rax; lpData
0x180011c98  mov     r9d, 1; dwType
0x180011c9e  xor     r8d, r8d; Reserved
0x180011ca1  lea     rdx, ValueName; "DisableWatson"
0x180011ca8  mov     rcx, [rbp+hKey]; hKey
0x180011cac  call    cs:__imp_RegSetValueExW
0x180011cb2  mov     edi, eax
0x180011cb4  lea     rax, WPP_GLOBAL_Control
0x180011cbb  mov     rcx, cs:WPP_GLOBAL_Control
0x180011cc2  cmp     rcx, rax
0x180011cc5  jz      short loc_180011CCF
0x180011cc7  movzx   edx, byte ptr [rcx+19h]
0x180011ccb  cmp     edx, edi
0x180011ccd  jl      short loc_180011CF0
0x180011ccf  mov     edx, 64h ; 'd'
0x180011cd4  mov     [rsp+50h+phkResult], rsi
0x180011cd9  lea     r9, ValueName; "DisableWatson"
0x180011ce0  lea     r8, WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids
0x180011ce7  mov     rcx, [rcx+10h]
0x180011ceb  call    WPP_SF_SS
0x180011cf0  test    edi, edi
0x180011cf2  jz      short loc_180011D03
0x180011cf4  jg      short loc_180011CFA
0x180011cf6  mov     ebx, edi
0x180011cf8  jmp     short loc_180011D03
0x180011cfa  movzx   ebx, di
0x180011cfd  or      ebx, 80070000h
0x180011d03  mov     rcx, [rbp+hKey]; hKey
0x180011d07  test    rcx, rcx
0x180011d0a  jz      short loc_180011D13
0x180011d0c  call    cs:__imp_RegCloseKey
0x180011d12  nop
0x180011d13  mov     [rbp+var_20], r12
0x180011d17  lea     rcx, [rbp+var_20]; this
0x180011d1b  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x180011d20  mov     eax, ebx
0x180011d22  lea     r11, [rsp+50h+var_s0]
0x180011d27  mov     rbx, [r11+28h]
0x180011d2b  mov     rsi, [r11+30h]
0x180011d2f  mov     rsp, r11
0x180011d32  pop     r12
0x180011d34  pop     rdi
0x180011d35  pop     rbp
0x180011d36  retn
```
