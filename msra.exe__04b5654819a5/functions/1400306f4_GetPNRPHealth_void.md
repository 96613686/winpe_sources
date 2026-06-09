# GetPNRPHealth(void *)

- ea: `0x1400306f4`
- end: `0x140030a3b`
- name: `?GetPNRPHealth@@YAKPEAX@Z`
- size: `839`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14000e870`

## callees

- `0x140002463`
- `0x1400306f4`
- `0x140030a44`
- `0x140034ce4`
- `0x140037e7c`
- `0x14004d010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x14003089f`
- `KERNEL32!SetEvent` at `0x140030a08`
- `KERNEL32!SetEvent` at `0x14003089f`
- `KERNEL32!SetEvent` at `0x140030a08`
- `KERNEL32!HeapFree` at `0x1400308eb`
- `KERNEL32!HeapFree` at `0x1400308eb`
- `KERNEL32!GetProcessHeap` at `0x1400308d7`
- `KERNEL32!GetProcessHeap` at `0x1400308d7`
- `KERNEL32!LeaveCriticalSection` at `0x1400308ae`
- `KERNEL32!LeaveCriticalSection` at `0x140030a17`
- `KERNEL32!LeaveCriticalSection` at `0x1400308ae`
- `KERNEL32!LeaveCriticalSection` at `0x140030a17`
- `KERNEL32!EnterCriticalSection` at `0x140030888`
- `KERNEL32!EnterCriticalSection` at `0x1400309f1`
- `KERNEL32!EnterCriticalSection` at `0x140030888`
- `KERNEL32!EnterCriticalSection` at `0x1400309f1`
- `ole32!CoTaskMemFree` at `0x140030900`
- `ole32!CoTaskMemFree` at `0x140030900`
- `ole32!CoUninitialize` at `0x140030953`
- `ole32!CoUninitialize` at `0x140030953`
- `ole32!CoCreateInstance` at `0x1400307f3`
- `ole32!CoCreateInstance` at `0x1400307f3`
- `ole32!CoInitializeEx` at `0x140030784`
- `ole32!CoInitializeEx` at `0x140030784`

## pseudocode

```c
__int64 __fastcall GetPNRPHealth(LPCRITICAL_SECTION lpCriticalSection)
{
  HRESULT ProcessSID; // eax
  int v4; // edi
  unsigned int v5; // r9d
  void *v6; // rcx
  CSqmManager *v7; // rcx
  unsigned int v8; // edx
  void *v9; // rbx
  HANDLE ProcessHeap; // rax
  void *v11; // rcx
  LPVOID lpMem[2]; // [rsp+30h] [rbp-59h] BYREF
  const wchar_t *v13; // [rsp+40h] [rbp-49h] BYREF
  _DWORD v14[38]; // [rsp+48h] [rbp-41h] BYREF
  int v15; // [rsp+F0h] [rbp+67h] BYREF
  LPVOID ppv; // [rsp+F8h] [rbp+6Fh] BYREF
  __int64 v17; // [rsp+100h] [rbp+77h] BYREF
  LPVOID pv; // [rsp+108h] [rbp+7Fh] BYREF

  v13 = 0;
  memset_0(v14, 0, 0x88u);
  ppv = 0;
  v17 = 0;
  pv = 0;
  v15 = 2;
  *(_OWORD *)lpMem = 0;
  if ( !lpCriticalSection )
  {
    CEventLogger::LogError(
      (CEventLogger *)L"GetPNRPHealth",
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
      0x214u,
      L"GetPNRPHealth",
      0x80070057);
    return 2147942487LL;
  }
  ProcessSID = CoInitializeEx(0, 0);
  if ( ProcessSID >= 0 )
  {
    v4 = 1;
    ProcessSID = GetProcessSID((struct tagOCTET_STRING *)lpMem);
    if ( ProcessSID >= 0 )
    {
      v14[0] = 7;
      v13 = L"DiagnosisType";
      v14[2] = 4;
      ProcessSID = CoCreateInstance(&CLSID_RAHelper, 0, 1u, &GUID_c0b35746_ebf5_11d8_bbe9_505054503030, &ppv);
      if ( ProcessSID >= 0 )
      {
        ProcessSID = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
                       ppv,
                       &GUID_972dab4d_e4e3_4fc6_ae54_5f65ccde4a15,
                       &v17);
        if ( ProcessSID >= 0 )
        {
          ProcessSID = (*(__int64 (__fastcall **)(LPVOID, __int64, const wchar_t **))(*(_QWORD *)ppv + 24LL))(
                         ppv,
                         1,
                         &v13);
          if ( ProcessSID == -2147024894 )
          {
            CEventLogger::LogError(
              (CEventLogger *)L"GetPNRPHealth",
              &Recoverable_Error,
              L"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
              0x238u,
              L"GetPNRPHealth",
              0x80070002);
            goto LABEL_13;
          }
          if ( ProcessSID >= 0 )
          {
            ProcessSID = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 40LL))(v17);
            if ( ProcessSID >= 0 )
            {
              ProcessSID = (*(__int64 (__fastcall **)(LPVOID, _QWORD, LPVOID *, _QWORD, int *))(*(_QWORD *)ppv + 48LL))(
                             ppv,
                             0,
                             &pv,
                             0,
                             &v15);
              if ( ProcessSID >= 0 )
                goto LABEL_34;
              v5 = 583;
            }
            else
            {
              v5 = 578;
            }
          }
          else
          {
            v5 = 572;
          }
        }
        else
        {
          v5 = 556;
        }
      }
      else
      {
        v5 = 553;
      }
    }
    else
    {
      v5 = 541;
    }
  }
  else
  {
    v4 = 0;
    v5 = 538;
  }
  CEventLogger::LogError(
    (CEventLogger *)L"GetPNRPHealth",
    &Recoverable_Error,
    L"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
    v5,
    L"GetPNRPHealth",
    ProcessSID);
