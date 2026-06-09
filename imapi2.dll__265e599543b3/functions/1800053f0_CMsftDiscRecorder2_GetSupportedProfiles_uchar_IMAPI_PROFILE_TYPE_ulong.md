# CMsftDiscRecorder2::GetSupportedProfiles(uchar,_IMAPI_PROFILE_TYPE * *,ulong *)

- ea: `0x1800053f0`
- end: `0x18000569c`
- name: `?GetSupportedProfiles@CMsftDiscRecorder2@@UEAAJEPEAPEAW4_IMAPI_PROFILE_TYPE@@PEAK@Z`
- size: `684`
- prototype: `__int64 __fastcall(CMsftDiscRecorder2 *__hidden this, unsigned __int8, enum _IMAPI_PROFILE_TYPE **, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180002fc8`
- `0x180004af0`
- `0x1800053f0`
- `0x1800140f4`
- `0x180014134`
- `0x180016778`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180005653`
- `ole32!CoTaskMemFree` at `0x18000565e`
- `ole32!CoTaskMemFree` at `0x180005653`
- `ole32!CoTaskMemFree` at `0x18000565e`
- `ole32!CoTaskMemAlloc` at `0x180005564`
- `ole32!CoTaskMemAlloc` at `0x180005564`

## pseudocode

```c
__int64 __fastcall CMsftDiscRecorder2::GetSupportedProfiles(
        CMsftDiscRecorder2 *this,
        char a2,
        enum _IMAPI_PROFILE_TYPE **a3,
        unsigned int *a4)
{
  PVOID *v8; // rcx
  signed int FeaturesHelper; // ebx
  __int64 v10; // r9
  unsigned int v11; // edi
  enum _IMAPI_PROFILE_TYPE *v12; // r14
  __int64 v13; // r8
  unsigned __int8 *v14; // rdx
  unsigned int i; // r9d
  const struct _GUID *v16; // r8
  unsigned int v18; // [rsp+70h] [rbp+18h] BYREF
  LPVOID pv; // [rsp+78h] [rbp+20h] BYREF

  pv = 0;
  v18 = 0;
  if ( a3 )
  {
    FeaturesHelper = 0;
    *a3 = 0;
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 137, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    FeaturesHelper = -2147467261;
  }
  if ( !a4 )
  {
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 188) & 4) != 0 && *((_BYTE *)v8 + 185) >= 3u )
      WPP_SF_(v8[22], 138, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
    FeaturesHelper = -2147467261;
    goto LABEL_36;
  }
  *a4 = 0;
  if ( FeaturesHelper < 0 )
  {
LABEL_36:
    CoTaskMemFree(0);
    goto LABEL_37;
  }
  v10 = *((unsigned int *)this + 58);
  if ( (v10 & 2) == 0 )
  {
    FeaturesHelper = -2147467259;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 22),
        139,
        &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
        v10,
        -2147467259);
    }
    goto LABEL_36;
  }
  FeaturesHelper = CMsftDiscRecorder2::GetFeaturesHelper(
                     (CMsftDiscRecorder2 *)((char *)this - 8),
                     0,
                     0,
                     0,
                     (unsigned __int8 **)&pv,
                     &v18);
  if ( FeaturesHelper < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 22),
        140,
        &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
        (unsigned int)FeaturesHelper);
    }
    goto LABEL_36;
  }
  v11 = *((unsigned __int8 *)pv + 3) >> 2;
  v12 = (enum _IMAPI_PROFILE_TYPE *)CoTaskMemAlloc(4LL * v11);
  if ( !v12 )
  {
    FeaturesHelper = -2147024882;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 22), 141, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids, v11, v11);
    }
    goto LABEL_36;
  }
  v13 = 0;
  v14 = (unsigned __int8 *)pv + 4;
  for ( i = 0; i < v11; v14 += 4 )
  {
    if ( !a2 || (v14[2] & 1) != 0 )
    {
      v12[v13] = v14[1] | (*v14 << 8);
      v13 = (unsigned int)(v13 + 1);
    }
    ++i;
  }
  *a3 = v12;
  *a4 = v13;
LABEL_37:
  CoTaskMemFree(pv);
  pv = 0;
  if ( (FeaturesHelper & 0x80FF0000) == 0x80AA0000 )
    Imapi2Utility::SetErrorDescription(FeaturesHelper, (int)&CLSID_MsftDiscRecorder2, v16);
  return (unsigned int)FeaturesHelper;
}

