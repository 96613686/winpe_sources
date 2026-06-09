# ATL::AtlWinModuleTerm(ATL::_ATL_WIN_MODULE70 *,HINSTANCE__ *)

- ea: `0x1800079d0`
- end: `0x180007a64`
- name: `?AtlWinModuleTerm@ATL@@YAJPEAU_ATL_WIN_MODULE70@1@PEAUHINSTANCE__@@@Z`
- size: `148`
- prototype: `__int64 __fastcall(struct ATL::_ATL_WIN_MODULE70 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007938`

## callees

- `0x1800079d0`
- `0x180007b0c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180007a48`
- `KERNEL32!DeleteCriticalSection` at `0x180007a48`
- `KERNEL32!RaiseException` at `0x180007a31`
- `KERNEL32!RaiseException` at `0x180007a31`
- `USER32!UnregisterClassA` at `0x180007a13`
- `USER32!UnregisterClassA` at `0x180007a13`

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
0x1800079d0  push    rbx
0x1800079d2  push    rbp
0x1800079d3  push    rsi
0x1800079d4  push    rdi
0x1800079d5  sub     rsp, 28h
0x1800079d9  mov     rbp, rdx
0x1800079dc  mov     rbx, rcx
0x1800079df  test    rcx, rcx
0x1800079e2  jz      short loc_180007A56
0x1800079e4  cmp     dword ptr [rcx], 0
0x1800079e7  jnz     short loc_1800079ED
0x1800079e9  xor     eax, eax
0x1800079eb  jmp     short loc_180007A5B
0x1800079ed  cmp     dword ptr [rcx], 48h ; 'H'
0x1800079f0  jnz     short loc_180007A56
0x1800079f2  xor     esi, esi
0x1800079f4  cmp     [rcx+40h], esi
0x1800079f7  jle     short loc_180007A38
0x1800079f9  test    esi, esi
0x1800079fb  js      short loc_180007A22
0x1800079fd  lea     rdi, [rbx+38h]
0x180007a01  cmp     esi, [rdi+8]
0x180007a04  jge     short loc_180007A22
0x180007a06  mov     rax, [rdi]
0x180007a09  mov     rdx, rbp; hInstance
0x180007a0c  movsxd  rcx, esi
0x180007a0f  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x180007a13  call    cs:__imp_UnregisterClassA
0x180007a19  inc     esi
0x180007a1b  cmp     esi, [rbx+40h]
0x180007a1e  jl      short loc_1800079F9
0x180007a20  jmp     short loc_180007A3C
0x180007a22  xor     r9d, r9d; lpArguments
0x180007a25  xor     r8d, r8d; nNumberOfArguments
0x180007a28  mov     ecx, 0C000008Ch; dwExceptionCode
0x180007a2d  lea     edx, [r9+1]; dwExceptionFlags
0x180007a31  call    cs:__imp_RaiseException
0x180007a37  int     3; Trap to Debugger
0x180007a38  lea     rdi, [rcx+38h]
0x180007a3c  mov     rcx, rdi
0x180007a3f  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x180007a44  lea     rcx, [rbx+8]; lpCriticalSection
0x180007a48  call    cs:__imp_DeleteCriticalSection
0x180007a4e  mov     dword ptr [rbx], 0
0x180007a54  jmp     short loc_1800079E9
0x180007a56  mov     eax, 80070057h
0x180007a5b  add     rsp, 28h
0x180007a5f  pop     rdi
0x180007a60  pop     rsi
0x180007a61  pop     rbp
0x180007a62  pop     rbx
0x180007a63  retn
```
