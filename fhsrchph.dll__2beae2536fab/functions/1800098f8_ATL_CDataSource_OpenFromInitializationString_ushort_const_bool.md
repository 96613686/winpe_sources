# ATL::CDataSource::OpenFromInitializationString(ushort const *,bool)

- ea: `0x1800098f8`
- end: `0x1800099db`
- name: `?OpenFromInitializationString@CDataSource@ATL@@QEAAJPEBG_N@Z`
- size: `227`
- prototype: `__int64 __fastcall(ATL::CDataSource *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800099e4`

## callees

- `0x1800098f8`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009932`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009932`

## pseudocode

```c
__int64 __fastcall ATL::CDataSource::OpenFromInitializationString(ATL::CDataSource *this, const unsigned __int16 *a2)
{
  HRESULT v4; // ebx
  LPVOID v6; // [rsp+40h] [rbp-18h] BYREF

  v6 = 0;
  v4 = CoCreateInstance(
         &GUID_2206cdb0_19c1_11d1_89e0_00c04fd7a829,
         0,
         1u,
         &GUID_2206ccb1_19c1_11d1_89e0_00c04fd7a829,
         &v6);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, const unsigned __int16 *, GUID *, ATL::CDataSource *))(*(_QWORD *)v6 + 24LL))(
           v6,
           0,
           1,
           a2,
           &GUID_0c733a8b_2a1c_11ce_ade5_00aa0044773d,
           this);
    if ( v4 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 24LL))(*(_QWORD *)this);
      if ( v6 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
    }
    else if ( v6 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  else if ( v6 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800098f8  mov     r11, rsp
0x1800098fb  mov     [r11+18h], rbx
0x1800098ff  mov     [r11+20h], rsi
0x180009903  push    rdi
0x180009904  sub     rsp, 50h
0x180009908  mov     rsi, rdx
0x18000990b  mov     rdi, rcx
0x18000990e  mov     qword ptr [r11-18h], 0
0x180009916  lea     rax, [r11-18h]
0x18000991a  mov     [r11-38h], rax
0x18000991e  lea     r9, _GUID_2206ccb1_19c1_11d1_89e0_00c04fd7a829; riid
0x180009925  xor     edx, edx; pUnkOuter
0x180009927  lea     r8d, [rdx+1]; dwClsContext
0x18000992b  lea     rcx, _GUID_2206cdb0_19c1_11d1_89e0_00c04fd7a829; rclsid
0x180009932  call    cs:__imp_CoCreateInstance
0x180009938  mov     ebx, eax
0x18000993a  test    eax, eax
0x18000993c  jns     short loc_180009957
0x18000993e  mov     rcx, [rsp+58h+var_18]
0x180009943  test    rcx, rcx
0x180009946  jz      short loc_180009955
0x180009948  mov     rdx, [rcx]
0x18000994b  mov     rax, [rdx+10h]
0x18000994f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009954  nop
0x180009955  jmp     short loc_1800099C9
0x180009957  mov     rcx, [rsp+58h+var_18]
0x18000995c  mov     rax, [rcx]
0x18000995f  mov     [rsp+58h+var_30], rdi
0x180009964  lea     rdx, _GUID_0c733a8b_2a1c_11ce_ade5_00aa0044773d
0x18000996b  mov     [rsp+58h+var_38], rdx
0x180009970  mov     r9, rsi
0x180009973  xor     edx, edx
0x180009975  lea     r8d, [rdx+1]
0x180009979  mov     rax, [rax+18h]
0x18000997d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009982  mov     ebx, eax
0x180009984  test    eax, eax
0x180009986  jns     short loc_1800099A1
0x180009988  mov     rcx, [rsp+58h+var_18]
0x18000998d  test    rcx, rcx
0x180009990  jz      short loc_18000999F
0x180009992  mov     rdx, [rcx]
0x180009995  mov     rax, [rdx+10h]
0x180009999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000999e  nop
0x18000999f  jmp     short loc_1800099C9
0x1800099a1  mov     rcx, [rdi]
0x1800099a4  mov     rax, [rcx]
0x1800099a7  mov     rax, [rax+18h]
0x1800099ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099b0  mov     ebx, eax
0x1800099b2  mov     rcx, [rsp+58h+var_18]
0x1800099b7  test    rcx, rcx
0x1800099ba  jz      short loc_1800099C9
0x1800099bc  mov     rdx, [rcx]
0x1800099bf  mov     rax, [rdx+10h]
0x1800099c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099c8  nop
0x1800099c9  mov     eax, ebx
0x1800099cb  mov     rbx, [rsp+58h+arg_10]
0x1800099d0  mov     rsi, [rsp+58h+arg_18]
0x1800099d5  add     rsp, 50h
0x1800099d9  pop     rdi
0x1800099da  retn
```
