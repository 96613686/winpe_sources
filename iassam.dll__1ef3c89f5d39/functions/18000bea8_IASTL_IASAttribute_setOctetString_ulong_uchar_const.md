# IASTL::IASAttribute::setOctetString(ulong,uchar const *)

- ea: `0x18000bea8`
- end: `0x18000bf19`
- name: `?setOctetString@IASAttribute@IASTL@@QEAAXKPEBE@Z`
- size: `113`
- prototype: `void __fastcall(IASTL::IASAttribute *__hidden this, size_t Size, const unsigned __int8 *Src)`
- caller_count: `14`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000bf20`
- `0x180013b70`
- `0x180014d20`
- `0x180016938`
- `0x180016d0c`
- `0x180017330`
- `0x180018de4`
- `0x18001aa00`
- `0x18001b958`
- `0x18001c160`
- `0x18001c2a4`
- `0x18001c544`
- `0x18002752c`
- `0x1800276b0`

## callees

- `0x180001f26`
- `0x18000b680`
- `0x18000b81c`
- `0x18000bea8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bec3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bec3`

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
0x18000bea8  push    rbx
0x18000beaa  push    rbp
0x18000beab  push    rsi
0x18000beac  push    rdi
0x18000bead  push    r14
0x18000beaf  sub     rsp, 20h
0x18000beb3  xor     edi, edi
0x18000beb5  mov     esi, edx
0x18000beb7  mov     rbp, r8
0x18000beba  mov     rbx, rcx
0x18000bebd  test    edx, edx
0x18000bebf  jz      short loc_18000BEEF
0x18000bec1  mov     ecx, esi; cb
0x18000bec3  call    cs:__imp_CoTaskMemAlloc
0x18000bec9  mov     rdi, rax
0x18000becc  test    rax, rax
0x18000becf  jnz     short loc_18000BEDC
0x18000bed1  mov     ecx, 8007000Eh; this
0x18000bed6  call    ?issue_error@IASTL@@YAXJ@Z; IASTL::issue_error(long)
0x18000bedc  test    rbp, rbp
0x18000bedf  jz      short loc_18000BEEF
0x18000bee1  mov     r8, rsi; Size
0x18000bee4  mov     rdx, rbp; Src
0x18000bee7  mov     rcx, rax; void *
0x18000beea  call    memcpy_0
0x18000beef  mov     rcx, rbx; this
0x18000bef2  call    ?clearValue@IASAttribute@IASTL@@IEAAXXZ; IASTL::IASAttribute::clearValue(void)
0x18000bef7  mov     rax, [rbx]
0x18000befa  mov     [rax+20h], rdi
0x18000befe  mov     rax, [rbx]
0x18000bf01  mov     [rax+18h], esi
0x18000bf04  mov     rax, [rbx]
0x18000bf07  mov     dword ptr [rax+10h], 6
0x18000bf0e  add     rsp, 20h
0x18000bf12  pop     r14
0x18000bf14  pop     rdi
0x18000bf15  pop     rsi
0x18000bf16  pop     rbp
0x18000bf17  pop     rbx
0x18000bf18  retn
```
