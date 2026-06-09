# CMQSigCertStore::_Open(char *,MQSigOpenCertParams *)

- ea: `0x18001c8bc`
- end: `0x18001cb12`
- name: `?_Open@CMQSigCertStore@@AEAAJPEADPEAUMQSigOpenCertParams@@@Z`
- size: `598`
- prototype: `__int64 __fastcall(CMQSigCertStore *__hidden this, LPCSTR lpSubKey, struct MQSigOpenCertParams *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001b4c0`

## callees

- `0x180004074`
- `0x1800139dc`
- `0x180017430`
- `0x18001c80c`
- `0x18001c8bc`
- `0x18001cb18`

## import_xrefs

- `CRYPT32!CertOpenStore` at `0x18001cac7`
- `CRYPT32!CertOpenStore` at `0x18001cac7`
- `ADVAPI32!RegCreateKeyExA` at `0x18001c974`
- `ADVAPI32!RegCreateKeyExA` at `0x18001c974`
- `ADVAPI32!RegOpenKeyExA` at `0x18001c916`
- `ADVAPI32!RegOpenKeyExA` at `0x18001c916`
- `KERNEL32!GetLastError` at `0x18001cad6`
- `KERNEL32!GetLastError` at `0x18001cad6`

## pseudocode

```c
__int64 __fastcall CMQSigCertStore::_Open(CMQSigCertStore *this, LPCSTR lpSubKey, struct MQSigOpenCertParams *a3)
{
  __int64 v4; // rbx
  const void **v7; // r14
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  int inited; // ebx
  unsigned int v12; // eax
  HCERTSTORE v13; // rax
  DWORD LastError; // eax
  DWORD dwDisposition; // [rsp+80h] [rbp+8h] BYREF
  int v16; // [rsp+90h] [rbp+18h] BYREF

  v4 = *(_QWORD *)a3;
  if ( !*(_QWORD *)a3 )
  {
    v4 = -2147483647;
    if ( *((_BYTE *)a3 + 10) )
      v4 = -2147483646;
  }
  v7 = (const void **)((char *)this + 32);
  v8 = RegOpenKeyExA((HKEY)v4, lpSubKey, 0, *((_BYTE *)a3 + 8) != 0 ? 131103 : 131097, (PHKEY)this + 4);
  if ( !v8 )
  {
LABEL_15:
    inited = CMQSigCertStore::_InitCryptProvider(this);
    if ( inited >= 0 )
    {
      v13 = CertOpenStore((LPCSTR)4, 0x10001u, *((_QWORD *)this + 3), *((_BYTE *)a3 + 8) != 0 ? 1 : 32769, *v7);
      *((_QWORD *)this + 2) = v13;
      if ( v13 )
      {
        return 0;
      }
      else
      {
        LastError = GetLastError();
        if ( LastError )
          LogMsgNTStatus(LastError, (wchar_t *)L"certifct/cmqstore", 0x28u);
        return 3222146087LL;
      }
    }
    else
    {
      LOWORD(dwDisposition) = 30;
      v16 = inited;
      if ( g_pMSMQErrorLoggingTrace )
      {
        v12 = mqwcslen(L"certifct/cmqstore");
        CMSMQTrace::MSMQTraceEvent(
          g_pMSMQErrorLoggingTrace,
          1,
          1,
          2LL * (v12 + 1),
          L"certifct/cmqstore",
          2,
          &dwDisposition,
          4,
          &v16,
          0,
          0);
      }
      return (unsigned int)inited;
    }
  }
  if ( *((_BYTE *)a3 + 9) )
  {
    dwDisposition = 0;
    v9 = RegCreateKeyExA((HKEY)v4, lpSubKey, 0, (LPSTR)&byte_180034A70, 0, 0x2001Fu, 0, (PHKEY)v7, &dwDisposition);
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 32), v9);
      return 3222143087LL;
    }
    goto LABEL_15;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
    WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 32), v8);
  return 3222143088LL;
}

```

## disassembly

