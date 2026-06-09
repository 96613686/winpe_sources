# CSqmManager::SetNetworkStatus(ushort *)

- ea: `0x1400380dc`
- end: `0x1400383c0`
- name: `?SetNetworkStatus@CSqmManager@@QEAAJPEAG@Z`
- size: `740`
- prototype: `__int64 __fastcall(CSqmManager *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140021e00`

## callees

- `0x140034ce4`
- `0x1400363a4`
- `0x140037868`
- `0x1400380dc`
- `0x140039268`
- `0x1400393ac`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x140038283`
- `KERNEL32!CompareStringW` at `0x140038283`
- `KERNEL32!GetLastError` at `0x1400381e8`
- `KERNEL32!GetLastError` at `0x1400381e8`
- `WS2_32!FreeAddrInfoW` at `0x14003832f`
- `WS2_32!FreeAddrInfoW` at `0x140038372`
- `WS2_32!FreeAddrInfoW` at `0x14003832f`
- `WS2_32!FreeAddrInfoW` at `0x140038372`
- `WS2_32!GetAddrInfoW` at `0x1400381d8`
- `WS2_32!GetAddrInfoW` at `0x1400381d8`

## string_xrefs

- `0x14003813f`: `base\diagnosis\ra\racommon\src\rasqm.cpp`
- `0x140038180`: `base\diagnosis\ra\racommon\src\rasqm.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSqmManager::SetNetworkStatus(CSqmManager *this, unsigned __int16 *a2)
{
  int v2; // esi
  unsigned __int16 **v3; // r12
  unsigned int v4; // r15d
  signed int v5; // eax
  CEventLogger *v6; // rcx
  int v7; // ebx
  signed int LocalV4Addrs; // eax
  CEventLogger *v9; // rcx
  int v10; // r14d
  int v11; // r13d
  signed int LastError; // eax
  CEventLogger *v13; // rcx
  PADDRINFOW v14; // rdi
  USHORT v15; // r9
  USHORT v16; // r10
  USHORT v17; // dx
  USHORT v18; // r8
  const WCHAR *v19; // r13
  const WCHAR *v20; // r11
  const WCHAR *lpString2; // rcx
  struct sockaddr *ai_addr; // rax
  __int16 v23; // cx
  PADDRINFOW ppResult; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int16 **v26; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int16 *v27; // [rsp+40h] [rbp-20h] BYREF
  int v28; // [rsp+48h] [rbp-18h]
  __int128 v29; // [rsp+50h] [rbp-10h]
  const WCHAR *v31; // [rsp+B0h] [rbp+50h] BYREF
  int v32; // [rsp+B8h] [rbp+58h]

  v2 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v3 = 0;
  v26 = 0;
  v4 = 0;
  LODWORD(v31) = 0;
  ppResult = 0;
  v5 = CRATicketInfo::InitializeTicket(&v27, a2);
  v7 = v5;
  if ( v5 >= 0 )
  {
    LocalV4Addrs = GetLocalV4Addrs(&v26, (unsigned int *)&v31);
    v7 = LocalV4Addrs;
    if ( LocalV4Addrs < 0 )
    {
      CEventLogger::LogError(
        v9,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\racommon\\src\\rasqm.cpp",
        0x15Bu,
        L"CSqmManager::SetNetworkStatus",
        LocalV4Addrs);
      v3 = v26;
      v4 = (unsigned int)v31;
      goto LABEL_36;
    }
    v10 = 0;
    v11 = 0;
    v32 = 0;
    v3 = v26;
    v4 = (unsigned int)v31;
    if ( v28 <= 0 )
    {
LABEL_35:
      *((_DWORD *)this + 15) |= v10;
      goto LABEL_36;
    }
    while ( 1 )
    {
      v31 = (const WCHAR *)v11;
      if ( GetAddrInfoW(*(PCWSTR *)(v29 + 8LL * v11), *(PCWSTR *)(*((_QWORD *)&v29 + 1) + 8LL * v11), 0, &ppResult) )
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        if ( v7 < 0 )
        {
          CEventLogger::LogError(
            v13,
            &Recoverable_Error,
            L"base\\diagnosis\\ra\\racommon\\src\\rasqm.cpp",
            0x16Cu,
            L"CSqmManager::SetNetworkStatus",
            v7);
          goto LABEL_36;
        }
      }
      v14 = ppResult;
      if ( ppResult )
        break;
LABEL_33:
      FreeAddrInfoW(v14);
      ppResult = 0;
      if ( v10 != 3 )
      {
        v32 = ++v11;
        if ( v11 < v28 )
          continue;
      }
      goto LABEL_35;
    }
    v15 = in6addr_teredoprefix.u.Word[1];
    v16 = in6addr_teredoprefix.u.Word[0];
    v17 = in6addr_teredoprefix_old.u.Word[1];
    v18 = in6addr_teredoprefix_old.u.Word[0];
    v19 = v31;
LABEL_13:
    if ( v14->ai_family != 2 )
    {
      if ( v14->ai_family == 23 )
      {
        ai_addr = v14->ai_addr;
        if ( ai_addr )
        {
          if ( (v23 = *(_WORD *)&ai_addr->sa_data[6], v23 == v16) && *(_WORD *)&ai_addr->sa_data[8] == v15
            || v23 == v18 && *(_WORD *)&ai_addr->sa_data[8] == v17 )
          {
            v10 |= 1u;
          }
        }
      }
      goto LABEL_31;
    }
    if ( !v14->ai_addr )
      goto LABEL_31;
    v20 = *(const WCHAR **)(v29 + 8LL * (_QWORD)v19);
    v31 = v20;
    if ( !v4 )
    {
LABEL_21:
      v10 |= 2u;
      goto LABEL_22;
    }
    while ( 1 )
    {
      lpString2 = v3[v2];
      if ( lpString2 )
      {
        if ( CompareStringW(0x7Fu, 1u, v20, -1, lpString2, -1) == 2 )
        {
          v15 = in6addr_teredoprefix.u.Word[1];
          v16 = in6addr_teredoprefix.u.Word[0];
          v17 = in6addr_teredoprefix_old.u.Word[1];
          v18 = in6addr_teredoprefix_old.u.Word[0];
LABEL_22:
          v2 = 0;
LABEL_31:
          v14 = v14->ai_next;
          if ( !v14 )
          {
            v11 = v32;
            v14 = ppResult;
            goto LABEL_33;
          }
          goto LABEL_13;
        }
        v20 = v31;
      }
      if ( ++v2 >= v4 )
      {
        v15 = in6addr_teredoprefix.u.Word[1];
        v16 = in6addr_teredoprefix.u.Word[0];
        v17 = in6addr_teredoprefix_old.u.Word[1];
        v18 = in6addr_teredoprefix_old.u.Word[0];
        goto LABEL_21;
      }
    }
  }
  CEventLogger::LogError(
    v6,
    &Recoverable_Error,
    L"base\\diagnosis\\ra\\racommon\\src\\rasqm.cpp",
    0x156u,
    L"CSqmManager::SetNetworkStatus",
    v5);
