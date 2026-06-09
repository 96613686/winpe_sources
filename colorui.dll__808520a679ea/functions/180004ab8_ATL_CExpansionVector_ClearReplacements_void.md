# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180004ab8`
- end: `0x180004b60`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `168`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003018`
- `0x180004b70`

## callees

- `0x180001340`
- `0x180004ab8`
- `0x18000b3dc`

## import_xrefs

- `msvcrt!free` at `0x180004b0d`
- `msvcrt!free` at `0x180004b23`
- `msvcrt!free` at `0x180004b0d`
- `msvcrt!free` at `0x180004b23`

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
        JUMPOUT(0x180004B5FLL);
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
0x180004ab8  mov     [rsp+arg_0], rbx
0x180004abd  mov     [rsp+arg_8], rsi
0x180004ac2  push    rdi
0x180004ac3  sub     rsp, 20h
0x180004ac7  mov     eax, [rcx+10h]
0x180004aca  mov     rbx, rcx
0x180004acd  test    eax, eax
0x180004acf  jle     short loc_180004B05
0x180004ad1  xor     edi, edi
0x180004ad3  test    edi, edi
0x180004ad5  js      short loc_180004B4A
0x180004ad7  cmp     edi, eax
0x180004ad9  jge     short loc_180004B4A
0x180004adb  mov     rcx, [rbx]
0x180004ade  movsxd  rsi, edi
0x180004ae1  mov     rcx, [rcx+rsi*8]; Block
0x180004ae5  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180004aea  cmp     edi, [rbx+10h]
0x180004aed  jge     short loc_180004B55
0x180004aef  mov     rcx, [rbx+8]
0x180004af3  mov     rcx, [rcx+rsi*8]; Block
0x180004af7  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180004afc  mov     eax, [rbx+10h]
0x180004aff  inc     edi
0x180004b01  cmp     edi, eax
0x180004b03  jl      short loc_180004AD3
0x180004b05  mov     rcx, [rbx]; Block
0x180004b08  test    rcx, rcx
0x180004b0b  jz      short loc_180004B1A
0x180004b0d  call    cs:__imp_free
0x180004b13  mov     qword ptr [rbx], 0
0x180004b1a  mov     rcx, [rbx+8]; Block
0x180004b1e  test    rcx, rcx
0x180004b21  jz      short loc_180004B31
0x180004b23  call    cs:__imp_free
0x180004b29  mov     qword ptr [rbx+8], 0
0x180004b31  mov     rsi, [rsp+28h+arg_8]
0x180004b36  xor     eax, eax
0x180004b38  mov     dword ptr [rbx+10h], 0
0x180004b3f  mov     rbx, [rsp+28h+arg_0]
0x180004b44  add     rsp, 20h
0x180004b48  pop     rdi
0x180004b49  retn
0x180004b4a  mov     ecx, 0C000008Ch; unsigned int
0x180004b4f  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180004b54  int     3; Trap to Debugger
0x180004b55  mov     ecx, 0C000008Ch; unsigned int
0x180004b5a  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
