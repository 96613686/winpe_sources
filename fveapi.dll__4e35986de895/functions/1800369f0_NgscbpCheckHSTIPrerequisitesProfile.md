# NgscbpCheckHSTIPrerequisitesProfile

- ea: `0x1800369f0`
- end: `0x180036f02`
- name: `NgscbpCheckHSTIPrerequisitesProfile`
- size: `1298`
- prototype: `__int64 __fastcall(HKEY hkey)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800362e4`
- `0x180036fbc`

## callees

- `0x180008d70`
- `0x1800090c0`
- `0x180009130`
- `0x1800369f0`
- `0x180037e78`
- `0x180037edc`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `msvcrt!wcstoul` at `0x180036baa`
- `msvcrt!wcstoul` at `0x180036baa`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180036a9c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180036a9c`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180036b52`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180036b52`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180036e33`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180036e33`

## pseudocode

```c
__int64 __fastcall NgscbpCheckHSTIPrerequisitesProfile(HKEY hkey, _BYTE *a2, unsigned int *a3)
{
  _BYTE *v4; // r13
  unsigned int v6; // r12d
  LSTATUS ValueW; // eax
  unsigned int v8; // ebx
  PVOID *v9; // rcx
  char *v10; // r15
  unsigned int v11; // r14d
  DWORD j; // eax
  LSTATUS v13; // eax
  unsigned int v14; // eax
  PVOID *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  unsigned int i; // r15d
  __int64 v20; // r12
  char *v21; // r13
  unsigned int v22; // eax
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchValueName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  BYTE Data[4]; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v27; // [rsp+50h] [rbp-B0h]
  _BYTE *v28; // [rsp+58h] [rbp-A8h]
  wchar_t *EndPtr; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h]
  WCHAR ValueName[24]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR String1[256]; // [rsp+A0h] [rbp-60h] BYREF

  v28 = a2;
  v4 = a2;
  hKey = hkey;
  memset_0(String1, 0, sizeof(String1));
  v6 = 0;
  EndPtr = 0;
  *(_DWORD *)Data = 0;
  cchValueName = 0;
  Type = 0;
  if ( !v4 )
  {
    v8 = -2147467261;
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      return v8;
    v16 = 107;
    goto LABEL_50;
  }
  if ( !a3 )
  {
    v8 = -2147024809;
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      return v8;
    v16 = 108;
LABEL_50:
    v17 = v8;
    goto LABEL_34;
  }
  cbData = 512;
  ValueW = RegGetValueW(hkey, 0, L"ImplementationId", 2u, 0, String1, &cbData);
  v8 = ValueW;
  if ( ValueW > 0 )
    v8 = (unsigned __int16)ValueW | 0x80070000;
  if ( v8 == -2147024894 )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    String1[0] = 0;
  }
  else
  {
    if ( v8 )
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v8);
        v9 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( (v8 & 0x80000000) != 0 )
        return v8;
    }
    else
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( String1[0] )
    {
      if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 )
        WPP_SF_S(v9[2], 111, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, String1);
      for ( i = 0; ; ++i )
      {
        if ( i >= a3[5] )
          goto LABEL_77;
        v20 = a3[4];
        v21 = (char *)a3 + i * (a3[3] + 520LL);
        if ( CompareStringOrdinal(String1, 256, (LPCWCH)&v21[v20 + 8], 256, 1) == 2 )
          break;
      }
      v10 = &v21[v20 + 520];
      if ( !v10 )
      {
LABEL_77:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, String1);
        *v28 = 0;
        return v8;
      }
      v22 = *(_DWORD *)&v21[v20 + 4];
      v6 = 0;
      v4 = v28;
      v27 = v22;
      goto LABEL_10;
    }
  }
  v10 = (char *)a3 + a3[2];
  v27 = a3[3];
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 )
    WPP_SF_(v9[2], 110, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids);
