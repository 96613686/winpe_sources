# I_UrlCacheWriteCryptBlobArray2

- ea: `0x18000195c`
- end: `0x180001c6c`
- name: `I_UrlCacheWriteCryptBlobArray2`
- size: `784`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800015bc`
- `0x180001878`
- `0x180002460`

## callees

- `0x1800017e0`
- `0x18000195c`
- `0x18002656a`
- `0x1800265b0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001a25`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001a25`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180001a51`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180001b0d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180001ba6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180001bdd`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180001c4b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180001a51`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180001b0d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180001ba6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180001bdd`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180001c4b`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180001aef`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180001b2b`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180001aef`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180001b2b`

## pseudocode

```c
__int64 __fastcall I_UrlCacheWriteCryptBlobArray2(
        const void *a1,
        void *a2,
        void *a3,
        _DWORD *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  unsigned int *v10; // r15
  __int64 v11; // xmm0_8
  __int64 v12; // rdi
  __int64 v13; // rax
  unsigned int v14; // edi
  unsigned int v15; // esi
  _WORD *v17; // rcx
  _QWORD *v18; // rax
  struct _FILETIME *v19; // rcx
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-A1h] BYREF
  DWORD v21; // [rsp+34h] [rbp-9Dh] BYREF
  _DWORD *v22; // [rsp+38h] [rbp-99h]
  LPCVOID lpBuffer; // [rsp+40h] [rbp-91h]
  _DWORD Buffer[3]; // [rsp+50h] [rbp-81h] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+5Ch] [rbp-75h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp-71h] BYREF
  int v27; // [rsp+68h] [rbp-69h]
  int v28; // [rsp+90h] [rbp-41h]
  __int64 v29; // [rsp+94h] [rbp-3Dh]
  int v30; // [rsp+9Ch] [rbp-35h]
  int v31; // [rsp+A0h] [rbp-31h]
  __int16 v32; // [rsp+A4h] [rbp-2Dh]
  __int16 v33; // [rsp+A6h] [rbp-2Bh]
  __int64 v34; // [rsp+A8h] [rbp-29h]
  int v35; // [rsp+B0h] [rbp-21h]
  DWORD v36; // [rsp+B4h] [rbp-1Dh]
  int v37; // [rsp+B8h] [rbp-19h]

  lpBuffer = a1;
  v22 = a4;
  NumberOfBytesWritten = 0;
  v10 = a4;
  memset_0(Buffer, 0, 0x70u);
  Buffer[0] = 112;
  Buffer[1] = 537002241;
  v27 = 40;
  if ( a5 )
  {
    v11 = *(_QWORD *)(a5 + 4);
    v28 = *(_DWORD *)a5;
    v30 = *(_DWORD *)(a5 + 12);
    v29 = v11;
  }
  else
  {
    v28 = 16;
  }
  if ( a3 )
    Buffer[2] = *v10;
  v12 = -1;
  if ( a1 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *((_WORD *)a1 + v13) );
  }
  else
  {
    LODWORD(v13) = 0;
  }
  nNumberOfBytesToWrite = 2 * v13 + 2;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v31 = 32;
  if ( a7 )
  {
    v17 = *(_WORD **)(a7 + 24);
    v32 = *(_WORD *)(a7 + 4);
    v33 = *(_WORD *)(a7 + 6);
    v34 = *(_QWORD *)(a7 + 8);
    v35 = *(_DWORD *)(a7 + 16);
    v37 = *(_DWORD *)(a7 + 32);
    if ( v17 )
    {
      if ( *v17 )
      {
        do
          ++v12;
        while ( v17[v12] );
        v36 = 2 * v12 + 2;
      }
    }
  }
  v14 = 0;
  if ( !WriteFile(a2, Buffer, 0x70u, &NumberOfBytesWritten, 0) )
    return 0;
  v15 = 1;
  if ( a3 )
  {
    while ( v14 < *v10 )
    {
      v21 = *(_DWORD *)(*((_QWORD *)v22 + 1) + 16LL * v14);
      if ( !WriteFile(a2, &v21, 4u, &NumberOfBytesWritten, 0)
        || v21 && !WriteFile(a3, *(LPCVOID *)(*((_QWORD *)v22 + 1) + 16LL * v14 + 8), v21, &NumberOfBytesWritten, 0) )
      {
        return 0;
      }
      v10 = v22;
      ++v14;
    }
    SetEndOfFile(a3);
  }
  if ( WriteFile(a2, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0)
    && (!v36 || WriteFile(a2, *(LPCVOID *)(a7 + 24), v36, &NumberOfBytesWritten, 0)) )
  {
    SetEndOfFile(a2);
    if ( a6 )
    {
      if ( *(_DWORD *)a6 > 8u )
      {
        v19 = *(struct _FILETIME **)(a6 + 8);
        if ( v19 )
          *v19 = SystemTimeAsFileTime;
      }
      if ( *(_DWORD *)a6 > 0x18u && *(_QWORD *)(a6 + 24) )
        I_UrlCacheZeroCbSizeStruct();
      if ( *(_DWORD *)a6 > 0x20u && *(_QWORD *)(a6 + 32) )
        I_UrlCacheZeroCbSizeStruct();
      if ( *(_DWORD *)a6 > 0x28u )
      {
        v18 = *(_QWORD **)(a6 + 40);
        if ( v18 )
          *v18 = 0;
      }
    }
  }
  else
  {
    return 0;
  }
  return v15;
}

