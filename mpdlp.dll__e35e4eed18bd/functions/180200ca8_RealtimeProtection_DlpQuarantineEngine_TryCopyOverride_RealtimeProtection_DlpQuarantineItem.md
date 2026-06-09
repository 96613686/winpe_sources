# RealtimeProtection::DlpQuarantineEngine::TryCopyOverride(RealtimeProtection::_DlpQuarantineItem &)

- ea: `0x180200ca8`
- end: `0x180200fbe`
- name: `?TryCopyOverride@DlpQuarantineEngine@RealtimeProtection@@AEAA_NAEAU_DlpQuarantineItem@2@@Z`
- size: `790`
- prototype: `bool __fastcall(RealtimeProtection::DlpQuarantineEngine *__hidden this, struct RealtimeProtection::_DlpQuarantineItem *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180094038`

## callees

- `0x180034420`
- `0x180080030`
- `0x180089510`
- `0x18009351c`
- `0x1800943dc`
- `0x1801047b4`
- `0x180105f50`
- `0x18010cb40`
- `0x1801a5598`
- `0x180200ca8`

## import_xrefs

- `KERNEL32!Sleep` at `0x180200efa`
- `KERNEL32!Sleep` at `0x180200efa`
- `KERNEL32!DeleteFileW` at `0x180200e8b`
- `KERNEL32!DeleteFileW` at `0x180200f12`
- `KERNEL32!DeleteFileW` at `0x180200e8b`
- `KERNEL32!DeleteFileW` at `0x180200f12`
- `KERNEL32!GetLastError` at `0x180200f2b`
- `KERNEL32!GetLastError` at `0x180200f2b`
- `KERNEL32!CloseHandle` at `0x180200d87`
- `KERNEL32!CloseHandle` at `0x180200e17`
- `KERNEL32!CloseHandle` at `0x180200e68`
- `KERNEL32!CloseHandle` at `0x180200d87`
- `KERNEL32!CloseHandle` at `0x180200e17`
- `KERNEL32!CloseHandle` at `0x180200e68`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall RealtimeProtection::DlpQuarantineEngine::TryCopyOverride(
        RealtimeProtection::DlpQuarantineEngine *this,
        struct RealtimeProtection::_DlpQuarantineItem *a2)
{
  _QWORD *v3; // r9
  const WCHAR **v4; // rbx
  void **v5; // r15
  int File; // eax
  void ***v7; // r9
  void ***v9; // r9
  const WCHAR *v10; // rcx
  BOOL v11; // r15d
  int v12; // r12d
  char LastFailure; // al
  PVOID *v14; // rcx
  const WCHAR *v15; // r8
  const WCHAR *v16; // rcx
  char LastError; // al
  HANDLE hObject; // [rsp+40h] [rbp-30h] BYREF
  void **v19[3]; // [rsp+48h] [rbp-28h] BYREF
  unsigned __int64 v20; // [rsp+60h] [rbp-10h]