LABEL_10:
  v11 = 0;
  for ( j = 0; ; j = (_DWORD)v28 + 1 )
  {
    LODWORD(v28) = j;
    cchValueName = 21;
    cbData = 4;
    v13 = RegEnumValueW(hKey, j, ValueName, &cchValueName, 0, &Type, Data, &cbData);
    v8 = v13;
    if ( v13 > 0 )
      v8 = (unsigned __int16)v13 | 0x80070000;
    if ( v8 == -2147024637 )
      break;
    if ( v8 != -2147024662 )
    {
      if ( v8 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v8);
        if ( (v8 & 0x80000000) != 0 )
          return v8;
      }
      if ( Type == 4 )
      {
        v14 = wcstoul(ValueName, &EndPtr, 10);
        if ( v14 != -1 && EndPtr != ValueName && EndPtr && !*EndPtr && Data[0] )
        {
          if ( v14 >= v27 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v14);
            ++v11;
            goto LABEL_28;
          }
          if ( (Data[0] & (unsigned __int8)v10[v14]) != Data[0] )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_dDD(*((_QWORD *)WPP_GLOBAL_Control + 2));
            ++v11;
LABEL_28:
            *v4 = 0;
            continue;
          }
          ++v6;
        }
      }
    }
  }
  v8 = 0;
  if ( v11 )
  {
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v11, v6);
      v15 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( !*v4 )
      return v8;
    v8 = -2147418113;
    if ( v15 == &WPP_GLOBAL_Control || (*((_BYTE *)v15 + 28) & 0x40) == 0 )
      return v8;
    v16 = 117;
    v17 = 2147549183LL;
LABEL_34:
    WPP_SF_d(v15[2], v16, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v17);
    return v8;
  }
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v16 = 118;
    v17 = v6;
    goto LABEL_34;
  }
  return v8;
}

