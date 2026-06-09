# CFaxConfigUI::Open(void)

- ea: `0x1800101a0`
- end: `0x180010537`
- name: `?Open@CFaxConfigUI@@UEAAKXZ`
- size: `919`
- prototype: `unsigned int __fastcall(CFaxConfigUI *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180001f9c`
- `0x180005eac`
- `0x180005ed4`
- `0x18000edb0`
- `0x18000fac4`
- `0x18000fc3c`
- `0x18000fd8c`
- `0x1800101a0`
- `0x1800131f0`
- `0x180013410`
- `0x180015cbe`
- `0x180017010`

## import_xrefs

- `FXSAPI!FaxAccessCheckEx2` at `0x180010242`
- `FXSAPI!FaxAccessCheckEx2` at `0x180010242`
- `FXSAPI!FaxConnectFaxServerW` at `0x1800101f4`
- `FXSAPI!FaxConnectFaxServerW` at `0x1800101f4`
- `KERNEL32!GetLastError` at `0x1800101fe`
- `KERNEL32!GetLastError` at `0x180010250`
- `KERNEL32!GetLastError` at `0x1800104ca`
- `KERNEL32!GetLastError` at `0x1800101fe`
- `KERNEL32!GetLastError` at `0x180010250`
- `KERNEL32!GetLastError` at `0x1800104ca`
- `KERNEL32!ActivateActCtx` at `0x1800104a0`
- `KERNEL32!ActivateActCtx` at `0x1800104a0`
- `KERNEL32!DeactivateActCtx` at `0x1800104bf`
- `KERNEL32!DeactivateActCtx` at `0x1800104bf`

## pseudocode

```c
__int64 __fastcall CFaxConfigUI::Open(CFaxConfigUI *this)
{
  DWORD LastError; // eax
  unsigned int v3; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  DWORD v7; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  _QWORD *v11; // rax
  _QWORD *v12; // rbx
  __int64 v13; // rcx
  unsigned int v14; // r8d
  CBaseUI *v15; // rcx
  __int64 v16; // rax
  DWORD v17; // esi
  __int64 v18; // rbx
  __int64 v19; // rax
  __int64 v20; // rbx
  ULONG_PTR Cookie; // [rsp+70h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_3b2439340fb236e4397136d0fae00a22_Traceguids);
  }
  if ( !FaxConnectFaxServerW(0, (LPHANDLE)this + 7) )
  {
    LastError = GetLastError();
    v3 = LastError;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = 20;
      v6 = LastError;
LABEL_56:
      WPP_SF_d(v4[2], v5, WPP_3b2439340fb236e4397136d0fae00a22_Traceguids, v6);
      goto LABEL_57;
    }
    goto LABEL_57;
  }
  if ( !(unsigned int)FaxAccessCheckEx2(*((_QWORD *)this + 7), 32, 0) )
  {
    v7 = GetLastError();
    v3 = v7;
    if ( !v7 )
    {
      v3 = 5;
      goto LABEL_13;
    }
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v10 = 21;
LABEL_19:
    WPP_SF_d(v9[2], v10, WPP_3b2439340fb236e4397136d0fae00a22_Traceguids, v7);
    goto LABEL_13;
  }
  v11 = operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
  v12 = v11;
  if ( v11 )
  {
    v13 = *((_QWORD *)this + 1);
    v11[2] = *((_QWORD *)this + 2);
    v11[1] = v13;
    *((_DWORD *)v11 + 6) = 4650;
    v11[4] = 0;
    memset_0(v11 + 5, 0, 0x60u);
    v12[17] = 0;
    *v12 = &CPropertySheetUI::`vftable';
  }
  else
  {
    v12 = 0;
  }
  *((_QWORD *)this + 3) = v12;
  if ( !v12 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_3b2439340fb236e4397136d0fae00a22_Traceguids);
    }
    v3 = 8;
    goto LABEL_13;
  }
  v7 = CFaxConfigUI::InitializePages(this);
  v3 = v7;
  if ( v7 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v10 = 23;
    goto LABEL_19;
  }
  v7 = CBaseUI::AddPages(*((CBaseUI **)this + 3), *((struct CPage ***)this + 4), *((_DWORD *)this + 12));
  v3 = v7;
  if ( v7 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v10 = 24;
    goto LABEL_19;
  }
  v15 = (CBaseUI *)*((_QWORD *)this + 3);
  Cookie = *((_QWORD *)this + 5);
  v7 = CBaseUI::AddPagesByHandle(v15, (struct _PSP **)&Cookie, v14);
  v3 = v7;
  if ( v7 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v10 = 25;
    goto LABEL_19;
  }
  v16 = *((_QWORD *)this + 3);
  if ( !*(_DWORD *)(v16 + 136) )
  {
    v3 = 87;
    v17 = 87;
    goto LABEL_52;
  }
  v17 = 0;
  v18 = v16 + 40;
  *(_DWORD *)(v16 + 88) = 0;
  v19 = qword_18001E4F0;
  Cookie = 0;
  if ( qword_18001E4F0 == -1 )
  {
    GetProcFromComCtl32(&qword_18001E4F0, "PropertySheetW");
    v19 = qword_18001E4F0;
  }
  if ( v19 )
  {
    Cookie = 0;
    ActivateActCtx(0, &Cookie);
    v20 = ((__int64 (__fastcall *)(__int64))qword_18001E4F0)(v18);
    DeactivateActCtx(0, Cookie);
    if ( v20 < 0 )
      v17 = GetLastError();
  }
  v3 = v17;
  if ( v17 )
  {
LABEL_52:
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v5 = 26;
        v6 = v17;
        goto LABEL_56;
      }
