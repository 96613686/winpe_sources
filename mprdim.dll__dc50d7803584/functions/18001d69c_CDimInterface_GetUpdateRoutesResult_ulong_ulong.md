# CDimInterface::GetUpdateRoutesResult(ulong,ulong *)

- ea: `0x18001d69c`
- end: `0x18001d86a`
- name: `?GetUpdateRoutesResult@CDimInterface@@QEAAKKPEAK@Z`
- size: `462`
- prototype: `unsigned int(CDimInterface *__hidden this, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002599c`

## callees

- `0x18000df70`
- `0x18001ac14`
- `0x18001d69c`
- `0x18002e15c`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001d772`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001d772`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001d7ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001d7ad`

## string_xrefs

- `0x18001d7d4`: `CDimInterface::GetUpdateRoutesResult for returned %d`

## pseudocode

```c
__int64 __fastcall CDimInterface::GetUpdateRoutesResult(CDimInterface *this, unsigned int a2, unsigned int *a3)
{
  void (__fastcall **v6)(CDimInterface *); // rax
  unsigned int v7; // ebx
  __int64 *v8; // rax
  CDimRouterManager *v9; // rbx
  __int64 v10; // r15
  RTL_SRWLOCK *v11; // rsi
  struct CDimRouterManager::_ROUTER *Router; // rax
  __int64 (__fastcall *v13)(__int64, unsigned int *); // rax
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
        v13 = (__int64 (__fastcall *)(__int64, unsigned int *))*((_QWORD *)Router + 13);
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
    FormatRRASErrorString(&v23, L"CDimInterface::GetUpdateRoutesResult for returned %d", v7);
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
0x18001d69c  push    rbp
0x18001d69e  push    rbx
0x18001d69f  push    rsi
0x18001d6a0  push    rdi
0x18001d6a1  push    r12
0x18001d6a3  push    r14
0x18001d6a5  push    r15
0x18001d6a7  lea     rbp, [rsp-780h]
0x18001d6af  sub     rsp, 880h
0x18001d6b6  mov     rax, cs:__security_cookie
0x18001d6bd  xor     rax, rsp
0x18001d6c0  mov     [rbp+7B0h+var_40], rax
0x18001d6c7  mov     r12, r8
0x18001d6ca  mov     [rsp+8B0h+var_880], edx
0x18001d6ce  mov     r14d, edx
0x18001d6d1  mov     rdi, rcx
0x18001d6d4  xorps   xmm0, xmm0
0x18001d6d7  lea     rcx, [rsp+8B0h+var_83C]; void *
0x18001d6dc  xor     eax, eax
0x18001d6de  xor     edx, edx; Val
0x18001d6e0  mov     r8d, 7FCh; Size
0x18001d6e6  mov     [rsp+8B0h+var_840], eax
0x18001d6ea  movups  [rsp+8B0h+var_878], xmm0
0x18001d6ef  call    memset_0
0x18001d6f4  xor     eax, eax
0x18001d6f6  xorps   xmm0, xmm0
0x18001d6f9  mov     [rsp+8B0h+var_868], eax
0x18001d6fd  mov     rcx, rdi
0x18001d700  mov     [rsp+8B0h+var_844], eax
0x18001d704  mov     rax, [rdi]
0x18001d707  movups  [rsp+8B0h+var_864], xmm0
0x18001d70c  movups  [rsp+8B0h+var_854], xmm0
0x18001d711  mov     rax, [rax]
0x18001d714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d719  mov     rax, [rdi]
0x18001d71c  mov     rcx, rdi
0x18001d71f  mov     rax, [rax+28h]
0x18001d723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d728  cmp     eax, 2
0x18001d72b  jz      short loc_18001D737
0x18001d72d  mov     ebx, 38Ah
0x18001d732  jmp     loc_18001D7BA
0x18001d737  mov     rax, [rdi]
0x18001d73a  mov     edx, r14d
0x18001d73d  mov     rcx, rdi
0x18001d740  mov     rax, [rax+180h]
0x18001d747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d74c  test    al, al
0x18001d74e  jz      short loc_18001D7B5
0x18001d750  lea     rcx, [rdi+108h]
0x18001d757  lea     rdx, [rsp+8B0h+var_880]
0x18001d75c  call    ??A?$map@KU_INTERFACE_TRANSPORT_INFO@CDimInterface@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKU_INTERFACE_TRANSPORT_INFO@CDimInterface@@@std@@@4@@std@@QEAAAEAU_INTERFACE_TRANSPORT_INFO@CDimInterface@@AEBK@Z; std::map<ulong,CDimInterface::_INTERFACE_TRANSPORT_INFO>::operator[](ulong const &)
0x18001d761  mov     rbx, cs:?g_pCDimRouterManager@@3PEAVCDimRouterManager@@EA; CDimRouterManager * g_pCDimRouterManager
0x18001d768  mov     r15, [rax]
0x18001d76b  lea     rsi, [rbx+8]
0x18001d76f  mov     rcx, rsi; SRWLock
0x18001d772  call    cs:__imp_AcquireSRWLockShared
0x18001d778  mov     edx, r14d; unsigned int
0x18001d77b  mov     rcx, rbx; this
0x18001d77e  call    ?GetRouter@CDimRouterManager@@AEAAPEAU_ROUTER@1@K@Z; CDimRouterManager::GetRouter(ulong)
0x18001d783  test    rax, rax
0x18001d786  jnz     short loc_18001D78F
0x18001d788  mov     ebx, 386h
0x18001d78d  jmp     short loc_18001D7AA
0x18001d78f  mov     rax, [rax+68h]
0x18001d793  test    rax, rax
0x18001d796  jnz     short loc_18001D79D
0x18001d798  lea     ebx, [rax+32h]
0x18001d79b  jmp     short loc_18001D7AA
0x18001d79d  mov     rdx, r12
0x18001d7a0  mov     rcx, r15
0x18001d7a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7a8  mov     ebx, eax
0x18001d7aa  mov     rcx, rsi; SRWLock
0x18001d7ad  call    cs:__imp_ReleaseSRWLockShared
0x18001d7b3  jmp     short loc_18001D7BA
0x18001d7b5  mov     ebx, 389h
0x18001d7ba  mov     rax, [rdi]
0x18001d7bd  mov     rcx, rdi
0x18001d7c0  mov     rax, [rax+8]
0x18001d7c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7c9  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x18001d7d0  jz      short loc_18001D847
0x18001d7d2  xor     eax, eax
0x18001d7d4  lea     rdx, aCdiminterfaceG_3; "CDimInterface::GetUpdateRoutesResult fo"...
0x18001d7db  mov     r8d, ebx
0x18001d7de  mov     word ptr [rsp+8B0h+var_840], ax
0x18001d7e3  lea     rcx, [rsp+8B0h+var_840]
0x18001d7e8  mov     word ptr [rsp+8B0h+var_868], ax
0x18001d7ed  call    FormatRRASErrorString
0x18001d7f2  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x18001d7f9  jz      short loc_18001D847
0x18001d7fb  mov     rax, [rdi]
0x18001d7fe  mov     rcx, rdi
0x18001d801  mov     rax, [rax+118h]
0x18001d808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d80d  lea     rcx, [rdi+0C20h]
0x18001d814  test    rcx, rcx
0x18001d817  lea     r9, [rsp+8B0h+var_878]
0x18001d81c  lea     r8, [rsp+8B0h+var_840]
0x18001d821  cmovnz  r9, rcx
0x18001d825  lea     rdx, RasDimParamTraceInfo
0x18001d82c  lea     rcx, [rsp+8B0h+var_868]
0x18001d831  mov     [rsp+8B0h+var_888], rcx
0x18001d836  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001d83d  mov     [rsp+8B0h+var_890], rax
0x18001d842  call    McTemplateU0zjzz_EventWriteTransfer
0x18001d847  mov     eax, ebx
0x18001d849  mov     rcx, [rbp+7B0h+var_40]
0x18001d850  xor     rcx, rsp; StackCookie
0x18001d853  call    __security_check_cookie
0x18001d858  add     rsp, 880h
0x18001d85f  pop     r15
0x18001d861  pop     r14
0x18001d863  pop     r12
0x18001d865  pop     rdi
0x18001d866  pop     rsi
0x18001d867  pop     rbx
0x18001d868  pop     rbp
0x18001d869  retn
```
