# ATL::AtlWinModuleTerm(ATL::_ATL_WIN_MODULE70 *,HINSTANCE__ *)

- ea: `0x14001bd60`
- end: `0x14001bdf4`
- name: `?AtlWinModuleTerm@ATL@@YAJPEAU_ATL_WIN_MODULE70@1@PEAUHINSTANCE__@@@Z`
- size: `148`
- prototype: `int(struct ATL::_ATL_WIN_MODULE70 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001bcc8`

## callees

- `0x14001bd60`
- `0x14001bec4`

## import_xrefs

- `KERNEL32!RaiseException` at `0x14001bdc1`
- `KERNEL32!RaiseException` at `0x14001bdc1`
- `KERNEL32!DeleteCriticalSection` at `0x14001bdd8`
- `KERNEL32!DeleteCriticalSection` at `0x14001bdd8`
- `USER32!UnregisterClassA` at `0x14001bda3`
- `USER32!UnregisterClassA` at `0x14001bda3`

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
0x14001bd60  push    rbx
0x14001bd62  push    rbp
0x14001bd63  push    rsi
0x14001bd64  push    rdi
0x14001bd65  sub     rsp, 28h
0x14001bd69  mov     rbp, rdx
0x14001bd6c  mov     rbx, rcx
0x14001bd6f  test    rcx, rcx
0x14001bd72  jz      short loc_14001BDE6
0x14001bd74  cmp     dword ptr [rcx], 0
0x14001bd77  jnz     short loc_14001BD7D
0x14001bd79  xor     eax, eax
0x14001bd7b  jmp     short loc_14001BDEB
0x14001bd7d  cmp     dword ptr [rcx], 48h ; 'H'
0x14001bd80  jnz     short loc_14001BDE6
0x14001bd82  xor     esi, esi
0x14001bd84  cmp     [rcx+40h], esi
0x14001bd87  jle     short loc_14001BDC8
0x14001bd89  test    esi, esi
0x14001bd8b  js      short loc_14001BDB2
0x14001bd8d  lea     rdi, [rbx+38h]
0x14001bd91  cmp     esi, [rdi+8]
0x14001bd94  jge     short loc_14001BDB2
0x14001bd96  mov     rax, [rdi]
0x14001bd99  mov     rdx, rbp; hInstance
0x14001bd9c  movsxd  rcx, esi
0x14001bd9f  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x14001bda3  call    cs:__imp_UnregisterClassA
0x14001bda9  inc     esi
0x14001bdab  cmp     esi, [rbx+40h]
0x14001bdae  jl      short loc_14001BD89
0x14001bdb0  jmp     short loc_14001BDCC
0x14001bdb2  xor     r9d, r9d; lpArguments
0x14001bdb5  xor     r8d, r8d; nNumberOfArguments
0x14001bdb8  mov     ecx, 0C000008Ch; dwExceptionCode
0x14001bdbd  lea     edx, [r9+1]; dwExceptionFlags
0x14001bdc1  call    cs:__imp_RaiseException
0x14001bdc7  int     3; Trap to Debugger
0x14001bdc8  lea     rdi, [rcx+38h]
0x14001bdcc  mov     rcx, rdi
0x14001bdcf  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x14001bdd4  lea     rcx, [rbx+8]; lpCriticalSection
0x14001bdd8  call    cs:__imp_DeleteCriticalSection
0x14001bdde  mov     dword ptr [rbx], 0
0x14001bde4  jmp     short loc_14001BD79
0x14001bde6  mov     eax, 80070057h
0x14001bdeb  add     rsp, 28h
0x14001bdef  pop     rdi
0x14001bdf0  pop     rsi
0x14001bdf1  pop     rbp
0x14001bdf2  pop     rbx
0x14001bdf3  retn
```
