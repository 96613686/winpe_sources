# FTP_SERVERP::UpdateFtpHost(IFtpHost *)

- ea: `0x180004e70`
- end: `0x1800050da`
- name: `?UpdateFtpHost@FTP_SERVERP@@UEAAJPEAUIFtpHost@@@Z`
- size: `618`
- prototype: `__int64 __fastcall(FTP_SERVERP *__hidden this, struct IFtpHost *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180004e70`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180004f66`
- `ole32!CoCreateInstance` at `0x180004f66`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180004ea7`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180004ea7`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800050b6`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800050b6`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x180004f48`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x1800050ad`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x180004f48`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x1800050ad`
- `iisutil!PuDbgPrintError` at `0x180004faa`
- `iisutil!PuDbgPrintError` at `0x180004faa`

## string_xrefs

- `0x180004f86`: `CoCreateInstance for the __uuidof( FtpHost ) failed.`
- `0x180004f92`: `FTP_SERVERP::UpdateFtpHost`

## pseudocode

```c
__int64 __fastcall FTP_SERVERP::UpdateFtpHost(FTP_SERVERP *this, struct IFtpHost *a2)
{
  CReaderWriterLock3 *v2; // r14
  LPVOID *ppv; // rdi
  struct IFtpHost *v5; // rcx
  HRESULT Instance; // ebx
  __int64 v7; // rax
  CEtwTracer *v8; // rax
  __int64 v9; // rax
  CEtwTracer *v10; // rax
  __int64 v11; // rax
  HRESULT v13; // [rsp+30h] [rbp-39h] BYREF
  __int16 v14; // [rsp+40h] [rbp-29h] BYREF
  __int128 v15; // [rsp+42h] [rbp-27h]
  _BYTE v16[38]; // [rsp+52h] [rbp-17h] BYREF
  __int64 v17; // [rsp+78h] [rbp+Fh]

  v2 = (FTP_SERVERP *)((char *)this + 168);
  ppv = (LPVOID *)((char *)this + 176);
  CReaderWriterLock3::WriteLock((FTP_SERVERP *)((char *)this + 168));
  v5 = (struct IFtpHost *)*ppv;
  if ( *ppv )
  {
    Instance = 0;
    if ( v5 != a2 )
      goto LABEL_20;
    (*(void (__fastcall **)(struct IFtpHost *))(*(_QWORD *)v5 + 16LL))(v5);
    *ppv = 0;
  }
  v7 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
  if ( *(_DWORD *)(v7 + 8) && (*(_BYTE *)(v7 + 40) & 0x12) != 0 && *(_DWORD *)(v7 + 44) >= 4u )
  {
    v8 = (CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
    v14 = 48;
    v15 = 0;
    BYTE2(v15) = 7;
    *(_QWORD *)v16 = 0;
    WORD2(v15) = 1;
    *(_OWORD *)&v16[14] = 0;
    *(_DWORD *)&v16[26] = 1703936;
    *(_QWORD *)&v16[6] = &`FtpExtensibilityEvents::GetAreaGuid'::`2'::AreaGuid;
    CEtwTracer::EtwTraceEvent(v8, (struct _EVENT_TRACE_HEADER *)&v14);
  }
  Instance = CoCreateInstance(
               &GUID_315fa593_3cf5_4310_887b_3977a578488a,
               0,
               4u,
               &GUID_ee673f07_b5ab_4036_80ae_59c7b5d32d89,
               ppv);
  if ( Instance >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
    if ( *(_DWORD *)(v11 + 8) && (*(_BYTE *)(v11 + 40) & 0x12) != 0 && *(_DWORD *)(v11 + 44) >= 4u )
    {
      v10 = (CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
      v14 = 48;
      v15 = 0;
      WORD2(v15) = 1;
      *(_QWORD *)v16 = 0;
      *(_QWORD *)&v16[6] = &`FtpExtensibilityEvents::GetAreaGuid'::`2'::AreaGuid;
      *(_OWORD *)&v16[14] = 0;
      BYTE2(v15) = 8;
      goto LABEL_19;
    }
  }
  else
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_serverp.cxx",
        1345,
        "FTP_SERVERP::UpdateFtpHost",
        Instance,
        "CoCreateInstance for the __uuidof( FtpHost ) failed.");
    v9 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
    if ( *(_DWORD *)(v9 + 8) && (*(_BYTE *)(v9 + 40) & 0x12) != 0 && *(_DWORD *)(v9 + 44) >= 3u )
    {
      v13 = Instance;
      v10 = (CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
      v14 = 64;
      v15 = 0;
      WORD2(v15) = 1;
      memset(v16, 0, 32);
      *(_QWORD *)&v16[6] = &`FtpExtensibilityEvents::GetAreaGuid'::`2'::AreaGuid;
      BYTE2(v15) = 9;
      *(_QWORD *)&v16[30] = &v13;
      v17 = 4;
LABEL_19:
      *(_DWORD *)&v16[26] = 1703936;
      CEtwTracer::EtwTraceEvent(v10, (struct _EVENT_TRACE_HEADER *)&v14);
    }
  }
LABEL_20:
  CReaderWriterLock3::WriteUnlock(v2);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180004e70  push    rbp
0x180004e72  push    rbx
0x180004e73  push    rsi
0x180004e74  push    rdi
0x180004e75  push    r13
0x180004e77  push    r14
0x180004e79  lea     rbp, [rsp-2Fh]
0x180004e7e  sub     rsp, 98h
0x180004e85  mov     rax, cs:__security_cookie
0x180004e8c  xor     rax, rsp
0x180004e8f  mov     [rbp+57h+var_40], rax
0x180004e93  lea     r14, [rcx+0A8h]
0x180004e9a  mov     rsi, rdx
0x180004e9d  lea     rdi, [rcx+0B0h]
0x180004ea4  mov     rcx, r14
0x180004ea7  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180004ead  mov     rcx, [rdi]
0x180004eb0  test    rcx, rcx
0x180004eb3  jz      short loc_180004ECF
0x180004eb5  xor     ebx, ebx
0x180004eb7  cmp     rcx, rsi
0x180004eba  jnz     loc_1800050B3
0x180004ec0  mov     rax, [rcx]
0x180004ec3  mov     rax, [rax+10h]
0x180004ec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ecc  mov     [rdi], rbx
0x180004ecf  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180004ed6  mov     rax, [rcx]
0x180004ed9  mov     rax, [rax+20h]
0x180004edd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ee2  mov     r13d, 30h ; '0'
0x180004ee8  lea     rbx, ?AreaGuid@?1??GetAreaGuid@FtpExtensibilityEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `FtpExtensibilityEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180004eef  cmp     dword ptr [rax+8], 0
0x180004ef3  lea     esi, [r13-2Ch]
0x180004ef7  jz      short loc_180004F4E
0x180004ef9  test    byte ptr [rax+28h], 12h
0x180004efd  jz      short loc_180004F4E
0x180004eff  cmp     [rax+2Ch], esi
0x180004f02  jb      short loc_180004F4E
0x180004f04  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180004f0b  mov     rax, [rcx]
0x180004f0e  mov     rax, [rax+20h]
0x180004f12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f17  xorps   xmm0, xmm0
0x180004f1a  mov     [rbp+57h+var_80], r13w
0x180004f1f  movups  [rbp+57h+var_7E], xmm0
0x180004f23  lea     ecx, [rsi-3]
0x180004f26  mov     byte ptr [rbp+57h+var_7E+2], 7
0x180004f2a  movups  [rbp+57h+var_6E], xmm0
0x180004f2e  mov     word ptr [rbp+57h+var_7E+4], cx
0x180004f32  lea     rdx, [rbp+57h+var_80]
0x180004f36  movups  [rbp+57h+var_6E+0Eh], xmm0
0x180004f3a  mov     rcx, rax
0x180004f3d  mov     [rbp+57h+var_54], 1A0000h
0x180004f44  mov     qword ptr [rbp+57h+var_6E+6], rbx
0x180004f48  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z; CEtwTracer::EtwTraceEvent(_EVENT_TRACE_HEADER *)
0x180004f4e  lea     r9, _GUID_ee673f07_b5ab_4036_80ae_59c7b5d32d89; riid
0x180004f55  mov     [rsp+0C0h+ppv], rdi; ppv
0x180004f5a  mov     r8d, esi; dwClsContext
0x180004f5d  lea     rcx, _GUID_315fa593_3cf5_4310_887b_3977a578488a; rclsid
0x180004f64  xor     edx, edx; pUnkOuter
0x180004f66  call    cs:__imp_CoCreateInstance
0x180004f6c  mov     ebx, eax
0x180004f6e  test    eax, eax
0x180004f70  jns     loc_18000503C
0x180004f76  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180004f7d  jz      short loc_180004FB0
0x180004f7f  mov     rcx, cs:g_pDebug
0x180004f86  lea     rax, aCocreateinstan; "CoCreateInstance for the __uuidof( FtpH"...
0x180004f8d  mov     [rsp+0C0h+var_98], rax
0x180004f92  lea     r9, aFtpServerpUpda; "FTP_SERVERP::UpdateFtpHost"
0x180004f99  mov     r8d, 541h
0x180004f9f  mov     dword ptr [rsp+0C0h+ppv], ebx
0x180004fa3  lea     rdx, aInetsrvIisIisr_23; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x180004faa  call    cs:__imp_PuDbgPrintError
0x180004fb0  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180004fb7  mov     rax, [rcx]
0x180004fba  mov     rax, [rax+20h]
0x180004fbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fc3  cmp     dword ptr [rax+8], 0
0x180004fc7  jz      loc_1800050B3
0x180004fcd  test    byte ptr [rax+28h], 12h
0x180004fd1  jz      loc_1800050B3
0x180004fd7  cmp     dword ptr [rax+2Ch], 3
0x180004fdb  jb      loc_1800050B3
0x180004fe1  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180004fe8  mov     [rbp+57h+var_90], ebx
0x180004feb  mov     rax, [rcx]
0x180004fee  mov     rax, [rax+20h]
0x180004ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ff7  xorps   xmm0, xmm0
0x180004ffa  lea     rdx, [rbp+57h+var_80]
0x180004ffe  mov     ecx, 40h ; '@'
0x180005003  mov     [rbp+57h+var_80], cx
0x180005007  mov     ecx, 1
0x18000500c  movups  [rbp+57h+var_7E], xmm0
0x180005010  mov     word ptr [rbp+57h+var_7E+4], cx
0x180005014  lea     rcx, ?AreaGuid@?1??GetAreaGuid@FtpExtensibilityEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `FtpExtensibilityEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000501b  movups  [rbp+57h+var_6E], xmm0
0x18000501f  mov     qword ptr [rbp+57h+var_6E+6], rcx
0x180005023  lea     rcx, [rbp+57h+var_90]
0x180005027  movups  xmmword ptr [rbp-7], xmm0
0x18000502b  mov     byte ptr [rbp+57h+var_7E+2], 9
0x18000502f  movups  [rbp+57h+var_50], xmm0
0x180005033  mov     qword ptr [rbp+57h+var_50], rcx
0x180005037  mov     dword ptr [rbp+57h+var_50+8], esi
0x18000503a  jmp     short loc_1800050A3
0x18000503c  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180005043  mov     rax, [rcx]
0x180005046  mov     rax, [rax+20h]
0x18000504a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000504f  cmp     dword ptr [rax+8], 0
0x180005053  jz      short loc_1800050B3
0x180005055  test    byte ptr [rax+28h], 12h
0x180005059  jz      short loc_1800050B3
0x18000505b  cmp     [rax+2Ch], esi
0x18000505e  jb      short loc_1800050B3
0x180005060  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180005067  mov     rax, [rcx]
0x18000506a  mov     rax, [rax+20h]
0x18000506e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005073  xorps   xmm0, xmm0
0x180005076  mov     [rbp+57h+var_80], r13w
0x18000507b  mov     ecx, 1
0x180005080  lea     rdx, [rbp+57h+var_80]
0x180005084  movups  [rbp+57h+var_7E], xmm0
0x180005088  mov     word ptr [rbp+57h+var_7E+4], cx
0x18000508c  lea     rcx, ?AreaGuid@?1??GetAreaGuid@FtpExtensibilityEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `FtpExtensibilityEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180005093  movups  [rbp+57h+var_6E], xmm0
0x180005097  mov     qword ptr [rbp+57h+var_6E+6], rcx
0x18000509b  movups  [rbp+57h+var_6E+0Eh], xmm0
0x18000509f  mov     byte ptr [rbp+57h+var_7E+2], 8
0x1800050a3  mov     rcx, rax
0x1800050a6  mov     [rbp+57h+var_54], 1A0000h
0x1800050ad  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z; CEtwTracer::EtwTraceEvent(_EVENT_TRACE_HEADER *)
0x1800050b3  mov     rcx, r14
0x1800050b6  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x1800050bc  mov     eax, ebx
0x1800050be  mov     rcx, [rbp+57h+var_40]
0x1800050c2  xor     rcx, rsp; StackCookie
0x1800050c5  call    __security_check_cookie
0x1800050ca  add     rsp, 98h
0x1800050d1  pop     r14
0x1800050d3  pop     r13
0x1800050d5  pop     rdi
0x1800050d6  pop     rsi
0x1800050d7  pop     rbx
0x1800050d8  pop     rbp
0x1800050d9  retn
```
