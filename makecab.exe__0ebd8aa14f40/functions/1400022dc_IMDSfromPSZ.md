# IMDSfromPSZ

- ea: `0x1400022dc`
- end: `0x14000233c`
- name: `IMDSfromPSZ`
- size: `96`
- prototype: `__int64 __fastcall(char *String)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1400025b0`
- `0x1400029e0`
- `0x140002aa0`
- `0x140008244`
- `0x14000836c`

## callees

- `0x1400022dc`

## import_xrefs

- `msvcrt!atol` at `0x14000230e`
- `msvcrt!atol` at `0x140002319`
- `msvcrt!atol` at `0x14000230e`
- `msvcrt!atol` at `0x140002319`
- `msvcrt!_stricmp` at `0x1400022ff`
- `msvcrt!_stricmp` at `0x1400022ff`

## pseudocode

```c
__int64 __fastcall IMDSfromPSZ(char *String)
{
  unsigned int i; // edi
  __int64 v3; // rbx
  int v4; // ebx
  __int64 result; // rax

  for ( i = 0; i < 8; ++i )
  {
    v3 = 4LL * (int)i;
    if ( !_stricmp(String, amds[v3]) )
      break;
    v4 = atol(amds[v3 + 3]);
    if ( atol(String) == v4 )
      break;
  }
  result = 0xFFFFFFFFLL;
  if ( i < 8 )
    return i;
  return result;
}

```

## disassembly

```asm
0x1400022dc  push    rbx
0x1400022de  push    rbp
0x1400022df  push    rsi
0x1400022e0  push    rdi
0x1400022e1  sub     rsp, 28h
0x1400022e5  mov     rsi, rcx
0x1400022e8  lea     rbp, amds
0x1400022ef  xor     edi, edi
0x1400022f1  movsxd  rbx, edi
0x1400022f4  mov     rcx, rsi; String1
0x1400022f7  shl     rbx, 5
0x1400022fb  mov     rdx, [rbx+rbp]; String2
0x1400022ff  call    cs:__imp__stricmp
0x140002305  test    eax, eax
0x140002307  jz      short loc_14000232A
0x140002309  mov     rcx, [rbx+rbp+18h]; String
0x14000230e  call    cs:__imp_atol
0x140002314  mov     rcx, rsi; String
0x140002317  mov     ebx, eax
0x140002319  call    cs:__imp_atol
0x14000231f  cmp     eax, ebx
0x140002321  jz      short loc_14000232A
0x140002323  inc     edi
0x140002325  cmp     edi, 8
0x140002328  jb      short loc_1400022F1
0x14000232a  or      eax, 0FFFFFFFFh
0x14000232d  cmp     edi, 8
0x140002330  cmovb   eax, edi
0x140002333  add     rsp, 28h
0x140002337  pop     rdi
0x140002338  pop     rsi
0x140002339  pop     rbp
0x14000233a  pop     rbx
0x14000233b  retn
```
