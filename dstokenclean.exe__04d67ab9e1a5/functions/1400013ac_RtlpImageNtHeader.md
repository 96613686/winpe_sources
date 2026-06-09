# RtlpImageNtHeader

- ea: `0x1400013ac`
- end: `0x1400013fd`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140001404`

## callees

- `0x1400013ac`

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
0x1400013ac  sub     rsp, 18h
0x1400013b0  xor     edx, edx
0x1400013b2  lea     rax, [rcx-1]
0x1400013b6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400013ba  ja      short loc_1400013F5
0x1400013bc  mov     eax, 5A4Dh
0x1400013c1  cmp     [rcx], ax
0x1400013c4  jnz     short loc_1400013ED
0x1400013c6  movsxd  rax, dword ptr [rcx+3Ch]
0x1400013ca  test    eax, eax
0x1400013cc  js      short loc_1400013ED
0x1400013ce  cmp     eax, 10000000h
0x1400013d3  jnb     short loc_1400013ED
0x1400013d5  lea     rdx, [rcx+rax]
0x1400013d9  mov     [rsp+18h+var_18], rdx
0x1400013dd  xor     eax, eax
0x1400013df  cmp     dword ptr [rdx], 4550h
0x1400013e5  cmovnz  rdx, rax
0x1400013e9  mov     [rsp+18h+var_18], rdx
0x1400013ed  jmp     short loc_1400013F5
0x1400013ef  xor     edx, edx
0x1400013f1  mov     [rsp+18h+var_18], rdx
0x1400013f5  mov     rax, rdx
0x1400013f8  add     rsp, 18h
0x1400013fc  retn
```
