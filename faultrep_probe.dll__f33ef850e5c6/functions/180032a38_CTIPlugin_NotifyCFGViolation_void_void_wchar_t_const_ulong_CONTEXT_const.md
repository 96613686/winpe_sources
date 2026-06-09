# CTIPlugin::NotifyCFGViolation(void *,void *,wchar_t const *,ulong,_CONTEXT const *)

- ea: `0x180032a38`
- end: `0x180032d2f`
- name: `?NotifyCFGViolation@CTIPlugin@@CAXPEAX0PEB_WKPEBU_CONTEXT@@@Z`
- size: `759`
- prototype: `void __usercall(void *@<rcx>, void *@<rdx>, const wchar_t *@<r8>, unsigned int@<r9d>, const struct _CONTEXT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800329a0`

## callees

- `0x180002890`
- `0x180003474`
- `0x180009f00`
- `0x180032750`
- `0x18003282c`
- `0x180032a38`
- `0x18003e5a8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x180032b69`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x180032b69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032b90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032b90`
- `ntdll!EtwEventWriteNoRegistration` at `0x180032cd1`
- `ntdll!EtwEventWriteNoRegistration` at `0x180032cd1`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180032b04`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180032b47`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180032b04`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180032b47`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180032ac3`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180032ac3`

## pseudocode

```c
void __fastcall CTIPlugin::NotifyCFGViolation(void *a1, void *a2, const wchar_t *a3, int a4, const struct _CONTEXT *a5)
{
  const struct _CONTEXT *v5; // rdi
  const void *R8; // rdx
  unsigned int v10; // edx
  signed int LastError; // eax
  __int64 v12; // rax
  unsigned int v13; // eax
  unsigned int v14; // edx
  unsigned int TICallAddressInfo; // eax
  __int64 v16; // rcx
  int v17; // r9d
  unsigned int v18; // eax
  WINBOOL Wow64Process; // [rsp+30h] [rbp-D0h] BYREF
  int v20; // [rsp+34h] [rbp-CCh] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+38h] [rbp-C8h] BYREF
  struct _FILETIME ExitTime; // [rsp+40h] [rbp-C0h] BYREF
  struct _FILETIME CreationTime; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE Buffer[128]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v25; // [rsp+D0h] [rbp-30h]
  LPCVOID lpBaseAddress; // [rsp+E8h] [rbp-18h]
  _QWORD v27[90]; // [rsp+520h] [rbp+420h] BYREF
  _QWORD v28[90]; // [rsp+7F0h] [rbp+6F0h] BYREF
  const wchar_t *v29; // [rsp+AC0h] [rbp+9C0h] BYREF
  int v30; // [rsp+AC8h] [rbp+9C8h]
  int v31; // [rsp+ACCh] [rbp+9CCh]
  int *v32; // [rsp+AD0h] [rbp+9D0h]
  __int64 v33; // [rsp+AD8h] [rbp+9D8h]
  struct _FILETIME *p_CreationTime; // [rsp+AE0h] [rbp+9E0h]
  __int64 v35; // [rsp+AE8h] [rbp+9E8h]
  int *v36; // [rsp+AF0h] [rbp+9F0h]
  __int64 v37; // [rsp+AF8h] [rbp+9F8h]
  struct _EVENT_DATA_DESCRIPTOR v38; // [rsp+B00h] [rbp+A00h] BYREF
  int v39; // [rsp+C98h] [rbp+B98h] BYREF

  v39 = a4;
  v5 = a5;
  Wow64Process = 0;
  memset_0(v27, 0, 0x2C8u);
  memset_0(v28, 0, 0x2C8u);
  CreationTime = 0;
  ExitTime = 0;
  v20 = 1;
  if ( IsWow64Process(a1, &Wow64Process) && Wow64Process )
    v20 = 0;
  R8 = (const void *)v5->R8;
  NumberOfBytesRead = 0;
  if ( R8 )
  {
    Wow64Process = ReadProcessMemory(a1, R8, Buffer, 0x4D0u, &NumberOfBytesRead);
    if ( Wow64Process )
    {
      if ( NumberOfBytesRead == 1232 )
      {
        v28[0] = v25;
        if ( lpBaseAddress )
          ReadProcessMemory(a1, lpBaseAddress, v27, 8u, &NumberOfBytesRead);
      }
    }
  }
  Wow64Process = GetProcessTimes(a1, &CreationTime, &ExitTime, &ExitTime, &ExitTime);
  if ( !Wow64Process )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        &WPP_5d1834416bbb32ed8157f52948dd8803_Traceguids,
        (unsigned int)LastError);
    }
    CreationTime = 0;
  }
  if ( v28[0] )
    CTIPlugin::FillCallInfo((struct TI_ADDRESS_INFO *)v28, a1, a2, 1);
  if ( v27[0] )
    CTIPlugin::FillCallInfo((struct TI_ADDRESS_INFO *)v27, a1, a2, 0);
  v29 = a3;
  v12 = -1;
  do
    ++v12;
  while ( a3[v12] );
  v31 = 0;
  v30 = 2 * v12 + 2;
  v33 = 4;
  v32 = &v39;
  v35 = 8;
  p_CreationTime = &CreationTime;
  v36 = &v20;
  v37 = 4;
  v13 = CTIPlugin::EventDataDescCreateTICallAddressInfo(&v38, v10, (const struct TI_ADDRESS_INFO *)v27);
  TICallAddressInfo = CTIPlugin::EventDataDescCreateTICallAddressInfo(
                        (struct _EVENT_DATA_DESCRIPTOR *)&(&v29)[2 * v13 + 4],
                        v14,
                        (const struct TI_ADDRESS_INFO *)v28);
  if ( v17 + TICallAddressInfo != 24 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v16);
  v18 = EtwEventWriteNoRegistration(&S_MICROSOFT_WINDOWS_WER_DIAG, &EVENT_CFG_VIOLATION, 24, &v29);
  Wow64Process = v18;
  if ( v18 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_5d1834416bbb32ed8157f52948dd8803_Traceguids, v18);
}

