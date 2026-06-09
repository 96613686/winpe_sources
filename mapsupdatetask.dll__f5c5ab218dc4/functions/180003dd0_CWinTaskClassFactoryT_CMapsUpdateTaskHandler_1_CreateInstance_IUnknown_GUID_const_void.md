# CWinTaskClassFactoryT<CMapsUpdateTaskHandler,1>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180003dd0`
- end: `0x180003eae`
- name: `?CreateInstance@?$CWinTaskClassFactoryT@VCMapsUpdateTaskHandler@@$00@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `222`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x180001c04`
- `0x180003dd0`
- `0x180009010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CMapsUpdateTaskHandler,1>::CreateInstance(
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
      v7 = operator new(0x68u);
      v7[1] = 0;
      *((_DWORD *)v7 + 4) = 0;
      v7[3] = -1;
      *((_DWORD *)v7 + 8) = 1;
      *((_DWORD *)v7 + 9) = 0;
      v7[5] = 0;
      v7[6] = 0;
      _InterlockedAdd(&CWinTaskHandler::s_cInstances, 1u);
      *v7 = &CMapsUpdateTaskHandler::`vftable';
      v7[7] = 0;
      v7[12] = 0;
      *((_DWORD *)v7 + 4) = 1;
      v6 = ((__int64 (__fastcall *)(_QWORD *, __int64, _QWORD *))CMapsUpdateTaskHandler::`vftable')(v7, a3, a4);
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
0x180003dd0  mov     [rsp+arg_0], rbx
0x180003dd5  mov     [rsp+arg_8], rsi
0x180003dda  push    rdi
0x180003ddb  sub     rsp, 20h
0x180003ddf  mov     rdi, r9
0x180003de2  mov     rsi, r8
0x180003de5  test    r9, r9
0x180003de8  jnz     short loc_180003DF4
0x180003dea  mov     edi, 80070057h
0x180003def  jmp     loc_180003E9C
0x180003df4  mov     qword ptr [r9], 0
0x180003dfb  test    rdx, rdx
0x180003dfe  jz      short loc_180003E0A
0x180003e00  mov     edi, 80040110h
0x180003e05  jmp     loc_180003E9C
0x180003e0a  mov     ecx, 68h ; 'h'; Size
0x180003e0f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003e14  mov     ecx, 1
0x180003e19  mov     [rsp+28h+arg_18], rax
0x180003e1e  mov     rbx, rax
0x180003e21  mov     qword ptr [rax+8], 0
0x180003e29  mov     dword ptr [rax+10h], 0
0x180003e30  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x180003e38  mov     [rax+20h], ecx
0x180003e3b  mov     dword ptr [rax+24h], 0
0x180003e42  mov     qword ptr [rax+28h], 0
0x180003e4a  mov     qword ptr [rax+30h], 0
0x180003e52  lock add cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x180003e59  lea     rax, ??_7CMapsUpdateTaskHandler@@6B@; const CMapsUpdateTaskHandler::`vftable'
0x180003e60  mov     r8, rdi
0x180003e63  mov     [rbx], rax
0x180003e66  mov     rdx, rsi
0x180003e69  mov     qword ptr [rbx+38h], 0
0x180003e71  mov     qword ptr [rbx+60h], 0
0x180003e79  mov     [rbx+10h], ecx
0x180003e7c  mov     rcx, rbx
0x180003e7f  mov     rax, cs:??_7CMapsUpdateTaskHandler@@6B@; const CMapsUpdateTaskHandler::`vftable'
0x180003e86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e8b  mov     edi, eax
0x180003e8d  mov     rcx, [rbx]
0x180003e90  mov     rax, [rcx+10h]
0x180003e94  mov     rcx, rbx
0x180003e97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e9c  mov     rbx, [rsp+28h+arg_0]
0x180003ea1  mov     eax, edi
0x180003ea3  mov     rsi, [rsp+28h+arg_8]
0x180003ea8  add     rsp, 20h
0x180003eac  pop     rdi
0x180003ead  retn
```
