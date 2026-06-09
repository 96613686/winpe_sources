# ATL::AtlWinModuleTerm(ATL::_ATL_WIN_MODULE70 *,HINSTANCE__ *)

- ea: `0x18000f978`
- end: `0x18000fa0c`
- name: `?AtlWinModuleTerm@ATL@@YAJPEAU_ATL_WIN_MODULE70@1@PEAUHINSTANCE__@@@Z`
- size: `148`
- prototype: `int(struct ATL::_ATL_WIN_MODULE70 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f918`

## callees

- `0x18000f978`
- `0x18000fa14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f9f0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f9f0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f9d9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f9d9`
- `USER32!UnregisterClassA` at `0x18000f9bb`
- `USER32!UnregisterClassA` at `0x18000f9bb`

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
0x18000f978  push    rbx
0x18000f97a  push    rbp
0x18000f97b  push    rsi
0x18000f97c  push    rdi
0x18000f97d  sub     rsp, 28h
0x18000f981  mov     rbp, rdx
0x18000f984  mov     rbx, rcx
0x18000f987  test    rcx, rcx
0x18000f98a  jz      short loc_18000F9FE
0x18000f98c  cmp     dword ptr [rcx], 0
0x18000f98f  jnz     short loc_18000F995
0x18000f991  xor     eax, eax
0x18000f993  jmp     short loc_18000FA03
0x18000f995  cmp     dword ptr [rcx], 48h ; 'H'
0x18000f998  jnz     short loc_18000F9FE
0x18000f99a  xor     esi, esi
0x18000f99c  cmp     [rcx+40h], esi
0x18000f99f  jle     short loc_18000F9E0
0x18000f9a1  test    esi, esi
0x18000f9a3  js      short loc_18000F9CA
0x18000f9a5  lea     rdi, [rbx+38h]
0x18000f9a9  cmp     esi, [rdi+8]
0x18000f9ac  jge     short loc_18000F9CA
0x18000f9ae  mov     rax, [rdi]
0x18000f9b1  mov     rdx, rbp; hInstance
0x18000f9b4  movsxd  rcx, esi
0x18000f9b7  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x18000f9bb  call    cs:__imp_UnregisterClassA
0x18000f9c1  inc     esi
0x18000f9c3  cmp     esi, [rbx+40h]
0x18000f9c6  jl      short loc_18000F9A1
0x18000f9c8  jmp     short loc_18000F9E4
0x18000f9ca  xor     r9d, r9d; lpArguments
0x18000f9cd  xor     r8d, r8d; nNumberOfArguments
0x18000f9d0  mov     ecx, 0C000008Ch; dwExceptionCode
0x18000f9d5  lea     edx, [r9+1]; dwExceptionFlags
0x18000f9d9  call    cs:__imp_RaiseException
0x18000f9df  int     3; Trap to Debugger
0x18000f9e0  lea     rdi, [rcx+38h]
0x18000f9e4  mov     rcx, rdi
0x18000f9e7  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18000f9ec  lea     rcx, [rbx+8]; lpCriticalSection
0x18000f9f0  call    cs:__imp_DeleteCriticalSection
0x18000f9f6  mov     dword ptr [rbx], 0
0x18000f9fc  jmp     short loc_18000F991
0x18000f9fe  mov     eax, 80070057h
0x18000fa03  add     rsp, 28h
0x18000fa07  pop     rdi
0x18000fa08  pop     rsi
0x18000fa09  pop     rbp
0x18000fa0a  pop     rbx
0x18000fa0b  retn
```
