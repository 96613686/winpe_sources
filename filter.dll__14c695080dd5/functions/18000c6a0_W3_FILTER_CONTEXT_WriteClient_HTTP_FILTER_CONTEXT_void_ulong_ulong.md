# W3_FILTER_CONTEXT::WriteClient(_HTTP_FILTER_CONTEXT *,void *,ulong *,ulong)

- ea: `0x18000c6a0`
- end: `0x18000c86c`
- name: `?WriteClient@W3_FILTER_CONTEXT@@SAHPEAU_HTTP_FILTER_CONTEXT@@PEAXPEAKK@Z`
- size: `460`
- prototype: `__int64 __fastcall(struct _HTTP_FILTER_CONTEXT *, void *, unsigned int *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800057a0`
- `0x180007490`
- `0x18000af48`
- `0x18000c648`
- `0x18000c6a0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c850`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c850`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000c701`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000c701`

## pseudocode

```c
__int64 __fastcall W3_FILTER_CONTEXT::WriteClient(struct _HTTP_FILTER_CONTEXT *a1, void *a2, unsigned int *a3)
{
  W3_FILTER_CONTEXT *ServerContext; // rdi
  __int64 v7; // rbx
  _QWORD *Ptr; // rax
  __int64 v9; // r12
  DWORD v10; // ecx
  _DWORD *v11; // rbx
  __int64 v12; // r15
  int v13; // ebx
  DWORD cbInData; // eax
  DWORD v15; // eax
  int v16; // eax
  int v18; // [rsp+40h] [rbp-29h] BYREF
  struct _HTTP_FILTER_RAW_DATA v19; // [rsp+48h] [rbp-21h] BYREF
  __int128 v20; // [rsp+60h] [rbp-9h] BYREF
  __int128 v21; // [rsp+70h] [rbp+7h]
  int v22; // [rsp+D0h] [rbp+67h] BYREF

  v18 = 0;
  v20 = 0;
  v21 = 0;
  if ( !a1 || (ServerContext = (W3_FILTER_CONTEXT *)a1->ServerContext) == 0 || !a2 )
  {
    v10 = 87;
    goto LABEL_21;
  }
  v7 = *((unsigned int *)ServerContext + 70);
  Ptr = BUFFER::QueryPtr((BUFFER *)(*((_QWORD *)ServerContext + 14) + 24LL));
  v9 = *((_QWORD *)ServerContext + 3);
  if ( v9 )
  {
    v11 = (_DWORD *)Ptr[v7];
    v12 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v9 + 32LL))(*((_QWORD *)ServerContext + 3));
    W3_FILTER_CONTEXT::SetClientContext(ServerContext, v11, a1->pFilterContext);
    v11[32] = 1;
    if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v9 + 40LL))(v9) && !*((_DWORD *)ServerContext + 100) )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 128LL))(v12);
    v13 = *((_DWORD *)ServerContext + 35);
    if ( v13
      || *((_DWORD *)ServerContext + 36) && (unsigned int)W3_FILTER_CONTEXT::IsNotificationNeeded(ServerContext, 0x400u) )
    {
      v15 = *a3;
      v19.pvInData = a2;
      *(_QWORD *)&v19.dwReserved = 0;
      *((_DWORD *)ServerContext + 35) = 1;
      v22 = 0;
      v19.cbInData = v15;
      v19.cbInBuffer = v15;
      v16 = W3_FILTER_CONTEXT::NotifySendRawFilters(ServerContext, &v19, &v22);
      *((_DWORD *)ServerContext + 35) = v13;
      if ( v16 < 0 )
      {
LABEL_14:
        v10 = WIN32_FROM_HRESULT(v16);
        goto LABEL_21;
      }
      if ( v22 )
        return 1;
      *((_QWORD *)&v20 + 1) = v19.pvInData;
      cbInData = v19.cbInData;
    }
    else
    {
      cbInData = *a3;
      *((_QWORD *)&v20 + 1) = a2;
    }
    LODWORD(v21) = cbInData;
    LODWORD(v20) = 0;
    *((_DWORD *)ServerContext + 100) = 1;
    v16 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64, _QWORD, int, int *, _QWORD))(*(_QWORD *)v12 + 168LL))(
            v12,
            &v20,
            1,
            0,
            1,
            &v18,
            0);
    if ( v16 < 0 )
      goto LABEL_14;
    return 1;
  }
  v10 = 50;
