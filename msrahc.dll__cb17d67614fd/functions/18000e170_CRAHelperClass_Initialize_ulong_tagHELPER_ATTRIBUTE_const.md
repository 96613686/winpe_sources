# CRAHelperClass::Initialize(ulong,tagHELPER_ATTRIBUTE * const)

- ea: `0x18000e170`
- end: `0x18000e485`
- name: `?Initialize@CRAHelperClass@@UEAAJKQEAUtagHELPER_ATTRIBUTE@@@Z`
- size: `789`
- prototype: `__int64 __fastcall(CRAHelperClass *this, const struct _EVENT_DESCRIPTOR *, struct tagHELPER_ATTRIBUTE *const)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000c964`
- `0x18000cf88`
- `0x18000d274`
- `0x18000d3d4`
- `0x18000e170`
- `0x180011424`
- `0x180014660`
- `0x180014da0`
- `0x18001a178`

## import_xrefs

- `ADVAPI32!EventRegister` at `0x18000e2ad`
- `ADVAPI32!EventRegister` at `0x18000e2ad`

## string_xrefs

- `0x18000e253`: `%systemroot%\system32\msra.exe`

## pseudocode

```c
__int64 __fastcall CRAHelperClass::Initialize(
        CRAHelperClass *this,
        const struct _EVENT_DESCRIPTOR *a2,
        struct tagHELPER_ATTRIBUTE *const a3)
{
  unsigned int v4; // ebp
  unsigned int v6; // r9d
  signed int v8; // eax
  const struct _EVENT_DESCRIPTOR *v9; // rdx
  CEventLogger *v10; // rcx
  unsigned int v11; // ebx
  struct _attribute_t *v12; // rax
  const struct _EVENT_DESCRIPTOR *v13; // rdx
  CEventLogger *v14; // rcx
  struct _attribute_t *v15; // rax
  const unsigned __int16 *v16; // rcx
  signed int v17; // eax
  const struct _EVENT_DESCRIPTOR *v18; // rdx
  CEventLogger *v19; // rcx
  const struct _EVENT_DESCRIPTOR *v20; // rdx
  CEventLogger *v21; // rcx
  struct _attribute_t *v22; // rax
  GUID v23; // xmm0
  signed int v24; // eax
  const struct _EVENT_DESCRIPTOR *v25; // rdx
  CEventLogger *v26; // rcx
  struct _attribute_t *v27; // rax
  struct _attribute_t *v28; // rax
  const unsigned __int16 *v29; // rcx
  signed int v30; // eax
  const struct _EVENT_DESCRIPTOR *v31; // rdx
  CEventLogger *v32; // rcx
  struct _attribute_t *v33; // rax
  const unsigned __int16 *v34; // rcx
  signed int v35; // eax
  const struct _EVENT_DESCRIPTOR *v36; // rdx
  CEventLogger *v37; // rcx
  struct _attribute_t *v38; // rax
  const struct _EVENT_DESCRIPTOR *v39; // rdx
  CEventLogger *v40; // rcx
  const unsigned __int16 *v41; // rcx
  signed int v42; // eax

  v4 = (unsigned int)a2;
  if ( !(_DWORD)a2 )
  {
    v6 = 267;
LABEL_3:
    CEventLogger::LogError(
      this,
      a2,
      L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
      v6,
      L"CRAHelperClass::Initialize",
      0x80070057);
    return 2147942487LL;
  }
  if ( !a3 )
  {
    v6 = 268;
    goto LABEL_3;
  }
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 4, 1, 0) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  CRAHelperClass::CleanAllMemory(this);
  v8 = _attributes_array_t::Copy((CRAHelperClass *)((char *)this + 120), v4, a3);
  v11 = v8;
  if ( v8 >= 0 )
  {
    v12 = _attributes_array_t::Find((CRAHelperClass *)((char *)this + 120), L"DiagnosisType");
    if ( v12 )
    {
      *((_DWORD *)this + 40) = _attribute_t::operator long(v12);
      v15 = _attributes_array_t::Find((CRAHelperClass *)((char *)this + 120), L"AppID");
      if ( v15 )
      {
        if ( *((_DWORD *)v15 + 2) == 10 )
          v16 = (const unsigned __int16 *)*((_QWORD *)v15 + 2);
        else
          v16 = 0;
      }
      else
      {
        v16 = L"%systemroot%\\system32\\msra.exe";
      }
      v17 = DuplicateString(v16, (unsigned __int16 **)this + 22);
      v11 = v17;
      if ( v17 >= 0 )
      {
        if ( Microsoft_Windows_Networking_CorrelationHandle
          || !EventRegister(
                &Microsoft_Windows_Networking_CorrelationId,
                Microsoft_Windows_Networking_Correlation_EtwEnableCallback,
                0,
                &Microsoft_Windows_Networking_CorrelationHandle) )
        {
          Microsoft_Windows_Networking_ProviderId = (__int128)RemoteAssistanceGUID;
          v22 = _attributes_array_t::Find((CRAHelperClass *)((char *)this + 120), L"RAActivityID");
          if ( v22
            && (*((_DWORD *)v22 + 2) != 11 ? (v23 = GUID_NULL) : (v23 = (GUID)*((_OWORD *)v22 + 1)),
                *(GUID *)((char *)this + 200) = v23,
                v24 = InitializeTraceRelation((struct _GUID *)((char *)this + 200)),
                v11 = v24,
                v24 < 0) )
          {
            CEventLogger::LogError(
              v26,
              v25,
              L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
              0x151u,
              L"CRAHelperClass::Initialize",
              v24);
          }
          else
          {
            v27 = _attributes_array_t::Find((CRAHelperClass *)((char *)this + 120), L"EscalationType");
            if ( v27 )
              LODWORD(v27) = _attribute_t::operator long(v27);
            *((_DWORD *)this + 54) = (_DWORD)v27;
            v28 = _attributes_array_t::Find((CRAHelperClass *)((char *)this + 120), L"TicketString");
            if ( v28
              && (*((_DWORD *)v28 + 2) != 10 ? (v29 = 0) : (v29 = (const unsigned __int16 *)*((_QWORD *)v28 + 2)),
                  v30 = DuplicateString(v29, (unsigned __int16 **)this + 34),
                  v11 = v30,
                  v30 < 0) )
            {
              CEventLogger::LogError(
                v32,
                v31,
                L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
                0x168u,
                L"CRAHelperClass::Initialize",
                v30);
            }
            else
            {
              v33 = _attributes_array_t::Find((CRAHelperClass *)((char *)this + 120), L"PNRPAddress");
              if ( v33
                && (*((_DWORD *)v33 + 2) != 10 ? (v34 = 0) : (v34 = (const unsigned __int16 *)*((_QWORD *)v33 + 2)),
                    v35 = DuplicateString(v34, (unsigned __int16 **)this + 38),
                    v11 = v35,
                    v35 < 0) )
              {
                CEventLogger::LogError(
                  v37,
                  v36,
                  L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
                  0x171u,
                  L"CRAHelperClass::Initialize",
                  v35);
              }
              else
              {
                v38 = _attributes_array_t::Find((CRAHelperClass *)((char *)this + 120), L"PNRPAddressList");
                if ( v38
                  && (*((_DWORD *)v38 + 2) != 10 ? (v41 = 0) : (v41 = (const unsigned __int16 *)*((_QWORD *)v38 + 2)),
                      v42 = DuplicateString(v41, (unsigned __int16 **)this + 39),
                      v11 = v42,
                      v42 < 0) )
                {
                  CEventLogger::LogError(
                    v40,
                    v39,
                    L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
                    0x17Au,
                    L"CRAHelperClass::Initialize",
                    v42);
                }
                else if ( ((unsigned int)(*((_DWORD *)this + 54) - 7) <= 1
                        || (unsigned int)(*((_DWORD *)this + 40) - 4) <= 2)
                       && !*((_QWORD *)this + 41) )
                {
                  v11 = -2147024894;
                  CEventLogger::LogError(
                    v40,
                    v39,
                    L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
                    0x189u,
                    L"CRAHelperClass::Initialize",
                    0x80070002);
                }
              }
            }
          }
        }
        else
        {
          CEventLogger::LogError(
            v21,
            v20,
            L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
            0x144u,
            L"CRAHelperClass::Initialize",
            0);
          return (unsigned int)-2147467259;
        }
      }
      else
      {
        CEventLogger::LogError(
          v19,
          v18,
          L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
          0x13Eu,
          L"CRAHelperClass::Initialize",
          v17);
      }
    }
    else
    {
      v11 = -2147024809;
      CEventLogger::LogError(
        v14,
        v13,
        L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
        0x129u,
        L"CRAHelperClass::Initialize",
        0x80070057);
    }
  }
  else
  {
    CEventLogger::LogError(
      v10,
      v9,
      L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
      0x123u,
      L"CRAHelperClass::Initialize",
      v8);
  }
  return v11;
}

```

