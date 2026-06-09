# CIptPlugin::EnableIpt(void)

- ea: `0x180032dec`
- end: `0x180033018`
- name: `?EnableIpt@CIptPlugin@@AEAAJXZ`
- size: `556`
- prototype: `__int64 __fastcall(CIptPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180033520`

## callees

- `0x180009ed8`
- `0x180009f00`
- `0x180032dec`
- `0x180033654`
- `0x180037908`
- `0x180037d20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032e41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032eac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032eee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032f14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032e41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032eac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032eee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032f14`
- `ntdll!RtlInitUnicodeString` at `0x180032fa4`
- `ntdll!RtlInitUnicodeString` at `0x180032fbb`
- `ntdll!RtlInitUnicodeString` at `0x180032fa4`
- `ntdll!RtlInitUnicodeString` at `0x180032fbb`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180032e12`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180032e12`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180032edb`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180032edb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180032f3c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180032f45`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180032f3c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180032f45`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180032e7b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180032e7b`

## pseudocode

```c
int __fastcall CIptPlugin::EnableIpt(PCWSTR *this)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // r14
  _QWORD *v4; // rcx
  DWORD LastError; // eax
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // rbp
  BOOL started; // esi
  DWORD v9; // eax
  DWORD v10; // eax
  const WCHAR *v12; // rdx
  struct _UNICODE_STRING *p_DestinationString; // rdi
  int v14; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF
  struct _UNICODE_STRING v16; // [rsp+40h] [rbp-38h] BYREF

  v16 = 0;
  DestinationString = 0;
  v2 = OpenSCManagerW(0, 0, 1u);
  v3 = v2;
  if ( !v2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return -2147467259;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
LABEL_18:
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 )
        WPP_SF_(v4[2], 23, &WPP_3229bad3034f32dffa4581e190add958_Traceguids);
      return -2147467259;
    }
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 171, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids, LastError);
LABEL_17:
    v4 = WPP_GLOBAL_Control;
    goto LABEL_18;
  }
  v6 = OpenServiceW(v2, L"Ipt", 0x10u);
  v7 = v6;
  if ( v6 )
  {
    started = StartServiceW(v6, 0, 0);
    if ( !started )
    {
      if ( GetLastError() == 1056 )
      {
        started = 1;
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v10 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 173, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids, v10);
      }
    }
    CloseServiceHandle(v7);
  }
  else
  {
    started = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v9 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 172, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids, v9);
    }
  }
  CloseServiceHandle(v3);
  if ( !started )
    goto LABEL_17;
  CIptPlugin::PrepareIptSettings((CIptPlugin *)this);
  if ( *((_BYTE *)this + 2880) )
  {
    v14 = StartCoreIptTracing(this[358], *((unsigned int *)this + 718), (unsigned int)(86400 * *((_DWORD *)this + 719)));
  }
  else
  {
    v12 = this[357];
    LODWORD(p_DestinationString) = 0;
    if ( v12 )
    {
      RtlInitUnicodeString(&DestinationString, v12);
      p_DestinationString = &DestinationString;
    }
    RtlInitUnicodeString(&v16, this[356]);
    v14 = RegisterExtendedImageForIptTracing(
            (unsigned int)&v16,
            (_DWORD)p_DestinationString,
            (unsigned int)this[358],
            *((_DWORD *)this + 718),
            86400 * *((_DWORD *)this + 719));
  }
  return v14 | 0x10000000;
}

```

## disassembly

