# Microsoft::Windows::MDM::OmadmClient::WinhttpApiWrapper::WinHttpOpen(ushort const *,ulong,ushort const *,void * *)

- ea: `0x140054550`
- end: `0x1400545c2`
- name: `?WinHttpOpen@WinhttpApiWrapper@OmadmClient@MDM@Windows@Microsoft@@UEAAJPEBGK0PEAPEAX@Z`
- size: `114`
- prototype: `int(Microsoft::Windows::MDM::OmadmClient::WinhttpApiWrapper *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int16 *, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140054550`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400545a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400545a3`
- `WINHTTP!WinHttpOpen` at `0x14005458b`
- `WINHTTP!WinHttpOpen` at `0x14005458b`

## pseudocode

```c
int __fastcall Microsoft::Windows::MDM::OmadmClient::WinhttpApiWrapper::WinHttpOpen(
        Microsoft::Windows::MDM::OmadmClient::WinhttpApiWrapper *this,
        const unsigned __int16 *a2,
        DWORD a3,
        const unsigned __int16 *a4,
        void **a5)
{
  int result; // eax
  void *v6; // rax

  if ( !a5 )
    return -805306126;
  *a5 = 0;
  v6 = WinHttpOpen(a2, a3, a4, 0, 0);
  if ( v6 )
  {
    *a5 = v6;
    return 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x140054550  push    rbx
0x140054552  sub     rsp, 30h
0x140054556  mov     rbx, [rsp+38h+arg_20]
0x14005455b  mov     rax, r9
0x14005455e  mov     r10d, r8d
0x140054561  mov     r11, rdx
0x140054564  test    rbx, rbx
0x140054567  jnz     short loc_140054570
0x140054569  mov     eax, 0D00000F2h
0x14005456e  jmp     short loc_1400545BB
0x140054570  xor     r9d, r9d; pszProxyBypassW
0x140054573  mov     qword ptr [rbx], 0
0x14005457a  mov     r8, rax; pszProxyW
0x14005457d  mov     [rsp+38h+dwFlags], 0; dwFlags
0x140054585  mov     edx, r10d; dwAccessType
0x140054588  mov     rcx, r11; pszAgentW
0x14005458b  call    cs:__imp_WinHttpOpen
0x140054592  nop     dword ptr [rax+rax+00h]
0x140054597  test    rax, rax
0x14005459a  jz      short loc_1400545A3
0x14005459c  mov     [rbx], rax
0x14005459f  xor     eax, eax
0x1400545a1  jmp     short loc_1400545BB
0x1400545a3  call    cs:__imp_GetLastError
0x1400545aa  nop     dword ptr [rax+rax+00h]
0x1400545af  test    eax, eax
0x1400545b1  jle     short loc_1400545BB
0x1400545b3  movzx   eax, ax
0x1400545b6  or      eax, 80070000h
0x1400545bb  add     rsp, 30h
0x1400545bf  pop     rbx
0x1400545c0  retn
```
