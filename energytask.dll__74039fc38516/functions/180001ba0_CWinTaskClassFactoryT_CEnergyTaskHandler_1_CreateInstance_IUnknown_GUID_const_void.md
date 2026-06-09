# CWinTaskClassFactoryT<CEnergyTaskHandler,1>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180001ba0`
- end: `0x180001c8d`
- name: `?CreateInstance@?$CWinTaskClassFactoryT@VCEnergyTaskHandler@@$00@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `237`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180001008`
- `0x180001ba0`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180001c42`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180001c42`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CEnergyTaskHandler,1>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v6; // ebx
  char *v7; // rax
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
      v7 = (char *)operator new(0x68u);
      v8 = v7;
      if ( v7 )
      {
        *((_QWORD *)v7 + 1) = 0;
        *((_DWORD *)v7 + 4) = 0;
        *((_QWORD *)v7 + 3) = -1;
        *((_DWORD *)v7 + 8) = 1;
        *((_DWORD *)v7 + 9) = 0;
        *((_QWORD *)v7 + 5) = 0;
        *((_QWORD *)v7 + 6) = 0;
        _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
        *((_QWORD *)v7 + 12) = 0;
        *(_QWORD *)v7 = &CEnergyTaskHandler::`vftable';
        InitializeCriticalSection((LPCRITICAL_SECTION)(v7 + 56));
        v9 = *(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v8;
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
0x180001ba0  mov     [rsp+arg_0], rbx
0x180001ba5  mov     [rsp+arg_8], rsi
0x180001baa  push    rdi
0x180001bab  sub     rsp, 20h
0x180001baf  mov     rbx, r9
0x180001bb2  mov     rsi, r8
0x180001bb5  test    r9, r9
0x180001bb8  jnz     short loc_180001BC4
0x180001bba  mov     ebx, 80070057h
0x180001bbf  jmp     loc_180001C7B
0x180001bc4  mov     qword ptr [r9], 0
0x180001bcb  test    rdx, rdx
0x180001bce  jz      short loc_180001BDA
0x180001bd0  mov     ebx, 80040110h
0x180001bd5  jmp     loc_180001C7B
0x180001bda  mov     ecx, 68h ; 'h'; Size
0x180001bdf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001be4  mov     rdi, rax
0x180001be7  test    rax, rax
0x180001bea  jz      loc_180001C76
0x180001bf0  mov     qword ptr [rax+8], 0
0x180001bf8  mov     dword ptr [rax+10h], 0
0x180001bff  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x180001c07  mov     dword ptr [rax+20h], 1
0x180001c0e  mov     dword ptr [rax+24h], 0
0x180001c15  mov     qword ptr [rax+28h], 0
0x180001c1d  mov     qword ptr [rax+30h], 0
0x180001c25  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180001c2c  lea     rax, ??_7CEnergyTaskHandler@@6B@; const CEnergyTaskHandler::`vftable'
0x180001c33  mov     qword ptr [rdi+60h], 0
0x180001c3b  lea     rcx, [rdi+38h]; lpCriticalSection
0x180001c3f  mov     [rdi], rax
0x180001c42  call    cs:__imp_InitializeCriticalSection
0x180001c48  mov     rax, [rdi]
0x180001c4b  mov     r8, rbx
0x180001c4e  mov     rdx, rsi
0x180001c51  mov     dword ptr [rdi+10h], 1
0x180001c58  mov     rcx, rdi
0x180001c5b  mov     rax, [rax]
0x180001c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c63  mov     ebx, eax
0x180001c65  mov     rcx, [rdi]
0x180001c68  mov     rax, [rcx+10h]
0x180001c6c  mov     rcx, rdi
0x180001c6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c74  jmp     short loc_180001C7B
0x180001c76  mov     ebx, 8007000Eh
0x180001c7b  mov     rsi, [rsp+28h+arg_8]
0x180001c80  mov     eax, ebx
0x180001c82  mov     rbx, [rsp+28h+arg_0]
0x180001c87  add     rsp, 20h
0x180001c8b  pop     rdi
0x180001c8c  retn
```
