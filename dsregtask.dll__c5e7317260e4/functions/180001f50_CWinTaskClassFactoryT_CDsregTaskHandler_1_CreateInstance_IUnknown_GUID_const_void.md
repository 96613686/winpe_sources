# CWinTaskClassFactoryT<CDsregTaskHandler,1>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180001f50`
- end: `0x180002021`
- name: `?CreateInstance@?$CWinTaskClassFactoryT@VCDsregTaskHandler@@$00@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `209`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180001030`
- `0x180001f50`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CDsregTaskHandler,1>::CreateInstance(
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
        *v7 = &CDsregTaskHandler::`vftable';
        *((_DWORD *)v7 + 4) = 1;
        v6 = ((__int64 (__fastcall *)(_QWORD *, __int64, _QWORD *))CDsregTaskHandler::`vftable')(v7, a3, a4);
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
0x180001f50  mov     [rsp+arg_0], rbx
0x180001f55  mov     [rsp+arg_8], rsi
0x180001f5a  push    rdi
0x180001f5b  sub     rsp, 20h
0x180001f5f  mov     rbx, r9
0x180001f62  mov     rsi, r8
0x180001f65  test    r9, r9
0x180001f68  jnz     short loc_180001F74
0x180001f6a  mov     ebx, 80070057h
0x180001f6f  jmp     loc_18000200F
0x180001f74  mov     qword ptr [r9], 0
0x180001f7b  test    rdx, rdx
0x180001f7e  jz      short loc_180001F8A
0x180001f80  mov     ebx, 80040110h
0x180001f85  jmp     loc_18000200F
0x180001f8a  mov     ecx, 38h ; '8'; Size
0x180001f8f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001f94  mov     rdi, rax
0x180001f97  test    rax, rax
0x180001f9a  jz      short loc_18000200A
0x180001f9c  mov     qword ptr [rax+8], 0
0x180001fa4  mov     ecx, 1
0x180001fa9  mov     dword ptr [rax+10h], 0
0x180001fb0  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x180001fb8  mov     [rax+20h], ecx
0x180001fbb  mov     dword ptr [rax+24h], 0
0x180001fc2  mov     qword ptr [rax+28h], 0
0x180001fca  mov     qword ptr [rax+30h], 0
0x180001fd2  lock add cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x180001fd9  lea     rax, ??_7CDsregTaskHandler@@6B@; const CDsregTaskHandler::`vftable'
0x180001fe0  mov     r8, rbx
0x180001fe3  mov     [rdi], rax
0x180001fe6  mov     rdx, rsi
0x180001fe9  mov     rax, [rax]
0x180001fec  mov     [rdi+10h], ecx
0x180001fef  mov     rcx, rdi
0x180001ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ff7  mov     ebx, eax
0x180001ff9  mov     rcx, [rdi]
0x180001ffc  mov     rax, [rcx+10h]
0x180002000  mov     rcx, rdi
0x180002003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002008  jmp     short loc_18000200F
0x18000200a  mov     ebx, 8007000Eh
0x18000200f  mov     rsi, [rsp+28h+arg_8]
0x180002014  mov     eax, ebx
0x180002016  mov     rbx, [rsp+28h+arg_0]
0x18000201b  add     rsp, 20h
0x18000201f  pop     rdi
0x180002020  retn
```
