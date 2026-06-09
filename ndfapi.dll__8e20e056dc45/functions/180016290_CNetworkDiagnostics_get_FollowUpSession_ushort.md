# CNetworkDiagnostics::get_FollowUpSession(ushort * *)

- ea: `0x180016290`
- end: `0x180016354`
- name: `?get_FollowUpSession@CNetworkDiagnostics@@UEAAJPEAPEAG@Z`
- size: `196`
- prototype: `__int64 __fastcall(CNetworkDiagnostics *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180016290`
- `0x18001f646`
- `0x18001f690`

## import_xrefs

- `ole32!StringFromCLSID` at `0x18001630a`
- `ole32!StringFromCLSID` at `0x18001630a`
- `ole32!CoTaskMemFree` at `0x180016334`
- `ole32!CoTaskMemFree` at `0x180016334`
- `OLEAUT32!__imp_SysAllocString` at `0x18001631b`
- `OLEAUT32!__imp_SysAllocString` at `0x18001631b`

## pseudocode

```c
__int64 __fastcall CNetworkDiagnostics::get_FollowUpSession(CNetworkDiagnostics *this, unsigned __int16 **a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  unsigned __int16 *v6; // rax
  LPOLESTR lpsz; // [rsp+20h] [rbp-28h] BYREF
  IID Buf2; // [rsp+28h] [rbp-20h] BYREF

  if ( *((int *)this + 30) < 3 )
    return 2147943176LL;
  v4 = *((_QWORD *)this + 2);
  Buf2 = 0;
  Buf2 = *(IID *)(v4 + 3064);
  if ( !memcmp_0(qword_1800276A8, &Buf2, 0x10u) )
  {
    return (unsigned int)-2147023728;
  }
  else
  {
    lpsz = 0;
    v5 = StringFromCLSID(&Buf2, &lpsz);
    if ( !v5 )
    {
      v6 = SysAllocString(lpsz);
      *a2 = v6;
      if ( !v6 )
        v5 = -2147024882;
      CoTaskMemFree(lpsz);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180016290  mov     [rsp+arg_10], rbx
0x180016295  push    rdi
0x180016296  sub     rsp, 40h
0x18001629a  mov     rax, cs:__security_cookie
0x1800162a1  xor     rax, rsp
0x1800162a4  mov     [rsp+48h+var_10], rax
0x1800162a9  cmp     dword ptr [rcx+78h], 3
0x1800162ad  mov     rdi, rdx
0x1800162b0  jge     short loc_1800162BC
0x1800162b2  mov     eax, 80070308h
0x1800162b7  jmp     loc_18001633C
0x1800162bc  mov     rax, [rcx+10h]
0x1800162c0  lea     rdx, [rsp+48h+Buf2]; Buf2
0x1800162c5  xorps   xmm0, xmm0
0x1800162c8  lea     rcx, qword_1800276A8; Buf1
0x1800162cf  movups  [rsp+48h+Buf2], xmm0
0x1800162d4  mov     r8d, 10h; Size
0x1800162da  movups  xmm1, xmmword ptr [rax+0BF8h]
0x1800162e1  movdqu  [rsp+48h+Buf2], xmm1
0x1800162e7  call    memcmp_0
0x1800162ec  test    eax, eax
0x1800162ee  jnz     short loc_1800162F7
0x1800162f0  mov     ebx, 80070490h
0x1800162f5  jmp     short loc_18001633A
0x1800162f7  lea     rdx, [rsp+48h+lpsz]; lplpsz
0x1800162fc  mov     [rsp+48h+lpsz], 0
0x180016305  lea     rcx, [rsp+48h+Buf2]; rclsid
0x18001630a  call    cs:__imp_StringFromCLSID
0x180016310  mov     ebx, eax
0x180016312  test    eax, eax
0x180016314  jnz     short loc_18001633A
0x180016316  mov     rcx, [rsp+48h+lpsz]; psz
0x18001631b  call    cs:__imp_SysAllocString
0x180016321  test    rax, rax
0x180016324  mov     [rdi], rax
0x180016327  mov     ecx, 8007000Eh
0x18001632c  cmovz   ebx, ecx
0x18001632f  mov     rcx, [rsp+48h+lpsz]; pv
0x180016334  call    cs:__imp_CoTaskMemFree
0x18001633a  mov     eax, ebx
0x18001633c  mov     rcx, [rsp+48h+var_10]
0x180016341  xor     rcx, rsp; StackCookie
0x180016344  call    __security_check_cookie
0x180016349  mov     rbx, [rsp+48h+arg_10]
0x18001634e  add     rsp, 40h
0x180016352  pop     rdi
0x180016353  retn
```
