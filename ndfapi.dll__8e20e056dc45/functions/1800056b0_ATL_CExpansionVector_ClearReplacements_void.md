# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x1800056b0`
- end: `0x18000575a`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `170`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180004220`
- `0x180005760`

## callees

- `0x1800056b0`
- `0x180006f84`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800056dd`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800056f0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800056dd`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800056f0`
- `msvcrt!free` at `0x180005707`
- `msvcrt!free` at `0x18000571d`
- `msvcrt!free` at `0x180005707`
- `msvcrt!free` at `0x18000571d`

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
        JUMPOUT(0x180005759LL);
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
0x1800056b0  mov     [rsp+arg_0], rbx
0x1800056b5  mov     [rsp+arg_8], rsi
0x1800056ba  push    rdi
0x1800056bb  sub     rsp, 20h
0x1800056bf  mov     eax, [rcx+10h]
0x1800056c2  mov     rbx, rcx
0x1800056c5  test    eax, eax
0x1800056c7  jle     short loc_1800056FF
0x1800056c9  xor     edi, edi
0x1800056cb  test    edi, edi
0x1800056cd  js      short loc_180005744
0x1800056cf  cmp     edi, eax
0x1800056d1  jge     short loc_180005744
0x1800056d3  mov     rcx, [rbx]
0x1800056d6  movsxd  rsi, edi
0x1800056d9  mov     rcx, [rcx+rsi*8]
0x1800056dd  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800056e3  cmp     edi, [rbx+10h]
0x1800056e6  jge     short loc_18000574F
0x1800056e8  mov     rcx, [rbx+8]
0x1800056ec  mov     rcx, [rcx+rsi*8]
0x1800056f0  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800056f6  mov     eax, [rbx+10h]
0x1800056f9  inc     edi
0x1800056fb  cmp     edi, eax
0x1800056fd  jl      short loc_1800056CB
0x1800056ff  mov     rcx, [rbx]; Block
0x180005702  test    rcx, rcx
0x180005705  jz      short loc_180005714
0x180005707  call    cs:__imp_free
0x18000570d  mov     qword ptr [rbx], 0
0x180005714  mov     rcx, [rbx+8]; Block
0x180005718  test    rcx, rcx
0x18000571b  jz      short loc_18000572B
0x18000571d  call    cs:__imp_free
0x180005723  mov     qword ptr [rbx+8], 0
0x18000572b  mov     rsi, [rsp+28h+arg_8]
0x180005730  xor     eax, eax
0x180005732  mov     dword ptr [rbx+10h], 0
0x180005739  mov     rbx, [rsp+28h+arg_0]
0x18000573e  add     rsp, 20h
0x180005742  pop     rdi
0x180005743  retn
0x180005744  mov     ecx, 0C000008Ch; unsigned int
0x180005749  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x18000574e  int     3; Trap to Debugger
0x18000574f  mov     ecx, 0C000008Ch; unsigned int
0x180005754  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
