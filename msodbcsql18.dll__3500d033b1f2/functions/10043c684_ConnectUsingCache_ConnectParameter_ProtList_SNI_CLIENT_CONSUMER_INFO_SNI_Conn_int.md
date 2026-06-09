# ConnectUsingCache(ConnectParameter *,ProtList *,SNI_CLIENT_CONSUMER_INFO *,SNI_Conn * *,int)

- ea: `0x10043c684`
- end: `0x10043ca4a`
- name: `?ConnectUsingCache@@YA_NPEAVConnectParameter@@PEAVProtList@@PEAUSNI_CLIENT_CONSUMER_INFO@@PEAPEAVSNI_Conn@@H@Z`
- size: `966`
- prototype: `bool __usercall@<al>(struct ConnectParameter *@<rcx>, struct ProtList *@<rdx>, struct SNI_CLIENT_CONSUMER_INFO *@<r8>, struct SNI_Conn **@<r9>, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x10043d748`

## callees

- `0x100413560`
- `0x10043c498`
- `0x10043c684`
- `0x10043cafc`
- `0x10043e35c`
- `0x10043f328`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x10043c855`
- `KERNEL32!CompareStringW` at `0x10043c855`
- `KERNEL32!GetTickCount` at `0x10043c73d`
- `KERNEL32!GetTickCount` at `0x10043c911`
- `KERNEL32!GetTickCount` at `0x10043c73d`
- `KERNEL32!GetTickCount` at `0x10043c911`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall ConnectUsingCache(
        struct ConnectParameter *a1,
        struct ProtList *a2,
        struct SNI_CLIENT_CONSUMER_INFO *a3,
        struct SNI_Conn **a4,
        int a5)
{
  char v9; // bl
  unsigned int v10; // esi
  struct ProtElem *v11; // r8
  wchar_t *v12; // r9
  __int64 v13; // r8
  const WCHAR *v14; // r8
  const unsigned __int16 *v15; // rdx
  DWORD v16; // ecx
  const unsigned __int16 *v17; // rdx
  struct SNI_Conn **cchCount2; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+30h] [rbp-D0h]
  DWORD TickCount; // [rsp+40h] [rbp-C0h]
  _QWORD v22[3]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v23[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v24; // [rsp+64h] [rbp-9Ch]
  __int16 v25; // [rsp+68h] [rbp-98h]
  __int16 v26; // [rsp+268h] [rbp+168h]
  __int16 v27; // [rsp+468h] [rbp+368h]
  __int64 v28; // [rsp+A68h] [rbp+968h]

  v22[1] = -2;
  v22[0] = -1;
  v9 = 0;
  v10 = a5;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E7EE8[0] )
  {
    v20 = a5;
    cchCount2 = a4;
    bidScopeEnterW(v22, off_1005E7EE8[0], a1);
  }
  *(_DWORD *)v23 = 9;
  v24 = 9;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  TickCount = GetTickCount();
  if ( ProtElem::Init((ProtElem *)v23, (const unsigned __int16 *const)a1, (const unsigned __int16 *const)a1 + 256) )
  {
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E5E40[0] && bidID != -1 )
    {
      v12 = off_1005E5E40[0];
      v13 = 507904;
LABEL_42:
      ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD, struct SNI_Conn **, int))off_1005D39E0[0])(
        bidID,
        0,
        v13,
        v12,
        0,
        cchCount2,
        v20);
      goto LABEL_48;
    }
    goto LABEL_48;
  }
  if ( (unsigned int)LastConnectCache::GetEntry((struct ConnectParameter *)((char *)a1 + 2070), v23, v11) )
  {
    if ( *((_WORD *)a1 + 768) )
    {
      switch ( *(_DWORD *)v23 )
      {
        case 1:
          v14 = L"np";
          break;
        case 4:
          v14 = L"lpc";
          break;
        case 7:
          v14 = L"tcp";
          break;
        default:
LABEL_22:
          if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E5E50[0] && bidID != -1 )
          {
            v12 = off_1005E5E50[0];
            v13 = 560128;
            goto LABEL_42;
          }
          goto LABEL_48;
      }
      if ( CompareStringW(0x800u, 0x20000u, v14, -1, (PCNZWCH)a1 + 768, -1) != 2 )
        goto LABEL_22;
    }
    else if ( !ProtList::Find(a2, *(unsigned int *)v23) )
    {
      LastConnectCache::RemoveEntry((struct ConnectParameter *)((char *)a1 + 2070), v15);
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E5E58[0] && bidID != -1 )
      {
        v12 = off_1005E5E58[0];
        v13 = 569344;
        goto LABEL_42;
      }
      goto LABEL_48;
    }
    if ( a5 != -1 )
    {
      v16 = a5 + TickCount - GetTickCount();
      v10 = -2;
      if ( v16 != -1 )
        v10 = v16;
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E5E60[0] )
        bidTraceW(0, 585728, off_1005E5E60[0], v10);
    }
    if ( Connect(a1, a3, (struct ProtElem *)v23, a4, v10) )
    {
      LastConnectCache::RemoveEntry((struct ConnectParameter *)((char *)a1 + 2070), v17);
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E5E68[0] && bidID != -1 )
      {
        v12 = off_1005E5E68[0];
        v13 = 592896;
        goto LABEL_42;
      }
    }
    else
    {
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E5E70[0] && bidID != -1 )
        ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD, struct SNI_Conn **, int))off_1005D39E0[0])(
          bidID,
          0,
          598016,
          off_1005E5E70[0],
          0,
          cchCount2,
          v20);
      v9 = 1;
    }
    goto LABEL_48;
  }
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E5E48[0] && bidID != -1 )
  {
    v12 = off_1005E5E48[0];
    v13 = 517120;
    goto LABEL_42;
  }
LABEL_48:
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)v22);
  return v9;
}

```

