# MONITOR_MGR::_CreateBootPersistentMonitors(_DXGK_DISPLAY_SCENARIO_CONTEXT *)

- ea: `0x140188b44`
- end: `0x140188fd8`
- name: `?_CreateBootPersistentMonitors@MONITOR_MGR@@QEAAJPEAU_DXGK_DISPLAY_SCENARIO_CONTEXT@@@Z`
- size: `1172`
- prototype: `__int64 __fastcall(MONITOR_MGR *__hidden this, struct _DXGK_DISPLAY_SCENARIO_CONTEXT *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1402f4270`

## callees

- `0x140009030`
- `0x14000d7d0`
- `0x140037128`
- `0x1400a0100`
- `0x140188b44`
- `0x1401895a8`
- `0x1401e4098`
- `0x1402f4320`
- `0x1402f4604`
- `0x140339ed8`
- `0x14033b9b0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140188fa2`
- `ntoskrnl!ZwClose` at `0x140188fa2`
- `ntoskrnl!RtlInitUnicodeString` at `0x140188dbb`
- `ntoskrnl!RtlInitUnicodeString` at `0x140188dcf`
- `ntoskrnl!RtlInitUnicodeString` at `0x140188dbb`
- `ntoskrnl!RtlInitUnicodeString` at `0x140188dcf`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140188de6`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140188de6`
- `ntoskrnl!ZwEnumerateValueKey` at `0x140188c3a`
- `ntoskrnl!ZwEnumerateValueKey` at `0x140188ce0`
- `ntoskrnl!ZwEnumerateValueKey` at `0x140188c3a`
- `ntoskrnl!ZwEnumerateValueKey` at `0x140188ce0`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x140188f60`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x140188f60`
- `watchdog!WdLogSingleEntry2` at `0x140188c5f`
- `watchdog!WdLogSingleEntry2` at `0x140188ca2`
- `watchdog!WdLogSingleEntry2` at `0x140188d23`
- `watchdog!WdLogSingleEntry2` at `0x140188c5f`
- `watchdog!WdLogSingleEntry2` at `0x140188ca2`
- `watchdog!WdLogSingleEntry2` at `0x140188d23`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x140188b76`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x140188e72`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x140188b76`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x140188e72`
- `watchdog!WdLogSingleEntry0` at `0x140188bc0`
- `watchdog!WdLogSingleEntry0` at `0x140188cfd`
- `watchdog!WdLogSingleEntry0` at `0x140188dfb`
- `watchdog!WdLogSingleEntry0` at `0x140188e52`
- `watchdog!WdLogSingleEntry0` at `0x140188f0a`
- `watchdog!WdLogSingleEntry0` at `0x140188bc0`
- `watchdog!WdLogSingleEntry0` at `0x140188cfd`
- `watchdog!WdLogSingleEntry0` at `0x140188dfb`
- `watchdog!WdLogSingleEntry0` at `0x140188e52`
- `watchdog!WdLogSingleEntry0` at `0x140188f0a`
- `watchdog!WdLogSingleEntry1` at `0x140188d76`
- `watchdog!WdLogSingleEntry1` at `0x140188e32`
- `watchdog!WdLogSingleEntry1` at `0x140188f76`
- `watchdog!WdLogSingleEntry1` at `0x140188d76`
- `watchdog!WdLogSingleEntry1` at `0x140188e32`
- `watchdog!WdLogSingleEntry1` at `0x140188f76`

## pseudocode

