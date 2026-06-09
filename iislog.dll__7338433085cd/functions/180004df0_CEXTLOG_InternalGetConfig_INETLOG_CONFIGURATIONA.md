# CEXTLOG::InternalGetConfig(_INETLOG_CONFIGURATIONA *)

- ea: `0x180004df0`
- end: `0x180004e1c`
- name: `?InternalGetConfig@CEXTLOG@@MEAAXPEAU_INETLOG_CONFIGURATIONA@@@Z`
- size: `44`
- prototype: `void __fastcall(CEXTLOG *__hidden this, struct _INETLOG_CONFIGURATIONA *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180002a90`

## pseudocode

```c
void __fastcall CEXTLOG::InternalGetConfig(const char **this, struct _INETLOG_CONFIGURATIONA *a2)
{
  CLogFileCtrl::InternalGetConfig(this, a2);
  *((_DWORD *)a2 + 70) = *((_DWORD *)this + 394);
}

```

## disassembly

```asm
0x180004df0  mov     [rsp+arg_0], rbx
0x180004df5  push    rdi
0x180004df6  sub     rsp, 20h
0x180004dfa  mov     rdi, rdx
0x180004dfd  mov     rbx, rcx
0x180004e00  call    ?InternalGetConfig@CLogFileCtrl@@MEAAXPEAU_INETLOG_CONFIGURATIONA@@@Z; CLogFileCtrl::InternalGetConfig(_INETLOG_CONFIGURATIONA *)
0x180004e05  mov     eax, [rbx+628h]
0x180004e0b  mov     rbx, [rsp+28h+arg_0]
0x180004e10  mov     [rdi+118h], eax
0x180004e16  add     rsp, 20h
0x180004e1a  pop     rdi
0x180004e1b  retn
```
