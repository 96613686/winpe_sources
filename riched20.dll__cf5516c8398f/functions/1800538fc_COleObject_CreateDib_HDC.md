# COleObject::CreateDib(HDC__ *)

- ea: `0x1800538fc`
- end: `0x180053a49`
- name: `?CreateDib@COleObject@@AEAAXPEAUHDC__@@@Z`
- size: `333`
- prototype: `void(COleObject *__hidden this, HDC)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180053e88`

## callees

- `0x1800455c4`
- `0x18004a8fc`
- `0x1800538fc`
- `0x1800910fe`

## import_xrefs

- `KERNEL32!GlobalLock` at `0x180053947`
- `KERNEL32!GlobalLock` at `0x180053947`
- `KERNEL32!GlobalUnlock` at `0x180053a2b`
- `KERNEL32!GlobalUnlock` at `0x180053a2b`
- `GDI32!CreateDIBSection` at `0x1800539aa`
- `GDI32!CreateDIBSection` at `0x1800539aa`

## pseudocode

```c
void __fastcall COleObject::CreateDib(COleObject *this, HDC a2)
{
  __int64 v2; // rax
  __int64 v5; // rax
  void *v6; // rcx
  const BITMAPINFO *v7; // rax
  unsigned __int16 *v8; // rdi
  int v9; // r14d
  unsigned int biWidth; // esi
  LONG biHeight; // ebp
  HBITMAP v12; // rax
  unsigned int v13; // ebp
  size_t v14; // r8
  unsigned int v15; // ecx
  unsigned __int16 *v16; // rdx
  void *ppvBits; // [rsp+80h] [rbp+8h] BYREF

  v2 = *((_QWORD *)this + 8);
  if ( v2 )
  {
    v5 = *(_QWORD *)(v2 + 136);
    if ( v5 )
    {
      if ( *(_QWORD *)(v5 + 32) )
      {
        v6 = (void *)*((_QWORD *)this + 15);
        ppvBits = 0;
        v7 = (const BITMAPINFO *)GlobalLock(v6);
        v8 = (unsigned __int16 *)v7;
        if ( v7->bmiHeader.biBitCount > 8u )
        {
          biWidth = v7->bmiHeader.biWidth;
          v9 = 0;
        }
        else
        {
          v9 = 1 << v7->bmiHeader.biBitCount;
          biWidth = 8u
                  / v7->bmiHeader.biBitCount
                  * ((((v7->bmiHeader.biWidth * (unsigned int)v7->bmiHeader.biBitCount + 7) >> 3) + 3) & 0xFFFFFFFC);
        }
        biHeight = v7->bmiHeader.biHeight;
        v12 = CreateDIBSection(a2, v7, 0, &ppvBits, 0, 0);
        *((_QWORD *)this + 16) = v12;
        if ( v12 )
        {
          v13 = biWidth * biHeight;
          v14 = 4 * v13;
          if ( v9 )
          {
            if ( v8[7] )
            {
              v15 = 8u / v8[7];
              if ( v15 )
                v14 = v13 / v15;
            }
          }
          if ( ppvBits )
          {
            v16 = &v8[2 * v9 + 20];
            if ( v16 )
              memmove_0(ppvBits, v16, v14);
          }
          GlobalUnlock(v8);
          CW32System::GlobalFree(0);
        }
        else
        {
          CCallMgr::SetOutOfMemory(*(CCallMgr **)(*((_QWORD *)this + 8) + 144LL));
          *((_DWORD *)this + 40) &= ~0x20u;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800538fc  mov     r11, rsp
0x1800538ff  push    rbx
0x180053900  push    rbp
0x180053901  push    rsi
0x180053902  push    rdi
0x180053903  push    r12
0x180053905  push    r13
0x180053907  push    r14
0x180053909  push    r15
0x18005390b  sub     rsp, 38h
0x18005390f  mov     rax, [rcx+40h]
0x180053913  xor     r12d, r12d
0x180053916  mov     r15, rdx
0x180053919  mov     rbx, rcx
0x18005391c  test    rax, rax
0x18005391f  jz      loc_180053A38
0x180053925  mov     rax, [rax+88h]
0x18005392c  test    rax, rax
0x18005392f  jz      loc_180053A38
0x180053935  cmp     [rax+20h], r12
0x180053939  jz      loc_180053A38
0x18005393f  mov     rcx, [rcx+78h]; hMem
0x180053943  mov     [r11+8], r12
0x180053947  call    cs:__imp_GlobalLock
0x18005394d  lea     r13d, [r12+8]
0x180053952  mov     rdi, rax
0x180053955  cmp     [rax+0Eh], r13w
0x18005395a  ja      short loc_180053986
0x18005395c  movzx   ecx, word ptr [rax+0Eh]
0x180053960  lea     r14d, [r12+1]
0x180053965  xor     edx, edx
0x180053967  shl     r14d, cl
0x18005396a  mov     esi, ecx
0x18005396c  imul    esi, [rax+4]
0x180053970  mov     eax, r13d
0x180053973  div     ecx
0x180053975  add     esi, 7
0x180053978  shr     esi, 3
0x18005397b  add     esi, 3
0x18005397e  and     esi, 0FFFFFFFCh
0x180053981  imul    esi, eax
0x180053984  jmp     short loc_18005398C
0x180053986  mov     esi, [rax+4]
0x180053989  mov     r14d, r12d
0x18005398c  mov     ebp, [rdi+8]
0x18005398f  lea     r9, [rsp+78h+ppvBits]; ppvBits
0x180053997  mov     [rsp+78h+offset], r12d; offset
0x18005399c  xor     r8d, r8d; usage
0x18005399f  mov     rdx, rdi; pbmi
0x1800539a2  mov     [rsp+78h+hSection], r12; hSection
0x1800539a7  mov     rcx, r15; hdc
0x1800539aa  call    cs:__imp_CreateDIBSection
0x1800539b0  mov     [rbx+80h], rax
0x1800539b7  test    rax, rax
0x1800539ba  jnz     short loc_1800539D5
0x1800539bc  mov     rcx, [rbx+40h]
0x1800539c0  mov     rcx, [rcx+90h]; this
0x1800539c7  call    ?SetOutOfMemory@CCallMgr@@QEAAXXZ; CCallMgr::SetOutOfMemory(void)
0x1800539cc  and     dword ptr [rbx+0A0h], 0FFFFFFDFh
0x1800539d3  jmp     short loc_180053A38
0x1800539d5  imul    ebp, esi
0x1800539d8  lea     r8d, ds:0[rbp*4]
0x1800539e0  test    r14d, r14d
0x1800539e3  jz      short loc_180053A06
0x1800539e5  cmp     [rdi+0Eh], r12w
0x1800539ea  jz      short loc_180053A06
0x1800539ec  movzx   ecx, word ptr [rdi+0Eh]
0x1800539f0  xor     edx, edx
0x1800539f2  mov     eax, r13d
0x1800539f5  div     ecx
0x1800539f7  mov     ecx, eax
0x1800539f9  test    eax, eax
0x1800539fb  jz      short loc_180053A06
0x1800539fd  xor     edx, edx
0x1800539ff  mov     eax, ebp
0x180053a01  div     ecx
0x180053a03  mov     r8d, eax; Size
0x180053a06  mov     rcx, [rsp+78h+ppvBits]; void *
0x180053a0e  test    rcx, rcx
0x180053a11  jz      short loc_180053A28
0x180053a13  movsxd  rdx, r14d
0x180053a16  add     rdx, 0Ah
0x180053a1a  lea     rdx, [rdi+rdx*4]; Src
0x180053a1e  test    rdx, rdx
0x180053a21  jz      short loc_180053A28
0x180053a23  call    memmove_0
0x180053a28  mov     rcx, rdi; hMem
0x180053a2b  call    cs:__imp_GlobalUnlock
0x180053a31  xor     ecx, ecx; void *
0x180053a33  call    ?GlobalFree@CW32System@@SAPEAXPEAX@Z; CW32System::GlobalFree(void *)
0x180053a38  add     rsp, 38h
0x180053a3c  pop     r15
0x180053a3e  pop     r14
0x180053a40  pop     r13
0x180053a42  pop     r12
0x180053a44  pop     rdi
0x180053a45  pop     rsi
0x180053a46  pop     rbp
0x180053a47  pop     rbx
0x180053a48  retn
```
