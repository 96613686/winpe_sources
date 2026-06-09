# RtlpImageNtHeader

- ea: `0x14000285c`
- end: `0x1400028ad`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1400028b4`

## callees

- `0x14000285c`

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
0x14000285c  sub     rsp, 18h
0x140002860  xor     edx, edx
0x140002862  lea     rax, [rcx-1]
0x140002866  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000286a  ja      short loc_1400028A5
0x14000286c  mov     eax, 5A4Dh
0x140002871  cmp     [rcx], ax
0x140002874  jnz     short loc_14000289D
0x140002876  movsxd  rax, dword ptr [rcx+3Ch]
0x14000287a  test    eax, eax
0x14000287c  js      short loc_14000289D
0x14000287e  cmp     eax, 10000000h
0x140002883  jnb     short loc_14000289D
0x140002885  lea     rdx, [rcx+rax]
0x140002889  mov     [rsp+18h+var_18], rdx
0x14000288d  xor     eax, eax
0x14000288f  cmp     dword ptr [rdx], 4550h
0x140002895  cmovnz  rdx, rax
0x140002899  mov     [rsp+18h+var_18], rdx
0x14000289d  jmp     short loc_1400028A5
0x14000289f  xor     edx, edx
0x1400028a1  mov     [rsp+18h+var_18], rdx
0x1400028a5  mov     rax, rdx
0x1400028a8  add     rsp, 18h
0x1400028ac  retn
```
