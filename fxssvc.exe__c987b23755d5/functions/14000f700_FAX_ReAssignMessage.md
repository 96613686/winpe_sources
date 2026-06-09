# FAX_ReAssignMessage

- ea: `0x14000f700`
- end: `0x14000fc99`
- name: `FAX_ReAssignMessage`
- size: `1433`
- prototype: `__int64 __fastcall(__int64, unsigned __int64, wchar_t **)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140002c43`
- `0x140004b30`
- `0x140004b58`
- `0x14000bf38`
- `0x14000cf58`
- `0x14000d79c`
- `0x14000f700`
- `0x14000fca0`
- `0x14000fce0`
- `0x1400452ac`
- `0x140065d14`
- `0x140065dbc`
- `0x140070b0c`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14000fad5`
- `KERNEL32!EnterCriticalSection` at `0x14000fad5`
- `KERNEL32!LeaveCriticalSection` at `0x14000fb70`
- `KERNEL32!LeaveCriticalSection` at `0x14000fb70`
- `msvcrt!wcschr` at `0x14000f9ea`
- `msvcrt!wcschr` at `0x14000f9ea`

## string_xrefs

- `0x14000f847`: `Microsoft-Windows-Fax-Common-EnableServerPolicy`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall FAX_ReAssignMessage(__int64 a1, unsigned __int64 a2, wchar_t **a3)
{
  unsigned int v5; // eax
  unsigned int v6; // edi
  CMapDeviceId *v8; // rcx
  __int64 v9; // rdx
  wchar_t *v10; // rcx
  __int64 v11; // r14
  __int64 v12; // rax
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  wchar_t *v16; // rdi
  CMapDeviceId *v17; // r10
  unsigned int v18; // esi
  const wchar_t *i; // rcx
  wchar_t *v20; // rax
  wchar_t *v21; // rax
  unsigned int v22; // edi
  void **v23; // rax
  void **v24; // rsi
  unsigned int AccountSIDsFromAccountString; // r14d
  CMapDeviceId *v26; // rcx
  __int64 v27; // rdx
  unsigned int j; // ebx
  unsigned int v29; // [rsp+28h] [rbp-D8h]
  __int32 v30; // [rsp+30h] [rbp-D0h] BYREF
  int v31; // [rsp+34h] [rbp-CCh] BYREF
  int v32; // [rsp+38h] [rbp-C8h]
  WCHAR FileName[264]; // [rsp+40h] [rbp-C0h] BYREF

  v31 = 0;
  v30 = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 142, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids);
  }
  v5 = FaxSvcAccessCheck(0x200u, &v31, 0, 1);
  v6 = v5;
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids, v5);
    }
    return v6;
  }
  if ( !v31 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 144, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids);
    }
    return 5;
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids);
  }
  v32 = 0;
  if ( (int)GetLicensingPolicyValue((wchar_t *)L"Microsoft-Windows-Fax-Common-EnableServerPolicy") < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control )
      return 4317;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      goto LABEL_102;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids);
LABEL_101:
    v8 = WPP_GLOBAL_Control;
LABEL_102:
    if ( v8 == (CMapDeviceId *)&WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 4) == 0 || *((_BYTE *)v8 + 25) < 2u )
      return 4317;
    v9 = 145;
LABEL_106:
    WPP_SF_(*((_QWORD *)v8 + 2), v9, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids);
    return 4317;
  }
  if ( !v32 )
    goto LABEL_101;
  _InterlockedExchange(&v30, *((_DWORD *)g_pFaxConfig + 21));
  if ( v30 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 4317;
    }
    v9 = 146;
    goto LABEL_106;
  }
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_i(*((_QWORD *)WPP_GLOBAL_Control + 2), 147, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids, 0);
    }
    return 87;
  }
  v10 = *a3;
  if ( !*a3 )
    goto LABEL_94;
  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( v10[v12] );
  if ( !v12 )
  {
LABEL_94:
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 148, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids);
    }
    return 87;
  }
  v13 = CFaxArchiving::SearchMessage((CFaxArchiving *)v10, a2, 0, 0, FileName, v29);
  v6 = v13;
  if ( v13 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_id(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, v15, a2, v13);
    }
    return v6;
  }
  v16 = *a3;
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_04fb59550d79390d980a26525e0212b0_Traceguids);
    v17 = WPP_GLOBAL_Control;
  }
  if ( v16 )
  {
    v18 = 0;
    for ( i = v16; ; i = v20 + 1 )
    {
      v20 = wcschr(i, 0x3Bu);
      if ( !v20 )
        break;
      ++v18;
    }
    v17 = WPP_GLOBAL_Control;
  }
  else
  {
    if ( v17 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 2) != 0 && *((_BYTE *)v17 + 25) >= 3u )
    {
      WPP_SF_(*((_QWORD *)v17 + 2), 69, WPP_04fb59550d79390d980a26525e0212b0_Traceguids);
      v17 = WPP_GLOBAL_Control;
    }
    v18 = 0;
  }
  v21 = *a3;
  do
    ++v11;
  while ( v21[v11] );
  v22 = v18 + 1;
  if ( v21[v11 - 1] == 59 )
    v22 = v18;
  if ( v22 > 0x2710 )
  {
    if ( v17 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 4) != 0 && *((_BYTE *)v17 + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)v17 + 2), 150, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids, v22);
    return 111;
  }
  if ( is_mul_ok(v22, 8u) )
  {
    v23 = (void **)pMemAlloc(8LL * v22);
    v24 = v23;
    if ( !v23 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 152, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids, 8 * v22);
      }
      return 8;
    }
    memset_0(v23, 0, 8LL * v22);
    EnterCriticalSection(&g_CsConfig);
    AccountSIDsFromAccountString = GetAccountSIDsFromAccountString(*a3, v24, v22);
    if ( AccountSIDsFromAccountString )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_84;
      }
      v27 = 153;
    }
    else
    {
      AccountSIDsFromAccountString = ReAssignMessage(FileName, a2, a3, v24, v22);
      if ( !AccountSIDsFromAccountString )
        goto LABEL_84;
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_84;
      }
      v27 = 154;
    }
    WPP_SF_d(*((_QWORD *)v26 + 2), v27, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids, AccountSIDsFromAccountString);
LABEL_84:
    LeaveCriticalSection(&g_CsConfig);
    for ( j = 0; j < v22; ++j )
      pMemFree(v24[j]);
    pMemFree(v24);
    return AccountSIDsFromAccountString;
  }
  if ( v17 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 4) != 0 && *((_BYTE *)v17 + 25) >= 2u )
    WPP_SF_d(*((_QWORD *)v17 + 2), 151, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids, 2147942934LL);
  return 534;
}

```

