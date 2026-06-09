# CImpTipConnection::Init(CImpTipConnectionMgr *,ITipConnection *,ITcpConnectionFactory *,ITipConnectionSink *)

- ea: `0x1800af5d4`
- end: `0x1800af74a`
- name: `?Init@CImpTipConnection@@QEAAJPEAVCImpTipConnectionMgr@@PEAUITipConnection@@PEAUITcpConnectionFactory@@PEAUITipConnectionSink@@@Z`
- size: `374`
- prototype: `__int64 __fastcall(CImpTipConnection *__hidden this, struct CImpTipConnectionMgr *, struct ITipConnection *, struct ITcpConnectionFactory *, struct ITipConnectionSink *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800add20`

## callees

- `0x1800063b0`
- `0x1800af5d4`
- `0x1800b0f94`
- `0x1800b83ee`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800af605`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800af687`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800af605`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800af687`

## string_xrefs

- `0x1800af62e`: `com\complus\dtc\dtc\tipgw\tipconn\src\tipconnection.cpp`

## pseudocode

```c
__int64 __fastcall CImpTipConnection::Init(
        CImpTipConnection *this,
        struct CImpTipConnectionMgr *a2,
        struct ITipConnection *a3,
        struct ITcpConnectionFactory *a4,
        struct ITipConnectionSink *a5)
{
  void *v5; // rax
  int *v6; // rdi
  const wchar_t *v11; // rcx
  __int64 v12; // r9
  unsigned int v13; // ebp
  void *v14; // rcx
  _DWORD *v15; // rsi
  LPVOID v16; // rax

  v5 = (void *)*((_QWORD *)this + 21);
  v6 = (int *)((char *)this + 176);
  if ( !v5 )
  {
    v5 = CoTaskMemAlloc(*v6);
    *((_QWORD *)this + 21) = v5;
    if ( !v5 )
    {
      *v6 = 0;
      v11 = L"NULL == m_pbOutputBuffer";
      v12 = 178;
LABEL_4:
      v13 = -2147467259;
      TraceStringInline(
        10,
        1,
        L"com\\complus\\dtc\\dtc\\tipgw\\tipconn\\src\\tipconnection.cpp",
        v12,
        L"CImpTipConnection::Init",
        -2147467259,
        v11);
      return v13;
    }
  }
  memset_0(v5, 0, *v6);
  v14 = (void *)*((_QWORD *)this + 17);
  v15 = (_DWORD *)((char *)this + 144);
  if ( !v14 )
  {
    v16 = CoTaskMemAlloc(*v15 + 1);
    *((_QWORD *)this + 17) = v16;
    v14 = v16;
    if ( !v16 )
    {
      *v15 = 0;
      v11 = L"m_pbInputBuffer == NULL";
      *((_DWORD *)this + 37) = 0;
      v12 = 193;
      goto LABEL_4;
    }
  }
  v13 = 0;
  memset_0(v14, 0, *v15 + 1);
  *((_DWORD *)this + 18) = 1;
  *((_DWORD *)this + 19) = 1;
  CImpTipConnection::SetState(this, 203, 1, "CImpTipConnection::Init");
  if ( !*((_QWORD *)this + 13) )
  {
    *((_QWORD *)this + 13) = a2;
    (*(void (__fastcall **)(struct CImpTipConnectionMgr *))(*(_QWORD *)a2 + 8LL))(a2);
  }
  if ( !*((_QWORD *)this + 14) )
  {
    *((_QWORD *)this + 14) = a4;
    (*(void (__fastcall **)(struct ITcpConnectionFactory *))(*(_QWORD *)a4 + 8LL))(a4);
  }
  if ( !*((_QWORD *)this + 11) )
  {
    *((_QWORD *)this + 11) = a5;
    (*(void (__fastcall **)(struct ITipConnectionSink *))(*(_QWORD *)a5 + 8LL))(a5);
  }
  *((_QWORD *)this + 15) = a3;
  return v13;
}

```

## disassembly

