# AllowUnmarshalerCLSID(ushort const *)

- ea: `0x18000ac7c`
- end: `0x18000ace8`
- name: `?AllowUnmarshalerCLSID@@YAJPEBG@Z`
- size: `108`
- prototype: `int __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000af38`

## callees

- `0x180001d00`
- `0x18000ac7c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18000ac9c`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18000ac9c`
- `api-ms-win-core-com-l1-1-0!CoAllowUnmarshalerCLSID` at `0x18000acc2`
- `api-ms-win-core-com-l1-1-0!CoAllowUnmarshalerCLSID` at `0x18000acc2`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000acb5`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000acb5`

## string_xrefs

- `0x18000acac`: `AllowUnmarshalerCLSID`

## pseudocode

```c
int __fastcall AllowUnmarshalerCLSID(const unsigned __int16 *a1)
{
  HRESULT v1; // eax
  int v2; // r8d
  IID iid; // [rsp+20h] [rbp-28h] BYREF

  iid = 0;
  v1 = IIDFromString(a1, &iid);
  if ( v1 < 0 )
  {
    v2 = 306;
    return ZTraceReportOriginationNoThis(v1, "AllowUnmarshalerCLSID", v2);
  }
  v1 = CoAllowUnmarshalerCLSID(&iid);
  if ( v1 < 0 )
  {
    v2 = 307;
    return ZTraceReportOriginationNoThis(v1, "AllowUnmarshalerCLSID", v2);
  }
  return 0;
}

```

## disassembly

```asm
0x18000ac7c  sub     rsp, 48h
0x18000ac80  mov     rax, cs:__security_cookie
0x18000ac87  xor     rax, rsp
0x18000ac8a  mov     [rsp+48h+var_18], rax
0x18000ac8f  xorps   xmm0, xmm0
0x18000ac92  lea     rdx, [rsp+48h+iid]; lpiid
0x18000ac97  movups  xmmword ptr [rsp+48h+iid.Data1], xmm0
0x18000ac9c  call    cs:__imp_IIDFromString
0x18000aca2  test    eax, eax
0x18000aca4  jns     short loc_18000ACBD
0x18000aca6  mov     r8d, 132h
0x18000acac  lea     rdx, aAllowunmarshal; "AllowUnmarshalerCLSID"
0x18000acb3  mov     ecx, eax
0x18000acb5  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000acbb  jmp     short loc_18000ACD6
0x18000acbd  lea     rcx, [rsp+48h+iid]
0x18000acc2  call    cs:__imp_CoAllowUnmarshalerCLSID
0x18000acc8  test    eax, eax
0x18000acca  jns     short loc_18000ACD4
0x18000accc  mov     r8d, 133h
0x18000acd2  jmp     short loc_18000ACAC
0x18000acd4  xor     eax, eax
0x18000acd6  mov     rcx, [rsp+48h+var_18]
0x18000acdb  xor     rcx, rsp; StackCookie
0x18000acde  call    __security_check_cookie
0x18000ace3  add     rsp, 48h
0x18000ace7  retn
```
