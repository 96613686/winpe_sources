# ATL::AtlWinModuleTerm(ATL::_ATL_WIN_MODULE70 *,HINSTANCE__ *)

- ea: `0x18003a710`
- end: `0x18003a7a4`
- name: `?AtlWinModuleTerm@ATL@@YAJPEAU_ATL_WIN_MODULE70@1@PEAUHINSTANCE__@@@Z`
- size: `148`
- prototype: `__int64 __fastcall(struct ATL::_ATL_WIN_MODULE70 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18003a678`

## callees

- `0x18003a710`
- `0x18003a874`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003a788`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003a788`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003a771`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003a771`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassA` at `0x18003a753`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassA` at `0x18003a753`

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
0x18003a710  push    rbx
0x18003a712  push    rbp
0x18003a713  push    rsi
0x18003a714  push    rdi
0x18003a715  sub     rsp, 28h
0x18003a719  mov     rbp, rdx
0x18003a71c  mov     rbx, rcx
0x18003a71f  test    rcx, rcx
0x18003a722  jz      short loc_18003A796
0x18003a724  cmp     dword ptr [rcx], 0
0x18003a727  jnz     short loc_18003A72D
0x18003a729  xor     eax, eax
0x18003a72b  jmp     short loc_18003A79B
0x18003a72d  cmp     dword ptr [rcx], 48h ; 'H'
0x18003a730  jnz     short loc_18003A796
0x18003a732  xor     esi, esi
0x18003a734  cmp     [rcx+40h], esi
0x18003a737  jle     short loc_18003A778
0x18003a739  test    esi, esi
0x18003a73b  js      short loc_18003A762
0x18003a73d  lea     rdi, [rbx+38h]
0x18003a741  cmp     esi, [rdi+8]
0x18003a744  jge     short loc_18003A762
0x18003a746  mov     rax, [rdi]
0x18003a749  mov     rdx, rbp; hInstance
0x18003a74c  movsxd  rcx, esi
0x18003a74f  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x18003a753  call    cs:__imp_UnregisterClassA
0x18003a759  inc     esi
0x18003a75b  cmp     esi, [rbx+40h]
0x18003a75e  jl      short loc_18003A739
0x18003a760  jmp     short loc_18003A77C
0x18003a762  xor     r9d, r9d; lpArguments
0x18003a765  xor     r8d, r8d; nNumberOfArguments
0x18003a768  mov     ecx, 0C000008Ch; dwExceptionCode
0x18003a76d  lea     edx, [r9+1]; dwExceptionFlags
0x18003a771  call    cs:__imp_RaiseException
0x18003a777  int     3; Trap to Debugger
0x18003a778  lea     rdi, [rcx+38h]
0x18003a77c  mov     rcx, rdi
0x18003a77f  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18003a784  lea     rcx, [rbx+8]; lpCriticalSection
0x18003a788  call    cs:__imp_DeleteCriticalSection
0x18003a78e  mov     dword ptr [rbx], 0
0x18003a794  jmp     short loc_18003A729
0x18003a796  mov     eax, 80070057h
0x18003a79b  add     rsp, 28h
0x18003a79f  pop     rdi
0x18003a7a0  pop     rsi
0x18003a7a1  pop     rbp
0x18003a7a2  pop     rbx
0x18003a7a3  retn
```
