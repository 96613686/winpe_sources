# DiagnoseRASystemHealth(HWND__ *)

- ea: `0x1400302a0`
- end: `0x140030459`
- name: `?DiagnoseRASystemHealth@@YAJPEAUHWND__@@@Z`
- size: `441`
- prototype: `__int64 __fastcall(HWND)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1400194c8`

## callees

- `0x140002463`
- `0x1400187cc`
- `0x1400302a0`
- `0x140030a44`
- `0x140034ce4`
- `0x14004ad80`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140030426`
- `KERNEL32!HeapFree` at `0x140030426`
- `KERNEL32!GetProcessHeap` at `0x140030412`
- `KERNEL32!GetProcessHeap` at `0x140030412`
- `NDFAPI!NdfCloseIncident` at `0x140030401`
- `NDFAPI!NdfCloseIncident` at `0x140030401`
- `NDFAPI!NdfExecuteDiagnosis` at `0x1400303cf`
- `NDFAPI!NdfExecuteDiagnosis` at `0x1400303cf`
- `NDFAPI!NdfCreateIncident` at `0x1400303ab`
- `NDFAPI!NdfCreateIncident` at `0x1400303ab`

## string_xrefs

- `0x140030353`: `UserSID`
- `0x140030392`: `%systemroot%\system32\msra.exe`

## pseudocode

```c
__int64 __fastcall DiagnoseRASystemHealth(HWND a1)
{
  HRESULT ProcessSID; // eax
  CEventLogger *v2; // rcx
  void *v3; // rdi
  unsigned int v4; // ebx
  unsigned int v5; // r9d
  HRESULT v6; // eax
  HANDLE ProcessHeap; // rax
  int v9; // [rsp+20h] [rbp-E0h]
  NDFHANDLE handle; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID lpMem[3]; // [rsp+38h] [rbp-C8h] BYREF
  HELPER_ATTRIBUTE attributes; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v13; // [rsp+E0h] [rbp-20h]
  int v14; // [rsp+E8h] [rbp-18h]
  LPVOID v15; // [rsp+F0h] [rbp-10h]
  LPVOID v16; // [rsp+F8h] [rbp-8h]
  const wchar_t *v17; // [rsp+170h] [rbp+70h]
  int v18; // [rsp+178h] [rbp+78h]
  const wchar_t *v19; // [rsp+180h] [rbp+80h]
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  handle = 0;
  attributes.pwszName = 0;
  memset_0(&attributes.type, 0, 0x1A8u);
  *(_OWORD *)lpMem = 0;
  ProcessSID = GetProcessSID((struct tagOCTET_STRING *)lpMem);
  v3 = lpMem[1];
  v4 = ProcessSID;
  if ( ProcessSID < 0 )
  {
    v5 = 883;
LABEL_3:
    CEventLogger::LogError(
      v2,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
      v5,
      L"DiagnoseRASystemHealth",
      ProcessSID);
    goto LABEL_9;
  }
  attributes.type = AT_UINT32;
  attributes.pwszName = L"DiagnosisType";
  attributes.Boolean = 1;
  v13 = L"UserSID";
  v15 = lpMem[0];
  v14 = 14;
  v17 = L"AppID";
  v19 = L"%systemroot%\\system32\\msra.exe";
  v16 = lpMem[1];
  v18 = 10;
  ProcessSID = NdfCreateIncident(L"RAHelperClass", 3u, &attributes, &handle);
  v4 = ProcessSID;
  if ( ProcessSID < 0 )
  {
    v5 = 903;
    goto LABEL_3;
  }
  v6 = NdfExecuteDiagnosis(handle, 0);
  v4 = v6;
  if ( v6 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x392,
      (unsigned int)"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
      (const char *)(unsigned int)v6,
      v9);
  NdfCloseIncident(handle);
LABEL_9:
  if ( v3 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3);
  }
  return v4;
}

