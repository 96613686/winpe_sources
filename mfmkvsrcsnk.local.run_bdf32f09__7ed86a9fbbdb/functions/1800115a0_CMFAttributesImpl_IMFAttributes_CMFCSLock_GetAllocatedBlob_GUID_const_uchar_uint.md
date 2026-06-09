# CMFAttributesImpl<IMFAttributes,CMFCSLock>::GetAllocatedBlob(_GUID const &,uchar * *,uint *)

- ea: `0x1800115a0`
- end: `0x180011639`
- name: `?GetAllocatedBlob@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@UEAAJAEBU_GUID@@PEAPEAEPEAI@Z`
- size: `153`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800036c5`
- `0x1800115a0`
- `0x180020800`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800115be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800115be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011626`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011626`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800115ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800115ee`

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
0x1800115a0  push    rbx
0x1800115a2  push    rbp
0x1800115a3  push    rsi
0x1800115a4  push    rdi
0x1800115a5  push    r14
0x1800115a7  sub     rsp, 20h
0x1800115ab  lea     rbp, [rcx+8]
0x1800115af  mov     rdi, rcx
0x1800115b2  mov     rcx, rbp; lpCriticalSection
0x1800115b5  mov     rsi, r9
0x1800115b8  mov     r14, r8
0x1800115bb  mov     rbx, rdx
0x1800115be  call    cs:__imp_EnterCriticalSection
0x1800115c4  mov     rdx, rbx
0x1800115c7  mov     rcx, rdi
0x1800115ca  call    ?_FindItem@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CMFCSLock>::_FindItem(_GUID const &)
0x1800115cf  mov     rdi, rax
0x1800115d2  test    rax, rax
0x1800115d5  jz      short loc_18001161E
0x1800115d7  mov     eax, 1011h
0x1800115dc  cmp     [rdi], ax
0x1800115df  jnz     short loc_180011617
0x1800115e1  test    rsi, rsi
0x1800115e4  jz      short loc_1800115EB
0x1800115e6  mov     ecx, [rdi+8]
0x1800115e9  mov     [rsi], ecx
0x1800115eb  mov     ecx, [rdi+8]; cb
0x1800115ee  call    cs:__imp_CoTaskMemAlloc
0x1800115f4  mov     [r14], rax
0x1800115f7  test    rax, rax
0x1800115fa  jnz     short loc_180011603
0x1800115fc  mov     ebx, 8007000Eh
0x180011601  jmp     short loc_180011623
0x180011603  mov     r8d, [rdi+8]; Size
0x180011607  xor     ebx, ebx
0x180011609  mov     rdx, [rdi+10h]; Src
0x18001160d  mov     rcx, rax; void *
0x180011610  call    memcpy_0
0x180011615  jmp     short loc_180011623
0x180011617  mov     ebx, 0C00D36BDh
0x18001161c  jmp     short loc_180011623
0x18001161e  mov     ebx, 0C00D36E6h
0x180011623  mov     rcx, rbp; lpCriticalSection
0x180011626  call    cs:__imp_LeaveCriticalSection
0x18001162c  mov     eax, ebx
0x18001162e  add     rsp, 20h
0x180011632  pop     r14
0x180011634  pop     rdi
0x180011635  pop     rsi
0x180011636  pop     rbp
0x180011637  pop     rbx
0x180011638  retn
```
