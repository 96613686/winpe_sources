# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180002aec`
- end: `0x180002b94`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `168`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002028`
- `0x180002ba0`

## callees

- `0x180001150`
- `0x180002aec`
- `0x1800046fc`

## import_xrefs

- `msvcrt!free` at `0x180002b41`
- `msvcrt!free` at `0x180002b57`
- `msvcrt!free` at `0x180002b41`
- `msvcrt!free` at `0x180002b57`

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
        JUMPOUT(0x180002B93LL);
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
0x180002aec  mov     [rsp+arg_0], rbx
0x180002af1  mov     [rsp+arg_8], rsi
0x180002af6  push    rdi
0x180002af7  sub     rsp, 20h
0x180002afb  mov     eax, [rcx+10h]
0x180002afe  mov     rbx, rcx
0x180002b01  test    eax, eax
0x180002b03  jle     short loc_180002B39
0x180002b05  xor     edi, edi
0x180002b07  test    edi, edi
0x180002b09  js      short loc_180002B7E
0x180002b0b  cmp     edi, eax
0x180002b0d  jge     short loc_180002B7E
0x180002b0f  mov     rcx, [rbx]
0x180002b12  movsxd  rsi, edi
0x180002b15  mov     rcx, [rcx+rsi*8]; Block
0x180002b19  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180002b1e  cmp     edi, [rbx+10h]
0x180002b21  jge     short loc_180002B89
0x180002b23  mov     rcx, [rbx+8]
0x180002b27  mov     rcx, [rcx+rsi*8]; Block
0x180002b2b  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180002b30  mov     eax, [rbx+10h]
0x180002b33  inc     edi
0x180002b35  cmp     edi, eax
0x180002b37  jl      short loc_180002B07
0x180002b39  mov     rcx, [rbx]; Block
0x180002b3c  test    rcx, rcx
0x180002b3f  jz      short loc_180002B4E
0x180002b41  call    cs:__imp_free
0x180002b47  mov     qword ptr [rbx], 0
0x180002b4e  mov     rcx, [rbx+8]; Block
0x180002b52  test    rcx, rcx
0x180002b55  jz      short loc_180002B65
0x180002b57  call    cs:__imp_free
0x180002b5d  mov     qword ptr [rbx+8], 0
0x180002b65  mov     rsi, [rsp+28h+arg_8]
0x180002b6a  xor     eax, eax
0x180002b6c  mov     dword ptr [rbx+10h], 0
0x180002b73  mov     rbx, [rsp+28h+arg_0]
0x180002b78  add     rsp, 20h
0x180002b7c  pop     rdi
0x180002b7d  retn
0x180002b7e  mov     ecx, 0C000008Ch; unsigned int
0x180002b83  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180002b88  int     3; Trap to Debugger
0x180002b89  mov     ecx, 0C000008Ch; unsigned int
0x180002b8e  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
