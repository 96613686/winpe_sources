# _CCompRC::LoadLibraryHelper_::_1_::catch$12

- ea: `0x140015d85`
- end: `0x140015ea1`
- name: `_CCompRC::LoadLibraryHelper_::_1_::catch$12`
- size: `284`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140001614`
- `0x14000e304`
- `0x140013f30`
- `0x140015d85`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x140015e34`
- `OLEAUT32!__imp_SetErrorInfo` at `0x140015e34`

## pseudocode

```c
__int64 __fastcall CCompRC::LoadLibraryHelper_::_1_::catch_12(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  __int64 v4; // rcx
  __int64 v5; // rcx
  IErrorInfo *v6; // rax
  IErrorInfo *v7; // rdi

  *(_QWORD *)(a2 + 168) = &Exception::`vftable';
  *(_QWORD *)(a2 + 176) = 0;
  *(_QWORD *)(a2 + 168) = &DelegatingException::`vftable';
  *(_QWORD *)(a2 + 184) = -1;
  v3 = *(_QWORD *)(a2 + 160);
  *(_QWORD *)(a2 + 104) = v3;
  *(_DWORD *)(a2 + 112) = 0;
  *(_DWORD *)(a2 + 112) = v3 != 0;
  Exception::HandlerState::SetupCatch((Exception::HandlerState *)(a2 + 152), 919);
  v4 = a2 + 168;
  if ( v3 )
    v4 = v3;
  *(_DWORD *)(a2 + 80) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = a2 + 168;
  if ( v3 )
    v5 = v3;
  v6 = (IErrorInfo *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 32LL))(v5);
  v7 = v6;
  if ( v6 )
  {
    SetErrorInfo(0, v6);
    ((void (__fastcall *)(IErrorInfo *))v7->lpVtbl->Release)(v7);
  }
  if ( v3 )
  {
    if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v3 + 80LL))(v3) )
      (**(void (__fastcall ***)(__int64, __int64))v3)(v3, 5);
    *(_DWORD *)(a2 + 112) = 0;
  }
  DelegatingException::~DelegatingException((DelegatingException *)(a2 + 168));
  return 0;
}

```

## disassembly

```asm
0x140015d85  mov     [rsp+arg_8], rdx
0x140015d8a  push    rbx
0x140015d8b  push    rbp
0x140015d8c  push    rsi
0x140015d8d  push    rdi
0x140015d8e  sub     rsp, 58h
0x140015d92  mov     rbp, rdx
0x140015d95  lea     rax, ??_7Exception@@6B@; const Exception::`vftable'
0x140015d9c  mov     [rbp+0A8h], rax
0x140015da3  and     qword ptr [rbp+0B0h], 0
0x140015dab  lea     rax, ??_7DelegatingException@@6B@; const DelegatingException::`vftable'
0x140015db2  mov     [rbp+0A8h], rax
0x140015db9  or      qword ptr [rbp+0B8h], 0FFFFFFFFFFFFFFFFh
0x140015dc1  mov     rbx, [rbp+0A0h]
0x140015dc8  mov     [rbp+68h], rbx
0x140015dcc  xor     esi, esi
0x140015dce  mov     [rbp+70h], esi
0x140015dd1  lea     eax, [rsi+1]
0x140015dd4  test    rbx, rbx
0x140015dd7  cmovnz  esi, eax
0x140015dda  mov     [rbp+70h], esi
0x140015ddd  mov     edx, 397h; int
0x140015de2  lea     rcx, [rbp+98h]; this
0x140015de9  call    ?SetupCatch@HandlerState@Exception@@QEAAXH_N@Z; Exception::HandlerState::SetupCatch(int,bool)
0x140015dee  lea     rcx, [rbp+0A8h]
0x140015df5  test    rbx, rbx
0x140015df8  cmovnz  rcx, rbx
0x140015dfc  mov     rax, [rcx]
0x140015dff  mov     rax, [rax+10h]
0x140015e03  call    cs:__guard_dispatch_icall_fptr
0x140015e09  mov     [rbp+50h], eax
0x140015e0c  lea     rcx, [rbp+0A8h]
0x140015e13  test    rbx, rbx
0x140015e16  cmovnz  rcx, rbx
0x140015e1a  mov     rax, [rcx]
0x140015e1d  mov     rax, [rax+20h]
0x140015e21  call    cs:__guard_dispatch_icall_fptr
0x140015e27  mov     rdi, rax
0x140015e2a  test    rax, rax
0x140015e2d  jz      short loc_140015E4B
0x140015e2f  mov     rdx, rax; perrinfo
0x140015e32  xor     ecx, ecx; dwReserved
0x140015e34  call    cs:__imp_SetErrorInfo
0x140015e3a  mov     rcx, [rdi]
0x140015e3d  mov     rax, [rcx+10h]
0x140015e41  mov     rcx, rdi
0x140015e44  call    cs:__guard_dispatch_icall_fptr
0x140015e4a  nop
0x140015e4b  test    esi, esi
0x140015e4d  jz      short loc_140015E80
0x140015e4f  test    rbx, rbx
0x140015e52  jz      short loc_140015E7C
0x140015e54  mov     rax, [rbx]
0x140015e57  mov     rcx, rbx
0x140015e5a  mov     rax, [rax+50h]
0x140015e5e  call    cs:__guard_dispatch_icall_fptr
0x140015e64  test    eax, eax
0x140015e66  jnz     short loc_140015E7C
0x140015e68  mov     rax, [rbx]
0x140015e6b  mov     edx, 5
0x140015e70  mov     rcx, rbx
0x140015e73  mov     rax, [rax]
0x140015e76  call    cs:__guard_dispatch_icall_fptr
0x140015e7c  and     dword ptr [rbp+70h], 0
0x140015e80  lea     rcx, [rbp+0A8h]; this
0x140015e87  call    ??1DelegatingException@@UEAA@XZ; DelegatingException::~DelegatingException(void)
0x140015e8c  nop
0x140015e8d  mov     rax, 0
0x140015e97  add     rsp, 58h
0x140015e9b  pop     rdi
0x140015e9c  pop     rsi
0x140015e9d  pop     rbp
0x140015e9e  pop     rbx
0x140015e9f  retn
```
