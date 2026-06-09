# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180004070`
- end: `0x18000411a`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `170`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180002c28`
- `0x180004120`

## callees

- `0x180004070`
- `0x180005950`

## import_xrefs

- `msvcrt!free` at `0x1800040c7`
- `msvcrt!free` at `0x1800040dd`
- `msvcrt!free` at `0x1800040c7`
- `msvcrt!free` at `0x1800040dd`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000409d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800040b0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000409d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800040b0`

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
        __debugbreak();
      }
      operator delete[](*(void **)(*(_QWORD *)this + 8LL * i));
      if ( i >= *((_DWORD *)this + 4) )
      {
        ATL::_AtlRaiseException(0xC000008C, v5);
        JUMPOUT(0x180004119LL);
      }
      operator delete[](*(void **)(*((_QWORD *)this + 1) + 8LL * i));
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
0x180004070  mov     [rsp+arg_0], rbx
0x180004075  mov     [rsp+arg_8], rsi
0x18000407a  push    rdi
0x18000407b  sub     rsp, 20h
0x18000407f  mov     eax, [rcx+10h]
0x180004082  mov     rbx, rcx
0x180004085  test    eax, eax
0x180004087  jle     short loc_1800040BF
0x180004089  xor     edi, edi
0x18000408b  test    edi, edi
0x18000408d  js      short loc_180004104
0x18000408f  cmp     edi, eax
0x180004091  jge     short loc_180004104
0x180004093  mov     rcx, [rbx]
0x180004096  movsxd  rsi, edi
0x180004099  mov     rcx, [rcx+rsi*8]
0x18000409d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800040a3  cmp     edi, [rbx+10h]
0x1800040a6  jge     short loc_18000410F
0x1800040a8  mov     rcx, [rbx+8]
0x1800040ac  mov     rcx, [rcx+rsi*8]
0x1800040b0  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800040b6  mov     eax, [rbx+10h]
0x1800040b9  inc     edi
0x1800040bb  cmp     edi, eax
0x1800040bd  jl      short loc_18000408B
0x1800040bf  mov     rcx, [rbx]; Block
0x1800040c2  test    rcx, rcx
0x1800040c5  jz      short loc_1800040D4
0x1800040c7  call    cs:__imp_free
0x1800040cd  mov     qword ptr [rbx], 0
0x1800040d4  mov     rcx, [rbx+8]; Block
0x1800040d8  test    rcx, rcx
0x1800040db  jz      short loc_1800040EB
0x1800040dd  call    cs:__imp_free
0x1800040e3  mov     qword ptr [rbx+8], 0
0x1800040eb  mov     rsi, [rsp+28h+arg_8]
0x1800040f0  xor     eax, eax
0x1800040f2  mov     dword ptr [rbx+10h], 0
0x1800040f9  mov     rbx, [rsp+28h+arg_0]
0x1800040fe  add     rsp, 20h
0x180004102  pop     rdi
0x180004103  retn
0x180004104  mov     ecx, 0C000008Ch; unsigned int
0x180004109  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x18000410e  int     3; Trap to Debugger
0x18000410f  mov     ecx, 0C000008Ch; unsigned int
0x180004114  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
