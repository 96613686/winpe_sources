# GetNextBlock

- ea: `0x180026e78`
- end: `0x180027254`
- name: `GetNextBlock`
- size: `988`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180026940`

## callees

- `0x180006ef8`
- `0x180007c80`
- `0x180026660`
- `0x1800266f0`
- `0x180026e78`
- `0x18002725c`
- `0x18004482a`

## import_xrefs

- `msvcrt!malloc` at `0x180026f1f`
- `msvcrt!malloc` at `0x1800271fa`
- `msvcrt!malloc` at `0x180026f1f`
- `msvcrt!malloc` at `0x1800271fa`
- `msvcrt!_read` at `0x180026eec`
- `msvcrt!_read` at `0x180026f3a`
- `msvcrt!_read` at `0x1800270d3`
- `msvcrt!_read` at `0x180027227`
- `msvcrt!_read` at `0x180026eec`
- `msvcrt!_read` at `0x180026f3a`
- `msvcrt!_read` at `0x1800270d3`
- `msvcrt!_read` at `0x180027227`
- `msvcrt!free` at `0x180026f67`
- `msvcrt!free` at `0x1800270b1`
- `msvcrt!free` at `0x1800271e8`
- `msvcrt!free` at `0x180026f67`
- `msvcrt!free` at `0x1800270b1`
- `msvcrt!free` at `0x1800271e8`
- `msvcrt!_lseeki64` at `0x180026f8d`
- `msvcrt!_lseeki64` at `0x180026f8d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180027006`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180027061`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800270fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180027198`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800271c9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180027006`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180027061`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800270fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180027198`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800271c9`

## string_xrefs

- `0x180026ffb`: `mpunits.dll`
- `0x180027056`: `mpunits.dll`
- `0x1800270f1`: `mpunits.dll`
- `0x18002718d`: `mpunits.dll`
- `0x1800271be`: `mpunits.dll`
- `0x180027025`: `BinaryLogReader`
- `0x180027080`: `BinaryLogReader`
- `0x18002711b`: `BinaryLogReader`

## pseudocode

```c
__int64 __fastcall GetNextBlock(__int64 a1, _BYTE *a2, int *a3)
{
  char v6; // al
  unsigned int v7; // r14d
  __int64 i; // rdx
  int v9; // eax
  unsigned int v10; // ebx
  void *v11; // rax
  void *v12; // rsi
  int v13; // eax
  unsigned int v14; // ebx
  HMODULE ModuleHandleA; // rax
  HMODULE v16; // rax
  int v17; // eax
  HMODULE v18; // rax
  __int64 v19; // rdx
  size_t v21; // rbx
  unsigned int v22; // eax
  void *v23; // rax
  int v24; // eax
  __int128 v25; // [rsp+40h] [rbp-20h] BYREF
  __int64 v26; // [rsp+50h] [rbp-10h]
  unsigned int DstBuf; // [rsp+A0h] [rbp+40h] BYREF
  size_t Size; // [rsp+A8h] [rbp+48h] BYREF

  v26 = 0;
  v6 = -(*(_DWORD *)a1 & 4);
  v25 = 0;
  *a3 = 0;
  v7 = v6 != 0 ? 209715200 : 5242880;
  Size = 0;
  *a2 = 0;
  if ( *(_BYTE *)(a1 + 68) )
  {
    for ( i = *(unsigned int *)(a1 + 4); ; i = *(unsigned int *)(a1 + 4) )
    {
      DstBuf = 0;
      v14 = Logger_LockPartOfFile(&v25, i, 4);
      if ( v14 )
      {
        ModuleHandleA = GetModuleHandleA("mpunits.dll");
        Intlstr_GetString_LoadString(ModuleHandleA, 2012);
        MI_ReportErrorDetails_ForCustomError(11, (int)L"BinaryLogReader", 0, 0);
        goto LABEL_28;
      }
      v9 = _read(*(_DWORD *)(a1 + 4), &DstBuf, 4u);
      if ( !v9 )
        return (unsigned int)Logger_UnlockPartOfFile(&v25);
      if ( v9 == -1 )
        goto LABEL_25;
      v10 = DstBuf;
      if ( !DstBuf )
        break;
      if ( *(_BYTE *)(a1 + 104) || *(_DWORD *)(a1 + 96) != DstBuf )
      {
        if ( _lseeki64(*(_DWORD *)(a1 + 4), DstBuf, 1) == -1 )
          goto LABEL_27;
        if ( *(_BYTE *)(a1 + 104) )
          break;
        v14 = SkipInstance(a1);
        if ( v14 )
          goto LABEL_28;
      }
      else
      {
        v11 = malloc(DstBuf);
        v12 = v11;
        if ( !v11 )
          goto LABEL_22;
        v13 = _read(*(_DWORD *)(a1 + 4), v11, v10);
        if ( v13 != (unsigned __int64)DstBuf )
        {
          v16 = GetModuleHandleA("mpunits.dll");
          Intlstr_GetString_LoadString(v16, 2012);
          MI_ReportErrorDetails_ForCustomError(11, (int)L"BinaryLogReader", 0, 0);
          v14 = 1;
          free(v12);
          goto LABEL_28;
        }
        if ( !memcmp_0(v12, *(const void **)(a1 + 88), DstBuf) )
          *(_BYTE *)(a1 + 104) = 1;
        free(v12);
        v14 = SkipInstance(a1);
        if ( v14 )
          goto LABEL_28;
      }
      v14 = Logger_UnlockPartOfFile(&v25);
      if ( v14 )
        goto LABEL_28;
    }
  }
  v17 = _read(*(_DWORD *)(a1 + 4), &Size, 8u);
  if ( !v17 )
  {
    if ( *(_BYTE *)(a1 + 68) )
    {
LABEL_25:
      v18 = GetModuleHandleA("mpunits.dll");
      v19 = 2012;
      goto LABEL_26;
    }
    return (unsigned int)Logger_UnlockPartOfFile(&v25);
  }
  if ( v17 == -1 )
    goto LABEL_25;
  v21 = Size;
  if ( (unsigned int)(Size - 129) > 2 && (_DWORD)Size != 136 )
  {
    v18 = GetModuleHandleA("mpunits.dll");
    v19 = 2028;
    goto LABEL_26;
  }
  if ( (_DWORD)Size != 131 )
    *a2 = 1;
  v22 = HIDWORD(Size);
  if ( HIDWORD(Size) > v7 )
  {
    v18 = GetModuleHandleA("mpunits.dll");
    v19 = 2029;
LABEL_26:
    Intlstr_GetString_LoadString(v18, v19);
    MI_ReportErrorDetails_ForCustomError(11, (int)L"BinaryLogReader", 0, 0);
LABEL_27:
    v14 = 1;
    goto LABEL_28;
  }
  if ( HIDWORD(Size) <= *(_DWORD *)(a1 + 64) )
    goto LABEL_42;
  if ( *(_DWORD *)(a1 + 64) )
  {
    free(*(void **)(a1 + 56));
    v22 = HIDWORD(Size);
    v21 = Size;
  }
  *(_DWORD *)(a1 + 64) = v22;
  v23 = malloc(v22);
  *(_QWORD *)(a1 + 56) = v23;
  if ( v23 )
  {
LABEL_42:
    **(_QWORD **)(a1 + 56) = v21;
    v24 = _read(*(_DWORD *)(a1 + 4), (void *)(*(_QWORD *)(a1 + 56) + 8LL), HIDWORD(Size) - 8);
    if ( v24 != HIDWORD(Size) - 8LL )
      goto LABEL_25;
    *a3 = v24;
    return (unsigned int)Logger_UnlockPartOfFile(&v25);
  }
LABEL_22:
  v14 = 27;
LABEL_28:
  Logger_UnlockPartOfFile(&v25);
  return v14;
}

