# DpspGetScenarioInstancesForUser(__TARGETUSER *,uchar * *,_DPS_MESSAGE *,ulong *,ulong *,_GUID *)

- ea: `0x180012e2c`
- end: `0x1800130a1`
- name: `?DpspGetScenarioInstancesForUser@@YAJPEAU__TARGETUSER@@PEAPEAEPEAU_DPS_MESSAGE@@PEAK3PEAU_GUID@@@Z`
- size: `629`
- prototype: `__int64 __fastcall(struct __TARGETUSER *, unsigned __int8 **, struct _DPS_MESSAGE *, unsigned int *, unsigned int *, struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800149dc`

## callees

- `0x180008dc0`
- `0x180009090`
- `0x180012e2c`
- `0x180013a10`
- `0x1800142f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013052`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013052`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012e6e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012e6e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180012fcd`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180012fcd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180012ee8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180012ee8`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180012f86`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180012f86`

## pseudocode

```c
__int64 __fastcall DpspGetScenarioInstancesForUser(
        struct __TARGETUSER *a1,
        unsigned __int8 **a2,
        struct _DPS_MESSAGE *a3,
        unsigned int *a4,
        unsigned int *a5,
        struct _GUID *a6)
{
  int v10; // r8d
  int v11; // edi
  unsigned int *v12; // r12
  __int64 *v13; // rsi
  int v14; // edx
  struct _GUID *v15; // rcx
  int Args; // eax
  int v17; // eax
  BOOL v18; // eax
  unsigned int v20; // [rsp+30h] [rbp-58h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-50h] BYREF
  __int64 *v22; // [rsp+40h] [rbp-48h]
  int v23; // [rsp+90h] [rbp+8h] BYREF
  struct _DPS_MESSAGE *v24; // [rsp+A0h] [rbp+18h]

