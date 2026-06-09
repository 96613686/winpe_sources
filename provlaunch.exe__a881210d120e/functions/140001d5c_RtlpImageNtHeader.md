# RtlpImageNtHeader

- ea: `0x140001d5c`
- end: `0x140001dad`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140001db4`

## callees

- `0x140001d5c`

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
0x140001d5c  sub     rsp, 18h
0x140001d60  xor     edx, edx
0x140001d62  lea     rax, [rcx-1]
0x140001d66  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140001d6a  ja      short loc_140001DA5
0x140001d6c  mov     eax, 5A4Dh
0x140001d71  cmp     [rcx], ax
0x140001d74  jnz     short loc_140001D9D
0x140001d76  movsxd  rax, dword ptr [rcx+3Ch]
0x140001d7a  test    eax, eax
0x140001d7c  js      short loc_140001D9D
0x140001d7e  cmp     eax, 10000000h
0x140001d83  jnb     short loc_140001D9D
0x140001d85  lea     rdx, [rcx+rax]
0x140001d89  mov     [rsp+18h+var_18], rdx
0x140001d8d  xor     eax, eax
0x140001d8f  cmp     dword ptr [rdx], 4550h
0x140001d95  cmovnz  rdx, rax
0x140001d99  mov     [rsp+18h+var_18], rdx
0x140001d9d  jmp     short loc_140001DA5
0x140001d9f  xor     edx, edx
0x140001da1  mov     [rsp+18h+var_18], rdx
0x140001da5  mov     rax, rdx
0x140001da8  add     rsp, 18h
0x140001dac  retn
```
