# CWinTaskClassFactoryT<CsvtaskHandler,1>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180001a70`
- end: `0x180001b48`
- name: `?CreateInstance@?$CWinTaskClassFactoryT@VCsvtaskHandler@@$00@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `216`
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
__int64 __fastcall CWinTaskClassFactoryT<CsvtaskHandler,1>::CreateInstance(
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
      v7 = operator new(0x40u);
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
        *((_DWORD *)v7 + 14) = 0;
        *v7 = &CsvtaskHandler::`vftable';
        *((_DWORD *)v7 + 4) = 1;
        v6 = ((__int64 (__fastcall *)(_QWORD *, __int64, _QWORD *))CsvtaskHandler::`vftable')(v7, a3, a4);
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
0x180001a8f  jmp     loc_180001B36
0x180001a94  mov     qword ptr [r9], 0
0x180001a9b  test    rdx, rdx
0x180001a9e  jz      short loc_180001AAA
0x180001aa0  mov     ebx, 80040110h
0x180001aa5  jmp     loc_180001B36
0x180001aaa  mov     ecx, 40h ; '@'; Size
0x180001aaf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001ab4  mov     rdi, rax
0x180001ab7  test    rax, rax
0x180001aba  jz      short loc_180001B31
0x180001abc  mov     qword ptr [rax+8], 0
0x180001ac4  mov     ecx, 1
0x180001ac9  mov     dword ptr [rax+10h], 0
0x180001ad0  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x180001ad8  mov     [rax+20h], ecx
0x180001adb  mov     dword ptr [rax+24h], 0
0x180001ae2  mov     qword ptr [rax+28h], 0
0x180001aea  mov     qword ptr [rax+30h], 0
0x180001af2  lock add cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x180001af9  lea     rax, ??_7CsvtaskHandler@@6B@; const CsvtaskHandler::`vftable'
0x180001b00  mov     dword ptr [rdi+38h], 0
0x180001b07  mov     [rdi], rax
0x180001b0a  mov     r8, rbx
0x180001b0d  mov     rax, [rax]
0x180001b10  mov     rdx, rsi
0x180001b13  mov     [rdi+10h], ecx
0x180001b16  mov     rcx, rdi
0x180001b19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b1e  mov     ebx, eax
0x180001b20  mov     rcx, [rdi]
0x180001b23  mov     rax, [rcx+10h]
0x180001b27  mov     rcx, rdi
0x180001b2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b2f  jmp     short loc_180001B36
0x180001b31  mov     ebx, 8007000Eh
0x180001b36  mov     rsi, [rsp+28h+arg_8]
0x180001b3b  mov     eax, ebx
0x180001b3d  mov     rbx, [rsp+28h+arg_0]
0x180001b42  add     rsp, 20h
0x180001b46  pop     rdi
0x180001b47  retn
```