LABEL_57:
      if ( !v3 )
        goto LABEL_14;
    }
LABEL_13:
    FaxMsgBox(*((_QWORD *)this + 2), *((_QWORD *)this + 1), 4656);
  }
LABEL_14:
  CFaxConfigUI::CleanUp(this);
  return v3;
}

```

## disassembly

```asm
0x1800101a0  push    rbx
0x1800101a2  push    rsi
0x1800101a3  push    rdi
0x1800101a4  push    r12
0x1800101a6  push    r14
0x1800101a8  push    r15
0x1800101aa  sub     rsp, 38h
0x1800101ae  mov     rdi, rcx
0x1800101b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800101b8  lea     r15, WPP_GLOBAL_Control
0x1800101bf  lea     r12, WPP_3b2439340fb236e4397136d0fae00a22_Traceguids
0x1800101c6  mov     r14d, 100h
0x1800101cc  cmp     rcx, r15
0x1800101cf  jz      short loc_1800101EE
0x1800101d1  test    [rcx+1Ch], r14d
0x1800101d5  jz      short loc_1800101EE
0x1800101d7  cmp     byte ptr [rcx+19h], 5
0x1800101db  jb      short loc_1800101EE
0x1800101dd  mov     rcx, [rcx+10h]
0x1800101e1  mov     edx, 13h
0x1800101e6  mov     r8, r12
0x1800101e9  call    WPP_SF_
0x1800101ee  lea     rdx, [rdi+38h]; FaxHandle
0x1800101f2  xor     ecx, ecx; MachineName
0x1800101f4  call    cs:__imp_FaxConnectFaxServerW
0x1800101fa  test    eax, eax
0x1800101fc  jnz     short loc_180010237
0x1800101fe  call    cs:__imp_GetLastError
0x180010204  mov     ebx, eax
0x180010206  mov     rcx, cs:WPP_GLOBAL_Control
0x18001020d  cmp     rcx, r15
0x180010210  jz      loc_180010508
0x180010216  test    [rcx+1Ch], r14d
0x18001021a  jz      loc_180010508
0x180010220  cmp     byte ptr [rcx+19h], 2
0x180010224  jb      loc_180010508
0x18001022a  mov     edx, 14h
0x18001022f  mov     r9d, eax
0x180010232  jmp     loc_1800104FC
0x180010237  mov     rcx, [rdi+38h]
0x18001023b  xor     r8d, r8d
0x18001023e  lea     edx, [r8+20h]
0x180010242  call    cs:__imp_FaxAccessCheckEx2
0x180010248  test    eax, eax
0x18001024a  jnz     loc_1800102D5
0x180010250  call    cs:__imp_GetLastError
0x180010256  mov     ebx, eax
0x180010258  test    eax, eax
0x18001025a  jnz     short loc_180010298
0x18001025c  lea     ebx, [rax+5]
0x18001025f  mov     r9d, 1235h
0x180010265  mov     rdx, [rdi+8]
0x180010269  mov     r8d, 1230h
0x18001026f  mov     rcx, [rdi+10h]
0x180010273  mov     [rsp+68h+var_48], 10h
0x18001027b  call    FaxMsgBox
0x180010280  mov     rcx, rdi; this
0x180010283  call    ?CleanUp@CFaxConfigUI@@AEAAXXZ; CFaxConfigUI::CleanUp(void)
0x180010288  mov     eax, ebx
0x18001028a  add     rsp, 38h
0x18001028e  pop     r15
0x180010290  pop     r14
0x180010292  pop     r12
0x180010294  pop     rdi
0x180010295  pop     rsi
0x180010296  pop     rbx
0x180010297  retn
0x180010298  mov     rcx, cs:WPP_GLOBAL_Control
0x18001029f  cmp     rcx, r15
0x1800102a2  jz      loc_180010510
0x1800102a8  test    [rcx+1Ch], r14d
0x1800102ac  jz      loc_180010510
0x1800102b2  cmp     byte ptr [rcx+19h], 2
0x1800102b6  jb      loc_180010510
0x1800102bc  mov     edx, 15h
0x1800102c1  mov     rcx, [rcx+10h]
0x1800102c5  mov     r9d, eax
0x1800102c8  mov     r8, r12
0x1800102cb  call    WPP_SF_d
0x1800102d0  jmp     loc_180010510
0x1800102d5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800102dc  mov     ecx, 90h; unsigned __int64
0x1800102e1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800102e6  mov     rbx, rax
0x1800102e9  test    rax, rax
0x1800102ec  jz      short loc_180010333
0x1800102ee  mov     rdx, [rdi+10h]
0x1800102f2  mov     rcx, [rdi+8]
0x1800102f6  mov     [rax+10h], rdx
0x1800102fa  xor     edx, edx; Val
0x1800102fc  mov     [rax+8], rcx
0x180010300  lea     rcx, [rax+28h]; void *
0x180010304  mov     dword ptr [rax+18h], 122Ah
0x18001030b  mov     qword ptr [rax+20h], 0
0x180010313  lea     r8d, [rdx+60h]; Size
0x180010317  call    memset_0
0x18001031c  lea     rax, ??_7CPropertySheetUI@@6B@; const CPropertySheetUI::`vftable'
0x180010323  mov     qword ptr [rbx+88h], 0
0x18001032e  mov     [rbx], rax
0x180010331  jmp     short loc_180010335
0x180010333  xor     ebx, ebx
0x180010335  mov     [rdi+18h], rbx
0x180010339  test    rbx, rbx
0x18001033c  jnz     short loc_180010375
0x18001033e  mov     rcx, cs:WPP_GLOBAL_Control
0x180010345  cmp     rcx, r15
0x180010348  jz      short loc_180010365
0x18001034a  test    [rcx+1Ch], r14d
0x18001034e  jz      short loc_180010365
0x180010350  cmp     byte ptr [rcx+19h], 2
0x180010354  jb      short loc_180010365
0x180010356  mov     rcx, [rcx+10h]
0x18001035a  lea     edx, [rbx+16h]
0x18001035d  mov     r8, r12
0x180010360  call    WPP_SF_
0x180010365  mov     ebx, 8
0x18001036a  mov     r9d, 1237h
0x180010370  jmp     loc_180010265
0x180010375  mov     rcx, rdi; this
0x180010378  call    ?InitializePages@CFaxConfigUI@@AEAAKXZ; CFaxConfigUI::InitializePages(void)
0x18001037d  mov     ebx, eax
0x18001037f  test    eax, eax
0x180010381  jz      short loc_1800103B1
0x180010383  mov     rcx, cs:WPP_GLOBAL_Control
0x18001038a  cmp     rcx, r15
0x18001038d  jz      loc_180010510
0x180010393  test    [rcx+1Ch], r14d
0x180010397  jz      loc_180010510
0x18001039d  cmp     byte ptr [rcx+19h], 2
0x1800103a1  jb      loc_180010510
0x1800103a7  mov     edx, 17h
0x1800103ac  jmp     loc_1800102C1
0x1800103b1  mov     r8d, [rdi+30h]; unsigned int
0x1800103b5  mov     rdx, [rdi+20h]; struct CPage **
0x1800103b9  mov     rcx, [rdi+18h]; this
0x1800103bd  call    ?AddPages@CBaseUI@@MEAAKPEAPEAVCPage@@K@Z; CBaseUI::AddPages(CPage * *,ulong)
0x1800103c2  mov     ebx, eax
0x1800103c4  test    eax, eax
0x1800103c6  jz      short loc_1800103F6
0x1800103c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800103cf  cmp     rcx, r15
0x1800103d2  jz      loc_180010510
0x1800103d8  test    [rcx+1Ch], r14d
0x1800103dc  jz      loc_180010510
0x1800103e2  cmp     byte ptr [rcx+19h], 2
0x1800103e6  jb      loc_180010510
0x1800103ec  mov     edx, 18h
0x1800103f1  jmp     loc_1800102C1
0x1800103f6  mov     rax, [rdi+28h]
0x1800103fa  lea     rdx, [rsp+68h+Cookie]; struct _PSP **
0x1800103ff  mov     rcx, [rdi+18h]; this
0x180010403  mov     [rsp+68h+Cookie], rax
0x180010408  call    ?AddPagesByHandle@CBaseUI@@QEAAKPEAPEAU_PSP@@K@Z; CBaseUI::AddPagesByHandle(_PSP * *,ulong)
0x18001040d  mov     ebx, eax
0x18001040f  test    eax, eax
0x180010411  jz      short loc_180010441
0x180010413  mov     rcx, cs:WPP_GLOBAL_Control
0x18001041a  cmp     rcx, r15
0x18001041d  jz      loc_180010510
0x180010423  test    [rcx+1Ch], r14d
0x180010427  jz      loc_180010510
0x18001042d  cmp     byte ptr [rcx+19h], 2
0x180010431  jb      loc_180010510
0x180010437  mov     edx, 19h
0x18001043c  jmp     loc_1800102C1
0x180010441  mov     rax, [rdi+18h]
0x180010445  cmp     dword ptr [rax+88h], 0
0x18001044c  ja      short loc_18001045A
0x18001044e  mov     ebx, 57h ; 'W'
0x180010453  mov     esi, ebx
0x180010455  jmp     loc_1800104DC
0x18001045a  xor     esi, esi
0x18001045c  lea     rbx, [rax+28h]
0x180010460  mov     [rbx+30h], esi
0x180010463  mov     rax, cs:qword_18001E4F0
0x18001046a  mov     [rsp+68h+Cookie], rsi
0x18001046f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180010473  jnz     short loc_18001048F
0x180010475  lea     rdx, aPropertysheetw; "PropertySheetW"
0x18001047c  lea     rcx, qword_18001E4F0
0x180010483  call    _GetProcFromComCtl32
0x180010488  mov     rax, cs:qword_18001E4F0
0x18001048f  test    rax, rax
0x180010492  jz      short loc_1800104D2
0x180010494  lea     rdx, [rsp+68h+Cookie]; lpCookie
0x180010499  mov     [rsp+68h+Cookie], rsi
0x18001049e  xor     ecx, ecx; hActCtx
0x1800104a0  call    cs:__imp_ActivateActCtx
0x1800104a6  mov     rax, cs:qword_18001E4F0
0x1800104ad  mov     rcx, rbx
0x1800104b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104b5  mov     rdx, [rsp+68h+Cookie]; ulCookie
0x1800104ba  xor     ecx, ecx; dwFlags
0x1800104bc  mov     rbx, rax
0x1800104bf  call    cs:__imp_DeactivateActCtx
0x1800104c5  test    rbx, rbx
0x1800104c8  jns     short loc_1800104D2
0x1800104ca  call    cs:__imp_GetLastError
0x1800104d0  mov     esi, eax
0x1800104d2  mov     ebx, esi
0x1800104d4  test    esi, esi
0x1800104d6  jz      loc_180010280
0x1800104dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800104e3  cmp     rcx, r15
0x1800104e6  jz      short loc_180010510
0x1800104e8  test    [rcx+1Ch], r14d
0x1800104ec  jz      short loc_180010508
0x1800104ee  cmp     byte ptr [rcx+19h], 2
0x1800104f2  jb      short loc_180010508
0x1800104f4  mov     edx, 1Ah
0x1800104f9  mov     r9d, esi
0x1800104fc  mov     rcx, [rcx+10h]
0x180010500  mov     r8, r12
0x180010503  call    WPP_SF_d
0x180010508  test    ebx, ebx
0x18001050a  jz      loc_180010280
0x180010510  cmp     ebx, 5
0x180010513  jz      loc_18001025F
0x180010519  cmp     ebx, 8
0x18001051c  jz      loc_18001036A
0x180010522  mov     eax, 1236h
0x180010527  cmp     ebx, 7Ah ; 'z'
0x18001052a  lea     r9d, [rax-2]
0x18001052e  cmovnz  r9d, eax
0x180010532  jmp     loc_180010265
```
