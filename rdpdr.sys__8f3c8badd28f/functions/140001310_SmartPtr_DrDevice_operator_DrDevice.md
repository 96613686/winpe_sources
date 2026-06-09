# SmartPtr<DrDevice>::operator=(DrDevice *)

- ea: `0x140001310`
- end: `0x14000134a`
- name: `??4?$SmartPtr@VDrDevice@@@@QEAAAEAV0@PEAVDrDevice@@@Z`
- size: `58`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1400010fc`
- `0x140004050`
- `0x140011b3c`
- `0x140020100`
- `0x140020788`
- `0x140026c18`
- `0x140027fe0`

## callees

- `0x140001310`
- `0x140001660`

## pseudocode

```c
RefCount **__fastcall SmartPtr<DrDevice>::operator=(RefCount **a1, volatile signed __int32 *a2)
{
  RefCount *v4; // rcx
  RefCount **result; // rax

  v4 = *a1;
  if ( v4 )
    RefCount::Release(v4);
  *a1 = (RefCount *)a2;
  result = a1;
  if ( a2 )
    _InterlockedIncrement(a2 + 4);
  return result;
}

```

## disassembly

```asm
0x140001310  mov     [rsp+arg_0], rbx
0x140001315  push    rdi
0x140001316  sub     rsp, 20h
0x14000131a  mov     rdi, rcx
0x14000131d  mov     rbx, rdx
0x140001320  mov     rcx, [rcx]; this
0x140001323  test    rcx, rcx
0x140001326  jnz     short loc_140001343
0x140001328  mov     [rdi], rbx
0x14000132b  mov     rax, rdi
0x14000132e  test    rbx, rbx
0x140001331  jz      short loc_140001337
0x140001333  lock inc dword ptr [rbx+10h]
0x140001337  mov     rbx, [rsp+28h+arg_0]
0x14000133c  add     rsp, 20h
0x140001340  pop     rdi
0x140001341  retn
0x140001343  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x140001348  jmp     short loc_140001328
```
