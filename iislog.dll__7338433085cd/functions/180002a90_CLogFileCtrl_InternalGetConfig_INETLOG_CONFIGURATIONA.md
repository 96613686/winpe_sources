# CLogFileCtrl::InternalGetConfig(_INETLOG_CONFIGURATIONA *)

- ea: `0x180002a90`
- end: `0x180002af1`
- name: `?InternalGetConfig@CLogFileCtrl@@MEAAXPEAU_INETLOG_CONFIGURATIONA@@@Z`
- size: `97`
- prototype: `void __fastcall(CLogFileCtrl *__hidden this, struct _INETLOG_CONFIGURATIONA *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180004df0`

## callees

- `0x180010010`

## import_xrefs

- `msvcrt!strcpy_s` at `0x180002ab6`
- `msvcrt!strcpy_s` at `0x180002ab6`

## pseudocode

```c
void __fastcall CLogFileCtrl::InternalGetConfig(const char **this, struct _INETLOG_CONFIGURATIONA *a2)
{
  *(_DWORD *)a2 = 1;
  strcpy_s((char *)a2 + 4, 0x104u, this[34]);
  *((_DWORD *)a2 + 66) = *((_DWORD *)this + 26);
  *((_DWORD *)a2 + 67) = *((_DWORD *)this + 27);
  *((_DWORD *)a2 + 69) = (*((__int64 (__fastcall **)(const char **))*this + 16))(this);
}

```

## disassembly

```asm
0x180002a90  mov     [rsp+arg_0], rbx
0x180002a95  push    rdi
0x180002a96  sub     rsp, 20h
0x180002a9a  mov     rbx, rcx
0x180002a9d  mov     dword ptr [rdx], 1
0x180002aa3  mov     rdi, rdx
0x180002aa6  lea     rcx, [rdx+4]; Destination
0x180002aaa  mov     edx, 104h; SizeInBytes
0x180002aaf  mov     r8, [rbx+110h]; Source
0x180002ab6  call    cs:__imp_strcpy_s
0x180002abc  mov     eax, [rbx+68h]
0x180002abf  mov     rcx, rbx
0x180002ac2  mov     [rdi+108h], eax
0x180002ac8  mov     eax, [rbx+6Ch]
0x180002acb  mov     [rdi+10Ch], eax
0x180002ad1  mov     rax, [rbx]
0x180002ad4  mov     rax, [rax+80h]
0x180002adb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ae0  mov     rbx, [rsp+28h+arg_0]
0x180002ae5  mov     [rdi+114h], eax
0x180002aeb  add     rsp, 20h
0x180002aef  pop     rdi
0x180002af0  retn
```
