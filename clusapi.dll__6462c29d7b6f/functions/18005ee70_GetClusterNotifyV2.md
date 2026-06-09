# GetClusterNotifyV2

- ea: `0x18005ee70`
- end: `0x18005f264`
- name: `GetClusterNotifyV2`
- size: `1012`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180002f50`
- `0x180003bfc`
- `0x180025478`
- `0x18005987c`
- `0x18005c960`
- `0x18005ee70`
- `0x18006f910`
- `0x18009e348`
- `0x1800a2e60`
- `0x1800a3118`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18005f091`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18005f0eb`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18005f141`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18005f199`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18005f091`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18005f0eb`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18005f141`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18005f199`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f20a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f20a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005ef54`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005ef8e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005ef54`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005ef8e`

## string_xrefs

- `0x18005f0ab`: `Error copying object id for notifications: 0x%X`
- `0x18005f105`: `Error copying parent id for notifications: 0x%X`
- `0x18005f15b`: `Error copying name for notifications: 0x%X`
- `0x18005f1b3`: `Error copying type for notifications: 0x%X`

## pseudocode

```c
DWORD __fastcall GetClusterNotifyV2(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        void *a4,
        unsigned int *a5,
        __int64 a6,
        unsigned int *a7,
        __int64 a8,
        unsigned int *a9,
        __int64 a10,
        unsigned int *a11,
        __int64 a12,
        unsigned int *a13,
        unsigned int a14)
{
  DWORD result; // eax
  ULONGLONG TickCount64; // rbx
  __int64 v17; // rax
  __int64 v18; // rdx
  unsigned __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rbx
  __int64 v22; // rdx
  __int64 EntryHash; // rax
  unsigned int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  __int64 v29; // [rsp+28h] [rbp-D8h]
  ULONGLONG v31; // [rsp+68h] [rbp-98h]
  __int64 v34; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v35[10]; // [rsp+A0h] [rbp-60h] BYREF

  if ( !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCHANGE *>(
                           a1,
                           a1) )
    return 6;
  v35[6] = a6;
  v35[7] = a7;
  v35[8] = a8;
  v35[9] = a9;
  v35[0] = a4;
  v35[1] = a5;
  v35[2] = a10;
  v35[3] = a11;
  v35[4] = a12;
  v35[5] = a13;
  TickCount64 = GetTickCount64();
  v31 = TickCount64;
  if ( *(_DWORD *)(a1 + 776) != 2 )
    return 87;
  v17 = a1 + 56;
  while ( 1 )
  {
    if ( a14 == -1 )
    {
      v18 = 0xFFFFFFFFLL;
    }
    else
    {
      v19 = GetTickCount64() - TickCount64;
      v18 = a14 <= v19 ? 0LL : a14 - (unsigned int)v19;
      v17 = a1 + 56;
    }
    v20 = ClRtlRemoveHeadQueueTimeout(v17, v18, GetClusterNotifyCallbackV2, v35);
    v21 = v20;
    if ( !v20 )
      break;
    v22 = *(unsigned int *)(v20 + 20);
    v34 = v20;
    EntryHash = ClRtlGetEntryHash(a1 + 136, v22);
    if ( EntryHash )
    {
      *(_DWORD *)(EntryHash + 56) = *(_DWORD *)(v21 + 28);
      *a2 = *(_QWORD *)(EntryHash + 48);
      if ( a3 )
      {
        *(_DWORD *)a3 = *(_DWORD *)(v21 + 48);
        *(_QWORD *)(a3 + 8) = *(_QWORD *)(v21 + 56);
      }
      if ( a4 )
      {
        if ( a5 )
        {
          v24 = *(_DWORD *)(v21 + 72);
          if ( *a5 >= v24 )
          {
            memcpy_0(a4, *(const void **)(v21 + 64), v24);
            *a5 = *(_DWORD *)(v21 + 72);
          }
        }
      }
      if ( a6 )
      {
        v25 = _o_wcscpy_s(a6, *a7, *(_QWORD *)(v21 + 80));
        if ( v25 )
          TraceMsg(
            4u,
            7u,
            (__int64)L"GetClusterNotifyV2",
            4168,
            L"Error copying object id for notifications: 0x%X",
            v25);
        MylstrlenW(*(const wchar_t **)(v21 + 80), 0x7FFFFFFFu, a7);
      }
      if ( a8 )
      {
        v26 = _o_wcscpy_s(a8, *a9, *(_QWORD *)(v21 + 88));
        if ( v26 )
        {
          LODWORD(v29) = v26;
          TraceMsg(
            4u,
            7u,
            (__int64)L"GetClusterNotifyV2",
            4178,
            L"Error copying parent id for notifications: 0x%X",
            v29);
        }
        MylstrlenW(*(const wchar_t **)(v21 + 88), 0x7FFFFFFFu, a9);
      }
      if ( a10 && a11 )
      {
        v27 = _o_wcscpy_s(a10, *a11, *(_QWORD *)(v21 + 96));
        if ( v27 )
        {
          LODWORD(v29) = v27;
          TraceMsg(4u, 7u, (__int64)L"GetClusterNotifyV2", 4188, L"Error copying name for notifications: 0x%X", v29);
        }
        MylstrlenW(*(const wchar_t **)(v21 + 96), 0x7FFFFFFFu, a11);
      }
      if ( a12 && a13 )
      {
        v28 = _o_wcscpy_s(a12, *a13, *(_QWORD *)(v21 + 104));
        if ( v28 )
        {
          LODWORD(v29) = v28;
          TraceMsg(4u, 7u, (__int64)L"GetClusterNotifyV2", 4198, L"Error copying type for notifications: 0x%X", v29);
        }
        MylstrlenW(*(const wchar_t **)(v21 + 104), 0x7FFFFFFFu, a13);
      }
      if ( *(_DWORD *)(v21 + 116) )
        ClRtlRemoveEntryHash((LPCRITICAL_SECTION)(a1 + 136));
      FreePacket(&v34, *(unsigned int *)(a1 + 776), 0);
      return 0;
    }
    TraceMsg(4u, 7u, (__int64)L"GetClusterNotifyV2", 4138, L"Received notification for non-existent event, retrying..");
    v17 = a1 + 56;
    TickCount64 = v31;
  }
  result = GetLastError();
  if ( !a4 && a5 && result == 234 || !a10 && a11 && result == 234 || !a12 && a13 && result == 234 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x18005ee70  push    rbp
0x18005ee72  push    rbx
0x18005ee73  push    rsi
0x18005ee74  push    rdi
0x18005ee75  push    r12
0x18005ee77  push    r13
0x18005ee79  push    r14
0x18005ee7b  push    r15
0x18005ee7d  lea     rbp, [rsp-8]
0x18005ee82  sub     rsp, 108h
0x18005ee89  mov     rax, cs:__security_cookie
0x18005ee90  xor     rax, rsp
0x18005ee93  mov     [rbp+40h+var_50], rax
0x18005ee97  mov     rax, [rbp+40h+arg_28]
0x18005ee9b  mov     rsi, r9
0x18005ee9e  mov     rbx, [rbp+40h+arg_58]
0x18005eea5  mov     rdi, [rbp+40h+arg_20]
0x18005eea9  mov     r13, [rbp+40h+arg_48]
0x18005eeb0  mov     r14, [rbp+40h+arg_50]
0x18005eeb7  mov     r15, [rbp+40h+arg_60]
0x18005eebe  mov     r12d, [rbp+40h+arg_68]
0x18005eec5  mov     [rsp+140h+var_100], rax
0x18005eeca  mov     rax, [rbp+40h+arg_30]
0x18005eed1  mov     [rsp+140h+var_F8], rax
0x18005eed6  mov     rax, [rbp+40h+arg_38]
0x18005eedd  mov     [rsp+140h+var_F0], rax
0x18005eee2  mov     rax, [rbp+40h+arg_40]
0x18005eee9  mov     [rsp+140h+var_D0], rdx
0x18005eeee  mov     rdx, rcx
0x18005eef1  mov     [rsp+140h+var_E8], rax
0x18005eef6  mov     [rsp+140h+var_C8], r8
0x18005eefb  mov     [rsp+140h+var_110], rcx
0x18005ef00  mov     [rsp+140h+var_E0], rbx
0x18005ef05  call    ??$Contains@PEAU_HCHANGE@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCHANGE@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCHANGE *>(_HCHANGE *)
0x18005ef0a  test    al, al
0x18005ef0c  jnz     short loc_18005EF18
0x18005ef0e  mov     eax, 6
0x18005ef13  jmp     loc_18005F244
0x18005ef18  mov     rax, [rsp+140h+var_100]
0x18005ef1d  mov     [rbp+40h+var_70], rax
0x18005ef21  mov     rax, [rsp+140h+var_F8]
0x18005ef26  mov     [rbp+40h+var_68], rax
0x18005ef2a  mov     rax, [rsp+140h+var_F0]
0x18005ef2f  mov     [rbp+40h+var_60], rax
0x18005ef33  mov     rax, [rsp+140h+var_E8]
0x18005ef38  mov     [rbp+40h+var_58], rax
0x18005ef3c  mov     [rbp+40h+var_A0], rsi
0x18005ef40  mov     [rbp+40h+var_98], rdi
0x18005ef44  mov     [rbp+40h+var_90], r13
0x18005ef48  mov     [rbp+40h+var_88], r14
0x18005ef4c  mov     [rbp+40h+var_80], rbx
0x18005ef50  mov     [rbp+40h+var_78], r15
0x18005ef54  call    cs:__imp_GetTickCount64
0x18005ef5a  mov     rbx, rax
0x18005ef5d  mov     [rsp+140h+var_D8], rax
0x18005ef62  mov     rax, [rsp+140h+var_110]
0x18005ef67  cmp     dword ptr [rax+308h], 2
0x18005ef6e  jz      short loc_18005EF7A
0x18005ef70  mov     eax, 57h ; 'W'
0x18005ef75  jmp     loc_18005F244
0x18005ef7a  add     rax, 38h ; '8'
0x18005ef7e  mov     [rsp+140h+var_108], rax
0x18005ef83  cmp     r12d, 0FFFFFFFFh
0x18005ef87  jnz     short loc_18005EF8E
0x18005ef89  mov     edx, r12d
0x18005ef8c  jmp     short loc_18005EFAA
0x18005ef8e  call    cs:__imp_GetTickCount64
0x18005ef94  sub     rax, rbx
0x18005ef97  cmp     r12, rax
0x18005ef9a  jbe     short loc_18005EFA3
0x18005ef9c  mov     edx, r12d
0x18005ef9f  sub     edx, eax
0x18005efa1  jmp     short loc_18005EFA5
0x18005efa3  xor     edx, edx
0x18005efa5  mov     rax, [rsp+140h+var_108]
0x18005efaa  lea     r9, [rbp+40h+var_A0]
0x18005efae  mov     rcx, rax
0x18005efb1  lea     r8, ?GetClusterNotifyCallbackV2@@YAKPEAU_LIST_ENTRY@@PEAX@Z; GetClusterNotifyCallbackV2(_LIST_ENTRY *,void *)
0x18005efb8  call    ClRtlRemoveHeadQueueTimeout
0x18005efbd  mov     rbx, rax
0x18005efc0  test    rax, rax
0x18005efc3  jz      loc_18005F20A
0x18005efc9  mov     edx, [rbx+14h]
0x18005efcc  mov     [rbp+40h+var_B0], rax
0x18005efd0  mov     rax, [rsp+140h+var_110]
0x18005efd5  add     rax, 88h
0x18005efdb  mov     rcx, rax
0x18005efde  mov     [rbp+40h+lpCriticalSection], rax
0x18005efe2  call    ClRtlGetEntryHash
0x18005efe7  mov     [rbp+40h+var_C0], rax
0x18005efeb  mov     rcx, rax
0x18005efee  test    rax, rax
0x18005eff1  jnz     short loc_18005F026
0x18005eff3  lea     edx, [rcx+7]
0x18005eff6  mov     r9d, 102Ah
0x18005effc  lea     rax, aReceivedNotifi; "Received notification for non-existent "...
0x18005f003  lea     ecx, [rdx-3]
0x18005f006  mov     [rsp+140h+var_120], rax
0x18005f00b  lea     r8, aGetclusternoti_2; "GetClusterNotifyV2"
0x18005f012  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005f017  mov     rax, [rsp+140h+var_108]
0x18005f01c  mov     rbx, [rsp+140h+var_D8]
0x18005f021  jmp     loc_18005EF83
0x18005f026  mov     eax, [rbx+1Ch]
0x18005f029  mov     [rcx+38h], eax
0x18005f02c  mov     rax, [rcx+30h]
0x18005f030  mov     rcx, [rsp+140h+var_D0]
0x18005f035  mov     [rcx], rax
0x18005f038  mov     rcx, [rsp+140h+var_C8]
0x18005f03d  test    rcx, rcx
0x18005f040  jz      short loc_18005F04F
0x18005f042  mov     eax, [rbx+30h]
0x18005f045  mov     [rcx], eax
0x18005f047  mov     rax, [rbx+38h]
0x18005f04b  mov     [rcx+8], rax
0x18005f04f  test    rsi, rsi
0x18005f052  jz      short loc_18005F074
0x18005f054  test    rdi, rdi
0x18005f057  jz      short loc_18005F074
0x18005f059  mov     eax, [rbx+48h]
0x18005f05c  cmp     [rdi], eax
0x18005f05e  jb      short loc_18005F074
0x18005f060  mov     rdx, [rbx+40h]; Src
0x18005f064  mov     r8d, eax; Size
0x18005f067  mov     rcx, rsi; void *
0x18005f06a  call    memcpy_0
0x18005f06f  mov     eax, [rbx+48h]
0x18005f072  mov     [rdi], eax
0x18005f074  mov     rax, [rsp+140h+var_100]
0x18005f079  mov     esi, 7FFFFFFFh
0x18005f07e  test    rax, rax
0x18005f081  jz      short loc_18005F0D3
0x18005f083  mov     rdi, [rsp+140h+var_F8]
0x18005f088  mov     rcx, rax
0x18005f08b  mov     r8, [rbx+50h]
0x18005f08f  mov     edx, [rdi]
0x18005f091  call    cs:__imp__o_wcscpy_s
0x18005f097  test    eax, eax
0x18005f099  jz      short loc_18005F0C5
0x18005f09b  mov     dword ptr [rsp+140h+var_118], eax
0x18005f09f  lea     r8, aGetclusternoti_2; "GetClusterNotifyV2"
0x18005f0a6  mov     edx, 7
0x18005f0ab  lea     rax, aErrorCopyingOb; "Error copying object id for notificatio"...
0x18005f0b2  mov     r9d, 1048h
0x18005f0b8  mov     [rsp+140h+var_120], rax
0x18005f0bd  lea     ecx, [rdx-3]
0x18005f0c0  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005f0c5  mov     rcx, [rbx+50h]; wchar_t *
0x18005f0c9  mov     r8, rdi; unsigned int *
0x18005f0cc  mov     edx, esi; unsigned int
0x18005f0ce  call    ?MylstrlenW@@YAKPEB_WKPEAK@Z; MylstrlenW(wchar_t const *,ulong,ulong *)
0x18005f0d3  mov     rax, [rsp+140h+var_F0]
0x18005f0d8  test    rax, rax
0x18005f0db  jz      short loc_18005F12D
0x18005f0dd  mov     rdi, [rsp+140h+var_E8]
0x18005f0e2  mov     rcx, rax
0x18005f0e5  mov     r8, [rbx+58h]
0x18005f0e9  mov     edx, [rdi]
0x18005f0eb  call    cs:__imp__o_wcscpy_s
0x18005f0f1  test    eax, eax
0x18005f0f3  jz      short loc_18005F11F
0x18005f0f5  mov     dword ptr [rsp+140h+var_118], eax
0x18005f0f9  lea     r8, aGetclusternoti_2; "GetClusterNotifyV2"
0x18005f100  mov     edx, 7
0x18005f105  lea     rax, aErrorCopyingPa; "Error copying parent id for notificatio"...
0x18005f10c  mov     r9d, 1052h
0x18005f112  mov     [rsp+140h+var_120], rax
0x18005f117  lea     ecx, [rdx-3]
0x18005f11a  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005f11f  mov     rcx, [rbx+58h]; wchar_t *
0x18005f123  mov     r8, rdi; unsigned int *
0x18005f126  mov     edx, esi; unsigned int
0x18005f128  call    ?MylstrlenW@@YAKPEB_WKPEAK@Z; MylstrlenW(wchar_t const *,ulong,ulong *)
0x18005f12d  test    r13, r13
0x18005f130  jz      short loc_18005F183
0x18005f132  test    r14, r14
0x18005f135  jz      short loc_18005F183
0x18005f137  mov     edx, [r14]
0x18005f13a  mov     rcx, r13
0x18005f13d  mov     r8, [rbx+60h]
0x18005f141  call    cs:__imp__o_wcscpy_s
0x18005f147  test    eax, eax
0x18005f149  jz      short loc_18005F175
0x18005f14b  mov     dword ptr [rsp+140h+var_118], eax
0x18005f14f  lea     r8, aGetclusternoti_2; "GetClusterNotifyV2"
0x18005f156  mov     edx, 7
0x18005f15b  lea     rax, aErrorCopyingNa; "Error copying name for notifications: 0"...
0x18005f162  mov     r9d, 105Ch
0x18005f168  mov     [rsp+140h+var_120], rax
0x18005f16d  lea     ecx, [rdx-3]
0x18005f170  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005f175  mov     rcx, [rbx+60h]; wchar_t *
0x18005f179  mov     r8, r14; unsigned int *
0x18005f17c  mov     edx, esi; unsigned int
0x18005f17e  call    ?MylstrlenW@@YAKPEB_WKPEAK@Z; MylstrlenW(wchar_t const *,ulong,ulong *)
0x18005f183  mov     rcx, [rsp+140h+var_E0]
0x18005f188  test    rcx, rcx
0x18005f18b  jz      short loc_18005F1DB
0x18005f18d  test    r15, r15
0x18005f190  jz      short loc_18005F1DB
0x18005f192  mov     edx, [r15]
0x18005f195  mov     r8, [rbx+68h]
0x18005f199  call    cs:__imp__o_wcscpy_s
0x18005f19f  test    eax, eax
0x18005f1a1  jz      short loc_18005F1CD
0x18005f1a3  mov     dword ptr [rsp+140h+var_118], eax
0x18005f1a7  lea     r8, aGetclusternoti_2; "GetClusterNotifyV2"
0x18005f1ae  mov     edx, 7
0x18005f1b3  lea     rax, aErrorCopyingTy; "Error copying type for notifications: 0"...
0x18005f1ba  mov     r9d, 1066h
0x18005f1c0  mov     [rsp+140h+var_120], rax
0x18005f1c5  lea     ecx, [rdx-3]
0x18005f1c8  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005f1cd  mov     rcx, [rbx+68h]; wchar_t *
0x18005f1d1  mov     r8, r15; unsigned int *
0x18005f1d4  mov     edx, esi; unsigned int
0x18005f1d6  call    ?MylstrlenW@@YAKPEB_WKPEAK@Z; MylstrlenW(wchar_t const *,ulong,ulong *)
0x18005f1db  cmp     dword ptr [rbx+74h], 0
0x18005f1df  jz      short loc_18005F1F1
0x18005f1e1  mov     rdx, [rbp+40h+var_C0]
0x18005f1e5  mov     rcx, [rbp+40h+lpCriticalSection]; lpCriticalSection
0x18005f1e9  mov     edx, [rdx+3Ch]
0x18005f1ec  call    ClRtlRemoveEntryHash
0x18005f1f1  mov     rax, [rsp+140h+var_110]
0x18005f1f6  lea     rcx, [rbp+40h+var_B0]
0x18005f1fa  xor     r8d, r8d
0x18005f1fd  mov     edx, [rax+308h]
0x18005f203  call    ?FreePacket@@YAKAEAPEAU_CNOTIFY_PACKET@@W4CLUSTER_NOTIFICATIONS_VERSION@@_N@Z; FreePacket(_CNOTIFY_PACKET * &,CLUSTER_NOTIFICATIONS_VERSION,bool)
0x18005f208  jmp     short loc_18005F242
0x18005f20a  call    cs:__imp_GetLastError
0x18005f210  mov     edx, 0EAh
0x18005f215  test    rsi, rsi
0x18005f218  jnz     short loc_18005F223
0x18005f21a  test    rdi, rdi
0x18005f21d  jz      short loc_18005F223
0x18005f21f  cmp     eax, edx
0x18005f221  jz      short loc_18005F242
0x18005f223  test    r13, r13
0x18005f226  jnz     short loc_18005F231
0x18005f228  test    r14, r14
0x18005f22b  jz      short loc_18005F231
0x18005f22d  cmp     eax, edx
0x18005f22f  jz      short loc_18005F242
0x18005f231  cmp     [rsp+140h+var_E0], 0
0x18005f237  jnz     short loc_18005F244
0x18005f239  test    r15, r15
0x18005f23c  jz      short loc_18005F244
0x18005f23e  cmp     eax, edx
0x18005f240  jnz     short loc_18005F244
0x18005f242  xor     eax, eax
0x18005f244  mov     rcx, [rbp+40h+var_50]
0x18005f248  xor     rcx, rsp; StackCookie
0x18005f24b  call    __security_check_cookie
0x18005f250  add     rsp, 108h
0x18005f257  pop     r15
0x18005f259  pop     r14
0x18005f25b  pop     r13
0x18005f25d  pop     r12
0x18005f25f  pop     rdi
0x18005f260  pop     rsi
0x18005f261  pop     rbx
0x18005f262  pop     rbp
0x18005f263  retn
```
