# CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)

- ea: `0x14000a3bc`
- end: `0x14000a60e`
- name: `?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z`
- size: `594`
- prototype: `unsigned __int64 __fastcall(const struct CLRConfig::ConfigDWORDInfo *, __int64, bool *, __int64)`
- caller_count: `8`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140004b08`
- `0x140006188`
- `0x140009104`
- `0x14000ecf4`
- `0x14000ee28`
- `0x1400151b3`
- `0x140015309`
- `0x140015497`

## callees

- `0x14000a2ac`
- `0x14000a3bc`
- `0x14000fc30`
- `0x140013200`
- `0x140013f30`

## import_xrefs

- `ucrtbase_clr0400!_errno` at `0x14000a42c`
- `ucrtbase_clr0400!_errno` at `0x14000a449`
- `ucrtbase_clr0400!_errno` at `0x14000a51c`
- `ucrtbase_clr0400!_errno` at `0x14000a53a`
- `ucrtbase_clr0400!_errno` at `0x14000a42c`
- `ucrtbase_clr0400!_errno` at `0x14000a449`
- `ucrtbase_clr0400!_errno` at `0x14000a51c`
- `ucrtbase_clr0400!_errno` at `0x14000a53a`
- `ucrtbase_clr0400!wcstoul` at `0x14000a441`
- `ucrtbase_clr0400!wcstoul` at `0x14000a532`
- `ucrtbase_clr0400!wcstoul` at `0x14000a441`
- `ucrtbase_clr0400!wcstoul` at `0x14000a532`

## pseudocode

```c
unsigned __int64 __fastcall CLRConfig::GetConfigValue(
        const struct CLRConfig::ConfigDWORDInfo *a1,
        __int64 a2,
        bool *a3,
        __int64 a4)
{
  int v6; // esi
  wchar_t *v7; // rcx
  unsigned int v8; // esi
  unsigned __int64 result; // rax
  int v10; // r8d
  char v11; // dl
  char v12; // r15
  BOOL v13; // r14d
  unsigned int v14; // r8d
  unsigned int v15; // esi
  __int64 v16; // r9
  wchar_t *EndPtr; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *v18; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD v19[4]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v20[264]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t String[132]; // [rsp+168h] [rbp+68h] BYREF

  v6 = (*((_DWORD *)a1 + 3) >> 11) & 1;
  if ( (*((_DWORD *)a1 + 3) & 0x400) == 0 )
  {
    if ( CLRConfig::s_IsQuirkEnabledCallback )
    {
      v7 = *(wchar_t **)a1;
      LODWORD(EndPtr) = 0;
      if ( (int)CLRConfig::getQuirkEnabledAndValueFromWinDB(v7, (int *)&EndPtr, (struct _CPT_QUIRK_DATA *)v20) >= 0 )
      {
        if ( (_DWORD)EndPtr )
        {
          *_errno() = 0;
          v8 = wcstoul(String, &EndPtr, 0);
          if ( *_errno() != 34 && EndPtr != String )
          {
            *a3 = 0;
            return v8;
          }
          goto LABEL_29;
        }
      }
    }
  }
  v10 = *((_DWORD *)a1 + 3);
  v11 = ((v10 & 1) == 0) | 2;
  if ( (v10 & 8) != 0 )
    v11 = (*((_DWORD *)a1 + 3) & 1) == 0;
  v12 = v11 | 4;
  if ( (v10 & 4) != 0 )
    v12 = v11;
  v13 = (v10 & 2) == 0;
  if ( (v10 & 0x20) == 0 )
  {
    REGUTIL::GetConfigInteger(*(wchar_t **)a1, *((unsigned int *)a1 + 2), &EndPtr, a4, v12, v13, v6);
    result = (unsigned __int64)EndPtr;
    if ( (_DWORD)EndPtr != *((_DWORD *)a1 + 2) )
    {
LABEL_23:
      *a3 = 0;
      return result;
    }
  }
  v14 = *((_DWORD *)a1 + 3);
  if ( (v14 & 0x10) == 0
    && CLRConfig::s_GetConfigValueCallback
    && (int)CLRConfig::s_GetConfigValueCallback(*(_QWORD *)a1, &EndPtr, (v14 >> 6) & 1, (v14 >> 7) & 1) >= 0
    && EndPtr )
  {
    *_errno() = 0;
    v15 = wcstoul(EndPtr, &v18, 0);
    if ( *_errno() != 34 && v18 != EndPtr )
    {
      result = v15;
      goto LABEL_23;
    }
  }
  else
  {
    if ( (*((_BYTE *)a1 + 12) & 0x20) != 0 )
    {
      REGUTIL::GetConfigInteger(*(wchar_t **)a1, *((unsigned int *)a1 + 2), &v18, a4, v12, v13, v6);
      result = (unsigned __int64)v18;
      if ( (_DWORD)v18 != *((_DWORD *)a1 + 2) )
        goto LABEL_23;
    }
    if ( (*((_DWORD *)a1 + 3) & 0x200) != 0
      && CLRConfig::s_GetPerformanceDefaultValueCallback
      && (unsigned int)CLRConfig::s_GetPerformanceDefaultValueCallback(*(_QWORD *)a1, v19)
      && (int)REGUTIL::GetConfigInteger(*(wchar_t **)a1, *((unsigned int *)a1 + 2), &v18, v16, v12, v13, v6) < 0 )
    {
      result = v19[0];
      *a3 = 1;
      return result;
    }
  }
LABEL_29:
  *a3 = 1;
  return *((unsigned int *)a1 + 2);
}

