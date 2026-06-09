# HrBStrToWStr(ushort * const,ushort * *)

- ea: `0x180050cc0`
- end: `0x180050d3e`
- name: `?HrBStrToWStr@@YAJQEAGPEAPEAG@Z`
- size: `126`
- prototype: `__int64 __fastcall(unsigned __int16 *const Src, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180050e60`
- `0x180052144`

## callees

- `0x180050cc0`
- `0x18006141c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180050cfe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180050cfe`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180050ce2`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180050ce2`

## pseudocode

```c
__int64 __fastcall HrBStrToWStr(unsigned __int16 *const Src, unsigned __int16 **a2)
{
  UINT v5; // eax
  size_t v6; // rbx
  unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // r14
  unsigned int v9; // edi

  *a2 = 0;
  if ( !Src )
    return 0;
  v5 = SysStringByteLen(Src);
  v6 = v5 + 2LL;
  if ( v6 < v5 )
    return 2147942934LL;
  v7 = (unsigned __int16 *)CoTaskMemAlloc(v5 + 4LL);
  v8 = v7;
  if ( v7 )
  {
    v9 = 0;
    memcpy_0(v7, Src, v6);
    v8[v6 >> 1] = 0;
    *a2 = v8;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v9;
}

```

## disassembly

```asm
0x180050cc0  push    rbx
0x180050cc2  push    rsi
0x180050cc3  push    rdi
0x180050cc4  push    r14
0x180050cc6  push    r15
0x180050cc8  sub     rsp, 20h
0x180050ccc  mov     qword ptr [rdx], 0
0x180050cd3  mov     r15, rdx
0x180050cd6  mov     rsi, rcx
0x180050cd9  test    rcx, rcx
0x180050cdc  jnz     short loc_180050CE2
0x180050cde  xor     eax, eax
0x180050ce0  jmp     short loc_180050D32
0x180050ce2  call    cs:__imp_SysStringByteLen
0x180050ce8  mov     eax, eax
0x180050cea  lea     rbx, [rax+2]
0x180050cee  cmp     rbx, rax
0x180050cf1  jnb     short loc_180050CFA
0x180050cf3  mov     eax, 80070216h
0x180050cf8  jmp     short loc_180050D32
0x180050cfa  lea     rcx, [rbx+2]; cb
0x180050cfe  call    cs:__imp_CoTaskMemAlloc
0x180050d04  mov     r14, rax
0x180050d07  test    rax, rax
0x180050d0a  jnz     short loc_180050D13
0x180050d0c  mov     edi, 8007000Eh
0x180050d11  jmp     short loc_180050D30
0x180050d13  mov     r8, rbx; Size
0x180050d16  mov     rdx, rsi; Src
0x180050d19  mov     rcx, r14; void *
0x180050d1c  xor     edi, edi
0x180050d1e  call    memcpy_0
0x180050d23  shr     rbx, 1
0x180050d26  xor     ecx, ecx
0x180050d28  mov     [r14+rbx*2], cx
0x180050d2d  mov     [r15], r14
0x180050d30  mov     eax, edi
0x180050d32  add     rsp, 20h
0x180050d36  pop     r15
0x180050d38  pop     r14
0x180050d3a  pop     rdi
0x180050d3b  pop     rsi
0x180050d3c  pop     rbx
0x180050d3d  retn
```
