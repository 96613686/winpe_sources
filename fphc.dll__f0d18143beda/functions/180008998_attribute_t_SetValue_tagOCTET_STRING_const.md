# _attribute_t::SetValue(tagOCTET_STRING const *)

- ea: `0x180008998`
- end: `0x180008a45`
- name: `?SetValue@_attribute_t@@QEAAJPEBUtagOCTET_STRING@@@Z`
- size: `173`
- prototype: `__int64 __fastcall(_attribute_t *__hidden this, const struct tagOCTET_STRING *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006160`
- `0x18000a38c`

## callees

- `0x1800026e6`
- `0x180008998`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800089b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800089cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800089b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800089cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800089fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800089fc`

## pseudocode

```c
__int64 __fastcall _attribute_t::SetValue(LPVOID *this, const struct tagOCTET_STRING *a2)
{
  __int64 result; // rax
  SIZE_T dwLength; // rbp
  void *v6; // rax

  if ( *((_DWORD *)this + 2) == 10 )
  {
    CoTaskMemFree(this[2]);
    this[2] = 0;
  }
  else if ( *((_DWORD *)this + 2) == 14 )
  {
    CoTaskMemFree(this[3]);
    this[3] = 0;
    *((_DWORD *)this + 4) = 0;
  }
  result = 0;
  if ( a2 )
  {
    if ( this == (LPVOID *)-16LL || a2->dwLength >= 0xFFFF )
    {
      result = 2147942487LL;
    }
    else
    {
      dwLength = a2->dwLength;
      v6 = CoTaskMemAlloc(dwLength);
      this[3] = v6;
      if ( v6 )
      {
        memcpy_0(v6, a2->lpValue, dwLength);
        *((_DWORD *)this + 4) = a2->dwLength;
        result = 0;
        *((_DWORD *)this + 2) = 14;
        return result;
      }
      result = 2147942414LL;
    }
    *((_DWORD *)this + 2) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180008998  push    rbx
0x18000899a  push    rbp
0x18000899b  push    rsi
0x18000899c  push    rdi
0x18000899d  sub     rsp, 28h
0x1800089a1  cmp     dword ptr [rcx+8], 0Ah
0x1800089a5  mov     rdi, rdx
0x1800089a8  mov     rbx, rcx
0x1800089ab  jnz     short loc_1800089C1
0x1800089ad  mov     rcx, [rcx+10h]; pv
0x1800089b1  call    cs:__imp_CoTaskMemFree
0x1800089b7  mov     qword ptr [rbx+10h], 0
0x1800089bf  jmp     short loc_1800089E0
0x1800089c1  cmp     dword ptr [rcx+8], 0Eh
0x1800089c5  jnz     short loc_1800089E0
0x1800089c7  mov     rcx, [rcx+18h]; pv
0x1800089cb  call    cs:__imp_CoTaskMemFree
0x1800089d1  mov     qword ptr [rbx+18h], 0
0x1800089d9  mov     dword ptr [rbx+10h], 0
0x1800089e0  xor     eax, eax
0x1800089e2  test    rdi, rdi
0x1800089e5  jz      short loc_180008A3C
0x1800089e7  lea     rsi, [rbx+10h]
0x1800089eb  test    rsi, rsi
0x1800089ee  jz      short loc_180008A30
0x1800089f0  cmp     dword ptr [rdi], 0FFFFh
0x1800089f6  jnb     short loc_180008A30
0x1800089f8  mov     ebp, [rdi]
0x1800089fa  mov     ecx, ebp; cb
0x1800089fc  call    cs:__imp_CoTaskMemAlloc
0x180008a02  mov     [rsi+8], rax
0x180008a06  test    rax, rax
0x180008a09  jnz     short loc_180008A12
0x180008a0b  mov     eax, 8007000Eh
0x180008a10  jmp     short loc_180008A35
0x180008a12  mov     rdx, [rdi+8]; Src
0x180008a16  mov     r8, rbp; Size
0x180008a19  mov     rcx, rax; void *
0x180008a1c  call    memcpy_0
0x180008a21  mov     eax, [rdi]
0x180008a23  mov     [rsi], eax
0x180008a25  xor     eax, eax
0x180008a27  mov     dword ptr [rbx+8], 0Eh
0x180008a2e  jmp     short loc_180008A3C
0x180008a30  mov     eax, 80070057h
0x180008a35  mov     dword ptr [rbx+8], 0
0x180008a3c  add     rsp, 28h
0x180008a40  pop     rdi
0x180008a41  pop     rsi
0x180008a42  pop     rbp
0x180008a43  pop     rbx
0x180008a44  retn
```
