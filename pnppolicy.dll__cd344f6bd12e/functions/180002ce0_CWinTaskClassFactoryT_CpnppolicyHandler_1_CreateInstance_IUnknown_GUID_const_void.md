# CWinTaskClassFactoryT<CpnppolicyHandler,1>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180002ce0`
- end: `0x180002db1`
- name: `?CreateInstance@?$CWinTaskClassFactoryT@VCpnppolicyHandler@@$00@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `209`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x180001008`
- `0x180002ce0`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CpnppolicyHandler,1>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v6; // ebx
  _QWORD *v7; // rax
  _QWORD *v8; // rdi

  if ( a4 )
  {
    *a4 = 0;
    if ( a2 )
    {
      return (unsigned int)-2147221232;
    }
    else
    {
      v7 = operator new(0x38u);
      v8 = v7;
      if ( v7 )
      {
        v7[1] = 0;
        *((_DWORD *)v7 + 4) = 0;
        v7[3] = -1;
        *((_DWORD *)v7 + 8) = 1;
        *((_DWORD *)v7 + 9) = 0;
        v7[5] = 0;
        v7[6] = 0;
        _InterlockedAdd(&CWinTaskHandler::s_cInstances, 1u);
        *v7 = &CpnppolicyHandler::`vftable';
        *((_DWORD *)v7 + 4) = 1;
        v6 = ((__int64 (__fastcall *)(_QWORD *, __int64, _QWORD *))CpnppolicyHandler::`vftable')(v7, a3, a4);
        (*(void (__fastcall **)(_QWORD *))(*v8 + 16LL))(v8);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x180002ce0  mov     [rsp+arg_0], rbx
0x180002ce5  mov     [rsp+arg_8], rsi
0x180002cea  push    rdi
0x180002ceb  sub     rsp, 20h
0x180002cef  mov     rbx, r9
0x180002cf2  mov     rsi, r8
0x180002cf5  test    r9, r9
0x180002cf8  jnz     short loc_180002D04
0x180002cfa  mov     ebx, 80070057h
0x180002cff  jmp     loc_180002D9F
0x180002d04  mov     qword ptr [r9], 0
0x180002d0b  test    rdx, rdx
0x180002d0e  jz      short loc_180002D1A
0x180002d10  mov     ebx, 80040110h
0x180002d15  jmp     loc_180002D9F
0x180002d1a  mov     ecx, 38h ; '8'; Size
0x180002d1f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002d24  mov     rdi, rax
0x180002d27  test    rax, rax
0x180002d2a  jz      short loc_180002D9A
0x180002d2c  mov     qword ptr [rax+8], 0
0x180002d34  mov     ecx, 1
0x180002d39  mov     dword ptr [rax+10h], 0
0x180002d40  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x180002d48  mov     [rax+20h], ecx
0x180002d4b  mov     dword ptr [rax+24h], 0
0x180002d52  mov     qword ptr [rax+28h], 0
0x180002d5a  mov     qword ptr [rax+30h], 0
0x180002d62  lock add cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x180002d69  lea     rax, ??_7CpnppolicyHandler@@6B@; const CpnppolicyHandler::`vftable'
0x180002d70  mov     r8, rbx
0x180002d73  mov     [rdi], rax
0x180002d76  mov     rdx, rsi
0x180002d79  mov     rax, [rax]
0x180002d7c  mov     [rdi+10h], ecx
0x180002d7f  mov     rcx, rdi
0x180002d82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d87  mov     ebx, eax
0x180002d89  mov     rcx, [rdi]
0x180002d8c  mov     rax, [rcx+10h]
0x180002d90  mov     rcx, rdi
0x180002d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d98  jmp     short loc_180002D9F
0x180002d9a  mov     ebx, 8007000Eh
0x180002d9f  mov     rsi, [rsp+28h+arg_8]
0x180002da4  mov     eax, ebx
0x180002da6  mov     rbx, [rsp+28h+arg_0]
0x180002dab  add     rsp, 20h
0x180002daf  pop     rdi
0x180002db0  retn
```
