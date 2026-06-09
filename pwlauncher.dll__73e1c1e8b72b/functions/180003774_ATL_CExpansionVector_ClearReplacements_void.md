# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180003774`
- end: `0x18000381e`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `170`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x1800026bc`
- `0x180003830`

## callees

- `0x180003774`
- `0x180005028`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800037a1`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800037b4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800037a1`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800037b4`
- `msvcrt!free` at `0x1800037cb`
- `msvcrt!free` at `0x1800037e1`
- `msvcrt!free` at `0x1800037cb`
- `msvcrt!free` at `0x1800037e1`

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
        JUMPOUT(0x18000381DLL);
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
0x180003774  mov     [rsp+arg_0], rbx
0x180003779  mov     [rsp+arg_8], rsi
0x18000377e  push    rdi
0x18000377f  sub     rsp, 20h
0x180003783  mov     eax, [rcx+10h]
0x180003786  mov     rbx, rcx
0x180003789  test    eax, eax
0x18000378b  jle     short loc_1800037C3
0x18000378d  xor     edi, edi
0x18000378f  test    edi, edi
0x180003791  js      short loc_180003808
0x180003793  cmp     edi, eax
0x180003795  jge     short loc_180003808
0x180003797  mov     rcx, [rbx]
0x18000379a  movsxd  rsi, edi
0x18000379d  mov     rcx, [rcx+rsi*8]
0x1800037a1  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800037a7  cmp     edi, [rbx+10h]
0x1800037aa  jge     short loc_180003813
0x1800037ac  mov     rcx, [rbx+8]
0x1800037b0  mov     rcx, [rcx+rsi*8]
0x1800037b4  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800037ba  mov     eax, [rbx+10h]
0x1800037bd  inc     edi
0x1800037bf  cmp     edi, eax
0x1800037c1  jl      short loc_18000378F
0x1800037c3  mov     rcx, [rbx]; Block
0x1800037c6  test    rcx, rcx
0x1800037c9  jz      short loc_1800037D8
0x1800037cb  call    cs:__imp_free
0x1800037d1  mov     qword ptr [rbx], 0
0x1800037d8  mov     rcx, [rbx+8]; Block
0x1800037dc  test    rcx, rcx
0x1800037df  jz      short loc_1800037EF
0x1800037e1  call    cs:__imp_free
0x1800037e7  mov     qword ptr [rbx+8], 0
0x1800037ef  mov     rsi, [rsp+28h+arg_8]
0x1800037f4  xor     eax, eax
0x1800037f6  mov     dword ptr [rbx+10h], 0
0x1800037fd  mov     rbx, [rsp+28h+arg_0]
0x180003802  add     rsp, 20h
0x180003806  pop     rdi
0x180003807  retn
0x180003808  mov     ecx, 0C000008Ch; unsigned int
0x18000380d  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180003812  int     3; Trap to Debugger
0x180003813  mov     ecx, 0C000008Ch; unsigned int
0x180003818  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
