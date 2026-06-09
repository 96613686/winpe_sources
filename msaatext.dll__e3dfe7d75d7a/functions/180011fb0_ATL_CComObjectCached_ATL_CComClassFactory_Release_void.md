# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180011fb0`
- end: `0x180012045`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `149`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180011fb0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180012024`
- `msvcrt!??3@YAXPEAX@Z` at `0x180012024`
- `KERNEL32!DeleteCriticalSection` at `0x180012007`
- `KERNEL32!DeleteCriticalSection` at `0x18001201b`
- `KERNEL32!DeleteCriticalSection` at `0x180012007`
- `KERNEL32!DeleteCriticalSection` at `0x18001201b`

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
    _InterlockedDecrement(&dword_180024B28);
  }
  return v3;
}

```

## disassembly

```asm
0x180011fb0  mov     [rsp+arg_0], rbx
0x180011fb5  push    rdi
0x180011fb6  sub     rsp, 20h
0x180011fba  mov     rbx, rcx
0x180011fbd  mov     r8d, 7FFFFFFFh
0x180011fc3  mov     ecx, [rcx+8]
0x180011fc6  jmp     short loc_180011FD7
0x180011fc8  lea     edx, [rcx-1]
0x180011fcb  mov     eax, ecx
0x180011fcd  lock cmpxchg [rbx+8], edx
0x180011fd2  jz      short loc_180011FDC
0x180011fd4  mov     ecx, [rbx+8]
0x180011fd7  cmp     ecx, r8d
0x180011fda  jnz     short loc_180011FC8
0x180011fdc  lea     edi, [rcx-1]
0x180011fdf  test    edi, edi
0x180011fe1  jnz     short loc_18001202C
0x180011fe3  test    rbx, rbx
0x180011fe6  jz      short loc_180012038
0x180011fe8  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180011fef  mov     dword ptr [rbx+8], 1
0x180011ff6  lea     rcx, [rbx+48h]; lpCriticalSection
0x180011ffa  mov     [rbx], rax
0x180011ffd  cmp     [rcx+28h], dil
0x180012001  jz      short loc_18001200D
0x180012003  mov     [rcx+28h], dil
0x180012007  call    cs:__imp_DeleteCriticalSection
0x18001200d  lea     rcx, [rbx+10h]; lpCriticalSection
0x180012011  cmp     byte ptr [rcx+28h], 0
0x180012015  jz      short loc_180012021
0x180012017  mov     byte ptr [rcx+28h], 0
0x18001201b  call    cs:__imp_DeleteCriticalSection
0x180012021  mov     rcx, rbx
0x180012024  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001202a  jmp     short loc_180012038
0x18001202c  cmp     edi, 1
0x18001202f  jnz     short loc_180012038
0x180012031  lock dec cs:dword_180024B28
0x180012038  mov     rbx, [rsp+28h+arg_0]
0x18001203d  mov     eax, edi
0x18001203f  add     rsp, 20h
0x180012043  pop     rdi
0x180012044  retn
```
