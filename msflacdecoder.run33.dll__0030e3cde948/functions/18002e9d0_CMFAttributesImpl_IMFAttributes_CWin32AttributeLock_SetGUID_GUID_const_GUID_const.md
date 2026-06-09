# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::SetGUID(_GUID const &,_GUID const &)

- ea: `0x18002e9d0`
- end: `0x18002ea60`
- name: `?SetGUID@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@0@Z`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18002b05c`
- `0x18002e9d0`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ea4d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ea4d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e9e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e9e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ea0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ea0d`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::SetGUID(__int64 a1, __int64 a2, _OWORD *a3)
{
  __int64 Item; // rsi
  unsigned int v7; // ebx
  _OWORD *v8; // rax

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::CreateItem(a1, a2);
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
0x18002e9d0  push    rbx
0x18002e9d2  push    rbp
0x18002e9d3  push    rsi
0x18002e9d4  push    rdi
0x18002e9d5  push    r14
0x18002e9d7  sub     rsp, 20h
0x18002e9db  mov     rdi, rcx
0x18002e9de  mov     r14, r8
0x18002e9e1  add     rcx, 8; lpCriticalSection
0x18002e9e5  mov     rbx, rdx
0x18002e9e8  call    cs:__imp_EnterCriticalSection
0x18002e9ee  mov     rdx, rbx
0x18002e9f1  mov     rcx, rdi
0x18002e9f4  call    ?CreateItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::CreateItem(_GUID const &)
0x18002e9f9  mov     rsi, rax
0x18002e9fc  test    rax, rax
0x18002e9ff  jnz     short loc_18002EA08
0x18002ea01  mov     ebx, 8007000Eh
0x18002ea06  jmp     short loc_18002EA49
0x18002ea08  mov     ecx, 10h; cb
0x18002ea0d  call    cs:__imp_CoTaskMemAlloc
0x18002ea13  mov     [rsi+8], rax
0x18002ea17  test    rax, rax
0x18002ea1a  jnz     short loc_18002EA33
0x18002ea1c  mov     rax, [rdi]
0x18002ea1f  mov     rdx, rbx
0x18002ea22  mov     rcx, rdi
0x18002ea25  mov     rax, [rax+98h]
0x18002ea2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea31  jmp     short loc_18002EA01
0x18002ea33  mov     word ptr [rsi], 48h ; 'H'
0x18002ea38  xor     ebx, ebx
0x18002ea3a  movups  xmm0, xmmword ptr [r14]
0x18002ea3e  movdqu  xmmword ptr [rax], xmm0
0x18002ea42  mov     dword ptr [rdi+40h], 1
0x18002ea49  lea     rcx, [rdi+8]; lpCriticalSection
0x18002ea4d  call    cs:__imp_LeaveCriticalSection
0x18002ea53  mov     eax, ebx
0x18002ea55  add     rsp, 20h
0x18002ea59  pop     r14
0x18002ea5b  pop     rdi
0x18002ea5c  pop     rsi
0x18002ea5d  pop     rbp
0x18002ea5e  pop     rbx
0x18002ea5f  retn
```
