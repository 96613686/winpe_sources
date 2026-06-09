# DriverSecurityContext::DriverSecurityContext(CACSecurityContext const *)

- ea: `0x14000e414`
- end: `0x14000e481`
- name: `??0DriverSecurityContext@@AEAA@PEBVCACSecurityContext@@@Z`
- size: `109`
- prototype: `DriverSecurityContext *__fastcall(DriverSecurityContext *__hidden this, const struct CACSecurityContext *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000e9a8`

## callees

- `0x140024fc0`

## pseudocode

```c
DriverSecurityContext *__fastcall DriverSecurityContext::DriverSecurityContext(
        DriverSecurityContext *this,
        const struct CACSecurityContext *a2)
{
  memset(this, 0, 0x40u);
  *((_DWORD *)this + 6) = 1;
  *((_DWORD *)this + 6) = *((_DWORD *)a2 + 6);
  *((_DWORD *)this + 7) = *((_DWORD *)a2 + 7);
  *((_DWORD *)this + 8) = *((_DWORD *)a2 + 8);
  *((_DWORD *)this + 12) = *((_DWORD *)a2 + 12);
  *((_DWORD *)this + 13) = *((_DWORD *)a2 + 13);
  *((_DWORD *)this + 14) = *((_DWORD *)a2 + 14);
  *((_DWORD *)this + 15) = *((_DWORD *)a2 + 15);
  *((_DWORD *)this + 9) = *((_DWORD *)a2 + 9);
  *((_DWORD *)this + 10) = *((_DWORD *)a2 + 10);
  *((_DWORD *)this + 11) = *((_DWORD *)a2 + 11);
  return this;
}

```

## disassembly

```asm
0x14000e414  mov     [rsp+arg_0], rbx
0x14000e419  push    rdi
0x14000e41a  sub     rsp, 20h
0x14000e41e  mov     rbx, rdx
0x14000e421  mov     rdi, rcx
0x14000e424  xor     edx, edx; Val
0x14000e426  lea     r8d, [rdx+40h]; Size
0x14000e42a  call    memset
0x14000e42f  mov     dword ptr [rdi+18h], 1
0x14000e436  mov     eax, [rbx+18h]
0x14000e439  mov     [rdi+18h], eax
0x14000e43c  mov     eax, [rbx+1Ch]
0x14000e43f  mov     [rdi+1Ch], eax
0x14000e442  mov     eax, [rbx+20h]
0x14000e445  mov     [rdi+20h], eax
0x14000e448  mov     eax, [rbx+30h]
0x14000e44b  mov     [rdi+30h], eax
0x14000e44e  mov     eax, [rbx+34h]
0x14000e451  mov     [rdi+34h], eax
0x14000e454  mov     eax, [rbx+38h]
0x14000e457  mov     [rdi+38h], eax
0x14000e45a  mov     eax, [rbx+3Ch]
0x14000e45d  mov     [rdi+3Ch], eax
0x14000e460  mov     eax, [rbx+24h]
0x14000e463  mov     [rdi+24h], eax
0x14000e466  mov     eax, [rbx+28h]
0x14000e469  mov     [rdi+28h], eax
0x14000e46c  mov     eax, [rbx+2Ch]
0x14000e46f  mov     rbx, [rsp+28h+arg_0]
0x14000e474  mov     [rdi+2Ch], eax
0x14000e477  mov     rax, rdi
0x14000e47a  add     rsp, 20h
0x14000e47e  pop     rdi
0x14000e47f  retn
```
