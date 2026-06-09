# CVersionInfo::GetSubcomponentCount(ulong,ulong *)

- ea: `0x180008510`
- end: `0x180008547`
- name: `?GetSubcomponentCount@CVersionInfo@@UEAAJKPEAK@Z`
- size: `55`
- prototype: `__int64 __fastcall(CVersionInfo *__hidden this, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008510`

## pseudocode

```c
__int64 __fastcall CVersionInfo::GetSubcomponentCount(CVersionInfo *this, unsigned int a2, unsigned int *a3)
{
  __int64 v3; // r9
  unsigned int v5; // eax

  v3 = *((_QWORD *)this + 1);
  if ( a2 > (unsigned __int64)((*((_QWORD *)this + 2) - v3) >> 3) )
    return 2147942487LL;
  if ( v3 == *((_QWORD *)this + 2) )
  {
    v5 = 0;
  }
  else
  {
    _mm_lfence();
    v5 = *(_DWORD *)(*(_QWORD *)(v3 + 8LL * a2) + 40LL);
  }
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180008510  mov     r9, [rcx+8]
0x180008514  mov     rax, [rcx+10h]
0x180008518  sub     rax, r9
0x18000851b  mov     r10d, edx
0x18000851e  sar     rax, 3
0x180008522  cmp     r10, rax
0x180008525  jbe     short loc_18000852D
0x180008527  mov     eax, 80070057h
0x18000852c  retn
0x18000852d  cmp     r9, [rcx+10h]
0x180008531  jnz     short loc_180008537
0x180008533  xor     eax, eax
0x180008535  jmp     short loc_180008541
0x180008537  lfence
0x18000853a  mov     rax, [r9+r10*8]
0x18000853e  mov     eax, [rax+28h]
0x180008541  mov     [r8], eax
0x180008544  xor     eax, eax
0x180008546  retn
```
