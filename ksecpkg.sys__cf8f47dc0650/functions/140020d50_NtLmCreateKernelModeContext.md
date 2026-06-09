# NtLmCreateKernelModeContext

- ea: `0x140020d50`
- end: `0x140021019`
- name: `NtLmCreateKernelModeContext`
- size: `713`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, char **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140021110`

## callees

- `0x140004b30`
- `0x140010240`
- `0x1400102c0`
- `0x1400105c0`
- `0x140020d50`
- `0x14002ff40`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140020da9`
- `ntoskrnl!ExAllocatePool2` at `0x140020f73`
- `ntoskrnl!ExAllocatePool2` at `0x140020da9`
- `ntoskrnl!ExAllocatePool2` at `0x140020f73`
- `cng!BCryptImportKey` at `0x140020e76`
- `cng!BCryptImportKey` at `0x140020ee9`
- `cng!BCryptImportKey` at `0x140020e76`
- `cng!BCryptImportKey` at `0x140020ee9`

## pseudocode

```c
__int64 __fastcall NtLmCreateKernelModeContext(__int64 a1, __int64 a2, __int64 a3, char **a4)
{
  enum _POOL_TYPE v6; // r13d
  __int64 v7; // rdi
  __int64 v8; // r15
  char *Pool2; // rax
  char *v10; // rbx
  NTSTATUS v11; // esi
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  int v14; // eax
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  void *MsRc4AlgorithmProvider; // rbp
  __int64 v19; // rax
  __int64 v20; // rax
  _DWORD *v21; // rdx
  _DWORD *v22; // rcx
  char *v23; // rax
  void *v24; // rax
  void *v25; // rcx

  if ( *(_DWORD *)a3 < 0xA8u )
    return 3221225485LL;
  v6 = NtlmPoolType;
  v7 = *(_QWORD *)(a3 + 8);
  v8 = 256;
  if ( NtlmPoolType != PagedPool )
    v8 = 64;
  Pool2 = (char *)ExAllocatePool2((unsigned int)v8, 280, 1131836237);
  v10 = Pool2;
  if ( Pool2 )
  {
    memset(Pool2, 0, 0x118u);
    v12 = *(_OWORD *)(v7 + 20);
    v13 = *(_OWORD *)(v7 + 76);
    *((_DWORD *)v10 + 12) = *(_DWORD *)(v7 + 4);
    v14 = *(_DWORD *)(v7 + 36);
    *(_OWORD *)(v10 + 148) = v12;
    *((_DWORD *)v10 + 41) = v14;
    v15 = *(_OWORD *)(v7 + 92);
    *(_OWORD *)(v10 + 196) = v13;
    v16 = *(_OWORD *)(v7 + 108);
    *(_OWORD *)(v10 + 212) = v15;
    v17 = *(_OWORD *)(v7 + 124);
    *(_OWORD *)(v10 + 228) = v16;
    *(_OWORD *)(v10 + 244) = v17;
    if ( *(_DWORD *)(v7 + 148) || *(_DWORD *)(v7 + 156) )
    {
      MsRc4AlgorithmProvider = GetMsRc4AlgorithmProvider();
      if ( !MsRc4AlgorithmProvider )
      {
        v11 = -1073741816;
        goto LABEL_28;
      }
    }
    else
    {
      MsRc4AlgorithmProvider = 0;
    }
    v19 = *(unsigned int *)(v7 + 148);
    if ( !(_DWORD)v19 )
    {
      v11 = 0;
LABEL_16:
      v20 = *(unsigned int *)(v7 + 156);
      if ( (_DWORD)v20 )
      {
        v11 = BCryptImportKey(
                MsRc4AlgorithmProvider,
                0,
                L"OpaqueKeyBlob",
                (BCRYPT_KEY_HANDLE *)v10 + 13,
                0,
                0,
                (PUCHAR)(v7 + v20),
                *(_DWORD *)(v7 + 160),
                0);
        if ( v11 < 0 )
          goto LABEL_28;
      }
      v21 = v10 + 120;
      *((_QWORD *)v10 + 1) = 0;
      *(_QWORD *)v10 = 0;
      *((_DWORD *)v10 + 4) = 1;
      *((_DWORD *)v10 + 5) = 1296847950;
      *((_QWORD *)v10 + 3) = 0;
      *((_QWORD *)v10 + 4) = 0;
      *((_QWORD *)v10 + 7) = a2;
      if ( *((_DWORD *)v10 + 30) == -1 )
        *v21 = 0;
      v22 = v10 + 124;
      if ( *((_DWORD *)v10 + 31) == -1 )
        *v22 = 0;
      if ( (*((_DWORD *)v10 + 12) & 0x80000) != 0 )
      {
        v23 = v10 + 112;
      }
      else
      {
        v22 = v10 + 120;
        v23 = v10 + 104;
      }
      *((_QWORD *)v10 + 11) = v10 + 104;
      *((_QWORD *)v10 + 12) = v23;
      *((_QWORD *)v10 + 9) = v21;
      *((_QWORD *)v10 + 10) = v22;
      if ( *(_DWORD *)(v7 + 60) )
      {
        v24 = (void *)ExAllocatePool2(v8, *(unsigned int *)(v7 + 64), 1131836237);
        *((_QWORD *)v10 + 16) = v24;
        if ( !v24 )
        {
          v11 = -1073741670;
          goto LABEL_28;
        }
        memmove(v24, (const void *)(v7 + *(unsigned int *)(v7 + 60)), *(unsigned int *)(v7 + 64));
      }
      else
      {
        *((_QWORD *)v10 + 16) = 0;
      }
      v25 = NtlmNonPagedList;
      if ( v6 == PagedPool )
        v25 = NtlmPagedList;
      *((_QWORD *)v10 + 22) = *(_QWORD *)(v7 + 40);
      *((_QWORD *)v10 + 23) = *(_QWORD *)(v7 + 48);
      *((_DWORD *)v10 + 48) = *(_DWORD *)(v7 + 56);
      (*((void (__fastcall **)(void *, char *))LsaKernelFunctions + 3))(v25, v10);
      *a4 = v10;
      return (unsigned int)v11;
    }
    v11 = BCryptImportKey(
            MsRc4AlgorithmProvider,
            0,
            L"OpaqueKeyBlob",
            (BCRYPT_KEY_HANDLE *)v10 + 13,
            0,
            0,
            (PUCHAR)(v7 + v19),
            *(_DWORD *)(v7 + 152),
            0);
    if ( v11 >= 0 )
      goto LABEL_16;
LABEL_28:
    NtlmFreeKernelContext(v10);
    return (unsigned int)v11;
  }
  return (unsigned int)-1073741670;
}

```

