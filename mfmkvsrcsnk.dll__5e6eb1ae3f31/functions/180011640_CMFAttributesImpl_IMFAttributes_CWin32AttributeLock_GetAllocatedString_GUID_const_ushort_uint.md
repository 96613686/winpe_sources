# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::GetAllocatedString(_GUID const &,ushort * *,uint *)

- ea: `0x180011640`
- end: `0x1800116f5`
- name: `?GetAllocatedString@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEAPEAGPEAI@Z`
- size: `181`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800036c5`
- `0x180011640`
- `0x180020800`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011660`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011660`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800116e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800116e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800116b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800116b2`

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
0x180011640  push    rbx
0x180011642  push    rbp
0x180011643  push    rsi
0x180011644  push    rdi
0x180011645  push    r14
0x180011647  push    r15
0x180011649  sub     rsp, 28h
0x18001164d  lea     rbp, [rcx+8]
0x180011651  mov     rdi, rcx
0x180011654  mov     rcx, rbp; lpCriticalSection
0x180011657  mov     r14, r9
0x18001165a  mov     r15, r8
0x18001165d  mov     rbx, rdx
0x180011660  call    cs:__imp_EnterCriticalSection
0x180011666  mov     rdx, rbx
0x180011669  mov     rcx, rdi
0x18001166c  call    ?_FindItem@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CMFCSLock>::_FindItem(_GUID const &)
0x180011671  xor     ebx, ebx
0x180011673  mov     rsi, rax
0x180011676  test    rax, rax
0x180011679  jz      short loc_1800116D8
0x18001167b  cmp     word ptr [rax], 1Fh
0x18001167f  jnz     short loc_1800116D1
0x180011681  mov     rcx, [rax+8]
0x180011685  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011689  inc     rax
0x18001168c  cmp     [rcx+rax*2], bx
0x180011690  jnz     short loc_180011689
0x180011692  cmp     rax, 7FFFFFFEh
0x180011698  jb      short loc_1800116A1
0x18001169a  mov     ebx, 8007000Eh
0x18001169f  jmp     short loc_1800116DD
0x1800116a1  test    r14, r14
0x1800116a4  jz      short loc_1800116A9
0x1800116a6  mov     [r14], eax
0x1800116a9  lea     edi, [rax+1]
0x1800116ac  add     rdi, rdi
0x1800116af  mov     rcx, rdi; cb
0x1800116b2  call    cs:__imp_CoTaskMemAlloc
0x1800116b8  mov     [r15], rax
0x1800116bb  test    rax, rax
0x1800116be  jz      short loc_18001169A
0x1800116c0  mov     rdx, [rsi+8]; Src
0x1800116c4  mov     r8, rdi; Size
0x1800116c7  mov     rcx, rax; void *
0x1800116ca  call    memcpy_0
0x1800116cf  jmp     short loc_1800116DD
0x1800116d1  mov     ebx, 0C00D36BDh
0x1800116d6  jmp     short loc_1800116DD
0x1800116d8  mov     ebx, 0C00D36E6h
0x1800116dd  mov     rcx, rbp; lpCriticalSection
0x1800116e0  call    cs:__imp_LeaveCriticalSection
0x1800116e6  mov     eax, ebx
0x1800116e8  add     rsp, 28h
0x1800116ec  pop     r15
0x1800116ee  pop     r14
0x1800116f0  pop     rdi
0x1800116f1  pop     rsi
0x1800116f2  pop     rbp
0x1800116f3  pop     rbx
0x1800116f4  retn
```
