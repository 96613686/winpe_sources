# MemoryDC::MemoryDC(HDC__ *)

- ea: `0x18020c2c0`
- end: `0x18020c318`
- name: `??0MemoryDC@@QEAA@PEAUHDC__@@@Z`
- size: `88`
- prototype: `MemoryDC *__fastcall(MemoryDC *__hidden this, HDC)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801eb5bc`

## callees

- `0x18020bc10`
- `0x18020c2c0`
- `0x18020c3b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18020c2d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18020c2d6`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x18020c2de`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x18020c2de`

## pseudocode

```c
MemoryDC *__fastcall MemoryDC::MemoryDC(MemoryDC *this, HDC a2)
{
  HDC CompatibleDC; // rax
  GdiException *v4; // rax
  HDC v6; // [rsp+38h] [rbp+10h] BYREF

  v6 = a2;
  *(_QWORD *)this = 0;
  SetLastError(0);
  CompatibleDC = CreateCompatibleDC(0);
  *(_QWORD *)this = CompatibleDC;
  if ( !CompatibleDC )
  {
    v4 = GdiException::GdiException((GdiException *)&v6);
    LogAndThrow<GdiException>(v4, 0x43446D656DLL, 21);
  }
  return this;
}

```

## disassembly

```asm
0x18020c2c0  mov     [rsp+arg_8], rdx
0x18020c2c5  push    rbx
0x18020c2c6  sub     rsp, 20h
0x18020c2ca  mov     rbx, rcx
0x18020c2cd  mov     qword ptr [rcx], 0
0x18020c2d4  xor     ecx, ecx; dwErrCode
0x18020c2d6  call    cs:__imp_SetLastError
0x18020c2dc  xor     ecx, ecx; hdc
0x18020c2de  call    cs:__imp_CreateCompatibleDC
0x18020c2e4  mov     [rbx], rax
0x18020c2e7  test    rax, rax
0x18020c2ea  jnz     short loc_18020C30F
0x18020c2ec  lea     rcx, [rsp+28h+arg_8]; this
0x18020c2f1  call    ??0GdiException@@QEAA@XZ; GdiException::GdiException(void)
0x18020c2f6  mov     rdx, 43446D656Dh
0x18020c300  mov     r8d, 15h
0x18020c306  mov     rcx, rax
0x18020c309  call    ??$LogAndThrow@VGdiException@@@@YAXAEBVGdiException@@VEventTag@@I@Z; LogAndThrow<GdiException>(GdiException const &,EventTag,uint)
0x18020c30f  mov     rax, rbx
0x18020c312  add     rsp, 20h
0x18020c316  pop     rbx
0x18020c317  retn
```
