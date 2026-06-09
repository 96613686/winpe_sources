# SecCacheFsQueryFileEa

- ea: `0x14002fdd8`
- end: `0x14003001e`
- name: `SecCacheFsQueryFileEa`
- size: `582`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400302a4`

## callees

- `0x140009b80`
- `0x1400100d4`
- `0x140011610`
- `0x140011650`
- `0x140011700`
- `0x1400119c0`
- `0x14002fdd8`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002fec3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002fec3`

## pseudocode

```c
__int64 __fastcall SecCacheFsQueryFileEa(
        __int64 a1,
        __int64 a2,
        unsigned __int64 a3,
        _QWORD *a4,
        _QWORD *a5,
        _DWORD *a6)
{
  unsigned int v6; // esi
  _QWORD *v8; // rdi
  unsigned int v10; // r12d
  int v11; // r14d
  unsigned int v12; // r8d
  __int64 v13; // rax
  int v14; // edx
  SIZE_T v15; // rdx
  _BYTE *PoolWithTag; // rax
  _BYTE *v17; // rbp
  char *v18; // r15
  unsigned __int64 v19; // rdx
  __int64 v20; // rcx
  int v21; // r12d
  unsigned int v22; // r14d
  __int64 v23; // rdi
  unsigned int v24; // eax
  unsigned int v25; // ebx
  int v26; // ebx
  int v28; // [rsp+50h] [rbp-88h]
  unsigned int v29; // [rsp+54h] [rbp-84h]
  int v33; // [rsp+90h] [rbp-48h] BYREF

  v6 = 0;
  v8 = a4;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v33 = 0;
  v29 = 0;
  v28 = 0;
  if ( a3 )
  {
    v13 = 0;
    do
    {
      ++v12;
      v14 = **(unsigned __int16 **)(a2 + 24 * v13);
      v10 += (v14 + *(unsigned __int16 *)(a2 + 24 * v13 + 16) + 12) & 0xFFFFFFFC;
      v11 += (v14 + 9) & 0xFFFFFFFC;
      v13 = v12;
    }
    while ( v12 < a3 );
    v29 = v10;
    v28 = v11;
  }
  v15 = v11 + v10;
  if ( qword_140020008 )
    PoolWithTag = (_BYTE *)((__int64 (__fastcall *)(__int64, SIZE_T, __int64, __int64))qword_140020008)(
                             256,
                             v15,
                             1366123859,
                             a2);
  else
    PoolWithTag = ExAllocatePoolWithTag(PagedPool, v15, 0x516D6553u);
  v17 = PoolWithTag;
  if ( PoolWithTag )
  {
    memset(PoolWithTag, 0, v11 + v10);
    v18 = &v17[v11];
    if ( a3 )
    {
      v19 = a3 - 1;
      v20 = 0;
      v21 = 0;
      v22 = 0;
      do
      {
        v23 = 3 * v20;
        v24 = 0;
        v25 = (**(unsigned __int16 **)(a2 + 24 * v20) + 9) & 0xFFFFFFFC;
        if ( v20 != v19 )
          v24 = (**(unsigned __int16 **)(a2 + 24 * v20) + 9) & 0xFFFFFFFC;
        *(_DWORD *)&v17[v21] = v24;
        v17[v21 + 4] = **(_BYTE **)(a2 + 24 * v20);
        memmove(
          &v17[v21 + 5],
          *(const void **)(*(_QWORD *)(a2 + 24 * v20) + 8LL),
          **(unsigned __int16 **)(a2 + 24 * v20));
        ++v22;
        *(_DWORD *)(a2 + 8 * v23 + 20) = -1073741275;
        v20 = v22;
        v19 = a3 - 1;
        v21 += v25;
      }
      while ( v22 < a3 );
      v11 = v28;
      v10 = v29;
      v8 = a4;
    }
    v26 = FsRtlQueryKernelEaFile_0(a1, v18, v10, 0, v17, v11, 0, 0, &v33);
    if ( v26 < 0 )
    {
      SecFreePool(v17, 0x516D6553u);
      return (unsigned int)v26;
    }
    else
    {
      *v8 = v17;
      *a5 = v18;
      *a6 = v33;
    }
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v6;
}

```

