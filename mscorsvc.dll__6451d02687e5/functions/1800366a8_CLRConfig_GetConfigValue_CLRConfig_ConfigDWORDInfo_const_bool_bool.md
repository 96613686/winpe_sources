# CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)

- ea: `0x1800366a8`
- end: `0x1800368fa`
- name: `?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z`
- size: `594`
- prototype: `unsigned int __fastcall(const struct CLRConfig::ConfigDWORDInfo *, bool, bool *)`
- caller_count: `43`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180001060`
- `0x180002f0c`
- `0x180003630`
- `0x180004170`
- `0x180004cac`
- `0x1800050b4`
- `0x1800053a0`
- `0x1800064a8`
- `0x180007130`
- `0x180007518`
- `0x18000765c`
- `0x180010530`
- `0x18001458c`
- `0x180015208`
- `0x180016fd4`
- `0x180017a10`
- `0x180017d20`
- `0x180018270`
- `0x180018320`
- `0x1800183f0`
- `0x1800184a0`
- `0x180019444`
- `0x18001b340`
- `0x18001b800`
- `0x18001d274`
- `0x18001dcb0`
- `0x18001eed0`
- `0x18002b988`
- `0x18002d9f0`
- `0x18002dca8`
- `0x18002f454`
- `0x180035ef8`
- `0x180036030`
- `0x180036524`
- `0x180038ef0`
- `0x180039054`
- `0x18004057f`
- `0x18004158c`
- `0x180042db4`
- `0x180043449`
- `0x18004385c`
- `0x180044593`
- `0x180044b24`

## callees

- `0x180036598`
- `0x1800366a8`
- `0x180036dfc`
- `0x18003dc30`
- `0x18003f280`

## import_xrefs

- `ucrtbase_clr0400!wcstoul` at `0x18003672d`
- `ucrtbase_clr0400!wcstoul` at `0x18003681e`
- `ucrtbase_clr0400!wcstoul` at `0x18003672d`
- `ucrtbase_clr0400!wcstoul` at `0x18003681e`
- `ucrtbase_clr0400!_errno` at `0x180036718`
- `ucrtbase_clr0400!_errno` at `0x180036735`
- `ucrtbase_clr0400!_errno` at `0x180036808`
- `ucrtbase_clr0400!_errno` at `0x180036826`
- `ucrtbase_clr0400!_errno` at `0x180036718`
- `ucrtbase_clr0400!_errno` at `0x180036735`
- `ucrtbase_clr0400!_errno` at `0x180036808`
- `ucrtbase_clr0400!_errno` at `0x180036826`

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
0x1800366a8  mov     [rsp-8+arg_8], rbx
0x1800366ad  push    rbp
0x1800366ae  push    rsi
0x1800366af  push    rdi
0x1800366b0  push    r14
0x1800366b2  push    r15
0x1800366b4  lea     rbp, [rsp-180h]
0x1800366bc  sub     rsp, 280h
0x1800366c3  mov     rax, cs:__security_cookie
0x1800366ca  xor     rax, rsp
0x1800366cd  mov     [rbp+1A0h+var_30], rax
0x1800366d4  mov     esi, [rcx+0Ch]
0x1800366d7  mov     rdi, r8
0x1800366da  shr     esi, 0Bh
0x1800366dd  mov     rbx, rcx
0x1800366e0  and     esi, 1
0x1800366e3  test    dword ptr [rcx+0Ch], 400h
0x1800366ea  jnz     short loc_18003675D
0x1800366ec  cmp     cs:?s_IsQuirkEnabledCallback@CLRConfig@@0P6A_NPEBGK@ZEA, 0; bool (*CLRConfig::s_IsQuirkEnabledCallback)(ushort const *,ulong)
0x1800366f4  jz      short loc_18003675D
0x1800366f6  mov     rcx, [rcx]; Source
0x1800366f9  lea     r8, [rsp+2A0h+var_240]; struct _CPT_QUIRK_DATA *
0x1800366fe  and     dword ptr [rsp+2A0h+EndPtr], 0
0x180036703  lea     rdx, [rsp+2A0h+EndPtr]; int *
0x180036708  call    ?getQuirkEnabledAndValueFromWinDB@CLRConfig@@SAJPEBGPEAHPEAU_CPT_QUIRK_DATA@@@Z; CLRConfig::getQuirkEnabledAndValueFromWinDB(ushort const *,int *,_CPT_QUIRK_DATA *)
0x18003670d  test    eax, eax
0x18003670f  js      short loc_18003675D
0x180036711  cmp     dword ptr [rsp+2A0h+EndPtr], 0
0x180036716  jz      short loc_18003675D
0x180036718  call    cs:__imp__errno
0x18003671e  xor     r8d, r8d; Radix
0x180036721  lea     rdx, [rsp+2A0h+EndPtr]; EndPtr
0x180036726  lea     rcx, [rbp+1A0h+String]; String
0x18003672a  and     dword ptr [rax], 0
0x18003672d  call    cs:__imp_wcstoul
0x180036733  mov     esi, eax
0x180036735  call    cs:__imp__errno
0x18003673b  cmp     dword ptr [rax], 22h ; '"'
0x18003673e  jz      loc_1800368CE
0x180036744  lea     rax, [rbp+1A0h+String]
0x180036748  cmp     [rsp+2A0h+EndPtr], rax
0x18003674d  jz      loc_1800368CE
0x180036753  mov     byte ptr [rdi], 0
0x180036756  mov     eax, esi
0x180036758  jmp     loc_1800368D4
0x18003675d  mov     r8d, [rbx+0Ch]
0x180036761  mov     eax, r8d
0x180036764  mov     ecx, r8d
0x180036767  mov     r14d, r8d
0x18003676a  not     ecx
0x18003676c  and     ecx, 1
0x18003676f  mov     edx, ecx
0x180036771  or      edx, 2
0x180036774  and     al, 8
0x180036776  mov     eax, r8d
0x180036779  cmovnz  edx, ecx
0x18003677c  mov     r15d, edx
0x18003677f  or      r15d, 4
0x180036783  and     al, 4
0x180036785  cmovnz  r15d, edx
0x180036789  shr     r14d, 1
0x18003678c  not     r14d
0x18003678f  and     r14d, 1
0x180036793  test    r8b, 20h
0x180036797  jnz     short loc_1800367C5
0x180036799  mov     edx, [rbx+8]
0x18003679c  lea     r8, [rsp+2A0h+EndPtr]
0x1800367a1  mov     rcx, [rbx]
0x1800367a4  mov     [rsp+2A0h+var_270], esi
0x1800367a8  mov     [rsp+2A0h+var_278], r14d
0x1800367ad  mov     [rsp+2A0h+var_280], r15d
0x1800367b2  call    ?GetConfigInteger@REGUTIL@@CAJPEBG_KPEA_KHW4CORConfigLevel@1@HH@Z; REGUTIL::GetConfigInteger(ushort const *,unsigned __int64,unsigned __int64 *,int,REGUTIL::CORConfigLevel,int,int)
0x1800367b7  mov     rax, [rsp+2A0h+EndPtr]
0x1800367bc  cmp     eax, [rbx+8]
0x1800367bf  jnz     loc_180036877
0x1800367c5  mov     r8d, [rbx+0Ch]
0x1800367c9  test    r8b, 10h
0x1800367cd  jnz     short loc_180036849
0x1800367cf  mov     rax, cs:?s_GetConfigValueCallback@CLRConfig@@0P6AJPEBGPEAPEBGHH@ZEA; long (*CLRConfig::s_GetConfigValueCallback)(ushort const *,ushort const * *,int,int)
0x1800367d6  test    rax, rax
0x1800367d9  jz      short loc_180036849
0x1800367db  mov     rcx, [rbx]
0x1800367de  lea     rdx, [rsp+2A0h+EndPtr]
0x1800367e3  mov     r9d, r8d
0x1800367e6  shr     r8d, 6
0x1800367ea  shr     r9d, 7
0x1800367ee  and     r8d, 1
0x1800367f2  and     r9d, 1
0x1800367f6  call    cs:__guard_dispatch_icall_fptr
0x1800367fc  test    eax, eax
0x1800367fe  js      short loc_180036849
0x180036800  cmp     [rsp+2A0h+EndPtr], 0
0x180036806  jz      short loc_180036849
0x180036808  call    cs:__imp__errno
0x18003680e  xor     r8d, r8d; Radix
0x180036811  lea     rdx, [rsp+2A0h+var_258]; EndPtr
0x180036816  and     dword ptr [rax], 0
0x180036819  mov     rcx, [rsp+2A0h+EndPtr]; String
0x18003681e  call    cs:__imp_wcstoul
0x180036824  mov     esi, eax
0x180036826  call    cs:__imp__errno
0x18003682c  cmp     dword ptr [rax], 22h ; '"'
0x18003682f  jz      loc_1800368CE
0x180036835  mov     rcx, [rsp+2A0h+EndPtr]
0x18003683a  cmp     [rsp+2A0h+var_258], rcx
0x18003683f  jz      loc_1800368CE
0x180036845  mov     eax, esi
0x180036847  jmp     short loc_180036877
0x180036849  test    byte ptr [rbx+0Ch], 20h
0x18003684d  jz      short loc_18003687C
0x18003684f  mov     edx, [rbx+8]
0x180036852  lea     r8, [rsp+2A0h+var_258]
0x180036857  mov     rcx, [rbx]
0x18003685a  mov     [rsp+2A0h+var_270], esi
0x18003685e  mov     [rsp+2A0h+var_278], r14d
0x180036863  mov     [rsp+2A0h+var_280], r15d
0x180036868  call    ?GetConfigInteger@REGUTIL@@CAJPEBG_KPEA_KHW4CORConfigLevel@1@HH@Z; REGUTIL::GetConfigInteger(ushort const *,unsigned __int64,unsigned __int64 *,int,REGUTIL::CORConfigLevel,int,int)
0x18003686d  mov     rax, [rsp+2A0h+var_258]
0x180036872  cmp     eax, [rbx+8]
0x180036875  jz      short loc_18003687C
0x180036877  mov     byte ptr [rdi], 0
0x18003687a  jmp     short loc_1800368D4
0x18003687c  test    dword ptr [rbx+0Ch], 200h
0x180036883  jz      short loc_1800368CE
0x180036885  mov     rax, cs:?s_GetPerformanceDefaultValueCallback@CLRConfig@@0P6AHPEBGPEAK@ZEA; int (*CLRConfig::s_GetPerformanceDefaultValueCallback)(ushort const *,ulong *)
0x18003688c  test    rax, rax
0x18003688f  jz      short loc_1800368CE
0x180036891  mov     rcx, [rbx]
0x180036894  lea     rdx, [rsp+2A0h+var_250]
0x180036899  call    cs:__guard_dispatch_icall_fptr
0x18003689f  test    eax, eax
0x1800368a1  jz      short loc_1800368CE
0x1800368a3  mov     edx, [rbx+8]
0x1800368a6  lea     r8, [rsp+2A0h+var_258]
0x1800368ab  mov     rcx, [rbx]
0x1800368ae  mov     [rsp+2A0h+var_270], esi
0x1800368b2  mov     [rsp+2A0h+var_278], r14d
0x1800368b7  mov     [rsp+2A0h+var_280], r15d
0x1800368bc  call    ?GetConfigInteger@REGUTIL@@CAJPEBG_KPEA_KHW4CORConfigLevel@1@HH@Z; REGUTIL::GetConfigInteger(ushort const *,unsigned __int64,unsigned __int64 *,int,REGUTIL::CORConfigLevel,int,int)
0x1800368c1  test    eax, eax
0x1800368c3  jns     short loc_1800368CE
0x1800368c5  mov     eax, [rsp+2A0h+var_250]
0x1800368c9  mov     byte ptr [rdi], 1
0x1800368cc  jmp     short loc_1800368D4
0x1800368ce  mov     byte ptr [rdi], 1
0x1800368d1  mov     eax, [rbx+8]
0x1800368d4  mov     rcx, [rbp+1A0h+var_30]
0x1800368db  xor     rcx, rsp; StackCookie
0x1800368de  call    __security_check_cookie
0x1800368e3  mov     rbx, [rsp+2A0h+arg_8]
0x1800368eb  add     rsp, 280h
0x1800368f2  pop     r15
0x1800368f4  pop     r14
0x1800368f6  pop     rdi
0x1800368f7  pop     rsi
0x1800368f8  pop     rbp
0x1800368f9  retn
```
