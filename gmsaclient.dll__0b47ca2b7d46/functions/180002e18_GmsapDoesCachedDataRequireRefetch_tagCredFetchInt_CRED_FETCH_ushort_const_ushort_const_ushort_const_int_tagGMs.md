# GmsapDoesCachedDataRequireRefetch(_tagCredFetchInt,_CRED_FETCH,ushort const *,ushort const *,ushort const *,int *,_tagGMsaListEntry * *,int *,int *)

- ea: `0x180002e18`
- end: `0x180003157`
- name: `?GmsapDoesCachedDataRequireRefetch@@YAJW4_tagCredFetchInt@@W4_CRED_FETCH@@PEBG22PEAHPEAPEAU_tagGMsaListEntry@@33@Z`
- size: `831`
- prototype: `int __high(enum _tagCredFetchInt, enum _CRED_FETCH, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int *, struct _tagGMsaListEntry **, int *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800036c0`

## callees

- `0x180002a64`
- `0x180002b18`
- `0x180002e18`
- `0x1800043f0`
- `0x180006280`
- `0x1800062b0`
- `0x1800063cc`
- `0x180007a34`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003064`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800030ac`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003064`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800030ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800030f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003106`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800030f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003106`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003051`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003098`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003051`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003098`
- `ntdll!RtlReleaseResource` at `0x180002f2e`
- `ntdll!RtlReleaseResource` at `0x180002f2e`
- `ntdll!RtlAcquireResourceExclusive` at `0x180002f43`
- `ntdll!RtlAcquireResourceExclusive` at `0x180002f43`

## pseudocode

```c
__int64 __fastcall GmsapDoesCachedDataRequireRefetch(
        int a1,
        int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        _DWORD *a6,
        struct _tagGMsaListEntry **a7,
        struct _FILETIME SystemTimeAsFileTime,
        _DWORD *a9)
{
  unsigned int v11; // esi
  HLOCAL v12; // rbx
  HLOCAL v13; // rdi
  _DWORD *v14; // r12
  int v15; // eax
  int CachedLSASecret; // eax
  int v17; // r15d
  _DWORD *v18; // rax
  struct _tagGMsaListEntry *v19; // rax
  const FILETIME *v20; // r15
  struct _tagGMsaListEntry *v21; // r14
  HLOCAL v23; // [rsp+30h] [rbp-10h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-8h] BYREF

  v11 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_70b8577d707437755865c965214ce19a_Traceguids);
  v12 = 0;
  v13 = 0;
  v14 = (_DWORD *)SystemTimeAsFileTime;
  v23 = 0;
  *a9 = 0;
  hMem = 0;
  *v14 = 1;
  *a6 = 0;
  if ( !*a7 )
  {
    GmsapCheckGMSAInList(a3, a4, a5, a7);
    if ( !*a7 )
    {
      v15 = GmsapCrackDomainName(0, 0, a5, 0, (unsigned __int16 **)&v23, (unsigned __int16 **)&hMem);
      v11 = v15;
      if ( v15 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_D(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            57,
            &WPP_70b8577d707437755865c965214ce19a_Traceguids,
            (unsigned int)v15);
        v12 = v23;
        v13 = hMem;
        goto LABEL_32;
      }
      _InterlockedIncrement(&dword_18000B670);
      RtlReleaseResource(&Resource);
      RtlAcquireResourceExclusive(&Resource, 1u);
      _InterlockedDecrement(&dword_18000B670);
      GmsapCheckGMSAInList(a3, a4, a5, a7);
      v12 = v23;
      v13 = hMem;
      if ( !*a7 )
      {
        CachedLSASecret = GmsapLoadCachedLSASecret(
                            (unsigned int)(a1 - 2) > 1,
                            a3,
                            (const unsigned __int16 *)v23,
                            (const unsigned __int16 *)hMem,
                            a7);
        v17 = CachedLSASecret;
        if ( CachedLSASecret < 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_SSD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              58,
              (unsigned int)&WPP_70b8577d707437755865c965214ce19a_Traceguids,
              (_DWORD)a5,
              (__int64)a3,
              CachedLSASecret);
          if ( v17 != -1073741772 )
            v11 = v17;
          SCLockConvertExclusiveToShared();
          goto LABEL_32;
        }
        v18 = a9;
        if ( (unsigned int)(a1 - 2) <= 1 )
          v18 = a6;
        *v18 = 1;
      }
      SCLockConvertExclusiveToShared();
    }
    v14 = (_DWORD *)SystemTimeAsFileTime;
  }
  if ( ((a1 - 1) & 0xFFFFFFFD) != 0 )
  {
    v19 = *a7;
    if ( !*((_DWORD *)*a7 + 24) )
    {
      if ( a2 != 2
        || (SystemTimeAsFileTime = 0,
            v20 = (const FILETIME *)((char *)v19 + 56),
            GetSystemTimeAsFileTime(&SystemTimeAsFileTime),
            CompareFileTime(v20, &SystemTimeAsFileTime) > 0)
        && (unsigned int)((*(_QWORD *)v20 - *(_QWORD *)&SystemTimeAsFileTime) / 0x2710uLL) )
      {
        v21 = *a7;
        SystemTimeAsFileTime = 0;
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        if ( CompareFileTime((const FILETIME *)v21 + 6, &SystemTimeAsFileTime) > 0 )
        {
          if ( (unsigned int)((*((_QWORD *)v21 + 6) - *(_QWORD *)&SystemTimeAsFileTime) / 0x2710uLL) )
            *v14 = 0;
        }
      }
    }
  }
