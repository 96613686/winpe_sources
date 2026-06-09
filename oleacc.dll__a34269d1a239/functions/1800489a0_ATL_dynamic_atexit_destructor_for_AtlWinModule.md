# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x1800489a0`
- end: `0x180048a38`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `152`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180018c18`
- `0x1800489a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180048a31`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180048a31`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800489fc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800489fc`
- `USER32!UnregisterClassA` at `0x1800489d9`
- `USER32!UnregisterClassA` at `0x1800489d9`

## pseudocode

```c
__int64 ATL::_dynamic_atexit_destructor_for___AtlWinModule__()
{
  HINSTANCE v0; // rdi
  int i; // ebx

  if ( ATL::_AtlWinModule == 72 )
  {
    v0 = hInstance;
    for ( i = 0; i < dword_1800614A0; ++i )
    {
      if ( i < 0 )
      {
        RaiseException(0xC000008C, 1u, 0, 0);
        JUMPOUT(0x180048A37LL);
      }
      UnregisterClassA((LPCSTR)*(unsigned __int16 *)(qword_180061498 + 2LL * i), v0);
    }
    ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll(&qword_180061498);
    DeleteCriticalSection(&stru_180061468);
    ATL::_AtlWinModule = 0;
  }
  return ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll(&qword_180061498);
}

```

## disassembly

```asm
0x1800489a0  mov     [rsp+arg_0], rbx
0x1800489a5  push    rdi
0x1800489a6  sub     rsp, 20h
0x1800489aa  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x1800489b1  jnz     short loc_180048A0C
0x1800489b3  mov     rdi, cs:hInstance
0x1800489ba  xor     ebx, ebx
0x1800489bc  cmp     cs:dword_1800614A0, ebx
0x1800489c2  jle     short loc_1800489E9
0x1800489c4  test    ebx, ebx
0x1800489c6  js      short loc_180048A22
0x1800489c8  mov     rax, cs:qword_180061498
0x1800489cf  mov     rdx, rdi; hInstance
0x1800489d2  movsxd  rcx, ebx
0x1800489d5  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x1800489d9  call    cs:__imp_UnregisterClassA
0x1800489df  inc     ebx
0x1800489e1  cmp     ebx, cs:dword_1800614A0
0x1800489e7  jl      short loc_1800489C4
0x1800489e9  lea     rcx, qword_180061498
0x1800489f0  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x1800489f5  lea     rcx, stru_180061468; lpCriticalSection
0x1800489fc  call    cs:__imp_DeleteCriticalSection
0x180048a02  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x180048a0c  lea     rcx, qword_180061498
0x180048a13  mov     rbx, [rsp+28h+arg_0]
0x180048a18  add     rsp, 20h
0x180048a1c  pop     rdi
0x180048a1d  jmp     ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x180048a22  xor     r9d, r9d; lpArguments
0x180048a25  xor     r8d, r8d; nNumberOfArguments
0x180048a28  mov     ecx, 0C000008Ch; dwExceptionCode
0x180048a2d  lea     edx, [r9+1]; dwExceptionFlags
0x180048a31  call    cs:__imp_RaiseException
```
