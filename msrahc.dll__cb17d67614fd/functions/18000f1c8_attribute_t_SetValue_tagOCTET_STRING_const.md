# _attribute_t::SetValue(tagOCTET_STRING const *)

- ea: `0x18000f1c8`
- end: `0x18000f240`
- name: `?SetValue@_attribute_t@@QEAAJPEBUtagOCTET_STRING@@@Z`
- size: `120`
- prototype: `__int64 __fastcall(LPVOID *this, const struct tagOCTET_STRING *)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d188`
- `0x18000d274`
- `0x18000f450`

## callees

- `0x1800021c6`
- `0x18000d4d0`
- `0x18000f1c8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f1f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f1f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _attribute_t::SetValue(LPVOID *this, const struct tagOCTET_STRING *a2)
{
  __int64 result; // rax
  SIZE_T dwLength; // rbp
  void *v6; // rax
  int v7; // ecx

  _attribute_t::FreeValue(this);
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
      }
      else
      {
        result = 2147942414LL;
      }
    }
    v7 = 0;
    if ( (int)result >= 0 )
      v7 = 14;
    *((_DWORD *)this + 2) = v7;
  }
  return result;
}

```

## disassembly

```asm
0x18000f1c8  push    rbx
0x18000f1ca  push    rbp
0x18000f1cb  push    rsi
0x18000f1cc  push    rdi
0x18000f1cd  sub     rsp, 28h
0x18000f1d1  mov     rbx, rdx
0x18000f1d4  mov     rsi, rcx
0x18000f1d7  call    ?FreeValue@_attribute_t@@QEAAXXZ; _attribute_t::FreeValue(void)
0x18000f1dc  xor     eax, eax
0x18000f1de  test    rbx, rbx
0x18000f1e1  jz      short loc_18000F237
0x18000f1e3  lea     rdi, [rsi+10h]
0x18000f1e7  test    rdi, rdi
0x18000f1ea  jz      short loc_18000F225
0x18000f1ec  cmp     dword ptr [rbx], 0FFFFh
0x18000f1f2  jnb     short loc_18000F225
0x18000f1f4  mov     ebp, [rbx]
0x18000f1f6  mov     ecx, ebp; cb
0x18000f1f8  call    cs:__imp_CoTaskMemAlloc
0x18000f1fe  mov     [rdi+8], rax
0x18000f202  test    rax, rax
0x18000f205  jnz     short loc_18000F20E
0x18000f207  mov     eax, 8007000Eh
0x18000f20c  jmp     short loc_18000F22A
0x18000f20e  mov     rdx, [rbx+8]; Src
0x18000f212  mov     r8, rbp; Size
0x18000f215  mov     rcx, rax; void *
0x18000f218  call    memcpy_0
0x18000f21d  mov     eax, [rbx]
0x18000f21f  mov     [rdi], eax
0x18000f221  xor     eax, eax
0x18000f223  jmp     short loc_18000F22A
0x18000f225  mov     eax, 80070057h
0x18000f22a  xor     ecx, ecx
0x18000f22c  test    eax, eax
0x18000f22e  lea     edx, [rcx+0Eh]
0x18000f231  cmovns  ecx, edx
0x18000f234  mov     [rsi+8], ecx
0x18000f237  add     rsp, 28h
0x18000f23b  pop     rdi
0x18000f23c  pop     rsi
0x18000f23d  pop     rbp
0x18000f23e  pop     rbx
0x18000f23f  retn
```