```

## disassembly

```asm
0x180032a38  mov     [rsp-8+arg_10], rbx
0x180032a3d  mov     [rsp-8+arg_18], r9d
0x180032a42  push    rbp
0x180032a43  push    rsi
0x180032a44  push    rdi
0x180032a45  push    r12
0x180032a47  push    r14
0x180032a49  lea     rbp, [rsp-0B50h]
0x180032a51  sub     rsp, 0C50h
0x180032a58  mov     rax, cs:__security_cookie
0x180032a5f  xor     rax, rsp
0x180032a62  mov     [rbp+0B70h+var_30], rax
0x180032a69  mov     rdi, [rbp+0B70h+arg_20]
0x180032a70  mov     rsi, r8
0x180032a73  mov     r14, rdx
0x180032a76  mov     rbx, rcx
0x180032a79  xor     r12d, r12d
0x180032a7c  lea     rcx, [rbp+0B70h+var_750]; void *
0x180032a83  xor     edx, edx; Val
0x180032a85  mov     [rsp+0C70h+Wow64Process], r12d
0x180032a8a  mov     r8d, 2C8h; Size
0x180032a90  call    memset_0
0x180032a95  xor     edx, edx; Val
0x180032a97  lea     rcx, [rbp+0B70h+var_480]; void *
0x180032a9e  mov     r8d, 2C8h; Size
0x180032aa4  call    memset_0
0x180032aa9  lea     rdx, [rsp+0C70h+Wow64Process]; Wow64Process
0x180032aae  mov     qword ptr [rsp+0C70h+CreationTime.dwLowDateTime], r12
0x180032ab3  mov     rcx, rbx; hProcess
0x180032ab6  mov     qword ptr [rsp+0C70h+ExitTime.dwLowDateTime], r12
0x180032abb  mov     [rsp+0C70h+var_C3C], 1
0x180032ac3  call    cs:__imp_IsWow64Process
0x180032ac9  test    eax, eax
0x180032acb  jz      short loc_180032AD9
0x180032acd  cmp     [rsp+0C70h+Wow64Process], r12d
0x180032ad2  jz      short loc_180032AD9
0x180032ad4  mov     [rsp+0C70h+var_C3C], r12d
0x180032ad9  mov     rdx, [rdi+0B8h]; lpBaseAddress
0x180032ae0  mov     [rsp+0C70h+NumberOfBytesRead], r12
0x180032ae5  test    rdx, rdx
0x180032ae8  jz      short loc_180032B4D
0x180032aea  lea     rax, [rsp+0C70h+NumberOfBytesRead]
0x180032aef  mov     edi, 4D0h
0x180032af4  mov     r9d, edi; nSize
0x180032af7  mov     [rsp+0C70h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x180032afc  lea     r8, [rsp+0C70h+Buffer]; lpBuffer
0x180032b01  mov     rcx, rbx; hProcess
0x180032b04  call    cs:__imp_ReadProcessMemory
0x180032b0a  mov     [rsp+0C70h+Wow64Process], eax
0x180032b0e  test    eax, eax
0x180032b10  jz      short loc_180032B4D
0x180032b12  cmp     [rsp+0C70h+NumberOfBytesRead], rdi
0x180032b17  jnz     short loc_180032B4D
0x180032b19  mov     rdx, [rbp+0B70h+lpBaseAddress]; lpBaseAddress
0x180032b1d  mov     rax, [rbp+0B70h+var_BA0]
0x180032b21  mov     [rbp+0B70h+var_480], rax
0x180032b28  test    rdx, rdx
0x180032b2b  jz      short loc_180032B4D
0x180032b2d  lea     rax, [rsp+0C70h+NumberOfBytesRead]
0x180032b32  mov     r9d, 8; nSize
0x180032b38  lea     r8, [rbp+0B70h+var_750]; lpBuffer
0x180032b3f  mov     [rsp+0C70h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x180032b44  mov     rcx, rbx; hProcess
0x180032b47  call    cs:__imp_ReadProcessMemory
0x180032b4d  lea     rax, [rsp+0C70h+ExitTime]
0x180032b52  mov     rcx, rbx; hProcess
0x180032b55  lea     r9, [rsp+0C70h+ExitTime]; lpKernelTime
0x180032b5a  mov     [rsp+0C70h+lpNumberOfBytesRead], rax; lpUserTime
0x180032b5f  lea     r8, [rsp+0C70h+ExitTime]; lpExitTime
0x180032b64  lea     rdx, [rsp+0C70h+CreationTime]; lpCreationTime
0x180032b69  call    cs:__imp_GetProcessTimes
0x180032b6f  mov     [rsp+0C70h+Wow64Process], eax
0x180032b73  lea     rdi, WPP_GLOBAL_Control
0x180032b7a  test    eax, eax
0x180032b7c  jnz     short loc_180032BC6
0x180032b7e  mov     rax, cs:WPP_GLOBAL_Control
0x180032b85  cmp     rax, rdi
0x180032b88  jz      short loc_180032BC1
0x180032b8a  test    byte ptr [rax+1Ch], 2
0x180032b8e  jz      short loc_180032BC1
0x180032b90  call    cs:__imp_GetLastError
0x180032b96  test    eax, eax
0x180032b98  jle     short loc_180032BA2
0x180032b9a  movzx   eax, ax
0x180032b9d  or      eax, 80070000h
0x180032ba2  mov     rcx, cs:WPP_GLOBAL_Control
0x180032ba9  lea     r8, WPP_5d1834416bbb32ed8157f52948dd8803_Traceguids
0x180032bb0  mov     edx, 0Ah
0x180032bb5  mov     r9d, eax
0x180032bb8  mov     rcx, [rcx+10h]
0x180032bbc  call    WPP_SF_d
0x180032bc1  mov     qword ptr [rsp+0C70h+CreationTime.dwLowDateTime], r12
0x180032bc6  cmp     [rbp+0B70h+var_480], r12
0x180032bcd  jz      short loc_180032BE7
0x180032bcf  mov     r9d, 1; int
0x180032bd5  lea     rcx, [rbp+0B70h+var_480]; struct TI_ADDRESS_INFO *
0x180032bdc  mov     r8, r14; void *
0x180032bdf  mov     rdx, rbx; void *
0x180032be2  call    ?FillCallInfo@CTIPlugin@@CAXPEAUTI_ADDRESS_INFO@@PEAX1H@Z; CTIPlugin::FillCallInfo(TI_ADDRESS_INFO *,void *,void *,int)
0x180032be7  cmp     [rbp+0B70h+var_750], r12
0x180032bee  jz      short loc_180032C05
0x180032bf0  xor     r9d, r9d; int
0x180032bf3  lea     rcx, [rbp+0B70h+var_750]; struct TI_ADDRESS_INFO *
0x180032bfa  mov     r8, r14; void *
0x180032bfd  mov     rdx, rbx; void *
0x180032c00  call    ?FillCallInfo@CTIPlugin@@CAXPEAUTI_ADDRESS_INFO@@PEAX1H@Z; CTIPlugin::FillCallInfo(TI_ADDRESS_INFO *,void *,void *,int)
0x180032c05  mov     [rbp+0B70h+var_1B0], rsi
0x180032c0c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180032c10  inc     rax
0x180032c13  cmp     [rsi+rax*2], r12w
0x180032c18  jnz     short loc_180032C10
0x180032c1a  lea     eax, ds:2[rax*2]
0x180032c21  mov     [rbp+0B70h+var_1A4], r12d
0x180032c28  mov     [rbp+0B70h+var_1A8], eax
0x180032c2e  lea     r8, [rbp+0B70h+var_750]; struct TI_ADDRESS_INFO *
0x180032c35  lea     rax, [rbp+0B70h+arg_18]
0x180032c3c  mov     [rbp+0B70h+var_198], 4
0x180032c47  mov     [rbp+0B70h+var_1A0], rax
0x180032c4e  lea     rcx, [rbp+0B70h+var_170]; struct _EVENT_DATA_DESCRIPTOR *
0x180032c55  lea     rax, [rsp+0C70h+CreationTime]
0x180032c5a  mov     [rbp+0B70h+var_188], 8
0x180032c65  mov     [rbp+0B70h+var_190], rax
0x180032c6c  lea     rax, [rsp+0C70h+var_C3C]
0x180032c71  mov     [rbp+0B70h+var_180], rax
0x180032c78  mov     [rbp+0B70h+var_178], 4
0x180032c83  call    ?EventDataDescCreateTICallAddressInfo@CTIPlugin@@CAKPEAU_EVENT_DATA_DESCRIPTOR@@KPEBUTI_ADDRESS_INFO@@@Z; CTIPlugin::EventDataDescCreateTICallAddressInfo(_EVENT_DATA_DESCRIPTOR *,ulong,TI_ADDRESS_INFO const *)
0x180032c88  lea     rcx, [rbp+0B70h+var_1B0]
0x180032c8f  lea     r8, [rbp+0B70h+var_480]; struct TI_ADDRESS_INFO *
0x180032c96  lea     r9d, [rax+4]
0x180032c9a  mov     eax, r9d
0x180032c9d  shl     rax, 4
0x180032ca1  add     rcx, rax; struct _EVENT_DATA_DESCRIPTOR *
0x180032ca4  call    ?EventDataDescCreateTICallAddressInfo@CTIPlugin@@CAKPEAU_EVENT_DATA_DESCRIPTOR@@KPEBUTI_ADDRESS_INFO@@@Z; CTIPlugin::EventDataDescCreateTICallAddressInfo(_EVENT_DATA_DESCRIPTOR *,ulong,TI_ADDRESS_INFO const *)
0x180032ca9  add     eax, r9d
0x180032cac  cmp     eax, 18h
0x180032caf  jz      short loc_180032CB6
0x180032cb1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180032cb6  lea     r9, [rbp+0B70h+var_1B0]
0x180032cbd  mov     r8d, 18h
0x180032cc3  lea     rdx, EVENT_CFG_VIOLATION
0x180032cca  lea     rcx, S_MICROSOFT_WINDOWS_WER_DIAG
0x180032cd1  call    cs:__imp_EtwEventWriteNoRegistration
0x180032cd7  mov     [rsp+0C70h+Wow64Process], eax
0x180032cdb  test    eax, eax
0x180032cdd  jz      short loc_180032D09
0x180032cdf  mov     rcx, cs:WPP_GLOBAL_Control
0x180032ce6  cmp     rcx, rdi
0x180032ce9  jz      short loc_180032D09
0x180032ceb  test    byte ptr [rcx+1Ch], 2
0x180032cef  jz      short loc_180032D09
0x180032cf1  mov     rcx, [rcx+10h]
0x180032cf5  lea     r8, WPP_5d1834416bbb32ed8157f52948dd8803_Traceguids
0x180032cfc  mov     edx, 0Bh
0x180032d01  mov     r9d, eax
0x180032d04  call    WPP_SF_d
0x180032d09  mov     rcx, [rbp+0B70h+var_30]
0x180032d10  xor     rcx, rsp; StackCookie
0x180032d13  call    __security_check_cookie
0x180032d18  mov     rbx, [rsp+0C70h+arg_10]
0x180032d20  add     rsp, 0C50h
0x180032d27  pop     r14
0x180032d29  pop     r12
0x180032d2b  pop     rdi
0x180032d2c  pop     rsi
0x180032d2d  pop     rbp
0x180032d2e  retn
```