```

## disassembly

```asm
0x18000195c  push    rbp
0x18000195e  push    rbx
0x18000195f  push    rsi
0x180001960  push    rdi
0x180001961  push    r12
0x180001963  push    r13
0x180001965  push    r14
0x180001967  push    r15
0x180001969  lea     rbp, [rsp-7]
0x18000196e  sub     rsp, 0D8h
0x180001975  mov     rax, cs:__security_cookie
0x18000197c  xor     rax, rsp
0x18000197f  mov     [rbp+3Fh+var_50], rax
0x180001983  mov     rbx, [rbp+3Fh+arg_28]
0x180001987  mov     r12, rdx
0x18000198a  mov     rdi, [rbp+3Fh+arg_20]
0x18000198e  xor     edx, edx; Val
0x180001990  mov     r14, [rbp+3Fh+arg_30]
0x180001994  mov     r13, r8
0x180001997  mov     rsi, rcx
0x18000199a  mov     [rsp+110h+lpBuffer], rcx
0x18000199f  lea     rcx, [rsp+110h+Buffer]; void *
0x1800019a4  mov     [rsp+110h+var_D8], r9
0x1800019a9  lea     r8d, [rdx+70h]; Size
0x1800019ad  mov     [rsp+110h+NumberOfBytesWritten], 0
0x1800019b5  mov     r15, r9
0x1800019b8  call    memset_0
0x1800019bd  xor     ecx, ecx
0x1800019bf  mov     [rsp+110h+Buffer], 70h ; 'p'
0x1800019c7  mov     [rbp+3Fh+var_BC], 20020101h
0x1800019ce  mov     [rbp+3Fh+var_A8], 28h ; '('
0x1800019d5  test    rdi, rdi
0x1800019d8  jz      loc_180001ACD
0x1800019de  mov     eax, [rdi]
0x1800019e0  movsd   xmm0, qword ptr [rdi+4]
0x1800019e5  mov     [rbp+3Fh+var_80], eax
0x1800019e8  mov     eax, [rdi+0Ch]
0x1800019eb  mov     [rbp+3Fh+var_74], eax
0x1800019ee  movsd   [rbp+3Fh+var_7C], xmm0
0x1800019f3  test    r13, r13
0x1800019f6  jz      short loc_1800019FE
0x1800019f8  mov     eax, [r15]
0x1800019fb  mov     [rbp+3Fh+var_B8], eax
0x1800019fe  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180001a02  test    rsi, rsi
0x180001a05  jz      loc_180001C65
0x180001a0b  mov     rax, rdi
0x180001a0e  inc     rax
0x180001a11  cmp     [rsi+rax*2], cx
0x180001a15  jnz     short loc_180001A0E
0x180001a17  lea     eax, ds:2[rax*2]
0x180001a1e  lea     rcx, [rbp+3Fh+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001a22  mov     [rbp+3Fh+nNumberOfBytesToWrite], eax
0x180001a25  call    cs:__imp_GetSystemTimeAsFileTime
0x180001a2b  xor     edx, edx
0x180001a2d  mov     [rbp+3Fh+var_70], 20h ; ' '
0x180001a34  test    r14, r14
0x180001a37  jnz     short loc_180001A7F
0x180001a39  xor     edi, edi
0x180001a3b  lea     r9, [rsp+110h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180001a40  lea     rdx, [rsp+110h+Buffer]; lpBuffer
0x180001a45  mov     [rsp+110h+lpOverlapped], rdi; lpOverlapped
0x180001a4a  mov     rcx, r12; hFile
0x180001a4d  lea     r8d, [rdi+70h]; nNumberOfBytesToWrite
0x180001a51  call    cs:__imp_WriteFile
0x180001a57  test    eax, eax
0x180001a59  jnz     short loc_180001AD9
0x180001a5b  mov     esi, edi
0x180001a5d  mov     eax, esi
0x180001a5f  mov     rcx, [rbp+3Fh+var_50]
0x180001a63  xor     rcx, rsp; StackCookie
0x180001a66  call    __security_check_cookie
0x180001a6b  add     rsp, 0D8h
0x180001a72  pop     r15
0x180001a74  pop     r14
0x180001a76  pop     r13
0x180001a78  pop     r12
0x180001a7a  pop     rdi
0x180001a7b  pop     rsi
0x180001a7c  pop     rbx
0x180001a7d  pop     rbp
0x180001a7e  retn
0x180001a7f  movzx   eax, word ptr [r14+4]
0x180001a84  mov     rcx, [r14+18h]
0x180001a88  mov     [rbp+3Fh+var_6C], ax
0x180001a8c  movzx   eax, word ptr [r14+6]
0x180001a91  mov     [rbp+3Fh+var_6A], ax
0x180001a95  mov     rax, [r14+8]
0x180001a99  mov     [rbp+3Fh+var_68], rax
0x180001a9d  mov     eax, [r14+10h]
0x180001aa1  mov     [rbp+3Fh+var_60], eax
0x180001aa4  mov     eax, [r14+20h]
0x180001aa8  mov     [rbp+3Fh+var_58], eax
0x180001aab  test    rcx, rcx
0x180001aae  jz      short loc_180001A39
0x180001ab0  cmp     dx, [rcx]
0x180001ab3  jz      short loc_180001A39
0x180001ab5  inc     rdi
0x180001ab8  cmp     [rcx+rdi*2], dx
0x180001abc  jnz     short loc_180001AB5
0x180001abe  lea     eax, ds:2[rdi*2]
0x180001ac5  mov     [rbp+3Fh+var_5C], eax
0x180001ac8  jmp     loc_180001A39
0x180001acd  mov     [rbp+3Fh+var_80], 10h
0x180001ad4  jmp     loc_1800019F3
0x180001ad9  mov     esi, 1
0x180001ade  test    r13, r13
0x180001ae1  jz      short loc_180001AF7
0x180001ae3  cmp     edi, [r15]
0x180001ae6  jb      loc_180001B73
0x180001aec  mov     rcx, r13; hFile
0x180001aef  call    cs:__imp_SetEndOfFile
0x180001af5  xor     edi, edi
0x180001af7  mov     r8d, [rbp+3Fh+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x180001afb  lea     r9, [rsp+110h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180001b00  mov     rdx, [rsp+110h+lpBuffer]; lpBuffer
0x180001b05  mov     rcx, r12; hFile
0x180001b08  mov     [rsp+110h+lpOverlapped], rdi; lpOverlapped
0x180001b0d  call    cs:__imp_WriteFile
0x180001b13  test    eax, eax
0x180001b15  jz      loc_180001A5B
0x180001b1b  mov     r8d, [rbp+3Fh+var_5C]; nNumberOfBytesToWrite
0x180001b1f  test    r8d, r8d
0x180001b22  jnz     loc_180001C3A
0x180001b28  mov     rcx, r12; hFile
0x180001b2b  call    cs:__imp_SetEndOfFile
0x180001b31  test    rbx, rbx
0x180001b34  jz      loc_180001A5D
0x180001b3a  cmp     dword ptr [rbx], 8
0x180001b3d  ja      loc_180001C21
0x180001b43  cmp     dword ptr [rbx], 18h
0x180001b46  ja      loc_180001BF3
0x180001b4c  cmp     dword ptr [rbx], 20h ; ' '
0x180001b4f  ja      loc_180001C0A
0x180001b55  cmp     dword ptr [rbx], 28h ; '('
0x180001b58  jbe     loc_180001A5D
0x180001b5e  mov     rax, [rbx+28h]
0x180001b62  test    rax, rax
0x180001b65  jz      loc_180001A5D
0x180001b6b  mov     [rax], rdi
0x180001b6e  jmp     loc_180001A5D
0x180001b73  mov     rax, [rsp+110h+var_D8]
0x180001b78  lea     r9, [rsp+110h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180001b7d  mov     r15d, edi
0x180001b80  lea     rdx, [rsp+110h+var_DC]; lpBuffer
0x180001b85  add     r15, r15
0x180001b88  mov     [rsp+110h+lpOverlapped], 0; lpOverlapped
0x180001b91  mov     r8d, 4; nNumberOfBytesToWrite
0x180001b97  mov     rax, [rax+8]
0x180001b9b  mov     ecx, [rax+r15*8]
0x180001b9f  mov     [rsp+110h+var_DC], ecx
0x180001ba3  mov     rcx, r12; hFile
0x180001ba6  call    cs:__imp_WriteFile
0x180001bac  test    eax, eax
0x180001bae  jz      loc_180001C5E
0x180001bb4  mov     r8d, [rsp+110h+var_DC]; nNumberOfBytesToWrite
0x180001bb9  test    r8d, r8d
0x180001bbc  jz      short loc_180001BE7
0x180001bbe  mov     rax, [rsp+110h+var_D8]
0x180001bc3  lea     r9, [rsp+110h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180001bc8  mov     rcx, r13; hFile
0x180001bcb  mov     [rsp+110h+lpOverlapped], 0; lpOverlapped
0x180001bd4  mov     rdx, [rax+8]
0x180001bd8  mov     rdx, [rdx+r15*8+8]; lpBuffer
0x180001bdd  call    cs:__imp_WriteFile
0x180001be3  test    eax, eax
0x180001be5  jz      short loc_180001C5E
0x180001be7  mov     r15, [rsp+110h+var_D8]
0x180001bec  add     edi, esi
0x180001bee  jmp     loc_180001AE3
0x180001bf3  mov     rcx, [rbx+18h]
0x180001bf7  test    rcx, rcx
0x180001bfa  jz      loc_180001B4C
0x180001c00  call    I_UrlCacheZeroCbSizeStruct
0x180001c05  jmp     loc_180001B4C
0x180001c0a  mov     rcx, [rbx+20h]
0x180001c0e  test    rcx, rcx
0x180001c11  jz      loc_180001B55
0x180001c17  call    I_UrlCacheZeroCbSizeStruct
0x180001c1c  jmp     loc_180001B55
0x180001c21  mov     rcx, [rbx+8]
0x180001c25  test    rcx, rcx
0x180001c28  jz      loc_180001B43
0x180001c2e  mov     rax, qword ptr [rbp+3Fh+SystemTimeAsFileTime.dwLowDateTime]
0x180001c32  mov     [rcx], rax
0x180001c35  jmp     loc_180001B43
0x180001c3a  mov     rdx, [r14+18h]; lpBuffer
0x180001c3e  lea     r9, [rsp+110h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180001c43  mov     rcx, r12; hFile
0x180001c46  mov     [rsp+110h+lpOverlapped], rdi; lpOverlapped
0x180001c4b  call    cs:__imp_WriteFile
0x180001c51  test    eax, eax
0x180001c53  jnz     loc_180001B28
0x180001c59  jmp     loc_180001A5B
0x180001c5e  xor     edi, edi
0x180001c60  jmp     loc_180001A5B
0x180001c65  mov     eax, ecx
0x180001c67  jmp     loc_180001A17
```
