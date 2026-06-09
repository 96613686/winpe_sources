# CCommandList::ETWWrite(unsigned __int64,_EVENT_DESCRIPTOR const *)

- ea: `0x18004f4c4`
- end: `0x18004f532`
- name: `?ETWWrite@CCommandList@@QEAAX_KPEBU_EVENT_DESCRIPTOR@@@Z`
- size: `110`
- prototype: `void __fastcall(CCommandList *__hidden this, unsigned __int64, const struct _EVENT_DESCRIPTOR *)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004ef60`
- `0x18004f6b0`
- `0x1800a4fd0`
- `0x1800c5620`

## callees

- `0x1800a9d20`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18004f51a`
- `ntdll!EtwEventWrite` at `0x18004f51a`

## pseudocode

```c
void __fastcall CCommandList::ETWWrite(CCommandList *this, __int64 a2, const struct _EVENT_DESCRIPTOR *a3)
{
  __int64 v3; // rax
  _QWORD v4[4]; // [rsp+20h] [rbp-38h] BYREF

  v3 = *((_QWORD *)this + 27);
  v4[1] = 8;
  v4[0] = v3 + 216;
  v4[3] = 8;
  v4[2] = (char *)this + 168;
  EtwEventWrite(Direct3D11EtwProviderGuid_Context, a3, 2, v4);
}

```

## disassembly

```asm
0x18004f4c4  mov     r11, rsp
0x18004f4c7  sub     rsp, 58h
0x18004f4cb  mov     rax, cs:__security_cookie
0x18004f4d2  xor     rax, rsp
0x18004f4d5  mov     [rsp+58h+var_18], rax
0x18004f4da  mov     rax, [rcx+0D8h]
0x18004f4e1  lea     r9, [r11-38h]
0x18004f4e5  add     rax, 0D8h
0x18004f4eb  mov     qword ptr [r11-30h], 8
0x18004f4f3  mov     [r11-38h], rax
0x18004f4f7  mov     rdx, r8
0x18004f4fa  lea     rax, [rcx+0A8h]
0x18004f501  mov     qword ptr [r11-20h], 8
0x18004f509  mov     rcx, cs:Direct3D11EtwProviderGuid_Context
0x18004f510  mov     r8d, 2
0x18004f516  mov     [r11-28h], rax
0x18004f51a  call    cs:__imp_EtwEventWrite
0x18004f520  mov     rcx, [rsp+58h+var_18]
0x18004f525  xor     rcx, rsp; StackCookie
0x18004f528  call    __security_check_cookie
0x18004f52d  add     rsp, 58h
0x18004f531  retn
```
