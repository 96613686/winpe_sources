# TryScheduleRetryTask(ushort const *,ushort const *,tagDMACCOUNTLOOKUPTYPE,long)

- ea: `0x14001401c`
- end: `0x140014198`
- name: `?TryScheduleRetryTask@@YAJPEBG0W4tagDMACCOUNTLOOKUPTYPE@@J@Z`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000fff0`

## callees

- `0x14000b708`
- `0x14000beb8`
- `0x14000c084`
- `0x14000f580`
- `0x14000f6b8`
- `0x140012288`
- `0x14001401c`

## import_xrefs

- `DMCmnUtils!DmDeleteTaskFolder` at `0x1400140cf`
- `DMCmnUtils!DmDeleteTaskFolder` at `0x1400140cf`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x140014182`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x140014182`

## string_xrefs

- `0x140014087`: `DeleteRetriableSessions`
- `0x1400140af`: `DeleteRetryCount`
- `0x1400140e5`: `DmDeleteTaskFolder`
- `0x140014142`: `ScheduleRetryTask`
- `0x140014114`: `TryScheduleRetryTask`
- `0x140014152`: `TryScheduleRetryTask`

## pseudocode

```c
int __fastcall TryScheduleRetryTask(const unsigned __int16 *a1, const unsigned __int16 *a2, __int64 a3, int a4)
{
  int v6; // ecx
  int v8; // edi
  int v9; // edi
  int v10; // eax
  COmaDmPrcLogger *Logger; // rax
  const unsigned __int16 *v12; // r8
  int v13; // eax
  COmaDmPrcLogger *v14; // rax
  const unsigned __int16 *v15; // r8
  int v16; // eax
  COmaDmPrcLogger *v17; // rax
  const unsigned __int16 *v18; // r8
  COmaDmPrcLogger *v19; // rax
  COmaDmPrcLogger *v20; // rax

  if ( (unsigned int)(a4 + 2147012894) > 0x1E || (v6 = 1476427821, !_bittest(&v6, a4 + 2147012894)) )
  {
    if ( a4 != -2147012816 && a4 != -2102657013 )
      return -2147024809;
  }
  v8 = ScheduleRetryTask(a1);
  if ( v8 == -2102657017 )
  {
    v9 = 0;
    v10 = DeleteRetriableSessions(a1);
    if ( v10 < 0 )
      v9 = v10;
    Logger = COmaDmPrcLogger::GetLogger();
    COmaDmPrcLogger::LogOmaDmPrcRetryRecoveryResult(Logger, a1, v12, L"DeleteRetriableSessions", v9);
    v13 = DeleteRetryCount(a1);
    if ( v13 < 0 )
      v9 = v13;
    v14 = COmaDmPrcLogger::GetLogger();
    COmaDmPrcLogger::LogOmaDmPrcRetryRecoveryResult(v14, a1, v15, L"DeleteRetryCount", v9);
    v16 = DmDeleteTaskFolder(L"\\Microsoft\\Windows\\EnterpriseMgmt\\SessionRetry", a1);
    if ( v16 < 0 )
      v9 = v16;
    v17 = COmaDmPrcLogger::GetLogger();
    COmaDmPrcLogger::LogOmaDmPrcRetryRecoveryResult(v17, a1, v18, L"DmDeleteTaskFolder", v9);
    if ( v9 < 0 )
    {
      v19 = COmaDmPrcLogger::GetLogger();
      COmaDmPrcLogger::LogOmaDmPrcScheduleRetrySessionResult(v19, a1, a2, L"TryScheduleRetryTask", L"RetryRecovery", v9);
    }
    v8 = ScheduleRetryTask(a1);
  }
  if ( v8 >= 0 )
    return OmaDmRegistrySetDWORD(HKEY_LOCAL_MACHINE, a2, L"SessionState", 6u);
  v20 = COmaDmPrcLogger::GetLogger();
  COmaDmPrcLogger::LogOmaDmPrcScheduleRetrySessionResult(v20, a1, a2, L"TryScheduleRetryTask", L"ScheduleRetryTask", v8);
  return v8;
}

