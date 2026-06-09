# MakeDirectory

- ea: `0x140066db4`
- end: `0x14006706b`
- name: `MakeDirectory`
- size: `695`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x140073ff0`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140004df0`
- `0x140065dbc`
- `0x140066868`
- `0x140066db4`
- `0x14008187e`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140066e16`
- `KERNEL32!GetLastError` at `0x140066f3c`
- `KERNEL32!GetLastError` at `0x140066fa9`
- `KERNEL32!GetLastError` at `0x140066fc5`
- `KERNEL32!GetLastError` at `0x140066ff6`
- `KERNEL32!GetLastError` at `0x140067003`
- `KERNEL32!GetLastError` at `0x140066e16`
- `KERNEL32!GetLastError` at `0x140066f3c`
- `KERNEL32!GetLastError` at `0x140066fa9`
- `KERNEL32!GetLastError` at `0x140066fc5`
- `KERNEL32!GetLastError` at `0x140066ff6`
- `KERNEL32!GetLastError` at `0x140067003`
- `KERNEL32!SetLastError` at `0x14006704d`
- `KERNEL32!SetLastError` at `0x14006704d`
- `KERNEL32!GetFileAttributesW` at `0x140066e60`
- `KERNEL32!GetFileAttributesW` at `0x140066e60`
- `KERNEL32!CreateDirectoryW` at `0x140066f32`
- `KERNEL32!CreateDirectoryW` at `0x140066f9f`
- `KERNEL32!CreateDirectoryW` at `0x140066fec`
- `KERNEL32!CreateDirectoryW` at `0x140066f32`
- `KERNEL32!CreateDirectoryW` at `0x140066f9f`
- `KERNEL32!CreateDirectoryW` at `0x140066fec`
- `msvcrt!iswalpha` at `0x140066f03`
- `msvcrt!iswalpha` at `0x140066f03`
- `msvcrt!wcschr` at `0x140066ead`
- `msvcrt!wcschr` at `0x140066ec2`
- `msvcrt!wcschr` at `0x140066f88`
- `msvcrt!wcschr` at `0x140066ead`
- `msvcrt!wcschr` at `0x140066ec2`
- `msvcrt!wcschr` at `0x140066f88`

## pseudocode

```c
_BOOL8 __fastcall MakeDirectory(unsigned __int16 *a1)
{
  const WCHAR *v2; // rax
  wchar_t *v3; // rbx
  WCHAR *v4; // rbp
  DWORD LastError; // eax
  DWORD v6; // edi
  DWORD FileAttributesW; // eax
  unsigned __int64 v8; // rdi
  wchar_t *v9; // rax
  DWORD v10; // eax
  CMapDeviceId *v11; // rcx
  int v12; // edx
  wchar_t *v13; // rax
  const wchar_t *v14; // rbx

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_04fb59550d79390d980a26525e0212b0_Traceguids);
  }
  v2 = (const WCHAR *)ExpandEnvironmentString(a1);
  v3 = (wchar_t *)v2;
  v4 = (WCHAR *)v2;
  if ( !v2 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_04fb59550d79390d980a26525e0212b0_Traceguids, LastError);
    }
    goto LABEL_52;
  }
  FileAttributesW = GetFileAttributesW(v2);
  if ( FileAttributesW != -1 && (FileAttributesW & 0x10) != 0 )
  {
LABEL_12:
    v6 = 0;
    goto LABEL_52;
  }
  v8 = -1;
  do
    ++v8;
  while ( v3[v8] );
  if ( v8 <= 2 )
  {
    if ( v8 <= 1 )
      goto LABEL_34;
  }
  else if ( !wcsncmp_0(v3, L"\\\\", 2u) )
  {
    v9 = wcschr(v3 + 2, 0x5Cu);
    v3 = v9;
    if ( !v9 )
      goto LABEL_28;
    v3 = wcschr(v9 + 1, 0x5Cu);
    if ( !v3 )
      goto LABEL_28;
    goto LABEL_22;
  }
  if ( wcsncmp_0(v3, L"\\", 1u) )
  {
    if ( v8 <= 3 || !iswalpha(*v3) || wcsncmp_0(v3 + 1, L":\\", 2u) )
    {
LABEL_34:
      v6 = 0;
      while ( 1 )
      {
        v14 = v3 + 1;
        if ( !*v14 )
          goto LABEL_52;
        v13 = wcschr(v14, 0x5Cu);
        v3 = v13;
        if ( !v13 )
        {
          if ( !CreateDirectoryW(v4, 0) && GetLastError() != 183 )
          {
            v10 = GetLastError();
            v6 = v10;
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v12 = 21;
              goto LABEL_51;
            }
          }
          goto LABEL_52;
        }
        *v13 = 0;
        if ( !CreateDirectoryW(v4, 0) && GetLastError() != 183 )
        {
          v10 = GetLastError();
          v6 = v10;
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v12 = 22;
            goto LABEL_51;
          }
          goto LABEL_52;
        }
        *v3 = 92;
      }
    }
    v3 += 3;
    goto LABEL_27;
  }
