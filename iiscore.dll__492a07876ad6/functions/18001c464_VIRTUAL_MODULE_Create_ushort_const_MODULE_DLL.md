# VIRTUAL_MODULE::Create(ushort const *,MODULE_DLL *)

- ea: `0x18001c464`
- end: `0x18001c49a`
- name: `?Create@VIRTUAL_MODULE@@QEAAJPEBGPEAVMODULE_DLL@@@Z`
- size: `54`
- prototype: `__int64 __fastcall(VIRTUAL_MODULE *__hidden this, const unsigned __int16 *, struct MODULE_DLL *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x18001e020`
- `0x180031310`

## callees

- `0x18001c464`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001c478`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001c478`

## pseudocode

```c
int __fastcall VIRTUAL_MODULE::Create(VIRTUAL_MODULE *this, const unsigned __int16 *a2, struct MODULE_DLL *a3)
{
  int result; // eax

  result = STRU::Copy((VIRTUAL_MODULE *)((char *)this + 40), a2);
  if ( result >= 0 )
  {
    *((_QWORD *)this + 12) = a3;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001c464  mov     [rsp+arg_0], rbx
0x18001c469  push    rdi
0x18001c46a  sub     rsp, 20h
0x18001c46e  mov     rbx, rcx
0x18001c471  mov     rdi, r8
0x18001c474  add     rcx, 28h ; '('
0x18001c478  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001c47f  nop     dword ptr [rax+rax+00h]
0x18001c484  test    eax, eax
0x18001c486  js      short loc_18001C48E
0x18001c488  mov     [rbx+60h], rdi
0x18001c48c  xor     eax, eax
0x18001c48e  mov     rbx, [rsp+28h+arg_0]
0x18001c493  add     rsp, 20h
0x18001c497  pop     rdi
0x18001c498  retn
```
