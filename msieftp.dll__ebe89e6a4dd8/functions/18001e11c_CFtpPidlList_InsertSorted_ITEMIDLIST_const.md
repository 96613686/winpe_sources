# CFtpPidlList::InsertSorted(_ITEMIDLIST const *)

- ea: `0x18001e11c`
- end: `0x18001e1a7`
- name: `?InsertSorted@CFtpPidlList@@QEAAJPEFBU_ITEMIDLIST@@@Z`
- size: `139`
- prototype: `int(CFtpPidlList *__hidden this, const struct _ITEMIDLIST *)`
- caller_count: `11`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001237c`
- `0x180014834`
- `0x1800159c4`
- `0x18001a010`
- `0x18001a2a0`
- `0x18001ddf4`
- `0x18001e2d4`
- `0x18001e8e4`
- `0x1800224f0`
- `0x180024378`
- `0x180024638`

## callees

- `0x18001e11c`
- `0x180026a4c`
- `0x180026ab8`

## import_xrefs

- `SHELL32!__imp_ILClone` at `0x18001e13d`
- `SHELL32!__imp_ILClone` at `0x18001e13d`
- `SHELL32!__imp_ILFree` at `0x18001e18f`
- `SHELL32!__imp_ILFree` at `0x18001e18f`

## pseudocode

```c
__int64 __fastcall CFtpPidlList::InsertSorted(CFtpPidlList *this, const struct _ITEMIDLIST *a2)
{
  unsigned int v3; // edi
  LPITEMIDLIST v4; // rax
  ITEMIDLIST *v5; // rsi
  __int64 v6; // rbx
  int v7; // eax

  v3 = -2147024882;
  if ( *((_QWORD *)this + 2) )
  {
    v4 = ILClone(a2);
    v5 = v4;
    if ( v4 )
    {
      v6 = *((_QWORD *)this + 2);
      v7 = DPA_Search(*(HDPA *)(v6 + 16), v4, 0, CFtpPidlList::ComparePidlName, 0, 3u);
      if ( DPA_InsertPtr(*(HDPA *)(v6 + 16), v7, v5) < 0 )
        ILFree(v5);
      else
        return 0;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18001e11c  mov     [rsp+arg_0], rbx
0x18001e121  mov     [rsp+arg_8], rsi
0x18001e126  push    rdi
0x18001e127  sub     rsp, 30h
0x18001e12b  cmp     qword ptr [rcx+10h], 0
0x18001e130  mov     rbx, rcx
0x18001e133  mov     edi, 8007000Eh
0x18001e138  jz      short loc_18001E195
0x18001e13a  mov     rcx, rdx; pidl
0x18001e13d  call    cs:__imp_ILClone
0x18001e143  mov     rsi, rax
0x18001e146  test    rax, rax
0x18001e149  jz      short loc_18001E195
0x18001e14b  mov     rbx, [rbx+10h]
0x18001e14f  lea     r9, ?ComparePidlName@CFtpPidlList@@SAHPEAX0_J@Z; pfnCompare
0x18001e156  mov     [rsp+38h+options], 3; options
0x18001e15e  xor     r8d, r8d; iStart
0x18001e161  mov     rdx, rax; pFind
0x18001e164  mov     [rsp+38h+lParam], 0; lParam
0x18001e16d  mov     rcx, [rbx+10h]; hdpa
0x18001e171  call    DPA_Search
0x18001e176  mov     rcx, [rbx+10h]; hdpa
0x18001e17a  mov     r8, rsi; p
0x18001e17d  mov     edx, eax; i
0x18001e17f  call    DPA_InsertPtr
0x18001e184  test    eax, eax
0x18001e186  js      short loc_18001E18C
0x18001e188  xor     edi, edi
0x18001e18a  jmp     short loc_18001E195
0x18001e18c  mov     rcx, rsi; pidl
0x18001e18f  call    cs:__imp_ILFree
0x18001e195  mov     rbx, [rsp+38h+arg_0]
0x18001e19a  mov     eax, edi
0x18001e19c  mov     rsi, [rsp+38h+arg_8]
0x18001e1a1  add     rsp, 30h
0x18001e1a5  pop     rdi
0x18001e1a6  retn
```
