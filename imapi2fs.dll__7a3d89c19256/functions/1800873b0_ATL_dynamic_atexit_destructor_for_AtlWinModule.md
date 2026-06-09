# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x1800873b0`
- end: `0x180087465`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `181`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005250`
- `0x1800873b0`

## import_xrefs

- `msvcrt!free` at `0x180087428`
- `msvcrt!free` at `0x180087428`
- `USER32!UnregisterClassW` at `0x1800873e9`
- `USER32!UnregisterClassW` at `0x1800873e9`
- `KERNEL32!DeleteCriticalSection` at `0x18008740c`
- `KERNEL32!DeleteCriticalSection` at `0x18008740c`
- `KERNEL32!RaiseException` at `0x18008745e`
- `KERNEL32!RaiseException` at `0x18008745e`

## pseudocode

```c
void ATL::_dynamic_atexit_destructor_for___AtlWinModule__()
{
  HINSTANCE v0; // rdi
  int i; // ebx

  if ( ATL::_AtlWinModule == 72 )
  {
    v0 = (HINSTANCE)hInstance;
    for ( i = 0; i < (int)qword_1800B5610; ++i )
    {
      if ( i < 0 )
      {
        RaiseException(0xC000008C, 1u, 0, 0);
        JUMPOUT(0x180087464LL);
      }
      UnregisterClassW((LPCWSTR)*((unsigned __int16 *)Block + i), v0);
    }
    ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll(&Block);
    DeleteCriticalSection(&CriticalSection);
    ATL::_AtlWinModule = 0;
  }
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  qword_1800B5610 = 0;
}

```

## disassembly

```asm
0x1800873b0  mov     [rsp+arg_0], rbx
0x1800873b5  push    rdi
0x1800873b6  sub     rsp, 20h
0x1800873ba  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x1800873c1  jnz     short loc_18008741C
0x1800873c3  mov     rdi, cs:hInstance
0x1800873ca  xor     ebx, ebx
0x1800873cc  cmp     dword ptr cs:qword_1800B5610, ebx
0x1800873d2  jle     short loc_1800873F9
0x1800873d4  test    ebx, ebx
0x1800873d6  js      short loc_18008744F
0x1800873d8  mov     rax, cs:Block
0x1800873df  mov     rdx, rdi; hInstance
0x1800873e2  movsxd  rcx, ebx
0x1800873e5  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x1800873e9  call    cs:__imp_UnregisterClassW
0x1800873ef  inc     ebx
0x1800873f1  cmp     ebx, dword ptr cs:qword_1800B5610
0x1800873f7  jl      short loc_1800873D4
0x1800873f9  lea     rcx, Block
0x180087400  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x180087405  lea     rcx, CriticalSection; lpCriticalSection
0x18008740c  call    cs:__imp_DeleteCriticalSection
0x180087412  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x18008741c  mov     rcx, cs:Block; Block
0x180087423  test    rcx, rcx
0x180087426  jz      short loc_180087439
0x180087428  call    cs:__imp_free
0x18008742e  mov     cs:Block, 0
0x180087439  mov     rbx, [rsp+28h+arg_0]
0x18008743e  mov     cs:qword_1800B5610, 0
0x180087449  add     rsp, 20h
0x18008744d  pop     rdi
0x18008744e  retn
0x18008744f  xor     r9d, r9d; lpArguments
0x180087452  xor     r8d, r8d; nNumberOfArguments
0x180087455  mov     ecx, 0C000008Ch; dwExceptionCode
0x18008745a  lea     edx, [r9+1]; dwExceptionFlags
0x18008745e  call    cs:__imp_RaiseException
```
