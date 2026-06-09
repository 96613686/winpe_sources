# EndSystemPhase::Execute(ActivityContext *)

- ea: `0x18006f0d0`
- end: `0x18006f277`
- name: `?Execute@EndSystemPhase@@UEAAJPEAVActivityContext@@@Z`
- size: `423`
- prototype: `__int64 __fastcall(EndSystemPhase *this, struct ActivityContext *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000de50`
- `0x180019e8c`
- `0x18001a86c`
- `0x18001ab40`
- `0x18002e1a0`
- `0x18003a918`
- `0x18003b068`
- `0x18003b118`
- `0x18004252c`
- `0x18006116c`
- `0x18006f0d0`
- `0x18007b010`

## import_xrefs

- `DMCmnUtils!DmRevertToSelf` at `0x18006f181`
- `DMCmnUtils!DmRevertToSelf` at `0x18006f181`
- `DMCmnUtils!DmImpersonate` at `0x18006f177`
- `DMCmnUtils!DmImpersonate` at `0x18006f177`

## string_xrefs

- `0x18006f196`: `onecoreuap\admin\enterprisemgmt\enrollengine\activities\src\mdmunenroll\endsystemphase.cpp`

## pseudocode

```c
__int64 __fastcall EndSystemPhase::Execute(EndSystemPhase *this, struct ActivityContext *a2)
{
  int Phase2UnenrollOnLoginSchedule; // edi
  int EnrollmentString; // eax
  __int64 v6; // r8
  int v7; // eax
  unsigned int v8; // eax
  int v10; // [rsp+20h] [rbp-B8h]
  LPCWSTR lpSubKey[2]; // [rsp+30h] [rbp-A8h] BYREF
  struct _GUID v12; // [rsp+40h] [rbp-98h] BYREF
  unsigned __int16 v13[40]; // [rsp+50h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  lpSubKey[0] = 0;
  Phase2UnenrollOnLoginSchedule = 0;
  if ( ActivityContext::get_KeyAsString(a2, v13) < 0 )
    goto LABEL_21;
  v12 = *(struct _GUID *)((char *)a2 + 8);
  EnrollmentString = EEDBManager::GetEnrollmentString(&v12, L"SID", (unsigned __int16 **)lpSubKey);
  Phase2UnenrollOnLoginSchedule = EnrollmentString;
  if ( *((_DWORD *)this + 10) && EnrollmentString >= 0 )
  {
    Phase2UnenrollOnLoginSchedule = CreatePhase2UnenrollOnLoginSchedule(v13, lpSubKey[0]);
  }
  else if ( EnrollmentString == -2147024894 )
  {
    Phase2UnenrollOnLoginSchedule = 0;
  }
  if ( !*((_QWORD *)a2 + 3) )
    goto LABEL_17;
  if ( !lpSubKey[0] )
    goto LABEL_13;
  if ( (int)DmImpersonate(lpSubKey[0]) < 0 )
  {
    if ( (unsigned int)IsSIDInvalid(lpSubKey[0]) )
      goto LABEL_13;
LABEL_17:
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 8) != 0 )
      McGenEventWrite_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, NotRunningUserPhase, v6, 1, &v12);
    if ( !*((_QWORD *)a2 + 3) )
      goto LABEL_20;
    goto LABEL_21;
  }
  v7 = DmRevertToSelf();
  if ( v7 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x1F,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollengine\\activities\\src\\mdmunenroll\\endsystemphase.cpp",
      (const char *)(unsigned int)v7,
      v10);
LABEL_13:
  *(_QWORD *)&v12.Data1 = *(_QWORD *)(*((_QWORD *)a2 + 52) + 1792LL);
  v8 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD, struct _GUID *))(**((_QWORD **)a2 + 3) + 136LL))(
         *((_QWORD *)a2 + 3),
         (char *)a2 + 8,
         *((unsigned int *)a2 + 18),
         &v12);
  Phase2UnenrollOnLoginSchedule = v8;
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
    McTemplateU0q_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, RunningUserPhase, v8);
  if ( Phase2UnenrollOnLoginSchedule < 0 )
LABEL_20:
    MicrosoftTelemetryAssertTriggeredNoArgs();
LABEL_21:
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>(lpSubKey);
  return (unsigned int)Phase2UnenrollOnLoginSchedule;
}

```

## disassembly

