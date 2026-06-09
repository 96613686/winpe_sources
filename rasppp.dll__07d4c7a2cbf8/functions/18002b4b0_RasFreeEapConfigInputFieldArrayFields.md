# RasFreeEapConfigInputFieldArrayFields

- ea: `0x18002b4b0`
- end: `0x18002b594`
- name: `RasFreeEapConfigInputFieldArrayFields`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18002b59c`

## callees

- `0x18002b4b0`
- `0x18002b66c`
- `0x18002bb54`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18002b51b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18002b51b`

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
0x18002b4b0  push    rbx
0x18002b4b2  push    rbp
0x18002b4b3  push    rsi
0x18002b4b4  push    rdi
0x18002b4b5  push    r15
0x18002b4b7  sub     rsp, 20h
0x18002b4bb  mov     rbx, rcx
0x18002b4be  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b4c5  lea     r15, WPP_GLOBAL_Control
0x18002b4cc  cmp     rcx, r15
0x18002b4cf  jz      short loc_18002B4F2
0x18002b4d1  test    byte ptr [rcx+1Ch], 2
0x18002b4d5  jz      short loc_18002B4F2
0x18002b4d7  cmp     byte ptr [rcx+19h], 6
0x18002b4db  jb      short loc_18002B4F2
0x18002b4dd  mov     rcx, [rcx+10h]
0x18002b4e1  mov     edx, 12h
0x18002b4e6  call    WPP_SF_
0x18002b4eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b4f2  test    rbx, rbx
0x18002b4f5  jz      short loc_18002B56A
0x18002b4f7  cmp     qword ptr [rbx+8], 0
0x18002b4fc  jz      short loc_18002B56A
0x18002b4fe  cmp     dword ptr [rbx+4], 0
0x18002b502  jbe     short loc_18002B56A
0x18002b504  xor     edi, edi
0x18002b506  mov     rax, [rbx+8]
0x18002b50a  lea     rbp, [rdi+rdi*4]
0x18002b50e  mov     rsi, [rax+rbp*8+18h]
0x18002b513  test    rsi, rsi
0x18002b516  jz      short loc_18002B540
0x18002b518  mov     rcx, rsi; lpString
0x18002b51b  call    cs:__imp_lstrlenW
0x18002b521  lea     edx, [rax+1]
0x18002b524  mov     rax, rsi
0x18002b527  add     rdx, rdx
0x18002b52a  jz      short loc_18002B538
0x18002b52c  mov     byte ptr [rax], 0
0x18002b52f  inc     rax
0x18002b532  sub     rdx, 1
0x18002b536  jnz     short loc_18002B52C
0x18002b538  mov     rcx, rsi; pData
0x18002b53b  call    RasFreeEapMemory
0x18002b540  mov     rax, [rbx+8]
0x18002b544  mov     rcx, [rax+rbp*8+10h]; pData
0x18002b549  test    rcx, rcx
0x18002b54c  jz      short loc_18002B553
0x18002b54e  call    RasFreeEapMemory
0x18002b553  inc     edi
0x18002b555  cmp     edi, [rbx+4]
0x18002b558  jb      short loc_18002B506
0x18002b55a  mov     rcx, [rbx+8]; pData
0x18002b55e  call    RasFreeEapMemory
0x18002b563  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b56a  cmp     rcx, r15
0x18002b56d  jz      short loc_18002B589
0x18002b56f  test    byte ptr [rcx+1Ch], 2
0x18002b573  jz      short loc_18002B589
0x18002b575  cmp     byte ptr [rcx+19h], 6
0x18002b579  jb      short loc_18002B589
0x18002b57b  mov     rcx, [rcx+10h]
0x18002b57f  mov     edx, 13h
0x18002b584  call    WPP_SF_
0x18002b589  add     rsp, 20h
0x18002b58d  pop     r15
0x18002b58f  pop     rdi
0x18002b590  pop     rsi
0x18002b591  pop     rbp
0x18002b592  pop     rbx
0x18002b593  retn
```
