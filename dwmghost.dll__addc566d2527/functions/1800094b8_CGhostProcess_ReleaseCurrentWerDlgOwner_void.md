# CGhostProcess::ReleaseCurrentWerDlgOwner(void)

- ea: `0x1800094b8`
- end: `0x180009512`
- name: `?ReleaseCurrentWerDlgOwner@CGhostProcess@@AEAAHXZ`
- size: `90`
- prototype: `__int64 __fastcall(CGhostProcess *__hidden this)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x180008d54`
- `0x1800092fc`
- `0x1800093f8`
- `0x180009468`
- `0x180009518`
- `0x180009580`

## callees

- `0x180004dc4`
- `0x1800094b8`
- `0x180009678`
- `0x180009f60`
- `0x180009f70`

## pseudocode

```c
__int64 __fastcall CGhostProcess::ReleaseCurrentWerDlgOwner(CGhostProcess *this)
{
  unsigned int v2; // edi

  v2 = 0;
  CLock::Acquire((LPCRITICAL_SECTION)((char *)this + 16));
  if ( *((_QWORD *)this + 13) )
  {
    CGhostProcess::SetWerDlgOwnerHwnd(this, 0);
    CCountedObject::Release(*((CCountedObject **)this + 13));
    *((_QWORD *)this + 13) = 0;
    v2 = 1;
  }
  CLock::Release((LPCRITICAL_SECTION)((char *)this + 16));
  return v2;
}

```

## disassembly

```asm
0x1800094b8  mov     [rsp+arg_0], rbx
0x1800094bd  mov     [rsp+arg_8], rsi
0x1800094c2  push    rdi
0x1800094c3  sub     rsp, 20h
0x1800094c7  mov     rbx, rcx
0x1800094ca  xor     edi, edi
0x1800094cc  add     rcx, 10h; lpCriticalSection
0x1800094d0  call    ?Acquire@CLock@@QEAAXXZ; CLock::Acquire(void)
0x1800094d5  cmp     [rbx+68h], rdi
0x1800094d9  jz      short loc_1800094F7
0x1800094db  xor     edx, edx; HWND
0x1800094dd  mov     rcx, rbx; this
0x1800094e0  call    ?SetWerDlgOwnerHwnd@CGhostProcess@@AEAAJPEAUHWND__@@@Z; CGhostProcess::SetWerDlgOwnerHwnd(HWND__ *)
0x1800094e5  mov     rcx, [rbx+68h]; this
0x1800094e9  call    ?Release@CCountedObject@@QEAAXXZ; CCountedObject::Release(void)
0x1800094ee  mov     [rbx+68h], rdi
0x1800094f2  mov     edi, 1
0x1800094f7  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800094fb  call    ?Release@CLock@@QEAAXXZ; CLock::Release(void)
0x180009500  mov     rbx, [rsp+28h+arg_0]
0x180009505  mov     eax, edi
0x180009507  mov     rsi, [rsp+28h+arg_8]
0x18000950c  add     rsp, 20h
0x180009510  pop     rdi
0x180009511  retn
```