LABEL_22:
  ++v3;
LABEL_27:
  if ( v3 )
    goto LABEL_34;
LABEL_28:
  if ( CreateDirectoryW(v4, 0) )
    goto LABEL_34;
  v10 = GetLastError();
  v6 = v10;
  if ( v10 == 183 )
    goto LABEL_12;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v12 = 20;
LABEL_51:
    WPP_SF_Sd(*((_QWORD *)v11 + 2), v12, (unsigned int)WPP_04fb59550d79390d980a26525e0212b0_Traceguids, (_DWORD)v4, v10);
  }
LABEL_52:
  pMemFree(v4);
  if ( v6 )
    SetLastError(v6);
  return v6 == 0;
}

```

## disassembly

```asm
0x140066db4  push    rbx
0x140066db6  push    rbp
0x140066db7  push    rdi
0x140066db8  push    r12
0x140066dba  push    r13
0x140066dbc  push    r14
0x140066dbe  push    r15
0x140066dc0  sub     rsp, 30h
0x140066dc4  mov     rbx, rcx
0x140066dc7  mov     rcx, cs:WPP_GLOBAL_Control
0x140066dce  lea     r12, WPP_GLOBAL_Control
0x140066dd5  mov     r15d, 2
0x140066ddb  cmp     rcx, r12
0x140066dde  jz      short loc_140066E00
0x140066de0  test    [rcx+1Ch], r15b
0x140066de4  jz      short loc_140066E00
0x140066de6  cmp     byte ptr [rcx+19h], 5
0x140066dea  jb      short loc_140066E00
0x140066dec  mov     rcx, [rcx+10h]
0x140066df0  lea     edx, [r15+10h]
0x140066df4  lea     r8, WPP_04fb59550d79390d980a26525e0212b0_Traceguids
0x140066dfb  call    WPP_SF_
0x140066e00  mov     rcx, rbx; unsigned __int16 *
0x140066e03  call    ExpandEnvironmentString
0x140066e08  xor     r14d, r14d
0x140066e0b  mov     rbx, rax
0x140066e0e  mov     rbp, rax
0x140066e11  test    rax, rax
0x140066e14  jnz     short loc_140066E5D
0x140066e16  call    cs:__imp_GetLastError
0x140066e1c  mov     edi, eax
0x140066e1e  mov     rcx, cs:WPP_GLOBAL_Control
0x140066e25  cmp     rcx, r12
0x140066e28  jz      loc_14006703F
0x140066e2e  test    [rcx+1Ch], r15b
0x140066e32  jz      loc_14006703F
0x140066e38  cmp     [rcx+19h], r15b
0x140066e3c  jb      loc_14006703F
0x140066e42  mov     rcx, [rcx+10h]
0x140066e46  lea     edx, [rbp+13h]
0x140066e49  mov     r9d, eax
0x140066e4c  lea     r8, WPP_04fb59550d79390d980a26525e0212b0_Traceguids
0x140066e53  call    WPP_SF_d
0x140066e58  jmp     loc_14006703F
0x140066e5d  mov     rcx, rbx; lpFileName
0x140066e60  call    cs:__imp_GetFileAttributesW
0x140066e66  cmp     eax, 0FFFFFFFFh
0x140066e69  jz      short loc_140066E77
0x140066e6b  test    al, 10h
0x140066e6d  jz      short loc_140066E77
0x140066e6f  mov     edi, r14d
0x140066e72  jmp     loc_14006703F
0x140066e77  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140066e7b  inc     rdi
0x140066e7e  cmp     [rbx+rdi*2], r14w
0x140066e83  jnz     short loc_140066E7B
0x140066e85  mov     r13d, 5Ch ; '\'
0x140066e8b  cmp     rdi, r15
0x140066e8e  jbe     short loc_140066ED2
0x140066e90  mov     r8d, r15d; MaxCount
0x140066e93  lea     rdx, asc_14008F498; "\\\\"
0x140066e9a  mov     rcx, rbx; String1
0x140066e9d  call    wcsncmp_0
0x140066ea2  test    eax, eax
0x140066ea4  jnz     short loc_140066EDC
0x140066ea6  mov     edx, r13d; Ch
0x140066ea9  lea     rcx, [rbx+4]; Str
0x140066ead  call    cs:__imp_wcschr
0x140066eb3  mov     rbx, rax
0x140066eb6  test    rax, rax
0x140066eb9  jz      short loc_140066F2D
0x140066ebb  mov     edx, r13d; Ch
0x140066ebe  lea     rcx, [rax+2]; Str
0x140066ec2  call    cs:__imp_wcschr
0x140066ec8  mov     rbx, rax
0x140066ecb  test    rax, rax
0x140066ece  jz      short loc_140066F2D
0x140066ed0  jmp     short loc_140066EF5
0x140066ed2  cmp     rdi, 1
0x140066ed6  jbe     loc_140066F7D
0x140066edc  mov     r8d, 1; MaxCount
0x140066ee2  lea     rdx, SubBlock; "\\"
0x140066ee9  mov     rcx, rbx; String1
0x140066eec  call    wcsncmp_0
0x140066ef1  test    eax, eax
0x140066ef3  jnz     short loc_140066EFA
0x140066ef5  add     rbx, r15
0x140066ef8  jmp     short loc_140066F28
0x140066efa  cmp     rdi, 3
0x140066efe  jbe     short loc_140066F7D
0x140066f00  movzx   ecx, word ptr [rbx]; C
0x140066f03  call    cs:__imp_iswalpha
0x140066f09  test    eax, eax
0x140066f0b  jz      short loc_140066F7D
0x140066f0d  lea     rcx, [rbx+2]; String1
0x140066f11  mov     r8d, r15d; MaxCount
0x140066f14  lea     rdx, asc_14008F4A0; ":\\"
0x140066f1b  call    wcsncmp_0
0x140066f20  test    eax, eax
0x140066f22  jnz     short loc_140066F7D
0x140066f24  add     rbx, 6
0x140066f28  test    rbx, rbx
0x140066f2b  jnz     short loc_140066F7D
0x140066f2d  xor     edx, edx; lpSecurityAttributes
0x140066f2f  mov     rcx, rbp; lpPathName
0x140066f32  call    cs:__imp_CreateDirectoryW
0x140066f38  test    eax, eax
0x140066f3a  jnz     short loc_140066F7D
0x140066f3c  call    cs:__imp_GetLastError
0x140066f42  mov     edi, eax
0x140066f44  cmp     eax, 0B7h
0x140066f49  jz      loc_140066E6F
0x140066f4f  mov     rcx, cs:WPP_GLOBAL_Control
0x140066f56  cmp     rcx, r12
0x140066f59  jz      loc_14006703F
0x140066f5f  test    [rcx+1Ch], r15b
0x140066f63  jz      loc_14006703F
0x140066f69  cmp     [rcx+19h], r15b
0x140066f6d  jb      loc_14006703F
0x140066f73  mov     edx, 14h
0x140066f78  jmp     loc_140067028
0x140066f7d  mov     edi, r14d
0x140066f80  jmp     short loc_140066FBA
0x140066f82  mov     edx, r13d; Ch
0x140066f85  mov     rcx, rbx; Str
0x140066f88  call    cs:__imp_wcschr
0x140066f8e  xor     edx, edx; lpSecurityAttributes
0x140066f90  mov     rcx, rbp; lpPathName
0x140066f93  mov     rbx, rax
0x140066f96  test    rax, rax
0x140066f99  jz      short loc_140066FEC
0x140066f9b  mov     [rax], r14w
0x140066f9f  call    cs:__imp_CreateDirectoryW
0x140066fa5  test    eax, eax
0x140066fa7  jnz     short loc_140066FB6
0x140066fa9  call    cs:__imp_GetLastError
0x140066faf  cmp     eax, 0B7h
0x140066fb4  jnz     short loc_140066FC5
0x140066fb6  mov     [rbx], r13w
0x140066fba  add     rbx, r15
0x140066fbd  cmp     [rbx], r14w
0x140066fc1  jnz     short loc_140066F82
0x140066fc3  jmp     short loc_14006703F
0x140066fc5  call    cs:__imp_GetLastError
0x140066fcb  mov     edi, eax
0x140066fcd  mov     rcx, cs:WPP_GLOBAL_Control
0x140066fd4  cmp     rcx, r12
0x140066fd7  jz      short loc_14006703F
0x140066fd9  test    [rcx+1Ch], r15b
0x140066fdd  jz      short loc_14006703F
0x140066fdf  cmp     [rcx+19h], r15b
0x140066fe3  jb      short loc_14006703F
0x140066fe5  mov     edx, 16h
0x140066fea  jmp     short loc_140067028
0x140066fec  call    cs:__imp_CreateDirectoryW
0x140066ff2  test    eax, eax
0x140066ff4  jnz     short loc_14006703F
0x140066ff6  call    cs:__imp_GetLastError
0x140066ffc  cmp     eax, 0B7h
0x140067001  jz      short loc_14006703F
0x140067003  call    cs:__imp_GetLastError
0x140067009  mov     edi, eax
0x14006700b  mov     rcx, cs:WPP_GLOBAL_Control
0x140067012  cmp     rcx, r12
0x140067015  jz      short loc_14006703F
0x140067017  test    [rcx+1Ch], r15b
0x14006701b  jz      short loc_14006703F
0x14006701d  cmp     [rcx+19h], r15b
0x140067021  jb      short loc_14006703F
0x140067023  mov     edx, 15h
0x140067028  mov     rcx, [rcx+10h]
0x14006702c  lea     r8, WPP_04fb59550d79390d980a26525e0212b0_Traceguids
0x140067033  mov     r9, rbp
0x140067036  mov     [rsp+68h+var_48], eax
0x14006703a  call    WPP_SF_Sd
0x14006703f  mov     rcx, rbp; lpMem
0x140067042  call    pMemFree
0x140067047  test    edi, edi
0x140067049  jz      short loc_140067053
0x14006704b  mov     ecx, edi; dwErrCode
0x14006704d  call    cs:__imp_SetLastError
0x140067053  test    edi, edi
0x140067055  mov     eax, r14d
0x140067058  setz    al
0x14006705b  add     rsp, 30h
0x14006705f  pop     r15
0x140067061  pop     r14
0x140067063  pop     r13
0x140067065  pop     r12
0x140067067  pop     rdi
0x140067068  pop     rbp
0x140067069  pop     rbx
0x14006706a  retn
```
