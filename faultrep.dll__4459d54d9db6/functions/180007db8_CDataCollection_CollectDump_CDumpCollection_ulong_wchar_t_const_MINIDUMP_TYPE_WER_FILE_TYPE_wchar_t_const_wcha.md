# CDataCollection::CollectDump(CDumpCollection *,ulong,wchar_t const *,_MINIDUMP_TYPE,_WER_FILE_TYPE,wchar_t const *,wchar_t *,ulong,int *)

- ea: `0x180007db8`
- end: `0x18000801b`
- name: `?CollectDump@CDataCollection@@AEAAJPEAVCDumpCollection@@KPEB_WW4_MINIDUMP_TYPE@@W4_WER_FILE_TYPE@@1PEA_WKPEAH@Z`
- size: `611`
- prototype: `__int64 __fastcall(CDataCollection *this, struct _RTL_CRITICAL_SECTION *, unsigned int, const wchar_t *, enum _MINIDUMP_TYPE, enum _WER_FILE_TYPE, const wchar_t *, wchar_t *lpFileName, unsigned int, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180009190`

## callees

- `0x180002890`
- `0x180007db8`
- `0x180009ed8`
- `0x180009f00`
- `0x18000a154`
- `0x18003e5a8`
- `0x18003ea08`
- `0x18003f740`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007e82`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007e82`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007e91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007e91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007eba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007f9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007eba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007f9e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180007ed3`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180007ed3`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180007e73`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180007e73`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180007ea1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180007ea1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180007fb0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180007fb0`

## pseudocode

```c
__int64 __fastcall CDataCollection::CollectDump(
        CDataCollection *this,
        struct _RTL_CRITICAL_SECTION *a2,
        unsigned int a3,
        const wchar_t *a4,
        enum _MINIDUMP_TYPE a5,
        enum _WER_FILE_TYPE a6,
        const wchar_t *a7,
        wchar_t *lpFileName,
        unsigned int a9,
        int *a10)
{
  unsigned int v13; // ebp
  int ShortApplicationName; // ebx
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  HRESULT v17; // eax
  __int64 v18; // rcx
  DWORD SpinCount; // ebx
  HANDLE v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  HANDLE hObject; // [rsp+40h] [rbp-268h] BYREF
  __int64 v26; // [rsp+48h] [rbp-260h]
  wchar_t v27[264]; // [rsp+50h] [rbp-258h] BYREF

  v13 = 0;
  if ( lpFileName && a2 )
  {
    *lpFileName = 0;
    *a10 = 0;
    hObject = 0;
    ShortApplicationName = CDumpCollection::GetShortApplicationName(a2, v27, a3);
    if ( ShortApplicationName >= 0 )
    {
      *a10 = 0;
      v17 = CoImpersonateClient();
      ShortApplicationName = v17;
      if ( v17 < 0 )
      {
        if ( v17 != -2147417833 )
          goto LABEL_25;
      }
      else
      {
        EnterCriticalSection(a2);
        SpinCount = a2[27].SpinCount;
        LeaveCriticalSection(a2);
        v20 = OpenProcess(0x410u, 0, SpinCount);
        if ( (unsigned __int64)v20 + 1 <= 1 )
        {
          v13 = 1;
          *a10 = 1;
          v26 = 0;
        }
        else
        {
          v26 = 0;
          CloseHandle(v20);
        }
        if ( CoRevertToSelf() < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v18, v21, v22, v23);
      }
      ShortApplicationName = CFileCollection::CreateCollectionFileByName(
                               v18,
                               a7,
                               v13,
                               (__int16 *)v27,
                               (__int64)a4,
                               0,
                               lpFileName,
                               &hObject);
      if ( ShortApplicationName >= 0 )
      {
        ShortApplicationName = CDumpCollection::CollectDump((CDumpCollection *)a2, a5, hObject, a3);
        if ( ShortApplicationName >= 0 )
        {
          ShortApplicationName = 0;
          goto LABEL_25;
        }
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_25;
        v16 = 14;
      }
      else
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_25;
        v16 = 13;
      }
    }
    else
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_25;
      v16 = 12;
    }
    WPP_SF_d(v15[2], v16, WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids, (unsigned int)ShortApplicationName);
LABEL_25:
    if ( (unsigned __int64)hObject + 1 > 1 )
      CloseHandle(hObject);
    if ( ShortApplicationName < 0 )
    {
      if ( *lpFileName )
      {
        DeleteFileW(lpFileName);
        *lpFileName = 0;
      }
    }
    return (unsigned int)ShortApplicationName;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180007db8  mov     [rsp+arg_0], rbx
