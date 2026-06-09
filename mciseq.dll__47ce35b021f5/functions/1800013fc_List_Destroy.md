# List_Destroy

- ea: `0x1800013fc`
- end: `0x180001456`
- name: `List_Destroy`
- size: `90`
- prototype: `HLOCAL __fastcall(unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000240c`
- `0x180003d28`
- `0x1800042b0`
- `0x180005a1c`

## callees

- `0x1800013fc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001428`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001428`

## pseudocode

```c
HLOCAL __fastcall List_Destroy(unsigned int a1)
{
  __int64 v1; // rdi
  __int64 **v2; // rcx
  __int64 *v3; // rbx
  HLOCAL result; // rax

  v1 = 2LL * a1;
  v2 = (__int64 **)*(&arrayOfLists + 2 * a1 + 1);
  if ( v2 )
  {
    do
    {
      v3 = *v2;
      result = LocalFree(v2[1]);
      v2 = (__int64 **)v3;
    }
    while ( v3 );
  }
  *(&arrayOfLists + v1 + 1) = 0;
  *((_DWORD *)&arrayOfLists + 2 * v1) = 0;
  return result;
}

```

## disassembly

```asm
0x1800013fc  mov     [rsp+arg_0], rbx
0x180001401  mov     [rsp+arg_8], rsi
0x180001406  push    rdi
0x180001407  sub     rsp, 20h
0x18000140b  mov     edi, ecx
0x18000140d  lea     rsi, arrayOfLists
0x180001414  add     rdi, rdi
0x180001417  mov     rcx, [rsi+rdi*8+8]
0x18000141c  test    rcx, rcx
0x18000141f  jz      short loc_180001436
0x180001421  mov     rbx, [rcx]
0x180001424  mov     rcx, [rcx+8]; hMem
0x180001428  call    cs:__imp_LocalFree
0x18000142e  mov     rcx, rbx
0x180001431  test    rbx, rbx
0x180001434  jnz     short loc_180001421
0x180001436  mov     rbx, [rsp+28h+arg_0]
0x18000143b  mov     qword ptr [rsi+rdi*8+8], 0
0x180001444  mov     dword ptr [rsi+rdi*8], 0
0x18000144b  mov     rsi, [rsp+28h+arg_8]
0x180001450  add     rsp, 20h
0x180001454  pop     rdi
0x180001455  retn
```
