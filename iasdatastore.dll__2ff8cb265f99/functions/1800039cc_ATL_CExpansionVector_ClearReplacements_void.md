# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x1800039cc`
- end: `0x180003a7a`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `174`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002254`
- `0x180003a80`

## callees

- `0x1800039cc`
- `0x18000619c`

## import_xrefs

- `msvcrt!free` at `0x1800039fd`
- `msvcrt!free` at `0x180003a10`
- `msvcrt!free` at `0x180003a27`
- `msvcrt!free` at `0x180003a3d`
- `msvcrt!free` at `0x1800039fd`
- `msvcrt!free` at `0x180003a10`
- `msvcrt!free` at `0x180003a27`
- `msvcrt!free` at `0x180003a3d`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::ClearReplacements(ATL::CExpansionVector *this, unsigned int a2)
{
  int v2; // eax
  int i; // edi
  unsigned int v5; // edx
  void *v6; // rcx
  __int64 result; // rax

  v2 = *((_DWORD *)this + 4);
  if ( v2 > 0 )
  {
    for ( i = 0; i < v2; ++i )
    {
      if ( i < 0 || i >= v2 )
      {
        ATL::_AtlRaiseException(0xC000008C, a2);
        JUMPOUT(0x180003A79LL);
      }
      free(*(void **)(*(_QWORD *)this + 8LL * i));
      if ( i >= *((_DWORD *)this + 4) )
      {
        ATL::_AtlRaiseException(0xC000008C, v5);
        __debugbreak();
      }
      free(*(void **)(*((_QWORD *)this + 1) + 8LL * i));
      v2 = *((_DWORD *)this + 4);
    }
  }
  if ( *(_QWORD *)this )
  {
    free(*(void **)this);
    *(_QWORD *)this = 0;
  }
  v6 = (void *)*((_QWORD *)this + 1);
  if ( v6 )
  {
    free(v6);
    *((_QWORD *)this + 1) = 0;
  }
  result = 0;
  *((_DWORD *)this + 4) = 0;
  return result;
}

```

## disassembly

```asm
0x1800039cc  mov     [rsp+arg_0], rbx
0x1800039d1  mov     [rsp+arg_8], rsi
0x1800039d6  push    rdi
0x1800039d7  sub     rsp, 20h
0x1800039db  mov     eax, [rcx+10h]
0x1800039de  mov     rbx, rcx
0x1800039e1  test    eax, eax
0x1800039e3  jle     short loc_180003A1F
0x1800039e5  xor     edi, edi
0x1800039e7  test    edi, edi
0x1800039e9  js      loc_180003A6F
0x1800039ef  cmp     edi, eax
0x1800039f1  jge     short loc_180003A6F
0x1800039f3  mov     rcx, [rbx]
0x1800039f6  movsxd  rsi, edi
0x1800039f9  mov     rcx, [rcx+rsi*8]; Block
0x1800039fd  call    cs:__imp_free
0x180003a03  cmp     edi, [rbx+10h]
0x180003a06  jge     short loc_180003A64
0x180003a08  mov     rcx, [rbx+8]
0x180003a0c  mov     rcx, [rcx+rsi*8]; Block
0x180003a10  call    cs:__imp_free
0x180003a16  mov     eax, [rbx+10h]
0x180003a19  inc     edi
0x180003a1b  cmp     edi, eax
0x180003a1d  jl      short loc_1800039E7
0x180003a1f  mov     rcx, [rbx]; Block
0x180003a22  test    rcx, rcx
0x180003a25  jz      short loc_180003A34
0x180003a27  call    cs:__imp_free
0x180003a2d  mov     qword ptr [rbx], 0
0x180003a34  mov     rcx, [rbx+8]; Block
0x180003a38  test    rcx, rcx
0x180003a3b  jz      short loc_180003A4B
0x180003a3d  call    cs:__imp_free
0x180003a43  mov     qword ptr [rbx+8], 0
0x180003a4b  mov     rsi, [rsp+28h+arg_8]
0x180003a50  xor     eax, eax
0x180003a52  mov     dword ptr [rbx+10h], 0
0x180003a59  mov     rbx, [rsp+28h+arg_0]
0x180003a5e  add     rsp, 20h
0x180003a62  pop     rdi
0x180003a63  retn
0x180003a64  mov     ecx, 0C000008Ch; unsigned int
0x180003a69  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180003a6e  int     3; Trap to Debugger
0x180003a6f  mov     ecx, 0C000008Ch; unsigned int
0x180003a74  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
