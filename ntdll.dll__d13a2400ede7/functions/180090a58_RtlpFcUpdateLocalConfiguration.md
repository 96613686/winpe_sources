# RtlpFcUpdateLocalConfiguration

- ea: `0x180090a58`
- end: `0x180090c88`
- name: `RtlpFcUpdateLocalConfiguration`
- size: `560`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800903e0`
- `0x180090500`

## callees

- `0x180017e90`
- `0x1800183a0`
- `0x180090a58`
- `0x180090c90`
- `0x180090d5c`
- `0x180090e00`
- `0x180090e90`
- `0x180091350`
- `0x18015ecc0`
- `0x18015f020`
- `0x180161890`
- `0x180162810`
- `0x18016e774`
- `0x18016f030`

## pseudocode

```c
__int64 __fastcall RtlpFcUpdateLocalConfiguration(__int64 a1, unsigned __int64 a2, char a3)
{
  __int64 *v6; // rdi
  unsigned __int64 v7; // rdx
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rsi
  int v11; // eax
  __int64 j; // rdi
  __int64 k; // rdi
  HANDLE v14; // rcx
  __int64 v16; // rtt
  __int64 *v17; // rdx
  unsigned int i; // r8d
  unsigned int v19; // eax
  __int64 v20; // r8
  _DWORD v21[4]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v22; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v23; // [rsp+50h] [rbp-B0h]
  HANDLE v24[14]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v25[96]; // [rsp+D0h] [rbp-30h] BYREF

  v22 = 0;
  v23 = 0;
  memset_thunk_772440563353939046(v24, 0, 0x68u);
  memset_thunk_772440563353939046(v25, 0, 0x60u);
  if ( byte_1801CA908 )
  {
    v8 = -1073741058;
    goto LABEL_17;
  }
  if ( a3 )
  {
    RtlAcquireSRWLockExclusive(a1);
  }
  else if ( !(unsigned __int8)RtlTryAcquireSRWLockExclusive(a1) )
  {
    v8 = -1073741608;
    goto LABEL_17;
  }
  v6 = (__int64 *)(a1 + 8);
  if ( *(_QWORD *)(a1 + 8 + 8 * (*(_QWORD *)(a1 + 8) & 1LL) + 216) >= a2 )
  {
    v8 = 0;
  }
  else
  {
    v21[0] = 0;
    while ( 1 )
    {
      _m_prefetchw(v6);
      v7 = *v6 & 1 | ((*v6 & 0xFFFFFFFFFFFFFFFEuLL) + 2);
      if ( v7 < 2 )
        __fastfail(0xEu);
      v16 = *v6;
      if ( v16 == _InterlockedCompareExchange64(v6, v7, *v6) )
        break;
      RtlBackoff(v21);
    }
    v22 = 0;
    v23 = 0;
    v17 = &v6[12 * (v7 & 1) + 3];
    for ( i = 0; i < 4; i = v20 + 1 )
    {
      v19 = RtlpFcSectionTypeToBufferType(i, v17);
      *((_QWORD *)&v22 + v20) = v17[3 * v19];
    }
    RtlpFcBufferManagerDereferenceBuffers(a1 + 8);
    v8 = NtQuerySystemInformationEx(211, &v22, 32, v24, 104, 0);
    if ( v8 >= 0 )
    {
      v10 = 0;
      while ( 1 )
      {
        v11 = RtlpFcSectionTypeToBufferType((unsigned int)v10, v9);
        v8 = RtlpFcMapSingleBuffer(&v24[3 * v10 + 1], &v25[24 * v11]);
        if ( v8 < 0 )
          break;
        v10 = (unsigned int)(v10 + 1);
        if ( (unsigned int)v10 >= 4 )
        {
          RtlpFcBufferManagerUpdateBuffers(a1 + 8, v24[0], v25);
          break;
        }
      }
    }
  }
  RtlReleaseSRWLockExclusive(a1);
LABEL_17:
  for ( j = 0; j != 4; ++j )
  {
    if ( *(_QWORD *)&v25[24 * j + 8] )
      NtUnmapViewOfSection(-1);
  }
  for ( k = 0; k != 4; ++k )
  {
    v14 = v24[3 * k + 2];
    if ( v14 )
      NtClose(v14);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180090a58  push    rbp
0x180090a5a  push    rbx
0x180090a5b  push    rsi
0x180090a5c  push    rdi
0x180090a5d  push    r14
0x180090a5f  push    r15
0x180090a61  lea     rbp, [rsp-48h]
0x180090a66  sub     rsp, 148h
0x180090a6d  mov     rax, cs:__security_cookie
0x180090a74  xor     rax, rsp
0x180090a77  mov     [rbp+70h+var_40], rax
0x180090a7b  xorps   xmm0, xmm0
0x180090a7e  mov     rsi, rdx
0x180090a81  xor     edx, edx; Val
0x180090a83  mov     bl, r8b
0x180090a86  mov     r14, rcx
0x180090a89  lea     rcx, [rsp+170h+var_110]; void *
0x180090a8e  movups  [rsp+170h+var_130], xmm0
0x180090a93  lea     r8d, [rdx+68h]; Size
0x180090a97  movups  [rsp+170h+var_120], xmm0
0x180090a9c  call    memset$thunk$772440563353939046
0x180090aa1  xor     edx, edx; Val
0x180090aa3  lea     rcx, [rbp+70h+var_A0]; void *
0x180090aa7  lea     r8d, [rdx+60h]; Size
0x180090aab  call    memset$thunk$772440563353939046
0x180090ab0  cmp     cs:byte_1801CA908, 0
0x180090ab7  jnz     short loc_180090B29
0x180090ab9  mov     rcx, r14
0x180090abc  test    bl, bl
0x180090abe  jz      short loc_180090B13
0x180090ac0  call    RtlAcquireSRWLockExclusive
0x180090ac5  mov     r15b, 1
0x180090ac8  lea     rdi, [r14+8]
0x180090acc  mov     rax, [rdi]
0x180090acf  and     eax, 1
0x180090ad2  cmp     [rdi+rax*8+0D8h], rsi
0x180090ada  jnb     loc_180090C25
0x180090ae0  mov     [rsp+170h+var_140], 0
0x180090ae8  prefetchw byte ptr [rdi]
0x180090aeb  mov     rax, [rdi]
0x180090aee  mov     rcx, rax
0x180090af1  mov     rdx, rax
0x180090af4  and     rdx, 0FFFFFFFFFFFFFFFEh
0x180090af8  and     ecx, 1
0x180090afb  add     rdx, 2
0x180090aff  or      rdx, rcx
0x180090b02  cmp     rdx, 2
0x180090b06  jnb     loc_180090C29
0x180090b0c  mov     ecx, 0Eh
0x180090b11  int     29h; Win8: RtlFailFast(ecx)
0x180090b13  call    RtlTryAcquireSRWLockExclusive
0x180090b18  mov     r15b, al
0x180090b1b  test    al, al
0x180090b1d  jnz     short loc_180090AC8
0x180090b1f  mov     ebx, 0C00000D8h
0x180090b24  jmp     loc_180090BC4
0x180090b29  mov     ebx, 0C00002FEh
0x180090b2e  jmp     loc_180090BC4
0x180090b33  mov     rcx, rdi
0x180090b36  call    RtlpFcBufferManagerDereferenceBuffers
0x180090b3b  lea     r9, [rsp+170h+var_110]
0x180090b40  mov     [rsp+170h+var_148], 0
0x180090b49  mov     r8d, 20h ; ' '
0x180090b4f  mov     [rsp+170h+var_150], 68h ; 'h'
0x180090b57  lea     rdx, [rsp+170h+var_130]
0x180090b5c  mov     ecx, 0D3h
0x180090b61  call    NtQuerySystemInformationEx
0x180090b66  mov     ebx, eax
0x180090b68  test    eax, eax
0x180090b6a  js      short loc_180090BB7
0x180090b6c  xor     esi, esi
0x180090b6e  mov     ecx, esi
0x180090b70  call    RtlpFcSectionTypeToBufferType
0x180090b75  mov     ecx, eax
0x180090b77  lea     rdx, [rbp+70h+var_A0]
0x180090b7b  lea     rax, [rcx+rcx*2]
0x180090b7f  lea     rdx, [rdx+rax*8]
0x180090b83  lea     rax, [rsp+170h+var_108]
0x180090b88  lea     rcx, [rsi+rsi*2]
0x180090b8c  lea     rcx, [rax+rcx*8]
0x180090b90  call    RtlpFcMapSingleBuffer
0x180090b95  mov     ebx, eax
0x180090b97  test    eax, eax
0x180090b99  js      short loc_180090BB7
0x180090b9b  inc     esi
0x180090b9d  cmp     esi, 4
0x180090ba0  jb      short loc_180090B6E
0x180090ba2  test    eax, eax
0x180090ba4  js      short loc_180090BB7
0x180090ba6  mov     rdx, [rsp+170h+var_110]
0x180090bab  lea     r8, [rbp+70h+var_A0]
0x180090baf  mov     rcx, rdi
0x180090bb2  call    RtlpFcBufferManagerUpdateBuffers
0x180090bb7  test    r15b, r15b
0x180090bba  jz      short loc_180090BC4
0x180090bbc  mov     rcx, r14
0x180090bbf  call    RtlReleaseSRWLockExclusive
0x180090bc4  xor     edi, edi
0x180090bc6  lea     rax, [rdi+rdi*2]
0x180090bca  mov     rdx, [rbp+rax*8+70h+var_98]
0x180090bcf  test    rdx, rdx
0x180090bd2  jnz     short loc_180090C1A
0x180090bd4  inc     rdi
0x180090bd7  cmp     rdi, 4
0x180090bdb  jnz     short loc_180090BC6
0x180090bdd  xor     edi, edi
0x180090bdf  lea     rax, [rdi+rdi*2]
0x180090be3  mov     rcx, [rsp+rax*8+170h+Handle]; Handle
0x180090be8  test    rcx, rcx
0x180090beb  jz      short loc_180090BF2
0x180090bed  call    NtClose
0x180090bf2  inc     rdi
0x180090bf5  cmp     rdi, 4
0x180090bf9  jnz     short loc_180090BDF
0x180090bfb  mov     eax, ebx
0x180090bfd  mov     rcx, [rbp+70h+var_40]
0x180090c01  xor     rcx, rsp; StackCookie
0x180090c04  call    __security_check_cookie
0x180090c09  add     rsp, 148h
0x180090c10  pop     r15
0x180090c12  pop     r14
0x180090c14  pop     rdi
0x180090c15  pop     rsi
0x180090c16  pop     rbx
0x180090c17  pop     rbp
0x180090c18  retn
0x180090c1a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180090c1e  call    NtUnmapViewOfSection
0x180090c23  jmp     short loc_180090BD4
0x180090c25  xor     ebx, ebx
0x180090c27  jmp     short loc_180090BB7
0x180090c29  mov     ecx, edx
0x180090c2b  lock cmpxchg [rdi], rdx
0x180090c30  jnz     short loc_180090C79
0x180090c32  and     ecx, 1
0x180090c35  xorps   xmm0, xmm0
0x180090c38  movups  [rsp+170h+var_130], xmm0
0x180090c3d  movups  [rsp+170h+var_120], xmm0
0x180090c42  lea     rdx, [rcx+rcx*2]
0x180090c46  shl     rdx, 5
0x180090c4a  add     rdx, 18h
0x180090c4e  add     rdx, rdi
0x180090c51  xor     r8d, r8d
0x180090c54  mov     ecx, r8d
0x180090c57  call    RtlpFcSectionTypeToBufferType
0x180090c5c  mov     ecx, eax
0x180090c5e  lea     rax, [rcx+rcx*2]
0x180090c62  mov     rax, [rdx+rax*8]
0x180090c66  mov     qword ptr [rsp+r8*8+170h+var_130], rax
0x180090c6b  inc     r8d
0x180090c6e  cmp     r8d, 4
0x180090c72  jb      short loc_180090C54
0x180090c74  jmp     loc_180090B33
0x180090c79  lea     rcx, [rsp+170h+var_140]
0x180090c7e  call    RtlBackoff
0x180090c83  jmp     loc_180090AE8
```
