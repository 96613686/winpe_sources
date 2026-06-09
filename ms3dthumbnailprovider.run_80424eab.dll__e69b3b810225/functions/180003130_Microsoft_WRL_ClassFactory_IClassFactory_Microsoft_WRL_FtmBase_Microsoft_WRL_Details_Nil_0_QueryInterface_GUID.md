# Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>::QueryInterface(_GUID const &,void * *)

- ea: `0x180003130`
- end: `0x180003199`
- name: `?QueryInterface@?$ClassFactory@UIClassFactory@@VFtmBase@WRL@Microsoft@@VNil@Details@34@$0A@@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `105`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800031a0`
- `0x1800031b0`

## callees

- `0x180002d40`
- `0x180003130`
- `0x18000b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  int CanCastTo; // ebx
  _QWORD *v4; // r8

  *a3 = 0;
  if ( !*a2
    && a2[1] == *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
    && a2[2] == *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4
    && a2[3] == *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4] )
  {
    *a3 = a1;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    return 0;
  }
  else
  {
    CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<6>,0,IClassFactory,IClassFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo();
    if ( CanCastTo >= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 8LL))(*v4);
  }
  return (unsigned int)CanCastTo;
}

```

## disassembly

```asm
0x180003130  push    rbx
0x180003132  sub     rsp, 20h
0x180003136  mov     qword ptr [r8], 0
0x18000313d  cmp     dword ptr [rdx], 0
0x180003140  jnz     short loc_180003176
0x180003142  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x180003148  cmp     [rdx+4], eax
0x18000314b  jnz     short loc_180003176
0x18000314d  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x180003153  cmp     [rdx+8], eax
0x180003156  jnz     short loc_180003176
0x180003158  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18000315e  cmp     [rdx+0Ch], eax
0x180003161  jnz     short loc_180003176
0x180003163  mov     [r8], rcx
0x180003166  mov     rax, [rcx]
0x180003169  mov     rax, [rax+8]
0x18000316d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003172  xor     ebx, ebx
0x180003174  jmp     short loc_180003191
0x180003176  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$05@WRL@Microsoft@@$0A@UIClassFactory@@U4@VFtmBase@23@VNil@Details@23@V6723@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<6>,0,IClassFactory,IClassFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(_GUID const &,void * *,bool *)
0x18000317b  mov     ebx, eax
0x18000317d  test    eax, eax
0x18000317f  js      short loc_180003191
0x180003181  mov     rcx, [r8]
0x180003184  mov     rdx, [rcx]
0x180003187  mov     rax, [rdx+8]
0x18000318b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003190  nop
0x180003191  mov     eax, ebx
0x180003193  add     rsp, 20h
0x180003197  pop     rbx
0x180003198  retn
```
