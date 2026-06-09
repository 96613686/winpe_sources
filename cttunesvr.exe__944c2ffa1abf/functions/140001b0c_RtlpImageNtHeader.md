# RtlpImageNtHeader

- ea: `0x140001b0c`
- end: `0x140001b5d`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140001b64`

## callees

- `0x140001b0c`

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
0x140001b0c  sub     rsp, 18h
0x140001b10  xor     edx, edx
0x140001b12  lea     rax, [rcx-1]
0x140001b16  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140001b1a  ja      short loc_140001B55
0x140001b1c  mov     eax, 5A4Dh
0x140001b21  cmp     [rcx], ax
0x140001b24  jnz     short loc_140001B4D
0x140001b26  movsxd  rax, dword ptr [rcx+3Ch]
0x140001b2a  test    eax, eax
0x140001b2c  js      short loc_140001B4D
0x140001b2e  cmp     eax, 10000000h
0x140001b33  jnb     short loc_140001B4D
0x140001b35  lea     rdx, [rcx+rax]
0x140001b39  mov     [rsp+18h+var_18], rdx
0x140001b3d  xor     eax, eax
0x140001b3f  cmp     dword ptr [rdx], 4550h
0x140001b45  cmovnz  rdx, rax
0x140001b49  mov     [rsp+18h+var_18], rdx
0x140001b4d  jmp     short loc_140001B55
0x140001b4f  xor     edx, edx
0x140001b51  mov     [rsp+18h+var_18], rdx
0x140001b55  mov     rax, rdx
0x140001b58  add     rsp, 18h
0x140001b5c  retn
```
