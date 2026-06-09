# QosGetNetBufferCount

- ea: `0x140007f60`
- end: `0x140007f85`
- name: `QosGetNetBufferCount`
- size: `37`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140004c58`
- `0x140007260`
- `0x14000bdf4`
- `0x140011b58`

## callees

- `0x140007f60`

## pseudocode

```c
__int64 __fastcall QosGetNetBufferCount(__int64 a1, _DWORD *a2)
{
  __int64 *v2; // rcx
  __int64 result; // rax
  int i; // r8d

  v2 = *(__int64 **)(a1 + 8);
  result = 0;
  for ( i = 0; v2; v2 = (__int64 *)*v2 )
  {
    i += *((_DWORD *)v2 + 6);
    result = (unsigned int)(result + 1);
  }
  if ( a2 )
    *a2 = i;
  return result;
}

```

## disassembly

```asm
0x140007f60  mov     rcx, [rcx+8]
0x140007f64  xor     eax, eax
0x140007f66  xor     r8d, r8d
0x140007f69  test    rcx, rcx
0x140007f6c  jz      short loc_140007F7C
0x140007f6e  add     r8d, [rcx+18h]
0x140007f72  inc     eax
0x140007f74  mov     rcx, [rcx]
0x140007f77  test    rcx, rcx
0x140007f7a  jnz     short loc_140007F6E
0x140007f7c  test    rdx, rdx
0x140007f7f  jz      short locret_140007F84
0x140007f81  mov     [rdx], r8d
0x140007f84  retn
```
