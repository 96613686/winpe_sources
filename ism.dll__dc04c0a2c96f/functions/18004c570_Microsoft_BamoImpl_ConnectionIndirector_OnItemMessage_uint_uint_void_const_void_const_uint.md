# Microsoft::BamoImpl::ConnectionIndirector::OnItemMessage(uint,uint,void const *,void const *,uint)

- ea: `0x18004c570`
- end: `0x18004c724`
- name: `?OnItemMessage@ConnectionIndirector@BamoImpl@Microsoft@@UEAAJIIPEBX0I@Z`
- size: `436`
- prototype: `__int64 __fastcall(Microsoft::BamoImpl::ConnectionIndirector *__hidden this, unsigned int, unsigned int, const void *, const void *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180049530`
- `0x18004c570`
- `0x18008e194`
- `0x18008ead4`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c59d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c5c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c62f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c59d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c5c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c62f`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::BamoImpl::ConnectionIndirector::OnItemMessage(
        Microsoft::BamoImpl::ConnectionIndirector *this,
        int a2,
        int a3,
        const void *a4,
        const void *a5,
        unsigned int a6)
{
  char *v10; // rbx
  __int64 v11; // rbp
  const char *v12; // r9
  __int64 v13; // rsi
  _DWORD *i; // rax
  unsigned int v15; // edi
  __int64 v16; // rsi
  const char *v17; // r9
  signed __int32 v18; // edx
  bool v19; // sf
  signed __int32 v20; // edx
  int v22; // eax
  int v23; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v10 = 0;
  v11 = *((_QWORD *)this + 2);
  if ( *(_DWORD *)(v11 + 184) != GetCurrentThreadId() )
  {
    v10 = (char *)this - 16;
    _InterlockedIncrement((volatile signed __int32 *)this - 2);
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v11 + 16) + 24LL))(*(_QWORD *)(v11 + 16));
    *(_DWORD *)(v11 + 184) = GetCurrentThreadId();
  }
  v13 = *((_QWORD *)this + 2);
  if ( *(_QWORD *)(v13 + 64) )
  {
    for ( i = *(_DWORD **)(v13 + 192); i != *(_DWORD **)(v13 + 200); ++i )
    {
      if ( *i == a3 )
        goto LABEL_18;
    }
    if ( a4 )
    {
      *(_DWORD *)(v13 + 32) = a2;
      v15 = (*(__int64 (__fastcall **)(const void *, const void *, _QWORD))(*(_QWORD *)a4 + 32LL))(a4, a5, a6);
      *(_DWORD *)(v13 + 32) = 0;
    }
    else
    {
      v22 = Microsoft::BamoImpl::BaseBamoConnectionImpl::TrackError(
              (Microsoft::BamoImpl::BaseBamoConnectionImpl *)v13,
              -2018375668,
              0);
      v15 = v22;
      if ( v22 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x76E,
          (unsigned int)"d:\\os\\tools\\BamoCodegen\\Inc\\BamoConnection.inl",
          (const char *)(unsigned int)v22,
          v23);
    }
  }
  else
  {
LABEL_18:
    v15 = 0;
  }
  if ( v10 )
  {
    v16 = *((_QWORD *)v10 + 4);
    if ( *(_DWORD *)(v16 + 184) != GetCurrentThreadId() )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x9A3,
        (unsigned int)"d:\\os\\tools\\BamoCodegen\\Inc\\BamoConnection.inl",
        v17);
    *(_DWORD *)(v16 + 184) = 0;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v16 + 16) + 32LL))(*(_QWORD *)(v16 + 16));
  }
  if ( v10 )
  {
    v18 = _InterlockedExchangeAdd((volatile signed __int32 *)v10 + 2, 0xFFFFFFFF);
    v19 = v18 - 1 < 0;
    v20 = v18 - 1;
    if ( v19 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x33,
        (unsigned int)"d:\\os\\tools\\BamoCodegen\\Inc\\BamoImplObject.inl",
        v12);
    if ( !v20 )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 24LL))(v10);
  }
  return v15;
}

```

## disassembly

