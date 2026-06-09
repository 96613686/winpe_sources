# ShowRegistryValue

- ea: `0x140002bc0`
- end: `0x140002f2a`
- name: `ShowRegistryValue`
- size: `874`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140005e84`
- `0x140009574`

## callees

- `0x140001bb2`
- `0x140002bc0`
- `0x14000cd48`
- `0x14000dce0`
- `0x14000e020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002d16`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002d71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002f13`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002d16`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002d71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002f13`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140002c53`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140002ee1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140002c53`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140002ee1`

## pseudocode

```c
__int64 __fastcall ShowRegistryValue(int *a1)
{
  int v3; // ebx
  FILE *v4; // rax
  const WCHAR *ResString2FromModule; // rbx
  __int64 v6; // rcx
  int v7; // ebp
  FILE *v8; // rax
  FILE *v9; // rax
  const WCHAR *v10; // rbx
  FILE *v11; // rcx
  const WCHAR *v12; // rdx
  int v13; // edx
  unsigned int v14; // eax
  const WCHAR *v15; // rbp
  int v16; // ebx
  FILE *v17; // rax
  const WCHAR *v18; // rbp
  FILE *v19; // rax
  const WCHAR *v20; // rbx
  FILE *v21; // rcx
  const WCHAR *v22; // rdx
  const WCHAR *v23; // r14
  __int64 v24; // rbp
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // ebx
  FILE *v30; // rax
  FILE *v31; // rax
  int v32; // eax
  __int64 v33; // rbx
  FILE *v34; // rax
  unsigned int v35; // esi
  int v36; // ebx
  FILE *v37; // rax
  const WCHAR *v38; // r15
  int v39; // ebx
  const WCHAR *v40; // rsi
  __int64 v41; // rax
  FILE *v42; // rax
  FILE *v43; // rax
  FILE *v44; // rax
  __int64 v45; // [rsp+20h] [rbp-48h]
  __int64 v46; // [rsp+28h] [rbp-40h]

  if ( !a1 )
    goto LABEL_64;
  if ( (a1[7] & 0xF) == 0xF )
    return 1;
  v3 = a1[8];
  if ( v3 )
  {
    v4 = o___acrt_iob_func_0(1u);
    ShowMessageEx(v4, 1, 1, L"%*s", v3, L" ");
  }
  if ( (a1[7] & 1) == 0 )
  {
    ResString2FromModule = (const WCHAR *)*((_QWORD *)a1 + 2);
    if ( !ResString2FromModule || *((_QWORD *)a1 + 5) && (a1[7] & 0x10) != 0 )
      goto LABEL_64;
    if ( !lstrlenW(*((LPCWSTR *)a1 + 2)) )
      ResString2FromModule = (const WCHAR *)GetResString2FromModule(v6, 501, 0);
    if ( (a1[7] & 0x10) != 0 )
    {
      v7 = a1[6];
      if ( !v7 )
        goto LABEL_64;
      v8 = o___acrt_iob_func_0(1u);
      LODWORD(v45) = v7;
      ShowMessageEx(v8, 2, 1, L"%-*s", v45, ResString2FromModule);
    }
    else
    {
      v9 = o___acrt_iob_func_0(1u);
      ShowMessage(v9, ResString2FromModule);
    }
    v10 = (const WCHAR *)*((_QWORD *)a1 + 5);
    v11 = o___acrt_iob_func_0(1u);
    v12 = v10;
    if ( !v10 )
      v12 = L" ";
    ShowMessage(v11, v12);
  }
  if ( (a1[7] & 2) == 0 )
  {
    v13 = *a1;
    v14 = 0;
    if ( (a1[7] & 0x20) != 0 )
    {
      while ( v13 != LODWORD(g_regTypes[2 * v14]) )
      {
        if ( ++v14 >= 0xC )
          goto LABEL_25;
      }
      v15 = (const WCHAR *)g_regTypes[2 * v14 + 1];
      if ( v15 )
        goto LABEL_26;
LABEL_25:
      SetLastError(0x490u);
      v15 = L"REG_NONE";
LABEL_26:
      v16 = *a1;
      v17 = o___acrt_iob_func_0(1u);
      LODWORD(v46) = v16;
      ShowMessageEx(v17, 2, 1, L"%s (%d)", v15, v46);
    }
    else
    {
      while ( v13 != LODWORD(g_regTypes[2 * v14]) )
      {
        if ( ++v14 >= 0xC )
          goto LABEL_31;
      }
      v18 = (const WCHAR *)g_regTypes[2 * v14 + 1];
      if ( v18 )
        goto LABEL_32;
LABEL_31:
      SetLastError(0x490u);
      v18 = L"REG_NONE";
LABEL_32:
      v19 = o___acrt_iob_func_0(1u);
      ShowMessage(v19, v18);
    }
    v20 = (const WCHAR *)*((_QWORD *)a1 + 5);
    v21 = o___acrt_iob_func_0(1u);
    v22 = v20;
    if ( !v20 )
      v22 = L" ";
    ShowMessage(v21, v22);
  }
  if ( (a1[7] & 4) != 0 )
    goto LABEL_63;
  v23 = (const WCHAR *)*((_QWORD *)a1 + 1);
  if ( v23 )
  {
    v24 = (unsigned int)a1[1];
    if ( (_DWORD)v24 )
    {
      v25 = *a1;
      if ( (unsigned int)*a1 > 6 )
      {
        v32 = v25 - 7;
        if ( !v32 )
        {
          v38 = L"\\0";
          v39 = 0;
          if ( *((_QWORD *)a1 + 6) )
            v38 = (const WCHAR *)*((_QWORD *)a1 + 6);
          v40 = (const WCHAR *)((char *)v23 + v24);
          while ( v23 < v40 )
          {
            if ( *v23 )
            {
              if ( v39 == 1 )
              {
                v42 = o___acrt_iob_func_0(1u);
                ShowMessage(v42, v38);
              }
              v43 = o___acrt_iob_func_0(1u);
              ShowMessage(v43, v23);
              v41 = 2LL * (unsigned int)lstrlenW(v23);
            }
            else
            {
              v39 = 1;
              v41 = 2;
            }
            v23 = (const WCHAR *)((char *)v23 + v41);
          }
          goto LABEL_63;
        }
        if ( v32 == 4 )
        {
          v33 = *(_QWORD *)v23;
          v34 = o___acrt_iob_func_0(1u);
          ShowMessageEx(v34, 1, 1, L"0x%I64x", v33);
          goto LABEL_63;
        }
      }
      else if ( v25 != 6 )
      {
        v26 = v25 - 1;
        if ( !v26 || (v27 = v26 - 1) == 0 )
        {
          v31 = o___acrt_iob_func_0(1u);
          ShowMessage(v31, v23);
          goto LABEL_63;
        }
        v28 = v27 - 1;
        if ( v28 )
        {
          if ( (unsigned int)(v28 - 1) <= 1 )
          {
            v29 = *(_DWORD *)v23;
            v30 = o___acrt_iob_func_0(1u);
            LODWORD(v45) = v29;
            ShowMessageEx(v30, 1, 1, L"0x%x", v45);
            goto LABEL_63;
          }
        }
      }
      v35 = 0;
      do
      {
        v36 = *((unsigned __int8 *)v23 + v35);
        v37 = o___acrt_iob_func_0(1u);
        LODWORD(v45) = v36;
        ShowMessageEx(v37, 1, 1, L"%02X", v45);
        ++v35;
      }
      while ( v35 < (unsigned int)v24 );
    }
LABEL_63:
    v44 = o___acrt_iob_func_0(1u);
    ShowMessage(v44, L"\n");
    return 1;
  }
LABEL_64:
  SetLastError(0x57u);
  return 0;
}

