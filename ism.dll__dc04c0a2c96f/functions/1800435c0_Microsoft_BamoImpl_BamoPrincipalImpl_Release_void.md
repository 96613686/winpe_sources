# Microsoft::BamoImpl::BamoPrincipalImpl::Release(void)

- ea: `0x1800435c0`
- end: `0x180043716`
- name: `?Release@BamoPrincipalImpl@BamoImpl@Microsoft@@UEAAKXZ`
- size: `342`
- prototype: `unsigned int __fastcall(Microsoft::BamoImpl::BamoPrincipalImpl *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800435c0`
- `0x180043720`
- `0x18004376c`
- `0x18008e194`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800435e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004360e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043645`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800435e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004360e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043645`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::BamoImpl::BamoPrincipalImpl::Release(Microsoft::BamoImpl::BamoPrincipalImpl *this)
{
  __int64 v2; // rdi
  Microsoft::BamoImpl::BamoImplObject *v3; // rbx
  __int64 v4; // rbp
  const char *v5; // r9
  signed __int32 v6; // edi
  bool v7; // sf
  unsigned __int32 v8; // edi
  bool v9; // bp
  __int64 v10; // r14
  const char *v11; // r9
  __int64 v13; // rax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = *((_QWORD *)this + 2);
  v3 = 0;
  v4 = *(_QWORD *)(v2 + 32);
  if ( *(_DWORD *)(v4 + 184) != GetCurrentThreadId() )
  {
    v3 = (Microsoft::BamoImpl::BamoImplObject *)v2;
    _InterlockedIncrement((volatile signed __int32 *)(v2 + 8));
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v4 + 16) + 24LL))(*(_QWORD *)(v4 + 16));
    *(_DWORD *)(v4 + 184) = GetCurrentThreadId();
  }
  v6 = _InterlockedExchangeAdd((volatile signed __int32 *)this + 2, 0xFFFFFFFF);
  v7 = v6 - 1 < 0;
  v8 = v6 - 1;
  if ( v7 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x33,
      (unsigned int)"d:\\os\\tools\\BamoCodegen\\Inc\\BamoImplObject.inl",
      v5);
  v9 = 0;
  if ( !v8 )
  {
    (*(void (__fastcall **)(Microsoft::BamoImpl::BamoPrincipalImpl *))(*(_QWORD *)this + 24LL))(this);
    v9 = Microsoft::BamoImpl::BamoPrincipalImpl::TryDisposeAndNotifyRemoteProxies(this);
  }
  if ( v3 )
  {
    v10 = *((_QWORD *)v3 + 4);
    if ( *(_DWORD *)(v10 + 184) != GetCurrentThreadId() )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x9A3,
        (unsigned int)"d:\\os\\tools\\BamoCodegen\\Inc\\BamoConnection.inl",
        v11);
    *(_DWORD *)(v10 + 184) = 0;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v10 + 16) + 32LL))(*(_QWORD *)(v10 + 16));
  }
  if ( v3 )
    Microsoft::BamoImpl::BamoImplObject::Release(v3);
  if ( v9 )
  {
    v13 = (*(__int64 (__fastcall **)(Microsoft::BamoImpl::BamoPrincipalImpl *))(*(_QWORD *)this + 56LL))(this);
    if ( v13 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 24LL))(v13, 1);
  }
  return v8;
}

