# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x1800030dc`
- end: `0x180003186`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `170`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800023f8`
- `0x180003190`

## callees

- `0x1800030dc`
- `0x180005328`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180003109`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000311c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003109`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000311c`
- `msvcrt!free` at `0x180003133`
- `msvcrt!free` at `0x180003149`
- `msvcrt!free` at `0x180003133`
- `msvcrt!free` at `0x180003149`

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
        JUMPOUT(0x180003185LL);
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
0x1800030dc  mov     [rsp+arg_0], rbx
0x1800030e1  mov     [rsp+arg_8], rsi
0x1800030e6  push    rdi
0x1800030e7  sub     rsp, 20h
0x1800030eb  mov     eax, [rcx+10h]
0x1800030ee  mov     rbx, rcx
0x1800030f1  test    eax, eax
0x1800030f3  jle     short loc_18000312B
0x1800030f5  xor     edi, edi
0x1800030f7  test    edi, edi
0x1800030f9  js      short loc_180003170
0x1800030fb  cmp     edi, eax
0x1800030fd  jge     short loc_180003170
0x1800030ff  mov     rcx, [rbx]
0x180003102  movsxd  rsi, edi
0x180003105  mov     rcx, [rcx+rsi*8]
0x180003109  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000310f  cmp     edi, [rbx+10h]
0x180003112  jge     short loc_18000317B
0x180003114  mov     rcx, [rbx+8]
0x180003118  mov     rcx, [rcx+rsi*8]
0x18000311c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180003122  mov     eax, [rbx+10h]
0x180003125  inc     edi
0x180003127  cmp     edi, eax
0x180003129  jl      short loc_1800030F7
0x18000312b  mov     rcx, [rbx]; Block
0x18000312e  test    rcx, rcx
0x180003131  jz      short loc_180003140
0x180003133  call    cs:__imp_free
0x180003139  mov     qword ptr [rbx], 0
0x180003140  mov     rcx, [rbx+8]; Block
0x180003144  test    rcx, rcx
0x180003147  jz      short loc_180003157
0x180003149  call    cs:__imp_free
0x18000314f  mov     qword ptr [rbx+8], 0
0x180003157  mov     rsi, [rsp+28h+arg_8]
0x18000315c  xor     eax, eax
0x18000315e  mov     dword ptr [rbx+10h], 0
0x180003165  mov     rbx, [rsp+28h+arg_0]
0x18000316a  add     rsp, 20h
0x18000316e  pop     rdi
0x18000316f  retn
0x180003170  mov     ecx, 0C000008Ch; unsigned int
0x180003175  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x18000317a  int     3; Trap to Debugger
0x18000317b  mov     ecx, 0C000008Ch; unsigned int
0x180003180  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
