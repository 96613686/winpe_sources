# CDataCollection::CollectSecureDump(ulong,ulong,ulong,wchar_t const *,_WER_FILE_TYPE,wchar_t const *,wchar_t *,ulong,void *)

- ea: `0x180008be4`
- end: `0x180008f40`
- name: `?CollectSecureDump@CDataCollection@@AEAAJKKKPEB_WW4_WER_FILE_TYPE@@0PEA_WKPEAX@Z`
- size: `860`
- prototype: `int(CDataCollection *__hidden this, unsigned int, unsigned int, unsigned int, const wchar_t *, enum _WER_FILE_TYPE, const wchar_t *, wchar_t *, unsigned int, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180009190`

## callees

- `0x180002890`
- `0x180003474`
- `0x180006684`
- `0x18000760c`
- `0x180008be4`
- `0x1800096cc`
- `0x180009f00`
- `0x180009f40`
- `0x18000a154`
- `0x18003bd80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e90`
- `ntdll!wcsrchr` at `0x180008d4b`
- `ntdll!wcsrchr` at `0x180008d4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008ef3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008f07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008ef3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008f07`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180008d34`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180008d34`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180008cbf`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180008cbf`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDataCollection::CollectSecureDump(
        CDataCollection *this,
        DWORD a2,
        unsigned int a3,
        __int64 a4,
        const wchar_t *a5,
        enum _WER_FILE_TYPE a6,
        const wchar_t *a7,
        wchar_t *a8,
        unsigned int a9,
        void *a10)
{
  HANDLE v12; // rdi
  char *v13; // r13
  signed int LastError; // eax
  unsigned int v15; // edx
  int v16; // ebx
  wchar_t *v17; // rax
  __int16 *v18; // rsi
  __int64 v19; // rcx
  CDataCollection *v20; // rcx
  signed int v21; // eax
  HANDLE hObject; // [rsp+40h] [rbp-C0h] BYREF
  DWORD dwSize; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *v25; // [rsp+50h] [rbp-B0h]
  HANDLE hSourceHandle; // [rsp+58h] [rbp-A8h]
  char *v27; // [rsp+60h] [rbp-A0h]
  wchar_t v28[56]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR ExeName[264]; // [rsp+E0h] [rbp-20h] BYREF

  v25 = a7;
  hSourceHandle = a10;
  memset_0(ExeName, 0, 0x208u);
  dwSize = 259;
  v12 = 0;
  hObject = 0;
  if ( !a2 || !a5 || !a8 )
    return 2147942487LL;
  *a8 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids, a2, a3);
  v13 = (char *)OpenProcess(0x1000u, 0, a2);
  v27 = v13;
  if ( v13 == (char *)-1LL || v13 + 1 == (char *)1 )
  {
    LastError = GetLastError();
    v16 = LastError;
    if ( LastError > 0 )
      v16 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids, a2, v16);
    goto LABEL_36;
  }
  if ( !QueryFullProcessImageNameW(v13, 0, ExeName, &dwSize) )
  {
    v21 = GetLastError();
    v16 = v21;
    if ( v21 > 0 )
      v16 = (unsigned __int16)v21 | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        50,
        &WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids,
        (unsigned int)v16);
LABEL_36:
    if ( v16 < 0 )
      goto LABEL_37;
    goto LABEL_39;
  }
  v17 = wcsrchr(ExeName, 0x5Cu);
  if ( v17 )
    v18 = (__int16 *)(v17 + 1);
  else
    v18 = (__int16 *)ExeName;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids, v18);
  v16 = StringCchPrintfW(v28, 0x32u, L"secure.%s", a5);
  if ( v16 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        51,
        &WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids,
        (unsigned int)v16);
    goto LABEL_37;
  }
  v16 = CFileCollection::CreateCollectionFileByName(v19, v25, 0, v18, (__int64)v28, 1, a8, &hObject);
  if ( v16 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52,
        &WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids,
        (unsigned int)v16);
    v12 = hObject;
    goto LABEL_37;
  }
  v12 = hObject;
  v16 = CDataCollection::LaunchSecureDumpCollection(v20, a2, a3, a6, hObject, hSourceHandle);
  if ( v16 < 0 )
  {
LABEL_37:
    if ( (unsigned __int64)v12 + 1 > 1 )
      UtilMarkFileForDelete(v12, v15);
    goto LABEL_39;
  }
  v16 = 0;
