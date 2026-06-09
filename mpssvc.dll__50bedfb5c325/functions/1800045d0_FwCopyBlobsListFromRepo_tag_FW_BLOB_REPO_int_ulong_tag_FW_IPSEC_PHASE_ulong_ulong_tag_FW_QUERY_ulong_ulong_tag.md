# FwCopyBlobsListFromRepo(_tag_FW_BLOB_REPO *,int,ulong,_tag_FW_IPSEC_PHASE,ulong,ulong,_tag_FW_QUERY *,ulong,ulong *,_tag_FW_BLOB_RULE * *,int)

- ea: `0x1800045d0`
- end: `0x180004a12`
- name: `?FwCopyBlobsListFromRepo@@YAJPEAU_tag_FW_BLOB_REPO@@HKW4_tag_FW_IPSEC_PHASE@@KKPEAU_tag_FW_QUERY@@KPEAKPEAPEAU_tag_FW_BLOB_RULE@@H@Z`
- size: `1090`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003be0`
- `0x180003da4`

## callees

- `0x1800045d0`
- `0x180004a18`
- `0x18000a710`
- `0x18006a710`
- `0x1800729c0`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800048ab`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800048ab`
- `fwbase!FwMetaDataCopy` at `0x180004835`
- `fwbase!FwMetaDataCopy` at `0x180004835`
- `FWPolicyIOMgr!FwCopyRule` at `0x180004791`
- `FWPolicyIOMgr!FwCopyRule` at `0x180004791`
- `FWPolicyIOMgr!FwCopyMMRule` at `0x18000497d`
- `FWPolicyIOMgr!FwCopyMMRule` at `0x18000497d`
- `FWPolicyIOMgr!FwCopyCryptoSet` at `0x1800049b2`
- `FWPolicyIOMgr!FwCopyCryptoSet` at `0x1800049b2`
- `FWPolicyIOMgr!FwPolioCopyAuthSet` at `0x180004997`
- `FWPolicyIOMgr!FwPolioCopyAuthSet` at `0x180004997`
- `FWPolicyIOMgr!FwCopyCSRule` at `0x180004962`
- `FWPolicyIOMgr!FwCopyCSRule` at `0x180004962`

## string_xrefs

- `0x180004942`: `mpssvc.dll`
- `0x1800049f1`: `mpssvc.dll`

## pseudocode

```c
__int64 __fastcall FwCopyBlobsListFromRepo(
        _QWORD *a1,
        unsigned int a2,
        unsigned int a3,
        int a4,
        int a5,
        int a6,
        __int64 a7,
        char a8,
        _DWORD *a9,
        _QWORD *a10,
        int a11)
{
  int v11; // ebp
  unsigned int v12; // edi
  __int64 v13; // rsi
  _QWORD *v14; // rbx
  unsigned int v15; // r8d
  unsigned int v16; // r14d
  _QWORD *v17; // r13
  __int64 v18; // rax
  __int64 v19; // rax
  char v20; // r15
  __int16 *v21; // rdx
  __int64 v22; // rbp
  unsigned int v23; // r15d
  __int64 v24; // rdi
  __int64 j; // rbx
  __int64 v26; // rbx
  __int64 v27; // rcx
  __int64 result; // rax
  __int64 v29; // rbx
  LPCWSTR *v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rdx
  unsigned int v33; // [rsp+20h] [rbp-98h]
  int v34; // [rsp+24h] [rbp-94h]
  int v36; // [rsp+2Ch] [rbp-8Ch]
  __int64 i; // [rsp+38h] [rbp-80h]
  _QWORD *v40; // [rsp+58h] [rbp-60h] BYREF

  v11 = 0;
  v12 = a2;
  v13 = a3;
  v14 = a1;
  v15 = 0;
  v36 = v13;
  v33 = 0;
  v40 = 0;
  v34 = 0;
  if ( !a2 )
  {
    if ( !(_DWORD)v13 )
    {
      v16 = 4;
      goto LABEL_4;
    }
    if ( (_DWORD)v13 == 1 )
    {
      v16 = 5;
      goto LABEL_4;
    }
LABEL_54:
    MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", (unsigned int)v13, a2);
    v15 = 0;
    goto LABEL_3;
  }
  if ( (_DWORD)v13 )
  {
    if ( (_DWORD)v13 == 1 )
    {
      v16 = 1;
      goto LABEL_4;
    }
    if ( (_DWORD)v13 == 2 )
    {
      v16 = 2;
      goto LABEL_4;
    }
    goto LABEL_54;
  }
LABEL_3:
  v16 = 0;
LABEL_4:
  v17 = (_QWORD *)*v14;
  v18 = 0;
  if ( !v12 )
    v18 = 3;
  v19 = 48 * (v13 + v18);
  for ( i = v19; ; v19 = i )
  {
    v20 = a8;
    v21 = &_ImageBase;
    if ( v17 == v14 )
    {
      *a9 += v11;
      return v15;
    }
    if ( a7 )
    {
      v22 = *(v17 - 2);
      v23 = 0;
LABEL_10:
      if ( v23 >= *(_DWORD *)(a7 + 4) )
      {
        v12 = a2;
LABEL_17:
        v15 = v33;
        goto LABEL_18;
      }
      v24 = *(_QWORD *)(a7 + 8) + 16LL * v23;
      for ( j = 0; (unsigned int)j < *(_DWORD *)v24; j = (unsigned int)(j + 1) )
      {
        if ( !(unsigned int)FwQueryConditionMatchObject(*(_QWORD *)(v24 + 8) + 24 * j, v22, v16, v17 + 3) )
        {
          ++v23;
          goto LABEL_10;
        }
      }
      v12 = a2;
      LODWORD(v13) = v36;
      v11 = v34;
      v20 = a8;
      v26 = i;
    }
    else
    {
      if ( (a5
          & *(_DWORD *)(*(enum _tag_FW_RULE_STATUS *(__fastcall **)(void *))((char *)&off_18012A728 + v19))((void *)*(v17 - 2))) == 0 )
        goto LABEL_17;
      v26 = i;
      if ( (a6 & *(*(unsigned int *(__fastcall **)(void *))((char *)&off_18012A730 + i))((void *)*(v17 - 2))) == 0 )
        goto LABEL_17;
    }
    if ( !v12 )
    {
      if ( a11 )
        goto LABEL_25;
      v30 = (LPCWSTR *)(*(__int64 (__fastcall **)(_QWORD, __int16 *))((char *)off_18012A738 + v26))(*(v17 - 2), v21);
      if ( !lstrcmpiW((LPCWSTR)(&wszDefaultSetGuids)[3 * (unsigned int)v13 + a4], *v30) )
        goto LABEL_17;
    }
    if ( v12 == 1 && (v20 & 0x20) != 0 && !v17[3] )
      goto LABEL_17;
LABEL_25:
    v27 = *(v17 - 2);
    if ( v12 == 1 )
    {
      if ( (_DWORD)v13 )
      {
        if ( (_DWORD)v13 == 1 )
        {
          LODWORD(result) = FwCopyCSRule(v27, &v40);
        }
        else
        {
          if ( (_DWORD)v13 != 2 )
            goto LABEL_66;
          LODWORD(result) = FwCopyMMRule(v27, &v40);
        }
      }
      else
      {
        LODWORD(result) = FwCopyRule(v27, &v40);
      }
    }
    else if ( (_DWORD)v13 )
    {
      if ( (_DWORD)v13 != 1 )
      {
LABEL_66:
        MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", (unsigned int)v13, v12);
        v15 = -2147024809;
        v33 = -2147024809;
        LODWORD(result) = -2147024809;
LABEL_42:
        v31 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v32 = 146;
          goto LABEL_45;
        }
        return v15;
      }
      LODWORD(result) = FwCopyCryptoSet(v27, &v40);
    }
    else
    {
      LODWORD(result) = FwPolioCopyAuthSet(v27, &v40);
    }
    v33 = result;
    v15 = result;
    if ( (int)result < 0 )
      goto LABEL_42;
    if ( !v12 || (v20 & 0x40) == 0 )
      goto LABEL_31;
    v29 = 11LL * v16;
    result = FwMetaDataCopy(v17 + 3, (char *)v40 + HIDWORD(g_FwObjectHandler[v29 + 5]), (unsigned int)result);
    v33 = result;
    v15 = result;
    if ( (int)result < 0 )
      break;
    *(_DWORD *)((char *)v40 + LODWORD(g_FwObjectHandler[v29 + 6])) |= 1u;
LABEL_31:
    v34 = v11 + 1;
    *v40 = *a10;
    *a10 = v40;
    v40 = 0;
LABEL_18:
    v17 = (_QWORD *)*v17;
    v14 = a1;
    LODWORD(v13) = v36;
    v11 = v34;
  }
  v31 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v32 = 147;
