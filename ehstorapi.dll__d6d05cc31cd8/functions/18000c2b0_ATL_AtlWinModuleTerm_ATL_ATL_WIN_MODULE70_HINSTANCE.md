# ATL::AtlWinModuleTerm(ATL::_ATL_WIN_MODULE70 *,HINSTANCE__ *)

- ea: `0x18000c2b0`
- end: `0x18000c344`
- name: `?AtlWinModuleTerm@ATL@@YAJPEAU_ATL_WIN_MODULE70@1@PEAUHINSTANCE__@@@Z`
- size: `148`
- prototype: `int(struct ATL::_ATL_WIN_MODULE70 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c250`

## callees

- `0x18000c2b0`
- `0x18000c34c`

## import_xrefs

- `USER32!UnregisterClassA` at `0x18000c2f3`
- `USER32!UnregisterClassA` at `0x18000c2f3`
- `KERNEL32!DeleteCriticalSection` at `0x18000c328`
- `KERNEL32!DeleteCriticalSection` at `0x18000c328`
- `KERNEL32!RaiseException` at `0x18000c311`
- `KERNEL32!RaiseException` at `0x18000c311`

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
0x18000c2b0  push    rbx
0x18000c2b2  push    rbp
0x18000c2b3  push    rsi
0x18000c2b4  push    rdi
0x18000c2b5  sub     rsp, 28h
0x18000c2b9  mov     rbp, rdx
0x18000c2bc  mov     rbx, rcx
0x18000c2bf  test    rcx, rcx
0x18000c2c2  jz      short loc_18000C336
0x18000c2c4  cmp     dword ptr [rcx], 0
0x18000c2c7  jnz     short loc_18000C2CD
0x18000c2c9  xor     eax, eax
0x18000c2cb  jmp     short loc_18000C33B
0x18000c2cd  cmp     dword ptr [rcx], 48h ; 'H'
0x18000c2d0  jnz     short loc_18000C336
0x18000c2d2  xor     esi, esi
0x18000c2d4  cmp     [rcx+40h], esi
0x18000c2d7  jle     short loc_18000C318
0x18000c2d9  test    esi, esi
0x18000c2db  js      short loc_18000C302
0x18000c2dd  lea     rdi, [rbx+38h]
0x18000c2e1  cmp     esi, [rdi+8]
0x18000c2e4  jge     short loc_18000C302
0x18000c2e6  mov     rax, [rdi]
0x18000c2e9  mov     rdx, rbp; hInstance
0x18000c2ec  movsxd  rcx, esi
0x18000c2ef  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x18000c2f3  call    cs:__imp_UnregisterClassA
0x18000c2f9  inc     esi
0x18000c2fb  cmp     esi, [rbx+40h]
0x18000c2fe  jl      short loc_18000C2D9
0x18000c300  jmp     short loc_18000C31C
0x18000c302  xor     r9d, r9d; lpArguments
0x18000c305  xor     r8d, r8d; nNumberOfArguments
0x18000c308  mov     ecx, 0C000008Ch; dwExceptionCode
0x18000c30d  lea     edx, [r9+1]; dwExceptionFlags
0x18000c311  call    cs:__imp_RaiseException
0x18000c317  int     3; Trap to Debugger
0x18000c318  lea     rdi, [rcx+38h]
0x18000c31c  mov     rcx, rdi
0x18000c31f  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18000c324  lea     rcx, [rbx+8]; lpCriticalSection
0x18000c328  call    cs:__imp_DeleteCriticalSection
0x18000c32e  mov     dword ptr [rbx], 0
0x18000c334  jmp     short loc_18000C2C9
0x18000c336  mov     eax, 80070057h
0x18000c33b  add     rsp, 28h
0x18000c33f  pop     rdi
0x18000c340  pop     rsi
0x18000c341  pop     rbp
0x18000c342  pop     rbx
0x18000c343  retn
```
