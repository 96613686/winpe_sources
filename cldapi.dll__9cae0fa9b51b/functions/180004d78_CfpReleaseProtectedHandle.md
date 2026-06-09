# CfpReleaseProtectedHandle

- ea: `0x180004d78`
- end: `0x180004dc7`
- name: `CfpReleaseProtectedHandle`
- size: `79`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800046b0`
- `0x18000dfe0`
- `0x18000e560`
- `0x18000e980`
- `0x18000eaf0`
- `0x18000edb0`
- `0x18000ef50`
- `0x18000f100`
- `0x180012c28`

## callees

- `0x180004d78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180004db5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180004db5`

## pseudocode

```c
void __fastcall CfpReleaseProtectedHandle(__int64 a1)
{
  unsigned __int64 v1; // rcx
  signed __int64 v2; // rax
  __int64 v3; // rtt

  if ( a1 != -1 && (a1 & 1) != 0 )
  {
    v1 = a1 & 0xFFFFFFFFFFFFFFFEuLL;
    do
    {
      v2 = *(_QWORD *)(v1 + 16);
      if ( v2 < 2 )
        break;
      v3 = *(_QWORD *)(v1 + 16);
      if ( v3 == _InterlockedCompareExchange64((volatile signed __int64 *)(v1 + 16), v2 - 2, v2) )
      {
        if ( v2 == 2 )
          SetEvent(*(HANDLE *)(v1 + 8));
        return;
      }
    }
    while ( v2 != 2 );
  }
}

```

## disassembly

```asm
0x180004d78  sub     rsp, 28h
0x180004d7c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180004d80  jz      short loc_180004DC1
0x180004d82  test    cl, 1
0x180004d85  jz      short loc_180004DC1
0x180004d87  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180004d8b  mov     rax, [rcx+10h]
0x180004d8f  cmp     rax, 2
0x180004d93  jl      short loc_180004DC1
0x180004d95  lea     rdx, [rax-2]
0x180004d99  lock cmpxchg [rcx+10h], rdx
0x180004d9f  jz      short loc_180004DAC
0x180004da1  test    rdx, rdx
0x180004da4  jnz     short loc_180004D8B
0x180004da6  add     rsp, 28h
0x180004daa  retn
0x180004dac  test    rdx, rdx
0x180004daf  jnz     short loc_180004DC1
0x180004db1  mov     rcx, [rcx+8]; hEvent
0x180004db5  call    cs:__imp_SetEvent
0x180004dbc  nop     dword ptr [rax+rax+00h]
0x180004dc1  add     rsp, 28h
0x180004dc5  retn
```