```asm
0x1800af5d4  push    rbx
0x1800af5d6  push    rbp
0x1800af5d7  push    rsi
0x1800af5d8  push    rdi
0x1800af5d9  push    r12
0x1800af5db  push    r14
0x1800af5dd  push    r15
0x1800af5df  sub     rsp, 40h
0x1800af5e3  mov     rax, [rcx+0A8h]
0x1800af5ea  lea     rdi, [rcx+0B0h]
0x1800af5f1  mov     r14, r9
0x1800af5f4  mov     r12, r8
0x1800af5f7  mov     r15, rdx
0x1800af5fa  mov     rbx, rcx
0x1800af5fd  test    rax, rax
0x1800af600  jnz     short loc_1800AF65B
0x1800af602  movsxd  rcx, dword ptr [rdi]; cb
0x1800af605  call    cs:__imp_CoTaskMemAlloc
0x1800af60b  mov     [rbx+0A8h], rax
0x1800af612  test    rax, rax
0x1800af615  jnz     short loc_1800AF65B
0x1800af617  mov     [rdi], eax
0x1800af619  lea     rcx, aNullMPboutputb; "NULL == m_pbOutputBuffer"
0x1800af620  mov     r9d, 0B2h
0x1800af626  lea     edx, [rax+1]
0x1800af629  mov     [rsp+78h+var_48], rcx
0x1800af62e  lea     r8, aComComplusDtcD_30; "com\\complus\\dtc\\dtc\\tipgw\\tipconn"...
0x1800af635  mov     eax, 80004005h
0x1800af63a  mov     ecx, 0Ah
0x1800af63f  mov     [rsp+78h+var_50], eax
0x1800af643  mov     ebp, eax
0x1800af645  lea     rax, aCimptipconnect_39; "CImpTipConnection::Init"
0x1800af64c  mov     [rsp+78h+var_58], rax
0x1800af651  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800af656  jmp     loc_1800AF739
0x1800af65b  movsxd  r8, dword ptr [rdi]; Size
0x1800af65e  xor     edx, edx; Val
0x1800af660  mov     rcx, rax; void *
0x1800af663  call    memset_0
0x1800af668  mov     rcx, [rbx+88h]; void *
0x1800af66f  lea     rsi, [rbx+90h]
0x1800af676  mov     edi, 1
0x1800af67b  test    rcx, rcx
0x1800af67e  jnz     short loc_1800AF6B8
0x1800af680  mov     eax, [rsi]
0x1800af682  add     eax, edi
0x1800af684  movsxd  rcx, eax; cb
0x1800af687  call    cs:__imp_CoTaskMemAlloc
0x1800af68d  mov     [rbx+88h], rax
0x1800af694  mov     rcx, rax
0x1800af697  test    rax, rax
0x1800af69a  jnz     short loc_1800AF6B8
0x1800af69c  mov     [rsi], eax
0x1800af69e  lea     rcx, aMPbinputbuffer; "m_pbInputBuffer == NULL"
0x1800af6a5  mov     [rbx+94h], eax
0x1800af6ab  mov     r9d, 0C1h
0x1800af6b1  mov     edx, edi
0x1800af6b3  jmp     loc_1800AF629
0x1800af6b8  mov     eax, [rsi]
0x1800af6ba  xor     edx, edx; Val
0x1800af6bc  add     eax, edi
0x1800af6be  xor     ebp, ebp
0x1800af6c0  movsxd  r8, eax; Size
0x1800af6c3  call    memset_0
0x1800af6c8  lea     r9, aCimptipconnect_13; "CImpTipConnection::Init"
0x1800af6cf  mov     [rbx+48h], edi
0x1800af6d2  mov     r8d, edi
0x1800af6d5  mov     [rbx+4Ch], edi
0x1800af6d8  mov     edx, 0CBh
0x1800af6dd  mov     rcx, rbx
0x1800af6e0  call    ?SetState@CImpTipConnection@@AEAAXHW4ETipConnectionState@@PEAD@Z; CImpTipConnection::SetState(int,ETipConnectionState,char *)
0x1800af6e5  cmp     [rbx+68h], rbp
0x1800af6e9  jnz     short loc_1800AF6FE
0x1800af6eb  mov     [rbx+68h], r15
0x1800af6ef  mov     rcx, r15
0x1800af6f2  mov     rax, [r15]
0x1800af6f5  mov     rax, [rax+8]
0x1800af6f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af6fe  cmp     [rbx+70h], rbp
0x1800af702  jnz     short loc_1800AF717
0x1800af704  mov     [rbx+70h], r14
0x1800af708  mov     rcx, r14
0x1800af70b  mov     rax, [r14]
0x1800af70e  mov     rax, [rax+8]
0x1800af712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af717  cmp     [rbx+58h], rbp
0x1800af71b  jnz     short loc_1800AF735
0x1800af71d  mov     rcx, [rsp+78h+arg_20]
0x1800af725  mov     [rbx+58h], rcx
0x1800af729  mov     rdx, [rcx]
0x1800af72c  mov     rax, [rdx+8]
0x1800af730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af735  mov     [rbx+78h], r12
0x1800af739  mov     eax, ebp
0x1800af73b  add     rsp, 40h
0x1800af73f  pop     r15
0x1800af741  pop     r14
0x1800af743  pop     r12
0x1800af745  pop     rdi
0x1800af746  pop     rsi
0x1800af747  pop     rbp
0x1800af748  pop     rbx
0x1800af749  retn
```
