# TlsEncryptPreMasterKey

- ea: `0x180012d98`
- end: `0x180012f7c`
- name: `TlsEncryptPreMasterKey`
- size: `484`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180006070`
- `0x180013740`

## callees

- `0x1800081a8`
- `0x18000b594`
- `0x18000b654`
- `0x180012d98`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x180012e42`
- `bcrypt!BCryptGenRandom` at `0x180012e42`
- `ncrypt!NCryptEncrypt` at `0x180012f47`
- `ncrypt!NCryptEncrypt` at `0x180012f47`

## string_xrefs

- `0x180012e77`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180012ec2`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180012f59`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall TlsEncryptPreMasterKey(
        __int64 a1,
        _DWORD *a2,
        NCRYPT_KEY_HANDLE a3,
        __int64 a4,
        DWORD dwFlags,
        PBYTE pbOutput,
        DWORD cbOutput,
        DWORD *pcbResult)
{
  BYTE *v9; // rdi
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rsi
  BYTE v13; // ah
  int v14; // edx
  int v15; // r8d
  __int64 v17; // r9
  int v18; // [rsp+90h] [rbp+8h] BYREF
  int v19; // [rsp+94h] [rbp+Ch]

  v19 = HIDWORD(a1);
  v18 = 0;
  if ( a2 && *a2 >= 0x3Cu )
  {
    v9 = (BYTE *)(a2 + 3);
    v10 = TlsParseParameterList(a4, (unsigned int)a2[2], 0, 0, 0, 0, 0, 0, 0, 0, &v18);
    v11 = v10;
    v12 = 48;
    if ( v10 < 0 )
    {
      v17 = 980;
    }
    else
    {
      v13 = BYTE1(v18);
      v9[1] = v18;
      *v9 = v13;
      v11 = BCryptGenRandom(0, v9 + 2, 0x2Eu, 2u);
      if ( (v11 & 0x80000000) != 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v14,
            v15,
            (unsigned int)"Status",
            v11,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
            230);
        goto LABEL_18;
      }
      v10 = NCryptEncrypt(a3, v9, 0x30u, 0, pbOutput, cbOutput, pcbResult, dwFlags);
      v11 = v10;
      if ( v10 >= 0 )
        return v11;
      v17 = 1017;
    }
    DebugTraceError((unsigned int)v10, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", v17);
LABEL_18:
    if ( v9 )
    {
      do
      {
        *v9++ = 0;
        --v12;
      }
      while ( v12 );
    }
    return v11;
  }
  v11 = -2146893779;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)a2,
      a3,
      (unsigned int)"Status",
      45,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
      193);
  return v11;
}

