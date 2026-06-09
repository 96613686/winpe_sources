# CWinTaskClassFactoryT<CmCleanupWim,1>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180003ba0`
- end: `0x180003c6e`
- name: `?CreateInstance@?$CWinTaskClassFactoryT@VCmCleanupWim@@$00@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `206`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180001534`
- `0x180003ba0`
- `0x180009010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CmCleanupWim,1>::CreateInstance(
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
      *v7 = &CmCleanupWim::`vftable';
      *((_DWORD *)v7 + 4) = 1;
      v6 = ((__int64 (__fastcall *)(_QWORD *, __int64, _QWORD *))CmCleanupWim::`vftable')(v7, a3, a4);
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
0x180003ba0  mov     [rsp+arg_0], rbx
0x180003ba5  mov     [rsp+arg_8], rsi
0x180003baa  push    rdi
0x180003bab  sub     rsp, 20h
0x180003baf  mov     rdi, r9
0x180003bb2  mov     rsi, r8
0x180003bb5  test    r9, r9
0x180003bb8  jnz     short loc_180003BC4
0x180003bba  mov     edi, 80070057h
0x180003bbf  jmp     loc_180003C5C
0x180003bc4  mov     qword ptr [r9], 0
0x180003bcb  test    rdx, rdx
0x180003bce  jz      short loc_180003BDA
0x180003bd0  mov     edi, 80040110h
0x180003bd5  jmp     loc_180003C5C
0x180003bda  mov     ecx, 38h ; '8'; Size
0x180003bdf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003be4  mov     ecx, 1
0x180003be9  mov     [rsp+28h+arg_18], rax
0x180003bee  mov     rbx, rax
0x180003bf1  mov     qword ptr [rax+8], 0
0x180003bf9  mov     dword ptr [rax+10h], 0
0x180003c00  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x180003c08  mov     [rax+20h], ecx
0x180003c0b  mov     dword ptr [rax+24h], 0
0x180003c12  mov     qword ptr [rax+28h], 0
0x180003c1a  mov     qword ptr [rax+30h], 0
0x180003c22  lock add cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x180003c29  lea     rax, ??_7CmCleanupWim@@6B@; const CmCleanupWim::`vftable'
0x180003c30  mov     r8, rdi
0x180003c33  mov     [rbx], rax
0x180003c36  mov     rdx, rsi
0x180003c39  mov     [rbx+10h], ecx
0x180003c3c  mov     rcx, rbx
0x180003c3f  mov     rax, cs:??_7CmCleanupWim@@6B@; const CmCleanupWim::`vftable'
0x180003c46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c4b  mov     edi, eax
0x180003c4d  mov     rcx, [rbx]
0x180003c50  mov     rax, [rcx+10h]
0x180003c54  mov     rcx, rbx
0x180003c57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c5c  mov     rbx, [rsp+28h+arg_0]
0x180003c61  mov     eax, edi
0x180003c63  mov     rsi, [rsp+28h+arg_8]
0x180003c68  add     rsp, 20h
0x180003c6c  pop     rdi
0x180003c6d  retn
```
