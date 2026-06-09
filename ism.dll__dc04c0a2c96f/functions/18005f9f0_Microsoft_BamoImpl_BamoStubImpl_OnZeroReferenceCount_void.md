# Microsoft::BamoImpl::BamoStubImpl::OnZeroReferenceCount(void)

- ea: `0x18005f9f0`
- end: `0x18005fade`
- name: `?OnZeroReferenceCount@BamoStubImpl@BamoImpl@Microsoft@@EEAAXXZ`
- size: `238`
- prototype: `void __fastcall(Microsoft::BamoImpl::BamoStubImpl *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18005f9f0`
- `0x18008e194`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005fa1e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005fa46`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005fab6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005fa1e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005fa46`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005fab6`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Microsoft::BamoImpl::BamoStubImpl::OnZeroReferenceCount(Microsoft::BamoImpl::BamoStubImpl *this)
{
  __int64 v2; // rdi
  __int64 v3; // rsi
  int v4; // ebx
  const char *v5; // r9
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 4) + 24LL) + 32LL);
  v3 = 0;
  if ( v2 && *(_DWORD *)(v2 + 184) == GetCurrentThreadId() && !*(_DWORD *)(v2 + 188) )
  {
    v3 = v2;
    v4 = *(_DWORD *)(v2 + 184);
    if ( v4 != GetCurrentThreadId() )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x9A3,
        (unsigned int)"d:\\os\\tools\\BamoCodegen\\Inc\\BamoConnection.inl",
        v5);
    *(_DWORD *)(v2 + 184) = 0;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v2 + 16) + 32LL))(*(_QWORD *)(v2 + 16));
  }
  else
  {
    v2 = 0;
  }
  v6 = (*(__int64 (__fastcall **)(Microsoft::BamoImpl::BamoStubImpl *))(*(_QWORD *)this + 32LL))(this);
  v8 = v6;
  if ( v6 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 24LL))(v6, 1);
  if ( v3 )
  {
    (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v2 + 16) + 24LL))(*(_QWORD *)(v2 + 16), v7, v8);
    *(_DWORD *)(v2 + 184) = GetCurrentThreadId();
  }
}

```

## disassembly

```asm
0x18005f9f0  push    rbx
0x18005f9f2  push    rsi
0x18005f9f3  push    rdi
0x18005f9f4  push    r14
0x18005f9f6  sub     rsp, 38h
0x18005f9fa  mov     r14, rcx
0x18005f9fd  mov     [rsp+58h+var_30], 0
0x18005fa06  mov     rax, [rcx+20h]
0x18005fa0a  mov     rdx, [rax+18h]
0x18005fa0e  mov     rdi, [rdx+20h]
0x18005fa12  xor     esi, esi
0x18005fa14  mov     [rsp+58h+var_38], rsi
0x18005fa19  test    rdi, rdi
0x18005fa1c  jz      short loc_18005FA2C
0x18005fa1e  call    cs:__imp_GetCurrentThreadId
0x18005fa24  cmp     [rdi+0B8h], eax
0x18005fa2a  jz      short loc_18005FA30
0x18005fa2c  xor     edi, edi
0x18005fa2e  jmp     short loc_18005FA75
0x18005fa30  cmp     [rdi+0BCh], esi
0x18005fa36  ja      short loc_18005FA2C
0x18005fa38  mov     rsi, rdi
0x18005fa3b  mov     [rsp+58h+var_38], rdi
0x18005fa40  mov     ebx, [rdi+0B8h]
0x18005fa46  call    cs:__imp_GetCurrentThreadId
0x18005fa4c  cmp     ebx, eax
0x18005fa4e  setnz   al
0x18005fa51  mov     rcx, [rsp+58h]; this
0x18005fa56  test    al, al
0x18005fa58  jnz     short loc_18005FACC
0x18005fa5a  mov     dword ptr [rdi+0B8h], 0
0x18005fa64  mov     rcx, [rdi+10h]
0x18005fa68  mov     rax, [rcx]
0x18005fa6b  mov     rax, [rax+20h]
0x18005fa6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fa74  nop
0x18005fa75  mov     rax, [r14]
0x18005fa78  mov     rcx, r14
0x18005fa7b  mov     rax, [rax+20h]
0x18005fa7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fa84  mov     r8, rax
0x18005fa87  test    rax, rax
0x18005fa8a  jz      short loc_18005FAA1
0x18005fa8c  mov     rcx, [rax]
0x18005fa8f  mov     rax, [rcx+18h]
0x18005fa93  mov     edx, 1
0x18005fa98  mov     rcx, r8
0x18005fa9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005faa0  nop
0x18005faa1  test    rsi, rsi
0x18005faa4  jz      short loc_18005FAC2
0x18005faa6  mov     rcx, [rdi+10h]
0x18005faaa  mov     rax, [rcx]
0x18005faad  mov     rax, [rax+18h]
0x18005fab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fab6  call    cs:__imp_GetCurrentThreadId
0x18005fabc  mov     [rdi+0B8h], eax
0x18005fac2  add     rsp, 38h
0x18005fac6  pop     r14
0x18005fac8  pop     rdi
0x18005fac9  pop     rsi
0x18005faca  pop     rbx
0x18005facb  retn
0x18005facc  lea     r8, aDOsToolsBamoco_9; "d:\\os\\tools\\BamoCodegen\\Inc\\BamoCo"...
0x18005fad3  mov     edx, 9A3h; void *
0x18005fad8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
