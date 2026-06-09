# RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x180002acc`
- end: `0x180002d4b`
- name: `?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `639`
- prototype: `enum REQUEST_NOTIFICATION_STATUS __high(unsigned int, int, struct IHttpContext *, struct IHttpEventProvider *, struct IHttpCompletionInfo *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800021a0`
- `0x180002280`

## callees

- `0x180001b5c`
- `0x180002acc`
- `0x180002f68`
- `0x180005010`

## import_xrefs

- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180002ccb`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180002ccb`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002cb4`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002cb4`

## pseudocode

```c
__int64 __fastcall RequestDoWork(
        int a1,
        __int64 a2,
        struct IHttpContext *a3,
        __int64 a4,
        void (__fastcall ***a5)(_QWORD))
{
  void (__fastcall ***v5)(_QWORD); // rbx
  int v8; // r14d
  int v9; // esi
  __int64 (__fastcall ***v11)(_QWORD, void *); // rax
  __int64 (__fastcall **v12)(_QWORD, void *); // rcx
  __int64 v13; // rbx
  int ParsedMetadata; // ebx
  __int64 v15; // rax
  __int64 v16; // rax
  void (*v17)(void); // rax
  __int64 v18; // rax
  __int64 v19; // rax
  int v20; // r8d
  __int64 v21; // rcx
  __int64 v22; // rax
  struct INativeSectionException *v23; // [rsp+40h] [rbp-18h] BYREF
  struct ACCESS_META_STORED_CONTEXT *v24; // [rsp+48h] [rbp-10h] BYREF
  __int64 v25; // [rsp+A8h] [rbp+50h] BYREF

  v5 = a5;
  v24 = 0;
  v23 = 0;
  v25 = 0;
  if ( a5 )
  {
    v8 = 1;
    (**a5)(a5);
    v9 = ((__int64 (__fastcall *)(_QWORD))(*v5)[1])(v5);
  }
  else
  {
    v8 = 0;
    v9 = 0;
  }
  if ( a1 != 1 )
    return 0;
  v11 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 56LL))(a3);
  v12 = *v11;
  if ( v8 )
  {
    v22 = (*v12)(v11, g_pIpRestrictionModuleContext);
    v20 = v8;
    v21 = v22;
  }
  else
  {
    v13 = (*v12)(v11, g_pIpRestrictionModuleContext);
    if ( !v13 )
    {
      ParsedMetadata = ACCESS_META_STORED_CONTEXT::GetParsedMetadata(a3, &v24, &v23);
      if ( ParsedMetadata < 0 )
      {
        if ( v23 )
          (**(void (__fastcall ***)(struct INativeSectionException *, GUID *, __int64 *))v23)(
            v23,
            &IID_IAppHostConfigException,
            &v25);
        v15 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
        *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15) + 536) = 0;
        v16 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
        (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, __int64, _DWORD))(*(_QWORD *)v16 + 24LL))(
          v16,
          500,
          "Internal Server Error",
          19,
          ParsedMetadata,
          v25,
          0);
        if ( v25 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
          v25 = 0;
        }
        if ( !v23 )
          return 2;
        v17 = *(void (**)(void))(*(_QWORD *)v23 + 16LL);
        goto LABEL_18;
      }
      v18 = (*(__int64 (__fastcall **)(struct IHttpContext *, __int64))(*(_QWORD *)a3 + 144LL))(a3, 368);
      v13 = v18;
      if ( !v18 )
        return 2;
      *(_QWORD *)(v18 + 8) = a3;
      *(_QWORD *)v18 = &CHECK_ACCESS_HANDLER::`vftable';
      *(_QWORD *)(v18 + 16) = v24;
      *(_DWORD *)(v18 + 24) = 1;
      *(_DWORD *)(v18 + 28) = 1;
      STRU::STRU((STRU *)(v18 + 64), (unsigned __int16 *)(v18 + 120), 0x40u);
      STRA::STRA((STRA *)(v13 + 248), (char *)(v13 + 304), 0x40u);
      v19 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 56LL))(a3);
      v9 = (*(__int64 (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)v19 + 8LL))(
             v19,
             v13,
             g_pIpRestrictionModuleContext);
      if ( v9 < 0 )
      {
        v17 = **(void (***)(void))v13;
LABEL_18:
        v17();
        return 2;
      }
    }
    v20 = 0;
    v21 = v13;
  }
  return CHECK_ACCESS_HANDLER::DoWork(v21, a3, v20, v9);
}

```

