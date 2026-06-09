# DfscReferralSetCurrentAccessStatus

- ea: `0x14000136c`
- end: `0x14000138b`
- name: `DfscReferralSetCurrentAccessStatus`
- size: `31`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140011c80`
- `0x140021688`
- `0x140024930`

## callees

- `0x14000136c`

## pseudocode

```c
__int64 __fastcall DfscReferralSetCurrentAccessStatus(__int64 a1, int a2)
{
  __int64 v2; // r8
  __int64 result; // rax

  v2 = 112LL * *(unsigned __int16 *)(a1 + 32);
  result = *(_QWORD *)(a1 + 16);
  if ( *(_DWORD *)(v2 + result + 168) != a2 )
    *(_DWORD *)(v2 + result + 168) = a2;
  return result;
}

```

## disassembly

```asm
0x14000136c  movzx   eax, word ptr [rcx+20h]
0x140001370  imul    r8, rax, 70h ; 'p'
0x140001374  mov     rax, [rcx+10h]
0x140001378  cmp     [r8+rax+0A8h], edx
0x140001380  jz      short locret_14000138A
0x140001382  mov     [r8+rax+0A8h], edx
0x14000138a  retn
```
