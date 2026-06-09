# CAdapterIpSettings::Initialize(_GUID *)

- ea: `0x18001d948`
- end: `0x18001d9ed`
- name: `?Initialize@CAdapterIpSettings@@QEAAJPEAU_GUID@@@Z`
- size: `165`
- prototype: `int(CAdapterIpSettings *__hidden this, struct _GUID *)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180018560`
- `0x18001ee3c`
- `0x18001fc90`
- `0x18001fe80`

## callees

- `0x18001d948`
- `0x18002d1d2`
- `0x18002d200`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001d9be`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001d9be`
- `WS2_32!__imp_WSAStartup` at `0x18001d989`
- `WS2_32!__imp_WSAStartup` at `0x18001d989`

## pseudocode

```c
int __fastcall CAdapterIpSettings::Initialize(CAdapterIpSettings *this, struct _GUID *a2)
{
  int result; // eax
  WSAData WSAData; // [rsp+20h] [rbp-1B8h] BYREF

  memset_0(&WSAData, 0, sizeof(WSAData));
  result = WSAStartup(0x202u, &WSAData);
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    *((_BYTE *)this + 42) = 1;
    if ( a2 )
    {
      *((struct _GUID *)this + 1) = *a2;
      result = StringFromCLSID(a2, (LPOLESTR *)this + 4);
      if ( result >= 0 )
        *((_BYTE *)this + 41) = 1;
    }
    else
    {
      return -2147024809;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001d948  mov     [rsp+arg_10], rbx
0x18001d94d  push    rdi
0x18001d94e  sub     rsp, 1D0h
0x18001d955  mov     rax, cs:__security_cookie
0x18001d95c  xor     rax, rsp
0x18001d95f  mov     [rsp+1D8h+var_18], rax
0x18001d967  mov     rdi, rdx
0x18001d96a  mov     rbx, rcx
0x18001d96d  xor     edx, edx; Val
0x18001d96f  lea     rcx, [rsp+1D8h+WSAData]; void *
0x18001d974  mov     r8d, 198h; Size
0x18001d97a  call    memset_0
0x18001d97f  mov     ecx, 202h; wVersionRequested
0x18001d984  lea     rdx, [rsp+1D8h+WSAData]; lpWSAData
0x18001d989  call    cs:__imp_WSAStartup
0x18001d98f  test    eax, eax
0x18001d991  jz      short loc_18001D99F
0x18001d993  jle     short loc_18001D9CC
0x18001d995  movzx   eax, ax
0x18001d998  or      eax, 80070000h
0x18001d99d  jmp     short loc_18001D9CC
0x18001d99f  mov     byte ptr [rbx+2Ah], 1
0x18001d9a3  test    rdi, rdi
0x18001d9a6  jnz     short loc_18001D9AF
0x18001d9a8  mov     eax, 80070057h
0x18001d9ad  jmp     short loc_18001D9CC
0x18001d9af  movups  xmm0, xmmword ptr [rdi]
0x18001d9b2  lea     rdx, [rbx+20h]; lplpsz
0x18001d9b6  mov     rcx, rdi; rclsid
0x18001d9b9  movdqu  xmmword ptr [rbx+10h], xmm0
0x18001d9be  call    cs:__imp_StringFromCLSID
0x18001d9c4  test    eax, eax
0x18001d9c6  js      short loc_18001D9CC
0x18001d9c8  mov     byte ptr [rbx+29h], 1
0x18001d9cc  mov     rcx, [rsp+1D8h+var_18]
0x18001d9d4  xor     rcx, rsp; StackCookie
0x18001d9d7  call    __security_check_cookie
0x18001d9dc  mov     rbx, [rsp+1D8h+arg_10]
0x18001d9e4  add     rsp, 1D0h
0x18001d9eb  pop     rdi
0x18001d9ec  retn
```
