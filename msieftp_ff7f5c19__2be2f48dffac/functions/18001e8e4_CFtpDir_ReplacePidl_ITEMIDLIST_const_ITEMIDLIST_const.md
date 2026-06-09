# CFtpDir::ReplacePidl(_ITEMIDLIST const *,_ITEMIDLIST const *)

- ea: `0x18001e8e4`
- end: `0x18001e97d`
- name: `?ReplacePidl@CFtpDir@@QEAAJPEFBU_ITEMIDLIST@@0@Z`
- size: `153`
- prototype: `int(CFtpDir *__hidden this, const struct _ITEMIDLIST *, const struct _ITEMIDLIST *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001ea10`
- `0x180024378`

## callees

- `0x18001e11c`
- `0x18001e8e4`
- `0x180026884`
- `0x1800269f4`
- `0x180026ab8`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x18001e950`
- `SHELL32!__imp_ILFree` at `0x18001e950`

## pseudocode

```c
__int64 __fastcall CFtpDir::ReplacePidl(CFtpDir *this, struct _ITEMIDLIST *a2, const struct _ITEMIDLIST *a3)
{
  CFtpPidlList *v3; // rbx
  __int64 v6; // rcx
  unsigned int v7; // edi
  int v8; // eax
  int v9; // esi
  __int64 v10; // rcx
  ITEMIDLIST *Ptr; // rax

  v3 = (CFtpPidlList *)*((_QWORD *)this + 3);
  if ( !v3 )
    return 0;
  v6 = *((_QWORD *)v3 + 2);
  v7 = 1;
  if ( v6 )
  {
    v8 = DPA_Search(*(HDPA *)(v6 + 16), a2, 0, CFtpPidlList::ComparePidlName, 0, 1u);
    v9 = v8;
    if ( v8 != -1 )
    {
      v10 = *((_QWORD *)v3 + 2);
      if ( v10 )
      {
        Ptr = (ITEMIDLIST *)DPA_GetPtr(*(HDPA *)(v10 + 16), v8);
        if ( Ptr )
        {
          ILFree(Ptr);
          DPA_DeletePtr(*(HDPA *)(*((_QWORD *)v3 + 2) + 16LL), v9);
          CFtpPidlList::InsertSorted(v3, a3);
          return 0;
        }
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18001e8e4  push    rbx
0x18001e8e6  push    rbp
0x18001e8e7  push    rsi
0x18001e8e8  push    rdi
0x18001e8e9  sub     rsp, 38h
0x18001e8ed  mov     rbx, [rcx+18h]
0x18001e8f1  mov     rbp, r8
0x18001e8f4  test    rbx, rbx
0x18001e8f7  jnz     short loc_18001E8FD
0x18001e8f9  xor     eax, eax
0x18001e8fb  jmp     short loc_18001E974
0x18001e8fd  mov     rcx, [rbx+10h]
0x18001e901  mov     edi, 1
0x18001e906  test    rcx, rcx
0x18001e909  jz      short loc_18001E972
0x18001e90b  mov     rcx, [rcx+10h]; hdpa
0x18001e90f  lea     r9, ?ComparePidlName@CFtpPidlList@@SAHPEAX0_J@Z; pfnCompare
0x18001e916  mov     [rsp+58h+options], edi; options
0x18001e91a  xor     r8d, r8d; iStart
0x18001e91d  mov     [rsp+58h+lParam], 0; lParam
0x18001e926  call    DPA_Search
0x18001e92b  movsxd  rsi, eax
0x18001e92e  cmp     esi, 0FFFFFFFFh
0x18001e931  jz      short loc_18001E972
0x18001e933  mov     rcx, [rbx+10h]
0x18001e937  test    rcx, rcx
0x18001e93a  jz      short loc_18001E972
0x18001e93c  mov     rcx, [rcx+10h]; hdpa
0x18001e940  mov     rdx, rsi; i
0x18001e943  call    DPA_GetPtr
0x18001e948  test    rax, rax
0x18001e94b  jz      short loc_18001E972
0x18001e94d  mov     rcx, rax; pidl
0x18001e950  call    cs:__imp_ILFree
0x18001e956  mov     rcx, [rbx+10h]
0x18001e95a  mov     edx, esi; i
0x18001e95c  mov     rcx, [rcx+10h]; hdpa
0x18001e960  call    DPA_DeletePtr
0x18001e965  mov     rdx, rbp; struct _ITEMIDLIST *
0x18001e968  mov     rcx, rbx; this
0x18001e96b  call    ?InsertSorted@CFtpPidlList@@QEAAJPEFBU_ITEMIDLIST@@@Z; CFtpPidlList::InsertSorted(_ITEMIDLIST const *)
0x18001e970  xor     edi, edi
0x18001e972  mov     eax, edi
0x18001e974  add     rsp, 38h
0x18001e978  pop     rdi
0x18001e979  pop     rsi
0x18001e97a  pop     rbp
0x18001e97b  pop     rbx
0x18001e97c  retn
```
