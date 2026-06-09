# CWinTaskClassFactoryT<CMapsToastTaskHandler,1>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180002e00`
- end: `0x180002ece`
- name: `?CreateInstance@?$CWinTaskClassFactoryT@VCMapsToastTaskHandler@@$00@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `206`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x1800015d4`
- `0x180002e00`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CMapsToastTaskHandler,1>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v6; // edi
  _QWORD *v7; // rbx

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
      v7[1] = 0;
      *((_DWORD *)v7 + 4) = 0;
      v7[3] = -1;
      *((_DWORD *)v7 + 8) = 1;
      *((_DWORD *)v7 + 9) = 0;
      v7[5] = 0;
      v7[6] = 0;
      _InterlockedAdd(&CWinTaskHandler::s_cInstances, 1u);
      *v7 = &CMapsToastTaskHandler::`vftable';
      *((_DWORD *)v7 + 4) = 1;
      v6 = ((__int64 (__fastcall *)(_QWORD *, __int64, _QWORD *))CMapsToastTaskHandler::`vftable')(v7, a3, a4);
      (*(void (__fastcall **)(_QWORD *))(*v7 + 16LL))(v7);
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
0x180002e00  mov     [rsp+arg_0], rbx
0x180002e05  mov     [rsp+arg_8], rsi
0x180002e0a  push    rdi
0x180002e0b  sub     rsp, 20h
0x180002e0f  mov     rdi, r9
0x180002e12  mov     rsi, r8
0x180002e15  test    r9, r9
0x180002e18  jnz     short loc_180002E24
0x180002e1a  mov     edi, 80070057h
0x180002e1f  jmp     loc_180002EBC
0x180002e24  mov     qword ptr [r9], 0
0x180002e2b  test    rdx, rdx
0x180002e2e  jz      short loc_180002E3A
0x180002e30  mov     edi, 80040110h
0x180002e35  jmp     loc_180002EBC
0x180002e3a  mov     ecx, 38h ; '8'; Size
0x180002e3f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002e44  mov     ecx, 1
0x180002e49  mov     [rsp+28h+arg_18], rax
0x180002e4e  mov     rbx, rax
0x180002e51  mov     qword ptr [rax+8], 0
0x180002e59  mov     dword ptr [rax+10h], 0
0x180002e60  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x180002e68  mov     [rax+20h], ecx
0x180002e6b  mov     dword ptr [rax+24h], 0
0x180002e72  mov     qword ptr [rax+28h], 0
0x180002e7a  mov     qword ptr [rax+30h], 0
0x180002e82  lock add cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x180002e89  lea     rax, ??_7CMapsToastTaskHandler@@6B@; const CMapsToastTaskHandler::`vftable'
0x180002e90  mov     r8, rdi
0x180002e93  mov     [rbx], rax
0x180002e96  mov     rdx, rsi
0x180002e99  mov     [rbx+10h], ecx
0x180002e9c  mov     rcx, rbx
0x180002e9f  mov     rax, cs:??_7CMapsToastTaskHandler@@6B@; const CMapsToastTaskHandler::`vftable'
0x180002ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002eab  mov     edi, eax
0x180002ead  mov     rcx, [rbx]
0x180002eb0  mov     rax, [rcx+10h]
0x180002eb4  mov     rcx, rbx
0x180002eb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ebc  mov     rbx, [rsp+28h+arg_0]
0x180002ec1  mov     eax, edi
0x180002ec3  mov     rsi, [rsp+28h+arg_8]
0x180002ec8  add     rsp, 20h
0x180002ecc  pop     rdi
0x180002ecd  retn
```
