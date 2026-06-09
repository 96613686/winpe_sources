# CTransformInputPin::CompleteConnect(IPin *)

- ea: `0x1800291a0`
- end: `0x1800291cf`
- name: `?CompleteConnect@CTransformInputPin@@UEAAJPEAUIPin@@@Z`
- size: `47`
- prototype: `__int64 __fastcall(CTransformInputPin *__hidden this, struct IPin *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180088750`

## pseudocode

```c
__int64 __fastcall CTransformInputPin::CompleteConnect(CTransformInputPin *this, struct IPin *a2)
{
  int v2; // eax
  unsigned int v3; // ecx

  v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IPin *))(**((_QWORD **)this + 38) + 160LL))(
         *((_QWORD *)this + 38),
         0,
         a2);
  v3 = 0;
  if ( v2 < 0 )
    return (unsigned int)v2;
  return v3;
}

```

## disassembly

```asm
0x1800291a0  sub     rsp, 28h
0x1800291a4  mov     rcx, [rcx+130h]
0x1800291ab  mov     r8, rdx
0x1800291ae  xor     edx, edx
0x1800291b0  mov     rax, [rcx]
0x1800291b3  mov     rax, [rax+0A0h]
0x1800291ba  call    cs:__guard_dispatch_icall_fptr
0x1800291c0  xor     ecx, ecx
0x1800291c2  test    eax, eax
0x1800291c4  cmovs   ecx, eax
0x1800291c7  mov     eax, ecx
0x1800291c9  add     rsp, 28h
0x1800291cd  retn
```