```asm
0x18001c8bc  mov     [rsp+arg_8], rbx
0x18001c8c1  mov     [rsp+arg_18], rbp
0x18001c8c6  push    rsi
0x18001c8c7  push    rdi
0x18001c8c8  push    r14
0x18001c8ca  sub     rsp, 60h
0x18001c8ce  mov     al, [r8+8]
0x18001c8d2  mov     rdi, r8
0x18001c8d5  mov     rbx, [r8]
0x18001c8d8  neg     al
0x18001c8da  mov     rsi, rdx
0x18001c8dd  mov     rbp, rcx
0x18001c8e0  sbb     r9d, r9d
0x18001c8e3  and     r9d, 6
0x18001c8e7  add     r9d, 20019h; samDesired
0x18001c8ee  test    rbx, rbx
0x18001c8f1  jnz     short loc_18001C907
0x18001c8f3  cmp     byte ptr [r8+0Ah], 0
0x18001c8f8  mov     rbx, 0FFFFFFFF80000001h
0x18001c8ff  lea     rax, [rbx+1]
0x18001c903  cmovnz  rbx, rax
0x18001c907  lea     r14, [rcx+20h]
0x18001c90b  xor     r8d, r8d; ulOptions
0x18001c90e  mov     rcx, rbx; hKey
0x18001c911  mov     [rsp+78h+phkResult], r14; phkResult
0x18001c916  call    cs:__imp_RegOpenKeyExA
0x18001c91c  test    eax, eax
0x18001c91e  jz      loc_18001C9FA
0x18001c924  cmp     byte ptr [rdi+9], 0
0x18001c928  jz      loc_18001C9BC
0x18001c92e  lea     rax, [rsp+78h+dwDisposition]
0x18001c936  mov     [rsp+78h+dwDisposition], 0
0x18001c941  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x18001c946  lea     r9, byte_180034A70; lpClass
0x18001c94d  mov     [rsp+78h+var_40], r14; phkResult
0x18001c952  xor     r8d, r8d; Reserved
0x18001c955  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001c95e  mov     rdx, rsi; lpSubKey
0x18001c961  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x18001c969  mov     rcx, rbx; hKey
0x18001c96c  mov     dword ptr [rsp+78h+phkResult], 0; dwOptions
0x18001c974  call    cs:__imp_RegCreateKeyExA
0x18001c97a  test    eax, eax
0x18001c97c  jz      short loc_18001C9FA
0x18001c97e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c985  lea     rdx, WPP_GLOBAL_Control
0x18001c98c  cmp     rcx, rdx
0x18001c98f  jz      short loc_18001C9B2
0x18001c991  test    byte ptr [rcx+10Ch], 1
0x18001c998  jz      short loc_18001C9B2
0x18001c99a  mov     rcx, [rcx+100h]; LoggerHandle
0x18001c9a1  mov     edx, 0Ah
0x18001c9a6  mov     r9, rsi
0x18001c9a9  mov     dword ptr [rsp+78h+phkResult], eax; char
0x18001c9ad  call    WPP_SF_sD
0x18001c9b2  mov     eax, 0C00E006Fh
0x18001c9b7  jmp     loc_18001CAFD
0x18001c9bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c9c3  lea     rdx, WPP_GLOBAL_Control
0x18001c9ca  cmp     rcx, rdx
0x18001c9cd  jz      short loc_18001C9F0
0x18001c9cf  test    byte ptr [rcx+10Ch], 1
0x18001c9d6  jz      short loc_18001C9F0
0x18001c9d8  mov     rcx, [rcx+100h]; LoggerHandle
0x18001c9df  mov     edx, 0Bh
0x18001c9e4  mov     r9, rsi
0x18001c9e7  mov     dword ptr [rsp+78h+phkResult], eax; char
0x18001c9eb  call    WPP_SF_sD
0x18001c9f0  mov     eax, 0C00E0070h
0x18001c9f5  jmp     loc_18001CAFD
0x18001c9fa  mov     rcx, rbp; this
0x18001c9fd  call    ?_InitCryptProvider@CMQSigCertStore@@AEAAJXZ; CMQSigCertStore::_InitCryptProvider(void)
0x18001ca02  mov     ebx, eax
0x18001ca04  test    eax, eax
0x18001ca06  jns     loc_18001CA9B
0x18001ca0c  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001ca14  mov     eax, 1Eh
0x18001ca19  mov     word ptr [rsp+78h+dwDisposition], ax
0x18001ca21  mov     [rsp+78h+arg_10], ebx
0x18001ca28  jz      short loc_18001CA97
0x18001ca2a  lea     rdi, aCertifctCmqsto; "certifct/cmqstore"
0x18001ca31  mov     rcx, rdi; wchar_t *
0x18001ca34  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18001ca39  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001ca40  mov     edx, 1
0x18001ca45  mov     [rsp+78h+var_28], 0
0x18001ca4e  mov     r8d, edx
0x18001ca51  mov     [rsp+78h+var_30], 0
0x18001ca5a  lea     r9d, [rax+1]
0x18001ca5e  lea     rax, [rsp+78h+arg_10]
0x18001ca66  add     r9, r9
0x18001ca69  mov     [rsp+78h+lpdwDisposition], rax
0x18001ca6e  lea     rax, [rsp+78h+dwDisposition]
0x18001ca76  mov     [rsp+78h+var_40], 4
0x18001ca7f  mov     [rsp+78h+lpSecurityAttributes], rax
0x18001ca84  mov     qword ptr [rsp+78h+samDesired], 2
0x18001ca8d  mov     [rsp+78h+phkResult], rdi
0x18001ca92  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18001ca97  mov     eax, ebx
0x18001ca99  jmp     short loc_18001CAFD
0x18001ca9b  mov     al, [rdi+8]
0x18001ca9e  mov     edx, 10001h; dwEncodingType
0x18001caa3  mov     r8, [rbp+18h]; hCryptProv
0x18001caa7  neg     al
0x18001caa9  mov     rax, [r14]
0x18001caac  mov     ecx, 4; lpszStoreProvider
0x18001cab1  sbb     r9d, r9d
0x18001cab4  mov     [rsp+78h+phkResult], rax; pvPara
0x18001cab9  and     r9d, 0FFFF8000h
0x18001cac0  add     r9d, 8001h; dwFlags
0x18001cac7  call    cs:__imp_CertOpenStore
0x18001cacd  mov     [rbp+10h], rax
0x18001cad1  test    rax, rax
0x18001cad4  jnz     short loc_18001CAFB
0x18001cad6  call    cs:__imp_GetLastError
0x18001cadc  test    eax, eax
0x18001cade  jz      short loc_18001CAF4
0x18001cae0  mov     r8d, 28h ; '('; unsigned __int16
0x18001cae6  lea     rdx, aCertifctCmqsto; "certifct/cmqstore"
0x18001caed  mov     ecx, eax; int
0x18001caef  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x18001caf4  mov     eax, 0C00E0C27h
0x18001caf9  jmp     short loc_18001CAFD
0x18001cafb  xor     eax, eax
0x18001cafd  lea     r11, [rsp+78h+var_18]
0x18001cb02  mov     rbx, [r11+28h]
0x18001cb06  mov     rbp, [r11+38h]
0x18001cb0a  mov     rsp, r11
0x18001cb0d  pop     r14
0x18001cb0f  pop     rdi
0x18001cb10  pop     rsi
0x18001cb11  retn
```