0x180007dbd  push    rbp
0x180007dbe  push    rsi
0x180007dbf  push    rdi
0x180007dc0  push    r12
0x180007dc2  push    r13
0x180007dc4  push    r14
0x180007dc6  push    r15
0x180007dc8  sub     rsp, 270h
0x180007dcf  mov     rax, cs:__security_cookie
0x180007dd6  xor     rax, rsp
0x180007dd9  mov     [rsp+2A8h+var_48], rax
0x180007de1  mov     r12, r9
0x180007de4  mov     r15d, r8d
0x180007de7  mov     rsi, rdx
0x180007dea  mov     r13, [rsp+2A8h+arg_30]
0x180007df2  mov     rdi, [rsp+2A8h+lpFileName]
0x180007dfa  mov     r14, [rsp+2A8h+arg_48]
0x180007e02  xor     ebp, ebp
0x180007e04  test    rdi, rdi
0x180007e07  jz      loc_180007FBD
0x180007e0d  test    rdx, rdx
0x180007e10  jz      loc_180007FBD
0x180007e16  mov     [rdi], bp
0x180007e19  mov     [r14], ebp
0x180007e1c  mov     [rsp+2A8h+hObject], rbp
0x180007e21  lea     rdx, [rsp+2A8h+var_258]; wchar_t *
0x180007e26  mov     rcx, rsi; lpCriticalSection
0x180007e29  call    ?GetShortApplicationName@CDumpCollection@@QEAAJPEA_WI@Z; CDumpCollection::GetShortApplicationName(wchar_t *,uint)
0x180007e2e  mov     ebx, eax
0x180007e30  test    eax, eax
0x180007e32  jns     short loc_180007E70
0x180007e34  lea     rax, WPP_GLOBAL_Control
0x180007e3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e42  cmp     rcx, rax
0x180007e45  jz      loc_180007F8F
0x180007e4b  test    byte ptr [rcx+1Ch], 1
0x180007e4f  jz      loc_180007F8F
0x180007e55  lea     edx, [rbp+0Ch]
0x180007e58  mov     r9d, ebx
0x180007e5b  lea     r8, WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids
0x180007e62  mov     rcx, [rcx+10h]
0x180007e66  call    WPP_SF_d
0x180007e6b  jmp     loc_180007F8F
0x180007e70  mov     [r14], ebp
0x180007e73  call    cs:__imp_CoImpersonateClient
0x180007e79  mov     ebx, eax
0x180007e7b  test    eax, eax
0x180007e7d  js      short loc_180007EE5
0x180007e7f  mov     rcx, rsi; lpCriticalSection
0x180007e82  call    cs:__imp_EnterCriticalSection
0x180007e88  mov     ebx, [rsi+458h]
0x180007e8e  mov     rcx, rsi; lpCriticalSection
0x180007e91  call    cs:__imp_LeaveCriticalSection
0x180007e97  mov     r8d, ebx; dwProcessId
0x180007e9a  xor     edx, edx; bInheritHandle
0x180007e9c  mov     ecx, 410h; dwDesiredAccess
0x180007ea1  call    cs:__imp_OpenProcess
0x180007ea7  nop
0x180007ea8  lea     rcx, [rax+1]
0x180007eac  cmp     rcx, 1
0x180007eb0  jbe     short loc_180007EC2
0x180007eb2  mov     [rsp+2A8h+var_260], rbp
0x180007eb7  mov     rcx, rax; hObject
0x180007eba  call    cs:__imp_CloseHandle
0x180007ec0  jmp     short loc_180007ED3
0x180007ec2  mov     ebp, 1
0x180007ec7  mov     [r14], ebp
0x180007eca  mov     [rsp+2A8h+var_260], 0
0x180007ed3  call    cs:__imp_CoRevertToSelf
0x180007ed9  test    eax, eax
0x180007edb  jns     short loc_180007EE3
0x180007edd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180007ee2  nop
0x180007ee3  jmp     short loc_180007EF0
0x180007ee5  cmp     eax, 80010117h
0x180007eea  jnz     loc_180007F8D
0x180007ef0  lea     rax, [rsp+2A8h+hObject]
0x180007ef5  mov     [rsp+2A8h+var_270], rax
0x180007efa  mov     [rsp+2A8h+var_278], rdi
0x180007eff  mov     [rsp+2A8h+var_280], 0
0x180007f07  mov     qword ptr [rsp+2A8h+var_288], r12
0x180007f0c  lea     r9, [rsp+2A8h+var_258]
0x180007f11  mov     r8d, ebp
0x180007f14  mov     rdx, r13
0x180007f17  call    ?CreateCollectionFileByName@CFileCollection@@QEAAJPEB_WW4_FILECOLLECTION_ACL_TYPE@@00HPEA_WPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; CFileCollection::CreateCollectionFileByName(wchar_t const *,_FILECOLLECTION_ACL_TYPE,wchar_t const *,wchar_t const *,int,wchar_t *,tlx::unique_any<tlx::file_handle_traits> *)
0x180007f1c  mov     ebx, eax
0x180007f1e  xor     ebp, ebp
0x180007f20  test    eax, eax
0x180007f22  jns     short loc_180007F45
0x180007f24  lea     rax, WPP_GLOBAL_Control
0x180007f2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f32  cmp     rcx, rax
0x180007f35  jz      short loc_180007F8F
0x180007f37  test    byte ptr [rcx+1Ch], 1
0x180007f3b  jz      short loc_180007F8F
0x180007f3d  lea     edx, [rbp+0Dh]
0x180007f40  jmp     loc_180007E58
0x180007f45  mov     [rsp+2A8h+var_288], ebp; unsigned int
0x180007f49  mov     r9d, r15d; unsigned int
0x180007f4c  mov     r8, [rsp+2A8h+hObject]; void *
0x180007f51  mov     edx, [rsp+2A8h+arg_20]; enum _MINIDUMP_TYPE
0x180007f58  mov     rcx, rsi; this
0x180007f5b  call    ?CollectDump@CDumpCollection@@QEAAJW4_MINIDUMP_TYPE@@PEAXKK@Z; CDumpCollection::CollectDump(_MINIDUMP_TYPE,void *,ulong,ulong)
0x180007f60  mov     ebx, eax
0x180007f62  test    eax, eax
0x180007f64  jns     short loc_180007F89
0x180007f66  lea     rax, WPP_GLOBAL_Control
0x180007f6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f74  cmp     rcx, rax
0x180007f77  jz      short loc_180007F8F
0x180007f79  test    byte ptr [rcx+1Ch], 1
0x180007f7d  jz      short loc_180007F8F
0x180007f7f  mov     edx, 0Eh
0x180007f84  jmp     loc_180007E58
0x180007f89  mov     ebx, ebp
0x180007f8b  jmp     short loc_180007F8F
0x180007f8d  xor     ebp, ebp
0x180007f8f  mov     rcx, [rsp+2A8h+hObject]; hObject
0x180007f94  lea     rax, [rcx+1]
0x180007f98  cmp     rax, 1
0x180007f9c  jbe     short loc_180007FA4
0x180007f9e  call    cs:__imp_CloseHandle
0x180007fa4  test    ebx, ebx
0x180007fa6  jns     short loc_180007FB9
0x180007fa8  cmp     [rdi], bp
0x180007fab  jz      short loc_180007FB9
0x180007fad  mov     rcx, rdi; lpFileName
0x180007fb0  call    cs:__imp_DeleteFileW
0x180007fb6  mov     [rdi], bp
0x180007fb9  mov     eax, ebx
0x180007fbb  jmp     short loc_180007FF0
0x180007fbd  lea     rax, WPP_GLOBAL_Control
0x180007fc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180007fcb  cmp     rcx, rax
0x180007fce  jz      short loc_180007FEB
0x180007fd0  test    byte ptr [rcx+1Ch], 1
0x180007fd4  jz      short loc_180007FEB
0x180007fd6  mov     edx, 0Ah
0x180007fdb  lea     r8, WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids
0x180007fe2  mov     rcx, [rcx+10h]
0x180007fe6  call    WPP_SF_
0x180007feb  mov     eax, 80070057h
0x180007ff0  mov     rcx, [rsp+2A8h+var_48]
0x180007ff8  xor     rcx, rsp; StackCookie
0x180007ffb  call    __security_check_cookie
0x180008000  mov     rbx, [rsp+2A8h+arg_0]
0x180008008  add     rsp, 270h
0x18000800f  pop     r15
0x180008011  pop     r14
0x180008013  pop     r13
0x180008015  pop     r12
0x180008017  pop     rdi
0x180008018  pop     rsi
0x180008019  pop     rbp
0x18000801a  retn
```
