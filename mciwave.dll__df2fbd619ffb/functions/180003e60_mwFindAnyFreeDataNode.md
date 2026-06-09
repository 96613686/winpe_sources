# mwFindAnyFreeDataNode

- ea: `0x180003e60`
- end: `0x180004020`
- name: `mwFindAnyFreeDataNode`
- size: `448`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000180c`
- `0x180001aa8`
- `0x18000276c`
- `0x180004318`

## callees

- `0x180003a44`
- `0x180003e60`
- `0x180005c29`
- `0x180005c60`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180003f72`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180003f72`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180003fa3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180003fa3`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180003f4f`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180003f4f`

## pseudocode

```c
__int64 __fastcall mwFindAnyFreeDataNode(__int64 a1, unsigned int a2)
{
  unsigned int v2; // r11d
  unsigned int *v3; // rdi
  __int64 v4; // r9
  unsigned int v5; // r8d
  int v8; // ebp
  unsigned int v9; // r10d
  _DWORD *v10; // rdx
  unsigned int v11; // ecx
  unsigned int v12; // esi
  __int64 v13; // rax
  int v14; // ecx
  unsigned int v15; // ecx
  HANDLE FileW; // rax
  __int64 v18; // rcx
  __int64 v19; // rdx
  WCHAR PathName[264]; // [rsp+40h] [rbp-258h] BYREF

  v2 = *(_DWORD *)(a1 + 128);
  v3 = (unsigned int *)(a1 + 132);
  v4 = *(_QWORD *)(a1 + 104);
  v5 = 0;
  v8 = -1;
  v9 = -1;
  if ( v2 )
  {
    v10 = *(_DWORD **)(a1 + 104);
    do
    {
      if ( v10[1] == -1 )
      {
        v11 = v10[2];
        if ( v11 >= a2 )
        {
          v10[1] = 0;
          return v5;
        }
        if ( v11 )
        {
          if ( *v10 + v11 == *v3 )
            v9 = v5;
        }
        else
        {
          v8 = v5;
        }
      }
      v10 += 4;
      ++v5;
    }
    while ( v5 < v2 );
  }
  v12 = *(_DWORD *)(a1 + 148) + a2 - 1 - (*(_DWORD *)(a1 + 148) + a2 - 1) % *(_DWORD *)(a1 + 148);
  if ( v9 != -1 )
  {
    v13 = 2LL * v9;
    v14 = *(_DWORD *)(v4 + 16LL * v9) & 0x7FFFFFFF;
    *(_DWORD *)(v4 + 8 * v13 + 4) = 0;
    v15 = v12 + v14;
    *(_DWORD *)(v4 + 8 * v13 + 8) = v12;
    if ( v15 > *v3 )
      *v3 = v15;
    return v5;
  }
  if ( *(_QWORD *)(a1 + 88) == -1 )
  {
    memset_0(PathName, 0, 0x208u);
    if ( !(unsigned int)GetTempPath2W(260, PathName)
      || !GetTempFileNameW(PathName, aszPrefix, 0, (LPWSTR)(a1 + 776))
      || (FileW = CreateFileW((LPCWSTR)(a1 + 776), 0xC0000000, 0, 0, 2u, 0x80u, 0),
          *(_QWORD *)(a1 + 88) = FileW,
          FileW == (HANDLE)-1LL) )
    {
      *(_DWORD *)(a1 + 140) = 349;
      return 0xFFFFFFFFLL;
    }
  }
  if ( v8 == -1 )
  {
    v5 = mwAllocMoreBlockNodes(a1);
    if ( v5 == -1 )
      return 0xFFFFFFFFLL;
  }
  else
  {
    v5 = v8;
  }
  v18 = *(_QWORD *)(a1 + 104);
  v19 = 2LL * v5;
  *(_DWORD *)(v18 + 8 * v19) = *v3 | 0x80000000;
  *(_DWORD *)(v18 + 8 * v19 + 4) = 0;
  *(_DWORD *)(v18 + 8 * v19 + 8) = v12;
  *v3 += v12;
  return v5;
}

```

## disassembly

