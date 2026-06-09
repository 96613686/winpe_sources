# ClusterADObject::GetObjectSid(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x1800a508c`
- end: `0x1800a5139`
- name: `?GetObjectSid@ClusterADObject@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `173`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18007438c`
- `0x1800a5140`

## callees

- `0x180029978`
- `0x180038494`
- `0x1800a508c`
- `0x1800a78e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a50ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a50ec`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800a50e2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800a50e2`

## string_xrefs

- `0x1800a50af`: `objectSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ClusterADObject::GetObjectSid(__int64 a1, __int64 a2)
{
  int BinaryAttribute; // ebx
  __int64 v4; // r8
  signed int LastError; // eax
  LPWSTR v6; // rbx
  LPWSTR v8; // [rsp+40h] [rbp+8h] BYREF
  PSID Sid; // [rsp+50h] [rbp+18h] BYREF
  LPWSTR StringSid; // [rsp+58h] [rbp+20h] BYREF

  Sid = 0;
  BinaryAttribute = CLdapWrapper::GetBinaryAttribute(
                      *(CLdapWrapper **)(a1 + 256),
                      *(struct CLdapSearchResult **)(a1 + 264),
                      L"objectSid",
                      (unsigned __int8 **)&Sid,
                      (unsigned int *)&v8);
  if ( BinaryAttribute >= 0 )
  {
    StringSid = 0;
    if ( ConvertSidToStringSidW(Sid, &StringSid) )
    {
      v6 = StringSid;
      v8 = StringSid;
      std::wstring::assign(a2, StringSid, v4);
      CTSmartPtr_PolicyLocalMem::DestroyMem(v6);
      BinaryAttribute = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      BinaryAttribute = LastError;
    }
  }
  CTSmartPtr_PolicyLocalMem::DestroyMem(Sid);
  return (unsigned int)BinaryAttribute;
}

```

## disassembly

```asm
0x1800a508c  mov     r11, rsp
0x1800a508f  mov     [r11+10h], rbx
0x1800a5093  push    rdi
0x1800a5094  sub     rsp, 30h
0x1800a5098  mov     rdi, rdx
0x1800a509b  mov     qword ptr [r11+18h], 0
0x1800a50a3  lea     rax, [r11+8]
0x1800a50a7  mov     [r11-18h], rax
0x1800a50ab  lea     r9, [r11+18h]; unsigned __int8 **
0x1800a50af  lea     r8, aObjectsid; "objectSid"
0x1800a50b6  mov     rdx, [rcx+108h]; struct CLdapSearchResult *
0x1800a50bd  mov     rcx, [rcx+100h]; this
0x1800a50c4  call    ?GetBinaryAttribute@CLdapWrapper@@QEAAJPEAVCLdapSearchResult@@PEB_WPEAPEAEPEAK@Z; CLdapWrapper::GetBinaryAttribute(CLdapSearchResult *,wchar_t const *,uchar * *,ulong *)
0x1800a50c9  mov     ebx, eax
0x1800a50cb  test    eax, eax
0x1800a50cd  js      short loc_1800A5122
0x1800a50cf  mov     [rsp+38h+StringSid], 0
0x1800a50d8  lea     rdx, [rsp+38h+StringSid]; StringSid
0x1800a50dd  mov     rcx, [rsp+38h+Sid]; Sid
0x1800a50e2  call    cs:__imp_ConvertSidToStringSidW
0x1800a50e8  test    eax, eax
0x1800a50ea  jnz     short loc_1800A5102
0x1800a50ec  call    cs:__imp_GetLastError
0x1800a50f2  test    eax, eax
0x1800a50f4  jle     short loc_1800A50FE
0x1800a50f6  movzx   eax, ax
0x1800a50f9  or      eax, 80070000h
0x1800a50fe  mov     ebx, eax
0x1800a5100  jmp     short loc_1800A5122
0x1800a5102  mov     rbx, [rsp+38h+StringSid]
0x1800a5107  mov     [rsp+38h+arg_0], rbx
0x1800a510c  mov     rdx, rbx
0x1800a510f  mov     rcx, rdi
0x1800a5112  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x1800a5117  nop
0x1800a5118  mov     rcx, rbx; void *
0x1800a511b  call    ?DestroyMem@CTSmartPtr_PolicyLocalMem@@SAHPEAX@Z; CTSmartPtr_PolicyLocalMem::DestroyMem(void *)
0x1800a5120  xor     ebx, ebx
0x1800a5122  mov     rcx, [rsp+38h+Sid]; void *
0x1800a5127  call    ?DestroyMem@CTSmartPtr_PolicyLocalMem@@SAHPEAX@Z; CTSmartPtr_PolicyLocalMem::DestroyMem(void *)
0x1800a512c  mov     eax, ebx
0x1800a512e  mov     rbx, [rsp+38h+arg_8]
0x1800a5133  add     rsp, 30h
0x1800a5137  pop     rdi
0x1800a5138  retn
```
