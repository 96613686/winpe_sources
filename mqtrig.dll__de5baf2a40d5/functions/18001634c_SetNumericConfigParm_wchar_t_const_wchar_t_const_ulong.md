# SetNumericConfigParm(wchar_t const *,wchar_t const *,ulong)

- ea: `0x18001634c`
- end: `0x180016396`
- name: `?SetNumericConfigParm@@YA_NPEB_W0K@Z`
- size: `74`
- prototype: `bool __fastcall(const wchar_t *, const wchar_t *, int)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000ca90`
- `0x18000cb50`
- `0x18000cc10`
- `0x18000ccd0`

## callees

- `0x1800156d4`
- `0x18001634c`

## pseudocode

```c
bool __fastcall SetNumericConfigParm(const wchar_t *a1, const wchar_t *a2, int a3)
{
  bool result; // al
  int v4; // [rsp+20h] [rbp-38h] BYREF
  const wchar_t *v5; // [rsp+28h] [rbp-30h]
  const wchar_t *v6; // [rsp+30h] [rbp-28h]
  int v7; // [rsp+38h] [rbp-20h]
  __int64 v8; // [rsp+40h] [rbp-18h]
  int v9; // [rsp+70h] [rbp+18h] BYREF

  v4 = 1;
  v5 = a1;
  v6 = a2;
  v7 = 0;
  v8 = -2147483646;
  v9 = a3;
  try
  {
    SetValueInternal((struct RegEntry *)&v4, 4u, (BYTE *)&v9, 4u);
    result = 1;
  }
  catch ( exception )
  {
    return 0;
  }
  SetValueInternal((struct RegEntry *)&v4, 4u, (BYTE *)&v9, 4u);
}

```

## disassembly

```asm
0x18001634c  mov     rax, rsp
0x18001634f  sub     rsp, 58h
0x180016353  mov     dword ptr [rax-38h], 1
0x18001635a  mov     [rax-30h], rcx
0x18001635e  mov     [rax-28h], rdx
0x180016362  mov     dword ptr [rax-20h], 0
0x180016369  mov     qword ptr [rax-18h], 0FFFFFFFF80000002h
0x180016371  mov     [rax+18h], r8d
0x180016375  mov     edx, 4; dwType
0x18001637a  mov     r9d, edx; cbData
0x18001637d  lea     r8, [rax+18h]; lpData
0x180016381  lea     rcx, [rax-38h]; struct RegEntry *
0x180016385  call    SetValueInternal
0x18001638a  mov     al, 1
0x18001638c  jmp     short loc_180016390
0x18001638e  xor     al, al
0x180016390  add     rsp, 58h
0x180016394  retn
```
