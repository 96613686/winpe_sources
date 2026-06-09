# CopyDSToFQRegString

- ea: `0x180036c54`
- end: `0x180036ef7`
- name: `CopyDSToFQRegString`
- size: `675`
- prototype: `__int64 __fastcall(const wchar_t *, int, wchar_t **)`
- caller_count: `10`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008a98`
- `0x18002ba44`
- `0x18002ce78`
- `0x1800357c4`
- `0x180035b50`
- `0x180035e94`
- `0x1800362ac`
- `0x1800366c4`
- `0x180036a94`
- `0x18003da48`

## callees

- `0x180006f00`
- `0x18000b1d0`
- `0x18000c828`
- `0x18000e510`
- `0x180035650`
- `0x180036c54`
- `0x18003ec3c`
- `0x18004d090`

## import_xrefs

- `msvcrt!wcschr` at `0x180036cd8`
- `msvcrt!wcschr` at `0x180036cd8`

## string_xrefs

- `0x180036da4`: `SYSTEM\CurrentControlSet\Services\PolicyAgent\Parameters\Cache`

## pseudocode

```c
__int64 __fastcall CopyDSToFQRegString(const wchar_t *a1, int a2, wchar_t **a3)
{
  int v5; // edi
  unsigned int v6; // eax
  unsigned int v7; // esi
  _BYTE *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  wchar_t *v11; // rax
  const wchar_t *v12; // rbp
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned __int64 v15; // r14
  unsigned __int16 *v16; // rax
  wchar_t *v17; // rbx
  int v18; // eax
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  __int64 result; // rax
  wchar_t Str[264]; // [rsp+20h] [rbp-248h] BYREF

  v5 = 0;
  v6 = ComputePrelimCN(a1, Str, 0x104u);
  v7 = v6;
  if ( v6 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_37;
    v9 = 141;
    v10 = v6;
    goto LABEL_36;
  }
  v11 = wcschr(Str, 0x3Du);
  if ( v11 )
  {
    v12 = v11 + 1;
    if ( a2 )
    {
      v13 = -1;
      do
        ++v13;
      while ( v12[v13] );
      v14 = (unsigned int)(v13 + 64);
      v15 = (unsigned int)v14;
      v16 = (unsigned __int16 *)IpsecAllocMem(2 * v14);
      v17 = v16;
      if ( !v16 )
      {
        v10 = 14;
        v7 = 14;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          goto LABEL_37;
        v9 = 143;
        goto LABEL_36;
      }
      v7 = 0;
      v18 = StringCchCopyW(v16, v15, L"SYSTEM\\CurrentControlSet\\Services\\PolicyAgent\\Parameters\\Cache");
      v5 = v18;
      if ( v18 < 0 )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          goto LABEL_37;
        v20 = 144;
        goto LABEL_23;
      }
      v18 = StringCchCatW(v17, v15, L"\\");
      v5 = v18;
      if ( v18 < 0 )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          goto LABEL_37;
        v20 = 145;
        goto LABEL_23;
      }
      v18 = StringCchCatW(v17, v15, v12);
      v5 = v18;
      if ( v18 < 0 )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          goto LABEL_37;
        v20 = 146;
LABEL_23:
        WPP_SF_d(v19[2], v20, WPP_536406ce45663b69fb8864445bd745b5_Traceguids, (unsigned int)v18);
        goto LABEL_37;
      }
    }
    else
    {
      v17 = (wchar_t *)IpsecAllocStr(v11 + 1);
      if ( !v17 )
      {
        v10 = 14;
        v7 = 14;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          goto LABEL_37;
        v9 = 147;
        goto LABEL_36;
      }
    }
    *a3 = v17;
    return 0;
  }
  v8 = WPP_GLOBAL_Control;
  v7 = 87;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_37;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 148, WPP_536406ce45663b69fb8864445bd745b5_Traceguids, 87);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 == (_BYTE *)&WPP_GLOBAL_Control || (v8[28] & 0x10) == 0 )
    goto LABEL_37;
  v9 = 142;
  v10 = 87;
LABEL_36:
  WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_536406ce45663b69fb8864445bd745b5_Traceguids, v10);
LABEL_37:
  result = (unsigned __int16)v5;
  *a3 = 0;
  if ( v5 >= 0 )
    return v7;
  return result;
}

