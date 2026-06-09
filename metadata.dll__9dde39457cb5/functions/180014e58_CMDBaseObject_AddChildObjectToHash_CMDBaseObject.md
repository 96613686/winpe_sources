# CMDBaseObject::AddChildObjectToHash(CMDBaseObject *)

- ea: `0x180014e58`
- end: `0x180014ef1`
- name: `?AddChildObjectToHash@CMDBaseObject@@QEAAJPEAV1@@Z`
- size: `153`
- prototype: `__int64 __fastcall(CMDBaseObject *__hidden this, struct CMDBaseObject *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180015430`
- `0x18001919c`

## callees

- `0x180014e58`

## import_xrefs

- `IisRTL!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x180014ebc`
- `IisRTL!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x180014ebc`
- `IisRTL!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180014e72`
- `IisRTL!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180014e72`

## pseudocode

```c
__int64 __fastcall CMDBaseObject::AddChildObjectToHash(CMDBaseObject *this, struct CMDBaseObject *a2)
{
  int inserted; // eax
  unsigned int v5; // ebx
  char *v6; // rcx
  char *v7; // rax
  char **v8; // rdx

  inserted = CLKRHashTable::InsertRecord(g_phtChildren, a2, 0);
  if ( inserted )
  {
    v5 = -2147467259;
    if ( inserted == -98 )
      return (unsigned int)-2147024882;
    return v5;
  }
  v6 = (char *)this + 232;
  if ( this == (CMDBaseObject *)-232LL )
  {
    v5 = -2147024809;
LABEL_9:
    CLKRHashTable::DeleteRecord(g_phtChildren);
    return v5;
  }
  v7 = (char *)a2 + 248;
  if ( *(char **)v7 != v7 )
  {
    v5 = -2147418113;
    goto LABEL_9;
  }
  v8 = (char **)*((_QWORD *)this + 30);
  if ( *v8 != v6 )
    __fastfail(3u);
  *(_QWORD *)v7 = v6;
  *((_QWORD *)a2 + 32) = v8;
  *v8 = v7;
  *((_QWORD *)this + 30) = v7;
  return 0;
}

```

## disassembly

```asm
0x180014e58  mov     [rsp+arg_0], rbx
0x180014e5d  push    rdi
0x180014e5e  sub     rsp, 20h
0x180014e62  mov     rbx, rcx
0x180014e65  xor     r8d, r8d
0x180014e68  mov     rcx, cs:?g_phtChildren@@3PEAVCChildNodeHashTable@@EA; CChildNodeHashTable * g_phtChildren
0x180014e6f  mov     rdi, rdx
0x180014e72  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x180014e78  test    eax, eax
0x180014e7a  jz      short loc_180014E8E
0x180014e7c  cmp     eax, 0FFFFFF9Eh
0x180014e7f  mov     ebx, 80004005h
0x180014e84  mov     ecx, 8007000Eh
0x180014e89  cmovz   ebx, ecx
0x180014e8c  jmp     short loc_180014EE4
0x180014e8e  lea     rcx, [rbx+0E8h]
0x180014e95  test    rcx, rcx
0x180014e98  jnz     short loc_180014EA1
0x180014e9a  mov     ebx, 80070057h
0x180014e9f  jmp     short loc_180014EB2
0x180014ea1  lea     rax, [rdi+0F8h]
0x180014ea8  cmp     [rax], rax
0x180014eab  jz      short loc_180014EC4
0x180014ead  mov     ebx, 8000FFFFh
0x180014eb2  mov     rcx, cs:?g_phtChildren@@3PEAVCChildNodeHashTable@@EA; CChildNodeHashTable * g_phtChildren
0x180014eb9  mov     rdx, rdi
0x180014ebc  call    cs:__imp_?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z; CLKRHashTable::DeleteRecord(void const *)
0x180014ec2  jmp     short loc_180014EE4
0x180014ec4  mov     rdx, [rcx+8]
0x180014ec8  cmp     [rdx], rcx
0x180014ecb  jz      short loc_180014ED4
0x180014ecd  mov     ecx, 3
0x180014ed2  int     29h; Win8: RtlFailFast(ecx)
0x180014ed4  mov     [rax], rcx
0x180014ed7  mov     [rax+8], rdx
0x180014edb  mov     [rdx], rax
0x180014ede  mov     [rcx+8], rax
0x180014ee2  xor     ebx, ebx
0x180014ee4  mov     eax, ebx
0x180014ee6  mov     rbx, [rsp+28h+arg_0]
0x180014eeb  add     rsp, 20h
0x180014eef  pop     rdi
0x180014ef0  retn
```
