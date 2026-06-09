# CFveApi::AllowReseal(CScopedPolicyRedirector *,int *)

- ea: `0x1800bc56c`
- end: `0x1800bc97d`
- name: `?AllowReseal@CFveApi@@AEAAJPEAVCScopedPolicyRedirector@@PEAH@Z`
- size: `1041`
- prototype: `__int64 __fastcall(CFveApi *__hidden this, struct CScopedPolicyRedirector *, int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x1800c60fc`

## callees

- `0x180008d70`
- `0x1800090c0`
- `0x18000aae0`
- `0x18000ba30`
- `0x180018b10`
- `0x18003e7a8`
- `0x180047570`
- `0x18009ba80`
- `0x18009befc`
- `0x1800bc56c`
- `0x1800eb4b0`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `bcd!BcdCloseObject` at `0x1800bc900`
- `bcd!BcdCloseObject` at `0x180126d00`
- `bcd!BcdCloseObject` at `0x1800bc900`
- `bcd!BcdCloseObject` at `0x180126d00`
- `bcd!BcdOpenObject` at `0x1800bc75f`
- `bcd!BcdOpenObject` at `0x1800bc75f`
- `bcd!BcdCloseStore` at `0x1800bc920`
- `bcd!BcdCloseStore` at `0x180126d16`
- `bcd!BcdCloseStore` at `0x1800bc920`
- `bcd!BcdCloseStore` at `0x180126d16`
- `bcd!BcdOpenSystemStore` at `0x1800bc6d2`
- `bcd!BcdOpenSystemStore` at `0x1800bc6d2`

## pseudocode

