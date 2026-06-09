# I_CryptGetLowIntegrityUserPath

- ea: `0x180006db0`
- end: `0x1800070c6`
- name: `I_CryptGetLowIntegrityUserPath`
- size: `790`
- prototype: `__int64 __fastcall(__int64, _WORD *)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800011f4`
- `0x180005700`

## callees

- `0x1800068b0`
- `0x180006db0`
- `0x180008330`
- `0x1800090b0`
- `0x18000961c`
- `0x18000a4c0`
- `0x18000b02c`
- `0x18000e2f0`
- `0x180011458`
- `0x1800114c4`
- `0x1800174fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007089`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007089`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006ef7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006ef7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180006f20`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180006f20`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180006e14`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180006e14`

## pseudocode

```c
__int64 __fastcall I_CryptGetLowIntegrityUserPath(__int64 a1, _WORD *a2)
{
  int BasicProfileFolderPath; // ebx
  __int64 v4; // rdx
  wchar_t *v5; // rax
  __int64 v6; // rdi
  __int64 v7; // rcx
  _WORD *v8; // r8
  const wchar_t *v9; // r9
  _WORD *v10; // rcx
  int v11; // r9d
  __int64 v12; // rbx
  __int64 v13; // rdi
  WCHAR *v14; // rax
  WCHAR *v15; // r14
  DWORD FileAttributesW; // eax
  HRESULT v18; // eax
  const wchar_t *v19; // rcx
  wchar_t *v20; // rdx
  size_t v21; // rbp
  wchar_t *v22; // rcx
  DWORD v23; // ecx
  size_t pcchLength[2]; // [rsp+20h] [rbp-248h] BYREF
  wchar_t Src[260]; // [rsp+30h] [rbp-238h] BYREF
  _BYTE v26[8]; // [rsp+238h] [rbp-30h] BYREF

  if ( !(unsigned int)I_CryptIsAppContainerToken(a1) )
  {
    Src[0] = 0;
    BasicProfileFolderPath = GetBasicProfileFolderPath(6, 0, Src, 260);
    if ( BasicProfileFolderPath >= 0 )
    {
      v4 = 260;
      v5 = Src;
      do
      {
        if ( !*v5 )
          break;
        ++v5;
        --v4;
      }
      while ( v4 );
      BasicProfileFolderPath = -2147024809;
      if ( v4 )
      {
        v6 = 2147483646;
        v7 = 2147483646;
        v8 = &v26[-2 * v4];
        v9 = L"Low";
        do
        {
          if ( !v7 )
            break;
          if ( !*v9 )
            break;
          *v8++ = *v9++;
          --v7;
          --v4;
        }
        while ( v4 );
        v10 = v8 - 1;
        BasicProfileFolderPath = -2147024774;
        v11 = -2147024774;
        if ( v4 )
        {
          v10 = v8;
          v11 = 0;
        }
        *v10 = 0;
        if ( v4 )
        {
          if ( Src[0] == 37 )
            ExpandUserAppDataPathW(Src);
          if ( !a2 || *a2 == 92 )
            goto LABEL_16;
          pcchLength[0] = 0;
          v18 = StringLengthWorkerW(Src, 0x104u, pcchLength);
          if ( v18 >= 0 )
          {
            v19 = L"\\";
            v20 = &Src[pcchLength[0]];
            v21 = 260 - pcchLength[0];
            if ( 260 != pcchLength[0] )
            {
              do
              {
                if ( !v6 )
                  break;
                if ( !*v19 )
                  break;
                *v20++ = *v19++;
                --v6;
                --v21;
              }
              while ( v21 );
            }
            v22 = v20 - 1;
            if ( v21 )
            {
              v22 = v20;
              BasicProfileFolderPath = 0;
            }
            *v22 = 0;
            if ( !v21 )
              goto LABEL_43;
LABEL_16:
            v12 = -1;
            v13 = -1;
            do
              ++v13;
            while ( Src[v13] );
            if ( a2 )
            {
              do
                ++v12;
              while ( a2[v12] );
            }
            else
            {
              LODWORD(v12) = 0;
            }
            v14 = (WCHAR *)LocalAlloc(0, 2LL * (unsigned int)(v13 + v12 + 1));
            v15 = v14;
            if ( !v14 )
            {
              v23 = -2147024882;
              goto LABEL_44;
            }
            memcpy_0(v14, Src, 2LL * (unsigned int)(v13 + 1));
            FileAttributesW = GetFileAttributesW(v15);
            if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
            {
              if ( !(unsigned int)I_RecursiveCreateDirectory(v15) )
                goto LABEL_41;
            }
            else
            {
              LODWORD(pcchLength[0]) = 0;
              if ( !(unsigned int)CheckLowIntegrityDir(v15) )
                goto LABEL_41;
              if ( LODWORD(pcchLength[0]) )
              {
LABEL_25:
                memcpy_0(&v15[(unsigned int)v13], a2, 2LL * (unsigned int)(v12 + 1));
                return (__int64)v15;
              }
            }
            if ( (unsigned int)SetLowIntegrityFile(v15) )
              goto LABEL_25;
LABEL_41:
            PkiFree(v15);
            return 0;
          }
          BasicProfileFolderPath = v18;
        }
        else
        {
          BasicProfileFolderPath = v11;
        }
      }
    }
LABEL_43:
    v15 = 0;
    v23 = BasicProfileFolderPath;
LABEL_44:
    SetLastError(v23);
    return (__int64)v15;
  }
  return CryptGetAppContainerUserPath(a2);
}

