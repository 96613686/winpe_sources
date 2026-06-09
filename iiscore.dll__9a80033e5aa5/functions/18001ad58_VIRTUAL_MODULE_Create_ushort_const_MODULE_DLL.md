# VIRTUAL_MODULE::Create(ushort const *,MODULE_DLL *)

- ea: `0x18001ad58`
- end: `0x18001ad87`
- name: `?Create@VIRTUAL_MODULE@@QEAAJPEBGPEAVMODULE_DLL@@@Z`
- size: `47`
- prototype: `__int64 __fastcall(VIRTUAL_MODULE *__hidden this, const unsigned __int16 *, struct MODULE_DLL *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x18001c6fc`
- `0x18002e740`

## callees

- `0x18001ad58`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001ad6c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001ad6c`

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
0x18001ad58  mov     [rsp+arg_0], rbx
0x18001ad5d  push    rdi
0x18001ad5e  sub     rsp, 20h
0x18001ad62  mov     rbx, rcx
0x18001ad65  mov     rdi, r8
0x18001ad68  add     rcx, 28h ; '('
0x18001ad6c  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001ad72  test    eax, eax
0x18001ad74  js      short loc_18001AD7C
0x18001ad76  mov     [rbx+60h], rdi
0x18001ad7a  xor     eax, eax
0x18001ad7c  mov     rbx, [rsp+28h+arg_0]
0x18001ad81  add     rsp, 20h
0x18001ad85  pop     rdi
0x18001ad86  retn
```
