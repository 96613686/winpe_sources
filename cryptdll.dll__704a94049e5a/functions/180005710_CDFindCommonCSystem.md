# CDFindCommonCSystem

- ea: `0x180005710`
- end: `0x180005773`
- name: `CDFindCommonCSystem`
- size: `99`
- prototype: `__int64 __fastcall(unsigned int, __int64, _DWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005710`

## pseudocode

```c
__int64 __fastcall CDFindCommonCSystem(unsigned int a1, __int64 a2, _DWORD *a3)
{
  __int64 v5; // r9
  unsigned int i; // r8d
  int v7; // ecx

  *a3 = 0;
  v5 = 0;
LABEL_2:
  if ( (unsigned int)v5 >= a1 )
    return 2148008769LL;
  for ( i = 0; ; ++i )
  {
    if ( i >= cCSystems )
    {
      v5 = (unsigned int)(v5 + 1);
      goto LABEL_2;
    }
    v7 = *(_DWORD *)(a2 + 4 * v5);
    if ( v7 == LODWORD(CSystems[16 * (unsigned __int64)i]) )
      break;
  }
  *a3 = v7;
  return 0;
}

```

## disassembly

```asm
0x180005710  mov     [rsp+arg_0], rbx
0x180005715  mov     [rsp+arg_8], rdi
0x18000571a  mov     r10, r8
0x18000571d  mov     dword ptr [r8], 0
0x180005724  mov     r11d, ecx
0x180005727  xor     r9d, r9d
0x18000572a  cmp     r9d, r11d
0x18000572d  jnb     short loc_180005763
0x18000572f  xor     r8d, r8d
0x180005732  cmp     r8d, cs:cCSystems
0x180005739  jnb     short loc_180005757
0x18000573b  mov     ecx, [rdx+r9*4]
0x18000573f  lea     rdi, CSystems
0x180005746  mov     eax, r8d
0x180005749  shl     rax, 7
0x18000574d  cmp     ecx, [rax+rdi]
0x180005750  jz      short loc_18000575C
0x180005752  inc     r8d
0x180005755  jmp     short loc_180005732
0x180005757  inc     r9d
0x18000575a  jmp     short loc_18000572A
0x18000575c  mov     [r10], ecx
0x18000575f  xor     eax, eax
0x180005761  jmp     short loc_180005768
0x180005763  mov     eax, 80080341h
0x180005768  mov     rbx, [rsp+arg_0]
0x18000576d  mov     rdi, [rsp+arg_8]
0x180005772  retn
```