```asm
0x18006f0d0  push    rbp
0x18006f0d2  push    rsi
0x18006f0d3  push    rdi
0x18006f0d4  push    r14
0x18006f0d6  sub     rsp, 0B8h
0x18006f0dd  mov     rax, cs:__security_cookie
0x18006f0e4  xor     rax, rsp
0x18006f0e7  mov     [rsp+0D8h+var_38], rax
0x18006f0ef  mov     rsi, rdx
0x18006f0f2  mov     rbp, rcx
0x18006f0f5  mov     [rsp+0D8h+lpSubKey], 0
0x18006f0fe  xor     edi, edi
0x18006f100  lea     rdx, [rsp+0D8h+var_88]; unsigned __int16 *
0x18006f105  mov     rcx, rsi; this
0x18006f108  call    ?get_KeyAsString@ActivityContext@@QEAAJQEAG@Z; ActivityContext::get_KeyAsString(ushort * const)
0x18006f10d  test    eax, eax
0x18006f10f  js      loc_18006F24E
0x18006f115  movups  xmm0, xmmword ptr [rsi+8]
0x18006f119  movdqu  xmmword ptr [rsp+0D8h+var_98.Data1], xmm0
0x18006f11f  lea     r8, [rsp+0D8h+lpSubKey]; unsigned __int16 **
0x18006f124  lea     rdx, aSid; "SID"
0x18006f12b  lea     rcx, [rsp+0D8h+var_98]; struct _GUID
0x18006f130  call    ?GetEnrollmentString@EEDBManager@@CAJU_GUID@@PEBGPEAPEAG@Z; EEDBManager::GetEnrollmentString(_GUID,ushort const *,ushort * *)
0x18006f135  mov     edi, eax
0x18006f137  cmp     dword ptr [rbp+28h], 0
0x18006f13b  jz      short loc_18006F154
0x18006f13d  test    eax, eax
0x18006f13f  js      short loc_18006F154
0x18006f141  mov     rdx, [rsp+0D8h+lpSubKey]; unsigned __int16 *
0x18006f146  lea     rcx, [rsp+0D8h+var_88]; unsigned __int16 *
0x18006f14b  call    ?CreatePhase2UnenrollOnLoginSchedule@@YAJPEBG0@Z; CreatePhase2UnenrollOnLoginSchedule(ushort const *,ushort const *)
0x18006f150  mov     edi, eax
0x18006f152  jmp     short loc_18006F15F
0x18006f154  xor     eax, eax
0x18006f156  cmp     edi, 80070002h
0x18006f15c  cmovz   edi, eax
0x18006f15f  cmp     qword ptr [rsi+18h], 0
0x18006f164  jz      loc_18006F215
0x18006f16a  cmp     [rsp+0D8h+lpSubKey], 0
0x18006f170  jz      short loc_18006F1B6
0x18006f172  mov     rcx, [rsp+0D8h+lpSubKey]
0x18006f177  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x18006f17d  test    eax, eax
0x18006f17f  js      short loc_18006F1A8
0x18006f181  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18006f187  mov     rcx, [rsp+0D8h]; this
0x18006f18f  test    eax, eax
0x18006f191  jns     short loc_18006F1B6
0x18006f193  mov     r9d, eax; char *
0x18006f196  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006f19d  mov     edx, 1Fh; void *
0x18006f1a2  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18006f1a8  mov     rcx, [rsp+0D8h+lpSubKey]; lpSubKey
0x18006f1ad  call    ?IsSIDInvalid@@YAHPEBG@Z; IsSIDInvalid(ushort const *)
0x18006f1b2  test    eax, eax
0x18006f1b4  jz      short loc_18006F215
0x18006f1b6  mov     rax, [rsi+1A0h]
0x18006f1bd  mov     rcx, [rax+700h]
0x18006f1c4  mov     qword ptr [rsp+0D8h+var_98.Data1], rcx
0x18006f1c9  mov     rcx, [rsi+18h]
0x18006f1cd  mov     rax, [rcx]
0x18006f1d0  lea     r9, [rsp+0D8h+var_98]
0x18006f1d5  mov     r8d, [rsi+48h]
0x18006f1d9  lea     rdx, [rsi+8]
0x18006f1dd  mov     rax, [rax+88h]
0x18006f1e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f1e9  mov     edi, eax
0x18006f1eb  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x18006f1f2  jz      short loc_18006F20A
0x18006f1f4  mov     r8d, eax
0x18006f1f7  lea     rdx, RunningUserPhase
0x18006f1fe  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x18006f205  call    McTemplateU0q_EventWriteTransfer
0x18006f20a  test    edi, edi
0x18006f20c  jns     short loc_18006F24E
0x18006f20e  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "SUCCEEDED(hr)")
0x18006f213  jmp     short loc_18006F24E
0x18006f215  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 8
0x18006f21c  jz      short loc_18006F241
0x18006f21e  lea     rax, [rsp+0D8h+var_98]
0x18006f223  mov     qword ptr [rsp+0D8h+var_B8], rax
0x18006f228  mov     r9d, 1
0x18006f22e  lea     rdx, NotRunningUserPhase
0x18006f235  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x18006f23c  call    McGenEventWrite_EventWriteTransfer
0x18006f241  cmp     qword ptr [rsi+18h], 0
0x18006f246  jnz     short loc_18006F24E
0x18006f248  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "pContext->get_EnrollEngine()")
0x18006f24d  nop
0x18006f24e  lea     rcx, [rsp+0D8h+lpSubKey]
0x18006f253  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18006f258  mov     eax, edi
0x18006f25a  mov     rcx, [rsp+0D8h+var_38]
0x18006f262  xor     rcx, rsp; StackCookie
0x18006f265  call    __security_check_cookie
0x18006f26a  add     rsp, 0B8h
0x18006f271  pop     r14
0x18006f273  pop     rdi
0x18006f274  pop     rsi
0x18006f275  pop     rbp
0x18006f276  retn
```
