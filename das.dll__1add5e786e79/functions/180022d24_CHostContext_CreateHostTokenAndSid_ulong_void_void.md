# CHostContext::CreateHostTokenAndSid(ulong,void * *,void * *)

- ea: `0x180022d24`
- end: `0x1800233b1`
- name: `?CreateHostTokenAndSid@CHostContext@@IEAAJKPEAPEAX0@Z`
- size: `1677`
- prototype: `__int64 __fastcall(CHostContext *this, int, void **, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180022624`

## callees

- `0x180007500`
- `0x1800153e0`
- `0x1800186ac`
- `0x18001a760`
- `0x180022d24`
- `0x18003bc80`
- `0x18003c79c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023010`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023378`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023010`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023378`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023386`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023386`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002301f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002301f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023158`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800231e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800232f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023158`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800231e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800232f1`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180023343`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180023343`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180023114`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180023114`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180023145`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180023145`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002323f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002323f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800231d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800231d3`
- `SspiCli!LogonUserExExW` at `0x1800232e7`
- `SspiCli!LogonUserExExW` at `0x1800232e7`

## string_xrefs

- `0x180022da4`: `NetworkService`
- `0x180022d7c`: `LocalService`

## pseudocode

```c
__int64 __fastcall CHostContext::CreateHostTokenAndSid(CHostContext *this, int a2, void **a3, void **a4)
{
  unsigned __int64 v5; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int *v7; // rax
  int v8; // edx
  int v9; // r8d
  unsigned int *v10; // rdi
  unsigned int v11; // ebx
  unsigned int i; // r12d
  __int64 v13; // r9
  __int64 v14; // rbx
  void *v15; // rcx
  int v16; // edx
  int v17; // r8d
  char v18; // al
  int v19; // edx
  int v20; // r8d
  signed int LastError; // eax
  unsigned int j; // ebx
  int v23; // edx
  int v24; // r8d
  __int64 v25; // rax
  signed int v26; // eax
  int v27; // edx
  int v28; // r8d
  unsigned int k; // esi
  void *v30; // rcx
  int v31; // edx
  int v32; // r8d
  HANDLE v33; // rax
  LPWSTR StringSid; // [rsp+68h] [rbp-98h] BYREF
  void **v37; // [rsp+70h] [rbp-90h]
  void **v38; // [rsp+78h] [rbp-88h]
  _QWORD v39[3]; // [rsp+80h] [rbp-80h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+98h] [rbp-68h] BYREF
  _OWORD v41[4]; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD v42[6]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v43[96]; // [rsp+140h] [rbp+40h] BYREF
  __int128 v44; // [rsp+1A0h] [rbp+A0h]
  __int128 v45; // [rsp+1B0h] [rbp+B0h]
  __int128 v46; // [rsp+1C0h] [rbp+C0h]
  __int128 v47; // [rsp+1D0h] [rbp+D0h]
  _OWORD v48[5]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v49[30]; // [rsp+230h] [rbp+130h]
  _BYTE v50[82]; // [rsp+24Eh] [rbp+14Eh] BYREF
  __int128 v51; // [rsp+2A0h] [rbp+1A0h]
  __int128 v52; // [rsp+2B0h] [rbp+1B0h]
  __int128 v53; // [rsp+2C0h] [rbp+1C0h]
  __int128 v54; // [rsp+2D0h] [rbp+1D0h]
  _OWORD v55[5]; // [rsp+2E0h] [rbp+1E0h] BYREF
  _BYTE v56[28]; // [rsp+330h] [rbp+230h]
  _BYTE v57[84]; // [rsp+34Ch] [rbp+24Ch] BYREF
  __int128 v58; // [rsp+3A0h] [rbp+2A0h]
  __int128 v59; // [rsp+3B0h] [rbp+2B0h]
  __int128 v60; // [rsp+3C0h] [rbp+2C0h]
  __int128 v61; // [rsp+3D0h] [rbp+2D0h]
  _OWORD v62[6]; // [rsp+3E0h] [rbp+2E0h] BYREF
  int v63; // [rsp+440h] [rbp+340h]
  _BYTE v64[92]; // [rsp+444h] [rbp+344h] BYREF

  v41[0] = *(_OWORD *)L"S-1-5-21-2702878673-795188819-444038987-1031";
  v39[0] = &dword_18008C97C;
  v41[1] = *(_OWORD *)L"-2702878673-795188819-444038987-1031";
  v41[2] = *(_OWORD *)L"673-795188819-444038987-1031";
  v42[0] = *(_OWORD *)L"4038987-1031";
  v39[1] = L"LocalService";
  v41[3] = *(_OWORD *)L"88819-444038987-1031";
  v39[2] = L"NetworkService";
  memset((char *)&v42[2] + 10, 0, 22);
  v38 = a3;
  *(_OWORD *)((char *)&v42[1] + 10) = 0;
  v37 = a4;
  *(_OWORD *)((char *)v42 + 10) = *(_OWORD *)L"87-1031";
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  v42[4] = *(_OWORD *)L"ID_CAP_EVERYONE";
  v42[5] = *(_OWORD *)L"VERYONE";
  memset_0(v43, 0, sizeof(v43));
  v44 = *(_OWORD *)L"S-1-5-21-2702878673-795188819-444038987-1033";
  v46 = *(_OWORD *)L"673-795188819-444038987-1033";
  v48[0] = *(_OWORD *)L"4038987-1033";
  v45 = *(_OWORD *)L"-2702878673-795188819-444038987-1033";
  memset((char *)&v48[2] + 10, 0, 22);
  v47 = *(_OWORD *)L"88819-444038987-1033";
  *(_OWORD *)((char *)&v48[1] + 10) = 0;
  *(_OWORD *)((char *)v48 + 10) = *(_OWORD *)L"87-1033";
  v48[4] = *(_OWORD *)L"ID_CAP_BUILTIN_DEFAULT";
  *(_OWORD *)v49 = *(_OWORD *)L"UILTIN_DEFAULT";
  *(_OWORD *)&v49[14] = *(_OWORD *)L"DEFAULT";
  memset_0(v50, 0, sizeof(v50));
  v51 = *(_OWORD *)L"S-1-5-21-2702878673-795188819-444038987-1447";
  v52 = *(_OWORD *)L"-2702878673-795188819-444038987-1447";
  v53 = *(_OWORD *)L"673-795188819-444038987-1447";
  v55[0] = *(_OWORD *)L"4038987-1447";
  v54 = *(_OWORD *)L"88819-444038987-1447";
  memset((char *)&v55[2] + 10, 0, 22);
  *(_OWORD *)((char *)v55 + 10) = *(_OWORD *)L"87-1447";
  *(_OWORD *)((char *)&v55[1] + 10) = 0;
  v55[4] = *(_OWORD *)L"ID_CAP_EVERYONE_INROM";
  *(_OWORD *)v56 = *(_OWORD *)L"VERYONE_INROM";
  *(_OWORD *)&v56[12] = *(_OWORD *)L"E_INROM";
  memset_0(v57, 0, sizeof(v57));
  v58 = *(_OWORD *)L"S-1-5-21-2702878673-795188819-444038987-1043";
  v59 = *(_OWORD *)L"-2702878673-795188819-444038987-1043";
  v60 = *(_OWORD *)L"673-795188819-444038987-1043";
  v62[0] = *(_OWORD *)L"4038987-1043";
  v61 = *(_OWORD *)L"88819-444038987-1043";
  memset((char *)&v62[2] + 10, 0, 22);
  *(_OWORD *)((char *)&v62[1] + 10) = 0;
  v63 = *(_DWORD *)L"G";
  *(_OWORD *)((char *)v62 + 10) = *(_OWORD *)L"87-1043";
  v62[4] = *(_OWORD *)L"ID_CAP_NETWORKING";
  v62[5] = *(_OWORD *)L"ETWORKING";
  memset_0(v64, 0, sizeof(v64));
  v5 = (*((_QWORD *)this + 8) - *((_QWORD *)this + 7)) & 0xFFFFFFFFFFFFFFF0uLL;
  ProcessHeap = GetProcessHeap();
  v7 = (unsigned int *)HeapAlloc(ProcessHeap, 0, v5 + 88);
  v10 = v7;
  if ( v7 )
  {
    memset_0(v7, 0, ((*((_QWORD *)this + 8) - *((_QWORD *)this + 7)) & 0xFFFFFFFFFFFFFFF0uLL) + 88);
    *v10 = ((__int64)(*((_QWORD *)this + 8) - *((_QWORD *)this + 7)) >> 4) + 4;
    for ( i = 0; ; ++i )
    {
      v13 = *((_QWORD *)this + 7);
      if ( i >= (unsigned __int64)((*((_QWORD *)this + 8) - v13) >> 4) )
        break;
      v14 = 16LL * i;
      if ( !AllocateAndInitializeSid(
              &pIdentifierAuthority,
              6u,
              0x5Cu,
              *(_DWORD *)(*(_QWORD *)(v13 + v14) + 24LL),
              *(_DWORD *)(*(_QWORD *)(v13 + v14) + 28LL),
              *(_DWORD *)(*(_QWORD *)(v13 + v14) + 32LL),
              *(_DWORD *)(*(_QWORD *)(v13 + v14) + 36LL),
              0,
              0,
              0,
              (PSID *)&v10[(unsigned __int64)v14 / 4 + 2]) )
      {
LABEL_16:
        LastError = GetLastError();
        v11 = LastError;
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_30;
      }
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = *(void **)&v10[(unsigned __int64)v14 / 4 + 2];
        StringSid = 0;
        if ( ConvertSidToStringSidW(v15, &StringSid) )
        {
          if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_SS(
              *((_QWORD *)WPP_GLOBAL_Control + 5),
              v16,
              v17,
              28,
              &WPP_061eca0472ca35df833eac72ad0e5963_Traceguids,
              **(_QWORD **)(v14 + *((_QWORD *)this + 7)),
              (__int64)StringSid);
        }
        else if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v18 = GetLastError();
          WPP_RECORDER_SF_D(
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            v19,
            v20,
            27,
            &WPP_061eca0472ca35df833eac72ad0e5963_Traceguids,
            v18);
        }
        if ( StringSid )
          LocalFree(StringSid);
      }
      v10[(unsigned __int64)v14 / 4 + 4] = -1073741809;
    }
    for ( j = 0; j < 4; ++j )
    {
      if ( !ConvertStringSidToSidW(
              (LPCWSTR)&v41[16 * (unsigned __int64)j],
              (PSID *)&v10[4 * j + 2 + 4 * ((__int64)(*((_QWORD *)this + 8) - *((_QWORD *)this + 7)) >> 4)]) )
        goto LABEL_16;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u && *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v23,
          v24,
          29,
          &WPP_061eca0472ca35df833eac72ad0e5963_Traceguids,
          (__int64)&v41[16 * (unsigned __int64)j + 8]);
      v25 = j + ((__int64)(*((_QWORD *)this + 8) - *((_QWORD *)this + 7)) >> 4) + 1;
      v10[4 * v25] = 7;
    }
    v11 = 0;
    if ( !(unsigned int)LogonUserExExW(v39[a2], L"NT AUTHORITY", 0, 5, 0, v10, v38, v37, 0, 0, 0) )
    {
      v26 = GetLastError();
      v11 = v26;
      if ( v26 > 0 )
        v11 = (unsigned __int16)v26 | 0x80070000;
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v27,
          v28,
          30,
          &WPP_061eca0472ca35df833eac72ad0e5963_Traceguids,
          v11);
    }
