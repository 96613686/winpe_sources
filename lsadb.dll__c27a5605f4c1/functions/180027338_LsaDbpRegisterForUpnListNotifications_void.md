# LsaDbpRegisterForUpnListNotifications(void)

- ea: `0x180027338`
- end: `0x18002760c`
- name: `?LsaDbpRegisterForUpnListNotifications@@YAJXZ`
- size: `724`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009b24`

## callees

- `0x180001670`
- `0x180001fb8`
- `0x18000fd18`
- `0x18000fd40`
- `0x180011d6c`
- `0x18001f5c0`
- `0x18001fbcc`
- `0x180027338`

## import_xrefs

- `LSASRV!LsapAllocateLsaHeap` at `0x18002744c`
- `LSASRV!LsapAllocateLsaHeap` at `0x18002744c`
- `LSASRV!LsapFreeLsaHeap` at `0x1800275e8`
- `LSASRV!LsapFreeLsaHeap` at `0x1800275e8`
- `NTDSA!DirNotifyRegister` at `0x180027559`
- `NTDSA!DirNotifyRegister` at `0x180027559`
- `NTDSA!THClearErrors` at `0x180027569`
- `NTDSA!THClearErrors` at `0x180027569`
- `NTDSA!InitCommarg` at `0x18002750e`
- `NTDSA!InitCommarg` at `0x18002750e`
- `NTDSA!GetConfigurationName` at `0x180027442`
- `NTDSA!GetConfigurationName` at `0x18002748c`
- `NTDSA!GetConfigurationName` at `0x180027442`
- `NTDSA!GetConfigurationName` at `0x18002748c`

## pseudocode

```c
__int64 LsaDbpRegisterForUpnListNotifications(void)
{
  int inited; // eax
  unsigned int v1; // ebx
  __int64 LsaHeap; // rax
  __int64 v3; // r8
  __int64 v4; // rdi
  int ConfigurationName; // eax
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  unsigned int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  char v13[4]; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v14; // [rsp+24h] [rbp-DCh] BYREF
  struct _COMMRES *v15; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v16; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v17; // [rsp+40h] [rbp-C0h]
  __int128 v18; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v19; // [rsp+60h] [rbp-A0h]
  _DWORD v20[4]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v21; // [rsp+80h] [rbp-80h]
  _BYTE v22[128]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v23; // [rsp+110h] [rbp+10h] BYREF
  char v24; // [rsp+118h] [rbp+18h]
  int v25; // [rsp+11Ch] [rbp+1Ch]
  _BYTE *v26; // [rsp+120h] [rbp+20h]
  int v27; // [rsp+128h] [rbp+28h]
  __int128 *v28; // [rsp+130h] [rbp+30h]
  __int64 v29; // [rsp+138h] [rbp+38h]
  int v30; // [rsp+140h] [rbp+40h]
  char v31[192]; // [rsp+148h] [rbp+48h] BYREF
  __int64 v32; // [rsp+208h] [rbp+108h]

  v14 = 0;
  memset_0(v22, 0, 0x78u);
  v16 = 0;
  v17 = 0;
  memset_0(&v23, 0, 0x108u);
  v15 = 0;
  v18 = 0;
  v20[0] = 590714;
  v19 = 0;
  v20[2] = 0;
  v21 = 0;
  v13[0] = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 352, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
  inited = LsaDbpDsInitAllocAsNeededEx(50331648, 0, v13);
  v1 = inited;
  if ( inited >= 0 )
  {
    v14 = 0;
    GetConfigurationName(7, &v14, 0);
    LsaHeap = LsapAllocateLsaHeap(v14);
    v4 = LsaHeap;
    if ( !LsaHeap )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 354, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
      v1 = -1073741670;
      goto LABEL_21;
    }
    ConfigurationName = GetConfigurationName(7, &v14, LsaHeap);
    v1 = ConfigurationName;
    if ( ConfigurationName >= 0 )
    {
      v30 &= ~1u;
      *(_QWORD *)&v17 = v20;
      DWORD2(v16) = 1;
      v26 = v22;
      v25 = 1;
      v28 = &v16;
      v22[8] = 73;
      v22[16] = 8;
      LOBYTE(v16) = 76;
      BYTE8(v17) = 84;
      v23 = v4;
      v24 = 0;
      v27 = 0;
      v29 = 0;
      InitCommarg(v31);
      v32 = 0;
      *(_QWORD *)&v18 = LsaDbpNotifyPrepareToImpersonate;
      DWORD2(v19) = 0;
      *((_QWORD *)&v18 + 1) = LsaDbpForestTrustTransmitDataUpnSuffixChange;
      *(_QWORD *)&v19 = LsaDbpNotifyStopImpersonating;
      v9 = DirNotifyRegister(&v23, &v18, &v15);
      if ( v15 )
      {
        v1 = LsaDbpDsMapDsReturnToStatusEx(v9, v15);
        if ( (v1 & 0x80000000) == 0 )
        {
          v1 = 0;
          UpnSuffixNotificationHandle = *((_DWORD *)v15 + 4);
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 357, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
          goto LABEL_21;
        }
      }
      else
      {
        THClearErrors();
        v1 = -1073741801;
      }
      v6 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v7 = 356;
        v8 = v1;
        goto LABEL_18;
      }
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v7 = 355;
        v8 = (unsigned int)ConfigurationName;
LABEL_18:
        WPP_SF_d(v6[2], v7, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids, v8);
      }
    }
