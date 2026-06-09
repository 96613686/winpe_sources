# AslpFileQueryVersionString

- ea: `0x14000fb14`
- end: `0x14000fd83`
- name: `AslpFileQueryVersionString`
- size: `623`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *, __int64, unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14000f3a8`

## callees

- `0x140004998`
- `0x140004ca4`
- `0x140007074`
- `0x14000fb14`
- `0x14000fee8`
- `0x140010108`
- `0x1400115f0`

## string_xrefs

- `0x14000fd3f`: `RtlStringCchCopyW failed [%x]`

## pseudocode

```c
__int64 __fastcall AslpFileQueryVersionString(
        _QWORD *a1,
        _QWORD *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned __int64 a5,
        unsigned __int16 *a6)
{
  __int64 v10; // rdi
  __int64 v11; // rcx
  wchar_t *v12; // r8
  unsigned __int16 *v13; // rax
  __int64 v14; // rdx
  unsigned __int16 *v15; // rcx
  signed int v16; // ebx
  int v17; // eax
  const char *v18; // r9
  __int64 v19; // r8
  unsigned __int64 v20; // rdi
  int v21; // eax
  __int64 v23; // [rsp+20h] [rbp-E0h]
  __int64 v24; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v25; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v26; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v27; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v28; // [rsp+50h] [rbp-B0h]
  unsigned __int16 v29[128]; // [rsp+60h] [rbp-A0h] BYREF

  *a1 = 0;
  v28 = a6;
  *a2 = 0;
  v10 = 0;
  v29[0] = 0;
  v27 = 0;
  v26 = 0;
  v25 = 0;
  v24 = 0;
  while ( 1 )
  {
    v11 = 2147483646;
    v12 = off_140013C40[v10];
    v13 = v29;
    v14 = 128;
    do
    {
      if ( !v11 )
        break;
      if ( !*v12 )
        break;
      *v13++ = *v12++;
      --v11;
      --v14;
    }
    while ( v14 );
    v15 = v13 - 1;
    if ( v14 )
      v15 = v13;
    *v15 = 0;
    v16 = v14 == 0 ? 0x80000005 : 0;
    if ( !v14 )
      break;
    v16 = RtlStringCchCatW(v29, 128, v28);
    if ( v16 < 0 )
    {
      v18 = "RtlStringCchCatW failed [%x]";
      v19 = 3110;
      goto LABEL_29;
    }
    v17 = AslpFileVerQueryBlock(a3, v29, &v25, &v24);
    v16 = v17;
    if ( v17 >= 0 )
    {
      if ( (int)AslpFileVerStringBlockGetValue(&v27, &v26, v25, v24) < 0 )
      {
LABEL_16:
        if ( !a4 )
          return 3221226021LL;
        v20 = 0;
        if ( !a5 )
          return 3221226021LL;
        while ( 1 )
        {
          LODWORD(v23) = a4[1];
          v16 = RtlStringCchPrintfW(v29, 128, L"\\StringFileInfo\\%04X%04X\\%s", *a4, v23, v28);
          if ( v16 < 0 )
          {
            v18 = "RtlStringCchPrintfW failed [%x]";
            v19 = 3158;
            goto LABEL_29;
          }
          v21 = AslpFileVerQueryBlock(a3, v29, &v25, &v24);
          v16 = v21;
          if ( v21 >= 0 )
            break;
          if ( v21 != -1073741275 )
          {
            v18 = "AslpFileVerQueryBlock failed [%x]";
            v19 = 3188;
            goto LABEL_29;
          }
          ++v20;
          a4 += 2;
          if ( v20 >= a5 )
            return 3221226021LL;
        }
        if ( (int)AslpFileVerStringBlockGetValue(&v27, &v26, v25, v24) < 0 )
          return 3221226021LL;
      }
      *a2 = v26;
      *a1 = v27;
      return 0;
    }
    if ( v17 != -1073741275 )
    {
      v18 = "AslpFileVerQueryBlock failed [%x]";
      v19 = 3140;
      goto LABEL_29;
    }
    if ( (unsigned __int64)++v10 >= 4 )
      goto LABEL_16;
  }
  v18 = "RtlStringCchCopyW failed [%x]";
  v19 = 3104;
LABEL_29:
  LODWORD(v23) = v16;
  AslLogCallPrintf(1, "AslpFileQueryVersionString", v19, v18, v23);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x14000fb14  push    rbp
0x14000fb16  push    rbx
0x14000fb17  push    rsi
0x14000fb18  push    rdi
0x14000fb19  push    r12
0x14000fb1b  push    r13
0x14000fb1d  push    r14
0x14000fb1f  push    r15
0x14000fb21  lea     rbp, [rsp-78h]
0x14000fb26  sub     rsp, 178h
0x14000fb2d  mov     rax, cs:__security_cookie
0x14000fb34  xor     rax, rsp
0x14000fb37  mov     [rbp+0B0h+var_50], rax
0x14000fb3b  xor     esi, esi
0x14000fb3d  mov     r14, r9
0x14000fb40  mov     r9, [rbp+0B0h+arg_28]
0x14000fb47  mov     r13, r8
0x14000fb4a  mov     [rcx], rsi
0x14000fb4d  mov     r12, rdx
0x14000fb50  mov     [rsp+1B0h+var_160], r9
0x14000fb55  mov     r15, rcx
0x14000fb58  mov     [rdx], rsi
0x14000fb5b  mov     edi, esi
0x14000fb5d  mov     [rsp+1B0h+var_150], si
0x14000fb62  mov     [rsp+1B0h+var_168], rsi
0x14000fb67  mov     [rsp+1B0h+var_170], rsi
0x14000fb6c  mov     [rsp+1B0h+var_178], rsi
0x14000fb71  mov     [rsp+1B0h+var_180], rsi
0x14000fb76  lea     r8, off_140013C40; "\\StringFileInfo\\000004B0\\"
0x14000fb7d  mov     ecx, 7FFFFFFEh
0x14000fb82  mov     r8, [r8+rdi*8]
0x14000fb86  lea     rax, [rsp+1B0h+var_150]
0x14000fb8b  mov     edx, 80h
0x14000fb90  test    rcx, rcx
0x14000fb93  jz      short loc_14000FBB4
0x14000fb95  movzx   r9d, word ptr [r8]
0x14000fb99  test    r9w, r9w
0x14000fb9d  jz      short loc_14000FBB4
0x14000fb9f  mov     [rax], r9w
0x14000fba3  add     r8, 2
0x14000fba7  add     rax, 2
0x14000fbab  dec     rcx
0x14000fbae  sub     rdx, 1
0x14000fbb2  jnz     short loc_14000FB90
0x14000fbb4  test    rdx, rdx
0x14000fbb7  lea     rcx, [rax-2]
0x14000fbbb  cmovnz  rcx, rax
0x14000fbbf  mov     rax, rdx
0x14000fbc2  neg     rax
0x14000fbc5  sbb     ebx, ebx
0x14000fbc7  not     ebx
0x14000fbc9  mov     [rcx], si
0x14000fbcc  and     ebx, 80000005h
0x14000fbd2  test    rdx, rdx
0x14000fbd5  jz      loc_14000FD3F
0x14000fbdb  mov     r8, [rsp+1B0h+var_160]; unsigned __int16 *
0x14000fbe0  lea     rcx, [rsp+1B0h+var_150]; unsigned __int16 *
0x14000fbe5  mov     edx, 80h; unsigned __int64
0x14000fbea  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000fbef  mov     ebx, eax
0x14000fbf1  test    eax, eax
0x14000fbf3  js      loc_14000FD30
0x14000fbf9  lea     r9, [rsp+1B0h+var_180]
0x14000fbfe  mov     rcx, r13
0x14000fc01  lea     r8, [rsp+1B0h+var_178]
0x14000fc06  lea     rdx, [rsp+1B0h+var_150]
0x14000fc0b  call    AslpFileVerQueryBlock
0x14000fc10  mov     ebx, eax
0x14000fc12  test    eax, eax
0x14000fc14  jns     short loc_14000FC3E
0x14000fc16  cmp     eax, 0C0000225h
0x14000fc1b  jnz     short loc_14000FC2C
0x14000fc1d  inc     rdi
0x14000fc20  cmp     rdi, 4
0x14000fc24  jb      loc_14000FB76
0x14000fc2a  jmp     short loc_14000FC5F
0x14000fc2c  lea     r9, aAslpfileverque_0; "AslpFileVerQueryBlock failed [%x]"
0x14000fc33  mov     r8d, 0C44h
0x14000fc39  jmp     loc_14000FD4C
0x14000fc3e  mov     r9, [rsp+1B0h+var_180]
0x14000fc43  lea     rdx, [rsp+1B0h+var_170]
0x14000fc48  mov     r8, [rsp+1B0h+var_178]
0x14000fc4d  lea     rcx, [rsp+1B0h+var_168]
0x14000fc52  call    AslpFileVerStringBlockGetValue
0x14000fc57  test    eax, eax
0x14000fc59  jns     loc_14000FD0C
0x14000fc5f  test    r14, r14
0x14000fc62  jz      short loc_14000FCD6
0x14000fc64  mov     rdi, rsi
0x14000fc67  mov     rsi, [rbp+0B0h+arg_20]
0x14000fc6e  test    rsi, rsi
0x14000fc71  jz      short loc_14000FCD6
0x14000fc73  mov     rcx, [rsp+1B0h+var_160]
0x14000fc78  lea     r8, aStringfileinfo; "\\StringFileInfo\\%04X%04X\\%s"
0x14000fc7f  movzx   eax, word ptr [r14+2]
0x14000fc84  mov     edx, 80h
0x14000fc89  movzx   r9d, word ptr [r14]
0x14000fc8d  mov     [rsp+1B0h+var_188], rcx
0x14000fc92  lea     rcx, [rsp+1B0h+var_150]
0x14000fc97  mov     dword ptr [rsp+1B0h+var_190], eax
0x14000fc9b  call    RtlStringCchPrintfW
0x14000fca0  mov     ebx, eax
0x14000fca2  test    eax, eax
0x14000fca4  js      short loc_14000FD21
0x14000fca6  lea     r9, [rsp+1B0h+var_180]
0x14000fcab  mov     rcx, r13
0x14000fcae  lea     r8, [rsp+1B0h+var_178]
0x14000fcb3  lea     rdx, [rsp+1B0h+var_150]
0x14000fcb8  call    AslpFileVerQueryBlock
0x14000fcbd  mov     ebx, eax
0x14000fcbf  test    eax, eax
0x14000fcc1  jns     short loc_14000FCEF
0x14000fcc3  cmp     eax, 0C0000225h
0x14000fcc8  jnz     short loc_14000FCE0
0x14000fcca  inc     rdi
0x14000fccd  add     r14, 4
0x14000fcd1  cmp     rdi, rsi
0x14000fcd4  jb      short loc_14000FC73
0x14000fcd6  mov     eax, 0C0000225h
0x14000fcdb  jmp     loc_14000FD63
0x14000fce0  lea     r9, aAslpfileverque_0; "AslpFileVerQueryBlock failed [%x]"
0x14000fce7  mov     r8d, 0C74h
0x14000fced  jmp     short loc_14000FD4C
0x14000fcef  mov     r9, [rsp+1B0h+var_180]
0x14000fcf4  lea     rdx, [rsp+1B0h+var_170]
0x14000fcf9  mov     r8, [rsp+1B0h+var_178]
0x14000fcfe  lea     rcx, [rsp+1B0h+var_168]
0x14000fd03  call    AslpFileVerStringBlockGetValue
0x14000fd08  test    eax, eax
0x14000fd0a  js      short loc_14000FCD6
0x14000fd0c  mov     rax, [rsp+1B0h+var_170]
0x14000fd11  mov     [r12], rax
0x14000fd15  mov     rax, [rsp+1B0h+var_168]
0x14000fd1a  mov     [r15], rax
0x14000fd1d  xor     eax, eax
0x14000fd1f  jmp     short loc_14000FD63
0x14000fd21  lea     r9, aRtlstringcchpr; "RtlStringCchPrintfW failed [%x]"
0x14000fd28  mov     r8d, 0C56h
0x14000fd2e  jmp     short loc_14000FD4C
0x14000fd30  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x14000fd37  mov     r8d, 0C26h
0x14000fd3d  jmp     short loc_14000FD4C
0x14000fd3f  lea     r9, aRtlstringcchco; "RtlStringCchCopyW failed [%x]"
0x14000fd46  mov     r8d, 0C20h
0x14000fd4c  lea     rdx, aAslpfilequeryv; "AslpFileQueryVersionString"
0x14000fd53  mov     dword ptr [rsp+1B0h+var_190], ebx
0x14000fd57  mov     ecx, 1
0x14000fd5c  call    AslLogCallPrintf
0x14000fd61  mov     eax, ebx
0x14000fd63  mov     rcx, [rbp+0B0h+var_50]
0x14000fd67  xor     rcx, rsp; StackCookie
0x14000fd6a  call    __security_check_cookie
0x14000fd6f  add     rsp, 178h
0x14000fd76  pop     r15
0x14000fd78  pop     r14
0x14000fd7a  pop     r13
0x14000fd7c  pop     r12
0x14000fd7e  pop     rdi
0x14000fd7f  pop     rsi
0x14000fd80  pop     rbx
0x14000fd81  pop     rbp
0x14000fd82  retn
```
