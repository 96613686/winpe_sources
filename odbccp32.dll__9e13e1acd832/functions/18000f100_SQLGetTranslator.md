# SQLGetTranslator

- ea: `0x18000f100`
- end: `0x18000f29c`
- name: `SQLGetTranslator`
- size: `412`
- prototype: `BOOL __stdcall(HWND hwnd, LPSTR lpszName, WORD cchNameMax, WORD *pcchNameOut, LPSTR lpszPath, WORD cchPathMax, WORD *pcchPathOut, DWORD *pvOption)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x180002940`
- `0x180004bac`
- `0x180008fc0`
- `0x18000f100`
- `0x1800138e4`
- `0x180013c2c`
- `0x180014aae`

## import_xrefs

- `msvcrt!calloc` at `0x18000f1a1`
- `msvcrt!calloc` at `0x18000f1a1`
- `KERNEL32!LeaveCriticalSection` at `0x18000f17b`
- `KERNEL32!LeaveCriticalSection` at `0x18000f17b`
- `KERNEL32!EnterCriticalSection` at `0x18000f166`
- `KERNEL32!EnterCriticalSection` at `0x18000f166`

## pseudocode

```c
BOOL __stdcall SQLGetTranslator(
        HWND hwnd,
        LPSTR lpszName,
        WORD cchNameMax,
        WORD *pcchNameOut,
        LPSTR lpszPath,
        WORD cchPathMax,
        WORD *pcchPathOut,
        DWORD *pvOption)
{
  WORD *v8; // r12
  WORD *v9; // r13
  int v11; // r15d
  WCHAR *v12; // rbx
  WORD v14; // r14
  WCHAR *v15; // rsi
  BOOL v16; // edi
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int16 v21; // [rsp+40h] [rbp-10h] BYREF
  WCHAR *v22; // [rsp+48h] [rbp-8h] BYREF
  LPSTR v24; // [rsp+98h] [rbp+48h] BYREF
  __int16 v25; // [rsp+A8h] [rbp+58h] BYREF

  v24 = lpszName;
  v8 = (WORD *)&v25;
  v9 = (WORD *)&v21;
  v11 = cchNameMax;
  v22 = 0;
  v12 = 0;
  v25 = 0;
  if ( pcchNameOut )
    v8 = pcchNameOut;
  v21 = 0;
  if ( pcchPathOut )
    v9 = pcchPathOut;
  if ( lpszPath )
  {
    v14 = cchPathMax;
    v15 = 0;
    if ( !cchPathMax || (v15 = (WCHAR *)calloc(2LL * cchPathMax, 1u)) != 0 )
    {
      if ( !lpszName )
        goto LABEL_17;
      v17 = -1;
      do
        ++v17;
      while ( lpszName[v17] );
      if ( v11 <= (int)v17 + 1 )
        LOWORD(v11) = v17 + 1;
      memset_0(&lpszName[(int)v17], 0, (unsigned __int16)v11 - (int)v17);
      v18 = GWConvertToUnicode(lpszName, &v22, (unsigned __int16)v11);
      v12 = v22;
      if ( v18 )
      {
LABEL_17:
        v16 = SQLGetTranslatorW(hwnd, v12, v11, v8, v15, v14, v9, pvOption);
        if ( v16 )
        {
          LConvertToAnsiWordLengths(v19, v12, *v8, &v24, v11, v8);
          LConvertToAnsiWordLengths(v20, v15, *v9, &lpszPath, v14, v9);
        }
      }
      else
      {
        v16 = 0;
      }
    }
    else
    {
      v16 = 0;
    }
    OFree(v15);
    OFree(v12);
    return v16;
  }
  else
  {
    EnterCriticalSection(&g_csInstaller);
    PostInstError(12);
    LeaveCriticalSection(&g_csInstaller);
    return 0;
  }
}

```

## disassembly

