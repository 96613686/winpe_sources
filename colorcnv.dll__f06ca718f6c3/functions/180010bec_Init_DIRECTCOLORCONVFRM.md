# Init(DIRECTCOLORCONVFRM *)

- ea: `0x180010bec`
- end: `0x180010db2`
- name: `?Init@@YAXPEAUDIRECTCOLORCONVFRM@@@Z`
- size: `454`
- prototype: `void __fastcall(struct DIRECTCOLORCONVFRM *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180014d84`
- `0x18001a064`
- `0x18001fae0`

## callees

- `0x18000940c`
- `0x180014374`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180010d54`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180010d54`

## pseudocode

```c
void __fastcall Init(struct DIRECTCOLORCONVFRM *a1)
{
  int *v1; // rsi
  int *v2; // rdi
  int *v3; // rbx

  v1 = (int *)((char *)a1 + 15400);
  *(_QWORD *)a1 = 0;
  v2 = (int *)((char *)a1 + 15404);
  *((_QWORD *)a1 + 1) = 0;
  v3 = (int *)((char *)a1 + 15408);
  *((_QWORD *)a1 + 2) = 0;
  *((_QWORD *)a1 + 4) = 0;
  *((_DWORD *)a1 + 6) = 2;
  *((_DWORD *)a1 + 7) = 2;
  *((_DWORD *)a1 + 3637) = 1;
  *((_QWORD *)a1 + 1819) = 1;
  *((_QWORD *)a1 + 5) = 0;
  *((_QWORD *)a1 + 6) = 0;
  *((_QWORD *)a1 + 7) = 0;
  *((_QWORD *)a1 + 8) = 0;
  *((_QWORD *)a1 + 10) = 0;
  *((_QWORD *)a1 + 11) = 0;
  *((_QWORD *)a1 + 12) = 0;
  *(_QWORD *)((char *)a1 + 124) = 0;
  *(_QWORD *)((char *)a1 + 132) = 0;
  *(_QWORD *)((char *)a1 + 140) = 0;
  *(_QWORD *)((char *)a1 + 148) = 0;
  *(_QWORD *)((char *)a1 + 156) = 0;
  *((_QWORD *)a1 + 1817) = 0;
  *((_DWORD *)a1 + 3636) = 0;
  *((_QWORD *)a1 + 1820) = 0;
  *((_QWORD *)a1 + 1821) = 0;
  *((_QWORD *)a1 + 1822) = 0;
  *((_QWORD *)a1 + 1823) = 0;
  *((_QWORD *)a1 + 1824) = 0;
  *((_QWORD *)a1 + 1825) = 0;
  *((_QWORD *)a1 + 1826) = 0;
  *((_QWORD *)a1 + 1827) = 0;
  *((_QWORD *)a1 + 1828) = 0;
  *((_DWORD *)a1 + 3658) = 0;
  *((_DWORD *)a1 + 3659) = 0;
  *((_DWORD *)a1 + 3660) = 1;
  *((_QWORD *)a1 + 1910) = 0;
  *((_QWORD *)a1 + 1911) = 0;
  *((_QWORD *)a1 + 1912) = 0;
  *((_QWORD *)a1 + 1913) = 0;
  *((_QWORD *)a1 + 1914) = 0;
  *((_QWORD *)a1 + 1915) = 0;
  *((_QWORD *)a1 + 1916) = 0;
  *((_QWORD *)a1 + 1917) = 0;
  *((_QWORD *)a1 + 1918) = 0;
  *((_QWORD *)a1 + 1927) = 0;
  *((_QWORD *)a1 + 1928) = 0;
  *((_QWORD *)a1 + 1929) = 0;
  *((_QWORD *)a1 + 1930) = 0;
  *((_QWORD *)a1 + 1919) = 1;
  *((_QWORD *)a1 + 14) = 0;
  *((_DWORD *)a1 + 30) = 0;
  *((_DWORD *)a1 + 3850) = -1;
  *((_DWORD *)a1 + 3851) = -1;
  *((_DWORD *)a1 + 3852) = -1;
  InitializeCriticalSection((LPCRITICAL_SECTION)a1 + 384);
  readRegKey(v1, v2, v3);
  *((_DWORD *)a1 + 3639) = VerticalFlipPackedYUVRegistryKeySet();
  *((_DWORD *)a1 + 3839) = 1;
  *((_DWORD *)a1 + 3807) = 0;
  *((_DWORD *)a1 + 3678) = 0;
  *((_QWORD *)a1 + 1905) = 0;
  *((_QWORD *)a1 + 1904) = 0;
  *((_QWORD *)a1 + 1907) = 0;
  *((_QWORD *)a1 + 1906) = 0;
}

```

## disassembly

