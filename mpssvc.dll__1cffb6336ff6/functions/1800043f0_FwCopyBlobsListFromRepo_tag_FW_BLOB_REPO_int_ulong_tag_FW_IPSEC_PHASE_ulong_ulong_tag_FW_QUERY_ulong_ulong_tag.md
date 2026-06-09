# FwCopyBlobsListFromRepo(_tag_FW_BLOB_REPO *,int,ulong,_tag_FW_IPSEC_PHASE,ulong,ulong,_tag_FW_QUERY *,ulong,ulong *,_tag_FW_BLOB_RULE * *,int)

- ea: `0x1800043f0`
- end: `0x180004807`
- name: `?FwCopyBlobsListFromRepo@@YAJPEAU_tag_FW_BLOB_REPO@@HKW4_tag_FW_IPSEC_PHASE@@KKPEAU_tag_FW_QUERY@@KPEAKPEAPEAU_tag_FW_BLOB_RULE@@H@Z`
- size: `1047`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003a04`
- `0x180003bc8`

## callees

- `0x1800043f0`
- `0x180004810`
- `0x18000af3c`
- `0x1800670c0`
- `0x18006f520`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800046be`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800046be`
- `fwbase!FwMetaDataCopy` at `0x18000464e`
- `fwbase!FwMetaDataCopy` at `0x18000464e`
- `FWPolicyIOMgr!FwCopyMMRule` at `0x180004784`
- `FWPolicyIOMgr!FwCopyMMRule` at `0x180004784`
- `FWPolicyIOMgr!FwCopyCryptoSet` at `0x1800047ad`
- `FWPolicyIOMgr!FwCopyCryptoSet` at `0x1800047ad`
- `FWPolicyIOMgr!FwPolioCopyAuthSet` at `0x180004798`
- `FWPolicyIOMgr!FwPolioCopyAuthSet` at `0x180004798`
- `FWPolicyIOMgr!FwCopyCSRule` at `0x18000476f`
- `FWPolicyIOMgr!FwCopyCSRule` at `0x18000476f`
- `FWPolicyIOMgr!FwCopyRule` at `0x1800045b1`
- `FWPolicyIOMgr!FwCopyRule` at `0x1800045b1`

## string_xrefs

- `0x18000474f`: `mpssvc.dll`
- `0x1800047e6`: `mpssvc.dll`

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
          & *(_DWORD *)(*(enum _tag_FW_RULE_STATUS *(__fastcall **)(void *))((char *)&off_180124728 + v19))((void *)*(v17 - 2))) == 0 )
        goto LABEL_17;
      v26 = i;
      if ( (a6 & *(*(unsigned int *(__fastcall **)(void *))((char *)&off_180124730 + i))((void *)*(v17 - 2))) == 0 )
        goto LABEL_17;
    }
    if ( !v12 )
    {
      if ( a11 )
        goto LABEL_25;
      v30 = (LPCWSTR *)(*(__int64 (__fastcall **)(_QWORD, __int16 *))((char *)off_180124738 + v26))(*(v17 - 2), v21);
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
    WPP_SF_d(*(_QWORD *)(v31 + 16), v32, WPP_e2321870bb8f37110138dfc56d389809_Traceguids, (unsigned int)result);
    return v33;
  }
  return result;
}

```

## disassembly

