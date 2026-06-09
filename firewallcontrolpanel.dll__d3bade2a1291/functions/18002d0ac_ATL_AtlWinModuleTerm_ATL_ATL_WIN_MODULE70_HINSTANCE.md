# ATL::AtlWinModuleTerm(ATL::_ATL_WIN_MODULE70 *,HINSTANCE__ *)

- ea: `0x18002d0ac`
- end: `0x18002d140`
- name: `?AtlWinModuleTerm@ATL@@YAJPEAU_ATL_WIN_MODULE70@1@PEAUHINSTANCE__@@@Z`
- size: `148`
- prototype: `__int64 __fastcall(struct ATL::_ATL_WIN_MODULE70 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002d04c`

## callees

- `0x18002d0ac`
- `0x18002d148`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002d124`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002d124`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002d10d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002d10d`
- `USER32!UnregisterClassA` at `0x18002d0ef`
- `USER32!UnregisterClassA` at `0x18002d0ef`

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
0x18002d0ac  push    rbx
0x18002d0ae  push    rbp
0x18002d0af  push    rsi
0x18002d0b0  push    rdi
0x18002d0b1  sub     rsp, 28h
0x18002d0b5  mov     rbp, rdx
0x18002d0b8  mov     rbx, rcx
0x18002d0bb  test    rcx, rcx
0x18002d0be  jz      short loc_18002D132
0x18002d0c0  cmp     dword ptr [rcx], 0
0x18002d0c3  jnz     short loc_18002D0C9
0x18002d0c5  xor     eax, eax
0x18002d0c7  jmp     short loc_18002D137
0x18002d0c9  cmp     dword ptr [rcx], 48h ; 'H'
0x18002d0cc  jnz     short loc_18002D132
0x18002d0ce  xor     esi, esi
0x18002d0d0  cmp     [rcx+40h], esi
0x18002d0d3  jle     short loc_18002D114
0x18002d0d5  test    esi, esi
0x18002d0d7  js      short loc_18002D0FE
0x18002d0d9  lea     rdi, [rbx+38h]
0x18002d0dd  cmp     esi, [rdi+8]
0x18002d0e0  jge     short loc_18002D0FE
0x18002d0e2  mov     rax, [rdi]
0x18002d0e5  mov     rdx, rbp; hInstance
0x18002d0e8  movsxd  rcx, esi
0x18002d0eb  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x18002d0ef  call    cs:__imp_UnregisterClassA
0x18002d0f5  inc     esi
0x18002d0f7  cmp     esi, [rbx+40h]
0x18002d0fa  jl      short loc_18002D0D5
0x18002d0fc  jmp     short loc_18002D118
0x18002d0fe  xor     r9d, r9d; lpArguments
0x18002d101  xor     r8d, r8d; nNumberOfArguments
0x18002d104  mov     ecx, 0C000008Ch; dwExceptionCode
0x18002d109  lea     edx, [r9+1]; dwExceptionFlags
0x18002d10d  call    cs:__imp_RaiseException
0x18002d113  int     3; Trap to Debugger
0x18002d114  lea     rdi, [rcx+38h]
0x18002d118  mov     rcx, rdi
0x18002d11b  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18002d120  lea     rcx, [rbx+8]; lpCriticalSection
0x18002d124  call    cs:__imp_DeleteCriticalSection
0x18002d12a  mov     dword ptr [rbx], 0
0x18002d130  jmp     short loc_18002D0C5
0x18002d132  mov     eax, 80070057h
0x18002d137  add     rsp, 28h
0x18002d13b  pop     rdi
0x18002d13c  pop     rsi
0x18002d13d  pop     rbp
0x18002d13e  pop     rbx
0x18002d13f  retn
```
