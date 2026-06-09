# SecFileMonitorUpdateData

- ea: `0x14003cfb0`
- end: `0x14003d224`
- name: `SecFileMonitorUpdateData`
- size: `628`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x140022e20`

## callees

- `0x140009b80`
- `0x14001041f`
- `0x14001042b`
- `0x140011610`
- `0x140011650`
- `0x140011700`
- `0x140039968`
- `0x1400399d8`
- `0x14003cfb0`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003d06f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003d06f`

## pseudocode

```c
__int64 __fastcall SecFileMonitorUpdateData(void **a1, unsigned int a2, _QWORD *a3)
{
  _QWORD *v3; // rdi
  size_t v4; // rbx
  __int64 v7; // rax
  unsigned int v8; // ecx
  _QWORD *PoolWithTag; // rax
  int v10; // ebx
  int v11; // ebp
  __int64 v12; // rsi
  __int64 v13; // r14
  int v14; // eax
  void *v15; // rsi
  int v17; // [rsp+40h] [rbp-38h] BYREF

  v3 = 0;
  v4 = a2;
  v17 = 0;
  if ( !a3 || a2 < 0x18 )
    return (unsigned int)-1073741811;
  v7 = *(unsigned int *)a3;
  if ( !(_DWORD)v7 )
    goto LABEL_21;
  if ( (unsigned int)v7 > 0x1F4 )
    return (unsigned int)-1073741811;
  if ( (unsigned __int64)(48 * v7) > 0xFFFFFFFF )
    return (unsigned int)-1073741675;
  if ( a3[1] != 24 )
    return (unsigned int)-1073741811;
  v8 = 48 * v7 + 24;
  if ( v8 < 0x18 )
    return (unsigned int)-1073741675;
  if ( v8 >= a2 )
    return (unsigned int)-1073741811;
  _mm_lfence();
  if ( qword_140020008 )
    PoolWithTag = (_QWORD *)qword_140020008(256, a2, 1833329491);
  else
    PoolWithTag = ExAllocatePoolWithTag(PagedPool, a2, 0x6D466353u);
  v3 = PoolWithTag;
  if ( !PoolWithTag )
    return (unsigned int)-1073741670;
  memmove(PoolWithTag, a3, v4);
  v11 = v4 + (_DWORD)v3;
  if ( (_QWORD *)((char *)v3 + v4) < v3 )
  {
    v10 = -1073741675;
LABEL_25:
    SecFreePool(v3, 0x6D466353u);
    return (unsigned int)v10;
  }
  v12 = 0;
  v17 = v4 - 24;
  v3[1] = v3 + 3;
  if ( *(_DWORD *)v3 )
  {
    while ( 1 )
    {
      v13 = v3[1] + 48 * v12;
      v14 = *(unsigned __int16 *)(v13 + 16);
      if ( (_WORD)v14 != *(_WORD *)(v13 + 18) )
        break;
      v10 = ConvertStringOffsetToPointer((_DWORD)v3, v11, *(_QWORD *)(v13 + 24), v14, v17, (__int64)&v17, v13 + 24);
      if ( v10 < 0 )
        goto LABEL_25;
      _mm_lfence();
      v10 = ConvertOffsetToPointer((_DWORD)v3, v11, *(_QWORD *)v13, 48, v17, (__int64)&v17, v13);
      if ( v10 < 0 )
        goto LABEL_25;
      _mm_lfence();
      v10 = ConvertOffsetToPointer((_DWORD)v3, v11, *(_QWORD *)(v13 + 8), 48, v17, (__int64)&v17, v13 + 8);
      if ( v10 < 0 )
        goto LABEL_25;
      v12 = (unsigned int)(v12 + 1);
      if ( (unsigned int)v12 >= *(_DWORD *)v3 )
        goto LABEL_21;
    }
    v10 = -1073741811;
    goto LABEL_25;
  }
LABEL_21:
  FltAcquirePushLockExclusiveEx_0((char *)SecData + 1208, 0);
  v15 = *a1;
  *a1 = v3;
  v10 = 0;
  FltReleasePushLockEx_0((char *)SecData + 1208, 0);
  if ( v15 )
    SecFreePool(v15, 0x6D466353u);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14003cfb0  mov     [rsp+arg_18], rbx
0x14003cfb5  push    rbp
0x14003cfb6  push    rsi
0x14003cfb7  push    rdi
0x14003cfb8  push    r14
0x14003cfba  push    r15
0x14003cfbc  sub     rsp, 50h
0x14003cfc0  mov     rax, cs:__security_cookie
0x14003cfc7  xor     rax, rsp
0x14003cfca  mov     [rsp+78h+var_30], rax
0x14003cfcf  xor     edi, edi
0x14003cfd1  mov     ebx, edx
0x14003cfd3  mov     [rsp+78h+var_38], 0
0x14003cfdb  mov     r14, r8
0x14003cfde  mov     r15, rcx
0x14003cfe1  test    r8, r8
0x14003cfe4  jz      loc_14003D1FB
0x14003cfea  test    edx, edx
0x14003cfec  jz      loc_14003D1FB
0x14003cff2  cmp     ebx, 18h
0x14003cff5  jb      loc_14003D1FB
0x14003cffb  mov     eax, [r8]
0x14003cffe  test    eax, eax
0x14003d000  jz      loc_14003D18D
0x14003d006  cmp     eax, 1F4h
0x14003d00b  ja      loc_14003D1FB
0x14003d011  lea     rcx, [rax+rax*2]
0x14003d015  mov     eax, 0FFFFFFFFh
0x14003d01a  shl     rcx, 4
0x14003d01e  cmp     rcx, rax
0x14003d021  ja      loc_14003D1F4
0x14003d027  cmp     qword ptr [r8+8], 18h
0x14003d02c  jnz     loc_14003D1FB
0x14003d032  add     ecx, 18h
0x14003d035  cmp     ecx, 18h
0x14003d038  jb      loc_14003D1F4
0x14003d03e  cmp     ecx, ebx
0x14003d040  jnb     loc_14003D1FB
0x14003d046  lfence
0x14003d049  mov     rax, cs:qword_140020008
0x14003d050  mov     r8d, 6D466353h; Tag
0x14003d056  mov     edx, ebx; NumberOfBytes
0x14003d058  test    rax, rax
0x14003d05b  jz      short loc_14003D06A
0x14003d05d  mov     ecx, 100h
0x14003d062  call    cs:__guard_dispatch_icall_fptr
0x14003d068  jmp     short loc_14003D07B
0x14003d06a  mov     ecx, 1; PoolType
0x14003d06f  call    cs:__imp_ExAllocatePoolWithTag
0x14003d076  nop     dword ptr [rax+rax+00h]
0x14003d07b  mov     rdi, rax
0x14003d07e  test    rax, rax
0x14003d081  jnz     short loc_14003D08D
0x14003d083  mov     ebx, 0C000009Ah
0x14003d088  jmp     loc_14003D200
0x14003d08d  mov     r8, rbx; Size
0x14003d090  mov     rdx, r14; Src
0x14003d093  mov     rcx, rdi; void *
0x14003d096  call    memmove
0x14003d09b  lea     rbp, [rbx+rdi]
0x14003d09f  cmp     rbp, rdi
0x14003d0a2  jb      loc_14003D1DA
0x14003d0a8  lea     eax, [rbx-18h]
0x14003d0ab  xor     esi, esi
0x14003d0ad  mov     [rsp+78h+var_38], eax
0x14003d0b1  lea     rax, [rdi+18h]
0x14003d0b5  mov     [rdi+8], rax
0x14003d0b9  cmp     [rdi], esi
0x14003d0bb  jbe     loc_14003D18D
0x14003d0c1  lea     r14, [rsi+rsi*2]
0x14003d0c5  shl     r14, 4
0x14003d0c9  add     r14, [rdi+8]
0x14003d0cd  movzx   eax, word ptr [r14+10h]
0x14003d0d2  cmp     ax, [r14+12h]
0x14003d0d7  jnz     loc_14003D1D3
0x14003d0dd  mov     r9d, eax
0x14003d0e0  lea     r8, [r14+18h]
0x14003d0e4  mov     [rsp+78h+var_48], r8
0x14003d0e9  lea     rax, [rsp+78h+var_38]
0x14003d0ee  mov     r8, [r8]
0x14003d0f1  mov     rdx, rbp
0x14003d0f4  mov     [rsp+78h+var_50], rax
0x14003d0f9  mov     rcx, rdi
0x14003d0fc  mov     eax, [rsp+78h+var_38]
0x14003d100  mov     [rsp+78h+var_58], eax
0x14003d104  call    ConvertStringOffsetToPointer
0x14003d109  mov     ebx, eax
0x14003d10b  test    eax, eax
0x14003d10d  js      loc_14003D1DF
0x14003d113  lfence
0x14003d116  mov     r8, [r14]
0x14003d119  lea     rax, [rsp+78h+var_38]
0x14003d11e  mov     [rsp+78h+var_48], r14
0x14003d123  mov     r9d, 30h ; '0'
0x14003d129  mov     [rsp+78h+var_50], rax
0x14003d12e  mov     rdx, rbp
0x14003d131  mov     eax, [rsp+78h+var_38]
0x14003d135  mov     rcx, rdi
0x14003d138  mov     [rsp+78h+var_58], eax
0x14003d13c  call    ConvertOffsetToPointer
0x14003d141  mov     ebx, eax
0x14003d143  test    eax, eax
0x14003d145  js      loc_14003D1DF
0x14003d14b  lfence
0x14003d14e  lea     rax, [rsp+78h+var_38]
0x14003d153  mov     r9d, 30h ; '0'
0x14003d159  lea     r8, [r14+8]
0x14003d15d  mov     rdx, rbp
0x14003d160  mov     [rsp+78h+var_48], r8
0x14003d165  mov     rcx, rdi
0x14003d168  mov     r8, [r8]
0x14003d16b  mov     [rsp+78h+var_50], rax
0x14003d170  mov     eax, [rsp+78h+var_38]
0x14003d174  mov     [rsp+78h+var_58], eax
0x14003d178  call    ConvertOffsetToPointer
0x14003d17d  mov     ebx, eax
0x14003d17f  test    eax, eax
0x14003d181  js      short loc_14003D1DF
0x14003d183  inc     esi
0x14003d185  cmp     esi, [rdi]
0x14003d187  jb      loc_14003D0C1
0x14003d18d  mov     rcx, cs:SecData
0x14003d194  xor     edx, edx
0x14003d196  add     rcx, 4B8h
0x14003d19d  call    FltAcquirePushLockExclusiveEx_0
0x14003d1a2  mov     rsi, [r15]
0x14003d1a5  xor     edx, edx
0x14003d1a7  mov     [r15], rdi
0x14003d1aa  xor     ebx, ebx
0x14003d1ac  mov     rcx, cs:SecData
0x14003d1b3  add     rcx, 4B8h
0x14003d1ba  call    FltReleasePushLockEx_0
0x14003d1bf  test    rsi, rsi
0x14003d1c2  jz      short loc_14003D200
0x14003d1c4  mov     edx, 6D466353h; Tag
0x14003d1c9  mov     rcx, rsi; P
0x14003d1cc  call    SecFreePool
0x14003d1d1  jmp     short loc_14003D200
0x14003d1d3  mov     ebx, 0C000000Dh
0x14003d1d8  jmp     short loc_14003D1DF
0x14003d1da  mov     ebx, 0C0000095h
0x14003d1df  mov     edx, 6D466353h; Tag
0x14003d1e4  mov     rcx, rdi; P
0x14003d1e7  call    SecFreePool
0x14003d1ec  xor     edi, edi
0x14003d1ee  test    ebx, ebx
0x14003d1f0  jns     short loc_14003D18D
0x14003d1f2  jmp     short loc_14003D200
0x14003d1f4  mov     ebx, 0C0000095h
0x14003d1f9  jmp     short loc_14003D200
0x14003d1fb  mov     ebx, 0C000000Dh
0x14003d200  mov     eax, ebx
0x14003d202  mov     rcx, [rsp+78h+var_30]
0x14003d207  xor     rcx, rsp; StackCookie
0x14003d20a  call    __security_check_cookie
0x14003d20f  mov     rbx, [rsp+78h+arg_18]
0x14003d217  add     rsp, 50h
0x14003d21b  pop     r15
0x14003d21d  pop     r14
0x14003d21f  pop     rdi
0x14003d220  pop     rsi
0x14003d221  pop     rbp
0x14003d222  retn
```