LABEL_21:
    LOBYTE(v3) = v13[0];
    LsaDbpDsDeleteAllocAsNeededEx(50331648, 0, v3);
    LsapFreeLsaHeap(v4, v10, v11);
    return v1;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      353,
      &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids,
      (unsigned int)inited);
  return v1;
}

```

## disassembly

```asm
0x180027338  push    rbp
0x18002733a  push    rbx
0x18002733b  push    rdi
0x18002733c  push    r15
0x18002733e  lea     rbp, [rsp-138h]
0x180027346  sub     rsp, 238h
0x18002734d  mov     rax, cs:__security_cookie
0x180027354  xor     rax, rsp
0x180027357  mov     [rbp+150h+var_30], rax
0x18002735e  xor     edx, edx; Val
0x180027360  mov     [rsp+250h+var_22C], 0
0x180027368  lea     rcx, [rbp+150h+var_1C0]; void *
0x18002736c  lea     r8d, [rdx+78h]; Size
0x180027370  call    memset_0
0x180027375  xorps   xmm0, xmm0
0x180027378  lea     rcx, [rbp+150h+var_140]; void *
0x18002737c  xor     edx, edx; Val
0x18002737e  mov     r8d, 108h; Size
0x180027384  movups  [rsp+250h+var_220], xmm0
0x180027389  movups  [rsp+250h+var_210], xmm0
0x18002738e  call    memset_0
0x180027393  xorps   xmm0, xmm0
0x180027396  mov     [rsp+250h+var_228], 0
0x18002739f  movups  [rsp+250h+var_200], xmm0
0x1800273a4  mov     [rsp+250h+var_1E0], 9037Ah
0x1800273ac  movups  [rsp+250h+var_1F0], xmm0
0x1800273b1  mov     [rsp+250h+var_1D8], 0
0x1800273b9  mov     [rbp+150h+var_1D0], 0
0x1800273c1  mov     [rsp+250h+var_230], 0
0x1800273c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800273cd  lea     r15, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x1800273d4  test    byte ptr [rcx+1Ch], 8
0x1800273d8  jz      short loc_1800273EB
0x1800273da  mov     rcx, [rcx+10h]
0x1800273de  mov     edx, 160h
0x1800273e3  mov     r8, r15
0x1800273e6  call    WPP_SF_
0x1800273eb  lea     r8, [rsp+250h+var_230]
0x1800273f0  xor     edx, edx
0x1800273f2  mov     ecx, 3000000h
0x1800273f7  call    ?LsaDbpDsInitAllocAsNeededEx@@YAJKW4_LSAP_DB_OBJECT_TYPE_ID@@PEAE@Z; LsaDbpDsInitAllocAsNeededEx(ulong,_LSAP_DB_OBJECT_TYPE_ID,uchar *)
0x1800273fc  mov     ebx, eax
0x1800273fe  test    eax, eax
0x180027400  jns     short loc_18002742C
0x180027402  mov     rcx, cs:WPP_GLOBAL_Control
0x180027409  test    byte ptr [rcx+1Ch], 8
0x18002740d  jz      loc_1800275EE
0x180027413  mov     rcx, [rcx+10h]
0x180027417  mov     edx, 161h
0x18002741c  mov     r9d, eax
0x18002741f  mov     r8, r15
0x180027422  call    WPP_SF_d
0x180027427  jmp     loc_1800275EE
0x18002742c  xor     r8d, r8d
0x18002742f  mov     [rsp+250h+var_22C], 0
0x180027437  lea     rdx, [rsp+250h+var_22C]
0x18002743c  lea     ebx, [r8+7]
0x180027440  mov     ecx, ebx
0x180027442  call    cs:__imp_GetConfigurationName
0x180027448  mov     ecx, [rsp+250h+var_22C]
0x18002744c  call    cs:__imp_LsapAllocateLsaHeap
0x180027452  mov     rdi, rax
0x180027455  test    rax, rax
0x180027458  jnz     short loc_180027482
0x18002745a  mov     rcx, cs:WPP_GLOBAL_Control
0x180027461  test    byte ptr [rcx+1Ch], 8
0x180027465  jz      short loc_180027478
0x180027467  mov     rcx, [rcx+10h]
0x18002746b  mov     edx, 162h
0x180027470  mov     r8, r15
0x180027473  call    WPP_SF_
0x180027478  mov     ebx, 0C000009Ah
0x18002747d  jmp     loc_1800275D4
0x180027482  mov     r8, rdi
0x180027485  lea     rdx, [rsp+250h+var_22C]
0x18002748a  mov     ecx, ebx
0x18002748c  call    cs:__imp_GetConfigurationName
0x180027492  mov     ebx, eax
0x180027494  test    eax, eax
0x180027496  jns     short loc_1800274B6
0x180027498  mov     rcx, cs:WPP_GLOBAL_Control
0x18002749f  test    byte ptr [rcx+1Ch], 8
0x1800274a3  jz      loc_1800275D4
0x1800274a9  mov     edx, 163h
0x1800274ae  mov     r9d, eax
0x1800274b1  jmp     loc_180027598
0x1800274b6  and     [rbp+150h+var_110], 0FFFFFFFEh
0x1800274ba  lea     rax, [rsp+250h+var_1E0]
0x1800274bf  mov     qword ptr [rsp+250h+var_210], rax
0x1800274c4  mov     ecx, 1
0x1800274c9  lea     rax, [rbp+150h+var_1C0]
0x1800274cd  mov     dword ptr [rsp+250h+var_220+8], ecx
0x1800274d1  mov     [rbp+150h+var_130], rax
0x1800274d5  lea     rax, [rsp+250h+var_220]
0x1800274da  mov     [rbp+150h+var_134], ecx
0x1800274dd  lea     rcx, [rbp+150h+var_108]
0x1800274e1  mov     [rbp+150h+var_120], rax
0x1800274e5  mov     [rbp+150h+var_1B8], 49h ; 'I'
0x1800274e9  mov     [rbp+150h+var_1B0], 8
0x1800274ed  mov     byte ptr [rsp+250h+var_220], 4Ch ; 'L'
0x1800274f2  mov     byte ptr [rsp+250h+var_210+8], 54h ; 'T'
0x1800274f7  mov     [rbp+150h+var_140], rdi
0x1800274fb  mov     [rbp+150h+var_138], 0
0x1800274ff  mov     [rbp+150h+var_128], 0
0x180027506  mov     [rbp+150h+var_118], 0
0x18002750e  call    cs:__imp_InitCommarg
0x180027514  lea     rax, ?LsaDbpNotifyPrepareToImpersonate@@YAHKKPEAPEAX@Z; LsaDbpNotifyPrepareToImpersonate(ulong,ulong,void * *)
0x18002751b  mov     [rbp+150h+var_48], 0
0x180027526  mov     qword ptr [rsp+250h+var_200], rax
0x18002752b  lea     r8, [rsp+250h+var_228]
0x180027530  lea     rax, ?LsaDbpForestTrustTransmitDataUpnSuffixChange@@YAXKKPEAU_ENTINF@@@Z; LsaDbpForestTrustTransmitDataUpnSuffixChange(ulong,ulong,_ENTINF *)
0x180027537  mov     dword ptr [rsp+250h+var_1F0+8], 0
0x18002753f  mov     qword ptr [rsp+250h+var_200+8], rax
0x180027544  lea     rdx, [rsp+250h+var_200]
0x180027549  lea     rax, ?LsaDbpNotifyStopImpersonating@@YAXKKPEAX@Z; LsaDbpNotifyStopImpersonating(ulong,ulong,void *)
0x180027550  lea     rcx, [rbp+150h+var_140]
0x180027554  mov     qword ptr [rsp+250h+var_1F0], rax
0x180027559  call    cs:__imp_DirNotifyRegister
0x18002755f  mov     rdx, [rsp+250h+var_228]; struct _COMMRES *
0x180027564  test    rdx, rdx
0x180027567  jnz     short loc_180027576
0x180027569  call    cs:__imp_THClearErrors
0x18002756f  mov     ebx, 0C0000017h
0x180027574  jmp     short loc_180027583
0x180027576  mov     ecx, eax; unsigned int
0x180027578  call    ?LsaDbpDsMapDsReturnToStatusEx@@YAJKPEAU_COMMRES@@@Z; LsaDbpDsMapDsReturnToStatusEx(ulong,_COMMRES *)
0x18002757d  mov     ebx, eax
0x18002757f  test    eax, eax
0x180027581  jns     short loc_1800275A6
0x180027583  mov     rcx, cs:WPP_GLOBAL_Control
0x18002758a  test    byte ptr [rcx+1Ch], 8
0x18002758e  jz      short loc_1800275D4
0x180027590  mov     edx, 164h
0x180027595  mov     r9d, ebx
0x180027598  mov     rcx, [rcx+10h]
0x18002759c  mov     r8, r15
0x18002759f  call    WPP_SF_d
0x1800275a4  jmp     short loc_1800275D4
0x1800275a6  mov     rax, [rsp+250h+var_228]
0x1800275ab  xor     ebx, ebx
0x1800275ad  mov     ecx, [rax+10h]
0x1800275b0  mov     cs:?UpnSuffixNotificationHandle@@3KA, ecx; ulong UpnSuffixNotificationHandle
0x1800275b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800275bd  test    byte ptr [rcx+1Ch], 8
0x1800275c1  jz      short loc_1800275D4
0x1800275c3  mov     rcx, [rcx+10h]
0x1800275c7  mov     edx, 165h
0x1800275cc  mov     r8, r15
0x1800275cf  call    WPP_SF_
0x1800275d4  mov     r8b, [rsp+250h+var_230]
0x1800275d9  xor     edx, edx
0x1800275db  mov     ecx, 3000000h
0x1800275e0  call    ?LsaDbpDsDeleteAllocAsNeededEx@@YAXKW4_LSAP_DB_OBJECT_TYPE_ID@@E@Z; LsaDbpDsDeleteAllocAsNeededEx(ulong,_LSAP_DB_OBJECT_TYPE_ID,uchar)
0x1800275e5  mov     rcx, rdi
0x1800275e8  call    cs:__imp_LsapFreeLsaHeap
0x1800275ee  mov     eax, ebx
0x1800275f0  mov     rcx, [rbp+150h+var_30]
0x1800275f7  xor     rcx, rsp; StackCookie
0x1800275fa  call    __security_check_cookie
0x1800275ff  add     rsp, 238h
0x180027606  pop     r15
0x180027608  pop     rdi
0x180027609  pop     rbx
0x18002760a  pop     rbp
0x18002760b  retn
```
