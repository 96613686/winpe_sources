# ATL::AtlWinModuleTerm(ATL::_ATL_WIN_MODULE70 *,HINSTANCE__ *)

- ea: `0x18000ea98`
- end: `0x18000eb2c`
- name: `?AtlWinModuleTerm@ATL@@YAJPEAU_ATL_WIN_MODULE70@1@PEAUHINSTANCE__@@@Z`
- size: `148`
- prototype: `int(struct ATL::_ATL_WIN_MODULE70 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ea6c`

## callees

- `0x18000e3dc`
- `0x18000ea98`

## import_xrefs

- `USER32!UnregisterClassW` at `0x18000eadb`
- `USER32!UnregisterClassW` at `0x18000eadb`
- `KERNEL32!DeleteCriticalSection` at `0x18000eb10`
- `KERNEL32!DeleteCriticalSection` at `0x18000eb10`
- `KERNEL32!RaiseException` at `0x18000eaf9`
- `KERNEL32!RaiseException` at `0x18000eaf9`

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
0x18000ea98  push    rbx
0x18000ea9a  push    rbp
0x18000ea9b  push    rsi
0x18000ea9c  push    rdi
0x18000ea9d  sub     rsp, 28h
0x18000eaa1  mov     rbp, rdx
0x18000eaa4  mov     rbx, rcx
0x18000eaa7  test    rcx, rcx
0x18000eaaa  jz      short loc_18000EB1E
0x18000eaac  cmp     dword ptr [rcx], 0
0x18000eaaf  jnz     short loc_18000EAB5
0x18000eab1  xor     eax, eax
0x18000eab3  jmp     short loc_18000EB23
0x18000eab5  cmp     dword ptr [rcx], 48h ; 'H'
0x18000eab8  jnz     short loc_18000EB1E
0x18000eaba  xor     esi, esi
0x18000eabc  cmp     [rcx+40h], esi
0x18000eabf  jle     short loc_18000EB00
0x18000eac1  test    esi, esi
0x18000eac3  js      short loc_18000EAEA
0x18000eac5  lea     rdi, [rbx+38h]
0x18000eac9  cmp     esi, [rdi+8]
0x18000eacc  jge     short loc_18000EAEA
0x18000eace  mov     rax, [rdi]
0x18000ead1  mov     rdx, rbp; hInstance
0x18000ead4  movsxd  rcx, esi
0x18000ead7  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x18000eadb  call    cs:__imp_UnregisterClassW
0x18000eae1  inc     esi
0x18000eae3  cmp     esi, [rbx+40h]
0x18000eae6  jl      short loc_18000EAC1
0x18000eae8  jmp     short loc_18000EB04
0x18000eaea  xor     r9d, r9d; lpArguments
0x18000eaed  xor     r8d, r8d; nNumberOfArguments
0x18000eaf0  mov     ecx, 0C000008Ch; dwExceptionCode
0x18000eaf5  lea     edx, [r9+1]; dwExceptionFlags
0x18000eaf9  call    cs:__imp_RaiseException
0x18000eaff  int     3; Trap to Debugger
0x18000eb00  lea     rdi, [rcx+38h]
0x18000eb04  mov     rcx, rdi
0x18000eb07  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18000eb0c  lea     rcx, [rbx+8]; lpCriticalSection
0x18000eb10  call    cs:__imp_DeleteCriticalSection
0x18000eb16  mov     dword ptr [rbx], 0
0x18000eb1c  jmp     short loc_18000EAB1
0x18000eb1e  mov     eax, 80070057h
0x18000eb23  add     rsp, 28h
0x18000eb27  pop     rdi
0x18000eb28  pop     rsi
0x18000eb29  pop     rbp
0x18000eb2a  pop     rbx
0x18000eb2b  retn
```
