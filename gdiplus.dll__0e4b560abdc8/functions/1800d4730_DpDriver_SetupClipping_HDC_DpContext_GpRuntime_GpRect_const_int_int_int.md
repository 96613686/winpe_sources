# DpDriver::SetupClipping(HDC__ *,DpContext *,GpRuntime::GpRect const *,int &,int &,int)

- ea: `0x1800d4730`
- end: `0x1800d48a9`
- name: `?SetupClipping@DpDriver@@UEAAXPEAUHDC__@@PEAVDpContext@@PEBVGpRect@GpRuntime@@AEAH3H@Z`
- size: `377`
- prototype: `void(DpDriver *__hidden this, HDC, struct DpContext *, const struct GpRuntime::GpRect *, int *, int *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800d4550`

## callees

- `0x18001af90`
- `0x180024908`
- `0x1800d4730`
- `0x18013d770`

## import_xrefs

- `GDI32!ExtSelectClipRgn` at `0x1800d4886`
- `GDI32!ExtSelectClipRgn` at `0x1800d4886`
- `GDI32!IntersectClipRect` at `0x1800d4820`
- `GDI32!IntersectClipRect` at `0x1800d4820`
- `GDI32!SaveDC` at `0x1800d47a4`
- `GDI32!SaveDC` at `0x1800d486c`
- `GDI32!SaveDC` at `0x1800d47a4`
- `GDI32!SaveDC` at `0x1800d486c`
- `GDI32!DeleteObject` at `0x1800d4895`
- `GDI32!DeleteObject` at `0x1800d4895`

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
  int v9; // r12d
  DpRegion *v10; // rdi
  int v11; // r14d
  int v12; // r15d
  int v13; // r12d
  int bottom; // edi
  HRGN HRgn; // rdi

  v9 = *a6;
  *a6 = 0;
  *a5 = 0;
  if ( a7 )
  {
    v10 = (struct DpContext *)((char *)a3 + 304);
  }
  else
  {
    v10 = (struct DpContext *)((char *)a3 + 304);
    if ( (unsigned int)DpRegion::GetRectVisibility(
                         (char *)a3 + 304,
                         *(unsigned int *)a4,
                         *((unsigned int *)a4 + 1),
                         (unsigned int)(*(_DWORD *)a4 + *((_DWORD *)a4 + 2)),
                         *((_DWORD *)a4 + 1) + *((_DWORD *)a4 + 3),
                         0) == 3 )
      return;
  }
  if ( *((_QWORD *)a3 + 41) )
  {
    if ( v9 && (unsigned int)SetupPathClipping(a2) )
    {
      *a5 = 1;
      *a6 = 1;
    }
    else
    {
      HRgn = (HRGN)DpRegion::GetHRgn(v10);
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
    v11 = *((_DWORD *)v10 + 2);
    v12 = *((_DWORD *)v10 + 3);
    v13 = *((_DWORD *)v10 + 4);
    bottom = *((_DWORD *)v10 + 5);
    SaveDC(a2);
    if ( (*((_BYTE *)a3 + 308) & 1) == 0 )
      IntersectClipRect(a2, v11, v12, v13, bottom);
  }
}