```

## disassembly

```asm
0x180026e78  mov     [rsp-38h+arg_10], rbx
0x180026e7d  push    rbp
0x180026e7e  push    rsi
0x180026e7f  push    rdi
0x180026e80  push    r12
0x180026e82  push    r13
0x180026e84  push    r14
0x180026e86  push    r15
0x180026e88  mov     rbp, rsp
0x180026e8b  sub     rsp, 60h
0x180026e8f  xor     eax, eax
0x180026e91  xorps   xmm0, xmm0
0x180026e94  mov     [rbp+var_10], rax
0x180026e98  mov     r12, r8
0x180026e9b  mov     eax, [rcx]
0x180026e9d  mov     r15, rdx
0x180026ea0  and     al, 4
0x180026ea2  mov     rdi, rcx
0x180026ea5  neg     al
0x180026ea7  movups  [rbp+var_20], xmm0
0x180026eab  sbb     r14d, r14d
0x180026eae  xor     r13d, r13d
0x180026eb1  and     r14d, 0C300000h
0x180026eb8  mov     [r8], r13d
0x180026ebb  add     r14d, 500000h
0x180026ec2  mov     [rbp+Size], r13
0x180026ec6  mov     [rdx], r13b
0x180026ec9  lea     esi, [r13+1]
0x180026ecd  cmp     [rcx+44h], r13b
0x180026ed1  jz      loc_1800270C6
0x180026ed7  mov     edx, [rcx+4]
0x180026eda  jmp     loc_180026FCF
0x180026edf  mov     ecx, [rdi+4]; FileHandle
0x180026ee2  lea     rdx, [rbp+DstBuf]; DstBuf
0x180026ee6  mov     r8d, 4; MaxCharCount
0x180026eec  call    cs:__imp__read
0x180026ef2  movsxd  rcx, eax
0x180026ef5  test    eax, eax
0x180026ef7  jz      loc_180027244
0x180026efd  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180026f01  jz      loc_1800270EE
0x180026f07  mov     ebx, [rbp+DstBuf]
0x180026f0a  test    ebx, ebx
0x180026f0c  jz      loc_1800270C6
0x180026f12  cmp     [rdi+68h], r13b
0x180026f16  jnz     short loc_180026F84
0x180026f18  cmp     [rdi+60h], ebx
0x180026f1b  jnz     short loc_180026F84
0x180026f1d  mov     ecx, ebx; Size
0x180026f1f  call    cs:__imp_malloc
0x180026f25  mov     rsi, rax
0x180026f28  test    rax, rax
0x180026f2b  jz      loc_1800270BC
0x180026f31  mov     ecx, [rdi+4]; FileHandle
0x180026f34  mov     r8d, ebx; MaxCharCount
0x180026f37  mov     rdx, rax; DstBuf
0x180026f3a  call    cs:__imp__read
0x180026f40  mov     r8d, [rbp+DstBuf]; Size
0x180026f44  movsxd  rcx, eax
0x180026f47  cmp     rcx, r8
0x180026f4a  jnz     loc_180027053
0x180026f50  mov     rdx, [rdi+58h]; Buf2
0x180026f54  mov     rcx, rsi; Buf1
0x180026f57  call    memcmp_0
0x180026f5c  test    eax, eax
0x180026f5e  jnz     short loc_180026F64
0x180026f60  mov     byte ptr [rdi+68h], 1
0x180026f64  mov     rcx, rsi; Block
0x180026f67  call    cs:__imp_free
0x180026f6d  mov     rcx, rdi
0x180026f70  call    SkipInstance
0x180026f75  mov     ebx, eax
0x180026f77  test    eax, eax
0x180026f79  jnz     loc_180027146
0x180026f7f  lea     esi, [rax+1]
0x180026f82  jmp     short loc_180026FB9
0x180026f84  mov     ecx, [rdi+4]; FileHandle
0x180026f87  mov     rdx, rbx; Offset
0x180026f8a  mov     r8d, esi; Origin
0x180026f8d  call    cs:__imp__lseeki64
0x180026f93  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180026f97  jz      loc_180027144
0x180026f9d  cmp     [rdi+68h], r13b
0x180026fa1  jnz     loc_1800270C6
0x180026fa7  mov     rcx, rdi
0x180026faa  call    SkipInstance
0x180026faf  mov     ebx, eax
0x180026fb1  test    eax, eax
0x180026fb3  jnz     loc_180027146
0x180026fb9  lea     rcx, [rbp+var_20]
0x180026fbd  call    Logger_UnlockPartOfFile
0x180026fc2  mov     ebx, eax
0x180026fc4  test    eax, eax
0x180026fc6  jnz     loc_180027146
0x180026fcc  mov     edx, [rdi+4]
0x180026fcf  mov     r9d, 14h
0x180026fd5  mov     dword ptr [rsp+60h+var_40], 0C8h
0x180026fdd  lea     rcx, [rbp+var_20]
0x180026fe1  mov     [rbp+DstBuf], r13d
0x180026fe5  lea     r8d, [r9-10h]
0x180026fe9  call    Logger_LockPartOfFile
0x180026fee  mov     ebx, eax
0x180026ff0  test    eax, eax
0x180026ff2  jz      loc_180026EDF
0x180026ff8  xorps   xmm0, xmm0
0x180026ffb  lea     rcx, ModuleName; "mpunits.dll"
0x180027002  movups  [rbp+var_30], xmm0
0x180027006  call    cs:__imp_GetModuleHandleA
0x18002700c  mov     rcx, rax
0x18002700f  mov     edx, 7DCh
0x180027014  call    _Intlstr_GetString_LoadString
0x180027019  mov     qword ptr [rbp+var_30], rax
0x18002701d  lea     r9, [rbp+var_30]
0x180027021  mov     byte ptr [rbp+var_30+8], r13b
0x180027025  lea     rdx, aBinarylogreade_1; "BinaryLogReader"
0x18002702c  movaps  xmm0, [rbp+var_30]
0x180027030  mov     r8d, 16h
0x180027036  mov     [rsp+60h+var_38], r13; __int64
0x18002703b  movdqa  [rbp+var_30], xmm0
0x180027040  mov     [rsp+60h+var_40], r13; __int64
0x180027045  lea     ecx, [r8-0Bh]; int
0x180027049  call    MI_ReportErrorDetails_ForCustomError
0x18002704e  jmp     loc_180027146
0x180027053  xorps   xmm0, xmm0
0x180027056  lea     rcx, ModuleName; "mpunits.dll"
0x18002705d  movups  [rbp+var_30], xmm0
0x180027061  call    cs:__imp_GetModuleHandleA
0x180027067  mov     rcx, rax
0x18002706a  mov     edx, 7DCh
0x18002706f  call    _Intlstr_GetString_LoadString
0x180027074  mov     qword ptr [rbp+var_30], rax
0x180027078  lea     r9, [rbp+var_30]
0x18002707c  mov     byte ptr [rbp+var_30+8], r13b
0x180027080  lea     rdx, aBinarylogreade_1; "BinaryLogReader"
0x180027087  movaps  xmm0, [rbp+var_30]
0x18002708b  mov     r8d, 16h
0x180027091  mov     [rsp+60h+var_38], r13; __int64
0x180027096  movdqa  [rbp+var_30], xmm0
0x18002709b  mov     [rsp+60h+var_40], r13; __int64
0x1800270a0  lea     ecx, [r8-0Bh]; int
0x1800270a4  call    MI_ReportErrorDetails_ForCustomError
0x1800270a9  mov     rcx, rsi; Block
0x1800270ac  mov     ebx, 1
0x1800270b1  call    cs:__imp_free
0x1800270b7  jmp     loc_180027146
0x1800270bc  mov     ebx, 1Bh
0x1800270c1  jmp     loc_180027146
0x1800270c6  mov     ecx, [rdi+4]; FileHandle
0x1800270c9  lea     rdx, [rbp+Size]; DstBuf
0x1800270cd  mov     r8d, 8; MaxCharCount
0x1800270d3  call    cs:__imp__read
0x1800270d9  movsxd  rcx, eax
0x1800270dc  test    eax, eax
0x1800270de  jnz     loc_180027169
0x1800270e4  cmp     [rdi+44h], r13b
0x1800270e8  jz      loc_180027244
0x1800270ee  xorps   xmm0, xmm0
0x1800270f1  lea     rcx, ModuleName; "mpunits.dll"
0x1800270f8  movups  [rbp+var_30], xmm0
0x1800270fc  call    cs:__imp_GetModuleHandleA
0x180027102  mov     edx, 7DCh
0x180027107  mov     rcx, rax
0x18002710a  call    _Intlstr_GetString_LoadString
0x18002710f  mov     qword ptr [rbp+var_30], rax
0x180027113  lea     r9, [rbp+var_30]
0x180027117  mov     byte ptr [rbp+var_30+8], r13b
0x18002711b  lea     rdx, aBinarylogreade_1; "BinaryLogReader"
0x180027122  movaps  xmm0, [rbp+var_30]
0x180027126  mov     r8d, 16h
0x18002712c  mov     [rsp+60h+var_38], r13; __int64
0x180027131  mov     [rsp+60h+var_40], r13; __int64
0x180027136  movdqa  [rbp+var_30], xmm0
0x18002713b  lea     ecx, [r8-0Bh]; int
0x18002713f  call    MI_ReportErrorDetails_ForCustomError
0x180027144  mov     ebx, esi
0x180027146  lea     rcx, [rbp+var_20]
0x18002714a  call    Logger_UnlockPartOfFile
0x18002714f  mov     eax, ebx
0x180027151  mov     rbx, [rsp+60h+arg_10]
0x180027159  add     rsp, 60h
0x18002715d  pop     r15
0x18002715f  pop     r14
0x180027161  pop     r13
0x180027163  pop     r12
0x180027165  pop     rdi
0x180027166  pop     rsi
0x180027167  pop     rbp
0x180027168  retn
0x180027169  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002716d  jz      loc_1800270EE
0x180027173  mov     rbx, [rbp+Size]
0x180027177  lea     eax, [rbx-81h]
0x18002717d  cmp     eax, 2
0x180027180  jbe     short loc_1800271A8
0x180027182  cmp     ebx, 88h
0x180027188  jz      short loc_1800271A8
0x18002718a  xorps   xmm0, xmm0
0x18002718d  lea     rcx, ModuleName; "mpunits.dll"
0x180027194  movups  [rbp+var_30], xmm0
0x180027198  call    cs:__imp_GetModuleHandleA
0x18002719e  mov     edx, 7ECh
0x1800271a3  jmp     loc_180027107
0x1800271a8  cmp     ebx, 83h
0x1800271ae  jz      short loc_1800271B3
0x1800271b0  mov     [r15], sil
0x1800271b3  mov     eax, dword ptr [rbp+Size+4]
0x1800271b6  cmp     eax, r14d
0x1800271b9  jbe     short loc_1800271D9
0x1800271bb  xorps   xmm0, xmm0
0x1800271be  lea     rcx, ModuleName; "mpunits.dll"
0x1800271c5  movups  [rbp+var_30], xmm0
0x1800271c9  call    cs:__imp_GetModuleHandleA
0x1800271cf  mov     edx, 7EDh
0x1800271d4  jmp     loc_180027107
0x1800271d9  cmp     eax, [rdi+40h]
0x1800271dc  jbe     short loc_18002720D
0x1800271de  cmp     [rdi+40h], r13d
0x1800271e2  jbe     short loc_1800271F5
0x1800271e4  mov     rcx, [rdi+38h]; Block
0x1800271e8  call    cs:__imp_free
0x1800271ee  mov     eax, dword ptr [rbp+Size+4]
0x1800271f1  mov     rbx, [rbp+Size]
0x1800271f5  mov     ecx, eax; Size
0x1800271f7  mov     [rdi+40h], ecx
0x1800271fa  call    cs:__imp_malloc
0x180027200  mov     [rdi+38h], rax
0x180027204  test    rax, rax
0x180027207  jz      loc_1800270BC
0x18002720d  mov     rax, [rdi+38h]
0x180027211  mov     [rax], rbx
0x180027214  mov     r8d, dword ptr [rbp+Size+4]
0x180027218  mov     rdx, [rdi+38h]
0x18002721c  add     r8d, 0FFFFFFF8h; MaxCharCount
0x180027220  mov     ecx, [rdi+4]; FileHandle
0x180027223  add     rdx, 8; DstBuf
0x180027227  call    cs:__imp__read
0x18002722d  mov     edx, dword ptr [rbp+Size+4]
0x180027230  sub     rdx, 8
0x180027234  movsxd  rcx, eax
0x180027237  cmp     rcx, rdx
0x18002723a  jnz     loc_1800270EE
0x180027240  mov     [r12], eax
0x180027244  lea     rcx, [rbp+var_20]
0x180027248  call    Logger_UnlockPartOfFile
0x18002724d  mov     ebx, eax
0x18002724f  jmp     loc_18002714F
```
