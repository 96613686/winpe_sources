# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x140002cc0`
- end: `0x140002d68`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `168`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140002174`
- `0x140002d70`

## callees

- `0x1400011ec`
- `0x140002cc0`
- `0x14000522c`

## import_xrefs

- `msvcrt!free` at `0x140002d15`
- `msvcrt!free` at `0x140002d2b`
- `msvcrt!free` at `0x140002d15`
- `msvcrt!free` at `0x140002d2b`

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
        JUMPOUT(0x140002D67LL);
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
0x140002cc0  mov     [rsp+arg_0], rbx
0x140002cc5  mov     [rsp+arg_8], rsi
0x140002cca  push    rdi
0x140002ccb  sub     rsp, 20h
0x140002ccf  mov     eax, [rcx+10h]
0x140002cd2  mov     rbx, rcx
0x140002cd5  test    eax, eax
0x140002cd7  jle     short loc_140002D0D
0x140002cd9  xor     edi, edi
0x140002cdb  test    edi, edi
0x140002cdd  js      short loc_140002D52
0x140002cdf  cmp     edi, eax
0x140002ce1  jge     short loc_140002D52
0x140002ce3  mov     rcx, [rbx]
0x140002ce6  movsxd  rsi, edi
0x140002ce9  mov     rcx, [rcx+rsi*8]; Block
0x140002ced  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x140002cf2  cmp     edi, [rbx+10h]
0x140002cf5  jge     short loc_140002D5D
0x140002cf7  mov     rcx, [rbx+8]
0x140002cfb  mov     rcx, [rcx+rsi*8]; Block
0x140002cff  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x140002d04  mov     eax, [rbx+10h]
0x140002d07  inc     edi
0x140002d09  cmp     edi, eax
0x140002d0b  jl      short loc_140002CDB
0x140002d0d  mov     rcx, [rbx]; Block
0x140002d10  test    rcx, rcx
0x140002d13  jz      short loc_140002D22
0x140002d15  call    cs:__imp_free
0x140002d1b  mov     qword ptr [rbx], 0
0x140002d22  mov     rcx, [rbx+8]; Block
0x140002d26  test    rcx, rcx
0x140002d29  jz      short loc_140002D39
0x140002d2b  call    cs:__imp_free
0x140002d31  mov     qword ptr [rbx+8], 0
0x140002d39  mov     rsi, [rsp+28h+arg_8]
0x140002d3e  xor     eax, eax
0x140002d40  mov     dword ptr [rbx+10h], 0
0x140002d47  mov     rbx, [rsp+28h+arg_0]
0x140002d4c  add     rsp, 20h
0x140002d50  pop     rdi
0x140002d51  retn
0x140002d52  mov     ecx, 0C000008Ch; unsigned int
0x140002d57  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x140002d5c  int     3; Trap to Debugger
0x140002d5d  mov     ecx, 0C000008Ch; unsigned int
0x140002d62  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
