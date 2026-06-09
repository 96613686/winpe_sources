# SetBlockedTracksTo

- ea: `0x180004e20`
- end: `0x180004e5b`
- name: `SetBlockedTracksTo`
- size: `59`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000484c`
- `0x180004ef0`
- `0x180005a1c`

## callees

- `0x180004e20`

## pseudocode

```c
__int64 __fastcall SetBlockedTracksTo(__int64 a1, __int64 a2, int a3)
{
  __int64 v3; // rcx
  __int64 result; // rax
  _DWORD *i; // rdx
  __int64 v6; // rdx

  v3 = qword_18000A628[2 * *(unsigned int *)(a1 + 72)];
  result = v3 + 16;
  for ( i = (_DWORD *)((v3 + 16) & -(__int64)(v3 != 0)); i; i = (_DWORD *)(v6 + 16) )
  {
    if ( *i == 350 )
      *i = a3;
    v6 = *((_QWORD *)i - 2);
    if ( !v6 )
      break;
  }
  return result;
}

```

## disassembly

```asm
0x180004e20  mov     eax, [rcx+48h]
0x180004e23  lea     rcx, qword_18000A628
0x180004e2a  add     rax, rax
0x180004e2d  mov     rcx, [rcx+rax*8]
0x180004e31  lea     rax, [rcx+10h]
0x180004e35  neg     rcx
0x180004e38  sbb     rdx, rdx
0x180004e3b  and     rdx, rax
0x180004e3e  jz      short locret_180004E5A
0x180004e40  cmp     dword ptr [rdx], 15Eh
0x180004e46  jnz     short loc_180004E4B
0x180004e48  mov     [rdx], r8d
0x180004e4b  mov     rdx, [rdx-10h]
0x180004e4f  test    rdx, rdx
0x180004e52  jz      short locret_180004E5A
0x180004e54  add     rdx, 10h
0x180004e58  jnz     short loc_180004E40
0x180004e5a  retn
```
