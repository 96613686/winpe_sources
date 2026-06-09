# InternalResetCompression

- ea: `0x1800059b8`
- end: `0x1800059d4`
- name: `InternalResetCompression`
- size: `28`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800068d0`
- `0x1800069c0`

## callees

- `0x1800059b8`

## pseudocode

```c
__int64 __fastcall InternalResetCompression(__int64 a1)
{
  __int64 result; // rax

  result = 0;
  *(_QWORD *)(a1 + 104) = 0;
  *(_DWORD *)a1 = 0;
  *(_DWORD *)(a1 + 28) = 0;
  if ( *(_DWORD *)(a1 + 116) )
  {
    *(_QWORD *)(a1 + 124) = 0;
    *(_DWORD *)(a1 + 120) = 0;
  }
  *(_QWORD *)(a1 + 64) = 0;
  return result;
}

```

## disassembly

```asm
0x1800059b8  xor     eax, eax
0x1800059ba  mov     [rcx+68h], rax
0x1800059be  mov     [rcx], eax
0x1800059c0  mov     [rcx+1Ch], eax
0x1800059c3  cmp     [rcx+74h], eax
0x1800059c6  jz      short loc_1800059CF
0x1800059c8  mov     [rcx+7Ch], rax
0x1800059cc  mov     [rcx+78h], eax
0x1800059cf  mov     [rcx+40h], rax
0x1800059d3  retn
```