```asm
0x1800043f0  push    rbx
0x1800043f2  push    rbp
0x1800043f3  push    rsi
0x1800043f4  push    rdi
0x1800043f5  push    r12
0x1800043f7  push    r13
0x1800043f9  push    r14
0x1800043fb  push    r15
0x1800043fd  sub     rsp, 78h
0x180004401  mov     rax, cs:__security_cookie
0x180004408  xor     rax, rsp
0x18000440b  mov     [rsp+0B8h+var_58], rax
0x180004410  mov     rax, [rsp+0B8h+arg_40]
0x180004418  xor     ebp, ebp
0x18000441a  mov     r12, [rsp+0B8h+arg_30]
0x180004422  mov     edi, edx
0x180004424  mov     esi, r8d
0x180004427  mov     rbx, rcx
0x18000442a  xor     r8d, r8d
0x18000442d  mov     [rsp+0B8h+var_68], rax
0x180004432  mov     rax, [rsp+0B8h+arg_48]
0x18000443a  mov     [rsp+0B8h+var_78], rax
0x18000443f  mov     [rsp+0B8h+var_88], r9d
0x180004444  mov     [rsp+0B8h+var_8C], esi
0x180004448  mov     [rsp+0B8h+var_90], edx
0x18000444c  mov     [rsp+0B8h+var_70], rcx
0x180004451  mov     [rsp+0B8h+var_98], r8d
0x180004456  mov     [rsp+0B8h+var_60], r8
0x18000445b  mov     [rsp+0B8h+var_94], ebp
0x18000445f  test    edx, edx
0x180004461  jz      loc_18000472D
0x180004467  test    esi, esi
0x180004469  jnz     loc_180004713
0x18000446f  xor     r14d, r14d
0x180004472  mov     r13, [rbx]
0x180004475  xor     eax, eax
0x180004477  test    edi, edi
0x180004479  mov     edx, 3
0x18000447e  cmovz   eax, edx
0x180004481  add     rax, rsi
0x180004484  lea     rax, [rax+rax*2]
0x180004488  shl     rax, 4
0x18000448c  mov     [rsp+0B8h+var_80], rax
0x180004491  mov     r15d, dword ptr [rsp+0B8h+arg_38]
0x180004499  lea     rdx, __ImageBase
0x1800044a0  cmp     r13, rbx
0x1800044a3  jz      loc_180004608
0x1800044a9  test    r12, r12
0x1800044ac  jz      loc_180004540
0x1800044b2  mov     rbp, [r13-10h]
0x1800044b6  xor     r15d, r15d
0x1800044b9  nop     dword ptr [rax+00000000h]
0x1800044c0  cmp     r15d, [r12+4]
0x1800044c5  jnb     short loc_180004501
0x1800044c7  mov     edi, r15d
0x1800044ca  shl     rdi, 4
0x1800044ce  add     rdi, [r12+8]
0x1800044d3  xor     ebx, ebx
0x1800044d5  cmp     ebx, [rdi]
0x1800044d7  jnb     short loc_180004525
0x1800044d9  mov     rax, [rdi+8]
0x1800044dd  lea     rcx, [rbx+rbx*2]
0x1800044e1  lea     r9, [r13+18h]
0x1800044e5  mov     r8d, r14d
0x1800044e8  mov     rdx, rbp
0x1800044eb  lea     rcx, [rax+rcx*8]
0x1800044ef  call    FwQueryConditionMatchObject
0x1800044f4  test    eax, eax
0x1800044f6  jz      short loc_1800044FC
0x1800044f8  inc     ebx
0x1800044fa  jmp     short loc_1800044D5
0x1800044fc  inc     r15d
0x1800044ff  jmp     short loc_1800044C0
0x180004501  mov     edi, [rsp+0B8h+var_90]
0x180004505  mov     r8d, [rsp+0B8h+var_98]
0x18000450a  mov     r13, [r13+0]
0x18000450e  mov     rbx, [rsp+0B8h+var_70]
0x180004513  mov     esi, [rsp+0B8h+var_8C]
0x180004517  mov     ebp, [rsp+0B8h+var_94]
0x18000451b  mov     rax, [rsp+0B8h+var_80]
0x180004520  jmp     loc_180004491
0x180004525  mov     edi, [rsp+0B8h+var_90]
0x180004529  mov     esi, [rsp+0B8h+var_8C]
0x18000452d  mov     ebp, [rsp+0B8h+var_94]
0x180004531  mov     r15d, dword ptr [rsp+0B8h+arg_38]
0x180004539  mov     rbx, [rsp+0B8h+var_80]
0x18000453e  jmp     short loc_180004584
0x180004540  mov     rcx, [r13-10h]
0x180004544  mov     rax, [rax+rdx+124728h]
0x18000454c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004551  mov     ecx, [rsp+0B8h+arg_20]
0x180004558  test    [rax], ecx
0x18000455a  jz      short loc_180004505
0x18000455c  mov     rbx, [rsp+0B8h+var_80]
0x180004561  lea     rax, __ImageBase
0x180004568  mov     rcx, [r13-10h]
0x18000456c  mov     rax, [rbx+rax+124730h]
0x180004574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004579  mov     ecx, [rsp+0B8h+arg_28]
0x180004580  test    [rax], ecx
0x180004582  jz      short loc_180004505
0x180004584  test    edi, edi
0x180004586  jz      loc_180004678
0x18000458c  cmp     edi, 1
0x18000458f  jnz     short loc_180004597
0x180004591  test    r15b, 20h
0x180004595  jnz     short loc_1800045FC
0x180004597  mov     rcx, [r13-10h]
0x18000459b  cmp     edi, 1
0x18000459e  jnz     loc_18000478F
0x1800045a4  test    esi, esi
0x1800045a6  jnz     loc_180004765
0x1800045ac  lea     rdx, [rsp+0B8h+var_60]
0x1800045b1  call    cs:__imp_FwCopyRule
0x1800045b7  mov     [rsp+0B8h+var_98], eax
0x1800045bb  mov     r8d, eax
0x1800045be  test    eax, eax
0x1800045c0  js      loc_1800046D1
0x1800045c6  test    edi, edi
0x1800045c8  jz      short loc_1800045D0
0x1800045ca  test    r15b, 40h
0x1800045ce  jnz     short loc_180004630
0x1800045d0  mov     r9, [rsp+0B8h+var_78]
0x1800045d5  inc     ebp
0x1800045d7  mov     rcx, [rsp+0B8h+var_60]
0x1800045dc  mov     [rsp+0B8h+var_94], ebp
0x1800045e0  mov     rdx, [r9]
0x1800045e3  mov     [rcx], rdx
0x1800045e6  mov     rax, [rsp+0B8h+var_60]
0x1800045eb  mov     [r9], rax
0x1800045ee  mov     [rsp+0B8h+var_60], 0
0x1800045f7  jmp     loc_18000450A
0x1800045fc  cmp     qword ptr [r13+18h], 0
0x180004601  jnz     short loc_180004597
0x180004603  jmp     loc_180004505
0x180004608  mov     rcx, [rsp+0B8h+var_68]
0x18000460d  add     [rcx], ebp
0x18000460f  mov     eax, r8d
0x180004612  mov     rcx, [rsp+0B8h+var_58]
0x180004617  xor     rcx, rsp; StackCookie
0x18000461a  call    __security_check_cookie
0x18000461f  add     rsp, 78h
0x180004623  pop     r15
0x180004625  pop     r14
0x180004627  pop     r13
0x180004629  pop     r12
0x18000462b  pop     rdi
0x18000462c  pop     rsi
0x18000462d  pop     rbp
0x18000462e  pop     rbx
0x18000462f  retn
0x180004630  mov     eax, r14d
0x180004633  lea     rsi, __ImageBase
0x18000463a  imul    rbx, rax, 58h ; 'X'
0x18000463e  lea     rcx, [r13+18h]
0x180004642  mov     edx, [rbx+rsi+12B64Ch]
0x180004649  add     rdx, [rsp+0B8h+var_60]
0x18000464e  call    cs:__imp_FwMetaDataCopy
0x180004654  mov     [rsp+0B8h+var_98], eax
0x180004658  mov     r8d, eax
0x18000465b  test    eax, eax
0x18000465d  js      loc_1800047B8
0x180004663  mov     edx, [rbx+rsi+12B650h]
0x18000466a  mov     rcx, [rsp+0B8h+var_60]
0x18000466f  or      dword ptr [rdx+rcx], 1
0x180004673  jmp     loc_1800045D0
0x180004678  cmp     [rsp+0B8h+arg_50], 0
0x180004680  jnz     loc_180004597
0x180004686  mov     rcx, [r13-10h]
0x18000468a  lea     rax, __ImageBase
0x180004691  mov     rax, [rbx+rax+124738h]
0x180004699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000469e  movsxd  rdx, [rsp+0B8h+var_88]
0x1800046a3  mov     ecx, esi
0x1800046a5  lea     rcx, [rcx+rcx*2]
0x1800046a9  add     rcx, rdx
0x1800046ac  mov     rdx, [rax]; lpString2
0x1800046af  lea     rax, __ImageBase
0x1800046b6  mov     rcx, ds:rva ?wszDefaultSetGuids@@3PAY02PEAGA[rax+rcx*8]; lpString1
0x1800046be  call    cs:__imp_lstrcmpiW
0x1800046c4  test    eax, eax
0x1800046c6  jnz     loc_18000458C
0x1800046cc  jmp     loc_180004505
0x1800046d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800046d8  lea     rdx, WPP_GLOBAL_Control
0x1800046df  cmp     rcx, rdx
0x1800046e2  jz      loc_18000460F
0x1800046e8  test    byte ptr [rcx+1Ch], 1
0x1800046ec  jz      loc_18000460F
0x1800046f2  mov     edx, 92h
0x1800046f7  mov     rcx, [rcx+10h]
0x1800046fb  lea     r8, WPP_e2321870bb8f37110138dfc56d389809_Traceguids
0x180004702  mov     r9d, eax
0x180004705  call    WPP_SF_d
0x18000470a  mov     eax, [rsp+0B8h+var_98]
0x18000470e  jmp     loc_180004612
0x180004713  cmp     esi, 1
0x180004716  jnz     short loc_180004720
0x180004718  mov     r14d, esi
0x18000471b  jmp     loc_180004472
0x180004720  cmp     esi, 2
0x180004723  jnz     short loc_18000474C
0x180004725  mov     r14d, esi
0x180004728  jmp     loc_180004472
0x18000472d  test    esi, esi
0x18000472f  jnz     short loc_18000473C
0x180004731  mov     r14d, 4
0x180004737  jmp     loc_180004472
0x18000473c  cmp     esi, 1
0x18000473f  jnz     short loc_18000474C
0x180004741  mov     r14d, 5
0x180004747  jmp     loc_180004472
0x18000474c  mov     r8d, edi
0x18000474f  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x180004756  mov     edx, esi
0x180004758  call    MicrosoftTelemetryAssertTriggeredArgs
0x18000475d  mov     r8d, ebp
0x180004760  jmp     loc_18000446F
0x180004765  cmp     esi, 1
0x180004768  jnz     short loc_18000477A
0x18000476a  lea     rdx, [rsp+0B8h+var_60]
0x18000476f  call    cs:__imp_FwCopyCSRule
0x180004775  jmp     loc_1800045B7
0x18000477a  cmp     esi, 2
0x18000477d  jnz     short loc_1800047E3
0x18000477f  lea     rdx, [rsp+0B8h+var_60]
0x180004784  call    cs:__imp_FwCopyMMRule
0x18000478a  jmp     loc_1800045B7
0x18000478f  test    esi, esi
0x180004791  jnz     short loc_1800047A3
0x180004793  lea     rdx, [rsp+0B8h+var_60]
0x180004798  call    cs:__imp_FwPolioCopyAuthSet
0x18000479e  jmp     loc_1800045B7
0x1800047a3  cmp     esi, 1
0x1800047a6  jnz     short loc_1800047E3
0x1800047a8  lea     rdx, [rsp+0B8h+var_60]
0x1800047ad  call    cs:__imp_FwCopyCryptoSet
0x1800047b3  jmp     loc_1800045B7
0x1800047b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800047bf  lea     rdx, WPP_GLOBAL_Control
0x1800047c6  cmp     rcx, rdx
0x1800047c9  jz      loc_180004612
0x1800047cf  test    byte ptr [rcx+1Ch], 1
0x1800047d3  jz      loc_180004612
0x1800047d9  mov     edx, 93h
0x1800047de  jmp     loc_1800046F7
0x1800047e3  mov     r8d, edi
0x1800047e6  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x1800047ed  mov     edx, esi
0x1800047ef  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800047f4  mov     r8d, 80070057h
0x1800047fa  mov     [rsp+0B8h+var_98], r8d
0x1800047ff  mov     eax, r8d
0x180004802  jmp     loc_1800046D1
```