```

## disassembly

```asm
0x14001401c  push    rbx
0x14001401e  push    rbp
0x14001401f  push    rsi
0x140014020  push    rdi
0x140014021  sub     rsp, 38h
0x140014025  lea     eax, [r9+7FF8D11Eh]
0x14001402c  mov     ebx, r9d
0x14001402f  mov     rsi, rdx
0x140014032  mov     rbp, rcx
0x140014035  cmp     eax, 1Eh
0x140014038  ja      short loc_140014044
0x14001403a  mov     ecx, 5800802Dh
0x14001403f  bt      ecx, eax
0x140014042  jb      short loc_14001405E
0x140014044  cmp     ebx, 80072F30h
0x14001404a  jz      short loc_14001405E
0x14001404c  cmp     ebx, 82AC000Bh
0x140014052  jz      short loc_14001405E
0x140014054  mov     eax, 80070057h
0x140014059  jmp     loc_14001418E
0x14001405e  mov     rcx, rbp
0x140014061  call    ?ScheduleRetryTask@@YAJPEBG0W4tagDMACCOUNTLOOKUPTYPE@@J@Z; ScheduleRetryTask(ushort const *,ushort const *,tagDMACCOUNTLOOKUPTYPE,long)
0x140014066  mov     edi, eax
0x140014068  cmp     eax, 82AC0007h
0x14001406d  jnz     loc_140014139
0x140014073  mov     rcx, rbp; unsigned __int16 *
0x140014076  xor     edi, edi
0x140014078  call    ?DeleteRetriableSessions@@YAJPEBG@Z; DeleteRetriableSessions(ushort const *)
0x14001407d  test    eax, eax
0x14001407f  cmovs   edi, eax
0x140014082  call    ?GetLogger@COmaDmPrcLogger@@SAPEAV1@XZ; COmaDmPrcLogger::GetLogger(void)
0x140014087  lea     r9, aDeleteretriabl; "DeleteRetriableSessions"
0x14001408e  mov     dword ptr [rsp+58h+var_38], edi; int
0x140014092  mov     rdx, rbp; unsigned __int16 *
0x140014095  mov     rcx, rax; this
0x140014098  call    ?LogOmaDmPrcRetryRecoveryResult@COmaDmPrcLogger@@QEAAXPEBG00J@Z; COmaDmPrcLogger::LogOmaDmPrcRetryRecoveryResult(ushort const *,ushort const *,ushort const *,long)
0x14001409d  mov     rcx, rbp; unsigned __int16 *
0x1400140a0  call    ?DeleteRetryCount@@YAJPEBG@Z; DeleteRetryCount(ushort const *)
0x1400140a5  test    eax, eax
0x1400140a7  cmovs   edi, eax
0x1400140aa  call    ?GetLogger@COmaDmPrcLogger@@SAPEAV1@XZ; COmaDmPrcLogger::GetLogger(void)
0x1400140af  lea     r9, aDeleteretrycou; "DeleteRetryCount"
0x1400140b6  mov     dword ptr [rsp+58h+var_38], edi; int
0x1400140ba  mov     rdx, rbp; unsigned __int16 *
0x1400140bd  mov     rcx, rax; this
0x1400140c0  call    ?LogOmaDmPrcRetryRecoveryResult@COmaDmPrcLogger@@QEAAXPEBG00J@Z; COmaDmPrcLogger::LogOmaDmPrcRetryRecoveryResult(ushort const *,ushort const *,ushort const *,long)
0x1400140c5  mov     rdx, rbp
0x1400140c8  lea     rcx, aMicrosoftWindo_0; "\\Microsoft\\Windows\\EnterpriseMgmt\\S"...
0x1400140cf  call    cs:__imp_?DmDeleteTaskFolder@@YAJPEBG0@Z; DmDeleteTaskFolder(ushort const *,ushort const *)
0x1400140d6  nop     dword ptr [rax+rax+00h]
0x1400140db  test    eax, eax
0x1400140dd  cmovs   edi, eax
0x1400140e0  call    ?GetLogger@COmaDmPrcLogger@@SAPEAV1@XZ; COmaDmPrcLogger::GetLogger(void)
0x1400140e5  lea     r9, aDmdeletetaskfo; "DmDeleteTaskFolder"
0x1400140ec  mov     dword ptr [rsp+58h+var_38], edi; int
0x1400140f0  mov     rdx, rbp; unsigned __int16 *
0x1400140f3  mov     rcx, rax; this
0x1400140f6  call    ?LogOmaDmPrcRetryRecoveryResult@COmaDmPrcLogger@@QEAAXPEBG00J@Z; COmaDmPrcLogger::LogOmaDmPrcRetryRecoveryResult(ushort const *,ushort const *,ushort const *,long)
0x1400140fb  test    edi, edi
0x1400140fd  jns     short loc_140014129
0x1400140ff  call    ?GetLogger@COmaDmPrcLogger@@SAPEAV1@XZ; COmaDmPrcLogger::GetLogger(void)
0x140014104  lea     rcx, aRetryrecovery; "RetryRecovery"
0x14001410b  mov     [rsp+58h+var_30], edi; int
0x14001410f  mov     [rsp+58h+var_38], rcx; unsigned __int16 *
0x140014114  lea     r9, aTryscheduleret; "TryScheduleRetryTask"
0x14001411b  mov     rcx, rax; this
0x14001411e  mov     r8, rsi; unsigned __int16 *
0x140014121  mov     rdx, rbp; unsigned __int16 *
0x140014124  call    ?LogOmaDmPrcScheduleRetrySessionResult@COmaDmPrcLogger@@QEAAXPEBG000J@Z; COmaDmPrcLogger::LogOmaDmPrcScheduleRetrySessionResult(ushort const *,ushort const *,ushort const *,ushort const *,long)
0x140014129  mov     r9d, ebx
0x14001412c  mov     rdx, rsi
0x14001412f  mov     rcx, rbp
0x140014132  call    ?ScheduleRetryTask@@YAJPEBG0W4tagDMACCOUNTLOOKUPTYPE@@J@Z; ScheduleRetryTask(ushort const *,ushort const *,tagDMACCOUNTLOOKUPTYPE,long)
0x140014137  mov     edi, eax
0x140014139  test    edi, edi
0x14001413b  jns     short loc_14001416B
0x14001413d  call    ?GetLogger@COmaDmPrcLogger@@SAPEAV1@XZ; COmaDmPrcLogger::GetLogger(void)
0x140014142  lea     rcx, aScheduleretryt; "ScheduleRetryTask"
0x140014149  mov     [rsp+58h+var_30], edi; int
0x14001414d  mov     [rsp+58h+var_38], rcx; unsigned __int16 *
0x140014152  lea     r9, aTryscheduleret; "TryScheduleRetryTask"
0x140014159  mov     rcx, rax; this
0x14001415c  mov     r8, rsi; unsigned __int16 *
0x14001415f  mov     rdx, rbp; unsigned __int16 *
0x140014162  call    ?LogOmaDmPrcScheduleRetrySessionResult@COmaDmPrcLogger@@QEAAXPEBG000J@Z; COmaDmPrcLogger::LogOmaDmPrcScheduleRetrySessionResult(ushort const *,ushort const *,ushort const *,ushort const *,long)
0x140014167  mov     eax, edi
0x140014169  jmp     short loc_14001418E
0x14001416b  mov     r9d, 6
0x140014171  lea     r8, aSessionstate; "SessionState"
0x140014178  mov     rdx, rsi
0x14001417b  mov     rcx, 0FFFFFFFF80000002h
0x140014182  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x140014189  nop     dword ptr [rax+rax+00h]
0x14001418e  add     rsp, 38h
0x140014192  pop     rdi
0x140014193  pop     rsi
0x140014194  pop     rbp
0x140014195  pop     rbx
0x140014196  retn
```
