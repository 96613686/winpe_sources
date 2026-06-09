# GetDirectoryPolicyDN

- ea: `0x18000afe8`
- end: `0x18000b1ca`
- name: `GetDirectoryPolicyDN`
- size: `482`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `7`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001590`
- `0x18002ba44`
- `0x18002c380`
- `0x18002c9b0`
- `0x18002ce78`
- `0x18002d2ec`
- `0x18002d64c`

## callees

- `0x180001030`
- `0x180006f60`
- `0x18000afe8`
- `0x18000c828`
- `0x18000e078`
- `0x18000e510`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b031`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b031`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b1ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b1ae`

## string_xrefs

- `0x18000b08b`: `DSIPSECPolicyPath`

## pseudocode

```c
__int64 __fastcall GetDirectoryPolicyDN(__int64 *a1)
{
  unsigned __int16 *v2; // rdi
  unsigned int v3; // eax
  int v4; // edx
  DWORD dwMessageId; // ebx
  int v6; // ebp
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  DWORD ValueSpd; // eax
  unsigned __int64 v11; // rax
  __int64 v12; // rax
  __int64 v14; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int16 *v15; // [rsp+78h] [rbp+10h]
  HKEY hKey; // [rsp+80h] [rbp+18h] BYREF

  *a1 = 0;
  hKey = 0;
  v15 = 0;
  LODWORD(v14) = 0;
  v2 = 0;
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Policies\\Microsoft\\Windows\\IPSEC\\GPTIPSECPolicy",
         0,
         0x20019u,
         &hKey);
  dwMessageId = v3;
  if ( v3 )
  {
    v6 = 0;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_26;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v8 = 23;
      v9 = v3;
LABEL_21:
      WPP_SF_d(v7[2], v8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, v9);
      goto LABEL_22;
    }
LABEL_23:
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x10) != 0 )
      WPP_SF_d(v7[2], 27, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, dwMessageId);
LABEL_26:
    if ( !v6 )
      goto LABEL_29;
    goto LABEL_27;
  }
  v6 = 1;
  ValueSpd = RegstoreQueryValueSpd(hKey, L"DSIPSECPolicyPath", (__int64)&v14);
  dwMessageId = ValueSpd;
  if ( ValueSpd )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, ValueSpd);
      v2 = v15;
LABEL_22:
      v7 = WPP_GLOBAL_Control;
      goto LABEL_23;
    }
    v2 = v15;
    goto LABEL_23;
  }
  v2 = v15;
  v11 = -1;
  do
    ++v11;
  while ( v15[v11] );
  if ( v11 <= 7 )
  {
    dwMessageId = 13;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_23;
      v8 = 25;
LABEL_20:
      v9 = dwMessageId;
      goto LABEL_21;
    }
    goto LABEL_27;
  }
  v12 = IpsecAllocStr(v15 + 7);
  if ( !v12 )
  {
    dwMessageId = 14;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_23;
      v8 = 26;
      goto LABEL_20;
    }
LABEL_27:
    AuditIPSecPolicyErrorEventOld((int)v7, v4, 1269629040, (int)v2, dwMessageId);
    goto LABEL_29;
  }
  *a1 = v12;
LABEL_29:
  if ( v2 )
    IpsecFreeMem(v2);
  if ( hKey )
    RegCloseKey(hKey);
  return dwMessageId;
}

```

## disassembly

