# CKSThunkPin::LocateFormatHandler(KSDATAFORMAT *)

- ea: `0x14000af44`
- end: `0x14000b05b`
- name: `?LocateFormatHandler@CKSThunkPin@@QEAAPEAUIKsWOW64FormatThunk@@PEATKSDATAFORMAT@@@Z`
- size: `279`
- prototype: `struct IKsWOW64FormatThunk *__fastcall(CKSThunkPin *__hidden this, union KSDATAFORMAT *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000ac8c`
- `0x14000ae20`

## callees

- `0x140003770`
- `0x140003ac0`
- `0x14000aed8`
- `0x14000af44`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000af84`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000af84`
- `ks!??0CBaseUnknown@@QEAA@PEAUIUnknown@@@Z` at `0x14000afab`
- `ks!??0CBaseUnknown@@QEAA@PEAUIUnknown@@@Z` at `0x14000afab`

## pseudocode

```c
struct IKsWOW64FormatThunk *__fastcall CKSThunkPin::LocateFormatHandler(CKSThunkPin *this, union KSDATAFORMAT *a2)
{
  __int64 v3; // r8
  unsigned int v4; // ebx
  _QWORD *PoolWithTag; // rax
  _QWORD *v6; // rdi
  __int64 v8; // [rsp+30h] [rbp+8h] BYREF

  v8 = 0;
  if ( IsWellKnownFormatType(&a2->Specifier) )
  {
    v4 = v3 + 120;
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, (unsigned int)(v3 + 120), 0x774E434Bu);
    v6 = PoolWithTag;
    if ( PoolWithTag )
    {
      memset(PoolWithTag, 0, v4);
      CBaseUnknown::CBaseUnknown((CBaseUnknown *)(v6 + 1), 0);
      *v6 = &CVideoCaptureThunkHandler::`vftable';
      v6[1] = &CVideoCaptureThunkHandler::`vftable'{for `INonDelegatedUnknown'};
      v6[2] = &CVideoCaptureThunkHandler::`vftable'{for `IIndirectedUnknown'};
      CVideoCaptureThunkHandler::AddRef((CVideoCaptureThunkHandler *)v6);
      (*(void (__fastcall **)(_QWORD *, GUID *, __int64 *))*v6)(v6, &GUID_bc709de8_e80f_41b5_a170_68600c571ef0, &v8);
      (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
    }
    v3 = v8;
    if ( v8 )
    {
      if ( (*(int (__fastcall **)(__int64, union KSDATAFORMAT *))(*(_QWORD *)v8 + 24LL))(v8, a2) >= 0 )
      {
        return (struct IKsWOW64FormatThunk *)v8;
      }
      else
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
        return 0;
      }
    }
  }
  return (struct IKsWOW64FormatThunk *)v3;
}

```

## disassembly

```asm
0x14000af44  mov     rax, rsp
0x14000af47  mov     [rax+10h], rbx
0x14000af4b  mov     [rax+18h], rsi
0x14000af4f  mov     [rax+8], rcx
0x14000af53  push    rdi
0x14000af54  sub     rsp, 20h
0x14000af58  xor     r8d, r8d
0x14000af5b  lea     rcx, [rdx+30h]; struct _GUID *
0x14000af5f  mov     [rax+8], r8
0x14000af63  mov     rsi, rdx
0x14000af66  call    ?IsWellKnownFormatType@@YA_NAEBU_GUID@@@Z; IsWellKnownFormatType(_GUID const &)
0x14000af6b  test    al, al
0x14000af6d  jz      loc_14000B047
0x14000af73  lea     ebx, [r8+78h]
0x14000af77  mov     ecx, 200h; PoolType
0x14000af7c  mov     edx, ebx; NumberOfBytes
0x14000af7e  mov     r8d, 774E434Bh; Tag
0x14000af84  call    cs:__imp_ExAllocatePoolWithTag
0x14000af8b  nop     dword ptr [rax+rax+00h]
0x14000af90  mov     rdi, rax
0x14000af93  test    rax, rax
0x14000af96  jz      short loc_14000B00C
0x14000af98  mov     r8d, ebx; Size
0x14000af9b  xor     edx, edx; Val
0x14000af9d  mov     rcx, rax; void *
0x14000afa0  call    memset
0x14000afa5  xor     edx, edx
0x14000afa7  lea     rcx, [rdi+8]
0x14000afab  call    cs:__imp_??0CBaseUnknown@@QEAA@PEAUIUnknown@@@Z; CBaseUnknown::CBaseUnknown(IUnknown *)
0x14000afb2  nop     dword ptr [rax+rax+00h]
0x14000afb7  lea     rcx, ??_7CVideoCaptureThunkHandler@@6B@; const CVideoCaptureThunkHandler::`vftable'
0x14000afbe  lea     rax, ??_7CVideoCaptureThunkHandler@@6BINonDelegatedUnknown@@@; const CVideoCaptureThunkHandler::`vftable'{for `INonDelegatedUnknown'}
0x14000afc5  mov     [rdi], rcx
0x14000afc8  mov     [rdi+8], rax
0x14000afcc  lea     rax, ??_7CVideoCaptureThunkHandler@@6BIIndirectedUnknown@@@; const CVideoCaptureThunkHandler::`vftable'{for `IIndirectedUnknown'}
0x14000afd3  mov     [rdi+10h], rax
0x14000afd7  mov     rax, [rcx+8]
0x14000afdb  mov     rcx, rdi
0x14000afde  call    _guard_dispatch_icall
0x14000afe3  mov     rax, [rdi]
0x14000afe6  lea     r8, [rsp+28h+arg_0]
0x14000afeb  lea     rdx, _GUID_bc709de8_e80f_41b5_a170_68600c571ef0
0x14000aff2  mov     rcx, rdi
0x14000aff5  mov     rax, [rax]
0x14000aff8  call    _guard_dispatch_icall
0x14000affd  mov     rax, [rdi]
0x14000b000  mov     rcx, rdi
0x14000b003  mov     rax, [rax+10h]
0x14000b007  call    _guard_dispatch_icall
0x14000b00c  mov     r8, [rsp+28h+arg_0]
0x14000b011  test    r8, r8
0x14000b014  jz      short loc_14000B047
0x14000b016  mov     rax, [r8]
0x14000b019  mov     rdx, rsi
0x14000b01c  mov     rcx, r8
0x14000b01f  mov     rax, [rax+18h]
0x14000b023  call    _guard_dispatch_icall
0x14000b028  test    eax, eax
0x14000b02a  jns     short loc_14000B042
0x14000b02c  mov     rcx, [rsp+28h+arg_0]
0x14000b031  mov     rax, [rcx]
0x14000b034  mov     rax, [rax+10h]
0x14000b038  call    _guard_dispatch_icall
0x14000b03d  xor     r8d, r8d
0x14000b040  jmp     short loc_14000B047
0x14000b042  mov     r8, [rsp+28h+arg_0]
0x14000b047  mov     rbx, [rsp+28h+arg_8]
0x14000b04c  mov     rax, r8
0x14000b04f  mov     rsi, [rsp+28h+arg_10]
0x14000b054  add     rsp, 20h
0x14000b058  pop     rdi
0x14000b059  retn
```
