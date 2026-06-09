# CMSG_AddBuffer

- ea: `0x180004310`
- end: `0x18000444d`
- name: `CMSG_AddBuffer`
- size: `317`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000423c`
- `0x1800050d0`

## callees

- `0x180004310`
- `0x18000d02c`
- `0x18000e120`
- `0x18001f15d`
- `0x180020010`

## string_xrefs

- `0x1800043a9`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\cmsg.c`
- `0x1800043e5`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\cmsg.c`

## pseudocode

```c
__int64 __fastcall CMSG_AddBuffer(__int64 a1, __int64 a2)
{
  int v2; // eax
  const void *v4; // rsi
  unsigned int v6; // r8d
  __int64 v7; // rax
  int v8; // edx
  unsigned int v9; // edi
  void *v11; // rax
  bool v12; // zf

  v2 = *(_DWORD *)(a1 + 80);
  v4 = 0;
  v6 = (v2 & 0xFFFFFF00) + 256;
  if ( v2 )
  {
    if ( v2 + 1 >= v6 )
    {
      v11 = (void *)(*(__int64 (__fastcall **)(__int64))(a1 + 24))(8LL * ((v2 & 0xFFFFFF00) + 512));
      if ( !v11 )
      {
        v9 = -2146893810;
        DebugTraceError(
          2148073486LL,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\cmsg.c",
          65);
        return v9;
      }
      v12 = *(_DWORD *)(a1 + 80) == 0;
      v4 = *(const void **)(a1 + 72);
      *(_QWORD *)(a1 + 72) = v11;
      if ( !v12 )
        memcpy_0(v11, v4, 8LL * *(unsigned int *)(a1 + 80));
    }
    goto LABEL_3;
  }
  v7 = (*(__int64 (__fastcall **)(__int64))(a1 + 24))(8LL * v6);
  *(_QWORD *)(a1 + 72) = v7;
  if ( v7 )
  {
LABEL_3:
    *(_QWORD *)(*(_QWORD *)(a1 + 72) + 8LL * (unsigned int)(*(_DWORD *)(a1 + 80))++) = a2;
    v9 = 0;
    if ( v4 )
      (*(void (__fastcall **)(const void *))(a1 + 32))(v4);
    return v9;
  }
  v9 = -2146893810;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\cmsg.c",
      (unsigned int)"Status",
      14,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\cmsg.c",
      51);
  return v9;
}

```

## disassembly

```asm
0x180004310  mov     [rsp+arg_0], rbx
0x180004315  mov     [rsp+arg_8], rsi
0x18000431a  push    rdi
0x18000431b  sub     rsp, 40h
0x18000431f  mov     eax, [rcx+50h]
0x180004322  mov     rbx, rcx
0x180004325  mov     ecx, eax
0x180004327  xor     esi, esi
0x180004329  and     ecx, 0FFFFFF00h
0x18000432f  mov     rdi, rdx
0x180004332  lea     r8d, [rcx+100h]
0x180004339  test    eax, eax
0x18000433b  jnz     short loc_180004381
0x18000433d  mov     rax, [rbx+18h]
0x180004341  mov     ecx, r8d
0x180004344  shl     rcx, 3
0x180004348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000434d  mov     [rbx+48h], rax
0x180004351  test    rax, rax
0x180004354  jz      short loc_1800043C3
0x180004356  mov     edx, [rbx+50h]
0x180004359  mov     rax, [rbx+48h]
0x18000435d  mov     [rax+rdx*8], rdi
0x180004361  inc     dword ptr [rbx+50h]
0x180004364  xor     edi, edi
0x180004366  test    rsi, rsi
0x180004369  jnz     loc_18000443C
0x18000436f  mov     rbx, [rsp+48h+arg_0]
0x180004374  mov     eax, edi
0x180004376  mov     rsi, [rsp+48h+arg_8]
0x18000437b  add     rsp, 40h
0x18000437f  pop     rdi
0x180004380  retn
0x180004381  inc     eax
0x180004383  cmp     eax, r8d
0x180004386  jb      short loc_180004356
0x180004388  mov     rax, [rbx+18h]
0x18000438c  add     ecx, 200h
0x180004392  shl     rcx, 3
0x180004396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000439b  test    rax, rax
0x18000439e  jnz     short loc_180004412
0x1800043a0  lea     r9d, [rax+41h]
0x1800043a4  mov     ecx, 8009000Eh
0x1800043a9  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800043b0  mov     edi, 8009000Eh
0x1800043b5  lea     rdx, aStatus; "Status"
0x1800043bc  call    DebugTraceError
0x1800043c1  jmp     short loc_18000436F
0x1800043c3  mov     edi, 8009000Eh
0x1800043c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800043cf  lea     rax, WPP_GLOBAL_Control
0x1800043d6  cmp     rcx, rax
0x1800043d9  jz      short loc_18000436F
0x1800043db  test    byte ptr [rcx+1Ch], 1
0x1800043df  jz      short loc_18000436F
0x1800043e1  mov     rcx, [rcx+10h]
0x1800043e5  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800043ec  mov     [rsp+48h+var_18], 33h ; '3'
0x1800043f4  lea     r9, aStatus; "Status"
0x1800043fb  mov     [rsp+48h+var_20], r8
0x180004400  mov     [rsp+48h+var_28], 8009000Eh
0x180004408  call    WPP_SF_sDsd
0x18000440d  jmp     loc_18000436F
0x180004412  cmp     dword ptr [rbx+50h], 0
0x180004416  mov     rsi, [rbx+48h]
0x18000441a  mov     [rbx+48h], rax
0x18000441e  jbe     loc_180004356
0x180004424  mov     r8d, [rbx+50h]
0x180004428  mov     rdx, rsi; Src
0x18000442b  shl     r8, 3; Size
0x18000442f  mov     rcx, rax; void *
0x180004432  call    memcpy_0
0x180004437  jmp     loc_180004356
0x18000443c  mov     rax, [rbx+20h]
0x180004440  mov     rcx, rsi
0x180004443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004448  jmp     loc_18000436F
```
