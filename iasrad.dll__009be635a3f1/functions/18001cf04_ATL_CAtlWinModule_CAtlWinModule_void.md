# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x18001cf04`
- end: `0x18001cf89`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `133`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002fe20`

## callees

- `0x18001236c`
- `0x18001cf04`
- `0x18001cfc4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001cf61`
- `KERNEL32!DeleteCriticalSection` at `0x18001cf61`
- `USER32!UnregisterClassA` at `0x18001cf42`
- `USER32!UnregisterClassA` at `0x18001cf42`

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
          JUMPOUT(0x18001CF88LL);
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
0x18001cf04  push    rbx
0x18001cf06  push    rbp
0x18001cf07  push    rsi
0x18001cf08  push    rdi
0x18001cf09  sub     rsp, 28h
0x18001cf0d  mov     rbx, rcx
0x18001cf10  test    rcx, rcx
0x18001cf13  jz      short loc_18001CF6D
0x18001cf15  cmp     dword ptr [rcx], 48h ; 'H'
0x18001cf18  jnz     short loc_18001CF6D
0x18001cf1a  mov     rbp, cs:hInstance
0x18001cf21  xor     edi, edi
0x18001cf23  cmp     [rcx+40h], edi
0x18001cf26  jle     short loc_18001CF51
0x18001cf28  test    edi, edi
0x18001cf2a  js      short loc_18001CF7E
0x18001cf2c  lea     rsi, [rbx+38h]
0x18001cf30  cmp     edi, [rsi+8]
0x18001cf33  jge     short loc_18001CF7E
0x18001cf35  mov     rax, [rsi]
0x18001cf38  mov     rdx, rbp; hInstance
0x18001cf3b  movsxd  rcx, edi
0x18001cf3e  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x18001cf42  call    cs:__imp_UnregisterClassA
0x18001cf48  inc     edi
0x18001cf4a  cmp     edi, [rbx+40h]
0x18001cf4d  jl      short loc_18001CF28
0x18001cf4f  jmp     short loc_18001CF55
0x18001cf51  lea     rsi, [rcx+38h]
0x18001cf55  mov     rcx, rsi
0x18001cf58  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18001cf5d  lea     rcx, [rbx+8]; lpCriticalSection
0x18001cf61  call    cs:__imp_DeleteCriticalSection
0x18001cf67  mov     dword ptr [rbx], 0
0x18001cf6d  lea     rcx, [rbx+38h]
0x18001cf71  add     rsp, 28h
0x18001cf75  pop     rdi
0x18001cf76  pop     rsi
0x18001cf77  pop     rbp
0x18001cf78  pop     rbx
0x18001cf79  jmp     ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18001cf7e  mov     ecx, 0C000008Ch; unsigned int
0x18001cf83  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
