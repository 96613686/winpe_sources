# CopyNameResolutionInfo

- ea: `0x180001434`
- end: `0x18000154d`
- name: `CopyNameResolutionInfo`
- size: `281`
- prototype: `void __fastcall(unsigned __int16, unsigned __int16, __int64 *, __int64, unsigned __int16, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001560`

## callees

- `0x180001434`

## import_xrefs

- `ntdll!wcscpy_s` at `0x180001523`
- `ntdll!wcscpy_s` at `0x180001523`

## pseudocode

```c
void __fastcall CopyNameResolutionInfo(
        unsigned __int16 a1,
        unsigned __int16 a2,
        __int64 *a3,
        __int64 a4,
        unsigned __int16 a5,
        unsigned __int16 *a6)
{
  __int64 v7; // rax
  _DWORD *v8; // rdx
  _OWORD *v9; // r9
  int v10; // eax
  unsigned __int16 v11; // si
  wchar_t *v12; // rbp
  unsigned __int64 v13; // rbx

  if ( a3 )
  {
    v7 = a6[16];
    a6[1] = a2;
    v8 = (_DWORD *)((char *)a6 + v7 + 40);
    a6[2] = 0;
    *a6 = a1;
    v9 = &v8[a1];
    while ( *((_WORD *)a3 + 8) != 1 )
    {
      if ( *((_WORD *)a3 + 8) == 28 )
      {
        if ( !*((_WORD *)a3 + 16)
          && !*((_WORD *)a3 + 17)
          && !*((_WORD *)a3 + 18)
          && !*((_WORD *)a3 + 19)
          && !*((_WORD *)a3 + 20)
          && *((_WORD *)a3 + 21) == 0xFFFF )
        {
          v10 = *((_DWORD *)a3 + 11);
LABEL_14:
          *v8++ = v10;
          goto LABEL_15;
        }
        *v9++ = *((_OWORD *)a3 + 2);
      }
LABEL_15:
      a3 = (__int64 *)*a3;
      if ( !a3 )
        return;
    }
    v10 = *((_DWORD *)a3 + 8);
    goto LABEL_14;
  }
  if ( a4 )
  {
    v11 = 0;
    v12 = (unsigned __int16 *)((char *)a6 + a6[16] + 40);
    a6[2] = a5;
    for ( *(_DWORD *)a6 = 0; v11 < a5; v12 += v13 + 1 )
    {
      v13 = (unsigned __int64)*(unsigned __int16 *)(a4 + 16LL * v11) >> 1;
      wcscpy_s(v12, v13 + 1, *(const wchar_t **)(a4 + 16LL * v11++ + 8));
    }
  }
}

```

## disassembly

```asm
0x180001434  push    rbx
0x180001436  push    rbp
0x180001437  push    rsi
0x180001438  push    rdi
0x180001439  push    r14
0x18000143b  sub     rsp, 20h
0x18000143f  xor     r10d, r10d
0x180001442  mov     rdi, r9
0x180001445  test    r8, r8
0x180001448  jz      loc_1800014DC
0x18000144e  mov     r9, [rsp+48h+arg_28]
0x180001453  movzx   eax, word ptr [r9+20h]
0x180001458  mov     [r9+2], dx
0x18000145d  lea     rdx, [r9+28h]
0x180001461  add     rdx, rax
0x180001464  mov     [r9+4], r10w
0x180001469  movzx   eax, cx
0x18000146c  mov     [r9], cx
0x180001470  lea     r9, [rdx+rax*4]
0x180001474  movzx   ecx, word ptr [r8+10h]
0x180001479  sub     ecx, 1
0x18000147c  jz      short loc_1800014C8
0x18000147e  cmp     ecx, 1Bh
0x180001481  jnz     short loc_1800014D2
0x180001483  cmp     [r8+20h], r10w
0x180001488  jnz     short loc_1800014B8
0x18000148a  cmp     [r8+22h], r10w
0x18000148f  jnz     short loc_1800014B8
0x180001491  cmp     [r8+24h], r10w
0x180001496  jnz     short loc_1800014B8
0x180001498  cmp     [r8+26h], r10w
0x18000149d  jnz     short loc_1800014B8
0x18000149f  cmp     [r8+28h], r10w
0x1800014a4  jnz     short loc_1800014B8
0x1800014a6  mov     eax, 0FFFFh
0x1800014ab  cmp     [r8+2Ah], ax
0x1800014b0  jnz     short loc_1800014B8
0x1800014b2  mov     eax, [r8+2Ch]
0x1800014b6  jmp     short loc_1800014CC
0x1800014b8  movups  xmm0, xmmword ptr [r8+20h]
0x1800014bd  movdqu  xmmword ptr [r9], xmm0
0x1800014c2  add     r9, 10h
0x1800014c6  jmp     short loc_1800014D2
0x1800014c8  mov     eax, [r8+20h]
0x1800014cc  mov     [rdx], eax
0x1800014ce  add     rdx, 4
0x1800014d2  mov     r8, [r8]
0x1800014d5  test    r8, r8
0x1800014d8  jnz     short loc_180001474
0x1800014da  jmp     short loc_180001541
0x1800014dc  test    rdi, rdi
0x1800014df  jz      short loc_180001541
0x1800014e1  mov     rcx, [rsp+48h+arg_28]
0x1800014e6  mov     esi, r10d
0x1800014e9  movzx   r14d, [rsp+48h+arg_20]
0x1800014ef  movzx   eax, word ptr [rcx+20h]
0x1800014f3  lea     rbp, [rcx+28h]
0x1800014f7  add     rbp, rax
0x1800014fa  mov     [rcx+4], r14w
0x1800014ff  mov     [rcx], r10d
0x180001502  cmp     r10w, r14w
0x180001506  jnb     short loc_180001541
0x180001508  movzx   r8d, si
0x18000150c  mov     rcx, rbp; Destination
0x18000150f  add     r8, r8
0x180001512  movzx   ebx, word ptr [rdi+r8*8]
0x180001517  mov     r8, [rdi+r8*8+8]; Source
0x18000151c  shr     rbx, 1
0x18000151f  lea     rdx, [rbx+1]; SizeInWords
0x180001523  call    cs:__imp_wcscpy_s
0x18000152a  nop     dword ptr [rax+rax+00h]
0x18000152f  lea     rbp, [rbp+rbx*2+0]
0x180001534  inc     si
0x180001537  add     rbp, 2
0x18000153b  cmp     si, r14w
0x18000153f  jb      short loc_180001508
0x180001541  add     rsp, 20h
0x180001545  pop     r14
0x180001547  pop     rdi
0x180001548  pop     rsi
0x180001549  pop     rbp
0x18000154a  pop     rbx
0x18000154b  retn
```
