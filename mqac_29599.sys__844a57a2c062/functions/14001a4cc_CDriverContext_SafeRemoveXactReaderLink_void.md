# CDriverContext::SafeRemoveXactReaderLink(void)

- ea: `0x14001a4cc`
- end: `0x14001a506`
- name: `?SafeRemoveXactReaderLink@CDriverContext@@QEAAXXZ`
- size: `58`
- prototype: `void __fastcall(CDriverContext *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140019e5c`
- `0x14001a598`

## callees

- `0x14001a4cc`

## pseudocode

```c
void __fastcall CDriverContext::SafeRemoveXactReaderLink(CDriverContext ***this)
{
  CDriverContext **v1; // rax
  CDriverContext **v2; // rdx

  if ( ((_DWORD)this[3] & 7) == 2 )
  {
    v1 = *this;
    if ( (*this)[1] != (CDriverContext *)this || (v2 = this[1], *v2 != (CDriverContext *)this) )
      __fastfail(3u);
    *v2 = (CDriverContext *)v1;
    v1[1] = (CDriverContext *)v2;
    *this = 0;
    this[1] = 0;
  }
}

```

## disassembly

```asm
0x14001a4cc  mov     eax, [rcx+18h]
0x14001a4cf  and     al, 7
0x14001a4d1  cmp     al, 2
0x14001a4d3  jnz     short locret_14001A4FD
0x14001a4d5  mov     rax, [rcx]
0x14001a4d8  cmp     [rax+8], rcx
0x14001a4dc  jnz     short loc_14001A4FF
0x14001a4de  mov     rdx, [rcx+8]
0x14001a4e2  cmp     [rdx], rcx
0x14001a4e5  jnz     short loc_14001A4FF
0x14001a4e7  mov     [rdx], rax
0x14001a4ea  mov     [rax+8], rdx
0x14001a4ee  mov     qword ptr [rcx], 0
0x14001a4f5  mov     qword ptr [rcx+8], 0
0x14001a4fd  retn
0x14001a4ff  mov     ecx, 3
0x14001a504  int     29h; Win8: RtlFailFast(ecx)
```
