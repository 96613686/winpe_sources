# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::SetGUID(_GUID const &,_GUID const &)

- ea: `0x18001ce80`
- end: `0x18001cf23`
- name: `?SetGUID@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@0@Z`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000ede4`
- `0x18001ce80`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ce98`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ce98`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cf09`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cf09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001cec3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001cec3`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::SetGUID(__int64 a1, __int64 a2, _OWORD *a3)
{
  __int64 Item; // rsi
  unsigned int v7; // ebx
  _OWORD *v8; // rax

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = CMFAttributesImpl<IMFAttributes,CMFCSLock>::CreateItem(a1, a2);
  if ( Item )
  {
    v8 = CoTaskMemAlloc(0x10u);
    *(_QWORD *)(Item + 8) = v8;
    if ( v8 )
    {
      *(_WORD *)Item = 72;
      v7 = 0;
      *v8 = *a3;
      *(_DWORD *)(a1 + 64) = 1;
      goto LABEL_6;
    }
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 152LL))(a1, a2);
  }
  v7 = -2147024882;
LABEL_6:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return v7;
}

```

## disassembly

```asm
0x18001ce80  push    rbx
0x18001ce82  push    rbp
0x18001ce83  push    rsi
0x18001ce84  push    rdi
0x18001ce85  push    r14
0x18001ce87  sub     rsp, 20h
0x18001ce8b  mov     rdi, rcx
0x18001ce8e  mov     r14, r8
0x18001ce91  add     rcx, 8; lpCriticalSection
0x18001ce95  mov     rbx, rdx
0x18001ce98  call    cs:__imp_EnterCriticalSection
0x18001ce9f  nop     dword ptr [rax+rax+00h]
0x18001cea4  mov     rdx, rbx
0x18001cea7  mov     rcx, rdi
0x18001ceaa  call    ?CreateItem@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CMFCSLock>::CreateItem(_GUID const &)
0x18001ceaf  mov     rsi, rax
0x18001ceb2  test    rax, rax
0x18001ceb5  jnz     short loc_18001CEBE
0x18001ceb7  mov     ebx, 8007000Eh
0x18001cebc  jmp     short loc_18001CF05
0x18001cebe  mov     ecx, 10h; cb
0x18001cec3  call    cs:__imp_CoTaskMemAlloc
0x18001ceca  nop     dword ptr [rax+rax+00h]
0x18001cecf  mov     [rsi+8], rax
0x18001ced3  test    rax, rax
0x18001ced6  jnz     short loc_18001CEEF
0x18001ced8  mov     rax, [rdi]
0x18001cedb  mov     rdx, rbx
0x18001cede  mov     rcx, rdi
0x18001cee1  mov     rax, [rax+98h]
0x18001cee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ceed  jmp     short loc_18001CEB7
0x18001ceef  mov     word ptr [rsi], 48h ; 'H'
0x18001cef4  xor     ebx, ebx
0x18001cef6  movups  xmm0, xmmword ptr [r14]
0x18001cefa  movdqu  xmmword ptr [rax], xmm0
0x18001cefe  mov     dword ptr [rdi+40h], 1
0x18001cf05  lea     rcx, [rdi+8]; lpCriticalSection
0x18001cf09  call    cs:__imp_LeaveCriticalSection
0x18001cf10  nop     dword ptr [rax+rax+00h]
0x18001cf15  mov     eax, ebx
0x18001cf17  add     rsp, 20h
0x18001cf1b  pop     r14
0x18001cf1d  pop     rdi
0x18001cf1e  pop     rsi
0x18001cf1f  pop     rbp
0x18001cf20  pop     rbx
0x18001cf21  retn
```
