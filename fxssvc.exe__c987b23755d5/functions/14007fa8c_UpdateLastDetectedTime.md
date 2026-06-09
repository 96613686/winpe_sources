# UpdateLastDetectedTime

- ea: `0x14007fa8c`
- end: `0x14007fbd0`
- name: `UpdateLastDetectedTime`
- size: `324`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14007d9e4`

## callees

- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x1400708c4`
- `0x1400709a0`
- `0x14007fa8c`
- `0x1400818b0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14007fba3`
- `ADVAPI32!RegCloseKey` at `0x14007fba3`
- `KERNEL32!SetLastError` at `0x14007fb58`
- `KERNEL32!SetLastError` at `0x14007fb58`

## string_xrefs

- `0x14007faee`: `Software\Microsoft\Fax\Devices Cache`

## pseudocode

```c
__int64 __fastcall UpdateLastDetectedTime(int a1, __int64 a2)
{
  int v3; // eax
  DWORD v4; // ebx
  unsigned int v6; // ebx
  HKEY v7; // rax
  HKEY v8; // rdi
  int v9; // [rsp+20h] [rbp-248h]
  BYTE v10[16]; // [rsp+30h] [rbp-238h] BYREF
  unsigned __int16 v11[264]; // [rsp+40h] [rbp-228h] BYREF

  *(_QWORD *)v10 = a2;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 168, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids);
  }
  v9 = a1;
  v3 = StringCchPrintfW(v11, 0x104u, L"%s\\%08lx", L"Software\\Microsoft\\Fax\\Devices Cache", v9);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v6 = 0;
    v7 = OpenRegistryKey(HKEY_LOCAL_MACHINE, v11, 0, 0x20006u);
    v8 = v7;
    if ( v7 )
    {
      v6 = SetRegistryBinary(v7, L"LastDetected", v10, 8u);
      RegCloseKey(v8);
    }
    return v6;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        169,
        &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids,
        (unsigned int)v3);
    }
    if ( (v4 & 0x1FFF0000) == 0x70000 )
      v4 = (unsigned __int16)v4;
    SetLastError(v4);
    return 0;
  }
}

```

## disassembly

```asm
0x14007fa8c  mov     [rsp+arg_10], rbx
0x14007fa91  mov     [rsp+arg_18], rsi
0x14007fa96  push    rdi
0x14007fa97  sub     rsp, 260h
0x14007fa9e  mov     rax, cs:__security_cookie
0x14007faa5  xor     rax, rsp
0x14007faa8  mov     [rsp+268h+var_18], rax
0x14007fab0  mov     ebx, ecx
0x14007fab2  mov     qword ptr [rsp+268h+var_238], rdx
0x14007fab7  mov     rcx, cs:WPP_GLOBAL_Control
0x14007fabe  lea     rsi, WPP_GLOBAL_Control
0x14007fac5  mov     dil, 2
0x14007fac8  cmp     rcx, rsi
0x14007facb  jz      short loc_14007FAEE
0x14007facd  test    [rcx+1Ch], dil
0x14007fad1  jz      short loc_14007FAEE
0x14007fad3  cmp     byte ptr [rcx+19h], 5
0x14007fad7  jb      short loc_14007FAEE
0x14007fad9  mov     rcx, [rcx+10h]
0x14007fadd  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007fae4  mov     edx, 0A8h
0x14007fae9  call    WPP_SF_
0x14007faee  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Fax\\Devices Cache"
0x14007faf5  mov     [rsp+268h+var_248], ebx
0x14007faf9  lea     r8, aS08lx; "%s\\%08lx"
0x14007fb00  mov     edx, 104h; unsigned __int64
0x14007fb05  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x14007fb0a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14007fb0f  mov     ebx, eax
0x14007fb11  test    eax, eax
0x14007fb13  jns     short loc_14007FB62
0x14007fb15  mov     rcx, cs:WPP_GLOBAL_Control
0x14007fb1c  cmp     rcx, rsi
0x14007fb1f  jz      short loc_14007FB45
0x14007fb21  test    [rcx+1Ch], dil
0x14007fb25  jz      short loc_14007FB45
0x14007fb27  cmp     [rcx+19h], dil
0x14007fb2b  jb      short loc_14007FB45
0x14007fb2d  mov     rcx, [rcx+10h]
0x14007fb31  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007fb38  mov     edx, 0A9h
0x14007fb3d  mov     r9d, eax
0x14007fb40  call    WPP_SF_d
0x14007fb45  mov     eax, ebx
0x14007fb47  and     eax, 1FFF0000h
0x14007fb4c  cmp     eax, 70000h
0x14007fb51  jnz     short loc_14007FB56
0x14007fb53  movzx   ebx, bx
0x14007fb56  mov     ecx, ebx; dwErrCode
0x14007fb58  call    cs:__imp_SetLastError
0x14007fb5e  xor     eax, eax
0x14007fb60  jmp     short loc_14007FBAB
0x14007fb62  mov     r9d, 20006h
0x14007fb68  lea     rdx, [rsp+268h+var_228]
0x14007fb6d  xor     r8d, r8d
0x14007fb70  mov     rcx, 0FFFFFFFF80000002h
0x14007fb77  xor     ebx, ebx
0x14007fb79  call    OpenRegistryKey
0x14007fb7e  mov     rdi, rax
0x14007fb81  test    rax, rax
0x14007fb84  jz      short loc_14007FBA9
0x14007fb86  lea     r9d, [rbx+8]
0x14007fb8a  mov     rcx, rax
0x14007fb8d  lea     r8, [rsp+268h+var_238]
0x14007fb92  lea     rdx, aLastdetected; "LastDetected"
0x14007fb99  call    SetRegistryBinary
0x14007fb9e  mov     rcx, rdi; hKey
0x14007fba1  mov     ebx, eax
0x14007fba3  call    cs:__imp_RegCloseKey
0x14007fba9  mov     eax, ebx
0x14007fbab  mov     rcx, [rsp+268h+var_18]
0x14007fbb3  xor     rcx, rsp; StackCookie
0x14007fbb6  call    __security_check_cookie
0x14007fbbb  lea     r11, [rsp+268h+var_8]
0x14007fbc3  mov     rbx, [r11+20h]
0x14007fbc7  mov     rsi, [r11+28h]
0x14007fbcb  mov     rsp, r11
0x14007fbce  pop     rdi
0x14007fbcf  retn
```
