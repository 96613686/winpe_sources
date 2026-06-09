# CMFAttributesImpl<IMFAttributes,CMFCSLock>::GetAllocatedBlob(_GUID const &,uchar * *,uint *)

- ea: `0x180011d20`
- end: `0x180011dcc`
- name: `?GetAllocatedBlob@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@UEAAJAEBU_GUID@@PEAPEAEPEAI@Z`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003705`
- `0x180011d20`
- `0x180021678`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011d3e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011d3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011db2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011db2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011d74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011d74`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CMFCSLock>::GetAllocatedBlob(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        _DWORD *a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbp
  __int64 Item; // rdi
  void *v10; // rax
  unsigned int v11; // ebx

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = CMFAttributesImpl<IMFAttributes,CMFCSLock>::_FindItem(a1, a2);
  if ( Item )
  {
    if ( *(_WORD *)Item == 4113 )
    {
      if ( a4 )
        *a4 = *(_DWORD *)(Item + 8);
      v10 = CoTaskMemAlloc(*(unsigned int *)(Item + 8));
      *a3 = v10;
      if ( v10 )
      {
        v11 = 0;
        memcpy_0(v10, *(const void **)(Item + 16), *(unsigned int *)(Item + 8));
      }
      else
      {
        v11 = -2147024882;
      }
    }
    else
    {
      v11 = -1072875843;
    }
  }
  else
  {
    v11 = -1072875802;
  }
  LeaveCriticalSection(v4);
  return v11;
}

```

## disassembly

```asm
0x180011d20  push    rbx
0x180011d22  push    rbp
0x180011d23  push    rsi
0x180011d24  push    rdi
0x180011d25  push    r14
0x180011d27  sub     rsp, 20h
0x180011d2b  lea     rbp, [rcx+8]
0x180011d2f  mov     rdi, rcx
0x180011d32  mov     rcx, rbp; lpCriticalSection
0x180011d35  mov     rsi, r9
0x180011d38  mov     r14, r8
0x180011d3b  mov     rbx, rdx
0x180011d3e  call    cs:__imp_EnterCriticalSection
0x180011d45  nop     dword ptr [rax+rax+00h]
0x180011d4a  mov     rdx, rbx
0x180011d4d  mov     rcx, rdi
0x180011d50  call    ?_FindItem@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CMFCSLock>::_FindItem(_GUID const &)
0x180011d55  mov     rdi, rax
0x180011d58  test    rax, rax
0x180011d5b  jz      short loc_180011DAA
0x180011d5d  mov     eax, 1011h
0x180011d62  cmp     [rdi], ax
0x180011d65  jnz     short loc_180011DA3
0x180011d67  test    rsi, rsi
0x180011d6a  jz      short loc_180011D71
0x180011d6c  mov     ecx, [rdi+8]
0x180011d6f  mov     [rsi], ecx
0x180011d71  mov     ecx, [rdi+8]; cb
0x180011d74  call    cs:__imp_CoTaskMemAlloc
0x180011d7b  nop     dword ptr [rax+rax+00h]
0x180011d80  mov     [r14], rax
0x180011d83  test    rax, rax
0x180011d86  jnz     short loc_180011D8F
0x180011d88  mov     ebx, 8007000Eh
0x180011d8d  jmp     short loc_180011DAF
0x180011d8f  mov     r8d, [rdi+8]; Size
0x180011d93  xor     ebx, ebx
0x180011d95  mov     rdx, [rdi+10h]; Src
0x180011d99  mov     rcx, rax; void *
0x180011d9c  call    memcpy_0
0x180011da1  jmp     short loc_180011DAF
0x180011da3  mov     ebx, 0C00D36BDh
0x180011da8  jmp     short loc_180011DAF
0x180011daa  mov     ebx, 0C00D36E6h
0x180011daf  mov     rcx, rbp; lpCriticalSection
0x180011db2  call    cs:__imp_LeaveCriticalSection
0x180011db9  nop     dword ptr [rax+rax+00h]
0x180011dbe  mov     eax, ebx
0x180011dc0  add     rsp, 20h
0x180011dc4  pop     r14
0x180011dc6  pop     rdi
0x180011dc7  pop     rsi
0x180011dc8  pop     rbp
0x180011dc9  pop     rbx
0x180011dca  retn
```
