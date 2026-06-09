# CRegKey::SetValue(ushort const *,ushort const *,ulong)

- ea: `0x180003e88`
- end: `0x180003f0a`
- name: `?SetValue@CRegKey@@QEBAXPEBG0K@Z`
- size: `130`
- prototype: `void __fastcall(HKEY *this, const unsigned __int16 *, const BYTE *lpData, DWORD cbData)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180003c8c`

## callees

- `0x180003e88`
- `0x18000a360`
- `0x18000ab3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003ea4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003ea4`

## pseudocode

```c
void __fastcall CRegKey::SetValue(HKEY *this, const unsigned __int16 *a2, const BYTE *lpData, DWORD cbData)
{
  int v4; // ebx
  int pExceptionObject; // [rsp+40h] [rbp+8h] BYREF

  v4 = RegSetValueExW(*this, a2, 0, 1u, lpData, cbData);
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_1eba886745fe349fd97ae921e3b476bf_Traceguids,
        (unsigned int)v4);
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    pExceptionObject = v4;
    throw (CExcept *)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x180003e88  push    rbx
0x180003e8a  sub     rsp, 30h
0x180003e8e  mov     rcx, [rcx]; hKey
0x180003e91  mov     [rsp+38h+cbData], r9d; cbData
0x180003e96  mov     r9d, 1; dwType
0x180003e9c  mov     [rsp+38h+lpData], r8; lpData
0x180003ea1  xor     r8d, r8d; Reserved
0x180003ea4  call    cs:__imp_RegSetValueExW
0x180003eaa  mov     ebx, eax
0x180003eac  test    eax, eax
0x180003eae  jz      short loc_180003F04
0x180003eb0  mov     rcx, cs:WPP_GLOBAL_Control
0x180003eb7  lea     rax, WPP_GLOBAL_Control
0x180003ebe  cmp     rcx, rax
0x180003ec1  jz      short loc_180003EE1
0x180003ec3  test    byte ptr [rcx+1Ch], 2
0x180003ec7  jz      short loc_180003EE1
0x180003ec9  mov     rcx, [rcx+10h]
0x180003ecd  lea     r8, WPP_1eba886745fe349fd97ae921e3b476bf_Traceguids
0x180003ed4  mov     edx, 0Ch
0x180003ed9  mov     r9d, ebx
0x180003edc  call    WPP_SF_D
0x180003ee1  test    ebx, ebx
0x180003ee3  jle     short loc_180003EEE
0x180003ee5  movzx   ebx, bx
0x180003ee8  or      ebx, 80070000h
0x180003eee  lea     rdx, _TI1?AVCExcept@@; pThrowInfo
0x180003ef5  mov     [rsp+38h+pExceptionObject], ebx
0x180003ef9  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180003efe  call    _CxxThrowException_0
0x180003f04  add     rsp, 30h
0x180003f08  pop     rbx
0x180003f09  retn
```
