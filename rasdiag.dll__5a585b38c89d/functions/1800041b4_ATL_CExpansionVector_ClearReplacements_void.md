# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x1800041b4`
- end: `0x18000427f`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `203`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180002c04`
- `0x180004290`

## callees

- `0x1800041b4`
- `0x180005ca0`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800041e9`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180004202`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800041e9`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180004202`
- `msvcrt!free` at `0x18000421f`
- `msvcrt!free` at `0x18000423b`
- `msvcrt!free` at `0x18000421f`
- `msvcrt!free` at `0x18000423b`

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
        JUMPOUT(0x18000427ELL);
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
0x1800041b4  mov     [rsp+arg_0], rbx
0x1800041b9  mov     [rsp+arg_8], rsi
0x1800041be  push    rdi
0x1800041bf  sub     rsp, 20h
0x1800041c3  mov     eax, [rcx+10h]
0x1800041c6  mov     rbx, rcx
0x1800041c9  test    eax, eax
0x1800041cb  jle     short loc_180004217
0x1800041cd  xor     edi, edi
0x1800041cf  test    edi, edi
0x1800041d1  js      loc_180004269
0x1800041d7  cmp     edi, eax
0x1800041d9  jge     loc_180004269
0x1800041df  mov     rcx, [rbx]
0x1800041e2  movsxd  rsi, edi
0x1800041e5  mov     rcx, [rcx+rsi*8]
0x1800041e9  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800041f0  nop     dword ptr [rax+rax+00h]
0x1800041f5  cmp     edi, [rbx+10h]
0x1800041f8  jge     short loc_180004274
0x1800041fa  mov     rcx, [rbx+8]
0x1800041fe  mov     rcx, [rcx+rsi*8]
0x180004202  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180004209  nop     dword ptr [rax+rax+00h]
0x18000420e  mov     eax, [rbx+10h]
0x180004211  inc     edi
0x180004213  cmp     edi, eax
0x180004215  jl      short loc_1800041CF
0x180004217  mov     rcx, [rbx]; Block
0x18000421a  test    rcx, rcx
0x18000421d  jz      short loc_180004232
0x18000421f  call    cs:__imp_free
0x180004226  nop     dword ptr [rax+rax+00h]
0x18000422b  mov     qword ptr [rbx], 0
0x180004232  mov     rcx, [rbx+8]; Block
0x180004236  test    rcx, rcx
0x180004239  jz      short loc_18000424F
0x18000423b  call    cs:__imp_free
0x180004242  nop     dword ptr [rax+rax+00h]
0x180004247  mov     qword ptr [rbx+8], 0
0x18000424f  mov     rsi, [rsp+28h+arg_8]
0x180004254  xor     eax, eax
0x180004256  mov     dword ptr [rbx+10h], 0
0x18000425d  mov     rbx, [rsp+28h+arg_0]
0x180004262  add     rsp, 20h
0x180004266  pop     rdi
0x180004267  retn
0x180004269  mov     ecx, 0C000008Ch; unsigned int
0x18000426e  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180004273  int     3; Trap to Debugger
0x180004274  mov     ecx, 0C000008Ch; unsigned int
0x180004279  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
