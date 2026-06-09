# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x18000c4b4`
- end: `0x18000c55c`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `168`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000b5c8`
- `0x18000c570`

## callees

- `0x180002984`
- `0x18000c4b4`
- `0x1800107a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c509`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c51f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c509`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c51f`

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
      operator delete(*(void **)(*(_QWORD *)this + 8LL * i));
      if ( i >= *((_DWORD *)this + 4) )
      {
        ATL::_AtlRaiseException(0xC000008C, v5);
        JUMPOUT(0x18000C55BLL);
      }
      operator delete(*(void **)(*((_QWORD *)this + 1) + 8LL * i));
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
0x18000c4b4  mov     [rsp+arg_0], rbx
0x18000c4b9  mov     [rsp+arg_8], rsi
0x18000c4be  push    rdi
0x18000c4bf  sub     rsp, 20h
0x18000c4c3  mov     eax, [rcx+10h]
0x18000c4c6  mov     rbx, rcx
0x18000c4c9  test    eax, eax
0x18000c4cb  jle     short loc_18000C501
0x18000c4cd  xor     edi, edi
0x18000c4cf  test    edi, edi
0x18000c4d1  js      short loc_18000C546
0x18000c4d3  cmp     edi, eax
0x18000c4d5  jge     short loc_18000C546
0x18000c4d7  mov     rcx, [rbx]
0x18000c4da  movsxd  rsi, edi
0x18000c4dd  mov     rcx, [rcx+rsi*8]; Block
0x18000c4e1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c4e6  cmp     edi, [rbx+10h]
0x18000c4e9  jge     short loc_18000C551
0x18000c4eb  mov     rcx, [rbx+8]
0x18000c4ef  mov     rcx, [rcx+rsi*8]; Block
0x18000c4f3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c4f8  mov     eax, [rbx+10h]
0x18000c4fb  inc     edi
0x18000c4fd  cmp     edi, eax
0x18000c4ff  jl      short loc_18000C4CF
0x18000c501  mov     rcx, [rbx]; Block
0x18000c504  test    rcx, rcx
0x18000c507  jz      short loc_18000C516
0x18000c509  call    cs:__imp_free
0x18000c50f  mov     qword ptr [rbx], 0
0x18000c516  mov     rcx, [rbx+8]; Block
0x18000c51a  test    rcx, rcx
0x18000c51d  jz      short loc_18000C52D
0x18000c51f  call    cs:__imp_free
0x18000c525  mov     qword ptr [rbx+8], 0
0x18000c52d  mov     rsi, [rsp+28h+arg_8]
0x18000c532  xor     eax, eax
0x18000c534  mov     dword ptr [rbx+10h], 0
0x18000c53b  mov     rbx, [rsp+28h+arg_0]
0x18000c540  add     rsp, 20h
0x18000c544  pop     rdi
0x18000c545  retn
0x18000c546  mov     ecx, 0C000008Ch; unsigned int
0x18000c54b  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x18000c550  int     3; Trap to Debugger
0x18000c551  mov     ecx, 0C000008Ch; unsigned int
0x18000c556  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
