# CValue::Destroy(void)

- ea: `0x18000a954`
- end: `0x18000a996`
- name: `?Destroy@CValue@@QEAAXXZ`
- size: `66`
- prototype: `void __fastcall(CValue *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180008f28`
- `0x180009368`
- `0x18000994c`
- `0x18000a8bc`
- `0x18000aed4`

## callees

- `0x180001fec`
- `0x18000a954`

## pseudocode

```c
void __fastcall CValue::Destroy(CValue *this)
{
  void **v1; // rbx

  v1 = (void **)((char *)this + 32);
  if ( !*((_DWORD *)this + 2) )
  {
    operator delete(*v1);
    *v1 = 0;
  }
  *(_DWORD *)v1 = 0;
  *(_DWORD *)this = 0;
}

```

## disassembly

```asm
0x18000a954  mov     [rsp+arg_0], rbx
0x18000a959  push    rdi
0x18000a95a  sub     rsp, 20h
0x18000a95e  cmp     dword ptr [rcx+8], 0
0x18000a962  lea     rbx, [rcx+20h]
0x18000a966  mov     rdi, rcx
0x18000a969  jnz     short loc_18000A97F
0x18000a96b  mov     rcx, [rbx]; void *
0x18000a96e  mov     edx, 2; unsigned __int64
0x18000a973  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a978  mov     qword ptr [rbx], 0
0x18000a97f  mov     dword ptr [rbx], 0
0x18000a985  mov     rbx, [rsp+28h+arg_0]
0x18000a98a  mov     dword ptr [rdi], 0
0x18000a990  add     rsp, 20h
0x18000a994  pop     rdi
0x18000a995  retn
```
