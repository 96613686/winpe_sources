# DeleteRegistryValue(_GPOINFO *,ushort const *,ushort const *,ulong,ulong,uchar *,ushort const *,ushort const *,_REGHASHTABLE *,_REGHASHTABLE *)

- ea: `0x18004aa50`
- end: `0x18004acb9`
- name: `?DeleteRegistryValue@@YAHPEAU_GPOINFO@@PEBG1KKPEAE11PEAU_REGHASHTABLE@@3@Z`
- size: `617`
- prototype: `int(struct _GPOINFO *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, unsigned __int8 *, const unsigned __int16 *, const unsigned __int16 *, struct _REGHASHTABLE *, struct _REGHASHTABLE *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18004aa50`
- `0x18004acc0`
- `0x180075ec0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18004ab1d`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18004ab1d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ac9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ac9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004aa70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ac38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004aa70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ac38`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004aab3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004aada`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004ab01`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004aab3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004aada`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004ab01`
- `ext-ms-win-devmgmt-policy-l1-1-2!MDMWinsOverGP_IsGPPolicySetByMDMEx` at `0x18004aba4`
- `ext-ms-win-devmgmt-policy-l1-1-2!MDMWinsOverGP_IsGPPolicySetByMDMEx` at `0x18004aba4`

## string_xrefs

- `0x18004abf3`: `DeleteRegistryValue: Deleted %s\%s`
- `0x18004ac25`: `DeleteRegistryValue: Deleted %s\%s`
- `0x18004ac5e`: `DeleteRegistryValue: Failed to delete %s\%s`
- `0x18004ac89`: `DeleteRegistryValue: Failed to delete %s\%s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DeleteRegistryValue(struct _GPOINFO *a1, WCHAR *a2, const unsigned __int16 *a3, int a4)
{
  DWORD LastError; // ebx
  unsigned int v9; // r14d
  int v10; // r15d
  int v11; // r15d
  __int64 v12; // rcx
  int v13; // eax
  __int128 v15; // [rsp+38h] [rbp-40h] BYREF
  __int128 v16; // [rsp+48h] [rbp-30h]
  __int128 v17; // [rsp+58h] [rbp-20h]
  int v18; // [rsp+C8h] [rbp+50h] BYREF

  LastError = GetLastError();
  v9 = 1;
  if ( !a2
    || !*a2
    || CompareStringW(0x7Fu, 1u, L"Software\\Policies", 17, a2, 17) != 2
    && CompareStringW(0x7Fu, 1u, L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies", 50, a2, 50) != 2
    && CompareStringW(0x7Fu, 1u, L"System\\CurrentControlSet\\Policies", 33, a2, 33) != 2
    || a3 && wcsnlen(a3, 0x104u) > 1 && *a3 == 42 && a3[1] == 42 )
  {
    goto LABEL_34;
  }
  v18 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v10 = a4 - 1;
  if ( !v10 )
  {
    DWORD2(v15) = 2;
LABEL_16:
    *(_QWORD *)&v15 = 0x200000001LL;
    v12 = *((_QWORD *)a1 + 9);
    HIDWORD(v15) = v12 != 0;
    LODWORD(v16) = 1;
    *((_QWORD *)&v16 + 1) = v12;
    if ( (int)MDMWinsOverGP_IsGPPolicySetByMDMEx(a2, a3, &v15, &v18) >= 0 )
    {
      v13 = v18;
    }
    else
    {
      v13 = 0;
      v18 = 0;
    }
    if ( v13 )
      goto LABEL_34;
    goto LABEL_20;
  }
  v11 = v10 - 3;
  if ( !v11 )
  {
    DWORD2(v15) = 1;
    goto LABEL_16;
  }
  if ( v11 == 3 )
  {
    DWORD2(v15) = 4;
    goto LABEL_16;
  }
LABEL_20:
  if ( (unsigned int)RegCleanUpValue(*((HKEY *)a1 + 5), a2, a3) )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"DeleteRegistryValue: Deleted %s\\%s", a2, a3);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"DeleteRegistryValue: Deleted %s\\%s", a2, a3);
      }
    }
  }
  else
  {
    LastError = GetLastError();
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"DeleteRegistryValue: Failed to delete %s\\%s", a2, a3);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"DeleteRegistryValue: Failed to delete %s\\%s", a2, a3);
      }
    }
    v9 = 0;
  }
LABEL_34:
  SetLastError(LastError);
  return v9;
}

