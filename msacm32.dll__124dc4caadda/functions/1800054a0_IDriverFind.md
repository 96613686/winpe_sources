# IDriverFind

- ea: `0x1800054a0`
- end: `0x180005522`
- name: `IDriverFind`
- size: `130`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004b70`

## callees

- `0x1800054a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000550c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000550c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800054f2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800054f2`

## pseudocode

```c
__int64 __fastcall IDriverFind(__int64 a1, const WCHAR *a2, char a3)
{
  __int64 CurrentThreadId; // rsi
  __int64 v7; // rbx
  int v8; // edi
  bool v9; // zf

  if ( *(_QWORD *)(a1 + 96) )
  {
    CurrentThreadId = 0;
    if ( (a3 & 8) == 0 )
      CurrentThreadId = GetCurrentThreadId();
    v7 = *(_QWORD *)(a1 + 96);
    v8 = a3 & 7;
    while ( 1 )
    {
      if ( !v7 )
        return 0;
      if ( *(_QWORD *)(v7 + 36) == CurrentThreadId )
        break;
LABEL_10:
      v7 = *(_QWORD *)(v7 + 20);
    }
    if ( v8 != 4 )
    {
      if ( v8 == 1 )
      {
        v9 = lstrcmpW(a2, (LPCWSTR)(v7 + 120)) == 0;
LABEL_9:
        if ( v9 )
          return v7;
        goto LABEL_10;
      }
      if ( (unsigned int)(v8 - 2) > 1 )
        return 0;
    }
    v9 = *(_QWORD *)(v7 + 44) == (_QWORD)a2;
    goto LABEL_9;
  }
  return 0;
}

```

## disassembly

```asm
0x1800054a0  push    rbx
0x1800054a2  push    rbp
0x1800054a3  push    rsi
0x1800054a4  push    rdi
0x1800054a5  sub     rsp, 28h
0x1800054a9  cmp     qword ptr [rcx+60h], 0
0x1800054ae  mov     edi, r8d
0x1800054b1  mov     rbp, rdx
0x1800054b4  mov     rbx, rcx
0x1800054b7  jz      short loc_180005508
0x1800054b9  xor     esi, esi
0x1800054bb  test    dil, 8
0x1800054bf  jz      short loc_18000550C
0x1800054c1  mov     rbx, [rbx+60h]
0x1800054c5  and     edi, 7
0x1800054c8  test    rbx, rbx
0x1800054cb  jz      short loc_180005508
0x1800054cd  cmp     [rbx+24h], rsi
0x1800054d1  jnz     short loc_1800054DE
0x1800054d3  cmp     edi, 4
0x1800054d6  jnz     short loc_1800054E4
0x1800054d8  cmp     [rbx+2Ch], rbp
0x1800054dc  jz      short loc_1800054FC
0x1800054de  mov     rbx, [rbx+14h]
0x1800054e2  jmp     short loc_1800054C8
0x1800054e4  mov     eax, edi
0x1800054e6  sub     eax, 1
0x1800054e9  jnz     short loc_180005516
0x1800054eb  lea     rdx, [rbx+78h]; lpString2
0x1800054ef  mov     rcx, rbp; lpString1
0x1800054f2  call    cs:__imp_lstrcmpW
0x1800054f8  test    eax, eax
0x1800054fa  jmp     short loc_1800054DC
0x1800054fc  mov     rax, rbx
0x1800054ff  add     rsp, 28h
0x180005503  pop     rdi
0x180005504  pop     rsi
0x180005505  pop     rbp
0x180005506  pop     rbx
0x180005507  retn
0x180005508  xor     eax, eax
0x18000550a  jmp     short loc_1800054FF
0x18000550c  call    cs:__imp_GetCurrentThreadId
0x180005512  mov     esi, eax
0x180005514  jmp     short loc_1800054C1
0x180005516  sub     eax, 1
0x180005519  jz      short loc_1800054D8
0x18000551b  cmp     eax, 1
0x18000551e  jnz     short loc_180005508
0x180005520  jmp     short loc_1800054D8
```
