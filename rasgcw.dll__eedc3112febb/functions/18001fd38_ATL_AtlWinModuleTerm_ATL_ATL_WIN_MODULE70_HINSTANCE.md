# ATL::AtlWinModuleTerm(ATL::_ATL_WIN_MODULE70 *,HINSTANCE__ *)

- ea: `0x18001fd38`
- end: `0x18001fdcc`
- name: `?AtlWinModuleTerm@ATL@@YAJPEAU_ATL_WIN_MODULE70@1@PEAUHINSTANCE__@@@Z`
- size: `148`
- prototype: `__int64 __fastcall(struct ATL::_ATL_WIN_MODULE70 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001fcd8`

## callees

- `0x18001fd38`
- `0x18001fdd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001fdb0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001fdb0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001fd99`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001fd99`
- `USER32!UnregisterClassA` at `0x18001fd7b`
- `USER32!UnregisterClassA` at `0x18001fd7b`

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
0x18001fd38  push    rbx
0x18001fd3a  push    rbp
0x18001fd3b  push    rsi
0x18001fd3c  push    rdi
0x18001fd3d  sub     rsp, 28h
0x18001fd41  mov     rbp, rdx
0x18001fd44  mov     rbx, rcx
0x18001fd47  test    rcx, rcx
0x18001fd4a  jz      short loc_18001FDBE
0x18001fd4c  cmp     dword ptr [rcx], 0
0x18001fd4f  jnz     short loc_18001FD55
0x18001fd51  xor     eax, eax
0x18001fd53  jmp     short loc_18001FDC3
0x18001fd55  cmp     dword ptr [rcx], 48h ; 'H'
0x18001fd58  jnz     short loc_18001FDBE
0x18001fd5a  xor     esi, esi
0x18001fd5c  cmp     [rcx+40h], esi
0x18001fd5f  jle     short loc_18001FDA0
0x18001fd61  test    esi, esi
0x18001fd63  js      short loc_18001FD8A
0x18001fd65  lea     rdi, [rbx+38h]
0x18001fd69  cmp     esi, [rdi+8]
0x18001fd6c  jge     short loc_18001FD8A
0x18001fd6e  mov     rax, [rdi]
0x18001fd71  mov     rdx, rbp; hInstance
0x18001fd74  movsxd  rcx, esi
0x18001fd77  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x18001fd7b  call    cs:__imp_UnregisterClassA
0x18001fd81  inc     esi
0x18001fd83  cmp     esi, [rbx+40h]
0x18001fd86  jl      short loc_18001FD61
0x18001fd88  jmp     short loc_18001FDA4
0x18001fd8a  xor     r9d, r9d; lpArguments
0x18001fd8d  xor     r8d, r8d; nNumberOfArguments
0x18001fd90  mov     ecx, 0C000008Ch; dwExceptionCode
0x18001fd95  lea     edx, [r9+1]; dwExceptionFlags
0x18001fd99  call    cs:__imp_RaiseException
0x18001fd9f  int     3; Trap to Debugger
0x18001fda0  lea     rdi, [rcx+38h]
0x18001fda4  mov     rcx, rdi
0x18001fda7  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18001fdac  lea     rcx, [rbx+8]; lpCriticalSection
0x18001fdb0  call    cs:__imp_DeleteCriticalSection
0x18001fdb6  mov     dword ptr [rbx], 0
0x18001fdbc  jmp     short loc_18001FD51
0x18001fdbe  mov     eax, 80070057h
0x18001fdc3  add     rsp, 28h
0x18001fdc7  pop     rdi
0x18001fdc8  pop     rsi
0x18001fdc9  pop     rbp
0x18001fdca  pop     rbx
0x18001fdcb  retn
```