```

## disassembly

```asm
0x180012d98  mov     r11, rsp
0x180012d9b  mov     [r11+8], rcx
0x180012d9f  push    rbx
0x180012da0  push    rbp
0x180012da1  push    rsi
0x180012da2  push    rdi
0x180012da3  sub     rsp, 68h
0x180012da7  mov     dword ptr [r11+8], 0
0x180012daf  mov     rax, r9
0x180012db2  mov     rbp, r8
0x180012db5  test    rdx, rdx
0x180012db8  jz      loc_180012EA0
0x180012dbe  cmp     dword ptr [rdx], 3Ch ; '<'
0x180012dc1  jb      loc_180012EA0
0x180012dc7  lea     rcx, [r11+8]
0x180012dcb  xor     r9d, r9d
0x180012dce  mov     [r11-38h], rcx
0x180012dd2  lea     rdi, [rdx+0Ch]
0x180012dd6  mov     edx, [rdx+8]
0x180012dd9  xor     r8d, r8d
0x180012ddc  mov     qword ptr [r11-40h], 0
0x180012de4  mov     rcx, rax
0x180012de7  mov     qword ptr [r11-48h], 0
0x180012def  mov     qword ptr [r11-50h], 0
0x180012df7  mov     qword ptr [r11-58h], 0
0x180012dff  mov     qword ptr [r11-60h], 0
0x180012e07  mov     qword ptr [r11-68h], 0
0x180012e0f  call    TlsParseParameterList
0x180012e14  mov     ebx, eax
0x180012e16  mov     esi, 30h ; '0'
0x180012e1b  test    eax, eax
0x180012e1d  js      loc_180012F03
0x180012e23  mov     ecx, [rsp+88h+arg_0]
0x180012e2a  lea     rdx, [rdi+2]; pbBuffer
0x180012e2e  mov     eax, ecx
0x180012e30  mov     [rdi+1], cl
0x180012e33  shr     eax, 8
0x180012e36  lea     r9d, [rsi-2Eh]; dwFlags
0x180012e3a  xor     ecx, ecx; hAlgorithm
0x180012e3c  mov     [rdi], al
0x180012e3e  lea     r8d, [rsi-2]; cbBuffer
0x180012e42  call    cs:__imp_BCryptGenRandom
0x180012e48  mov     ebx, eax
0x180012e4a  test    eax, eax
0x180012e4c  jns     loc_180012F0B
0x180012e52  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e59  lea     rax, WPP_GLOBAL_Control
0x180012e60  cmp     rcx, rax
0x180012e63  jz      loc_180012F6E
0x180012e69  test    byte ptr [rcx+1Ch], 1
0x180012e6d  jz      loc_180012F6E
0x180012e73  mov     rcx, [rcx+10h]
0x180012e77  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012e7e  mov     dword ptr [rsp+88h+pcbResult], 3E6h
0x180012e86  lea     r9, aStatus; "Status"
0x180012e8d  mov     qword ptr [rsp+88h+cbOutput], rax
0x180012e92  mov     dword ptr [rsp+88h+pbOutput], ebx
0x180012e96  call    WPP_SF_sDsd
0x180012e9b  jmp     loc_180012F6E
0x180012ea0  mov     ebx, 8009002Dh
0x180012ea5  mov     rcx, cs:WPP_GLOBAL_Control
0x180012eac  lea     rax, WPP_GLOBAL_Control
0x180012eb3  cmp     rcx, rax
0x180012eb6  jz      short loc_180012EEA
0x180012eb8  test    byte ptr [rcx+1Ch], 1
0x180012ebc  jz      short loc_180012EEA
0x180012ebe  mov     rcx, [rcx+10h]
0x180012ec2  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012ec9  mov     dword ptr [rsp+88h+pcbResult], 3C1h
0x180012ed1  lea     r9, aStatus; "Status"
0x180012ed8  mov     qword ptr [rsp+88h+cbOutput], rax
0x180012edd  mov     dword ptr [rsp+88h+pbOutput], 8009002Dh
0x180012ee5  call    WPP_SF_sDsd
0x180012eea  mov     eax, ebx
0x180012eec  add     rsp, 68h
0x180012ef0  pop     rdi
0x180012ef1  pop     rsi
0x180012ef2  pop     rbp
0x180012ef3  pop     rbx
0x180012ef4  retn
0x180012ef5  mov     byte ptr [rdi], 0
0x180012ef8  inc     rdi
0x180012efb  sub     rsi, 1
0x180012eff  jnz     short loc_180012EF5
0x180012f01  jmp     short loc_180012EEA
0x180012f03  mov     r9d, 3D4h
0x180012f09  jmp     short loc_180012F59
0x180012f0b  mov     eax, [rsp+88h+arg_20]
0x180012f12  xor     r9d, r9d; pPaddingInfo
0x180012f15  mov     [rsp+88h+dwFlags], eax; dwFlags
0x180012f19  mov     r8d, esi; cbInput
0x180012f1c  mov     rax, [rsp+88h+arg_38]
0x180012f24  mov     rdx, rdi; pbInput
0x180012f27  mov     [rsp+88h+pcbResult], rax; pcbResult
0x180012f2c  mov     rcx, rbp; hKey
0x180012f2f  mov     eax, [rsp+88h+arg_30]
0x180012f36  mov     [rsp+88h+cbOutput], eax; cbOutput
0x180012f3a  mov     rax, [rsp+88h+arg_28]
0x180012f42  mov     [rsp+88h+pbOutput], rax; pbOutput
0x180012f47  call    cs:__imp_NCryptEncrypt
0x180012f4d  mov     ebx, eax
0x180012f4f  test    eax, eax
0x180012f51  jns     short loc_180012EEA
0x180012f53  mov     r9d, 3F9h
0x180012f59  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012f60  mov     ecx, eax
0x180012f62  lea     rdx, aStatus; "Status"
0x180012f69  call    DebugTraceError
0x180012f6e  test    rdi, rdi
0x180012f71  jz      loc_180012EEA
0x180012f77  jmp     loc_180012EF5
```
