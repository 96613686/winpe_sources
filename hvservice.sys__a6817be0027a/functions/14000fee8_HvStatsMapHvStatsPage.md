# HvStatsMapHvStatsPage

- ea: `0x14000fee8`
- end: `0x140010064`
- name: `HvStatsMapHvStatsPage`
- size: `380`
- prototype: `__int64 __fastcall(__int64, int, unsigned int, unsigned int, _QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14000ecd0`

## callees

- `0x140002824`
- `0x140002ae0`
- `0x140002f00`
- `0x14000e070`
- `0x14000e0b0`
- `0x14000e230`
- `0x14000fee8`
- `0x1400102f0`
- `0x140010320`
- `0x140010458`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000ff8c`
- `ntoskrnl!ExAllocatePool2` at `0x14000ff8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010031`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010031`

## pseudocode

```c
__int64 __fastcall HvStatsMapHvStatsPage(__int64 a1, int a2, unsigned int a3, unsigned int a4, _QWORD *a5)
{
  int v9; // ebx
  __int64 v10; // rsi
  int v11; // ebp
  _QWORD *v12; // rdi
  int v13; // r8d
  int v14; // r9d
  _DWORD *Pool2; // rax
  _QWORD *v16; // rcx
  __int128 v18; // [rsp+30h] [rbp-58h] BYREF

  *a5 = 0;
  v18 = 0;
  HviGetHypervisorFeatures(&v18);
  if ( (v18 & 0x100000000000LL) != 0 || ((a3 - 3) & 0xFFFFFFFB) == 0 )
  {
    v10 = a1 + 160;
    v11 = 0;
    HvStatspLockExclusive(v10);
    v12 = (_QWORD *)HvStatspLookupMapping(v10, a3, a4);
    if ( v12 )
      goto LABEL_8;
    Pool2 = (_DWORD *)ExAllocatePool2(256, 104, 1951626824);
    v12 = Pool2;
    if ( !Pool2 )
    {
      v9 = -1073741670;
      goto LABEL_15;
    }
    v11 = 1;
    Pool2[4] = a3;
    Pool2[5] = a4;
    memset(Pool2 + 10, 0, 0x40u);
    v12[11] = v12 + 10;
    v12[10] = v12 + 10;
    v9 = HvStatspMap(v12);
    if ( v9 >= 0 )
    {
LABEL_8:
      v9 = HvStatspClientBufferShare((int)v12 + 40, a2, v13, v14, (__int64)a5);
      if ( v9 >= 0 )
      {
        if ( v11 )
        {
          v16 = *(_QWORD **)(v10 + 16);
          if ( *v16 != v10 + 8 )
            __fastfail(3u);
          *v12 = v10 + 8;
          v12[1] = v16;
          *v16 = v12;
          *(_QWORD *)(v10 + 16) = v12;
        }
        goto LABEL_15;
      }
      if ( !v11 )
      {
LABEL_15:
        HvStatspUnlock(v10);
        return (unsigned int)v9;
      }
    }
    HvStatspUnmap(v12);
    ExFreePoolWithTag(v12, 0x74537648u);
    goto LABEL_15;
  }
  return (unsigned int)-1073741790;
}

```

## disassembly