LABEL_32:
  if ( v13 )
    LocalFree(v13);
  if ( v12 )
    LocalFree(v12);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_70b8577d707437755865c965214ce19a_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x180002e18  mov     [rsp-38h+arg_10], rbx
0x180002e1d  mov     [rsp-38h+arg_8], edx
0x180002e21  mov     [rsp-38h+arg_0], ecx
0x180002e25  push    rbp
0x180002e26  push    rsi
0x180002e27  push    rdi
0x180002e28  push    r12
0x180002e2a  push    r13
0x180002e2c  push    r14
0x180002e2e  push    r15
0x180002e30  mov     rbp, rsp
0x180002e33  sub     rsp, 40h
0x180002e37  mov     r15, r9
0x180002e3a  mov     r13, r8
0x180002e3d  xor     esi, esi
0x180002e3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e46  lea     rax, WPP_GLOBAL_Control
0x180002e4d  cmp     rcx, rax
0x180002e50  jz      short loc_180002E6B
0x180002e52  test    byte ptr [rcx+1Ch], 8
0x180002e56  jz      short loc_180002E6B
0x180002e58  mov     rcx, [rcx+10h]
0x180002e5c  lea     edx, [rsi+38h]
0x180002e5f  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180002e66  call    WPP_SF_
0x180002e6b  mov     rax, [rbp+arg_40]
0x180002e72  xor     ebx, ebx
0x180002e74  mov     r14, [rbp+arg_30]
0x180002e78  xor     edi, edi
0x180002e7a  mov     r12, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002e7e  mov     [rbp+var_10], rbx
0x180002e82  mov     [rax], ebx
0x180002e84  mov     rax, [rbp+arg_28]
0x180002e88  mov     [rbp+hMem], rdi
0x180002e8c  mov     dword ptr [r12], 1
0x180002e94  mov     [rax], ebx
0x180002e96  cmp     [r14], rbx
0x180002e99  jnz     loc_180003014
0x180002e9f  mov     r12, [rbp+arg_20]
0x180002ea3  mov     r9, r14; struct _tagGMsaListEntry **
0x180002ea6  mov     r8, r12; unsigned __int16 *
0x180002ea9  mov     rdx, r15; unsigned __int16 *
0x180002eac  mov     rcx, r13; unsigned __int16 *
0x180002eaf  call    ?GmsapCheckGMSAInList@@YAXPEBG00PEAPEAU_tagGMsaListEntry@@@Z; GmsapCheckGMSAInList(ushort const *,ushort const *,ushort const *,_tagGMsaListEntry * *)
0x180002eb4  cmp     [r14], rbx
0x180002eb7  jnz     loc_180003010
0x180002ebd  lea     rax, [rbp+hMem]
0x180002ec1  xor     r9d, r9d; unsigned __int16 **
0x180002ec4  mov     [rsp+40h+var_18], rax; unsigned __int16 **
0x180002ec9  mov     r8, r12; unsigned __int16 *
0x180002ecc  lea     rax, [rbp+var_10]
0x180002ed0  xor     edx, edx; int
0x180002ed2  xor     ecx, ecx; int
0x180002ed4  mov     [rsp+40h+var_20], rax; unsigned __int16 **
0x180002ed9  call    ?GmsapCrackDomainName@@YAJHHPEBGPEAPEAG11@Z; GmsapCrackDomainName(int,int,ushort const *,ushort * *,ushort * *,ushort * *)
0x180002ede  mov     esi, eax
0x180002ee0  test    eax, eax
0x180002ee2  jns     short loc_180002F20
0x180002ee4  mov     rcx, cs:WPP_GLOBAL_Control
0x180002eeb  lea     r14, WPP_GLOBAL_Control
0x180002ef2  cmp     rcx, r14
0x180002ef5  jz      short loc_180002F13
0x180002ef7  test    byte ptr [rcx+1Ch], 4
0x180002efb  jz      short loc_180002F13
0x180002efd  mov     rcx, [rcx+10h]
0x180002f01  lea     edx, [rbx+39h]
0x180002f04  mov     r9d, eax
0x180002f07  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180002f0e  call    WPP_SF_D
0x180002f13  mov     rbx, [rbp+var_10]
0x180002f17  mov     rdi, [rbp+hMem]
0x180002f1b  jmp     loc_1800030EA
0x180002f20  lock inc cs:dword_18000B670
0x180002f27  lea     rcx, Resource; Resource
0x180002f2e  call    cs:__imp_RtlReleaseResource
0x180002f35  nop     dword ptr [rax+rax+00h]
0x180002f3a  mov     dl, 1; Wait
0x180002f3c  lea     rcx, Resource; Resource
0x180002f43  call    cs:__imp_RtlAcquireResourceExclusive
0x180002f4a  nop     dword ptr [rax+rax+00h]
0x180002f4f  lock dec cs:dword_18000B670
0x180002f56  mov     r9, r14; struct _tagGMsaListEntry **
0x180002f59  mov     r8, r12; unsigned __int16 *
0x180002f5c  mov     rdx, r15; unsigned __int16 *
0x180002f5f  mov     rcx, r13; unsigned __int16 *
0x180002f62  call    ?GmsapCheckGMSAInList@@YAXPEBG00PEAPEAU_tagGMsaListEntry@@@Z; GmsapCheckGMSAInList(ushort const *,ushort const *,ushort const *,_tagGMsaListEntry * *)
0x180002f67  cmp     qword ptr [r14], 0
0x180002f6b  mov     rbx, [rbp+var_10]
0x180002f6f  mov     rdi, [rbp+hMem]
0x180002f73  jnz     loc_18000300B
0x180002f79  mov     eax, [rbp+arg_0]
0x180002f7c  xor     ecx, ecx
0x180002f7e  add     eax, 0FFFFFFFEh
0x180002f81  mov     [rsp+40h+var_20], r14; struct _tagGMsaListEntry **
0x180002f86  cmp     eax, 1
0x180002f89  mov     r9, rdi; unsigned __int16 *
0x180002f8c  mov     r8, rbx; unsigned __int16 *
0x180002f8f  mov     rdx, r13; unsigned __int16 *
0x180002f92  setnbe  cl; int
0x180002f95  mov     dword ptr [rbp+arg_30], ecx
0x180002f98  call    ?GmsapLoadCachedLSASecret@@YAJHPEBG00PEAPEAU_tagGMsaListEntry@@@Z; GmsapLoadCachedLSASecret(int,ushort const *,ushort const *,ushort const *,_tagGMsaListEntry * *)
0x180002f9d  mov     r15d, eax
0x180002fa0  test    eax, eax
0x180002fa2  jns     short loc_180002FF4
0x180002fa4  mov     rcx, cs:WPP_GLOBAL_Control
0x180002fab  lea     r14, WPP_GLOBAL_Control
0x180002fb2  cmp     rcx, r14
0x180002fb5  jz      short loc_180002FDE
0x180002fb7  test    byte ptr [rcx+1Ch], 4
0x180002fbb  jz      short loc_180002FDE
0x180002fbd  mov     rcx, [rcx+10h]
0x180002fc1  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180002fc8  mov     dword ptr [rsp+40h+var_18], eax
0x180002fcc  mov     edx, 3Ah ; ':'
0x180002fd1  mov     r9, r12
0x180002fd4  mov     [rsp+40h+var_20], r13
0x180002fd9  call    WPP_SF_SSD
0x180002fde  cmp     r15d, 0C0000034h
0x180002fe5  jz      short loc_180002FEA
0x180002fe7  mov     esi, r15d
0x180002fea  call    SCLockConvertExclusiveToShared
0x180002fef  jmp     loc_1800030EA
0x180002ff4  cmp     dword ptr [rbp+arg_30], 0
0x180002ff8  mov     rax, [rbp+arg_40]
0x180002fff  jnz     short loc_180003005
0x180003001  mov     rax, [rbp+arg_28]
0x180003005  mov     dword ptr [rax], 1
0x18000300b  call    SCLockConvertExclusiveToShared
0x180003010  mov     r12, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003014  mov     eax, [rbp+arg_0]
0x180003017  dec     eax
0x180003019  test    eax, 0FFFFFFFDh
0x18000301e  jz      loc_1800030E3
0x180003024  mov     rax, [r14]
0x180003027  cmp     dword ptr [rax+60h], 0
0x18000302b  jnz     loc_1800030E3
0x180003031  cmp     [rbp+arg_8], 2
0x180003035  mov     r13, 346DC5D63886594Bh
0x18000303f  jnz     short loc_180003089
0x180003041  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003045  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18000304d  lea     r15, [rax+38h]
0x180003051  call    cs:__imp_GetSystemTimeAsFileTime
0x180003058  nop     dword ptr [rax+rax+00h]
0x18000305d  lea     rdx, [rbp+SystemTimeAsFileTime]; lpFileTime2
0x180003061  mov     rcx, r15; lpFileTime1
0x180003064  call    cs:__imp_CompareFileTime
0x18000306b  nop     dword ptr [rax+rax+00h]
0x180003070  test    eax, eax
0x180003072  jle     short loc_1800030E3
0x180003074  mov     rcx, [r15]
0x180003077  mov     rax, r13
0x18000307a  sub     rcx, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000307e  mul     rcx
0x180003081  shr     rdx, 0Bh
0x180003085  test    edx, edx
0x180003087  jz      short loc_1800030E3
0x180003089  mov     r14, [r14]
0x18000308c  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003090  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180003098  call    cs:__imp_GetSystemTimeAsFileTime
0x18000309f  nop     dword ptr [rax+rax+00h]
0x1800030a4  lea     rdx, [rbp+SystemTimeAsFileTime]; lpFileTime2
0x1800030a8  lea     rcx, [r14+30h]; lpFileTime1
0x1800030ac  call    cs:__imp_CompareFileTime
0x1800030b3  nop     dword ptr [rax+rax+00h]
0x1800030b8  test    eax, eax
0x1800030ba  jle     short loc_1800030E3
0x1800030bc  mov     rdx, [r14+30h]
0x1800030c0  mov     rax, r13
0x1800030c3  sub     rdx, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800030c7  mul     rdx
0x1800030ca  shr     rdx, 0Bh
0x1800030ce  lea     r14, WPP_GLOBAL_Control
0x1800030d5  test    edx, edx
0x1800030d7  jz      short loc_1800030EA
0x1800030d9  mov     dword ptr [r12], 0
0x1800030e1  jmp     short loc_1800030EA
0x1800030e3  lea     r14, WPP_GLOBAL_Control
0x1800030ea  test    rdi, rdi
0x1800030ed  jz      short loc_1800030FE
0x1800030ef  mov     rcx, rdi; hMem
0x1800030f2  call    cs:__imp_LocalFree
0x1800030f9  nop     dword ptr [rax+rax+00h]
0x1800030fe  test    rbx, rbx
0x180003101  jz      short loc_180003112
0x180003103  mov     rcx, rbx; hMem
0x180003106  call    cs:__imp_LocalFree
0x18000310d  nop     dword ptr [rax+rax+00h]
0x180003112  mov     rcx, cs:WPP_GLOBAL_Control
0x180003119  cmp     rcx, r14
0x18000311c  jz      short loc_18000313C
0x18000311e  test    byte ptr [rcx+1Ch], 8
0x180003122  jz      short loc_18000313C
0x180003124  mov     rcx, [rcx+10h]
0x180003128  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x18000312f  mov     edx, 3Bh ; ';'
0x180003134  mov     r9d, esi
0x180003137  call    WPP_SF_D
0x18000313c  mov     rbx, [rsp+40h+arg_10]
0x180003144  mov     eax, esi
0x180003146  add     rsp, 40h
0x18000314a  pop     r15
0x18000314c  pop     r14
0x18000314e  pop     r13
0x180003150  pop     r12
0x180003152  pop     rdi
0x180003153  pop     rsi
0x180003154  pop     rbp
0x180003155  retn
```
