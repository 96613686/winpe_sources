# Memory::HeapAllocator::Alloc(unsigned __int64)

- ea: `0x180148580`
- end: `0x1801485dc`
- name: `?Alloc@HeapAllocator@Memory@@QEAAPEAD_K@Z`
- size: `92`
- prototype: `char *__fastcall(Memory::HeapAllocator *__hidden this, unsigned __int64)`
- caller_count: `71`
- callee_count: `2`
- tags: ``

## callers

- `0x180045600`
- `0x180076c34`
- `0x18008bc24`
- `0x180093740`
- `0x180095278`
- `0x180095b6c`
- `0x180096524`
- `0x180096794`
- `0x180096834`
- `0x1800b2148`
- `0x180118d58`
- `0x18011bd70`
- `0x180145a28`
- `0x180146a84`
- `0x180146b68`
- `0x180146c64`
- `0x180146f50`
- `0x180146fc4`
- `0x180147240`
- `0x1801474b0`
- `0x18014757c`
- `0x180148210`
- `0x18014847c`
- `0x180148974`
- `0x180148af0`
- `0x18014961c`
- `0x180149fe4`
- `0x18014ab90`
- `0x18014b794`
- `0x18014c1e4`
- `0x18014c558`
- `0x18014c8a0`
- `0x18014dfdc`
- `0x18014ed7c`
- `0x180150bb8`
- `0x180150d98`
- `0x180150f64`
- `0x1801510f4`
- `0x180152228`
- `0x180152fe0`
- `0x180156660`
- `0x1801a8b90`
- `0x1801b4eb4`
- `0x1801bebcc`
- `0x1801c9470`
- `0x1801fbc30`
- `0x180245cec`
- `0x1802471bc`
- `0x18025bb64`
- `0x1802ed284`

## callees

- `0x180148580`
- `0x1803c4080`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801485a6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801485a6`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1801485c5`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1801485c5`

## pseudocode

```c
char *__fastcall Memory::HeapAllocator::Alloc(HANDLE *this, SIZE_T a2)
{
  HANDLE v3; // rax
  char *result; // rax

  v3 = *this;
  if ( !*this )
  {
    v3 = HeapCreate(0, 0, 0);
    *this = v3;
  }
  result = (char *)HeapAlloc(v3, 0, a2);
  if ( !result )
    Js::Throw::OutOfMemory();
  return result;
}

```

## disassembly

```asm
0x180148580  mov     [rsp+dwBytes], rdx
0x180148585  mov     [rsp+arg_0], rcx
0x18014858a  push    rbx
0x18014858b  sub     rsp, 20h
0x18014858f  mov     rbx, [rsp+28h+arg_0]
0x180148594  mov     rax, [rbx]
0x180148597  test    rax, rax
0x18014859a  jz      short loc_1801485BE
0x18014859c  mov     r8, [rsp+28h+dwBytes]; dwBytes
0x1801485a1  xor     edx, edx; dwFlags
0x1801485a3  mov     rcx, rax; hHeap
0x1801485a6  call    cs:__imp_HeapAlloc
0x1801485ad  nop     dword ptr [rax+rax+00h]
0x1801485b2  test    rax, rax
0x1801485b5  jz      short loc_1801485D6
0x1801485b7  add     rsp, 20h
0x1801485bb  pop     rbx
0x1801485bc  retn
0x1801485be  xor     r8d, r8d; dwMaximumSize
0x1801485c1  xor     edx, edx; dwInitialSize
0x1801485c3  xor     ecx, ecx; flOptions
0x1801485c5  call    cs:__imp_HeapCreate
0x1801485cc  nop     dword ptr [rax+rax+00h]
0x1801485d1  mov     [rbx], rax
0x1801485d4  jmp     short loc_18014859C
0x1801485d6  call    ?OutOfMemory@Throw@Js@@SAXXZ; Js::Throw::OutOfMemory(void)
```