```asm
0x180010bec  push    rbx
0x180010bee  push    rbp
0x180010bef  push    rsi
0x180010bf0  push    rdi
0x180010bf1  push    r14
0x180010bf3  push    r15
0x180010bf5  sub     rsp, 28h
0x180010bf9  xor     r15d, r15d
0x180010bfc  lea     rsi, [rcx+3C28h]
0x180010c03  mov     [rcx], r15
0x180010c06  lea     rdi, [rcx+3C2Ch]
0x180010c0d  mov     [rcx+8], r15
0x180010c11  lea     rbx, [rcx+3C30h]
0x180010c18  mov     [rcx+10h], r15
0x180010c1c  mov     r14, rcx
0x180010c1f  lea     eax, [r15+2]
0x180010c23  mov     [rcx+20h], r15
0x180010c27  lea     ebp, [rax-1]
0x180010c2a  mov     [rcx+18h], eax
0x180010c2d  mov     [rcx+1Ch], eax
0x180010c30  or      eax, 0FFFFFFFFh
0x180010c33  mov     [rcx+38D4h], ebp
0x180010c39  mov     [rcx+38D8h], rbp
0x180010c40  mov     [rcx+28h], r15
0x180010c44  mov     [rcx+30h], r15
0x180010c48  mov     [rcx+38h], r15
0x180010c4c  mov     [rcx+40h], r15
0x180010c50  mov     [rcx+50h], r15
0x180010c54  mov     [rcx+58h], r15
0x180010c58  mov     [rcx+60h], r15
0x180010c5c  mov     [rcx+7Ch], r15
0x180010c60  mov     [rcx+84h], r15
0x180010c67  mov     [rcx+8Ch], r15
0x180010c6e  mov     [rcx+94h], r15
0x180010c75  mov     [rcx+9Ch], r15
0x180010c7c  mov     [rcx+38C8h], r15
0x180010c83  mov     [rcx+38D0h], r15d
0x180010c8a  mov     [rcx+38E0h], r15
0x180010c91  mov     [rcx+38E8h], r15
0x180010c98  mov     [rcx+38F0h], r15
0x180010c9f  mov     [rcx+38F8h], r15
0x180010ca6  mov     [rcx+3900h], r15
0x180010cad  mov     [rcx+3908h], r15
0x180010cb4  mov     [rcx+3910h], r15
0x180010cbb  mov     [rcx+3918h], r15
0x180010cc2  mov     [rcx+3920h], r15
0x180010cc9  mov     [rcx+3928h], r15d
0x180010cd0  mov     [rcx+392Ch], r15d
0x180010cd7  mov     [rcx+3930h], ebp
0x180010cdd  mov     [rcx+3BB0h], r15
0x180010ce4  mov     [rcx+3BB8h], r15
0x180010ceb  mov     [rcx+3BC0h], r15
0x180010cf2  mov     [rcx+3BC8h], r15
0x180010cf9  mov     [rcx+3BD0h], r15
0x180010d00  mov     [rcx+3BD8h], r15
0x180010d07  mov     [rcx+3BE0h], r15
0x180010d0e  mov     [rcx+3BE8h], r15
0x180010d15  mov     [rcx+3BF0h], r15
0x180010d1c  mov     [rcx+3C38h], r15
0x180010d23  mov     [rcx+3C40h], r15
0x180010d2a  mov     [rcx+3C48h], r15
0x180010d31  mov     [rcx+3C50h], r15
0x180010d38  mov     [rcx+3BF8h], rbp
0x180010d3f  mov     [rcx+70h], r15
0x180010d43  mov     [rcx+78h], r15d
0x180010d47  add     rcx, 3C00h; lpCriticalSection
0x180010d4e  mov     [rsi], eax
0x180010d50  mov     [rdi], eax
0x180010d52  mov     [rbx], eax
0x180010d54  call    cs:__imp_InitializeCriticalSection
0x180010d5a  mov     r8, rbx; int *
0x180010d5d  mov     rdx, rdi; int *
0x180010d60  mov     rcx, rsi; int *
0x180010d63  call    ?readRegKey@@YAHPEAJ00@Z; readRegKey(long *,long *,long *)
0x180010d68  call    VerticalFlipPackedYUVRegistryKeySet
0x180010d6d  mov     [r14+38DCh], eax
0x180010d74  mov     [r14+3BFCh], ebp
0x180010d7b  mov     [r14+3B7Ch], r15d
0x180010d82  mov     [r14+3978h], r15d
0x180010d89  mov     [r14+3B88h], r15
0x180010d90  mov     [r14+3B80h], r15
0x180010d97  mov     [r14+3B98h], r15
0x180010d9e  mov     [r14+3B90h], r15
0x180010da5  add     rsp, 28h
0x180010da9  pop     r15
0x180010dab  pop     r14
0x180010dad  pop     rdi
0x180010dae  pop     rsi
0x180010daf  pop     rbp
0x180010db0  pop     rbx
0x180010db1  retn
```