LABEL_36:
  FreeStringList(v3, v4);
  if ( ppResult )
  {
    FreeAddrInfoW(ppResult);
    ppResult = 0;
  }
  CRATicketInfo::Cleanup((CRATicketInfo *)&v27);
  CRATicketInfo::Cleanup((CRATicketInfo *)&v27);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400380dc  mov     [rsp-38h+arg_8], rbx
0x1400380e1  mov     [rsp-38h+arg_0], rcx
0x1400380e6  push    rbp
0x1400380e7  push    rsi
0x1400380e8  push    rdi
0x1400380e9  push    r12
0x1400380eb  push    r13
0x1400380ed  push    r14
0x1400380ef  push    r15
0x1400380f1  mov     rbp, rsp
0x1400380f4  sub     rsp, 60h
0x1400380f8  xor     esi, esi
0x1400380fa  mov     [rbp+var_20], rsi
0x1400380fe  mov     [rbp+var_18], esi
0x140038101  xorps   xmm0, xmm0
0x140038104  movdqu  [rbp+var_10], xmm0
0x140038109  mov     r12d, esi
0x14003810c  mov     [rbp+var_28], rsi
0x140038110  mov     r15d, esi
0x140038113  mov     dword ptr [rbp+arg_10], esi
0x140038116  mov     [rbp+ppResult], rsi
0x14003811a  lea     rcx, [rbp+var_20]; this
0x14003811e  call    ?InitializeTicket@CRATicketInfo@@QEAAJPEAG@Z; CRATicketInfo::InitializeTicket(ushort *)
0x140038123  mov     ebx, eax
0x140038125  test    eax, eax
0x140038127  jns     short loc_140038157
0x140038129  mov     [rsp+60h+cchCount2], eax; unsigned int
0x14003812d  mov     r9d, 156h; unsigned int
0x140038133  lea     rax, aCsqmmanagerSet_0; "CSqmManager::SetNetworkStatus"
0x14003813a  mov     [rsp+60h+lpString2], rax; unsigned __int16 *
0x14003813f  lea     r8, aBaseDiagnosisR_23; "base\\diagnosis\\ra\\racommon\\src\\ras"...
0x140038146  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14003814d  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140038152  jmp     loc_14003835E
0x140038157  lea     rdx, [rbp+arg_10]; unsigned int *
0x14003815b  lea     rcx, [rbp+var_28]; unsigned __int16 ***
0x14003815f  call    ?GetLocalV4Addrs@@YAJPEAPEAPEAGPEAK@Z; GetLocalV4Addrs(ushort * * *,ulong *)
0x140038164  mov     ebx, eax
0x140038166  test    eax, eax
0x140038168  jns     short loc_1400381A0
0x14003816a  mov     [rsp+60h+cchCount2], eax; unsigned int
0x14003816e  lea     rax, aCsqmmanagerSet_0; "CSqmManager::SetNetworkStatus"
0x140038175  mov     [rsp+60h+lpString2], rax; unsigned __int16 *
0x14003817a  mov     r9d, 15Bh; unsigned int
0x140038180  lea     r8, aBaseDiagnosisR_23; "base\\diagnosis\\ra\\racommon\\src\\ras"...
0x140038187  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14003818e  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140038193  mov     r12, [rbp+var_28]
0x140038197  mov     r15d, dword ptr [rbp+arg_10]
0x14003819b  jmp     loc_14003835E
0x1400381a0  mov     r14d, esi
0x1400381a3  mov     r13d, esi
0x1400381a6  mov     [rbp+arg_18], esi
0x1400381a9  mov     r12, [rbp+var_28]
0x1400381ad  mov     r15d, dword ptr [rbp+arg_10]
0x1400381b1  cmp     [rbp+var_18], esi
0x1400381b4  jle     loc_140038356
0x1400381ba  movsxd  rax, r13d
0x1400381bd  mov     [rbp+arg_10], rax
0x1400381c1  lea     r9, [rbp+ppResult]; ppResult
0x1400381c5  xor     r8d, r8d; pHints
0x1400381c8  mov     rdx, qword ptr [rbp+var_10+8]
0x1400381cc  mov     rdx, [rdx+rax*8]; pServiceName
0x1400381d0  mov     rcx, qword ptr [rbp+var_10]
0x1400381d4  mov     rcx, [rcx+rax*8]; pNodeName
0x1400381d8  call    cs:__imp_GetAddrInfoW
0x1400381df  nop     dword ptr [rax+rax+00h]
0x1400381e4  test    eax, eax
0x1400381e6  jz      short loc_14003820B
0x1400381e8  call    cs:__imp_GetLastError
0x1400381ef  nop     dword ptr [rax+rax+00h]
0x1400381f4  mov     ebx, eax
0x1400381f6  test    eax, eax
0x1400381f8  jle     short loc_140038203
0x1400381fa  movzx   ebx, ax
0x1400381fd  or      ebx, 80070000h
0x140038203  test    ebx, ebx
0x140038205  js      loc_1400383B0
0x14003820b  mov     rdi, [rbp+ppResult]
0x14003820f  test    rdi, rdi
0x140038212  jz      loc_14003832C
0x140038218  movzx   r9d, word ptr cs:in6addr_teredoprefix.u+2
0x140038220  movzx   r10d, word ptr cs:in6addr_teredoprefix.u
0x140038228  movzx   edx, word ptr cs:in6addr_teredoprefix_old.u+2
0x14003822f  movzx   r8d, word ptr cs:in6addr_teredoprefix_old.u
0x140038237  mov     r13, [rbp+arg_10]
0x14003823b  cmp     dword ptr [rdi+4], 2
0x14003823f  jnz     loc_1400382E7
0x140038245  cmp     [rdi+20h], rsi
0x140038249  jz      loc_140038317
0x14003824f  mov     rax, qword ptr [rbp+var_10]
0x140038253  mov     r11, [rax+r13*8]
0x140038257  mov     [rbp+arg_10], r11
0x14003825b  test    r15d, r15d
0x14003825e  jz      short loc_1400382BE
0x140038260  mov     eax, esi
0x140038262  mov     rcx, [r12+rax*8]
0x140038266  test    rcx, rcx
0x140038269  jz      short loc_140038298
0x14003826b  or      eax, 0FFFFFFFFh
0x14003826e  mov     [rsp+60h+cchCount2], eax; cchCount2
0x140038272  mov     [rsp+60h+lpString2], rcx; lpString2
0x140038277  mov     r9d, eax; cchCount1
0x14003827a  mov     r8, r11; lpString1
0x14003827d  lea     edx, [rax+2]; dwCmpFlags
0x140038280  lea     ecx, [rdx+7Eh]; Locale
0x140038283  call    cs:__imp_CompareStringW
0x14003828a  nop     dword ptr [rax+rax+00h]
0x14003828f  cmp     eax, 2
0x140038292  jz      short loc_1400382C6
0x140038294  mov     r11, [rbp+arg_10]
0x140038298  inc     esi
0x14003829a  cmp     esi, r15d
0x14003829d  jb      short loc_140038260
0x14003829f  movzx   r9d, word ptr cs:in6addr_teredoprefix.u+2
0x1400382a7  movzx   r10d, word ptr cs:in6addr_teredoprefix.u
0x1400382af  movzx   edx, word ptr cs:in6addr_teredoprefix_old.u+2
0x1400382b6  movzx   r8d, word ptr cs:in6addr_teredoprefix_old.u
0x1400382be  or      r14d, 2
0x1400382c2  xor     esi, esi
0x1400382c4  jmp     short loc_140038317
0x1400382c6  movzx   r9d, word ptr cs:in6addr_teredoprefix.u+2
0x1400382ce  movzx   r10d, word ptr cs:in6addr_teredoprefix.u
0x1400382d6  movzx   edx, word ptr cs:in6addr_teredoprefix_old.u+2
0x1400382dd  movzx   r8d, word ptr cs:in6addr_teredoprefix_old.u
0x1400382e5  jmp     short loc_1400382C2
0x1400382e7  cmp     dword ptr [rdi+4], 17h
0x1400382eb  jnz     short loc_140038317
0x1400382ed  mov     rax, [rdi+20h]
0x1400382f1  test    rax, rax
0x1400382f4  jz      short loc_140038317
0x1400382f6  movzx   ecx, word ptr [rax+8]
0x1400382fa  cmp     cx, r10w
0x1400382fe  jnz     short loc_140038307
0x140038300  cmp     [rax+0Ah], r9w
0x140038305  jz      short loc_140038313
0x140038307  cmp     cx, r8w
0x14003830b  jnz     short loc_140038317
0x14003830d  cmp     [rax+0Ah], dx
0x140038311  jnz     short loc_140038317
0x140038313  or      r14d, 1
0x140038317  mov     rdi, [rdi+28h]
0x14003831b  test    rdi, rdi
0x14003831e  jnz     loc_14003823B
0x140038324  mov     r13d, [rbp+arg_18]
0x140038328  mov     rdi, [rbp+ppResult]
0x14003832c  mov     rcx, rdi; pAddrInfo
0x14003832f  call    cs:__imp_FreeAddrInfoW
0x140038336  nop     dword ptr [rax+rax+00h]
0x14003833b  mov     [rbp+ppResult], rsi
0x14003833f  cmp     r14d, 3
0x140038343  jz      short loc_140038356
0x140038345  inc     r13d
0x140038348  mov     [rbp+arg_18], r13d
0x14003834c  cmp     r13d, [rbp+var_18]
0x140038350  jl      loc_1400381BA
0x140038356  mov     rax, [rbp+arg_0]
0x14003835a  or      [rax+3Ch], r14d
0x14003835e  mov     edx, r15d; unsigned int
0x140038361  mov     rcx, r12; lpMem
0x140038364  call    ?FreeStringList@@YAJPEAPEAGK@Z; FreeStringList(ushort * *,ulong)
0x140038369  mov     rcx, [rbp+ppResult]; pAddrInfo
0x14003836d  test    rcx, rcx
0x140038370  jz      short loc_140038382
0x140038372  call    cs:__imp_FreeAddrInfoW
0x140038379  nop     dword ptr [rax+rax+00h]
0x14003837e  mov     [rbp+ppResult], rsi
0x140038382  lea     rcx, [rbp+var_20]; this
0x140038386  call    ?Cleanup@CRATicketInfo@@QEAAJXZ; CRATicketInfo::Cleanup(void)
0x14003838b  nop
0x14003838c  lea     rcx, [rbp+var_20]; this
0x140038390  call    ?Cleanup@CRATicketInfo@@QEAAJXZ; CRATicketInfo::Cleanup(void)
0x140038395  mov     eax, ebx
0x140038397  mov     rbx, [rsp+60h+arg_8]
0x14003839f  add     rsp, 60h
0x1400383a3  pop     r15
0x1400383a5  pop     r14
0x1400383a7  pop     r13
0x1400383a9  pop     r12
0x1400383ab  pop     rdi
0x1400383ac  pop     rsi
0x1400383ad  pop     rbp
0x1400383ae  retn
0x1400383b0  mov     [rsp+60h+cchCount2], ebx
0x1400383b4  mov     r9d, 16Ch
0x1400383ba  jmp     loc_140038133
```
