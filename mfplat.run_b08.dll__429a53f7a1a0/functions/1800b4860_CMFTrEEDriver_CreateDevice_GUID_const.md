# CMFTrEEDriver::CreateDevice(_GUID const &)

- ea: `0x1800b4860`
- end: `0x1800b4b03`
- name: `?CreateDevice@CMFTrEEDriver@@IEAAJAEBU_GUID@@@Z`
- size: `675`
- prototype: `int(CMFTrEEDriver *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callers

- `0x18018d948`

## callees

- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x1800a0a24`
- `0x1800b4860`
- `0x1801200d0`
- `0x180120ecc`
- `0x180125918`
- `0x180125958`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4a1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4a1f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b4a0b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b4a0b`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_ListW` at `0x1800b48ca`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_ListW` at `0x1800b48ca`

## string_xrefs

- `0x1800b4890`: `CMFTrEEDriver::CreateDevice`
- `0x1800b4978`: `CMFTrEEDriver::CreateDevice`
- `0x1800b4aa8`: `CMFTrEEDriver::CreateDevice`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMFTrEEDriver::CreateDevice(CMFTrEEDriver *this, struct _GUID *a2)
{
  int v4; // ebx
  CONFIGRET Device_Interface_ListW; // eax
  int v6; // edx
  CallStackTracing *v7; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v9; // rdx
  HANDLE FileW; // rax
  signed int LastError; // eax
  int v12; // edx
  CallStackTracing *v13; // rcx
  struct CallStackContext *v14; // rax
  CallStackScopeTrace v16; // [rsp+40h] [rbp-828h] BYREF
  WCHAR Buffer[1024]; // [rsp+50h] [rbp-818h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(&v16, "CMFTrEEDriver::CreateDevice", 280);
  v4 = 0;
  memset_0(Buffer, 0, sizeof(Buffer));
  Device_Interface_ListW = CM_Get_Device_Interface_ListW(a2, 0, Buffer, 0x400u, 0);
  if ( !Device_Interface_ListW )
    goto LABEL_15;
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM >= 2u )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      34,
      &WPP_453d7342e50836af18c1bd3f8b6e482b_Traceguids,
      Device_Interface_ListW);
  v4 = MF::OriginateError((MF *)0x8000FFFFLL, v6);
  if ( v4 < 0 )
  {
    v7 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v7 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v7->m_fEnabled )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v7);
      if ( ThreadRelativeContext->m_result != v4 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFTrEEDriver::CreateDevice", 294, v4);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v9 = 35;
LABEL_14:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_453d7342e50836af18c1bd3f8b6e482b_Traceguids, this, v4);
    }
  }
  else
  {
LABEL_15:
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM >= 2u )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_453d7342e50836af18c1bd3f8b6e482b_Traceguids, Buffer);
    FileW = CreateFileW(Buffer, 3u, 0, 0, 3u, 0x40000000u, 0);
    *((_QWORD *)this + 5) = FileW;
    if ( FileW != (HANDLE)-1LL )
      goto LABEL_30;
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v4 = MF::OriginateError((MF *)(unsigned int)LastError, v12);
    if ( v4 >= 0 )
    {
LABEL_30:
      *((struct _GUID *)this + 4) = *a2;
      goto LABEL_31;
    }
    v13 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v13 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v13->m_fEnabled )
    {
      v14 = CallStackTracing::GetThreadRelativeContext(v13);
      if ( v14->m_result != v4 )
        CallStackContext::TraceFailure(v14, "CMFTrEEDriver::CreateDevice", 308, v4);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v9 = 37;
      goto LABEL_14;
    }
  }
LABEL_31:
  CallStackScopeTrace::~CallStackScopeTrace(&v16);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800b4860  mov     [rsp+arg_10], rbx
0x1800b4865  mov     [rsp+arg_18], rsi
0x1800b486a  push    rdi
0x1800b486b  sub     rsp, 860h
0x1800b4872  mov     rax, cs:__security_cookie
0x1800b4879  xor     rax, rsp
0x1800b487c  mov     [rsp+868h+var_18], rax
0x1800b4884  mov     rsi, rdx
0x1800b4887  mov     rdi, rcx
0x1800b488a  mov     r8d, 118h; int
0x1800b4890  lea     rdx, aCmftreedriverC_0; "CMFTrEEDriver::CreateDevice"
0x1800b4897  lea     rcx, [rsp+868h+var_828]; this
0x1800b489c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b48a1  nop
0x1800b48a2  xor     ebx, ebx
0x1800b48a4  xor     edx, edx; Val
0x1800b48a6  mov     r8d, 800h; Size
0x1800b48ac  lea     rcx, [rsp+868h+Buffer]; void *
0x1800b48b1  call    memset_0
0x1800b48b6  mov     [rsp+868h+ulFlags], ebx; ulFlags
0x1800b48ba  mov     r9d, 400h; BufferLen
0x1800b48c0  lea     r8, [rsp+868h+Buffer]; Buffer
0x1800b48c5  xor     edx, edx; pDeviceID
0x1800b48c7  mov     rcx, rsi; InterfaceClassGuid
0x1800b48ca  call    cs:__imp_CM_Get_Device_Interface_ListW
0x1800b48d0  test    eax, eax
0x1800b48d2  jz      loc_1800B49BC
0x1800b48d8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 2; MFWppLevels g_wppLevels
0x1800b48df  jb      short loc_1800B48FE
0x1800b48e1  lea     edx, [rbx+22h]
0x1800b48e4  mov     r9d, eax
0x1800b48e7  lea     r8, WPP_453d7342e50836af18c1bd3f8b6e482b_Traceguids
0x1800b48ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b48f5  mov     rcx, [rcx+10h]
0x1800b48f9  call    WPP_SF_d
0x1800b48fe  mov     ecx, 8000FFFFh; this
0x1800b4903  call    ?OriginateError@MF@@YAJJ@Z; MF::OriginateError(long)
0x1800b4908  mov     ebx, eax
0x1800b490a  test    eax, eax
0x1800b490c  jns     loc_1800B49BC
0x1800b4912  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4919  test    rcx, rcx
0x1800b491c  jnz     short loc_1800B495C
0x1800b491e  lea     rcx, stru_1801FC290
0x1800b4925  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b492c  mov     rdx, cs:stru_1801FC290.__vftable
0x1800b4933  mov     rax, [rdx+8]
0x1800b4937  mov     edx, 7F0h
0x1800b493c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4941  test    eax, eax
0x1800b4943  jnz     short loc_1800B4955
0x1800b4945  lea     rcx, stru_1801F8A30
0x1800b494c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4953  jmp     short loc_1800B495C
0x1800b4955  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800b495c  cmp     byte ptr [rcx+8], 0
0x1800b4960  jz      short loc_1800B4987
0x1800b4962  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b4967  cmp     [rax+7CCh], ebx
0x1800b496d  jz      short loc_1800B4987
0x1800b496f  mov     r9d, ebx; int
0x1800b4972  mov     r8d, 126h; int
0x1800b4978  lea     rdx, aCmftreedriverC_0; "CMFTrEEDriver::CreateDevice"
0x1800b497f  mov     rcx, rax; this
0x1800b4982  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b4987  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b498e  jb      loc_1800B4AD2
0x1800b4994  mov     edx, 23h ; '#'
0x1800b4999  mov     [rsp+868h+ulFlags], ebx
0x1800b499d  mov     r9, rdi
0x1800b49a0  lea     r8, WPP_453d7342e50836af18c1bd3f8b6e482b_Traceguids
0x1800b49a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b49ae  mov     rcx, [rcx+10h]
0x1800b49b2  call    WPP_SF_qD
0x1800b49b7  jmp     loc_1800B4AD2
0x1800b49bc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 2; MFWppLevels g_wppLevels
0x1800b49c3  jb      short loc_1800B49E6
0x1800b49c5  mov     edx, 24h ; '$'
0x1800b49ca  lea     r9, [rsp+868h+Buffer]
0x1800b49cf  lea     r8, WPP_453d7342e50836af18c1bd3f8b6e482b_Traceguids
0x1800b49d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b49dd  mov     rcx, [rcx+10h]
0x1800b49e1  call    WPP_SF_S
0x1800b49e6  mov     [rsp+868h+hTemplateFile], 0; hTemplateFile
0x1800b49ef  mov     [rsp+868h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x1800b49f7  mov     edx, 3; dwDesiredAccess
0x1800b49fc  mov     [rsp+868h+ulFlags], edx; dwCreationDisposition
0x1800b4a00  xor     r9d, r9d; lpSecurityAttributes
0x1800b4a03  xor     r8d, r8d; dwShareMode
0x1800b4a06  lea     rcx, [rsp+868h+Buffer]; lpFileName
0x1800b4a0b  call    cs:__imp_CreateFileW
0x1800b4a11  mov     [rdi+28h], rax
0x1800b4a15  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800b4a19  jnz     loc_1800B4ACA
0x1800b4a1f  call    cs:__imp_GetLastError
0x1800b4a25  test    eax, eax
0x1800b4a27  jle     short loc_1800B4A31
0x1800b4a29  movzx   eax, ax
0x1800b4a2c  or      eax, 80070000h
0x1800b4a31  mov     ecx, eax; this
0x1800b4a33  call    ?OriginateError@MF@@YAJJ@Z; MF::OriginateError(long)
0x1800b4a38  mov     ebx, eax
0x1800b4a3a  test    eax, eax
0x1800b4a3c  jns     loc_1800B4ACA
0x1800b4a42  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4a49  test    rcx, rcx
0x1800b4a4c  jnz     short loc_1800B4A8C
0x1800b4a4e  lea     rcx, stru_1801FC290
0x1800b4a55  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4a5c  mov     rax, cs:stru_1801FC290.__vftable
0x1800b4a63  mov     edx, 7F0h
0x1800b4a68  mov     rax, [rax+8]
0x1800b4a6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4a71  test    eax, eax
0x1800b4a73  jnz     short loc_1800B4A85
0x1800b4a75  lea     rcx, stru_1801F8A30
0x1800b4a7c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4a83  jmp     short loc_1800B4A8C
0x1800b4a85  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800b4a8c  cmp     byte ptr [rcx+8], 0
0x1800b4a90  jz      short loc_1800B4AB7
0x1800b4a92  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b4a97  cmp     [rax+7CCh], ebx
0x1800b4a9d  jz      short loc_1800B4AB7
0x1800b4a9f  mov     r9d, ebx; int
0x1800b4aa2  mov     r8d, 134h; int
0x1800b4aa8  lea     rdx, aCmftreedriverC_0; "CMFTrEEDriver::CreateDevice"
0x1800b4aaf  mov     rcx, rax; this
0x1800b4ab2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b4ab7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b4abe  jb      short loc_1800B4AD2
0x1800b4ac0  mov     edx, 25h ; '%'
0x1800b4ac5  jmp     loc_1800B4999
0x1800b4aca  movups  xmm0, xmmword ptr [rsi]
0x1800b4acd  movdqu  xmmword ptr [rdi+40h], xmm0
0x1800b4ad2  lea     rcx, [rsp+868h+var_828]; this
0x1800b4ad7  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800b4adc  mov     eax, ebx
0x1800b4ade  mov     rcx, [rsp+868h+var_18]
0x1800b4ae6  xor     rcx, rsp; StackCookie
0x1800b4ae9  call    __security_check_cookie
0x1800b4aee  lea     r11, [rsp+868h+var_8]
0x1800b4af6  mov     rbx, [r11+20h]
0x1800b4afa  mov     rsi, [r11+28h]
0x1800b4afe  mov     rsp, r11
0x1800b4b01  pop     rdi
0x1800b4b02  retn
```
