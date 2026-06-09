# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x18000f2a4`
- end: `0x18000f352`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `174`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d860`
- `0x18000f360`

## callees

- `0x18000f2a4`
- `0x1800127fc`

## import_xrefs

- `msvcrt!free` at `0x18000f2d5`
- `msvcrt!free` at `0x18000f2e8`
- `msvcrt!free` at `0x18000f2ff`
- `msvcrt!free` at `0x18000f315`
- `msvcrt!free` at `0x18000f2d5`
- `msvcrt!free` at `0x18000f2e8`
- `msvcrt!free` at `0x18000f2ff`
- `msvcrt!free` at `0x18000f315`

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
        JUMPOUT(0x18000F351LL);
      }
      free(*(void **)(*(_QWORD *)this + 8LL * i));
      if ( i >= *((_DWORD *)this + 4) )
      {
        ATL::_AtlRaiseException(0xC000008C);
        __debugbreak();
      }
      free(*(void **)(*((_QWORD *)this + 1) + 8LL * i));
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
0x18000f2a4  mov     [rsp+arg_0], rbx
0x18000f2a9  mov     [rsp+arg_8], rsi
0x18000f2ae  push    rdi
0x18000f2af  sub     rsp, 20h
0x18000f2b3  mov     eax, [rcx+10h]
0x18000f2b6  mov     rbx, rcx
0x18000f2b9  test    eax, eax
0x18000f2bb  jle     short loc_18000F2F7
0x18000f2bd  xor     edi, edi
0x18000f2bf  test    edi, edi
0x18000f2c1  js      loc_18000F347
0x18000f2c7  cmp     edi, eax
0x18000f2c9  jge     short loc_18000F347
0x18000f2cb  mov     rcx, [rbx]
0x18000f2ce  movsxd  rsi, edi
0x18000f2d1  mov     rcx, [rcx+rsi*8]; Block
0x18000f2d5  call    cs:__imp_free
0x18000f2db  cmp     edi, [rbx+10h]
0x18000f2de  jge     short loc_18000F33C
0x18000f2e0  mov     rcx, [rbx+8]
0x18000f2e4  mov     rcx, [rcx+rsi*8]; Block
0x18000f2e8  call    cs:__imp_free
0x18000f2ee  mov     eax, [rbx+10h]
0x18000f2f1  inc     edi
0x18000f2f3  cmp     edi, eax
0x18000f2f5  jl      short loc_18000F2BF
0x18000f2f7  mov     rcx, [rbx]; Block
0x18000f2fa  test    rcx, rcx
0x18000f2fd  jz      short loc_18000F30C
0x18000f2ff  call    cs:__imp_free
0x18000f305  mov     qword ptr [rbx], 0
0x18000f30c  mov     rcx, [rbx+8]; Block
0x18000f310  test    rcx, rcx
0x18000f313  jz      short loc_18000F323
0x18000f315  call    cs:__imp_free
0x18000f31b  mov     qword ptr [rbx+8], 0
0x18000f323  mov     rsi, [rsp+28h+arg_8]
0x18000f328  xor     eax, eax
0x18000f32a  mov     dword ptr [rbx+10h], 0
0x18000f331  mov     rbx, [rsp+28h+arg_0]
0x18000f336  add     rsp, 20h
0x18000f33a  pop     rdi
0x18000f33b  retn
0x18000f33c  mov     ecx, 0C000008Ch; unsigned int
0x18000f341  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x18000f346  int     3; Trap to Debugger
0x18000f347  mov     ecx, 0C000008Ch; unsigned int
0x18000f34c  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
