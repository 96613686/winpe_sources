# COleObject::CreateDib(HDC__ *)

- ea: `0x1801fb4b0`
- end: `0x1801fb638`
- name: `?CreateDib@COleObject@@AEAAXPEAUHDC__@@@Z`
- size: `392`
- prototype: `void __fastcall(void **this, HDC)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1801fb640`

## callees

- `0x18013dcda`
- `0x1801fb4b0`
- `0x180209568`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1801fb61a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1801fb61a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1801fb4ea`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1801fb4ea`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x1801fb577`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x1801fb577`

## pseudocode

```c
void __fastcall COleObject::CreateDib(void **this, HDC a2)
{
  unsigned int v4; // esi
  void *v5; // rcx
  BITMAPINFO *v6; // rax
  BITMAPINFO *v7; // rbx
  unsigned int biBitCount; // eax
  int v9; // r14d
  unsigned int biWidth; // ebp
  int v11; // esi
  LONG biHeight; // r15d
  HBITMAP v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rax
  unsigned int v16; // ecx
  unsigned int v17; // r15d
  unsigned int v18; // ecx
  void *ppvBits; // [rsp+80h] [rbp+8h] BYREF

  v4 = CW32System::GlobalSize(this[14]);
  if ( v4 >= 0x2C )
  {
    v5 = this[14];
    ppvBits = 0;
    v6 = (BITMAPINFO *)GlobalLock(v5);
    v7 = v6;
    if ( v6 )
    {
      biBitCount = v6->bmiHeader.biBitCount;
      if ( (unsigned __int16)biBitCount > 8u )
      {
        biWidth = v7->bmiHeader.biWidth;
        v9 = 0;
      }
      else
      {
        if ( !(_WORD)biBitCount )
        {
LABEL_19:
          GlobalUnlock(v7);
          return;
        }
        v9 = 1 << biBitCount;
        biWidth = 8 / biBitCount * ((((v7->bmiHeader.biWidth * biBitCount + 7) >> 3) + 3) & 0xFFFFFFFC);
      }
      v11 = v4 - (4 * v9 + 40);
      if ( v11 > 0 )
      {
        biHeight = v7->bmiHeader.biHeight;
        v13 = CreateDIBSection(a2, v7, 0, &ppvBits, 0, 0);
        this[15] = v13;
        if ( v13 )
        {
          v16 = v7->bmiHeader.biBitCount;
          v17 = biWidth * biHeight;
          if ( v9 )
            v18 = v17 / (8 / v16);
          else
            v18 = v17 * (v16 >> 3);
          if ( v18 <= v11 )
            memmove_0(ppvBits, &v7->bmiColors[v9], (int)v18);
        }
        else
        {
          v14 = (unsigned __int64)this[6] & -(__int64)(*((_WORD *)this[6] + 28) != 0);
          if ( (-(__int64)(v14 != 0) & (v14 + 48)) != 0 )
          {
            v15 = v14 + 60;
            if ( !v14 )
              v15 = 12;
            *(_DWORD *)v15 |= 0x40u;
          }
          *((_WORD *)this + 77) &= ~0x20u;
        }
      }
      goto LABEL_19;
    }
  }
}

```

## disassembly

