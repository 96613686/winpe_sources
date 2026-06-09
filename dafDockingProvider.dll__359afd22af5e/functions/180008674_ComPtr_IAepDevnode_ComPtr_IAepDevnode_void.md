# ComPtr<IAepDevnode>::~ComPtr<IAepDevnode>(void)

- ea: `0x180008674`
- end: `0x18000869e`
- name: `??1?$ComPtr@UIAepDevnode@@@@QEAA@XZ`
- size: `42`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `16`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001cf1b`
- `0x18001cf68`
- `0x18001cfdc`
- `0x18001d019`
- `0x18001d050`
- `0x18001d069`
- `0x18001d0cd`
- `0x18001d17c`
- `0x18001d1c7`
- `0x18001d1e0`
- `0x18001d755`
- `0x18001dc7b`
- `0x18001df22`
- `0x18001e02b`
- `0x18001e349`
- `0x18001e35b`

## callees

- `0x180008674`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall ComPtr<IAepDevnode>::~ComPtr<IAepDevnode>(__int64 *a1)
{
  __int64 v2; // rcx
  __int64 result; // rax

  v2 = *a1;
  if ( v2 )
  {
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180008674  push    rbx
0x180008676  sub     rsp, 20h
0x18000867a  mov     rbx, rcx
0x18000867d  mov     rcx, [rcx]
0x180008680  test    rcx, rcx
0x180008683  jz      short loc_180008698
0x180008685  mov     rax, [rcx]
0x180008688  mov     rax, [rax+10h]
0x18000868c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008691  mov     qword ptr [rbx], 0
0x180008698  add     rsp, 20h
0x18000869c  pop     rbx
0x18000869d  retn
```
