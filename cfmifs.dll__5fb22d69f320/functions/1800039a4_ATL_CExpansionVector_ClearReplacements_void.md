# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x1800039a4`
- end: `0x180003a7e`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `218`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002824`
- `0x180003a90`

## callees

- `0x1800039a4`
- `0x180005afc`

## import_xrefs

- `msvcrt!free` at `0x180003a2b`
- `msvcrt!free` at `0x180003a41`
- `msvcrt!free` at `0x180003a2b`
- `msvcrt!free` at `0x180003a41`
- `ntdll!RtlFreeHeap` at `0x1800039ed`
- `ntdll!RtlFreeHeap` at `0x180003a14`
- `ntdll!RtlFreeHeap` at `0x1800039ed`
- `ntdll!RtlFreeHeap` at `0x180003a14`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::ClearReplacements(ATL::CExpansionVector *this, unsigned int a2)
{
  int v2; // eax
  int i; // edi
  void *v5; // r8
  void *v6; // r8
  void *v7; // rcx
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
      v5 = *(void **)(*(_QWORD *)this + 8LL * i);
      if ( v5 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
      if ( i >= *((_DWORD *)this + 4) )
      {
        ATL::_AtlRaiseException(0xC000008C, a2);
        JUMPOUT(0x180003A7DLL);
      }
      v6 = *(void **)(*((_QWORD *)this + 1) + 8LL * i);
      if ( v6 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
      v2 = *((_DWORD *)this + 4);
    }
  }
  if ( *(_QWORD *)this )
  {
    free(*(void **)this);
    *(_QWORD *)this = 0;
  }
  v7 = (void *)*((_QWORD *)this + 1);
  if ( v7 )
  {
    free(v7);
    *((_QWORD *)this + 1) = 0;
  }
  result = 0;
  *((_DWORD *)this + 4) = 0;
  return result;
}

```

## disassembly

```asm
0x1800039a4  mov     [rsp+arg_0], rbx
0x1800039a9  mov     [rsp+arg_8], rsi
0x1800039ae  push    rdi
0x1800039af  sub     rsp, 20h
0x1800039b3  mov     eax, [rcx+10h]
0x1800039b6  mov     rbx, rcx
0x1800039b9  test    eax, eax
0x1800039bb  jle     short loc_180003A23
0x1800039bd  xor     edi, edi
0x1800039bf  test    edi, edi
0x1800039c1  js      loc_180003A68
0x1800039c7  cmp     edi, eax
0x1800039c9  jge     loc_180003A68
0x1800039cf  mov     rax, [rbx]
0x1800039d2  movsxd  rsi, edi
0x1800039d5  mov     r8, [rax+rsi*8]; P
0x1800039d9  test    r8, r8
0x1800039dc  jz      short loc_1800039F3
0x1800039de  mov     rcx, gs:60h
0x1800039e7  xor     edx, edx; Flags
0x1800039e9  mov     rcx, [rcx+30h]; HeapHandle
0x1800039ed  call    cs:__imp_RtlFreeHeap
0x1800039f3  cmp     edi, [rbx+10h]
0x1800039f6  jge     short loc_180003A73
0x1800039f8  mov     rax, [rbx+8]
0x1800039fc  mov     r8, [rax+rsi*8]; P
0x180003a00  test    r8, r8
0x180003a03  jz      short loc_180003A1A
0x180003a05  mov     rcx, gs:60h
0x180003a0e  xor     edx, edx; Flags
0x180003a10  mov     rcx, [rcx+30h]; HeapHandle
0x180003a14  call    cs:__imp_RtlFreeHeap
0x180003a1a  mov     eax, [rbx+10h]
0x180003a1d  inc     edi
0x180003a1f  cmp     edi, eax
0x180003a21  jl      short loc_1800039BF
0x180003a23  mov     rcx, [rbx]; Block
0x180003a26  test    rcx, rcx
0x180003a29  jz      short loc_180003A38
0x180003a2b  call    cs:__imp_free
0x180003a31  mov     qword ptr [rbx], 0
0x180003a38  mov     rcx, [rbx+8]; Block
0x180003a3c  test    rcx, rcx
0x180003a3f  jz      short loc_180003A4F
0x180003a41  call    cs:__imp_free
0x180003a47  mov     qword ptr [rbx+8], 0
0x180003a4f  mov     rsi, [rsp+28h+arg_8]
0x180003a54  xor     eax, eax
0x180003a56  mov     dword ptr [rbx+10h], 0
0x180003a5d  mov     rbx, [rsp+28h+arg_0]
0x180003a62  add     rsp, 20h
0x180003a66  pop     rdi
0x180003a67  retn
0x180003a68  mov     ecx, 0C000008Ch; unsigned int
0x180003a6d  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180003a72  int     3; Trap to Debugger
0x180003a73  mov     ecx, 0C000008Ch; unsigned int
0x180003a78  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
