# NpCreateSymlinkFsCtl

- ea: `0x14000b15c`
- end: `0x14000b34c`
- name: `NpCreateSymlinkFsCtl`
- size: `496`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x14000efb0`

## callees

- `0x140001e10`
- `0x140002240`
- `0x14000b15c`
- `0x14000bf50`
- `0x14000c3b4`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000b22a`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000b22a`
- `ntoskrnl!SeCreateAccessState` at `0x14000b248`
- `ntoskrnl!SeCreateAccessState` at `0x14000b248`
- `ntoskrnl!PsGetCurrentSilo` at `0x14000b27d`
- `ntoskrnl!PsGetCurrentSilo` at `0x14000b27d`
- `ntoskrnl!SeDeleteAccessState` at `0x14000b309`
- `ntoskrnl!SeDeleteAccessState` at `0x14000b309`

## pseudocode

```c
__int64 __fastcall NpCreateSymlinkFsCtl(__int64 a1, __int64 a2)
{
  __int64 v4; // r9
  __int64 v5; // rcx
  unsigned int v6; // r9d
  unsigned __int16 *v7; // rsi
  unsigned int v8; // edx
  PGENERIC_MAPPING FileObjectGenericMapping; // rax
  __int64 result; // rax
  KPROCESSOR_MODE PreviousMode; // di
  __int64 v12; // rbx
  int CurrentSilo; // eax
  int Symlink; // ebx
  __int64 v15; // r9
  int v16; // r8d
  int v17; // [rsp+30h] [rbp-D0h] BYREF
  int v18; // [rsp+34h] [rbp-CCh]
  char *v19; // [rsp+38h] [rbp-C8h]
  _WORD v20[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v21; // [rsp+44h] [rbp-BCh]
  char *v22; // [rsp+48h] [rbp-B8h]
  __int64 v23; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v24[20]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v25[224]; // [rsp+100h] [rbp+0h] BYREF

  memset(v24, 0, sizeof(v24));
  memset(v25, 0, sizeof(v25));
  v4 = *(_QWORD *)(a2 + 184);
  v18 = 0;
  v21 = 0;
  v23 = 0;
  v5 = *(_QWORD *)(v4 + 48);
  if ( **(_WORD **)(v5 + 24) != 513 || (*(_QWORD *)(v5 + 32) & 1) == 0 )
    return 3221225647LL;
  v6 = *(_DWORD *)(v4 + 16);
  if ( v6 < 0xC )
    return 3221225485LL;
  v7 = *(unsigned __int16 **)(a2 + 24);
  v8 = v7[1] + *v7;
  if ( v8 <= v7[2] + (unsigned int)v7[3] )
    v8 = v7[2] + v7[3];
  if ( v8 > v6 )
    return 3221225485LL;
  FileObjectGenericMapping = IoGetFileObjectGenericMapping();
  result = SeCreateAccessState(v24, v25, 2, FileObjectGenericMapping);
  if ( (int)result >= 0 )
  {
    PreviousMode = *(_BYTE *)(a2 + 64);
    v12 = *(_QWORD *)(a1 + 64);
    v19 = (char *)v7 + *v7;
    LOWORD(v17) = v7[1];
    HIWORD(v17) = v17;
    CurrentSilo = PsGetCurrentSilo();
    Symlink = NpCreateSymlinkAccessCheck((int)&v17, *((_DWORD *)v7 + 2), CurrentSilo, v12, PreviousMode, (__int64)v24);
    if ( Symlink >= 0 )
    {
      v15 = *(_QWORD *)(a1 + 64);
      v16 = *((_DWORD *)v7 + 2);
      v22 = (char *)v7 + v7[2];
      v20[0] = v7[3];
      v20[1] = v20[0];
      Symlink = NpCreateSymlink((unsigned int)&v17, (unsigned int)v20, v16, v15, (__int64)v24, (__int64)&v23);
      if ( Symlink >= 0 )
        *(_QWORD *)(a2 + 56) = 0;
    }
    SeDeleteAccessState(v24);
    return (unsigned int)Symlink;
  }
  return result;
}

```

## disassembly

```asm
0x14000b15c  mov     [rsp-8+arg_10], rbx
0x14000b161  push    rbp
0x14000b162  push    rsi
0x14000b163  push    rdi
0x14000b164  push    r14
0x14000b166  push    r15
0x14000b168  lea     rbp, [rsp-0F0h]
0x14000b170  sub     rsp, 1F0h
0x14000b177  mov     rax, cs:__security_cookie
0x14000b17e  xor     rax, rsp
0x14000b181  mov     [rbp+110h+var_30], rax
0x14000b188  mov     r14, rdx
0x14000b18b  mov     r15, rcx
0x14000b18e  xor     edx, edx; Val
0x14000b190  lea     rcx, [rsp+210h+var_1B0]; void *
0x14000b195  mov     r8d, 0A0h; Size
0x14000b19b  call    memset
0x14000b1a0  xor     edx, edx; Val
0x14000b1a2  lea     rcx, [rbp+110h+var_110]; void *
0x14000b1a6  mov     r8d, 0E0h; Size
0x14000b1ac  call    memset
0x14000b1b1  mov     r9, [r14+0B8h]
0x14000b1b8  mov     edx, 201h
0x14000b1bd  mov     [rsp+210h+var_1DC], 0
0x14000b1c5  mov     [rsp+210h+var_1CC], 0
0x14000b1cd  mov     [rsp+210h+var_1C0], 0
0x14000b1d6  mov     rcx, [r9+30h]
0x14000b1da  mov     rax, [rcx+18h]
0x14000b1de  cmp     [rax], dx
0x14000b1e1  jnz     loc_14000B320
0x14000b1e7  mov     rax, [rcx+20h]
0x14000b1eb  test    al, 1
0x14000b1ed  jz      loc_14000B320
0x14000b1f3  mov     r9d, [r9+10h]
0x14000b1f7  cmp     r9d, 0Ch
0x14000b1fb  jb      loc_14000B319
0x14000b201  mov     rsi, [r14+18h]
0x14000b205  movzx   eax, word ptr [rsi+4]
0x14000b209  movzx   r8d, word ptr [rsi+6]
0x14000b20e  movzx   edx, word ptr [rsi]
0x14000b211  add     r8d, eax
0x14000b214  movzx   eax, word ptr [rsi+2]
0x14000b218  add     edx, eax
0x14000b21a  cmp     edx, r8d
0x14000b21d  cmovbe  edx, r8d
0x14000b221  cmp     edx, r9d
0x14000b224  ja      loc_14000B319
0x14000b22a  call    cs:__imp_IoGetFileObjectGenericMapping
0x14000b231  nop     dword ptr [rax+rax+00h]
0x14000b236  mov     r8d, 2
0x14000b23c  lea     rdx, [rbp+110h+var_110]
0x14000b240  mov     r9, rax
0x14000b243  lea     rcx, [rsp+210h+var_1B0]
0x14000b248  call    cs:__imp_SeCreateAccessState
0x14000b24f  nop     dword ptr [rax+rax+00h]
0x14000b254  test    eax, eax
0x14000b256  js      loc_14000B325
0x14000b25c  movzx   eax, word ptr [rsi]
0x14000b25f  mov     dil, [r14+40h]
0x14000b263  add     rax, rsi
0x14000b266  mov     rbx, [r15+40h]
0x14000b26a  mov     [rsp+210h+var_1D8], rax
0x14000b26f  movzx   eax, word ptr [rsi+2]
0x14000b273  mov     word ptr [rsp+210h+var_1E0], ax
0x14000b278  mov     word ptr [rsp+210h+var_1E0+2], ax
0x14000b27d  call    cs:__imp_PsGetCurrentSilo
0x14000b284  nop     dword ptr [rax+rax+00h]
0x14000b289  mov     edx, [rsi+8]; int
0x14000b28c  lea     rcx, [rsp+210h+var_1B0]
0x14000b291  mov     [rsp+210h+var_1E8], rcx; __int64
0x14000b296  mov     r9, rbx; int
0x14000b299  lea     rcx, [rsp+210h+var_1E0]; int
0x14000b29e  mov     [rsp+210h+PreviousMode], dil; PreviousMode
0x14000b2a3  mov     r8, rax; int
0x14000b2a6  call    NpCreateSymlinkAccessCheck
0x14000b2ab  mov     ebx, eax
0x14000b2ad  test    eax, eax
0x14000b2af  js      short loc_14000B304
0x14000b2b1  movzx   eax, word ptr [rsi+4]
0x14000b2b5  lea     rdx, [rsp+210h+var_1D0]
0x14000b2ba  mov     r9, [r15+40h]
0x14000b2be  lea     rcx, [rsp+210h+var_1E0]
0x14000b2c3  mov     r8d, [rsi+8]
0x14000b2c7  add     rax, rsi
0x14000b2ca  mov     [rsp+210h+var_1C8], rax
0x14000b2cf  movzx   eax, word ptr [rsi+6]
0x14000b2d3  mov     [rsp+210h+var_1D0], ax
0x14000b2d8  mov     [rsp+210h+var_1CE], ax
0x14000b2dd  lea     rax, [rsp+210h+var_1C0]
0x14000b2e2  mov     [rsp+210h+var_1E8], rax
0x14000b2e7  lea     rax, [rsp+210h+var_1B0]
0x14000b2ec  mov     qword ptr [rsp+210h+PreviousMode], rax
0x14000b2f1  call    NpCreateSymlink
0x14000b2f6  mov     ebx, eax
0x14000b2f8  test    eax, eax
0x14000b2fa  js      short loc_14000B304
0x14000b2fc  mov     qword ptr [r14+38h], 0
0x14000b304  lea     rcx, [rsp+210h+var_1B0]
0x14000b309  call    cs:__imp_SeDeleteAccessState
0x14000b310  nop     dword ptr [rax+rax+00h]
0x14000b315  mov     eax, ebx
0x14000b317  jmp     short loc_14000B325
0x14000b319  mov     eax, 0C000000Dh
0x14000b31e  jmp     short loc_14000B325
0x14000b320  mov     eax, 0C00000AFh
0x14000b325  mov     rcx, [rbp+110h+var_30]
0x14000b32c  xor     rcx, rsp; StackCookie
0x14000b32f  call    __security_check_cookie
0x14000b334  mov     rbx, [rsp+210h+arg_10]
0x14000b33c  add     rsp, 1F0h
0x14000b343  pop     r15
0x14000b345  pop     r14
0x14000b347  pop     rdi
0x14000b348  pop     rsi
0x14000b349  pop     rbp
0x14000b34a  retn
```
