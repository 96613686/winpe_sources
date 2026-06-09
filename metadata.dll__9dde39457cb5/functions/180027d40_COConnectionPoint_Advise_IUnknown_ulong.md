# COConnectionPoint::Advise(IUnknown *,ulong *)

- ea: `0x180027d40`
- end: `0x180027e14`
- name: `?Advise@COConnectionPoint@@UEAAJPEAUIUnknown@@PEAK@Z`
- size: `212`
- prototype: `__int64 __fastcall(COConnectionPoint *__hidden this, struct IUnknown *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180005730`
- `0x180027d40`
- `0x180031010`

## import_xrefs

- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180027df5`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180027df5`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180027d81`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180027d81`

## pseudocode

```c
__int64 __fastcall COConnectionPoint::Advise(COConnectionPoint *this, struct IUnknown *a2, unsigned int *a3)
{
  int Slot; // ebx
  __int64 v7; // r8
  unsigned int v9; // [rsp+38h] [rbp+10h] BYREF
  __int64 v10; // [rsp+48h] [rbp+20h] BYREF

  v9 = 0;
  v10 = 0;
  if ( a2 && a3 )
  {
    CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)&g_LockSinkResource);
    *a3 = 0;
    if ( ((__int64 (__fastcall *)(struct IUnknown *, char *, __int64 *))a2->lpVtbl->QueryInterface)(
           a2,
           (char *)this + 24,
           &v10) < 0 )
    {
      Slot = -2147220990;
    }
    else
    {
      Slot = COConnectionPoint::GetSlot(this, &v9);
      if ( Slot >= 0 )
      {
        v7 = 2LL * v9;
        *(_QWORD *)(*((_QWORD *)this + 7) + 8 * v7) = v10;
        *(_DWORD *)(*((_QWORD *)this + 7) + 8 * v7 + 8) = *((_DWORD *)this + 10);
        *a3 = (*((_DWORD *)this + 10))++;
        ++*((_DWORD *)this + 11);
      }
    }
    CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)&g_LockSinkResource);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)Slot;
}

```

## disassembly

```asm
0x180027d40  mov     rax, rsp
0x180027d43  mov     [rax+8], rbx
0x180027d47  mov     [rax+18h], rsi
0x180027d4b  push    rdi
0x180027d4c  sub     rsp, 20h
0x180027d50  mov     dword ptr [rax+10h], 0
0x180027d57  mov     rsi, r8
0x180027d5a  mov     qword ptr [rax+20h], 0
0x180027d62  mov     rbx, rdx
0x180027d65  mov     rdi, rcx
0x180027d68  test    rdx, rdx
0x180027d6b  jz      loc_180027DFD
0x180027d71  test    r8, r8
0x180027d74  jz      loc_180027DFD
0x180027d7a  lea     rcx, ?g_LockSinkResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockSinkResource
0x180027d81  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180027d87  mov     dword ptr [rsi], 0
0x180027d8d  lea     rdx, [rdi+18h]
0x180027d91  mov     rax, [rbx]
0x180027d94  lea     r8, [rsp+28h+arg_18]
0x180027d99  mov     rcx, rbx
0x180027d9c  mov     rax, [rax]
0x180027d9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027da4  test    eax, eax
0x180027da6  js      short loc_180027DE9
0x180027da8  lea     rdx, [rsp+28h+arg_8]; unsigned int *
0x180027dad  mov     rcx, rdi; this
0x180027db0  call    ?GetSlot@COConnectionPoint@@AEAAJPEAI@Z; COConnectionPoint::GetSlot(uint *)
0x180027db5  mov     ebx, eax
0x180027db7  test    eax, eax
0x180027db9  js      short loc_180027DEE
0x180027dbb  mov     rdx, [rdi+38h]
0x180027dbf  mov     rcx, [rsp+28h+arg_18]
0x180027dc4  mov     r8d, [rsp+28h+arg_8]
0x180027dc9  add     r8, r8
0x180027dcc  mov     [rdx+r8*8], rcx
0x180027dd0  mov     ecx, [rdi+28h]
0x180027dd3  mov     rdx, [rdi+38h]
0x180027dd7  mov     [rdx+r8*8+8], ecx
0x180027ddc  mov     eax, [rdi+28h]
0x180027ddf  mov     [rsi], eax
0x180027de1  inc     dword ptr [rdi+28h]
0x180027de4  inc     dword ptr [rdi+2Ch]
0x180027de7  jmp     short loc_180027DEE
0x180027de9  mov     ebx, 80040202h
0x180027dee  lea     rcx, ?g_LockSinkResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockSinkResource
0x180027df5  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180027dfb  jmp     short loc_180027E02
0x180027dfd  mov     ebx, 80070057h
0x180027e02  mov     rsi, [rsp+28h+arg_10]
0x180027e07  mov     eax, ebx
0x180027e09  mov     rbx, [rsp+28h+arg_0]
0x180027e0e  add     rsp, 20h
0x180027e12  pop     rdi
0x180027e13  retn
```
