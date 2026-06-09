# BinaryLogWriter_Core_NewFile

- ea: `0x180028948`
- end: `0x180028af7`
- name: `BinaryLogWriter_Core_NewFile`
- size: `431`
- prototype: `__int64 __fastcall(int *FileHandle, wchar_t *FileName)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180026010`
- `0x1800283d0`

## callees

- `0x180007dc0`
- `0x18000abb8`
- `0x18002876c`
- `0x180028948`
- `0x180044880`

## import_xrefs

- `msvcrt!_wstat` at `0x180028a49`
- `msvcrt!_wstat` at `0x180028a49`
- `msvcrt!_wsopen_s` at `0x180028a6f`
- `msvcrt!_wsopen_s` at `0x180028a6f`
- `msvcrt!_errno` at `0x180028a7d`
- `msvcrt!_errno` at `0x180028a88`
- `msvcrt!_errno` at `0x180028a7d`
- `msvcrt!_errno` at `0x180028a88`
- `msvcrt!calloc` at `0x18002899a`
- `msvcrt!calloc` at `0x1800289b7`
- `msvcrt!calloc` at `0x18002899a`
- `msvcrt!calloc` at `0x1800289b7`

## string_xrefs

- `0x180028a90`: `MSFT DSC CU BINARY-LOG-WRITER`

## pseudocode

```c
__int64 __fastcall BinaryLogWriter_Core_NewFile(int *FileHandle, wchar_t *FileName)
{
  _QWORD *v2; // r8
  _BYTE *v5; // rax
  _BYTE *v6; // rbx
  void *v7; // rax
  unsigned __int64 i; // rdx
  __int64 *j; // rcx
  int v10; // ebx
  unsigned int v11; // eax
  __int64 v12; // rdx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+30h] [rbp-50h] BYREF
  _OWORD v15[3]; // [rsp+40h] [rbp-40h] BYREF

  v2 = (_QWORD *)*((_QWORD *)FileHandle + 3);
  *((_QWORD *)FileHandle + 2) = 0;
  *((_QWORD *)FileHandle + 1) = 0;
  if ( v2 )
  {
    for ( i = 0; i < v2[1]; ++i )
    {
      for ( j = *(__int64 **)(*v2 + 8 * i); j; j = (__int64 *)*j )
      {
        if ( *((_DWORD *)j + 6) == 1 )
          *((_DWORD *)j + 6) = 0;
      }
    }
  }
  else
  {
    v5 = calloc(1u, 0x30u);
    *((_QWORD *)FileHandle + 3) = v5;
    v6 = v5;
    if ( !v5 )
      return 1;
    v7 = calloc(0x64u, 8u);
    *(_QWORD *)v6 = v7;
    if ( !v7 )
      return 1;
    v6[16] = 1;
    *((_QWORD *)v6 + 3) = ClassCacheHash;
    *((_QWORD *)v6 + 4) = ClassCacheEqual;
    *((_QWORD *)v6 + 5) = ClassCacheRelease;
    *((_QWORD *)v6 + 1) = 100;
  }
  v10 = 33025;
  if ( *((_QWORD *)FileHandle + 8) )
  {
    memset(v15, 0, sizeof(v15));
    if ( (unsigned int)_wstat(FileName, v15) )
    {
      if ( *_errno() != 2 )
      {
        v12 = (unsigned int)*_errno();
        goto LABEL_19;
      }
    }
    else
    {
      v10 = 33033;
    }
  }
  v11 = _wsopen_s(FileHandle, FileName, v10, 32, 384);
  if ( v11 )
  {
    v12 = v11;
LABEL_19:
    MI_ReportErrorDetails_FromFOpen(FileName, v12, L"MSFT DSC CU BINARY-LOG-WRITER");
    return 1;
  }
  *(_DWORD *)&EventDescriptor.Id = 115;
  *(_DWORD *)&EventDescriptor.Level = 4;
  EventDescriptor.Keyword = 1;
  Etw_Trace1_LPCWSTR(&EventDescriptor);
  if ( (v10 & 8) != 0 )
    return 0;
  else
    return BinaryLogWriter_Core_AddHeader((__int64)FileHandle);
}

```

## disassembly

