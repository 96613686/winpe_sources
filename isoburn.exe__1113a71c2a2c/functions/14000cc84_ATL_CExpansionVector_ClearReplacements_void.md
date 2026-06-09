# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x14000cc84`
- end: `0x14000cd2c`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `168`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14000c318`
- `0x14000cd40`

## callees

- `0x140001c54`
- `0x140009858`
- `0x14000cc84`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000ccd9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000ccef`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000ccd9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000ccef`

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
        JUMPOUT(0x14000CD2BLL);
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
0x14000cc84  mov     [rsp+arg_0], rbx
0x14000cc89  mov     [rsp+arg_8], rsi
0x14000cc8e  push    rdi
0x14000cc8f  sub     rsp, 20h
0x14000cc93  mov     eax, [rcx+10h]
0x14000cc96  mov     rbx, rcx
0x14000cc99  test    eax, eax
0x14000cc9b  jle     short loc_14000CCD1
0x14000cc9d  xor     edi, edi
0x14000cc9f  test    edi, edi
0x14000cca1  js      short loc_14000CD16
0x14000cca3  cmp     edi, eax
0x14000cca5  jge     short loc_14000CD16
0x14000cca7  mov     rcx, [rbx]
0x14000ccaa  movsxd  rsi, edi
0x14000ccad  mov     rcx, [rcx+rsi*8]; Block
0x14000ccb1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000ccb6  cmp     edi, [rbx+10h]
0x14000ccb9  jge     short loc_14000CD21
0x14000ccbb  mov     rcx, [rbx+8]
0x14000ccbf  mov     rcx, [rcx+rsi*8]; Block
0x14000ccc3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000ccc8  mov     eax, [rbx+10h]
0x14000cccb  inc     edi
0x14000cccd  cmp     edi, eax
0x14000cccf  jl      short loc_14000CC9F
0x14000ccd1  mov     rcx, [rbx]; Block
0x14000ccd4  test    rcx, rcx
0x14000ccd7  jz      short loc_14000CCE6
0x14000ccd9  call    cs:__imp_free
0x14000ccdf  mov     qword ptr [rbx], 0
0x14000cce6  mov     rcx, [rbx+8]; Block
0x14000ccea  test    rcx, rcx
0x14000cced  jz      short loc_14000CCFD
0x14000ccef  call    cs:__imp_free
0x14000ccf5  mov     qword ptr [rbx+8], 0
0x14000ccfd  mov     rsi, [rsp+28h+arg_8]
0x14000cd02  xor     eax, eax
0x14000cd04  mov     dword ptr [rbx+10h], 0
0x14000cd0b  mov     rbx, [rsp+28h+arg_0]
0x14000cd10  add     rsp, 20h
0x14000cd14  pop     rdi
0x14000cd15  retn
0x14000cd16  mov     ecx, 0C000008Ch; unsigned int
0x14000cd1b  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x14000cd20  int     3; Trap to Debugger
0x14000cd21  mov     ecx, 0C000008Ch; unsigned int
0x14000cd26  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
