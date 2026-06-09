# ATL::CAtlWinModule::Term(void)

- ea: `0x180016338`
- end: `0x1800163c3`
- name: `?Term@CAtlWinModule@ATL@@QEAAXXZ`
- size: `139`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800052c0`

## callees

- `0x180005250`
- `0x180016338`

## import_xrefs

- `USER32!UnregisterClassW` at `0x180016379`
- `USER32!UnregisterClassW` at `0x180016379`
- `KERNEL32!DeleteCriticalSection` at `0x1800163ae`
- `KERNEL32!DeleteCriticalSection` at `0x1800163ae`
- `KERNEL32!RaiseException` at `0x180016397`
- `KERNEL32!RaiseException` at `0x180016397`

## pseudocode

```c
void __fastcall ATL::CAtlWinModule::Term(ATL::CAtlWinModule *this)
{
  HINSTANCE v2; // rbp
  int v3; // esi
  _QWORD *v4; // rdi

  if ( this && *(_DWORD *)this == 72 )
  {
    v2 = (HINSTANCE)hInstance;
    v3 = 0;
    if ( *((int *)this + 16) <= 0 )
    {
      v4 = (_QWORD *)((char *)this + 56);
    }
    else
    {
      do
      {
        if ( v3 < 0 || (v4 = (_QWORD *)((char *)this + 56), v3 >= *((_DWORD *)this + 16)) )
        {
          RaiseException(0xC000008C, 1u, 0, 0);
          __debugbreak();
        }
        UnregisterClassW((LPCWSTR)*(unsigned __int16 *)(*v4 + 2LL * v3++), v2);
      }
      while ( v3 < *((_DWORD *)this + 16) );
    }
    ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll(v4);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    *(_DWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180016338  test    rcx, rcx
0x18001633b  jz      locret_1800163C2
0x180016341  push    rbx
0x180016342  push    rbp
0x180016343  push    rsi
0x180016344  push    rdi
0x180016345  sub     rsp, 28h
0x180016349  cmp     dword ptr [rcx], 48h ; 'H'
0x18001634c  mov     rbx, rcx
0x18001634f  jnz     short loc_1800163BA
0x180016351  mov     rbp, cs:hInstance
0x180016358  xor     esi, esi
0x18001635a  cmp     [rcx+40h], esi
0x18001635d  jle     short loc_18001639E
0x18001635f  test    esi, esi
0x180016361  js      short loc_180016388
0x180016363  lea     rdi, [rbx+38h]
0x180016367  cmp     esi, [rdi+8]
0x18001636a  jge     short loc_180016388
0x18001636c  mov     rax, [rdi]
0x18001636f  mov     rdx, rbp; hInstance
0x180016372  movsxd  rcx, esi
0x180016375  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x180016379  call    cs:__imp_UnregisterClassW
0x18001637f  inc     esi
0x180016381  cmp     esi, [rbx+40h]
0x180016384  jl      short loc_18001635F
0x180016386  jmp     short loc_1800163A2
0x180016388  xor     r9d, r9d; lpArguments
0x18001638b  xor     r8d, r8d; nNumberOfArguments
0x18001638e  mov     ecx, 0C000008Ch; dwExceptionCode
0x180016393  lea     edx, [r9+1]; dwExceptionFlags
0x180016397  call    cs:__imp_RaiseException
0x18001639d  int     3; Trap to Debugger
0x18001639e  lea     rdi, [rcx+38h]
0x1800163a2  mov     rcx, rdi
0x1800163a5  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x1800163aa  lea     rcx, [rbx+8]; lpCriticalSection
0x1800163ae  call    cs:__imp_DeleteCriticalSection
0x1800163b4  mov     dword ptr [rbx], 0
0x1800163ba  add     rsp, 28h
0x1800163be  pop     rdi
0x1800163bf  pop     rsi
0x1800163c0  pop     rbp
0x1800163c1  pop     rbx
0x1800163c2  retn
```