```

## disassembly

```asm
0x1400302a0  mov     [rsp-8+arg_0], rbx
0x1400302a5  mov     [rsp-8+arg_8], rdi
0x1400302aa  push    rbp
0x1400302ab  lea     rbp, [rsp-110h]
0x1400302b3  sub     rsp, 210h
0x1400302ba  mov     rax, cs:__security_cookie
0x1400302c1  xor     rax, rsp
0x1400302c4  mov     [rbp+110h+var_10], rax
0x1400302cb  xor     edx, edx; Val
0x1400302cd  mov     [rsp+210h+handle], 0
0x1400302d6  mov     r8d, 1A8h; Size
0x1400302dc  mov     [rsp+210h+attributes.pwszName], 0
0x1400302e5  lea     rcx, [rsp+210h+attributes.type]; void *
0x1400302ea  call    memset_0
0x1400302ef  xorps   xmm0, xmm0
0x1400302f2  lea     rcx, [rsp+210h+lpMem]; struct tagOCTET_STRING *
0x1400302f7  movups  xmmword ptr [rsp+210h+lpMem], xmm0
0x1400302fc  call    ?GetProcessSID@@YAJPEAUtagOCTET_STRING@@@Z; GetProcessSID(tagOCTET_STRING *)
0x140030301  mov     rdi, [rsp+210h+lpMem+8]
0x140030306  mov     ebx, eax
0x140030308  test    eax, eax
0x14003030a  jns     short loc_14003033A
0x14003030c  mov     r9d, 373h; unsigned int
0x140030312  mov     [rsp+210h+var_1E8], eax; unsigned int
0x140030316  lea     r8, aBaseDiagnosisR_28; "base\\diagnosis\\ra\\ui\\radiagutils.cp"...
0x14003031d  lea     rax, aDiagnoserasyst; "DiagnoseRASystemHealth"
0x140030324  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14003032b  mov     [rsp+210h+var_1F0], rax; unsigned __int16 *
0x140030330  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140030335  jmp     loc_14003040D
0x14003033a  lea     rax, aDiagnosistype; "DiagnosisType"
0x140030341  mov     [rsp+210h+attributes.type], 7
0x140030349  mov     [rsp+210h+attributes.pwszName], rax
0x14003034e  lea     r9, [rsp+210h+handle]; handle
0x140030353  lea     rax, aUsersid; "UserSID"
0x14003035a  mov     dword ptr [rsp+210h+attributes.10h], 1
0x140030362  mov     [rbp+110h+var_130], rax
0x140030366  lea     r8, [rsp+210h+attributes]; attributes
0x14003036b  mov     rax, [rsp+210h+lpMem]
0x140030370  lea     rcx, helperClassName; "RAHelperClass"
0x140030377  mov     [rbp+110h+var_120], rax
0x14003037b  mov     edx, 3; celt
0x140030380  lea     rax, aAppid_0; "AppID"
0x140030387  mov     [rbp+110h+var_128], 0Eh
0x14003038e  mov     [rbp+110h+var_A0], rax
0x140030392  lea     rax, aSystemrootSyst; "%systemroot%\\system32\\msra.exe"
0x140030399  mov     [rbp+110h+var_90], rax
0x1400303a0  mov     [rbp+110h+var_118], rdi
0x1400303a4  mov     [rbp+110h+var_98], 0Ah
0x1400303ab  call    cs:__imp_NdfCreateIncident
0x1400303b2  nop     dword ptr [rax+rax+00h]
0x1400303b7  mov     ebx, eax
0x1400303b9  test    eax, eax
0x1400303bb  jns     short loc_1400303C8
0x1400303bd  mov     r9d, 387h
0x1400303c3  jmp     loc_140030312
0x1400303c8  mov     rcx, [rsp+210h+handle]; handle
0x1400303cd  xor     edx, edx; hwnd
0x1400303cf  call    cs:__imp_NdfExecuteDiagnosis
0x1400303d6  nop     dword ptr [rax+rax+00h]
0x1400303db  mov     ebx, eax
0x1400303dd  test    eax, eax
0x1400303df  jns     short loc_1400303FC
0x1400303e1  mov     rcx, [rbp+118h]; this
0x1400303e8  lea     r8, aBaseDiagnosisR_22; "base\\diagnosis\\ra\\ui\\radiagutils.cp"...
0x1400303ef  mov     r9d, eax; char *
0x1400303f2  mov     edx, 392h; void *
0x1400303f7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400303fc  mov     rcx, [rsp+210h+handle]; handle
0x140030401  call    cs:__imp_NdfCloseIncident
0x140030408  nop     dword ptr [rax+rax+00h]
0x14003040d  test    rdi, rdi
0x140030410  jz      short loc_140030432
0x140030412  call    cs:__imp_GetProcessHeap
0x140030419  nop     dword ptr [rax+rax+00h]
0x14003041e  mov     r8, rdi; lpMem
0x140030421  xor     edx, edx; dwFlags
0x140030423  mov     rcx, rax; hHeap
0x140030426  call    cs:__imp_HeapFree
0x14003042d  nop     dword ptr [rax+rax+00h]
0x140030432  mov     eax, ebx
0x140030434  mov     rcx, [rbp+110h+var_10]
0x14003043b  xor     rcx, rsp; StackCookie
0x14003043e  call    __security_check_cookie
0x140030443  lea     r11, [rsp+210h+var_s0]
0x14003044b  mov     rbx, [r11+10h]
0x14003044f  mov     rdi, [r11+18h]
0x140030453  mov     rsp, r11
0x140030456  pop     rbp
0x140030457  retn
```
