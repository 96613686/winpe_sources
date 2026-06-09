# NgscbDeleteDWordConfig(ushort const *)

- ea: `0x180053db4`
- end: `0x180053ed0`
- name: `?NgscbDeleteDWordConfig@@YAJPEBG@Z`
- size: `284`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180052134`

## callees

- `0x180053db4`
- `0x180053ed8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053eb6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053eb6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180053e08`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180053e08`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180053e61`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180053e61`

## pseudocode

```c
__int64 __fastcall NgscbDeleteDWordConfig(const unsigned __int16 *a1)
{
  LSTATUS v1; // eax
  __int64 v2; // r8
  unsigned int v3; // ebx
  LSTATUS v4; // eax
  __int64 v5; // r8
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  hKey = 0;
  v1 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\BitLocker", 0, 0, 0, 2u, 0, &hKey, 0);
  v3 = v1;
  if ( v1 > 0 )
    v3 = (unsigned __int16)v1 | 0x80070000;
  if ( !v3 )
    goto LABEL_8;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 308, v2, v3);
  if ( (v3 & 0x80000000) == 0 )
  {
LABEL_8:
    v4 = RegDeleteValueW(hKey, L"ExcludedPcrsBitmap");
    v3 = v4;
    if ( v4 == 2 )
    {
      v3 = 0;
    }
    else if ( v4 > 0 )
    {
      v3 = (unsigned __int16)v4 | 0x80070000;
    }
    if ( v3
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 309, v5, v3);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x180053db4  mov     r11, rsp
0x180053db7  mov     [r11+10h], rbx
0x180053dbb  mov     [r11+8], rcx
0x180053dbf  push    rsi
0x180053dc0  sub     rsp, 50h
0x180053dc4  mov     qword ptr [r11-18h], 0
0x180053dcc  lea     rax, [r11+8]
0x180053dd0  mov     [r11-20h], rax
0x180053dd4  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\Bit"...
0x180053ddb  mov     qword ptr [r11-28h], 0
0x180053de3  xor     r9d, r9d; lpClass
0x180053de6  mov     [rsp+58h+samDesired], 2; samDesired
0x180053dee  xor     r8d, r8d; Reserved
0x180053df1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180053df8  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180053e00  mov     qword ptr [r11+8], 0
0x180053e08  call    cs:__imp_RegCreateKeyExW
0x180053e0f  nop     dword ptr [rax+rax+00h]
0x180053e14  mov     ebx, eax
0x180053e16  test    eax, eax
0x180053e18  jle     short loc_180053E23
0x180053e1a  movzx   ebx, ax
0x180053e1d  or      ebx, 80070000h
0x180053e23  lea     rsi, WPP_GLOBAL_Control
0x180053e2a  test    ebx, ebx
0x180053e2c  jz      short loc_180053E55
0x180053e2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180053e35  cmp     rcx, rsi
0x180053e38  jz      short loc_180053E51
0x180053e3a  test    byte ptr [rcx+1Ch], 40h
0x180053e3e  jz      short loc_180053E51
0x180053e40  mov     rcx, [rcx+10h]
0x180053e44  mov     edx, 134h
0x180053e49  mov     r9d, ebx
0x180053e4c  call    WPP_SF_d
0x180053e51  test    ebx, ebx
0x180053e53  js      short loc_180053EAC
0x180053e55  mov     rcx, [rsp+58h+hKey]; hKey
0x180053e5a  lea     rdx, aExcludedpcrsbi; "ExcludedPcrsBitmap"
0x180053e61  call    cs:__imp_RegDeleteValueW
0x180053e68  nop     dword ptr [rax+rax+00h]
0x180053e6d  mov     ebx, eax
0x180053e6f  cmp     eax, 2
0x180053e72  jnz     short loc_180053E78
0x180053e74  xor     ebx, ebx
0x180053e76  jmp     short loc_180053E85
0x180053e78  test    eax, eax
0x180053e7a  jle     short loc_180053E85
0x180053e7c  movzx   ebx, ax
0x180053e7f  or      ebx, 80070000h
0x180053e85  test    ebx, ebx
0x180053e87  jz      short loc_180053EAC
0x180053e89  mov     rcx, cs:WPP_GLOBAL_Control
0x180053e90  cmp     rcx, rsi
0x180053e93  jz      short loc_180053EAC
0x180053e95  test    byte ptr [rcx+1Ch], 40h
0x180053e99  jz      short loc_180053EAC
0x180053e9b  mov     rcx, [rcx+10h]
0x180053e9f  mov     edx, 135h
0x180053ea4  mov     r9d, ebx
0x180053ea7  call    WPP_SF_d
0x180053eac  mov     rcx, [rsp+58h+hKey]; hKey
0x180053eb1  test    rcx, rcx
0x180053eb4  jz      short loc_180053EC2
0x180053eb6  call    cs:__imp_RegCloseKey
0x180053ebd  nop     dword ptr [rax+rax+00h]
0x180053ec2  mov     eax, ebx
0x180053ec4  mov     rbx, [rsp+58h+arg_8]
0x180053ec9  add     rsp, 50h
0x180053ecd  pop     rsi
0x180053ece  retn
```
