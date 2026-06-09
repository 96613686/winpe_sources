# CddBitmapSw::StopGdiAccessNoUpdate(CDDBITMAP_GDIDESC *)

- ea: `0x140019390`
- end: `0x1400193a0`
- name: `?StopGdiAccessNoUpdate@CddBitmapSw@@UEAAXPEAUCDDBITMAP_GDIDESC@@@Z`
- size: `16`
- prototype: `void __fastcall(CddBitmapSw *__hidden this, struct CDDBITMAP_GDIDESC *)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## pseudocode

```c
void __fastcall CddBitmapSw::StopGdiAccessNoUpdate(CddBitmapSw *this, struct CDDBITMAP_GDIDESC *a2)
{
  *(_QWORD *)a2 = 0;
  *((_DWORD *)a2 + 4) = 0;
  *((_QWORD *)a2 + 3) = 0;
  *((_DWORD *)a2 + 8) = 0;
}

```

## disassembly

```asm
0x140019390  xor     eax, eax
0x140019392  mov     [rdx], rax
0x140019395  mov     [rdx+10h], eax
0x140019398  mov     [rdx+18h], rax
0x14001939c  mov     [rdx+20h], eax
0x14001939f  retn
```