```asm
0x18000afe8  mov     r11, rsp
0x18000afeb  mov     [r11+20h], rbx
0x18000afef  push    rbp
0x18000aff0  push    rsi
0x18000aff1  push    rdi
0x18000aff2  push    r12
0x18000aff4  push    r14
0x18000aff6  sub     rsp, 40h
0x18000affa  xor     r14d, r14d
0x18000affd  lea     rax, [r11+18h]
0x18000b001  mov     [rcx], r14
0x18000b004  lea     rdx, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18000b00b  mov     rsi, rcx
0x18000b00e  mov     [r11+18h], r14
0x18000b012  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b019  mov     [r11+10h], r14
0x18000b01d  mov     r9d, 20019h; samDesired
0x18000b023  mov     [r11+8], r14d
0x18000b027  xor     r8d, r8d; ulOptions
0x18000b02a  mov     [r11-48h], rax
0x18000b02e  mov     edi, r14d
0x18000b031  call    cs:__imp_RegOpenKeyExW
0x18000b037  lea     r12, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18000b03e  mov     ebx, eax
0x18000b040  test    eax, eax
0x18000b042  jz      short loc_18000B074
0x18000b044  mov     ebp, r14d
0x18000b047  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b04e  lea     rsi, WPP_GLOBAL_Control
0x18000b055  cmp     rcx, rsi
0x18000b058  jz      loc_18000B179
0x18000b05e  test    byte ptr [rcx+1Ch], 10h
0x18000b062  jz      loc_18000B15A
0x18000b068  lea     edx, [r14+17h]
0x18000b06c  mov     r9d, eax
0x18000b06f  jmp     loc_18000B147
0x18000b074  mov     rcx, [rsp+68h+hKey]; hKey
0x18000b07c  lea     rax, [rsp+68h+arg_0]
0x18000b081  lea     r9, [rsp+68h+arg_8]
0x18000b086  mov     qword ptr [rsp+68h+dwMessageId], rax; __int64
0x18000b08b  lea     rdx, aDsipsecpolicyp; "DSIPSECPolicyPath"
0x18000b092  mov     ebp, 1
0x18000b097  call    RegstoreQueryValueSpd
0x18000b09c  mov     ebx, eax
0x18000b09e  test    eax, eax
0x18000b0a0  jz      short loc_18000B0DB
0x18000b0a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b0a9  lea     rsi, WPP_GLOBAL_Control
0x18000b0b0  cmp     rcx, rsi
0x18000b0b3  jz      short loc_18000B0D4
0x18000b0b5  test    byte ptr [rcx+1Ch], 10h
0x18000b0b9  jz      short loc_18000B0D4
0x18000b0bb  mov     rcx, [rcx+10h]
0x18000b0bf  lea     edx, [rbp+17h]
0x18000b0c2  mov     r9d, eax
0x18000b0c5  mov     r8, r12
0x18000b0c8  call    WPP_SF_d
0x18000b0cd  mov     rdi, [rsp+68h+arg_8]
0x18000b0d2  jmp     short loc_18000B153
0x18000b0d4  mov     rdi, [rsp+68h+arg_8]
0x18000b0d9  jmp     short loc_18000B15A
0x18000b0db  mov     rdi, [rsp+68h+arg_8]
0x18000b0e0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b0e4  inc     rax
0x18000b0e7  cmp     [rdi+rax*2], r14w
0x18000b0ec  jnz     short loc_18000B0E4
0x18000b0ee  cmp     rax, 7
0x18000b0f2  ja      short loc_18000B117
0x18000b0f4  mov     ebx, 0Dh
0x18000b0f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b100  lea     rsi, WPP_GLOBAL_Control
0x18000b107  cmp     rcx, rsi
0x18000b10a  jz      short loc_18000B17D
0x18000b10c  test    byte ptr [rcx+1Ch], 10h
0x18000b110  jz      short loc_18000B15A
0x18000b112  lea     edx, [rbx+0Ch]
0x18000b115  jmp     short loc_18000B144
0x18000b117  lea     rcx, [rdi+0Eh]; unsigned __int16 *
0x18000b11b  call    IpsecAllocStr
0x18000b120  test    rax, rax
0x18000b123  jnz     short loc_18000B191
0x18000b125  lea     ebx, [rax+0Eh]
0x18000b128  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b12f  lea     rsi, WPP_GLOBAL_Control
0x18000b136  cmp     rcx, rsi
0x18000b139  jz      short loc_18000B17D
0x18000b13b  test    byte ptr [rcx+1Ch], 10h
0x18000b13f  jz      short loc_18000B15A
0x18000b141  lea     edx, [rax+1Ah]
0x18000b144  mov     r9d, ebx
0x18000b147  mov     rcx, [rcx+10h]
0x18000b14b  mov     r8, r12
0x18000b14e  call    WPP_SF_d
0x18000b153  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b15a  cmp     rcx, rsi
0x18000b15d  jz      short loc_18000B179
0x18000b15f  test    byte ptr [rcx+1Ch], 10h
0x18000b163  jz      short loc_18000B179
0x18000b165  mov     rcx, [rcx+10h]
0x18000b169  mov     edx, 1Bh
0x18000b16e  mov     r9d, ebx
0x18000b171  mov     r8, r12
0x18000b174  call    WPP_SF_d
0x18000b179  test    ebp, ebp
0x18000b17b  jz      short loc_18000B194
0x18000b17d  mov     r9, rdi; int
0x18000b180  mov     [rsp+68h+dwMessageId], ebx; dwMessageId
0x18000b184  mov     r8d, 4BAD0070h; int
0x18000b18a  call    AuditIPSecPolicyErrorEventOld
0x18000b18f  jmp     short loc_18000B194
0x18000b191  mov     [rsi], rax
0x18000b194  test    rdi, rdi
0x18000b197  jz      short loc_18000B1A1
0x18000b199  mov     rcx, rdi; lpMem
0x18000b19c  call    IpsecFreeMem
0x18000b1a1  mov     rcx, [rsp+68h+hKey]; hKey
0x18000b1a9  test    rcx, rcx
0x18000b1ac  jz      short loc_18000B1B4
0x18000b1ae  call    cs:__imp_RegCloseKey
0x18000b1b4  mov     eax, ebx
0x18000b1b6  mov     rbx, [rsp+68h+arg_18]
0x18000b1be  add     rsp, 40h
0x18000b1c2  pop     r14
0x18000b1c4  pop     r12
0x18000b1c6  pop     rdi
0x18000b1c7  pop     rsi
0x18000b1c8  pop     rbp
0x18000b1c9  retn
```
