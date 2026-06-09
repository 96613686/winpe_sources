# CDimInterface::UpdateRoutes(ulong,void * const)

- ea: `0x180020ae8`
- end: `0x180020cb6`
- name: `?UpdateRoutes@CDimInterface@@QEAAKKQEAX@Z`
- size: `462`
- prototype: `unsigned int(CDimInterface *__hidden this, unsigned int, void *const)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180028640`

## callees

- `0x18000df70`
- `0x18001ac14`
- `0x180020ae8`
- `0x18002e15c`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180020bbe`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180020bbe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180020bf9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180020bf9`

## string_xrefs

- `0x180020c20`: `CDimInterface::UpdateRoutes for returned %d`

## pseudocode

```c
__int64 __fastcall CDimInterface::UpdateRoutes(CDimInterface *this, unsigned int a2, void *const a3)
{
  void (__fastcall **v6)(CDimInterface *); // rax
  unsigned int v7; // ebx
  __int64 *v8; // rax
  CDimRouterManager *v9; // rbx
  __int64 v10; // r15
  RTL_SRWLOCK *v11; // rsi
  struct CDimRouterManager::_ROUTER *Router; // rax
  __int64 (__fastcall *v13)(__int64, void *const); // rax
  __int64 v14; // rax
  __int128 *v15; // r9
  unsigned int v17; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v18; // [rsp+38h] [rbp-C8h] BYREF
  int v19; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v20; // [rsp+4Ch] [rbp-B4h]
  __int128 v21; // [rsp+5Ch] [rbp-A4h]
  int v22; // [rsp+6Ch] [rbp-94h]
  int v23; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v24[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v17 = a2;
  v23 = 0;
  v18 = 0;
  memset_0(v24, 0, sizeof(v24));
  v19 = 0;
  v22 = 0;
  v6 = *(void (__fastcall ***)(CDimInterface *))this;
  v20 = 0;
  v21 = 0;
  (*v6)(this);
  if ( (*(unsigned int (__fastcall **)(CDimInterface *))(*(_QWORD *)this + 40LL))(this) == 2 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(CDimInterface *, _QWORD))(*(_QWORD *)this + 384LL))(this, a2) )
    {
      v8 = (__int64 *)std::map<unsigned long,CDimInterface::_INTERFACE_TRANSPORT_INFO>::operator[](
                        (__int64)this + 264,
                        (__int64)&v17);
      v9 = g_pCDimRouterManager;
      v10 = *v8;
      v11 = (RTL_SRWLOCK *)((char *)g_pCDimRouterManager + 8);
      AcquireSRWLockShared((PSRWLOCK)g_pCDimRouterManager + 1);
      Router = CDimRouterManager::GetRouter(v9, a2);
      if ( Router )
      {
        v13 = (__int64 (__fastcall *)(__int64, void *const))*((_QWORD *)Router + 12);
        if ( v13 )
          v7 = v13(v10, a3);
        else
          v7 = 50;
      }
      else
      {
        v7 = 902;
      }
      ReleaseSRWLockShared(v11);
    }
    else
    {
      v7 = 905;
    }
  }
  else
  {
    v7 = 906;
  }
  (*(void (__fastcall **)(CDimInterface *))(*(_QWORD *)this + 8LL))(this);
  if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
  {
    LOWORD(v23) = 0;
    LOWORD(v19) = 0;
    FormatRRASErrorString(&v23, L"CDimInterface::UpdateRoutes for returned %d", v7);
    if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
    {
      v14 = (*(__int64 (__fastcall **)(CDimInterface *))(*(_QWORD *)this + 280LL))(this);
      v15 = &v18;
      if ( this != (CDimInterface *)-3104LL )
        LODWORD(v15) = (_DWORD)this + 3104;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDimParamTraceInfo,
        (unsigned int)&v23,
        (_DWORD)v15,
        v14,
        (__int64)&v19);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180020ae8  push    rbp
0x180020aea  push    rbx
0x180020aeb  push    rsi
0x180020aec  push    rdi
0x180020aed  push    r12
0x180020aef  push    r14
0x180020af1  push    r15
0x180020af3  lea     rbp, [rsp-780h]
0x180020afb  sub     rsp, 880h
0x180020b02  mov     rax, cs:__security_cookie
0x180020b09  xor     rax, rsp
0x180020b0c  mov     [rbp+7B0h+var_40], rax
0x180020b13  mov     r12, r8
0x180020b16  mov     [rsp+8B0h+var_880], edx
0x180020b1a  mov     r14d, edx
0x180020b1d  mov     rdi, rcx
0x180020b20  xorps   xmm0, xmm0
0x180020b23  lea     rcx, [rsp+8B0h+var_83C]; void *
0x180020b28  xor     eax, eax
0x180020b2a  xor     edx, edx; Val
0x180020b2c  mov     r8d, 7FCh; Size
0x180020b32  mov     [rsp+8B0h+var_840], eax
0x180020b36  movups  [rsp+8B0h+var_878], xmm0
0x180020b3b  call    memset_0
0x180020b40  xor     eax, eax
0x180020b42  xorps   xmm0, xmm0
0x180020b45  mov     [rsp+8B0h+var_868], eax
0x180020b49  mov     rcx, rdi
0x180020b4c  mov     [rsp+8B0h+var_844], eax
0x180020b50  mov     rax, [rdi]
0x180020b53  movups  [rsp+8B0h+var_864], xmm0
0x180020b58  movups  [rsp+8B0h+var_854], xmm0
0x180020b5d  mov     rax, [rax]
0x180020b60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b65  mov     rax, [rdi]
0x180020b68  mov     rcx, rdi
0x180020b6b  mov     rax, [rax+28h]
0x180020b6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b74  cmp     eax, 2
0x180020b77  jz      short loc_180020B83
0x180020b79  mov     ebx, 38Ah
0x180020b7e  jmp     loc_180020C06
0x180020b83  mov     rax, [rdi]
0x180020b86  mov     edx, r14d
0x180020b89  mov     rcx, rdi
0x180020b8c  mov     rax, [rax+180h]
0x180020b93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b98  test    al, al
0x180020b9a  jz      short loc_180020C01
0x180020b9c  lea     rcx, [rdi+108h]
0x180020ba3  lea     rdx, [rsp+8B0h+var_880]
0x180020ba8  call    ??A?$map@KU_INTERFACE_TRANSPORT_INFO@CDimInterface@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKU_INTERFACE_TRANSPORT_INFO@CDimInterface@@@std@@@4@@std@@QEAAAEAU_INTERFACE_TRANSPORT_INFO@CDimInterface@@AEBK@Z; std::map<ulong,CDimInterface::_INTERFACE_TRANSPORT_INFO>::operator[](ulong const &)
0x180020bad  mov     rbx, cs:?g_pCDimRouterManager@@3PEAVCDimRouterManager@@EA; CDimRouterManager * g_pCDimRouterManager
0x180020bb4  mov     r15, [rax]
0x180020bb7  lea     rsi, [rbx+8]
0x180020bbb  mov     rcx, rsi; SRWLock
0x180020bbe  call    cs:__imp_AcquireSRWLockShared
0x180020bc4  mov     edx, r14d; unsigned int
0x180020bc7  mov     rcx, rbx; this
0x180020bca  call    ?GetRouter@CDimRouterManager@@AEAAPEAU_ROUTER@1@K@Z; CDimRouterManager::GetRouter(ulong)
0x180020bcf  test    rax, rax
0x180020bd2  jnz     short loc_180020BDB
0x180020bd4  mov     ebx, 386h
0x180020bd9  jmp     short loc_180020BF6
0x180020bdb  mov     rax, [rax+60h]
0x180020bdf  test    rax, rax
0x180020be2  jnz     short loc_180020BE9
0x180020be4  lea     ebx, [rax+32h]
0x180020be7  jmp     short loc_180020BF6
0x180020be9  mov     rdx, r12
0x180020bec  mov     rcx, r15
0x180020bef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bf4  mov     ebx, eax
0x180020bf6  mov     rcx, rsi; SRWLock
0x180020bf9  call    cs:__imp_ReleaseSRWLockShared
0x180020bff  jmp     short loc_180020C06
0x180020c01  mov     ebx, 389h
0x180020c06  mov     rax, [rdi]
0x180020c09  mov     rcx, rdi
0x180020c0c  mov     rax, [rax+8]
0x180020c10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c15  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x180020c1c  jz      short loc_180020C93
0x180020c1e  xor     eax, eax
0x180020c20  lea     rdx, aCdiminterfaceU; "CDimInterface::UpdateRoutes for returne"...
0x180020c27  mov     r8d, ebx
0x180020c2a  mov     word ptr [rsp+8B0h+var_840], ax
0x180020c2f  lea     rcx, [rsp+8B0h+var_840]
0x180020c34  mov     word ptr [rsp+8B0h+var_868], ax
0x180020c39  call    FormatRRASErrorString
0x180020c3e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x180020c45  jz      short loc_180020C93
0x180020c47  mov     rax, [rdi]
0x180020c4a  mov     rcx, rdi
0x180020c4d  mov     rax, [rax+118h]
0x180020c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c59  lea     rcx, [rdi+0C20h]
0x180020c60  test    rcx, rcx
0x180020c63  lea     r9, [rsp+8B0h+var_878]
0x180020c68  lea     r8, [rsp+8B0h+var_840]
0x180020c6d  cmovnz  r9, rcx
0x180020c71  lea     rdx, RasDimParamTraceInfo
0x180020c78  lea     rcx, [rsp+8B0h+var_868]
0x180020c7d  mov     [rsp+8B0h+var_888], rcx
0x180020c82  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180020c89  mov     [rsp+8B0h+var_890], rax
0x180020c8e  call    McTemplateU0zjzz_EventWriteTransfer
0x180020c93  mov     eax, ebx
0x180020c95  mov     rcx, [rbp+7B0h+var_40]
0x180020c9c  xor     rcx, rsp; StackCookie
0x180020c9f  call    __security_check_cookie
0x180020ca4  add     rsp, 880h
0x180020cab  pop     r15
0x180020cad  pop     r14
0x180020caf  pop     r12
0x180020cb1  pop     rdi
0x180020cb2  pop     rsi
0x180020cb3  pop     rbx
0x180020cb4  pop     rbp
0x180020cb5  retn
```