```c
__int64 __fastcall CFveApi::AllowReseal(CFveApi *this, struct CScopedPolicyRedirector *a2, int *a3)
{
  __int64 v6; // rdx
  PVOID *v7; // rcx
  unsigned int v8; // ebx
  int DoesRegKeyExist; // eax
  __int64 v10; // rdx
  __int64 v11; // rdx
  int v12; // eax
  int v13; // eax
  __int64 v15; // [rsp+20h] [rbp-288h] BYREF
  void *lpMem; // [rsp+28h] [rbp-280h] BYREF
  unsigned int v17; // [rsp+30h] [rbp-278h] BYREF
  struct CFvePolicy *v18; // [rsp+38h] [rbp-270h] BYREF
  void *v19; // [rsp+40h] [rbp-268h] BYREF
  void *v20; // [rsp+48h] [rbp-260h] BYREF
  struct _GUID v21; // [rsp+50h] [rbp-258h] BYREF
  unsigned __int16 v22[264]; // [rsp+60h] [rbp-248h] BYREF

  v21 = 0;
  v19 = 0;
  v18 = 0;
  lpMem = 0;
  v17 = 0;
  v20 = 0;
  HIDWORD(v15) = 0;
  memset_0(v22, 0, 0x208u);
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a3 )
  {
    v8 = -2147467261;
    goto LABEL_52;
  }
  *a3 = 0;
  DoesRegKeyExist = NgscbpDoesRegKeyExist(v7, v6, (char *)&v15 + 4);
  v8 = DoesRegKeyExist;
  if ( DoesRegKeyExist < 0 )
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v10 = 11;
LABEL_10:
      WPP_SF_d(v7[2], v10, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, (unsigned int)DoesRegKeyExist);
LABEL_51:
      v7 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_52;
    }
    goto LABEL_52;
  }
  if ( (*((_DWORD *)this + 27) & 0x10000001) != 0 )
  {
    if ( !HIDWORD(v15) )
      goto LABEL_50;
  }
  else if ( !HIDWORD(v15) )
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_52;
    v11 = 12;
    goto LABEL_16;
  }
  v12 = BcdOpenSystemStore(&v19, v6);
  DoesRegKeyExist = FromNtStatus(v12);
  v8 = DoesRegKeyExist;
  if ( DoesRegKeyExist >= 0 )
  {
    DoesRegKeyExist = CFveApiBase::GetAssociatedOs(v19, &v21);
    v8 = DoesRegKeyExist;
    if ( DoesRegKeyExist < 0 )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v10 = 14;
        goto LABEL_10;
      }
      goto LABEL_52;
    }
    v13 = BcdOpenObject(v19, &v21, &v20);
    DoesRegKeyExist = FromNtStatus(v13);
    v8 = DoesRegKeyExist;
    if ( DoesRegKeyExist < 0 )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v10 = 15;
        goto LABEL_10;
      }
      goto LABEL_52;
    }
    DoesRegKeyExist = CFveApiBase::GetBcdElementData(v20, 0x21000001u, &lpMem, &v17);
    v8 = DoesRegKeyExist;
    LODWORD(v15) = DoesRegKeyExist;
    if ( DoesRegKeyExist < 0 )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v10 = 16;
        goto LABEL_10;
      }
      goto LABEL_52;
    }
    if ( *(_DWORD *)lpMem != 2 )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_52;
      v11 = 17;
LABEL_16:
      WPP_SF_(v7[2], v11, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids);
      goto LABEL_51;
    }
    DoesRegKeyExist = StringCchPrintfW(v22, 0x104u, L"\\\\?\\GLOBALROOT%s", (char *)lpMem + 20, v15);
    v8 = DoesRegKeyExist;
    if ( DoesRegKeyExist < 0 )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v10 = 18;
        goto LABEL_10;
      }
      goto LABEL_52;
    }
    DoesRegKeyExist = CFveApiBase::GetPolicy(this, &v18);
    v8 = DoesRegKeyExist;
    if ( DoesRegKeyExist < 0 )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v10 = 19;
        goto LABEL_10;
      }
      goto LABEL_52;
    }
    DoesRegKeyExist = CScopedPolicyRedirector::RedirectFvePolicy(a2, v18, v22);
    v8 = DoesRegKeyExist;
    if ( DoesRegKeyExist < 0 )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v10 = 20;
        goto LABEL_10;
      }
      goto LABEL_52;
    }
LABEL_50:
    *a3 = 1;
    goto LABEL_51;
  }
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v10 = 13;
    goto LABEL_10;
  }
LABEL_52:
  if ( lpMem )
  {
    CFveApiBase::FastFree(lpMem);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v20 )
  {
    BcdCloseObject(v20);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v19 )
  {
    BcdCloseStore(v19, v6);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x20) != 0 )
    WPP_SF_d(v7[2], 21, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x1800bc56c  mov     [rsp+arg_18], rbx
0x1800bc571  push    rsi
0x1800bc572  push    rdi
0x1800bc573  push    r13
0x1800bc575  push    r14
0x1800bc577  push    r15
0x1800bc579  sub     rsp, 280h
0x1800bc580  mov     rax, cs:__security_cookie
0x1800bc587  xor     rax, rsp
0x1800bc58a  mov     [rsp+2A8h+var_38], rax
0x1800bc592  mov     rsi, r8
0x1800bc595  mov     r15, rdx
0x1800bc598  mov     r14, rcx
0x1800bc59b  xorps   xmm0, xmm0
0x1800bc59e  movups  xmmword ptr [rsp+2A8h+var_258.Data1], xmm0
0x1800bc5a3  mov     [rsp+2A8h+var_268], 0
0x1800bc5ac  mov     [rsp+2A8h+var_270], 0
0x1800bc5b5  mov     [rsp+2A8h+lpMem], 0
0x1800bc5be  mov     [rsp+2A8h+var_278], 0
0x1800bc5c6  mov     [rsp+2A8h+var_260], 0
0x1800bc5cf  mov     [rsp+2A8h+var_284], 0
0x1800bc5d7  xor     edx, edx; Val
0x1800bc5d9  mov     r8d, 208h; Size
0x1800bc5df  lea     rcx, [rsp+2A8h+var_248]; void *
0x1800bc5e4  call    memset_0
0x1800bc5e9  lea     r13, WPP_GLOBAL_Control
0x1800bc5f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc5f7  lea     rdi, WPP_e2677893b9163e8423a47779f4b931d1_Traceguids
0x1800bc5fe  cmp     rcx, r13
0x1800bc601  jz      short loc_1800BC621
0x1800bc603  test    byte ptr [rcx+1Ch], 20h
0x1800bc607  jz      short loc_1800BC621
0x1800bc609  mov     edx, 0Ah
0x1800bc60e  mov     r8, rdi
0x1800bc611  mov     rcx, [rcx+10h]
0x1800bc615  call    WPP_SF_
0x1800bc61a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc621  test    rsi, rsi
0x1800bc624  jnz     short loc_1800BC634
0x1800bc626  mov     ebx, 80004003h
0x1800bc62b  mov     [rsp+2A8h+var_288], ebx
0x1800bc62f  jmp     loc_1800BC8DA
0x1800bc634  mov     dword ptr [rsi], 0
0x1800bc63a  lea     r8, [rsp+2A8h+var_284]
0x1800bc63f  call    NgscbpDoesRegKeyExist
0x1800bc644  mov     ebx, eax
0x1800bc646  mov     [rsp+2A8h+var_288], eax
0x1800bc64a  test    eax, eax
0x1800bc64c  jns     short loc_1800BC681
0x1800bc64e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc655  cmp     rcx, r13
0x1800bc658  jz      loc_1800BC8DA
0x1800bc65e  test    byte ptr [rcx+1Ch], 2
0x1800bc662  jz      loc_1800BC8DA
0x1800bc668  mov     edx, 0Bh
0x1800bc66d  mov     r9d, eax
0x1800bc670  mov     r8, rdi
0x1800bc673  mov     rcx, [rcx+10h]
0x1800bc677  call    WPP_SF_d
0x1800bc67c  jmp     loc_1800BC8D3
0x1800bc681  test    dword ptr [r14+6Ch], 10000001h
0x1800bc689  jnz     short loc_1800BC6C2
0x1800bc68b  cmp     [rsp+2A8h+var_284], 0
0x1800bc690  jnz     short loc_1800BC6CD
0x1800bc692  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc699  cmp     rcx, r13
0x1800bc69c  jz      loc_1800BC8DA
0x1800bc6a2  test    byte ptr [rcx+1Ch], 8
0x1800bc6a6  jz      loc_1800BC8DA
0x1800bc6ac  mov     edx, 0Ch
0x1800bc6b1  mov     r8, rdi
0x1800bc6b4  mov     rcx, [rcx+10h]
0x1800bc6b8  call    WPP_SF_
0x1800bc6bd  jmp     loc_1800BC8D3
0x1800bc6c2  cmp     [rsp+2A8h+var_284], 0
0x1800bc6c7  jz      loc_1800BC8CD
0x1800bc6cd  lea     rcx, [rsp+2A8h+var_268]
0x1800bc6d2  call    cs:__imp_BcdOpenSystemStore
0x1800bc6d9  nop     dword ptr [rax+rax+00h]
0x1800bc6de  mov     ecx, eax; int
0x1800bc6e0  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800bc6e5  mov     ebx, eax
0x1800bc6e7  mov     [rsp+2A8h+var_288], eax
0x1800bc6eb  test    eax, eax
0x1800bc6ed  jns     short loc_1800BC713
0x1800bc6ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc6f6  cmp     rcx, r13
0x1800bc6f9  jz      loc_1800BC8DA
0x1800bc6ff  test    byte ptr [rcx+1Ch], 2
0x1800bc703  jz      loc_1800BC8DA
0x1800bc709  mov     edx, 0Dh
0x1800bc70e  jmp     loc_1800BC66D
0x1800bc713  lea     rdx, [rsp+2A8h+var_258]; struct _GUID *
0x1800bc718  mov     rcx, [rsp+2A8h+var_268]; void *
0x1800bc71d  call    ?GetAssociatedOs@CFveApiBase@@KAJPEAXPEAU_GUID@@@Z; CFveApiBase::GetAssociatedOs(void *,_GUID *)
0x1800bc722  mov     ebx, eax
0x1800bc724  mov     [rsp+2A8h+var_288], eax
0x1800bc728  test    eax, eax
0x1800bc72a  jns     short loc_1800BC750
0x1800bc72c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc733  cmp     rcx, r13
0x1800bc736  jz      loc_1800BC8DA
0x1800bc73c  test    byte ptr [rcx+1Ch], 2
0x1800bc740  jz      loc_1800BC8DA
0x1800bc746  mov     edx, 0Eh
0x1800bc74b  jmp     loc_1800BC66D
0x1800bc750  lea     r8, [rsp+2A8h+var_260]
0x1800bc755  lea     rdx, [rsp+2A8h+var_258]
0x1800bc75a  mov     rcx, [rsp+2A8h+var_268]
0x1800bc75f  call    cs:__imp_BcdOpenObject
0x1800bc766  nop     dword ptr [rax+rax+00h]
0x1800bc76b  mov     ecx, eax; int
0x1800bc76d  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800bc772  mov     ebx, eax
0x1800bc774  mov     [rsp+2A8h+var_288], eax
0x1800bc778  test    eax, eax
0x1800bc77a  jns     short loc_1800BC7A0
0x1800bc77c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc783  cmp     rcx, r13
0x1800bc786  jz      loc_1800BC8DA
0x1800bc78c  test    byte ptr [rcx+1Ch], 2
0x1800bc790  jz      loc_1800BC8DA
0x1800bc796  mov     edx, 0Fh
0x1800bc79b  jmp     loc_1800BC66D
0x1800bc7a0  lea     r9, [rsp+2A8h+var_278]; unsigned int *
0x1800bc7a5  lea     r8, [rsp+2A8h+lpMem]; void **
0x1800bc7aa  mov     edx, 21000001h; unsigned int
0x1800bc7af  mov     rcx, [rsp+2A8h+var_260]; void *
0x1800bc7b4  call    ?GetBcdElementData@CFveApiBase@@SAJPEAXKPEAPEAXPEAK@Z; CFveApiBase::GetBcdElementData(void *,ulong,void * *,ulong *)
0x1800bc7b9  mov     ebx, eax
0x1800bc7bb  mov     [rsp+2A8h+var_288], eax
0x1800bc7bf  test    eax, eax
0x1800bc7c1  jns     short loc_1800BC7E7
0x1800bc7c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc7ca  cmp     rcx, r13
0x1800bc7cd  jz      loc_1800BC8DA
0x1800bc7d3  test    byte ptr [rcx+1Ch], 2
0x1800bc7d7  jz      loc_1800BC8DA
0x1800bc7dd  mov     edx, 10h
0x1800bc7e2  jmp     loc_1800BC66D
0x1800bc7e7  mov     rax, [rsp+2A8h+lpMem]
0x1800bc7ec  cmp     dword ptr [rax], 2
0x1800bc7ef  jz      short loc_1800BC815
0x1800bc7f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc7f8  cmp     rcx, r13
0x1800bc7fb  jz      loc_1800BC8DA
0x1800bc801  test    byte ptr [rcx+1Ch], 8
0x1800bc805  jz      loc_1800BC8DA
0x1800bc80b  mov     edx, 11h
0x1800bc810  jmp     loc_1800BC6B1
0x1800bc815  mov     r9, [rsp+2A8h+lpMem]
0x1800bc81a  add     r9, 14h
0x1800bc81e  lea     r8, aGlobalrootS; "\\\\?\\GLOBALROOT%s"
0x1800bc825  mov     edx, 104h; unsigned __int64
0x1800bc82a  lea     rcx, [rsp+2A8h+var_248]; unsigned __int16 *
0x1800bc82f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800bc834  mov     ebx, eax
0x1800bc836  mov     [rsp+2A8h+var_288], eax
0x1800bc83a  test    eax, eax
0x1800bc83c  jns     short loc_1800BC862
0x1800bc83e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc845  cmp     rcx, r13
0x1800bc848  jz      loc_1800BC8DA
0x1800bc84e  test    byte ptr [rcx+1Ch], 2
0x1800bc852  jz      loc_1800BC8DA
0x1800bc858  mov     edx, 12h
0x1800bc85d  jmp     loc_1800BC66D
0x1800bc862  lea     rdx, [rsp+2A8h+var_270]; struct CFvePolicy **
0x1800bc867  mov     rcx, r14; this
0x1800bc86a  call    ?GetPolicy@CFveApiBase@@IEAAJPEAPEAVCFvePolicy@@@Z; CFveApiBase::GetPolicy(CFvePolicy * *)
0x1800bc86f  mov     ebx, eax
0x1800bc871  mov     [rsp+2A8h+var_288], eax
0x1800bc875  test    eax, eax
0x1800bc877  jns     short loc_1800BC895
0x1800bc879  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc880  cmp     rcx, r13
0x1800bc883  jz      short loc_1800BC8DA
0x1800bc885  test    byte ptr [rcx+1Ch], 2
0x1800bc889  jz      short loc_1800BC8DA
0x1800bc88b  mov     edx, 13h
0x1800bc890  jmp     loc_1800BC66D
0x1800bc895  lea     r8, [rsp+2A8h+var_248]; unsigned __int16 *
0x1800bc89a  mov     rdx, [rsp+2A8h+var_270]; struct CFvePolicy *
0x1800bc89f  mov     rcx, r15; this
0x1800bc8a2  call    ?RedirectFvePolicy@CScopedPolicyRedirector@@QEAAJPEAVCFvePolicy@@PEBG@Z; CScopedPolicyRedirector::RedirectFvePolicy(CFvePolicy *,ushort const *)
0x1800bc8a7  mov     ebx, eax
0x1800bc8a9  mov     [rsp+2A8h+var_288], eax
0x1800bc8ad  test    eax, eax
0x1800bc8af  jns     short loc_1800BC8CD
0x1800bc8b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc8b8  cmp     rcx, r13
0x1800bc8bb  jz      short loc_1800BC8DA
0x1800bc8bd  test    byte ptr [rcx+1Ch], 2
0x1800bc8c1  jz      short loc_1800BC8DA
0x1800bc8c3  mov     edx, 14h
0x1800bc8c8  jmp     loc_1800BC66D
0x1800bc8cd  mov     dword ptr [rsi], 1
0x1800bc8d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc8da  mov     rax, [rsp+2A8h+lpMem]
0x1800bc8df  test    rax, rax
0x1800bc8e2  jz      short loc_1800BC8F3
0x1800bc8e4  mov     rcx, rax; lpMem
0x1800bc8e7  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x1800bc8ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc8f3  mov     rax, [rsp+2A8h+var_260]
0x1800bc8f8  test    rax, rax
0x1800bc8fb  jz      short loc_1800BC913
0x1800bc8fd  mov     rcx, rax
0x1800bc900  call    cs:__imp_BcdCloseObject
0x1800bc907  nop     dword ptr [rax+rax+00h]
0x1800bc90c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc913  mov     rax, [rsp+2A8h+var_268]
0x1800bc918  test    rax, rax
0x1800bc91b  jz      short loc_1800BC933
0x1800bc91d  mov     rcx, rax
0x1800bc920  call    cs:__imp_BcdCloseStore
0x1800bc927  nop     dword ptr [rax+rax+00h]
0x1800bc92c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc933  cmp     rcx, r13
0x1800bc936  jz      short loc_1800BC952
0x1800bc938  test    byte ptr [rcx+1Ch], 20h
0x1800bc93c  jz      short loc_1800BC952
0x1800bc93e  mov     edx, 15h
0x1800bc943  mov     r9d, ebx
0x1800bc946  mov     r8, rdi
0x1800bc949  mov     rcx, [rcx+10h]
0x1800bc94d  call    WPP_SF_d
0x1800bc952  mov     eax, ebx
0x1800bc954  mov     rcx, [rsp+2A8h+var_38]
0x1800bc95c  xor     rcx, rsp; StackCookie
0x1800bc95f  call    __security_check_cookie
0x1800bc964  mov     rbx, [rsp+2A8h+arg_18]
0x1800bc96c  add     rsp, 280h
0x1800bc973  pop     r15
0x1800bc975  pop     r14
0x1800bc977  pop     r13
0x1800bc979  pop     rdi
0x1800bc97a  pop     rsi
0x1800bc97b  retn
0x180126cdf  push    rbp
0x180126ce1  sub     rsp, 20h
0x180126ce5  mov     rbp, rdx
0x180126ce8  mov     rcx, [rbp+28h]; lpMem
0x180126cec  test    rcx, rcx
0x180126cef  jz      short loc_180126CF7
0x180126cf1  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x180126cf6  nop
0x180126cf7  mov     rcx, [rbp+48h]
0x180126cfb  test    rcx, rcx
0x180126cfe  jz      short loc_180126D0D
0x180126d00  call    cs:__imp_BcdCloseObject
0x180126d07  nop     dword ptr [rax+rax+00h]
0x180126d0c  nop
0x180126d0d  mov     rcx, [rbp+40h]
0x180126d11  test    rcx, rcx
0x180126d14  jz      short loc_180126D23
0x180126d16  call    cs:__imp_BcdCloseStore
0x180126d1d  nop     dword ptr [rax+rax+00h]
0x180126d22  nop
0x180126d23  add     rsp, 20h
0x180126d27  pop     rbp
0x180126d28  retn
```
