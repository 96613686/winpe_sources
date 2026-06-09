# MakeAlertLegacy(_EAPTLS_CONTROL_BLOCK *,ulong,int)

- ea: `0x180053858`
- end: `0x180053a8f`
- name: `?MakeAlertLegacy@@YAXPEAU_EAPTLS_CONTROL_BLOCK@@KH@Z`
- size: `567`
- prototype: `void __fastcall(struct _EAPTLS_CONTROL_BLOCK *, int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800537e0`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x180030710`
- `0x180035680`
- `0x180053858`
- `0x18005a90c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053940`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053940`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180053924`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180053924`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800538f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800538f4`
- `SspiCli!ApplyControlToken` at `0x180053a0c`
- `SspiCli!ApplyControlToken` at `0x180053a0c`

## pseudocode

```c
void __fastcall MakeAlertLegacy(struct _EAPTLS_CONTROL_BLOCK *a1, int a2, int a3)
{
  struct _EAPTLS_CONTROL_BLOCK *v6; // rcx
  const char *v7; // rax
  _WORD *v8; // rcx
  _WORD *v9; // rax
  DWORD LastError; // eax
  SECURITY_STATUS v11; // eax
  struct _EAPTLS_CONTROL_BLOCK *v12; // rcx
  __int64 v13; // rdx
  struct _SecBufferDesc pInput; // [rsp+30h] [rbp-40h] BYREF
  _DWORD v15[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 *v16; // [rsp+48h] [rbp-28h]
  __int64 v17; // [rsp+50h] [rbp-20h] BYREF
  int v18; // [rsp+58h] [rbp-18h]

  v17 = 0;
  v18 = 0;
  pInput = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    v7 = " Manual ";
    if ( !a3 )
      v7 = " Schannel ";
    WPP_SF_ds(*((_QWORD *)WPP_GLOBAL_Control + 2), 259, a3, a2, (__int64)v7);
    v6 = WPP_GLOBAL_Control;
  }
  if ( a3 )
  {
    if ( *((_DWORD *)a1 + 177) < 7u )
    {
      LocalFree(*((HLOCAL *)a1 + 87));
      *((_QWORD *)a1 + 87) = 0;
      *((_QWORD *)a1 + 88) = 0;
    }
    v8 = (_WORD *)*((_QWORD *)a1 + 87);
    if ( !v8 )
    {
      v9 = LocalAlloc(0x40u, 7u);
      *((_QWORD *)a1 + 87) = v9;
      v8 = v9;
      if ( !v9 )
      {
        *((_QWORD *)a1 + 88) = 0;
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            260,
            &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
            LastError);
        goto LABEL_24;
      }
      *((_DWORD *)a1 + 177) = 7;
    }
    *(_DWORD *)v8 = dword_1800A575C;
    v8[2] = word_1800A5760;
    *(_BYTE *)(*((_QWORD *)a1 + 87) + 6LL) = a2;
    *((_DWORD *)a1 + 176) = 7;
    return;
  }
  if ( (*((_BYTE *)a1 + 4) & 0x40) != 0 )
  {
    if ( v6 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)v6 + 2), 261, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
    goto LABEL_24;
  }
  v18 = a2;
  v17 = 0x200000002LL;
  v16 = &v17;
  v15[1] = 2;
  pInput.pBuffers = (PSecBuffer)v15;
  v15[0] = 12;
  pInput.cBuffers = 1;
  pInput.ulVersion = 0;
  v11 = ApplyControlToken((PCtxtHandle)((char *)a1 + 648), &pInput);
  if ( v11 >= 0 )
  {
    v11 = SecurityContextFunction(a1);
    if ( v11 >= 0 )
      return;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v13 = 263;
      goto LABEL_23;
    }
  }
  else
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v13 = 262;
LABEL_23:
      WPP_SF_d(*((_QWORD *)v12 + 2), v13, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, (unsigned int)v11);
    }
  }
LABEL_24:
  *((_QWORD *)a1 + 89) = 0;
  *((_DWORD *)a1 + 176) = 0;
}

