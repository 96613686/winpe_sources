# ATL::CAtlModule::Term(void)

- ea: `0x18000bcdc`
- end: `0x18000bd8f`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `179`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180008b10`
- `0x18000c5dc`
- `0x18001b310`

## callees

- `0x18000bcdc`
- `0x18001c010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000bd3f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000bd3f`
- `KERNEL32!RaiseException` at `0x18000bd1c`
- `KERNEL32!RaiseException` at `0x18000bd1c`
- `KERNEL32!DeleteCriticalSection` at `0x18000bd76`
- `KERNEL32!DeleteCriticalSection` at `0x18000bd76`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ATL::CAtlModule::Term(ATL::CAtlModule *this)
{
  unsigned __int64 v2; // r14
  __int64 v3; // rsi
  _QWORD *v4; // r15
  _QWORD *v5; // rbx
  __int64 v6; // rcx

  v2 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v3 = v2 & -(__int64)(this != 0);
      if ( !v3 )
      {
        RaiseException(0xC0000005, 1u, 0, 0);
        __debugbreak();
      }
      v4 = *(_QWORD **)((v2 & -(__int64)(this != 0)) + 8);
      if ( v4 )
      {
        do
        {
          ((void (__fastcall *)(_QWORD))*v4)(v4[1]);
          v5 = (_QWORD *)v4[2];
          operator delete(v4);
          v4 = v5;
        }
        while ( v5 );
      }
      *(_QWORD *)(v3 + 8) = 0;
      *((_QWORD *)this + 2) = 0;
    }
    v6 = *((_QWORD *)this + 8);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *(_DWORD *)v2 = 0;
  }
}

```

## disassembly

```asm
0x18000bcdc  push    rbx
0x18000bcde  push    rsi
0x18000bcdf  push    rdi
0x18000bce0  push    r14
0x18000bce2  push    r15
0x18000bce4  sub     rsp, 20h
0x18000bce8  mov     rdi, rcx
0x18000bceb  lea     r14, [rcx+8]
0x18000bcef  cmp     dword ptr [r14], 0
0x18000bcf3  jz      loc_18000BD83
0x18000bcf9  cmp     qword ptr [rcx+10h], 0
0x18000bcfe  jz      short loc_18000BD5D
0x18000bd00  mov     rax, rcx
0x18000bd03  neg     rax
0x18000bd06  sbb     rsi, rsi
0x18000bd09  and     rsi, r14
0x18000bd0c  jnz     short loc_18000BD23
0x18000bd0e  xor     r9d, r9d; lpArguments
0x18000bd11  xor     r8d, r8d; nNumberOfArguments
0x18000bd14  lea     edx, [rsi+1]; dwExceptionFlags
0x18000bd17  mov     ecx, 0C0000005h; dwExceptionCode
0x18000bd1c  call    cs:__imp_RaiseException
0x18000bd22  int     3; Trap to Debugger
0x18000bd23  mov     r15, [rsi+8]
0x18000bd27  test    r15, r15
0x18000bd2a  jz      short loc_18000BD4D
0x18000bd2c  mov     rcx, [r15+8]
0x18000bd30  mov     rax, [r15]
0x18000bd33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd38  mov     rbx, [r15+10h]
0x18000bd3c  mov     rcx, r15
0x18000bd3f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000bd45  mov     r15, rbx
0x18000bd48  test    rbx, rbx
0x18000bd4b  jnz     short loc_18000BD2C
0x18000bd4d  mov     qword ptr [rsi+8], 0
0x18000bd55  mov     qword ptr [rdi+10h], 0
0x18000bd5d  mov     rcx, [rdi+40h]
0x18000bd61  test    rcx, rcx
0x18000bd64  jz      short loc_18000BD72
0x18000bd66  mov     rax, [rcx]
0x18000bd69  mov     rax, [rax+10h]
0x18000bd6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd72  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000bd76  call    cs:__imp_DeleteCriticalSection
0x18000bd7c  mov     dword ptr [r14], 0
0x18000bd83  add     rsp, 20h
0x18000bd87  pop     r15
0x18000bd89  pop     r14
0x18000bd8b  pop     rdi
0x18000bd8c  pop     rsi
0x18000bd8d  pop     rbx
0x18000bd8e  retn
```
