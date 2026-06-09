# NcaApiSrvImplInitialize(void)

- ea: `0x180006ec0`
- end: `0x180007048`
- name: `?NcaApiSrvImplInitialize@@YAJXZ`
- size: `392`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004f04`
- `0x180004f34`
- `0x180006ec0`
- `0x180007360`
- `0x180018ffc`
- `0x18001cc3e`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006faf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006faf`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180006f9f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180006f9f`

## pseudocode

```c
__int64 NcaApiSrvImplInitialize(void)
{
  int v0; // eax
  unsigned int v1; // ebx
  signed int LastError; // eax
  PVOID *v3; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids);
  memset_0(&gNcaApiSrvImpl, 0, 0x80u);
  qword_180028C88 = (__int64)&qword_180028C80;
  qword_180028C80 = (__int64)&qword_180028C80;
  qword_180028C98 = (__int64)&qword_180028C90;
  qword_180028C90 = (__int64)&qword_180028C90;
  qword_180028C78 = (__int64)&qword_180028C70;
  qword_180028C70 = (__int64)&qword_180028C70;
  v0 = NcaCriticalSectionCreate(&gNcaApiSrvImpl);
  v1 = v0;
  if ( v0 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids,
        (unsigned int)v0);
    goto LABEL_15;
  }
  if ( ConvertStringSidToSidW(L"SY", &SidToCheck) )
  {
    dword_180028CB4 = 1;
    goto LABEL_17;
  }
  LastError = GetLastError();
  v1 = LastError;
  if ( LastError > 0 )
    v1 = (unsigned __int16)LastError | 0x80070000;
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids, v1);
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (v1 & 0x80000000) != 0 )
  {
LABEL_15:
    NcaApiSrvImplShutdown();
LABEL_17:
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 8) != 0 )
    WPP_SF_d(v3[2], 13, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x180006ec0  mov     [rsp+arg_0], rbx
0x180006ec5  push    rdi
0x180006ec6  sub     rsp, 20h
0x180006eca  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ed1  lea     rdi, WPP_GLOBAL_Control
0x180006ed8  cmp     rcx, rdi
0x180006edb  jz      short loc_180006EF8
0x180006edd  test    byte ptr [rcx+1Ch], 8
0x180006ee1  jz      short loc_180006EF8
0x180006ee3  mov     rcx, [rcx+10h]
0x180006ee7  lea     r8, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids
0x180006eee  mov     edx, 0Ah
0x180006ef3  call    WPP_SF_
0x180006ef8  xor     edx, edx; Val
0x180006efa  lea     rcx, ?gNcaApiSrvImpl@@3UNCA_API_SRV_IMPL_COMPONENT_@@A; void *
0x180006f01  mov     r8d, 80h; Size
0x180006f07  call    memset_0
0x180006f0c  lea     rax, qword_180028C80
0x180006f13  mov     cs:qword_180028C88, rax
0x180006f1a  lea     rcx, ?gNcaApiSrvImpl@@3UNCA_API_SRV_IMPL_COMPONENT_@@A; lpCriticalSection
0x180006f21  mov     cs:qword_180028C80, rax
0x180006f28  lea     rax, qword_180028C90
0x180006f2f  mov     cs:qword_180028C98, rax
0x180006f36  mov     cs:qword_180028C90, rax
0x180006f3d  lea     rax, qword_180028C70
0x180006f44  mov     cs:qword_180028C78, rax
0x180006f4b  mov     cs:qword_180028C70, rax
0x180006f52  call    NcaCriticalSectionCreate
0x180006f57  mov     ebx, eax
0x180006f59  test    eax, eax
0x180006f5b  jns     short loc_180006F91
0x180006f5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f64  cmp     rcx, rdi
0x180006f67  jz      loc_180006FFF
0x180006f6d  test    byte ptr [rcx+1Ch], 1
0x180006f71  jz      loc_180006FFF
0x180006f77  mov     rcx, [rcx+10h]
0x180006f7b  lea     r8, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids
0x180006f82  mov     edx, 0Bh
0x180006f87  mov     r9d, eax
0x180006f8a  call    WPP_SF_d
0x180006f8f  jmp     short loc_180006FFF
0x180006f91  lea     rdx, SidToCheck; Sid
0x180006f98  lea     rcx, StringSid; "SY"
0x180006f9f  call    cs:__imp_ConvertStringSidToSidW
0x180006fa6  nop     dword ptr [rax+rax+00h]
0x180006fab  test    eax, eax
0x180006fad  jnz     short loc_180007006
0x180006faf  call    cs:__imp_GetLastError
0x180006fb6  nop     dword ptr [rax+rax+00h]
0x180006fbb  mov     ebx, eax
0x180006fbd  test    eax, eax
0x180006fbf  jle     short loc_180006FCA
0x180006fc1  movzx   ebx, ax
0x180006fc4  or      ebx, 80070000h
0x180006fca  mov     rcx, cs:WPP_GLOBAL_Control
0x180006fd1  cmp     rcx, rdi
0x180006fd4  jz      short loc_180006FFB
0x180006fd6  test    byte ptr [rcx+1Ch], 1
0x180006fda  jz      short loc_180006FFB
0x180006fdc  mov     rcx, [rcx+10h]
0x180006fe0  lea     r8, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids
0x180006fe7  mov     edx, 0Ch
0x180006fec  mov     r9d, ebx
0x180006fef  call    WPP_SF_d
0x180006ff4  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ffb  test    ebx, ebx
0x180006ffd  jns     short loc_180007017
0x180006fff  call    ?NcaApiSrvImplShutdown@@YAXXZ; NcaApiSrvImplShutdown(void)
0x180007004  jmp     short loc_180007010
0x180007006  mov     cs:dword_180028CB4, 1
0x180007010  mov     rcx, cs:WPP_GLOBAL_Control
0x180007017  cmp     rcx, rdi
0x18000701a  jz      short loc_18000703A
0x18000701c  test    byte ptr [rcx+1Ch], 8
0x180007020  jz      short loc_18000703A
0x180007022  mov     rcx, [rcx+10h]
0x180007026  lea     r8, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids
0x18000702d  mov     edx, 0Dh
0x180007032  mov     r9d, ebx
0x180007035  call    WPP_SF_d
0x18000703a  mov     eax, ebx
0x18000703c  mov     rbx, [rsp+28h+arg_0]
0x180007041  add     rsp, 20h
0x180007045  pop     rdi
0x180007046  retn
```