```asm
0x180028948  mov     [rsp-18h+arg_10], rbx
0x18002894d  mov     [rsp-18h+arg_18], rsi
0x180028952  push    rbp
0x180028953  push    rdi
0x180028954  push    r15
0x180028956  mov     rbp, rsp
0x180028959  sub     rsp, 80h
0x180028960  mov     rax, cs:__security_cookie
0x180028967  xor     rax, rsp
0x18002896a  mov     [rbp+var_10], rax
0x18002896e  mov     r8, [rcx+18h]
0x180028972  mov     rsi, rdx
0x180028975  mov     qword ptr [rcx+10h], 0
0x18002897d  mov     rdi, rcx
0x180028980  mov     qword ptr [rcx+8], 0
0x180028988  mov     r15d, 1
0x18002898e  test    r8, r8
0x180028991  jnz     short loc_1800289F8
0x180028993  lea     edx, [r8+30h]; Size
0x180028997  mov     ecx, r15d; Count
0x18002899a  call    cs:__imp_calloc
0x1800289a0  mov     [rdi+18h], rax
0x1800289a4  mov     rbx, rax
0x1800289a7  test    rax, rax
0x1800289aa  jz      loc_180028A9F
0x1800289b0  lea     edx, [r15+7]; Size
0x1800289b4  lea     ecx, [rdx+5Ch]; Count
0x1800289b7  call    cs:__imp_calloc
0x1800289bd  mov     [rbx], rax
0x1800289c0  test    rax, rax
0x1800289c3  jz      loc_180028A9F
0x1800289c9  lea     rax, ClassCacheHash
0x1800289d0  mov     [rbx+10h], r15b
0x1800289d4  mov     [rbx+18h], rax
0x1800289d8  lea     rax, ClassCacheEqual
0x1800289df  mov     [rbx+20h], rax
0x1800289e3  lea     rax, ClassCacheRelease
0x1800289ea  mov     [rbx+28h], rax
0x1800289ee  mov     qword ptr [rbx+8], 64h ; 'd'
0x1800289f6  jmp     short loc_180028A27
0x1800289f8  xor     edx, edx
0x1800289fa  cmp     [r8+8], rdx
0x1800289fe  jbe     short loc_180028A27
0x180028a00  mov     rax, [r8]
0x180028a03  mov     rcx, [rax+rdx*8]
0x180028a07  jmp     short loc_180028A19
0x180028a09  cmp     [rcx+18h], r15d
0x180028a0d  jnz     short loc_180028A16
0x180028a0f  mov     dword ptr [rcx+18h], 0
0x180028a16  mov     rcx, [rcx]
0x180028a19  test    rcx, rcx
0x180028a1c  jnz     short loc_180028A09
0x180028a1e  add     rdx, r15
0x180028a21  cmp     rdx, [r8+8]
0x180028a25  jb      short loc_180028A00
0x180028a27  cmp     qword ptr [rdi+40h], 0
0x180028a2c  mov     ebx, 8101h
0x180028a31  jz      short loc_180028A58
0x180028a33  xorps   xmm0, xmm0
0x180028a36  lea     rdx, [rbp+var_40]
0x180028a3a  mov     rcx, rsi
0x180028a3d  movups  [rbp+var_40], xmm0
0x180028a41  movups  [rbp+var_30], xmm0
0x180028a45  movups  [rbp+var_20], xmm0
0x180028a49  call    cs:__imp__wstat
0x180028a4f  test    eax, eax
0x180028a51  jnz     short loc_180028A7D
0x180028a53  mov     ebx, 8109h
0x180028a58  mov     r9d, 20h ; ' '; ShareFlag
0x180028a5e  mov     [rsp+80h+PermissionFlag], 180h; PermissionFlag
0x180028a66  mov     r8d, ebx; OpenFlag
0x180028a69  mov     rdx, rsi; FileName
0x180028a6c  mov     rcx, rdi; FileHandle
0x180028a6f  call    cs:__imp__wsopen_s
0x180028a75  test    eax, eax
0x180028a77  jz      short loc_180028AA4
0x180028a79  mov     edx, eax
0x180028a7b  jmp     short loc_180028A90
0x180028a7d  call    cs:__imp__errno
0x180028a83  cmp     dword ptr [rax], 2
0x180028a86  jz      short loc_180028A58
0x180028a88  call    cs:__imp__errno
0x180028a8e  mov     edx, [rax]
0x180028a90  lea     r8, aMsftDscCuBinar; "MSFT DSC CU BINARY-LOG-WRITER"
0x180028a97  mov     rcx, rsi
0x180028a9a  call    MI_ReportErrorDetails_FromFOpen
0x180028a9f  mov     eax, r15d
0x180028aa2  jmp     short loc_180028AD3
0x180028aa4  mov     rdx, rsi
0x180028aa7  mov     dword ptr [rbp+EventDescriptor.Id], 73h ; 's'
0x180028aae  lea     rcx, [rbp+EventDescriptor]; EventDescriptor
0x180028ab2  mov     dword ptr [rbp+EventDescriptor.Level], 4
0x180028ab9  mov     [rbp+EventDescriptor.Keyword], r15
0x180028abd  call    Etw_Trace1_LPCWSTR
0x180028ac2  test    bl, 8
0x180028ac5  jnz     short loc_180028AD1
0x180028ac7  mov     rcx, rdi
0x180028aca  call    BinaryLogWriter_Core_AddHeader
0x180028acf  jmp     short loc_180028AD3
0x180028ad1  xor     eax, eax
0x180028ad3  mov     rcx, [rbp+var_10]
0x180028ad7  xor     rcx, rsp; StackCookie
0x180028ada  call    __security_check_cookie
0x180028adf  lea     r11, [rsp+80h+var_s0]
0x180028ae7  mov     rbx, [r11+30h]
0x180028aeb  mov     rsi, [r11+38h]
0x180028aef  mov     rsp, r11
0x180028af2  pop     r15
0x180028af4  pop     rdi
0x180028af5  pop     rbp
0x180028af6  retn
```
