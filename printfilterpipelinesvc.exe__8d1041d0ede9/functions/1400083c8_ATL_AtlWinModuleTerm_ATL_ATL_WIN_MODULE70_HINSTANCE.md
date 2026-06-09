# ATL::AtlWinModuleTerm(ATL::_ATL_WIN_MODULE70 *,HINSTANCE__ *)

- ea: `0x1400083c8`
- end: `0x14000845c`
- name: `?AtlWinModuleTerm@ATL@@YAJPEAU_ATL_WIN_MODULE70@1@PEAUHINSTANCE__@@@Z`
- size: `148`
- prototype: `int(struct ATL::_ATL_WIN_MODULE70 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140008368`

## callees

- `0x1400083c8`
- `0x140008464`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140008440`
- `KERNEL32!DeleteCriticalSection` at `0x140008440`
- `KERNEL32!RaiseException` at `0x140008429`
- `KERNEL32!RaiseException` at `0x140008429`
- `USER32!UnregisterClassA` at `0x14000840b`
- `USER32!UnregisterClassA` at `0x14000840b`

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
0x1400083c8  push    rbx
0x1400083ca  push    rbp
0x1400083cb  push    rsi
0x1400083cc  push    rdi
0x1400083cd  sub     rsp, 28h
0x1400083d1  mov     rbp, rdx
0x1400083d4  mov     rbx, rcx
0x1400083d7  test    rcx, rcx
0x1400083da  jz      short loc_14000844E
0x1400083dc  cmp     dword ptr [rcx], 0
0x1400083df  jnz     short loc_1400083E5
0x1400083e1  xor     eax, eax
0x1400083e3  jmp     short loc_140008453
0x1400083e5  cmp     dword ptr [rcx], 48h ; 'H'
0x1400083e8  jnz     short loc_14000844E
0x1400083ea  xor     esi, esi
0x1400083ec  cmp     [rcx+40h], esi
0x1400083ef  jle     short loc_140008430
0x1400083f1  test    esi, esi
0x1400083f3  js      short loc_14000841A
0x1400083f5  lea     rdi, [rbx+38h]
0x1400083f9  cmp     esi, [rdi+8]
0x1400083fc  jge     short loc_14000841A
0x1400083fe  mov     rax, [rdi]
0x140008401  mov     rdx, rbp; hInstance
0x140008404  movsxd  rcx, esi
0x140008407  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x14000840b  call    cs:__imp_UnregisterClassA
0x140008411  inc     esi
0x140008413  cmp     esi, [rbx+40h]
0x140008416  jl      short loc_1400083F1
0x140008418  jmp     short loc_140008434
0x14000841a  xor     r9d, r9d; lpArguments
0x14000841d  xor     r8d, r8d; nNumberOfArguments
0x140008420  mov     ecx, 0C000008Ch; dwExceptionCode
0x140008425  lea     edx, [r9+1]; dwExceptionFlags
0x140008429  call    cs:__imp_RaiseException
0x14000842f  int     3; Trap to Debugger
0x140008430  lea     rdi, [rcx+38h]
0x140008434  mov     rcx, rdi
0x140008437  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x14000843c  lea     rcx, [rbx+8]; lpCriticalSection
0x140008440  call    cs:__imp_DeleteCriticalSection
0x140008446  mov     dword ptr [rbx], 0
0x14000844c  jmp     short loc_1400083E1
0x14000844e  mov     eax, 80070057h
0x140008453  add     rsp, 28h
0x140008457  pop     rdi
0x140008458  pop     rsi
0x140008459  pop     rbp
0x14000845a  pop     rbx
0x14000845b  retn
```
