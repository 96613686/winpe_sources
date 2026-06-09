# ATL::AtlWinModuleTerm(ATL::_ATL_WIN_MODULE70 *,HINSTANCE__ *)

- ea: `0x180014468`
- end: `0x1800144fc`
- name: `?AtlWinModuleTerm@ATL@@YAJPEAU_ATL_WIN_MODULE70@1@PEAUHINSTANCE__@@@Z`
- size: `148`
- prototype: `__int64 __fastcall(struct ATL::_ATL_WIN_MODULE70 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800143d0`

## callees

- `0x180014468`
- `0x180014580`

## import_xrefs

- `USER32!UnregisterClassA` at `0x1800144ab`
- `USER32!UnregisterClassA` at `0x1800144ab`
- `KERNEL32!RaiseException` at `0x1800144c9`
- `KERNEL32!RaiseException` at `0x1800144c9`
- `KERNEL32!DeleteCriticalSection` at `0x1800144e0`
- `KERNEL32!DeleteCriticalSection` at `0x1800144e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180014468  push    rbx
0x18001446a  push    rbp
0x18001446b  push    rsi
0x18001446c  push    rdi
0x18001446d  sub     rsp, 28h
0x180014471  mov     rbp, rdx
0x180014474  mov     rbx, rcx
0x180014477  test    rcx, rcx
0x18001447a  jz      short loc_1800144EE
0x18001447c  cmp     dword ptr [rcx], 0
0x18001447f  jnz     short loc_180014485
0x180014481  xor     eax, eax
0x180014483  jmp     short loc_1800144F3
0x180014485  cmp     dword ptr [rcx], 48h ; 'H'
0x180014488  jnz     short loc_1800144EE
0x18001448a  xor     esi, esi
0x18001448c  cmp     [rcx+40h], esi
0x18001448f  jle     short loc_1800144D0
0x180014491  test    esi, esi
0x180014493  js      short loc_1800144BA
0x180014495  lea     rdi, [rbx+38h]
0x180014499  cmp     esi, [rdi+8]
0x18001449c  jge     short loc_1800144BA
0x18001449e  mov     rax, [rdi]
0x1800144a1  mov     rdx, rbp; hInstance
0x1800144a4  movsxd  rcx, esi
0x1800144a7  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x1800144ab  call    cs:__imp_UnregisterClassA
0x1800144b1  inc     esi
0x1800144b3  cmp     esi, [rbx+40h]
0x1800144b6  jl      short loc_180014491
0x1800144b8  jmp     short loc_1800144D4
0x1800144ba  xor     r9d, r9d; lpArguments
0x1800144bd  xor     r8d, r8d; nNumberOfArguments
0x1800144c0  mov     ecx, 0C000008Ch; dwExceptionCode
0x1800144c5  lea     edx, [r9+1]; dwExceptionFlags
0x1800144c9  call    cs:__imp_RaiseException
0x1800144cf  int     3; Trap to Debugger
0x1800144d0  lea     rdi, [rcx+38h]
0x1800144d4  mov     rcx, rdi
0x1800144d7  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x1800144dc  lea     rcx, [rbx+8]; lpCriticalSection
0x1800144e0  call    cs:__imp_DeleteCriticalSection
0x1800144e6  mov     dword ptr [rbx], 0
0x1800144ec  jmp     short loc_180014481
0x1800144ee  mov     eax, 80070057h
0x1800144f3  add     rsp, 28h
0x1800144f7  pop     rdi
0x1800144f8  pop     rsi
0x1800144f9  pop     rbp
0x1800144fa  pop     rbx
0x1800144fb  retn
```
