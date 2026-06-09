# BamoWindowsMessageDeliveryProxy::GetHwnd(void)

- ea: `0x180023c90`
- end: `0x180023da1`
- name: `?GetHwnd@BamoWindowsMessageDeliveryProxy@@UEAA_KXZ`
- size: `273`
- prototype: `unsigned __int64 __fastcall(BamoWindowsMessageDeliveryProxy *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180023ac0`
- `0x18008cc98`

## callees

- `0x180023c90`
- `0x18008e194`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023cb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023ce2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023cfe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023cb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023ce2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023cfe`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall BamoWindowsMessageDeliveryProxy::GetHwnd(BamoWindowsMessageDeliveryProxy *this)
{
  __int64 v2; // rbx
  __int64 v3; // rsi
  const char *v4; // r9
  __int64 v5; // rax
  __int64 v6; // rsi
  __int64 v7; // rdi
  const char *v8; // r9
  signed __int32 v9; // edx
  bool v10; // sf
  signed __int32 v11; // edx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = *(_QWORD *)(*((_QWORD *)this + 3) + 24LL);
  v3 = *(_QWORD *)(v2 + 32);
  if ( *(_DWORD *)(v3 + 184) == GetCurrentThreadId() )
  {
    v2 = 0;
    v5 = 0;
  }
  else
  {
    _InterlockedIncrement((volatile signed __int32 *)(v2 + 8));
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v3 + 16) + 24LL))(*(_QWORD *)(v3 + 16));
    *(_DWORD *)(v3 + 184) = GetCurrentThreadId();
    v5 = v2;
  }
  v6 = *((_QWORD *)this + 5);
  if ( v2 )
  {
    v7 = *(_QWORD *)(v5 + 32);
    if ( *(_DWORD *)(v7 + 184) != GetCurrentThreadId() )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x9A3,
        (unsigned int)"d:\\os\\tools\\BamoCodegen\\Inc\\BamoConnection.inl",
        v8);
    *(_DWORD *)(v7 + 184) = 0;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v7 + 16) + 32LL))(*(_QWORD *)(v7 + 16));
  }
  if ( v2 )
  {
    v9 = _InterlockedExchangeAdd((volatile signed __int32 *)(v2 + 8), 0xFFFFFFFF);
    v10 = v9 - 1 < 0;
    v11 = v9 - 1;
    if ( v10 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x33,
        (unsigned int)"d:\\os\\tools\\BamoCodegen\\Inc\\BamoImplObject.inl",
        v4);
    if ( !v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 24LL))(v2);
  }
  return v6;
}

```

## disassembly

```asm
0x180023c90  mov     [rsp+arg_8], rbx
0x180023c95  mov     [rsp+arg_10], rsi
0x180023c9a  push    rdi
0x180023c9b  sub     rsp, 20h
0x180023c9f  mov     rdi, rcx
0x180023ca2  mov     rax, [rcx+18h]
0x180023ca6  mov     rbx, [rax+18h]
0x180023caa  mov     [rsp+28h+arg_0], 0
0x180023cb3  mov     rsi, [rbx+20h]
0x180023cb7  call    cs:__imp_GetCurrentThreadId
0x180023cbd  cmp     [rsi+0B8h], eax
0x180023cc3  jz      loc_180023D74
0x180023cc9  mov     [rsp+28h+arg_0], rbx
0x180023cce  lock inc dword ptr [rbx+8]
0x180023cd2  mov     rcx, [rsi+10h]
0x180023cd6  mov     rax, [rcx]
0x180023cd9  mov     rax, [rax+18h]
0x180023cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ce2  call    cs:__imp_GetCurrentThreadId
0x180023ce8  mov     [rsi+0B8h], eax
0x180023cee  mov     rax, rbx
0x180023cf1  mov     rsi, [rdi+28h]
0x180023cf5  test    rbx, rbx
0x180023cf8  jz      short loc_180023D31
0x180023cfa  mov     rdi, [rax+20h]
0x180023cfe  call    cs:__imp_GetCurrentThreadId
0x180023d04  cmp     [rdi+0B8h], eax
0x180023d0a  setnz   al
0x180023d0d  mov     rcx, [rsp+28h]; this
0x180023d12  test    al, al
0x180023d14  jnz     short loc_180023D7D
0x180023d16  mov     dword ptr [rdi+0B8h], 0
0x180023d20  mov     rcx, [rdi+10h]
0x180023d24  mov     rax, [rcx]
0x180023d27  mov     rax, [rax+20h]
0x180023d2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d30  nop
0x180023d31  test    rbx, rbx
0x180023d34  jz      short loc_180023D61
0x180023d36  or      edx, 0FFFFFFFFh
0x180023d39  lock xadd [rbx+8], edx
0x180023d3e  add     edx, 0FFFFFFFFh
0x180023d41  sets    al
0x180023d44  mov     rcx, [rsp+28h]; this
0x180023d49  test    al, al
0x180023d4b  jnz     short loc_180023D8F
0x180023d4d  test    edx, edx
0x180023d4f  jnz     short loc_180023D61
0x180023d51  mov     rdx, [rbx]
0x180023d54  mov     rcx, rbx
0x180023d57  mov     rax, [rdx+18h]
0x180023d5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d60  nop
0x180023d61  mov     rax, rsi
0x180023d64  mov     rbx, [rsp+28h+arg_8]
0x180023d69  mov     rsi, [rsp+28h+arg_10]
0x180023d6e  add     rsp, 20h
0x180023d72  pop     rdi
0x180023d73  retn
0x180023d74  xor     ebx, ebx
0x180023d76  xor     eax, eax
0x180023d78  jmp     loc_180023CF1
0x180023d7d  lea     r8, aDOsToolsBamoco_9; "d:\\os\\tools\\BamoCodegen\\Inc\\BamoCo"...
0x180023d84  mov     edx, 9A3h; void *
0x180023d89  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180023d8f  lea     r8, aDOsToolsBamoco_5; "d:\\os\\tools\\BamoCodegen\\Inc\\BamoIm"...
0x180023d96  mov     edx, 33h ; '3'; void *
0x180023d9b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
