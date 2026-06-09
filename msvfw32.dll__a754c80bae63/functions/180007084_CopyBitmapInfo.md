# CopyBitmapInfo

- ea: `0x180007084`
- end: `0x1800070be`
- name: `CopyBitmapInfo`
- size: `58`
- prototype: `HLOCAL __fastcall(__int64)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800072f4`
- `0x1800076c4`

## callees

- `0x180007034`
- `0x180007084`
- `0x180007464`
- `0x180017010`

## pseudocode

```c
HLOCAL __fastcall CopyBitmapInfo(__int64 a1)
{
  _DWORD *v1; // rax
  unsigned int BMI16Size; // eax
  void *v3; // r9

  v1 = (_DWORD *)((__int64 (__fastcall *)(__int64, _QWORD, __int64))GetVDMPointer)(a1, 0, 1);
  if ( !*v1 )
    *v1 = 40;
  BMI16Size = GetBMI16Size(v1);
  return CopyAlloc(v3, BMI16Size);
}

```

## disassembly

```asm
0x180007084  sub     rsp, 28h
0x180007088  mov     rax, cs:GetVDMPointer
0x18000708f  xor     edx, edx
0x180007091  lea     r8d, [rdx+1]
0x180007095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000709a  mov     r9, rax
0x18000709d  cmp     dword ptr [rax], 0
0x1800070a0  jnz     short loc_1800070A8
0x1800070a2  mov     dword ptr [rax], 28h ; '('
0x1800070a8  mov     rcx, r9
0x1800070ab  call    GetBMI16Size
0x1800070b0  mov     edx, eax; Size
0x1800070b2  mov     rcx, r9; Src
0x1800070b5  add     rsp, 28h
0x1800070b9  jmp     CopyAlloc
```
