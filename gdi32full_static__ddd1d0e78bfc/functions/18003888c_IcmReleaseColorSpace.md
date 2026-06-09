# IcmReleaseColorSpace

- ea: `0x18003888c`
- end: `0x180038a2d`
- name: `IcmReleaseColorSpace`
- size: `417`
- prototype: ``
- caller_count: `16`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x18001f090`
- `0x18002e6f0`
- `0x18002f820`
- `0x180035af0`
- `0x180037f34`
- `0x1800385c8`
- `0x1800386a8`
- `0x180038a34`
- `0x1800499a4`
- `0x18006efa0`
- `0x180070288`
- `0x1800772b0`
- `0x18008d480`
- `0x18008e7d8`
- `0x1800954c0`
- `0x1800970b0`

## callees

- `0x18003888c`
- `0x18003acb8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180038a15`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180038a15`
- `ntdll!RtlFreeHeap` at `0x18003890f`
- `ntdll!RtlFreeHeap` at `0x18003893b`
- `ntdll!RtlFreeHeap` at `0x180038995`
- `ntdll!RtlFreeHeap` at `0x1800389f5`
- `ntdll!RtlFreeHeap` at `0x18003890f`
- `ntdll!RtlFreeHeap` at `0x18003893b`
- `ntdll!RtlFreeHeap` at `0x180038995`
- `ntdll!RtlFreeHeap` at `0x1800389f5`
- `ntdll!RtlEnterCriticalSection` at `0x1800388b4`
- `ntdll!RtlEnterCriticalSection` at `0x1800388b4`
- `ntdll!RtlLeaveCriticalSection` at `0x1800389a8`
- `ntdll!RtlLeaveCriticalSection` at `0x1800389a8`

## pseudocode

```c
void __fastcall IcmReleaseColorSpace(__int64 a1, __int64 *a2, int a3)
{
  int v6; // eax
  void *v7; // r8
  void *v8; // r8
  __int64 *v9; // rax
  __int64 **v10; // rdx

  if ( a2 )
  {
    RtlEnterCriticalSection(&semColorSpaceCache);
    v6 = --*((_DWORD *)a2 + 7);
    if ( ((a2[3] & 0x10000) == 0 || !v6) && (!v6 || a3 && a2[2] == a1) )
    {
      if ( a2[4] )
        IcmUnrealizeColorProfile(a2);
      if ( (a2[3] & 0x40000) != 0 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)a2[7]);
        a2[7] = 0;
      }
      v7 = (void *)a2[9];
      if ( v7 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
        a2[9] = 0;
      }
      v8 = (void *)a2[10];
      if ( v8 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
        a2[10] = 0;
      }
      if ( (a2[3] & 0x80000) != 0 )
        DeleteFileW((LPCWSTR)a2 + 78);
      v9 = (__int64 *)*a2;
      if ( *(__int64 **)(*a2 + 8) != a2 || (v10 = (__int64 **)a2[1], *v10 != a2) )
        __fastfail(3u);
      --cCachedColorSpace;
      *v10 = v9;
      v9[1] = (__int64)v10;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, a2);
    }
    RtlLeaveCriticalSection(&semColorSpaceCache);
  }
}

```

## disassembly

