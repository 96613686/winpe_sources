# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::GetAllocatedBlob(_GUID const &,uchar * *,uint *)

- ea: `0x1800bb050`
- end: `0x1800bb0fc`
- name: `?GetAllocatedBlob@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEAPEAEPEAI@Z`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180010010`
- `0x180074a12`
- `0x1800bb050`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bb0e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bb0e2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bb06e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bb06e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bb0a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bb0a4`

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
0x1800bb050  push    rbx
0x1800bb052  push    rbp
0x1800bb053  push    rsi
0x1800bb054  push    rdi
0x1800bb055  push    r14
0x1800bb057  sub     rsp, 20h
0x1800bb05b  lea     rbp, [rcx+8]
0x1800bb05f  mov     rdi, rcx
0x1800bb062  mov     rcx, rbp; lpCriticalSection
0x1800bb065  mov     rsi, r9
0x1800bb068  mov     r14, r8
0x1800bb06b  mov     rbx, rdx
0x1800bb06e  call    cs:__imp_EnterCriticalSection
0x1800bb075  nop     dword ptr [rax+rax+00h]
0x1800bb07a  mov     rdx, rbx
0x1800bb07d  mov     rcx, rdi
0x1800bb080  call    ?_FindItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_FindItem(_GUID const &)
0x1800bb085  mov     rdi, rax
0x1800bb088  test    rax, rax
0x1800bb08b  jz      short loc_1800BB0DA
0x1800bb08d  mov     eax, 1011h
0x1800bb092  cmp     [rdi], ax
0x1800bb095  jnz     short loc_1800BB0D3
0x1800bb097  test    rsi, rsi
0x1800bb09a  jz      short loc_1800BB0A1
0x1800bb09c  mov     ecx, [rdi+8]
0x1800bb09f  mov     [rsi], ecx
0x1800bb0a1  mov     ecx, [rdi+8]; cb
0x1800bb0a4  call    cs:__imp_CoTaskMemAlloc
0x1800bb0ab  nop     dword ptr [rax+rax+00h]
0x1800bb0b0  mov     [r14], rax
0x1800bb0b3  test    rax, rax
0x1800bb0b6  jnz     short loc_1800BB0BF
0x1800bb0b8  mov     ebx, 8007000Eh
0x1800bb0bd  jmp     short loc_1800BB0DF
0x1800bb0bf  mov     r8d, [rdi+8]; Size
0x1800bb0c3  xor     ebx, ebx
0x1800bb0c5  mov     rdx, [rdi+10h]; Src
0x1800bb0c9  mov     rcx, rax; void *
0x1800bb0cc  call    memcpy_0
0x1800bb0d1  jmp     short loc_1800BB0DF
0x1800bb0d3  mov     ebx, 0C00D36BDh
0x1800bb0d8  jmp     short loc_1800BB0DF
0x1800bb0da  mov     ebx, 0C00D36E6h
0x1800bb0df  mov     rcx, rbp; lpCriticalSection
0x1800bb0e2  call    cs:__imp_LeaveCriticalSection
0x1800bb0e9  nop     dword ptr [rax+rax+00h]
0x1800bb0ee  mov     eax, ebx
0x1800bb0f0  add     rsp, 20h
0x1800bb0f4  pop     r14
0x1800bb0f6  pop     rdi
0x1800bb0f7  pop     rsi
0x1800bb0f8  pop     rbp
0x1800bb0f9  pop     rbx
0x1800bb0fa  retn
```
