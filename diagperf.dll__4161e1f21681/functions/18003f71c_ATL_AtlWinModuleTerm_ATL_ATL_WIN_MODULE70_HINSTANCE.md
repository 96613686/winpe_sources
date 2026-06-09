# ATL::AtlWinModuleTerm(ATL::_ATL_WIN_MODULE70 *,HINSTANCE__ *)

- ea: `0x18003f71c`
- end: `0x18003f7b0`
- name: `?AtlWinModuleTerm@ATL@@YAJPEAU_ATL_WIN_MODULE70@1@PEAUHINSTANCE__@@@Z`
- size: `148`
- prototype: `int(struct ATL::_ATL_WIN_MODULE70 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18003f6f0`

## callees

- `0x18003f71c`
- `0x18003f7b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003f77d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003f77d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003f794`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003f794`
- `USER32!UnregisterClassA` at `0x18003f75f`
- `USER32!UnregisterClassA` at `0x18003f75f`

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
          UnregisterClassA((LPCSTR)*(unsigned __int16 *)(*v6 + 2LL * v5++), a2);
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
0x18003f71c  push    rbx
0x18003f71e  push    rbp
0x18003f71f  push    rsi
0x18003f720  push    rdi
0x18003f721  sub     rsp, 28h
0x18003f725  mov     rbp, rdx
0x18003f728  mov     rbx, rcx
0x18003f72b  test    rcx, rcx
0x18003f72e  jz      short loc_18003F7A2
0x18003f730  cmp     dword ptr [rcx], 0
0x18003f733  jnz     short loc_18003F739
0x18003f735  xor     eax, eax
0x18003f737  jmp     short loc_18003F7A7
0x18003f739  cmp     dword ptr [rcx], 48h ; 'H'
0x18003f73c  jnz     short loc_18003F7A2
0x18003f73e  xor     esi, esi
0x18003f740  cmp     [rcx+40h], esi
0x18003f743  jle     short loc_18003F784
0x18003f745  test    esi, esi
0x18003f747  js      short loc_18003F76E
0x18003f749  lea     rdi, [rbx+38h]
0x18003f74d  cmp     esi, [rdi+8]
0x18003f750  jge     short loc_18003F76E
0x18003f752  mov     rax, [rdi]
0x18003f755  mov     rdx, rbp; hInstance
0x18003f758  movsxd  rcx, esi
0x18003f75b  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x18003f75f  call    cs:__imp_UnregisterClassA
0x18003f765  inc     esi
0x18003f767  cmp     esi, [rbx+40h]
0x18003f76a  jl      short loc_18003F745
0x18003f76c  jmp     short loc_18003F788
0x18003f76e  xor     r9d, r9d; lpArguments
0x18003f771  xor     r8d, r8d; nNumberOfArguments
0x18003f774  mov     ecx, 0C000008Ch; dwExceptionCode
0x18003f779  lea     edx, [r9+1]; dwExceptionFlags
0x18003f77d  call    cs:__imp_RaiseException
0x18003f783  int     3; Trap to Debugger
0x18003f784  lea     rdi, [rcx+38h]
0x18003f788  mov     rcx, rdi
0x18003f78b  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18003f790  lea     rcx, [rbx+8]; lpCriticalSection
0x18003f794  call    cs:__imp_DeleteCriticalSection
0x18003f79a  mov     dword ptr [rbx], 0
0x18003f7a0  jmp     short loc_18003F735
0x18003f7a2  mov     eax, 80070057h
0x18003f7a7  add     rsp, 28h
0x18003f7ab  pop     rdi
0x18003f7ac  pop     rsi
0x18003f7ad  pop     rbp
0x18003f7ae  pop     rbx
0x18003f7af  retn
```
