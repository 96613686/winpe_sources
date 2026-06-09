# RasEapGetConfigBlobAndUserBlob

- ea: `0x180016ee0`
- end: `0x180017046`
- name: `RasEapGetConfigBlobAndUserBlob`
- size: `358`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callees

- `0x180001210`
- `0x180002954`
- `0x1800038d0`
- `0x180016ee0`
- `0x180023c30`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001701b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017024`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001702d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001701b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017024`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001702d`

## pseudocode

```c
__int64 __fastcall RasEapGetConfigBlobAndUserBlob(
        char a1,
        int a2,
        __int64 a3,
        _DWORD *a4,
        _QWORD *a5,
        _DWORD *a6,
        _QWORD *a7)
{
  _QWORD *v7; // rax
  void *v11; // rbx
  void *v12; // rsi
  void *v13; // r14
  unsigned int v14; // edi
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r9
  unsigned int updated; // eax
  _QWORD *v20; // rax
  int v21; // eax
  void *v23; // [rsp+30h] [rbp-18h] BYREF
  void *v24; // [rsp+38h] [rbp-10h] BYREF
  _DWORD *v25; // [rsp+A8h] [rbp+60h] BYREF

  v7 = a5;
  *a4 = 0;
  v25 = 0;
  v11 = 0;
  *v7 = 0;
  v12 = 0;
  v13 = 0;
  v23 = 0;
  v24 = 0;
  *a6 = 0;
  *a7 = 0;
  if ( a2 != 26 )
  {
    v14 = 87;
    goto LABEL_18;
  }
  v14 = ReadConnectionData(a1, 0, 0, &v25);
  if ( v14 )
  {
LABEL_17:
    v11 = v25;
    goto LABEL_18;
  }
  v14 = ReadUserData(0, 0, &v23);
  if ( v14 )
  {
    v12 = v23;
    goto LABEL_17;
  }
  v11 = v25;
  if ( (a1 & 0x20) != 0 )
  {
LABEL_14:
    v13 = v23;
    v25[1] = 2;
LABEL_15:
    v20 = a5;
    *a4 = 8;
    *v20 = v11;
    v21 = MschapV2UserPropBuffSize(v13);
    *a6 = v21;
    *a7 = v13;
    v11 = 0;
    v13 = 0;
    goto LABEL_18;
  }
  if ( *(_DWORD *)a3 != 1 )
  {
    if ( *(_DWORD *)a3 != 2 )
    {
      v12 = v23;
      v14 = 87;
      goto LABEL_18;
    }
    goto LABEL_14;
  }
  v15 = *(_QWORD *)(a3 + 16);
  v16 = -1;
  v17 = *(_QWORD *)(a3 + 8);
  v18 = -1;
  v25[1] = 0;
  do
    ++v18;
  while ( *(_WORD *)(v15 + 2 * v18) );
  do
    ++v16;
  while ( *(_WORD *)(v17 + 2 * v16) );
  v12 = v23;
  updated = EapMsChapv2UpdateCredential(v17, (int)v16 + 1, v15, (int)v18 + 1, (__int64)v23, (__int64)&v24);
  v13 = v24;
  v14 = updated;
  if ( !updated )
    goto LABEL_15;
LABEL_18:
  LocalFree(v11);
  LocalFree(v12);
  LocalFree(v13);
  return v14;
}

