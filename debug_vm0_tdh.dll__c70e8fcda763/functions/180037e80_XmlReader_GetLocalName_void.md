# XmlReader::GetLocalName(void)

- ea: `0x180037e80`
- end: `0x180037ee9`
- name: `?GetLocalName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ`
- size: `105`
- prototype: `__int64 __fastcall(XmlReader *this)`
- caller_count: `26`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180011b30`
- `0x18001d810`
- `0x18002c2fc`
- `0x18002c650`
- `0x18003479c`
- `0x180034cbc`
- `0x180035780`
- `0x180036020`
- `0x1800360b4`
- `0x180036d30`
- `0x1800380ec`
- `0x180038228`
- `0x180038498`
- `0x1800386fc`
- `0x18003889c`
- `0x180038a44`
- `0x180038c30`
- `0x180038d38`
- `0x180039780`
- `0x180039878`
- `0x180039cdc`
- `0x18003b29c`
- `0x18003b4dc`
- `0x18003b6f8`
- `0x18003b7e0`
- `0x18003bae4`

## callees

- `0x18001ee78`
- `0x18004c010`

## pseudocode

```c
_QWORD *__fastcall XmlReader::GetLocalName(XmlReader *this, _QWORD *a2)
{
  __int64 v3; // rcx
  int v5; // eax
  unsigned int v7; // [rsp+30h] [rbp+8h] BYREF
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = 0;
  v3 = *(_QWORD *)this;
  v7 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *, unsigned int *))(*(_QWORD *)v3 + 112LL))(v3, &v8, &v7);
  XmlReader::ThrowIfFailed(this, "GetLocalName", v5);
  *a2 = v8;
  a2[1] = v7;
  return a2;
}

```

## disassembly

```asm
0x180037e80  mov     r11, rsp
0x180037e83  mov     [r11+18h], rbx
0x180037e87  push    rdi
0x180037e88  sub     rsp, 20h
0x180037e8c  mov     rbx, rcx
0x180037e8f  mov     qword ptr [r11+10h], 0
0x180037e97  mov     rcx, [rcx]
0x180037e9a  lea     r8, [r11+8]
0x180037e9e  mov     [rsp+28h+arg_0], 0
0x180037ea6  mov     rdi, rdx
0x180037ea9  lea     rdx, [r11+10h]
0x180037ead  mov     rax, [rcx]
0x180037eb0  mov     rax, [rax+70h]
0x180037eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037eb9  mov     r8d, eax; int
0x180037ebc  lea     rdx, aGetlocalname; "GetLocalName"
0x180037ec3  mov     rcx, rbx; this
0x180037ec6  call    ?ThrowIfFailed@XmlReader@@AEBAXPEBDJ@Z; XmlReader::ThrowIfFailed(char const *,long)
0x180037ecb  mov     rax, [rsp+28h+arg_8]
0x180037ed0  mov     rbx, [rsp+28h+arg_10]
0x180037ed5  mov     [rdi], rax
0x180037ed8  mov     eax, [rsp+28h+arg_0]
0x180037edc  mov     [rdi+8], rax
0x180037ee0  mov     rax, rdi
0x180037ee3  add     rsp, 20h
0x180037ee7  pop     rdi
0x180037ee8  retn
```
