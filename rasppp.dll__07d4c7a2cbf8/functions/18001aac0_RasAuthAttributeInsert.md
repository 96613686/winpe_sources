# RasAuthAttributeInsert

- ea: `0x18001aac0`
- end: `0x18001aca4`
- name: `RasAuthAttributeInsert`
- size: `484`
- prototype: `__int64 __fastcall(int, int, int, int, size_t Size, void *Src)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x1800023a8`
- `0x18000a610`
- `0x18001016c`
- `0x1800111d8`
- `0x180012794`
- `0x18001a170`
- `0x18001a200`
- `0x180027340`
- `0x180027964`
- `0x180029d0c`

## callees

- `0x18001aac0`
- `0x180032460`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ac69`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ac69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ac79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ac79`

## pseudocode

```c
DWORD __fastcall RasAuthAttributeInsert(unsigned int a1, __int64 a2, int a3, __int64 a4, size_t Size, void *Src)
{
  __int64 v7; // rdi
  DWORD result; // eax
  bool v10; // zf
  bool v11; // zf
  int v12; // ecx
  HLOCAL v13; // rax

  v7 = 2LL * a1;
  if ( !*(_DWORD *)(a2 + 16LL * a1) )
    return 8;
  if ( a3 > 60 )
  {
    if ( a3 > 8099 )
    {
      if ( a3 == 8100
        || a3 != 8102
        && (a3 == 8103 || a3 != 8250 && a3 != 9000 && a3 != 9001 && a3 != 9002 && (unsigned int)(a3 - 9003) > 1) )
      {
        goto LABEL_41;
      }
      goto LABEL_51;
    }
    if ( a3 == 8099 )
    {
LABEL_41:
      *(_QWORD *)(a2 + 8 * v7 + 8) = Src;
LABEL_42:
      *(_DWORD *)(a2 + 8 * v7 + 4) = Size;
      result = 0;
      *(_DWORD *)(a2 + 8 * v7) = a3;
      return result;
    }
    if ( a3 > 79 )
    {
      if ( a3 == 80 || a3 == 96 || a3 == 97 )
        goto LABEL_51;
      v10 = a3 == 8097;
      goto LABEL_40;
    }
    if ( a3 == 79 || a3 == 63 || a3 == 66 || a3 == 67 )
      goto LABEL_51;
    v12 = a3 - 77;
    v11 = a3 == 77;
  }
  else
  {
    if ( a3 == 60 )
      goto LABEL_51;
    if ( a3 > 26 )
    {
      if ( a3 == 30 || a3 == 31 || a3 == 32 || a3 == 33 || a3 == 34 || a3 == 35 || a3 == 36 || a3 == 44 )
        goto LABEL_51;
      v10 = a3 == 50;
      goto LABEL_40;
    }
    if ( a3 == 26 )
      goto LABEL_51;
    if ( a3 <= 19 )
    {
      if ( a3 == 19 || a3 == 1 || a3 == 2 || a3 == 3 || a3 == 11 )
        goto LABEL_51;
      v10 = a3 == 18;
      goto LABEL_40;
    }
    if ( a3 == 20 || a3 == 22 )
      goto LABEL_51;
    v12 = a3 - 24;
    v11 = a3 == 24;
  }
  if ( v11 )
    goto LABEL_51;
  v10 = v12 == 1;
LABEL_40:
  if ( !v10 )
    goto LABEL_41;
LABEL_51:
  if ( !Src )
  {
    *(_QWORD *)(a2 + 8 * v7 + 8) = 0;
    goto LABEL_42;
  }
  if ( (int)Size + 1 < (unsigned int)Size )
    return 534;
  v13 = LocalAlloc(0x40u, (unsigned int)(Size + 1));
  *(_QWORD *)(a2 + 8 * v7 + 8) = v13;
  if ( v13 )
  {
    memcpy_0(v13, Src, (unsigned int)Size);
    goto LABEL_42;
  }
  return GetLastError();
}

```

## disassembly