## disassembly

```asm
0x10043c684  push    rbp
0x10043c686  push    rbx
0x10043c687  push    rsi
0x10043c688  push    rdi
0x10043c689  push    r12
0x10043c68b  push    r13
0x10043c68d  push    r14
0x10043c68f  push    r15
0x10043c691  lea     rbp, [rsp-988h]
0x10043c699  sub     rsp, 0A88h
0x10043c6a0  mov     [rsp+0AC0h+var_A70], 0FFFFFFFFFFFFFFFEh
0x10043c6a9  mov     rax, cs:__security_cookie
0x10043c6b0  xor     rax, rsp
0x10043c6b3  mov     [rbp+9C0h+var_50], rax
0x10043c6ba  mov     r13, r9
0x10043c6bd  mov     r12, r8
0x10043c6c0  mov     rdi, rdx
0x10043c6c3  mov     r14, rcx
0x10043c6c6  or      [rsp+0AC0h+var_A78], 0FFFFFFFFFFFFFFFFh
0x10043c6cc  mov     eax, cs:_bidGblFlags
0x10043c6d2  mov     ecx, 20004h
0x10043c6d7  and     eax, ecx
0x10043c6d9  xor     ebx, ebx
0x10043c6db  mov     esi, [rbp+9C0h+arg_20]
0x10043c6e1  cmp     eax, ecx
0x10043c6e3  jnz     short loc_10043C716
0x10043c6e5  mov     rax, cs:off_1005E7EE8; "<ConnectUsingCache|API|SNI> pConnectPar"...
0x10043c6ec  test    rax, rax
0x10043c6ef  jz      short loc_10043C716
0x10043c6f1  mov     [rsp+0AC0h+var_A90], esi
0x10043c6f5  mov     qword ptr [rsp+0AC0h+cchCount2], r9; cchCount2
0x10043c6fa  mov     [rsp+0AC0h+lpString2], r8
0x10043c6ff  mov     r9, rdx
0x10043c702  mov     r8, r14
0x10043c705  mov     rdx, cs:off_1005E7EE8; "<ConnectUsingCache|API|SNI> pConnectPar"...
0x10043c70c  lea     rcx, [rsp+0AC0h+var_A78]
0x10043c711  call    _bidScopeEnterW
0x10043c716  mov     eax, 9
0x10043c71b  mov     dword ptr [rsp+0AC0h+var_A60], eax
0x10043c71f  mov     [rsp+0AC0h+var_A5C], eax
0x10043c723  mov     [rsp+0AC0h+var_A58], bx
0x10043c728  mov     [rbp+9C0h+var_858], bx
0x10043c72f  mov     [rbp+9C0h+var_658], bx
0x10043c736  mov     [rbp+9C0h+var_58], rbx
0x10043c73d  call    cs:__imp_GetTickCount
0x10043c743  mov     [rsp+0AC0h+var_A80], eax
0x10043c747  lea     r8, [r14+200h]; unsigned __int16 *
0x10043c74e  mov     rdx, r14; unsigned __int16 *
0x10043c751  lea     rcx, [rsp+0AC0h+var_A60]; this
0x10043c756  call    ?Init@ProtElem@@QEAAKQEBG0@Z; ProtElem::Init(ushort const * const,ushort const * const)
0x10043c75b  test    eax, eax
0x10043c75d  jz      short loc_10043C7A4
0x10043c75f  mov     eax, cs:_bidGblFlags
0x10043c765  mov     edi, 20002h
0x10043c76a  and     eax, edi
0x10043c76c  cmp     eax, edi
0x10043c76e  jnz     loc_10043CA1B
0x10043c774  mov     rax, cs:off_1005E5E40; "<ConnectUsingCache|RET|SNI> false\n"
0x10043c77b  test    rax, rax
0x10043c77e  jz      loc_10043CA1B
0x10043c784  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x10043c78c  jz      loc_10043CA1B
0x10043c792  mov     r9, cs:off_1005E5E40; "<ConnectUsingCache|RET|SNI> false\n"
0x10043c799  mov     r8d, 7C000h
0x10043c79f  jmp     loc_10043C9B2
0x10043c7a4  lea     r15, [r14+816h]
0x10043c7ab  lea     rdx, [rsp+0AC0h+var_A60]; unsigned __int16 *
0x10043c7b0  mov     rcx, r15; this
0x10043c7b3  call    ?GetEntry@LastConnectCache@@YAHPEBGPEAVProtElem@@@Z; LastConnectCache::GetEntry(ushort const *,ProtElem *)
0x10043c7b8  test    eax, eax
0x10043c7ba  jnz     short loc_10043C801
0x10043c7bc  mov     eax, cs:_bidGblFlags
0x10043c7c2  mov     edi, 20002h
0x10043c7c7  and     eax, edi
0x10043c7c9  cmp     eax, edi
0x10043c7cb  jnz     loc_10043CA1B
0x10043c7d1  mov     rax, cs:off_1005E5E48; "<ConnectUsingCache|RET|SNI> false\n"
0x10043c7d8  test    rax, rax
0x10043c7db  jz      loc_10043CA1B
0x10043c7e1  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x10043c7e9  jz      loc_10043CA1B
0x10043c7ef  mov     r9, cs:off_1005E5E48; "<ConnectUsingCache|RET|SNI> false\n"
0x10043c7f6  mov     r8d, 7E400h
0x10043c7fc  jmp     loc_10043C9B2
0x10043c801  lea     rdx, [r14+600h]
0x10043c808  cmp     [rdx], bx
0x10043c80b  jz      loc_10043C8A9
0x10043c811  mov     ecx, dword ptr [rsp+0AC0h+var_A60]
0x10043c815  sub     ecx, 1
0x10043c818  jz      short loc_10043C836
0x10043c81a  sub     ecx, 3
0x10043c81d  jz      short loc_10043C82D
0x10043c81f  cmp     ecx, 3
0x10043c822  jnz     short loc_10043C864
0x10043c824  lea     r8, aTcp_1; "tcp"
0x10043c82b  jmp     short loc_10043C83D
0x10043c82d  lea     r8, aLpc; "lpc"
0x10043c834  jmp     short loc_10043C83D
0x10043c836  lea     r8, aNp; "np"
0x10043c83d  or      [rsp+0AC0h+cchCount2], 0FFFFFFFFh
0x10043c842  mov     [rsp+0AC0h+lpString2], rdx; lpString2
0x10043c847  or      r9d, 0FFFFFFFFh; cchCount1
0x10043c84b  mov     edx, 20000h; dwCmpFlags
0x10043c850  mov     ecx, 800h; Locale
0x10043c855  call    cs:__imp_CompareStringW
0x10043c85b  cmp     eax, 2
0x10043c85e  jz      loc_10043C907
0x10043c864  mov     eax, cs:_bidGblFlags
0x10043c86a  mov     edi, 20002h
0x10043c86f  and     eax, edi
0x10043c871  cmp     eax, edi
0x10043c873  jnz     loc_10043CA1B
0x10043c879  mov     rax, cs:off_1005E5E50; "<ConnectUsingCache|RET|SNI> false\n"
0x10043c880  test    rax, rax
0x10043c883  jz      loc_10043CA1B
0x10043c889  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x10043c891  jz      loc_10043CA1B
0x10043c897  mov     r9, cs:off_1005E5E50; "<ConnectUsingCache|RET|SNI> false\n"
0x10043c89e  mov     r8d, 88C00h
0x10043c8a4  jmp     loc_10043C9B2
0x10043c8a9  mov     edx, dword ptr [rsp+0AC0h+var_A60]
0x10043c8ad  mov     rcx, rdi
0x10043c8b0  call    ?Find@ProtList@@QEAAPEAVProtElem@@W4ProviderNum@@@Z; ProtList::Find(ProviderNum)
0x10043c8b5  test    rax, rax
0x10043c8b8  jnz     short loc_10043C907
0x10043c8ba  mov     rcx, r15; this
0x10043c8bd  call    ?RemoveEntry@LastConnectCache@@YAXPEBG@Z; LastConnectCache::RemoveEntry(ushort const *)
0x10043c8c2  mov     eax, cs:_bidGblFlags
0x10043c8c8  mov     edi, 20002h
0x10043c8cd  and     eax, edi
0x10043c8cf  cmp     eax, edi
0x10043c8d1  jnz     loc_10043CA1B
0x10043c8d7  mov     rax, cs:off_1005E5E58; "<ConnectUsingCache|RET|SNI> false\n"
0x10043c8de  test    rax, rax
0x10043c8e1  jz      loc_10043CA1B
0x10043c8e7  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x10043c8ef  jz      loc_10043CA1B
0x10043c8f5  mov     r9, cs:off_1005E5E58; "<ConnectUsingCache|RET|SNI> false\n"
0x10043c8fc  mov     r8d, 8B000h
0x10043c902  jmp     loc_10043C9B2
0x10043c907  mov     edi, 20002h
0x10043c90c  cmp     esi, 0FFFFFFFFh
0x10043c90f  jz      short loc_10043C958
0x10043c911  call    cs:__imp_GetTickCount
0x10043c917  mov     ecx, [rsp+0AC0h+var_A80]
0x10043c91b  add     ecx, esi
0x10043c91d  sub     ecx, eax
0x10043c91f  mov     esi, 0FFFFFFFEh
0x10043c924  cmp     ecx, 0FFFFFFFFh
0x10043c927  cmovnz  esi, ecx
0x10043c92a  mov     eax, cs:_bidGblFlags
0x10043c930  and     eax, edi
0x10043c932  cmp     eax, edi
0x10043c934  jnz     short loc_10043C958
0x10043c936  mov     rax, cs:off_1005E5E60; "<ConnectUsingCache|SNI> timeout: %d\n"
0x10043c93d  test    rax, rax
0x10043c940  jz      short loc_10043C958
0x10043c942  mov     r9d, esi
0x10043c945  mov     r8, cs:off_1005E5E60; "<ConnectUsingCache|SNI> timeout: %d\n"
0x10043c94c  mov     edx, 8F000h
0x10043c951  xor     ecx, ecx
0x10043c953  call    _bidTraceW
0x10043c958  mov     dword ptr [rsp+0AC0h+lpString2], esi; int
0x10043c95c  mov     r9, r13; struct SNI_Conn **
0x10043c95f  lea     r8, [rsp+0AC0h+var_A60]; struct ProtElem *
0x10043c964  mov     rdx, r12; struct SNI_CLIENT_CONSUMER_INFO *
0x10043c967  mov     rcx, r14; struct ConnectParameter *
0x10043c96a  call    ?Connect@@YAKPEAVConnectParameter@@PEAUSNI_CLIENT_CONSUMER_INFO@@PEAVProtElem@@PEAPEAVSNI_Conn@@H@Z; Connect(ConnectParameter *,SNI_CLIENT_CONSUMER_INFO *,ProtElem *,SNI_Conn * *,int)
0x10043c96f  test    eax, eax
0x10043c971  jz      short loc_10043C9CF
0x10043c973  mov     rcx, r15; this
0x10043c976  call    ?RemoveEntry@LastConnectCache@@YAXPEBG@Z; LastConnectCache::RemoveEntry(ushort const *)
0x10043c97b  mov     eax, cs:_bidGblFlags
0x10043c981  and     eax, edi
0x10043c983  cmp     eax, edi
0x10043c985  jnz     loc_10043CA1B
0x10043c98b  mov     rax, cs:off_1005E5E68; "<ConnectUsingCache|RET|SNI> false\n"
0x10043c992  test    rax, rax
0x10043c995  jz      loc_10043CA1B
0x10043c99b  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x10043c9a3  jz      short loc_10043CA1B
0x10043c9a5  mov     r9, cs:off_1005E5E68; "<ConnectUsingCache|RET|SNI> false\n"
0x10043c9ac  mov     r8d, 90C00h
0x10043c9b2  mov     rax, cs:off_1005D39E0
0x10043c9b9  mov     [rsp+0AC0h+lpString2], rbx
0x10043c9be  xor     edx, edx
0x10043c9c0  mov     rcx, cs:_bidID
0x10043c9c7  call    cs:__guard_dispatch_icall_fptr
0x10043c9cd  jmp     short loc_10043CA1B
0x10043c9cf  mov     eax, cs:_bidGblFlags
0x10043c9d5  and     eax, edi
0x10043c9d7  cmp     eax, edi
0x10043c9d9  jnz     short loc_10043CA19
0x10043c9db  mov     rax, cs:off_1005E5E70; "<ConnectUsingCache|RET|SNI> true\n"
0x10043c9e2  test    rax, rax
0x10043c9e5  jz      short loc_10043CA19
0x10043c9e7  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x10043c9ef  jz      short loc_10043CA19
0x10043c9f1  mov     rax, cs:off_1005D39E0
0x10043c9f8  mov     [rsp+0AC0h+lpString2], rbx
0x10043c9fd  mov     r9, cs:off_1005E5E70; "<ConnectUsingCache|RET|SNI> true\n"
0x10043ca04  xor     edx, edx
0x10043ca06  mov     r8d, 92000h
0x10043ca0c  mov     rcx, cs:_bidID
0x10043ca13  call    cs:__guard_dispatch_icall_fptr
0x10043ca19  mov     bl, 1
0x10043ca1b  lea     rcx, [rsp+0AC0h+var_A78]; this
0x10043ca20  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x10043ca25  mov     al, bl
0x10043ca27  mov     rcx, [rbp+9C0h+var_50]
0x10043ca2e  xor     rcx, rsp; StackCookie
0x10043ca31  call    __security_check_cookie
0x10043ca36  add     rsp, 0A88h
0x10043ca3d  pop     r15
0x10043ca3f  pop     r14
0x10043ca41  pop     r13
0x10043ca43  pop     r12
0x10043ca45  pop     rdi
0x10043ca46  pop     rsi
0x10043ca47  pop     rbx
0x10043ca48  pop     rbp
0x10043ca49  retn
```
