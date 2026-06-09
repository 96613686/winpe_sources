# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::GetAllocatedBlob(_GUID const &,uchar * *,uint *)

- ea: `0x18002b610`
- end: `0x18002b6a9`
- name: `?GetAllocatedBlob@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEAPEAEPEAI@Z`
- size: `153`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180016b0c`
- `0x18002b610`
- `0x18002f58c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b696`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b696`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b62e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b62e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b65e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b65e`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::GetAllocatedBlob(
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
  Item = CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_FindItem(a1, a2);
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
0x18002b610  push    rbx
0x18002b612  push    rbp
0x18002b613  push    rsi
0x18002b614  push    rdi
0x18002b615  push    r14
0x18002b617  sub     rsp, 20h
0x18002b61b  lea     rbp, [rcx+8]
0x18002b61f  mov     rdi, rcx
0x18002b622  mov     rcx, rbp; lpCriticalSection
0x18002b625  mov     rsi, r9
0x18002b628  mov     r14, r8
0x18002b62b  mov     rbx, rdx
0x18002b62e  call    cs:__imp_EnterCriticalSection
0x18002b634  mov     rdx, rbx
0x18002b637  mov     rcx, rdi
0x18002b63a  call    ?_FindItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_FindItem(_GUID const &)
0x18002b63f  mov     rdi, rax
0x18002b642  test    rax, rax
0x18002b645  jz      short loc_18002B68E
0x18002b647  mov     eax, 1011h
0x18002b64c  cmp     [rdi], ax
0x18002b64f  jnz     short loc_18002B687
0x18002b651  test    rsi, rsi
0x18002b654  jz      short loc_18002B65B
0x18002b656  mov     ecx, [rdi+8]
0x18002b659  mov     [rsi], ecx
0x18002b65b  mov     ecx, [rdi+8]; cb
0x18002b65e  call    cs:__imp_CoTaskMemAlloc
0x18002b664  mov     [r14], rax
0x18002b667  test    rax, rax
0x18002b66a  jnz     short loc_18002B673
0x18002b66c  mov     ebx, 8007000Eh
0x18002b671  jmp     short loc_18002B693
0x18002b673  mov     r8d, [rdi+8]; Size
0x18002b677  xor     ebx, ebx
0x18002b679  mov     rdx, [rdi+10h]; Src
0x18002b67d  mov     rcx, rax; void *
0x18002b680  call    memcpy_0
0x18002b685  jmp     short loc_18002B693
0x18002b687  mov     ebx, 0C00D36BDh
0x18002b68c  jmp     short loc_18002B693
0x18002b68e  mov     ebx, 0C00D36E6h
0x18002b693  mov     rcx, rbp; lpCriticalSection
0x18002b696  call    cs:__imp_LeaveCriticalSection
0x18002b69c  mov     eax, ebx
0x18002b69e  add     rsp, 20h
0x18002b6a2  pop     r14
0x18002b6a4  pop     rdi
0x18002b6a5  pop     rsi
0x18002b6a6  pop     rbp
0x18002b6a7  pop     rbx
0x18002b6a8  retn
```
