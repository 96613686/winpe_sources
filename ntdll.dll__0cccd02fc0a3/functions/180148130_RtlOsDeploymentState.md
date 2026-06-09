# RtlOsDeploymentState

- ea: `0x180148130`
- end: `0x180148278`
- name: `RtlOsDeploymentState`
- size: `328`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800c0420`
- `0x180148130`
- `0x18015e4b0`
- `0x18015e510`
- `0x18015e5b0`
- `0x180162000`

## string_xrefs

- `0x180148188`: `\Registry\Machine\System\Setup`
- `0x1801481dc`: `Compact`

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
0x180148130  mov     r11, rsp
0x180148133  mov     [r11+8], rbx
0x180148137  push    rsi
0x180148138  sub     rsp, 0B0h
0x18014813f  mov     rax, cs:__security_cookie
0x180148146  xor     rax, rsp
0x180148149  mov     [rsp+0B8h+var_10], rax
0x180148151  mov     [rsp+0B8h+Handle], 0
0x18014815a  mov     ebx, 1
0x18014815f  mov     [rsp+0B8h+var_80], 0
0x180148167  xor     eax, eax
0x180148169  xorps   xmm0, xmm0
0x18014816c  movups  [rsp+0B8h+var_78], xmm0
0x180148171  movups  [rsp+0B8h+var_68], xmm0
0x180148176  movups  [rsp+0B8h+var_68+0Ch], xmm0
0x18014817b  movups  [rsp+0B8h+var_48], xmm0
0x180148180  xorps   xmm1, xmm1
0x180148183  movups  xmmword ptr [r11-38h], xmm1
0x180148188  lea     rdx, aRegistryMachin_14; "\\Registry\\Machine\\System\\Setup"
0x18014818f  lea     rcx, [r11-48h]; DestinationString
0x180148193  call    RtlInitUnicodeString
0x180148198  mov     dword ptr [rsp+0B8h+var_78], 30h ; '0'
0x1801481a0  mov     qword ptr [rsp+0B8h+var_78+8], 0
0x1801481a9  mov     dword ptr [rsp+0B8h+var_68+8], 240h
0x1801481b1  lea     rax, [rsp+0B8h+var_48]
0x1801481b6  mov     qword ptr [rsp+0B8h+var_68], rax
0x1801481bb  xorps   xmm0, xmm0
0x1801481be  movdqu  [rsp+0B8h+var_58], xmm0
0x1801481c4  lea     r8, [rsp+0B8h+var_78]
0x1801481c9  mov     edx, 20019h
0x1801481ce  lea     rcx, [rsp+0B8h+Handle]
0x1801481d3  call    NtOpenKey
0x1801481d8  test    eax, eax
0x1801481da  js      short loc_180148245
0x1801481dc  lea     rdx, aCompact; "Compact"
0x1801481e3  lea     rcx, [rsp+0B8h+DestinationString]; DestinationString
0x1801481eb  call    RtlInitUnicodeString
0x1801481f0  lea     rax, [rsp+0B8h+var_80]
0x1801481f5  mov     [rsp+0B8h+var_90], rax
0x1801481fa  mov     [rsp+0B8h+var_98], 14h
0x180148202  lea     r9, [rsp+0B8h+var_28]
0x18014820a  lea     esi, [rbx+1]
0x18014820d  mov     r8d, esi
0x180148210  lea     rdx, [rsp+0B8h+DestinationString]
0x180148218  mov     rcx, [rsp+0B8h+Handle]
0x18014821d  call    NtQueryValueKey
0x180148222  test    eax, eax
0x180148224  js      short loc_180148245
0x180148226  cmp     [rsp+0B8h+var_24], 4
0x18014822e  jnz     short loc_180148245
0x180148230  cmp     [rsp+0B8h+var_20], 4
0x180148238  jnz     short loc_180148245
0x18014823a  cmp     [rsp+0B8h+var_1C], 0
0x180148242  cmovnz  ebx, esi
0x180148245  mov     rcx, [rsp+0B8h+Handle]; Handle
0x18014824a  test    rcx, rcx
0x18014824d  jz      short loc_180148254
0x18014824f  call    NtClose
0x180148254  mov     eax, ebx
0x180148256  mov     rcx, [rsp+0B8h+var_10]
0x18014825e  xor     rcx, rsp; StackCookie
0x180148261  call    __security_check_cookie
0x180148266  mov     rbx, [rsp+0B8h+arg_0]
0x18014826e  add     rsp, 0B0h
0x180148275  pop     rsi
0x180148276  retn
0x180168523  push    rbp
0x180168525  sub     rsp, 30h
0x180168529  mov     rbp, rdx
0x18016852c  mov     rcx, [rbp+30h]; Handle
0x180168530  test    rcx, rcx
0x180168533  jz      short loc_18016853B
0x180168535  call    NtClose
0x18016853a  nop
0x18016853b  add     rsp, 30h
0x18016853f  pop     rbp
0x180168540  retn
```
