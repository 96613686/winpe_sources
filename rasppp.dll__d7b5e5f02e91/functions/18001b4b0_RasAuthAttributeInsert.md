# RasAuthAttributeInsert

- ea: `0x18001b4b0`
- end: `0x18001b6ab`
- name: `RasAuthAttributeInsert`
- size: `507`
- prototype: `DWORD __fastcall(unsigned int, __int64, int, __int64, size_t Size, void *Src)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x1800023c0`
- `0x18000a9f0`
- `0x18001063c`
- `0x180011778`
- `0x180012e38`
- `0x18001ab0c`
- `0x18001aba0`
- `0x1800281ac`
- `0x18002881c`
- `0x18002aca4`

## callees

- `0x18001b4b0`
- `0x180033a80`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b661`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b661`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b677`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b677`

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
0x18001b4b0  push    rbx
0x18001b4b2  push    rbp
0x18001b4b3  push    rdi
0x18001b4b4  push    r14
0x18001b4b6  sub     rsp, 28h
0x18001b4ba  mov     edi, ecx
0x18001b4bc  mov     ebx, r8d
0x18001b4bf  add     rdi, rdi
0x18001b4c2  mov     rbp, rdx
0x18001b4c5  cmp     dword ptr [rdx+rdi*8], 0
0x18001b4c9  jnz     short loc_18001B4D5
0x18001b4cb  mov     eax, 8
0x18001b4d0  jmp     loc_18001B5FF
0x18001b4d5  mov     r14d, dword ptr [rsp+48h+Size]
0x18001b4da  cmp     ebx, 3Ch ; '<'
0x18001b4dd  jg      loc_18001B598
0x18001b4e3  jz      loc_18001B642
0x18001b4e9  cmp     ebx, 1Ah
0x18001b4ec  jg      short loc_18001B549
0x18001b4ee  jz      loc_18001B642
0x18001b4f4  cmp     ebx, 13h
0x18001b4f7  jg      short loc_18001B52D
0x18001b4f9  jz      loc_18001B642
0x18001b4ff  mov     ecx, ebx
0x18001b501  sub     ecx, 1
0x18001b504  jz      loc_18001B642
0x18001b50a  sub     ecx, 1
0x18001b50d  jz      loc_18001B642
0x18001b513  sub     ecx, 1
0x18001b516  jz      loc_18001B642
0x18001b51c  sub     ecx, 8
0x18001b51f  jz      loc_18001B642
0x18001b525  cmp     ecx, 7
0x18001b528  jmp     loc_18001B5E8
0x18001b52d  mov     ecx, ebx
0x18001b52f  sub     ecx, 14h
0x18001b532  jz      loc_18001B642
0x18001b538  sub     ecx, 2
0x18001b53b  jz      loc_18001B642
0x18001b541  sub     ecx, 2
0x18001b544  jmp     loc_18001B5CA
0x18001b549  mov     ecx, ebx
0x18001b54b  sub     ecx, 1Eh
0x18001b54e  jz      loc_18001B642
0x18001b554  sub     ecx, 1
0x18001b557  jz      loc_18001B642
0x18001b55d  sub     ecx, 1
0x18001b560  jz      loc_18001B642
0x18001b566  sub     ecx, 1
0x18001b569  jz      loc_18001B642
0x18001b56f  sub     ecx, 1
0x18001b572  jz      loc_18001B642
0x18001b578  sub     ecx, 1
0x18001b57b  jz      loc_18001B642
0x18001b581  sub     ecx, 1
0x18001b584  jz      loc_18001B642
0x18001b58a  sub     ecx, 8
0x18001b58d  jz      loc_18001B642
0x18001b593  cmp     ecx, 6
0x18001b596  jmp     short loc_18001B5E8
0x18001b598  mov     eax, 1FA3h
0x18001b59d  cmp     ebx, eax
0x18001b59f  jg      short loc_18001B60A
0x18001b5a1  jz      short loc_18001B5EA
0x18001b5a3  cmp     ebx, 4Fh ; 'O'
0x18001b5a6  jg      short loc_18001B5D1
0x18001b5a8  jz      loc_18001B642
0x18001b5ae  mov     ecx, ebx
0x18001b5b0  sub     ecx, 3Fh ; '?'
0x18001b5b3  jz      loc_18001B642
0x18001b5b9  sub     ecx, 3
0x18001b5bc  jz      loc_18001B642
0x18001b5c2  sub     ecx, 1
0x18001b5c5  jz      short loc_18001B642
0x18001b5c7  sub     ecx, 0Ah
0x18001b5ca  jz      short loc_18001B642
0x18001b5cc  cmp     ecx, 1
0x18001b5cf  jmp     short loc_18001B5E8
0x18001b5d1  mov     ecx, ebx
0x18001b5d3  sub     ecx, 50h ; 'P'
0x18001b5d6  jz      short loc_18001B642
0x18001b5d8  sub     ecx, 10h
0x18001b5db  jz      short loc_18001B642
0x18001b5dd  sub     ecx, 1
0x18001b5e0  jz      short loc_18001B642
0x18001b5e2  cmp     ecx, 1F40h
0x18001b5e8  jz      short loc_18001B642
0x18001b5ea  mov     rax, [rsp+48h+Src]
0x18001b5ef  mov     [rdx+rdi*8+8], rax
0x18001b5f4  mov     [rbp+rdi*8+4], r14d
0x18001b5f9  xor     eax, eax
0x18001b5fb  mov     [rbp+rdi*8+0], ebx
0x18001b5ff  add     rsp, 28h
0x18001b603  pop     r14
0x18001b605  pop     rdi
0x18001b606  pop     rbp
0x18001b607  pop     rbx
0x18001b608  retn
0x18001b60a  mov     ecx, ebx
0x18001b60c  sub     ecx, 1FA4h
0x18001b612  jz      short loc_18001B5EA
0x18001b614  sub     ecx, 2
0x18001b617  jz      short loc_18001B642
0x18001b619  sub     ecx, 1
0x18001b61c  jz      short loc_18001B5EA
0x18001b61e  sub     ecx, 93h
0x18001b624  jz      short loc_18001B642
0x18001b626  sub     ecx, 2EEh
0x18001b62c  jz      short loc_18001B642
0x18001b62e  sub     ecx, 1
0x18001b631  jz      short loc_18001B642
0x18001b633  sub     ecx, 1
0x18001b636  jz      short loc_18001B642
0x18001b638  sub     ecx, 1
0x18001b63b  jz      short loc_18001B642
0x18001b63d  cmp     ecx, 1
0x18001b640  jnz     short loc_18001B5EA
0x18001b642  cmp     [rsp+48h+Src], 0
0x18001b648  jz      short loc_18001B69D
0x18001b64a  lea     eax, [r14+1]
0x18001b64e  cmp     eax, r14d
0x18001b651  jnb     short loc_18001B65A
0x18001b653  mov     eax, 216h
0x18001b658  jmp     short loc_18001B5FF
0x18001b65a  mov     edx, eax; uBytes
0x18001b65c  mov     ecx, 40h ; '@'; uFlags
0x18001b661  call    cs:__imp_LocalAlloc
0x18001b668  nop     dword ptr [rax+rax+00h]
0x18001b66d  mov     [rbp+rdi*8+8], rax
0x18001b672  test    rax, rax
0x18001b675  jnz     short loc_18001B688
0x18001b677  call    cs:__imp_GetLastError
0x18001b67e  nop     dword ptr [rax+rax+00h]
0x18001b683  jmp     loc_18001B5FF
0x18001b688  mov     rdx, [rsp+48h+Src]; Src
0x18001b68d  mov     r8, r14; Size
0x18001b690  mov     rcx, rax; void *
0x18001b693  call    memcpy_0
0x18001b698  jmp     loc_18001B5F4
0x18001b69d  mov     qword ptr [rdx+rdi*8+8], 0
0x18001b6a6  jmp     loc_18001B5F4
```