```c
__int64 __fastcall MONITOR_MGR::_CreateBootPersistentMonitors(
        MONITOR_MGR *this,
        struct _DXGK_DISPLAY_SCENARIO_CONTEXT *a2)
{
  ULONG v3; // esi
  unsigned int *v4; // rdi
  unsigned int *v5; // rbx
  unsigned int *v6; // r12
  _DWORD *v7; // r15
  NTSTATUS v8; // eax
  __int64 v9; // rcx
  unsigned int v10; // eax
  NTSTATUS v11; // eax
  __int64 v12; // rcx
  unsigned int v13; // r14d
  int IsTargetForceable; // eax
  MONITOR_MGR *v15; // rcx
  __int64 result; // rax
  __int64 v17; // rax
  __int64 v18; // r14
  unsigned int *v19; // r8
  unsigned int *v20; // rdi
  struct DXGMONITOR *v21; // rdx
  int SimulatedMonitor; // esi
  char v23[8]; // [rsp+30h] [rbp-99h] BYREF
  HANDLE KeyHandle; // [rsp+38h] [rbp-91h] BYREF
  ULONG ResultLength; // [rsp+40h] [rbp-89h] BYREF
  _QWORD v26[2]; // [rsp+48h] [rbp-81h] BYREF
  UNICODE_STRING String2; // [rsp+58h] [rbp-71h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-61h] BYREF
  _BYTE v29[16]; // [rsp+78h] [rbp-51h] BYREF
  char KeyValueInformation[12]; // [rsp+88h] [rbp-41h] BYREF
  unsigned int v31; // [rsp+94h] [rbp-35h]
  WCHAR SourceString[32]; // [rsp+A0h] [rbp-29h] BYREF

  v26[0] = a2;
  *(_QWORD *)(WdLogNewEntry5_WdTrace(this) + 24) = this;
  WdLogGlobalForLineNumber = 3691;
  KeyHandle = 0;
  if ( MONITOR_MGR::_OpenPersistencyRegistry(this, 0x20019u, &KeyHandle) >= 0 )
  {
    if ( !KeyHandle )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 3703;
    }
    v3 = -1;
    ResultLength = 0;
    v4 = 0;
    v5 = 0;
    while ( 1 )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          if ( !v4 )
          {
            v4 = (unsigned int *)operator new[](96, 1298626628, 256);
            if ( !v4 )
            {
              WdLogSingleEntry0(6);
              result = 3221225495LL;
              WdLogGlobalForLineNumber = 3754;
              return result;
            }
          }
          ++v3;
          v6 = v4 + 2;
          v4[2] = -1;
          v7 = v4 + 3;
          v8 = ZwEnumerateValueKey(KeyHandle, v3, KeyValueBasicInformation, v4 + 3, 0x4Eu, &ResultLength);
          if ( v8 == -2147483622 )
          {
            v17 = WdLogNewEntry5_WdTrace(v9);
            *(_QWORD *)(v17 + 24) = v3;
            *(_QWORD *)(v17 + 32) = this;
            WdLogGlobalForLineNumber = 3786;
            DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v4);
            if ( v5 )
            {
              v18 = v26[0];
              do
              {
                v19 = v5;
                v20 = v5;
                v5 = *(unsigned int **)v5;
                if ( v19[2] == -1 )
                {
                  if ( RtlDeleteRegistryValue(0x40000000u, (PCWSTR)KeyHandle, (PCWSTR)v19 + 12) < 0 )
                  {
                    WdLogSingleEntry1(2);
                    WdLogGlobalForLineNumber = 3997;
                  }
                }
                else
                {
                  MONITOR_REF_ACCESSOR::MONITOR_REF_ACCESSOR((MONITOR_REF_ACCESSOR *)v26, 0);
                  MONITOR_REF_ACCESSOR::MONITOR_REF_ACCESSOR((MONITOR_REF_ACCESSOR *)v29, v21);
                  SimulatedMonitor = MONITOR_MGR::_HandleCreateSimulatedMonitor(this, v20[2], 2, v29, v26, v18);
                  if ( SimulatedMonitor >= 0 && !v26[1] )
                  {
                    WdLogSingleEntry0(1);
                    WdLogGlobalForLineNumber = 3979;
                  }
                  MONITOR_MGR::_LogMonitorPresentEvent(this, 1073741825, v20[2], (unsigned int)SimulatedMonitor, 0);
                  MONITOR_REF_ACCESSOR::Release((MONITOR_REF_ACCESSOR *)v29);
                  MONITOR_REF_ACCESSOR::Release((MONITOR_REF_ACCESSOR *)v26);
                }
                DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v20);
              }
              while ( v5 );
            }
            ZwClose(KeyHandle);
            return 0;
          }
          if ( v8 >= 0 )
            break;
          WdLogSingleEntry2(3, v3);
          WdLogGlobalForLineNumber = 3802;
        }
        *((_WORD *)v7 + ((unsigned __int64)v4[5] >> 1) + 6) = 0;
        *(_QWORD *)v4 = v5;
        v5 = v4;
        v10 = v4[4];
        v4 = 0;
        if ( v10 == 4 )
          break;
        WdLogSingleEntry2(3, v3);
        WdLogGlobalForLineNumber = 3828;
      }
      v11 = ZwEnumerateValueKey(KeyHandle, v3, KeyValuePartialInformation, KeyValueInformation, 0x13u, &ResultLength);
      if ( v11 == -2147483622 )
        break;
      if ( v11 >= 0 )
      {
        v12 = *((_QWORD *)this + 3);
        v13 = v31;
        v23[0] = 0;
        IsTargetForceable = DmmIsTargetForceable(*(_QWORD *)(v12 + 16), v31, v23, 0);
        if ( IsTargetForceable < 0 )
        {
          if ( IsTargetForceable == -1071774971 )
          {
            WdLogSingleEntry1(3);
            WdLogGlobalForLineNumber = 3894;
          }
        }
        else if ( v23[0] )
        {
          if ( MONITOR_MGR::_PersistencyRegNameFromTargetID(v15, v13, SourceString) >= 0 )
          {
            DestinationString = 0;
            String2 = 0;
            RtlInitUnicodeString(&DestinationString, (PCWSTR)v7 + 6);
            RtlInitUnicodeString(&String2, SourceString);
            if ( RtlCompareUnicodeString(&DestinationString, &String2, 0) )
            {
              WdLogSingleEntry0(3);
              WdLogGlobalForLineNumber = 3934;
            }
            else
            {
              *v6 = v13;
            }
          }
        }
        else
        {
          WdLogSingleEntry1(3);
          WdLogGlobalForLineNumber = 3881;
        }
      }
      else
      {
LABEL_15:
        WdLogSingleEntry2(3, v3);
        WdLogGlobalForLineNumber = 3854;
      }
    }
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 3840;
    goto LABEL_15;
  }
  return 0;
}

```

