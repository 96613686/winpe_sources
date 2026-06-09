# LanConnection::GetPropertiesEx(tagNETCON_PROPERTIES_EX * *)

- ea: `0x180025020`
- end: `0x180025288`
- name: `?GetPropertiesEx@LanConnection@@UEAAJPEAPEAUtagNETCON_PROPERTIES_EX@@@Z`
- size: `616`
- prototype: `__int64 __fastcall(LanConnection *__hidden this, struct tagNETCON_PROPERTIES_EX **)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001710`
- `0x180002320`
- `0x18000538c`
- `0x180025020`
- `0x180025734`
- `0x18002ff54`
- `0x180030714`
- `0x180031b1c`
- `0x180031d0c`
- `0x180031d44`
- `0x180032110`
- `0x180036010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180025167`
- `ADVAPI32!RegCloseKey` at `0x180025167`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002507f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002507f`

## pseudocode

```c
__int64 __fastcall LanConnection::GetPropertiesEx(LanConnection *this, struct tagNETCON_PROPERTIES_EX **a2)
{
  LanConnection *v2; // r14
  int PseudoMediaTypes; // edi
  char *v6; // rax
  char *v7; // rsi
  struct IPersistNetConnection *v8; // r8
  CIntelliName *v9; // rcx
  __int64 v10; // rdx
  int v11; // edi
  unsigned int v12; // ebx
  int v13; // r15d
  int v14; // eax
  int v15; // eax
  int v16; // ecx
  unsigned int v18; // [rsp+30h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-18h] BYREF
  struct tagNETCON_PROPERTIES *pv; // [rsp+40h] [rbp-10h] BYREF

  v2 = (LanConnection *)((char *)this - 24);
  *a2 = 0;
  if ( *((_DWORD *)this + 18) )
  {
    pv = 0;
    v6 = (char *)CoTaskMemAlloc(0x68u);
    v7 = v6;
    if ( !v6 )
    {
      PseudoMediaTypes = -2147024882;
      goto LABEL_38;
    }
    memset_0(v6, 0, 0x68u);
    PseudoMediaTypes = (*(__int64 (__fastcall **)(LanConnection *, struct tagNETCON_PROPERTIES **))(*(_QWORD *)v2 + 56LL))(
                         v2,
                         &pv);
    if ( PseudoMediaTypes < 0 )
      goto LABEL_36;
    if ( v2 )
      v8 = (LanConnection *)((char *)this - 16);
    else
      v8 = 0;
    PseudoMediaTypes = HrBuildPropertiesExFromProperties(pv, (struct tagNETCON_PROPERTIES_EX *)v7, v8);
    if ( PseudoMediaTypes < 0 )
    {
LABEL_35:
      FreeNetconProperties(pv);
      if ( PseudoMediaTypes >= 0 )
        return (unsigned int)PseudoMediaTypes;
LABEL_36:
      *a2 = 0;
      HrFreeNetConProperties2((struct tagNETCON_PROPERTIES_EX *)v7);
      goto LABEL_38;
    }
    if ( *((_DWORD *)v7 + 11) != 3 )
    {
      *((_DWORD *)v7 + 12) = 0;
      goto LABEL_34;
    }
    LODWORD(hKey) = 0;
    v18 = 0;
    PseudoMediaTypes = CIntelliName::HrGetPseudoMediaTypes(
                         v9,
                         (const struct _GUID *)(v7 + 4),
                         (enum tagNETCON_MEDIATYPE *)&hKey,
                         (enum tagNETCON_SUBMEDIATYPE *)&v18);
    if ( PseudoMediaTypes >= 0 )
    {
      v12 = v18;
LABEL_22:
      v13 = 0;
      v14 = LanConnection::HrEnsureHNetPropertiesCached(v2);
      if ( v14 )
      {
        if ( v14 < 0 )
          goto LABEL_27;
      }
      else
      {
        v13 = *(unsigned __int8 *)(*((_QWORD *)v2 + 21) + 11LL);
      }
      if ( v13 == 1 )
        v12 = 10;
LABEL_27:
      v15 = LanConnection::HrEnsureHNetPropertiesCached(v2);
      if ( v15 )
      {
        v16 = 0;
        if ( v15 < 0 )
        {
LABEL_32:
          *((_DWORD *)v7 + 12) = v12;
LABEL_34:
          *a2 = (struct tagNETCON_PROPERTIES_EX *)v7;
          goto LABEL_35;
        }
      }
      else
      {
        v16 = *(unsigned __int8 *)(*((_QWORD *)v2 + 21) + 10LL);
      }
      if ( v16 == 1 )
        v12 = 11;
      goto LABEL_32;
    }
    hKey = 0;
    v11 = HrOpenConnectionKey(v7 + 4, v10, 131097, 0);
    if ( v11 < 0 )
    {
      v12 = v18;
    }
    else
    {
      v18 = 0;
      v12 = 1;
      v11 = HrRegQueryDword(hKey, L"MediaSubType", &v18);
      if ( v11 >= 0 )
        v12 = v18;
      RegCloseKey(hKey);
      if ( v11 >= 0 )
        goto LABEL_20;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        &WPP_c391b5a9ef0e35e0488fc434df876d07_Traceguids,
        (unsigned int)v11);
LABEL_20:
    PseudoMediaTypes = 0;
    goto LABEL_22;
  }
  PseudoMediaTypes = -2147418113;
LABEL_38:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      38,
      &WPP_c391b5a9ef0e35e0488fc434df876d07_Traceguids,
      (unsigned int)PseudoMediaTypes);
  return (unsigned int)PseudoMediaTypes;
}

