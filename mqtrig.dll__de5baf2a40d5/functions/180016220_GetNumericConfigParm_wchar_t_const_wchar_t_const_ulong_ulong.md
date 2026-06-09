# GetNumericConfigParm(wchar_t const *,wchar_t const *,ulong *,ulong)

- ea: `0x180016220`
- end: `0x18001626a`
- name: `?GetNumericConfigParm@@YAXPEB_W0PEAKK@Z`
- size: `74`
- prototype: `void __fastcall(const wchar_t *, const wchar_t *, unsigned int *, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000c7b0`
- `0x18000c830`
- `0x18000c8c0`
- `0x18000c940`

## callees

- `0x18001557c`
- `0x180016220`

## pseudocode

```c
void __fastcall GetNumericConfigParm(const wchar_t *a1, const wchar_t *a2, unsigned int *a3, unsigned int a4)
{
  int v4; // [rsp+20h] [rbp-38h] BYREF
  const wchar_t *v5; // [rsp+28h] [rbp-30h]
  const wchar_t *v6; // [rsp+30h] [rbp-28h]
  unsigned int v7; // [rsp+38h] [rbp-20h]
  __int64 v8; // [rsp+40h] [rbp-18h]
  unsigned int v11; // [rsp+78h] [rbp+20h] BYREF

  v11 = a4;
  v4 = 1;
  v5 = a1;
  v6 = a2;
  v7 = a4;
  v8 = -2147483646;
  *a3 = a4;
  try
  {
    QueryValueInternal((struct RegEntry *)&v4);
  }
  catch ( exception )
  {
    v4 = 0;
    v5 = a1;
    v6 = a2;
    v7 = 0;
    v8 = -2147483646;
    SetValueInternal((struct RegEntry *)&v4, 4u, (BYTE *)&v11, 4u);
  }
}

```

## disassembly

```asm
0x180016220  mov     rax, rsp
0x180016223  mov     [rax+20h], r9d
0x180016227  mov     [rax+10h], rdx
0x18001622b  mov     [rax+8], rcx
0x18001622f  sub     rsp, 58h
0x180016233  mov     dword ptr [rax-38h], 1
0x18001623a  mov     [rax-30h], rcx
0x18001623e  mov     [rax-28h], rdx
0x180016242  mov     [rax-20h], r9d
0x180016246  mov     qword ptr [rax-18h], 0FFFFFFFF80000002h
0x18001624e  mov     [r8], r9d
0x180016251  mov     edx, 4
0x180016256  mov     r9d, edx
0x180016259  lea     rcx, [rax-38h]; struct RegEntry *
0x18001625d  call    QueryValueInternal
0x180016262  jmp     short $+2
0x180016264  add     rsp, 58h
0x180016268  retn
```
