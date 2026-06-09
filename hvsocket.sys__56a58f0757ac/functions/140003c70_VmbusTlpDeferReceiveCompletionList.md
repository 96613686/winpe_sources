# VmbusTlpDeferReceiveCompletionList

- ea: `0x140003c70`
- end: `0x140003ce4`
- name: `VmbusTlpDeferReceiveCompletionList`
- size: `116`
- prototype: `void __fastcall(__int64, __int64, char)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400034f4`

## callees

- `0x140003c70`

## pseudocode

```c
void __fastcall VmbusTlpDeferReceiveCompletionList(__int64 a1, __int64 a2, char a3)
{
  _QWORD *v4; // rdx
  __int64 v5; // rax
  _QWORD *v6; // r8
  _QWORD *v7; // rax

  if ( a3 && (*(_DWORD *)(a1 + 152) & 2) == 0 || !*(_QWORD *)(a1 + 176) )
  {
    v4 = (_QWORD *)(a1 + 104);
    v5 = *(_QWORD *)(a1 + 104);
    if ( *(_QWORD *)(v5 + 8) != a1 + 104 )
      goto LABEL_11;
    v6 = *(_QWORD **)(a1 + 112);
    if ( (_QWORD *)*v6 != v4 )
      goto LABEL_11;
    *v6 = v5;
    *(_QWORD *)(v5 + 8) = v6;
    if ( !_InterlockedExchange64((volatile __int64 *)(*(_QWORD *)(a1 + 224) + 104LL), 0) )
    {
      *(_QWORD *)(a1 + 112) = a1 + 104;
      *v4 = v4;
      return;
    }
    v7 = *(_QWORD **)(a2 + 8);
    if ( *v7 != a2 )
LABEL_11:
      __fastfail(3u);
    *v4 = a2;
    *(_QWORD *)(a1 + 112) = v7;
    *v7 = v4;
    *(_QWORD *)(a2 + 8) = v4;
  }
}

```

## disassembly

```asm
0x140003c70  mov     r9, rdx
0x140003c73  test    r8b, r8b
0x140003c76  jz      short loc_140003C82
0x140003c78  mov     eax, [rcx+98h]
0x140003c7e  test    al, 2
0x140003c80  jz      short loc_140003C8C
0x140003c82  cmp     qword ptr [rcx+0B0h], 0
0x140003c8a  jnz     short locret_140003CD2
0x140003c8c  lea     rdx, [rcx+68h]
0x140003c90  mov     rax, [rdx]
0x140003c93  cmp     [rax+8], rdx
0x140003c97  jnz     short loc_140003CDD
0x140003c99  mov     r8, [rdx+8]
0x140003c9d  cmp     [r8], rdx
0x140003ca0  jnz     short loc_140003CDD
0x140003ca2  mov     [r8], rax
0x140003ca5  mov     [rax+8], r8
0x140003ca9  mov     rax, [rcx+0E0h]
0x140003cb0  xor     ecx, ecx
0x140003cb2  xchg    rcx, [rax+68h]
0x140003cb6  test    rcx, rcx
0x140003cb9  jz      short loc_140003CD4
0x140003cbb  mov     rax, [r9+8]
0x140003cbf  cmp     [rax], r9
0x140003cc2  jnz     short loc_140003CDD
0x140003cc4  mov     [rdx], r9
0x140003cc7  mov     [rdx+8], rax
0x140003ccb  mov     [rax], rdx
0x140003cce  mov     [r9+8], rdx
0x140003cd2  retn
0x140003cd4  mov     [rdx+8], rdx
0x140003cd8  mov     [rdx], rdx
0x140003cdb  retn
0x140003cdd  mov     ecx, 3
0x140003ce2  int     29h; Win8: RtlFailFast(ecx)
```