```asm
0x14000fee8  push    rbx
0x14000feea  push    rbp
0x14000feeb  push    rsi
0x14000feec  push    rdi
0x14000feed  push    r12
0x14000feef  push    r14
0x14000fef1  push    r15
0x14000fef3  sub     rsp, 50h
0x14000fef7  mov     rax, cs:__security_cookie
0x14000fefe  xor     rax, rsp
0x14000ff01  mov     [rsp+88h+var_48], rax
0x14000ff06  mov     r15, [rsp+88h+arg_20]
0x14000ff0e  mov     rsi, rcx
0x14000ff11  xorps   xmm0, xmm0
0x14000ff14  lea     rcx, [rsp+88h+var_58]
0x14000ff19  mov     r14d, r9d
0x14000ff1c  mov     ebx, r8d
0x14000ff1f  mov     r12, rdx
0x14000ff22  mov     qword ptr [r15], 0
0x14000ff29  movups  [rsp+88h+var_58], xmm0
0x14000ff2e  call    HviGetHypervisorFeatures
0x14000ff33  mov     rax, 100000000000h
0x14000ff3d  test    qword ptr [rsp+88h+var_58], rax
0x14000ff42  jnz     short loc_14000FF58
0x14000ff44  lea     eax, [rbx-3]
0x14000ff47  test    eax, 0FFFFFFFBh
0x14000ff4c  jz      short loc_14000FF58
0x14000ff4e  mov     ebx, 0C0000022h
0x14000ff53  jmp     loc_140010045
0x14000ff58  add     rsi, 0A0h
0x14000ff5f  xor     ebp, ebp
0x14000ff61  mov     rcx, rsi
0x14000ff64  call    HvStatspLockExclusive
0x14000ff69  mov     r8d, r14d
0x14000ff6c  mov     edx, ebx
0x14000ff6e  mov     rcx, rsi
0x14000ff71  call    HvStatspLookupMapping
0x14000ff76  mov     rdi, rax
0x14000ff79  test    rax, rax
0x14000ff7c  jnz     short loc_14000FFDE
0x14000ff7e  lea     edx, [rbp+68h]
0x14000ff81  mov     ecx, 100h
0x14000ff86  mov     r8d, 74537648h
0x14000ff8c  call    cs:__imp_ExAllocatePool2
0x14000ff93  nop     dword ptr [rax+rax+00h]
0x14000ff98  mov     rdi, rax
0x14000ff9b  test    rax, rax
0x14000ff9e  jnz     short loc_14000FFAA
0x14000ffa0  mov     ebx, 0C000009Ah
0x14000ffa5  jmp     loc_14001003D
0x14000ffaa  mov     ebp, 1
0x14000ffaf  mov     [rax+10h], ebx
0x14000ffb2  xor     edx, edx; Val
0x14000ffb4  mov     [rax+14h], r14d
0x14000ffb8  lea     rcx, [rax+28h]; void *
0x14000ffbc  lea     r8d, [rbp+3Fh]; Size
0x14000ffc0  call    memset
0x14000ffc5  lea     rax, [rdi+50h]
0x14000ffc9  mov     rcx, rdi
0x14000ffcc  mov     [rax+8], rax
0x14000ffd0  mov     [rax], rax
0x14000ffd3  call    HvStatspMap
0x14000ffd8  mov     ebx, eax
0x14000ffda  test    eax, eax
0x14000ffdc  js      short loc_140010021
0x14000ffde  lea     rcx, [rdi+28h]
0x14000ffe2  mov     [rsp+88h+var_68], r15
0x14000ffe7  mov     rdx, r12
0x14000ffea  call    HvStatspClientBufferShare
0x14000ffef  mov     ebx, eax
0x14000fff1  test    eax, eax
0x14000fff3  js      short loc_14001001D
0x14000fff5  test    ebp, ebp
0x14000fff7  jz      short loc_14001003D
0x14000fff9  lea     rax, [rsi+8]
0x14000fffd  mov     rcx, [rax+8]
0x140010001  cmp     [rcx], rax
0x140010004  jz      short loc_14001000D
0x140010006  mov     ecx, 3
0x14001000b  int     29h; Win8: RtlFailFast(ecx)
0x14001000d  mov     [rdi], rax
0x140010010  mov     [rdi+8], rcx
0x140010014  mov     [rcx], rdi
0x140010017  mov     [rax+8], rdi
0x14001001b  jmp     short loc_14001003D
0x14001001d  test    ebp, ebp
0x14001001f  jz      short loc_14001003D
0x140010021  mov     rcx, rdi
0x140010024  call    HvStatspUnmap
0x140010029  mov     edx, 74537648h; Tag
0x14001002e  mov     rcx, rdi; P
0x140010031  call    cs:__imp_ExFreePoolWithTag
0x140010038  nop     dword ptr [rax+rax+00h]
0x14001003d  mov     rcx, rsi
0x140010040  call    HvStatspUnlock
0x140010045  mov     eax, ebx
0x140010047  mov     rcx, [rsp+88h+var_48]
0x14001004c  xor     rcx, rsp; StackCookie
0x14001004f  call    __security_check_cookie
0x140010054  add     rsp, 50h
0x140010058  pop     r15
0x14001005a  pop     r14
0x14001005c  pop     r12
0x14001005e  pop     rdi
0x14001005f  pop     rsi
0x140010060  pop     rbp
0x140010061  pop     rbx
0x140010062  retn
```
