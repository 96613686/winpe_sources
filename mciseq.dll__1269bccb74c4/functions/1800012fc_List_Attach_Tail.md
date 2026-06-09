# List_Attach_Tail

- ea: `0x1800012fc`
- end: `0x18000133c`
- name: `List_Attach_Tail`
- size: `64`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002eac`
- `0x180003a34`
- `0x180003bb8`
- `0x1800042b0`

## callees

- `0x1800012fc`

## pseudocode

```c
__int64 __fastcall List_Attach_Tail(unsigned int a1, __int64 a2)
{
  __int64 *v2; // rdx
  __int64 result; // rax
  __int64 **v4; // r8
  __int64 *v5; // rcx

  v2 = (__int64 *)(a2 - 16);
  result = 2LL * a1;
  v4 = (__int64 **)qword_18000A628[2 * a1];
  if ( v4 )
  {
    v5 = *v4;
    if ( *v4 )
    {
      do
      {
        result = *v5;
        v4 = (__int64 **)v5;
        v5 = (__int64 *)result;
      }
      while ( result );
    }
    *v4 = v2;
  }
  else
  {
    qword_18000A628[2 * a1] = (__int64)v2;
  }
  *v2 = 0;
  return result;
}

```

## disassembly

```asm
0x1800012fc  mov     eax, ecx
0x1800012fe  add     rdx, 0FFFFFFFFFFFFFFF0h
0x180001302  add     rax, rax
0x180001305  lea     rcx, qword_18000A628
0x18000130c  mov     r8, [rcx+rax*8]
0x180001310  test    r8, r8
0x180001313  jnz     short loc_18000131B
0x180001315  mov     [rcx+rax*8], rdx
0x180001319  jmp     short loc_180001334
0x18000131b  mov     rcx, [r8]
0x18000131e  test    rcx, rcx
0x180001321  jz      short loc_180001331
0x180001323  mov     rax, [rcx]
0x180001326  mov     r8, rcx
0x180001329  mov     rcx, rax
0x18000132c  test    rax, rax
0x18000132f  jnz     short loc_180001323
0x180001331  mov     [r8], rdx
0x180001334  mov     qword ptr [rdx], 0
0x18000133b  retn
```
