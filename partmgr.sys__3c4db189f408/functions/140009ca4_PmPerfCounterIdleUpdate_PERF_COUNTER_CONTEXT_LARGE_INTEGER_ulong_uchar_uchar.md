# PmPerfCounterIdleUpdate(_PERF_COUNTER_CONTEXT *,_LARGE_INTEGER,ulong *,uchar,uchar)

- ea: `0x140009ca4`
- end: `0x140009ebd`
- name: `?PmPerfCounterIdleUpdate@@YA_KPEAU_PERF_COUNTER_CONTEXT@@T_LARGE_INTEGER@@PEAKEE@Z`
- size: `537`
- prototype: `unsigned __int64 __fastcall(struct _PERF_COUNTER_CONTEXT *, union _LARGE_INTEGER, unsigned int *, unsigned __int8, char)`
- caller_count: `8`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400021c0`
- `0x140002550`
- `0x140002730`
- `0x1400029b0`
- `0x140009c40`
- `0x140009ed0`
- `0x140020e14`
- `0x1400250f0`

## callees

- `0x140009ca4`

## pseudocode

```c
LONGLONG __fastcall PmPerfCounterIdleUpdate(
        union _LARGE_INTEGER *a1,
        union _LARGE_INTEGER a2,
        unsigned int *a3,
        char a4,
        char a5)
{
  signed __int64 v5; // rax
  int v7; // ebx
  union _LARGE_INTEGER *v8; // r10
  unsigned __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // rcx
  unsigned __int64 v13; // [rsp+38h] [rbp+18h]

  v5 = 0;
  HIDWORD(v13) = a4 != 0;
  v7 = 1;
  v8 = 0;
  LODWORD(v13) = 1;
  v9 = v13;
  if ( a5 )
  {
    v9 = -(__int64)v13;
    HIDWORD(v13) = (unsigned __int64)-(__int64)v13 >> 32;
    v7 = v9;
  }
  if ( !a3 )
  {
    if ( a5 && a1[8].LowPart == 1 )
      a1[9] = a2;
    v5 = v9 + _InterlockedExchangeAdd64((volatile signed __int64 *)&a1[8], v9);
    LODWORD(v9) = HIDWORD(KeGetPcr()[1].LockArray);
    if ( (unsigned int)v9 < a1[7].HighPart )
      v8 = &a1[24 * v9 + 16];
LABEL_29:
    v11 = 0;
    if ( a5 )
      return v11;
    goto LABEL_30;
  }
  if ( !a5 )
    *a3 = HIDWORD(KeGetPcr()[1].LockArray);
  v10 = *a3;
  if ( (unsigned int)v10 >= a1[7].HighPart )
    goto LABEL_29;
  v8 = &a1[24 * v10 + 16];
  v5 = v9 + _InterlockedExchangeAdd64((volatile signed __int64 *)&v8[16], v9);
  if ( a5 )
  {
    if ( (_DWORD)v5 )
    {
      if ( !HIDWORD(v5) && a4 )
      {
        v7 = 0;
        v5 = _InterlockedExchangeAdd64((volatile signed __int64 *)&a1[8], 0xFFFFFFFF00000000uLL) - 0x100000000LL;
      }
    }
    else
    {
      v5 = v9 + _InterlockedExchangeAdd64((volatile signed __int64 *)&a1[8], v9);
    }
    if ( !(_DWORD)v5 )
      a1[9] = a2;
    if ( a4 && !HIDWORD(v5) )
    {
      a1[10] = a2;
      return 0;
    }
    goto LABEL_29;
  }
  if ( (_DWORD)v5 == 1 )
  {
    v5 = v9 + _InterlockedExchangeAdd64((volatile signed __int64 *)&a1[8], v9);
  }
  else if ( HIDWORD(v5) == 1 && a4 )
  {
    v7 = 0;
    LODWORD(v13) = 0;
    v5 = v13 + _InterlockedExchangeAdd64((volatile signed __int64 *)&a1[8], v13);
  }
  v11 = 0;
LABEL_30:
  if ( (_DWORD)v5 == 1 && v7 == 1 || a4 && HIDWORD(v5) == 1 )
  {
    if ( v8 )
    {
      if ( (_DWORD)v5 == 1 && v7 == 1 && a2.QuadPart > a1[9].QuadPart )
        v8[5].QuadPart = a2.QuadPart + v8[5].QuadPart - a1[9].QuadPart;
      if ( a4 && HIDWORD(v5) == 1 && a2.QuadPart > a1[10].QuadPart )
        v8[13].QuadPart = a2.QuadPart + v8[13].QuadPart - a1[10].QuadPart;
    }
    if ( (_DWORD)v5 == 1 && v7 == 1 && a2.QuadPart > a1[9].QuadPart )
      return a2.QuadPart - a1[9].QuadPart;
  }
  return v11;
}