```

## disassembly

```asm
0x140002bc0  push    rbx
0x140002bc2  push    rbp
0x140002bc3  push    rsi
0x140002bc4  push    rdi
0x140002bc5  push    r12
0x140002bc7  push    r14
0x140002bc9  push    r15
0x140002bcb  sub     rsp, 30h
0x140002bcf  xor     r12d, r12d
0x140002bd2  mov     rsi, rcx
0x140002bd5  test    rcx, rcx
0x140002bd8  jz      loc_140002F0E
0x140002bde  mov     eax, [rcx+1Ch]
0x140002be1  and     eax, 0Fh
0x140002be4  cmp     al, 0Fh
0x140002be6  jnz     short loc_140002BF2
0x140002be8  lea     eax, [r12+1]
0x140002bed  jmp     loc_140002F1B
0x140002bf2  mov     ebx, [rcx+20h]
0x140002bf5  lea     r14, asc_140010954; " "
0x140002bfc  mov     edi, 1
0x140002c01  test    ebx, ebx
0x140002c03  jz      short loc_140002C29
0x140002c05  mov     ecx, edi; Ix
0x140002c07  call    _o___acrt_iob_func_0
0x140002c0c  mov     rcx, rax
0x140002c0f  mov     [rsp+68h+var_40], r14
0x140002c14  lea     r9, aS_1; "%*s"
0x140002c1b  mov     dword ptr [rsp+68h+var_48], ebx
0x140002c1f  mov     r8d, edi
0x140002c22  mov     edx, edi
0x140002c24  call    ShowMessageEx
0x140002c29  test    [rsi+1Ch], dil
0x140002c2d  jnz     loc_140002CD7
0x140002c33  mov     rbx, [rsi+10h]
0x140002c37  test    rbx, rbx
0x140002c3a  jz      loc_140002F0E
0x140002c40  cmp     [rsi+28h], r12
0x140002c44  jz      short loc_140002C50
0x140002c46  test    byte ptr [rsi+1Ch], 10h
0x140002c4a  jnz     loc_140002F0E
0x140002c50  mov     rcx, rbx; lpString
0x140002c53  call    cs:__imp_lstrlenW
0x140002c59  test    eax, eax
0x140002c5b  jnz     short loc_140002C6D
0x140002c5d  xor     r8d, r8d
0x140002c60  mov     edx, 1F5h
0x140002c65  call    GetResString2FromModule
0x140002c6a  mov     rbx, rax
0x140002c6d  test    byte ptr [rsi+1Ch], 10h
0x140002c71  jz      short loc_140002CA7
0x140002c73  mov     ebp, [rsi+18h]
0x140002c76  test    ebp, ebp
0x140002c78  jz      loc_140002F0E
0x140002c7e  mov     ecx, edi; Ix
0x140002c80  call    _o___acrt_iob_func_0
0x140002c85  mov     rcx, rax
0x140002c88  mov     [rsp+68h+var_40], rbx
0x140002c8d  lea     r9, aS; "%-*s"
0x140002c94  mov     dword ptr [rsp+68h+var_48], ebp
0x140002c98  mov     r8d, edi
0x140002c9b  mov     edx, 2
0x140002ca0  call    ShowMessageEx
0x140002ca5  jmp     short loc_140002CB9
0x140002ca7  mov     ecx, edi; Ix
0x140002ca9  call    _o___acrt_iob_func_0
0x140002cae  mov     rcx, rax; Stream
0x140002cb1  mov     rdx, rbx; lpString
0x140002cb4  call    ShowMessage
0x140002cb9  mov     rbx, [rsi+28h]
0x140002cbd  mov     ecx, edi; Ix
0x140002cbf  call    _o___acrt_iob_func_0
0x140002cc4  mov     rcx, rax; Stream
0x140002cc7  mov     rdx, rbx
0x140002cca  test    rbx, rbx
0x140002ccd  jnz     short loc_140002CD2
0x140002ccf  mov     rdx, r14; lpString
0x140002cd2  call    ShowMessage
0x140002cd7  test    byte ptr [rsi+1Ch], 2
0x140002cdb  jnz     loc_140002DAE
0x140002ce1  test    byte ptr [rsi+1Ch], 20h
0x140002ce5  lea     rbp, g_regTypes
0x140002cec  mov     edx, [rsi]
0x140002cee  mov     eax, r12d
0x140002cf1  jz      short loc_140002D4E
0x140002cf3  mov     ecx, eax
0x140002cf5  add     rcx, rcx
0x140002cf8  cmp     edx, [rbp+rcx*8+0]
0x140002cfc  jz      short loc_140002D07
0x140002cfe  add     eax, edi
0x140002d00  cmp     eax, 0Ch
0x140002d03  jb      short loc_140002CF3
0x140002d05  jmp     short loc_140002D11
0x140002d07  mov     rbp, [rbp+rcx*8+8]
0x140002d0c  test    rbp, rbp
0x140002d0f  jnz     short loc_140002D23
0x140002d11  mov     ecx, 490h; dwErrCode
0x140002d16  call    cs:__imp_SetLastError
0x140002d1c  lea     rbp, cwszRegNone; "REG_NONE"
0x140002d23  mov     ebx, [rsi]
0x140002d25  mov     ecx, edi; Ix
0x140002d27  call    _o___acrt_iob_func_0
0x140002d2c  mov     rcx, rax
0x140002d2f  mov     dword ptr [rsp+68h+var_40], ebx
0x140002d33  lea     r9, aSD; "%s (%d)"
0x140002d3a  mov     [rsp+68h+var_48], rbp
0x140002d3f  mov     r8d, edi
0x140002d42  mov     edx, 2
0x140002d47  call    ShowMessageEx
0x140002d4c  jmp     short loc_140002D90
0x140002d4e  mov     ecx, eax
0x140002d50  add     rcx, rcx
0x140002d53  cmp     edx, [rbp+rcx*8+0]
0x140002d57  jz      short loc_140002D62
0x140002d59  add     eax, edi
0x140002d5b  cmp     eax, 0Ch
0x140002d5e  jb      short loc_140002D4E
0x140002d60  jmp     short loc_140002D6C
0x140002d62  mov     rbp, [rbp+rcx*8+8]
0x140002d67  test    rbp, rbp
0x140002d6a  jnz     short loc_140002D7E
0x140002d6c  mov     ecx, 490h; dwErrCode
0x140002d71  call    cs:__imp_SetLastError
0x140002d77  lea     rbp, cwszRegNone; "REG_NONE"
0x140002d7e  mov     ecx, edi; Ix
0x140002d80  call    _o___acrt_iob_func_0
0x140002d85  mov     rcx, rax; Stream
0x140002d88  mov     rdx, rbp; lpString
0x140002d8b  call    ShowMessage
0x140002d90  mov     rbx, [rsi+28h]
0x140002d94  mov     ecx, edi; Ix
0x140002d96  call    _o___acrt_iob_func_0
0x140002d9b  mov     rcx, rax; Stream
0x140002d9e  mov     rdx, rbx
0x140002da1  test    rbx, rbx
0x140002da4  jnz     short loc_140002DA9
0x140002da6  mov     rdx, r14; lpString
0x140002da9  call    ShowMessage
0x140002dae  test    byte ptr [rsi+1Ch], 4
0x140002db2  jnz     loc_140002EF4
0x140002db8  mov     r14, [rsi+8]
0x140002dbc  test    r14, r14
0x140002dbf  jz      loc_140002F0E
0x140002dc5  mov     ebp, [rsi+4]
0x140002dc8  test    ebp, ebp
0x140002dca  jz      loc_140002EF4
0x140002dd0  mov     eax, [rsi]
0x140002dd2  cmp     eax, 6
0x140002dd5  ja      short loc_140002E2B
0x140002dd7  jz      short loc_140002E55
0x140002dd9  sub     eax, edi
0x140002ddb  jz      short loc_140002E14
0x140002ddd  sub     eax, edi
0x140002ddf  jz      short loc_140002E14
0x140002de1  sub     eax, edi
0x140002de3  jz      short loc_140002E55
0x140002de5  sub     eax, edi
0x140002de7  jz      short loc_140002DED
0x140002de9  cmp     eax, edi
0x140002deb  jnz     short loc_140002E55
0x140002ded  mov     ebx, [r14]
0x140002df0  mov     ecx, edi; Ix
0x140002df2  call    _o___acrt_iob_func_0
0x140002df7  lea     r9, a0xX; "0x%x"
0x140002dfe  mov     dword ptr [rsp+68h+var_48], ebx
0x140002e02  mov     rcx, rax
0x140002e05  mov     r8d, edi
0x140002e08  mov     edx, edi
0x140002e0a  call    ShowMessageEx
0x140002e0f  jmp     loc_140002EF4
0x140002e14  mov     ecx, edi; Ix
0x140002e16  call    _o___acrt_iob_func_0
0x140002e1b  mov     rcx, rax; Stream
0x140002e1e  mov     rdx, r14; lpString
0x140002e21  call    ShowMessage
0x140002e26  jmp     loc_140002EF4
0x140002e2b  sub     eax, 7
0x140002e2e  jz      short loc_140002E8E
0x140002e30  sub     eax, edi
0x140002e32  jz      short loc_140002E55
0x140002e34  sub     eax, edi
0x140002e36  jz      short loc_140002E55
0x140002e38  cmp     eax, 2
0x140002e3b  jnz     short loc_140002E55
0x140002e3d  mov     rbx, [r14]
0x140002e40  mov     ecx, edi; Ix
0x140002e42  call    _o___acrt_iob_func_0
0x140002e47  lea     r9, a0xI64x; "0x%I64x"
0x140002e4e  mov     [rsp+68h+var_48], rbx
0x140002e53  jmp     short loc_140002E02
0x140002e55  mov     esi, r12d
0x140002e58  test    ebp, ebp
0x140002e5a  jz      loc_140002EF4
0x140002e60  mov     eax, esi
0x140002e62  mov     ecx, edi; Ix
0x140002e64  movzx   ebx, byte ptr [rax+r14]
0x140002e69  call    _o___acrt_iob_func_0
0x140002e6e  mov     rcx, rax
0x140002e71  mov     dword ptr [rsp+68h+var_48], ebx
0x140002e75  lea     r9, a02x; "%02X"
0x140002e7c  mov     r8d, edi
0x140002e7f  mov     edx, edi
0x140002e81  call    ShowMessageEx
0x140002e86  add     esi, edi
0x140002e88  cmp     esi, ebp
0x140002e8a  jb      short loc_140002E60
0x140002e8c  jmp     short loc_140002EF4
0x140002e8e  cmp     [rsi+30h], r12
0x140002e92  lea     r15, a0; "\\0"
0x140002e99  mov     ebx, r12d
0x140002e9c  cmovnz  r15, [rsi+30h]
0x140002ea1  lea     rsi, [r14+rbp]
0x140002ea5  jmp     short loc_140002EEF
0x140002ea7  cmp     [r14], r12w
0x140002eab  jnz     short loc_140002EB6
0x140002ead  mov     ebx, edi
0x140002eaf  mov     eax, 2
0x140002eb4  jmp     short loc_140002EEC
0x140002eb6  cmp     ebx, edi
0x140002eb8  jnz     short loc_140002ECC
0x140002eba  mov     ecx, edi; Ix
0x140002ebc  call    _o___acrt_iob_func_0
0x140002ec1  mov     rcx, rax; Stream
0x140002ec4  mov     rdx, r15; lpString
0x140002ec7  call    ShowMessage
0x140002ecc  mov     ecx, edi; Ix
0x140002ece  call    _o___acrt_iob_func_0
0x140002ed3  mov     rcx, rax; Stream
0x140002ed6  mov     rdx, r14; lpString
0x140002ed9  call    ShowMessage
0x140002ede  mov     rcx, r14; lpString
0x140002ee1  call    cs:__imp_lstrlenW
0x140002ee7  mov     eax, eax
0x140002ee9  add     rax, rax
0x140002eec  add     r14, rax
0x140002eef  cmp     r14, rsi
0x140002ef2  jb      short loc_140002EA7
0x140002ef4  mov     ecx, edi; Ix
0x140002ef6  call    _o___acrt_iob_func_0
0x140002efb  mov     rcx, rax; Stream
0x140002efe  lea     rdx, asc_140010950; "\n"
0x140002f05  call    ShowMessage
0x140002f0a  mov     eax, edi
0x140002f0c  jmp     short loc_140002F1B
0x140002f0e  mov     ecx, 57h ; 'W'; dwErrCode
0x140002f13  call    cs:__imp_SetLastError
0x140002f19  xor     eax, eax
0x140002f1b  add     rsp, 30h
0x140002f1f  pop     r15
0x140002f21  pop     r14
0x140002f23  pop     r12
0x140002f25  pop     rdi
0x140002f26  pop     rsi
0x140002f27  pop     rbp
0x140002f28  pop     rbx
0x140002f29  retn
```