```

## disassembly

```asm
0x180006db0  push    rsi
0x180006db2  sub     rsp, 260h
0x180006db9  mov     rax, cs:__security_cookie
0x180006dc0  xor     rax, rsp
0x180006dc3  mov     [rsp+268h+var_28], rax
0x180006dcb  mov     rsi, rdx
0x180006dce  call    I_CryptIsAppContainerToken
0x180006dd3  test    eax, eax
0x180006dd5  jnz     loc_180007058
0x180006ddb  mov     [rsp+268h+arg_10], rbx
0x180006de3  lea     r8, [rsp+268h+Src]
0x180006de8  mov     [rsp+268h+arg_18], rbp
0x180006df0  xor     edx, edx
0x180006df2  mov     ebp, 104h
0x180006df7  mov     [rsp+268h+var_10], rdi
0x180006dff  mov     r9d, ebp
0x180006e02  mov     [rsp+268h+var_18], r14
0x180006e0a  mov     ecx, 6
0x180006e0f  mov     [rsp+268h+Src], ax
0x180006e14  call    cs:__imp_GetBasicProfileFolderPath
0x180006e1a  mov     ebx, eax
0x180006e1c  test    eax, eax
0x180006e1e  js      loc_180007084
0x180006e24  mov     edx, ebp
0x180006e26  lea     rax, [rsp+268h+Src]
0x180006e2b  nop     dword ptr [rax+rax+00h]
0x180006e30  cmp     word ptr [rax], 0
0x180006e34  jz      short loc_180006E40
0x180006e36  add     rax, 2
0x180006e3a  sub     rdx, 1
0x180006e3e  jnz     short loc_180006E30
0x180006e40  xor     eax, eax
0x180006e42  mov     ebx, 80070057h
0x180006e47  test    rdx, rdx
0x180006e4a  cmovnz  ebx, eax
0x180006e4d  jz      loc_180007084
0x180006e53  mov     edi, 7FFFFFFEh
0x180006e58  lea     rax, [rdx+rdx]
0x180006e5c  lea     r8, [rsp+268h+var_30]
0x180006e64  mov     ecx, edi
0x180006e66  sub     r8, rax
0x180006e69  lea     r9, aLow; "Low"
0x180006e70  test    rcx, rcx
0x180006e73  jz      short loc_180006E82
0x180006e75  movzx   eax, word ptr [r9]
0x180006e79  test    ax, ax
0x180006e7c  jnz     loc_180006FB0
0x180006e82  xor     eax, eax
0x180006e84  lea     rcx, [r8-2]
0x180006e88  test    rdx, rdx
0x180006e8b  mov     ebx, 8007007Ah
0x180006e90  mov     r9d, ebx
0x180006e93  cmovnz  rcx, r8
0x180006e97  cmovnz  r9d, eax
0x180006e9b  mov     [rcx], ax
0x180006e9e  jz      loc_180007081
0x180006ea4  mov     eax, 25h ; '%'
0x180006ea9  cmp     ax, [rsp+268h+Src]
0x180006eae  jz      loc_18000709B
0x180006eb4  test    rsi, rsi
0x180006eb7  jnz     loc_180006FCE
0x180006ebd  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180006ec4  lea     rax, [rsp+268h+Src]
0x180006ec9  mov     rdi, rbx
0x180006ecc  nop     dword ptr [rax+00h]
0x180006ed0  inc     rdi
0x180006ed3  cmp     word ptr [rax+rdi*2], 0
0x180006ed8  jnz     short loc_180006ED0
0x180006eda  test    rsi, rsi
0x180006edd  jz      loc_180007094
0x180006ee3  inc     rbx
0x180006ee6  cmp     word ptr [rsi+rbx*2], 0
0x180006eeb  jnz     short loc_180006EE3
0x180006eed  lea     edx, [rbx+1]
0x180006ef0  xor     ecx, ecx; uFlags
0x180006ef2  add     edx, edi
0x180006ef4  add     rdx, rdx; uBytes
0x180006ef7  call    cs:__imp_LocalAlloc
0x180006efd  mov     r14, rax
0x180006f00  test    rax, rax
0x180006f03  jz      loc_1800070AE
0x180006f09  lea     r8d, [rdi+1]
0x180006f0d  mov     rcx, rax; void *
0x180006f10  add     r8, r8; Size
0x180006f13  lea     rdx, [rsp+268h+Src]; Src
0x180006f18  call    memcpy_0
0x180006f1d  mov     rcx, r14; lpFileName
0x180006f20  call    cs:__imp_GetFileAttributesW
0x180006f26  cmp     eax, 0FFFFFFFFh
0x180006f29  jz      loc_180007065
0x180006f2f  test    al, 10h
0x180006f31  jz      loc_180007065
0x180006f37  lea     rdx, [rsp+268h+pcchLength]
0x180006f3c  mov     dword ptr [rsp+268h+pcchLength], 0
0x180006f44  mov     rcx, r14; lpFileName
0x180006f47  call    _CheckLowIntegrityDir
0x180006f4c  test    eax, eax
0x180006f4e  jz      loc_180007071
0x180006f54  cmp     dword ptr [rsp+268h+pcchLength], 0
0x180006f59  jz      loc_1800070B5
0x180006f5f  mov     eax, edi
0x180006f61  lea     r8d, [rbx+1]
0x180006f65  add     r8, r8; Size
0x180006f68  mov     rdx, rsi; Src
0x180006f6b  lea     rcx, [r14+rax*2]; void *
0x180006f6f  call    memcpy_0
0x180006f74  mov     rdi, [rsp+268h+var_10]
0x180006f7c  mov     rax, r14
0x180006f7f  mov     r14, [rsp+268h+var_18]
0x180006f87  mov     rbp, [rsp+268h+arg_18]
0x180006f8f  mov     rbx, [rsp+268h+arg_10]
0x180006f97  mov     rcx, [rsp+268h+var_28]
0x180006f9f  xor     rcx, rsp; StackCookie
0x180006fa2  call    __security_check_cookie
0x180006fa7  add     rsp, 260h
0x180006fae  pop     rsi
0x180006faf  retn
0x180006fb0  mov     [r8], ax
0x180006fb4  add     r9, 2
0x180006fb8  add     r8, 2
0x180006fbc  dec     rcx
0x180006fbf  sub     rdx, 1
0x180006fc3  jnz     loc_180006E70
0x180006fc9  jmp     loc_180006E82
0x180006fce  mov     eax, 5Ch ; '\'
0x180006fd3  cmp     ax, [rsi]
0x180006fd6  jz      loc_180006EBD
0x180006fdc  lea     r8, [rsp+268h+pcchLength]; pcchLength
0x180006fe1  mov     [rsp+268h+pcchLength], 0
0x180006fea  mov     rdx, rbp; cchMax
0x180006fed  lea     rcx, [rsp+268h+Src]; psz
0x180006ff2  call    StringLengthWorkerW
0x180006ff7  test    eax, eax
0x180006ff9  js      loc_1800070AA
0x180006fff  mov     rax, [rsp+268h+pcchLength]
0x180007004  lea     rdx, [rsp+268h+Src]
0x180007009  lea     rcx, asc_18001A2E0; "\\"
0x180007010  lea     rdx, [rdx+rax*2]
0x180007014  sub     rbp, rax
0x180007017  jz      short loc_18000703A
0x180007019  test    rdi, rdi
0x18000701c  jz      short loc_18000703A
0x18000701e  movzx   eax, word ptr [rcx]
0x180007021  test    ax, ax
0x180007024  jz      short loc_18000703A
0x180007026  mov     [rdx], ax
0x180007029  add     rcx, 2
0x18000702d  add     rdx, 2
0x180007031  dec     rdi
0x180007034  sub     rbp, 1
0x180007038  jnz     short loc_180007019
0x18000703a  test    rbp, rbp
0x18000703d  lea     rcx, [rdx-2]
0x180007041  cmovnz  rcx, rdx
0x180007045  xor     eax, eax
0x180007047  test    rbp, rbp
0x18000704a  cmovnz  ebx, eax
0x18000704d  mov     [rcx], ax
0x180007050  jnz     loc_180006EBD
0x180007056  jmp     short loc_180007084
0x180007058  mov     rcx, rsi; Src
0x18000705b  call    _CryptGetAppContainerUserPath
0x180007060  jmp     loc_180006F97
0x180007065  mov     rcx, r14; lpFileName
0x180007068  call    I_RecursiveCreateDirectory
0x18000706d  test    eax, eax
0x18000706f  jnz     short loc_1800070B5
0x180007071  mov     rcx, r14; hMem
0x180007074  call    PkiFree
0x180007079  xor     r14d, r14d
0x18000707c  jmp     loc_180006F74
0x180007081  mov     ebx, r9d
0x180007084  xor     r14d, r14d
0x180007087  mov     ecx, ebx; dwErrCode
0x180007089  call    cs:__imp_SetLastError
0x18000708f  jmp     loc_180006F74
0x180007094  xor     ebx, ebx
0x180007096  jmp     loc_180006EED
0x18000709b  lea     rcx, [rsp+268h+Src]; void *
0x1800070a0  call    _ExpandUserAppDataPathW
0x1800070a5  jmp     loc_180006EB4
0x1800070aa  mov     ebx, eax
0x1800070ac  jmp     short loc_180007084
0x1800070ae  mov     ecx, 8007000Eh
0x1800070b3  jmp     short loc_180007089
0x1800070b5  mov     rcx, r14; lpFileName
0x1800070b8  call    _SetLowIntegrityFile
0x1800070bd  test    eax, eax
0x1800070bf  jz      short loc_180007071
0x1800070c1  jmp     loc_180006F5F
```
