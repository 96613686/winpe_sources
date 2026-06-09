# NbtGetCompartmentForLuid

- ea: `0x14001b688`
- end: `0x14001b731`
- name: `NbtGetCompartmentForLuid`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001b2f4`

## callees

- `0x140030f40`
- `0x140031440`

## import_xrefs

- `NETIO!NsiGetAllParameters` at `0x14001b6fd`
- `NETIO!NsiGetAllParameters` at `0x14001b6fd`

## pseudocode

```c
__int64 __fastcall NbtGetCompartmentForLuid(__int64 a1, _DWORD *a2)
{
  __int64 result; // rax
  _DWORD v5[24]; // [rsp+60h] [rbp-78h] BYREF

  memset(v5, 0, 0x58u);
  result = NsiGetAllParameters(3, &NPI_MS_IPV4_MODULEID, 7, a1, 8, 0, 0, v5, 88, 0, 0);
  *a2 = v5[1];
  return result;
}

```

## disassembly

```asm
0x14001b688  mov     [rsp+arg_10], rbx
0x14001b68d  push    rdi
0x14001b68e  sub     rsp, 0D0h
0x14001b695  mov     rax, cs:__security_cookie
0x14001b69c  xor     rax, rsp
0x14001b69f  mov     [rsp+0D8h+var_18], rax
0x14001b6a7  mov     rdi, rdx
0x14001b6aa  mov     rbx, rcx
0x14001b6ad  xor     edx, edx; Val
0x14001b6af  lea     rcx, [rsp+0D8h+var_78]; void *
0x14001b6b4  lea     r8d, [rdx+58h]; Size
0x14001b6b8  call    memset
0x14001b6bd  xor     ecx, ecx
0x14001b6bf  lea     rax, [rsp+0D8h+var_78]
0x14001b6c4  mov     [rsp+0D8h+var_88], ecx
0x14001b6c8  lea     rdx, NPI_MS_IPV4_MODULEID
0x14001b6cf  mov     [rsp+0D8h+var_90], rcx
0x14001b6d4  mov     r9, rbx
0x14001b6d7  mov     [rsp+0D8h+var_98], 58h ; 'X'
0x14001b6df  mov     [rsp+0D8h+var_A0], rax
0x14001b6e4  lea     r8d, [rcx+7]
0x14001b6e8  mov     [rsp+0D8h+var_A8], ecx
0x14001b6ec  mov     [rsp+0D8h+var_B0], rcx
0x14001b6f1  lea     ecx, [r8-4]
0x14001b6f5  mov     [rsp+0D8h+var_B8], 8
0x14001b6fd  call    cs:__imp_NsiGetAllParameters
0x14001b704  nop     dword ptr [rax+rax+00h]
0x14001b709  mov     ecx, [rsp+0D8h+var_74]
0x14001b70d  mov     [rdi], ecx
0x14001b70f  mov     rcx, [rsp+0D8h+var_18]
0x14001b717  xor     rcx, rsp; StackCookie
0x14001b71a  call    __security_check_cookie
0x14001b71f  mov     rbx, [rsp+0D8h+arg_10]
0x14001b727  add     rsp, 0D0h
0x14001b72e  pop     rdi
0x14001b72f  retn
```
