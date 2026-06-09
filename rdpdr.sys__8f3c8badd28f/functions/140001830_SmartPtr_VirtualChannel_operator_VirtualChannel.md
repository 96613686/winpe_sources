# SmartPtr<VirtualChannel>::operator=(VirtualChannel *)

- ea: `0x140001830`
- end: `0x140001885`
- name: `??4?$SmartPtr@VVirtualChannel@@@@QEAAAEAV0@PEAVVirtualChannel@@@Z`
- size: `85`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x1400010fc`
- `0x140002a40`
- `0x140011010`
- `0x14001b608`
- `0x14001bf2c`
- `0x14001f310`
- `0x140020100`
- `0x140026a48`
- `0x140026c18`
- `0x140027190`
- `0x140027fe0`
- `0x140028f80`
- `0x14002c3f0`

## callees

- `0x140001830`
- `0x140006560`

## pseudocode

```c
volatile signed __int32 **__fastcall SmartPtr<VirtualChannel>::operator=(
        volatile signed __int32 **a1,
        volatile signed __int32 *a2)
{
  volatile signed __int32 *v4; // rcx
  volatile signed __int32 **result; // rax

  v4 = *a1;
  if ( v4 && _InterlockedExchangeAdd(v4 + 4, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v4 + 16LL))(v4, 1);
  *a1 = a2;
  result = a1;
  if ( a2 )
    _InterlockedIncrement(a2 + 4);
  return result;
}

```

## disassembly

```asm
0x140001830  mov     [rsp+arg_8], rbx
0x140001835  push    rdi
0x140001836  sub     rsp, 20h
0x14000183a  mov     rdi, rcx
0x14000183d  mov     rbx, rdx
0x140001840  mov     rcx, [rcx]
0x140001843  test    rcx, rcx
0x140001846  jz      short loc_140001857
0x140001848  mov     eax, 0FFFFFFFFh
0x14000184d  lock xadd [rcx+10h], eax
0x140001852  cmp     eax, 1
0x140001855  jz      short loc_140001872
0x140001857  mov     [rdi], rbx
0x14000185a  mov     rax, rdi
0x14000185d  test    rbx, rbx
0x140001860  jz      short loc_140001866
0x140001862  lock inc dword ptr [rbx+10h]
0x140001866  mov     rbx, [rsp+28h+arg_8]
0x14000186b  add     rsp, 20h
0x14000186f  pop     rdi
0x140001870  retn
0x140001872  mov     rax, [rcx]
0x140001875  mov     edx, 1
0x14000187a  mov     rax, [rax+10h]
0x14000187e  call    _guard_dispatch_icall
0x140001883  jmp     short loc_140001857
```
