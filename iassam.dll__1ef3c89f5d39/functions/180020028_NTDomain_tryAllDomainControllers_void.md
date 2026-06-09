# NTDomain::tryAllDomainControllers(void)

- ea: `0x180020028`
- end: `0x1800200ed`
- name: `?tryAllDomainControllers@NTDomain@@AEAAKXZ`
- size: `197`
- prototype: `unsigned int __fastcall(NTDomain *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001f7b4`

## callees

- `0x18001f640`
- `0x180020028`

## import_xrefs

- `netutils!NetApiBufferFree` at `0x1800200cb`
- `netutils!NetApiBufferFree` at `0x1800200cb`
- `logoncli!DsGetDcOpenW` at `0x180020080`
- `logoncli!DsGetDcOpenW` at `0x180020080`
- `logoncli!DsGetDcCloseW` at `0x1800200da`
- `logoncli!DsGetDcCloseW` at `0x1800200da`
- `logoncli!DsGetDcNextW` at `0x1800200a2`
- `logoncli!DsGetDcNextW` at `0x1800200a2`

## pseudocode

```c
DWORD __fastcall NTDomain::tryAllDomainControllers(NTDomain *this)
{
  DWORD result; // eax
  char *v3; // rcx
  DWORD DcNextW; // edi
  LPWSTR DnsHostName; // [rsp+50h] [rbp+8h] BYREF
  HANDLE GetDcContextHandle; // [rsp+58h] [rbp+10h] BYREF

  if ( !*((_QWORD *)this + 12) )
    return -2147467259;
  v3 = (char *)this + 80;
  GetDcContextHandle = 0;
  if ( *((_QWORD *)v3 + 3) >= 8u )
    v3 = *(char **)v3;
  result = DsGetDcOpenW((LPCWSTR)v3, 0, 0, 0, 0, 1u, &GetDcContextHandle);
  if ( !result )
  {
    do
    {
      DnsHostName = 0;
      DcNextW = DsGetDcNextW(GetDcContextHandle, 0, 0, &DnsHostName);
      if ( DcNextW )
        break;
      DcNextW = NTDomain::connectDomainController(this, DnsHostName, 1, 0x80004005);
      NetApiBufferFree(DnsHostName);
    }
    while ( DcNextW );
    DsGetDcCloseW(GetDcContextHandle);
    return DcNextW;
  }
  return result;
}

```

## disassembly

```asm
0x180020028  mov     [rsp+arg_10], rbx
0x18002002d  push    rdi
0x18002002e  sub     rsp, 40h
0x180020032  cmp     qword ptr [rcx+60h], 0
0x180020037  mov     rbx, rcx
0x18002003a  jnz     short loc_180020046
0x18002003c  mov     eax, 80004005h
0x180020041  jmp     loc_1800200E2
0x180020046  add     rcx, 50h ; 'P'
0x18002004a  mov     [rsp+48h+GetDcContextHandle], 0
0x180020053  cmp     qword ptr [rcx+18h], 8
0x180020058  jb      short loc_18002005D
0x18002005a  mov     rcx, [rcx]; DnsName
0x18002005d  lea     rax, [rsp+48h+GetDcContextHandle]
0x180020062  xor     r9d, r9d; DomainGuid
0x180020065  mov     [rsp+48h+RetGetDcContext], rax; RetGetDcContext
0x18002006a  xor     r8d, r8d; SiteName
0x18002006d  mov     [rsp+48h+DcFlags], 1; DcFlags
0x180020075  xor     edx, edx; OptionFlags
0x180020077  mov     [rsp+48h+DnsForestName], 0; DnsForestName
0x180020080  call    cs:__imp_DsGetDcOpenW
0x180020086  test    eax, eax
0x180020088  jnz     short loc_1800200E2
0x18002008a  mov     rcx, [rsp+48h+GetDcContextHandle]; GetDcContextHandle
0x18002008f  lea     r9, [rsp+48h+DnsHostName]; DnsHostName
0x180020094  xor     r8d, r8d; SockAddresses
0x180020097  mov     [rsp+48h+DnsHostName], 0
0x1800200a0  xor     edx, edx; SockAddressCount
0x1800200a2  call    cs:__imp_DsGetDcNextW
0x1800200a8  mov     edi, eax
0x1800200aa  test    eax, eax
0x1800200ac  jnz     short loc_1800200D5
0x1800200ae  mov     rdx, [rsp+48h+DnsHostName]; unsigned __int16 *
0x1800200b3  mov     r9d, 80004005h; unsigned int
0x1800200b9  mov     r8b, 1; bool
0x1800200bc  mov     rcx, rbx; this
0x1800200bf  call    ?connectDomainController@NTDomain@@AEAAKPEBG_NK@Z; NTDomain::connectDomainController(ushort const *,bool,ulong)
0x1800200c4  mov     rcx, [rsp+48h+DnsHostName]; Buffer
0x1800200c9  mov     edi, eax
0x1800200cb  call    cs:__imp_NetApiBufferFree
0x1800200d1  test    edi, edi
0x1800200d3  jnz     short loc_18002008A
0x1800200d5  mov     rcx, [rsp+48h+GetDcContextHandle]; GetDcContextHandle
0x1800200da  call    cs:__imp_DsGetDcCloseW
0x1800200e0  mov     eax, edi
0x1800200e2  mov     rbx, [rsp+48h+arg_10]
0x1800200e7  add     rsp, 40h
0x1800200eb  pop     rdi
0x1800200ec  retn
```
