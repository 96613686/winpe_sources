# DpDriver::SetupClipping(HDC__ *,DpContext *,GpRuntime::GpRect const *,int &,int &,int)

- ea: `0x1800e39d0`
- end: `0x1800e3b33`
- name: `?SetupClipping@DpDriver@@UEAAXPEAUHDC__@@PEAVDpContext@@PEBVGpRect@GpRuntime@@AEAH3H@Z`
- size: `355`
- prototype: `void(DpDriver *__hidden this, HDC, struct DpContext *, const struct GpRuntime::GpRect *, int *, int *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800e37f0`

## callees

- `0x18000f6b0`
- `0x18001b8c8`
- `0x1800e39d0`
- `0x18014615c`

## import_xrefs

- `GDI32!ExtSelectClipRgn` at `0x1800e3b10`
- `GDI32!ExtSelectClipRgn` at `0x1800e3b10`
- `GDI32!IntersectClipRect` at `0x1800e3a6f`
- `GDI32!IntersectClipRect` at `0x1800e3a6f`
- `GDI32!SaveDC` at `0x1800e3a4b`
- `GDI32!SaveDC` at `0x1800e3af6`
- `GDI32!SaveDC` at `0x1800e3a4b`
- `GDI32!SaveDC` at `0x1800e3af6`
- `GDI32!DeleteObject` at `0x1800e3b1f`
- `GDI32!DeleteObject` at `0x1800e3b1f`

## pseudocode

```c
void __fastcall DpDriver::SetupClipping(
        DpDriver *this,
        HDC a2,
        struct DpContext *a3,
        const struct GpRuntime::GpRect *a4,
        int *a5,
        int *a6,
        int a7)
{
  DpRegion *v7; // rbx
  int v10; // r12d
  int v11; // ebp
  int v12; // r14d
  int v13; // r15d
  int bottom; // r12d
  HRGN HRgn; // rdi

  v7 = (struct DpContext *)((char *)a3 + 304);
  v10 = *a6;
  *a6 = 0;
  *a5 = 0;
  if ( a7
    || (unsigned int)DpRegion::GetRectVisibility(
                       v7,
                       *(unsigned int *)a4,
                       *((unsigned int *)a4 + 1),
                       (unsigned int)(*(_DWORD *)a4 + *((_DWORD *)a4 + 2)),
                       *((_DWORD *)a4 + 1) + *((_DWORD *)a4 + 3),
                       0) != 3 )
  {
    if ( *((_QWORD *)v7 + 3) )
    {
      if ( v10 && (unsigned int)SetupPathClipping(a2) )
      {
        *a5 = 1;
        *a6 = 1;
      }
      else
      {
        HRgn = (HRGN)DpRegion::GetHRgn(v7);
        if ( HRgn )
        {
          SaveDC(a2);
          ExtSelectClipRgn(a2, HRgn, 1);
          DeleteObject(HRgn);
          *a5 = 1;
        }
      }
    }
    else
    {
      *a5 = 1;
      v11 = *((_DWORD *)a3 + 78);
      v12 = *((_DWORD *)a3 + 79);
      v13 = *((_DWORD *)a3 + 80);
      bottom = *((_DWORD *)a3 + 81);
      SaveDC(a2);
      if ( (*((_BYTE *)a3 + 308) & 1) == 0 )
        IntersectClipRect(a2, v11, v12, v13, bottom);
    }
  }
}

```

## disassembly

