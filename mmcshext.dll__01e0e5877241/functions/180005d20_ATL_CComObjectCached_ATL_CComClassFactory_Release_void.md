# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180005d20`
- end: `0x180005db5`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `149`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005d20`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180005d94`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005d94`
- `KERNEL32!DeleteCriticalSection` at `0x180005d77`
- `KERNEL32!DeleteCriticalSection` at `0x180005d8b`
- `KERNEL32!DeleteCriticalSection` at `0x180005d77`
- `KERNEL32!DeleteCriticalSection` at `0x180005d8b`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::Release(char *a1)
{
  signed __int32 i; // ecx
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 2);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange((volatile signed __int32 *)a1 + 2, i - 1, i);
        i = *((_DWORD *)a1 + 2) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    if ( a1 )
    {
      *((_DWORD *)a1 + 2) = 1;
      *(_QWORD *)a1 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
      if ( a1[112] != (_BYTE)v3 )
      {
        a1[112] = v3;
        DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 72));
      }
      if ( a1[56] )
      {
        a1[56] = 0;
        DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
      }
      operator delete(a1);
    }
  }
  else if ( i == 2 )
  {
    _InterlockedDecrement(&dword_180012EE8);
  }
  return v3;
}

```

## disassembly

```asm
0x180005d20  mov     [rsp+arg_0], rbx
0x180005d25  push    rdi
0x180005d26  sub     rsp, 20h
0x180005d2a  mov     rbx, rcx
0x180005d2d  mov     r8d, 7FFFFFFFh
0x180005d33  mov     ecx, [rcx+8]
0x180005d36  jmp     short loc_180005D47
0x180005d38  lea     edx, [rcx-1]
0x180005d3b  mov     eax, ecx
0x180005d3d  lock cmpxchg [rbx+8], edx
0x180005d42  jz      short loc_180005D4C
0x180005d44  mov     ecx, [rbx+8]
0x180005d47  cmp     ecx, r8d
0x180005d4a  jnz     short loc_180005D38
0x180005d4c  lea     edi, [rcx-1]
0x180005d4f  test    edi, edi
0x180005d51  jnz     short loc_180005D9C
0x180005d53  test    rbx, rbx
0x180005d56  jz      short loc_180005DA8
0x180005d58  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180005d5f  mov     dword ptr [rbx+8], 1
0x180005d66  lea     rcx, [rbx+48h]; lpCriticalSection
0x180005d6a  mov     [rbx], rax
0x180005d6d  cmp     [rcx+28h], dil
0x180005d71  jz      short loc_180005D7D
0x180005d73  mov     [rcx+28h], dil
0x180005d77  call    cs:__imp_DeleteCriticalSection
0x180005d7d  lea     rcx, [rbx+10h]; lpCriticalSection
0x180005d81  cmp     byte ptr [rcx+28h], 0
0x180005d85  jz      short loc_180005D91
0x180005d87  mov     byte ptr [rcx+28h], 0
0x180005d8b  call    cs:__imp_DeleteCriticalSection
0x180005d91  mov     rcx, rbx
0x180005d94  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005d9a  jmp     short loc_180005DA8
0x180005d9c  cmp     edi, 1
0x180005d9f  jnz     short loc_180005DA8
0x180005da1  lock dec cs:dword_180012EE8
0x180005da8  mov     rbx, [rsp+28h+arg_0]
0x180005dad  mov     eax, edi
0x180005daf  add     rsp, 20h
0x180005db3  pop     rdi
0x180005db4  retn
```
