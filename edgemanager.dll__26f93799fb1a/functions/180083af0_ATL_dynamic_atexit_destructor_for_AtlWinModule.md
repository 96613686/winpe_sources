# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x180083af0`
- end: `0x180083ba4`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `180`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180021ae0`
- `0x18002c508`
- `0x180083af0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180083b4c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180083b4c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180083b9d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180083b9d`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassA` at `0x180083b29`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassA` at `0x180083b29`

## pseudocode

```c
void ATL::_dynamic_atexit_destructor_for___AtlWinModule__()
{
  HINSTANCE v0; // rdi
  int i; // ebx

  if ( ATL::_AtlWinModule == 72 )
  {
    v0 = hInstance;
    for ( i = 0; i < (int)qword_1800B6820; ++i )
    {
      if ( i < 0 )
      {
        RaiseException(0xC000008C, 1u, 0, 0);
        JUMPOUT(0x180083BA3LL);
      }
      UnregisterClassA((LPCSTR)*((unsigned __int16 *)qword_1800B6818 + i), v0);
    }
    ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll(&qword_1800B6818);
    DeleteCriticalSection(&stru_1800B67E8);
    ATL::_AtlWinModule = 0;
  }
  if ( qword_1800B6818 )
  {
    free(qword_1800B6818);
    qword_1800B6818 = 0;
  }
  qword_1800B6820 = 0;
}

```

## disassembly

```asm
0x180083af0  mov     [rsp+arg_0], rbx
0x180083af5  push    rdi
0x180083af6  sub     rsp, 20h
0x180083afa  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x180083b01  jnz     short loc_180083B5C
0x180083b03  mov     rdi, cs:hInstance
0x180083b0a  xor     ebx, ebx
0x180083b0c  cmp     dword ptr cs:qword_1800B6820, ebx
0x180083b12  jle     short loc_180083B39
0x180083b14  test    ebx, ebx
0x180083b16  js      short loc_180083B8E
0x180083b18  mov     rax, cs:qword_1800B6818
0x180083b1f  mov     rdx, rdi; hInstance
0x180083b22  movsxd  rcx, ebx
0x180083b25  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x180083b29  call    cs:__imp_UnregisterClassA
0x180083b2f  inc     ebx
0x180083b31  cmp     ebx, dword ptr cs:qword_1800B6820
0x180083b37  jl      short loc_180083B14
0x180083b39  lea     rcx, qword_1800B6818
0x180083b40  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x180083b45  lea     rcx, stru_1800B67E8; lpCriticalSection
0x180083b4c  call    cs:__imp_DeleteCriticalSection
0x180083b52  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x180083b5c  mov     rcx, cs:qword_1800B6818; Block
0x180083b63  test    rcx, rcx
0x180083b66  jz      short loc_180083B78
0x180083b68  call    free
0x180083b6d  mov     cs:qword_1800B6818, 0
0x180083b78  mov     rbx, [rsp+28h+arg_0]
0x180083b7d  mov     cs:qword_1800B6820, 0
0x180083b88  add     rsp, 20h
0x180083b8c  pop     rdi
0x180083b8d  retn
0x180083b8e  xor     r9d, r9d; lpArguments
0x180083b91  xor     r8d, r8d; nNumberOfArguments
0x180083b94  mov     ecx, 0C000008Ch; dwExceptionCode
0x180083b99  lea     edx, [r9+1]; dwExceptionFlags
0x180083b9d  call    cs:__imp_RaiseException
```
