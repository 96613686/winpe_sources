# ATL::AtlWinModuleTerm(ATL::_ATL_WIN_MODULE70 *,HINSTANCE__ *)

- ea: `0x18000712c`
- end: `0x1800071c0`
- name: `?AtlWinModuleTerm@ATL@@YAJPEAU_ATL_WIN_MODULE70@1@PEAUHINSTANCE__@@@Z`
- size: `148`
- prototype: `__int64 __fastcall(struct ATL::_ATL_WIN_MODULE70 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007d3c`

## callees

- `0x18000712c`
- `0x18000769c`

## import_xrefs

- `USER32!UnregisterClassW` at `0x18000716f`
- `USER32!UnregisterClassW` at `0x18000716f`
- `KERNEL32!DeleteCriticalSection` at `0x1800071a4`
- `KERNEL32!DeleteCriticalSection` at `0x1800071a4`
- `KERNEL32!RaiseException` at `0x18000718d`
- `KERNEL32!RaiseException` at `0x18000718d`

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
0x18000712c  push    rbx
0x18000712e  push    rbp
0x18000712f  push    rsi
0x180007130  push    rdi
0x180007131  sub     rsp, 28h
0x180007135  mov     rbp, rdx
0x180007138  mov     rbx, rcx
0x18000713b  test    rcx, rcx
0x18000713e  jz      short loc_1800071B2
0x180007140  cmp     dword ptr [rcx], 0
0x180007143  jnz     short loc_180007149
0x180007145  xor     eax, eax
0x180007147  jmp     short loc_1800071B7
0x180007149  cmp     dword ptr [rcx], 48h ; 'H'
0x18000714c  jnz     short loc_1800071B2
0x18000714e  xor     esi, esi
0x180007150  cmp     [rcx+40h], esi
0x180007153  jle     short loc_180007194
0x180007155  test    esi, esi
0x180007157  js      short loc_18000717E
0x180007159  lea     rdi, [rbx+38h]
0x18000715d  cmp     esi, [rdi+8]
0x180007160  jge     short loc_18000717E
0x180007162  mov     rax, [rdi]
0x180007165  mov     rdx, rbp; hInstance
0x180007168  movsxd  rcx, esi
0x18000716b  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x18000716f  call    cs:__imp_UnregisterClassW
0x180007175  inc     esi
0x180007177  cmp     esi, [rbx+40h]
0x18000717a  jl      short loc_180007155
0x18000717c  jmp     short loc_180007198
0x18000717e  xor     r9d, r9d; lpArguments
0x180007181  xor     r8d, r8d; nNumberOfArguments
0x180007184  mov     ecx, 0C000008Ch; dwExceptionCode
0x180007189  lea     edx, [r9+1]; dwExceptionFlags
0x18000718d  call    cs:__imp_RaiseException
0x180007193  int     3; Trap to Debugger
0x180007194  lea     rdi, [rcx+38h]
0x180007198  mov     rcx, rdi
0x18000719b  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x1800071a0  lea     rcx, [rbx+8]; lpCriticalSection
0x1800071a4  call    cs:__imp_DeleteCriticalSection
0x1800071aa  mov     dword ptr [rbx], 0
0x1800071b0  jmp     short loc_180007145
0x1800071b2  mov     eax, 80070057h
0x1800071b7  add     rsp, 28h
0x1800071bb  pop     rdi
0x1800071bc  pop     rsi
0x1800071bd  pop     rbp
0x1800071be  pop     rbx
0x1800071bf  retn
```
