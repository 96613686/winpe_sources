# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000a2fc`
- end: `0x18000a3df`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d530`

## callees

- `0x18000183c`
- `0x18000a2fc`
- `0x180027010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  _DWORD *v5; // rdi
  unsigned int v6; // r14d
  _DWORD *v7; // [rsp+40h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v5 = operator new(0x20u);
    v5[6] = 0;
    *((_QWORD *)v5 + 1) = 0;
    *((_QWORD *)v5 + 2) = 0;
    *(_QWORD *)v5 = &ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    v7 = v5;
  }
  catch ( ... )
  {
    v3 = a3;
    v6 = -2147024882;
    v5 = v7;
  }
  if ( v5 )
  {
    v6 = (**(__int64 (__fastcall ***)(void *, GUID *, _QWORD *))v5)(v5, &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33, v3);
    if ( v6 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v5 + 136LL))(v5, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x18000a2fc  mov     [rsp+arg_10], r8
0x18000a301  mov     [rsp+arg_8], rdx
0x18000a306  mov     [rsp+arg_0], rcx
0x18000a30b  push    rsi
0x18000a30c  push    rdi
0x18000a30d  push    r14
0x18000a30f  sub     rsp, 20h
0x18000a313  mov     rsi, r8
0x18000a316  test    r8, r8
0x18000a319  jnz     short loc_18000A325
0x18000a31b  mov     eax, 80004003h
0x18000a320  jmp     loc_18000A3D5
0x18000a325  mov     qword ptr [r8], 0
0x18000a32c  mov     r14d, 8007000Eh
0x18000a332  mov     dword ptr [rsp+38h+arg_8], r14d
0x18000a337  mov     [rsp+38h+arg_0], 0
0x18000a340  mov     ecx, 20h ; ' '; Size
0x18000a345  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a34a  mov     rdi, rax
0x18000a34d  mov     dword ptr [rax+18h], 0
0x18000a354  mov     qword ptr [rax+8], 0
0x18000a35c  mov     qword ptr [rax+10h], 0
0x18000a364  lea     rax, ??_7?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::`vftable'
0x18000a36b  mov     [rdi], rax
0x18000a36e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a375  mov     rax, [rcx]
0x18000a378  mov     rax, [rax+8]
0x18000a37c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a381  mov     [rsp+38h+arg_0], rdi
0x18000a386  jmp     short loc_18000A397
0x18000a388  mov     rsi, [rsp+38h+arg_10]
0x18000a38d  mov     r14d, dword ptr [rsp+38h+arg_8]
0x18000a392  mov     rdi, [rsp+38h+arg_0]
0x18000a397  test    rdi, rdi
0x18000a39a  jz      short loc_18000A3D2
0x18000a39c  mov     rax, [rdi]
0x18000a39f  mov     r8, rsi
0x18000a3a2  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x18000a3a9  mov     rcx, rdi
0x18000a3ac  mov     rax, [rax]
0x18000a3af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3b4  mov     r14d, eax
0x18000a3b7  test    eax, eax
0x18000a3b9  jz      short loc_18000A3D2
0x18000a3bb  mov     rdx, [rdi]
0x18000a3be  mov     rax, [rdx+88h]
0x18000a3c5  mov     edx, 1
0x18000a3ca  mov     rcx, rdi
0x18000a3cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3d2  mov     eax, r14d
0x18000a3d5  add     rsp, 20h
0x18000a3d9  pop     r14
0x18000a3db  pop     rdi
0x18000a3dc  pop     rsi
0x18000a3dd  retn
```
