# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::GetAllocatedString(_GUID const &,ushort * *,uint *)

- ea: `0x180011de0`
- end: `0x180011ea8`
- name: `?GetAllocatedString@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEAPEAGPEAI@Z`
- size: `200`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003705`
- `0x180011de0`
- `0x180021678`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011e00`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011e00`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011e8c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011e8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011e58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011e58`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::GetAllocatedString(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        _DWORD *a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbp
  __int64 Item; // rax
  unsigned int v10; // ebx
  __int64 v11; // rsi
  __int64 v12; // rcx
  unsigned __int64 v13; // rax
  SIZE_T v14; // rdi
  void *v15; // rax

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = CMFAttributesImpl<IMFAttributes,CMFCSLock>::_FindItem(a1, a2);
  v10 = 0;
  v11 = Item;
  if ( Item )
  {
    if ( *(_WORD *)Item == 31 )
    {
      v12 = *(_QWORD *)(Item + 8);
      v13 = -1;
      do
        ++v13;
      while ( *(_WORD *)(v12 + 2 * v13) );
      if ( v13 >= 0x7FFFFFFE )
        goto LABEL_6;
      if ( a4 )
        *a4 = v13;
      v14 = 2LL * (unsigned int)(v13 + 1);
      v15 = CoTaskMemAlloc(v14);
      *a3 = v15;
      if ( v15 )
        memcpy_0(v15, *(const void **)(v11 + 8), v14);
      else
LABEL_6:
        v10 = -2147024882;
    }
    else
    {
      v10 = -1072875843;
    }
  }
  else
  {
    v10 = -1072875802;
  }
  LeaveCriticalSection(v4);
  return v10;
}

```

## disassembly

```asm
0x180011de0  push    rbx
0x180011de2  push    rbp
0x180011de3  push    rsi
0x180011de4  push    rdi
0x180011de5  push    r14
0x180011de7  push    r15
0x180011de9  sub     rsp, 28h
0x180011ded  lea     rbp, [rcx+8]
0x180011df1  mov     rdi, rcx
0x180011df4  mov     rcx, rbp; lpCriticalSection
0x180011df7  mov     r14, r9
0x180011dfa  mov     r15, r8
0x180011dfd  mov     rbx, rdx
0x180011e00  call    cs:__imp_EnterCriticalSection
0x180011e07  nop     dword ptr [rax+rax+00h]
0x180011e0c  mov     rdx, rbx
0x180011e0f  mov     rcx, rdi
0x180011e12  call    ?_FindItem@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CMFCSLock>::_FindItem(_GUID const &)
0x180011e17  xor     ebx, ebx
0x180011e19  mov     rsi, rax
0x180011e1c  test    rax, rax
0x180011e1f  jz      short loc_180011E84
0x180011e21  cmp     word ptr [rax], 1Fh
0x180011e25  jnz     short loc_180011E7D
0x180011e27  mov     rcx, [rax+8]
0x180011e2b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011e2f  inc     rax
0x180011e32  cmp     [rcx+rax*2], bx
0x180011e36  jnz     short loc_180011E2F
0x180011e38  cmp     rax, 7FFFFFFEh
0x180011e3e  jb      short loc_180011E47
0x180011e40  mov     ebx, 8007000Eh
0x180011e45  jmp     short loc_180011E89
0x180011e47  test    r14, r14
0x180011e4a  jz      short loc_180011E4F
0x180011e4c  mov     [r14], eax
0x180011e4f  lea     edi, [rax+1]
0x180011e52  add     rdi, rdi
0x180011e55  mov     rcx, rdi; cb
0x180011e58  call    cs:__imp_CoTaskMemAlloc
0x180011e5f  nop     dword ptr [rax+rax+00h]
0x180011e64  mov     [r15], rax
0x180011e67  test    rax, rax
0x180011e6a  jz      short loc_180011E40
0x180011e6c  mov     rdx, [rsi+8]; Src
0x180011e70  mov     r8, rdi; Size
0x180011e73  mov     rcx, rax; void *
0x180011e76  call    memcpy_0
0x180011e7b  jmp     short loc_180011E89
0x180011e7d  mov     ebx, 0C00D36BDh
0x180011e82  jmp     short loc_180011E89
0x180011e84  mov     ebx, 0C00D36E6h
0x180011e89  mov     rcx, rbp; lpCriticalSection
0x180011e8c  call    cs:__imp_LeaveCriticalSection
0x180011e93  nop     dword ptr [rax+rax+00h]
0x180011e98  mov     eax, ebx
0x180011e9a  add     rsp, 28h
0x180011e9e  pop     r15
0x180011ea0  pop     r14
0x180011ea2  pop     rdi
0x180011ea3  pop     rsi
0x180011ea4  pop     rbp
0x180011ea5  pop     rbx
0x180011ea6  retn
```