```asm
0x18001aac0  push    rbx
0x18001aac2  push    rbp
0x18001aac3  push    rdi
0x18001aac4  push    r14
0x18001aac6  sub     rsp, 28h
0x18001aaca  mov     edi, ecx
0x18001aacc  mov     ebx, r8d
0x18001aacf  add     rdi, rdi
0x18001aad2  mov     rbp, rdx
0x18001aad5  cmp     dword ptr [rdx+rdi*8], 0
0x18001aad9  jnz     short loc_18001AAE5
0x18001aadb  mov     eax, 8
0x18001aae0  jmp     loc_18001AC08
0x18001aae5  mov     r14d, dword ptr [rsp+48h+Size]
0x18001aaea  cmp     ebx, 3Ch ; '<'
0x18001aaed  jg      loc_18001ABA5
0x18001aaf3  jz      loc_18001AC4A
0x18001aaf9  cmp     ebx, 1Ah
0x18001aafc  jg      short loc_18001AB56
0x18001aafe  jz      loc_18001AC4A
0x18001ab04  cmp     ebx, 13h
0x18001ab07  jg      short loc_18001AB3D
0x18001ab09  jz      loc_18001AC4A
0x18001ab0f  mov     ecx, ebx
0x18001ab11  sub     ecx, 1
0x18001ab14  jz      loc_18001AC4A
0x18001ab1a  sub     ecx, 1
0x18001ab1d  jz      loc_18001AC4A
0x18001ab23  sub     ecx, 1
0x18001ab26  jz      loc_18001AC4A
0x18001ab2c  sub     ecx, 8
0x18001ab2f  jz      loc_18001AC4A
0x18001ab35  cmp     ecx, 7
0x18001ab38  jmp     loc_18001ABF1
0x18001ab3d  mov     ecx, ebx
0x18001ab3f  sub     ecx, 14h
0x18001ab42  jz      loc_18001AC4A
0x18001ab48  sub     ecx, 2
0x18001ab4b  jz      loc_18001AC4A
0x18001ab51  sub     ecx, 2
0x18001ab54  jmp     short loc_18001ABD3
0x18001ab56  mov     ecx, ebx
0x18001ab58  sub     ecx, 1Eh
0x18001ab5b  jz      loc_18001AC4A
0x18001ab61  sub     ecx, 1
0x18001ab64  jz      loc_18001AC4A
0x18001ab6a  sub     ecx, 1
0x18001ab6d  jz      loc_18001AC4A
0x18001ab73  sub     ecx, 1
0x18001ab76  jz      loc_18001AC4A
0x18001ab7c  sub     ecx, 1
0x18001ab7f  jz      loc_18001AC4A
0x18001ab85  sub     ecx, 1
0x18001ab88  jz      loc_18001AC4A
0x18001ab8e  sub     ecx, 1
0x18001ab91  jz      loc_18001AC4A
0x18001ab97  sub     ecx, 8
0x18001ab9a  jz      loc_18001AC4A
0x18001aba0  cmp     ecx, 6
0x18001aba3  jmp     short loc_18001ABF1
0x18001aba5  mov     eax, 1FA3h
0x18001abaa  cmp     ebx, eax
0x18001abac  jg      short loc_18001AC12
0x18001abae  jz      short loc_18001ABF3
0x18001abb0  cmp     ebx, 4Fh ; 'O'
0x18001abb3  jg      short loc_18001ABDA
0x18001abb5  jz      loc_18001AC4A
0x18001abbb  mov     ecx, ebx
0x18001abbd  sub     ecx, 3Fh ; '?'
0x18001abc0  jz      loc_18001AC4A
0x18001abc6  sub     ecx, 3
0x18001abc9  jz      short loc_18001AC4A
0x18001abcb  sub     ecx, 1
0x18001abce  jz      short loc_18001AC4A
0x18001abd0  sub     ecx, 0Ah
0x18001abd3  jz      short loc_18001AC4A
0x18001abd5  cmp     ecx, 1
0x18001abd8  jmp     short loc_18001ABF1
0x18001abda  mov     ecx, ebx
0x18001abdc  sub     ecx, 50h ; 'P'
0x18001abdf  jz      short loc_18001AC4A
0x18001abe1  sub     ecx, 10h
0x18001abe4  jz      short loc_18001AC4A
0x18001abe6  sub     ecx, 1
0x18001abe9  jz      short loc_18001AC4A
0x18001abeb  cmp     ecx, 1F40h
0x18001abf1  jz      short loc_18001AC4A
0x18001abf3  mov     rax, [rsp+48h+Src]
0x18001abf8  mov     [rdx+rdi*8+8], rax
0x18001abfd  mov     [rbp+rdi*8+4], r14d
0x18001ac02  xor     eax, eax
0x18001ac04  mov     [rbp+rdi*8+0], ebx
0x18001ac08  add     rsp, 28h
0x18001ac0c  pop     r14
0x18001ac0e  pop     rdi
0x18001ac0f  pop     rbp
0x18001ac10  pop     rbx
0x18001ac11  retn
0x18001ac12  mov     ecx, ebx
0x18001ac14  sub     ecx, 1FA4h
0x18001ac1a  jz      short loc_18001ABF3
0x18001ac1c  sub     ecx, 2
0x18001ac1f  jz      short loc_18001AC4A
0x18001ac21  sub     ecx, 1
0x18001ac24  jz      short loc_18001ABF3
0x18001ac26  sub     ecx, 93h
0x18001ac2c  jz      short loc_18001AC4A
0x18001ac2e  sub     ecx, 2EEh
0x18001ac34  jz      short loc_18001AC4A
0x18001ac36  sub     ecx, 1
0x18001ac39  jz      short loc_18001AC4A
0x18001ac3b  sub     ecx, 1
0x18001ac3e  jz      short loc_18001AC4A
0x18001ac40  sub     ecx, 1
0x18001ac43  jz      short loc_18001AC4A
0x18001ac45  cmp     ecx, 1
0x18001ac48  jnz     short loc_18001ABF3
0x18001ac4a  cmp     [rsp+48h+Src], 0
0x18001ac50  jz      short loc_18001AC96
0x18001ac52  lea     eax, [r14+1]
0x18001ac56  cmp     eax, r14d
0x18001ac59  jnb     short loc_18001AC62
0x18001ac5b  mov     eax, 216h
0x18001ac60  jmp     short loc_18001AC08
0x18001ac62  mov     edx, eax; uBytes
0x18001ac64  mov     ecx, 40h ; '@'; uFlags
0x18001ac69  call    cs:__imp_LocalAlloc
0x18001ac6f  mov     [rbp+rdi*8+8], rax
0x18001ac74  test    rax, rax
0x18001ac77  jnz     short loc_18001AC81
0x18001ac79  call    cs:__imp_GetLastError
0x18001ac7f  jmp     short loc_18001AC08
0x18001ac81  mov     rdx, [rsp+48h+Src]; Src
0x18001ac86  mov     r8, r14; Size
0x18001ac89  mov     rcx, rax; void *
0x18001ac8c  call    memcpy_0
0x18001ac91  jmp     loc_18001ABFD
0x18001ac96  mov     qword ptr [rdx+rdi*8+8], 0
0x18001ac9f  jmp     loc_18001ABFD
```
