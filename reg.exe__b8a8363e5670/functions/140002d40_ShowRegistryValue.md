# ShowRegistryValue

- ea: `0x140002d40`
- end: `0x140003060`
- name: `ShowRegistryValue`
- size: `800`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1400061e4`
- `0x140009b2c`

## callees

- `0x140001bb2`
- `0x14000228c`
- `0x140002d40`
- `0x14000d694`
- `0x14000e864`
- `0x14000ec2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003042`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003042`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140002dd3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000300a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140002dd3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000300a`

## pseudocode

```c
__int64 __fastcall ShowRegistryValue(unsigned int *a1, __int64 a2)
{
  unsigned int v4; // ebx
  FILE *v5; // rax
  const WCHAR *ResString2FromModule; // rbx
  __int64 v7; // rcx
  unsigned int v8; // ebp
  FILE *v9; // rax
  FILE *v10; // rax
  const WCHAR *v11; // rbx
  FILE *v12; // rcx
  const WCHAR *v13; // rdx
  int v14; // ebp
  __int64 v15; // r8
  __int64 TypeStrFromType; // rbx
  FILE *v17; // rax
  const WCHAR *v18; // rbx
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
    goto LABEL_54;
  if ( (a1[7] & 0xF) == 0xF )
    return 1;
  v4 = a1[8];
  if ( v4 )
  {
    v5 = o___acrt_iob_func_0(1u);
    ShowMessageEx(v5, 1, 1, L"%*s", v4, L" ");
  }
  if ( (a1[7] & 1) == 0 )
  {
    ResString2FromModule = (const WCHAR *)*((_QWORD *)a1 + 2);
    if ( !ResString2FromModule || *((_QWORD *)a1 + 5) && (a1[7] & 0x10) != 0 )
      goto LABEL_54;
    if ( !lstrlenW(*((LPCWSTR *)a1 + 2)) )
      ResString2FromModule = (const WCHAR *)GetResString2FromModule(v7, 501, 0);
    if ( (a1[7] & 0x10) != 0 )
    {
      v8 = a1[6];
      if ( !v8 )
        goto LABEL_54;
      v9 = o___acrt_iob_func_0(1u);
      LODWORD(v45) = v8;
      ShowMessageEx(v9, 2, 1, L"%-*s", v45, ResString2FromModule);
    }
    else
    {
      v10 = o___acrt_iob_func_0(1u);
      ShowMessage(v10, ResString2FromModule);
    }
    v11 = (const WCHAR *)*((_QWORD *)a1 + 5);
    v12 = o___acrt_iob_func_0(1u);
    v13 = v11;
    if ( !v11 )
      v13 = L" ";
    ShowMessage(v12, v13);
  }
  if ( (a1[7] & 2) == 0 )
  {
    v14 = *a1;
    v15 = *a1;
    if ( (a1[7] & 0x20) != 0 )
    {
      TypeStrFromType = GetTypeStrFromType(a1, a2, v15);
      v17 = o___acrt_iob_func_0(1u);
      LODWORD(v46) = v14;
      ShowMessageEx(v17, 2, 1, L"%s (%d)", TypeStrFromType, v46);
    }
    else
    {
      v18 = (const WCHAR *)GetTypeStrFromType(a1, a2, v15);
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
    goto LABEL_53;
  v23 = (const WCHAR *)*((_QWORD *)a1 + 1);
  if ( v23 )
  {
    v24 = a1[1];
    if ( (_DWORD)v24 )
    {
      v25 = *a1;
      if ( *a1 > 6 )
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
          goto LABEL_53;
        }
        if ( v32 == 4 )
        {
          v33 = *(_QWORD *)v23;
          v34 = o___acrt_iob_func_0(1u);
          ShowMessageEx(v34, 1, 1, L"0x%I64x", v33);
          goto LABEL_53;
        }
      }
      else if ( v25 != 6 )
      {
        v26 = v25 - 1;
        if ( !v26 || (v27 = v26 - 1) == 0 )
        {
          v31 = o___acrt_iob_func_0(1u);
          ShowMessage(v31, v23);
          goto LABEL_53;
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
            goto LABEL_53;
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
LABEL_53:
    v44 = o___acrt_iob_func_0(1u);
    ShowMessage(v44, L"\n");
    return 1;
  }
LABEL_54:
  SetLastError(0x57u);
  return 0;
}

```

## disassembly

```asm
0x140002d40  push    rbx
0x140002d42  push    rbp
0x140002d43  push    rsi
0x140002d44  push    rdi
0x140002d45  push    r12
0x140002d47  push    r14
0x140002d49  push    r15
0x140002d4b  sub     rsp, 30h
0x140002d4f  xor     r12d, r12d
0x140002d52  mov     rsi, rcx
0x140002d55  test    rcx, rcx
0x140002d58  jz      loc_14000303D
0x140002d5e  mov     eax, [rcx+1Ch]
0x140002d61  and     eax, 0Fh
0x140002d64  cmp     al, 0Fh
0x140002d66  jnz     short loc_140002D72
0x140002d68  lea     eax, [r12+1]
0x140002d6d  jmp     loc_140003050
0x140002d72  mov     ebx, [rcx+20h]
0x140002d75  lea     r14, asc_140011954; " "
0x140002d7c  mov     edi, 1
0x140002d81  test    ebx, ebx
0x140002d83  jz      short loc_140002DA9
0x140002d85  mov     ecx, edi; Ix
0x140002d87  call    _o___acrt_iob_func_0
0x140002d8c  mov     rcx, rax
0x140002d8f  mov     [rsp+68h+var_40], r14
0x140002d94  lea     r9, aS_1; "%*s"
0x140002d9b  mov     dword ptr [rsp+68h+var_48], ebx
0x140002d9f  mov     r8d, edi
0x140002da2  mov     edx, edi
0x140002da4  call    ShowMessageEx
0x140002da9  test    [rsi+1Ch], dil
0x140002dad  jnz     loc_140002E5D
0x140002db3  mov     rbx, [rsi+10h]
0x140002db7  test    rbx, rbx
0x140002dba  jz      loc_14000303D
0x140002dc0  cmp     [rsi+28h], r12
0x140002dc4  jz      short loc_140002DD0
0x140002dc6  test    byte ptr [rsi+1Ch], 10h
0x140002dca  jnz     loc_14000303D
0x140002dd0  mov     rcx, rbx; lpString
0x140002dd3  call    cs:__imp_lstrlenW
0x140002dda  nop     dword ptr [rax+rax+00h]
0x140002ddf  test    eax, eax
0x140002de1  jnz     short loc_140002DF3
0x140002de3  xor     r8d, r8d
0x140002de6  mov     edx, 1F5h
0x140002deb  call    GetResString2FromModule
0x140002df0  mov     rbx, rax
0x140002df3  test    byte ptr [rsi+1Ch], 10h
0x140002df7  jz      short loc_140002E2D
0x140002df9  mov     ebp, [rsi+18h]
0x140002dfc  test    ebp, ebp
0x140002dfe  jz      loc_14000303D
0x140002e04  mov     ecx, edi; Ix
0x140002e06  call    _o___acrt_iob_func_0
0x140002e0b  mov     rcx, rax
0x140002e0e  mov     [rsp+68h+var_40], rbx
0x140002e13  lea     r9, aS; "%-*s"
0x140002e1a  mov     dword ptr [rsp+68h+var_48], ebp
0x140002e1e  mov     r8d, edi
0x140002e21  mov     edx, 2
0x140002e26  call    ShowMessageEx
0x140002e2b  jmp     short loc_140002E3F
0x140002e2d  mov     ecx, edi; Ix
0x140002e2f  call    _o___acrt_iob_func_0
0x140002e34  mov     rcx, rax; Stream
0x140002e37  mov     rdx, rbx; lpString
0x140002e3a  call    ShowMessage
0x140002e3f  mov     rbx, [rsi+28h]
0x140002e43  mov     ecx, edi; Ix
0x140002e45  call    _o___acrt_iob_func_0
0x140002e4a  mov     rcx, rax; Stream
0x140002e4d  mov     rdx, rbx
0x140002e50  test    rbx, rbx
0x140002e53  jnz     short loc_140002E58
0x140002e55  mov     rdx, r14; lpString
0x140002e58  call    ShowMessage
0x140002e5d  test    byte ptr [rsi+1Ch], 2
0x140002e61  jnz     short loc_140002ED7
0x140002e63  test    byte ptr [rsi+1Ch], 20h
0x140002e67  mov     ebp, [rsi]
0x140002e69  mov     r8d, ebp
0x140002e6c  jz      short loc_140002E9F
0x140002e6e  call    GetTypeStrFromType
0x140002e73  mov     ecx, edi; Ix
0x140002e75  mov     rbx, rax
0x140002e78  call    _o___acrt_iob_func_0
0x140002e7d  mov     rcx, rax
0x140002e80  mov     dword ptr [rsp+68h+var_40], ebp
0x140002e84  lea     r9, aSD; "%s (%d)"
0x140002e8b  mov     [rsp+68h+var_48], rbx
0x140002e90  mov     r8d, edi
0x140002e93  mov     edx, 2
0x140002e98  call    ShowMessageEx
0x140002e9d  jmp     short loc_140002EB9
0x140002e9f  call    GetTypeStrFromType
0x140002ea4  mov     ecx, edi; Ix
0x140002ea6  mov     rbx, rax
0x140002ea9  call    _o___acrt_iob_func_0
0x140002eae  mov     rcx, rax; Stream
0x140002eb1  mov     rdx, rbx; lpString
0x140002eb4  call    ShowMessage
0x140002eb9  mov     rbx, [rsi+28h]
0x140002ebd  mov     ecx, edi; Ix
0x140002ebf  call    _o___acrt_iob_func_0
0x140002ec4  mov     rcx, rax; Stream
0x140002ec7  mov     rdx, rbx
0x140002eca  test    rbx, rbx
0x140002ecd  jnz     short loc_140002ED2
0x140002ecf  mov     rdx, r14; lpString
0x140002ed2  call    ShowMessage
0x140002ed7  test    byte ptr [rsi+1Ch], 4
0x140002edb  jnz     loc_140003023
0x140002ee1  mov     r14, [rsi+8]
0x140002ee5  test    r14, r14
0x140002ee8  jz      loc_14000303D
0x140002eee  mov     ebp, [rsi+4]
0x140002ef1  test    ebp, ebp
0x140002ef3  jz      loc_140003023
0x140002ef9  mov     eax, [rsi]
0x140002efb  cmp     eax, 6
0x140002efe  ja      short loc_140002F54
0x140002f00  jz      short loc_140002F7E
0x140002f02  sub     eax, edi
0x140002f04  jz      short loc_140002F3D
0x140002f06  sub     eax, edi
0x140002f08  jz      short loc_140002F3D
0x140002f0a  sub     eax, edi
0x140002f0c  jz      short loc_140002F7E
0x140002f0e  sub     eax, edi
0x140002f10  jz      short loc_140002F16
0x140002f12  cmp     eax, edi
0x140002f14  jnz     short loc_140002F7E
0x140002f16  mov     ebx, [r14]
0x140002f19  mov     ecx, edi; Ix
0x140002f1b  call    _o___acrt_iob_func_0
0x140002f20  lea     r9, a0xX; "0x%x"
0x140002f27  mov     dword ptr [rsp+68h+var_48], ebx
0x140002f2b  mov     rcx, rax
0x140002f2e  mov     r8d, edi
0x140002f31  mov     edx, edi
0x140002f33  call    ShowMessageEx
0x140002f38  jmp     loc_140003023
0x140002f3d  mov     ecx, edi; Ix
0x140002f3f  call    _o___acrt_iob_func_0
0x140002f44  mov     rcx, rax; Stream
0x140002f47  mov     rdx, r14; lpString
0x140002f4a  call    ShowMessage
0x140002f4f  jmp     loc_140003023
0x140002f54  sub     eax, 7
0x140002f57  jz      short loc_140002FB7
0x140002f59  sub     eax, edi
0x140002f5b  jz      short loc_140002F7E
0x140002f5d  sub     eax, edi
0x140002f5f  jz      short loc_140002F7E
0x140002f61  cmp     eax, 2
0x140002f64  jnz     short loc_140002F7E
0x140002f66  mov     rbx, [r14]
0x140002f69  mov     ecx, edi; Ix
0x140002f6b  call    _o___acrt_iob_func_0
0x140002f70  lea     r9, a0xI64x; "0x%I64x"
0x140002f77  mov     [rsp+68h+var_48], rbx
0x140002f7c  jmp     short loc_140002F2B
0x140002f7e  mov     esi, r12d
0x140002f81  test    ebp, ebp
0x140002f83  jz      loc_140003023
0x140002f89  mov     eax, esi
0x140002f8b  mov     ecx, edi; Ix
0x140002f8d  movzx   ebx, byte ptr [rax+r14]
0x140002f92  call    _o___acrt_iob_func_0
0x140002f97  mov     rcx, rax
0x140002f9a  mov     dword ptr [rsp+68h+var_48], ebx
0x140002f9e  lea     r9, a02x; "%02X"
0x140002fa5  mov     r8d, edi
0x140002fa8  mov     edx, edi
0x140002faa  call    ShowMessageEx
0x140002faf  add     esi, edi
0x140002fb1  cmp     esi, ebp
0x140002fb3  jb      short loc_140002F89
0x140002fb5  jmp     short loc_140003023
0x140002fb7  cmp     [rsi+30h], r12
0x140002fbb  lea     r15, a0; "\\0"
0x140002fc2  mov     ebx, r12d
0x140002fc5  cmovnz  r15, [rsi+30h]
0x140002fca  lea     rsi, [r14+rbp]
0x140002fce  jmp     short loc_14000301E
0x140002fd0  cmp     [r14], r12w
0x140002fd4  jnz     short loc_140002FDF
0x140002fd6  mov     ebx, edi
0x140002fd8  mov     eax, 2
0x140002fdd  jmp     short loc_14000301B
0x140002fdf  cmp     ebx, edi
0x140002fe1  jnz     short loc_140002FF5
0x140002fe3  mov     ecx, edi; Ix
0x140002fe5  call    _o___acrt_iob_func_0
0x140002fea  mov     rcx, rax; Stream
0x140002fed  mov     rdx, r15; lpString
0x140002ff0  call    ShowMessage
0x140002ff5  mov     ecx, edi; Ix
0x140002ff7  call    _o___acrt_iob_func_0
0x140002ffc  mov     rcx, rax; Stream
0x140002fff  mov     rdx, r14; lpString
0x140003002  call    ShowMessage
0x140003007  mov     rcx, r14; lpString
0x14000300a  call    cs:__imp_lstrlenW
0x140003011  nop     dword ptr [rax+rax+00h]
0x140003016  mov     eax, eax
0x140003018  add     rax, rax
0x14000301b  add     r14, rax
0x14000301e  cmp     r14, rsi
0x140003021  jb      short loc_140002FD0
0x140003023  mov     ecx, edi; Ix
0x140003025  call    _o___acrt_iob_func_0
0x14000302a  mov     rcx, rax; Stream
0x14000302d  lea     rdx, asc_140011950; "\n"
0x140003034  call    ShowMessage
0x140003039  mov     eax, edi
0x14000303b  jmp     short loc_140003050
0x14000303d  mov     ecx, 57h ; 'W'; dwErrCode
0x140003042  call    cs:__imp_SetLastError
0x140003049  nop     dword ptr [rax+rax+00h]
0x14000304e  xor     eax, eax
0x140003050  add     rsp, 30h
0x140003054  pop     r15
0x140003056  pop     r14
0x140003058  pop     r12
0x14000305a  pop     rdi
0x14000305b  pop     rsi
0x14000305c  pop     rbp
0x14000305d  pop     rbx
0x14000305e  retn
```