```asm
0x180032dec  push    rbx
0x180032dee  push    rbp
0x180032def  push    rsi
0x180032df0  push    rdi
0x180032df1  push    r14
0x180032df3  sub     rsp, 50h
0x180032df7  xor     edx, edx; lpDatabaseName
0x180032df9  mov     rbx, rcx
0x180032dfc  xorps   xmm0, xmm0
0x180032dff  xorps   xmm1, xmm1
0x180032e02  xor     ecx, ecx; lpMachineName
0x180032e04  movups  xmmword ptr [rsp+78h+var_38.Length], xmm0
0x180032e09  lea     r8d, [rdx+1]; dwDesiredAccess
0x180032e0d  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm1
0x180032e12  call    cs:__imp_OpenSCManagerW
0x180032e18  mov     r14, rax
0x180032e1b  test    rax, rax
0x180032e1e  jnz     short loc_180032E6B
0x180032e20  mov     rcx, cs:WPP_GLOBAL_Control
0x180032e27  lea     rdi, WPP_GLOBAL_Control
0x180032e2e  cmp     rcx, rdi
0x180032e31  jz      loc_180032F76
0x180032e37  test    byte ptr [rcx+1Ch], 1
0x180032e3b  jz      loc_180032F56
0x180032e41  call    cs:__imp_GetLastError
0x180032e47  mov     rcx, cs:WPP_GLOBAL_Control
0x180032e4e  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180032e55  mov     edx, 0ABh
0x180032e5a  mov     r9d, eax
0x180032e5d  mov     rcx, [rcx+10h]
0x180032e61  call    WPP_SF_d
0x180032e66  jmp     loc_180032F4F
0x180032e6b  mov     r8d, 10h; dwDesiredAccess
0x180032e71  lea     rdx, ServiceName; "Ipt"
0x180032e78  mov     rcx, r14; hSCManager
0x180032e7b  call    cs:__imp_OpenServiceW
0x180032e81  mov     rbp, rax
0x180032e84  test    rax, rax
0x180032e87  jnz     short loc_180032ED3
0x180032e89  xor     esi, esi
0x180032e8b  mov     rax, cs:WPP_GLOBAL_Control
0x180032e92  lea     rdi, WPP_GLOBAL_Control
0x180032e99  cmp     rax, rdi
0x180032e9c  jz      loc_180032F42
0x180032ea2  test    byte ptr [rax+1Ch], 4
0x180032ea6  jz      loc_180032F42
0x180032eac  call    cs:__imp_GetLastError
0x180032eb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180032eb9  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180032ec0  mov     edx, 0ACh
0x180032ec5  mov     r9d, eax
0x180032ec8  mov     rcx, [rcx+10h]
0x180032ecc  call    WPP_SF_d
0x180032ed1  jmp     short loc_180032F42
0x180032ed3  xor     r8d, r8d; lpServiceArgVectors
0x180032ed6  xor     edx, edx; dwNumServiceArgs
0x180032ed8  mov     rcx, rbp; hService
0x180032edb  call    cs:__imp_StartServiceW
0x180032ee1  lea     rdi, WPP_GLOBAL_Control
0x180032ee8  mov     esi, eax
0x180032eea  test    eax, eax
0x180032eec  jnz     short loc_180032F39
0x180032eee  call    cs:__imp_GetLastError
0x180032ef4  cmp     eax, 420h
0x180032ef9  jnz     short loc_180032F02
0x180032efb  mov     esi, 1
0x180032f00  jmp     short loc_180032F39
0x180032f02  mov     rax, cs:WPP_GLOBAL_Control
0x180032f09  cmp     rax, rdi
0x180032f0c  jz      short loc_180032F39
0x180032f0e  test    byte ptr [rax+1Ch], 4
0x180032f12  jz      short loc_180032F39
0x180032f14  call    cs:__imp_GetLastError
0x180032f1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180032f21  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180032f28  mov     edx, 0ADh
0x180032f2d  mov     r9d, eax
0x180032f30  mov     rcx, [rcx+10h]
0x180032f34  call    WPP_SF_d
0x180032f39  mov     rcx, rbp; hSCObject
0x180032f3c  call    cs:__imp_CloseServiceHandle
0x180032f42  mov     rcx, r14; hSCObject
0x180032f45  call    cs:__imp_CloseServiceHandle
0x180032f4b  test    esi, esi
0x180032f4d  jnz     short loc_180032F80
0x180032f4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180032f56  cmp     rcx, rdi
0x180032f59  jz      short loc_180032F76
0x180032f5b  test    byte ptr [rcx+1Ch], 1
0x180032f5f  jz      short loc_180032F76
0x180032f61  mov     rcx, [rcx+10h]
0x180032f65  lea     r8, WPP_3229bad3034f32dffa4581e190add958_Traceguids
0x180032f6c  mov     edx, 17h
0x180032f71  call    WPP_SF_
0x180032f76  mov     eax, 80004005h
0x180032f7b  jmp     loc_18003300D
0x180032f80  mov     rcx, rbx; this
0x180032f83  call    ?PrepareIptSettings@CIptPlugin@@AEAAXXZ; CIptPlugin::PrepareIptSettings(void)
0x180032f88  cmp     byte ptr [rbx+0B40h], 0
0x180032f8f  jnz     short loc_180032FEC
0x180032f91  mov     rdx, [rbx+0B28h]; SourceString
0x180032f98  xor     edi, edi
0x180032f9a  test    rdx, rdx
0x180032f9d  jz      short loc_180032FAF
0x180032f9f  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x180032fa4  call    cs:__imp_RtlInitUnicodeString
0x180032faa  lea     rdi, [rsp+78h+DestinationString]
0x180032faf  mov     rdx, [rbx+0B20h]; SourceString
0x180032fb6  lea     rcx, [rsp+78h+var_38]; DestinationString
0x180032fbb  call    cs:__imp_RtlInitUnicodeString
0x180032fc1  imul    eax, [rbx+0B3Ch], 15180h
0x180032fcb  lea     rcx, [rsp+78h+var_38]
0x180032fd0  mov     r9d, [rbx+0B38h]
0x180032fd7  mov     rdx, rdi
0x180032fda  mov     r8, [rbx+0B30h]
0x180032fe1  mov     [rsp+78h+var_58], eax
0x180032fe5  call    RegisterExtendedImageForIptTracing
0x180032fea  jmp     short loc_180033009
0x180032fec  imul    r8d, [rbx+0B3Ch], 15180h
0x180032ff7  mov     edx, [rbx+0B38h]
0x180032ffd  mov     rcx, [rbx+0B30h]
0x180033004  call    StartCoreIptTracing
0x180033009  bts     eax, 1Ch
0x18003300d  add     rsp, 50h
0x180033011  pop     r14
0x180033013  pop     rdi
0x180033014  pop     rsi
0x180033015  pop     rbp
0x180033016  pop     rbx
0x180033017  retn
```