```asm
0x180003e60  push    rbx
0x180003e62  push    rbp
0x180003e63  push    rsi
0x180003e64  push    rdi
0x180003e65  push    r14
0x180003e67  push    r15
0x180003e69  sub     rsp, 268h
0x180003e70  mov     rax, cs:__security_cookie
0x180003e77  xor     rax, rsp
0x180003e7a  mov     [rsp+298h+var_48], rax
0x180003e82  mov     r11d, [rcx+80h]
0x180003e89  lea     rdi, [rcx+84h]
0x180003e90  mov     r9, [rcx+68h]
0x180003e94  or      r15d, 0FFFFFFFFh
0x180003e98  xor     r8d, r8d
0x180003e9b  mov     esi, edx
0x180003e9d  mov     rbx, rcx
0x180003ea0  mov     ebp, r15d
0x180003ea3  mov     r10d, r15d
0x180003ea6  test    r11d, r11d
0x180003ea9  jz      short loc_180003ED8
0x180003eab  mov     rdx, r9
0x180003eae  cmp     [rdx+4], r15d
0x180003eb2  jnz     short loc_180003ECC
0x180003eb4  mov     ecx, [rdx+8]
0x180003eb7  cmp     ecx, esi
0x180003eb9  jnb     short loc_180003F1C
0x180003ebb  test    ecx, ecx
0x180003ebd  jnz     short loc_180003EC4
0x180003ebf  mov     ebp, r8d
0x180003ec2  jmp     short loc_180003ECC
0x180003ec4  add     ecx, [rdx]
0x180003ec6  cmp     ecx, [rdi]
0x180003ec8  cmovz   r10d, r8d
0x180003ecc  add     rdx, 10h
0x180003ed0  inc     r8d
0x180003ed3  cmp     r8d, r11d
0x180003ed6  jb      short loc_180003EAE
0x180003ed8  mov     ecx, [rbx+94h]
0x180003ede  dec     esi
0x180003ee0  add     esi, ecx
0x180003ee2  xor     edx, edx
0x180003ee4  mov     eax, esi
0x180003ee6  div     ecx
0x180003ee8  sub     esi, edx
0x180003eea  cmp     r10d, r15d
0x180003eed  jz      short loc_180003F28
0x180003eef  mov     eax, r10d
0x180003ef2  add     rax, rax
0x180003ef5  mov     ecx, [r9+rax*8]
0x180003ef9  btr     ecx, 1Fh
0x180003efd  mov     dword ptr [r9+rax*8+4], 0
0x180003f06  add     ecx, esi
0x180003f08  mov     [r9+rax*8+8], esi
0x180003f0d  cmp     ecx, [rdi]
0x180003f0f  jbe     loc_180003FFD
0x180003f15  mov     [rdi], ecx
0x180003f17  jmp     loc_180003FFD
0x180003f1c  mov     dword ptr [rdx+4], 0
0x180003f23  jmp     loc_180003FFD
0x180003f28  cmp     qword ptr [rbx+58h], 0FFFFFFFFFFFFFFFFh
0x180003f2d  jnz     loc_180003FC2
0x180003f33  xor     edx, edx; Val
0x180003f35  lea     rcx, [rsp+298h+PathName]; void *
0x180003f3a  mov     r8d, 208h; Size
0x180003f40  call    memset_0
0x180003f45  lea     rdx, [rsp+298h+PathName]
0x180003f4a  mov     ecx, 104h
0x180003f4f  call    cs:__imp_GetTempPath2W
0x180003f55  test    eax, eax
0x180003f57  jz      short loc_180003FB3
0x180003f59  lea     r14, [rbx+308h]
0x180003f60  xor     r8d, r8d; uUnique
0x180003f63  mov     r9, r14; lpTempFileName
0x180003f66  lea     rdx, aszPrefix; "mci"
0x180003f6d  lea     rcx, [rsp+298h+PathName]; lpPathName
0x180003f72  call    cs:__imp_GetTempFileNameW
0x180003f78  test    eax, eax
0x180003f7a  jz      short loc_180003FB3
0x180003f7c  mov     [rsp+298h+hTemplateFile], 0; hTemplateFile
0x180003f85  xor     r9d, r9d; lpSecurityAttributes
0x180003f88  mov     [rsp+298h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180003f90  xor     r8d, r8d; dwShareMode
0x180003f93  mov     edx, 0C0000000h; dwDesiredAccess
0x180003f98  mov     [rsp+298h+dwCreationDisposition], 2; dwCreationDisposition
0x180003fa0  mov     rcx, r14; lpFileName
0x180003fa3  call    cs:__imp_CreateFileW
0x180003fa9  mov     [rbx+58h], rax
0x180003fad  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180003fb1  jnz     short loc_180003FC2
0x180003fb3  mov     dword ptr [rbx+8Ch], 15Dh
0x180003fbd  mov     eax, r15d
0x180003fc0  jmp     short loc_180004000
0x180003fc2  cmp     ebp, r15d
0x180003fc5  jz      short loc_180003FCC
0x180003fc7  mov     r8d, ebp
0x180003fca  jmp     short loc_180003FDC
0x180003fcc  mov     rcx, rbx
0x180003fcf  call    mwAllocMoreBlockNodes
0x180003fd4  mov     r8d, eax
0x180003fd7  cmp     eax, r15d
0x180003fda  jz      short loc_180003FBD
0x180003fdc  mov     eax, [rdi]
0x180003fde  mov     rcx, [rbx+68h]
0x180003fe2  bts     eax, 1Fh
0x180003fe6  mov     edx, r8d
0x180003fe9  add     rdx, rdx
0x180003fec  mov     [rcx+rdx*8], eax
0x180003fef  mov     dword ptr [rcx+rdx*8+4], 0
0x180003ff7  mov     [rcx+rdx*8+8], esi
0x180003ffb  add     [rdi], esi
0x180003ffd  mov     eax, r8d
0x180004000  mov     rcx, [rsp+298h+var_48]
0x180004008  xor     rcx, rsp; StackCookie
0x18000400b  call    __security_check_cookie
0x180004010  add     rsp, 268h
0x180004017  pop     r15
0x180004019  pop     r14
0x18000401b  pop     rdi
0x18000401c  pop     rsi
0x18000401d  pop     rbp
0x18000401e  pop     rbx
0x18000401f  retn
```