```

## disassembly

```asm
0x1800369f0  mov     [rsp-8+arg_18], rbx
0x1800369f5  push    rbp
0x1800369f6  push    rsi
0x1800369f7  push    rdi
0x1800369f8  push    r12
0x1800369fa  push    r13
0x1800369fc  push    r14
0x1800369fe  push    r15
0x180036a00  lea     rbp, [rsp-1B0h]
0x180036a08  sub     rsp, 2B0h
0x180036a0f  mov     rax, cs:__security_cookie
0x180036a16  xor     rax, rsp
0x180036a19  mov     [rbp+1E0h+var_40], rax
0x180036a20  mov     r14, r8
0x180036a23  mov     [rsp+2E0h+var_288], rdx
0x180036a28  mov     r13, rdx
0x180036a2b  mov     [rsp+2E0h+hKey], rcx
0x180036a30  mov     rbx, rcx
0x180036a33  mov     edi, 200h
0x180036a38  mov     r8d, edi; Size
0x180036a3b  lea     rcx, [rbp+1E0h+String1]; void *
0x180036a3f  xor     edx, edx; Val
0x180036a41  call    memset_0
0x180036a46  xor     r12d, r12d
0x180036a49  mov     [rsp+2E0h+EndPtr], r12
0x180036a4e  mov     dword ptr [rsp+2E0h+Data], r12d
0x180036a53  mov     [rsp+2E0h+cchValueName], r12d
0x180036a58  mov     [rsp+2E0h+Type], r12d
0x180036a5d  test    r13, r13
0x180036a60  jz      loc_180036D2E
0x180036a66  test    r14, r14
0x180036a69  jz      loc_180036D6F
0x180036a6f  lea     rax, [rsp+2E0h+cbData]
0x180036a74  mov     [rsp+2E0h+cbData], edi
0x180036a78  mov     [rsp+2E0h+pcbData], rax; pcbData
0x180036a7d  lea     r9d, [r12+2]; dwFlags
0x180036a82  lea     rax, [rbp+1E0h+String1]
0x180036a86  xor     edx, edx; lpSubKey
0x180036a88  mov     [rsp+2E0h+pvData], rax; pvData
0x180036a8d  lea     r8, Value; "ImplementationId"
0x180036a94  mov     rcx, rbx; hkey
0x180036a97  mov     [rsp+2E0h+pdwType], r12; pdwType
0x180036a9c  call    cs:__imp_RegGetValueW
0x180036aa3  nop     dword ptr [rax+rax+00h]
0x180036aa8  mov     ebx, eax
0x180036aaa  test    eax, eax
0x180036aac  jle     short loc_180036AB7
0x180036aae  movzx   ebx, ax
0x180036ab1  or      ebx, 80070000h
0x180036ab7  lea     rdi, WPP_GLOBAL_Control
0x180036abe  lea     rsi, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x180036ac5  cmp     ebx, 80070002h
0x180036acb  jz      loc_180036CBA
0x180036ad1  test    ebx, ebx
0x180036ad3  jnz     loc_180036D97
0x180036ad9  mov     rcx, cs:WPP_GLOBAL_Control
0x180036ae0  cmp     [rbp+1E0h+String1], r12w
0x180036ae5  jnz     loc_180036DD1
0x180036aeb  mov     r15d, [r14+8]
0x180036aef  mov     edx, [r14+0Ch]
0x180036af3  add     r15, r14
0x180036af6  mov     [rsp+2E0h+var_290], edx
0x180036afa  cmp     rcx, rdi
0x180036afd  jnz     loc_180036C9A
0x180036b03  xor     edx, edx
0x180036b05  mov     r14d, edx
0x180036b08  mov     eax, edx
0x180036b0a  lea     rcx, [rsp+2E0h+cbData]
0x180036b0f  mov     dword ptr [rsp+2E0h+var_288], eax
0x180036b13  mov     [rsp+2E0h+lpcbData], rcx; lpcbData
0x180036b18  lea     r9, [rsp+2E0h+cchValueName]; lpcchValueName
0x180036b1d  lea     rcx, [rsp+2E0h+Data]
0x180036b22  mov     [rsp+2E0h+cchValueName], 15h
0x180036b2a  mov     [rsp+2E0h+pcbData], rcx; lpData
0x180036b2f  lea     r8, [rsp+2E0h+ValueName]; lpValueName
0x180036b34  lea     rcx, [rsp+2E0h+Type]
0x180036b39  mov     [rsp+2E0h+cbData], 4
0x180036b41  mov     [rsp+2E0h+pvData], rcx; lpType
0x180036b46  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180036b4b  mov     [rsp+2E0h+pdwType], rdx; lpReserved
0x180036b50  mov     edx, eax; dwIndex
0x180036b52  call    cs:__imp_RegEnumValueW
0x180036b59  nop     dword ptr [rax+rax+00h]
0x180036b5e  xor     edx, edx
0x180036b60  mov     ebx, eax
0x180036b62  test    eax, eax
0x180036b64  jle     short loc_180036B6F
0x180036b66  movzx   ebx, ax
0x180036b69  or      ebx, 80070000h
0x180036b6f  cmp     ebx, 80070103h
0x180036b75  jz      loc_180036C36
0x180036b7b  cmp     ebx, 800700EAh
0x180036b81  jz      loc_180036C2B
0x180036b87  test    ebx, ebx
0x180036b89  jnz     loc_180036E6C
0x180036b8f  cmp     [rsp+2E0h+Type], 4
0x180036b94  jnz     loc_180036C2B
0x180036b9a  mov     r8d, 0Ah; Radix
0x180036ba0  lea     rdx, [rsp+2E0h+EndPtr]; EndPtr
0x180036ba5  lea     rcx, [rsp+2E0h+ValueName]; String
0x180036baa  call    cs:__imp_wcstoul
0x180036bb1  nop     dword ptr [rax+rax+00h]
0x180036bb6  xor     edx, edx
0x180036bb8  mov     r9d, eax
0x180036bbb  cmp     eax, 0FFFFFFFFh
0x180036bbe  jz      short loc_180036C2B
0x180036bc0  mov     rcx, [rsp+2E0h+EndPtr]
0x180036bc5  lea     rax, [rsp+2E0h+ValueName]
0x180036bca  cmp     rcx, rax
0x180036bcd  jz      short loc_180036C2B
0x180036bcf  test    rcx, rcx
0x180036bd2  jz      short loc_180036C2B
0x180036bd4  cmp     [rcx], dx
0x180036bd7  jnz     short loc_180036C2B
0x180036bd9  movzx   ecx, [rsp+2E0h+Data]
0x180036bde  test    cl, cl
0x180036be0  jz      short loc_180036C2B
0x180036be2  cmp     r9d, [rsp+2E0h+var_290]
0x180036be7  jnb     loc_180036EA1
0x180036bed  movzx   edx, byte ptr [r9+r15]
0x180036bf2  mov     al, dl
0x180036bf4  and     al, cl
0x180036bf6  cmp     al, cl
0x180036bf8  jz      loc_180036C93
0x180036bfe  mov     r8, cs:WPP_GLOBAL_Control
0x180036c05  cmp     r8, rdi
0x180036c08  jz      short loc_180036C22
0x180036c0a  test    byte ptr [r8+1Ch], 4
0x180036c0f  jz      short loc_180036C22
0x180036c11  mov     dword ptr [rsp+2E0h+pvData], edx
0x180036c15  mov     dword ptr [rsp+2E0h+pdwType], ecx
0x180036c19  mov     rcx, [r8+10h]
0x180036c1d  call    WPP_SF_dDD
0x180036c22  inc     r14d
0x180036c25  xor     edx, edx
0x180036c27  mov     [r13+0], dl
0x180036c2b  mov     eax, dword ptr [rsp+2E0h+var_288]
0x180036c2f  inc     eax
0x180036c31  jmp     loc_180036B0A
0x180036c36  mov     ebx, edx
0x180036c38  test    r14d, r14d
0x180036c3b  jnz     loc_180036CCB
0x180036c41  mov     rcx, cs:WPP_GLOBAL_Control
0x180036c48  cmp     rcx, rdi
0x180036c4b  jz      short loc_180036C66
0x180036c4d  test    byte ptr [rcx+1Ch], 8
0x180036c51  jz      short loc_180036C66
0x180036c53  lea     edx, [r14+76h]
0x180036c57  mov     r9d, r12d
0x180036c5a  mov     r8, rsi
0x180036c5d  mov     rcx, [rcx+10h]
0x180036c61  call    WPP_SF_d
0x180036c66  mov     eax, ebx
0x180036c68  mov     rcx, [rbp+1E0h+var_40]
0x180036c6f  xor     rcx, rsp; StackCookie
0x180036c72  call    __security_check_cookie
0x180036c77  mov     rbx, [rsp+2E0h+arg_18]
0x180036c7f  add     rsp, 2B0h
0x180036c86  pop     r15
0x180036c88  pop     r14
0x180036c8a  pop     r13
0x180036c8c  pop     r12
0x180036c8e  pop     rdi
0x180036c8f  pop     rsi
0x180036c90  pop     rbp
0x180036c91  retn
0x180036c93  inc     r12d
0x180036c96  xor     edx, edx
0x180036c98  jmp     short loc_180036C2B
0x180036c9a  test    byte ptr [rcx+1Ch], 8
0x180036c9e  jz      loc_180036B03
0x180036ca4  mov     rcx, [rcx+10h]
0x180036ca8  mov     edx, 6Eh ; 'n'
0x180036cad  mov     r8, rsi
0x180036cb0  call    WPP_SF_
0x180036cb5  jmp     loc_180036B03
0x180036cba  mov     rcx, cs:WPP_GLOBAL_Control
0x180036cc1  mov     [rbp+1E0h+String1], r12w
0x180036cc6  jmp     loc_180036AEB
0x180036ccb  mov     rcx, cs:WPP_GLOBAL_Control
0x180036cd2  cmp     rcx, rdi
0x180036cd5  jz      short loc_180036CFF
0x180036cd7  test    byte ptr [rcx+1Ch], 4
0x180036cdb  jz      short loc_180036CFF
0x180036cdd  mov     rcx, [rcx+10h]
0x180036ce1  mov     edx, 74h ; 't'
0x180036ce6  mov     r9d, r14d
0x180036ce9  mov     dword ptr [rsp+2E0h+pdwType], r12d
0x180036cee  mov     r8, rsi
0x180036cf1  call    WPP_SF_Dd
0x180036cf6  mov     rcx, cs:WPP_GLOBAL_Control
0x180036cfd  xor     edx, edx
0x180036cff  cmp     [r13+0], dl
0x180036d03  jz      loc_180036C66
0x180036d09  mov     ebx, 8000FFFFh
0x180036d0e  cmp     rcx, rdi
0x180036d11  jz      loc_180036C66
0x180036d17  test    byte ptr [rcx+1Ch], 40h
0x180036d1b  jz      loc_180036C66
0x180036d21  mov     edx, 75h ; 'u'
0x180036d26  mov     r9d, ebx
0x180036d29  jmp     loc_180036C5A
0x180036d2e  mov     ebx, 80004003h
0x180036d33  mov     rcx, cs:WPP_GLOBAL_Control
0x180036d3a  lea     rdi, WPP_GLOBAL_Control
0x180036d41  cmp     rcx, rdi
0x180036d44  jz      loc_180036C66
0x180036d4a  test    byte ptr [rcx+1Ch], 40h
0x180036d4e  jz      loc_180036C66
0x180036d54  mov     edx, 6Bh ; 'k'
0x180036d59  jmp     short loc_180036D60
0x180036d5b  mov     edx, 6Ch ; 'l'
0x180036d60  mov     r9d, ebx
0x180036d63  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x180036d6a  jmp     loc_180036C5D
0x180036d6f  mov     ebx, 80070057h
0x180036d74  mov     rcx, cs:WPP_GLOBAL_Control
0x180036d7b  lea     rdi, WPP_GLOBAL_Control
0x180036d82  cmp     rcx, rdi
0x180036d85  jz      loc_180036C66
0x180036d8b  test    byte ptr [rcx+1Ch], 40h
0x180036d8f  jz      loc_180036C66
0x180036d95  jmp     short loc_180036D5B
0x180036d97  mov     rcx, cs:WPP_GLOBAL_Control
0x180036d9e  cmp     rcx, rdi
0x180036da1  jz      short loc_180036DC4
0x180036da3  test    byte ptr [rcx+1Ch], 40h
0x180036da7  jz      short loc_180036DC4
0x180036da9  mov     rcx, [rcx+10h]
0x180036dad  mov     edx, 6Dh ; 'm'
0x180036db2  mov     r9d, ebx
0x180036db5  mov     r8, rsi
0x180036db8  call    WPP_SF_d
0x180036dbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180036dc4  test    ebx, ebx
0x180036dc6  js      loc_180036C66
0x180036dcc  jmp     loc_180036AE0
0x180036dd1  cmp     rcx, rdi
0x180036dd4  jz      short loc_180036DF1
0x180036dd6  test    byte ptr [rcx+1Ch], 8
0x180036dda  jz      short loc_180036DF1
0x180036ddc  mov     rcx, [rcx+10h]
0x180036de0  lea     r9, [rbp+1E0h+String1]
0x180036de4  mov     edx, 6Fh ; 'o'
0x180036de9  mov     r8, rsi
0x180036dec  call    WPP_SF_S
0x180036df1  mov     r15d, r12d
0x180036df4  cmp     r15d, [r14+14h]
0x180036df8  jnb     loc_180036ECE
0x180036dfe  mov     r13d, [r14+0Ch]
0x180036e02  lea     rcx, [rbp+1E0h+String1]; lpString1
0x180036e06  mov     r12d, [r14+10h]
0x180036e0a  add     r13, 208h
0x180036e11  mov     eax, r15d
0x180036e14  mov     edx, 100h; cchCount1
0x180036e19  imul    r13, rax
0x180036e1d  mov     r9d, edx; cchCount2
0x180036e20  mov     dword ptr [rsp+2E0h+pdwType], 1; bIgnoreCase
0x180036e28  add     r13, r14
0x180036e2b  lea     r8, [r12+8]
0x180036e30  add     r8, r13; lpString2
0x180036e33  call    cs:__imp_CompareStringOrdinal
0x180036e3a  nop     dword ptr [rax+rax+00h]
0x180036e3f  cmp     eax, 2
0x180036e42  jz      short loc_180036E49
0x180036e44  inc     r15d
0x180036e47  jmp     short loc_180036DF4
0x180036e49  lea     r15, [r12+208h]
0x180036e51  add     r15, r13
0x180036e54  jz      short loc_180036ECE
0x180036e56  mov     eax, [r12+r13+4]
0x180036e5b  xor     r12d, r12d
0x180036e5e  mov     r13, [rsp+2E0h+var_288]
0x180036e63  mov     [rsp+2E0h+var_290], eax
0x180036e67  jmp     loc_180036B03
0x180036e6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180036e73  cmp     rcx, rdi
0x180036e76  jz      short loc_180036E94
0x180036e78  test    byte ptr [rcx+1Ch], 40h
0x180036e7c  jz      short loc_180036E94
0x180036e7e  mov     rcx, [rcx+10h]
0x180036e82  mov     edx, 71h ; 'q'
0x180036e87  mov     r9d, ebx
0x180036e8a  mov     r8, rsi
0x180036e8d  call    WPP_SF_d
0x180036e92  xor     edx, edx
0x180036e94  test    ebx, ebx
0x180036e96  js      loc_180036C66
0x180036e9c  jmp     loc_180036B8F
0x180036ea1  mov     rcx, cs:WPP_GLOBAL_Control
0x180036ea8  cmp     rcx, rdi
0x180036eab  jz      short loc_180036EC6
0x180036ead  test    byte ptr [rcx+1Ch], 4
0x180036eb1  jz      short loc_180036EC6
0x180036eb3  mov     rcx, [rcx+10h]
0x180036eb7  mov     edx, 72h ; 'r'
0x180036ebc  mov     r8, rsi
0x180036ebf  call    WPP_SF_d
0x180036ec4  xor     edx, edx
0x180036ec6  inc     r14d
  ... truncated ...
```
