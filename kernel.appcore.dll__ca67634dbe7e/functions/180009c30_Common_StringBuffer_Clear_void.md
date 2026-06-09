# Common::StringBuffer::Clear(void)

- ea: `0x180009c30`
- end: `0x180009c45`
- name: `?Clear@StringBuffer@Common@@QEAAXXZ`
- size: `21`
- prototype: `void __fastcall(Common::StringBuffer *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001ef0`
- `0x1800020d0`
- `0x180002850`

## callees

- `0x180009c30`

## pseudocode

```c
void __fastcall Common::StringBuffer::Clear(Common::StringBuffer *this)
{
  _WORD *v1; // rdx

  v1 = (_WORD *)*((_QWORD *)this + 1);
  if ( v1 )
    *v1 = 0;
  *(_DWORD *)this = 0;
}

```

## disassembly

```asm
0x180009c30  mov     rdx, [rcx+8]
0x180009c34  test    rdx, rdx
0x180009c37  jz      short loc_180009C3E
0x180009c39  xor     eax, eax
0x180009c3b  mov     [rdx], ax
0x180009c3e  mov     dword ptr [rcx], 0
0x180009c44  retn
```