```

## disassembly

```asm
0x180016ee0  push    rbp
0x180016ee2  push    rbx
0x180016ee3  push    rsi
0x180016ee4  push    rdi
0x180016ee5  push    r12
0x180016ee7  push    r13
0x180016ee9  push    r14
0x180016eeb  push    r15
0x180016eed  mov     rbp, rsp
0x180016ef0  sub     rsp, 48h
0x180016ef4  mov     rax, [rbp+arg_20]
0x180016ef8  mov     r12d, ecx
0x180016efb  xor     ecx, ecx
0x180016efd  mov     r13, r9
0x180016f00  mov     [r9], ecx
0x180016f03  mov     r15, r8
0x180016f06  mov     [rbp+arg_18], rcx
0x180016f0a  mov     ebx, ecx
0x180016f0c  mov     [rax], rcx
0x180016f0f  mov     esi, ecx
0x180016f11  mov     rax, [rbp+arg_28]
0x180016f15  mov     r14d, ecx
0x180016f18  mov     [rbp+var_18], rcx
0x180016f1c  mov     [rbp+var_10], rcx
0x180016f20  mov     [rax], ecx
0x180016f22  mov     rax, [rbp+arg_30]
0x180016f26  mov     [rax], rcx
0x180016f29  cmp     edx, 1Ah
0x180016f2c  jz      short loc_180016F36
0x180016f2e  lea     edi, [rcx+57h]
0x180016f31  jmp     loc_180017018
0x180016f36  lea     r9, [rbp+arg_18]
0x180016f3a  xor     r8d, r8d
0x180016f3d  xor     edx, edx
0x180016f3f  mov     ecx, r12d
0x180016f42  call    ReadConnectionData
0x180016f47  mov     edi, eax
0x180016f49  test    eax, eax
0x180016f4b  jnz     loc_180017014
0x180016f51  lea     r8, [rbp+var_18]
0x180016f55  xor     edx, edx; Size
0x180016f57  xor     ecx, ecx; Src
0x180016f59  call    ReadUserData
0x180016f5e  mov     edi, eax
0x180016f60  xor     eax, eax
0x180016f62  test    edi, edi
0x180016f64  jnz     loc_180017010
0x180016f6a  mov     rbx, [rbp+arg_18]
0x180016f6e  test    r12b, 20h
0x180016f72  jnz     short loc_180016FD8
0x180016f74  cmp     dword ptr [r15], 1
0x180016f78  jnz     short loc_180016FC7
0x180016f7a  mov     r8, [r15+10h]
0x180016f7e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180016f82  mov     rcx, [r15+8]
0x180016f86  mov     r9, rdx
0x180016f89  mov     [rbx+4], eax
0x180016f8c  inc     r9
0x180016f8f  cmp     [r8+r9*2], ax
0x180016f94  jnz     short loc_180016F8C
0x180016f96  inc     rdx
0x180016f99  cmp     [rcx+rdx*2], ax
0x180016f9d  jnz     short loc_180016F96
0x180016f9f  mov     rsi, [rbp+var_18]
0x180016fa3  lea     rax, [rbp+var_10]
0x180016fa7  inc     r9d
0x180016faa  mov     [rsp+48h+var_20], rax
0x180016faf  inc     edx
0x180016fb1  mov     [rsp+48h+var_28], rsi
0x180016fb6  call    EapMsChapv2UpdateCredential
0x180016fbb  mov     r14, [rbp+var_10]
0x180016fbf  mov     edi, eax
0x180016fc1  test    eax, eax
0x180016fc3  jz      short loc_180016FE3
0x180016fc5  jmp     short loc_180017018
0x180016fc7  cmp     dword ptr [r15], 2
0x180016fcb  jz      short loc_180016FD8
0x180016fcd  mov     rsi, [rbp+var_18]
0x180016fd1  mov     edi, 57h ; 'W'
0x180016fd6  jmp     short loc_180017018
0x180016fd8  mov     r14, [rbp+var_18]
0x180016fdc  mov     dword ptr [rbx+4], 2
0x180016fe3  mov     rax, [rbp+arg_20]
0x180016fe7  mov     rcx, r14
0x180016fea  mov     dword ptr [r13+0], 8
0x180016ff2  mov     [rax], rbx
0x180016ff5  call    MschapV2UserPropBuffSize
0x180016ffa  mov     rcx, [rbp+arg_28]
0x180016ffe  mov     [rcx], eax
0x180017000  mov     rax, [rbp+arg_30]
0x180017004  mov     [rax], r14
0x180017007  xor     eax, eax
0x180017009  mov     ebx, eax
0x18001700b  mov     r14d, eax
0x18001700e  jmp     short loc_180017018
0x180017010  mov     rsi, [rbp+var_18]
0x180017014  mov     rbx, [rbp+arg_18]
0x180017018  mov     rcx, rbx; hMem
0x18001701b  call    cs:__imp_LocalFree
0x180017021  mov     rcx, rsi; hMem
0x180017024  call    cs:__imp_LocalFree
0x18001702a  mov     rcx, r14; hMem
0x18001702d  call    cs:__imp_LocalFree
0x180017033  mov     eax, edi
0x180017035  add     rsp, 48h
0x180017039  pop     r15
0x18001703b  pop     r14
0x18001703d  pop     r13
0x18001703f  pop     r12
0x180017041  pop     rdi
0x180017042  pop     rsi
0x180017043  pop     rbx
0x180017044  pop     rbp
0x180017045  retn
```
