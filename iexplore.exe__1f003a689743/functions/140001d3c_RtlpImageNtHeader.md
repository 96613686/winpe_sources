# RtlpImageNtHeader

- ea: `0x140001d3c`
- end: `0x140001d8d`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140001d94`

## callees

- `0x140001d3c`

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
0x140001d3c  sub     rsp, 18h
0x140001d40  xor     edx, edx
0x140001d42  lea     rax, [rcx-1]
0x140001d46  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140001d4a  ja      short loc_140001D85
0x140001d4c  mov     eax, 5A4Dh
0x140001d51  cmp     [rcx], ax
0x140001d54  jnz     short loc_140001D7D
0x140001d56  movsxd  rax, dword ptr [rcx+3Ch]
0x140001d5a  test    eax, eax
0x140001d5c  js      short loc_140001D7D
0x140001d5e  cmp     eax, 10000000h
0x140001d63  jnb     short loc_140001D7D
0x140001d65  lea     rdx, [rcx+rax]
0x140001d69  mov     [rsp+18h+var_18], rdx
0x140001d6d  xor     eax, eax
0x140001d6f  cmp     dword ptr [rdx], 4550h
0x140001d75  cmovnz  rdx, rax
0x140001d79  mov     [rsp+18h+var_18], rdx
0x140001d7d  jmp     short loc_140001D85
0x140001d7f  xor     edx, edx
0x140001d81  mov     [rsp+18h+var_18], rdx
0x140001d85  mov     rax, rdx
0x140001d88  add     rsp, 18h
0x140001d8c  retn
```
