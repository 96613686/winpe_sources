# PersistMasterKeyToStorage(MASTERKEY_STORED *,ulong,uchar *,ulong)

- ea: `0x180012da4`
- end: `0x180012ef7`
- name: `?PersistMasterKeyToStorage@@YAKPEAUMASTERKEY_STORED@@KPEAEK@Z`
- size: `339`
- prototype: `__int64 __fastcall(struct MASTERKEY_STORED *, int, unsigned __int8 *, unsigned int)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000e9c0`
- `0x180012258`
- `0x1800180cc`
- `0x18002a794`
- `0x18002d330`
- `0x18002ea4c`

## callees

- `0x180007f10`
- `0x180012da4`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012e38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012ecc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012e38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012ecc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012e4e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012e4e`

## string_xrefs

- `0x180012e71`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`

## pseudocode

```c
__int64 __fastcall PersistMasterKeyToStorage(struct MASTERKEY_STORED *a1, int a2, unsigned __int8 *a3, unsigned int a4)
{
  SIZE_T v4; // rbp
  int v7; // edx
  int v8; // edx
  __int64 v10; // rdi
  __int64 v11; // rsi
  _BYTE *v12; // rcx
  __int64 v13; // rax
  size_t v14; // r14
  _BYTE *v15; // rax
  __int64 i; // rcx

  v4 = a4;
  if ( a2 )
  {
    v7 = a2 - 1;
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( v8 )
      {
        if ( v8 != 1 )
          return 2148073475LL;
        v10 = 152;
        v11 = 144;
      }
      else
      {
        v10 = 136;
        v11 = 128;
      }
    }
    else
    {
      v10 = 120;
      v11 = 112;
    }
  }
  else
  {
    v10 = 104;
    v11 = 100;
  }
  if ( !a3 || !a4 )
  {
    v15 = *(_BYTE **)((char *)a1 + v10);
    if ( v15 )
    {
      for ( i = *(unsigned int *)((char *)a1 + v11); i; --i )
        *v15++ = 0;
      LocalFree(*(HLOCAL *)((char *)a1 + v10));
    }
    *(_QWORD *)((char *)a1 + v10) = 0;
    *(_DWORD *)((char *)a1 + v11) = 0;
    return 0;
  }
  v12 = *(_BYTE **)((char *)a1 + v10);
  if ( v12 )
  {
    v13 = *(unsigned int *)((char *)a1 + v11);
    if ( *(_DWORD *)((char *)a1 + v11) )
    {
      do
      {
        *v12++ = 0;
        --v13;
      }
      while ( v13 );
      v12 = *(_BYTE **)((char *)a1 + v10);
    }
    v14 = a4;
    if ( *(_DWORD *)((char *)a1 + v11) >= a4 )
      goto LABEL_20;
    LocalFree(v12);
  }
  else
  {
    v14 = a4;
  }
  *(_QWORD *)((char *)a1 + v10) = LocalAlloc(0, v4);
LABEL_20:
  *(_DWORD *)((char *)a1 + v11) = 0;
  if ( !*(_QWORD *)((char *)a1 + v10) )
  {
    DebugTraceError(
      1130,
      "ERROR_NOT_ENOUGH_SERVER_MEMORY",
      "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp",
      4896);
    return 1130;
  }
  *(_DWORD *)((char *)a1 + v11) = v4;
  memcpy_0(*(void **)((char *)a1 + v10), a3, v14);
  *((_DWORD *)a1 + 1) = 1;
  return 0;
}

```

## disassembly

