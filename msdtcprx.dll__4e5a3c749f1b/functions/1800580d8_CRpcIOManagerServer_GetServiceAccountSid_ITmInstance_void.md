# CRpcIOManagerServer::GetServiceAccountSid(ITmInstance *,void * *)

- ea: `0x1800580d8`
- end: `0x1800581cb`
- name: `?GetServiceAccountSid@CRpcIOManagerServer@@AEAAJPEAUITmInstance@@PEAPEAX@Z`
- size: `243`
- prototype: `int(CRpcIOManagerServer *__hidden this, struct ITmInstance *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180019f80`

## callees

- `0x180003cf0`
- `0x1800580d8`
- `0x180072cd4`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800581a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800581b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800581a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800581b3`

## string_xrefs

- `0x180058180`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x180058125`: `Failed to check token for admin.`
- `0x180058190`: `CRpcIOManagerServer::GetServiceAccountSid`

## pseudocode

```c
__int64 __fastcall CRpcIOManagerServer::GetServiceAccountSid(
        CRpcIOManagerServer *this,
        struct ITmInstance *a2,
        void **a3)
{
  __int64 v4; // rax
  int AccountSid; // ebx
  const wchar_t *v7; // rax
  __int64 v8; // r9
  __int64 v10; // [rsp+28h] [rbp-20h]
  LPVOID pv; // [rsp+50h] [rbp+8h] BYREF
  LPCWSTR lpSystemName; // [rsp+58h] [rbp+10h] BYREF

  pv = this;
  *a3 = 0;
  v4 = *(_QWORD *)a2;
  pv = 0;
  lpSystemName = 0;
  AccountSid = (*(__int64 (__fastcall **)(struct ITmInstance *, LPVOID *))(v4 + 312))(a2, &pv);
  if ( AccountSid < 0 )
  {
    v7 = L"Failed to check token for admin.";
    v8 = 469;
LABEL_8:
    LODWORD(v10) = AccountSid;
    TraceStringInline(
      1,
      1,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
      v8,
      L"CRpcIOManagerServer::GetServiceAccountSid",
      v10,
      v7);
    goto LABEL_9;
  }
  AccountSid = (*(__int64 (__fastcall **)(struct ITmInstance *, LPCWSTR *))(*(_QWORD *)a2 + 40LL))(a2, &lpSystemName);
  if ( AccountSid < 0 )
  {
    v8 = 476;
LABEL_7:
    v7 = L"Failed to get the host name from the specified TM instance";
    goto LABEL_8;
  }
  AccountSid = GetAccountSid(lpSystemName, (unsigned __int16 *)pv, a3);
  if ( AccountSid < 0 )
  {
    v8 = 483;
    goto LABEL_7;
  }
LABEL_9:
  CoTaskMemFree(pv);
  CoTaskMemFree((LPVOID)lpSystemName);
  return (unsigned int)AccountSid;
}

```

## disassembly

```asm
0x1800580d8  mov     r11, rsp
0x1800580db  mov     [r11+18h], rbx
0x1800580df  mov     [r11+20h], rsi
0x1800580e3  mov     [r11+8], rcx
0x1800580e7  push    rdi
0x1800580e8  sub     rsp, 40h
0x1800580ec  mov     rdi, rdx
0x1800580ef  mov     qword ptr [r8], 0
0x1800580f6  mov     rax, [rdx]
0x1800580f9  mov     rcx, rdi
0x1800580fc  lea     rdx, [r11+8]
0x180058100  mov     qword ptr [r11+8], 0
0x180058108  mov     rsi, r8
0x18005810b  mov     qword ptr [r11+10h], 0
0x180058113  mov     rax, [rax+138h]
0x18005811a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005811f  mov     ebx, eax
0x180058121  test    eax, eax
0x180058123  jns     short loc_180058134
0x180058125  lea     rax, aFailedToCheckT_1; "Failed to check token for admin."
0x18005812c  mov     r9d, 1D5h
0x180058132  jmp     short loc_18005817B
0x180058134  mov     rax, [rdi]
0x180058137  lea     rdx, [rsp+48h+lpSystemName]
0x18005813c  mov     rcx, rdi
0x18005813f  mov     rax, [rax+28h]
0x180058143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058148  mov     ebx, eax
0x18005814a  test    eax, eax
0x18005814c  jns     short loc_180058156
0x18005814e  mov     r9d, 1DCh
0x180058154  jmp     short loc_180058174
0x180058156  mov     rdx, [rsp+48h+pv]; unsigned __int16 *
0x18005815b  mov     r8, rsi; void **
0x18005815e  mov     rcx, [rsp+48h+lpSystemName]; lpSystemName
0x180058163  call    ?GetAccountSid@@YAJPEAG0PEAPEAX@Z; GetAccountSid(ushort *,ushort *,void * *)
0x180058168  mov     ebx, eax
0x18005816a  test    eax, eax
0x18005816c  jns     short loc_1800581A3
0x18005816e  mov     r9d, 1E3h
0x180058174  lea     rax, aFailedToGetThe_4; "Failed to get the host name from the sp"...
0x18005817b  mov     [rsp+48h+var_18], rax
0x180058180  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x180058187  mov     ecx, 1
0x18005818c  mov     dword ptr [rsp+48h+var_20], ebx
0x180058190  lea     rax, aCrpciomanagers_1; "CRpcIOManagerServer::GetServiceAccountS"...
0x180058197  mov     edx, ecx
0x180058199  mov     [rsp+48h+var_28], rax
0x18005819e  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800581a3  mov     rcx, [rsp+48h+pv]; pv
0x1800581a8  call    cs:__imp_CoTaskMemFree
0x1800581ae  mov     rcx, [rsp+48h+lpSystemName]; pv
0x1800581b3  call    cs:__imp_CoTaskMemFree
0x1800581b9  mov     rsi, [rsp+48h+arg_18]
0x1800581be  mov     eax, ebx
0x1800581c0  mov     rbx, [rsp+48h+arg_10]
0x1800581c5  add     rsp, 40h
0x1800581c9  pop     rdi
0x1800581ca  retn
```
