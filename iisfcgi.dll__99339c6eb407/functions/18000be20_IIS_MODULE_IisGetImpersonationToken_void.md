# IIS_MODULE::IisGetImpersonationToken(void)

- ea: `0x18000be20`
- end: `0x18000be8e`
- name: `?IisGetImpersonationToken@IIS_MODULE@@UEAAPEAXXZ`
- size: `110`
- prototype: `void *__fastcall(IIS_MODULE *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000be20`
- `0x180010010`

## pseudocode

```c
void *__fastcall IIS_MODULE::IisGetImpersonationToken(IIS_MODULE *this)
{
  void *result; // rax
  __int64 v3; // rcx
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rcx

  result = 0;
  v3 = *((_QWORD *)this + 21);
  if ( v3 )
  {
    v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 160LL))(v3);
    v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    if ( v5 )
    {
      return (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 56LL))(v5);
    }
    else
    {
      v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 21) + 48LL))(*((_QWORD *)this + 21));
      return (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 32LL))(v6);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000be20  push    rbx
0x18000be22  sub     rsp, 20h
0x18000be26  mov     rbx, rcx
0x18000be29  xor     eax, eax
0x18000be2b  mov     rcx, [rcx+0A8h]
0x18000be32  test    rcx, rcx
0x18000be35  jz      short loc_18000BE88
0x18000be37  mov     rax, [rcx]
0x18000be3a  mov     rax, [rax+0A0h]
0x18000be41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be46  mov     rcx, rax
0x18000be49  mov     rax, [rax]
0x18000be4c  mov     rax, [rax+10h]
0x18000be50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be55  mov     rcx, rax
0x18000be58  test    rax, rax
0x18000be5b  jnz     short loc_18000BE7C
0x18000be5d  mov     rcx, [rbx+0A8h]
0x18000be64  mov     rax, [rcx]
0x18000be67  mov     rax, [rax+30h]
0x18000be6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be70  mov     rcx, rax
0x18000be73  mov     rax, [rax]
0x18000be76  mov     rax, [rax+20h]
0x18000be7a  jmp     short loc_18000BE83
0x18000be7c  mov     rax, [rax]
0x18000be7f  mov     rax, [rax+38h]
0x18000be83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be88  add     rsp, 20h
0x18000be8c  pop     rbx
0x18000be8d  retn
```
