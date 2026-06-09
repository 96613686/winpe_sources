# SecAllocateHashContext

- ea: `0x1400328b4`
- end: `0x140032946`
- name: `SecAllocateHashContext`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140032adc`

## callees

- `0x1400011a0`
- `0x140001c20`
- `0x140002f80`
- `0x14000a480`
- `0x140011610`
- `0x1400328b4`
- `0x14003b8a4`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400328d2`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400328d2`

## pseudocode

```c
__int64 SecAllocateHashContext()
{
  char *v0; // rdi
  union _SLIST_HEADER *v1; // rcx
  PSLIST_ENTRY v2; // rbx
  __int64 v3; // rdx
  __int64 (__fastcall *v4)(__int64, __int64, __int64); // rax
  __int64 v5; // r8
  __int64 v6; // rcx
  __int64 result; // rax

  v0 = (char *)SecData + 768;
  v1 = (union _SLIST_HEADER *)((char *)SecData + 768);
  ++*((_DWORD *)SecData + 197);
  v2 = ExpInterlockedPopEntrySList(v1);
  if ( v2
    || (v3 = *((unsigned int *)v0 + 11),
        v4 = (__int64 (__fastcall *)(__int64, __int64, __int64))*((_QWORD *)v0 + 6),
        v5 = *((unsigned int *)v0 + 10),
        v6 = *((unsigned int *)v0 + 9),
        ++*((_DWORD *)v0 + 6),
        result = v4(v6, v3, v5),
        (v2 = (PSLIST_ENTRY)result) != 0) )
  {
    SymCryptMd5Init(v2);
    SymCryptSha1Init(&v2[7]);
    SymCryptSha256Init(&v2[15]);
    if ( (unsigned __int8)SecIsLshashCalculationEnabled() )
      LshashInit(&v2[23]);
    return (__int64)v2;
  }
  return result;
}

```

## disassembly

```asm
0x1400328b4  mov     [rsp+arg_0], rbx
0x1400328b9  push    rdi
0x1400328ba  sub     rsp, 20h
0x1400328be  mov     rdi, cs:SecData
0x1400328c5  add     rdi, 300h
0x1400328cc  mov     rcx, rdi; ListHead
0x1400328cf  inc     dword ptr [rdi+14h]
0x1400328d2  call    cs:__imp_ExpInterlockedPopEntrySList
0x1400328d9  nop     dword ptr [rax+rax+00h]
0x1400328de  mov     rbx, rax
0x1400328e1  test    rax, rax
0x1400328e4  jnz     short loc_140032905
0x1400328e6  mov     edx, [rdi+2Ch]
0x1400328e9  mov     rax, [rdi+30h]
0x1400328ed  mov     r8d, [rdi+28h]
0x1400328f1  mov     ecx, [rdi+24h]
0x1400328f4  inc     dword ptr [rdi+18h]
0x1400328f7  call    cs:__guard_dispatch_icall_fptr
0x1400328fd  mov     rbx, rax
0x140032900  test    rax, rax
0x140032903  jz      short loc_14003293A
0x140032905  mov     rcx, rbx
0x140032908  call    SymCryptMd5Init
0x14003290d  lea     rcx, [rbx+70h]
0x140032911  call    SymCryptSha1Init
0x140032916  lea     rcx, [rbx+0F0h]
0x14003291d  call    SymCryptSha256Init
0x140032922  call    SecIsLshashCalculationEnabled
0x140032927  test    al, al
0x140032929  jz      short loc_140032937
0x14003292b  lea     rcx, [rbx+170h]
0x140032932  call    LshashInit
0x140032937  mov     rax, rbx
0x14003293a  mov     rbx, [rsp+28h+arg_0]
0x14003293f  add     rsp, 20h
0x140032943  pop     rdi
0x140032944  retn
```
