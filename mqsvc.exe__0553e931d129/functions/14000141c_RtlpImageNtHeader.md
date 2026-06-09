# RtlpImageNtHeader

- ea: `0x14000141c`
- end: `0x14000146d`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140001474`

## callees

- `0x14000141c`

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
0x14000141c  sub     rsp, 18h
0x140001420  xor     edx, edx
0x140001422  lea     rax, [rcx-1]
0x140001426  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000142a  ja      short loc_140001465
0x14000142c  mov     eax, 5A4Dh
0x140001431  cmp     [rcx], ax
0x140001434  jnz     short loc_14000145D
0x140001436  movsxd  rax, dword ptr [rcx+3Ch]
0x14000143a  test    eax, eax
0x14000143c  js      short loc_14000145D
0x14000143e  cmp     eax, 10000000h
0x140001443  jnb     short loc_14000145D
0x140001445  lea     rdx, [rcx+rax]
0x140001449  mov     [rsp+18h+var_18], rdx
0x14000144d  xor     eax, eax
0x14000144f  cmp     dword ptr [rdx], 4550h
0x140001455  cmovnz  rdx, rax
0x140001459  mov     [rsp+18h+var_18], rdx
0x14000145d  jmp     short loc_140001465
0x14000145f  xor     edx, edx
0x140001461  mov     [rsp+18h+var_18], rdx
0x140001465  mov     rax, rdx
0x140001468  add     rsp, 18h
0x14000146c  retn
```
