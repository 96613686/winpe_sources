# RtlOsDeploymentState

- ea: `0x180148a90`
- end: `0x180148bd8`
- name: `RtlOsDeploymentState`
- size: `328`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800c4700`
- `0x180148a90`
- `0x18015ecc0`
- `0x18015ed20`
- `0x18015edc0`
- `0x180162810`

## string_xrefs

- `0x180148b3c`: `Compact`
- `0x180148ae8`: `\Registry\Machine\System\Setup`

## pseudocode

```c
__int64 RtlOsDeploymentState()
{
  unsigned int v0; // ebx
  HANDLE Handle; // [rsp+30h] [rbp-88h] BYREF
  int v3; // [rsp+38h] [rbp-80h] BYREF
  _DWORD v4[2]; // [rsp+40h] [rbp-78h] BYREF
  __int64 v5; // [rsp+48h] [rbp-70h]
  UNICODE_STRING *v6; // [rsp+50h] [rbp-68h]
  int v7; // [rsp+58h] [rbp-60h]
  int v8; // [rsp+5Ch] [rbp-5Ch]
  __int128 v9; // [rsp+60h] [rbp-58h]
  UNICODE_STRING v10; // [rsp+70h] [rbp-48h] BYREF
  UNICODE_STRING DestinationString; // [rsp+80h] [rbp-38h] BYREF
  _BYTE v12[4]; // [rsp+90h] [rbp-28h] BYREF
  int v13; // [rsp+94h] [rbp-24h]
  int v14; // [rsp+98h] [rbp-20h]
  int v15; // [rsp+9Ch] [rbp-1Ch]

  Handle = 0;
  v0 = 1;
  v3 = 0;
  v4[1] = 0;
  v8 = 0;
  v10 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&v10, L"\\Registry\\Machine\\System\\Setup");
  v4[0] = 48;
  v5 = 0;
  v7 = 576;
  v6 = &v10;
  v9 = 0;
  if ( (int)NtOpenKey(&Handle, 131097, v4) >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"Compact");
    if ( (int)NtQueryValueKey(Handle, &DestinationString, 2, v12, 20, &v3) >= 0 && v13 == 4 && v14 == 4 && v15 )
      v0 = 2;
  }
  if ( Handle )
    NtClose(Handle);
  return v0;
}

```

## disassembly

```asm
0x180148a90  mov     r11, rsp
0x180148a93  mov     [r11+8], rbx
0x180148a97  push    rsi
0x180148a98  sub     rsp, 0B0h
0x180148a9f  mov     rax, cs:__security_cookie
0x180148aa6  xor     rax, rsp
0x180148aa9  mov     [rsp+0B8h+var_10], rax
0x180148ab1  mov     [rsp+0B8h+Handle], 0
0x180148aba  mov     ebx, 1
0x180148abf  mov     [rsp+0B8h+var_80], 0
0x180148ac7  xor     eax, eax
0x180148ac9  xorps   xmm0, xmm0
0x180148acc  movups  [rsp+0B8h+var_78], xmm0
0x180148ad1  movups  [rsp+0B8h+var_68], xmm0
0x180148ad6  movups  [rsp+0B8h+var_68+0Ch], xmm0
0x180148adb  movups  [rsp+0B8h+var_48], xmm0
0x180148ae0  xorps   xmm1, xmm1
0x180148ae3  movups  xmmword ptr [r11-38h], xmm1
0x180148ae8  lea     rdx, aRegistryMachin_14; "\\Registry\\Machine\\System\\Setup"
0x180148aef  lea     rcx, [r11-48h]; DestinationString
0x180148af3  call    RtlInitUnicodeString
0x180148af8  mov     dword ptr [rsp+0B8h+var_78], 30h ; '0'
0x180148b00  mov     qword ptr [rsp+0B8h+var_78+8], 0
0x180148b09  mov     dword ptr [rsp+0B8h+var_68+8], 240h
0x180148b11  lea     rax, [rsp+0B8h+var_48]
0x180148b16  mov     qword ptr [rsp+0B8h+var_68], rax
0x180148b1b  xorps   xmm0, xmm0
0x180148b1e  movdqu  [rsp+0B8h+var_58], xmm0
0x180148b24  lea     r8, [rsp+0B8h+var_78]
0x180148b29  mov     edx, 20019h
0x180148b2e  lea     rcx, [rsp+0B8h+Handle]
0x180148b33  call    NtOpenKey
0x180148b38  test    eax, eax
0x180148b3a  js      short loc_180148BA5
0x180148b3c  lea     rdx, aCompact; "Compact"
0x180148b43  lea     rcx, [rsp+0B8h+DestinationString]; DestinationString
0x180148b4b  call    RtlInitUnicodeString
0x180148b50  lea     rax, [rsp+0B8h+var_80]
0x180148b55  mov     [rsp+0B8h+var_90], rax
0x180148b5a  mov     [rsp+0B8h+var_98], 14h
0x180148b62  lea     r9, [rsp+0B8h+var_28]
0x180148b6a  lea     esi, [rbx+1]
0x180148b6d  mov     r8d, esi
0x180148b70  lea     rdx, [rsp+0B8h+DestinationString]
0x180148b78  mov     rcx, [rsp+0B8h+Handle]
0x180148b7d  call    NtQueryValueKey
0x180148b82  test    eax, eax
0x180148b84  js      short loc_180148BA5
0x180148b86  cmp     [rsp+0B8h+var_24], 4
0x180148b8e  jnz     short loc_180148BA5
0x180148b90  cmp     [rsp+0B8h+var_20], 4
0x180148b98  jnz     short loc_180148BA5
0x180148b9a  cmp     [rsp+0B8h+var_1C], 0
0x180148ba2  cmovnz  ebx, esi
0x180148ba5  mov     rcx, [rsp+0B8h+Handle]; Handle
0x180148baa  test    rcx, rcx
0x180148bad  jz      short loc_180148BB4
0x180148baf  call    NtClose
0x180148bb4  mov     eax, ebx
0x180148bb6  mov     rcx, [rsp+0B8h+var_10]
0x180148bbe  xor     rcx, rsp; StackCookie
0x180148bc1  call    __security_check_cookie
0x180148bc6  mov     rbx, [rsp+0B8h+arg_0]
0x180148bce  add     rsp, 0B0h
0x180148bd5  pop     rsi
0x180148bd6  retn
0x180168d43  push    rbp
0x180168d45  sub     rsp, 30h
0x180168d49  mov     rbp, rdx
0x180168d4c  mov     rcx, [rbp+30h]; Handle
0x180168d50  test    rcx, rcx
0x180168d53  jz      short loc_180168D5B
0x180168d55  call    NtClose
0x180168d5a  nop
0x180168d5b  add     rsp, 30h
0x180168d5f  pop     rbp
0x180168d60  retn
```
