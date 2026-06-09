# CWinTaskClassFactoryT<CPnpRebootHandler,1>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000b3c0`
- end: `0x18000b491`
- name: `?CreateInstance@?$CWinTaskClassFactoryT@VCPnpRebootHandler@@$00@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `209`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180001254`
- `0x18000b3c0`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CPnpRebootHandler,1>::CreateInstance(
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
        *v7 = &CPnpRebootHandler::`vftable';
        *((_DWORD *)v7 + 4) = 1;
        v6 = ((__int64 (__fastcall *)(_QWORD *, __int64, _QWORD *))CPnpRebootHandler::`vftable')(v7, a3, a4);
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
0x18000b3c0  mov     [rsp+arg_0], rbx
0x18000b3c5  mov     [rsp+arg_8], rsi
0x18000b3ca  push    rdi
0x18000b3cb  sub     rsp, 20h
0x18000b3cf  mov     rbx, r9
0x18000b3d2  mov     rsi, r8
0x18000b3d5  test    r9, r9
0x18000b3d8  jnz     short loc_18000B3E4
0x18000b3da  mov     ebx, 80070057h
0x18000b3df  jmp     loc_18000B47F
0x18000b3e4  mov     qword ptr [r9], 0
0x18000b3eb  test    rdx, rdx
0x18000b3ee  jz      short loc_18000B3FA
0x18000b3f0  mov     ebx, 80040110h
0x18000b3f5  jmp     loc_18000B47F
0x18000b3fa  mov     ecx, 38h ; '8'; Size
0x18000b3ff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b404  mov     rdi, rax
0x18000b407  test    rax, rax
0x18000b40a  jz      short loc_18000B47A
0x18000b40c  mov     qword ptr [rax+8], 0
0x18000b414  mov     ecx, 1
0x18000b419  mov     dword ptr [rax+10h], 0
0x18000b420  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x18000b428  mov     [rax+20h], ecx
0x18000b42b  mov     dword ptr [rax+24h], 0
0x18000b432  mov     qword ptr [rax+28h], 0
0x18000b43a  mov     qword ptr [rax+30h], 0
0x18000b442  lock add cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x18000b449  lea     rax, ??_7CPnpRebootHandler@@6B@; const CPnpRebootHandler::`vftable'
0x18000b450  mov     r8, rbx
0x18000b453  mov     [rdi], rax
0x18000b456  mov     rdx, rsi
0x18000b459  mov     rax, [rax]
0x18000b45c  mov     [rdi+10h], ecx
0x18000b45f  mov     rcx, rdi
0x18000b462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b467  mov     ebx, eax
0x18000b469  mov     rcx, [rdi]
0x18000b46c  mov     rax, [rcx+10h]
0x18000b470  mov     rcx, rdi
0x18000b473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b478  jmp     short loc_18000B47F
0x18000b47a  mov     ebx, 8007000Eh
0x18000b47f  mov     rsi, [rsp+28h+arg_8]
0x18000b484  mov     eax, ebx
0x18000b486  mov     rbx, [rsp+28h+arg_0]
0x18000b48b  add     rsp, 20h
0x18000b48f  pop     rdi
0x18000b490  retn
```
