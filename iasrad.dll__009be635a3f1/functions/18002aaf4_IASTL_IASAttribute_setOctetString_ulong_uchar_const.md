# IASTL::IASAttribute::setOctetString(ulong,uchar const *)

- ea: `0x18002aaf4`
- end: `0x18002ab65`
- name: `?setOctetString@IASAttribute@IASTL@@QEAAXKPEBE@Z`
- size: `113`
- prototype: `void __fastcall(IASTL::IASAttribute *__hidden this, size_t Size, const unsigned __int8 *Src)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001b118`
- `0x180024e00`
- `0x180025308`

## callees

- `0x180002106`
- `0x18002a530`
- `0x18002a6bc`
- `0x18002aaf4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ab0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ab0f`

## pseudocode

```c
void __fastcall IASTL::IASAttribute::setOctetString(IASTL::IASAttribute *this, size_t Size, const unsigned __int8 *Src)
{
  void *v3; // rdi
  size_t v4; // rsi
  void *v7; // rax
  int v8; // edx

  v3 = 0;
  v4 = (unsigned int)Size;
  if ( (_DWORD)Size )
  {
    v7 = CoTaskMemAlloc((unsigned int)Size);
    v3 = v7;
    if ( !v7 )
      IASTL::issue_error((IASTL *)0x8007000ELL, v8);
    if ( Src )
      memcpy_0(v7, Src, v4);
  }
  IASTL::IASAttribute::clearValue(this);
  *(_QWORD *)(*(_QWORD *)this + 32LL) = v3;
  *(_DWORD *)(*(_QWORD *)this + 24LL) = v4;
  *(_DWORD *)(*(_QWORD *)this + 16LL) = 6;
}

```

## disassembly

```asm
0x18002aaf4  push    rbx
0x18002aaf6  push    rbp
0x18002aaf7  push    rsi
0x18002aaf8  push    rdi
0x18002aaf9  push    r14
0x18002aafb  sub     rsp, 20h
0x18002aaff  xor     edi, edi
0x18002ab01  mov     esi, edx
0x18002ab03  mov     rbp, r8
0x18002ab06  mov     rbx, rcx
0x18002ab09  test    edx, edx
0x18002ab0b  jz      short loc_18002AB3B
0x18002ab0d  mov     ecx, esi; cb
0x18002ab0f  call    cs:__imp_CoTaskMemAlloc
0x18002ab15  mov     rdi, rax
0x18002ab18  test    rax, rax
0x18002ab1b  jnz     short loc_18002AB28
0x18002ab1d  mov     ecx, 8007000Eh; this
0x18002ab22  call    ?issue_error@IASTL@@YAXJ@Z; IASTL::issue_error(long)
0x18002ab28  test    rbp, rbp
0x18002ab2b  jz      short loc_18002AB3B
0x18002ab2d  mov     r8, rsi; Size
0x18002ab30  mov     rdx, rbp; Src
0x18002ab33  mov     rcx, rax; void *
0x18002ab36  call    memcpy_0
0x18002ab3b  mov     rcx, rbx; this
0x18002ab3e  call    ?clearValue@IASAttribute@IASTL@@IEAAXXZ; IASTL::IASAttribute::clearValue(void)
0x18002ab43  mov     rax, [rbx]
0x18002ab46  mov     [rax+20h], rdi
0x18002ab4a  mov     rax, [rbx]
0x18002ab4d  mov     [rax+18h], esi
0x18002ab50  mov     rax, [rbx]
0x18002ab53  mov     dword ptr [rax+10h], 6
0x18002ab5a  add     rsp, 20h
0x18002ab5e  pop     r14
0x18002ab60  pop     rdi
0x18002ab61  pop     rsi
0x18002ab62  pop     rbp
0x18002ab63  pop     rbx
0x18002ab64  retn
```
