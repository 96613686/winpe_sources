# ATL::AtlWinModuleTerm(ATL::_ATL_WIN_MODULE70 *,HINSTANCE__ *)

- ea: `0x180006e88`
- end: `0x180006f1c`
- name: `?AtlWinModuleTerm@ATL@@YAJPEAU_ATL_WIN_MODULE70@1@PEAUHINSTANCE__@@@Z`
- size: `148`
- prototype: `__int64 __fastcall(struct ATL::_ATL_WIN_MODULE70 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002677c`

## callees

- `0x180006e88`
- `0x18000732c`

## import_xrefs

- `KERNEL32!RaiseException` at `0x180006ee9`
- `KERNEL32!RaiseException` at `0x180006ee9`
- `KERNEL32!DeleteCriticalSection` at `0x180006f00`
- `KERNEL32!DeleteCriticalSection` at `0x180006f00`
- `USER32!UnregisterClassW` at `0x180006ecb`
- `USER32!UnregisterClassW` at `0x180006ecb`

## pseudocode

```c
__int64 __fastcall ATL::AtlWinModuleTerm(struct ATL::_ATL_WIN_MODULE70 *a1, HINSTANCE a2)
{
  int v5; // esi
  _QWORD *v6; // rdi

  if ( a1 )
  {
    if ( !*(_DWORD *)a1 )
      return 0;
    if ( *(_DWORD *)a1 == 72 )
    {
      v5 = 0;
      if ( *((int *)a1 + 16) <= 0 )
      {
        v6 = (_QWORD *)((char *)a1 + 56);
      }
      else
      {
        do
        {
          if ( v5 < 0 || (v6 = (_QWORD *)((char *)a1 + 56), v5 >= *((_DWORD *)a1 + 16)) )
          {
            RaiseException(0xC000008C, 1u, 0, 0);
            __debugbreak();
          }
          UnregisterClassW((LPCWSTR)*(unsigned __int16 *)(*v6 + 2LL * v5++), a2);
        }
        while ( v5 < *((_DWORD *)a1 + 16) );
      }
      ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll(v6);
      DeleteCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 8));
      *(_DWORD *)a1 = 0;
      return 0;
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180006e88  push    rbx
0x180006e8a  push    rbp
0x180006e8b  push    rsi
0x180006e8c  push    rdi
0x180006e8d  sub     rsp, 28h
0x180006e91  mov     rbp, rdx
0x180006e94  mov     rbx, rcx
0x180006e97  test    rcx, rcx
0x180006e9a  jz      short loc_180006F0E
0x180006e9c  cmp     dword ptr [rcx], 0
0x180006e9f  jnz     short loc_180006EA5
0x180006ea1  xor     eax, eax
0x180006ea3  jmp     short loc_180006F13
0x180006ea5  cmp     dword ptr [rcx], 48h ; 'H'
0x180006ea8  jnz     short loc_180006F0E
0x180006eaa  xor     esi, esi
0x180006eac  cmp     [rcx+40h], esi
0x180006eaf  jle     short loc_180006EF0
0x180006eb1  test    esi, esi
0x180006eb3  js      short loc_180006EDA
0x180006eb5  lea     rdi, [rbx+38h]
0x180006eb9  cmp     esi, [rdi+8]
0x180006ebc  jge     short loc_180006EDA
0x180006ebe  mov     rax, [rdi]
0x180006ec1  mov     rdx, rbp; hInstance
0x180006ec4  movsxd  rcx, esi
0x180006ec7  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x180006ecb  call    cs:__imp_UnregisterClassW
0x180006ed1  inc     esi
0x180006ed3  cmp     esi, [rbx+40h]
0x180006ed6  jl      short loc_180006EB1
0x180006ed8  jmp     short loc_180006EF4
0x180006eda  xor     r9d, r9d; lpArguments
0x180006edd  xor     r8d, r8d; nNumberOfArguments
0x180006ee0  mov     ecx, 0C000008Ch; dwExceptionCode
0x180006ee5  lea     edx, [r9+1]; dwExceptionFlags
0x180006ee9  call    cs:__imp_RaiseException
0x180006eef  int     3; Trap to Debugger
0x180006ef0  lea     rdi, [rcx+38h]
0x180006ef4  mov     rcx, rdi
0x180006ef7  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x180006efc  lea     rcx, [rbx+8]; lpCriticalSection
0x180006f00  call    cs:__imp_DeleteCriticalSection
0x180006f06  mov     dword ptr [rbx], 0
0x180006f0c  jmp     short loc_180006EA1
0x180006f0e  mov     eax, 80070057h
0x180006f13  add     rsp, 28h
0x180006f17  pop     rdi
0x180006f18  pop     rsi
0x180006f19  pop     rbp
0x180006f1a  pop     rbx
0x180006f1b  retn
```
