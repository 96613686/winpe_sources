# GetUserSid

- ea: `0x1800175c0`
- end: `0x18001765c`
- name: `GetUserSid`
- size: `156`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180017520`

## callees

- `0x1800175c0`
- `0x18001aa50`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001760e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001760e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001763e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001763e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017649`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017649`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180017604`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180017604`

## pseudocode

```c
__int64 __fastcall GetUserSid(__int64 *a1, unsigned __int16 *a2, WCHAR *a3)
{
  __int64 v3; // rax
  signed int v5; // ebx
  signed int LastError; // eax
  PSID Sid; // [rsp+30h] [rbp+8h] BYREF
  LPWSTR StringSid; // [rsp+40h] [rbp+18h] BYREF

  StringSid = a3;
  v3 = *a1;
  Sid = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, PSID *))(v3 + 72))(a1, &Sid);
  if ( v5 >= 0 )
  {
    StringSid = 0;
    if ( ConvertSidToStringSidW(Sid, &StringSid) )
    {
      v5 = StringCchCopyW(a2, 0x104u, StringSid);
      LocalFree(StringSid);
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
    CoTaskMemFree(Sid);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800175c0  mov     r11, rsp
0x1800175c3  mov     [r11+10h], rbx
0x1800175c7  mov     [r11+18h], r8
0x1800175cb  push    rdi
0x1800175cc  sub     rsp, 20h
0x1800175d0  mov     rax, [rcx]
0x1800175d3  mov     rdi, rdx
0x1800175d6  lea     rdx, [r11+8]
0x1800175da  mov     qword ptr [r11+8], 0
0x1800175e2  mov     rax, [rax+48h]
0x1800175e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175eb  mov     ebx, eax
0x1800175ed  test    eax, eax
0x1800175ef  js      short loc_18001764F
0x1800175f1  mov     rcx, [rsp+28h+Sid]; Sid
0x1800175f6  lea     rdx, [rsp+28h+StringSid]; StringSid
0x1800175fb  mov     [rsp+28h+StringSid], 0
0x180017604  call    cs:__imp_ConvertSidToStringSidW
0x18001760a  test    eax, eax
0x18001760c  jnz     short loc_180017625
0x18001760e  call    cs:__imp_GetLastError
0x180017614  mov     ebx, eax
0x180017616  test    eax, eax
0x180017618  jle     short loc_180017644
0x18001761a  movzx   ebx, ax
0x18001761d  or      ebx, 80070000h
0x180017623  jmp     short loc_180017644
0x180017625  mov     r8, [rsp+28h+StringSid]; unsigned __int16 *
0x18001762a  mov     edx, 104h; unsigned __int64
0x18001762f  mov     rcx, rdi; unsigned __int16 *
0x180017632  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017637  mov     rcx, [rsp+28h+StringSid]; hMem
0x18001763c  mov     ebx, eax
0x18001763e  call    cs:__imp_LocalFree
0x180017644  mov     rcx, [rsp+28h+Sid]; pv
0x180017649  call    cs:__imp_CoTaskMemFree
0x18001764f  mov     eax, ebx
0x180017651  mov     rbx, [rsp+28h+arg_8]
0x180017656  add     rsp, 20h
0x18001765a  pop     rdi
0x18001765b  retn
```