## disassembly

```asm
0x140188b44  mov     [rsp-8+arg_10], rbx
0x140188b49  push    rbp
0x140188b4a  push    rsi
0x140188b4b  push    rdi
0x140188b4c  push    r12
0x140188b4e  push    r13
0x140188b50  push    r14
0x140188b52  push    r15
0x140188b54  lea     rbp, [rsp-27h]
0x140188b59  sub     rsp, 0F0h
0x140188b60  mov     rax, cs:__security_cookie
0x140188b67  xor     rax, rsp
0x140188b6a  mov     [rbp+57h+var_40], rax
0x140188b6e  mov     [rsp+120h+var_D8], rdx
0x140188b73  mov     r13, rcx
0x140188b76  call    cs:__imp_WdLogNewEntry5_WdTrace
0x140188b7d  nop     dword ptr [rax+rax+00h]
0x140188b82  lea     r8, [rsp+120h+KeyHandle]; void **
0x140188b87  mov     edx, 20019h; unsigned int
0x140188b8c  mov     rcx, r13; this
0x140188b8f  mov     [rax+18h], r13
0x140188b93  mov     cs:WdLogGlobalForLineNumber, 0E6Bh
0x140188b9d  mov     [rsp+120h+KeyHandle], 0
0x140188ba6  call    ?_OpenPersistencyRegistry@MONITOR_MGR@@AEBAJKPEAPEAX@Z; MONITOR_MGR::_OpenPersistencyRegistry(ulong,void * *)
0x140188bab  test    eax, eax
0x140188bad  js      loc_140188FAE
0x140188bb3  cmp     [rsp+120h+KeyHandle], 0
0x140188bb9  jnz     short loc_140188BD6
0x140188bbb  mov     ecx, 1
0x140188bc0  call    cs:__imp_WdLogSingleEntry0
0x140188bc7  nop     dword ptr [rax+rax+00h]
0x140188bcc  mov     cs:WdLogGlobalForLineNumber, 0E77h
0x140188bd6  or      esi, 0FFFFFFFFh
0x140188bd9  mov     [rsp+120h+var_E0], 0
0x140188be1  xor     edi, edi
0x140188be3  xor     ebx, ebx
0x140188be5  test    rdi, rdi
0x140188be8  jnz     short loc_140188C09
0x140188bea  mov     edx, 4D677844h
0x140188bef  lea     ecx, [rdi+60h]
0x140188bf2  mov     r8d, 100h
0x140188bf8  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140188bfd  mov     rdi, rax
0x140188c00  test    rax, rax
0x140188c03  jz      loc_140188E4D
0x140188c09  lea     rax, [rsp+120h+var_E0]
0x140188c0e  inc     esi
0x140188c10  mov     [rsp+120h+ResultLength], rax; ResultLength
0x140188c15  lea     r12, [rdi+8]
0x140188c19  mov     dword ptr [r12], 0FFFFFFFFh
0x140188c21  lea     r15, [rdi+0Ch]
0x140188c25  mov     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x140188c2a  mov     r9, r15; KeyValueInformation
0x140188c2d  xor     r8d, r8d; KeyValueInformationClass
0x140188c30  mov     [rsp+120h+Length], 4Eh ; 'N'; Length
0x140188c38  mov     edx, esi; Index
0x140188c3a  call    cs:__imp_ZwEnumerateValueKey
0x140188c41  nop     dword ptr [rax+rax+00h]
0x140188c46  cmp     eax, 8000001Ah
0x140188c4b  jz      loc_140188E72
0x140188c51  test    eax, eax
0x140188c53  jns     short loc_140188C7A
0x140188c55  movsxd  r8, eax
0x140188c58  mov     ecx, 3
0x140188c5d  mov     edx, esi
0x140188c5f  call    cs:__imp_WdLogSingleEntry2
0x140188c66  nop     dword ptr [rax+rax+00h]
0x140188c6b  mov     cs:WdLogGlobalForLineNumber, 0EDAh
0x140188c75  jmp     loc_140188BE5
0x140188c7a  mov     ecx, [r15+8]
0x140188c7e  xor     eax, eax
0x140188c80  shr     rcx, 1
0x140188c83  mov     [r15+rcx*2+0Ch], ax
0x140188c89  mov     [rdi], rbx
0x140188c8c  mov     rbx, rdi
0x140188c8f  mov     eax, [r15+4]
0x140188c93  xor     edi, edi
0x140188c95  cmp     eax, 4
0x140188c98  jz      short loc_140188CBD
0x140188c9a  mov     r8d, eax
0x140188c9d  mov     edx, esi
0x140188c9f  lea     ecx, [rdi+3]
0x140188ca2  call    cs:__imp_WdLogSingleEntry2
0x140188ca9  nop     dword ptr [rax+rax+00h]
0x140188cae  mov     cs:WdLogGlobalForLineNumber, 0EF4h
0x140188cb8  jmp     loc_140188BE5
0x140188cbd  mov     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x140188cc2  lea     rax, [rsp+120h+var_E0]
0x140188cc7  mov     [rsp+120h+ResultLength], rax; ResultLength
0x140188ccc  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x140188cd0  mov     r8d, 2; KeyValueInformationClass
0x140188cd6  mov     [rsp+120h+Length], 13h; Length
0x140188cde  mov     edx, esi; Index
0x140188ce0  call    cs:__imp_ZwEnumerateValueKey
0x140188ce7  nop     dword ptr [rax+rax+00h]
0x140188cec  movsxd  r14, eax
0x140188cef  cmp     r14d, 8000001Ah
0x140188cf6  jnz     short loc_140188D15
0x140188cf8  mov     ecx, 1
0x140188cfd  call    cs:__imp_WdLogSingleEntry0
0x140188d04  nop     dword ptr [rax+rax+00h]
0x140188d09  mov     cs:WdLogGlobalForLineNumber, 0F00h
0x140188d13  jmp     short loc_140188D19
0x140188d15  test    eax, eax
0x140188d17  jns     short loc_140188D3E
0x140188d19  mov     r8, r14
0x140188d1c  mov     edx, esi
0x140188d1e  mov     ecx, 3
0x140188d23  call    cs:__imp_WdLogSingleEntry2
0x140188d2a  nop     dword ptr [rax+rax+00h]
0x140188d2f  mov     cs:WdLogGlobalForLineNumber, 0F0Eh
0x140188d39  jmp     loc_140188BE5
0x140188d3e  mov     rcx, [r13+18h]
0x140188d42  lea     r8, [rsp+120h+var_F0]
0x140188d47  mov     r14d, [rbp+57h+var_8C]
0x140188d4b  xor     r9d, r9d
0x140188d4e  mov     edx, r14d
0x140188d51  mov     [rsp+120h+var_F0], dil
0x140188d56  mov     rcx, [rcx+10h]
0x140188d5a  call    ?DmmIsTargetForceable@@YAJQEAXIPEAEW4_DMM_VIDPN_MONITOR_TYPE@@@Z; DmmIsTargetForceable(void * const,uint,uchar *,_DMM_VIDPN_MONITOR_TYPE)
0x140188d5f  test    eax, eax
0x140188d61  js      loc_140188E1F
0x140188d67  cmp     [rsp+120h+var_F0], dil
0x140188d6c  jnz     short loc_140188D91
0x140188d6e  mov     edx, r14d
0x140188d71  mov     ecx, 3
0x140188d76  call    cs:__imp_WdLogSingleEntry1
0x140188d7d  nop     dword ptr [rax+rax+00h]
0x140188d82  mov     cs:WdLogGlobalForLineNumber, 0F29h
0x140188d8c  jmp     loc_140188BE5
0x140188d91  lea     r8, [rbp+57h+SourceString]; unsigned __int16 *
0x140188d95  mov     edx, r14d; unsigned int
0x140188d98  call    ?_PersistencyRegNameFromTargetID@MONITOR_MGR@@AEBAJIQEAG@Z; MONITOR_MGR::_PersistencyRegNameFromTargetID(uint,ushort * const)
0x140188d9d  test    eax, eax
0x140188d9f  js      loc_140188BE5
0x140188da5  xorps   xmm0, xmm0
0x140188da8  lea     rdx, [r15+0Ch]; SourceString
0x140188dac  xorps   xmm1, xmm1
0x140188daf  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140188db3  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140188db7  movups  xmmword ptr [rbp+57h+String2.Length], xmm1
0x140188dbb  call    cs:__imp_RtlInitUnicodeString
0x140188dc2  nop     dword ptr [rax+rax+00h]
0x140188dc7  lea     rdx, [rbp+57h+SourceString]; SourceString
0x140188dcb  lea     rcx, [rbp+57h+String2]; DestinationString
0x140188dcf  call    cs:__imp_RtlInitUnicodeString
0x140188dd6  nop     dword ptr [rax+rax+00h]
0x140188ddb  xor     r8d, r8d; CaseInSensitive
0x140188dde  lea     rdx, [rbp+57h+String2]; String2
0x140188de2  lea     rcx, [rbp+57h+DestinationString]; String1
0x140188de6  call    cs:__imp_RtlCompareUnicodeString
0x140188ded  nop     dword ptr [rax+rax+00h]
0x140188df2  test    eax, eax
0x140188df4  jz      short loc_140188E16
0x140188df6  mov     ecx, 3
0x140188dfb  call    cs:__imp_WdLogSingleEntry0
0x140188e02  nop     dword ptr [rax+rax+00h]
0x140188e07  mov     cs:WdLogGlobalForLineNumber, 0F5Eh
0x140188e11  jmp     loc_140188BE5
0x140188e16  mov     [r12], r14d
0x140188e1a  jmp     loc_140188BE5
0x140188e1f  cmp     eax, 0C01E0305h
0x140188e24  jnz     loc_140188BE5
0x140188e2a  mov     rdx, r14
0x140188e2d  mov     ecx, 3
0x140188e32  call    cs:__imp_WdLogSingleEntry1
0x140188e39  nop     dword ptr [rax+rax+00h]
0x140188e3e  mov     cs:WdLogGlobalForLineNumber, 0F36h
0x140188e48  jmp     loc_140188BE5
0x140188e4d  mov     ecx, 6
0x140188e52  call    cs:__imp_WdLogSingleEntry0
0x140188e59  nop     dword ptr [rax+rax+00h]
0x140188e5e  mov     eax, 0C0000017h
0x140188e63  mov     cs:WdLogGlobalForLineNumber, 0EAAh
0x140188e6d  jmp     loc_140188FB0
0x140188e72  call    cs:__imp_WdLogNewEntry5_WdTrace
0x140188e79  nop     dword ptr [rax+rax+00h]
0x140188e7e  mov     ecx, esi
0x140188e80  mov     [rax+18h], rcx
0x140188e84  mov     rcx, rdi; void *
0x140188e87  mov     [rax+20h], r13
0x140188e8b  mov     cs:WdLogGlobalForLineNumber, 0ECAh
0x140188e95  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x140188e9a  test    rbx, rbx
0x140188e9d  jz      loc_140188F9D
0x140188ea3  mov     r14, [rsp+120h+var_D8]
0x140188ea8  mov     r15d, 2
0x140188eae  mov     r8, rbx
0x140188eb1  mov     rdi, rbx
0x140188eb4  mov     rbx, [rbx]
0x140188eb7  cmp     dword ptr [r8+8], 0FFFFFFFFh
0x140188ebc  jz      loc_140188F52
0x140188ec2  xor     edx, edx; struct DXGMONITOR *
0x140188ec4  lea     rcx, [rsp+120h+var_D8]; this
0x140188ec9  call    ??0MONITOR_REF_ACCESSOR@@QEAA@PEAVDXGMONITOR@@@Z; MONITOR_REF_ACCESSOR::MONITOR_REF_ACCESSOR(DXGMONITOR *)
0x140188ece  lea     rcx, [rbp+57h+var_A8]; this
0x140188ed2  call    ??0MONITOR_REF_ACCESSOR@@QEAA@PEAVDXGMONITOR@@@Z; MONITOR_REF_ACCESSOR::MONITOR_REF_ACCESSOR(DXGMONITOR *)
0x140188ed7  mov     edx, [rdi+8]
0x140188eda  lea     rax, [rsp+120h+var_D8]
0x140188edf  mov     [rsp+120h+ResultLength], r14
0x140188ee4  lea     r9, [rbp+57h+var_A8]
0x140188ee8  mov     r8d, r15d
0x140188eeb  mov     qword ptr [rsp+120h+Length], rax
0x140188ef0  mov     rcx, r13
0x140188ef3  call    ?_HandleCreateSimulatedMonitor@MONITOR_MGR@@QEAAJIW4_DMM_VIDPN_MONITOR_TYPE@@AEBVMONITOR_REF_ACCESSOR@@AEAV3@PEAU_DXGK_DISPLAY_SCENARIO_CONTEXT@@@Z; MONITOR_MGR::_HandleCreateSimulatedMonitor(uint,_DMM_VIDPN_MONITOR_TYPE,MONITOR_REF_ACCESSOR const &,MONITOR_REF_ACCESSOR &,_DXGK_DISPLAY_SCENARIO_CONTEXT *)
0x140188ef8  mov     esi, eax
0x140188efa  test    eax, eax
0x140188efc  js      short loc_140188F20
0x140188efe  cmp     [rbp+57h+var_D0], 0
0x140188f03  jnz     short loc_140188F20
0x140188f05  mov     ecx, 1
0x140188f0a  call    cs:__imp_WdLogSingleEntry0
0x140188f11  nop     dword ptr [rax+rax+00h]
0x140188f16  mov     cs:WdLogGlobalForLineNumber, 0F8Bh
0x140188f20  mov     r8d, [rdi+8]
0x140188f24  mov     r9d, esi
0x140188f27  mov     edx, 40000001h
0x140188f2c  mov     qword ptr [rsp+120h+Length], 0
0x140188f35  mov     rcx, r13
0x140188f38  call    ?_LogMonitorPresentEvent@MONITOR_MGR@@QEAAXW4_DMM_MONITOR_PRESENCE_EVENT_TYPE@@IJPEAU_DXGK_DIAG_MONITOR_MGR_EXTRA_INFO@@@Z; MONITOR_MGR::_LogMonitorPresentEvent(_DMM_MONITOR_PRESENCE_EVENT_TYPE,uint,long,_DXGK_DIAG_MONITOR_MGR_EXTRA_INFO *)
0x140188f3d  lea     rcx, [rbp+57h+var_A8]; this
0x140188f41  call    ?Release@MONITOR_REF_ACCESSOR@@QEAAXXZ; MONITOR_REF_ACCESSOR::Release(void)
0x140188f46  lea     rcx, [rsp+120h+var_D8]; this
0x140188f4b  call    ?Release@MONITOR_REF_ACCESSOR@@QEAAXXZ; MONITOR_REF_ACCESSOR::Release(void)
0x140188f50  jmp     short loc_140188F8C
0x140188f52  mov     rdx, [rsp+120h+KeyHandle]; Path
0x140188f57  add     r8, 18h; ValueName
0x140188f5b  mov     ecx, 40000000h; RelativeTo
0x140188f60  call    cs:__imp_RtlDeleteRegistryValue
0x140188f67  nop     dword ptr [rax+rax+00h]
0x140188f6c  test    eax, eax
0x140188f6e  jns     short loc_140188F8C
0x140188f70  movsxd  rdx, eax
0x140188f73  mov     ecx, r15d
0x140188f76  call    cs:__imp_WdLogSingleEntry1
0x140188f7d  nop     dword ptr [rax+rax+00h]
0x140188f82  mov     cs:WdLogGlobalForLineNumber, 0F9Dh
0x140188f8c  mov     rcx, rdi; void *
0x140188f8f  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x140188f94  test    rbx, rbx
0x140188f97  jnz     loc_140188EAE
0x140188f9d  mov     rcx, [rsp+120h+KeyHandle]; Handle
0x140188fa2  call    cs:__imp_ZwClose
0x140188fa9  nop     dword ptr [rax+rax+00h]
0x140188fae  xor     eax, eax
0x140188fb0  mov     rcx, [rbp+57h+var_40]
0x140188fb4  xor     rcx, rsp; StackCookie
0x140188fb7  call    __security_check_cookie
0x140188fbc  mov     rbx, [rsp+120h+arg_10]
0x140188fc4  add     rsp, 0F0h
0x140188fcb  pop     r15
0x140188fcd  pop     r14
0x140188fcf  pop     r13
0x140188fd1  pop     r12
0x140188fd3  pop     rdi
0x140188fd4  pop     rsi
0x140188fd5  pop     rbp
0x140188fd6  retn
```
