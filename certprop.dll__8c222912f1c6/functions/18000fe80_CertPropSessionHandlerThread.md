# CertPropSessionHandlerThread

- ea: `0x18000fe80`
- end: `0x1800103e4`
- name: `CertPropSessionHandlerThread`
- size: `1380`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, unsigned int *Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002df0`
- `0x180004600`
- `0x1800061c0`
- `0x18000d588`
- `0x18000d7c0`
- `0x18000fe80`
- `0x180014210`
- `0x180014fa8`
- `0x180016090`
- `0x180018bb4`
- `0x180018d78`
- `0x180018e7c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000fec7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000fed6`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180010395`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000fec7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000fed6`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180010395`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ff6e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180010386`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ff6e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180010386`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800102ea`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800102ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800102dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800102dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010091`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010193`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010091`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010193`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010009`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010009`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180010074`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180010074`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010053`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010082`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010053`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010082`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010064`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800100a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010064`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800100a0`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180010049`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180010049`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180010199`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180010199`
- `WTSAPI32!WTSQueryUserToken` at `0x180010019`
- `WTSAPI32!WTSQueryUserToken` at `0x180010019`

## pseudocode

```c
void __fastcall CertPropSessionHandlerThread(PTP_CALLBACK_INSTANCE Instance, unsigned int *Context, PTP_WORK Work)
{
  __int64 v5; // rcx
  int v6; // ebx
  ULONG v7; // ebx
  int v8; // r9d
  DWORD LastError; // ebx
  void *v10; // rcx
  STRSAFE_LPSTR v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rcx
  char v16; // bl
  int LocalCerts; // eax
  __int64 v18; // rcx
  char v19; // bl
  int v20; // r9d
  void *phNewToken; // [rsp+40h] [rbp-69h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-61h] BYREF
  GUID ActivityId; // [rsp+58h] [rbp-51h] BYREF
  GUID v24; // [rsp+68h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+78h] [rbp-31h] BYREF
  char *v26; // [rsp+88h] [rbp-21h]
  int v27; // [rsp+90h] [rbp-19h]
  int v28; // [rsp+94h] [rbp-15h]
  struct _EVENT_DATA_DESCRIPTOR v29; // [rsp+98h] [rbp-11h] BYREF
  char *v30; // [rsp+A8h] [rbp-1h]
  int v31; // [rsp+B0h] [rbp+7h]
  int v32; // [rsp+B4h] [rbp+Bh]
  void **p_phNewToken; // [rsp+B8h] [rbp+Fh]
  __int64 v34; // [rsp+C0h] [rbp+17h]

  ActivityId = 0;
  v24 = 0;
  EventActivityIdControl(5u, &ActivityId);
  EventActivityIdControl(1u, &v24);
  if ( (unsigned int)dword_180031008 > 5 )
  {
    *(_DWORD *)&EventDescriptor.Level = 261;
    UserData.Ptr = (ULONGLONG)off_180031010;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_180031010;
    v26 = byte_180029A01;
    UserData.Reserved = 2;
    v27 = 27;
    v28 = 1;
    LODWORD(phNewToken) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, &v24, &ActivityId, 2u, &UserData);
  }
  if ( Context )
  {
    if ( g_fShutdownInProgress )
    {
      v6 = 1115;
    }
    else
    {
      v6 = 0;
      switch ( *Context )
      {
        case 1u:
        case 5u:
          goto LABEL_32;
        case 2u:
        case 6u:
          CertPropHandleNonRemovableCerts(Context[1], 1);
          goto LABEL_52;
        case 3u:
          v7 = Context[1];
          phNewToken = 0;
          WppTraceIndent(&_ImageBase, 2);
          if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control[28] & 1) != 0
            && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
          {
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              62,
              (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
              v8,
              v7);
          }
          EnterCriticalSection(&g_csSessionList);
          *(_QWORD *)&EventDescriptor.Id = 0;
          if ( !WTSQueryUserToken(v7, (PHANDLE)&EventDescriptor)
            || (LastError = 0,
                !DuplicateTokenEx(
                   *(HANDLE *)&EventDescriptor.Id,
                   0xEu,
                   0,
                   SecurityImpersonation,
                   TokenImpersonation,
                   &phNewToken)) )
          {
            LastError = GetLastError();
          }
          if ( *(_QWORD *)&EventDescriptor.Id )
            CloseHandle(*(HANDLE *)&EventDescriptor.Id);
          if ( LastError )
            goto LABEL_20;
          if ( SetThreadToken(0, phNewToken) )
          {
            LastError = DeleteNonRemovableCertificatesFromUserStore(0);
            if ( LastError )
            {
              WppTraceIndent(v13, 2);
              if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
                && (WPP_GLOBAL_Control[28] & 1) != 0
                && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
              {
                WPP_SF_sD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  63,
                  (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
                  WPP_pszIndent,
                  LastError);
              }
            }
            LeaveCriticalSection(&g_csSessionList);
            RevertToSelf();
          }
          else
          {
            LastError = GetLastError();
LABEL_20:
            LeaveCriticalSection(&g_csSessionList);
          }
          v10 = phNewToken;
          if ( phNewToken )
            CloseHandle(phNewToken);
          WppTraceIndent(v10, 2);
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control[28] & 1) != 0
            && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
          {
            WPP_SF_sD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              64,
              (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
              WPP_pszIndent,
              LastError);
          }
          if ( LastError )
          {
            WppTraceIndent(v11, 2);
            if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control[28] & 1) != 0
              && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
            {
              WPP_SF_sD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                65,
                (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
                WPP_pszIndent,
                LastError);
            }
          }
LABEL_32:
          v12 = CertPropAddSession(Context[1], 0);
          goto LABEL_53;
        case 4u:
          v14 = CertPropHandleNonRemovableCerts(Context[1], 0);
          v16 = v14;
          if ( v14 )
          {
            WppTraceIndent(v15, 2);
            if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control[28] & 1) != 0
              && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
            {
              WPP_SF_sD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                67,
                (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
                WPP_pszIndent,
                v16);
            }
          }
          LocalCerts = CertPropLoadLocalCerts(Context[1]);
          v19 = LocalCerts;
          if ( LocalCerts )
          {
            WppTraceIndent(v18, 2);
            if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control[28] & 1) != 0
              && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
            {
              WPP_SF_sD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                68,
                (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
                WPP_pszIndent,
                v19);
            }
          }
LABEL_52:
          v12 = CertPropDeleteSession(Context[1]);
          goto LABEL_53;
        case 7u:
          v12 = CertPropChangeStatus(Context[1], 0);
          goto LABEL_53;
        case 8u:
          v12 = CertPropChangeStatus(Context[1], 1);
LABEL_53:
          v6 = v12;
          break;
        default:
          break;
      }
    }
  }
  else
  {
    v6 = 87;
  }
  WppTraceIndent(v5, 2);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
  {
    WPP_SF_sddD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      69,
      (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
      v20,
      *Context,
      Context[1],
      v6);
  }
  if ( Context )
    HeapFree(g_hHeap, 0, Context);
  if ( Work )
    CloseThreadpoolWork(Work);
  if ( (unsigned int)dword_180031008 > 5 )
  {
    LODWORD(phNewToken) = v6;
    p_phNewToken = &phNewToken;
    v29.Ptr = (ULONGLONG)off_180031010;
    v34 = 4;
    UserData.Ptr = 0x2050B000000LL;
    *(_QWORD *)&UserData.Size = 0;
    v29.Size = *(unsigned __int16 *)off_180031010;
    v30 = &byte_180029917;
    v29.Reserved = 2;
    v31 = 35;
    v32 = 1;
    *(_DWORD *)&EventDescriptor.Id = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&UserData, &v24, &ActivityId, 3u, &v29);
  }
  EventActivityIdControl(2u, &ActivityId);
}

```