## disassembly

```asm
0x14002fdd8  mov     r11, rsp
0x14002fddb  mov     [r11+18h], rbx
0x14002fddf  push    rbp
0x14002fde0  push    rsi
0x14002fde1  push    rdi
0x14002fde2  push    r12
0x14002fde4  push    r13
0x14002fde6  push    r14
0x14002fde8  push    r15
0x14002fdea  sub     rsp, 0A0h
0x14002fdf1  mov     rax, cs:__security_cookie
0x14002fdf8  xor     rax, rsp
0x14002fdfb  mov     [rsp+0D8h+var_40], rax
0x14002fe03  mov     rax, [rsp+0D8h+arg_20]
0x14002fe0b  xor     esi, esi
0x14002fe0d  mov     r13, r8
0x14002fe10  mov     [rsp+0D8h+var_58], rax
0x14002fe18  mov     rax, [rsp+0D8h+arg_28]
0x14002fe20  mov     rdi, r9
0x14002fe23  mov     [rsp+0D8h+var_68], r9
0x14002fe28  mov     r9, rdx
0x14002fe2b  mov     [rsp+0D8h+var_50], rax
0x14002fe33  mov     r12d, esi
0x14002fe36  mov     [rsp+0D8h+var_78], rdx
0x14002fe3b  mov     r14d, esi
0x14002fe3e  mov     [rsp+0D8h+var_60], rcx
0x14002fe43  mov     r8d, esi
0x14002fe46  mov     [r11-48h], esi
0x14002fe4a  mov     r10d, 0FFFFFFFCh
0x14002fe50  mov     [rsp+0D8h+var_84], esi
0x14002fe54  mov     [rsp+0D8h+var_88], esi
0x14002fe58  test    r13, r13
0x14002fe5b  jz      short loc_14002FE99
0x14002fe5d  mov     eax, esi
0x14002fe5f  lea     rcx, [rax+rax*2]
0x14002fe63  inc     r8d
0x14002fe66  mov     rax, [r9+rcx*8]
0x14002fe6a  movzx   ecx, word ptr [r9+rcx*8+10h]
0x14002fe70  add     ecx, 0Ch
0x14002fe73  movzx   edx, word ptr [rax]
0x14002fe76  add     ecx, edx
0x14002fe78  and     ecx, r10d
0x14002fe7b  add     r12d, ecx
0x14002fe7e  lea     eax, [rdx+9]
0x14002fe81  and     eax, r10d
0x14002fe84  add     r14d, eax
0x14002fe87  mov     eax, r8d
0x14002fe8a  cmp     rax, r13
0x14002fe8d  jb      short loc_14002FE5F
0x14002fe8f  mov     [rsp+0D8h+var_84], r12d
0x14002fe94  mov     [rsp+0D8h+var_88], r14d
0x14002fe99  mov     rax, cs:qword_140020008
0x14002fea0  lea     ebx, [r14+r12]
0x14002fea4  mov     r8d, 516D6553h; Tag
0x14002feaa  mov     edx, ebx; NumberOfBytes
0x14002feac  test    rax, rax
0x14002feaf  jz      short loc_14002FEBE
0x14002feb1  mov     ecx, 100h
0x14002feb6  call    cs:__guard_dispatch_icall_fptr
0x14002febc  jmp     short loc_14002FECF
0x14002febe  mov     ecx, 1; PoolType
0x14002fec3  call    cs:__imp_ExAllocatePoolWithTag
0x14002feca  nop     dword ptr [rax+rax+00h]
0x14002fecf  mov     rbp, rax
0x14002fed2  test    rax, rax
0x14002fed5  jnz     short loc_14002FEE1
0x14002fed7  mov     esi, 0C000009Ah
0x14002fedc  jmp     loc_14002FFF0
0x14002fee1  mov     r8, rbx; Size
0x14002fee4  xor     edx, edx; Val
0x14002fee6  mov     rcx, rbp; void *
0x14002fee9  call    memset
0x14002feee  mov     r15d, r14d
0x14002fef1  add     r15, rbp
0x14002fef4  mov     [rsp+0D8h+var_70], r15
0x14002fef9  test    r13, r13
0x14002fefc  jz      loc_14002FF86
0x14002ff02  mov     r15, [rsp+0D8h+var_78]
0x14002ff07  lea     rdx, [r13-1]
0x14002ff0b  mov     rcx, rsi
0x14002ff0e  mov     r12d, esi
0x14002ff11  mov     r14d, esi
0x14002ff14  lea     rdi, [rcx+rcx*2]
0x14002ff18  mov     r9d, r12d
0x14002ff1b  mov     rax, [r15+rdi*8]
0x14002ff1f  movzx   ebx, word ptr [rax]
0x14002ff22  mov     eax, esi
0x14002ff24  add     ebx, 9
0x14002ff27  and     ebx, 0FFFFFFFCh
0x14002ff2a  cmp     rcx, rdx
0x14002ff2d  cmovnz  eax, ebx
0x14002ff30  mov     [r9+rbp], eax
0x14002ff34  mov     rax, [r15+rdi*8]
0x14002ff38  mov     cl, [rax]
0x14002ff3a  mov     [r9+rbp+4], cl
0x14002ff3f  lea     rcx, [r9+5]
0x14002ff43  mov     rdx, [r15+rdi*8]
0x14002ff47  add     rcx, rbp; void *
0x14002ff4a  movzx   r8d, word ptr [rdx]; Size
0x14002ff4e  mov     rdx, [rdx+8]; Src
0x14002ff52  call    memmove
0x14002ff57  inc     r14d
0x14002ff5a  mov     dword ptr [r15+rdi*8+14h], 0C0000225h
0x14002ff63  mov     ecx, r14d
0x14002ff66  lea     rdx, [r13-1]
0x14002ff6a  add     r12d, ebx
0x14002ff6d  cmp     rcx, r13
0x14002ff70  jb      short loc_14002FF14
0x14002ff72  mov     r14d, [rsp+0D8h+var_88]
0x14002ff77  mov     r15, [rsp+0D8h+var_70]
0x14002ff7c  mov     r12d, [rsp+0D8h+var_84]
0x14002ff81  mov     rdi, [rsp+0D8h+var_68]
0x14002ff86  mov     rcx, [rsp+0D8h+var_60]
0x14002ff8b  lea     rax, [rsp+0D8h+var_48]
0x14002ff93  mov     [rsp+0D8h+var_98], rax
0x14002ff98  xor     r9d, r9d
0x14002ff9b  mov     [rsp+0D8h+var_A0], sil
0x14002ffa0  mov     r8d, r12d
0x14002ffa3  mov     [rsp+0D8h+var_A8], rsi
0x14002ffa8  mov     rdx, r15
0x14002ffab  mov     [rsp+0D8h+var_B0], r14d
0x14002ffb0  mov     [rsp+0D8h+var_B8], rbp
0x14002ffb5  call    FsRtlQueryKernelEaFile_0
0x14002ffba  mov     ebx, eax
0x14002ffbc  test    eax, eax
0x14002ffbe  js      short loc_14002FFE1
0x14002ffc0  mov     rax, [rsp+0D8h+var_58]
0x14002ffc8  mov     rcx, [rsp+0D8h+var_50]
0x14002ffd0  mov     [rdi], rbp
0x14002ffd3  mov     [rax], r15
0x14002ffd6  mov     eax, [rsp+0D8h+var_48]
0x14002ffdd  mov     [rcx], eax
0x14002ffdf  jmp     short loc_14002FFF0
0x14002ffe1  mov     edx, 516D6553h; Tag
0x14002ffe6  mov     rcx, rbp; P
0x14002ffe9  call    SecFreePool
0x14002ffee  mov     esi, ebx
0x14002fff0  mov     eax, esi
0x14002fff2  mov     rcx, [rsp+0D8h+var_40]
0x14002fffa  xor     rcx, rsp; StackCookie
0x14002fffd  call    __security_check_cookie
0x140030002  mov     rbx, [rsp+0D8h+arg_10]
0x14003000a  add     rsp, 0A0h
0x140030011  pop     r15
0x140030013  pop     r14
0x140030015  pop     r13
0x140030017  pop     r12
0x140030019  pop     rdi
0x14003001a  pop     rsi
0x14003001b  pop     rbp
0x14003001c  retn
```