LABEL_34:
  if ( v15 != 1 )
  {
    EnterCriticalSection(lpCriticalSection);
    v11 = *(void **)&lpCriticalSection[1].LockCount;
    LODWORD(lpCriticalSection[1].DebugInfo) = 1;
    SetEvent(v11);
    LeaveCriticalSection(lpCriticalSection);
    if ( !_AtlModule )
      goto LABEL_16;
    v8 = 17003;
    goto LABEL_15;
  }
LABEL_13:
  EnterCriticalSection(lpCriticalSection);
  v6 = *(void **)&lpCriticalSection[1].LockCount;
  LODWORD(lpCriticalSection[1].DebugInfo) = 2;
  SetEvent(v6);
  LeaveCriticalSection(lpCriticalSection);
  if ( _AtlModule )
  {
    v8 = 17004;
LABEL_15:
    CSqmManager::RecordUIUsage(v7, v8);
  }
LABEL_16:
  v9 = lpMem[1];
  if ( lpMem[1] )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v9);
  }
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v4 == 1 )
    CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x1400306f4  push    rbp
0x1400306f6  push    rbx
0x1400306f7  push    rdi
0x1400306f8  lea     rbp, [rsp-47h]
0x1400306fd  sub     rsp, 0D0h
0x140030704  mov     rbx, rcx
0x140030707  mov     [rbp+57h+var_A0], 0
0x14003070f  lea     rcx, [rbp+57h+var_98]; void *
0x140030713  xor     edx, edx; Val
0x140030715  mov     r8d, 88h; Size
0x14003071b  call    memset_0
0x140030720  mov     [rbp+57h+arg_8], 0
0x140030728  xorps   xmm0, xmm0
0x14003072b  mov     [rbp+57h+arg_10], 0
0x140030733  mov     [rbp+57h+pv], 0
0x14003073b  mov     [rbp+57h+arg_0], 2
0x140030742  movups  xmmword ptr [rbp+57h+lpMem], xmm0
0x140030746  test    rbx, rbx
0x140030749  jnz     short loc_140030780
0x14003074b  lea     rcx, aGetpnrphealth; "GetPNRPHealth"
0x140030752  mov     ebx, 80070057h
0x140030757  mov     [rsp+0E0h+var_B8], ebx; unsigned int
0x14003075b  lea     r8, aBaseDiagnosisR_28; "base\\diagnosis\\ra\\ui\\radiagutils.cp"...
0x140030762  mov     r9d, 214h; unsigned int
0x140030768  mov     [rsp+0E0h+ppv], rcx; unsigned __int16 *
0x14003076d  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140030774  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140030779  mov     eax, ebx
0x14003077b  jmp     loc_140030961
0x140030780  xor     edx, edx; dwCoInit
0x140030782  xor     ecx, ecx; pvReserved
0x140030784  call    cs:__imp_CoInitializeEx
0x14003078b  nop     dword ptr [rax+rax+00h]
0x140030790  test    eax, eax
0x140030792  jns     short loc_1400307A1
0x140030794  xor     edi, edi
0x140030796  mov     r9d, 21Ah
0x14003079c  jmp     loc_1400309C1
0x1400307a1  lea     rcx, [rbp+57h+lpMem]; struct tagOCTET_STRING *
0x1400307a5  mov     edi, 1
0x1400307aa  call    ?GetProcessSID@@YAJPEAUtagOCTET_STRING@@@Z; GetProcessSID(tagOCTET_STRING *)
0x1400307af  test    eax, eax
0x1400307b1  jns     short loc_1400307BE
0x1400307b3  mov     r9d, 21Dh
0x1400307b9  jmp     loc_1400309C1
0x1400307be  lea     rax, aDiagnosistype; "DiagnosisType"
0x1400307c5  mov     [rbp+57h+var_98], 7
0x1400307cc  mov     [rbp+57h+var_A0], rax
0x1400307d0  lea     r9, _GUID_c0b35746_ebf5_11d8_bbe9_505054503030; riid
0x1400307d7  lea     rax, [rbp+57h+arg_8]
0x1400307db  mov     [rbp+57h+var_90], 4
0x1400307e2  xor     edx, edx; pUnkOuter
0x1400307e4  mov     [rsp+0E0h+ppv], rax; ppv
0x1400307e9  mov     r8d, edi; dwClsContext
0x1400307ec  lea     rcx, CLSID_RAHelper; rclsid
0x1400307f3  call    cs:__imp_CoCreateInstance
0x1400307fa  nop     dword ptr [rax+rax+00h]
0x1400307ff  test    eax, eax
0x140030801  jns     short loc_14003080E
0x140030803  mov     r9d, 229h
0x140030809  jmp     loc_1400309C1
0x14003080e  mov     rcx, [rbp+57h+arg_8]
0x140030812  lea     r8, [rbp+57h+arg_10]
0x140030816  lea     rdx, _GUID_972dab4d_e4e3_4fc6_ae54_5f65ccde4a15
0x14003081d  mov     rax, [rcx]
0x140030820  mov     rax, [rax]
0x140030823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030828  test    eax, eax
0x14003082a  jns     short loc_140030837
0x14003082c  mov     r9d, 22Ch
0x140030832  jmp     loc_1400309C1
0x140030837  mov     rcx, [rbp+57h+arg_8]
0x14003083b  lea     r8, [rbp+57h+var_A0]
0x14003083f  mov     edx, edi
0x140030841  mov     rax, [rcx]
0x140030844  mov     rax, [rax+18h]
0x140030848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003084d  cmp     eax, 80070002h
0x140030852  jnz     loc_14003096D
0x140030858  lea     rcx, aGetpnrphealth; "GetPNRPHealth"
0x14003085f  mov     [rsp+0E0h+var_B8], 80070002h; unsigned int
0x140030867  mov     r9d, 238h; unsigned int
0x14003086d  mov     [rsp+0E0h+ppv], rcx; unsigned __int16 *
0x140030872  lea     r8, aBaseDiagnosisR_28; "base\\diagnosis\\ra\\ui\\radiagutils.cp"...
0x140030879  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140030880  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140030885  mov     rcx, rbx; lpCriticalSection
0x140030888  call    cs:__imp_EnterCriticalSection
0x14003088f  nop     dword ptr [rax+rax+00h]
0x140030894  mov     rcx, [rbx+30h]; hEvent
0x140030898  mov     dword ptr [rbx+28h], 2
0x14003089f  call    cs:__imp_SetEvent
0x1400308a6  nop     dword ptr [rax+rax+00h]
0x1400308ab  mov     rcx, rbx; lpCriticalSection
0x1400308ae  call    cs:__imp_LeaveCriticalSection
0x1400308b5  nop     dword ptr [rax+rax+00h]
0x1400308ba  cmp     cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA, 0; CRemoteAssistanceApp * _AtlModule
0x1400308c2  jz      short loc_1400308CE
0x1400308c4  mov     edx, 426Ch; unsigned int
0x1400308c9  call    ?RecordUIUsage@CSqmManager@@QEAAXK@Z; CSqmManager::RecordUIUsage(ulong)
0x1400308ce  mov     rbx, [rbp+57h+lpMem+8]
0x1400308d2  test    rbx, rbx
0x1400308d5  jz      short loc_1400308F7
0x1400308d7  call    cs:__imp_GetProcessHeap
0x1400308de  nop     dword ptr [rax+rax+00h]
0x1400308e3  mov     r8, rbx; lpMem
0x1400308e6  xor     edx, edx; dwFlags
0x1400308e8  mov     rcx, rax; hHeap
0x1400308eb  call    cs:__imp_HeapFree
0x1400308f2  nop     dword ptr [rax+rax+00h]
0x1400308f7  mov     rcx, [rbp+57h+pv]; pv
0x1400308fb  test    rcx, rcx
0x1400308fe  jz      short loc_140030914
0x140030900  call    cs:__imp_CoTaskMemFree
0x140030907  nop     dword ptr [rax+rax+00h]
0x14003090c  mov     [rbp+57h+pv], 0
0x140030914  mov     rcx, [rbp+57h+arg_10]
0x140030918  test    rcx, rcx
0x14003091b  jz      short loc_140030931
0x14003091d  mov     rax, [rcx]
0x140030920  mov     rax, [rax+10h]
0x140030924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030929  mov     [rbp+57h+arg_10], 0
0x140030931  mov     rcx, [rbp+57h+arg_8]
0x140030935  test    rcx, rcx
0x140030938  jz      short loc_14003094E
0x14003093a  mov     rax, [rcx]
0x14003093d  mov     rax, [rax+10h]
0x140030941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030946  mov     [rbp+57h+arg_8], 0
0x14003094e  cmp     edi, 1
0x140030951  jnz     short loc_14003095F
0x140030953  call    cs:__imp_CoUninitialize
0x14003095a  nop     dword ptr [rax+rax+00h]
0x14003095f  xor     eax, eax
0x140030961  add     rsp, 0D0h
0x140030968  pop     rdi
0x140030969  pop     rbx
0x14003096a  pop     rbp
0x14003096b  retn
0x14003096d  test    eax, eax
0x14003096f  jns     short loc_140030979
0x140030971  mov     r9d, 23Ch
0x140030977  jmp     short loc_1400309C1
0x140030979  mov     rcx, [rbp+57h+arg_10]
0x14003097d  mov     rax, [rcx]
0x140030980  mov     rax, [rax+28h]
0x140030984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030989  test    eax, eax
0x14003098b  jns     short loc_140030995
0x14003098d  mov     r9d, 242h
0x140030993  jmp     short loc_1400309C1
0x140030995  mov     rcx, [rbp+57h+arg_8]
0x140030999  lea     rdx, [rbp+57h+arg_0]
0x14003099d  mov     [rsp+0E0h+ppv], rdx
0x1400309a2  lea     r8, [rbp+57h+pv]
0x1400309a6  xor     r9d, r9d
0x1400309a9  xor     edx, edx
0x1400309ab  mov     rax, [rcx]
0x1400309ae  mov     rax, [rax+30h]
0x1400309b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400309b7  test    eax, eax
0x1400309b9  jns     short loc_1400309E4
0x1400309bb  mov     r9d, 247h; unsigned int
0x1400309c1  lea     rcx, aGetpnrphealth; "GetPNRPHealth"
0x1400309c8  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x1400309cc  lea     r8, aBaseDiagnosisR_28; "base\\diagnosis\\ra\\ui\\radiagutils.cp"...
0x1400309d3  mov     [rsp+0E0h+ppv], rcx; unsigned __int16 *
0x1400309d8  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x1400309df  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400309e4  cmp     [rbp+57h+arg_0], 1
0x1400309e8  jz      loc_140030885
0x1400309ee  mov     rcx, rbx; lpCriticalSection
0x1400309f1  call    cs:__imp_EnterCriticalSection
0x1400309f8  nop     dword ptr [rax+rax+00h]
0x1400309fd  mov     rcx, [rbx+30h]; hEvent
0x140030a01  mov     dword ptr [rbx+28h], 1
0x140030a08  call    cs:__imp_SetEvent
0x140030a0f  nop     dword ptr [rax+rax+00h]
0x140030a14  mov     rcx, rbx; lpCriticalSection
0x140030a17  call    cs:__imp_LeaveCriticalSection
0x140030a1e  nop     dword ptr [rax+rax+00h]
0x140030a23  cmp     cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA, 0; CRemoteAssistanceApp * _AtlModule
0x140030a2b  jz      loc_1400308CE
0x140030a31  mov     edx, 426Bh
0x140030a36  jmp     loc_1400308C9
```