```

## disassembly

```asm
0x18004aa50  push    rbp
0x18004aa52  push    rbx
0x18004aa53  push    rsi
0x18004aa54  push    rdi
0x18004aa55  push    r12
0x18004aa57  push    r13
0x18004aa59  push    r14
0x18004aa5b  push    r15
0x18004aa5d  mov     rbp, rsp
0x18004aa60  sub     rsp, 78h
0x18004aa64  mov     r15d, r9d
0x18004aa67  mov     rdi, r8
0x18004aa6a  mov     rsi, rdx
0x18004aa6d  mov     r13, rcx
0x18004aa70  call    cs:__imp_GetLastError
0x18004aa76  mov     ebx, eax
0x18004aa78  mov     [rbp+var_48], eax
0x18004aa7b  mov     r14d, 1
0x18004aa81  xor     r12d, r12d
0x18004aa84  test    rsi, rsi
0x18004aa87  jz      loc_18004AC9D
0x18004aa8d  cmp     [rsi], r12w
0x18004aa91  jz      loc_18004AC9D
0x18004aa97  lea     r9d, [r14+10h]; cchCount1
0x18004aa9b  mov     [rsp+78h+cchCount2], r9d; cchCount2
0x18004aaa0  mov     [rsp+78h+lpString2], rsi; lpString2
0x18004aaa5  lea     r8, String1; "Software\\Policies"
0x18004aaac  mov     edx, r14d; dwCmpFlags
0x18004aaaf  lea     ecx, [r14+7Eh]; Locale
0x18004aab3  call    cs:__imp_CompareStringW
0x18004aab9  cmp     eax, 2
0x18004aabc  jz      short loc_18004AB10
0x18004aabe  lea     r9d, [r14+31h]; cchCount1
0x18004aac2  mov     [rsp+78h+cchCount2], r9d; cchCount2
0x18004aac7  mov     [rsp+78h+lpString2], rsi; lpString2
0x18004aacc  lea     r8, aSoftwareMicros_26; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004aad3  mov     edx, r14d; dwCmpFlags
0x18004aad6  lea     ecx, [r14+7Eh]; Locale
0x18004aada  call    cs:__imp_CompareStringW
0x18004aae0  cmp     eax, 2
0x18004aae3  jz      short loc_18004AB10
0x18004aae5  lea     r9d, [r14+20h]; cchCount1
0x18004aae9  mov     [rsp+78h+cchCount2], r9d; cchCount2
0x18004aaee  mov     [rsp+78h+lpString2], rsi; lpString2
0x18004aaf3  lea     r8, aSystemCurrentc; "System\\CurrentControlSet\\Policies"
0x18004aafa  mov     edx, r14d; dwCmpFlags
0x18004aafd  lea     ecx, [r14+7Eh]; Locale
0x18004ab01  call    cs:__imp_CompareStringW
0x18004ab07  cmp     eax, 2
0x18004ab0a  jnz     loc_18004AC9D
0x18004ab10  test    rdi, rdi
0x18004ab13  jz      short loc_18004AB39
0x18004ab15  mov     edx, 104h; MaxCount
0x18004ab1a  mov     rcx, rdi; Source
0x18004ab1d  call    cs:__imp_wcsnlen
0x18004ab23  cmp     rax, r14
0x18004ab26  jbe     short loc_18004AB39
0x18004ab28  cmp     word ptr [rdi], 2Ah ; '*'
0x18004ab2c  jnz     short loc_18004AB39
0x18004ab2e  cmp     word ptr [rdi+2], 2Ah ; '*'
0x18004ab33  jz      loc_18004AC9D
0x18004ab39  mov     [rbp+arg_8], r12d
0x18004ab3d  xorps   xmm0, xmm0
0x18004ab40  movups  [rbp+var_40], xmm0
0x18004ab44  movups  [rbp+var_30], xmm0
0x18004ab48  movups  [rbp+var_20], xmm0
0x18004ab4c  sub     r15d, r14d
0x18004ab4f  jz      short loc_18004AB6C
0x18004ab51  sub     r15d, 3
0x18004ab55  jz      short loc_18004AB66
0x18004ab57  cmp     r15d, 3
0x18004ab5b  jnz     short loc_18004ABC1
0x18004ab5d  mov     dword ptr [rbp+var_40+8], 4
0x18004ab64  jmp     short loc_18004AB73
0x18004ab66  mov     dword ptr [rbp+var_40+8], r14d
0x18004ab6a  jmp     short loc_18004AB73
0x18004ab6c  mov     dword ptr [rbp+var_40+8], 2
0x18004ab73  mov     dword ptr [rbp+var_40], r14d
0x18004ab77  mov     dword ptr [rbp+var_40+4], 2
0x18004ab7e  mov     rcx, [r13+48h]
0x18004ab82  mov     eax, r12d
0x18004ab85  test    rcx, rcx
0x18004ab88  setnz   al
0x18004ab8b  mov     dword ptr [rbp+var_40+0Ch], eax
0x18004ab8e  mov     dword ptr [rbp+var_30], r14d
0x18004ab92  mov     qword ptr [rbp+var_30+8], rcx
0x18004ab96  lea     r9, [rbp+arg_8]
0x18004ab9a  lea     r8, [rbp+var_40]
0x18004ab9e  mov     rdx, rdi
0x18004aba1  mov     rcx, rsi
0x18004aba4  call    cs:__imp_MDMWinsOverGP_IsGPPolicySetByMDMEx
0x18004abaa  test    eax, eax
0x18004abac  jns     short loc_18004ABB6
0x18004abae  mov     eax, r12d
0x18004abb1  mov     [rbp+arg_8], eax
0x18004abb4  jmp     short loc_18004ABB9
0x18004abb6  mov     eax, [rbp+arg_8]
0x18004abb9  test    eax, eax
0x18004abbb  jnz     loc_18004AC9D
0x18004abc1  mov     r8, rdi; unsigned __int16 *
0x18004abc4  mov     rdx, rsi; unsigned __int16 *
0x18004abc7  mov     rcx, [r13+28h]; hKey
0x18004abcb  call    ?RegCleanUpValue@@YAHPEAUHKEY__@@PEBG1@Z; RegCleanUpValue(HKEY__ *,ushort const *,ushort const *)
0x18004abd0  test    eax, eax
0x18004abd2  jz      short loc_18004AC38
0x18004abd4  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18004abdb  jz      loc_18004AC9D
0x18004abe1  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004abe8  test    rax, rax
0x18004abeb  jz      short loc_18004AC09
0x18004abed  mov     r9, rdi
0x18004abf0  mov     r8, rsi
0x18004abf3  lea     rdx, aDeleteregistry_0; "DeleteRegistryValue: Deleted %s\\%s"
0x18004abfa  mov     ecx, 4
0x18004abff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ac04  jmp     loc_18004AC9D
0x18004ac09  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18004ac10  jz      loc_18004AC9D
0x18004ac16  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18004ac1d  jz      short loc_18004AC9D
0x18004ac1f  mov     r9, rdi
0x18004ac22  mov     r8, rsi
0x18004ac25  lea     rdx, aDeleteregistry_0; "DeleteRegistryValue: Deleted %s\\%s"
0x18004ac2c  mov     ecx, 4; unsigned int
0x18004ac31  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18004ac36  jmp     short loc_18004AC9D
0x18004ac38  call    cs:__imp_GetLastError
0x18004ac3e  mov     ebx, eax
0x18004ac40  mov     [rbp+var_48], eax
0x18004ac43  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18004ac4a  jz      short loc_18004AC9A
0x18004ac4c  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004ac53  test    rax, rax
0x18004ac56  jz      short loc_18004AC71
0x18004ac58  mov     r9, rdi
0x18004ac5b  mov     r8, rsi
0x18004ac5e  lea     rdx, aDeleteregistry; "DeleteRegistryValue: Failed to delete %"...
0x18004ac65  mov     ecx, 2
0x18004ac6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ac6f  jmp     short loc_18004AC9A
0x18004ac71  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18004ac78  jz      short loc_18004AC9A
0x18004ac7a  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18004ac81  jz      short loc_18004AC9A
0x18004ac83  mov     r9, rdi
0x18004ac86  mov     r8, rsi
0x18004ac89  lea     rdx, aDeleteregistry; "DeleteRegistryValue: Failed to delete %"...
0x18004ac90  mov     ecx, 2; unsigned int
0x18004ac95  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18004ac9a  mov     r14d, r12d
0x18004ac9d  mov     ecx, ebx; dwErrCode
0x18004ac9f  call    cs:__imp_SetLastError
0x18004aca5  mov     eax, r14d
0x18004aca8  add     rsp, 78h
0x18004acac  pop     r15
0x18004acae  pop     r14
0x18004acb0  pop     r13
0x18004acb2  pop     r12
0x18004acb4  pop     rdi
0x18004acb5  pop     rsi
0x18004acb6  pop     rbx
0x18004acb7  pop     rbp
0x18004acb8  retn
```
