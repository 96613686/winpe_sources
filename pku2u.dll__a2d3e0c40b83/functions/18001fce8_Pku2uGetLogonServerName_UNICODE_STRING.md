# Pku2uGetLogonServerName(_UNICODE_STRING *)

- ea: `0x18001fce8`
- end: `0x18001fe28`
- name: `?Pku2uGetLogonServerName@@YAJPEAU_UNICODE_STRING@@@Z`
- size: `320`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180004830`
- `0x180038e7c`

## callees

- `0x180004d60`
- `0x180018870`
- `0x18001fce8`
- `0x180023d9c`
- `0x18002b744`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18001fd0a`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18001fdae`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18001fd0a`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18001fdae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fdd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fdd1`

## string_xrefs

- `0x18001fd31`: `onecore\ds\security\protocols\pku2u\token.cxx`
- `0x18001fdde`: `onecore\ds\security\protocols\pku2u\token.cxx`

## pseudocode

```c
__int64 __fastcall Pku2uGetLogonServerName(struct _UNICODE_STRING *a1)
{
  unsigned int v2; // ebx
  WCHAR *v4; // rax
  DWORD LastError; // eax
  struct _UNICODE_STRING v6; // [rsp+30h] [rbp-18h] BYREF
  DWORD nSize; // [rsp+58h] [rbp+10h] BYREF

  nSize = 0;
  v6 = 0;
  if ( GetComputerNameExW(ComputerNameNetBIOS, 0, &nSize) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        54,
        (unsigned int)&WPP_c43b604716f332f766453d0e055ebcf6_Traceguids,
        (unsigned int)"onecore\\ds\\security\\protocols\\pku2u\\token.cxx",
        52);
  }
  else if ( nSize < 0x104 )
  {
    v6.Length = 2 * nSize;
    v6.MaximumLength = 2 * nSize + 2;
    v4 = (WCHAR *)basessp::BaseSSP::WSTAllocate(Pku2uGlobalBaseSSP, v6.MaximumLength);
    v6.Buffer = v4;
    if ( !v4 )
    {
      v2 = -1073741670;
      goto LABEL_6;
    }
    if ( GetComputerNameExW(ComputerNameNetBIOS, v4, &nSize) )
    {
      *a1 = v6;
      v2 = 0;
      v6 = 0;
      goto LABEL_6;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_dsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        55,
        (unsigned int)&WPP_c43b604716f332f766453d0e055ebcf6_Traceguids,
        LastError,
        (__int64)"onecore\\ds\\security\\protocols\\pku2u\\token.cxx",
        71);
    }
  }
  v2 = -1073741823;
LABEL_6:
  KerbFreeString(&v6);
  return v2;
}

```

## disassembly

```asm
0x18001fce8  push    rbx
0x18001fcea  sub     rsp, 40h
0x18001fcee  mov     rbx, rcx
0x18001fcf1  mov     [rsp+48h+nSize], 0
0x18001fcf9  xorps   xmm0, xmm0
0x18001fcfc  lea     r8, [rsp+48h+nSize]; nSize
0x18001fd01  xor     ecx, ecx; NameType
0x18001fd03  xor     edx, edx; lpBuffer
0x18001fd05  movups  xmmword ptr [rsp+48h+var_18.Length], xmm0
0x18001fd0a  call    cs:__imp_GetComputerNameExW
0x18001fd10  test    eax, eax
0x18001fd12  jz      short loc_18001FD68
0x18001fd14  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fd1b  lea     rax, WPP_GLOBAL_Control
0x18001fd22  cmp     rcx, rax
0x18001fd25  jz      short loc_18001FD51
0x18001fd27  test    byte ptr [rcx+1Ch], 1
0x18001fd2b  jz      short loc_18001FD51
0x18001fd2d  mov     rcx, [rcx+10h]
0x18001fd31  lea     r9, aOnecoreDsSecur_3; "onecore\\ds\\security\\protocols\\pku2u"...
0x18001fd38  mov     edx, 36h ; '6'
0x18001fd3d  mov     dword ptr [rsp+48h+var_28], 0A34h
0x18001fd45  lea     r8, WPP_c43b604716f332f766453d0e055ebcf6_Traceguids
0x18001fd4c  call    WPP_SF_sd
0x18001fd51  mov     ebx, 0C0000001h
0x18001fd56  lea     rcx, [rsp+48h+var_18]; struct _UNICODE_STRING *
0x18001fd5b  call    ?KerbFreeString@@YAXPEAU_UNICODE_STRING@@@Z; KerbFreeString(_UNICODE_STRING *)
0x18001fd60  mov     eax, ebx
0x18001fd62  add     rsp, 40h
0x18001fd66  pop     rbx
0x18001fd67  retn
0x18001fd68  mov     eax, [rsp+48h+nSize]
0x18001fd6c  cmp     eax, 104h
0x18001fd71  jnb     short loc_18001FD51
0x18001fd73  mov     rcx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x18001fd7a  add     ax, ax
0x18001fd7d  mov     [rsp+48h+var_18.Length], ax
0x18001fd82  add     ax, 2
0x18001fd86  movzx   edx, ax; unsigned __int64
0x18001fd89  mov     [rsp+48h+var_18.MaximumLength], dx
0x18001fd8e  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x18001fd93  mov     [rsp+48h+var_18.Buffer], rax
0x18001fd98  test    rax, rax
0x18001fd9b  jnz     short loc_18001FDA4
0x18001fd9d  mov     ebx, 0C000009Ah
0x18001fda2  jmp     short loc_18001FD56
0x18001fda4  lea     r8, [rsp+48h+nSize]; nSize
0x18001fda9  mov     rdx, rax; lpBuffer
0x18001fdac  xor     ecx, ecx; NameType
0x18001fdae  call    cs:__imp_GetComputerNameExW
0x18001fdb4  test    eax, eax
0x18001fdb6  jnz     short loc_18001FE0F
0x18001fdb8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fdbf  lea     rax, WPP_GLOBAL_Control
0x18001fdc6  cmp     rcx, rax
0x18001fdc9  jz      short loc_18001FD51
0x18001fdcb  test    byte ptr [rcx+1Ch], 1
0x18001fdcf  jz      short loc_18001FD51
0x18001fdd1  call    cs:__imp_GetLastError
0x18001fdd7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fdde  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\protocols\\pku2u"...
0x18001fde5  mov     [rsp+48h+var_20], 0A47h
0x18001fded  mov     edx, 37h ; '7'
0x18001fdf2  mov     [rsp+48h+var_28], r8
0x18001fdf7  mov     r9d, eax
0x18001fdfa  lea     r8, WPP_c43b604716f332f766453d0e055ebcf6_Traceguids
0x18001fe01  mov     rcx, [rcx+10h]
0x18001fe05  call    WPP_SF_dsd
0x18001fe0a  jmp     loc_18001FD51
0x18001fe0f  movaps  xmm0, xmmword ptr [rsp+48h+var_18.Length]
0x18001fe14  xorps   xmm1, xmm1
0x18001fe17  movdqu  xmmword ptr [rbx], xmm0
0x18001fe1b  xor     ebx, ebx
0x18001fe1d  movdqa  xmmword ptr [rsp+48h+var_18.Length], xmm1
0x18001fe23  jmp     loc_18001FD56
```
