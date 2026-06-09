# RtlpImageNtHeader

- ea: `0x14000283c`
- end: `0x14000288d`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140002894`

## callees

- `0x14000283c`

## pseudocode

```c
__int64 __fastcall RtlpImageNtHeader(__int64 a1)
{
  __int64 v1; // rdx
  __int64 v2; // rax

  v1 = 0;
  if ( (unsigned __int64)(a1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && *(_WORD *)a1 == 23117 )
  {
    v2 = *(int *)(a1 + 60);
    if ( (unsigned int)v2 < 0x10000000 )
    {
      v1 = a1 + v2;
      if ( *(_DWORD *)(a1 + v2) != 17744 )
        return 0;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x14000283c  sub     rsp, 18h
0x140002840  xor     edx, edx
0x140002842  lea     rax, [rcx-1]
0x140002846  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000284a  ja      short loc_140002885
0x14000284c  mov     eax, 5A4Dh
0x140002851  cmp     [rcx], ax
0x140002854  jnz     short loc_14000287D
0x140002856  movsxd  rax, dword ptr [rcx+3Ch]
0x14000285a  test    eax, eax
0x14000285c  js      short loc_14000287D
0x14000285e  cmp     eax, 10000000h
0x140002863  jnb     short loc_14000287D
0x140002865  lea     rdx, [rcx+rax]
0x140002869  mov     [rsp+18h+var_18], rdx
0x14000286d  xor     eax, eax
0x14000286f  cmp     dword ptr [rdx], 4550h
0x140002875  cmovnz  rdx, rax
0x140002879  mov     [rsp+18h+var_18], rdx
0x14000287d  jmp     short loc_140002885
0x14000287f  xor     edx, edx
0x140002881  mov     [rsp+18h+var_18], rdx
0x140002885  mov     rax, rdx
0x140002888  add     rsp, 18h
0x14000288c  retn
```
