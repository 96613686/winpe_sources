# RtlpImageNtHeader

- ea: `0x1400013fc`
- end: `0x14000144d`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140001454`

## callees

- `0x1400013fc`

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
0x1400013fc  sub     rsp, 18h
0x140001400  xor     edx, edx
0x140001402  lea     rax, [rcx-1]
0x140001406  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000140a  ja      short loc_140001445
0x14000140c  mov     eax, 5A4Dh
0x140001411  cmp     [rcx], ax
0x140001414  jnz     short loc_14000143D
0x140001416  movsxd  rax, dword ptr [rcx+3Ch]
0x14000141a  test    eax, eax
0x14000141c  js      short loc_14000143D
0x14000141e  cmp     eax, 10000000h
0x140001423  jnb     short loc_14000143D
0x140001425  lea     rdx, [rcx+rax]
0x140001429  mov     [rsp+18h+var_18], rdx
0x14000142d  xor     eax, eax
0x14000142f  cmp     dword ptr [rdx], 4550h
0x140001435  cmovnz  rdx, rax
0x140001439  mov     [rsp+18h+var_18], rdx
0x14000143d  jmp     short loc_140001445
0x14000143f  xor     edx, edx
0x140001441  mov     [rsp+18h+var_18], rdx
0x140001445  mov     rax, rdx
0x140001448  add     rsp, 18h
0x14000144c  retn
```
