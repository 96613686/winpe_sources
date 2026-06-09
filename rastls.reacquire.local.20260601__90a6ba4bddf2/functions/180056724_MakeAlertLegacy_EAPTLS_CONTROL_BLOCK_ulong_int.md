# MakeAlertLegacy(_EAPTLS_CONTROL_BLOCK *,ulong,int)

- ea: `0x180056724`
- end: `0x180056974`
- name: `?MakeAlertLegacy@@YAXPEAU_EAPTLS_CONTROL_BLOCK@@KH@Z`
- size: `592`
- prototype: `void __fastcall(struct _EAPTLS_CONTROL_BLOCK *, unsigned int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800566ac`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180032f98`
- `0x180038270`
- `0x180056724`
- `0x18005dd00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056818`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056818`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800567f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800567f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800567c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800567c0`
- `SspiCli!ApplyControlToken` at `0x1800568ea`
- `SspiCli!ApplyControlToken` at `0x1800568ea`

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
            &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids,
            LastError);
        goto LABEL_24;
      }
      *((_DWORD *)a1 + 177) = 7;
    }
    *(_DWORD *)v8 = dword_1800AB85C;
    v8[2] = word_1800AB860;
    *(_BYTE *)(*((_QWORD *)a1 + 87) + 6LL) = a2;
    *((_DWORD *)a1 + 176) = 7;
    return;
  }
  if ( (*((_BYTE *)a1 + 4) & 0x40) != 0 )
  {
    if ( v6 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)v6 + 2), 261, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
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
      WPP_SF_d(*((_QWORD *)v12 + 2), v13, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, (unsigned int)v11);
    }
  }
LABEL_24:
  *((_QWORD *)a1 + 89) = 0;
  *((_DWORD *)a1 + 176) = 0;
}

```

## disassembly

