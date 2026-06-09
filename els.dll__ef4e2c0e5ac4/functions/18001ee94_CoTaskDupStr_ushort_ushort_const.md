# CoTaskDupStr(ushort * *,ushort const *)

- ea: `0x18001ee94`
- end: `0x18001eeeb`
- name: `?CoTaskDupStr@@YAJPEAPEAGPEBG@Z`
- size: `87`
- prototype: `int(unsigned __int16 **, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180004010`
- `0x180004080`
- `0x180004140`

## callees

- `0x18001ee94`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18001eed3`
- `msvcrt!wcscpy_s` at `0x18001eed3`
- `ole32!CoTaskMemAlloc` at `0x18001eeba`
- `ole32!CoTaskMemAlloc` at `0x18001eeba`

## pseudocode

```c
__int64 __fastcall CoTaskDupStr(unsigned __int16 **a1, const unsigned __int16 *a2)
{
  __int64 v2; // rax
  rsize_t v5; // rsi
  unsigned __int16 *v6; // rax
  unsigned int v7; // ebx

  v2 = -1;
  do
    ++v2;
  while ( a2[v2] );
  v5 = v2 + 1;
  v6 = (unsigned __int16 *)CoTaskMemAlloc(2 * (v2 + 1));
  *a1 = v6;
  if ( v6 )
  {
    v7 = 0;
    wcscpy_s(v6, v5, a2);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v7;
}

```

## disassembly

```asm
0x18001ee94  push    rbx
0x18001ee96  push    rbp
0x18001ee97  push    rsi
0x18001ee98  push    rdi
0x18001ee99  sub     rsp, 28h
0x18001ee9d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001eea1  mov     rdi, rdx
0x18001eea4  xor     ebp, ebp
0x18001eea6  mov     rbx, rcx
0x18001eea9  inc     rax
0x18001eeac  cmp     [rdx+rax*2], bp
0x18001eeb0  jnz     short loc_18001EEA9
0x18001eeb2  lea     rsi, [rax+1]
0x18001eeb6  lea     rcx, [rsi+rsi]; cb
0x18001eeba  call    cs:__imp_CoTaskMemAlloc
0x18001eec0  mov     [rbx], rax
0x18001eec3  test    rax, rax
0x18001eec6  jz      short loc_18001EEDB
0x18001eec8  mov     r8, rdi; Source
0x18001eecb  mov     rdx, rsi; SizeInWords
0x18001eece  mov     rcx, rax; Destination
0x18001eed1  mov     ebx, ebp
0x18001eed3  call    cs:__imp_wcscpy_s
0x18001eed9  jmp     short loc_18001EEE0
0x18001eedb  mov     ebx, 8007000Eh
0x18001eee0  mov     eax, ebx
0x18001eee2  add     rsp, 28h
0x18001eee6  pop     rdi
0x18001eee7  pop     rsi
0x18001eee8  pop     rbp
0x18001eee9  pop     rbx
0x18001eeea  retn
```
