# RtlpImageNtHeader

- ea: `0x14001085c`
- end: `0x1400108ad`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1400108b4`

## callees

- `0x14001085c`

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
0x14001085c  sub     rsp, 18h
0x140010860  xor     edx, edx
0x140010862  lea     rax, [rcx-1]
0x140010866  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001086a  ja      short loc_1400108A5
0x14001086c  mov     eax, 5A4Dh
0x140010871  cmp     [rcx], ax
0x140010874  jnz     short loc_14001089D
0x140010876  movsxd  rax, dword ptr [rcx+3Ch]
0x14001087a  test    eax, eax
0x14001087c  js      short loc_14001089D
0x14001087e  cmp     eax, 10000000h
0x140010883  jnb     short loc_14001089D
0x140010885  lea     rdx, [rcx+rax]
0x140010889  mov     [rsp+18h+var_18], rdx
0x14001088d  xor     eax, eax
0x14001088f  cmp     dword ptr [rdx], 4550h
0x140010895  cmovnz  rdx, rax
0x140010899  mov     [rsp+18h+var_18], rdx
0x14001089d  jmp     short loc_1400108A5
0x14001089f  xor     edx, edx
0x1400108a1  mov     [rsp+18h+var_18], rdx
0x1400108a5  mov     rax, rdx
0x1400108a8  add     rsp, 18h
0x1400108ac  retn
```
