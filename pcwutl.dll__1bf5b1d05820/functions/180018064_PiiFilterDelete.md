# PiiFilterDelete

- ea: `0x180018064`
- end: `0x1800180f2`
- name: `PiiFilterDelete`
- size: `142`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008948`
- `0x1800174a4`
- `0x1800198b0`

## callees

- `0x180003094`
- `0x180018064`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001808d`
- `KERNEL32!HeapFree` at `0x1800180bb`
- `KERNEL32!HeapFree` at `0x18001808d`
- `KERNEL32!HeapFree` at `0x1800180bb`
- `ntdll!RtlFreeHeap` at `0x1800180e1`
- `ntdll!RtlFreeHeap` at `0x1800180e1`

## pseudocode

```c
BOOLEAN __fastcall PiiFilterDelete(HANDLE *P)
{
  HANDLE v2; // r8
  HANDLE *v3; // rdi
  HANDLE v4; // r8
  BOOLEAN result; // al

  if ( P )
  {
    RtlNameValueArray::Clear((RtlNameValueArray *)P);
    v2 = P[5];
    if ( v2 )
      HeapFree(*P, 0, v2);
    v3 = P + 6;
    *(_OWORD *)P = 0;
    *((_OWORD *)P + 1) = 0;
    *((_OWORD *)P + 2) = 0;
    RtlNameValueArray::Clear((RtlNameValueArray *)(P + 6));
    v4 = P[11];
    if ( v4 )
      HeapFree(*v3, 0, v4);
    *(_OWORD *)v3 = 0;
    *((_OWORD *)P + 4) = 0;
    *((_OWORD *)P + 5) = 0;
    return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  }
  return result;
}

```

## disassembly

```asm
0x180018064  test    rcx, rcx
0x180018067  jz      locret_1800180F1
0x18001806d  mov     [rsp+arg_0], rbx
0x180018072  push    rdi
0x180018073  sub     rsp, 20h
0x180018077  mov     rbx, rcx
0x18001807a  call    ?Clear@RtlNameValueArray@@QEAAXXZ; RtlNameValueArray::Clear(void)
0x18001807f  mov     r8, [rbx+28h]; lpMem
0x180018083  test    r8, r8
0x180018086  jz      short loc_180018093
0x180018088  mov     rcx, [rbx]; hHeap
0x18001808b  xor     edx, edx; dwFlags
0x18001808d  call    cs:__imp_HeapFree
0x180018093  xorps   xmm0, xmm0
0x180018096  lea     rdi, [rbx+30h]
0x18001809a  movups  xmmword ptr [rbx], xmm0
0x18001809d  mov     rcx, rdi; this
0x1800180a0  movups  xmmword ptr [rbx+10h], xmm0
0x1800180a4  movups  xmmword ptr [rbx+20h], xmm0
0x1800180a8  call    ?Clear@RtlNameValueArray@@QEAAXXZ; RtlNameValueArray::Clear(void)
0x1800180ad  mov     r8, [rdi+28h]; lpMem
0x1800180b1  test    r8, r8
0x1800180b4  jz      short loc_1800180C1
0x1800180b6  mov     rcx, [rdi]; hHeap
0x1800180b9  xor     edx, edx; dwFlags
0x1800180bb  call    cs:__imp_HeapFree
0x1800180c1  xorps   xmm0, xmm0
0x1800180c4  mov     r8, rbx; P
0x1800180c7  movups  xmmword ptr [rdi], xmm0
0x1800180ca  xor     edx, edx; Flags
0x1800180cc  movups  xmmword ptr [rdi+10h], xmm0
0x1800180d0  movups  xmmword ptr [rdi+20h], xmm0
0x1800180d4  mov     rcx, gs:60h
0x1800180dd  mov     rcx, [rcx+30h]; HeapHandle
0x1800180e1  call    cs:__imp_RtlFreeHeap
0x1800180e7  mov     rbx, [rsp+28h+arg_0]
0x1800180ec  add     rsp, 20h
0x1800180f0  pop     rdi
0x1800180f1  retn
```
