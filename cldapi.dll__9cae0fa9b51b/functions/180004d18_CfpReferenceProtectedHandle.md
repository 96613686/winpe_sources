# CfpReferenceProtectedHandle

- ea: `0x180004d18`
- end: `0x180004d6f`
- name: `CfpReferenceProtectedHandle`
- size: `87`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004670`
- `0x18000dfe0`
- `0x18000e560`
- `0x18000e830`
- `0x18000e980`
- `0x18000eaf0`
- `0x18000edb0`
- `0x18000ef50`
- `0x18000f100`

## callees

- `0x180004d18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180004d5b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180004d5b`

## pseudocode

```c
char __fastcall CfpReferenceProtectedHandle(__int64 a1, char a2)
{
  unsigned __int64 v2; // rcx
  signed __int64 v3; // rax
  __int64 v4; // rtt

  if ( a1 == -1 || (a1 & 1) == 0 )
    return 1;
  v2 = a1 & 0xFFFFFFFFFFFFFFFEuLL;
  if ( *(_BYTE *)(v2 + 28) || !a2 )
  {
    do
    {
      v3 = *(_QWORD *)(v2 + 16);
      if ( (v3 & 1) == 0 || v3 + 2 <= v3 )
        break;
      v4 = *(_QWORD *)(v2 + 16);
      if ( v4 == _InterlockedCompareExchange64((volatile signed __int64 *)(v2 + 16), v3 + 2, v3) )
      {
        ResetEvent(*(HANDLE *)(v2 + 8));
        return 1;
      }
    }
    while ( v3 != -2 );
  }
  return 0;
}

```

## disassembly

```asm
0x180004d18  sub     rsp, 28h
0x180004d1c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180004d20  jz      short loc_180004D67
0x180004d22  test    cl, 1
0x180004d25  jz      short loc_180004D67
0x180004d27  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180004d2b  cmp     byte ptr [rcx+1Ch], 0
0x180004d2f  jnz     short loc_180004D35
0x180004d31  test    dl, dl
0x180004d33  jnz     short loc_180004D53
0x180004d35  mov     rax, [rcx+10h]
0x180004d39  test    al, 1
0x180004d3b  jz      short loc_180004D53
0x180004d3d  lea     rdx, [rax+2]
0x180004d41  cmp     rdx, rax
0x180004d44  jl      short loc_180004D53
0x180004d46  lock cmpxchg [rcx+10h], rdx
0x180004d4c  jz      short loc_180004D57
0x180004d4e  test    rdx, rdx
0x180004d51  jnz     short loc_180004D35
0x180004d53  xor     al, al
0x180004d55  jmp     short loc_180004D69
0x180004d57  mov     rcx, [rcx+8]; hEvent
0x180004d5b  call    cs:__imp_ResetEvent
0x180004d62  nop     dword ptr [rax+rax+00h]
0x180004d67  mov     al, 1
0x180004d69  add     rsp, 28h
0x180004d6d  retn
```