```

## disassembly

```asm
0x180036c54  mov     [rsp+arg_8], rbx
0x180036c59  mov     [rsp+arg_18], rbp
0x180036c5e  push    rsi
0x180036c5f  push    rdi
0x180036c60  push    r12
0x180036c62  push    r14
0x180036c64  push    r15
0x180036c66  sub     rsp, 240h
0x180036c6d  mov     rax, cs:__security_cookie
0x180036c74  xor     rax, rsp
0x180036c77  mov     [rsp+268h+var_38], rax
0x180036c7f  mov     r15, r8
0x180036c82  mov     ebx, edx
0x180036c84  xor     r12d, r12d
0x180036c87  lea     rdx, [rsp+268h+Str]
0x180036c8c  mov     r8d, 104h
0x180036c92  mov     edi, r12d
0x180036c95  call    ComputePrelimCN
0x180036c9a  mov     esi, eax
0x180036c9c  test    eax, eax
0x180036c9e  jz      short loc_180036CCE
0x180036ca0  mov     rcx, cs:WPP_GLOBAL_Control
0x180036ca7  lea     rbx, WPP_GLOBAL_Control
0x180036cae  cmp     rcx, rbx
0x180036cb1  jz      loc_180036EB9
0x180036cb7  test    byte ptr [rcx+1Ch], 10h
0x180036cbb  jz      loc_180036EB9
0x180036cc1  mov     edx, 8Dh
0x180036cc6  mov     r9d, eax
0x180036cc9  jmp     loc_180036EA9
0x180036cce  mov     edx, 3Dh ; '='; Ch
0x180036cd3  lea     rcx, [rsp+268h+Str]; Str
0x180036cd8  call    cs:__imp_wcschr
0x180036cde  test    rax, rax
0x180036ce1  jnz     short loc_180036D40
0x180036ce3  mov     rcx, cs:WPP_GLOBAL_Control
0x180036cea  lea     rbx, WPP_GLOBAL_Control
0x180036cf1  lea     esi, [rax+57h]
0x180036cf4  cmp     rcx, rbx
0x180036cf7  jz      loc_180036EB9
0x180036cfd  test    byte ptr [rcx+1Ch], 10h
0x180036d01  jz      short loc_180036D20
0x180036d03  mov     rcx, [rcx+10h]
0x180036d07  lea     edx, [rsi+3Dh]
0x180036d0a  mov     r9d, esi
0x180036d0d  lea     r8, WPP_536406ce45663b69fb8864445bd745b5_Traceguids
0x180036d14  call    WPP_SF_d
0x180036d19  mov     rcx, cs:WPP_GLOBAL_Control
0x180036d20  cmp     rcx, rbx
0x180036d23  jz      loc_180036EB9
0x180036d29  test    byte ptr [rcx+1Ch], 10h
0x180036d2d  jz      loc_180036EB9
0x180036d33  mov     edx, 8Eh
0x180036d38  mov     r9d, esi
0x180036d3b  jmp     loc_180036EA9
0x180036d40  lea     rbp, [rax+2]
0x180036d44  test    ebx, ebx
0x180036d46  jz      loc_180036E74
0x180036d4c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180036d50  inc     rax
0x180036d53  cmp     [rbp+rax*2+0], r12w
0x180036d59  jnz     short loc_180036D50
0x180036d5b  add     eax, 40h ; '@'
0x180036d5e  mov     r14d, eax
0x180036d61  lea     rcx, [rax+rax]
0x180036d65  call    IpsecAllocMem
0x180036d6a  mov     rbx, rax
0x180036d6d  test    rax, rax
0x180036d70  jnz     short loc_180036DA4
0x180036d72  lea     r9d, [rax+0Eh]
0x180036d76  mov     esi, r9d
0x180036d79  mov     rcx, cs:WPP_GLOBAL_Control
0x180036d80  lea     rbx, WPP_GLOBAL_Control
0x180036d87  cmp     rcx, rbx
0x180036d8a  jz      loc_180036EB9
0x180036d90  test    byte ptr [rcx+1Ch], 10h
0x180036d94  jz      loc_180036EB9
0x180036d9a  mov     edx, 8Fh
0x180036d9f  jmp     loc_180036EA9
0x180036da4  lea     r8, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Services\\Po"...
0x180036dab  mov     rdx, r14; unsigned __int64
0x180036dae  mov     rcx, rbx; unsigned __int16 *
0x180036db1  mov     esi, r12d
0x180036db4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180036db9  mov     edi, eax
0x180036dbb  test    eax, eax
0x180036dbd  jns     short loc_180036DFD
0x180036dbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180036dc6  lea     rbx, WPP_GLOBAL_Control
0x180036dcd  cmp     rcx, rbx
0x180036dd0  jz      loc_180036EB9
0x180036dd6  test    byte ptr [rcx+1Ch], 10h
0x180036dda  jz      loc_180036EB9
0x180036de0  mov     edx, 90h
0x180036de5  mov     rcx, [rcx+10h]
0x180036de9  lea     r8, WPP_536406ce45663b69fb8864445bd745b5_Traceguids
0x180036df0  mov     r9d, eax
0x180036df3  call    WPP_SF_d
0x180036df8  jmp     loc_180036EB9
0x180036dfd  lea     r8, pszSrc; "\\"
0x180036e04  mov     rdx, r14; cchDest
0x180036e07  mov     rcx, rbx; pszDest
0x180036e0a  call    StringCchCatW
0x180036e0f  mov     edi, eax
0x180036e11  test    eax, eax
0x180036e13  jns     short loc_180036E3D
0x180036e15  mov     rcx, cs:WPP_GLOBAL_Control
0x180036e1c  lea     rbx, WPP_GLOBAL_Control
0x180036e23  cmp     rcx, rbx
0x180036e26  jz      loc_180036EB9
0x180036e2c  test    byte ptr [rcx+1Ch], 10h
0x180036e30  jz      loc_180036EB9
0x180036e36  mov     edx, 91h
0x180036e3b  jmp     short loc_180036DE5
0x180036e3d  mov     r8, rbp; pszSrc
0x180036e40  mov     rdx, r14; cchDest
0x180036e43  mov     rcx, rbx; pszDest
0x180036e46  call    StringCchCatW
0x180036e4b  mov     edi, eax
0x180036e4d  test    eax, eax
0x180036e4f  jns     short loc_180036EC6
0x180036e51  mov     rcx, cs:WPP_GLOBAL_Control
0x180036e58  lea     rbx, WPP_GLOBAL_Control
0x180036e5f  cmp     rcx, rbx
0x180036e62  jz      short loc_180036EB9
0x180036e64  test    byte ptr [rcx+1Ch], 10h
0x180036e68  jz      short loc_180036EB9
0x180036e6a  mov     edx, 92h
0x180036e6f  jmp     loc_180036DE5
0x180036e74  mov     rcx, rbp; unsigned __int16 *
0x180036e77  call    IpsecAllocStr
0x180036e7c  mov     rbx, rax
0x180036e7f  test    rax, rax
0x180036e82  jnz     short loc_180036EC6
0x180036e84  lea     r9d, [rax+0Eh]
0x180036e88  mov     esi, r9d
0x180036e8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180036e92  lea     rbx, WPP_GLOBAL_Control
0x180036e99  cmp     rcx, rbx
0x180036e9c  jz      short loc_180036EB9
0x180036e9e  test    byte ptr [rcx+1Ch], 10h
0x180036ea2  jz      short loc_180036EB9
0x180036ea4  mov     edx, 93h
0x180036ea9  mov     rcx, [rcx+10h]
0x180036ead  lea     r8, WPP_536406ce45663b69fb8864445bd745b5_Traceguids
0x180036eb4  call    WPP_SF_d
0x180036eb9  test    edi, edi
0x180036ebb  movzx   eax, di
0x180036ebe  mov     [r15], r12
0x180036ec1  cmovns  eax, esi
0x180036ec4  jmp     short loc_180036ECB
0x180036ec6  mov     [r15], rbx
0x180036ec9  xor     eax, eax
0x180036ecb  mov     rcx, [rsp+268h+var_38]
0x180036ed3  xor     rcx, rsp; StackCookie
0x180036ed6  call    __security_check_cookie
0x180036edb  lea     r11, [rsp+268h+var_28]
0x180036ee3  mov     rbx, [r11+38h]
0x180036ee7  mov     rbp, [r11+48h]
0x180036eeb  mov     rsp, r11
0x180036eee  pop     r15
0x180036ef0  pop     r14
0x180036ef2  pop     r12
0x180036ef4  pop     rdi
0x180036ef5  pop     rsi
0x180036ef6  retn
```
