# RtlpImageNtHeader

- ea: `0x14000144c`
- end: `0x14000149d`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1400014a4`

## callees

- `0x14000144c`

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
0x14000144c  sub     rsp, 18h
0x140001450  xor     edx, edx
0x140001452  lea     rax, [rcx-1]
0x140001456  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000145a  ja      short loc_140001495
0x14000145c  mov     eax, 5A4Dh
0x140001461  cmp     [rcx], ax
0x140001464  jnz     short loc_14000148D
0x140001466  movsxd  rax, dword ptr [rcx+3Ch]
0x14000146a  test    eax, eax
0x14000146c  js      short loc_14000148D
0x14000146e  cmp     eax, 10000000h
0x140001473  jnb     short loc_14000148D
0x140001475  lea     rdx, [rcx+rax]
0x140001479  mov     [rsp+18h+var_18], rdx
0x14000147d  xor     eax, eax
0x14000147f  cmp     dword ptr [rdx], 4550h
0x140001485  cmovnz  rdx, rax
0x140001489  mov     [rsp+18h+var_18], rdx
0x14000148d  jmp     short loc_140001495
0x14000148f  xor     edx, edx
0x140001491  mov     [rsp+18h+var_18], rdx
0x140001495  mov     rax, rdx
0x140001498  add     rsp, 18h
0x14000149c  retn
```