```

## disassembly

```asm
0x1800435c0  mov     [rsp+arg_8], rbx
0x1800435c5  mov     [rsp+arg_10], rbp
0x1800435ca  push    rsi
0x1800435cb  push    rdi
0x1800435cc  push    r14
0x1800435ce  sub     rsp, 20h
0x1800435d2  mov     rsi, rcx
0x1800435d5  mov     rdi, [rcx+10h]
0x1800435d9  xor     ebx, ebx
0x1800435db  mov     [rsp+38h+arg_0], rbx
0x1800435e0  mov     rbp, [rdi+20h]
0x1800435e4  call    cs:__imp_GetCurrentThreadId
0x1800435ea  cmp     [rbp+0B8h], eax
0x1800435f0  jz      short loc_18004361A
0x1800435f2  mov     rbx, rdi
0x1800435f5  mov     [rsp+38h+arg_0], rbx
0x1800435fa  lock inc dword ptr [rdi+8]
0x1800435fe  mov     rcx, [rbp+10h]
0x180043602  mov     rax, [rcx]
0x180043605  mov     rax, [rax+18h]
0x180043609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004360e  call    cs:__imp_GetCurrentThreadId
0x180043614  mov     [rbp+0B8h], eax
0x18004361a  or      edi, 0FFFFFFFFh
0x18004361d  lock xadd [rsi+8], edi
0x180043622  add     edi, 0FFFFFFFFh
0x180043625  sets    al
0x180043628  mov     rcx, [rsp+38h]; this
0x18004362d  test    al, al
0x18004362f  jnz     loc_1800436F2
0x180043635  xor     bpl, bpl
0x180043638  test    edi, edi
0x18004363a  jz      short loc_1800436A6
0x18004363c  test    rbx, rbx
0x18004363f  jz      short loc_18004367E
0x180043641  mov     r14, [rbx+20h]
0x180043645  call    cs:__imp_GetCurrentThreadId
0x18004364b  cmp     [r14+0B8h], eax
0x180043652  setnz   dl
0x180043655  mov     rcx, [rsp+38h]; this
0x18004365a  test    dl, dl
0x18004365c  jnz     loc_180043704
0x180043662  mov     dword ptr [r14+0B8h], 0
0x18004366d  mov     rcx, [r14+10h]
0x180043671  mov     rax, [rcx]
0x180043674  mov     rax, [rax+20h]
0x180043678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004367d  nop
0x18004367e  test    rbx, rbx
0x180043681  jz      short loc_18004368C
0x180043683  mov     rcx, rbx; this
0x180043686  call    ?Release@BamoImplObject@BamoImpl@Microsoft@@UEAAKXZ; Microsoft::BamoImpl::BamoImplObject::Release(void)
0x18004368b  nop
0x18004368c  test    bpl, bpl
0x18004368f  jnz     short loc_1800436C5
0x180043691  mov     eax, edi
0x180043693  mov     rbx, [rsp+38h+arg_8]
0x180043698  mov     rbp, [rsp+38h+arg_10]
0x18004369d  add     rsp, 20h
0x1800436a1  pop     r14
0x1800436a3  pop     rdi
0x1800436a4  pop     rsi
0x1800436a5  retn
0x1800436a6  mov     rax, [rsi]
0x1800436a9  mov     rcx, rsi
0x1800436ac  mov     rax, [rax+18h]
0x1800436b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800436b5  mov     rcx, rsi; this
0x1800436b8  call    ?TryDisposeAndNotifyRemoteProxies@BamoPrincipalImpl@BamoImpl@Microsoft@@AEAA_NXZ; Microsoft::BamoImpl::BamoPrincipalImpl::TryDisposeAndNotifyRemoteProxies(void)
0x1800436bd  mov     bpl, al
0x1800436c0  jmp     loc_18004363C
0x1800436c5  mov     rax, [rsi]
0x1800436c8  mov     rcx, rsi
0x1800436cb  mov     rax, [rax+38h]
0x1800436cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800436d4  mov     r8, rax
0x1800436d7  test    rax, rax
0x1800436da  jz      short loc_180043691
0x1800436dc  mov     rcx, [rax]
0x1800436df  mov     rax, [rcx+18h]
0x1800436e3  mov     edx, 1
0x1800436e8  mov     rcx, r8
0x1800436eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800436f0  jmp     short loc_180043691
0x1800436f2  lea     r8, aDOsToolsBamoco_5; "d:\\os\\tools\\BamoCodegen\\Inc\\BamoIm"...
0x1800436f9  mov     edx, 33h ; '3'; void *
0x1800436fe  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180043704  lea     r8, aDOsToolsBamoco_9; "d:\\os\\tools\\BamoCodegen\\Inc\\BamoCo"...
0x18004370b  mov     edx, 9A3h; void *
0x180043710  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
