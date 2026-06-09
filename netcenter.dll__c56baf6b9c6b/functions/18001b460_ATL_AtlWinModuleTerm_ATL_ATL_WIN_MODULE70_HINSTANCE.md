# ATL::AtlWinModuleTerm(ATL::_ATL_WIN_MODULE70 *,HINSTANCE__ *)

- ea: `0x18001b460`
- end: `0x18001b4f4`
- name: `?AtlWinModuleTerm@ATL@@YAJPEAU_ATL_WIN_MODULE70@1@PEAUHINSTANCE__@@@Z`
- size: `148`
- prototype: `int(struct ATL::_ATL_WIN_MODULE70 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b400`

## callees

- `0x18001b460`
- `0x18001b4fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b4d8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b4d8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b4c1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b4c1`
- `USER32!UnregisterClassA` at `0x18001b4a3`
- `USER32!UnregisterClassA` at `0x18001b4a3`

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
0x18001b460  push    rbx
0x18001b462  push    rbp
0x18001b463  push    rsi
0x18001b464  push    rdi
0x18001b465  sub     rsp, 28h
0x18001b469  mov     rbp, rdx
0x18001b46c  mov     rbx, rcx
0x18001b46f  test    rcx, rcx
0x18001b472  jz      short loc_18001B4E6
0x18001b474  cmp     dword ptr [rcx], 0
0x18001b477  jnz     short loc_18001B47D
0x18001b479  xor     eax, eax
0x18001b47b  jmp     short loc_18001B4EB
0x18001b47d  cmp     dword ptr [rcx], 48h ; 'H'
0x18001b480  jnz     short loc_18001B4E6
0x18001b482  xor     esi, esi
0x18001b484  cmp     [rcx+40h], esi
0x18001b487  jle     short loc_18001B4C8
0x18001b489  test    esi, esi
0x18001b48b  js      short loc_18001B4B2
0x18001b48d  lea     rdi, [rbx+38h]
0x18001b491  cmp     esi, [rdi+8]
0x18001b494  jge     short loc_18001B4B2
0x18001b496  mov     rax, [rdi]
0x18001b499  mov     rdx, rbp; hInstance
0x18001b49c  movsxd  rcx, esi
0x18001b49f  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x18001b4a3  call    cs:__imp_UnregisterClassA
0x18001b4a9  inc     esi
0x18001b4ab  cmp     esi, [rbx+40h]
0x18001b4ae  jl      short loc_18001B489
0x18001b4b0  jmp     short loc_18001B4CC
0x18001b4b2  xor     r9d, r9d; lpArguments
0x18001b4b5  xor     r8d, r8d; nNumberOfArguments
0x18001b4b8  mov     ecx, 0C000008Ch; dwExceptionCode
0x18001b4bd  lea     edx, [r9+1]; dwExceptionFlags
0x18001b4c1  call    cs:__imp_RaiseException
0x18001b4c7  int     3; Trap to Debugger
0x18001b4c8  lea     rdi, [rcx+38h]
0x18001b4cc  mov     rcx, rdi
0x18001b4cf  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18001b4d4  lea     rcx, [rbx+8]; lpCriticalSection
0x18001b4d8  call    cs:__imp_DeleteCriticalSection
0x18001b4de  mov     dword ptr [rbx], 0
0x18001b4e4  jmp     short loc_18001B479
0x18001b4e6  mov     eax, 80070057h
0x18001b4eb  add     rsp, 28h
0x18001b4ef  pop     rdi
0x18001b4f0  pop     rsi
0x18001b4f1  pop     rbp
0x18001b4f2  pop     rbx
0x18001b4f3  retn
```
