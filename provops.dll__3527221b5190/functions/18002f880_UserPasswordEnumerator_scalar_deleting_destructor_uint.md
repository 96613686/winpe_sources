# UserPasswordEnumerator::`scalar deleting destructor'(uint)

- ea: `0x18002f880`
- end: `0x18002f8e2`
- name: `??_GUserPasswordEnumerator@@UEAAPEAXI@Z`
- size: `98`
- prototype: `UserPasswordEnumerator *__fastcall(UserPasswordEnumerator *this, char)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x18002f880`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002f8a9`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002f8ce`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002f8a9`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002f8ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f898`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f898`

## pseudocode

```c
UserPasswordEnumerator *__fastcall UserPasswordEnumerator::`scalar deleting destructor'(
        UserPasswordEnumerator *this,
        char a2)
{
  void *v4; // rcx

  v4 = (void *)*((_QWORD *)this + 5);
  if ( v4 )
    CoTaskMemFree(v4);
  if ( *((_QWORD *)this + 4) >= 8u )
    operator delete(*((void **)this + 1));
  *((_QWORD *)this + 4) = 7;
  *((_QWORD *)this + 3) = 0;
  *((_WORD *)this + 4) = 0;
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18002f880  mov     [rsp+arg_0], rbx
0x18002f885  push    rdi
0x18002f886  sub     rsp, 20h
0x18002f88a  mov     rbx, rcx
0x18002f88d  mov     edi, edx
0x18002f88f  mov     rcx, [rcx+28h]; pv
0x18002f893  test    rcx, rcx
0x18002f896  jz      short loc_18002F89E
0x18002f898  call    cs:__imp_CoTaskMemFree
0x18002f89e  cmp     qword ptr [rbx+20h], 8
0x18002f8a3  jb      short loc_18002F8AF
0x18002f8a5  mov     rcx, [rbx+8]
0x18002f8a9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002f8af  xor     eax, eax
0x18002f8b1  mov     qword ptr [rbx+20h], 7
0x18002f8b9  mov     qword ptr [rbx+18h], 0
0x18002f8c1  mov     [rbx+8], ax
0x18002f8c5  test    dil, 1
0x18002f8c9  jz      short loc_18002F8D4
0x18002f8cb  mov     rcx, rbx
0x18002f8ce  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002f8d4  mov     rax, rbx
0x18002f8d7  mov     rbx, [rsp+28h+arg_0]
0x18002f8dc  add     rsp, 20h
0x18002f8e0  pop     rdi
0x18002f8e1  retn
```
