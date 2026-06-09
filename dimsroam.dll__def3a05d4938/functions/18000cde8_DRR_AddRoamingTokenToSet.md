# DRR_AddRoamingTokenToSet

- ea: `0x18000cde8`
- end: `0x18000ceb6`
- name: `DRR_AddRoamingTokenToSet`
- size: `206`
- prototype: `__int64 __fastcall(__int64, const void *, int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800036c8`
- `0x180004110`
- `0x180005a30`

## callees

- `0x18000cde8`
- `0x18000d110`
- `0x18000d34c`
- `0x18000d886`

## pseudocode

```c
__int64 __fastcall DRR_AddRoamingTokenToSet(__int64 a1, const void *a2, int a3)
{
  unsigned int v3; // esi
  __int64 v4; // rbx
  const void **v8; // r12
  int v9; // eax
  int v10; // eax
  unsigned int v11; // r14d
  int v12; // eax
  unsigned int inserted; // ebx

  v3 = *(_DWORD *)(a1 + 8);
  LODWORD(v4) = 0;
  if ( !v3 )
    goto LABEL_17;
  v8 = *(const void ***)a1;
  v9 = memcmp_0(a2, **(const void ***)a1, 0x60u);
  if ( v9 < 0 )
    goto LABEL_17;
  if ( v9 <= 0 )
    goto LABEL_16;
  v4 = v3 - 1;
  v10 = memcmp_0(a2, v8[v4], 0x60u);
  if ( v10 > 0 )
    goto LABEL_5;
  if ( v10 >= 0 )
  {
LABEL_16:
    if ( !a3 )
      goto LABEL_17;
LABEL_15:
    inserted = 183;
    goto LABEL_18;
  }
  v11 = 0;
  if ( (unsigned int)v4 <= 1 )
    goto LABEL_17;
  while ( 1 )
  {
    v3 = ((unsigned int)v4 + v11) >> 1;
    v12 = memcmp_0(a2, v8[v3], 0x60u);
    if ( v12 >= 0 )
      break;
    LODWORD(v4) = ((unsigned int)v4 + v11) >> 1;
LABEL_12:
    if ( v11 + 1 >= (unsigned int)v4 )
      goto LABEL_17;
  }
  if ( v12 > 0 )
  {
    v11 = ((unsigned int)v4 + v11) >> 1;
    goto LABEL_12;
  }
  if ( a3 )
    goto LABEL_15;
LABEL_5:
  LODWORD(v4) = v3;
LABEL_17:
  inserted = DRR_InsertGrowableArray(a1, (unsigned int)v4, a2);
  if ( inserted )
LABEL_18:
    DRR_SecureFreeRoamingToken(a2);
  return inserted;
}

```

## disassembly

```asm
0x18000cde8  push    rbx
0x18000cdea  push    rbp
0x18000cdeb  push    rsi
0x18000cdec  push    rdi
0x18000cded  push    r12
0x18000cdef  push    r13
0x18000cdf1  push    r14
0x18000cdf3  push    r15
0x18000cdf5  sub     rsp, 28h
0x18000cdf9  mov     esi, [rcx+8]
0x18000cdfc  xor     ebx, ebx
0x18000cdfe  mov     edi, r8d
0x18000ce01  mov     rbp, rdx
0x18000ce04  mov     r15, rcx
0x18000ce07  test    esi, esi
0x18000ce09  jz      short loc_18000CE88
0x18000ce0b  mov     r12, [rcx]
0x18000ce0e  lea     r13d, [rbx+60h]
0x18000ce12  mov     r8d, r13d; Size
0x18000ce15  mov     rcx, rbp; Buf1
0x18000ce18  mov     rdx, [r12]; Buf2
0x18000ce1c  call    memcmp_0
0x18000ce21  test    eax, eax
0x18000ce23  js      short loc_18000CE88
0x18000ce25  jle     short loc_18000CE84
0x18000ce27  lea     ebx, [rsi-1]
0x18000ce2a  mov     r8d, r13d; Size
0x18000ce2d  mov     rdx, [r12+rbx*8]; Buf2
0x18000ce31  mov     rcx, rbp; Buf1
0x18000ce34  call    memcmp_0
0x18000ce39  test    eax, eax
0x18000ce3b  jle     short loc_18000CE41
0x18000ce3d  mov     ebx, esi
0x18000ce3f  jmp     short loc_18000CE88
0x18000ce41  jns     short loc_18000CE84
0x18000ce43  xor     r14d, r14d
0x18000ce46  cmp     ebx, 1
0x18000ce49  jbe     short loc_18000CE88
0x18000ce4b  lea     eax, [rbx+r14]
0x18000ce4f  mov     r8, r13; Size
0x18000ce52  shr     eax, 1
0x18000ce54  mov     rcx, rbp; Buf1
0x18000ce57  mov     esi, eax
0x18000ce59  mov     rdx, [r12+rax*8]; Buf2
0x18000ce5d  call    memcmp_0
0x18000ce62  test    eax, eax
0x18000ce64  jns     short loc_18000CE6A
0x18000ce66  mov     ebx, esi
0x18000ce68  jmp     short loc_18000CE6F
0x18000ce6a  jle     short loc_18000CE79
0x18000ce6c  mov     r14d, esi
0x18000ce6f  lea     eax, [r14+1]
0x18000ce73  cmp     eax, ebx
0x18000ce75  jb      short loc_18000CE4B
0x18000ce77  jmp     short loc_18000CE88
0x18000ce79  test    edi, edi
0x18000ce7b  jz      short loc_18000CE3D
0x18000ce7d  mov     ebx, 0B7h
0x18000ce82  jmp     short loc_18000CE9B
0x18000ce84  test    edi, edi
0x18000ce86  jnz     short loc_18000CE7D
0x18000ce88  mov     r8, rbp
0x18000ce8b  mov     edx, ebx
0x18000ce8d  mov     rcx, r15
0x18000ce90  call    DRR_InsertGrowableArray
0x18000ce95  mov     ebx, eax
0x18000ce97  test    eax, eax
0x18000ce99  jz      short loc_18000CEA3
0x18000ce9b  mov     rcx, rbp
0x18000ce9e  call    DRR_SecureFreeRoamingToken
0x18000cea3  mov     eax, ebx
0x18000cea5  add     rsp, 28h
0x18000cea9  pop     r15
0x18000ceab  pop     r14
0x18000cead  pop     r13
0x18000ceaf  pop     r12
0x18000ceb1  pop     rdi
0x18000ceb2  pop     rsi
0x18000ceb3  pop     rbp
0x18000ceb4  pop     rbx
0x18000ceb5  retn
```
