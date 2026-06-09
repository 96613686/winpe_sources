# CKSThunkPin::LocateFormatHandler(KSDATAFORMAT *)

- ea: `0x14000bea4`
- end: `0x14000bfbb`
- name: `?LocateFormatHandler@CKSThunkPin@@QEAAPEAUIKsWOW64FormatThunk@@PEATKSDATAFORMAT@@@Z`
- size: `279`
- prototype: `struct IKsWOW64FormatThunk *__fastcall(CKSThunkPin *__hidden this, union KSDATAFORMAT *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000bbec`
- `0x14000bd80`

## callees

- `0x1400041f0`
- `0x140004540`
- `0x14000be38`
- `0x14000bea4`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000bee4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000bee4`
- `ks!??0CBaseUnknown@@QEAA@PEAUIUnknown@@@Z` at `0x14000bf0b`
- `ks!??0CBaseUnknown@@QEAA@PEAUIUnknown@@@Z` at `0x14000bf0b`

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
0x14000bea4  mov     rax, rsp
0x14000bea7  mov     [rax+10h], rbx
0x14000beab  mov     [rax+18h], rsi
0x14000beaf  mov     [rax+8], rcx
0x14000beb3  push    rdi
0x14000beb4  sub     rsp, 20h
0x14000beb8  xor     r8d, r8d
0x14000bebb  lea     rcx, [rdx+30h]; struct _GUID *
0x14000bebf  mov     [rax+8], r8
0x14000bec3  mov     rsi, rdx
0x14000bec6  call    ?IsWellKnownFormatType@@YA_NAEBU_GUID@@@Z; IsWellKnownFormatType(_GUID const &)
0x14000becb  test    al, al
0x14000becd  jz      loc_14000BFA7
0x14000bed3  lea     ebx, [r8+78h]
0x14000bed7  mov     ecx, 200h; PoolType
0x14000bedc  mov     edx, ebx; NumberOfBytes
0x14000bede  mov     r8d, 774E434Bh; Tag
0x14000bee4  call    cs:__imp_ExAllocatePoolWithTag
0x14000beeb  nop     dword ptr [rax+rax+00h]
0x14000bef0  mov     rdi, rax
0x14000bef3  test    rax, rax
0x14000bef6  jz      short loc_14000BF6C
0x14000bef8  mov     r8d, ebx; Size
0x14000befb  xor     edx, edx; Val
0x14000befd  mov     rcx, rax; void *
0x14000bf00  call    memset
0x14000bf05  xor     edx, edx
0x14000bf07  lea     rcx, [rdi+8]
0x14000bf0b  call    cs:__imp_??0CBaseUnknown@@QEAA@PEAUIUnknown@@@Z; CBaseUnknown::CBaseUnknown(IUnknown *)
0x14000bf12  nop     dword ptr [rax+rax+00h]
0x14000bf17  lea     rcx, ??_7CVideoCaptureThunkHandler@@6B@; const CVideoCaptureThunkHandler::`vftable'
0x14000bf1e  lea     rax, ??_7CVideoCaptureThunkHandler@@6BINonDelegatedUnknown@@@; const CVideoCaptureThunkHandler::`vftable'{for `INonDelegatedUnknown'}
0x14000bf25  mov     [rdi], rcx
0x14000bf28  mov     [rdi+8], rax
0x14000bf2c  lea     rax, ??_7CVideoCaptureThunkHandler@@6BIIndirectedUnknown@@@; const CVideoCaptureThunkHandler::`vftable'{for `IIndirectedUnknown'}
0x14000bf33  mov     [rdi+10h], rax
0x14000bf37  mov     rax, [rcx+8]
0x14000bf3b  mov     rcx, rdi
0x14000bf3e  call    _guard_dispatch_icall
0x14000bf43  mov     rax, [rdi]
0x14000bf46  lea     r8, [rsp+28h+arg_0]
0x14000bf4b  lea     rdx, _GUID_bc709de8_e80f_41b5_a170_68600c571ef0
0x14000bf52  mov     rcx, rdi
0x14000bf55  mov     rax, [rax]
0x14000bf58  call    _guard_dispatch_icall
0x14000bf5d  mov     rax, [rdi]
0x14000bf60  mov     rcx, rdi
0x14000bf63  mov     rax, [rax+10h]
0x14000bf67  call    _guard_dispatch_icall
0x14000bf6c  mov     r8, [rsp+28h+arg_0]
0x14000bf71  test    r8, r8
0x14000bf74  jz      short loc_14000BFA7
0x14000bf76  mov     rax, [r8]
0x14000bf79  mov     rdx, rsi
0x14000bf7c  mov     rcx, r8
0x14000bf7f  mov     rax, [rax+18h]
0x14000bf83  call    _guard_dispatch_icall
0x14000bf88  test    eax, eax
0x14000bf8a  jns     short loc_14000BFA2
0x14000bf8c  mov     rcx, [rsp+28h+arg_0]
0x14000bf91  mov     rax, [rcx]
0x14000bf94  mov     rax, [rax+10h]
0x14000bf98  call    _guard_dispatch_icall
0x14000bf9d  xor     r8d, r8d
0x14000bfa0  jmp     short loc_14000BFA7
0x14000bfa2  mov     r8, [rsp+28h+arg_0]
0x14000bfa7  mov     rbx, [rsp+28h+arg_8]
0x14000bfac  mov     rax, r8
0x14000bfaf  mov     rsi, [rsp+28h+arg_10]
0x14000bfb4  add     rsp, 20h
0x14000bfb8  pop     rdi
0x14000bfb9  retn
```
