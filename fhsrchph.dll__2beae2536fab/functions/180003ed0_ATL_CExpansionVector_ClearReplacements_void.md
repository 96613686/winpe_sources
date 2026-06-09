# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180003ed0`
- end: `0x180003f7a`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `170`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180003130`
- `0x180003f80`

## callees

- `0x180002964`
- `0x180003ed0`

## import_xrefs

- `msvcrt!free` at `0x180003f27`
- `msvcrt!free` at `0x180003f3d`
- `msvcrt!free` at `0x180003f27`
- `msvcrt!free` at `0x180003f3d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003efd`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003f10`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003efd`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003f10`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::ClearReplacements(ATL::CExpansionVector *this)
{
  int v1; // eax
  int i; // edi
  void *v4; // rcx
  __int64 result; // rax

  v1 = *((_DWORD *)this + 4);
  if ( v1 > 0 )
  {
    for ( i = 0; i < v1; ++i )
    {
      if ( i < 0 || i >= v1 )
      {
        ATL::_AtlRaiseException(0xC000008C);
        __debugbreak();
      }
      operator delete[](*(void **)(*(_QWORD *)this + 8LL * i));
      if ( i >= *((_DWORD *)this + 4) )
      {
        ATL::_AtlRaiseException(0xC000008C);
        JUMPOUT(0x180003F79LL);
      }
      operator delete[](*(void **)(*((_QWORD *)this + 1) + 8LL * i));
      v1 = *((_DWORD *)this + 4);
    }
  }
  if ( *(_QWORD *)this )
  {
    free(*(void **)this);
    *(_QWORD *)this = 0;
  }
  v4 = (void *)*((_QWORD *)this + 1);
  if ( v4 )
  {
    free(v4);
    *((_QWORD *)this + 1) = 0;
  }
  result = 0;
  *((_DWORD *)this + 4) = 0;
  return result;
}

```

## disassembly

```asm
0x180003ed0  mov     [rsp+arg_0], rbx
0x180003ed5  mov     [rsp+arg_8], rsi
0x180003eda  push    rdi
0x180003edb  sub     rsp, 20h
0x180003edf  mov     eax, [rcx+10h]
0x180003ee2  mov     rbx, rcx
0x180003ee5  test    eax, eax
0x180003ee7  jle     short loc_180003F1F
0x180003ee9  xor     edi, edi
0x180003eeb  test    edi, edi
0x180003eed  js      short loc_180003F64
0x180003eef  cmp     edi, eax
0x180003ef1  jge     short loc_180003F64
0x180003ef3  mov     rcx, [rbx]
0x180003ef6  movsxd  rsi, edi
0x180003ef9  mov     rcx, [rcx+rsi*8]
0x180003efd  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180003f03  cmp     edi, [rbx+10h]
0x180003f06  jge     short loc_180003F6F
0x180003f08  mov     rcx, [rbx+8]
0x180003f0c  mov     rcx, [rcx+rsi*8]
0x180003f10  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180003f16  mov     eax, [rbx+10h]
0x180003f19  inc     edi
0x180003f1b  cmp     edi, eax
0x180003f1d  jl      short loc_180003EEB
0x180003f1f  mov     rcx, [rbx]; Block
0x180003f22  test    rcx, rcx
0x180003f25  jz      short loc_180003F34
0x180003f27  call    cs:__imp_free
0x180003f2d  mov     qword ptr [rbx], 0
0x180003f34  mov     rcx, [rbx+8]; Block
0x180003f38  test    rcx, rcx
0x180003f3b  jz      short loc_180003F4B
0x180003f3d  call    cs:__imp_free
0x180003f43  mov     qword ptr [rbx+8], 0
0x180003f4b  mov     rsi, [rsp+28h+arg_8]
0x180003f50  xor     eax, eax
0x180003f52  mov     dword ptr [rbx+10h], 0
0x180003f59  mov     rbx, [rsp+28h+arg_0]
0x180003f5e  add     rsp, 20h
0x180003f62  pop     rdi
0x180003f63  retn
0x180003f64  mov     ecx, 0C000008Ch; unsigned int
0x180003f69  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180003f6e  int     3; Trap to Debugger
0x180003f6f  mov     ecx, 0C000008Ch; unsigned int
0x180003f74  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
