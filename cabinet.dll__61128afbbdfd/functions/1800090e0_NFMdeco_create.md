# NFMdeco_create

- ea: `0x1800090e0`
- end: `0x180009151`
- name: `NFMdeco_create`
- size: `113`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180009030`
- `0x1800092c0`

## callees

- `0x1800090e0`
- `0x180009158`
- `0x18001562a`
- `0x18001c010`

## pseudocode

```c
void *__fastcall NFMdeco_create(
        __int64 (__fastcall *a1)(__int64),
        __int64 (__fastcall *a2)(__int64, __int64),
        __int64 a3)
{
  void *v3; // rax
  void *v4; // rbx

  if ( a1 )
  {
    v3 = (void *)a1(17720);
  }
  else
  {
    if ( !a2 )
      return 0;
    v3 = (void *)a2(a3, 17720);
  }
  v4 = v3;
  if ( v3 )
  {
    memset_0(v3, 0, 0x4538u);
    if ( !dword_180021108 )
    {
      InitFixed();
      dword_180021108 = 1;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800090e0  push    rbx
0x1800090e2  sub     rsp, 20h
0x1800090e6  mov     rax, rdx
0x1800090e9  mov     rdx, rcx
0x1800090ec  test    rcx, rcx
0x1800090ef  jnz     short loc_180009105
0x1800090f1  test    rax, rax
0x1800090f4  jz      short loc_18000914D
0x1800090f6  mov     edx, 4538h
0x1800090fb  mov     rcx, r8
0x1800090fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009103  jmp     short loc_180009112
0x180009105  mov     ecx, 4538h
0x18000910a  mov     rax, rdx
0x18000910d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009112  mov     rbx, rax
0x180009115  test    rax, rax
0x180009118  jz      short loc_180009133
0x18000911a  xor     edx, edx; Val
0x18000911c  mov     r8d, 4538h; Size
0x180009122  mov     rcx, rax; void *
0x180009125  call    memset_0
0x18000912a  cmp     cs:dword_180021108, 0
0x180009131  jz      short loc_18000913C
0x180009133  mov     rax, rbx
0x180009136  add     rsp, 20h
0x18000913a  pop     rbx
0x18000913b  retn
0x18000913c  call    InitFixed
0x180009141  mov     cs:dword_180021108, 1
0x18000914b  jmp     short loc_180009133
0x18000914d  xor     ebx, ebx
0x18000914f  jmp     short loc_180009133
```
