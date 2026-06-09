# CCabItemList::CleanList(void)

- ea: `0x18000d968`
- end: `0x18000d9c8`
- name: `?CleanList@CCabItemList@@AEAAXXZ`
- size: `96`
- prototype: `void __fastcall(CCabItemList *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ae98`
- `0x18000d300`
- `0x18000f56c`
- `0x18000fa60`

## callees

- `0x18000d968`
- `0x180012784`
- `0x1800127d0`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x18000d9a1`
- `SHELL32!__imp_ILFree` at `0x18000d9a1`

## pseudocode

```c
void __fastcall CCabItemList::CleanList(CCabItemList *this)
{
  int *v2; // rdi
  int v3; // edi
  ITEMIDLIST *Ptr; // rax
  struct _DPA *v5; // rcx

  if ( *(_DWORD *)this )
  {
    *((_QWORD *)this + 1) = 0;
    *(_DWORD *)this = 0;
  }
  else
  {
    v2 = (int *)*((_QWORD *)this + 1);
    if ( v2 )
    {
      v3 = *v2;
      while ( 1 )
      {
        --v3;
        v5 = (struct _DPA *)*((_QWORD *)this + 1);
        if ( v3 < 0 )
          break;
        Ptr = (ITEMIDLIST *)DPA_GetPtr(v5, (unsigned int)v3);
        ILFree(Ptr);
      }
      DPA_Destroy(v5);
      *((_QWORD *)this + 1) = 0;
    }
  }
}

```

## disassembly

```asm
0x18000d968  mov     [rsp+arg_0], rbx
0x18000d96d  push    rdi
0x18000d96e  sub     rsp, 20h
0x18000d972  cmp     dword ptr [rcx], 0
0x18000d975  mov     rbx, rcx
0x18000d978  jz      short loc_18000D98A
0x18000d97a  mov     qword ptr [rcx+8], 0
0x18000d982  mov     dword ptr [rcx], 0
0x18000d988  jmp     short loc_18000D9BD
0x18000d98a  mov     rdi, [rcx+8]
0x18000d98e  test    rdi, rdi
0x18000d991  jz      short loc_18000D9BD
0x18000d993  mov     edi, [rdi]
0x18000d995  jmp     short loc_18000D9A7
0x18000d997  mov     edx, edi; i
0x18000d999  call    DPA_GetPtr
0x18000d99e  mov     rcx, rax; pidl
0x18000d9a1  call    cs:__imp_ILFree
0x18000d9a7  sub     edi, 1
0x18000d9aa  mov     rcx, [rbx+8]; hdpa
0x18000d9ae  jns     short loc_18000D997
0x18000d9b0  call    DPA_Destroy
0x18000d9b5  mov     qword ptr [rbx+8], 0
0x18000d9bd  mov     rbx, [rsp+28h+arg_0]
0x18000d9c2  add     rsp, 20h
0x18000d9c6  pop     rdi
0x18000d9c7  retn
```
