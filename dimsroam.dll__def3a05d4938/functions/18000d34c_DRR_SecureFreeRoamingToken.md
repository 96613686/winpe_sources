# DRR_SecureFreeRoamingToken

- ea: `0x18000d34c`
- end: `0x18000d37b`
- name: `DRR_SecureFreeRoamingToken`
- size: `47`
- prototype: `void __fastcall(unsigned int *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180003fb4`
- `0x1800045f4`
- `0x18000556c`
- `0x180006230`
- `0x18000cde8`
- `0x18000d384`

## callees

- `0x18000d34c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d370`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d370`

## pseudocode

```c
void __fastcall DRR_SecureFreeRoamingToken(unsigned int *a1)
{
  unsigned int *v1; // rdx
  __int64 v2; // rax

  if ( a1 )
  {
    v1 = a1;
    v2 = a1[32] + 132LL;
    do
    {
      *(_BYTE *)v1 = 0;
      v1 = (unsigned int *)((char *)v1 + 1);
      --v2;
    }
    while ( v2 );
    LocalFree(a1);
  }
}

```

## disassembly

```asm
0x18000d34c  sub     rsp, 28h
0x18000d350  test    rcx, rcx
0x18000d353  jz      short loc_18000D376
0x18000d355  mov     eax, [rcx+80h]
0x18000d35b  mov     rdx, rcx
0x18000d35e  add     rax, 84h
0x18000d364  mov     byte ptr [rdx], 0
0x18000d367  inc     rdx
0x18000d36a  sub     rax, 1
0x18000d36e  jnz     short loc_18000D364
0x18000d370  call    cs:__imp_LocalFree
0x18000d376  add     rsp, 28h
0x18000d37a  retn
```