```

## disassembly

```asm
0x14000a3bc  mov     [rsp-8+arg_8], rbx
0x14000a3c1  push    rbp
0x14000a3c2  push    rsi
0x14000a3c3  push    rdi
0x14000a3c4  push    r14
0x14000a3c6  push    r15
0x14000a3c8  lea     rbp, [rsp-180h]
0x14000a3d0  sub     rsp, 280h
0x14000a3d7  mov     rax, cs:__security_cookie
0x14000a3de  xor     rax, rsp
0x14000a3e1  mov     [rbp+1A0h+var_30], rax
0x14000a3e8  mov     esi, [rcx+0Ch]
0x14000a3eb  mov     rdi, r8
0x14000a3ee  shr     esi, 0Bh
0x14000a3f1  mov     rbx, rcx
0x14000a3f4  and     esi, 1
0x14000a3f7  test    dword ptr [rcx+0Ch], 400h
0x14000a3fe  jnz     short loc_14000A471
0x14000a400  cmp     cs:?s_IsQuirkEnabledCallback@CLRConfig@@0P6A_NPEBGK@ZEA, 0; bool (*CLRConfig::s_IsQuirkEnabledCallback)(ushort const *,ulong)
0x14000a408  jz      short loc_14000A471
0x14000a40a  mov     rcx, [rcx]; Source
0x14000a40d  lea     r8, [rsp+2A0h+var_240]; struct _CPT_QUIRK_DATA *
0x14000a412  and     dword ptr [rsp+2A0h+EndPtr], 0
0x14000a417  lea     rdx, [rsp+2A0h+EndPtr]; int *
0x14000a41c  call    ?getQuirkEnabledAndValueFromWinDB@CLRConfig@@SAJPEBGPEAHPEAU_CPT_QUIRK_DATA@@@Z; CLRConfig::getQuirkEnabledAndValueFromWinDB(ushort const *,int *,_CPT_QUIRK_DATA *)
0x14000a421  test    eax, eax
0x14000a423  js      short loc_14000A471
0x14000a425  cmp     dword ptr [rsp+2A0h+EndPtr], 0
0x14000a42a  jz      short loc_14000A471
0x14000a42c  call    cs:__imp__errno
0x14000a432  xor     r8d, r8d; Radix
0x14000a435  lea     rdx, [rsp+2A0h+EndPtr]; EndPtr
0x14000a43a  lea     rcx, [rbp+1A0h+String]; String
0x14000a43e  and     dword ptr [rax], 0
0x14000a441  call    cs:__imp_wcstoul
0x14000a447  mov     esi, eax
0x14000a449  call    cs:__imp__errno
0x14000a44f  cmp     dword ptr [rax], 22h ; '"'
0x14000a452  jz      loc_14000A5E2
0x14000a458  lea     rax, [rbp+1A0h+String]
0x14000a45c  cmp     [rsp+2A0h+EndPtr], rax
0x14000a461  jz      loc_14000A5E2
0x14000a467  mov     byte ptr [rdi], 0
0x14000a46a  mov     eax, esi
0x14000a46c  jmp     loc_14000A5E8
0x14000a471  mov     r8d, [rbx+0Ch]
0x14000a475  mov     eax, r8d
0x14000a478  mov     ecx, r8d
0x14000a47b  mov     r14d, r8d
0x14000a47e  not     ecx
0x14000a480  and     ecx, 1
0x14000a483  mov     edx, ecx
0x14000a485  or      edx, 2
0x14000a488  and     al, 8
0x14000a48a  mov     eax, r8d
0x14000a48d  cmovnz  edx, ecx
0x14000a490  mov     r15d, edx
0x14000a493  or      r15d, 4
0x14000a497  and     al, 4
0x14000a499  cmovnz  r15d, edx
0x14000a49d  shr     r14d, 1
0x14000a4a0  not     r14d
0x14000a4a3  and     r14d, 1
0x14000a4a7  test    r8b, 20h
0x14000a4ab  jnz     short loc_14000A4D9
0x14000a4ad  mov     edx, [rbx+8]
0x14000a4b0  lea     r8, [rsp+2A0h+EndPtr]
0x14000a4b5  mov     rcx, [rbx]
0x14000a4b8  mov     [rsp+2A0h+var_270], esi
0x14000a4bc  mov     [rsp+2A0h+var_278], r14d
0x14000a4c1  mov     [rsp+2A0h+var_280], r15d
0x14000a4c6  call    ?GetConfigInteger@REGUTIL@@CAJPEBG_KPEA_KHW4CORConfigLevel@1@HH@Z; REGUTIL::GetConfigInteger(ushort const *,unsigned __int64,unsigned __int64 *,int,REGUTIL::CORConfigLevel,int,int)
0x14000a4cb  mov     rax, [rsp+2A0h+EndPtr]
0x14000a4d0  cmp     eax, [rbx+8]
0x14000a4d3  jnz     loc_14000A58B
0x14000a4d9  mov     r8d, [rbx+0Ch]
0x14000a4dd  test    r8b, 10h
0x14000a4e1  jnz     short loc_14000A55D
0x14000a4e3  mov     rax, cs:?s_GetConfigValueCallback@CLRConfig@@0P6AJPEBGPEAPEBGHH@ZEA; long (*CLRConfig::s_GetConfigValueCallback)(ushort const *,ushort const * *,int,int)
0x14000a4ea  test    rax, rax
0x14000a4ed  jz      short loc_14000A55D
0x14000a4ef  mov     rcx, [rbx]
0x14000a4f2  lea     rdx, [rsp+2A0h+EndPtr]
0x14000a4f7  mov     r9d, r8d
0x14000a4fa  shr     r8d, 6
0x14000a4fe  shr     r9d, 7
0x14000a502  and     r8d, 1
0x14000a506  and     r9d, 1
0x14000a50a  call    cs:__guard_dispatch_icall_fptr
0x14000a510  test    eax, eax
0x14000a512  js      short loc_14000A55D
0x14000a514  cmp     [rsp+2A0h+EndPtr], 0
0x14000a51a  jz      short loc_14000A55D
0x14000a51c  call    cs:__imp__errno
0x14000a522  xor     r8d, r8d; Radix
0x14000a525  lea     rdx, [rsp+2A0h+var_258]; EndPtr
0x14000a52a  and     dword ptr [rax], 0
0x14000a52d  mov     rcx, [rsp+2A0h+EndPtr]; String
0x14000a532  call    cs:__imp_wcstoul
0x14000a538  mov     esi, eax
0x14000a53a  call    cs:__imp__errno
0x14000a540  cmp     dword ptr [rax], 22h ; '"'
0x14000a543  jz      loc_14000A5E2
0x14000a549  mov     rcx, [rsp+2A0h+EndPtr]
0x14000a54e  cmp     [rsp+2A0h+var_258], rcx
0x14000a553  jz      loc_14000A5E2
0x14000a559  mov     eax, esi
0x14000a55b  jmp     short loc_14000A58B
0x14000a55d  test    byte ptr [rbx+0Ch], 20h
0x14000a561  jz      short loc_14000A590
0x14000a563  mov     edx, [rbx+8]
0x14000a566  lea     r8, [rsp+2A0h+var_258]
0x14000a56b  mov     rcx, [rbx]
0x14000a56e  mov     [rsp+2A0h+var_270], esi
0x14000a572  mov     [rsp+2A0h+var_278], r14d
0x14000a577  mov     [rsp+2A0h+var_280], r15d
0x14000a57c  call    ?GetConfigInteger@REGUTIL@@CAJPEBG_KPEA_KHW4CORConfigLevel@1@HH@Z; REGUTIL::GetConfigInteger(ushort const *,unsigned __int64,unsigned __int64 *,int,REGUTIL::CORConfigLevel,int,int)
0x14000a581  mov     rax, [rsp+2A0h+var_258]
0x14000a586  cmp     eax, [rbx+8]
0x14000a589  jz      short loc_14000A590
0x14000a58b  mov     byte ptr [rdi], 0
0x14000a58e  jmp     short loc_14000A5E8
0x14000a590  test    dword ptr [rbx+0Ch], 200h
0x14000a597  jz      short loc_14000A5E2
0x14000a599  mov     rax, cs:?s_GetPerformanceDefaultValueCallback@CLRConfig@@0P6AHPEBGPEAK@ZEA; int (*CLRConfig::s_GetPerformanceDefaultValueCallback)(ushort const *,ulong *)
0x14000a5a0  test    rax, rax
0x14000a5a3  jz      short loc_14000A5E2
0x14000a5a5  mov     rcx, [rbx]
0x14000a5a8  lea     rdx, [rsp+2A0h+var_250]
0x14000a5ad  call    cs:__guard_dispatch_icall_fptr
0x14000a5b3  test    eax, eax
0x14000a5b5  jz      short loc_14000A5E2
0x14000a5b7  mov     edx, [rbx+8]
0x14000a5ba  lea     r8, [rsp+2A0h+var_258]
0x14000a5bf  mov     rcx, [rbx]
0x14000a5c2  mov     [rsp+2A0h+var_270], esi
0x14000a5c6  mov     [rsp+2A0h+var_278], r14d
0x14000a5cb  mov     [rsp+2A0h+var_280], r15d
0x14000a5d0  call    ?GetConfigInteger@REGUTIL@@CAJPEBG_KPEA_KHW4CORConfigLevel@1@HH@Z; REGUTIL::GetConfigInteger(ushort const *,unsigned __int64,unsigned __int64 *,int,REGUTIL::CORConfigLevel,int,int)
0x14000a5d5  test    eax, eax
0x14000a5d7  jns     short loc_14000A5E2
0x14000a5d9  mov     eax, [rsp+2A0h+var_250]
0x14000a5dd  mov     byte ptr [rdi], 1
0x14000a5e0  jmp     short loc_14000A5E8
0x14000a5e2  mov     byte ptr [rdi], 1
0x14000a5e5  mov     eax, [rbx+8]
0x14000a5e8  mov     rcx, [rbp+1A0h+var_30]
0x14000a5ef  xor     rcx, rsp; StackCookie
0x14000a5f2  call    __security_check_cookie
0x14000a5f7  mov     rbx, [rsp+2A0h+arg_8]
0x14000a5ff  add     rsp, 280h
0x14000a606  pop     r15
0x14000a608  pop     r14
0x14000a60a  pop     rdi
0x14000a60b  pop     rsi
0x14000a60c  pop     rbp
0x14000a60d  retn
```
