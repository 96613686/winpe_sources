# WSTImportSecurityContext(_SecBuffer *,void *,unsigned __int64 *)

- ea: `0x180019200`
- end: `0x180019341`
- name: `?WSTImportSecurityContext@@YAJPEAU_SecBuffer@@PEAXPEA_K@Z`
- size: `321`
- prototype: `__int64 __fastcall(struct _SecBuffer *, void *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800196a0`

## callees

- `0x18000c5a4`
- `0x18000e7a4`
- `0x18000ebcc`
- `0x18000ffa4`
- `0x180018ea0`
- `0x180019200`
- `0x1800193d4`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall WSTImportSecurityContext(struct _SecBuffer *a1, void *a2, unsigned __int64 *a3)
{
  _DWORD *pvBuffer; // rsi
  int v6; // eax
  struct _NEGOEXTS_UMODE_CONTEXT *v7; // rdi
  int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  unsigned __int64 v11; // r9
  __int128 v13; // [rsp+20h] [rbp-28h] BYREF
  struct _NEGOEXTS_UMODE_CONTEXT *v14; // [rsp+50h] [rbp+8h] BYREF

  pvBuffer = a1->pvBuffer;
  v14 = 0;
  v13 = 0;
  v6 = WSTCreateUserModeContext(0, a1, &v14);
  v7 = v14;
  v8 = v6;
  if ( v6 >= 0 )
  {
    WSTDeleteUserModeContext((unsigned __int64)v14);
    LODWORD(v13) = pvBuffer[4];
    *((_QWORD *)&v13 + 1) = (char *)pvBuffer + (unsigned int)pvBuffer[3];
    v8 = (*(__int64 (__fastcall **)(__int128 *, void *, __int64))(*((_QWORD *)v7 + 6) + 104LL))(
           &v13,
           a2,
           (__int64)v7 + 32);
    if ( v8 >= 0 )
    {
      v8 = WSTInsertUserModeContext(v7);
      if ( v8 >= 0 )
      {
        v11 = *((_QWORD *)v7 + 4);
        *a3 = v11;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_8c1b4c250a203849e2737bc3a5ce992e_Traceguids, v11);
      }
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v10 = 16;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 15;
LABEL_5:
      WPP_SF_d(v9[2], v10, &WPP_8c1b4c250a203849e2737bc3a5ce992e_Traceguids, (unsigned int)v8);
    }
  }
  if ( v7 )
    WSTDereferenceUserModeContext(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180019200  mov     rax, rsp
0x180019203  mov     [rax+10h], rbx
0x180019207  mov     [rax+18h], rbp
0x18001920b  push    rsi
0x18001920c  push    rdi
0x18001920d  push    r14
0x18001920f  sub     rsp, 30h
0x180019213  mov     rsi, [rcx+8]
0x180019217  mov     rbp, rdx
0x18001921a  mov     rdx, rcx; struct _SecBuffer *
0x18001921d  mov     qword ptr [rax+8], 0
0x180019225  mov     r14, r8
0x180019228  xorps   xmm0, xmm0
0x18001922b  xor     ecx, ecx; unsigned __int64
0x18001922d  lea     r8, [rax+8]; struct _NEGOEXTS_UMODE_CONTEXT **
0x180019231  movups  xmmword ptr [rax-28h], xmm0
0x180019235  call    ?WSTCreateUserModeContext@@YAJ_KPEAU_SecBuffer@@PEAPEAU_NEGOEXTS_UMODE_CONTEXT@@@Z; WSTCreateUserModeContext(unsigned __int64,_SecBuffer *,_NEGOEXTS_UMODE_CONTEXT * *)
0x18001923a  mov     rdi, [rsp+48h+arg_0]
0x18001923f  mov     ebx, eax
0x180019241  test    eax, eax
0x180019243  jns     short loc_180019283
0x180019245  mov     rcx, cs:WPP_GLOBAL_Control
0x18001924c  lea     rax, WPP_GLOBAL_Control
0x180019253  cmp     rcx, rax
0x180019256  jz      loc_18001931F
0x18001925c  test    byte ptr [rcx+1Ch], 1
0x180019260  jz      loc_18001931F
0x180019266  mov     edx, 0Fh
0x18001926b  mov     rcx, [rcx+10h]
0x18001926f  lea     r8, WPP_8c1b4c250a203849e2737bc3a5ce992e_Traceguids
0x180019276  mov     r9d, ebx
0x180019279  call    WPP_SF_d
0x18001927e  jmp     loc_18001931F
0x180019283  mov     rcx, rdi; unsigned __int64
0x180019286  call    ?WSTDeleteUserModeContext@@YAJ_K@Z; WSTDeleteUserModeContext(unsigned __int64)
0x18001928b  mov     eax, [rsi+10h]
0x18001928e  lea     r8, [rdi+20h]
0x180019292  mov     [rsp+48h+var_28], eax
0x180019296  lea     rcx, [rsp+48h+var_28]
0x18001929b  mov     eax, [rsi+0Ch]
0x18001929e  mov     rdx, rbp
0x1800192a1  add     rax, rsi
0x1800192a4  mov     [rsp+48h+var_20], rax
0x1800192a9  mov     rax, [rdi+30h]
0x1800192ad  mov     rax, [rax+68h]
0x1800192b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800192b6  mov     ebx, eax
0x1800192b8  test    eax, eax
0x1800192ba  jns     short loc_1800192DC
0x1800192bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800192c3  lea     rax, WPP_GLOBAL_Control
0x1800192ca  cmp     rcx, rax
0x1800192cd  jz      short loc_18001931F
0x1800192cf  test    byte ptr [rcx+1Ch], 1
0x1800192d3  jz      short loc_18001931F
0x1800192d5  mov     edx, 10h
0x1800192da  jmp     short loc_18001926B
0x1800192dc  mov     rcx, rdi; struct _NEGOEXTS_UMODE_CONTEXT *
0x1800192df  call    ?WSTInsertUserModeContext@@YAJPEAU_NEGOEXTS_UMODE_CONTEXT@@@Z; WSTInsertUserModeContext(_NEGOEXTS_UMODE_CONTEXT *)
0x1800192e4  mov     ebx, eax
0x1800192e6  test    eax, eax
0x1800192e8  js      short loc_18001931F
0x1800192ea  mov     r9, [rdi+20h]
0x1800192ee  mov     [r14], r9
0x1800192f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800192f8  lea     rax, WPP_GLOBAL_Control
0x1800192ff  cmp     rcx, rax
0x180019302  jz      short loc_18001931F
0x180019304  test    byte ptr [rcx+1Ch], 2
0x180019308  jz      short loc_18001931F
0x18001930a  mov     rcx, [rcx+10h]
0x18001930e  lea     r8, WPP_8c1b4c250a203849e2737bc3a5ce992e_Traceguids
0x180019315  mov     edx, 11h
0x18001931a  call    WPP_SF_q
0x18001931f  test    rdi, rdi
0x180019322  jz      short loc_18001932C
0x180019324  mov     rcx, rdi; struct _NEGOEXTS_UMODE_CONTEXT *
0x180019327  call    ?WSTDereferenceUserModeContext@@YAXPEAU_NEGOEXTS_UMODE_CONTEXT@@@Z; WSTDereferenceUserModeContext(_NEGOEXTS_UMODE_CONTEXT *)
0x18001932c  mov     rbp, [rsp+48h+arg_10]
0x180019331  mov     eax, ebx
0x180019333  mov     rbx, [rsp+48h+arg_8]
0x180019338  add     rsp, 30h
0x18001933c  pop     r14
0x18001933e  pop     rdi
0x18001933f  pop     rsi
0x180019340  retn
```
