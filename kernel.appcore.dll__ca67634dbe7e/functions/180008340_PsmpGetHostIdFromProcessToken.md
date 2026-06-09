# PsmpGetHostIdFromProcessToken

- ea: `0x180008340`
- end: `0x1800083ec`
- name: `PsmpGetHostIdFromProcessToken`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007ec0`

## callees

- `0x180008340`
- `0x180009d9e`
- `0x180009dd0`

## import_xrefs

- `ntdll!NtQuerySecurityAttributesToken` at `0x1800083a4`
- `ntdll!NtQuerySecurityAttributesToken` at `0x1800083a4`

## pseudocode

```c
__int64 __fastcall PsmpGetHostIdFromProcessToken(__int64 a1, _QWORD *a2)
{
  __int64 result; // rax
  int v5; // [rsp+30h] [rbp-78h] BYREF
  _BYTE v6[4]; // [rsp+38h] [rbp-70h] BYREF
  int v7; // [rsp+3Ch] [rbp-6Ch]
  __int64 v8; // [rsp+40h] [rbp-68h]

  memset_0(v6, 0, 0x60u);
  v5 = 0;
  result = NtQuerySecurityAttributesToken(a1, &qword_18000B470, 1, v6, 96, &v5);
  if ( (int)result >= 0 )
  {
    if ( v7 )
      *a2 = **(_QWORD **)(v8 + 32);
    else
      return 3221226021LL;
  }
  return result;
}

```

## disassembly

```asm
0x180008340  mov     [rsp+arg_10], rbx
0x180008345  push    rdi
0x180008346  sub     rsp, 0A0h
0x18000834d  mov     rax, cs:__security_cookie
0x180008354  xor     rax, rsp
0x180008357  mov     [rsp+0A8h+var_10], rax
0x18000835f  mov     rdi, rdx
0x180008362  mov     rbx, rcx
0x180008365  xor     edx, edx; Val
0x180008367  lea     rcx, [rsp+0A8h+var_70]; void *
0x18000836c  lea     r8d, [rdx+60h]; Size
0x180008370  call    memset_0
0x180008375  lea     rax, [rsp+0A8h+var_78]
0x18000837a  mov     [rsp+0A8h+var_78], 0
0x180008382  mov     [rsp+0A8h+var_80], rax
0x180008387  lea     r9, [rsp+0A8h+var_70]
0x18000838c  mov     r8d, 1
0x180008392  mov     [rsp+0A8h+var_88], 60h ; '`'
0x18000839a  lea     rdx, qword_18000B470
0x1800083a1  mov     rcx, rbx
0x1800083a4  call    cs:__imp_NtQuerySecurityAttributesToken
0x1800083aa  test    eax, eax
0x1800083ac  js      short loc_1800083CB
0x1800083ae  cmp     [rsp+0A8h+var_6C], 0
0x1800083b3  jz      short loc_1800083C6
0x1800083b5  mov     rcx, [rsp+0A8h+var_68]
0x1800083ba  mov     rdx, [rcx+20h]
0x1800083be  mov     rcx, [rdx]
0x1800083c1  mov     [rdi], rcx
0x1800083c4  jmp     short loc_1800083CB
0x1800083c6  mov     eax, 0C0000225h
0x1800083cb  mov     rcx, [rsp+0A8h+var_10]
0x1800083d3  xor     rcx, rsp; StackCookie
0x1800083d6  call    __security_check_cookie
0x1800083db  mov     rbx, [rsp+0A8h+arg_10]
0x1800083e3  add     rsp, 0A0h
0x1800083ea  pop     rdi
0x1800083eb  retn
```