```

## disassembly

```asm
0x1800d4730  mov     rax, rsp
0x1800d4733  mov     [rax+8], rbx
0x1800d4737  mov     [rax+10h], rbp
0x1800d473b  mov     [rax+18h], rsi
0x1800d473f  mov     [rax+20h], rdi
0x1800d4743  push    r12
0x1800d4745  push    r14
0x1800d4747  push    r15
0x1800d4749  sub     rsp, 30h
0x1800d474d  mov     r15, [rsp+48h+arg_28]
0x1800d4752  mov     rbx, r9
0x1800d4755  mov     r14, [rsp+48h+arg_20]
0x1800d475a  mov     rbp, r8
0x1800d475d  mov     rsi, rdx
0x1800d4760  mov     r12d, [r15]
0x1800d4763  and     dword ptr [r15], 0
0x1800d4767  and     dword ptr [r14], 0
0x1800d476b  cmp     [rsp+48h+arg_30], 0
0x1800d4773  jz      short loc_1800D47D8
0x1800d4775  lea     rdi, [r8+130h]
0x1800d477c  cmp     qword ptr [rbp+148h], 0
0x1800d4784  jnz     loc_1800D482E
0x1800d478a  mov     ebx, 1
0x1800d478f  mov     rcx, rsi; hdc
0x1800d4792  mov     [r14], ebx
0x1800d4795  mov     r14d, [rdi+8]
0x1800d4799  mov     r15d, [rdi+0Ch]
0x1800d479d  mov     r12d, [rdi+10h]
0x1800d47a1  mov     edi, [rdi+14h]
0x1800d47a4  call    cs:__imp_SaveDC
0x1800d47ab  nop     dword ptr [rax+rax+00h]
0x1800d47b0  test    [rbp+134h], bl
0x1800d47b6  jz      short loc_1800D4810
0x1800d47b8  mov     rbx, [rsp+48h+arg_0]
0x1800d47bd  mov     rbp, [rsp+48h+arg_8]
0x1800d47c2  mov     rsi, [rsp+48h+arg_10]
0x1800d47c7  mov     rdi, [rsp+48h+arg_18]
0x1800d47cc  add     rsp, 30h
0x1800d47d0  pop     r15
0x1800d47d2  pop     r14
0x1800d47d4  pop     r12
0x1800d47d6  retn
0x1800d47d8  mov     ecx, [r9+0Ch]
0x1800d47dc  lea     rdi, [rbp+130h]
0x1800d47e3  mov     r8d, [r9+4]
0x1800d47e7  add     ecx, r8d
0x1800d47ea  mov     edx, [r9]
0x1800d47ed  mov     r9d, [r9+8]
0x1800d47f1  and     [rsp+48h+var_20], 0
0x1800d47f7  add     r9d, edx
0x1800d47fa  mov     [rsp+48h+bottom], ecx
0x1800d47fe  mov     rcx, rdi
0x1800d4801  call    ?GetRectVisibility@DpRegion@@QEAA?AW4Visibility@1@HHHHPEAVGpRect@GpRuntime@@@Z; DpRegion::GetRectVisibility(int,int,int,int,GpRuntime::GpRect *)
0x1800d4806  cmp     eax, 3
0x1800d4809  jz      short loc_1800D47B8
0x1800d480b  jmp     loc_1800D477C
0x1800d4810  mov     r9d, r12d; right
0x1800d4813  mov     [rsp+48h+bottom], edi; bottom
0x1800d4817  mov     r8d, r15d; top
0x1800d481a  mov     edx, r14d; left
0x1800d481d  mov     rcx, rsi; hdc
0x1800d4820  call    cs:__imp_IntersectClipRect
0x1800d4827  nop     dword ptr [rax+rax+00h]
0x1800d482c  jmp     short loc_1800D47B8
0x1800d482e  test    r12d, r12d
0x1800d4831  jz      short loc_1800D4855
0x1800d4833  mov     r9, rbx
0x1800d4836  mov     rdx, rbp
0x1800d4839  mov     rcx, rsi; HDC
0x1800d483c  call    SetupPathClipping
0x1800d4841  test    eax, eax
0x1800d4843  jz      short loc_1800D4855
0x1800d4845  mov     ebx, 1
0x1800d484a  mov     [r14], ebx
0x1800d484d  mov     [r15], ebx
0x1800d4850  jmp     loc_1800D47B8
0x1800d4855  mov     rcx, rdi; this
0x1800d4858  call    ?GetHRgn@DpRegion@@QEBAPEAUHRGN__@@XZ; DpRegion::GetHRgn(void)
0x1800d485d  mov     rdi, rax
0x1800d4860  test    rax, rax
0x1800d4863  jz      loc_1800D47B8
0x1800d4869  mov     rcx, rsi; hdc
0x1800d486c  call    cs:__imp_SaveDC
0x1800d4873  nop     dword ptr [rax+rax+00h]
0x1800d4878  mov     ebx, 1
0x1800d487d  mov     rdx, rdi; hrgn
0x1800d4880  mov     r8d, ebx; mode
0x1800d4883  mov     rcx, rsi; hdc
0x1800d4886  call    cs:__imp_ExtSelectClipRgn
0x1800d488d  nop     dword ptr [rax+rax+00h]
0x1800d4892  mov     rcx, rdi; ho
0x1800d4895  call    cs:__imp_DeleteObject
0x1800d489c  nop     dword ptr [rax+rax+00h]
0x1800d48a1  mov     [r14], ebx
0x1800d48a4  jmp     loc_1800D47B8
```