```

## disassembly

```asm
0x140009ca4  push    rbx
0x140009ca6  push    rbp
0x140009ca7  push    rsi
0x140009ca8  push    rdi
0x140009ca9  mov     sil, [rsp+20h+arg_20]
0x140009cae  xor     r10d, r10d
0x140009cb1  xor     eax, eax
0x140009cb3  mov     dil, r9b
0x140009cb6  test    dil, dil
0x140009cb9  mov     r11, rcx
0x140009cbc  mov     r9, r8
0x140009cbf  setnz   r10b
0x140009cc3  mov     dword ptr [rsp+20h+arg_10+4], r10d
0x140009cc8  lea     ebp, [rax+1]
0x140009ccb  mov     ebx, ebp
0x140009ccd  xor     r10d, r10d
0x140009cd0  mov     dword ptr [rsp+20h+arg_10], ebx
0x140009cd4  mov     rcx, [rsp+20h+arg_10]
0x140009cd9  test    sil, sil
0x140009cdc  jz      short loc_140009CEA
0x140009cde  neg     rcx
0x140009ce1  mov     [rsp+20h+arg_10], rcx
0x140009ce6  mov     ebx, dword ptr [rsp+20h+arg_10]
0x140009cea  test    r9, r9
0x140009ced  jz      loc_140009DD6
0x140009cf3  test    sil, sil
0x140009cf6  jnz     short loc_140009D04
0x140009cf8  mov     r8d, gs:1A4h
0x140009d01  mov     [r9], r8d
0x140009d04  mov     r8d, [r9]
0x140009d07  cmp     r8d, [r11+3Ch]
0x140009d0b  jnb     loc_140009E21
0x140009d11  lea     r10, [r8+r8*2]
0x140009d15  mov     rax, rcx
0x140009d18  shl     r10, 6
0x140009d1c  sub     r10, 0FFFFFFFFFFFFFF80h
0x140009d20  add     r10, r11
0x140009d23  lock xadd [r10+80h], rax
0x140009d2c  add     rax, rcx
0x140009d2f  test    sil, sil
0x140009d32  jnz     short loc_140009D73
0x140009d34  cmp     eax, ebp
0x140009d36  jnz     short loc_140009D4B
0x140009d38  mov     rax, rcx
0x140009d3b  lock xadd [r11+40h], rax
0x140009d41  add     rax, rcx
0x140009d44  xor     ecx, ecx
0x140009d46  jmp     loc_140009E2C
0x140009d4b  mov     rcx, rax
0x140009d4e  shr     rcx, 20h
0x140009d52  cmp     ecx, ebp
0x140009d54  jnz     short loc_140009D44
0x140009d56  test    dil, dil
0x140009d59  jz      short loc_140009D44
0x140009d5b  xor     ebx, ebx
0x140009d5d  mov     dword ptr [rsp+20h+arg_10], ebx
0x140009d61  mov     rax, [rsp+20h+arg_10]
0x140009d66  lock xadd [r11+40h], rax
0x140009d6c  add     rax, [rsp+20h+arg_10]
0x140009d71  jmp     short loc_140009D44
0x140009d73  test    eax, eax
0x140009d75  jnz     short loc_140009D85
0x140009d77  mov     rax, rcx
0x140009d7a  lock xadd [r11+40h], rax
0x140009d80  add     rax, rcx
0x140009d83  jmp     short loc_140009DB3
0x140009d85  mov     rcx, rax
0x140009d88  shr     rcx, 20h
0x140009d8c  test    ecx, ecx
0x140009d8e  jnz     short loc_140009DB3
0x140009d90  test    dil, dil
0x140009d93  jz      short loc_140009DB3
0x140009d95  xor     ebx, ebx
0x140009d97  mov     dword ptr [rsp+20h+arg_10+4], 0FFFFFFFFh
0x140009d9f  mov     dword ptr [rsp+20h+arg_10], ebx
0x140009da3  mov     rax, [rsp+20h+arg_10]
0x140009da8  lock xadd [r11+40h], rax
0x140009dae  add     rax, [rsp+20h+arg_10]
0x140009db3  test    eax, eax
0x140009db5  jnz     short loc_140009DBB
0x140009db7  mov     [r11+48h], rdx
0x140009dbb  test    dil, dil
0x140009dbe  jz      short loc_140009E21
0x140009dc0  mov     rcx, rax
0x140009dc3  shr     rcx, 20h
0x140009dc7  test    ecx, ecx
0x140009dc9  jnz     short loc_140009E21
0x140009dcb  mov     [r11+50h], rdx
0x140009dcf  xor     ecx, ecx
0x140009dd1  jmp     loc_140009EB4
0x140009dd6  test    sil, sil
0x140009dd9  jz      short loc_140009DF8
0x140009ddb  mov     eax, [r11+40h]
0x140009ddf  cmp     eax, ebp
0x140009de1  jnz     short loc_140009DE7
0x140009de3  mov     [r11+48h], rdx
0x140009de7  test    dil, dil
0x140009dea  jz      short loc_140009DF8
0x140009dec  mov     eax, [r11+44h]
0x140009df0  cmp     eax, ebp
0x140009df2  jnz     short loc_140009DF8
0x140009df4  mov     [r11+50h], rdx
0x140009df8  mov     rax, rcx
0x140009dfb  lock xadd [r11+40h], rax
0x140009e01  add     rax, rcx
0x140009e04  mov     ecx, gs:1A4h
0x140009e0c  cmp     ecx, [r11+3Ch]
0x140009e10  jnb     short loc_140009E21
0x140009e12  lea     r10, [rcx+rcx*2]
0x140009e16  shl     r10, 6
0x140009e1a  sub     r10, 0FFFFFFFFFFFFFF80h
0x140009e1e  add     r10, r11
0x140009e21  xor     ecx, ecx
0x140009e23  test    sil, sil
0x140009e26  jnz     loc_140009EB4
0x140009e2c  cmp     eax, ebp
0x140009e2e  jnz     short loc_140009E34
0x140009e30  cmp     ebx, ebp
0x140009e32  jz      short loc_140009E45
0x140009e34  test    dil, dil
0x140009e37  jz      short loc_140009EB4
0x140009e39  mov     r8, rax
0x140009e3c  shr     r8, 20h
0x140009e40  cmp     r8d, ebp
0x140009e43  jnz     short loc_140009EB4
0x140009e45  test    r10, r10
0x140009e48  jz      short loc_140009E99
0x140009e4a  cmp     eax, ebp
0x140009e4c  jnz     short loc_140009E6D
0x140009e4e  cmp     ebx, ebp
0x140009e50  jnz     short loc_140009E6D
0x140009e52  mov     r8, [r11+48h]
0x140009e56  cmp     rdx, r8
0x140009e59  jle     short loc_140009E6D
0x140009e5b  mov     r9, [r10+28h]
0x140009e5f  mov     r8, [r11+48h]
0x140009e63  sub     r9, r8
0x140009e66  add     r9, rdx
0x140009e69  mov     [r10+28h], r9
0x140009e6d  test    dil, dil
0x140009e70  jz      short loc_140009E99
0x140009e72  mov     r8, rax
0x140009e75  shr     r8, 20h
0x140009e79  cmp     r8d, ebp
0x140009e7c  jnz     short loc_140009E99
0x140009e7e  mov     r8, [r11+50h]
0x140009e82  cmp     rdx, r8
0x140009e85  jle     short loc_140009E99
0x140009e87  mov     r9, [r10+68h]
0x140009e8b  mov     r8, [r11+50h]
0x140009e8f  sub     r9, r8
0x140009e92  add     r9, rdx
0x140009e95  mov     [r10+68h], r9
0x140009e99  cmp     eax, ebp
0x140009e9b  jnz     short loc_140009EB4
0x140009e9d  cmp     ebx, ebp
0x140009e9f  jnz     short loc_140009EB4
0x140009ea1  mov     rax, [r11+48h]
0x140009ea5  cmp     rdx, rax
0x140009ea8  jle     short loc_140009EB4
0x140009eaa  mov     rax, [r11+48h]
0x140009eae  mov     rcx, rdx
0x140009eb1  sub     rcx, rax
0x140009eb4  mov     rax, rcx
0x140009eb7  pop     rdi
0x140009eb8  pop     rsi
0x140009eb9  pop     rbp
0x140009eba  pop     rbx
0x140009ebb  retn
```