## disassembly

```asm
0x14000f700  mov     [rsp-8+arg_0], rbx
0x14000f705  push    rbp
0x14000f706  push    rsi
0x14000f707  push    rdi
0x14000f708  push    r12
0x14000f70a  push    r13
0x14000f70c  push    r14
0x14000f70e  push    r15
0x14000f710  lea     rbp, [rsp-160h]
0x14000f718  sub     rsp, 260h
0x14000f71f  mov     rax, cs:__security_cookie
0x14000f726  xor     rax, rsp
0x14000f729  mov     [rbp+190h+var_40], rax
0x14000f730  xor     r13d, r13d
0x14000f733  mov     r15, r8
0x14000f736  mov     [rsp+290h+var_25C], r13d
0x14000f73b  mov     r12, rdx
0x14000f73e  mov     [rsp+290h+var_260], r13d
0x14000f743  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f74a  lea     rsi, WPP_GLOBAL_Control
0x14000f751  mov     r14b, 4
0x14000f754  cmp     rcx, rsi
0x14000f757  jz      short loc_14000F77A
0x14000f759  test    [rcx+1Ch], r14b
0x14000f75d  jz      short loc_14000F77A
0x14000f75f  cmp     byte ptr [rcx+19h], 5
0x14000f763  jb      short loc_14000F77A
0x14000f765  mov     rcx, [rcx+10h]
0x14000f769  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000f770  mov     edx, 8Eh
0x14000f775  call    WPP_SF_
0x14000f77a  mov     r9d, 1; int
0x14000f780  lea     rdx, [rsp+290h+var_25C]; int *
0x14000f785  xor     r8d, r8d; unsigned int *
0x14000f788  mov     ecx, 200h; unsigned int
0x14000f78d  call    ?FaxSvcAccessCheck@@YAKKPEAHPEAKH@Z; FaxSvcAccessCheck(ulong,int *,ulong *,int)
0x14000f792  mov     edi, eax
0x14000f794  test    eax, eax
0x14000f796  jz      short loc_14000F7D0
0x14000f798  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f79f  cmp     rcx, rsi
0x14000f7a2  jz      short loc_14000F7C9
0x14000f7a4  test    [rcx+1Ch], r14b
0x14000f7a8  jz      short loc_14000F7C9
0x14000f7aa  mov     bl, 2
0x14000f7ac  cmp     [rcx+19h], bl
0x14000f7af  jb      short loc_14000F7C9
0x14000f7b1  mov     rcx, [rcx+10h]
0x14000f7b5  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000f7bc  mov     edx, 8Fh
0x14000f7c1  mov     r9d, eax
0x14000f7c4  call    WPP_SF_d
0x14000f7c9  mov     eax, edi
0x14000f7cb  jmp     loc_14000FC6F
0x14000f7d0  cmp     [rsp+290h+var_25C], r13d
0x14000f7d5  jnz     short loc_14000F80F
0x14000f7d7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f7de  cmp     rcx, rsi
0x14000f7e1  jz      short loc_14000F805
0x14000f7e3  test    [rcx+1Ch], r14b
0x14000f7e7  jz      short loc_14000F805
0x14000f7e9  mov     bl, 2
0x14000f7eb  cmp     [rcx+19h], bl
0x14000f7ee  jb      short loc_14000F805
0x14000f7f0  mov     rcx, [rcx+10h]
0x14000f7f4  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000f7fb  mov     edx, 90h
0x14000f800  call    WPP_SF_
0x14000f805  mov     eax, 5
0x14000f80a  jmp     loc_14000FC6F
0x14000f80f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f816  mov     bl, 2
0x14000f818  cmp     rcx, rsi
0x14000f81b  jz      short loc_14000F83D
0x14000f81d  test    [rcx+1Ch], bl
0x14000f820  jz      short loc_14000F83D
0x14000f822  cmp     byte ptr [rcx+19h], 5
0x14000f826  jb      short loc_14000F83D
0x14000f828  mov     rcx, [rcx+10h]
0x14000f82c  lea     r8, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids
0x14000f833  mov     edx, 28h ; '('
0x14000f838  call    WPP_SF_
0x14000f83d  lea     rdx, [rsp+290h+var_258]
0x14000f842  mov     [rsp+290h+var_258], r13d
0x14000f847  lea     rcx, aMicrosoftWindo; "Microsoft-Windows-Fax-Common-EnableServ"...
0x14000f84e  call    GetLicensingPolicyValue
0x14000f853  test    eax, eax
0x14000f855  js      loc_14000FC12
0x14000f85b  cmp     [rsp+290h+var_258], r13d
0x14000f860  jz      loc_14000FC3E
0x14000f866  mov     rax, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x14000f86d  mov     ecx, [rax+54h]
0x14000f870  xchg    ecx, [rsp+290h+var_260]
0x14000f874  cmp     [rsp+290h+var_260], r13d
0x14000f879  jz      short loc_14000F8A8
0x14000f87b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f882  cmp     rcx, rsi
0x14000f885  jz      loc_14000FC6A
0x14000f88b  test    [rcx+1Ch], r14b
0x14000f88f  jz      loc_14000FC6A
0x14000f895  cmp     [rcx+19h], bl
0x14000f898  jb      loc_14000FC6A
0x14000f89e  mov     edx, 92h
0x14000f8a3  jmp     loc_14000FC5A
0x14000f8a8  test    r12, r12
0x14000f8ab  jnz     short loc_14000F8ED
0x14000f8ad  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f8b4  cmp     rcx, rsi
0x14000f8b7  jz      loc_14000FC0B
0x14000f8bd  test    [rcx+1Ch], r14b
0x14000f8c1  jz      loc_14000FC0B
0x14000f8c7  cmp     [rcx+19h], bl
0x14000f8ca  jb      loc_14000FC0B
0x14000f8d0  mov     rcx, [rcx+10h]
0x14000f8d4  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000f8db  mov     edx, 93h
0x14000f8e0  xor     r9d, r9d
0x14000f8e3  call    WPP_SF_i
0x14000f8e8  jmp     loc_14000FC0B
0x14000f8ed  mov     rcx, [r15]; this
0x14000f8f0  test    rcx, rcx
0x14000f8f3  jz      loc_14000FBDF
0x14000f8f9  or      r14, 0FFFFFFFFFFFFFFFFh
0x14000f8fd  mov     rax, r14
0x14000f900  inc     rax
0x14000f903  cmp     [rcx+rax*2], r13w
0x14000f908  jnz     short loc_14000F900
0x14000f90a  test    rax, rax
0x14000f90d  jz      loc_14000FBDC
0x14000f913  lea     rax, [rsp+290h+FileName]
0x14000f918  xor     r9d, r9d; void *
0x14000f91b  xor     r8d, r8d; int
0x14000f91e  mov     [rsp+290h+var_270], rax; unsigned __int16 *
0x14000f923  mov     rdx, r12; unsigned __int64
0x14000f926  call    ?SearchMessage@CFaxArchiving@@QEAAK_KHPEAXPEAGK@Z; CFaxArchiving::SearchMessage(unsigned __int64,int,void *,ushort *,ulong)
0x14000f92b  mov     edi, eax
0x14000f92d  test    eax, eax
0x14000f92f  jz      short loc_14000F969
0x14000f931  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f938  cmp     rcx, rsi
0x14000f93b  jz      loc_14000F7C9
0x14000f941  test    byte ptr [rcx+1Ch], 4
0x14000f945  jz      loc_14000F7C9
0x14000f94b  cmp     [rcx+19h], bl
0x14000f94e  jb      loc_14000F7C9
0x14000f954  mov     rcx, [rcx+10h]
0x14000f958  mov     r9, r12
0x14000f95b  mov     dword ptr [rsp+290h+var_270], eax
0x14000f95f  call    WPP_SF_id
0x14000f964  jmp     loc_14000F7C9
0x14000f969  mov     rdi, [r15]
0x14000f96c  mov     r10, cs:WPP_GLOBAL_Control
0x14000f973  cmp     r10, rsi
0x14000f976  jz      short loc_14000F9A1
0x14000f978  test    [r10+1Ch], bl
0x14000f97c  jz      short loc_14000F9A1
0x14000f97e  cmp     byte ptr [r10+19h], 5
0x14000f983  jb      short loc_14000F9A1
0x14000f985  mov     rcx, [r10+10h]
0x14000f989  lea     r8, WPP_04fb59550d79390d980a26525e0212b0_Traceguids
0x14000f990  mov     edx, 44h ; 'D'
0x14000f995  call    WPP_SF_
0x14000f99a  mov     r10, cs:WPP_GLOBAL_Control
0x14000f9a1  test    rdi, rdi
0x14000f9a4  jnz     short loc_14000F9D7
0x14000f9a6  cmp     r10, rsi
0x14000f9a9  jz      short loc_14000F9D2
0x14000f9ab  test    [r10+1Ch], bl
0x14000f9af  jz      short loc_14000F9D2
0x14000f9b1  cmp     byte ptr [r10+19h], 3
0x14000f9b6  jb      short loc_14000F9D2
0x14000f9b8  mov     rcx, [r10+10h]
0x14000f9bc  lea     edx, [rdi+45h]
0x14000f9bf  lea     r8, WPP_04fb59550d79390d980a26525e0212b0_Traceguids
0x14000f9c6  call    WPP_SF_
0x14000f9cb  mov     r10, cs:WPP_GLOBAL_Control
0x14000f9d2  mov     esi, r13d
0x14000f9d5  jmp     short loc_14000F9FC
0x14000f9d7  mov     esi, r13d
0x14000f9da  mov     rcx, rdi
0x14000f9dd  jmp     short loc_14000F9E5
0x14000f9df  inc     esi
0x14000f9e1  lea     rcx, [rax+2]; Str
0x14000f9e5  mov     edx, 3Bh ; ';'; Ch
0x14000f9ea  call    cs:__imp_wcschr
0x14000f9f0  test    rax, rax
0x14000f9f3  jnz     short loc_14000F9DF
0x14000f9f5  mov     r10, cs:WPP_GLOBAL_Control
0x14000f9fc  mov     rax, [r15]
0x14000f9ff  inc     r14
0x14000fa02  cmp     [rax+r14*2], r13w
0x14000fa07  jnz     short loc_14000F9FF
0x14000fa09  mov     ecx, 3Bh ; ';'
0x14000fa0e  lea     edi, [rsi+1]
0x14000fa11  cmp     [rax+r14*2-2], cx
0x14000fa17  cmovz   edi, esi
0x14000fa1a  cmp     edi, 2710h
0x14000fa20  jbe     short loc_14000FA5B
0x14000fa22  lea     rax, WPP_GLOBAL_Control
0x14000fa29  cmp     r10, rax
0x14000fa2c  jz      short loc_14000FA51
0x14000fa2e  test    byte ptr [r10+1Ch], 4
0x14000fa33  jz      short loc_14000FA51
0x14000fa35  cmp     [r10+19h], bl
0x14000fa39  jb      short loc_14000FA51
0x14000fa3b  lea     edx, [rcx+5Bh]
0x14000fa3e  mov     r9d, edi
0x14000fa41  mov     rcx, [r10+10h]
0x14000fa45  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000fa4c  call    WPP_SF_d
0x14000fa51  mov     eax, 6Fh ; 'o'
0x14000fa56  jmp     loc_14000FC6F
0x14000fa5b  mov     ecx, edi
0x14000fa5d  mov     eax, 8
0x14000fa62  mul     rcx
0x14000fa65  mov     r14, rax
0x14000fa68  test    rdx, rdx
0x14000fa6b  jnz     loc_14000FB9E
0x14000fa71  mov     rcx, rax; dwBytes
0x14000fa74  call    pMemAlloc
0x14000fa79  mov     rsi, rax
0x14000fa7c  test    rax, rax
0x14000fa7f  jnz     short loc_14000FAC1
0x14000fa81  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fa88  lea     rax, WPP_GLOBAL_Control
0x14000fa8f  cmp     rcx, rax
0x14000fa92  jz      short loc_14000FAB7
0x14000fa94  test    byte ptr [rcx+1Ch], 4
0x14000fa98  jz      short loc_14000FAB7
0x14000fa9a  cmp     [rcx+19h], bl
0x14000fa9d  jb      short loc_14000FAB7
0x14000fa9f  mov     rcx, [rcx+10h]
0x14000faa3  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000faaa  mov     r9d, r14d
0x14000faad  mov     edx, 98h
0x14000fab2  call    WPP_SF_d
0x14000fab7  mov     eax, 8
0x14000fabc  jmp     loc_14000FC6F
0x14000fac1  mov     r8, r14; Size
0x14000fac4  xor     edx, edx; Val
0x14000fac6  mov     rcx, rsi; void *
0x14000fac9  call    memset_0
0x14000face  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000fad5  call    cs:__imp_EnterCriticalSection
0x14000fadb  mov     rcx, [r15]; Str
0x14000fade  mov     r8d, edi; unsigned int
0x14000fae1  mov     rdx, rsi; void **
0x14000fae4  call    ?GetAccountSIDsFromAccountString@@YAKPEBGPEAPEAXK@Z; GetAccountSIDsFromAccountString(ushort const *,void * *,ulong)
0x14000fae9  mov     r14d, eax
0x14000faec  test    eax, eax
0x14000faee  jz      short loc_14000FB15
0x14000faf0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000faf7  lea     rax, WPP_GLOBAL_Control
0x14000fafe  cmp     rcx, rax
0x14000fb01  jz      short loc_14000FB69
0x14000fb03  test    byte ptr [rcx+1Ch], 4
0x14000fb07  jz      short loc_14000FB69
0x14000fb09  cmp     [rcx+19h], bl
0x14000fb0c  jb      short loc_14000FB69
0x14000fb0e  mov     edx, 99h
0x14000fb13  jmp     short loc_14000FB56
0x14000fb15  mov     r9, rsi; void **
0x14000fb18  mov     dword ptr [rsp+290h+var_270], edi; unsigned int
0x14000fb1c  mov     r8, r15; struct _FAX_REASSIGN_INFO *
0x14000fb1f  lea     rcx, [rsp+290h+FileName]; lpFileName
0x14000fb24  mov     rdx, r12; unsigned __int64
0x14000fb27  call    ?ReAssignMessage@@YAKPEBG_KPEAU_FAX_REASSIGN_INFO@@PEAPEAXK@Z; ReAssignMessage(ushort const *,unsigned __int64,_FAX_REASSIGN_INFO *,void * *,ulong)
0x14000fb2c  mov     r14d, eax
0x14000fb2f  test    eax, eax
0x14000fb31  jz      short loc_14000FB69
0x14000fb33  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fb3a  lea     rax, WPP_GLOBAL_Control
0x14000fb41  cmp     rcx, rax
0x14000fb44  jz      short loc_14000FB69
0x14000fb46  test    byte ptr [rcx+1Ch], 4
0x14000fb4a  jz      short loc_14000FB69
0x14000fb4c  cmp     [rcx+19h], bl
0x14000fb4f  jb      short loc_14000FB69
0x14000fb51  mov     edx, 9Ah
0x14000fb56  mov     rcx, [rcx+10h]
0x14000fb5a  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000fb61  mov     r9d, r14d
0x14000fb64  call    WPP_SF_d
0x14000fb69  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000fb70  call    cs:__imp_LeaveCriticalSection
0x14000fb76  mov     ebx, r13d
0x14000fb79  test    edi, edi
0x14000fb7b  jz      short loc_14000FB8E
0x14000fb7d  mov     ecx, ebx
0x14000fb7f  mov     rcx, [rsi+rcx*8]; lpMem
0x14000fb83  call    pMemFree
0x14000fb88  inc     ebx
0x14000fb8a  cmp     ebx, edi
0x14000fb8c  jb      short loc_14000FB7D
0x14000fb8e  mov     rcx, rsi; lpMem
0x14000fb91  call    pMemFree
0x14000fb96  mov     eax, r14d
0x14000fb99  jmp     loc_14000FC6F
0x14000fb9e  lea     rax, WPP_GLOBAL_Control
0x14000fba5  cmp     r10, rax
  ... truncated ...
```
