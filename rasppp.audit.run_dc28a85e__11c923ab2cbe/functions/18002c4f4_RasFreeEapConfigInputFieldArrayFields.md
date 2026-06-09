# RasFreeEapConfigInputFieldArrayFields

- ea: `0x18002c4f4`
- end: `0x18002c5df`
- name: `RasFreeEapConfigInputFieldArrayFields`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18002c5e8`

## callees

- `0x18002c4f4`
- `0x18002c6b8`
- `0x18002cbac`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18002c55f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18002c55f`

## pseudocode

```c
void __fastcall RasFreeEapConfigInputFieldArrayFields(__int64 a1)
{
  _QWORD *v2; // rcx
  __int64 v3; // rdi
  __int64 v4; // rax
  BYTE *v5; // rsi
  __int64 v6; // rdx
  BYTE *v7; // rax
  __int64 i; // rdx
  BYTE *v9; // rcx

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18);
    v2 = WPP_GLOBAL_Control;
  }
  if ( a1 && *(_QWORD *)(a1 + 8) && *(_DWORD *)(a1 + 4) )
  {
    v3 = 0;
    do
    {
      v4 = *(_QWORD *)(a1 + 8);
      v5 = *(BYTE **)(v4 + 40 * v3 + 24);
      if ( v5 )
      {
        v6 = (unsigned int)(lstrlenW(*(LPCWSTR *)(v4 + 40 * v3 + 24)) + 1);
        v7 = v5;
        for ( i = 2 * v6; i; --i )
          *v7++ = 0;
        RasFreeEapMemory(v5);
      }
      v9 = *(BYTE **)(*(_QWORD *)(a1 + 8) + 40 * v3 + 16);
      if ( v9 )
        RasFreeEapMemory(v9);
      v3 = (unsigned int)(v3 + 1);
    }
    while ( (unsigned int)v3 < *(_DWORD *)(a1 + 4) );
    RasFreeEapMemory(*(BYTE **)(a1 + 8));
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 2) != 0 && *((_BYTE *)v2 + 25) >= 6u )
    WPP_SF_(v2[2], 19);
}

```

## disassembly

```asm
0x18002c4f4  push    rbx
0x18002c4f6  push    rbp
0x18002c4f7  push    rsi
0x18002c4f8  push    rdi
0x18002c4f9  push    r15
0x18002c4fb  sub     rsp, 20h
0x18002c4ff  mov     rbx, rcx
0x18002c502  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c509  lea     r15, WPP_GLOBAL_Control
0x18002c510  cmp     rcx, r15
0x18002c513  jz      short loc_18002C536
0x18002c515  test    byte ptr [rcx+1Ch], 2
0x18002c519  jz      short loc_18002C536
0x18002c51b  cmp     byte ptr [rcx+19h], 6
0x18002c51f  jb      short loc_18002C536
0x18002c521  mov     rcx, [rcx+10h]
0x18002c525  mov     edx, 12h
0x18002c52a  call    WPP_SF_
0x18002c52f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c536  test    rbx, rbx
0x18002c539  jz      short loc_18002C5B4
0x18002c53b  cmp     qword ptr [rbx+8], 0
0x18002c540  jz      short loc_18002C5B4
0x18002c542  cmp     dword ptr [rbx+4], 0
0x18002c546  jbe     short loc_18002C5B4
0x18002c548  xor     edi, edi
0x18002c54a  mov     rax, [rbx+8]
0x18002c54e  lea     rbp, [rdi+rdi*4]
0x18002c552  mov     rsi, [rax+rbp*8+18h]
0x18002c557  test    rsi, rsi
0x18002c55a  jz      short loc_18002C58A
0x18002c55c  mov     rcx, rsi; lpString
0x18002c55f  call    cs:__imp_lstrlenW
0x18002c566  nop     dword ptr [rax+rax+00h]
0x18002c56b  lea     edx, [rax+1]
0x18002c56e  mov     rax, rsi
0x18002c571  add     rdx, rdx
0x18002c574  jz      short loc_18002C582
0x18002c576  mov     byte ptr [rax], 0
0x18002c579  inc     rax
0x18002c57c  sub     rdx, 1
0x18002c580  jnz     short loc_18002C576
0x18002c582  mov     rcx, rsi; pData
0x18002c585  call    RasFreeEapMemory
0x18002c58a  mov     rax, [rbx+8]
0x18002c58e  mov     rcx, [rax+rbp*8+10h]; pData
0x18002c593  test    rcx, rcx
0x18002c596  jz      short loc_18002C59D
0x18002c598  call    RasFreeEapMemory
0x18002c59d  inc     edi
0x18002c59f  cmp     edi, [rbx+4]
0x18002c5a2  jb      short loc_18002C54A
0x18002c5a4  mov     rcx, [rbx+8]; pData
0x18002c5a8  call    RasFreeEapMemory
0x18002c5ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c5b4  cmp     rcx, r15
0x18002c5b7  jz      short loc_18002C5D3
0x18002c5b9  test    byte ptr [rcx+1Ch], 2
0x18002c5bd  jz      short loc_18002C5D3
0x18002c5bf  cmp     byte ptr [rcx+19h], 6
0x18002c5c3  jb      short loc_18002C5D3
0x18002c5c5  mov     rcx, [rcx+10h]
0x18002c5c9  mov     edx, 13h
0x18002c5ce  call    WPP_SF_
0x18002c5d3  add     rsp, 20h
0x18002c5d7  pop     r15
0x18002c5d9  pop     rdi
0x18002c5da  pop     rsi
0x18002c5db  pop     rbp
0x18002c5dc  pop     rbx
0x18002c5dd  retn
```
