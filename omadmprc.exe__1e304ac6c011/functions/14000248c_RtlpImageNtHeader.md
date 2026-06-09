# RtlpImageNtHeader

- ea: `0x14000248c`
- end: `0x1400024dd`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1400024e4`

## callees

- `0x14000248c`

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
0x14000248c  sub     rsp, 18h
0x140002490  xor     edx, edx
0x140002492  lea     rax, [rcx-1]
0x140002496  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000249a  ja      short loc_1400024D5
0x14000249c  mov     eax, 5A4Dh
0x1400024a1  cmp     [rcx], ax
0x1400024a4  jnz     short loc_1400024CD
0x1400024a6  movsxd  rax, dword ptr [rcx+3Ch]
0x1400024aa  test    eax, eax
0x1400024ac  js      short loc_1400024CD
0x1400024ae  cmp     eax, 10000000h
0x1400024b3  jnb     short loc_1400024CD
0x1400024b5  lea     rdx, [rcx+rax]
0x1400024b9  mov     [rsp+18h+var_18], rdx
0x1400024bd  xor     eax, eax
0x1400024bf  cmp     dword ptr [rdx], 4550h
0x1400024c5  cmovnz  rdx, rax
0x1400024c9  mov     [rsp+18h+var_18], rdx
0x1400024cd  jmp     short loc_1400024D5
0x1400024cf  xor     edx, edx
0x1400024d1  mov     [rsp+18h+var_18], rdx
0x1400024d5  mov     rax, rdx
0x1400024d8  add     rsp, 18h
0x1400024dc  retn
```