## disassembly

```asm
0x18000e170  push    rbx
0x18000e172  push    rbp
0x18000e173  push    rsi
0x18000e174  push    rdi
0x18000e175  push    r15
0x18000e177  sub     rsp, 30h
0x18000e17b  mov     rbx, r8
0x18000e17e  mov     ebp, edx
0x18000e180  mov     rdi, rcx
0x18000e183  test    edx, edx
0x18000e185  jnz     short loc_18000E1B7
0x18000e187  mov     r9d, 10Bh; unsigned int
0x18000e18d  lea     rax, aCrahelperclass_11; "CRAHelperClass::Initialize"
0x18000e194  mov     [rsp+58h+var_30], 80070057h; unsigned int
0x18000e19c  lea     r8, aBaseDiagnosisR_2; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x18000e1a3  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x18000e1a8  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x18000e1ad  mov     eax, 80070057h
0x18000e1b2  jmp     loc_18000E47A
0x18000e1b7  test    rbx, rbx
0x18000e1ba  jnz     short loc_18000E1C4
0x18000e1bc  mov     r9d, 10Ch
0x18000e1c2  jmp     short loc_18000E18D
0x18000e1c4  xor     eax, eax
0x18000e1c6  lea     r15d, [rax+1]
0x18000e1ca  lock cmpxchg [rcx+10h], r15d
0x18000e1d0  jz      short loc_18000E1D7
0x18000e1d2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e1d7  mov     rcx, rdi; this
0x18000e1da  call    ?CleanAllMemory@CRAHelperClass@@QEAAJXZ; CRAHelperClass::CleanAllMemory(void)
0x18000e1df  lea     rsi, [rdi+78h]
0x18000e1e3  mov     r8, rbx; struct tagHELPER_ATTRIBUTE *
0x18000e1e6  mov     rcx, rsi; this
0x18000e1e9  mov     edx, ebp; unsigned int
0x18000e1eb  call    ?Copy@_attributes_array_t@@QEAAJKPEAUtagHELPER_ATTRIBUTE@@@Z; _attributes_array_t::Copy(ulong,tagHELPER_ATTRIBUTE *)
0x18000e1f0  mov     ebx, eax
0x18000e1f2  test    eax, eax
0x18000e1f4  jns     short loc_18000E205
0x18000e1f6  mov     [rsp+58h+var_30], eax
0x18000e1fa  mov     r9d, 123h
0x18000e200  jmp     loc_18000E460
0x18000e205  lea     rdx, aDiagnosistype; "DiagnosisType"
0x18000e20c  mov     rcx, rsi; this
0x18000e20f  call    ?Find@_attributes_array_t@@QEAAPEAV_attribute_t@@PEBG@Z; _attributes_array_t::Find(ushort const *)
0x18000e214  test    rax, rax
0x18000e217  jnz     short loc_18000E231
0x18000e219  mov     ebx, 80070057h
0x18000e21e  mov     [rsp+58h+var_30], 80070057h
0x18000e226  mov     r9d, 129h
0x18000e22c  jmp     loc_18000E460
0x18000e231  mov     rcx, rax
0x18000e234  call    ??B_attribute_t@@QEBAJXZ; _attribute_t::operator long(void)
0x18000e239  lea     rdx, aAppid_1; "AppID"
0x18000e240  mov     [rdi+0A0h], eax
0x18000e246  mov     rcx, rsi; this
0x18000e249  call    ?Find@_attributes_array_t@@QEAAPEAV_attribute_t@@PEBG@Z; _attributes_array_t::Find(ushort const *)
0x18000e24e  test    rax, rax
0x18000e251  jnz     short loc_18000E25C
0x18000e253  lea     rcx, aSystemrootSyst; "%systemroot%\\system32\\msra.exe"
0x18000e25a  jmp     short loc_18000E26A
0x18000e25c  cmp     dword ptr [rax+8], 0Ah
0x18000e260  jnz     short loc_18000E268
0x18000e262  mov     rcx, [rax+10h]
0x18000e266  jmp     short loc_18000E26A
0x18000e268  xor     ecx, ecx; Src
0x18000e26a  lea     rdx, [rdi+0B0h]; unsigned __int16 **
0x18000e271  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x18000e276  mov     ebx, eax
0x18000e278  test    eax, eax
0x18000e27a  jns     short loc_18000E28B
0x18000e27c  mov     [rsp+58h+var_30], eax
0x18000e280  mov     r9d, 13Eh
0x18000e286  jmp     loc_18000E460
0x18000e28b  cmp     cs:Microsoft_Windows_Networking_CorrelationHandle, 0
0x18000e293  jnz     short loc_18000E2E7
0x18000e295  lea     r9, Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x18000e29c  xor     r8d, r8d; CallbackContext
0x18000e29f  lea     rdx, Microsoft_Windows_Networking_Correlation_EtwEnableCallback; EnableCallback
0x18000e2a6  lea     rcx, Microsoft_Windows_Networking_CorrelationId; ProviderId
0x18000e2ad  call    cs:__imp_EventRegister
0x18000e2b3  test    eax, eax
0x18000e2b5  jz      short loc_18000E2E7
0x18000e2b7  lea     rax, aCrahelperclass_11; "CRAHelperClass::Initialize"
0x18000e2be  mov     [rsp+58h+var_30], 0; unsigned int
0x18000e2c6  mov     r9d, 144h; unsigned int
0x18000e2cc  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x18000e2d1  lea     r8, aBaseDiagnosisR_2; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x18000e2d8  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x18000e2dd  mov     ebx, 80004005h
0x18000e2e2  jmp     loc_18000E478
0x18000e2e7  movups  xmm0, xmmword ptr cs:RemoteAssistanceGUID.Data1
0x18000e2ee  lea     rdx, aRaactivityid; "RAActivityID"
0x18000e2f5  mov     rcx, rsi; this
0x18000e2f8  movdqu  cs:Microsoft_Windows_Networking_ProviderId, xmm0
0x18000e300  call    ?Find@_attributes_array_t@@QEAAPEAV_attribute_t@@PEBG@Z; _attributes_array_t::Find(ushort const *)
0x18000e305  test    rax, rax
0x18000e308  jz      short loc_18000E342
0x18000e30a  cmp     dword ptr [rax+8], 0Bh
0x18000e30e  jnz     short loc_18000E316
0x18000e310  movups  xmm0, xmmword ptr [rax+10h]
0x18000e314  jmp     short loc_18000E31D
0x18000e316  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000e31d  lea     rcx, [rdi+0C8h]; struct _GUID *
0x18000e324  movdqu  xmmword ptr [rcx], xmm0
0x18000e328  call    ?InitializeTraceRelation@@YAJPEAU_GUID@@@Z; InitializeTraceRelation(_GUID *)
0x18000e32d  mov     ebx, eax
0x18000e32f  test    eax, eax
0x18000e331  jns     short loc_18000E342
0x18000e333  mov     [rsp+58h+var_30], eax
0x18000e337  mov     r9d, 151h
0x18000e33d  jmp     loc_18000E460
0x18000e342  lea     rdx, aEscalationtype; "EscalationType"
0x18000e349  mov     rcx, rsi; this
0x18000e34c  call    ?Find@_attributes_array_t@@QEAAPEAV_attribute_t@@PEBG@Z; _attributes_array_t::Find(ushort const *)
0x18000e351  test    rax, rax
0x18000e354  jz      short loc_18000E35E
0x18000e356  mov     rcx, rax
0x18000e359  call    ??B_attribute_t@@QEBAJXZ; _attribute_t::operator long(void)
0x18000e35e  lea     rdx, aTicketstring; "TicketString"
0x18000e365  mov     [rdi+0D8h], eax
0x18000e36b  mov     rcx, rsi; this
0x18000e36e  call    ?Find@_attributes_array_t@@QEAAPEAV_attribute_t@@PEBG@Z; _attributes_array_t::Find(ushort const *)
0x18000e373  test    rax, rax
0x18000e376  jz      short loc_18000E3A7
0x18000e378  cmp     dword ptr [rax+8], 0Ah
0x18000e37c  jnz     short loc_18000E384
0x18000e37e  mov     rcx, [rax+10h]
0x18000e382  jmp     short loc_18000E386
0x18000e384  xor     ecx, ecx; Src
0x18000e386  lea     rdx, [rdi+110h]; unsigned __int16 **
0x18000e38d  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x18000e392  mov     ebx, eax
0x18000e394  test    eax, eax
0x18000e396  jns     short loc_18000E3A7
0x18000e398  mov     [rsp+58h+var_30], eax
0x18000e39c  mov     r9d, 168h
0x18000e3a2  jmp     loc_18000E460
0x18000e3a7  lea     rdx, aPnrpaddress; "PNRPAddress"
0x18000e3ae  mov     rcx, rsi; this
0x18000e3b1  call    ?Find@_attributes_array_t@@QEAAPEAV_attribute_t@@PEBG@Z; _attributes_array_t::Find(ushort const *)
0x18000e3b6  test    rax, rax
0x18000e3b9  jz      short loc_18000E3E7
0x18000e3bb  cmp     dword ptr [rax+8], 0Ah
0x18000e3bf  jnz     short loc_18000E3C7
0x18000e3c1  mov     rcx, [rax+10h]
0x18000e3c5  jmp     short loc_18000E3C9
0x18000e3c7  xor     ecx, ecx; Src
0x18000e3c9  lea     rdx, [rdi+130h]; unsigned __int16 **
0x18000e3d0  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x18000e3d5  mov     ebx, eax
0x18000e3d7  test    eax, eax
0x18000e3d9  jns     short loc_18000E3E7
0x18000e3db  mov     [rsp+58h+var_30], eax
0x18000e3df  mov     r9d, 171h
0x18000e3e5  jmp     short loc_18000E460
0x18000e3e7  lea     rdx, aPnrpaddresslis; "PNRPAddressList"
0x18000e3ee  mov     rcx, rsi; this
0x18000e3f1  call    ?Find@_attributes_array_t@@QEAAPEAV_attribute_t@@PEBG@Z; _attributes_array_t::Find(ushort const *)
0x18000e3f6  test    rax, rax
0x18000e3f9  jz      short loc_18000E427
0x18000e3fb  cmp     dword ptr [rax+8], 0Ah
0x18000e3ff  jnz     short loc_18000E407
0x18000e401  mov     rcx, [rax+10h]
0x18000e405  jmp     short loc_18000E409
0x18000e407  xor     ecx, ecx; Src
0x18000e409  lea     rdx, [rdi+138h]; unsigned __int16 **
0x18000e410  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x18000e415  mov     ebx, eax
0x18000e417  test    eax, eax
0x18000e419  jns     short loc_18000E427
0x18000e41b  mov     [rsp+58h+var_30], eax
0x18000e41f  mov     r9d, 17Ah
0x18000e425  jmp     short loc_18000E460
0x18000e427  mov     eax, [rdi+0D8h]
0x18000e42d  sub     eax, 7
0x18000e430  cmp     eax, r15d
0x18000e433  jbe     short loc_18000E443
0x18000e435  mov     eax, [rdi+0A0h]
0x18000e43b  sub     eax, 4
0x18000e43e  cmp     eax, 2
0x18000e441  ja      short loc_18000E478
0x18000e443  cmp     qword ptr [rdi+148h], 0
0x18000e44b  jnz     short loc_18000E478
0x18000e44d  mov     ebx, 80070002h
0x18000e452  mov     [rsp+58h+var_30], 80070002h; unsigned int
0x18000e45a  mov     r9d, 189h; unsigned int
0x18000e460  lea     rax, aCrahelperclass_11; "CRAHelperClass::Initialize"
0x18000e467  lea     r8, aBaseDiagnosisR_2; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x18000e46e  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x18000e473  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x18000e478  mov     eax, ebx
0x18000e47a  add     rsp, 30h
0x18000e47e  pop     r15
0x18000e480  pop     rdi
0x18000e481  pop     rsi
0x18000e482  pop     rbp
0x18000e483  pop     rbx
0x18000e484  retn
```
