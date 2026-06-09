# VmbusTlCreateObject

- ea: `0x140001350`
- end: `0x140001411`
- name: `VmbusTlCreateObject`
- size: `193`
- prototype: `__int64 __fastcall(unsigned int, __int64, _QWORD *)`
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x140008774`
- `0x140018350`
- `0x14001cc80`
- `0x14001cf60`
- `0x14001d304`
- `0x140021cb4`
- `0x140023b40`
- `0x1400251e0`
- `0x140025fe0`
- `0x140026694`

## callees

- `0x140001350`
- `0x140001714`
- `0x140009cf8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000136c`
- `ntoskrnl!ExAllocatePool2` at `0x14000136c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400013f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400013f2`

## string_xrefs

- `0x14000139d`: `VmbusTlCreateObject`
- `0x1400013de`: `VmbusTlCreateObject`

## pseudocode

```c
__int64 __fastcall VmbusTlCreateObject(int a1, size_t a2, int **a3)
{
  int *Pool2; // rax
  int *v7; // rdi
  unsigned int v8; // ebx
  int v9; // eax

  Pool2 = (int *)ExAllocatePool2(64, a2, 1768975958);
  v7 = Pool2;
  if ( Pool2 )
  {
    v9 = VmbusTlInitializeObject(a1, a2, 1, Pool2);
    v8 = v9;
    if ( v9 >= 0 )
    {
      *a3 = v7;
      return 0;
    }
    else
    {
      if ( (unsigned int)dword_140013058 > 2 )
        HvsocketTraceError("VmbusTlCreateObject", 130, (unsigned int)v9, "Failed to initialize object.");
      ExFreePoolWithTag(v7, 0x69706E56u);
    }
  }
  else
  {
    v8 = -1073741670;
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceError("VmbusTlCreateObject", 123, 3221225626LL, "Out of memory.");
  }
  return v8;
}

```

## disassembly

```asm
0x140001350  push    rbx
0x140001352  push    rbp
0x140001353  push    rsi
0x140001354  push    rdi
0x140001355  sub     rsp, 28h
0x140001359  mov     rsi, r8
0x14000135c  mov     ebp, ecx
0x14000135e  mov     ecx, 40h ; '@'
0x140001363  mov     r8d, 69706E56h
0x140001369  mov     rbx, rdx
0x14000136c  call    cs:__imp_ExAllocatePool2
0x140001373  nop     dword ptr [rax+rax+00h]
0x140001378  mov     rdi, rax
0x14000137b  test    rax, rax
0x14000137e  jnz     short loc_1400013AB
0x140001380  mov     eax, cs:dword_140013058
0x140001386  mov     ebx, 0C000009Ah
0x14000138b  cmp     eax, 2
0x14000138e  jbe     short loc_140001405
0x140001390  lea     r9, aOutOfMemory; "Out of memory."
0x140001397  mov     r8d, ebx
0x14000139a  lea     edx, [rdi+7Bh]
0x14000139d  lea     rcx, aVmbustlcreateo; "VmbusTlCreateObject"
0x1400013a4  call    HvsocketTraceError
0x1400013a9  jmp     short loc_140001405
0x1400013ab  mov     r9, rdi
0x1400013ae  mov     r8d, 1
0x1400013b4  mov     rdx, rbx
0x1400013b7  mov     ecx, ebp
0x1400013b9  call    VmbusTlInitializeObject
0x1400013be  mov     ebx, eax
0x1400013c0  test    eax, eax
0x1400013c2  jns     short loc_140001400
0x1400013c4  mov     ecx, cs:dword_140013058
0x1400013ca  cmp     ecx, 2
0x1400013cd  jbe     short loc_1400013EA
0x1400013cf  lea     r9, aFailedToInitia_0; "Failed to initialize object."
0x1400013d6  mov     r8d, eax
0x1400013d9  mov     edx, 82h
0x1400013de  lea     rcx, aVmbustlcreateo; "VmbusTlCreateObject"
0x1400013e5  call    HvsocketTraceError
0x1400013ea  mov     edx, 69706E56h; Tag
0x1400013ef  mov     rcx, rdi; P
0x1400013f2  call    cs:__imp_ExFreePoolWithTag
0x1400013f9  nop     dword ptr [rax+rax+00h]
0x1400013fe  jmp     short loc_140001405
0x140001400  mov     [rsi], rdi
0x140001403  xor     ebx, ebx
0x140001405  mov     eax, ebx
0x140001407  add     rsp, 28h
0x14000140b  pop     rdi
0x14000140c  pop     rsi
0x14000140d  pop     rbp
0x14000140e  pop     rbx
0x14000140f  retn
```
