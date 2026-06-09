# RtlpImageNtHeader

- ea: `0x14000173c`
- end: `0x14000178d`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140001794`

## callees

- `0x14000173c`

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
0x14000173c  sub     rsp, 18h
0x140001740  xor     edx, edx
0x140001742  lea     rax, [rcx-1]
0x140001746  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000174a  ja      short loc_140001785
0x14000174c  mov     eax, 5A4Dh
0x140001751  cmp     [rcx], ax
0x140001754  jnz     short loc_14000177D
0x140001756  movsxd  rax, dword ptr [rcx+3Ch]
0x14000175a  test    eax, eax
0x14000175c  js      short loc_14000177D
0x14000175e  cmp     eax, 10000000h
0x140001763  jnb     short loc_14000177D
0x140001765  lea     rdx, [rcx+rax]
0x140001769  mov     [rsp+18h+var_18], rdx
0x14000176d  xor     eax, eax
0x14000176f  cmp     dword ptr [rdx], 4550h
0x140001775  cmovnz  rdx, rax
0x140001779  mov     [rsp+18h+var_18], rdx
0x14000177d  jmp     short loc_140001785
0x14000177f  xor     edx, edx
0x140001781  mov     [rsp+18h+var_18], rdx
0x140001785  mov     rax, rdx
0x140001788  add     rsp, 18h
0x14000178c  retn
```
