# DestroyRecipients(MapiRecipDescW *,int)

- ea: `0x1800676ec`
- end: `0x180067736`
- name: `?DestroyRecipients@@YAXPEAUMapiRecipDescW@@H@Z`
- size: `74`
- prototype: `void __fastcall(HLOCAL hMem, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800675cc`
- `0x1800679b0`

## callees

- `0x1800676ec`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180067727`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180067727`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006770d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067718`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006770d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067718`

## pseudocode

```c
void __fastcall DestroyRecipients(LPVOID *hMem, int a2)
{
  __int64 i; // rsi

  if ( hMem )
  {
    for ( i = 0; (int)i < a2; i = (unsigned int)(i + 1) )
    {
      CoTaskMemFree(hMem[5 * i + 1]);
      CoTaskMemFree(hMem[5 * i + 2]);
    }
    LocalFree(hMem);
  }
}

```

## disassembly

```asm
0x1800676ec  test    rcx, rcx
0x1800676ef  jz      short locret_180067735
0x1800676f1  push    rbx
0x1800676f2  push    rbp
0x1800676f3  push    rsi
0x1800676f4  push    rdi
0x1800676f5  sub     rsp, 28h
0x1800676f9  xor     esi, esi
0x1800676fb  mov     ebp, edx
0x1800676fd  mov     rdi, rcx
0x180067700  test    edx, edx
0x180067702  jle     short loc_180067724
0x180067704  lea     rbx, [rsi+rsi*4]
0x180067708  mov     rcx, [rdi+rbx*8+8]; pv
0x18006770d  call    cs:__imp_CoTaskMemFree
0x180067713  mov     rcx, [rdi+rbx*8+10h]; pv
0x180067718  call    cs:__imp_CoTaskMemFree
0x18006771e  inc     esi
0x180067720  cmp     esi, ebp
0x180067722  jl      short loc_180067704
0x180067724  mov     rcx, rdi; hMem
0x180067727  call    cs:__imp_LocalFree
0x18006772d  add     rsp, 28h
0x180067731  pop     rdi
0x180067732  pop     rsi
0x180067733  pop     rbp
0x180067734  pop     rbx
0x180067735  retn
```
