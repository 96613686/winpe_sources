# NbtUnlinkNameFromHashTable

- ea: `0x140008110`
- end: `0x140008158`
- name: `NbtUnlinkNameFromHashTable`
- size: `72`
- prototype: ``
- caller_count: `15`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140004038`
- `0x140007df8`
- `0x140007ed8`
- `0x140009ee0`
- `0x14000c570`
- `0x14000e408`
- `0x140014df8`
- `0x14001570c`
- `0x140017214`
- `0x140017a3c`
- `0x140017d80`
- `0x14001b7d0`
- `0x14001d580`
- `0x140022d04`
- `0x140025260`

## callees

- `0x140008110`

## pseudocode

```c
void __fastcall NbtUnlinkNameFromHashTable(__int64 *a1)
{
  __int64 v1; // rdx
  __int64 **v2; // rax

  v1 = *a1;
  if ( *a1 )
  {
    v2 = (__int64 **)a1[1];
    if ( v2 )
    {
      if ( *(__int64 **)(v1 + 8) != a1 || *v2 != a1 )
        __fastfail(3u);
      *v2 = (__int64 *)v1;
      *(_QWORD *)(v1 + 8) = v2;
    }
  }
  if ( *((_DWORD *)a1 + 4) == -87097344 && --dword_140039608 < 0 )
    dword_140039608 = 0;
}

```

## disassembly

```asm
0x140008110  mov     rdx, [rcx]
0x140008113  test    rdx, rdx
0x140008116  jz      short loc_140008133
0x140008118  mov     rax, [rcx+8]
0x14000811c  test    rax, rax
0x14000811f  jz      short loc_140008133
0x140008121  cmp     [rdx+8], rcx
0x140008125  jnz     short loc_140008151
0x140008127  cmp     [rax], rcx
0x14000812a  jnz     short loc_140008151
0x14000812c  mov     [rax], rdx
0x14000812f  mov     [rdx+8], rax
0x140008133  cmp     dword ptr [rcx+10h], 0FACF0000h
0x14000813a  jnz     short locret_14000814F
0x14000813c  sub     cs:dword_140039608, 1
0x140008143  jns     short locret_14000814F
0x140008145  mov     cs:dword_140039608, 0
0x14000814f  retn
0x140008151  mov     ecx, 3
0x140008156  int     29h; Win8: RtlFailFast(ecx)
```
