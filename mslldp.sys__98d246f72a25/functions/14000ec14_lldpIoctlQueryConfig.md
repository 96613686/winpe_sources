# lldpIoctlQueryConfig

- ea: `0x14000ec14`
- end: `0x14000ec77`
- name: `lldpIoctlQueryConfig`
- size: `99`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14000fdd0`

## callees

- `0x140003500`
- `0x140006b40`
- `0x14000e614`
- `0x14000ec14`
- `0x140010530`

## pseudocode

```c
__int64 __fastcall lldpIoctlQueryConfig(__int64 a1, _DWORD *a2)
{
  __int64 v3; // rdi

  v3 = lldpFindAndReferencePort(a1);
  memset(a2, 0, 0x48u);
  if ( v3 )
  {
    *((_QWORD *)a2 + 1) = *(_QWORD *)(v3 + 120);
    a2[4] = *(_DWORD *)(v3 + 132);
    lldpGetPortAdminConfig(v3, a2 + 6);
    lldpDereferencePort(v3);
  }
  else
  {
    *a2 = -1073741275;
  }
  return 0;
}

```

## disassembly

```asm
0x14000ec14  mov     [rsp+arg_0], rbx
0x14000ec19  push    rdi
0x14000ec1a  sub     rsp, 20h
0x14000ec1e  mov     rbx, rdx
0x14000ec21  call    lldpFindAndReferencePort
0x14000ec26  xor     edx, edx; Val
0x14000ec28  mov     rcx, rbx; void *
0x14000ec2b  mov     rdi, rax
0x14000ec2e  lea     r8d, [rdx+48h]; Size
0x14000ec32  call    memset
0x14000ec37  test    rdi, rdi
0x14000ec3a  jz      short loc_14000EC63
0x14000ec3c  mov     rcx, [rdi+78h]
0x14000ec40  lea     rdx, [rbx+18h]
0x14000ec44  mov     [rbx+8], rcx
0x14000ec48  mov     ecx, [rdi+84h]
0x14000ec4e  mov     [rbx+10h], ecx
0x14000ec51  mov     rcx, rdi
0x14000ec54  call    lldpGetPortAdminConfig
0x14000ec59  mov     rcx, rdi
0x14000ec5c  call    lldpDereferencePort
0x14000ec61  jmp     short loc_14000EC69
0x14000ec63  mov     dword ptr [rbx], 0C0000225h
0x14000ec69  mov     rbx, [rsp+28h+arg_0]
0x14000ec6e  xor     eax, eax
0x14000ec70  add     rsp, 20h
0x14000ec74  pop     rdi
0x14000ec75  retn
```
