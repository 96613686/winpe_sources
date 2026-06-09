# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::GetAllocatedString(_GUID const &,ushort * *,uint *)

- ea: `0x18002b6b0`
- end: `0x18002b765`
- name: `?GetAllocatedString@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEAPEAGPEAI@Z`
- size: `181`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180016b0c`
- `0x18002b6b0`
- `0x18002f58c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b750`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b750`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b6d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b6d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b722`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b722`

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
  Item = CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_FindItem(a1, a2);
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
0x18002b6b0  push    rbx
0x18002b6b2  push    rbp
0x18002b6b3  push    rsi
0x18002b6b4  push    rdi
0x18002b6b5  push    r14
0x18002b6b7  push    r15
0x18002b6b9  sub     rsp, 28h
0x18002b6bd  lea     rbp, [rcx+8]
0x18002b6c1  mov     rdi, rcx
0x18002b6c4  mov     rcx, rbp; lpCriticalSection
0x18002b6c7  mov     r14, r9
0x18002b6ca  mov     r15, r8
0x18002b6cd  mov     rbx, rdx
0x18002b6d0  call    cs:__imp_EnterCriticalSection
0x18002b6d6  mov     rdx, rbx
0x18002b6d9  mov     rcx, rdi
0x18002b6dc  call    ?_FindItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_FindItem(_GUID const &)
0x18002b6e1  xor     ebx, ebx
0x18002b6e3  mov     rsi, rax
0x18002b6e6  test    rax, rax
0x18002b6e9  jz      short loc_18002B748
0x18002b6eb  cmp     word ptr [rax], 1Fh
0x18002b6ef  jnz     short loc_18002B741
0x18002b6f1  mov     rcx, [rax+8]
0x18002b6f5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b6f9  inc     rax
0x18002b6fc  cmp     [rcx+rax*2], bx
0x18002b700  jnz     short loc_18002B6F9
0x18002b702  cmp     rax, 7FFFFFFEh
0x18002b708  jb      short loc_18002B711
0x18002b70a  mov     ebx, 8007000Eh
0x18002b70f  jmp     short loc_18002B74D
0x18002b711  test    r14, r14
0x18002b714  jz      short loc_18002B719
0x18002b716  mov     [r14], eax
0x18002b719  lea     edi, [rax+1]
0x18002b71c  add     rdi, rdi
0x18002b71f  mov     rcx, rdi; cb
0x18002b722  call    cs:__imp_CoTaskMemAlloc
0x18002b728  mov     [r15], rax
0x18002b72b  test    rax, rax
0x18002b72e  jz      short loc_18002B70A
0x18002b730  mov     rdx, [rsi+8]; Src
0x18002b734  mov     r8, rdi; Size
0x18002b737  mov     rcx, rax; void *
0x18002b73a  call    memcpy_0
0x18002b73f  jmp     short loc_18002B74D
0x18002b741  mov     ebx, 0C00D36BDh
0x18002b746  jmp     short loc_18002B74D
0x18002b748  mov     ebx, 0C00D36E6h
0x18002b74d  mov     rcx, rbp; lpCriticalSection
0x18002b750  call    cs:__imp_LeaveCriticalSection
0x18002b756  mov     eax, ebx
0x18002b758  add     rsp, 28h
0x18002b75c  pop     r15
0x18002b75e  pop     r14
0x18002b760  pop     rdi
0x18002b761  pop     rsi
0x18002b762  pop     rbp
0x18002b763  pop     rbx
0x18002b764  retn
```
