# CWinTaskClassFactoryT<CRegIdleHandler,1>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180001a70`
- end: `0x180001b41`
- name: `?CreateInstance@?$CWinTaskClassFactoryT@VCRegIdleHandler@@$00@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `209`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180001008`
- `0x180001a70`
- `0x180003010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CRegIdleHandler,1>::CreateInstance(
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
        *v7 = &CRegIdleHandler::`vftable';
        *((_DWORD *)v7 + 4) = 1;
        v6 = ((__int64 (__fastcall *)(_QWORD *, __int64, _QWORD *))CRegIdleHandler::`vftable')(v7, a3, a4);
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
0x180001a70  mov     [rsp+arg_0], rbx
0x180001a75  mov     [rsp+arg_8], rsi
0x180001a7a  push    rdi
0x180001a7b  sub     rsp, 20h
0x180001a7f  mov     rbx, r9
0x180001a82  mov     rsi, r8
0x180001a85  test    r9, r9
0x180001a88  jnz     short loc_180001A94
0x180001a8a  mov     ebx, 80070057h
0x180001a8f  jmp     loc_180001B2F
0x180001a94  mov     qword ptr [r9], 0
0x180001a9b  test    rdx, rdx
0x180001a9e  jz      short loc_180001AAA
0x180001aa0  mov     ebx, 80040110h
0x180001aa5  jmp     loc_180001B2F
0x180001aaa  mov     ecx, 38h ; '8'; Size
0x180001aaf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001ab4  mov     rdi, rax
0x180001ab7  test    rax, rax
0x180001aba  jz      short loc_180001B2A
0x180001abc  mov     qword ptr [rax+8], 0
0x180001ac4  mov     ecx, 1
0x180001ac9  mov     dword ptr [rax+10h], 0
0x180001ad0  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x180001ad8  mov     [rax+20h], ecx
0x180001adb  mov     dword ptr [rax+24h], 0
0x180001ae2  mov     qword ptr [rax+28h], 0
0x180001aea  mov     qword ptr [rax+30h], 0
0x180001af2  lock add cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x180001af9  lea     rax, ??_7CRegIdleHandler@@6B@; const CRegIdleHandler::`vftable'
0x180001b00  mov     r8, rbx
0x180001b03  mov     [rdi], rax
0x180001b06  mov     rdx, rsi
0x180001b09  mov     rax, [rax]
0x180001b0c  mov     [rdi+10h], ecx
0x180001b0f  mov     rcx, rdi
0x180001b12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b17  mov     ebx, eax
0x180001b19  mov     rcx, [rdi]
0x180001b1c  mov     rax, [rcx+10h]
0x180001b20  mov     rcx, rdi
0x180001b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b28  jmp     short loc_180001B2F
0x180001b2a  mov     ebx, 8007000Eh
0x180001b2f  mov     rsi, [rsp+28h+arg_8]
0x180001b34  mov     eax, ebx
0x180001b36  mov     rbx, [rsp+28h+arg_0]
0x180001b3b  add     rsp, 20h
0x180001b3f  pop     rdi
0x180001b40  retn
```