```

## disassembly

```asm
0x180025020  mov     [rsp-28h+arg_10], rbx
0x180025025  mov     [rsp-28h+arg_18], rsi
0x18002502a  push    rbp
0x18002502b  push    rdi
0x18002502c  push    r12
0x18002502e  push    r14
0x180025030  push    r15
0x180025032  mov     rbp, rsp
0x180025035  sub     rsp, 50h
0x180025039  mov     rax, cs:__security_cookie
0x180025040  xor     rax, rsp
0x180025043  mov     [rbp+var_8], rax
0x180025047  lea     r14, [rcx-18h]
0x18002504b  mov     qword ptr [rdx], 0
0x180025052  cmp     dword ptr [r14+60h], 0
0x180025057  lea     r15, WPP_GLOBAL_Control
0x18002505e  mov     r12, rdx
0x180025061  mov     rbx, rcx
0x180025064  jnz     short loc_180025070
0x180025066  mov     edi, 8000FFFFh
0x18002506b  jmp     loc_180025237
0x180025070  mov     edi, 68h ; 'h'
0x180025075  mov     [rbp+pv], 0
0x18002507d  mov     ecx, edi; cb
0x18002507f  call    cs:__imp_CoTaskMemAlloc
0x180025085  mov     rsi, rax
0x180025088  test    rax, rax
0x18002508b  jz      loc_180025232
0x180025091  mov     r8d, edi; Size
0x180025094  xor     edx, edx; Val
0x180025096  mov     rcx, rax; void *
0x180025099  call    memset_0
0x18002509e  mov     rax, [r14]
0x1800250a1  lea     rdx, [rbp+pv]
0x1800250a5  mov     rcx, r14
0x1800250a8  mov     rax, [rax+38h]
0x1800250ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800250b1  mov     edi, eax
0x1800250b3  test    eax, eax
0x1800250b5  js      loc_180025220
0x1800250bb  test    r14, r14
0x1800250be  jz      short loc_1800250C6
0x1800250c0  lea     r8, [rbx-10h]
0x1800250c4  jmp     short loc_1800250C9
0x1800250c6  xor     r8d, r8d; struct IPersistNetConnection *
0x1800250c9  mov     rcx, [rbp+pv]; struct tagNETCON_PROPERTIES *
0x1800250cd  mov     rdx, rsi; struct tagNETCON_PROPERTIES_EX *
0x1800250d0  call    ?HrBuildPropertiesExFromProperties@@YAJPEAUtagNETCON_PROPERTIES@@PEAUtagNETCON_PROPERTIES_EX@@PEAUIPersistNetConnection@@@Z; HrBuildPropertiesExFromProperties(tagNETCON_PROPERTIES *,tagNETCON_PROPERTIES_EX *,IPersistNetConnection *)
0x1800250d5  mov     edi, eax
0x1800250d7  test    eax, eax
0x1800250d9  js      loc_180025213
0x1800250df  cmp     dword ptr [rsi+2Ch], 3
0x1800250e3  jnz     loc_180025208
0x1800250e9  lea     r9, [rbp+var_20]; enum tagNETCON_SUBMEDIATYPE *
0x1800250ed  mov     dword ptr [rbp+hKey], 0
0x1800250f4  lea     r8, [rbp+hKey]; enum tagNETCON_MEDIATYPE *
0x1800250f8  mov     [rbp+var_20], 0
0x1800250ff  lea     rdx, [rsi+4]; struct _GUID *
0x180025103  call    ?HrGetPseudoMediaTypes@CIntelliName@@QEBAJAEBU_GUID@@PEAW4tagNETCON_MEDIATYPE@@PEAW4tagNETCON_SUBMEDIATYPE@@@Z; CIntelliName::HrGetPseudoMediaTypes(_GUID const &,tagNETCON_MEDIATYPE *,tagNETCON_SUBMEDIATYPE *)
0x180025108  mov     edi, eax
0x18002510a  test    eax, eax
0x18002510c  jns     loc_1800251A4
0x180025112  lea     rax, [rbp+hKey]
0x180025116  mov     [rbp+hKey], 0
0x18002511e  xor     r9d, r9d
0x180025121  mov     [rsp+50h+var_28], rax
0x180025126  mov     r8d, 20019h
0x18002512c  lea     rcx, [rsi+4]
0x180025130  call    ?HrOpenConnectionKey@@YAJPEBU_GUID@@PEBGKW4OCC_FLAGS@@1PEAPEAUHKEY__@@@Z; HrOpenConnectionKey(_GUID const *,ushort const *,ulong,OCC_FLAGS,ushort const *,HKEY__ * *)
0x180025135  mov     edi, eax
0x180025137  test    eax, eax
0x180025139  js      short loc_180025173
0x18002513b  mov     rcx, [rbp+hKey]; HKEY
0x18002513f  lea     r8, [rbp+var_20]; unsigned int *
0x180025143  lea     rdx, ?c_szRegValueMediaSubType@@3QBGB; "MediaSubType"
0x18002514a  mov     [rbp+var_20], 0
0x180025151  call    ?HrRegQueryDword@@YAJPEAUHKEY__@@PEBGPEAK@Z; HrRegQueryDword(HKEY__ *,ushort const *,ulong *)
0x180025156  mov     rcx, [rbp+hKey]; hKey
0x18002515a  test    eax, eax
0x18002515c  mov     ebx, 1
0x180025161  mov     edi, eax
0x180025163  cmovns  ebx, [rbp+var_20]
0x180025167  call    cs:__imp_RegCloseKey
0x18002516d  test    edi, edi
0x18002516f  jns     short loc_1800251A0
0x180025171  jmp     short loc_180025176
0x180025173  mov     ebx, [rbp+var_20]
0x180025176  mov     rcx, cs:WPP_GLOBAL_Control
0x18002517d  cmp     rcx, r15
0x180025180  jz      short loc_1800251A0
0x180025182  test    byte ptr [rcx+1Ch], 1
0x180025186  jz      short loc_1800251A0
0x180025188  mov     rcx, [rcx+10h]
0x18002518c  lea     r8, WPP_c391b5a9ef0e35e0488fc434df876d07_Traceguids
0x180025193  mov     edx, 25h ; '%'
0x180025198  mov     r9d, edi
0x18002519b  call    WPP_SF_d
0x1800251a0  xor     edi, edi
0x1800251a2  jmp     short loc_1800251A7
0x1800251a4  mov     ebx, [rbp+var_20]
0x1800251a7  mov     rcx, r14; this
0x1800251aa  xor     r15d, r15d
0x1800251ad  call    ?HrEnsureHNetPropertiesCached@LanConnection@@AEAAJXZ; LanConnection::HrEnsureHNetPropertiesCached(void)
0x1800251b2  test    eax, eax
0x1800251b4  jnz     short loc_1800251C4
0x1800251b6  mov     rax, [r14+0A8h]
0x1800251bd  movzx   r15d, byte ptr [rax+0Bh]
0x1800251c2  jmp     short loc_1800251C6
0x1800251c4  js      short loc_1800251D2
0x1800251c6  cmp     r15d, 1
0x1800251ca  mov     eax, 0Ah
0x1800251cf  cmovz   ebx, eax
0x1800251d2  mov     rcx, r14; this
0x1800251d5  call    ?HrEnsureHNetPropertiesCached@LanConnection@@AEAAJXZ; LanConnection::HrEnsureHNetPropertiesCached(void)
0x1800251da  test    eax, eax
0x1800251dc  jnz     short loc_1800251EB
0x1800251de  mov     rax, [r14+0A8h]
0x1800251e5  movzx   ecx, byte ptr [rax+0Ah]
0x1800251e9  jmp     short loc_1800251F1
0x1800251eb  xor     ecx, ecx
0x1800251ed  test    eax, eax
0x1800251ef  js      short loc_1800251FC
0x1800251f1  cmp     ecx, 1
0x1800251f4  mov     eax, 0Bh
0x1800251f9  cmovz   ebx, eax
0x1800251fc  mov     [rsi+30h], ebx
0x1800251ff  lea     r15, WPP_GLOBAL_Control
0x180025206  jmp     short loc_18002520F
0x180025208  mov     dword ptr [rsi+30h], 0
0x18002520f  mov     [r12], rsi
0x180025213  mov     rcx, [rbp+pv]; pv
0x180025217  call    ?FreeNetconProperties@@YAXPEAUtagNETCON_PROPERTIES@@@Z; FreeNetconProperties(tagNETCON_PROPERTIES *)
0x18002521c  test    edi, edi
0x18002521e  jns     short loc_180025261
0x180025220  mov     rcx, rsi; pv
0x180025223  mov     qword ptr [r12], 0
0x18002522b  call    ?HrFreeNetConProperties2@@YAJPEAUtagNETCON_PROPERTIES_EX@@@Z; HrFreeNetConProperties2(tagNETCON_PROPERTIES_EX *)
0x180025230  jmp     short loc_180025237
0x180025232  mov     edi, 8007000Eh
0x180025237  mov     rcx, cs:WPP_GLOBAL_Control
0x18002523e  cmp     rcx, r15
0x180025241  jz      short loc_180025261
0x180025243  test    byte ptr [rcx+1Ch], 1
0x180025247  jz      short loc_180025261
0x180025249  mov     rcx, [rcx+10h]
0x18002524d  lea     r8, WPP_c391b5a9ef0e35e0488fc434df876d07_Traceguids
0x180025254  mov     edx, 26h ; '&'
0x180025259  mov     r9d, edi
0x18002525c  call    WPP_SF_d
0x180025261  mov     eax, edi
0x180025263  mov     rcx, [rbp+var_8]
0x180025267  xor     rcx, rsp; StackCookie
0x18002526a  call    __security_check_cookie
0x18002526f  lea     r11, [rsp+50h+var_s0]
0x180025274  mov     rbx, [r11+40h]
0x180025278  mov     rsi, [r11+48h]
0x18002527c  mov     rsp, r11
0x18002527f  pop     r15
0x180025281  pop     r14
0x180025283  pop     r12
0x180025285  pop     rdi
0x180025286  pop     rbp
0x180025287  retn
```