```

## disassembly

```asm
0x1800053f0  mov     [rsp+arg_0], rbx
0x1800053f5  push    rbp
0x1800053f6  push    rsi
0x1800053f7  push    rdi
0x1800053f8  push    r14
0x1800053fa  push    r15
0x1800053fc  sub     rsp, 30h
0x180005400  xor     r14d, r14d
0x180005403  lea     rax, WPP_GLOBAL_Control
0x18000540a  mov     [rsp+58h+pv], r14
0x18000540f  mov     rsi, r9
0x180005412  mov     [rsp+58h+arg_10], r14d
0x180005417  mov     r15, r8
0x18000541a  mov     bpl, dl
0x18000541d  mov     rdi, rcx
0x180005420  test    r8, r8
0x180005423  jnz     short loc_180005470
0x180005425  mov     rcx, cs:WPP_GLOBAL_Control
0x18000542c  cmp     rcx, rax
0x18000542f  jz      short loc_180005469
0x180005431  test    byte ptr [rcx+0BCh], 4
0x180005438  jz      short loc_180005469
0x18000543a  cmp     byte ptr [rcx+0B9h], 3
0x180005441  jb      short loc_180005469
0x180005443  mov     rcx, [rcx+0B0h]
0x18000544a  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180005451  mov     edx, 89h
0x180005456  call    WPP_SF_
0x18000545b  mov     rcx, cs:WPP_GLOBAL_Control
0x180005462  lea     rax, WPP_GLOBAL_Control
0x180005469  mov     ebx, 80004003h
0x18000546e  jmp     short loc_18000547C
0x180005470  xor     ebx, ebx
0x180005472  mov     [r8], rbx
0x180005475  mov     rcx, cs:WPP_GLOBAL_Control
0x18000547c  test    rsi, rsi
0x18000547f  jnz     short loc_1800054BA
0x180005481  cmp     rcx, rax
0x180005484  jz      short loc_1800054B0
0x180005486  test    byte ptr [rcx+0BCh], 4
0x18000548d  jz      short loc_1800054B0
0x18000548f  cmp     byte ptr [rcx+0B9h], 3
0x180005496  jb      short loc_1800054B0
0x180005498  mov     rcx, [rcx+0B0h]
0x18000549f  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x1800054a6  mov     edx, 8Ah
0x1800054ab  call    WPP_SF_
0x1800054b0  mov     ebx, 80004003h
0x1800054b5  jmp     loc_180005650
0x1800054ba  mov     [rsi], r14d
0x1800054bd  test    ebx, ebx
0x1800054bf  js      loc_180005650
0x1800054c5  mov     r9d, [rdi+0E8h]
0x1800054cc  test    r9b, 2
0x1800054d0  jz      loc_180005611
0x1800054d6  lea     rax, [rsp+58h+arg_10]
0x1800054db  xor     r8d, r8d; unsigned __int16
0x1800054de  mov     [rsp+58h+var_30], rax; unsigned int *
0x1800054e3  lea     rcx, [rdi-8]; this
0x1800054e7  lea     rax, [rsp+58h+pv]
0x1800054ec  xor     r9d, r9d; unsigned __int8
0x1800054ef  xor     edx, edx; unsigned __int8
0x1800054f1  mov     [rsp+58h+var_38], rax; unsigned __int8 **
0x1800054f6  call    ?GetFeaturesHelper@CMsftDiscRecorder2@@AEAAJEGEPEAPEAEPEAK@Z; CMsftDiscRecorder2::GetFeaturesHelper(uchar,ushort,uchar,uchar * *,ulong *)
0x1800054fb  mov     ebx, eax
0x1800054fd  test    eax, eax
0x1800054ff  jns     short loc_180005552
0x180005501  mov     rcx, cs:WPP_GLOBAL_Control
0x180005508  lea     rax, WPP_GLOBAL_Control
0x18000550f  cmp     rcx, rax
0x180005512  jz      loc_180005650
0x180005518  test    byte ptr [rcx+0BCh], 4
0x18000551f  jz      loc_180005650
0x180005525  cmp     byte ptr [rcx+0B9h], 3
0x18000552c  jb      loc_180005650
0x180005532  mov     rcx, [rcx+0B0h]
0x180005539  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180005540  mov     edx, 8Ch
0x180005545  mov     r9d, ebx
0x180005548  call    WPP_SF_d
0x18000554d  jmp     loc_180005650
0x180005552  mov     rax, [rsp+58h+pv]
0x180005557  movzx   edi, byte ptr [rax+3]
0x18000555b  shr     edi, 2
0x18000555e  mov     ecx, edi
0x180005560  shl     rcx, 2; cb
0x180005564  call    cs:__imp_CoTaskMemAlloc
0x18000556a  mov     r14, rax
0x18000556d  test    rax, rax
0x180005570  jnz     short loc_1800055CC
0x180005572  mov     ebx, 8007000Eh
0x180005577  mov     rcx, cs:WPP_GLOBAL_Control
0x18000557e  lea     rax, WPP_GLOBAL_Control
0x180005585  cmp     rcx, rax
0x180005588  jz      loc_180005650
0x18000558e  test    byte ptr [rcx+0BCh], 4
0x180005595  jz      loc_180005650
0x18000559b  cmp     byte ptr [rcx+0B9h], 3
0x1800055a2  jb      loc_180005650
0x1800055a8  mov     rcx, [rcx+0B0h]
0x1800055af  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x1800055b6  mov     edx, 8Dh
0x1800055bb  mov     dword ptr [rsp+58h+var_38], edi
0x1800055bf  mov     r9d, edi
0x1800055c2  call    WPP_SF_Dd
0x1800055c7  jmp     loc_180005650
0x1800055cc  mov     rdx, [rsp+58h+pv]
0x1800055d1  xor     r8d, r8d
0x1800055d4  add     rdx, 4
0x1800055d8  xor     r9d, r9d
0x1800055db  test    edi, edi
0x1800055dd  jz      short loc_180005609
0x1800055df  test    bpl, bpl
0x1800055e2  jz      short loc_1800055EA
0x1800055e4  test    byte ptr [rdx+2], 1
0x1800055e8  jz      short loc_1800055FD
0x1800055ea  movzx   ecx, byte ptr [rdx]
0x1800055ed  movzx   eax, byte ptr [rdx+1]
0x1800055f1  shl     ecx, 8
0x1800055f4  or      ecx, eax
0x1800055f6  mov     [r14+r8*4], ecx
0x1800055fa  inc     r8d
0x1800055fd  inc     r9d
0x180005600  add     rdx, 4
0x180005604  cmp     r9d, edi
0x180005607  jb      short loc_1800055DF
0x180005609  mov     [r15], r14
0x18000560c  mov     [rsi], r8d
0x18000560f  jmp     short loc_180005659
0x180005611  mov     ebx, 80004005h
0x180005616  mov     rcx, cs:WPP_GLOBAL_Control
0x18000561d  cmp     rcx, rax
0x180005620  jz      short loc_180005650
0x180005622  test    byte ptr [rcx+0BCh], 4
0x180005629  jz      short loc_180005650
0x18000562b  cmp     byte ptr [rcx+0B9h], 3
0x180005632  jb      short loc_180005650
0x180005634  mov     rcx, [rcx+0B0h]
0x18000563b  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180005642  mov     edx, 8Bh
0x180005647  mov     dword ptr [rsp+58h+var_38], ebx
0x18000564b  call    WPP_SF_Dd
0x180005650  mov     rcx, r14; pv
0x180005653  call    cs:__imp_CoTaskMemFree
0x180005659  mov     rcx, [rsp+58h+pv]; pv
0x18000565e  call    cs:__imp_CoTaskMemFree
0x180005664  mov     eax, ebx
0x180005666  mov     [rsp+58h+pv], 0
0x18000566f  and     eax, 80FF0000h
0x180005674  cmp     eax, 80AA0000h
0x180005679  jnz     short loc_180005689
0x18000567b  lea     rdx, CLSID_MsftDiscRecorder2; int
0x180005682  mov     ecx, ebx; dwMessageId
0x180005684  call    ?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z; Imapi2Utility::SetErrorDescription(long,_GUID const &)
0x180005689  mov     eax, ebx
0x18000568b  mov     rbx, [rsp+58h+arg_0]
0x180005690  add     rsp, 30h
0x180005694  pop     r15
0x180005696  pop     r14
0x180005698  pop     rdi
0x180005699  pop     rsi
0x18000569a  pop     rbp
0x18000569b  retn
```
