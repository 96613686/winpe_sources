# DriverGdi::SetupClipping(HDC__ *,DpContext *,GpRuntime::GpRect const *,int &,int &,int)

- ea: `0x180022e40`
- end: `0x180022f30`
- name: `?SetupClipping@DriverGdi@@UEAAXPEAUHDC__@@PEAVDpContext@@PEBVGpRect@GpRuntime@@AEAH3H@Z`
- size: `240`
- prototype: `void(DriverGdi *__hidden this, HDC, struct DpContext *, const struct GpRuntime::GpRect *, int *, int *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x18001af90`
- `0x180022e40`
- `0x180024908`
- `0x180024ce8`

## import_xrefs

- `GDI32!ExtSelectClipRgn` at `0x180022efb`
- `GDI32!ExtSelectClipRgn` at `0x180022efb`
- `GDI32!SaveDC` at `0x180022ee1`
- `GDI32!SaveDC` at `0x180022ee1`
- `GDI32!DeleteObject` at `0x180022eba`
- `GDI32!DeleteObject` at `0x180022eba`

## pseudocode

```c
void __fastcall DriverGdi::SetupClipping(
        DriverGdi *this,
        HDC a2,
        struct DpContext *a3,
        const struct GpRuntime::GpRect *a4,
        int *a5,
        int *a6,
        int a7)
{
  DpRegion *v7; // rsi
  HGDIOBJ *v10; // rbx
  DpRegion *v11; // rcx
  __int64 HRgn; // rax

  v7 = (struct DpContext *)((char *)a3 + 304);
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
    v10 = (HGDIOBJ *)((char *)this + 96);
    if ( (unsigned int)DpRegion::GetUniqueness(v7) == *((_DWORD *)this + 22) )
    {
      if ( *v10 )
        goto LABEL_7;
    }
    if ( *v10 )
      DeleteObject(*v10);
    *((_DWORD *)this + 22) = DpRegion::GetUniqueness(v7);
    HRgn = DpRegion::GetHRgn(v11);
    *v10 = (HGDIOBJ)HRgn;
    if ( HRgn )
    {
LABEL_7:
      SaveDC(a2);
      ExtSelectClipRgn(a2, (HRGN)*v10, 1);
      *a5 = 1;
    }
  }
}

```

## disassembly

```asm
0x180022e40  mov     rax, rsp
0x180022e43  mov     [rax+8], rbx
0x180022e47  mov     [rax+10h], rbp
0x180022e4b  mov     [rax+18h], rsi
0x180022e4f  mov     [rax+20h], rdi
0x180022e53  push    r14
0x180022e55  sub     rsp, 30h
0x180022e59  mov     r14, [rsp+38h+arg_20]
0x180022e5e  lea     rsi, [r8+130h]
0x180022e65  mov     rbp, rdx
0x180022e68  mov     rdi, rcx
0x180022e6b  and     dword ptr [r14], 0
0x180022e6f  cmp     [rsp+38h+arg_30], 0
0x180022e74  jnz     short loc_180022EA1
0x180022e76  mov     r8d, [r9+4]
0x180022e7a  mov     rcx, rsi
0x180022e7d  mov     r10d, [r9+0Ch]
0x180022e81  mov     edx, [r9]
0x180022e84  add     r10d, r8d
0x180022e87  mov     r9d, [r9+8]
0x180022e8b  and     qword ptr [rax-10h], 0
0x180022e90  add     r9d, edx
0x180022e93  mov     [rax-18h], r10d
0x180022e97  call    ?GetRectVisibility@DpRegion@@QEAA?AW4Visibility@1@HHHHPEAVGpRect@GpRuntime@@@Z; DpRegion::GetRectVisibility(int,int,int,int,GpRuntime::GpRect *)
0x180022e9c  cmp     eax, 3
0x180022e9f  jz      short loc_180022F0A
0x180022ea1  mov     rcx, rsi; this
0x180022ea4  call    ?GetUniqueness@DpRegion@@QEBAHXZ; DpRegion::GetUniqueness(void)
0x180022ea9  lea     rbx, [rdi+60h]
0x180022ead  cmp     eax, [rdi+58h]
0x180022eb0  jz      short loc_180022F26
0x180022eb2  mov     rcx, [rbx]; ho
0x180022eb5  test    rcx, rcx
0x180022eb8  jz      short loc_180022EC6
0x180022eba  call    cs:__imp_DeleteObject
0x180022ec1  nop     dword ptr [rax+rax+00h]
0x180022ec6  mov     rcx, rsi; this
0x180022ec9  call    ?GetUniqueness@DpRegion@@QEBAHXZ; DpRegion::GetUniqueness(void)
0x180022ece  mov     [rdi+58h], eax
0x180022ed1  call    ?GetHRgn@DpRegion@@QEBAPEAUHRGN__@@XZ; DpRegion::GetHRgn(void)
0x180022ed6  mov     [rbx], rax
0x180022ed9  test    rax, rax
0x180022edc  jz      short loc_180022F0A
0x180022ede  mov     rcx, rbp; hdc
0x180022ee1  call    cs:__imp_SaveDC
0x180022ee8  nop     dword ptr [rax+rax+00h]
0x180022eed  mov     rdx, [rbx]; hrgn
0x180022ef0  mov     edi, 1
0x180022ef5  mov     r8d, edi; mode
0x180022ef8  mov     rcx, rbp; hdc
0x180022efb  call    cs:__imp_ExtSelectClipRgn
0x180022f02  nop     dword ptr [rax+rax+00h]
0x180022f07  mov     [r14], edi
0x180022f0a  mov     rbx, [rsp+38h+arg_0]
0x180022f0f  mov     rbp, [rsp+38h+arg_8]
0x180022f14  mov     rsi, [rsp+38h+arg_10]
0x180022f19  mov     rdi, [rsp+38h+arg_18]
0x180022f1e  add     rsp, 30h
0x180022f22  pop     r14
0x180022f24  retn
0x180022f26  mov     rax, [rbx]
0x180022f29  test    rax, rax
0x180022f2c  jz      short loc_180022EB2
0x180022f2e  jmp     short loc_180022EDE
```
