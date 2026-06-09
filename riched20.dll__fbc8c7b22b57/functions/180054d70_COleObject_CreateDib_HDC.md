# COleObject::CreateDib(HDC__ *)

- ea: `0x180054d70`
- end: `0x180054ec6`
- name: `?CreateDib@COleObject@@AEAAXPEAUHDC__@@@Z`
- size: `342`
- prototype: `void(COleObject *__hidden this, HDC)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18005530c`

## callees

- `0x1800466f0`
- `0x18004bac8`
- `0x180054d70`
- `0x1800559d8`
- `0x180093bbe`

## import_xrefs

- `KERNEL32!GlobalLock` at `0x180054db1`
- `KERNEL32!GlobalLock` at `0x180054db1`
- `KERNEL32!GlobalUnlock` at `0x180054ea1`
- `KERNEL32!GlobalUnlock` at `0x180054ea1`
- `GDI32!CreateDIBSection` at `0x180054e1a`
- `GDI32!CreateDIBSection` at `0x180054e1a`

## pseudocode

```c
void __fastcall COleObject::CreateDib(COleObject *this, HDC a2)
{
  CTxtEdit *v3; // rcx
  void *v5; // rcx
  const BITMAPINFO *v6; // rax
  unsigned __int16 *v7; // rdi
  int v8; // r14d
  unsigned int biWidth; // esi
  LONG biHeight; // ebp
  HBITMAP v11; // rax
  unsigned int v12; // ebp
  size_t v13; // r8
  unsigned int v14; // ecx
  unsigned __int16 *v15; // rdx
  void *ppvBits; // [rsp+80h] [rbp+8h] BYREF

  v3 = (CTxtEdit *)*((_QWORD *)this + 8);
  if ( v3 && CTxtEdit::GetRECallback(v3) )
  {
    v5 = (void *)*((_QWORD *)this + 15);
    ppvBits = 0;
    v6 = (const BITMAPINFO *)GlobalLock(v5);
    v7 = (unsigned __int16 *)v6;
    if ( v6->bmiHeader.biBitCount > 8u )
    {
      biWidth = v6->bmiHeader.biWidth;
      v8 = 0;
    }
    else
    {
      v8 = 1 << v6->bmiHeader.biBitCount;
      biWidth = 8u
              / v6->bmiHeader.biBitCount
              * ((((v6->bmiHeader.biWidth * (unsigned int)v6->bmiHeader.biBitCount + 7) >> 3) + 3) & 0xFFFFFFFC);
    }
    biHeight = v6->bmiHeader.biHeight;
    v11 = CreateDIBSection(a2, v6, 0, &ppvBits, 0, 0);
    *((_QWORD *)this + 16) = v11;
    if ( v11 )
    {
      v12 = biWidth * biHeight;
      v13 = 4 * v12;
      if ( v8 )
      {
        if ( v7[7] )
        {
          v14 = 8u / v7[7];
          if ( v14 )
            v13 = v12 / v14;
        }
      }
      if ( ppvBits )
      {
        v15 = &v7[2 * v8 + 20];
        if ( v15 )
          memmove_0(ppvBits, v15, v13);
      }
      GlobalUnlock(v7);
      CW32System::GlobalFree(0);
    }
    else
    {
      CCallMgr::SetOutOfMemory(*(CCallMgr **)(*((_QWORD *)this + 8) + 144LL));
      *((_DWORD *)this + 40) &= ~0x20u;
    }
  }
}

```

## disassembly