```asm
0x1801fb4b0  push    rbx
0x1801fb4b2  push    rbp
0x1801fb4b3  push    rsi
0x1801fb4b4  push    rdi
0x1801fb4b5  push    r12
0x1801fb4b7  push    r13
0x1801fb4b9  push    r14
0x1801fb4bb  push    r15
0x1801fb4bd  sub     rsp, 38h
0x1801fb4c1  mov     rdi, rcx
0x1801fb4c4  mov     r12, rdx
0x1801fb4c7  mov     rcx, [rcx+70h]; void *
0x1801fb4cb  call    ?GlobalSize@CW32System@@SAKPEAX@Z; CW32System::GlobalSize(void *)
0x1801fb4d0  mov     esi, eax
0x1801fb4d2  cmp     eax, 2Ch ; ','
0x1801fb4d5  jb      loc_1801FB626
0x1801fb4db  mov     rcx, [rdi+70h]; hMem
0x1801fb4df  xor     r13d, r13d
0x1801fb4e2  mov     [rsp+78h+ppvBits], r13
0x1801fb4ea  call    cs:__imp_GlobalLock
0x1801fb4f1  nop     dword ptr [rax+rax+00h]
0x1801fb4f6  mov     rbx, rax
0x1801fb4f9  test    rax, rax
0x1801fb4fc  jz      loc_1801FB626
0x1801fb502  movzx   eax, word ptr [rax+0Eh]
0x1801fb506  lea     r8d, [r13+8]
0x1801fb50a  cmp     ax, r8w
0x1801fb50e  ja      short loc_1801FB540
0x1801fb510  test    ax, ax
0x1801fb513  jz      loc_1801FB617
0x1801fb519  mov     ecx, eax
0x1801fb51b  lea     r14d, [r13+1]
0x1801fb51f  mov     ebp, eax
0x1801fb521  shl     r14d, cl
0x1801fb524  imul    ebp, [rbx+4]
0x1801fb528  xor     edx, edx
0x1801fb52a  mov     eax, r8d
0x1801fb52d  div     ecx
0x1801fb52f  add     ebp, 7
0x1801fb532  shr     ebp, 3
0x1801fb535  add     ebp, 3
0x1801fb538  and     ebp, 0FFFFFFFCh
0x1801fb53b  imul    ebp, eax
0x1801fb53e  jmp     short loc_1801FB546
0x1801fb540  mov     ebp, [rbx+4]
0x1801fb543  mov     r14d, r13d
0x1801fb546  lea     eax, ds:28h[r14*4]
0x1801fb54e  sub     esi, eax
0x1801fb550  test    esi, esi
0x1801fb552  jle     loc_1801FB617
0x1801fb558  mov     r15d, [rbx+8]
0x1801fb55c  lea     r9, [rsp+78h+ppvBits]; ppvBits
0x1801fb564  mov     [rsp+78h+offset], r13d; offset
0x1801fb569  xor     r8d, r8d; usage
0x1801fb56c  mov     rdx, rbx; pbmi
0x1801fb56f  mov     [rsp+78h+hSection], r13; hSection
0x1801fb574  mov     rcx, r12; hdc
0x1801fb577  call    cs:__imp_CreateDIBSection
0x1801fb57e  nop     dword ptr [rax+rax+00h]
0x1801fb583  mov     [rdi+78h], rax
0x1801fb587  test    rax, rax
0x1801fb58a  jnz     short loc_1801FB5D0
0x1801fb58c  mov     rcx, [rdi+30h]
0x1801fb590  movzx   eax, word ptr [rcx+38h]
0x1801fb594  neg     ax
0x1801fb597  sbb     rdx, rdx
0x1801fb59a  and     rdx, rcx
0x1801fb59d  mov     rax, rdx
0x1801fb5a0  neg     rax
0x1801fb5a3  sbb     rax, rax
0x1801fb5a6  lea     rcx, [rdx+30h]
0x1801fb5aa  test    rcx, rax
0x1801fb5ad  jz      short loc_1801FB5C2
0x1801fb5af  test    rdx, rdx
0x1801fb5b2  lea     rax, [rdx+3Ch]
0x1801fb5b6  mov     ecx, 0Ch
0x1801fb5bb  cmovz   rax, rcx
0x1801fb5bf  or      dword ptr [rax], 40h
0x1801fb5c2  mov     eax, 0FFDFh
0x1801fb5c7  and     [rdi+9Ah], ax
0x1801fb5ce  jmp     short loc_1801FB617
0x1801fb5d0  movzx   ecx, word ptr [rbx+0Eh]
0x1801fb5d4  imul    r15d, ebp
0x1801fb5d8  test    r14d, r14d
0x1801fb5db  jz      short loc_1801FB5F1
0x1801fb5dd  xor     edx, edx
0x1801fb5df  lea     eax, [rdx+8]
0x1801fb5e2  div     ecx
0x1801fb5e4  xor     edx, edx
0x1801fb5e6  mov     ecx, eax
0x1801fb5e8  mov     eax, r15d
0x1801fb5eb  div     ecx
0x1801fb5ed  mov     ecx, eax
0x1801fb5ef  jmp     short loc_1801FB5F8
0x1801fb5f1  shr     ecx, 3
0x1801fb5f4  imul    ecx, r15d
0x1801fb5f8  cmp     ecx, esi
0x1801fb5fa  ja      short loc_1801FB617
0x1801fb5fc  movsxd  r8, ecx; Size
0x1801fb5ff  mov     rcx, [rsp+78h+ppvBits]; void *
0x1801fb607  movsxd  rax, r14d
0x1801fb60a  add     rax, 0Ah
0x1801fb60e  lea     rdx, [rbx+rax*4]; Src
0x1801fb612  call    memmove_0
0x1801fb617  mov     rcx, rbx; hMem
0x1801fb61a  call    cs:__imp_GlobalUnlock
0x1801fb621  nop     dword ptr [rax+rax+00h]
0x1801fb626  add     rsp, 38h
0x1801fb62a  pop     r15
0x1801fb62c  pop     r14
0x1801fb62e  pop     r13
0x1801fb630  pop     r12
0x1801fb632  pop     rdi
0x1801fb633  pop     rsi
0x1801fb634  pop     rbp
0x1801fb635  pop     rbx
0x1801fb636  retn
```
