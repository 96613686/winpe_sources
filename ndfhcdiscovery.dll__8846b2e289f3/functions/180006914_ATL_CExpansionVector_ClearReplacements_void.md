# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180006914`
- end: `0x1800069df`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `203`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800058b8`
- `0x1800069f0`

## callees

- `0x180006914`
- `0x180009fb0`

## import_xrefs

- `msvcrt!free` at `0x18000697f`
- `msvcrt!free` at `0x18000699b`
- `msvcrt!free` at `0x18000697f`
- `msvcrt!free` at `0x18000699b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180006949`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180006962`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180006949`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180006962`

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
        JUMPOUT(0x1800069DELL);
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
0x180006914  mov     [rsp+arg_0], rbx
0x180006919  mov     [rsp+arg_8], rsi
0x18000691e  push    rdi
0x18000691f  sub     rsp, 20h
0x180006923  mov     eax, [rcx+10h]
0x180006926  mov     rbx, rcx
0x180006929  test    eax, eax
0x18000692b  jle     short loc_180006977
0x18000692d  xor     edi, edi
0x18000692f  test    edi, edi
0x180006931  js      loc_1800069C9
0x180006937  cmp     edi, eax
0x180006939  jge     loc_1800069C9
0x18000693f  mov     rcx, [rbx]
0x180006942  movsxd  rsi, edi
0x180006945  mov     rcx, [rcx+rsi*8]
0x180006949  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180006950  nop     dword ptr [rax+rax+00h]
0x180006955  cmp     edi, [rbx+10h]
0x180006958  jge     short loc_1800069D4
0x18000695a  mov     rcx, [rbx+8]
0x18000695e  mov     rcx, [rcx+rsi*8]
0x180006962  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180006969  nop     dword ptr [rax+rax+00h]
0x18000696e  mov     eax, [rbx+10h]
0x180006971  inc     edi
0x180006973  cmp     edi, eax
0x180006975  jl      short loc_18000692F
0x180006977  mov     rcx, [rbx]; Block
0x18000697a  test    rcx, rcx
0x18000697d  jz      short loc_180006992
0x18000697f  call    cs:__imp_free
0x180006986  nop     dword ptr [rax+rax+00h]
0x18000698b  mov     qword ptr [rbx], 0
0x180006992  mov     rcx, [rbx+8]; Block
0x180006996  test    rcx, rcx
0x180006999  jz      short loc_1800069AF
0x18000699b  call    cs:__imp_free
0x1800069a2  nop     dword ptr [rax+rax+00h]
0x1800069a7  mov     qword ptr [rbx+8], 0
0x1800069af  mov     rsi, [rsp+28h+arg_8]
0x1800069b4  xor     eax, eax
0x1800069b6  mov     dword ptr [rbx+10h], 0
0x1800069bd  mov     rbx, [rsp+28h+arg_0]
0x1800069c2  add     rsp, 20h
0x1800069c6  pop     rdi
0x1800069c7  retn
0x1800069c9  mov     ecx, 0C000008Ch; unsigned int
0x1800069ce  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x1800069d3  int     3; Trap to Debugger
0x1800069d4  mov     ecx, 0C000008Ch; unsigned int
0x1800069d9  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
