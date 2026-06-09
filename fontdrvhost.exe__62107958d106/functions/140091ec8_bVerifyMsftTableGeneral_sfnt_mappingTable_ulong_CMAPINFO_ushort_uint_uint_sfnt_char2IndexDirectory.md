# bVerifyMsftTableGeneral(sfnt_mappingTable *,ulong *,_CMAPINFO *,ushort,uint,uint,sfnt_char2IndexDirectory *)

- ea: `0x140091ec8`
- end: `0x140091fd5`
- name: `?bVerifyMsftTableGeneral@@YAHPEAUsfnt_mappingTable@@PEAKPEAU_CMAPINFO@@GIIPEAUsfnt_char2IndexDirectory@@@Z`
- size: `269`
- prototype: `__int64 __fastcall(struct sfnt_mappingTable *, unsigned int *, struct _CMAPINFO *, unsigned __int16, unsigned int, unsigned int, struct sfnt_char2IndexDirectory *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140009224`

## callees

- `0x140046d40`
- `0x140091ec8`

## pseudocode

```c
_BOOL8 __fastcall bVerifyMsftTableGeneral(
        struct sfnt_mappingTable *a1,
        unsigned int *a2,
        struct _CMAPINFO *a3,
        __int16 a4,
        unsigned int a5,
        unsigned int a6,
        struct sfnt_char2IndexDirectory *a7)
{
  unsigned __int16 *v10; // rdx
  __int64 v11; // rax
  unsigned __int16 v12; // cx
  unsigned __int16 *v13; // r11
  unsigned int v14; // r10d
  unsigned __int16 *v15; // rbx
  unsigned __int16 v16; // r9
  unsigned __int16 v17; // r8

  if ( (unsigned __int16)(a4 - 2) <= 3u )
  {
    if ( (unsigned int)IsValidFormat4TableSize(a1, a7, a6, a5) )
    {
      v10 = (unsigned __int16 *)((char *)a1 + 14);
      v11 = (unsigned __int16)(*((unsigned __int8 *)a1 + 6) << 7) | (unsigned __int8)(*((_BYTE *)a1 + 7) >> 1);
      if ( *((_WORD *)a1 + v11 + 6) == 0xFFFF )
      {
        v12 = 0;
        *a2 = 6;
        v13 = &v10[v11];
        *(_QWORD *)a3 = 0;
        v14 = 0;
        *((_DWORD *)a3 + 3) = 0;
        v15 = v13 + 1;
        if ( v10 >= v13 )
          return 1;
        while ( 1 )
        {
          v16 = _byteswap_ushort(*v15);
          v17 = _byteswap_ushort(*v10);
          if ( v17 < v16 || v12 > v16 || v17 == 0xFFFF && v10 < v13 - 1 )
            break;
          ++v15;
          ++v10;
          v14 += v17 - v16 + 1;
          v12 = v17;
          if ( v10 >= v13 )
            return v14 <= 0xFFFF;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140091ec8  push    rbx
0x140091eca  push    rsi
0x140091ecb  push    rdi
0x140091ecc  push    r14
0x140091ece  push    r15
0x140091ed0  sub     rsp, 20h
0x140091ed4  mov     r15d, 2
0x140091eda  mov     rdi, r8
0x140091edd  sub     r9w, r15w
0x140091ee1  mov     rsi, rdx
0x140091ee4  mov     rbx, rcx
0x140091ee7  cmp     r9w, 3
0x140091eec  ja      loc_140091FC7
0x140091ef2  mov     r9d, [rsp+48h+arg_20]; unsigned int
0x140091ef7  mov     r8d, [rsp+48h+arg_28]; unsigned int
0x140091efc  mov     rdx, [rsp+48h+arg_30]; struct sfnt_char2IndexDirectory *
0x140091f04  call    ?IsValidFormat4TableSize@@YAHPEAUsfnt_mappingTable@@PEAUsfnt_char2IndexDirectory@@II@Z; IsValidFormat4TableSize(sfnt_mappingTable *,sfnt_char2IndexDirectory *,uint,uint)
0x140091f09  test    eax, eax
0x140091f0b  jz      loc_140091FC7
0x140091f11  mov     al, [rbx+7]
0x140091f14  lea     rdx, [rbx+0Eh]
0x140091f18  shr     al, 1
0x140091f1a  mov     r14d, 0FFFFh
0x140091f20  movzx   ecx, al
0x140091f23  movzx   eax, byte ptr [rbx+6]
0x140091f27  shl     ax, 7
0x140091f2b  or      cx, ax
0x140091f2e  movzx   eax, cx
0x140091f31  cmp     [rdx+rax*2-2], r14w
0x140091f37  jnz     loc_140091FC7
0x140091f3d  xor     ecx, ecx
0x140091f3f  mov     dword ptr [rsi], 6
0x140091f45  lea     r11, [rdx+rax*2]
0x140091f49  mov     [rdi], rcx
0x140091f4c  xor     r10d, r10d
0x140091f4f  mov     [rdi+0Ch], ecx
0x140091f52  lea     rbx, [r11+2]
0x140091f56  cmp     rdx, r11
0x140091f59  jnb     short loc_140091FC0
0x140091f5b  movzx   eax, byte ptr [rbx]
0x140091f5e  movzx   r9d, byte ptr [rbx+1]
0x140091f63  movzx   r8d, byte ptr [rdx]
0x140091f67  shl     ax, 8
0x140091f6b  or      r9w, ax
0x140091f6f  shl     r8w, 8
0x140091f74  movzx   eax, byte ptr [rdx+1]
0x140091f78  or      r8w, ax
0x140091f7c  cmp     r8w, r9w
0x140091f80  jb      short loc_140091FC7
0x140091f82  cmp     cx, r9w
0x140091f86  ja      short loc_140091FC7
0x140091f88  cmp     r8w, r14w
0x140091f8c  jnz     short loc_140091F97
0x140091f8e  lea     rax, [r11-2]
0x140091f92  cmp     rdx, rax
0x140091f95  jb      short loc_140091FC7
0x140091f97  inc     r10d
0x140091f9a  movzx   ecx, r8w
0x140091f9e  movzx   eax, r9w
0x140091fa2  add     rbx, r15
0x140091fa5  sub     ecx, eax
0x140091fa7  add     rdx, r15
0x140091faa  add     r10d, ecx
0x140091fad  movzx   ecx, r8w
0x140091fb1  cmp     rdx, r11
0x140091fb4  jb      short loc_140091F5B
0x140091fb6  xor     eax, eax
0x140091fb8  cmp     r10d, r14d
0x140091fbb  setbe   al
0x140091fbe  jmp     short loc_140091FC9
0x140091fc0  mov     eax, 1
0x140091fc5  jmp     short loc_140091FC9
0x140091fc7  xor     eax, eax
0x140091fc9  add     rsp, 20h
0x140091fcd  pop     r15
0x140091fcf  pop     r14
0x140091fd1  pop     rdi
0x140091fd2  pop     rsi
0x140091fd3  pop     rbx
0x140091fd4  retn
```
