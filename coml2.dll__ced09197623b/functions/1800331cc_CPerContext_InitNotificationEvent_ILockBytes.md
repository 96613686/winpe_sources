# CPerContext::InitNotificationEvent(ILockBytes *)

- ea: `0x1800331cc`
- end: `0x18003326b`
- name: `?InitNotificationEvent@CPerContext@@QEAAJPEAUILockBytes@@@Z`
- size: `159`
- prototype: `__int64 __fastcall(CPerContext *__hidden this, struct ILockBytes *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18001c99c`
- `0x18003313c`
- `0x18005ac70`

## callees

- `0x180026bc4`
- `0x1800331cc`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003325c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003325c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180033245`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180033245`

## pseudocode

```c
__int64 __fastcall CPerContext::InitNotificationEvent(CPerContext *this, struct ILockBytes *a2)
{
  struct ILockBytesVtbl *lpVtbl; // rax
  __int64 result; // rax
  HANDLE EventW; // rax
  DWORD LastError; // eax
  __int64 v8; // [rsp+30h] [rbp+8h] BYREF

  if ( *((_QWORD *)this + 10) != -1 || !a2 )
    return 0;
  lpVtbl = a2->lpVtbl;
  v8 = 0;
  result = ((__int64 (__fastcall *)(struct ILockBytes *, GUID *, __int64 *))lpVtbl->QueryInterface)(
             a2,
             &IID_IDfReserved1,
             &v8);
  if ( (int)result < 0 )
    return result;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  if ( a2[7].lpVtbl )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 10) = EventW;
    if ( !EventW )
    {
      *((_QWORD *)this + 10) = -1;
      LastError = GetLastError();
      return Win32ErrorToScode(LastError);
    }
    return 0;
  }
  return 2147500034LL;
}

```

## disassembly

```asm
0x1800331cc  mov     [rsp+arg_8], rbx
0x1800331d1  push    rdi
0x1800331d2  sub     rsp, 20h
0x1800331d6  cmp     qword ptr [rcx+50h], 0FFFFFFFFFFFFFFFFh
0x1800331db  mov     rbx, rdx
0x1800331de  mov     rdi, rcx
0x1800331e1  jnz     short loc_180033237
0x1800331e3  test    rdx, rdx
0x1800331e6  jz      short loc_180033237
0x1800331e8  mov     rax, [rdx]
0x1800331eb  lea     r8, [rsp+28h+arg_0]
0x1800331f0  lea     rdx, IID_IDfReserved1
0x1800331f7  mov     [rsp+28h+arg_0], 0
0x180033200  mov     rcx, rbx
0x180033203  mov     rax, [rax]
0x180033206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003320b  test    eax, eax
0x18003320d  js      short loc_18003322C
0x18003320f  mov     rcx, [rsp+28h+arg_0]
0x180033214  mov     rax, [rcx]
0x180033217  mov     rax, [rax+10h]
0x18003321b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033220  cmp     qword ptr [rbx+38h], 0
0x180033225  jnz     short loc_18003323B
0x180033227  mov     eax, 80004002h
0x18003322c  mov     rbx, [rsp+28h+arg_8]
0x180033231  add     rsp, 20h
0x180033235  pop     rdi
0x180033236  retn
0x180033237  xor     eax, eax
0x180033239  jmp     short loc_18003322C
0x18003323b  xor     r9d, r9d; lpName
0x18003323e  xor     r8d, r8d; bInitialState
0x180033241  xor     edx, edx; bManualReset
0x180033243  xor     ecx, ecx; lpEventAttributes
0x180033245  call    cs:__imp_CreateEventW
0x18003324b  mov     [rdi+50h], rax
0x18003324f  test    rax, rax
0x180033252  jnz     short loc_180033237
0x180033254  mov     qword ptr [rdi+50h], 0FFFFFFFFFFFFFFFFh
0x18003325c  call    cs:__imp_GetLastError
0x180033262  mov     ecx, eax; unsigned int
0x180033264  call    ?Win32ErrorToScode@@YAJK@Z; Win32ErrorToScode(ulong)
0x180033269  jmp     short loc_18003322C
```