```asm
0x18003888c  test    rdx, rdx
0x18003888f  jz      locret_1800389C3
0x180038895  mov     [rsp+arg_0], rbx
0x18003889a  mov     [rsp+arg_8], rsi
0x18003889f  push    rdi
0x1800388a0  sub     rsp, 20h
0x1800388a4  mov     rdi, rcx
0x1800388a7  mov     esi, r8d
0x1800388aa  lea     rcx, semColorSpaceCache; CriticalSection
0x1800388b1  mov     rbx, rdx
0x1800388b4  call    cs:__imp_RtlEnterCriticalSection
0x1800388bb  nop     dword ptr [rax+rax+00h]
0x1800388c0  dec     dword ptr [rbx+1Ch]
0x1800388c3  test    dword ptr [rbx+18h], 10000h
0x1800388ca  mov     eax, [rbx+1Ch]
0x1800388cd  jz      short loc_1800388D7
0x1800388cf  test    eax, eax
0x1800388d1  jnz     loc_1800389A1
0x1800388d7  test    eax, eax
0x1800388d9  jnz     loc_1800389C5
0x1800388df  cmp     qword ptr [rbx+20h], 0
0x1800388e4  jnz     loc_1800389D5
0x1800388ea  test    dword ptr [rbx+18h], 40000h
0x1800388f1  jnz     loc_1800389E2
0x1800388f7  mov     r8, [rbx+48h]; P
0x1800388fb  test    r8, r8
0x1800388fe  jz      short loc_180038923
0x180038900  mov     rcx, gs:60h
0x180038909  xor     edx, edx; Flags
0x18003890b  mov     rcx, [rcx+30h]; HeapHandle
0x18003890f  call    cs:__imp_RtlFreeHeap
0x180038916  nop     dword ptr [rax+rax+00h]
0x18003891b  mov     qword ptr [rbx+48h], 0
0x180038923  mov     r8, [rbx+50h]; P
0x180038927  test    r8, r8
0x18003892a  jz      short loc_18003894F
0x18003892c  mov     rcx, gs:60h
0x180038935  xor     edx, edx; Flags
0x180038937  mov     rcx, [rcx+30h]; HeapHandle
0x18003893b  call    cs:__imp_RtlFreeHeap
0x180038942  nop     dword ptr [rax+rax+00h]
0x180038947  mov     qword ptr [rbx+50h], 0
0x18003894f  test    dword ptr [rbx+18h], 80000h
0x180038956  jnz     loc_180038A0E
0x18003895c  mov     rax, [rbx]
0x18003895f  cmp     [rax+8], rbx
0x180038963  jnz     loc_180038A26
0x180038969  mov     rdx, [rbx+8]
0x18003896d  cmp     [rdx], rbx
0x180038970  jnz     loc_180038A26
0x180038976  dec     cs:?cCachedColorSpace@@3KA; ulong cCachedColorSpace
0x18003897c  mov     r8, rbx; P
0x18003897f  mov     [rdx], rax
0x180038982  mov     [rax+8], rdx
0x180038986  xor     edx, edx; Flags
0x180038988  mov     rcx, gs:60h
0x180038991  mov     rcx, [rcx+30h]; HeapHandle
0x180038995  call    cs:__imp_RtlFreeHeap
0x18003899c  nop     dword ptr [rax+rax+00h]
0x1800389a1  lea     rcx, semColorSpaceCache; CriticalSection
0x1800389a8  call    cs:__imp_RtlLeaveCriticalSection
0x1800389af  nop     dword ptr [rax+rax+00h]
0x1800389b4  mov     rbx, [rsp+28h+arg_0]
0x1800389b9  mov     rsi, [rsp+28h+arg_8]
0x1800389be  add     rsp, 20h
0x1800389c2  pop     rdi
0x1800389c3  retn
0x1800389c5  test    esi, esi
0x1800389c7  jz      short loc_1800389A1
0x1800389c9  cmp     [rbx+10h], rdi
0x1800389cd  jz      loc_1800388DF
0x1800389d3  jmp     short loc_1800389A1
0x1800389d5  mov     rcx, rbx
0x1800389d8  call    IcmUnrealizeColorProfile
0x1800389dd  jmp     loc_1800388EA
0x1800389e2  mov     rcx, gs:60h
0x1800389eb  xor     edx, edx; Flags
0x1800389ed  mov     r8, [rbx+38h]; P
0x1800389f1  mov     rcx, [rcx+30h]; HeapHandle
0x1800389f5  call    cs:__imp_RtlFreeHeap
0x1800389fc  nop     dword ptr [rax+rax+00h]
0x180038a01  mov     qword ptr [rbx+38h], 0
0x180038a09  jmp     loc_1800388F7
0x180038a0e  lea     rcx, [rbx+9Ch]; lpFileName
0x180038a15  call    cs:__imp_DeleteFileW
0x180038a1c  nop     dword ptr [rax+rax+00h]
0x180038a21  jmp     loc_18003895C
0x180038a26  mov     ecx, 3
0x180038a2b  int     29h; Win8: RtlFailFast(ecx)
```
