# Dhcpv6FreeLeaseInfoArray

- ea: `0x180001eb0`
- end: `0x180001fe5`
- name: `Dhcpv6FreeLeaseInfoArray`
- size: `309`
- prototype: `unsigned int __fastcall(__int64, LPVOID *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800016f0`

## callees

- `0x180001eb0`
- `0x1800082b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001f91`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001f91`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001f29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001f3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001f4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001fbf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001fda`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001f29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001f3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001f4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001fbf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001fda`

## pseudocode

```c
unsigned int __fastcall Dhcpv6FreeLeaseInfoArray(__int64 a1, LPVOID *a2)
{
  unsigned int v3; // ebp
  unsigned int result; // eax
  unsigned int i; // esi
  char *v6; // rbx
  __int64 v7; // rdi
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  __int64 j; // r15

  v3 = a1;
  if ( (xmmword_18000F160 & 0x10) != 0 )
    result = WPP_SF_(a1, 61, WPP_cb48999f8e5838f952918348529d50de_Traceguids);
  if ( a2 && *a2 && v3 )
  {
    for ( i = 0; i < v3; ++i )
    {
      v6 = (char *)*a2;
      result = i;
      v7 = 304LL * i;
      v8 = *(void **)((char *)*a2 + v7 + 200);
      if ( v8 )
        result = (unsigned int)LocalFree(v8);
      v9 = *(void **)&v6[v7 + 216];
      if ( v9 )
        result = (unsigned int)LocalFree(v9);
      v10 = *(void **)&v6[v7 + 288];
      if ( v10 )
        result = (unsigned int)LocalFree(v10);
      if ( *(_QWORD *)&v6[v7 + 272] )
      {
        for ( j = 0; (unsigned int)j < *(_DWORD *)&v6[v7 + 264]; j = (unsigned int)(j + 1) )
          LocalFree(*(HLOCAL *)(*(_QWORD *)&v6[v7 + 272] + 8 * j));
        result = (unsigned int)LocalFree(*(HLOCAL *)&v6[v7 + 272]);
      }
    }
    if ( *a2 )
    {
      result = HeapFree(NtCurrentPeb()->ProcessHeap, 0, *a2);
      *a2 = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180001eb0  push    rbp
0x180001eb2  push    r14
0x180001eb4  sub     rsp, 28h
0x180001eb8  mov     r14, rdx
0x180001ebb  mov     ebp, ecx
0x180001ebd  test    byte ptr cs:xmmword_18000F160, 10h
0x180001ec4  jz      short loc_180001ED7
0x180001ec6  mov     edx, 3Dh ; '='
0x180001ecb  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180001ed2  call    WPP_SF_
0x180001ed7  test    r14, r14
0x180001eda  jz      loc_180001F9E
0x180001ee0  cmp     qword ptr [r14], 0
0x180001ee4  jz      loc_180001F9E
0x180001eea  test    ebp, ebp
0x180001eec  jz      loc_180001F9E
0x180001ef2  mov     [rsp+38h+arg_8], rsi
0x180001ef7  xor     esi, esi
0x180001ef9  test    ebp, ebp
0x180001efb  jz      short loc_180001F75
0x180001efd  mov     [rsp+38h+arg_0], rbx
0x180001f02  mov     [rsp+38h+arg_10], rdi
0x180001f07  mov     [rsp+38h+var_18], r15
0x180001f0c  nop     dword ptr [rax+00h]
0x180001f10  mov     rbx, [r14]
0x180001f13  mov     eax, esi
0x180001f15  imul    rdi, rax, 130h
0x180001f1c  mov     rcx, [rdi+rbx+0C8h]; hMem
0x180001f24  test    rcx, rcx
0x180001f27  jz      short loc_180001F2F
0x180001f29  call    cs:__imp_LocalFree
0x180001f2f  mov     rcx, [rdi+rbx+0D8h]; hMem
0x180001f37  test    rcx, rcx
0x180001f3a  jz      short loc_180001F42
0x180001f3c  call    cs:__imp_LocalFree
0x180001f42  mov     rcx, [rdi+rbx+120h]; hMem
0x180001f4a  test    rcx, rcx
0x180001f4d  jz      short loc_180001F55
0x180001f4f  call    cs:__imp_LocalFree
0x180001f55  cmp     qword ptr [rdi+rbx+110h], 0
0x180001f5e  jnz     short loc_180001FA6
0x180001f60  inc     esi
0x180001f62  cmp     esi, ebp
0x180001f64  jb      short loc_180001F10
0x180001f66  mov     r15, [rsp+38h+var_18]
0x180001f6b  mov     rdi, [rsp+38h+arg_10]
0x180001f70  mov     rbx, [rsp+38h+arg_0]
0x180001f75  mov     r8, [r14]; lpMem
0x180001f78  mov     rsi, [rsp+38h+arg_8]
0x180001f7d  test    r8, r8
0x180001f80  jz      short loc_180001F9E
0x180001f82  mov     rcx, gs:60h
0x180001f8b  xor     edx, edx; dwFlags
0x180001f8d  mov     rcx, [rcx+30h]; hHeap
0x180001f91  call    cs:__imp_HeapFree
0x180001f97  mov     qword ptr [r14], 0
0x180001f9e  add     rsp, 28h
0x180001fa2  pop     r14
0x180001fa4  pop     rbp
0x180001fa5  retn
0x180001fa6  xor     r15d, r15d
0x180001fa9  cmp     [rdi+rbx+108h], r15d
0x180001fb1  jbe     short loc_180001FD2
0x180001fb3  mov     rcx, [rdi+rbx+110h]
0x180001fbb  mov     rcx, [rcx+r15*8]; hMem
0x180001fbf  call    cs:__imp_LocalFree
0x180001fc5  inc     r15d
0x180001fc8  cmp     r15d, [rdi+rbx+108h]
0x180001fd0  jb      short loc_180001FB3
0x180001fd2  mov     rcx, [rdi+rbx+110h]; hMem
0x180001fda  call    cs:__imp_LocalFree
0x180001fe0  jmp     loc_180001F60
```
