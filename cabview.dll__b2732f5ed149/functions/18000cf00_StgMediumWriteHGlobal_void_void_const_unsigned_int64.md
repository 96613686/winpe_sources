# StgMediumWriteHGlobal(void * *,void const *,unsigned __int64)

- ea: `0x18000cf00`
- end: `0x18000cf4f`
- name: `?StgMediumWriteHGlobal@@YAJPEAPEAXPEBX_K@Z`
- size: `79`
- prototype: `__int64 __fastcall(void **, _DWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ba40`
- `0x18000c714`

## callees

- `0x18000cf00`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cf29`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cf29`

## pseudocode

```c
__int64 __fastcall StgMediumWriteHGlobal(void **a1, _DWORD *a2)
{
  unsigned int v4; // edi
  _DWORD *v5; // rax

  *a1 = 0;
  v4 = -2147024882;
  v5 = LocalAlloc(0x40u, 4u);
  *a1 = v5;
  if ( v5 )
  {
    v4 = 0;
    *v5 = *a2;
  }
  return v4;
}

```

## disassembly

```asm
0x18000cf00  mov     [rsp+arg_0], rbx
0x18000cf05  mov     [rsp+arg_8], rsi
0x18000cf0a  push    rdi
0x18000cf0b  sub     rsp, 20h
0x18000cf0f  mov     rsi, rdx
0x18000cf12  mov     qword ptr [rcx], 0
0x18000cf19  mov     edx, 4; uBytes
0x18000cf1e  mov     rbx, rcx
0x18000cf21  mov     edi, 8007000Eh
0x18000cf26  lea     ecx, [rdx+3Ch]; uFlags
0x18000cf29  call    cs:__imp_LocalAlloc
0x18000cf2f  mov     [rbx], rax
0x18000cf32  test    rax, rax
0x18000cf35  jz      short loc_18000CF3D
0x18000cf37  mov     ecx, [rsi]
0x18000cf39  xor     edi, edi
0x18000cf3b  mov     [rax], ecx
0x18000cf3d  mov     rbx, [rsp+28h+arg_0]
0x18000cf42  mov     eax, edi
0x18000cf44  mov     rsi, [rsp+28h+arg_8]
0x18000cf49  add     rsp, 20h
0x18000cf4d  pop     rdi
0x18000cf4e  retn
```