```asm
0x1800e39d0  push    rbx
0x1800e39d2  push    rbp
0x1800e39d3  push    rsi
0x1800e39d4  push    rdi
0x1800e39d5  push    r12
0x1800e39d7  push    r14
0x1800e39d9  push    r15
0x1800e39db  sub     rsp, 30h
0x1800e39df  cmp     [rsp+68h+arg_30], 0
0x1800e39e7  lea     rbx, [r8+130h]
0x1800e39ee  mov     r15, [rsp+68h+arg_28]
0x1800e39f6  mov     rbp, r9
0x1800e39f9  mov     r14, [rsp+68h+arg_20]
0x1800e3a01  mov     rdi, r8
0x1800e3a04  mov     rsi, rdx
0x1800e3a07  mov     r12d, [r15]
0x1800e3a0a  mov     dword ptr [r15], 0
0x1800e3a11  mov     dword ptr [r14], 0
0x1800e3a18  jz      short loc_1800E3A8B
0x1800e3a1a  cmp     qword ptr [rbx+18h], 0
0x1800e3a1f  jnz     loc_1800E3ABF
0x1800e3a25  mov     ebx, 1
0x1800e3a2a  mov     rcx, rsi; hdc
0x1800e3a2d  mov     [r14], ebx
0x1800e3a30  mov     ebp, [rdi+138h]
0x1800e3a36  mov     r14d, [rdi+13Ch]
0x1800e3a3d  mov     r15d, [rdi+140h]
0x1800e3a44  mov     r12d, [rdi+144h]
0x1800e3a4b  call    cs:__imp_SaveDC
0x1800e3a52  nop     dword ptr [rax+rax+00h]
0x1800e3a57  test    [rdi+134h], bl
0x1800e3a5d  jnz     short loc_1800E3A7B
0x1800e3a5f  mov     r9d, r15d; right
0x1800e3a62  mov     [rsp+68h+bottom], r12d; bottom
0x1800e3a67  mov     r8d, r14d; top
0x1800e3a6a  mov     edx, ebp; left
0x1800e3a6c  mov     rcx, rsi; hdc
0x1800e3a6f  call    cs:__imp_IntersectClipRect
0x1800e3a76  nop     dword ptr [rax+rax+00h]
0x1800e3a7b  add     rsp, 30h
0x1800e3a7f  pop     r15
0x1800e3a81  pop     r14
0x1800e3a83  pop     r12
0x1800e3a85  pop     rdi
0x1800e3a86  pop     rsi
0x1800e3a87  pop     rbp
0x1800e3a88  pop     rbx
0x1800e3a89  retn
0x1800e3a8b  mov     ecx, [r9+0Ch]
0x1800e3a8f  mov     r8d, [r9+4]
0x1800e3a93  add     ecx, r8d
0x1800e3a96  mov     edx, [r9]
0x1800e3a99  mov     r9d, [r9+8]
0x1800e3a9d  mov     [rsp+68h+var_40], 0
0x1800e3aa6  add     r9d, edx
0x1800e3aa9  mov     [rsp+68h+bottom], ecx
0x1800e3aad  mov     rcx, rbx
0x1800e3ab0  call    ?GetRectVisibility@DpRegion@@QEAA?AW4Visibility@1@HHHHPEAVGpRect@GpRuntime@@@Z; DpRegion::GetRectVisibility(int,int,int,int,GpRuntime::GpRect *)
0x1800e3ab5  cmp     eax, 3
0x1800e3ab8  jz      short loc_1800E3A7B
0x1800e3aba  jmp     loc_1800E3A1A
0x1800e3abf  test    r12d, r12d
0x1800e3ac2  jz      short loc_1800E3AE3
0x1800e3ac4  mov     r9, rbp
0x1800e3ac7  mov     rdx, rdi
0x1800e3aca  mov     rcx, rsi; HDC
0x1800e3acd  call    SetupPathClipping
0x1800e3ad2  test    eax, eax
0x1800e3ad4  jz      short loc_1800E3AE3
0x1800e3ad6  mov     ebx, 1
0x1800e3adb  mov     [r14], ebx
0x1800e3ade  mov     [r15], ebx
0x1800e3ae1  jmp     short loc_1800E3A7B
0x1800e3ae3  mov     rcx, rbx; this
0x1800e3ae6  call    ?GetHRgn@DpRegion@@QEBAPEAUHRGN__@@XZ; DpRegion::GetHRgn(void)
0x1800e3aeb  mov     rdi, rax
0x1800e3aee  test    rax, rax
0x1800e3af1  jz      short loc_1800E3A7B
0x1800e3af3  mov     rcx, rsi; hdc
0x1800e3af6  call    cs:__imp_SaveDC
0x1800e3afd  nop     dword ptr [rax+rax+00h]
0x1800e3b02  mov     ebx, 1
0x1800e3b07  mov     rdx, rdi; hrgn
0x1800e3b0a  mov     r8d, ebx; mode
0x1800e3b0d  mov     rcx, rsi; hdc
0x1800e3b10  call    cs:__imp_ExtSelectClipRgn
0x1800e3b17  nop     dword ptr [rax+rax+00h]
0x1800e3b1c  mov     rcx, rdi; ho
0x1800e3b1f  call    cs:__imp_DeleteObject
0x1800e3b26  nop     dword ptr [rax+rax+00h]
0x1800e3b2b  mov     [r14], ebx
0x1800e3b2e  jmp     loc_1800E3A7B
```