```asm
0x18000f100  mov     [rsp-38h+arg_10], rbx
0x18000f105  mov     [rsp-38h+arg_8], rdx
0x18000f10a  mov     [rsp-38h+hwnd], rcx
0x18000f10f  push    rbp
0x18000f110  push    rsi
0x18000f111  push    rdi
0x18000f112  push    r12
0x18000f114  push    r13
0x18000f116  push    r14
0x18000f118  push    r15
0x18000f11a  mov     rbp, rsp
0x18000f11d  sub     rsp, 50h
0x18000f121  mov     rax, [rbp+pcchPathOut]
0x18000f125  lea     r12, [rbp+arg_18]
0x18000f129  mov     r10, [rbp+lpszPath]
0x18000f12d  lea     r13, [rbp+var_10]
0x18000f131  mov     rdi, rdx
0x18000f134  movzx   r15d, r8w
0x18000f138  xor     edx, edx
0x18000f13a  mov     [rbp+lpszPath], r10
0x18000f13e  test    r9, r9
0x18000f141  mov     [rbp+var_8], rdx
0x18000f145  mov     ebx, edx
0x18000f147  mov     [rbp+arg_18], dx
0x18000f14b  cmovnz  r12, r9
0x18000f14f  mov     [rbp+var_10], dx
0x18000f153  test    rax, rax
0x18000f156  cmovnz  r13, rax
0x18000f15a  test    r10, r10
0x18000f15d  jnz     short loc_18000F188
0x18000f15f  lea     rcx, g_csInstaller; lpCriticalSection
0x18000f166  call    cs:__imp_EnterCriticalSection
0x18000f16c  lea     ecx, [rbx+0Ch]
0x18000f16f  call    PostInstError
0x18000f174  lea     rcx, g_csInstaller; lpCriticalSection
0x18000f17b  call    cs:__imp_LeaveCriticalSection
0x18000f181  xor     eax, eax
0x18000f183  jmp     loc_18000F284
0x18000f188  movzx   r14d, [rbp+cchPathMax]
0x18000f18d  mov     rsi, rdx
0x18000f190  test    r14w, r14w
0x18000f194  jz      short loc_18000F1B8
0x18000f196  mov     ecx, r14d
0x18000f199  mov     edx, 1; Size
0x18000f19e  add     rcx, rcx; Count
0x18000f1a1  call    cs:__imp_calloc
0x18000f1a7  xor     edx, edx
0x18000f1a9  mov     rsi, rax
0x18000f1ac  test    rax, rax
0x18000f1af  jnz     short loc_18000F1B8
0x18000f1b1  mov     edi, edx
0x18000f1b3  jmp     loc_18000F272
0x18000f1b8  test    rdi, rdi
0x18000f1bb  jz      short loc_18000F208
0x18000f1bd  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000f1c1  inc     rcx
0x18000f1c4  cmp     [rdi+rcx], dl
0x18000f1c7  jnz     short loc_18000F1C1
0x18000f1c9  lea     edx, [rcx+1]
0x18000f1cc  cmp     r15d, edx
0x18000f1cf  jg      short loc_18000F1D5
0x18000f1d1  movzx   r15d, dx
0x18000f1d5  movzx   ebx, r15w
0x18000f1d9  xor     edx, edx; Val
0x18000f1db  mov     eax, ebx
0x18000f1dd  sub     eax, ecx
0x18000f1df  movsxd  rcx, ecx
0x18000f1e2  add     rcx, rdi; void *
0x18000f1e5  movsxd  r8, eax; Size
0x18000f1e8  call    memset_0
0x18000f1ed  mov     r8d, ebx
0x18000f1f0  lea     rdx, [rbp+var_8]
0x18000f1f4  mov     rcx, rdi; lpMultiByteStr
0x18000f1f7  call    GWConvertToUnicode
0x18000f1fc  mov     rbx, [rbp+var_8]
0x18000f200  test    eax, eax
0x18000f202  jnz     short loc_18000F208
0x18000f204  xor     edi, edi
0x18000f206  jmp     short loc_18000F272
0x18000f208  mov     rax, [rbp+pvOption]
0x18000f20c  mov     r9, r12; pcchNameOut
0x18000f20f  mov     rcx, [rbp+hwnd]; hwnd
0x18000f213  movzx   r8d, r15w; cchNameMax
0x18000f217  mov     [rsp+50h+var_18], rax; pvOption
0x18000f21c  mov     rdx, rbx; lpszName
0x18000f21f  mov     [rsp+50h+var_20], r13; pcchPathOut
0x18000f224  mov     [rsp+50h+var_28], r14w; cchPathMax
0x18000f22a  mov     [rsp+50h+var_30], rsi; lpszPath
0x18000f22f  call    SQLGetTranslatorW
0x18000f234  mov     edi, eax
0x18000f236  test    eax, eax
0x18000f238  jz      short loc_18000F272
0x18000f23a  movzx   r8d, word ptr [r12]
0x18000f23f  lea     r9, [rbp+arg_8]
0x18000f243  mov     qword ptr [rsp+50h+var_28], r12
0x18000f248  mov     rdx, rbx
0x18000f24b  mov     word ptr [rsp+50h+var_30], r15w
0x18000f251  call    LConvertToAnsiWordLengths
0x18000f256  movzx   r8d, word ptr [r13+0]
0x18000f25b  lea     r9, [rbp+lpszPath]
0x18000f25f  mov     rdx, rsi
0x18000f262  mov     qword ptr [rsp+50h+var_28], r13
0x18000f267  mov     word ptr [rsp+50h+var_30], r14w
0x18000f26d  call    LConvertToAnsiWordLengths
0x18000f272  mov     rcx, rsi
0x18000f275  call    OFree
0x18000f27a  mov     rcx, rbx
0x18000f27d  call    OFree
0x18000f282  mov     eax, edi
0x18000f284  mov     rbx, [rsp+50h+arg_10]
0x18000f28c  add     rsp, 50h
0x18000f290  pop     r15
0x18000f292  pop     r14
0x18000f294  pop     r13
0x18000f296  pop     r12
0x18000f298  pop     rdi
0x18000f299  pop     rsi
0x18000f29a  pop     rbp
0x18000f29b  retn
```
