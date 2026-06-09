# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x18000c5fc`
- end: `0x18000c681`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `133`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002d450`

## callees

- `0x18000960c`
- `0x18000c5fc`
- `0x18000c6bc`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000c659`
- `KERNEL32!DeleteCriticalSection` at `0x18000c659`
- `USER32!UnregisterClassA` at `0x18000c63a`
- `USER32!UnregisterClassA` at `0x18000c63a`

## pseudocode

```c
void __fastcall ATL::CAtlWinModule::~CAtlWinModule(ATL::CAtlWinModule *this, unsigned int a2)
{
  HINSTANCE v3; // rbp
  int v4; // edi
  _QWORD *v5; // rsi

  if ( this && *(_DWORD *)this == 72 )
  {
    v3 = hInstance;
    v4 = 0;
    if ( *((int *)this + 16) <= 0 )
    {
      v5 = (_QWORD *)((char *)this + 56);
    }
    else
    {
      do
      {
        if ( v4 < 0 || (v5 = (_QWORD *)((char *)this + 56), v4 >= *((_DWORD *)this + 16)) )
        {
          ATL::_AtlRaiseException(0xC000008C, a2);
          JUMPOUT(0x18000C680LL);
        }
        UnregisterClassA((LPCSTR)*(unsigned __int16 *)(*v5 + 2LL * v4++), v3);
      }
      while ( v4 < *((_DWORD *)this + 16) );
    }
    ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll(v5);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    *(_DWORD *)this = 0;
  }
  ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll((char *)this + 56);
}

```

## disassembly

```asm
0x18000c5fc  push    rbx
0x18000c5fe  push    rbp
0x18000c5ff  push    rsi
0x18000c600  push    rdi
0x18000c601  sub     rsp, 28h
0x18000c605  mov     rbx, rcx
0x18000c608  test    rcx, rcx
0x18000c60b  jz      short loc_18000C665
0x18000c60d  cmp     dword ptr [rcx], 48h ; 'H'
0x18000c610  jnz     short loc_18000C665
0x18000c612  mov     rbp, cs:hInstance
0x18000c619  xor     edi, edi
0x18000c61b  cmp     [rcx+40h], edi
0x18000c61e  jle     short loc_18000C649
0x18000c620  test    edi, edi
0x18000c622  js      short loc_18000C676
0x18000c624  lea     rsi, [rbx+38h]
0x18000c628  cmp     edi, [rsi+8]
0x18000c62b  jge     short loc_18000C676
0x18000c62d  mov     rax, [rsi]
0x18000c630  mov     rdx, rbp; hInstance
0x18000c633  movsxd  rcx, edi
0x18000c636  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x18000c63a  call    cs:__imp_UnregisterClassA
0x18000c640  inc     edi
0x18000c642  cmp     edi, [rbx+40h]
0x18000c645  jl      short loc_18000C620
0x18000c647  jmp     short loc_18000C64D
0x18000c649  lea     rsi, [rcx+38h]
0x18000c64d  mov     rcx, rsi
0x18000c650  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18000c655  lea     rcx, [rbx+8]; lpCriticalSection
0x18000c659  call    cs:__imp_DeleteCriticalSection
0x18000c65f  mov     dword ptr [rbx], 0
0x18000c665  lea     rcx, [rbx+38h]
0x18000c669  add     rsp, 28h
0x18000c66d  pop     rdi
0x18000c66e  pop     rsi
0x18000c66f  pop     rbp
0x18000c670  pop     rbx
0x18000c671  jmp     ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18000c676  mov     ecx, 0C000008Ch; unsigned int
0x18000c67b  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
