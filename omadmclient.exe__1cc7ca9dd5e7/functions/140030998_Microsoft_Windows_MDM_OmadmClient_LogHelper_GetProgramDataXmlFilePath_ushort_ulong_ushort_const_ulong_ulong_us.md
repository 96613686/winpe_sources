# Microsoft::Windows::MDM::OmadmClient::LogHelper::GetProgramDataXmlFilePath(ushort *,ulong,ushort const *,ulong,ulong,ushort const *)

- ea: `0x140030998`
- end: `0x140030ab9`
- name: `?GetProgramDataXmlFilePath@LogHelper@OmadmClient@MDM@Windows@Microsoft@@KAJPEAGKPEBGKK1@Z`
- size: `289`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned int@<edx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140031250`
- `0x140031560`

## callees

- `0x140003450`
- `0x14000b0f4`
- `0x14000bf50`
- `0x140030998`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400309f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400309f3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1400309e3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1400309e3`

## string_xrefs

- `0x1400309ce`: `%ProgramData%`
- `0x140030a68`: `%s\Microsoft\OmaDmClient\%s\%d\%d-%s.xml`

## pseudocode

```c
signed int __fastcall Microsoft::Windows::MDM::OmadmClient::LogHelper::GetProgramDataXmlFilePath(
        unsigned __int16 *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned int a5,
        const unsigned __int16 *a6)
{
  int v6; // esi
  signed int result; // eax
  int v9; // ebx
  __int64 v10; // rdx
  int v11; // [rsp+20h] [rbp-258h]
  WCHAR Dst[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  v6 = (int)a3;
  Dst[0] = 0;
  if ( ExpandEnvironmentStringsW(L"%ProgramData%", Dst, 0x104u) )
  {
    if ( a6 )
    {
      v11 = v6;
      v9 = StringCchPrintfW(a1, 0x104u, L"%s\\Microsoft\\OmaDmClient\\%s\\%d\\%d-%s.xml", Dst);
      if ( v9 < 0 )
      {
        v10 = 666;
        goto LABEL_7;
      }
    }
    else
    {
      v11 = v6;
      v9 = StringCchPrintfW(a1, 0x104u, L"%s\\Microsoft\\OmaDmClient\\%s\\%d", Dst);
      if ( v9 < 0 )
      {
        v10 = 653;
LABEL_7:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v10,
          (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\loghelper.cpp",
          (const char *)(unsigned int)v9,
          v11);
        return v9;
      }
    }
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140030998  mov     [rsp+arg_8], rbx
0x14003099d  push    rbp
0x14003099e  push    rsi
0x14003099f  push    rdi
0x1400309a0  sub     rsp, 260h
0x1400309a7  mov     rax, cs:__security_cookie
0x1400309ae  xor     rax, rsp
0x1400309b1  mov     [rsp+278h+var_28], rax
0x1400309b9  mov     rbx, [rsp+278h+arg_28]
0x1400309c1  lea     rdx, [rsp+278h+Dst]; lpDst
0x1400309c6  mov     rsi, r8
0x1400309c9  mov     rdi, rcx
0x1400309cc  xor     eax, eax
0x1400309ce  lea     rcx, Src; "%ProgramData%"
0x1400309d5  mov     r8d, 104h; nSize
0x1400309db  mov     [rsp+278h+Dst], ax
0x1400309e0  mov     ebp, r9d
0x1400309e3  call    cs:__imp_ExpandEnvironmentStringsW
0x1400309ea  nop     dword ptr [rax+rax+00h]
0x1400309ef  test    eax, eax
0x1400309f1  jnz     short loc_140030A14
0x1400309f3  call    cs:__imp_GetLastError
0x1400309fa  nop     dword ptr [rax+rax+00h]
0x1400309ff  test    eax, eax
0x140030a01  jle     loc_140030A95
0x140030a07  movzx   eax, ax
0x140030a0a  or      eax, 80070000h
0x140030a0f  jmp     loc_140030A95
0x140030a14  lea     r9, [rsp+278h+Dst]
0x140030a19  mov     edx, 104h; unsigned __int64
0x140030a1e  mov     rcx, rdi; unsigned __int16 *
0x140030a21  test    rbx, rbx
0x140030a24  jnz     short loc_140030A61
0x140030a26  mov     [rsp+278h+var_250], ebp
0x140030a2a  lea     r8, aSMicrosoftOmad; "%s\\Microsoft\\OmaDmClient\\%s\\%d"
0x140030a31  mov     qword ptr [rsp+278h+var_258], rsi; int
0x140030a36  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140030a3b  mov     ebx, eax
0x140030a3d  test    eax, eax
0x140030a3f  jns     short loc_140030A93
0x140030a41  mov     edx, 28Dh; void *
0x140030a46  mov     rcx, [rsp+278h]; this
0x140030a4e  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x140030a55  mov     r9d, ebx; char *
0x140030a58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140030a5d  mov     eax, ebx
0x140030a5f  jmp     short loc_140030A95
0x140030a61  mov     eax, [rsp+278h+arg_20]
0x140030a68  lea     r8, aSMicrosoftOmad_0; "%s\\Microsoft\\OmaDmClient\\%s\\%d\\%d-"...
0x140030a6f  mov     [rsp+278h+var_240], rbx
0x140030a74  mov     [rsp+278h+var_248], eax
0x140030a78  mov     [rsp+278h+var_250], ebp
0x140030a7c  mov     qword ptr [rsp+278h+var_258], rsi
0x140030a81  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140030a86  mov     ebx, eax
0x140030a88  test    eax, eax
0x140030a8a  jns     short loc_140030A93
0x140030a8c  mov     edx, 29Ah
0x140030a91  jmp     short loc_140030A46
0x140030a93  xor     eax, eax
0x140030a95  mov     rcx, [rsp+278h+var_28]
0x140030a9d  xor     rcx, rsp; StackCookie
0x140030aa0  call    __security_check_cookie
0x140030aa5  mov     rbx, [rsp+278h+arg_8]
0x140030aad  add     rsp, 260h
0x140030ab4  pop     rdi
0x140030ab5  pop     rsi
0x140030ab6  pop     rbp
0x140030ab7  retn
```