LABEL_30:
    for ( k = 0; k < *v10; ++k )
    {
      v30 = *(void **)&v10[4 * k + 2];
      if ( v30 && FreeSid(v30) && *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v31,
          v32,
          31,
          &WPP_061eca0472ca35df833eac72ad0e5963_Traceguids);
    }
    v33 = GetProcessHeap();
    HeapFree(v33, 0, v10);
  }
  else
  {
    v11 = -2147024882;
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v8,
        v9,
        26,
        &WPP_061eca0472ca35df833eac72ad0e5963_Traceguids,
        14);
  }
  return v11;
}

```

## disassembly

```asm
0x180022d24  push    rbp
0x180022d26  push    rbx
0x180022d27  push    rsi
0x180022d28  push    rdi
0x180022d29  push    r12
0x180022d2b  push    r13
0x180022d2d  push    r14
0x180022d2f  push    r15
0x180022d31  lea     rbp, [rsp-3B8h]
0x180022d39  sub     rsp, 4B8h
0x180022d40  mov     rax, cs:__security_cookie
0x180022d47  xor     rax, rsp
0x180022d4a  mov     [rbp+3F0h+var_50], rax
0x180022d51  movaps  xmm0, xmmword ptr cs:aS1521270287867_0; "S-1-5-21-2702878673-795188819-444038987"...
0x180022d58  lea     rax, dword_18008C97C
0x180022d5f  movaps  xmm1, xmmword ptr cs:aS1521270287867_0+10h; "-2702878673-795188819-444038987-1031"
0x180022d66  mov     rsi, rcx
0x180022d69  movaps  [rbp+3F0h+var_450], xmm0
0x180022d6d  lea     rcx, [rbp+3F0h+var_3B0]; void *
0x180022d71  movaps  xmm0, xmmword ptr cs:aS1521270287867_0+20h; "673-795188819-444038987-1031"
0x180022d78  mov     [rbp+3F0h+var_470], rax
0x180022d7c  lea     rax, aLocalservice; "LocalService"
0x180022d83  movaps  [rbp+3F0h+var_440], xmm1
0x180022d87  movaps  xmm1, xmmword ptr cs:aS1521270287867_0+30h; "88819-444038987-1031"
0x180022d8e  movaps  [rbp+3F0h+var_430], xmm0
0x180022d92  movaps  xmm0, xmmword ptr cs:aS1521270287867_0+40h; "4038987-1031"
0x180022d99  movaps  xmmword ptr [rbp+3F0h+var_410], xmm0
0x180022d9d  xorps   xmm0, xmm0
0x180022da0  mov     [rbp+3F0h+var_468], rax
0x180022da4  lea     rax, aNetworkservice; "NetworkService"
0x180022dab  movaps  [rbp+3F0h+var_420], xmm1
0x180022daf  movups  xmm1, xmmword ptr cs:aS1521270287867_0+4Ah; "87-1031"
0x180022db6  mov     [rbp+3F0h+var_460], rax
0x180022dba  xor     eax, eax
0x180022dbc  movups  xmmword ptr [rbp+3F0h+var_3E6], xmm0
0x180022dc0  mov     [rsp+4F0h+var_478], r8
0x180022dc5  movups  [rbp+3F0h+var_3F6], xmm0
0x180022dc9  mov     [rsp+4F0h+var_490], edx
0x180022dcd  xor     edx, edx; Val
0x180022dcf  movups  xmm0, xmmword ptr cs:aIdCapEveryone; "ID_CAP_EVERYONE"
0x180022dd6  lea     r8d, [rax+60h]; Size
0x180022dda  mov     [rsp+4F0h+var_480], r9
0x180022ddf  movups  xmmword ptr [rbp+3F0h+var_410+0Ah], xmm1
0x180022de3  mov     dword ptr [rbp+3F0h+pIdentifierAuthority.Value], 0
0x180022dea  movups  xmm1, xmmword ptr cs:aIdCapEveryone+10h; "VERYONE"
0x180022df1  mov     word ptr [rbp+3F0h+pIdentifierAuthority.Value+4], 500h
0x180022df7  movaps  [rbp+3F0h+var_3D0], xmm0
0x180022dfb  mov     qword ptr [rbp+3F0h+var_3E6+0Eh], rax
0x180022dff  movaps  [rbp+3F0h+var_3C0], xmm1
0x180022e03  call    memset_0
0x180022e08  movaps  xmm0, xmmword ptr cs:aS1521270287867; "S-1-5-21-2702878673-795188819-444038987"...
0x180022e0f  lea     rcx, [rbp+3F0h+var_2A2]; void *
0x180022e16  movaps  xmm1, xmmword ptr cs:aS1521270287867+10h; "-2702878673-795188819-444038987-1033"
0x180022e1d  xor     eax, eax
0x180022e1f  movaps  [rbp+3F0h+var_350], xmm0
0x180022e26  xor     edx, edx; Val
0x180022e28  movaps  xmm0, xmmword ptr cs:aS1521270287867+20h; "673-795188819-444038987-1033"
0x180022e2f  movaps  [rbp+3F0h+var_330], xmm0
0x180022e36  movaps  xmm0, xmmword ptr cs:aS1521270287867+40h; "4038987-1033"
0x180022e3d  lea     r8d, [rax+52h]; Size
0x180022e41  movaps  xmmword ptr [rbp+3F0h+var_310], xmm0
0x180022e48  xorps   xmm0, xmm0
0x180022e4b  movaps  [rbp+3F0h+var_340], xmm1
0x180022e52  movaps  xmm1, xmmword ptr cs:aS1521270287867+30h; "88819-444038987-1033"
0x180022e59  movups  xmmword ptr [rbp+3F0h+var_2E6], xmm0
0x180022e60  mov     qword ptr [rbp+3F0h+var_2E6+0Eh], rax
0x180022e67  movaps  [rbp+3F0h+var_320], xmm1
0x180022e6e  movups  xmm1, xmmword ptr cs:aS1521270287867+4Ah; "87-1033"
0x180022e75  movups  [rbp+3F0h+var_2F6], xmm0
0x180022e7c  movups  xmm0, xmmword ptr cs:aIdCapBuiltinDe; "ID_CAP_BUILTIN_DEFAULT"
0x180022e83  movups  xmmword ptr [rbp+3F0h+var_310+0Ah], xmm1
0x180022e8a  movups  xmm1, xmmword ptr cs:aIdCapBuiltinDe+10h; "UILTIN_DEFAULT"
0x180022e91  movaps  [rbp+3F0h+var_2D0], xmm0
0x180022e98  movups  xmm0, xmmword ptr cs:aIdCapBuiltinDe+1Eh; "DEFAULT"
0x180022e9f  movaps  xmmword ptr [rbp+3F0h+var_2C0], xmm1
0x180022ea6  movups  xmmword ptr [rbp+3F0h+var_2C0+0Eh], xmm0
0x180022ead  call    memset_0
0x180022eb2  movaps  xmm0, xmmword ptr cs:aS1521270287867_1; "S-1-5-21-2702878673-795188819-444038987"...
0x180022eb9  xor     eax, eax
0x180022ebb  movaps  xmm1, xmmword ptr cs:aS1521270287867_1+10h; "-2702878673-795188819-444038987-1447"
0x180022ec2  movaps  [rbp+3F0h+var_250], xmm0
0x180022ec9  movaps  xmm0, xmmword ptr cs:aS1521270287867_1+20h; "673-795188819-444038987-1447"
0x180022ed0  movaps  [rbp+3F0h+var_240], xmm1
0x180022ed7  movaps  xmm1, xmmword ptr cs:aS1521270287867_1+30h; "88819-444038987-1447"
0x180022ede  movaps  [rbp+3F0h+var_230], xmm0
0x180022ee5  movaps  xmm0, xmmword ptr cs:aS1521270287867_1+40h; "4038987-1447"
0x180022eec  movaps  xmmword ptr [rbp+3F0h+var_210], xmm0
0x180022ef3  xorps   xmm0, xmm0
0x180022ef6  movaps  [rbp+3F0h+var_220], xmm1
0x180022efd  movups  xmm1, xmmword ptr cs:aS1521270287867_1+4Ah; "87-1447"
0x180022f04  movups  xmmword ptr [rbp+3F0h+var_1E6], xmm0
0x180022f0b  mov     qword ptr [rbp+3F0h+var_1E6+0Eh], rax
0x180022f12  movups  xmmword ptr [rbp+3F0h+var_210+0Ah], xmm1
0x180022f19  movups  [rbp+3F0h+var_1F6], xmm0
0x180022f20  movups  xmm0, xmmword ptr cs:aIdCapEveryoneI; "ID_CAP_EVERYONE_INROM"
0x180022f27  xor     edx, edx; Val
0x180022f29  lea     r8d, [rax+54h]; Size
0x180022f2d  movups  xmm1, xmmword ptr cs:aIdCapEveryoneI+10h; "VERYONE_INROM"
0x180022f34  lea     rcx, [rbp+3F0h+var_1A4]; void *
0x180022f3b  movaps  [rbp+3F0h+var_1D0], xmm0
0x180022f42  movups  xmm0, xmmword ptr cs:aIdCapEveryoneI+1Ch; "E_INROM"
0x180022f49  movaps  xmmword ptr [rbp+3F0h+var_1C0], xmm1
0x180022f50  movups  xmmword ptr [rbp+3F0h+var_1C0+0Ch], xmm0
0x180022f57  call    memset_0
0x180022f5c  movaps  xmm0, xmmword ptr cs:aS1521270287867_2; "S-1-5-21-2702878673-795188819-444038987"...
0x180022f63  lea     rcx, [rbp+3F0h+var_AC]; void *
0x180022f6a  movaps  xmm1, xmmword ptr cs:aS1521270287867_2+10h; "-2702878673-795188819-444038987-1043"
0x180022f71  xor     eax, eax
0x180022f73  movaps  [rbp+3F0h+var_150], xmm0
0x180022f7a  xor     edx, edx; Val
0x180022f7c  movaps  xmm0, xmmword ptr cs:aS1521270287867_2+20h; "673-795188819-444038987-1043"
0x180022f83  movaps  [rbp+3F0h+var_140], xmm1
0x180022f8a  movaps  xmm1, xmmword ptr cs:aS1521270287867_2+30h; "88819-444038987-1043"
0x180022f91  movaps  [rbp+3F0h+var_130], xmm0
0x180022f98  lea     r8d, [rdx+5Ch]; Size
0x180022f9c  movaps  xmm0, xmmword ptr cs:aS1521270287867_2+40h; "4038987-1043"
0x180022fa3  movaps  xmmword ptr [rbp+3F0h+var_110], xmm0
0x180022faa  xorps   xmm0, xmm0
0x180022fad  movaps  [rbp+3F0h+var_120], xmm1
0x180022fb4  movups  xmm1, xmmword ptr cs:aS1521270287867_2+4Ah; "87-1043"
0x180022fbb  movups  xmmword ptr [rbp+3F0h+var_E6], xmm0
0x180022fc2  mov     qword ptr [rbp+3F0h+var_E6+0Eh], rax
0x180022fc9  mov     eax, dword ptr cs:aIdCapNetworkin+20h; "G"
0x180022fcf  movups  [rbp+3F0h+var_F6], xmm0
0x180022fd6  mov     [rbp+3F0h+var_B0], eax
0x180022fdc  movups  xmm0, xmmword ptr cs:aIdCapNetworkin; "ID_CAP_NETWORKING"
0x180022fe3  movups  xmmword ptr [rbp+3F0h+var_110+0Ah], xmm1
0x180022fea  movups  xmm1, xmmword ptr cs:aIdCapNetworkin+10h; "ETWORKING"
0x180022ff1  movaps  [rbp+3F0h+var_D0], xmm0
0x180022ff8  movaps  [rbp+3F0h+var_C0], xmm1
0x180022fff  call    memset_0
0x180023004  mov     rbx, [rsi+40h]
0x180023008  sub     rbx, [rsi+38h]
0x18002300c  and     rbx, 0FFFFFFFFFFFFFFF0h
0x180023010  call    cs:__imp_GetProcessHeap
0x180023016  lea     r8, [rbx+58h]; dwBytes
0x18002301a  xor     edx, edx; dwFlags
0x18002301c  mov     rcx, rax; hHeap
0x18002301f  call    cs:__imp_HeapAlloc
0x180023025  mov     rdi, rax
0x180023028  test    rax, rax
0x18002302b  jnz     short loc_180023073
0x18002302d  mov     ebx, 8007000Eh
0x180023032  lea     r14, WPP_RECORDER_INITIALIZED
0x180023039  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180023040  jz      loc_18002338C
0x180023046  mov     rcx, cs:WPP_GLOBAL_Control
0x18002304d  lea     r15, WPP_061eca0472ca35df833eac72ad0e5963_Traceguids
0x180023054  lea     r9d, [rax+1Ah]; int
0x180023058  mov     [rsp+4F0h+nSubAuthority3], 8007000Eh; char
0x180023060  mov     qword ptr [rsp+4F0h+nSubAuthority2], r15; MessageGuid
0x180023065  mov     rcx, [rcx+28h]; int
0x180023069  call    WPP_RECORDER_SF_D
0x18002306e  jmp     loc_18002338C
0x180023073  mov     r8, [rsi+40h]
0x180023077  xor     edx, edx; Val
0x180023079  sub     r8, [rsi+38h]
0x18002307d  mov     rcx, rdi; void *
0x180023080  and     r8, 0FFFFFFFFFFFFFFF0h
0x180023084  add     r8, 58h ; 'X'; Size
0x180023088  call    memset_0
0x18002308d  mov     rax, [rsi+40h]
0x180023091  lea     r14, WPP_RECORDER_INITIALIZED
0x180023098  sub     rax, [rsi+38h]
0x18002309c  lea     r15, WPP_061eca0472ca35df833eac72ad0e5963_Traceguids
0x1800230a3  sar     rax, 4
0x1800230a7  add     eax, 4
0x1800230aa  mov     [rdi], eax
0x1800230ac  xor     r12d, r12d
0x1800230af  mov     r9, [rsi+38h]
0x1800230b3  mov     rax, [rsi+40h]
0x1800230b7  sub     rax, r9
0x1800230ba  mov     ebx, r12d
0x1800230bd  sar     rax, 4
0x1800230c1  cmp     rbx, rax
0x1800230c4  jnb     loc_180023207
0x1800230ca  xor     eax, eax
0x1800230cc  shl     rbx, 4
0x1800230d0  lea     r13, [rdi+8]
0x1800230d4  mov     r8d, 5Ch ; '\'; nSubAuthority0
0x1800230da  add     r13, rbx
0x1800230dd  lea     rcx, [rbp+3F0h+pIdentifierAuthority]; pIdentifierAuthority
0x1800230e1  mov     [rsp+4F0h+pSid], r13; pSid
0x1800230e6  mov     dl, 6; nSubAuthorityCount
0x1800230e8  mov     r9, [r9+rbx]
0x1800230ec  mov     [rsp+4F0h+nSubAuthority7], eax; nSubAuthority7
0x1800230f0  mov     [rsp+4F0h+nSubAuthority6], eax; nSubAuthority6
0x1800230f4  mov     [rsp+4F0h+nSubAuthority5], eax; nSubAuthority5
0x1800230f8  mov     eax, [r9+24h]
0x1800230fc  mov     [rsp+4F0h+nSubAuthority4], eax; nSubAuthority4
0x180023100  mov     eax, [r9+20h]
0x180023104  mov     [rsp+4F0h+nSubAuthority3], eax; nSubAuthority3
0x180023108  mov     eax, [r9+1Ch]
0x18002310c  mov     r9d, [r9+18h]; nSubAuthority1
0x180023110  mov     [rsp+4F0h+nSubAuthority2], eax; nSubAuthority2
0x180023114  call    cs:__imp_AllocateAndInitializeSid
0x18002311a  test    eax, eax
0x18002311c  jz      loc_1800231E9
0x180023122  mov     rax, cs:WPP_GLOBAL_Control
0x180023129  cmp     byte ptr [rax+19h], 2
0x18002312d  jb      loc_1800231D9
0x180023133  mov     rcx, [r13+0]; Sid
0x180023137  lea     rdx, [rsp+4F0h+StringSid]; StringSid
0x18002313c  mov     [rsp+4F0h+StringSid], 0
0x180023145  call    cs:__imp_ConvertSidToStringSidW
0x18002314b  test    eax, eax
0x18002314d  jnz     short loc_18002318B
0x18002314f  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180023156  jz      short loc_1800231C9
0x180023158  call    cs:__imp_GetLastError
0x18002315e  test    eax, eax
0x180023160  jle     short loc_18002316A
0x180023162  movzx   eax, ax
0x180023165  or      eax, 80070000h
0x18002316a  mov     rcx, cs:WPP_GLOBAL_Control
0x180023171  mov     r9d, 1Bh; int
0x180023177  mov     [rsp+4F0h+nSubAuthority3], eax; char
0x18002317b  mov     qword ptr [rsp+4F0h+nSubAuthority2], r15; MessageGuid
0x180023180  mov     rcx, [rcx+28h]; int
0x180023184  call    WPP_RECORDER_SF_D
0x180023189  jmp     short loc_1800231C9
0x18002318b  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180023192  jz      short loc_1800231C9
0x180023194  mov     rax, [rsi+38h]
0x180023198  mov     r9d, 1Ch; int
0x18002319e  mov     rcx, [rbx+rax]
0x1800231a2  mov     rax, [rsp+4F0h+StringSid]
0x1800231a7  mov     qword ptr [rsp+4F0h+nSubAuthority4], rax; __int64
0x1800231ac  mov     rax, [rcx]
0x1800231af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800231b6  mov     qword ptr [rsp+4F0h+nSubAuthority3], rax; __int64
0x1800231bb  mov     qword ptr [rsp+4F0h+nSubAuthority2], r15; MessageGuid
0x1800231c0  mov     rcx, [rcx+28h]; int
0x1800231c4  call    WPP_RECORDER_SF_SS
0x1800231c9  mov     rcx, [rsp+4F0h+StringSid]; hMem
0x1800231ce  test    rcx, rcx
0x1800231d1  jz      short loc_1800231D9
0x1800231d3  call    cs:__imp_LocalFree
0x1800231d9  mov     dword ptr [rbx+rdi+10h], 0C000000Fh
0x1800231e1  inc     r12d
0x1800231e4  jmp     loc_1800230AF
0x1800231e9  call    cs:__imp_GetLastError
0x1800231ef  mov     ebx, eax
0x1800231f1  test    eax, eax
0x1800231f3  jle     loc_18002332E
0x1800231f9  movzx   ebx, ax
0x1800231fc  or      ebx, 80070000h
0x180023202  jmp     loc_18002332E
0x180023207  xor     ebx, ebx
0x180023209  cmp     ebx, 4
0x18002320c  jnb     loc_1800232A2
0x180023212  mov     rdx, [rsi+40h]
0x180023216  lea     r13, [rbp+3F0h+var_450]
0x18002321a  sub     rdx, [rsi+38h]
0x18002321e  sar     rdx, 4
0x180023222  mov     r12d, ebx
0x180023225  add     rdx, r12
0x180023228  mov     eax, ebx
0x18002322a  shl     rdx, 4
0x18002322e  shl     rax, 8
0x180023232  add     rdx, 8
0x180023236  add     r13, rax
0x180023239  add     rdx, rdi; Sid
0x18002323c  mov     rcx, r13; StringSid
0x18002323f  call    cs:__imp_ConvertStringSidToSidW
0x180023245  test    eax, eax
0x180023247  jz      short loc_1800231E9
0x180023249  mov     rcx, cs:WPP_GLOBAL_Control
0x180023250  cmp     byte ptr [rcx+19h], 2
0x180023254  jb      short loc_18002327F
0x180023256  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18002325d  jz      short loc_18002327F
0x18002325f  mov     rcx, [rcx+28h]; int
0x180023263  lea     rax, [r13+80h]
0x18002326a  mov     qword ptr [rsp+4F0h+nSubAuthority3], rax; __int64
0x18002326f  mov     r9d, 1Dh; int
0x180023275  mov     qword ptr [rsp+4F0h+nSubAuthority2], r15; MessageGuid
0x18002327a  call    WPP_RECORDER_SF_S
0x18002327f  mov     rax, [rsi+40h]
0x180023283  sub     rax, [rsi+38h]
0x180023287  sar     rax, 4
0x18002328b  inc     rax
0x18002328e  add     rax, r12
0x180023291  add     rax, rax
0x180023294  inc     ebx
0x180023296  mov     dword ptr [rdi+rax*8], 7
0x18002329d  jmp     loc_180023209
0x1800232a2  mov     rax, [rsp+4F0h+var_480]
0x1800232a7  lea     rdx, aNtAuthority; "NT AUTHORITY"
0x1800232ae  mov     ecx, [rsp+4F0h+var_490]
0x1800232b2  xor     ebx, ebx
0x1800232b4  mov     [rsp+4F0h+pSid], rbx
0x1800232b9  xor     r8d, r8d
0x1800232bc  mov     qword ptr [rsp+4F0h+nSubAuthority7], rbx
0x1800232c1  mov     qword ptr [rsp+4F0h+nSubAuthority6], rbx
0x1800232c6  mov     rcx, [rbp+rcx*8+3F0h+var_470]
0x1800232cb  lea     r9d, [rbx+5]
0x1800232cf  mov     qword ptr [rsp+4F0h+nSubAuthority5], rax
0x1800232d4  mov     rax, [rsp+4F0h+var_478]
0x1800232d9  mov     qword ptr [rsp+4F0h+nSubAuthority4], rax
  ... truncated ...
```
