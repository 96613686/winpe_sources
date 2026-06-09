# CAsyncRxThread::RemoveEntry(ulong)

- ea: `0x18001a74c`
- end: `0x18001a7d1`
- name: `?RemoveEntry@CAsyncRxThread@@AEAAXK@Z`
- size: `133`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001a63c`
- `0x18001a6e8`

## callees

- `0x180013bbc`
- `0x18001a74c`

## import_xrefs

- `msvcrt!free` at `0x18001a77f`
- `msvcrt!free` at `0x18001a77f`
- `KERNEL32!CloseHandle` at `0x18001a773`
- `KERNEL32!CloseHandle` at `0x18001a773`
- `KERNEL32!LeaveCriticalSection` at `0x18001a7ba`
- `KERNEL32!LeaveCriticalSection` at `0x18001a7ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CAsyncRxThread::RemoveEntry(CCriticalSection *lpCriticalSection, unsigned int a2)
{
  __int64 v2; // rsi
  __int64 v4; // r8

  v2 = a2;
  CCriticalSection::Lock(lpCriticalSection);
  CloseHandle(*((HANDLE *)lpCriticalSection + v2 + 74));
  free(*((void **)lpCriticalSection + v2 + 10));
  if ( (unsigned int)v2 < --*((_DWORD *)lpCriticalSection + 18) )
  {
    do
    {
      v4 = (unsigned int)(v2 + 1);
      *((_QWORD *)lpCriticalSection + (unsigned int)v2 + 74) = *((_QWORD *)lpCriticalSection + v4 + 74);
      *((_QWORD *)lpCriticalSection + (unsigned int)v2 + 10) = *((_QWORD *)lpCriticalSection + v4 + 10);
      LODWORD(v2) = v2 + 1;
    }
    while ( (unsigned int)v4 < *((_DWORD *)lpCriticalSection + 18) );
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
}

```

## disassembly

```asm
0x18001a74c  mov     [rsp+arg_8], rbx
0x18001a751  mov     [rsp+arg_10], rsi
0x18001a756  push    rdi
0x18001a757  sub     rsp, 20h
0x18001a75b  mov     esi, edx
0x18001a75d  mov     rdi, rcx
0x18001a760  mov     [rsp+28h+arg_0], rcx
0x18001a765  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18001a76a  nop
0x18001a76b  mov     rcx, [rdi+rsi*8+250h]; hObject
0x18001a773  call    cs:__imp_CloseHandle
0x18001a779  nop
0x18001a77a  mov     rcx, [rdi+rsi*8+50h]; Block
0x18001a77f  call    cs:__imp_free
0x18001a785  nop
0x18001a786  dec     dword ptr [rdi+48h]
0x18001a789  cmp     esi, [rdi+48h]
0x18001a78c  jnb     short loc_18001A7B7
0x18001a78e  lea     r8d, [rsi+1]
0x18001a792  mov     edx, esi
0x18001a794  mov     rax, [rdi+r8*8+250h]
0x18001a79c  mov     [rdi+rdx*8+250h], rax
0x18001a7a4  mov     rax, [rdi+r8*8+50h]
0x18001a7a9  mov     [rdi+rdx*8+50h], rax
0x18001a7ae  mov     esi, r8d
0x18001a7b1  cmp     r8d, [rdi+48h]
0x18001a7b5  jb      short loc_18001A78E
0x18001a7b7  mov     rcx, rdi; lpCriticalSection
0x18001a7ba  call    cs:__imp_LeaveCriticalSection
0x18001a7c0  nop
0x18001a7c1  mov     rbx, [rsp+28h+arg_8]
0x18001a7c6  mov     rsi, [rsp+28h+arg_10]
0x18001a7cb  add     rsp, 20h
0x18001a7cf  pop     rdi
0x18001a7d0  retn
```
