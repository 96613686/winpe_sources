# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180003ed8`
- end: `0x180003f80`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `168`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000310c`
- `0x180003f90`

## callees

- `0x180003ed8`
- `0x1800063bc`
- `0x180007d80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180003f2d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180003f43`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180003f2d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180003f43`

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
      MemFree(*(void **)(*(_QWORD *)this + 8LL * i));
      if ( i >= *((_DWORD *)this + 4) )
      {
        ATL::_AtlRaiseException(0xC000008C, v5);
        JUMPOUT(0x180003F7FLL);
      }
      MemFree(*(void **)(*((_QWORD *)this + 1) + 8LL * i));
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
0x180003ed8  mov     [rsp+arg_0], rbx
0x180003edd  mov     [rsp+arg_8], rsi
0x180003ee2  push    rdi
0x180003ee3  sub     rsp, 20h
0x180003ee7  mov     eax, [rcx+10h]
0x180003eea  mov     rbx, rcx
0x180003eed  test    eax, eax
0x180003eef  jle     short loc_180003F25
0x180003ef1  xor     edi, edi
0x180003ef3  test    edi, edi
0x180003ef5  js      short loc_180003F6A
0x180003ef7  cmp     edi, eax
0x180003ef9  jge     short loc_180003F6A
0x180003efb  mov     rcx, [rbx]
0x180003efe  movsxd  rsi, edi
0x180003f01  mov     rcx, [rcx+rsi*8]; lpMem
0x180003f05  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180003f0a  cmp     edi, [rbx+10h]
0x180003f0d  jge     short loc_180003F75
0x180003f0f  mov     rcx, [rbx+8]
0x180003f13  mov     rcx, [rcx+rsi*8]; lpMem
0x180003f17  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180003f1c  mov     eax, [rbx+10h]
0x180003f1f  inc     edi
0x180003f21  cmp     edi, eax
0x180003f23  jl      short loc_180003EF3
0x180003f25  mov     rcx, [rbx]; Block
0x180003f28  test    rcx, rcx
0x180003f2b  jz      short loc_180003F3A
0x180003f2d  call    cs:__imp_free
0x180003f33  mov     qword ptr [rbx], 0
0x180003f3a  mov     rcx, [rbx+8]; Block
0x180003f3e  test    rcx, rcx
0x180003f41  jz      short loc_180003F51
0x180003f43  call    cs:__imp_free
0x180003f49  mov     qword ptr [rbx+8], 0
0x180003f51  mov     rsi, [rsp+28h+arg_8]
0x180003f56  xor     eax, eax
0x180003f58  mov     dword ptr [rbx+10h], 0
0x180003f5f  mov     rbx, [rsp+28h+arg_0]
0x180003f64  add     rsp, 20h
0x180003f68  pop     rdi
0x180003f69  retn
0x180003f6a  mov     ecx, 0C000008Ch; unsigned int
0x180003f6f  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180003f74  int     3; Trap to Debugger
0x180003f75  mov     ecx, 0C000008Ch; unsigned int
0x180003f7a  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