LABEL_21:
  SetLastError(v10);
  return 0;
}

```

## disassembly

```asm
0x18000c6a0  push    rbp
0x18000c6a2  push    rbx
0x18000c6a3  push    rsi
0x18000c6a4  push    rdi
0x18000c6a5  push    r12
0x18000c6a7  push    r13
0x18000c6a9  push    r14
0x18000c6ab  push    r15
0x18000c6ad  lea     rbp, [rsp-1Fh]
0x18000c6b2  sub     rsp, 88h
0x18000c6b9  mov     [rbp+57h+var_80], 0
0x18000c6c0  xorps   xmm0, xmm0
0x18000c6c3  mov     r13, r8
0x18000c6c6  mov     rsi, rdx
0x18000c6c9  mov     r14, rcx
0x18000c6cc  movups  [rbp+57h+var_60], xmm0
0x18000c6d0  movups  [rbp+57h+var_50], xmm0
0x18000c6d4  test    rcx, rcx
0x18000c6d7  jz      loc_18000C84B
0x18000c6dd  mov     rdi, [rcx+8]
0x18000c6e1  test    rdi, rdi
0x18000c6e4  jz      loc_18000C84B
0x18000c6ea  test    rdx, rdx
0x18000c6ed  jz      loc_18000C84B
0x18000c6f3  mov     rcx, [rdi+70h]
0x18000c6f7  mov     ebx, [rdi+118h]
0x18000c6fd  add     rcx, 18h
0x18000c701  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000c707  mov     r12, [rdi+18h]
0x18000c70b  test    r12, r12
0x18000c70e  jnz     short loc_18000C71A
0x18000c710  lea     ecx, [r12+32h]
0x18000c715  jmp     loc_18000C850
0x18000c71a  mov     rbx, [rax+rbx*8]
0x18000c71e  mov     rcx, r12
0x18000c721  mov     rax, [r12]
0x18000c725  mov     rax, [rax+20h]
0x18000c729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c72e  mov     r8, [r14+18h]; void *
0x18000c732  mov     rdx, rbx; void *
0x18000c735  mov     rcx, rdi; this
0x18000c738  mov     r15, rax
0x18000c73b  call    ?SetClientContext@W3_FILTER_CONTEXT@@QEAAXPEAX0@Z; W3_FILTER_CONTEXT::SetClientContext(void *,void *)
0x18000c740  mov     dword ptr [rbx+80h], 1
0x18000c74a  mov     rcx, r12
0x18000c74d  mov     rdx, [r12]
0x18000c751  mov     rax, [rdx+28h]
0x18000c755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c75a  xor     r14d, r14d
0x18000c75d  test    eax, eax
0x18000c75f  jnz     short loc_18000C77C
0x18000c761  cmp     [rdi+190h], r14d
0x18000c768  jnz     short loc_18000C77C
0x18000c76a  mov     rax, [r15]
0x18000c76d  mov     rcx, r15
0x18000c770  mov     rax, [rax+80h]
0x18000c777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c77c  mov     ebx, [rdi+8Ch]
0x18000c782  test    ebx, ebx
0x18000c784  jnz     short loc_18000C7AF
0x18000c786  cmp     [rdi+90h], r14d
0x18000c78d  jz      short loc_18000C7A0
0x18000c78f  mov     edx, 400h; unsigned int
0x18000c794  mov     rcx, rdi; this
0x18000c797  call    ?IsNotificationNeeded@W3_FILTER_CONTEXT@@QEAAHK@Z; W3_FILTER_CONTEXT::IsNotificationNeeded(ulong)
0x18000c79c  test    eax, eax
0x18000c79e  jnz     short loc_18000C7AF
0x18000c7a0  mov     eax, [r13+0]
0x18000c7a4  mov     qword ptr [rbp+57h+var_60+8], rsi
0x18000c7a8  mov     esi, 1
0x18000c7ad  jmp     short loc_18000C80A
0x18000c7af  mov     eax, [r13+0]
0x18000c7b3  lea     r8, [rbp+57h+arg_0]; int *
0x18000c7b7  mov     [rbp+57h+var_78.pvInData], rsi
0x18000c7bb  lea     rdx, [rbp+57h+var_78]; struct _HTTP_FILTER_RAW_DATA *
0x18000c7bf  mov     esi, 1
0x18000c7c4  mov     qword ptr [rbp+57h+var_78.dwReserved], r14
0x18000c7c8  mov     rcx, rdi; this
0x18000c7cb  mov     [rdi+8Ch], esi
0x18000c7d1  mov     [rbp+57h+arg_0], r14d
0x18000c7d5  mov     [rbp+57h+var_78.cbInData], eax
0x18000c7d8  mov     [rbp+57h+var_78.cbInBuffer], eax
0x18000c7db  call    ?NotifySendRawFilters@W3_FILTER_CONTEXT@@QEAAJPEAU_HTTP_FILTER_RAW_DATA@@PEAH@Z; W3_FILTER_CONTEXT::NotifySendRawFilters(_HTTP_FILTER_RAW_DATA *,int *)
0x18000c7e0  mov     [rdi+8Ch], ebx
0x18000c7e6  test    eax, eax
0x18000c7e8  jns     short loc_18000C7F5
0x18000c7ea  mov     ecx, eax; int
0x18000c7ec  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18000c7f1  mov     ecx, eax
0x18000c7f3  jmp     short loc_18000C850
0x18000c7f5  cmp     [rbp+57h+arg_0], r14d
0x18000c7f9  jz      short loc_18000C7FF
0x18000c7fb  mov     eax, esi
0x18000c7fd  jmp     short loc_18000C858
0x18000c7ff  mov     rax, [rbp+57h+var_78.pvInData]
0x18000c803  mov     qword ptr [rbp+57h+var_60+8], rax
0x18000c807  mov     eax, [rbp+57h+var_78.cbInData]
0x18000c80a  mov     dword ptr [rbp+57h+var_50], eax
0x18000c80d  lea     rcx, [rbp+57h+var_80]
0x18000c811  mov     dword ptr [rbp+57h+var_60], r14d
0x18000c815  lea     rdx, [rbp+57h+var_60]
0x18000c819  mov     [rdi+190h], esi
0x18000c81f  xor     r9d, r9d
0x18000c822  mov     rax, [r15]
0x18000c825  mov     r8d, esi
0x18000c828  mov     [rsp+0C0h+var_90], r14
0x18000c82d  mov     [rsp+0C0h+var_98], rcx
0x18000c832  mov     rcx, r15
0x18000c835  mov     [rsp+0C0h+var_A0], esi
0x18000c839  mov     rax, [rax+0A8h]
0x18000c840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c845  test    eax, eax
0x18000c847  jns     short loc_18000C7FB
0x18000c849  jmp     short loc_18000C7EA
0x18000c84b  mov     ecx, 57h ; 'W'; dwErrCode
0x18000c850  call    cs:__imp_SetLastError
0x18000c856  xor     eax, eax
0x18000c858  add     rsp, 88h
0x18000c85f  pop     r15
0x18000c861  pop     r14
0x18000c863  pop     r13
0x18000c865  pop     r12
0x18000c867  pop     rdi
0x18000c868  pop     rsi
0x18000c869  pop     rbx
0x18000c86a  pop     rbp
0x18000c86b  retn
```