## disassembly

```asm
0x140020d50  mov     [rsp+arg_18], r9
0x140020d55  push    rbx
0x140020d56  push    rbp
0x140020d57  push    rsi
0x140020d58  push    rdi
0x140020d59  push    r12
0x140020d5b  push    r13
0x140020d5d  push    r14
0x140020d5f  push    r15
0x140020d61  sub     rsp, 58h
0x140020d65  cmp     dword ptr [r8], 0A8h
0x140020d6c  mov     r12, rdx
0x140020d6f  jnb     short loc_140020D7B
0x140020d71  mov     eax, 0C000000Dh
0x140020d76  jmp     loc_140021007
0x140020d7b  mov     r13d, cs:?NtlmPoolType@@3W4_POOL_TYPE@@A; _POOL_TYPE NtlmPoolType
0x140020d82  mov     eax, 40h ; '@'
0x140020d87  mov     rdi, [r8+8]
0x140020d8b  cmp     r13d, 1
0x140020d8f  mov     r15d, 100h
0x140020d95  mov     esi, 118h
0x140020d9a  cmovnz  r15d, eax
0x140020d9e  mov     r8d, 4376734Dh
0x140020da4  mov     ecx, r15d
0x140020da7  mov     edx, esi
0x140020da9  call    cs:__imp_ExAllocatePool2
0x140020db0  nop     dword ptr [rax+rax+00h]
0x140020db5  mov     rbx, rax
0x140020db8  test    rax, rax
0x140020dbb  jnz     short loc_140020DC7
0x140020dbd  mov     esi, 0C000009Ah
0x140020dc2  jmp     loc_140021005
0x140020dc7  mov     r8, rsi; Size
0x140020dca  xor     edx, edx; Val
0x140020dcc  mov     rcx, rbx; void *
0x140020dcf  call    memset
0x140020dd4  movups  xmm0, xmmword ptr [rdi+14h]
0x140020dd8  mov     eax, [rdi+4]
0x140020ddb  xor     r8d, r8d
0x140020dde  movups  xmm1, xmmword ptr [rdi+4Ch]
0x140020de2  mov     [rbx+30h], eax
0x140020de5  mov     eax, [rdi+24h]
0x140020de8  movdqu  xmmword ptr [rbx+94h], xmm0
0x140020df0  mov     [rbx+0A4h], eax
0x140020df6  movups  xmm0, xmmword ptr [rdi+5Ch]
0x140020dfa  movdqu  xmmword ptr [rbx+0C4h], xmm1
0x140020e02  movups  xmm1, xmmword ptr [rdi+6Ch]
0x140020e06  movdqu  xmmword ptr [rbx+0D4h], xmm0
0x140020e0e  movups  xmm0, xmmword ptr [rdi+7Ch]
0x140020e12  movdqu  xmmword ptr [rbx+0E4h], xmm1
0x140020e1a  movdqu  xmmword ptr [rbx+0F4h], xmm0
0x140020e22  cmp     [rdi+94h], r8d
0x140020e29  ja      short loc_140020E91
0x140020e2b  cmp     [rdi+9Ch], r8d
0x140020e32  ja      short loc_140020E91
0x140020e34  mov     ebp, r8d
0x140020e37  mov     eax, [rdi+94h]
0x140020e3d  lea     r14, [rbx+68h]
0x140020e41  test    eax, eax
0x140020e43  jz      short loc_140020EAB
0x140020e45  mov     [rsp+98h+dwFlags], r8d; dwFlags
0x140020e4a  lea     rcx, [rdi+rax]
0x140020e4e  mov     eax, [rdi+98h]
0x140020e54  mov     r9, r14; phKey
0x140020e57  mov     [rsp+98h+cbInput], eax; cbInput
0x140020e5b  xor     edx, edx; hImportKey
0x140020e5d  mov     [rsp+98h+pbInput], rcx; pbInput
0x140020e62  mov     rcx, rbp; hAlgorithm
0x140020e65  mov     [rsp+98h+cbKeyObject], r8d; cbKeyObject
0x140020e6a  mov     [rsp+98h+pbKeyObject], r8; pbKeyObject
0x140020e6f  lea     r8, pszBlobType; "OpaqueKeyBlob"
0x140020e76  call    cs:__imp_BCryptImportKey
0x140020e7d  nop     dword ptr [rax+rax+00h]
0x140020e82  xor     r8d, r8d
0x140020e85  mov     esi, eax
0x140020e87  test    eax, eax
0x140020e89  js      loc_140020F90
0x140020e8f  jmp     short loc_140020EAE
0x140020e91  call    ?GetMsRc4AlgorithmProvider@@YAPEAXXZ; GetMsRc4AlgorithmProvider(void)
0x140020e96  xor     r8d, r8d
0x140020e99  mov     rbp, rax
0x140020e9c  test    rax, rax
0x140020e9f  jnz     short loc_140020E37
0x140020ea1  mov     esi, 0C0000008h
0x140020ea6  jmp     loc_140020F90
0x140020eab  mov     esi, r8d
0x140020eae  mov     eax, [rdi+9Ch]
0x140020eb4  test    eax, eax
0x140020eb6  jz      short loc_140020F02
0x140020eb8  mov     [rsp+98h+dwFlags], r8d; dwFlags
0x140020ebd  lea     rcx, [rdi+rax]
0x140020ec1  mov     eax, [rdi+0A0h]
0x140020ec7  mov     r9, r14; phKey
0x140020eca  mov     [rsp+98h+cbInput], eax; cbInput
0x140020ece  xor     edx, edx; hImportKey
0x140020ed0  mov     [rsp+98h+pbInput], rcx; pbInput
0x140020ed5  mov     rcx, rbp; hAlgorithm
0x140020ed8  mov     [rsp+98h+cbKeyObject], r8d; cbKeyObject
0x140020edd  mov     [rsp+98h+pbKeyObject], r8; pbKeyObject
0x140020ee2  lea     r8, pszBlobType; "OpaqueKeyBlob"
0x140020ee9  call    cs:__imp_BCryptImportKey
0x140020ef0  nop     dword ptr [rax+rax+00h]
0x140020ef5  xor     r8d, r8d
0x140020ef8  mov     esi, eax
0x140020efa  test    eax, eax
0x140020efc  js      loc_140020F90
0x140020f02  lea     rdx, [rbx+78h]
0x140020f06  mov     [rbx+8], r8
0x140020f0a  or      eax, 0FFFFFFFFh
0x140020f0d  mov     [rbx], r8
0x140020f10  mov     dword ptr [rbx+10h], 1
0x140020f17  mov     dword ptr [rbx+14h], 4D4C544Eh
0x140020f1e  mov     [rbx+18h], r8
0x140020f22  mov     [rbx+20h], r8
0x140020f26  mov     [rbx+38h], r12
0x140020f2a  cmp     [rdx], eax
0x140020f2c  jnz     short loc_140020F31
0x140020f2e  mov     [rdx], r8d
0x140020f31  lea     rcx, [rbx+7Ch]
0x140020f35  cmp     [rcx], eax
0x140020f37  jnz     short loc_140020F3C
0x140020f39  mov     [rcx], r8d
0x140020f3c  test    dword ptr [rbx+30h], 80000h
0x140020f43  jz      short loc_140020F4B
0x140020f45  lea     rax, [rbx+70h]
0x140020f49  jmp     short loc_140020F51
0x140020f4b  mov     rcx, rdx
0x140020f4e  mov     rax, r14
0x140020f51  mov     [rbx+58h], r14
0x140020f55  mov     [rbx+60h], rax
0x140020f59  mov     [rbx+48h], rdx
0x140020f5d  mov     [rbx+50h], rcx
0x140020f61  cmp     [rdi+3Ch], r8d
0x140020f65  jz      short loc_140020FAE
0x140020f67  mov     edx, [rdi+40h]
0x140020f6a  mov     r8d, 4376734Dh
0x140020f70  mov     rcx, r15
0x140020f73  call    cs:__imp_ExAllocatePool2
0x140020f7a  nop     dword ptr [rax+rax+00h]
0x140020f7f  mov     [rbx+80h], rax
0x140020f86  test    rax, rax
0x140020f89  jnz     short loc_140020F9A
0x140020f8b  mov     esi, 0C000009Ah
0x140020f90  mov     rcx, rbx; P
0x140020f93  call    NtlmFreeKernelContext
0x140020f98  jmp     short loc_140021005
0x140020f9a  mov     edx, [rdi+3Ch]
0x140020f9d  mov     rcx, rax; void *
0x140020fa0  mov     r8d, [rdi+40h]; Size
0x140020fa4  add     rdx, rdi; Src
0x140020fa7  call    memmove
0x140020fac  jmp     short loc_140020FB5
0x140020fae  mov     [rbx+80h], r8
0x140020fb5  mov     rax, [rdi+28h]
0x140020fb9  cmp     r13d, 1
0x140020fbd  mov     rcx, cs:?NtlmNonPagedList@@3PEAXEA; void * NtlmNonPagedList
0x140020fc4  mov     rdx, rbx
0x140020fc7  cmovz   rcx, cs:?NtlmPagedList@@3PEAXEA; void * NtlmPagedList
0x140020fcf  mov     [rbx+0B0h], rax
0x140020fd6  mov     rax, [rdi+30h]
0x140020fda  mov     [rbx+0B8h], rax
0x140020fe1  mov     eax, [rdi+38h]
0x140020fe4  mov     [rbx+0C0h], eax
0x140020fea  mov     rax, cs:?LsaKernelFunctions@@3PEAU_SECPKG_KERNEL_FUNCTIONS@@EA; _SECPKG_KERNEL_FUNCTIONS * LsaKernelFunctions
0x140020ff1  mov     rax, [rax+18h]
0x140020ff5  call    _guard_dispatch_icall
0x140020ffa  mov     rax, [rsp+98h+arg_18]
0x140021002  mov     [rax], rbx
0x140021005  mov     eax, esi
0x140021007  add     rsp, 58h
0x14002100b  pop     r15
0x14002100d  pop     r14
0x14002100f  pop     r13
0x140021011  pop     r12
0x140021013  pop     rdi
0x140021014  pop     rsi
0x140021015  pop     rbp
0x140021016  pop     rbx
0x140021017  retn
```