```asm
0x180054d70  push    rbx
0x180054d72  push    rbp
0x180054d73  push    rsi
0x180054d74  push    rdi
0x180054d75  push    r12
0x180054d77  push    r13
0x180054d79  push    r14
0x180054d7b  push    r15
0x180054d7d  sub     rsp, 38h
0x180054d81  mov     rbx, rcx
0x180054d84  xor     r12d, r12d
0x180054d87  mov     rcx, [rcx+40h]; this
0x180054d8b  mov     r15, rdx
0x180054d8e  test    rcx, rcx
0x180054d91  jz      loc_180054EB4
0x180054d97  call    ?GetRECallback@CTxtEdit@@QEAAPEAUIRichEditOleCallback@@XZ; CTxtEdit::GetRECallback(void)
0x180054d9c  test    rax, rax
0x180054d9f  jz      loc_180054EB4
0x180054da5  mov     rcx, [rbx+78h]; hMem
0x180054da9  mov     [rsp+78h+ppvBits], r12
0x180054db1  call    cs:__imp_GlobalLock
0x180054db8  nop     dword ptr [rax+rax+00h]
0x180054dbd  lea     r13d, [r12+8]
0x180054dc2  mov     rdi, rax
0x180054dc5  cmp     [rax+0Eh], r13w
0x180054dca  ja      short loc_180054DF6
0x180054dcc  movzx   ecx, word ptr [rax+0Eh]
0x180054dd0  lea     r14d, [r12+1]
0x180054dd5  xor     edx, edx
0x180054dd7  shl     r14d, cl
0x180054dda  mov     esi, ecx
0x180054ddc  imul    esi, [rax+4]
0x180054de0  mov     eax, r13d
0x180054de3  div     ecx
0x180054de5  add     esi, 7
0x180054de8  shr     esi, 3
0x180054deb  add     esi, 3
0x180054dee  and     esi, 0FFFFFFFCh
0x180054df1  imul    esi, eax
0x180054df4  jmp     short loc_180054DFC
0x180054df6  mov     esi, [rax+4]
0x180054df9  mov     r14d, r12d
0x180054dfc  mov     ebp, [rdi+8]
0x180054dff  lea     r9, [rsp+78h+ppvBits]; ppvBits
0x180054e07  mov     [rsp+78h+offset], r12d; offset
0x180054e0c  xor     r8d, r8d; usage
0x180054e0f  mov     rdx, rdi; pbmi
0x180054e12  mov     [rsp+78h+hSection], r12; hSection
0x180054e17  mov     rcx, r15; hdc
0x180054e1a  call    cs:__imp_CreateDIBSection
0x180054e21  nop     dword ptr [rax+rax+00h]
0x180054e26  mov     [rbx+80h], rax
0x180054e2d  test    rax, rax
0x180054e30  jnz     short loc_180054E4B
0x180054e32  mov     rcx, [rbx+40h]
0x180054e36  mov     rcx, [rcx+90h]; this
0x180054e3d  call    ?SetOutOfMemory@CCallMgr@@QEAAXXZ; CCallMgr::SetOutOfMemory(void)
0x180054e42  and     dword ptr [rbx+0A0h], 0FFFFFFDFh
0x180054e49  jmp     short loc_180054EB4
0x180054e4b  imul    ebp, esi
0x180054e4e  lea     r8d, ds:0[rbp*4]
0x180054e56  test    r14d, r14d
0x180054e59  jz      short loc_180054E7C
0x180054e5b  cmp     [rdi+0Eh], r12w
0x180054e60  jz      short loc_180054E7C
0x180054e62  movzx   ecx, word ptr [rdi+0Eh]
0x180054e66  xor     edx, edx
0x180054e68  mov     eax, r13d
0x180054e6b  div     ecx
0x180054e6d  mov     ecx, eax
0x180054e6f  test    eax, eax
0x180054e71  jz      short loc_180054E7C
0x180054e73  xor     edx, edx
0x180054e75  mov     eax, ebp
0x180054e77  div     ecx
0x180054e79  mov     r8d, eax; Size
0x180054e7c  mov     rcx, [rsp+78h+ppvBits]; void *
0x180054e84  test    rcx, rcx
0x180054e87  jz      short loc_180054E9E
0x180054e89  movsxd  rdx, r14d
0x180054e8c  add     rdx, 0Ah
0x180054e90  lea     rdx, [rdi+rdx*4]; Src
0x180054e94  test    rdx, rdx
0x180054e97  jz      short loc_180054E9E
0x180054e99  call    memmove_0
0x180054e9e  mov     rcx, rdi; hMem
0x180054ea1  call    cs:__imp_GlobalUnlock
0x180054ea8  nop     dword ptr [rax+rax+00h]
0x180054ead  xor     ecx, ecx; void *
0x180054eaf  call    ?GlobalFree@CW32System@@SAPEAXPEAX@Z; CW32System::GlobalFree(void *)
0x180054eb4  add     rsp, 38h
0x180054eb8  pop     r15
0x180054eba  pop     r14
0x180054ebc  pop     r13
0x180054ebe  pop     r12
0x180054ec0  pop     rdi
0x180054ec1  pop     rsi
0x180054ec2  pop     rbp
0x180054ec3  pop     rbx
0x180054ec4  retn
```
