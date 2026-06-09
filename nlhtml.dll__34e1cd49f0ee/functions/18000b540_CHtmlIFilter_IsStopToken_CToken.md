# CHtmlIFilter::IsStopToken(CToken &)

- ea: `0x18000b540`
- end: `0x18000b685`
- name: `?IsStopToken@CHtmlIFilter@@QEAAHAEAVCToken@@@Z`
- size: `325`
- prototype: `__int64 __fastcall(CHtmlIFilter *__hidden this, struct CToken *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b110`

## callees

- `0x18000b540`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000b5ba`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000b5ba`

## pseudocode

```c
__int64 __fastcall CHtmlIFilter::IsStopToken(CHtmlIFilter *this, struct CToken *a2)
{
  __int64 v3; // rbx
  unsigned int v4; // esi
  _QWORD *v5; // rdx
  __int64 v6; // r14
  _DWORD *v7; // r15
  __int64 v9; // rax

  switch ( *(_DWORD *)a2 )
  {
    case 2:
    case 4:
    case 0xA:
    case 0x14:
    case 0x15:
    case 0x16:
    case 0x17:
    case 0x18:
    case 0x19:
    case 0x1A:
    case 0x1B:
    case 0x1C:
    case 0x1D:
    case 0x1F:
    case 0x20:
    case 0x21:
    case 0x22:
    case 0x23:
    case 0x3D:
    case 0x3E:
      return 1;
    default:
      v3 = *((_QWORD *)a2 + 1);
      if ( !v3 || !*(_DWORD *)(v3 + 172) )
        return 0;
      if ( *((_DWORD *)this + 16) )
        return 1;
      v4 = 0;
      break;
  }
  while ( 1 )
  {
    if ( v4 >= *((_DWORD *)this + 17) )
      return 0;
    v5 = *(_QWORD **)(v3 + 40);
    if ( v5 )
    {
      v6 = *((_QWORD *)this + 9) + 32LL * v4;
      if ( *(_DWORD *)(v6 + 16) )
      {
        v7 = (_DWORD *)(v6 + 24);
      }
      else
      {
        if ( *(_DWORD *)(v3 + 32) )
          goto LABEL_23;
        if ( !*(_QWORD *)(v3 + 64) )
          goto LABEL_23;
        v7 = (_DWORD *)(v6 + 24);
        if ( (unsigned int)_o__wcsicmp(*(_QWORD *)(v6 + 24)) )
          goto LABEL_23;
        v5 = *(_QWORD **)(v3 + 40);
      }
      if ( *(_DWORD *)(v6 + 16) != 1 || *(_DWORD *)(v3 + 32) == 1 && *(_DWORD *)(v3 + 48) == *v7 )
      {
        v9 = *(_QWORD *)v6 - *v5;
        if ( *(_QWORD *)v6 == *v5 )
          v9 = *(_QWORD *)(v6 + 8) - v5[1];
        if ( !v9 )
          return 1;
      }
    }
LABEL_23:
    ++v4;
  }
}

```

## disassembly

```asm
0x18000b540  push    rbx
0x18000b542  push    rsi
0x18000b543  push    rdi
0x18000b544  push    r14
0x18000b546  push    r15
0x18000b548  sub     rsp, 20h
0x18000b54c  mov     eax, [rdx]
0x18000b54e  mov     rdi, rcx
0x18000b551  add     eax, 0FFFFFFFEh; switch 61 cases
0x18000b554  cmp     eax, 3Ch
0x18000b557  jbe     loc_18000B5E9
0x18000b55d  mov     rbx, [rdx+8]; jumptable 000000018000B605 default case, cases 3,5-9,11-19,30,36-60
0x18000b561  test    rbx, rbx
0x18000b564  jz      short loc_18000B5CA
0x18000b566  cmp     dword ptr [rbx+0ACh], 0
0x18000b56d  jz      short loc_18000B5CA
0x18000b56f  cmp     dword ptr [rdi+40h], 0
0x18000b573  jnz     short loc_18000B5D8; jumptable 000000018000B605 cases 2,4,10,20-29,31-35,61,62
0x18000b575  xor     esi, esi
0x18000b577  cmp     esi, [rdi+44h]
0x18000b57a  jnb     short loc_18000B5CA
0x18000b57c  mov     rdx, [rbx+28h]
0x18000b580  test    rdx, rdx
0x18000b583  jz      loc_18000B636
0x18000b589  mov     r14d, esi
0x18000b58c  shl     r14, 5
0x18000b590  add     r14, [rdi+48h]
0x18000b594  cmp     dword ptr [r14+10h], 0
0x18000b599  jnz     short loc_18000B608
0x18000b59b  cmp     dword ptr [rbx+20h], 0
0x18000b59f  jnz     loc_18000B636
0x18000b5a5  mov     rdx, [rbx+40h]
0x18000b5a9  test    rdx, rdx
0x18000b5ac  jz      loc_18000B636
0x18000b5b2  mov     rcx, [r14+18h]
0x18000b5b6  lea     r15, [r14+18h]
0x18000b5ba  call    cs:__imp__o__wcsicmp
0x18000b5c0  test    eax, eax
0x18000b5c2  jnz     short loc_18000B636
0x18000b5c4  mov     rdx, [rbx+28h]
0x18000b5c8  jmp     short loc_18000B60C
0x18000b5ca  xor     eax, eax
0x18000b5cc  add     rsp, 20h
0x18000b5d0  pop     r15
0x18000b5d2  pop     r14
0x18000b5d4  pop     rdi
0x18000b5d5  pop     rsi
0x18000b5d6  pop     rbx
0x18000b5d7  retn
0x18000b5d8  mov     eax, 1; jumptable 000000018000B605 cases 2,4,10,20-29,31-35,61,62
0x18000b5dd  add     rsp, 20h
0x18000b5e1  pop     r15
0x18000b5e3  pop     r14
0x18000b5e5  pop     rdi
0x18000b5e6  pop     rsi
0x18000b5e7  pop     rbx
0x18000b5e8  retn
0x18000b5e9  lea     rcx, __ImageBase
0x18000b5f0  cdqe
0x18000b5f2  movzx   eax, ds:(byte_18000B648 - 180000000h)[rcx+rax]
0x18000b5fa  mov     r8d, ds:(jpt_18000B605 - 180000000h)[rcx+rax*4]
0x18000b602  add     r8, rcx
0x18000b605  jmp     r8; switch jump
0x18000b608  lea     r15, [r14+18h]
0x18000b60c  cmp     dword ptr [r14+10h], 1
0x18000b611  jnz     short loc_18000B621
0x18000b613  cmp     dword ptr [rbx+20h], 1
0x18000b617  jnz     short loc_18000B636
0x18000b619  mov     eax, [r15]
0x18000b61c  cmp     [rbx+30h], eax
0x18000b61f  jnz     short loc_18000B636
0x18000b621  mov     rax, [r14]
0x18000b624  sub     rax, [rdx]
0x18000b627  jnz     short loc_18000B631
0x18000b629  mov     rax, [r14+8]
0x18000b62d  sub     rax, [rdx+8]
0x18000b631  test    rax, rax
0x18000b634  jz      short loc_18000B5D8; jumptable 000000018000B605 cases 2,4,10,20-29,31-35,61,62
0x18000b636  inc     esi
0x18000b638  jmp     loc_18000B577
```
