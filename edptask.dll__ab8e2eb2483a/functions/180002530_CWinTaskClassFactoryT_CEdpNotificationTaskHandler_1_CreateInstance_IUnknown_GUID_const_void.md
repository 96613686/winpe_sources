# CWinTaskClassFactoryT<CEdpNotificationTaskHandler,1>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180002530`
- end: `0x18000260b`
- name: `?CreateInstance@?$CWinTaskClassFactoryT@VCEdpNotificationTaskHandler@@$00@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `219`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180001404`
- `0x180002530`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CEdpNotificationTaskHandler,1>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v6; // edi
  _QWORD *v7; // rax
  _QWORD *v8; // rbx

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
        v7[4] = 1;
        v7[5] = 0;
        v7[6] = 0;
        _InterlockedAdd(&CWinTaskHandler::s_cInstances, 1u);
        *v7 = &CEdpNotificationTaskHandler::`vftable';
        *((_DWORD *)v7 + 4) = 1;
        v6 = ((__int64 (__fastcall *)(_QWORD *, __int64, _QWORD *))CEdpNotificationTaskHandler::`vftable')(v7, a3, a4);
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
0x180002530  mov     [rsp+arg_0], rbx
0x180002535  mov     [rsp+arg_8], rsi
0x18000253a  push    rdi
0x18000253b  sub     rsp, 20h
0x18000253f  mov     rdi, r9
0x180002542  mov     rsi, r8
0x180002545  test    r9, r9
0x180002548  jnz     short loc_180002554
0x18000254a  mov     edi, 80070057h
0x18000254f  jmp     loc_1800025F9
0x180002554  mov     qword ptr [r9], 0
0x18000255b  test    rdx, rdx
0x18000255e  jz      short loc_18000256A
0x180002560  mov     edi, 80040110h
0x180002565  jmp     loc_1800025F9
0x18000256a  mov     ecx, 38h ; '8'; Size
0x18000256f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002574  mov     [rsp+28h+arg_18], rax
0x180002579  mov     rbx, rax
0x18000257c  test    rax, rax
0x18000257f  jz      short loc_1800025F4
0x180002581  mov     qword ptr [rax+8], 0
0x180002589  mov     ecx, 1
0x18000258e  mov     dword ptr [rax+10h], 0
0x180002595  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x18000259d  mov     [rax+20h], ecx
0x1800025a0  mov     dword ptr [rax+24h], 0
0x1800025a7  mov     qword ptr [rax+28h], 0
0x1800025af  mov     qword ptr [rax+30h], 0
0x1800025b7  lock add cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x1800025be  lea     rax, ??_7CEdpNotificationTaskHandler@@6B@; const CEdpNotificationTaskHandler::`vftable'
0x1800025c5  mov     [rbx], rax
0x1800025c8  test    rbx, rbx
0x1800025cb  jz      short loc_1800025F4
0x1800025cd  mov     rax, [rax]
0x1800025d0  mov     r8, rdi
0x1800025d3  mov     [rbx+10h], ecx
0x1800025d6  mov     rdx, rsi
0x1800025d9  mov     rcx, rbx
0x1800025dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025e1  mov     rdx, [rbx]
0x1800025e4  mov     edi, eax
0x1800025e6  mov     rcx, rbx
0x1800025e9  mov     rax, [rdx+10h]
0x1800025ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025f2  jmp     short loc_1800025F9
0x1800025f4  mov     edi, 8007000Eh
0x1800025f9  mov     rbx, [rsp+28h+arg_0]
0x1800025fe  mov     eax, edi
0x180002600  mov     rsi, [rsp+28h+arg_8]
0x180002605  add     rsp, 20h
0x180002609  pop     rdi
0x18000260a  retn
```
