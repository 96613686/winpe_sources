# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x140006968`
- end: `0x140006a21`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `185`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140005c40`
- `0x140006a30`

## callees

- `0x140001794`
- `0x140006968`
- `0x140008afc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400069c1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400069dd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400069c1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400069dd`

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
        JUMPOUT(0x140006A20LL);
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
0x140006968  mov     [rsp+arg_0], rbx
0x14000696d  mov     [rsp+arg_8], rsi
0x140006972  push    rdi
0x140006973  sub     rsp, 20h
0x140006977  mov     eax, [rcx+10h]
0x14000697a  mov     rbx, rcx
0x14000697d  test    eax, eax
0x14000697f  jle     short loc_1400069B9
0x140006981  xor     edi, edi
0x140006983  test    edi, edi
0x140006985  js      loc_140006A0B
0x14000698b  cmp     edi, eax
0x14000698d  jge     short loc_140006A0B
0x14000698f  mov     rcx, [rbx]
0x140006992  movsxd  rsi, edi
0x140006995  mov     rcx, [rcx+rsi*8]; Block
0x140006999  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000699e  cmp     edi, [rbx+10h]
0x1400069a1  jge     short loc_140006A16
0x1400069a3  mov     rcx, [rbx+8]
0x1400069a7  mov     rcx, [rcx+rsi*8]; Block
0x1400069ab  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400069b0  mov     eax, [rbx+10h]
0x1400069b3  inc     edi
0x1400069b5  cmp     edi, eax
0x1400069b7  jl      short loc_140006983
0x1400069b9  mov     rcx, [rbx]; Block
0x1400069bc  test    rcx, rcx
0x1400069bf  jz      short loc_1400069D4
0x1400069c1  call    cs:__imp_free
0x1400069c8  nop     dword ptr [rax+rax+00h]
0x1400069cd  mov     qword ptr [rbx], 0
0x1400069d4  mov     rcx, [rbx+8]; Block
0x1400069d8  test    rcx, rcx
0x1400069db  jz      short loc_1400069F1
0x1400069dd  call    cs:__imp_free
0x1400069e4  nop     dword ptr [rax+rax+00h]
0x1400069e9  mov     qword ptr [rbx+8], 0
0x1400069f1  mov     rsi, [rsp+28h+arg_8]
0x1400069f6  xor     eax, eax
0x1400069f8  mov     dword ptr [rbx+10h], 0
0x1400069ff  mov     rbx, [rsp+28h+arg_0]
0x140006a04  add     rsp, 20h
0x140006a08  pop     rdi
0x140006a09  retn
0x140006a0b  mov     ecx, 0C000008Ch; unsigned int
0x140006a10  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x140006a15  int     3; Trap to Debugger
0x140006a16  mov     ecx, 0C000008Ch; unsigned int
0x140006a1b  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