```asm
0x180012da4  push    rbx
0x180012da6  push    rbp
0x180012da7  push    rsi
0x180012da8  push    rdi
0x180012da9  push    r14
0x180012dab  push    r15
0x180012dad  sub     rsp, 28h
0x180012db1  mov     ebp, r9d
0x180012db4  mov     r15, r8
0x180012db7  mov     rbx, rcx
0x180012dba  test    edx, edx
0x180012dbc  jz      short loc_180012DF5
0x180012dbe  sub     edx, 1
0x180012dc1  jz      short loc_180012DEB
0x180012dc3  sub     edx, 1
0x180012dc6  jz      short loc_180012DE1
0x180012dc8  cmp     edx, 1
0x180012dcb  jz      short loc_180012DD7
0x180012dcd  mov     eax, 80090003h
0x180012dd2  jmp     loc_180012EE9
0x180012dd7  mov     edi, 98h
0x180012ddc  lea     esi, [rdi-8]
0x180012ddf  jmp     short loc_180012DFD
0x180012de1  mov     edi, 88h
0x180012de6  lea     esi, [rdi-8]
0x180012de9  jmp     short loc_180012DFD
0x180012deb  mov     edi, 78h ; 'x'
0x180012df0  lea     esi, [rdi-8]
0x180012df3  jmp     short loc_180012DFD
0x180012df5  mov     edi, 68h ; 'h'
0x180012dfa  lea     esi, [rdi-4]
0x180012dfd  test    r15, r15
0x180012e00  jz      loc_180012EAB
0x180012e06  test    r9d, r9d
0x180012e09  jz      loc_180012EAB
0x180012e0f  mov     rcx, [rdi+rcx]
0x180012e13  test    rcx, rcx
0x180012e16  jz      short loc_180012E46
0x180012e18  mov     eax, [rsi+rbx]
0x180012e1b  test    rax, rax
0x180012e1e  jz      short loc_180012E30
0x180012e20  mov     byte ptr [rcx], 0
0x180012e23  inc     rcx
0x180012e26  sub     rax, 1
0x180012e2a  jnz     short loc_180012E20
0x180012e2c  mov     rcx, [rdi+rbx]; hMem
0x180012e30  mov     r14, rbp
0x180012e33  cmp     [rsi+rbx], ebp
0x180012e36  jnb     short loc_180012E5E
0x180012e38  call    cs:__imp_LocalFree
0x180012e3f  nop     dword ptr [rax+rax+00h]
0x180012e44  jmp     short loc_180012E49
0x180012e46  mov     r14, rbp
0x180012e49  mov     rdx, rbp; uBytes
0x180012e4c  xor     ecx, ecx; uFlags
0x180012e4e  call    cs:__imp_LocalAlloc
0x180012e55  nop     dword ptr [rax+rax+00h]
0x180012e5a  mov     [rdi+rbx], rax
0x180012e5e  mov     dword ptr [rsi+rbx], 0
0x180012e65  cmp     qword ptr [rdi+rbx], 0
0x180012e6a  jnz     short loc_180012E90
0x180012e6c  mov     ebx, 46Ah
0x180012e71  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180012e78  mov     ecx, ebx
0x180012e7a  lea     rdx, aErrorNotEnough_0; "ERROR_NOT_ENOUGH_SERVER_MEMORY"
0x180012e81  mov     r9d, 1320h
0x180012e87  call    DebugTraceError
0x180012e8c  mov     eax, ebx
0x180012e8e  jmp     short loc_180012EE9
0x180012e90  mov     [rsi+rbx], ebp
0x180012e93  mov     r8, r14; Size
0x180012e96  mov     rcx, [rdi+rbx]; void *
0x180012e9a  mov     rdx, r15; Src
0x180012e9d  call    memcpy_0
0x180012ea2  mov     dword ptr [rbx+4], 1
0x180012ea9  jmp     short loc_180012EE7
0x180012eab  mov     rax, [rdi+rcx]
0x180012eaf  test    rax, rax
0x180012eb2  jz      short loc_180012ED8
0x180012eb4  mov     ecx, [rsi+rcx]
0x180012eb7  test    rcx, rcx
0x180012eba  jz      short loc_180012EC8
0x180012ebc  mov     byte ptr [rax], 0
0x180012ebf  inc     rax
0x180012ec2  sub     rcx, 1
0x180012ec6  jnz     short loc_180012EBC
0x180012ec8  mov     rcx, [rdi+rbx]; hMem
0x180012ecc  call    cs:__imp_LocalFree
0x180012ed3  nop     dword ptr [rax+rax+00h]
0x180012ed8  mov     qword ptr [rdi+rbx], 0
0x180012ee0  mov     dword ptr [rsi+rbx], 0
0x180012ee7  xor     eax, eax
0x180012ee9  add     rsp, 28h
0x180012eed  pop     r15
0x180012eef  pop     r14
0x180012ef1  pop     rdi
0x180012ef2  pop     rsi
0x180012ef3  pop     rbp
0x180012ef4  pop     rbx
0x180012ef5  retn
```
