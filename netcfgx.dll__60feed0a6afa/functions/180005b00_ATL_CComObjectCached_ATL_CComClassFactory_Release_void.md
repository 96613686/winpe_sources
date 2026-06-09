# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180005b00`
- end: `0x180005b91`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `145`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001fec`
- `0x180005b00`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005b57`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005b57`

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
      *((_DWORD *)a1 + 2) = -1073741823;
      *(_QWORD *)a1 = &ATL::CComClassFactory::`vftable';
      if ( a1[56] != (_BYTE)v3 )
      {
        a1[56] = v3;
        DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
      }
      operator delete(a1, 0x48u);
    }
  }
  else if ( i == 2 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *, _QWORD, __int64))(*(_QWORD *)ATL::_pAtlModule + 16LL))(
      ATL::_pAtlModule,
      *(_QWORD *)ATL::_pAtlModule,
      0x7FFFFFFF);
  }
  return v3;
}

```

## disassembly

```asm
0x180005b00  mov     [rsp+arg_0], rbx
0x180005b05  push    rdi
0x180005b06  sub     rsp, 20h
0x180005b0a  mov     rbx, rcx
0x180005b0d  mov     r8d, 7FFFFFFFh
0x180005b13  mov     ecx, [rcx+8]
0x180005b16  jmp     short loc_180005B27
0x180005b18  lea     edx, [rcx-1]
0x180005b1b  mov     eax, ecx
0x180005b1d  lock cmpxchg [rbx+8], edx
0x180005b22  jz      short loc_180005B2C
0x180005b24  mov     ecx, [rbx+8]
0x180005b27  cmp     ecx, r8d
0x180005b2a  jnz     short loc_180005B18
0x180005b2c  lea     edi, [rcx-1]
0x180005b2f  test    edi, edi
0x180005b31  jnz     short loc_180005B6C
0x180005b33  test    rbx, rbx
0x180005b36  jz      short loc_180005B84
0x180005b38  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180005b3f  mov     dword ptr [rbx+8], 0C0000001h
0x180005b46  lea     rcx, [rbx+10h]; lpCriticalSection
0x180005b4a  mov     [rbx], rax
0x180005b4d  cmp     [rcx+28h], dil
0x180005b51  jz      short loc_180005B5D
0x180005b53  mov     [rcx+28h], dil
0x180005b57  call    cs:__imp_DeleteCriticalSection
0x180005b5d  mov     edx, 48h ; 'H'; unsigned __int64
0x180005b62  mov     rcx, rbx; void *
0x180005b65  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005b6a  jmp     short loc_180005B84
0x180005b6c  cmp     edi, 1
0x180005b6f  jnz     short loc_180005B84
0x180005b71  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005b78  mov     rdx, [rcx]
0x180005b7b  mov     rax, [rdx+10h]
0x180005b7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b84  mov     rbx, [rsp+28h+arg_0]
0x180005b89  mov     eax, edi
0x180005b8b  add     rsp, 20h
0x180005b8f  pop     rdi
0x180005b90  retn
```
