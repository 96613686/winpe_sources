# RtlpImageNtHeader

- ea: `0x18000abf8`
- end: `0x18000ac49`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18000a96c`

## callees

- `0x18000abf8`

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
0x18000abf8  sub     rsp, 18h
0x18000abfc  xor     edx, edx
0x18000abfe  lea     rax, [rcx-1]
0x18000ac02  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000ac06  ja      short loc_18000AC41
0x18000ac08  mov     eax, 5A4Dh
0x18000ac0d  cmp     [rcx], ax
0x18000ac10  jnz     short loc_18000AC39
0x18000ac12  movsxd  rax, dword ptr [rcx+3Ch]
0x18000ac16  test    eax, eax
0x18000ac18  js      short loc_18000AC39
0x18000ac1a  cmp     eax, 10000000h
0x18000ac1f  jnb     short loc_18000AC39
0x18000ac21  lea     rdx, [rcx+rax]
0x18000ac25  mov     [rsp+18h+var_18], rdx
0x18000ac29  xor     eax, eax
0x18000ac2b  cmp     dword ptr [rdx], 4550h
0x18000ac31  cmovnz  rdx, rax
0x18000ac35  mov     [rsp+18h+var_18], rdx
0x18000ac39  jmp     short loc_18000AC41
0x18000ac3b  xor     edx, edx
0x18000ac3d  mov     [rsp+18h+var_18], rdx
0x18000ac41  mov     rax, rdx
0x18000ac44  add     rsp, 18h
0x18000ac48  retn
```
