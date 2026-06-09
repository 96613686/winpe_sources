# TlmiRHAppTableCompare

- ea: `0x18001ab90`
- end: `0x18001abdb`
- name: `TlmiRHAppTableCompare`
- size: `75`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001ab90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18001abaf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18001abaf`

## pseudocode

```c
char __fastcall TlmiRHAppTableCompare(struct _RTL_AVL_TABLE *Table, _QWORD *FirstStruct, _QWORD *SecondStruct)
{
  int v3; // ecx

  if ( *(_DWORD *)FirstStruct != *(_DWORD *)SecondStruct )
    return *(_DWORD *)FirstStruct > *(_DWORD *)SecondStruct;
  v3 = _o__wcsnicmp(FirstStruct[2], SecondStruct[2], 0x7FFF);
  if ( v3 )
    return v3 >= 0;
  else
    return 2;
}

```

## disassembly

```asm
0x18001ab90  sub     rsp, 28h
0x18001ab94  mov     ecx, [rdx]
0x18001ab96  mov     r9, r8
0x18001ab99  mov     rax, rdx
0x18001ab9c  cmp     ecx, [r8]
0x18001ab9f  jnz     short loc_18001ABCD
0x18001aba1  mov     rdx, [r9+10h]
0x18001aba5  mov     r8d, 7FFFh
0x18001abab  mov     rcx, [rax+10h]
0x18001abaf  call    cs:__imp__o__wcsnicmp
0x18001abb6  nop     dword ptr [rax+rax+00h]
0x18001abbb  mov     ecx, eax
0x18001abbd  xor     eax, eax
0x18001abbf  test    ecx, ecx
0x18001abc1  jnz     short loc_18001ABC8
0x18001abc3  lea     eax, [rcx+2]
0x18001abc6  jmp     short loc_18001ABD5
0x18001abc8  setns   al
0x18001abcb  jmp     short loc_18001ABD5
0x18001abcd  xor     eax, eax
0x18001abcf  cmp     ecx, [r8]
0x18001abd2  setnbe  al
0x18001abd5  add     rsp, 28h
0x18001abd9  retn
```
