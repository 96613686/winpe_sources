# _attribute_t::SetValue(tagOCTET_STRING const *)

- ea: `0x180007e58`
- end: `0x180007f18`
- name: `?SetValue@_attribute_t@@QEAAJPEBUtagOCTET_STRING@@@Z`
- size: `192`
- prototype: `__int64 __fastcall(LPVOID *this, const struct tagOCTET_STRING *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006274`
- `0x18000d100`

## callees

- `0x180002676`
- `0x180007e58`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007ec8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007ec8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007e71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007e91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007e71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007e91`

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
0x180007e58  push    rbx
0x180007e5a  push    rbp
0x180007e5b  push    rsi
0x180007e5c  push    rdi
0x180007e5d  sub     rsp, 28h
0x180007e61  cmp     dword ptr [rcx+8], 0Ah
0x180007e65  mov     rdi, rdx
0x180007e68  mov     rbx, rcx
0x180007e6b  jnz     short loc_180007E87
0x180007e6d  mov     rcx, [rcx+10h]; pv
0x180007e71  call    cs:__imp_CoTaskMemFree
0x180007e78  nop     dword ptr [rax+rax+00h]
0x180007e7d  mov     qword ptr [rbx+10h], 0
0x180007e85  jmp     short loc_180007EAC
0x180007e87  cmp     dword ptr [rcx+8], 0Eh
0x180007e8b  jnz     short loc_180007EAC
0x180007e8d  mov     rcx, [rcx+18h]; pv
0x180007e91  call    cs:__imp_CoTaskMemFree
0x180007e98  nop     dword ptr [rax+rax+00h]
0x180007e9d  mov     qword ptr [rbx+18h], 0
0x180007ea5  mov     dword ptr [rbx+10h], 0
0x180007eac  xor     eax, eax
0x180007eae  test    rdi, rdi
0x180007eb1  jz      short loc_180007F0E
0x180007eb3  lea     rsi, [rbx+10h]
0x180007eb7  test    rsi, rsi
0x180007eba  jz      short loc_180007F02
0x180007ebc  cmp     dword ptr [rdi], 0FFFFh
0x180007ec2  jnb     short loc_180007F02
0x180007ec4  mov     ebp, [rdi]
0x180007ec6  mov     ecx, ebp; cb
0x180007ec8  call    cs:__imp_CoTaskMemAlloc
0x180007ecf  nop     dword ptr [rax+rax+00h]
0x180007ed4  mov     [rsi+8], rax
0x180007ed8  test    rax, rax
0x180007edb  jnz     short loc_180007EE4
0x180007edd  mov     eax, 8007000Eh
0x180007ee2  jmp     short loc_180007F07
0x180007ee4  mov     rdx, [rdi+8]; Src
0x180007ee8  mov     r8, rbp; Size
0x180007eeb  mov     rcx, rax; void *
0x180007eee  call    memcpy_0
0x180007ef3  mov     eax, [rdi]
0x180007ef5  mov     [rsi], eax
0x180007ef7  xor     eax, eax
0x180007ef9  mov     dword ptr [rbx+8], 0Eh
0x180007f00  jmp     short loc_180007F0E
0x180007f02  mov     eax, 80070057h
0x180007f07  mov     dword ptr [rbx+8], 0
0x180007f0e  add     rsp, 28h
0x180007f12  pop     rdi
0x180007f13  pop     rsi
0x180007f14  pop     rbp
0x180007f15  pop     rbx
0x180007f16  retn
```
