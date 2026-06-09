# CWinTaskClassFactoryT<CReAgentTaskHandler,1>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800018d0`
- end: `0x180001993`
- name: `?CreateInstance@?$CWinTaskClassFactoryT@VCReAgentTaskHandler@@$00@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `195`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180001008`
- `0x1800018d0`
- `0x180003010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CReAgentTaskHandler,1>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v6; // ebx
  _DWORD *v7; // rax
  _DWORD *v8; // rdi
  __int64 (__fastcall **v9)(_DWORD *, __int64, _QWORD *); // rax

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
        *((_QWORD *)v7 + 1) = 0;
        v7[4] = 0;
        *((_QWORD *)v7 + 3) = -1;
        *((_QWORD *)v7 + 5) = 0;
        *((_QWORD *)v7 + 6) = 0;
        v7[8] = 1;
        v7[9] = 0;
        _InterlockedAdd(&CWinTaskHandler::s_cInstances, 1u);
        v7[14] = 1;
        *(_QWORD *)v7 = &CReAgentTaskHandler::`vftable';
        v9 = *(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v7;
        v8[4] = 1;
        v6 = (*v9)(v8, a3, a4);
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
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
0x1800018d0  mov     [rsp+arg_0], rbx
0x1800018d5  mov     [rsp+arg_8], rsi
0x1800018da  push    rdi
0x1800018db  sub     rsp, 20h
0x1800018df  mov     rbx, r9
0x1800018e2  mov     rsi, r8
0x1800018e5  test    r9, r9
0x1800018e8  jnz     short loc_1800018F4
0x1800018ea  mov     ebx, 80070057h
0x1800018ef  jmp     loc_180001980
0x1800018f4  and     qword ptr [r9], 0
0x1800018f8  test    rdx, rdx
0x1800018fb  jz      short loc_180001904
0x1800018fd  mov     ebx, 80040110h
0x180001902  jmp     short loc_180001980
0x180001904  mov     ecx, 40h ; '@'; Size
0x180001909  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000190e  mov     rdi, rax
0x180001911  test    rax, rax
0x180001914  jz      short loc_18000197B
0x180001916  and     qword ptr [rax+8], 0
0x18000191b  mov     ecx, 1
0x180001920  and     dword ptr [rax+10h], 0
0x180001924  or      qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x180001929  and     qword ptr [rax+28h], 0
0x18000192e  and     qword ptr [rax+30h], 0
0x180001933  mov     [rax+20h], ecx
0x180001936  mov     dword ptr [rax+24h], 0
0x18000193d  lock add cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x180001944  mov     [rdi+38h], ecx
0x180001947  lea     rax, ??_7CReAgentTaskHandler@@6B@; const CReAgentTaskHandler::`vftable'
0x18000194e  mov     [rdi], rax
0x180001951  mov     r8, rbx
0x180001954  mov     rax, [rdi]
0x180001957  mov     rdx, rsi
0x18000195a  mov     [rdi+10h], ecx
0x18000195d  mov     rcx, rdi
0x180001960  mov     rax, [rax]
0x180001963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001968  mov     ebx, eax
0x18000196a  mov     rcx, [rdi]
0x18000196d  mov     rax, [rcx+10h]
0x180001971  mov     rcx, rdi
0x180001974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001979  jmp     short loc_180001980
0x18000197b  mov     ebx, 8007000Eh
0x180001980  mov     rsi, [rsp+28h+arg_8]
0x180001985  mov     eax, ebx
0x180001987  mov     rbx, [rsp+28h+arg_0]
0x18000198c  add     rsp, 20h
0x180001990  pop     rdi
0x180001991  retn
```