```

## disassembly

```asm
0x180053858  mov     [rsp-18h+arg_10], rbx
0x18005385d  mov     [rsp-18h+arg_18], rsi
0x180053862  push    rbp
0x180053863  push    rdi
0x180053864  push    r15
0x180053866  mov     rbp, rsp
0x180053869  sub     rsp, 70h
0x18005386d  mov     rax, cs:__security_cookie
0x180053874  xor     rax, rsp
0x180053877  mov     [rbp+var_10], rax
0x18005387b  xor     eax, eax
0x18005387d  xorps   xmm0, xmm0
0x180053880  mov     [rbp+var_20], rax
0x180053884  mov     edi, r8d
0x180053887  mov     [rbp+var_18], eax
0x18005388a  mov     esi, edx
0x18005388c  movups  xmmword ptr [rbp+pInput.ulVersion], xmm0
0x180053890  mov     rbx, rcx
0x180053893  mov     rcx, cs:WPP_GLOBAL_Control
0x18005389a  lea     r15, WPP_GLOBAL_Control
0x1800538a1  cmp     rcx, r15
0x1800538a4  jz      short loc_1800538D8
0x1800538a6  mov     rcx, [rcx+10h]
0x1800538aa  lea     rdx, aSchannel; " Schannel "
0x1800538b1  test    r8d, r8d
0x1800538b4  lea     rax, aManual; " Manual "
0x1800538bb  mov     r9d, esi
0x1800538be  cmovz   rax, rdx
0x1800538c2  mov     edx, 103h
0x1800538c7  mov     [rsp+70h+var_50], rax
0x1800538cc  call    WPP_SF_ds
0x1800538d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800538d8  test    edi, edi
0x1800538da  jz      loc_1800539A2
0x1800538e0  mov     edi, 7
0x1800538e5  cmp     [rbx+2C4h], edi
0x1800538eb  jnb     short loc_180053910
0x1800538ed  mov     rcx, [rbx+2B8h]; hMem
0x1800538f4  call    cs:__imp_LocalFree
0x1800538fa  mov     qword ptr [rbx+2B8h], 0
0x180053905  mov     qword ptr [rbx+2C0h], 0
0x180053910  mov     rcx, [rbx+2B8h]
0x180053917  test    rcx, rcx
0x18005391a  jnz     short loc_180053979
0x18005391c  mov     rdx, rdi; uBytes
0x18005391f  mov     ecx, 40h ; '@'; uFlags
0x180053924  call    cs:__imp_LocalAlloc
0x18005392a  mov     [rbx+2B8h], rax
0x180053931  mov     rcx, rax
0x180053934  test    rax, rax
0x180053937  jnz     short loc_180053973
0x180053939  mov     [rbx+2C0h], rax
0x180053940  call    cs:__imp_GetLastError
0x180053946  mov     rcx, cs:WPP_GLOBAL_Control
0x18005394d  cmp     rcx, r15
0x180053950  jz      loc_180053A59
0x180053956  mov     rcx, [rcx+10h]
0x18005395a  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x180053961  mov     edx, 104h
0x180053966  mov     r9d, eax
0x180053969  call    WPP_SF_d
0x18005396e  jmp     loc_180053A59
0x180053973  mov     [rbx+2C4h], edi
0x180053979  mov     eax, cs:dword_1800A575C
0x18005397f  mov     [rcx], eax
0x180053981  movzx   eax, cs:word_1800A5760
0x180053988  mov     [rcx+4], ax
0x18005398c  mov     rax, [rbx+2B8h]
0x180053993  mov     [rax+6], sil
0x180053997  mov     [rbx+2C0h], edi
0x18005399d  jmp     loc_180053A6E
0x1800539a2  test    byte ptr [rbx+4], 40h
0x1800539a6  jz      short loc_1800539CB
0x1800539a8  cmp     rcx, r15
0x1800539ab  jz      loc_180053A59
0x1800539b1  mov     rcx, [rcx+10h]
0x1800539b5  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x1800539bc  mov     edx, 105h
0x1800539c1  call    WPP_SF_
0x1800539c6  jmp     loc_180053A59
0x1800539cb  mov     ecx, 2
0x1800539d0  mov     [rbp+var_18], esi
0x1800539d3  lea     rax, [rbp+var_20]
0x1800539d7  mov     dword ptr [rbp+var_20], ecx
0x1800539da  mov     [rbp+var_28], rax
0x1800539de  lea     rdx, [rbp+pInput]; pInput
0x1800539e2  lea     rax, [rbp+var_30]
0x1800539e6  mov     dword ptr [rbp+var_20+4], ecx
0x1800539e9  mov     [rbp+var_2C], ecx
0x1800539ec  lea     rcx, [rbx+288h]; phContext
0x1800539f3  mov     [rbp+pInput.pBuffers], rax
0x1800539f7  mov     [rbp+var_30], 0Ch
0x1800539fe  mov     [rbp+pInput.cBuffers], 1
0x180053a05  mov     [rbp+pInput.ulVersion], 0
0x180053a0c  call    cs:__imp_ApplyControlToken
0x180053a12  test    eax, eax
0x180053a14  jns     short loc_180053A29
0x180053a16  mov     rcx, cs:WPP_GLOBAL_Control
0x180053a1d  cmp     rcx, r15
0x180053a20  jz      short loc_180053A59
0x180053a22  mov     edx, 106h
0x180053a27  jmp     short loc_180053A46
0x180053a29  mov     rcx, rbx; struct _EAPTLS_CONTROL_BLOCK *
0x180053a2c  call    ?SecurityContextFunction@@YAJPEAU_EAPTLS_CONTROL_BLOCK@@@Z; SecurityContextFunction(_EAPTLS_CONTROL_BLOCK *)
0x180053a31  test    eax, eax
0x180053a33  jns     short loc_180053A6E
0x180053a35  mov     rcx, cs:WPP_GLOBAL_Control
0x180053a3c  cmp     rcx, r15
0x180053a3f  jz      short loc_180053A59
0x180053a41  mov     edx, 107h
0x180053a46  mov     rcx, [rcx+10h]
0x180053a4a  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x180053a51  mov     r9d, eax
0x180053a54  call    WPP_SF_d
0x180053a59  mov     qword ptr [rbx+2C8h], 0
0x180053a64  mov     dword ptr [rbx+2C0h], 0
0x180053a6e  mov     rcx, [rbp+var_10]
0x180053a72  xor     rcx, rsp; StackCookie
0x180053a75  call    __security_check_cookie
0x180053a7a  lea     r11, [rsp+70h+var_s0]
0x180053a7f  mov     rbx, [r11+30h]
0x180053a83  mov     rsi, [r11+38h]
0x180053a87  mov     rsp, r11
0x180053a8a  pop     r15
0x180053a8c  pop     rdi
0x180053a8d  pop     rbp
0x180053a8e  retn
```