  v24 = a3;
  v20 = 0;
  SystemTimeAsFileTime = 0;
  if ( !a1 )
  {
    v11 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
      (int)L"DpspGetScenarioInstancesForUser",
      1071,
      (int)L"Error = %d",
      87);
    return (unsigned int)v11;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 16));
  if ( a3 )
  {
    if ( a2 )
    {
      if ( a4 )
      {
        v12 = a5;
        if ( a5 )
        {
          v11 = 0;
          v13 = (__int64 *)*((_QWORD *)a1 + 9);
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          while ( v13 != (__int64 *)((char *)a1 + 72) && *a4 < 0x14 )
          {
            v14 = 0;
            v22 = (__int64 *)*v13;
            v23 = 0;
            if ( !*a4 )
              goto LABEL_22;
            while ( 1 )
            {
              v15 = &a6[v14];
              if ( *(_QWORD *)&v15->Data1 == v13[5] && *(_QWORD *)v15->Data4 == v13[6] )
                break;
              if ( ++v14 >= *a4 )
                goto LABEL_22;
            }
            Args = DpspRemoveInstanceFromUser(a1, (struct _GUID *)(v13 + 3), &v23);
            v11 = Args;
            if ( Args < 0 )
            {
              WdipTraceError(
                (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
                (int)L"DpspGetScenarioInstancesForUser",
                1101,
                (int)L"Error = %d",
                Args);
              goto LABEL_35;
            }
            if ( !*((_DWORD *)a1 + 22) )
              goto LABEL_35;
            if ( !v23 )
            {
LABEL_22:
              if ( (*((_BYTE *)v13 + 92) & 0x20) == 0
                || CompareFileTime((const FILETIME *)v13 + 15, &SystemTimeAsFileTime) > 0 )
              {
                goto LABEL_27;
              }
              v17 = DpspRemoveInstanceFromUser(a1, (struct _GUID *)(v13 + 3), &v23);
              v11 = v17;
              if ( v17 < 0 )
              {
                WdipTraceError(
                  (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
                  (int)L"DpspGetScenarioInstancesForUser",
                  1126,
                  (int)L"Error = %d",
                  v17);
                goto LABEL_35;
              }
              if ( !*((_DWORD *)a1 + 22) )
                goto LABEL_35;
              if ( !v23 )
              {
LABEL_27:
                v18 = EqualSid(g_pAdminSid, *((PSID *)a1 + 8));
                v11 = DpspWriteScenarioInstanceToMessageBuffer((struct INSTANCEINFO *)v13, v24, a2, &v20, v18);
                if ( v11 < 0 )
                {
                  v11 = 0;
                  goto LABEL_35;
                }
                WdipCopyGuid(&a6[*a4], v13 + 5);
                ++*a4;
                *v12 += v20;
              }
            }
            v13 = v22;
          }
          goto LABEL_35;
        }
        v10 = 1075;
      }
      else
      {
        v10 = 1074;
      }
    }
    else
    {
      v10 = 1073;
    }
  }
  else
  {
    v10 = 1072;
  }
  v11 = -2147024809;
  WdipTraceError(
    (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
    (int)L"DpspGetScenarioInstancesForUser",
    v10,
    (int)L"Error = %d",
    87);
LABEL_35:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 16));
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180012e2c  mov     rax, rsp
0x180012e2f  mov     [rax+10h], rbx
0x180012e33  mov     [rax+18h], r8
0x180012e37  push    rbp
0x180012e38  push    rsi
0x180012e39  push    rdi
0x180012e3a  push    r12
0x180012e3c  push    r13
0x180012e3e  push    r14
0x180012e40  push    r15
0x180012e42  sub     rsp, 50h
0x180012e46  mov     dword ptr [rax-58h], 0
0x180012e4d  mov     r14, r9
0x180012e50  mov     qword ptr [rax-50h], 0
0x180012e58  mov     rdi, r8
0x180012e5b  mov     r13, rdx
0x180012e5e  mov     rbp, rcx
0x180012e61  test    rcx, rcx
0x180012e64  jz      loc_18001305A
0x180012e6a  add     rcx, 10h; lpCriticalSection
0x180012e6e  call    cs:__imp_EnterCriticalSection
0x180012e74  test    rdi, rdi
0x180012e77  jnz     short loc_180012EAB
0x180012e79  mov     r8d, 430h; int
0x180012e7f  mov     dword ptr [rsp+88h+Args], 57h ; 'W'; Args
0x180012e87  mov     edi, 80070057h
0x180012e8c  lea     r9, aErrorD; "Error = %d"
0x180012e93  lea     rdx, aDpspgetscenari; "DpspGetScenarioInstancesForUser"
0x180012e9a  lea     rcx, aClientcoreBase_2; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180012ea1  call    WdipTraceError
0x180012ea6  jmp     loc_18001304E
0x180012eab  test    r13, r13
0x180012eae  jnz     short loc_180012EB8
0x180012eb0  mov     r8d, 431h
0x180012eb6  jmp     short loc_180012E7F
0x180012eb8  test    r14, r14
0x180012ebb  jnz     short loc_180012EC5
0x180012ebd  mov     r8d, 432h
0x180012ec3  jmp     short loc_180012E7F
0x180012ec5  mov     r12, [rsp+88h+arg_20]
0x180012ecd  test    r12, r12
0x180012ed0  jnz     short loc_180012EDA
0x180012ed2  mov     r8d, 433h
0x180012ed8  jmp     short loc_180012E7F
0x180012eda  lea     r15, [rbp+48h]
0x180012ede  xor     edi, edi
0x180012ee0  mov     rsi, [r15]
0x180012ee3  lea     rcx, [rsp+88h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180012ee8  call    cs:__imp_GetSystemTimeAsFileTime
0x180012eee  jmp     loc_18001301D
0x180012ef3  cmp     dword ptr [r14], 14h
0x180012ef7  jnb     loc_18001304E
0x180012efd  mov     rax, [rsi]
0x180012f00  xor     edx, edx
0x180012f02  mov     [rsp+88h+var_48], rax
0x180012f07  mov     [rsp+88h+arg_0], 0
0x180012f12  cmp     [r14], edx
0x180012f15  jbe     short loc_180012F77
0x180012f17  mov     ecx, edx
0x180012f19  shl     rcx, 4
0x180012f1d  add     rcx, [rsp+88h+arg_28]
0x180012f25  mov     rax, [rcx]
0x180012f28  cmp     rax, [rsi+28h]
0x180012f2c  jnz     short loc_180012F38
0x180012f2e  mov     rax, [rcx+8]
0x180012f32  cmp     rax, [rsi+30h]
0x180012f36  jz      short loc_180012F41
0x180012f38  inc     edx
0x180012f3a  cmp     edx, [r14]
0x180012f3d  jb      short loc_180012F17
0x180012f3f  jmp     short loc_180012F77
0x180012f41  lea     rdx, [rsi+18h]; struct _GUID *
0x180012f45  mov     rcx, rbp; struct __TARGETUSER *
0x180012f48  lea     r8, [rsp+88h+arg_0]; int *
0x180012f50  call    ?DpspRemoveInstanceFromUser@@YAJPEAU__TARGETUSER@@PEAU_GUID@@PEAH@Z; DpspRemoveInstanceFromUser(__TARGETUSER *,_GUID *,int *)
0x180012f55  mov     edi, eax
0x180012f57  test    eax, eax
0x180012f59  js      loc_180013028
0x180012f5f  cmp     dword ptr [rbp+58h], 0
0x180012f63  jz      loc_18001304E
0x180012f69  cmp     [rsp+88h+arg_0], 0
0x180012f71  jnz     loc_180013018
0x180012f77  test    byte ptr [rsi+5Ch], 20h
0x180012f7b  jz      short loc_180012FC2
0x180012f7d  lea     rcx, [rsi+78h]; lpFileTime1
0x180012f81  lea     rdx, [rsp+88h+SystemTimeAsFileTime]; lpFileTime2
0x180012f86  call    cs:__imp_CompareFileTime
0x180012f8c  test    eax, eax
0x180012f8e  jg      short loc_180012FC2
0x180012f90  lea     rdx, [rsi+18h]; struct _GUID *
0x180012f94  mov     rcx, rbp; struct __TARGETUSER *
0x180012f97  lea     r8, [rsp+88h+arg_0]; int *
0x180012f9f  call    ?DpspRemoveInstanceFromUser@@YAJPEAU__TARGETUSER@@PEAU_GUID@@PEAH@Z; DpspRemoveInstanceFromUser(__TARGETUSER *,_GUID *,int *)
0x180012fa4  mov     edi, eax
0x180012fa6  test    eax, eax
0x180012fa8  js      loc_18001303A
0x180012fae  cmp     dword ptr [rbp+58h], 0
0x180012fb2  jz      loc_18001304E
0x180012fb8  cmp     [rsp+88h+arg_0], 0
0x180012fc0  jnz     short loc_180013018
0x180012fc2  mov     rdx, [rbp+40h]; pSid2
0x180012fc6  mov     rcx, cs:g_pAdminSid; pSid1
0x180012fcd  call    cs:__imp_EqualSid
0x180012fd3  mov     rdx, [rsp+88h+arg_10]; struct _DPS_MESSAGE *
0x180012fdb  lea     r9, [rsp+88h+var_58]; unsigned int *
0x180012fe0  mov     r8, r13; unsigned __int8 **
0x180012fe3  mov     dword ptr [rsp+88h+Args], eax; int
0x180012fe7  mov     rcx, rsi; struct INSTANCEINFO *
0x180012fea  call    ?DpspWriteScenarioInstanceToMessageBuffer@@YAJPEAUINSTANCEINFO@@PEAU_DPS_MESSAGE@@PEAPEAEPEAKH@Z; DpspWriteScenarioInstanceToMessageBuffer(INSTANCEINFO *,_DPS_MESSAGE *,uchar * *,ulong *,int)
0x180012fef  mov     edi, eax
0x180012ff1  test    eax, eax
0x180012ff3  js      short loc_18001304C
0x180012ff5  mov     ecx, [r14]
0x180012ff8  lea     rdx, [rsi+28h]
0x180012ffc  shl     rcx, 4
0x180013000  add     rcx, [rsp+88h+arg_28]
0x180013008  call    WdipCopyGuid
0x18001300d  inc     dword ptr [r14]
0x180013010  mov     eax, [rsp+88h+var_58]
0x180013014  add     [r12], eax
0x180013018  mov     rsi, [rsp+88h+var_48]
0x18001301d  cmp     rsi, r15
0x180013020  jnz     loc_180012EF3
0x180013026  jmp     short loc_18001304E
0x180013028  movzx   eax, ax
0x18001302b  mov     r8d, 44Dh
0x180013031  mov     dword ptr [rsp+88h+Args], eax
0x180013035  jmp     loc_180012E8C
0x18001303a  movzx   eax, ax
0x18001303d  mov     r8d, 466h
0x180013043  mov     dword ptr [rsp+88h+Args], eax
0x180013047  jmp     loc_180012E8C
0x18001304c  xor     edi, edi
0x18001304e  lea     rcx, [rbp+10h]; lpCriticalSection
0x180013052  call    cs:__imp_LeaveCriticalSection
0x180013058  jmp     short loc_180013087
0x18001305a  lea     r9, aErrorD; "Error = %d"
0x180013061  mov     dword ptr [rsp+88h+Args], 57h ; 'W'; Args
0x180013069  mov     r8d, 42Fh; int
0x18001306f  lea     rdx, aDpspgetscenari; "DpspGetScenarioInstancesForUser"
0x180013076  lea     rcx, aClientcoreBase_2; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18001307d  mov     edi, 80070057h
0x180013082  call    WdipTraceError
0x180013087  mov     rbx, [rsp+88h+arg_8]
0x18001308f  mov     eax, edi
0x180013091  add     rsp, 50h
0x180013095  pop     r15
0x180013097  pop     r14
0x180013099  pop     r13
0x18001309b  pop     r12
0x18001309d  pop     rdi
0x18001309e  pop     rsi
0x18001309f  pop     rbp
0x1800130a0  retn
```