```asm
0x180056724  mov     [rsp-18h+arg_10], rbx
0x180056729  mov     [rsp-18h+arg_18], rsi
0x18005672e  push    rbp
0x18005672f  push    rdi
0x180056730  push    r15
0x180056732  mov     rbp, rsp
0x180056735  sub     rsp, 70h
0x180056739  mov     rax, cs:__security_cookie
0x180056740  xor     rax, rsp
0x180056743  mov     [rbp+var_10], rax
0x180056747  xor     eax, eax
0x180056749  xorps   xmm0, xmm0
0x18005674c  mov     [rbp+var_20], rax
0x180056750  mov     edi, r8d
0x180056753  mov     [rbp+var_18], eax
0x180056756  mov     esi, edx
0x180056758  movups  xmmword ptr [rbp+pInput.ulVersion], xmm0
0x18005675c  mov     rbx, rcx
0x18005675f  mov     rcx, cs:WPP_GLOBAL_Control
0x180056766  lea     r15, WPP_GLOBAL_Control
0x18005676d  cmp     rcx, r15
0x180056770  jz      short loc_1800567A4
0x180056772  mov     rcx, [rcx+10h]
0x180056776  lea     rdx, aSchannel; " Schannel "
0x18005677d  test    r8d, r8d
0x180056780  lea     rax, aManual; " Manual "
0x180056787  mov     r9d, esi
0x18005678a  cmovz   rax, rdx
0x18005678e  mov     edx, 103h
0x180056793  mov     [rsp+70h+var_50], rax
0x180056798  call    WPP_SF_ds
0x18005679d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800567a4  test    edi, edi
0x1800567a6  jz      loc_180056880
0x1800567ac  mov     edi, 7
0x1800567b1  cmp     [rbx+2C4h], edi
0x1800567b7  jnb     short loc_1800567E2
0x1800567b9  mov     rcx, [rbx+2B8h]; hMem
0x1800567c0  call    cs:__imp_LocalFree
0x1800567c7  nop     dword ptr [rax+rax+00h]
0x1800567cc  mov     qword ptr [rbx+2B8h], 0
0x1800567d7  mov     qword ptr [rbx+2C0h], 0
0x1800567e2  mov     rcx, [rbx+2B8h]
0x1800567e9  test    rcx, rcx
0x1800567ec  jnz     short loc_180056857
0x1800567ee  mov     rdx, rdi; uBytes
0x1800567f1  mov     ecx, 40h ; '@'; uFlags
0x1800567f6  call    cs:__imp_LocalAlloc
0x1800567fd  nop     dword ptr [rax+rax+00h]
0x180056802  mov     [rbx+2B8h], rax
0x180056809  mov     rcx, rax
0x18005680c  test    rax, rax
0x18005680f  jnz     short loc_180056851
0x180056811  mov     [rbx+2C0h], rax
0x180056818  call    cs:__imp_GetLastError
0x18005681f  nop     dword ptr [rax+rax+00h]
0x180056824  mov     rcx, cs:WPP_GLOBAL_Control
0x18005682b  cmp     rcx, r15
0x18005682e  jz      loc_18005693D
0x180056834  mov     rcx, [rcx+10h]
0x180056838  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18005683f  mov     edx, 104h
0x180056844  mov     r9d, eax
0x180056847  call    WPP_SF_d
0x18005684c  jmp     loc_18005693D
0x180056851  mov     [rbx+2C4h], edi
0x180056857  mov     eax, cs:dword_1800AB85C
0x18005685d  mov     [rcx], eax
0x18005685f  movzx   eax, cs:word_1800AB860
0x180056866  mov     [rcx+4], ax
0x18005686a  mov     rax, [rbx+2B8h]
0x180056871  mov     [rax+6], sil
0x180056875  mov     [rbx+2C0h], edi
0x18005687b  jmp     loc_180056952
0x180056880  test    byte ptr [rbx+4], 40h
0x180056884  jz      short loc_1800568A9
0x180056886  cmp     rcx, r15
0x180056889  jz      loc_18005693D
0x18005688f  mov     rcx, [rcx+10h]
0x180056893  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18005689a  mov     edx, 105h
0x18005689f  call    WPP_SF_
0x1800568a4  jmp     loc_18005693D
0x1800568a9  mov     ecx, 2
0x1800568ae  mov     [rbp+var_18], esi
0x1800568b1  lea     rax, [rbp+var_20]
0x1800568b5  mov     dword ptr [rbp+var_20], ecx
0x1800568b8  mov     [rbp+var_28], rax
0x1800568bc  lea     rdx, [rbp+pInput]; pInput
0x1800568c0  lea     rax, [rbp+var_30]
0x1800568c4  mov     dword ptr [rbp+var_20+4], ecx
0x1800568c7  mov     [rbp+var_2C], ecx
0x1800568ca  lea     rcx, [rbx+288h]; phContext
0x1800568d1  mov     [rbp+pInput.pBuffers], rax
0x1800568d5  mov     [rbp+var_30], 0Ch
0x1800568dc  mov     [rbp+pInput.cBuffers], 1
0x1800568e3  mov     [rbp+pInput.ulVersion], 0
0x1800568ea  call    cs:__imp_ApplyControlToken
0x1800568f1  nop     dword ptr [rax+rax+00h]
0x1800568f6  test    eax, eax
0x1800568f8  jns     short loc_18005690D
0x1800568fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180056901  cmp     rcx, r15
0x180056904  jz      short loc_18005693D
0x180056906  mov     edx, 106h
0x18005690b  jmp     short loc_18005692A
0x18005690d  mov     rcx, rbx; struct _EAPTLS_CONTROL_BLOCK *
0x180056910  call    ?SecurityContextFunction@@YAJPEAU_EAPTLS_CONTROL_BLOCK@@@Z; SecurityContextFunction(_EAPTLS_CONTROL_BLOCK *)
0x180056915  test    eax, eax
0x180056917  jns     short loc_180056952
0x180056919  mov     rcx, cs:WPP_GLOBAL_Control
0x180056920  cmp     rcx, r15
0x180056923  jz      short loc_18005693D
0x180056925  mov     edx, 107h
0x18005692a  mov     rcx, [rcx+10h]
0x18005692e  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x180056935  mov     r9d, eax
0x180056938  call    WPP_SF_d
0x18005693d  mov     qword ptr [rbx+2C8h], 0
0x180056948  mov     dword ptr [rbx+2C0h], 0
0x180056952  mov     rcx, [rbp+var_10]
0x180056956  xor     rcx, rsp; StackCookie
0x180056959  call    __security_check_cookie
0x18005695e  lea     r11, [rsp+70h+var_s0]
0x180056963  mov     rbx, [r11+30h]
0x180056967  mov     rsi, [r11+38h]
0x18005696b  mov     rsp, r11
0x18005696e  pop     r15
0x180056970  pop     rdi
0x180056971  pop     rbp
0x180056972  retn
```
