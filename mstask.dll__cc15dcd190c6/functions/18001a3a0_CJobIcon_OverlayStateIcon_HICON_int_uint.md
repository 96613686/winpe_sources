# CJobIcon::OverlayStateIcon(HICON__ *,int,uint)

- ea: `0x18001a3a0`
- end: `0x18001a433`
- name: `?OverlayStateIcon@CJobIcon@@QEAAPEAUHICON__@@PEAU2@HI@Z`
- size: `147`
- prototype: `HICON(CJobIcon *__hidden this, HICON, int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010c38`

## callees

- `0x18001a3a0`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x18001a3be`
- `USER32!GetSystemMetrics` at `0x18001a3cb`
- `USER32!GetSystemMetrics` at `0x18001a3be`
- `USER32!GetSystemMetrics` at `0x18001a3cb`
- `COMCTL32!ImageList_ReplaceIcon` at `0x18001a3ee`
- `COMCTL32!ImageList_ReplaceIcon` at `0x18001a3ee`
- `COMCTL32!ImageList_Remove` at `0x18001a41d`
- `COMCTL32!ImageList_Remove` at `0x18001a41d`
- `COMCTL32!ImageList_GetIcon` at `0x18001a40f`
- `COMCTL32!ImageList_GetIcon` at `0x18001a40f`

## pseudocode

```c
HICON __fastcall CJobIcon::OverlayStateIcon(HIMAGELIST *this, HICON a2, int a3, unsigned int a4)
{
  unsigned int SystemMetrics; // ebx
  unsigned int v9; // eax
  HIMAGELIST *v10; // rsi
  int v11; // edi
  HICON Icon; // rbx

  SystemMetrics = GetSystemMetrics(11);
  v9 = GetSystemMetrics(49);
  if ( a4 <= SystemMetrics )
  {
    v10 = this + 1;
    if ( a4 <= v9 )
      v10 = this;
  }
  else
  {
    v10 = this + 2;
  }
  v11 = ImageList_ReplaceIcon(*v10, -1, a2);
  Icon = ImageList_GetIcon(*v10, v11, a3 != 0 ? 256 : 512);
  ImageList_Remove(*v10, v11);
  return Icon;
}

```

## disassembly

```asm
0x18001a3a0  push    rbx
0x18001a3a2  push    rbp
0x18001a3a3  push    rsi
0x18001a3a4  push    rdi
0x18001a3a5  push    r14
0x18001a3a7  push    r15
0x18001a3a9  sub     rsp, 28h
0x18001a3ad  mov     rdi, rcx
0x18001a3b0  mov     ebp, r9d
0x18001a3b3  mov     ecx, 0Bh; nIndex
0x18001a3b8  mov     r14d, r8d
0x18001a3bb  mov     r15, rdx
0x18001a3be  call    cs:__imp_GetSystemMetrics
0x18001a3c4  mov     ecx, 31h ; '1'; nIndex
0x18001a3c9  mov     ebx, eax
0x18001a3cb  call    cs:__imp_GetSystemMetrics
0x18001a3d1  cmp     ebp, ebx
0x18001a3d3  jbe     short loc_18001A3DB
0x18001a3d5  lea     rsi, [rdi+10h]
0x18001a3d9  jmp     short loc_18001A3E5
0x18001a3db  cmp     ebp, eax
0x18001a3dd  lea     rsi, [rdi+8]
0x18001a3e1  cmovbe  rsi, rdi
0x18001a3e5  mov     rcx, [rsi]; himl
0x18001a3e8  mov     r8, r15; hicon
0x18001a3eb  or      edx, 0FFFFFFFFh; i
0x18001a3ee  call    cs:__imp_ImageList_ReplaceIcon
0x18001a3f4  mov     rcx, [rsi]; himl
0x18001a3f7  neg     r14d
0x18001a3fa  mov     edx, eax; i
0x18001a3fc  mov     edi, eax
0x18001a3fe  sbb     r8d, r8d
0x18001a401  and     r8d, 0FFFFFF00h
0x18001a408  add     r8d, 200h; flags
0x18001a40f  call    cs:__imp_ImageList_GetIcon
0x18001a415  mov     rcx, [rsi]; himl
0x18001a418  mov     edx, edi; i
0x18001a41a  mov     rbx, rax
0x18001a41d  call    cs:__imp_ImageList_Remove
0x18001a423  mov     rax, rbx
0x18001a426  add     rsp, 28h
0x18001a42a  pop     r15
0x18001a42c  pop     r14
0x18001a42e  pop     rdi
0x18001a42f  pop     rsi
0x18001a430  pop     rbp
0x18001a431  pop     rbx
0x18001a432  retn
```