LABEL_39:
  if ( (unsigned __int64)(v13 + 1) > 1 )
    CloseHandle(v13);
  if ( (unsigned __int64)v12 + 1 > 1 )
    CloseHandle(v12);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180008be4  mov     [rsp-8+arg_0], rbx
0x180008be9  push    rbp
0x180008bea  push    rsi
0x180008beb  push    rdi
0x180008bec  push    r12
0x180008bee  push    r13
0x180008bf0  push    r14
0x180008bf2  push    r15
0x180008bf4  lea     rbp, [rsp-200h]
0x180008bfc  sub     rsp, 300h
0x180008c03  mov     rax, cs:__security_cookie
0x180008c0a  xor     rax, rsp
0x180008c0d  mov     [rbp+230h+var_40], rax
0x180008c14  mov     r12d, r8d
0x180008c17  mov     r14d, edx
0x180008c1a  mov     rbx, [rbp+230h+arg_20]
0x180008c21  mov     rax, [rbp+230h+arg_30]
0x180008c28  mov     [rsp+330h+var_2E0], rax
0x180008c2d  mov     r15, [rbp+230h+arg_38]
0x180008c34  mov     rax, [rbp+230h+arg_48]
0x180008c3b  mov     [rsp+330h+var_2D8], rax
0x180008c40  xor     edx, edx; Val
0x180008c42  mov     r8d, 208h; Size
0x180008c48  lea     rcx, [rbp+230h+ExeName]; void *
0x180008c4c  call    memset_0
0x180008c51  mov     [rsp+330h+dwSize], 103h
0x180008c59  xor     edi, edi
0x180008c5b  mov     [rsp+330h+hObject], rdi
0x180008c60  test    r14d, r14d
0x180008c63  jz      loc_180008F11
0x180008c69  test    rbx, rbx
0x180008c6c  jz      loc_180008F11
0x180008c72  test    r15, r15
0x180008c75  jz      loc_180008F11
0x180008c7b  xor     eax, eax
0x180008c7d  mov     [r15], ax
0x180008c81  lea     rsi, WPP_GLOBAL_Control
0x180008c88  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c8f  cmp     rcx, rsi
0x180008c92  jz      short loc_180008CB5
0x180008c94  test    byte ptr [rcx+1Ch], 4
0x180008c98  jz      short loc_180008CB5
0x180008c9a  lea     edx, [rdi+2Fh]
0x180008c9d  mov     dword ptr [rsp+330h+var_310], r12d
0x180008ca2  mov     r9d, r14d
0x180008ca5  lea     r8, WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids
0x180008cac  mov     rcx, [rcx+10h]
0x180008cb0  call    WPP_SF_Dd
0x180008cb5  mov     r8d, r14d; dwProcessId
0x180008cb8  xor     edx, edx; bInheritHandle
0x180008cba  mov     ecx, 1000h; dwDesiredAccess
0x180008cbf  call    cs:__imp_OpenProcess
0x180008cc5  mov     r13, rax
0x180008cc8  mov     [rsp+330h+var_2D0], rax
0x180008ccd  inc     rax
0x180008cd0  cmp     rax, 1
0x180008cd4  ja      short loc_180008D26
0x180008cd6  call    cs:__imp_GetLastError
0x180008cdc  mov     ebx, eax
0x180008cde  test    eax, eax
0x180008ce0  jle     short loc_180008CEB
0x180008ce2  movzx   ebx, ax
0x180008ce5  or      ebx, 80070000h
0x180008ceb  mov     rcx, cs:WPP_GLOBAL_Control
0x180008cf2  cmp     rcx, rsi
0x180008cf5  jz      loc_180008ECF
0x180008cfb  test    byte ptr [rcx+1Ch], 1
0x180008cff  jz      loc_180008ECF
0x180008d05  mov     edx, 30h ; '0'
0x180008d0a  mov     dword ptr [rsp+330h+var_310], ebx
0x180008d0e  mov     r9d, r14d
0x180008d11  lea     r8, WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids
0x180008d18  mov     rcx, [rcx+10h]
0x180008d1c  call    WPP_SF_Dd
0x180008d21  jmp     loc_180008ECF
0x180008d26  lea     r9, [rsp+330h+dwSize]; lpdwSize
0x180008d2b  lea     r8, [rbp+230h+ExeName]; lpExeName
0x180008d2f  xor     edx, edx; dwFlags
0x180008d31  mov     rcx, r13; hProcess
0x180008d34  call    cs:__imp_QueryFullProcessImageNameW
0x180008d3a  test    eax, eax
0x180008d3c  jz      loc_180008E90
0x180008d42  mov     edx, 5Ch ; '\'; Ch
0x180008d47  lea     rcx, [rbp+230h+ExeName]; Str
0x180008d4b  call    cs:__imp_wcsrchr
0x180008d51  mov     rsi, rax
0x180008d54  test    rax, rax
0x180008d57  jz      short loc_180008D5F
0x180008d59  add     rsi, 2
0x180008d5d  jmp     short loc_180008D63
0x180008d5f  lea     rsi, [rbp+230h+ExeName]
0x180008d63  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d6a  lea     rax, WPP_GLOBAL_Control
0x180008d71  cmp     rcx, rax
0x180008d74  jz      short loc_180008D94
0x180008d76  test    byte ptr [rcx+1Ch], 8
0x180008d7a  jz      short loc_180008D94
0x180008d7c  mov     edx, 31h ; '1'
0x180008d81  mov     r9, rsi
0x180008d84  lea     r8, WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids
0x180008d8b  mov     rcx, [rcx+10h]
0x180008d8f  call    WPP_SF_S
0x180008d94  mov     r9, rbx
0x180008d97  lea     r8, aSecureS; "secure.%s"
0x180008d9e  mov     edx, 32h ; '2'; unsigned __int64
0x180008da3  lea     rcx, [rsp+330h+var_2C0]; wchar_t *
0x180008da8  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180008dad  mov     ebx, eax
0x180008daf  test    eax, eax
0x180008db1  jns     short loc_180008DF1
0x180008db3  mov     rcx, cs:WPP_GLOBAL_Control
0x180008dba  lea     rax, WPP_GLOBAL_Control
0x180008dc1  cmp     rcx, rax
0x180008dc4  jz      loc_180008ED3
0x180008dca  test    byte ptr [rcx+1Ch], 1
0x180008dce  jz      loc_180008ED3
0x180008dd4  mov     edx, 33h ; '3'
0x180008dd9  mov     r9d, ebx
0x180008ddc  lea     r8, WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids
0x180008de3  mov     rcx, [rcx+10h]
0x180008de7  call    WPP_SF_d
0x180008dec  jmp     loc_180008ED3
0x180008df1  lea     rax, [rsp+330h+hObject]
0x180008df6  mov     [rsp+330h+var_2F8], rax
0x180008dfb  mov     [rsp+330h+var_300], r15
0x180008e00  mov     dword ptr [rsp+330h+hSourceHandle], 1
0x180008e08  lea     rax, [rsp+330h+var_2C0]
0x180008e0d  mov     [rsp+330h+var_310], rax
0x180008e12  mov     r9, rsi
0x180008e15  xor     r8d, r8d
0x180008e18  mov     rdx, [rsp+330h+var_2E0]
0x180008e1d  call    ?CreateCollectionFileByName@CFileCollection@@QEAAJPEB_WW4_FILECOLLECTION_ACL_TYPE@@00HPEA_WPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; CFileCollection::CreateCollectionFileByName(wchar_t const *,_FILECOLLECTION_ACL_TYPE,wchar_t const *,wchar_t const *,int,wchar_t *,tlx::unique_any<tlx::file_handle_traits> *)
0x180008e22  mov     ebx, eax
0x180008e24  test    eax, eax
0x180008e26  jns     short loc_180008E60
0x180008e28  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e2f  lea     rax, WPP_GLOBAL_Control
0x180008e36  cmp     rcx, rax
0x180008e39  jz      short loc_180008E59
0x180008e3b  test    byte ptr [rcx+1Ch], 1
0x180008e3f  jz      short loc_180008E59
0x180008e41  mov     edx, 34h ; '4'
0x180008e46  mov     r9d, ebx
0x180008e49  lea     r8, WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids
0x180008e50  mov     rcx, [rcx+10h]
0x180008e54  call    WPP_SF_d
0x180008e59  mov     rdi, [rsp+330h+hObject]
0x180008e5e  jmp     short loc_180008ED3
0x180008e60  mov     rax, [rsp+330h+var_2D8]
0x180008e65  mov     [rsp+330h+hSourceHandle], rax; hSourceHandle
0x180008e6a  mov     rdi, [rsp+330h+hObject]
0x180008e6f  mov     [rsp+330h+var_310], rdi; void *
0x180008e74  mov     r9d, [rbp+230h+arg_28]; enum _WER_FILE_TYPE
0x180008e7b  mov     r8d, r12d; unsigned int
0x180008e7e  mov     edx, r14d; unsigned int
0x180008e81  call    ?LaunchSecureDumpCollection@CDataCollection@@AEAAJKKW4_WER_FILE_TYPE@@PEAX1@Z; CDataCollection::LaunchSecureDumpCollection(ulong,ulong,_WER_FILE_TYPE,void *,void *)
0x180008e86  mov     ebx, eax
0x180008e88  test    eax, eax
0x180008e8a  js      short loc_180008ED3
0x180008e8c  xor     ebx, ebx
0x180008e8e  jmp     short loc_180008EE6
0x180008e90  call    cs:__imp_GetLastError
0x180008e96  mov     ebx, eax
0x180008e98  test    eax, eax
0x180008e9a  jle     short loc_180008EA5
0x180008e9c  movzx   ebx, ax
0x180008e9f  or      ebx, 80070000h
0x180008ea5  mov     rcx, cs:WPP_GLOBAL_Control
0x180008eac  cmp     rcx, rsi
0x180008eaf  jz      short loc_180008ECF
0x180008eb1  test    byte ptr [rcx+1Ch], 1
0x180008eb5  jz      short loc_180008ECF
0x180008eb7  mov     edx, 32h ; '2'
0x180008ebc  mov     r9d, ebx
0x180008ebf  lea     r8, WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids
0x180008ec6  mov     rcx, [rcx+10h]
0x180008eca  call    WPP_SF_d
0x180008ecf  test    ebx, ebx
0x180008ed1  jns     short loc_180008EE6
0x180008ed3  lea     rax, [rdi+1]
0x180008ed7  cmp     rax, 1
0x180008edb  jbe     short loc_180008EE6
0x180008edd  mov     rcx, rdi; void *
0x180008ee0  call    ?UtilMarkFileForDelete@@YAXPEAXK@Z; UtilMarkFileForDelete(void *,ulong)
0x180008ee5  nop
0x180008ee6  lea     rax, [r13+1]
0x180008eea  cmp     rax, 1
0x180008eee  jbe     short loc_180008EFA
0x180008ef0  mov     rcx, r13; hObject
0x180008ef3  call    cs:__imp_CloseHandle
0x180008ef9  nop
0x180008efa  lea     rax, [rdi+1]
0x180008efe  cmp     rax, 1
0x180008f02  jbe     short loc_180008F0D
0x180008f04  mov     rcx, rdi; hObject
0x180008f07  call    cs:__imp_CloseHandle
0x180008f0d  mov     eax, ebx
0x180008f0f  jmp     short loc_180008F16
0x180008f11  mov     eax, 80070057h
0x180008f16  mov     rcx, [rbp+230h+var_40]
0x180008f1d  xor     rcx, rsp; StackCookie
0x180008f20  call    __security_check_cookie
0x180008f25  mov     rbx, [rsp+330h+arg_0]
0x180008f2d  add     rsp, 300h
0x180008f34  pop     r15
0x180008f36  pop     r14
0x180008f38  pop     r13
0x180008f3a  pop     r12
0x180008f3c  pop     rdi
0x180008f3d  pop     rsi
0x180008f3e  pop     rbp
0x180008f3f  retn
```
