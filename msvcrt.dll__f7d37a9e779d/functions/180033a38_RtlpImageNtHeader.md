# RtlpImageNtHeader

- ea: `0x180033a38`
- end: `0x180033a89`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180033a90`

## callees

- `0x180033a38`

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
0x180033a38  sub     rsp, 18h
0x180033a3c  xor     edx, edx
0x180033a3e  lea     rax, [rcx-1]
0x180033a42  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180033a46  ja      short loc_180033A81
0x180033a48  mov     eax, 5A4Dh
0x180033a4d  cmp     [rcx], ax
0x180033a50  jnz     short loc_180033A79
0x180033a52  movsxd  rax, dword ptr [rcx+3Ch]
0x180033a56  test    eax, eax
0x180033a58  js      short loc_180033A79
0x180033a5a  cmp     eax, 10000000h
0x180033a5f  jnb     short loc_180033A79
0x180033a61  lea     rdx, [rcx+rax]
0x180033a65  mov     [rsp+18h+var_18], rdx
0x180033a69  xor     eax, eax
0x180033a6b  cmp     dword ptr [rdx], 4550h
0x180033a71  cmovnz  rdx, rax
0x180033a75  mov     [rsp+18h+var_18], rdx
0x180033a79  jmp     short loc_180033A81
0x180033a7b  xor     edx, edx
0x180033a7d  mov     [rsp+18h+var_18], rdx
0x180033a81  mov     rax, rdx
0x180033a84  add     rsp, 18h
0x180033a88  retn
```