LABEL_45:
    WPP_SF_d(*(_QWORD *)(v31 + 16), v32, WPP_3d9dabe50e6b3e70315acf6b635a3004_Traceguids, (unsigned int)result);
    return v33;
  }
  return result;
}

```

## disassembly

```asm
0x1800045d0  push    rbx
0x1800045d2  push    rbp
0x1800045d3  push    rsi
0x1800045d4  push    rdi
0x1800045d5  push    r12
0x1800045d7  push    r13
0x1800045d9  push    r14
0x1800045db  push    r15
0x1800045dd  sub     rsp, 78h
0x1800045e1  mov     rax, cs:__security_cookie
0x1800045e8  xor     rax, rsp
0x1800045eb  mov     [rsp+0B8h+var_58], rax
0x1800045f0  mov     rax, [rsp+0B8h+arg_40]
0x1800045f8  xor     ebp, ebp
0x1800045fa  mov     r12, [rsp+0B8h+arg_30]
0x180004602  mov     edi, edx
0x180004604  mov     esi, r8d
0x180004607  mov     rbx, rcx
0x18000460a  xor     r8d, r8d
0x18000460d  mov     [rsp+0B8h+var_68], rax
0x180004612  mov     rax, [rsp+0B8h+arg_48]
0x18000461a  mov     [rsp+0B8h+var_78], rax
0x18000461f  mov     [rsp+0B8h+var_88], r9d
0x180004624  mov     [rsp+0B8h+var_8C], esi
0x180004628  mov     [rsp+0B8h+var_90], edx
0x18000462c  mov     [rsp+0B8h+var_70], rcx
0x180004631  mov     [rsp+0B8h+var_98], r8d
0x180004636  mov     [rsp+0B8h+var_60], r8
0x18000463b  mov     [rsp+0B8h+var_94], ebp
0x18000463f  test    edx, edx
0x180004641  jz      loc_180004920
0x180004647  test    esi, esi
0x180004649  jnz     loc_180004906
0x18000464f  xor     r14d, r14d
0x180004652  mov     r13, [rbx]
0x180004655  xor     eax, eax
0x180004657  test    edi, edi
0x180004659  mov     edx, 3
0x18000465e  cmovz   eax, edx
0x180004661  add     rax, rsi
0x180004664  lea     rax, [rax+rax*2]
0x180004668  shl     rax, 4
0x18000466c  mov     [rsp+0B8h+var_80], rax
0x180004671  mov     r15d, dword ptr [rsp+0B8h+arg_38]
0x180004679  lea     rdx, __ImageBase
0x180004680  cmp     r13, rbx
0x180004683  jz      loc_1800047EE
0x180004689  test    r12, r12
0x18000468c  jz      loc_180004720
0x180004692  mov     rbp, [r13-10h]
0x180004696  xor     r15d, r15d
0x180004699  nop     dword ptr [rax+00000000h]
0x1800046a0  cmp     r15d, [r12+4]
0x1800046a5  jnb     short loc_1800046E1
0x1800046a7  mov     edi, r15d
0x1800046aa  shl     rdi, 4
0x1800046ae  add     rdi, [r12+8]
0x1800046b3  xor     ebx, ebx
0x1800046b5  cmp     ebx, [rdi]
0x1800046b7  jnb     short loc_180004705
0x1800046b9  mov     rax, [rdi+8]
0x1800046bd  lea     rcx, [rbx+rbx*2]
0x1800046c1  lea     r9, [r13+18h]
0x1800046c5  mov     r8d, r14d
0x1800046c8  mov     rdx, rbp
0x1800046cb  lea     rcx, [rax+rcx*8]
0x1800046cf  call    FwQueryConditionMatchObject
0x1800046d4  test    eax, eax
0x1800046d6  jz      short loc_1800046DC
0x1800046d8  inc     ebx
0x1800046da  jmp     short loc_1800046B5
0x1800046dc  inc     r15d
0x1800046df  jmp     short loc_1800046A0
0x1800046e1  mov     edi, [rsp+0B8h+var_90]
0x1800046e5  mov     r8d, [rsp+0B8h+var_98]
0x1800046ea  mov     r13, [r13+0]
0x1800046ee  mov     rbx, [rsp+0B8h+var_70]
0x1800046f3  mov     esi, [rsp+0B8h+var_8C]
0x1800046f7  mov     ebp, [rsp+0B8h+var_94]
0x1800046fb  mov     rax, [rsp+0B8h+var_80]
0x180004700  jmp     loc_180004671
0x180004705  mov     edi, [rsp+0B8h+var_90]
0x180004709  mov     esi, [rsp+0B8h+var_8C]
0x18000470d  mov     ebp, [rsp+0B8h+var_94]
0x180004711  mov     r15d, dword ptr [rsp+0B8h+arg_38]
0x180004719  mov     rbx, [rsp+0B8h+var_80]
0x18000471e  jmp     short loc_180004764
0x180004720  mov     rcx, [r13-10h]
0x180004724  mov     rax, [rax+rdx+12A728h]
0x18000472c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004731  mov     ecx, [rsp+0B8h+arg_20]
0x180004738  test    [rax], ecx
0x18000473a  jz      short loc_1800046E5
0x18000473c  mov     rbx, [rsp+0B8h+var_80]
0x180004741  lea     rax, __ImageBase
0x180004748  mov     rcx, [r13-10h]
0x18000474c  mov     rax, [rbx+rax+12A730h]
0x180004754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004759  mov     ecx, [rsp+0B8h+arg_28]
0x180004760  test    [rax], ecx
0x180004762  jz      short loc_1800046E5
0x180004764  test    edi, edi
0x180004766  jz      loc_180004865
0x18000476c  cmp     edi, 1
0x18000476f  jnz     short loc_180004777
0x180004771  test    r15b, 20h
0x180004775  jnz     short loc_1800047E2
0x180004777  mov     rcx, [r13-10h]
0x18000477b  cmp     edi, 1
0x18000477e  jnz     loc_18000498E
0x180004784  test    esi, esi
0x180004786  jnz     loc_180004958
0x18000478c  lea     rdx, [rsp+0B8h+var_60]
0x180004791  call    cs:__imp_FwCopyRule
0x180004798  nop     dword ptr [rax+rax+00h]
0x18000479d  mov     [rsp+0B8h+var_98], eax
0x1800047a1  mov     r8d, eax
0x1800047a4  test    eax, eax
0x1800047a6  js      loc_1800048C4
0x1800047ac  test    edi, edi
0x1800047ae  jz      short loc_1800047B6
0x1800047b0  test    r15b, 40h
0x1800047b4  jnz     short loc_180004817
0x1800047b6  mov     r9, [rsp+0B8h+var_78]
0x1800047bb  inc     ebp
0x1800047bd  mov     rcx, [rsp+0B8h+var_60]
0x1800047c2  mov     [rsp+0B8h+var_94], ebp
0x1800047c6  mov     rdx, [r9]
0x1800047c9  mov     [rcx], rdx
0x1800047cc  mov     rax, [rsp+0B8h+var_60]
0x1800047d1  mov     [r9], rax
0x1800047d4  mov     [rsp+0B8h+var_60], 0
0x1800047dd  jmp     loc_1800046EA
0x1800047e2  cmp     qword ptr [r13+18h], 0
0x1800047e7  jnz     short loc_180004777
0x1800047e9  jmp     loc_1800046E5
0x1800047ee  mov     rcx, [rsp+0B8h+var_68]
0x1800047f3  add     [rcx], ebp
0x1800047f5  mov     eax, r8d
0x1800047f8  mov     rcx, [rsp+0B8h+var_58]
0x1800047fd  xor     rcx, rsp; StackCookie
0x180004800  call    __security_check_cookie
0x180004805  add     rsp, 78h
0x180004809  pop     r15
0x18000480b  pop     r14
0x18000480d  pop     r13
0x18000480f  pop     r12
0x180004811  pop     rdi
0x180004812  pop     rsi
0x180004813  pop     rbp
0x180004814  pop     rbx
0x180004815  retn
0x180004817  mov     eax, r14d
0x18000481a  lea     rsi, __ImageBase
0x180004821  imul    rbx, rax, 58h ; 'X'
0x180004825  lea     rcx, [r13+18h]
0x180004829  mov     edx, [rbx+rsi+13184Ch]
0x180004830  add     rdx, [rsp+0B8h+var_60]
0x180004835  call    cs:__imp_FwMetaDataCopy
0x18000483c  nop     dword ptr [rax+rax+00h]
0x180004841  mov     [rsp+0B8h+var_98], eax
0x180004845  mov     r8d, eax
0x180004848  test    eax, eax
0x18000484a  js      loc_1800049C3
0x180004850  mov     edx, [rbx+rsi+131850h]
0x180004857  mov     rcx, [rsp+0B8h+var_60]
0x18000485c  or      dword ptr [rdx+rcx], 1
0x180004860  jmp     loc_1800047B6
0x180004865  cmp     [rsp+0B8h+arg_50], 0
0x18000486d  jnz     loc_180004777
0x180004873  mov     rcx, [r13-10h]
0x180004877  lea     rax, __ImageBase
0x18000487e  mov     rax, [rbx+rax+12A738h]
0x180004886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000488b  movsxd  rdx, [rsp+0B8h+var_88]
0x180004890  mov     ecx, esi
0x180004892  lea     rcx, [rcx+rcx*2]
0x180004896  add     rcx, rdx
0x180004899  mov     rdx, [rax]; lpString2
0x18000489c  lea     rax, __ImageBase
0x1800048a3  mov     rcx, ds:rva ?wszDefaultSetGuids@@3PAY02PEAGA[rax+rcx*8]; lpString1
0x1800048ab  call    cs:__imp_lstrcmpiW
0x1800048b2  nop     dword ptr [rax+rax+00h]
0x1800048b7  test    eax, eax
0x1800048b9  jnz     loc_18000476C
0x1800048bf  jmp     loc_1800046E5
0x1800048c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800048cb  lea     rdx, WPP_GLOBAL_Control
0x1800048d2  cmp     rcx, rdx
0x1800048d5  jz      loc_1800047F5
0x1800048db  test    byte ptr [rcx+1Ch], 1
0x1800048df  jz      loc_1800047F5
0x1800048e5  mov     edx, 92h
0x1800048ea  mov     rcx, [rcx+10h]
0x1800048ee  lea     r8, WPP_3d9dabe50e6b3e70315acf6b635a3004_Traceguids
0x1800048f5  mov     r9d, eax
0x1800048f8  call    WPP_SF_d
0x1800048fd  mov     eax, [rsp+0B8h+var_98]
0x180004901  jmp     loc_1800047F8
0x180004906  cmp     esi, 1
0x180004909  jnz     short loc_180004913
0x18000490b  mov     r14d, esi
0x18000490e  jmp     loc_180004652
0x180004913  cmp     esi, 2
0x180004916  jnz     short loc_18000493F
0x180004918  mov     r14d, esi
0x18000491b  jmp     loc_180004652
0x180004920  test    esi, esi
0x180004922  jnz     short loc_18000492F
0x180004924  mov     r14d, 4
0x18000492a  jmp     loc_180004652
0x18000492f  cmp     esi, 1
0x180004932  jnz     short loc_18000493F
0x180004934  mov     r14d, 5
0x18000493a  jmp     loc_180004652
0x18000493f  mov     r8d, edi; __annotation("Debug", "TelemetryAssert", "FALSE", "Unknown FW_RULE_TYPE or FW_SET_TYPE")
0x180004942  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x180004949  mov     edx, esi
0x18000494b  call    MicrosoftTelemetryAssertTriggeredArgs
0x180004950  mov     r8d, ebp
0x180004953  jmp     loc_18000464F
0x180004958  cmp     esi, 1
0x18000495b  jnz     short loc_180004973
0x18000495d  lea     rdx, [rsp+0B8h+var_60]
0x180004962  call    cs:__imp_FwCopyCSRule
0x180004969  nop     dword ptr [rax+rax+00h]
0x18000496e  jmp     loc_18000479D
0x180004973  cmp     esi, 2
0x180004976  jnz     short loc_1800049EE
0x180004978  lea     rdx, [rsp+0B8h+var_60]
0x18000497d  call    cs:__imp_FwCopyMMRule
0x180004984  nop     dword ptr [rax+rax+00h]
0x180004989  jmp     loc_18000479D
0x18000498e  test    esi, esi
0x180004990  jnz     short loc_1800049A8
0x180004992  lea     rdx, [rsp+0B8h+var_60]
0x180004997  call    cs:__imp_FwPolioCopyAuthSet
0x18000499e  nop     dword ptr [rax+rax+00h]
0x1800049a3  jmp     loc_18000479D
0x1800049a8  cmp     esi, 1
0x1800049ab  jnz     short loc_1800049EE
0x1800049ad  lea     rdx, [rsp+0B8h+var_60]
0x1800049b2  call    cs:__imp_FwCopyCryptoSet
0x1800049b9  nop     dword ptr [rax+rax+00h]
0x1800049be  jmp     loc_18000479D
0x1800049c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800049ca  lea     rdx, WPP_GLOBAL_Control
0x1800049d1  cmp     rcx, rdx
0x1800049d4  jz      loc_1800047F8
0x1800049da  test    byte ptr [rcx+1Ch], 1
0x1800049de  jz      loc_1800047F8
0x1800049e4  mov     edx, 93h
0x1800049e9  jmp     loc_1800048EA
0x1800049ee  mov     r8d, edi; __annotation("Debug", "TelemetryAssert", "FALSE", "Unknown FW_RULE_TYPE or FW_SET_TYPE")
0x1800049f1  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x1800049f8  mov     edx, esi
0x1800049fa  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800049ff  mov     r8d, 80070057h
0x180004a05  mov     [rsp+0B8h+var_98], r8d
0x180004a0a  mov     eax, r8d
0x180004a0d  jmp     loc_1800048C4
```
