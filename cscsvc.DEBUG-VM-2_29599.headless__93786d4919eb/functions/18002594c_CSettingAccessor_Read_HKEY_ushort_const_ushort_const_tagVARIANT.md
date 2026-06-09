# CSettingAccessor::Read(HKEY__ *,ushort const *,ushort const *,tagVARIANT *)

- ea: `0x18002594c`
- end: `0x180025abb`
- name: `?Read@CSettingAccessor@@QEAAJPEAUHKEY__@@PEBG1PEAUtagVARIANT@@@Z`
- size: `367`
- prototype: `__int64 __usercall@<rax>(CSettingAccessor *__hidden this@<rcx>, HKEY@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, struct tagVARIANT *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001e5b4`
- `0x180022c60`
- `0x180025b44`

## callees

- `0x18002594c`
- `0x180025ff4`
- `0x180032bd8`
- `0x18005ce10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800259e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800259e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180025991`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180025991`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025a02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025a45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025a02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025a45`

## pseudocode

```c
__int64 __fastcall CSettingAccessor::Read(
        CSettingAccessor *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct tagVARIANT *a5)
{
  LSTATUS v9; // eax
  signed int v10; // ebx
  HKEY v11; // rdi
  int v12; // ebp
  LSTATUS v13; // eax
  int OneValue; // eax
  const wchar_t *v15; // r9
  HKEY hKey; // [rsp+40h] [rbp-38h] BYREF
  HKEY phkResult; // [rsp+88h] [rbp+10h] BYREF

  phkResult = 0;
  if ( a2 == HKEY_CURRENT_USER )
  {
    hKey = 0;
    v9 = RegOpenCurrentUser(0x20019u, &hKey);
    v10 = v9;
    if ( v9 )
    {
      v12 = 0;
      v11 = HKEY_CURRENT_USER;
      if ( v9 > 0 )
        v10 = (unsigned __int16)v9 | 0x80070000;
    }
    else
    {
      v11 = hKey;
      v12 = 1;
    }
  }
  else
  {
    v10 = 0;
    v11 = a2;
    v12 = 0;
  }
  if ( v10 < 0 )
    goto LABEL_18;
  v13 = RegOpenKeyExW(v11, a3, 0, 0x20019u, &phkResult);
  v10 = v13;
  if ( v13 > 0 )
    v10 = (unsigned __int16)v13 | 0x80070000;
  if ( v12 )
    RegCloseKey(v11);
  if ( v10 < 0 )
  {
LABEL_18:
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
    {
      v15 = L"HKCU";
      if ( !a4 )
        a4 = a3;
      if ( a2 != HKEY_CURRENT_USER )
        v15 = L"HKLM";
      WPP_SF_SSDS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)a3,
        (_DWORD)v15,
        (__int64)a3,
        v10,
        (__int64)a4);
    }
  }
  else
  {
    if ( a4 )
      OneValue = CSettingAccessor::_ReadOneValue(this, phkResult, a4, a5);
    else
      OneValue = CSettingAccessor::_ReadMultipleValues(this, phkResult, a5);
    v10 = OneValue;
    RegCloseKey(phkResult);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002594c  mov     rax, rsp
0x18002594f  mov     [rax+8], rbx
0x180025953  mov     [rax+18h], rbp
0x180025957  push    rsi
0x180025958  push    rdi
0x180025959  push    r12
0x18002595b  push    r14
0x18002595d  push    r15
0x18002595f  sub     rsp, 50h
0x180025963  mov     qword ptr [rax+10h], 0
0x18002596b  mov     rsi, r9
0x18002596e  mov     r12, r8
0x180025971  mov     r14, rdx
0x180025974  mov     r15, rcx
0x180025977  cmp     rdx, 0FFFFFFFF80000001h
0x18002597e  jnz     short loc_1800259BB
0x180025980  lea     rdx, [rax-38h]; phkResult
0x180025984  mov     qword ptr [rax-38h], 0
0x18002598c  mov     ecx, 20019h; samDesired
0x180025991  call    cs:__imp_RegOpenCurrentUser
0x180025997  mov     ebx, eax
0x180025999  test    eax, eax
0x18002599b  jnz     short loc_1800259A7
0x18002599d  mov     rdi, [rsp+78h+hKey]
0x1800259a2  lea     ebp, [rax+1]
0x1800259a5  jmp     short loc_1800259C2
0x1800259a7  xor     ebp, ebp
0x1800259a9  mov     rdi, r14
0x1800259ac  test    eax, eax
0x1800259ae  jle     short loc_1800259C2
0x1800259b0  movzx   ebx, ax
0x1800259b3  or      ebx, 80070000h
0x1800259b9  jmp     short loc_1800259C2
0x1800259bb  xor     ebx, ebx
0x1800259bd  mov     rdi, r14
0x1800259c0  xor     ebp, ebp
0x1800259c2  test    ebx, ebx
0x1800259c4  js      loc_180025A4D
0x1800259ca  lea     rax, [rsp+78h+arg_8]
0x1800259d2  mov     r9d, 20019h; samDesired
0x1800259d8  xor     r8d, r8d; ulOptions
0x1800259db  mov     [rsp+78h+phkResult], rax; phkResult
0x1800259e0  mov     rdx, r12; lpSubKey
0x1800259e3  mov     rcx, rdi; hKey
0x1800259e6  call    cs:__imp_RegOpenKeyExW
0x1800259ec  mov     ebx, eax
0x1800259ee  test    eax, eax
0x1800259f0  jle     short loc_1800259FB
0x1800259f2  movzx   ebx, ax
0x1800259f5  or      ebx, 80070000h
0x1800259fb  test    ebp, ebp
0x1800259fd  jz      short loc_180025A08
0x1800259ff  mov     rcx, rdi; hKey
0x180025a02  call    cs:__imp_RegCloseKey
0x180025a08  test    ebx, ebx
0x180025a0a  js      short loc_180025A4D
0x180025a0c  mov     rdx, [rsp+78h+arg_8]; HKEY
0x180025a14  mov     rcx, r15; this
0x180025a17  test    rsi, rsi
0x180025a1a  jnz     short loc_180025A2B
0x180025a1c  mov     r8, [rsp+78h+arg_20]; struct tagVARIANT *
0x180025a24  call    ?_ReadMultipleValues@CSettingAccessor@@AEAAJPEAUHKEY__@@PEAUtagVARIANT@@@Z; CSettingAccessor::_ReadMultipleValues(HKEY__ *,tagVARIANT *)
0x180025a29  jmp     short loc_180025A3B
0x180025a2b  mov     r9, [rsp+78h+arg_20]; struct tagVARIANT *
0x180025a33  mov     r8, rsi; unsigned __int16 *
0x180025a36  call    ?_ReadOneValue@CSettingAccessor@@AEAAJPEAUHKEY__@@PEBGPEAUtagVARIANT@@@Z; CSettingAccessor::_ReadOneValue(HKEY__ *,ushort const *,tagVARIANT *)
0x180025a3b  mov     rcx, [rsp+78h+arg_8]; hKey
0x180025a43  mov     ebx, eax
0x180025a45  call    cs:__imp_RegCloseKey
0x180025a4b  jmp     short loc_180025AA0
0x180025a4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180025a54  lea     rax, WPP_GLOBAL_Control
0x180025a5b  cmp     rcx, rax
0x180025a5e  jz      short loc_180025AA0
0x180025a60  test    dword ptr [rcx+1Ch], 10000h
0x180025a67  jz      short loc_180025AA0
0x180025a69  mov     rcx, [rcx+10h]
0x180025a6d  lea     rax, aHklm; "HKLM"
0x180025a74  test    rsi, rsi
0x180025a77  lea     r9, aHkcu; "HKCU"
0x180025a7e  cmovz   rsi, r12
0x180025a82  cmp     r14, 0FFFFFFFF80000001h
0x180025a89  mov     [rsp+78h+var_48], rsi
0x180025a8e  cmovnz  r9, rax
0x180025a92  mov     [rsp+78h+var_50], ebx
0x180025a96  mov     [rsp+78h+phkResult], r12
0x180025a9b  call    WPP_SF_SSDS
0x180025aa0  lea     r11, [rsp+78h+var_28]
0x180025aa5  mov     eax, ebx
0x180025aa7  mov     rbx, [r11+30h]
0x180025aab  mov     rbp, [r11+40h]
0x180025aaf  mov     rsp, r11
0x180025ab2  pop     r15
0x180025ab4  pop     r14
0x180025ab6  pop     r12
0x180025ab8  pop     rdi
0x180025ab9  pop     rsi
0x180025aba  retn
```
