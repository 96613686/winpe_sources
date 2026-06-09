# CUIFButton::GetIconSize(HICON__ *,tagSIZE *)

- ea: `0x180102e1c`
- end: `0x180102ea6`
- name: `?GetIconSize@CUIFButton@@IEAAXPEAUHICON__@@PEAUtagSIZE@@@Z`
- size: `138`
- prototype: `void(CUIFButton *__hidden this, HICON, struct tagSIZE *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180103e98`

## callees

- `0x180102e1c`

## import_xrefs

- `USER32!GetIconInfo` at `0x180102e44`
- `USER32!GetIconInfo` at `0x180102e44`
- `USER32!GetSystemMetrics` at `0x180102e8a`
- `USER32!GetSystemMetrics` at `0x180102e97`
- `USER32!GetSystemMetrics` at `0x180102e8a`
- `USER32!GetSystemMetrics` at `0x180102e97`
- `GDI32!DeleteObject` at `0x180102e68`
- `GDI32!DeleteObject` at `0x180102e73`
- `GDI32!DeleteObject` at `0x180102e68`
- `GDI32!DeleteObject` at `0x180102e73`
- `GDI32!GetObjectW` at `0x180102e5d`
- `GDI32!GetObjectW` at `0x180102e5d`

## pseudocode

```c
void __fastcall CUIFButton::GetIconSize(CUIFButton *this, HICON a2, struct tagSIZE *a3)
{
  LONG SystemMetrics; // eax
  ICONINFO v5; // [rsp+20h] [rbp-48h] BYREF
  _DWORD pv[10]; // [rsp+40h] [rbp-28h] BYREF

  memset(&v5, 0, sizeof(v5));
  memset(pv, 0, 32);
  if ( GetIconInfo(a2, &v5) )
  {
    GetObjectW(v5.hbmColor, 32, pv);
    DeleteObject(v5.hbmColor);
    DeleteObject(v5.hbmMask);
    a3->cx = pv[1];
    SystemMetrics = pv[2];
  }
  else
  {
    a3->cx = GetSystemMetrics(49);
    SystemMetrics = GetSystemMetrics(50);
  }
  a3->cy = SystemMetrics;
}

```

## disassembly

```asm
0x180102e1c  mov     rax, rsp
0x180102e1f  push    rbx
0x180102e20  sub     rsp, 60h
0x180102e24  xorps   xmm0, xmm0
0x180102e27  xorps   xmm1, xmm1
0x180102e2a  mov     rcx, rdx; hIcon
0x180102e2d  mov     rbx, r8
0x180102e30  lea     rdx, [rax-48h]; piconinfo
0x180102e34  movups  xmmword ptr [rax-48h], xmm0
0x180102e38  movups  xmmword ptr [rax-38h], xmm0
0x180102e3c  movups  xmmword ptr [rax-28h], xmm1
0x180102e40  movups  xmmword ptr [rax-18h], xmm1
0x180102e44  call    cs:__imp_GetIconInfo
0x180102e4a  test    eax, eax
0x180102e4c  jz      short loc_180102E85
0x180102e4e  mov     rcx, [rsp+68h+h]; h
0x180102e53  lea     r8, [rsp+68h+pv]; pv
0x180102e58  mov     edx, 20h ; ' '; c
0x180102e5d  call    cs:__imp_GetObjectW
0x180102e63  mov     rcx, [rsp+68h+h]; ho
0x180102e68  call    cs:__imp_DeleteObject
0x180102e6e  mov     rcx, [rsp+68h+ho]; ho
0x180102e73  call    cs:__imp_DeleteObject
0x180102e79  mov     eax, [rsp+68h+var_24]
0x180102e7d  mov     [rbx], eax
0x180102e7f  mov     eax, [rsp+68h+var_20]
0x180102e83  jmp     short loc_180102E9D
0x180102e85  mov     ecx, 31h ; '1'; nIndex
0x180102e8a  call    cs:__imp_GetSystemMetrics
0x180102e90  mov     ecx, 32h ; '2'; nIndex
0x180102e95  mov     [rbx], eax
0x180102e97  call    cs:__imp_GetSystemMetrics
0x180102e9d  mov     [rbx+4], eax
0x180102ea0  add     rsp, 60h
0x180102ea4  pop     rbx
0x180102ea5  retn
```