## disassembly

```asm
0x18000fe80  mov     [rsp-8+arg_0], rbx
0x18000fe85  push    rbp
0x18000fe86  push    rsi
0x18000fe87  push    rdi
0x18000fe88  push    r12
0x18000fe8a  push    r13
0x18000fe8c  push    r14
0x18000fe8e  push    r15
0x18000fe90  lea     rbp, [rsp-27h]
0x18000fe95  sub     rsp, 0D0h
0x18000fe9c  mov     rax, cs:__security_cookie
0x18000fea3  xor     rax, rsp
0x18000fea6  mov     [rbp+57h+var_38], rax
0x18000feaa  mov     rdi, rdx
0x18000fead  xorps   xmm0, xmm0
0x18000feb0  xorps   xmm1, xmm1
0x18000feb3  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x18000feb7  mov     ecx, 5; ControlCode
0x18000febc  mov     rsi, r8
0x18000febf  movups  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x18000fec3  movups  xmmword ptr [rbp+57h+var_98.Data1], xmm1
0x18000fec7  call    cs:__imp_EventActivityIdControl
0x18000fecd  lea     rdx, [rbp+57h+var_98]; ActivityId
0x18000fed1  mov     ecx, 1; ControlCode
0x18000fed6  call    cs:__imp_EventActivityIdControl
0x18000fedc  mov     eax, cs:dword_180031008
0x18000fee2  lea     r14, _TraceLoggingMetadataEnd
0x18000fee9  xor     r12d, r12d
0x18000feec  lea     r13, _TraceLoggingMetadata
0x18000fef3  cmp     eax, 5
0x18000fef6  jbe     short loc_18000FF74
0x18000fef8  movzx   eax, cs:word_1800299F7
0x18000feff  lea     r9, [rbp+57h+ActivityId]; RelatedActivityId
0x18000ff03  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18000ff06  lea     r8, [rbp+57h+var_98]; ActivityId
0x18000ff0a  mov     rax, cs:off_180031010
0x18000ff11  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18000ff15  mov     [rbp+57h+var_88.Ptr], rax
0x18000ff19  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18000ff20  mov     [rbp+57h+EventDescriptor.Keyword], r12
0x18000ff24  movzx   eax, word ptr [rax]
0x18000ff27  mov     [rbp+57h+var_88.Size], eax
0x18000ff2a  lea     rax, byte_180029A01
0x18000ff31  mov     [rbp+57h+var_78], rax
0x18000ff35  mov     rax, r14
0x18000ff38  sub     eax, r13d
0x18000ff3b  mov     dword ptr [rbp+57h+var_88.0Ch], 2
0x18000ff42  mov     [rbp+57h+var_70], 1Bh
0x18000ff49  mov     [rbp+57h+var_6C], 1
0x18000ff50  mov     dword ptr [rbp+57h+phNewToken], eax
0x18000ff53  mov     eax, dword ptr [rbp+57h+phNewToken]
0x18000ff56  mov     rcx, cs:RegHandle; RegHandle
0x18000ff5d  lea     rax, [rbp+57h+var_88]
0x18000ff61  mov     [rsp+100h+UserData], rax; UserData
0x18000ff66  mov     [rsp+100h+UserDataCount], 2; UserDataCount
0x18000ff6e  call    cs:__imp_EventWriteTransfer
0x18000ff74  lea     r15, WPP_GLOBAL_Control
0x18000ff7b  test    rdi, rdi
0x18000ff7e  jnz     short loc_18000FF8A
0x18000ff80  mov     ebx, 57h ; 'W'
0x18000ff85  jmp     def_18000FFBE; jumptable 000000018000FFBE default case
0x18000ff8a  cmp     cs:g_fShutdownInProgress, r12d
0x18000ff91  jz      short loc_18000FF9D
0x18000ff93  mov     ebx, 45Bh
0x18000ff98  jmp     def_18000FFBE; jumptable 000000018000FFBE default case
0x18000ff9d  mov     eax, [rdi]
0x18000ff9f  mov     ebx, r12d
0x18000ffa2  dec     eax; switch 8 cases
0x18000ffa4  cmp     eax, 7
0x18000ffa7  ja      def_18000FFBE; jumptable 000000018000FFBE default case
0x18000ffad  lea     rcx, __ImageBase
0x18000ffb4  mov     eax, ds:(jpt_18000FFBE - 180000000h)[rcx+rax*4]
0x18000ffbb  add     rax, rcx
0x18000ffbe  jmp     rax; switch jump
0x18000ffc0  mov     ebx, [rdi+4]; jumptable 000000018000FFBE case 3
0x18000ffc3  mov     edx, 2
0x18000ffc8  mov     [rbp+57h+phNewToken], r12
0x18000ffcc  call    WppTraceIndent
0x18000ffd1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ffd8  cmp     rcx, r15
0x18000ffdb  jz      short loc_180010002
0x18000ffdd  test    byte ptr [rcx+1Ch], 1
0x18000ffe1  jz      short loc_180010002
0x18000ffe3  cmp     byte ptr [rcx+19h], 5
0x18000ffe7  jb      short loc_180010002
0x18000ffe9  mov     rcx, [rcx+10h]
0x18000ffed  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x18000fff4  mov     edx, 3Eh ; '>'
0x18000fff9  mov     [rsp+100h+UserDataCount], ebx
0x18000fffd  call    WPP_SF_sd
0x180010002  lea     rcx, g_csSessionList; lpCriticalSection
0x180010009  call    cs:__imp_EnterCriticalSection
0x18001000f  lea     rdx, [rbp+57h+EventDescriptor]; phToken
0x180010013  mov     qword ptr [rbp+57h+EventDescriptor.Id], r12
0x180010017  mov     ecx, ebx; SessionId
0x180010019  call    cs:__imp_WTSQueryUserToken
0x18001001f  test    eax, eax
0x180010021  jz      short loc_180010053
0x180010023  mov     rcx, qword ptr [rbp+57h+EventDescriptor.Id]; hExistingToken
0x180010027  lea     rax, [rbp+57h+phNewToken]
0x18001002b  mov     [rsp+100h+UserData], rax; phNewToken
0x180010030  mov     r9d, 2; ImpersonationLevel
0x180010036  xor     r8d, r8d; lpTokenAttributes
0x180010039  mov     [rsp+100h+UserDataCount], 2; TokenType
0x180010041  mov     edx, 0Eh; dwDesiredAccess
0x180010046  mov     ebx, r12d
0x180010049  call    cs:__imp_DuplicateTokenEx
0x18001004f  test    eax, eax
0x180010051  jnz     short loc_18001005B
0x180010053  call    cs:__imp_GetLastError
0x180010059  mov     ebx, eax
0x18001005b  mov     rcx, qword ptr [rbp+57h+EventDescriptor.Id]; hObject
0x18001005f  test    rcx, rcx
0x180010062  jz      short loc_18001006A
0x180010064  call    cs:__imp_CloseHandle
0x18001006a  test    ebx, ebx
0x18001006c  jnz     short loc_18001008A
0x18001006e  mov     rdx, [rbp+57h+phNewToken]; Token
0x180010072  xor     ecx, ecx; Thread
0x180010074  call    cs:__imp_SetThreadToken
0x18001007a  test    eax, eax
0x18001007c  jnz     loc_18001013D
0x180010082  call    cs:__imp_GetLastError
0x180010088  mov     ebx, eax
0x18001008a  lea     rcx, g_csSessionList; lpCriticalSection
0x180010091  call    cs:__imp_LeaveCriticalSection
0x180010097  mov     rcx, [rbp+57h+phNewToken]; hObject
0x18001009b  test    rcx, rcx
0x18001009e  jz      short loc_1800100A6
0x1800100a0  call    cs:__imp_CloseHandle
0x1800100a6  mov     edx, 2
0x1800100ab  call    WppTraceIndent
0x1800100b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800100b7  cmp     rcx, r15
0x1800100ba  jz      short loc_1800100E8
0x1800100bc  test    byte ptr [rcx+1Ch], 1
0x1800100c0  jz      short loc_1800100E8
0x1800100c2  cmp     byte ptr [rcx+19h], 5
0x1800100c6  jb      short loc_1800100E8
0x1800100c8  mov     r9, cs:WPP_pszIndent
0x1800100cf  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x1800100d6  mov     rcx, [rcx+10h]
0x1800100da  mov     edx, 40h ; '@'
0x1800100df  mov     [rsp+100h+UserDataCount], ebx
0x1800100e3  call    WPP_SF_sD
0x1800100e8  test    ebx, ebx
0x1800100ea  jz      short loc_18001012E; jumptable 000000018000FFBE cases 1,5
0x1800100ec  mov     edx, 2
0x1800100f1  call    WppTraceIndent
0x1800100f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800100fd  cmp     rcx, r15
0x180010100  jz      short loc_18001012E; jumptable 000000018000FFBE cases 1,5
0x180010102  test    byte ptr [rcx+1Ch], 1
0x180010106  jz      short loc_18001012E; jumptable 000000018000FFBE cases 1,5
0x180010108  cmp     byte ptr [rcx+19h], 2
0x18001010c  jb      short loc_18001012E; jumptable 000000018000FFBE cases 1,5
0x18001010e  mov     r9, cs:WPP_pszIndent
0x180010115  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x18001011c  mov     rcx, [rcx+10h]
0x180010120  mov     edx, 41h ; 'A'
0x180010125  mov     [rsp+100h+UserDataCount], ebx
0x180010129  call    WPP_SF_sD
0x18001012e  mov     ecx, [rdi+4]; jumptable 000000018000FFBE cases 1,5
0x180010131  xor     edx, edx
0x180010133  call    CertPropAddSession
0x180010138  jmp     loc_180010281
0x18001013d  xor     ecx, ecx; hCertStore
0x18001013f  call    DeleteNonRemovableCertificatesFromUserStore
0x180010144  mov     ebx, eax
0x180010146  test    eax, eax
0x180010148  jz      short loc_18001018C
0x18001014a  mov     edx, 2
0x18001014f  call    WppTraceIndent
0x180010154  mov     rcx, cs:WPP_GLOBAL_Control
0x18001015b  cmp     rcx, r15
0x18001015e  jz      short loc_18001018C
0x180010160  test    byte ptr [rcx+1Ch], 1
0x180010164  jz      short loc_18001018C
0x180010166  cmp     byte ptr [rcx+19h], 2
0x18001016a  jb      short loc_18001018C
0x18001016c  mov     r9, cs:WPP_pszIndent
0x180010173  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x18001017a  mov     rcx, [rcx+10h]
0x18001017e  mov     edx, 3Fh ; '?'
0x180010183  mov     [rsp+100h+UserDataCount], ebx
0x180010187  call    WPP_SF_sD
0x18001018c  lea     rcx, g_csSessionList; lpCriticalSection
0x180010193  call    cs:__imp_LeaveCriticalSection
0x180010199  call    cs:__imp_RevertToSelf
0x18001019f  jmp     loc_180010097
0x1800101a4  mov     ecx, [rdi+4]; jumptable 000000018000FFBE case 7
0x1800101a7  xor     edx, edx
0x1800101a9  call    CertPropChangeStatus
0x1800101ae  jmp     loc_180010281
0x1800101b3  mov     ecx, [rdi+4]; jumptable 000000018000FFBE case 8
0x1800101b6  mov     edx, 1
0x1800101bb  call    CertPropChangeStatus
0x1800101c0  jmp     loc_180010281
0x1800101c5  mov     ecx, [rdi+4]; jumptable 000000018000FFBE cases 2,6
0x1800101c8  mov     edx, 1
0x1800101cd  call    CertPropHandleNonRemovableCerts
0x1800101d2  jmp     loc_180010279
0x1800101d7  mov     ecx, [rdi+4]; jumptable 000000018000FFBE case 4
0x1800101da  xor     edx, edx
0x1800101dc  call    CertPropHandleNonRemovableCerts
0x1800101e1  mov     ebx, eax
0x1800101e3  test    eax, eax
0x1800101e5  jz      short loc_180010229
0x1800101e7  mov     edx, 2
0x1800101ec  call    WppTraceIndent
0x1800101f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800101f8  cmp     rcx, r15
0x1800101fb  jz      short loc_180010229
0x1800101fd  test    byte ptr [rcx+1Ch], 1
0x180010201  jz      short loc_180010229
0x180010203  cmp     byte ptr [rcx+19h], 2
0x180010207  jb      short loc_180010229
0x180010209  mov     r9, cs:WPP_pszIndent
0x180010210  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x180010217  mov     rcx, [rcx+10h]
0x18001021b  mov     edx, 43h ; 'C'
0x180010220  mov     [rsp+100h+UserDataCount], ebx
0x180010224  call    WPP_SF_sD
0x180010229  mov     ecx, [rdi+4]
0x18001022c  call    CertPropLoadLocalCerts
0x180010231  mov     ebx, eax
0x180010233  test    eax, eax
0x180010235  jz      short loc_180010279
0x180010237  mov     edx, 2
0x18001023c  call    WppTraceIndent
0x180010241  mov     rcx, cs:WPP_GLOBAL_Control
0x180010248  cmp     rcx, r15
0x18001024b  jz      short loc_180010279
0x18001024d  test    byte ptr [rcx+1Ch], 1
0x180010251  jz      short loc_180010279
0x180010253  cmp     byte ptr [rcx+19h], 2
0x180010257  jb      short loc_180010279
0x180010259  mov     r9, cs:WPP_pszIndent
0x180010260  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x180010267  mov     rcx, [rcx+10h]
0x18001026b  mov     edx, 44h ; 'D'
0x180010270  mov     [rsp+100h+UserDataCount], ebx
0x180010274  call    WPP_SF_sD
0x180010279  mov     ecx, [rdi+4]
0x18001027c  call    CertPropDeleteSession
0x180010281  mov     ebx, eax
0x180010283  mov     edx, 2; jumptable 000000018000FFBE default case
0x180010288  call    WppTraceIndent
0x18001028d  mov     rcx, cs:WPP_GLOBAL_Control
0x180010294  cmp     rcx, r15
0x180010297  jz      short loc_1800102CB
0x180010299  test    byte ptr [rcx+1Ch], 1
0x18001029d  jz      short loc_1800102CB
0x18001029f  cmp     byte ptr [rcx+19h], 4
0x1800102a3  jb      short loc_1800102CB
0x1800102a5  mov     eax, [rdi+4]
0x1800102a8  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x1800102af  mov     rcx, [rcx+10h]
0x1800102b3  mov     edx, 45h ; 'E'
0x1800102b8  mov     [rsp+100h+var_D0], ebx
0x1800102bc  mov     dword ptr [rsp+100h+UserData], eax
0x1800102c0  mov     eax, [rdi]
0x1800102c2  mov     [rsp+100h+UserDataCount], eax
0x1800102c6  call    WPP_SF_sddD
0x1800102cb  test    rdi, rdi
0x1800102ce  jz      short loc_1800102E2
0x1800102d0  mov     rcx, cs:g_hHeap; hHeap
0x1800102d7  mov     r8, rdi; lpMem
0x1800102da  xor     edx, edx; dwFlags
0x1800102dc  call    cs:__imp_HeapFree
0x1800102e2  test    rsi, rsi
0x1800102e5  jz      short loc_1800102F0
0x1800102e7  mov     rcx, rsi; pwk
0x1800102ea  call    cs:__imp_CloseThreadpoolWork
0x1800102f0  mov     eax, cs:dword_180031008
0x1800102f6  cmp     eax, 5
0x1800102f9  jbe     loc_18001038C
0x1800102ff  lea     rax, [rbp+57h+phNewToken]
0x180010303  mov     dword ptr [rbp+57h+phNewToken], ebx
0x180010306  mov     [rbp+57h+var_48], rax
0x18001030a  lea     r9, [rbp+57h+ActivityId]; RelatedActivityId
0x18001030e  movzx   eax, cs:word_18002990D
0x180010315  lea     r8, [rbp+57h+var_98]; ActivityId
0x180010319  mov     dword ptr [rbp+57h+var_88.Ptr+4], eax
0x18001031c  lea     rdx, [rbp+57h+var_88]; EventDescriptor
0x180010320  mov     rax, cs:off_180031010
0x180010327  sub     r14d, r13d
0x18001032a  mov     [rbp+57h+var_68.Ptr], rax
0x18001032e  mov     [rbp+57h+var_40], 4
0x180010336  mov     dword ptr [rbp+57h+var_88.Ptr], 0B000000h
0x18001033d  mov     qword ptr [rbp+57h+var_88.Size], r12
0x180010341  movzx   eax, word ptr [rax]
0x180010344  mov     [rbp+57h+var_68.Size], eax
0x180010347  lea     rax, byte_180029917
0x18001034e  mov     [rbp+57h+var_58], rax
0x180010352  mov     dword ptr [rbp+57h+var_68.0Ch], 2
0x180010359  mov     [rbp+57h+var_50], 23h ; '#'
0x180010360  mov     [rbp+57h+var_4C], 1
0x180010367  mov     dword ptr [rbp+57h+EventDescriptor.Id], r14d
0x18001036b  mov     eax, dword ptr [rbp+57h+EventDescriptor.Id]
  ... truncated ...
```