```asm
0x18004c570  mov     [rsp+arg_8], rbx
0x18004c575  mov     [rsp+arg_10], rbp
0x18004c57a  push    rsi
0x18004c57b  push    rdi
0x18004c57c  push    r12
0x18004c57e  push    r14
0x18004c580  push    r15; int
0x18004c582  sub     rsp, 20h
0x18004c586  mov     r14, r9
0x18004c589  mov     r15d, r8d
0x18004c58c  mov     r12d, edx
0x18004c58f  mov     rsi, rcx
0x18004c592  xor     ebx, ebx
0x18004c594  mov     [rsp+48h+arg_0], rbx
0x18004c599  mov     rbp, [rcx+10h]
0x18004c59d  call    cs:__imp_GetCurrentThreadId
0x18004c5a3  cmp     [rbp+0B8h], eax
0x18004c5a9  jz      short loc_18004C5D4
0x18004c5ab  lea     rbx, [rsi-10h]
0x18004c5af  mov     [rsp+48h+arg_0], rbx
0x18004c5b4  lock inc dword ptr [rsi-8]
0x18004c5b8  mov     rcx, [rbp+10h]
0x18004c5bc  mov     rax, [rcx]
0x18004c5bf  mov     rax, [rax+18h]
0x18004c5c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c5c8  call    cs:__imp_GetCurrentThreadId
0x18004c5ce  mov     [rbp+0B8h], eax
0x18004c5d4  mov     rsi, [rsi+10h]
0x18004c5d8  cmp     qword ptr [rsi+40h], 0
0x18004c5dd  jz      loc_18004C6C1
0x18004c5e3  mov     rax, [rsi+0C0h]
0x18004c5ea  cmp     rax, [rsi+0C8h]
0x18004c5f1  jnz     loc_18004C6B3
0x18004c5f7  test    r14, r14
0x18004c5fa  jz      loc_18004C6C8
0x18004c600  mov     [rsi+20h], r12d
0x18004c604  mov     rax, [r14]
0x18004c607  mov     r8d, [rsp+48h+arg_28]
0x18004c60c  mov     rdx, [rsp+48h+arg_20]
0x18004c611  mov     rcx, r14
0x18004c614  mov     rax, [rax+20h]
0x18004c618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c61d  mov     edi, eax
0x18004c61f  mov     dword ptr [rsi+20h], 0
0x18004c626  test    rbx, rbx
0x18004c629  jz      short loc_18004C666
0x18004c62b  mov     rsi, [rbx+20h]
0x18004c62f  call    cs:__imp_GetCurrentThreadId
0x18004c635  cmp     [rsi+0B8h], eax
0x18004c63b  setnz   al
0x18004c63e  mov     rcx, [rsp+48h]; this
0x18004c643  test    al, al
0x18004c645  jnz     loc_18004C700
0x18004c64b  mov     dword ptr [rsi+0B8h], 0
0x18004c655  mov     rcx, [rsi+10h]
0x18004c659  mov     rax, [rcx]
0x18004c65c  mov     rax, [rax+20h]
0x18004c660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c665  nop
0x18004c666  test    rbx, rbx
0x18004c669  jz      short loc_18004C69A
0x18004c66b  or      edx, 0FFFFFFFFh
0x18004c66e  lock xadd [rbx+8], edx
0x18004c673  add     edx, 0FFFFFFFFh
0x18004c676  sets    al
0x18004c679  mov     rcx, [rsp+48h]; this
0x18004c67e  test    al, al
0x18004c680  jnz     loc_18004C712
0x18004c686  test    edx, edx
0x18004c688  jnz     short loc_18004C69A
0x18004c68a  mov     rcx, [rbx]
0x18004c68d  mov     rax, [rcx+18h]
0x18004c691  mov     rcx, rbx
0x18004c694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c699  nop
0x18004c69a  mov     eax, edi
0x18004c69c  mov     rbx, [rsp+48h+arg_8]
0x18004c6a1  mov     rbp, [rsp+48h+arg_10]
0x18004c6a6  add     rsp, 20h
0x18004c6aa  pop     r15
0x18004c6ac  pop     r14
0x18004c6ae  pop     r12
0x18004c6b0  pop     rdi
0x18004c6b1  pop     rsi
0x18004c6b2  retn
0x18004c6b3  cmp     [rax], r15d
0x18004c6b6  jz      short loc_18004C6C1
0x18004c6b8  add     rax, 4
0x18004c6bc  jmp     loc_18004C5EA
0x18004c6c1  xor     edi, edi
0x18004c6c3  jmp     loc_18004C626
0x18004c6c8  xor     r8d, r8d; unsigned int
0x18004c6cb  mov     edx, 87B2080Ch; int
0x18004c6d0  mov     rcx, rsi; this
0x18004c6d3  call    ?TrackError@BaseBamoConnectionImpl@BamoImpl@Microsoft@@QEAAJJI@Z; Microsoft::BamoImpl::BaseBamoConnectionImpl::TrackError(long,uint)
0x18004c6d8  mov     edi, eax
0x18004c6da  test    eax, eax
0x18004c6dc  jns     loc_18004C626
0x18004c6e2  mov     rcx, [rsp+48h]; this
0x18004c6e7  mov     r9d, eax; char *
0x18004c6ea  lea     r8, aDOsToolsBamoco_9; "d:\\os\\tools\\BamoCodegen\\Inc\\BamoCo"...
0x18004c6f1  mov     edx, 76Eh; void *
0x18004c6f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c6fb  jmp     loc_18004C626
0x18004c700  lea     r8, aDOsToolsBamoco_9; "d:\\os\\tools\\BamoCodegen\\Inc\\BamoCo"...
0x18004c707  mov     edx, 9A3h; void *
0x18004c70c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18004c712  lea     r8, aDOsToolsBamoco_5; "d:\\os\\tools\\BamoCodegen\\Inc\\BamoIm"...
0x18004c719  mov     edx, 33h ; '3'; void *
0x18004c71e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
