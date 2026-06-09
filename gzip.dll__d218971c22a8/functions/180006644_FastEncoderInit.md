# FastEncoderInit

- ea: `0x180006644`
- end: `0x1800066a6`
- name: `FastEncoderInit`
- size: `98`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800028e0`

## callees

- `0x180006644`
- `0x180006ad5`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000665c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000665c`

## pseudocode

```c
__int64 __fastcall FastEncoderInit(__int64 a1)
{
  __int64 result; // rax

  result = (__int64)HeapAlloc(g_hHeap, 0, 0x9310u);
  *(_QWORD *)(a1 + 96) = result;
  if ( result )
  {
    memset_0((void *)(result + 33546), 0, 0x1000u);
    *(_DWORD *)(a1 + 72) = 0x2000;
    *(_DWORD *)(a1 + 32) = 0x2000;
    *(_DWORD *)(a1 + 36) = 0x2000;
    *(_DWORD *)(*(_QWORD *)(a1 + 96) + 37644LL) = 0;
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180006644  push    rbx
0x180006646  sub     rsp, 20h
0x18000664a  mov     rbx, rcx
0x18000664d  xor     edx, edx; dwFlags
0x18000664f  mov     rcx, cs:g_hHeap; hHeap
0x180006656  mov     r8d, 9310h; dwBytes
0x18000665c  call    cs:__imp_HeapAlloc
0x180006662  mov     [rbx+60h], rax
0x180006666  test    rax, rax
0x180006669  jz      short loc_1800066A0
0x18000666b  lea     rcx, [rax+830Ah]; void *
0x180006672  xor     edx, edx; Val
0x180006674  mov     r8d, 1000h; Size
0x18000667a  call    memset_0
0x18000667f  mov     eax, 2000h
0x180006684  mov     [rbx+48h], eax
0x180006687  mov     [rbx+20h], eax
0x18000668a  mov     [rbx+24h], eax
0x18000668d  mov     rax, [rbx+60h]
0x180006691  mov     dword ptr [rax+930Ch], 0
0x18000669b  mov     eax, 1
0x1800066a0  add     rsp, 20h
0x1800066a4  pop     rbx
0x1800066a5  retn
```
