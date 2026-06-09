# DiagnosticsClient::AddRootCauseInfo(tagRootCauseInfo *)

- ea: `0x180005aa0`
- end: `0x180005b3d`
- name: `?AddRootCauseInfo@DiagnosticsClient@@UEAAJPEAUtagRootCauseInfo@@@Z`
- size: `157`
- prototype: `__int64 __fastcall(DiagnosticsClient *__hidden this, struct tagRootCauseInfo *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800056bc`
- `0x180005aa0`
- `0x18002b3a8`

## import_xrefs

- `wdi!WdiAddParameter` at `0x180005b18`
- `wdi!WdiAddParameter` at `0x180005b18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005b2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005b2a`

## pseudocode

```c
__int64 __fastcall DiagnosticsClient::AddRootCauseInfo(DiagnosticsClient *this, struct tagRootCauseInfo *a2)
{
  int v4; // ebx
  LPVOID v5; // rbx
  unsigned int v6; // eax
  LPVOID pv; // [rsp+48h] [rbp+10h] BYREF
  unsigned __int64 v8; // [rsp+50h] [rbp+18h] BYREF

  if ( !a2 )
    return 2147942487LL;
  if ( !*((_QWORD *)this + 1) )
    return 2147942406LL;
  pv = 0;
  v8 = 0;
  v4 = EncodeRootCauseInfo(a2, &pv, &v8);
  if ( v4 >= 0 )
  {
    v5 = pv;
    v6 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v8);
    v4 = WdiAddParameter(*((_QWORD *)this + 1), 0, L"NDFRootCauseInfo", v6, v5);
  }
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180005aa0  mov     [rsp+arg_0], rbx
0x180005aa5  push    rdi
0x180005aa6  sub     rsp, 30h
0x180005aaa  mov     rax, rdx
0x180005aad  mov     rdi, rcx
0x180005ab0  test    rdx, rdx
0x180005ab3  jnz     short loc_180005ABC
0x180005ab5  mov     eax, 80070057h
0x180005aba  jmp     short loc_180005B32
0x180005abc  cmp     qword ptr [rcx+8], 0
0x180005ac1  jnz     short loc_180005ACA
0x180005ac3  mov     eax, 80070006h
0x180005ac8  jmp     short loc_180005B32
0x180005aca  lea     r8, [rsp+38h+arg_10]
0x180005acf  mov     [rsp+38h+pv], 0
0x180005ad8  lea     rdx, [rsp+38h+pv]
0x180005add  mov     [rsp+38h+arg_10], 0
0x180005ae6  mov     rcx, rax
0x180005ae9  call    EncodeRootCauseInfo
0x180005aee  mov     ebx, eax
0x180005af0  test    eax, eax
0x180005af2  js      short loc_180005B20
0x180005af4  mov     rcx, [rsp+38h+arg_10]
0x180005af9  mov     rbx, [rsp+38h+pv]
0x180005afe  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x180005b03  mov     rcx, [rdi+8]
0x180005b07  lea     r8, aNdfrootcausein; "NDFRootCauseInfo"
0x180005b0e  mov     r9d, eax
0x180005b11  mov     [rsp+38h+var_18], rbx
0x180005b16  xor     edx, edx
0x180005b18  call    cs:__imp_WdiAddParameter
0x180005b1e  mov     ebx, eax
0x180005b20  mov     rcx, [rsp+38h+pv]; pv
0x180005b25  test    rcx, rcx
0x180005b28  jz      short loc_180005B30
0x180005b2a  call    cs:__imp_CoTaskMemFree
0x180005b30  mov     eax, ebx
0x180005b32  mov     rbx, [rsp+38h+arg_0]
0x180005b37  add     rsp, 30h
0x180005b3b  pop     rdi
0x180005b3c  retn
```
