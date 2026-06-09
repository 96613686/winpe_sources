# CStowedExceptionPlugin::CalculateRemoteStringLength(ulong *,void *,void *,ulong)

- ea: `0x18003170c`
- end: `0x180031847`
- name: `?CalculateRemoteStringLength@CStowedExceptionPlugin@@CAJPEAKPEAX1K@Z`
- size: `315`
- prototype: `__int64 __fastcall(unsigned int *, void *, char *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180030e2c`
- `0x180031d50`

## callees

- `0x18003170c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800317e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031815`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800317e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031815`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180031778`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180031778`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180031745`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180031745`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18003180d`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18003180d`

## pseudocode

```c
__int64 __fastcall CStowedExceptionPlugin::CalculateRemoteStringLength(unsigned int *a1, void *a2, char *a3)
{
  _WORD *v6; // rbx
  unsigned int v7; // edi
  __int64 v8; // rax
  _WORD *v9; // rcx
  signed int v10; // edi
  unsigned int v11; // eax
  signed int LastError; // eax
  signed int v13; // eax
  SIZE_T NumberOfBytesRead; // [rsp+80h] [rbp+8h] BYREF

  *a1 = 0;
  NumberOfBytesRead = 0;
  v6 = VirtualAlloc(0, 0x1000u, 0x1000u, 4u);
  if ( v6 )
  {
    v7 = 0;
    while ( ReadProcessMemory(a2, a3, v6, 0x1000u, &NumberOfBytesRead) )
    {
      if ( NumberOfBytesRead != 4096 )
      {
        v10 = -2147024597;
        goto LABEL_19;
      }
      v8 = 2048;
      v9 = v6;
      do
      {
        if ( !*v9 )
          break;
        ++v9;
        --v8;
      }
      while ( v8 );
      if ( v8 )
      {
        v11 = v7 + (((2 * (2048 - (_DWORD)v8)) & (unsigned int)-(v8 != 0)) >> 1);
        *a1 = v11;
        if ( v11 < 0x7FFF )
        {
          v10 = 0;
          goto LABEL_19;
        }
LABEL_11:
        v10 = -805306106;
        goto LABEL_19;
      }
      a3 += 4096;
      v7 += 2048;
      if ( v7 >= 0x7FFF )
      {
        *a1 = v7;
        goto LABEL_11;
      }
    }
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( v10 >= 0 )
      v10 = -2147467259;
LABEL_19:
    VirtualFree(v6, 0, 0x8000u);
  }
  else
  {
    v13 = GetLastError();
    v10 = v13;
    if ( v13 > 0 )
      v10 = (unsigned __int16)v13 | 0x80070000;
    if ( v10 >= 0 )
      return (unsigned int)-2147467259;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18003170c  mov     rax, rsp
0x18003170f  push    rbx
0x180031710  push    rbp
0x180031711  push    rsi
0x180031712  push    rdi
0x180031713  push    r12
0x180031715  push    r13
0x180031717  push    r14
0x180031719  push    r15
0x18003171b  sub     rsp, 38h
0x18003171f  xor     r12d, r12d
0x180031722  mov     r13d, 1000h
0x180031728  mov     rbp, r8
0x18003172b  mov     [rcx], r12d
0x18003172e  mov     r15, rdx
0x180031731  mov     [rax+8], r12
0x180031735  mov     r14, rcx
0x180031738  mov     r8d, r13d; flAllocationType
0x18003173b  lea     r9d, [r12+4]; flProtect
0x180031740  mov     edx, r13d; dwSize
0x180031743  xor     ecx, ecx; lpAddress
0x180031745  call    cs:__imp_VirtualAlloc
0x18003174b  mov     rbx, rax
0x18003174e  test    rax, rax
0x180031751  jz      loc_180031815
0x180031757  mov     edi, r12d
0x18003175a  mov     esi, 800h
0x18003175f  lea     rax, [rsp+78h+NumberOfBytesRead]
0x180031767  mov     r9, r13; nSize
0x18003176a  mov     r8, rbx; lpBuffer
0x18003176d  mov     [rsp+78h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x180031772  mov     rdx, rbp; lpBaseAddress
0x180031775  mov     rcx, r15; hProcess
0x180031778  call    cs:__imp_ReadProcessMemory
0x18003177e  test    eax, eax
0x180031780  jz      short loc_1800317E3
0x180031782  cmp     [rsp+78h+NumberOfBytesRead], r13
0x18003178a  jnz     short loc_1800317DC
0x18003178c  mov     rax, rsi
0x18003178f  mov     rcx, rbx
0x180031792  cmp     [rcx], r12w
0x180031796  jz      short loc_1800317A2
0x180031798  add     rcx, 2
0x18003179c  sub     rax, 1
0x1800317a0  jnz     short loc_180031792
0x1800317a2  test    rax, rax
0x1800317a5  jnz     short loc_1800317BE
0x1800317a7  add     rbp, r13
0x1800317aa  add     edi, esi
0x1800317ac  cmp     edi, 7FFFh
0x1800317b2  jb      short loc_18003175F
0x1800317b4  mov     [r14], edi
0x1800317b7  mov     edi, 0D0000106h
0x1800317bc  jmp     short loc_180031802
0x1800317be  sub     esi, eax
0x1800317c0  add     esi, esi
0x1800317c2  neg     rax
0x1800317c5  sbb     eax, eax
0x1800317c7  and     eax, esi
0x1800317c9  shr     eax, 1
0x1800317cb  add     eax, edi
0x1800317cd  mov     [r14], eax
0x1800317d0  cmp     eax, 7FFFh
0x1800317d5  jnb     short loc_1800317B7
0x1800317d7  mov     edi, r12d
0x1800317da  jmp     short loc_180031802
0x1800317dc  mov     edi, 8007012Bh
0x1800317e1  jmp     short loc_180031802
0x1800317e3  call    cs:__imp_GetLastError
0x1800317e9  mov     edi, eax
0x1800317eb  test    eax, eax
0x1800317ed  jle     short loc_1800317F8
0x1800317ef  movzx   edi, ax
0x1800317f2  or      edi, 80070000h
0x1800317f8  test    edi, edi
0x1800317fa  mov     eax, 80004005h
0x1800317ff  cmovns  edi, eax
0x180031802  xor     edx, edx; dwSize
0x180031804  mov     r8d, 8000h; dwFreeType
0x18003180a  mov     rcx, rbx; lpAddress
0x18003180d  call    cs:__imp_VirtualFree
0x180031813  jmp     short loc_180031834
0x180031815  call    cs:__imp_GetLastError
0x18003181b  mov     edi, eax
0x18003181d  test    eax, eax
0x18003181f  jle     short loc_18003182A
0x180031821  movzx   edi, ax
0x180031824  or      edi, 80070000h
0x18003182a  test    edi, edi
0x18003182c  mov     eax, 80004005h
0x180031831  cmovns  edi, eax
0x180031834  mov     eax, edi
0x180031836  add     rsp, 38h
0x18003183a  pop     r15
0x18003183c  pop     r14
0x18003183e  pop     r13
0x180031840  pop     r12
0x180031842  pop     rdi
0x180031843  pop     rsi
0x180031844  pop     rbp
0x180031845  pop     rbx
0x180031846  retn
```