  if ( !*((_BYTE *)a2 + 48) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids);
    return 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v3 = (_QWORD *)((char *)a2 + 224);
    if ( *((_QWORD *)a2 + 31) > 7u )
      v3 = (_QWORD *)*v3;
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids, v3);
  }
  hObject = (HANDLE)-1LL;
  v4 = (const WCHAR **)((char *)a2 + 224);
  std::filesystem::path::operator std::wstring((char *)a2 + 224, v19);
  v5 = (void **)v19;
  if ( v20 > 7 )
    v5 = v19[0];
  File = CommonUtil::UtilCreateFile((CommonUtil *)&hObject, v5, (const wchar_t *)0x40000000, 3u, 5u, 0, 0, 0, hObject);
  if ( File < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = v19;
      if ( v20 > 7 )
        LODWORD(v7) = v19[0];
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        58,
        (unsigned int)&WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids,
        (_DWORD)v7,
        File);
    }
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v19);
    if ( hObject != (HANDLE)-1LL )
      CloseHandle(hObject);
    return 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v9 = v19;
    if ( v20 > 7 )
      v9 = (void ***)v19[0];
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids, v9);
  }
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v19);
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  if ( !*((_BYTE *)a2 + 537) )
  {
    if ( *((_QWORD *)a2 + 31) <= 7u )
      v10 = (const WCHAR *)((char *)a2 + 224);
    else
      v10 = *v4;
    v11 = DeleteFileW(v10);
    v12 = 0;
    if ( v11 )
    {
      v14 = (PVOID *)WPP_GLOBAL_Control;
    }
    else
    {
      while ( 1 )
      {
        LastFailure = HrGetLastFailure();
        v14 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          if ( *((_QWORD *)a2 + 31) <= 7u )
            v15 = (const WCHAR *)((char *)a2 + 224);
          else
            v15 = *v4;
          WPP_SF_dSd(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v15, LastFailure);
          v14 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( ++v12 == 5 )
          break;
        Sleep(0xAu);
        if ( *((_QWORD *)a2 + 31) <= 7u )
          v16 = (const WCHAR *)((char *)a2 + 224);
        else
          v16 = *v4;
        v11 = DeleteFileW(v16);
        if ( v11 )
        {
          v14 = (PVOID *)WPP_GLOBAL_Control;
          break;
        }
      }
      if ( !v11 )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          if ( *((_QWORD *)a2 + 31) > 7u )
            v4 = (const WCHAR **)*v4;
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            61,
            (unsigned int)&WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids,
            (_DWORD)v4,
            LastError);
        }
        return 1;
      }
    }
    if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 4) != 0 )
    {
      if ( *((_QWORD *)a2 + 31) > 7u )
        v4 = (const WCHAR **)*v4;
      WPP_SF_S(v14[2], 62, &WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids, v4);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180200ca8  mov     [rsp-28h+arg_0], rbx
0x180200cad  mov     [rsp-28h+arg_10], rsi
0x180200cb2  push    rbp
0x180200cb3  push    rdi
0x180200cb4  push    r12
0x180200cb6  push    r14
0x180200cb8  push    r15
0x180200cba  mov     rbp, rsp
0x180200cbd  sub     rsp, 70h
0x180200cc1  mov     rax, cs:__security_cookie
0x180200cc8  xor     rax, rsp
0x180200ccb  mov     [rbp+var_8], rax
0x180200ccf  mov     r14, rdx
0x180200cd2  cmp     byte ptr [rdx+30h], 0
0x180200cd6  jnz     short loc_180200D13
0x180200cd8  lea     rdi, WPP_GLOBAL_Control
0x180200cdf  mov     rcx, cs:WPP_GLOBAL_Control
0x180200ce6  cmp     rcx, rdi
0x180200ce9  jz      loc_180200E1D
0x180200cef  test    byte ptr [rcx+1Ch], 1
0x180200cf3  jz      loc_180200E1D
0x180200cf9  mov     edx, 38h ; '8'
0x180200cfe  lea     r8, WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids
0x180200d05  mov     rcx, [rcx+10h]
0x180200d09  call    WPP_SF_
0x180200d0e  jmp     loc_180200E1D
0x180200d13  lea     rdi, WPP_GLOBAL_Control
0x180200d1a  lea     rsi, WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids
0x180200d21  mov     rcx, cs:WPP_GLOBAL_Control
0x180200d28  cmp     rcx, rdi
0x180200d2b  jz      short loc_180200D55
0x180200d2d  test    byte ptr [rcx+1Ch], 4
0x180200d31  jz      short loc_180200D55
0x180200d33  lea     r9, [rdx+0E0h]
0x180200d3a  cmp     qword ptr [r9+18h], 7
0x180200d3f  jbe     short loc_180200D44
0x180200d41  mov     r9, [r9]
0x180200d44  mov     edx, 39h ; '9'
0x180200d49  mov     r8, rsi
0x180200d4c  mov     rcx, [rcx+10h]
0x180200d50  call    WPP_SF_S
0x180200d55  or      r12, 0FFFFFFFFFFFFFFFFh
0x180200d59  mov     [rbp+hObject], r12
0x180200d5d  lea     rbx, [r14+0E0h]
0x180200d64  lea     rdx, [rbp+var_28]
0x180200d68  mov     rcx, rbx
0x180200d6b  call    ??Bpath@filesystem@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::filesystem::path::operator std::wstring(void)
0x180200d70  lea     r15, [rbp+var_28]
0x180200d74  cmp     [rbp+var_10], 7
0x180200d79  cmova   r15, [rbp+var_28]
0x180200d7e  mov     rcx, [rbp+hObject]; hObject
0x180200d82  cmp     rcx, r12
0x180200d85  jz      short loc_180200D91
0x180200d87  call    cs:__imp_CloseHandle
0x180200d8d  mov     [rbp+hObject], r12
0x180200d91  mov     [rsp+70h+var_38], 0; struct _SECURITY_ATTRIBUTES *
0x180200d9a  mov     qword ptr [rsp+70h+var_40], 0; unsigned int
0x180200da3  mov     dword ptr [rsp+70h+var_48], 0; unsigned int
0x180200dab  mov     [rsp+70h+var_50], 5; unsigned int
0x180200db3  mov     r9d, 3; unsigned int
0x180200db9  mov     r8d, 40000000h; wchar_t *
0x180200dbf  mov     rdx, r15; void **
0x180200dc2  lea     rcx, [rbp+hObject]; this
0x180200dc6  call    ?UtilCreateFile@CommonUtil@@YAJPEAPEAXPEB_WKKKKPEAU_SECURITY_ATTRIBUTES@@PEAX@Z; CommonUtil::UtilCreateFile(void * *,wchar_t const *,ulong,ulong,ulong,ulong,_SECURITY_ATTRIBUTES *,void *)
0x180200dcb  test    eax, eax
0x180200dcd  jns     short loc_180200E24
0x180200dcf  mov     rcx, cs:WPP_GLOBAL_Control
0x180200dd6  cmp     rcx, rdi
0x180200dd9  jz      short loc_180200E04
0x180200ddb  test    byte ptr [rcx+1Ch], 1
0x180200ddf  jz      short loc_180200E04
0x180200de1  lea     r9, [rbp+var_28]
0x180200de5  cmp     [rbp+var_10], 7
0x180200dea  cmova   r9, [rbp+var_28]
0x180200def  mov     edx, 3Ah ; ':'
0x180200df4  mov     [rsp+70h+var_50], eax
0x180200df8  mov     r8, rsi
0x180200dfb  mov     rcx, [rcx+10h]
0x180200dff  call    WPP_SF_Sd
0x180200e04  lea     rcx, [rbp+var_28]; void *
0x180200e08  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x180200e0d  nop
0x180200e0e  mov     rcx, [rbp+hObject]; hObject
0x180200e12  cmp     rcx, r12
0x180200e15  jz      short loc_180200E1D
0x180200e17  call    cs:__imp_CloseHandle
0x180200e1d  xor     al, al
0x180200e1f  jmp     loc_180200F99
0x180200e24  mov     rcx, cs:WPP_GLOBAL_Control
0x180200e2b  cmp     rcx, rdi
0x180200e2e  jz      short loc_180200E55
0x180200e30  test    byte ptr [rcx+1Ch], 4
0x180200e34  jz      short loc_180200E55
0x180200e36  lea     r9, [rbp+var_28]
0x180200e3a  cmp     [rbp+var_10], 7
0x180200e3f  cmova   r9, [rbp+var_28]
0x180200e44  mov     edx, 3Bh ; ';'
0x180200e49  mov     r8, rsi
0x180200e4c  mov     rcx, [rcx+10h]
0x180200e50  call    WPP_SF_S
0x180200e55  lea     rcx, [rbp+var_28]; void *
0x180200e59  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x180200e5e  nop
0x180200e5f  mov     rcx, [rbp+hObject]; hObject
0x180200e63  cmp     rcx, r12
0x180200e66  jz      short loc_180200E6E
0x180200e68  call    cs:__imp_CloseHandle
0x180200e6e  cmp     byte ptr [r14+219h], 0
0x180200e76  jnz     loc_180200F97
0x180200e7c  cmp     qword ptr [rbx+18h], 7
0x180200e81  jbe     short loc_180200E88
0x180200e83  mov     rcx, [rbx]
0x180200e86  jmp     short loc_180200E8B
0x180200e88  mov     rcx, rbx; lpFileName
0x180200e8b  call    cs:__imp_DeleteFileW
0x180200e91  mov     r15d, eax
0x180200e94  xor     r12d, r12d
0x180200e97  test    eax, eax
0x180200e99  jnz     loc_180200F67
0x180200e9f  call    HrGetLastFailure
0x180200ea4  mov     rcx, cs:WPP_GLOBAL_Control
0x180200eab  cmp     rcx, rdi
0x180200eae  jz      short loc_180200EEC
0x180200eb0  test    byte ptr [rcx+1Ch], 1
0x180200eb4  jz      short loc_180200EEC
0x180200eb6  cmp     qword ptr [r14+0F8h], 7
0x180200ebe  jbe     short loc_180200EC5
0x180200ec0  mov     r8, [rbx]
0x180200ec3  jmp     short loc_180200EC8
0x180200ec5  mov     r8, rbx
0x180200ec8  mov     edx, 3Ch ; '<'
0x180200ecd  mov     dword ptr [rsp+70h+var_48], eax; char
0x180200ed1  mov     qword ptr [rsp+70h+var_50], r8; __int64
0x180200ed6  mov     r9d, r12d
0x180200ed9  mov     r8, rsi
0x180200edc  mov     rcx, [rcx+10h]; LoggerHandle
0x180200ee0  call    WPP_SF_dSd
0x180200ee5  mov     rcx, cs:WPP_GLOBAL_Control
0x180200eec  inc     r12d
0x180200eef  cmp     r12d, 5
0x180200ef3  jz      short loc_180200F26
0x180200ef5  mov     ecx, 0Ah; dwMilliseconds
0x180200efa  call    cs:__imp_Sleep
0x180200f00  cmp     qword ptr [r14+0F8h], 7
0x180200f08  jbe     short loc_180200F0F
0x180200f0a  mov     rcx, [rbx]
0x180200f0d  jmp     short loc_180200F12
0x180200f0f  mov     rcx, rbx; lpFileName
0x180200f12  call    cs:__imp_DeleteFileW
0x180200f18  mov     r15d, eax
0x180200f1b  test    eax, eax
0x180200f1d  jz      short loc_180200E9F
0x180200f1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180200f26  test    r15d, r15d
0x180200f29  jnz     short loc_180200F6E
0x180200f2b  call    cs:__imp_GetLastError
0x180200f31  mov     rcx, cs:WPP_GLOBAL_Control
0x180200f38  cmp     rcx, rdi
0x180200f3b  jz      short loc_180200F97
0x180200f3d  test    byte ptr [rcx+1Ch], 1
0x180200f41  jz      short loc_180200F97
0x180200f43  cmp     qword ptr [rbx+18h], 7
0x180200f48  jbe     short loc_180200F4D
0x180200f4a  mov     rbx, [rbx]
0x180200f4d  mov     edx, 3Dh ; '='
0x180200f52  mov     [rsp+70h+var_50], eax
0x180200f56  mov     r9, rbx
0x180200f59  mov     r8, rsi
0x180200f5c  mov     rcx, [rcx+10h]
0x180200f60  call    WPP_SF_Sd
0x180200f65  jmp     short loc_180200F97
0x180200f67  mov     rcx, cs:WPP_GLOBAL_Control
0x180200f6e  cmp     rcx, rdi
0x180200f71  jz      short loc_180200F97
0x180200f73  test    byte ptr [rcx+1Ch], 4
0x180200f77  jz      short loc_180200F97
0x180200f79  cmp     qword ptr [rbx+18h], 7
0x180200f7e  jbe     short loc_180200F83
0x180200f80  mov     rbx, [rbx]
0x180200f83  mov     edx, 3Eh ; '>'
0x180200f88  mov     r9, rbx
0x180200f8b  mov     r8, rsi
0x180200f8e  mov     rcx, [rcx+10h]
0x180200f92  call    WPP_SF_S
0x180200f97  mov     al, 1
0x180200f99  mov     rcx, [rbp+var_8]
0x180200f9d  xor     rcx, rsp; StackCookie
0x180200fa0  call    __security_check_cookie
0x180200fa5  lea     r11, [rsp+70h+var_s0]
0x180200faa  mov     rbx, [r11+30h]
0x180200fae  mov     rsi, [r11+40h]
0x180200fb2  mov     rsp, r11
0x180200fb5  pop     r15
0x180200fb7  pop     r14
0x180200fb9  pop     r12
0x180200fbb  pop     rdi
0x180200fbc  pop     rbp
0x180200fbd  retn
```