## disassembly

```asm
0x180002acc  mov     [rsp-30h+arg_18], r9
0x180002ad1  push    rbp
0x180002ad2  push    rbx
0x180002ad3  push    rsi
0x180002ad4  push    rdi
0x180002ad5  push    r14
0x180002ad7  push    r15
0x180002ad9  mov     rbp, rsp
0x180002adc  sub     rsp, 58h
0x180002ae0  mov     rbx, [rbp+arg_20]
0x180002ae4  mov     rdi, r8
0x180002ae7  mov     [rbp+var_10], 0
0x180002aef  mov     r15d, ecx
0x180002af2  mov     [rbp+var_18], 0
0x180002afa  mov     [rbp+arg_18], 0
0x180002b02  test    rbx, rbx
0x180002b05  jz      short loc_180002B2E
0x180002b07  mov     rax, [rbx]
0x180002b0a  mov     rcx, rbx
0x180002b0d  mov     r14d, 1
0x180002b13  mov     rax, [rax]
0x180002b16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b1b  mov     rax, [rbx]
0x180002b1e  mov     rcx, rbx
0x180002b21  mov     rax, [rax+8]
0x180002b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b2a  mov     esi, eax
0x180002b2c  jmp     short loc_180002B33
0x180002b2e  xor     r14d, r14d
0x180002b31  xor     esi, esi
0x180002b33  cmp     r15d, 1
0x180002b37  jz      short loc_180002B40
0x180002b39  xor     eax, eax
0x180002b3b  jmp     loc_180002D3E
0x180002b40  mov     rax, [rdi]
0x180002b43  mov     rcx, rdi
0x180002b46  mov     rax, [rax+38h]
0x180002b4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b4f  mov     rdx, cs:?g_pIpRestrictionModuleContext@@3PEAXEA; void * g_pIpRestrictionModuleContext
0x180002b56  mov     rcx, [rax]
0x180002b59  test    r14d, r14d
0x180002b5c  jnz     loc_180002D1F
0x180002b62  mov     r8, rax
0x180002b65  mov     rax, [rcx]
0x180002b68  mov     rcx, r8
0x180002b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b70  mov     rbx, rax
0x180002b73  test    rax, rax
0x180002b76  jnz     loc_180002D17
0x180002b7c  lea     r8, [rbp+var_18]; struct INativeSectionException **
0x180002b80  mov     rcx, rdi; struct IHttpContext *
0x180002b83  lea     rdx, [rbp+var_10]; struct ACCESS_META_STORED_CONTEXT **
0x180002b87  call    ?GetParsedMetadata@ACCESS_META_STORED_CONTEXT@@SAJPEAVIHttpContext@@PEAPEAV1@PEAPEAVINativeSectionException@@@Z; ACCESS_META_STORED_CONTEXT::GetParsedMetadata(IHttpContext *,ACCESS_META_STORED_CONTEXT * *,INativeSectionException * *)
0x180002b8c  mov     ebx, eax
0x180002b8e  test    eax, eax
0x180002b90  jns     loc_180002C5D
0x180002b96  mov     rcx, [rbp+var_18]
0x180002b9a  test    rcx, rcx
0x180002b9d  jz      short loc_180002BB5
0x180002b9f  mov     rdx, [rcx]
0x180002ba2  lea     r8, [rbp+arg_18]
0x180002ba6  mov     rax, [rdx]
0x180002ba9  lea     rdx, IID_IAppHostConfigException
0x180002bb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bb5  mov     rax, [rdi]
0x180002bb8  mov     rcx, rdi
0x180002bbb  mov     rax, [rax+20h]
0x180002bbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bc4  mov     rdx, rax
0x180002bc7  mov     rcx, [rax]
0x180002bca  mov     rax, [rcx+8]
0x180002bce  mov     rcx, rdx
0x180002bd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bd6  xor     ecx, ecx
0x180002bd8  mov     [rax+218h], cx
0x180002bdf  mov     rcx, rdi
0x180002be2  mov     rax, [rdi]
0x180002be5  mov     rax, [rax+20h]
0x180002be9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bee  mov     r10, rax
0x180002bf1  mov     [rsp+58h+var_28], 0
0x180002bf9  mov     edx, 1F4h
0x180002bfe  lea     r8, aInternalServer; "Internal Server Error"
0x180002c05  mov     r9d, 13h
0x180002c0b  mov     rcx, [rax]
0x180002c0e  mov     rax, [rcx+18h]
0x180002c12  mov     rcx, [rbp+arg_18]
0x180002c16  mov     [rsp+58h+var_30], rcx
0x180002c1b  mov     rcx, r10
0x180002c1e  mov     [rsp+58h+var_38], ebx
0x180002c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c27  mov     rcx, [rbp+arg_18]
0x180002c2b  test    rcx, rcx
0x180002c2e  jz      short loc_180002C44
0x180002c30  mov     rax, [rcx]
0x180002c33  mov     rax, [rax+10h]
0x180002c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c3c  mov     [rbp+arg_18], 0
0x180002c44  mov     rcx, [rbp+var_18]
0x180002c48  test    rcx, rcx
0x180002c4b  jz      loc_180002D10
0x180002c51  mov     rax, [rcx]
0x180002c54  mov     rax, [rax+10h]
0x180002c58  jmp     loc_180002D0B
0x180002c5d  mov     rax, [rdi]
0x180002c60  mov     edx, 170h
0x180002c65  mov     rcx, rdi
0x180002c68  mov     rax, [rax+90h]
0x180002c6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c74  mov     rbx, rax
0x180002c77  test    rax, rax
0x180002c7a  jz      loc_180002D10
0x180002c80  lea     rax, ??_7CHECK_ACCESS_HANDLER@@6B@; const CHECK_ACCESS_HANDLER::`vftable'
0x180002c87  mov     [rbx+8], rdi
0x180002c8b  mov     [rbx], rax
0x180002c8e  lea     rdx, [rbx+78h]
0x180002c92  mov     rax, [rbp+var_10]
0x180002c96  lea     rcx, [rbx+40h]
0x180002c9a  mov     esi, 40h ; '@'
0x180002c9f  mov     [rbx+10h], rax
0x180002ca3  mov     r8d, esi
0x180002ca6  mov     dword ptr [rbx+18h], 1
0x180002cad  mov     dword ptr [rbx+1Ch], 1
0x180002cb4  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180002cba  lea     rdx, [rbx+130h]
0x180002cc1  mov     r8d, esi
0x180002cc4  lea     rcx, [rbx+0F8h]
0x180002ccb  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180002cd1  mov     rax, [rdi]
0x180002cd4  mov     rcx, rdi
0x180002cd7  mov     rax, [rax+38h]
0x180002cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ce0  mov     r8, cs:?g_pIpRestrictionModuleContext@@3PEAXEA; void * g_pIpRestrictionModuleContext
0x180002ce7  mov     r9, rax
0x180002cea  mov     rdx, rbx
0x180002ced  mov     rcx, [rax]
0x180002cf0  mov     rax, [rcx+8]
0x180002cf4  mov     rcx, r9
0x180002cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cfc  mov     esi, eax
0x180002cfe  test    eax, eax
0x180002d00  jns     short loc_180002D17
0x180002d02  mov     rax, [rbx]
0x180002d05  mov     rcx, rbx
0x180002d08  mov     rax, [rax]
0x180002d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d10  mov     eax, 2
0x180002d15  jmp     short loc_180002D3E
0x180002d17  xor     r8d, r8d
0x180002d1a  mov     rcx, rbx
0x180002d1d  jmp     short loc_180002D33
0x180002d1f  mov     r9, rax
0x180002d22  mov     rax, [rcx]
0x180002d25  mov     rcx, r9
0x180002d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d2d  mov     r8d, r14d
0x180002d30  mov     rcx, rax
0x180002d33  mov     r9d, esi
0x180002d36  mov     rdx, rdi
0x180002d39  call    ?DoWork@CHECK_ACCESS_HANDLER@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@HJ@Z; CHECK_ACCESS_HANDLER::DoWork(IHttpContext *,int,long)
0x180002d3e  add     rsp, 58h
0x180002d42  pop     r15
0x180002d44  pop     r14
0x180002d46  pop     rdi
0x180002d47  pop     rsi
0x180002d48  pop     rbx
0x180002d49  pop     rbp
0x180002d4a  retn
```
