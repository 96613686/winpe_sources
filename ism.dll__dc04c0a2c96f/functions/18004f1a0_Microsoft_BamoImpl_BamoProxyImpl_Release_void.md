# Microsoft::BamoImpl::BamoProxyImpl::Release(void)

- ea: `0x18004f1a0`
- end: `0x18004f330`
- name: `?Release@BamoProxyImpl@BamoImpl@Microsoft@@UEAAKXZ`
- size: `400`
- prototype: `unsigned int __fastcall(Microsoft::BamoImpl::BamoProxyImpl *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180043720`
- `0x18004f1a0`
- `0x18008e194`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004f1d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004f201`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004f246`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004f1d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004f201`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004f246`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::BamoImpl::BamoProxyImpl::Release(
        Microsoft::BamoImpl::BamoProxyImpl *this,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  __int64 v5; // rdi
  __int64 v6; // rdi
  __int64 v7; // rbp
  __int64 v8; // rbx
  const char *v9; // r9
  signed __int32 v10; // edi
  bool v11; // sf
  int v12; // edi
  __int64 v13; // rsi
  const char *v14; // r9
  signed __int32 v15; // edx
  signed __int32 v16; // edx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v5 = *((_QWORD *)this + 2);
  if ( v5 )
  {
    v6 = *(_QWORD *)(v5 + 24);
    v7 = *(_QWORD *)(v6 + 32);
    if ( *(int *)(v7 + 8) <= 0 )
    {
      v12 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
      if ( v12 < 0 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x33,
          (unsigned int)"d:\\os\\tools\\BamoCodegen\\Inc\\BamoImplObject.inl",
          a4);
      if ( !v12 )
        (*(void (__fastcall **)(Microsoft::BamoImpl::BamoProxyImpl *))(*(_QWORD *)this + 24LL))(this);
    }
    else
    {
      v8 = 0;
      if ( *(_DWORD *)(v7 + 184) != GetCurrentThreadId() )
      {
        v8 = v6;
        if ( v6 )
          _InterlockedIncrement((volatile signed __int32 *)(v6 + 8));
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v7 + 16) + 24LL))(*(_QWORD *)(v7 + 16));
        *(_DWORD *)(v7 + 184) = GetCurrentThreadId();
      }
      v10 = _InterlockedExchangeAdd((volatile signed __int32 *)this + 2, 0xFFFFFFFF);
      v11 = v10 - 1 < 0;
      v12 = v10 - 1;
      if ( v11 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x33,
          (unsigned int)"d:\\os\\tools\\BamoCodegen\\Inc\\BamoImplObject.inl",
          v9);
      if ( !v12 )
        (*(void (__fastcall **)(Microsoft::BamoImpl::BamoProxyImpl *))(*(_QWORD *)this + 24LL))(this);
      if ( v8 )
      {
        v13 = *(_QWORD *)(v8 + 32);
        if ( *(_DWORD *)(v13 + 184) != GetCurrentThreadId() )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x9A3,
            (unsigned int)"d:\\os\\tools\\BamoCodegen\\Inc\\BamoConnection.inl",
            v14);
        *(_DWORD *)(v13 + 184) = 0;
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v13 + 16) + 32LL))(*(_QWORD *)(v13 + 16));
      }
      if ( v8 )
      {
        v15 = _InterlockedExchangeAdd((volatile signed __int32 *)(v8 + 8), 0xFFFFFFFF);
        v11 = v15 - 1 < 0;
        v16 = v15 - 1;
        if ( v11 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x33,
            (unsigned int)"d:\\os\\tools\\BamoCodegen\\Inc\\BamoImplObject.inl",
            v9);
        if ( !v16 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 24LL))(v8);
      }
    }
  }
  else
  {
    return Microsoft::BamoImpl::BamoImplObject::Release(this);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18004f1a0  push    rbx
0x18004f1a2  push    rbp
0x18004f1a3  push    rsi
0x18004f1a4  push    rdi
0x18004f1a5  sub     rsp, 28h
0x18004f1a9  mov     rsi, rcx
0x18004f1ac  mov     rdi, [rcx+10h]
0x18004f1b0  test    rdi, rdi
0x18004f1b3  jz      loc_18004F2DA
0x18004f1b9  mov     rdi, [rdi+18h]
0x18004f1bd  mov     rbp, [rdi+20h]
0x18004f1c1  cmp     dword ptr [rbp+8], 0
0x18004f1c5  jle     loc_18004F2BA
0x18004f1cb  xor     ebx, ebx
0x18004f1cd  mov     [rsp+48h+arg_0], rbx
0x18004f1d2  call    cs:__imp_GetCurrentThreadId
0x18004f1d8  cmp     [rbp+0B8h], eax
0x18004f1de  jz      short loc_18004F20D
0x18004f1e0  mov     rbx, rdi
0x18004f1e3  mov     [rsp+48h+arg_0], rbx
0x18004f1e8  test    rdi, rdi
0x18004f1eb  jz      short loc_18004F1F1
0x18004f1ed  lock inc dword ptr [rdi+8]
0x18004f1f1  mov     rcx, [rbp+10h]
0x18004f1f5  mov     rax, [rcx]
0x18004f1f8  mov     rax, [rax+18h]
0x18004f1fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f201  call    cs:__imp_GetCurrentThreadId
0x18004f207  mov     [rbp+0B8h], eax
0x18004f20d  or      ebp, 0FFFFFFFFh
0x18004f210  mov     edi, ebp
0x18004f212  lock xadd [rsi+8], edi
0x18004f217  add     edi, ebp
0x18004f219  sets    al
0x18004f21c  mov     rcx, [rsp+48h]; this
0x18004f221  test    al, al
0x18004f223  jnz     loc_18004F2FA
0x18004f229  test    edi, edi
0x18004f22b  jnz     short loc_18004F23D
0x18004f22d  mov     rax, [rsi]
0x18004f230  mov     rcx, rsi
0x18004f233  mov     rax, [rax+18h]
0x18004f237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f23c  nop
0x18004f23d  test    rbx, rbx
0x18004f240  jz      short loc_18004F27D
0x18004f242  mov     rsi, [rbx+20h]
0x18004f246  call    cs:__imp_GetCurrentThreadId
0x18004f24c  cmp     [rsi+0B8h], eax
0x18004f252  setnz   al
0x18004f255  mov     rcx, [rsp+48h]; this
0x18004f25a  test    al, al
0x18004f25c  jnz     loc_18004F30C
0x18004f262  mov     dword ptr [rsi+0B8h], 0
0x18004f26c  mov     rcx, [rsi+10h]
0x18004f270  mov     rax, [rcx]
0x18004f273  mov     rax, [rax+20h]
0x18004f277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f27c  nop
0x18004f27d  test    rbx, rbx
0x18004f280  jz      short loc_18004F2AF
0x18004f282  mov     edx, ebp
0x18004f284  lock xadd [rbx+8], edx
0x18004f289  add     edx, ebp
0x18004f28b  sets    al
0x18004f28e  mov     rcx, [rsp+48h]; this
0x18004f293  test    al, al
0x18004f295  jnz     loc_18004F31E
0x18004f29b  test    edx, edx
0x18004f29d  jnz     short loc_18004F2AF
0x18004f29f  mov     rax, [rbx]
0x18004f2a2  mov     rcx, rbx
0x18004f2a5  mov     rax, [rax+18h]
0x18004f2a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f2ae  nop
0x18004f2af  mov     eax, edi
0x18004f2b1  add     rsp, 28h
0x18004f2b5  pop     rdi
0x18004f2b6  pop     rsi
0x18004f2b7  pop     rbp
0x18004f2b8  pop     rbx
0x18004f2b9  retn
0x18004f2ba  or      ebp, 0FFFFFFFFh
0x18004f2bd  mov     edi, ebp
0x18004f2bf  lock xadd [rcx+8], edi
0x18004f2c4  add     edi, ebp
0x18004f2c6  js      short loc_18004F2E3
0x18004f2c8  test    edi, edi
0x18004f2ca  jnz     short loc_18004F2AF
0x18004f2cc  mov     rax, [rcx]
0x18004f2cf  mov     rax, [rax+18h]
0x18004f2d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f2d8  jmp     short loc_18004F2AF
0x18004f2da  call    ?Release@BamoImplObject@BamoImpl@Microsoft@@UEAAKXZ; Microsoft::BamoImpl::BamoImplObject::Release(void)
0x18004f2df  mov     edi, eax
0x18004f2e1  jmp     short loc_18004F2AF
0x18004f2e3  mov     rcx, [rsp+48h]; this
0x18004f2e8  lea     r8, aDOsToolsBamoco_5; "d:\\os\\tools\\BamoCodegen\\Inc\\BamoIm"...
0x18004f2ef  mov     edx, 33h ; '3'; void *
0x18004f2f4  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18004f2fa  lea     r8, aDOsToolsBamoco_5; "d:\\os\\tools\\BamoCodegen\\Inc\\BamoIm"...
0x18004f301  mov     edx, 33h ; '3'; void *
0x18004f306  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18004f30c  lea     r8, aDOsToolsBamoco_9; "d:\\os\\tools\\BamoCodegen\\Inc\\BamoCo"...
0x18004f313  mov     edx, 9A3h; void *
0x18004f318  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18004f31e  lea     r8, aDOsToolsBamoco_5; "d:\\os\\tools\\BamoCodegen\\Inc\\BamoIm"...
0x18004f325  mov     edx, 33h ; '3'; void *
0x18004f32a  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
