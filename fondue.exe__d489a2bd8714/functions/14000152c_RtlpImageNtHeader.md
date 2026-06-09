# RtlpImageNtHeader

- ea: `0x14000152c`
- end: `0x14000157d`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140001584`

## callees

- `0x14000152c`

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
0x14000152c  sub     rsp, 18h
0x140001530  xor     edx, edx
0x140001532  lea     rax, [rcx-1]
0x140001536  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000153a  ja      short loc_140001575
0x14000153c  mov     eax, 5A4Dh
0x140001541  cmp     [rcx], ax
0x140001544  jnz     short loc_14000156D
0x140001546  movsxd  rax, dword ptr [rcx+3Ch]
0x14000154a  test    eax, eax
0x14000154c  js      short loc_14000156D
0x14000154e  cmp     eax, 10000000h
0x140001553  jnb     short loc_14000156D
0x140001555  lea     rdx, [rcx+rax]
0x140001559  mov     [rsp+18h+var_18], rdx
0x14000155d  xor     eax, eax
0x14000155f  cmp     dword ptr [rdx], 4550h
0x140001565  cmovnz  rdx, rax
0x140001569  mov     [rsp+18h+var_18], rdx
0x14000156d  jmp     short loc_140001575
0x14000156f  xor     edx, edx
0x140001571  mov     [rsp+18h+var_18], rdx
0x140001575  mov     rax, rdx
0x140001578  add     rsp, 18h
0x14000157c  retn
```
