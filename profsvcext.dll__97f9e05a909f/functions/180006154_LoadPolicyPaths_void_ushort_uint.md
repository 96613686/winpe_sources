# LoadPolicyPaths(void *,ushort * *,uint &)

- ea: `0x180006154`
- end: `0x18000633d`
- name: `?LoadPolicyPaths@@YAJPEAXPEAPEAGAEAI@Z`
- size: `489`
- prototype: `__int64 __fastcall(HANDLE hToken, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180005b54`

## callees

- `0x180001898`
- `0x180006138`
- `0x180006154`
- `0x180008b1c`
- `0x180008ea0`
- `0x18000f660`
- `0x18000f8f0`
- `0x18000f9c8`
- `0x18000fca8`
- `0x18001e580`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006223`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006270`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006223`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006270`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180006198`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180006198`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800062f8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800062f8`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x180006249`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x180006249`

## string_xrefs

- `0x1800061ea`: `clientcore\ds\security\gina\profile\cscsuspendpolicy\cscsuspendpolicy.cpp`
- `0x18000630d`: `clientcore\ds\security\gina\profile\cscsuspendpolicy\cscsuspendpolicy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall LoadPolicyPaths(HANDLE hToken, unsigned __int16 **a2, unsigned int *a3)
{
  int LocalSetting; // eax
  unsigned __int16 *v7; // rsi
  unsigned int v8; // ebx
  signed int LastError; // eax
  int v10; // eax
  WCHAR *v11; // rax
  unsigned __int16 *v12; // rbx
  unsigned __int64 v13; // rdi
  unsigned __int16 *v14; // rax
  unsigned int v15; // eax
  void *v16; // rcx
  unsigned int i; // ecx
  signed int v18; // eax
  int v20; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  LPCWSTR lpSrc; // [rsp+78h] [rbp+10h] BYREF

  v20 = (int)hToken;
  *a2 = 0;
  *a3 = 0;
  lpSrc = 0;
  LocalSetting = Profile::GetLocalSetting(hToken, &lpSrc);
  v7 = (unsigned __int16 *)lpSrc;
  v8 = LocalSetting;
  if ( LocalSetting >= 0 )
  {
    if ( ImpersonateLoggedOnUser(hToken) )
      goto LABEL_6;
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( (v8 & 0x80000000) == 0 )
    {
LABEL_6:
      if ( !v7 )
      {
LABEL_27:
        RevertToSelf();
        goto LABEL_30;
      }
      lpSrc = 0;
      v10 = StringCchLengthW(v7, 0x1000u, (unsigned __int64 *)&lpSrc);
      v8 = v10;
      if ( v10 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x58,
          (int)"clientcore\\ds\\security\\gina\\profile\\cscsuspendpolicy\\cscsuspendpolicy.cpp",
          (const char *)(unsigned int)v10);
        goto LABEL_27;
      }
      if ( !lpSrc )
      {
        v8 = 0;
        goto LABEL_27;
      }
      if ( v7[(_QWORD)lpSrc] )
      {
        v8 = -2147418113;
        goto LABEL_27;
      }
      v11 = (WCHAR *)CoTaskMemAlloc(0x2000u);
      lpSrc = v11;
      v12 = v11;
      if ( !v11 )
        goto LABEL_24;
      if ( !ExpandEnvironmentStringsForUserW(hToken, v7, v11, 0x1000u) )
      {
        v18 = GetLastError();
        v8 = v18;
        if ( v18 > 0 )
          v8 = (unsigned __int16)v18 | 0x80070000;
        goto LABEL_25;
      }
      RemoveExtraSemiColon(v12);
      v13 = -1;
      do
        ++v13;
      while ( v12[v13] );
      v14 = (unsigned __int16 *)CoTaskMemAlloc(2 * v13 + 4);
      *a2 = v14;
      if ( v14 )
      {
        v15 = wil::safe_cast_failfast<unsigned int,unsigned __int64,0>(v13 + 2);
        v16 = *a2;
        *a3 = v15;
        memcpy_0(v16, v12, 2 * v13 + 2);
        (*a2)[v13 + 1] = 0;
        for ( i = 0; i < v13; ++i )
        {
          if ( (*a2)[i] == 59 )
            (*a2)[i] = 0;
        }
        v8 = 0;
      }
      else
      {
LABEL_24:
        v8 = -2147024882;
      }
LABEL_25:
      CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&lpSrc);
      goto LABEL_27;
    }
  }
  if ( v8 != -2147024894 )
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x99,
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\cscsuspendpolicy\\cscsuspendpolicy.cpp",
      (const char *)v8,
      v20);
LABEL_30:
  if ( v7 )
    ResultFromHeapFree(v7);
  return v8;
}

```

## disassembly

```asm
0x180006154  push    rbx
0x180006156  push    rbp
0x180006157  push    rsi
0x180006158  push    rdi
0x180006159  push    r14
0x18000615b  push    r15
0x18000615d  sub     rsp, 38h
0x180006161  xor     ebp, ebp
0x180006163  mov     qword ptr [rsp+68h+var_48], rcx; int
0x180006168  mov     [rdx], rbp
0x18000616b  mov     r14, rdx
0x18000616e  lea     rdx, [rsp+68h+lpSrc]
0x180006173  mov     [r8], ebp
0x180006176  mov     r15, r8
0x180006179  mov     [rsp+68h+lpSrc], rbp
0x18000617e  mov     rdi, rcx
0x180006181  call    ?GetLocalSetting@Profile@@YAJW4PROFILE_SETTING_ID@1@PEAPEAGPEBGW4USERSTATE_SETTING_SOURCES@@PEAX@Z; Profile::GetLocalSetting(Profile::PROFILE_SETTING_ID,ushort * *,ushort const *,USERSTATE_SETTING_SOURCES,void *)
0x180006186  mov     rsi, [rsp+68h+lpSrc]
0x18000618b  mov     ebx, eax
0x18000618d  test    eax, eax
0x18000618f  js      loc_180006300
0x180006195  mov     rcx, rdi; hToken
0x180006198  call    cs:__imp_ImpersonateLoggedOnUser
0x18000619e  test    eax, eax
0x1800061a0  jnz     short loc_1800061BF
0x1800061a2  call    cs:__imp_GetLastError
0x1800061a8  mov     ebx, eax
0x1800061aa  test    eax, eax
0x1800061ac  jle     short loc_1800061B7
0x1800061ae  movzx   ebx, ax
0x1800061b1  or      ebx, 80070000h
0x1800061b7  test    ebx, ebx
0x1800061b9  js      loc_180006300
0x1800061bf  test    rsi, rsi
0x1800061c2  jz      loc_1800062F8
0x1800061c8  lea     r8, [rsp+68h+lpSrc]; unsigned __int64 *
0x1800061cd  mov     [rsp+68h+lpSrc], rbp
0x1800061d2  mov     edx, 1000h; unsigned __int64
0x1800061d7  mov     rcx, rsi; unsigned __int16 *
0x1800061da  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800061df  mov     ebx, eax
0x1800061e1  test    eax, eax
0x1800061e3  jns     short loc_180006203
0x1800061e5  mov     rcx, [rsp+68h]; this
0x1800061ea  lea     r8, aClientcoreDsSe_3; "clientcore\\ds\\security\\gina\\profile"...
0x1800061f1  mov     r9d, eax; char *
0x1800061f4  mov     edx, 58h ; 'X'; void *
0x1800061f9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800061fe  jmp     loc_1800062F8
0x180006203  mov     rax, [rsp+68h+lpSrc]
0x180006208  test    rax, rax
0x18000620b  jnz     short loc_180006214
0x18000620d  mov     ebx, ebp
0x18000620f  jmp     loc_1800062F8
0x180006214  cmp     [rsi+rax*2], bp
0x180006218  jnz     loc_1800062F3
0x18000621e  mov     ecx, 2000h; cb
0x180006223  call    cs:__imp_CoTaskMemAlloc
0x180006229  mov     [rsp+68h+lpSrc], rax
0x18000622e  mov     rbx, rax
0x180006231  test    rax, rax
0x180006234  jz      loc_1800062E2
0x18000623a  mov     r9d, 1000h; dwSize
0x180006240  mov     r8, rax; lpDest
0x180006243  mov     rdx, rsi; lpSrc
0x180006246  mov     rcx, rdi; hToken
0x180006249  call    cs:__imp_ExpandEnvironmentStringsForUserW
0x18000624f  test    eax, eax
0x180006251  jz      short loc_1800062CB
0x180006253  mov     rcx, rbx; unsigned __int16 *
0x180006256  call    ?RemoveExtraSemiColon@@YAXPEAG@Z; RemoveExtraSemiColon(ushort *)
0x18000625b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000625f  inc     rdi
0x180006262  cmp     [rbx+rdi*2], bp
0x180006266  jnz     short loc_18000625F
0x180006268  lea     rcx, ds:4[rdi*2]; cb
0x180006270  call    cs:__imp_CoTaskMemAlloc
0x180006276  mov     [r14], rax
0x180006279  test    rax, rax
0x18000627c  jz      short loc_1800062E2
0x18000627e  lea     rcx, [rdi+2]
0x180006282  call    ??$safe_cast_failfast@I_K$0A@@wil@@YAI_K@Z; wil::safe_cast_failfast<uint,unsigned __int64,0>(unsigned __int64)
0x180006287  mov     rcx, [r14]; void *
0x18000628a  lea     r8, ds:2[rdi*2]; Size
0x180006292  mov     rdx, rbx; Src
0x180006295  mov     [r15], eax
0x180006298  call    memcpy_0
0x18000629d  mov     rcx, [r14]
0x1800062a0  mov     [rcx+rdi*2+2], bp
0x1800062a5  mov     ecx, ebp
0x1800062a7  test    rdi, rdi
0x1800062aa  jz      short loc_1800062C7
0x1800062ac  mov     r8, [r14]
0x1800062af  mov     edx, ecx
0x1800062b1  cmp     word ptr [r8+rdx*2], 3Bh ; ';'
0x1800062b7  jnz     short loc_1800062BE
0x1800062b9  mov     [r8+rdx*2], bp
0x1800062be  inc     ecx
0x1800062c0  mov     eax, ecx
0x1800062c2  cmp     rax, rdi
0x1800062c5  jb      short loc_1800062AC
0x1800062c7  mov     ebx, ebp
0x1800062c9  jmp     short loc_1800062E7
0x1800062cb  call    cs:__imp_GetLastError
0x1800062d1  mov     ebx, eax
0x1800062d3  test    eax, eax
0x1800062d5  jle     short loc_1800062E7
0x1800062d7  movzx   ebx, ax
0x1800062da  or      ebx, 80070000h
0x1800062e0  jmp     short loc_1800062E7
0x1800062e2  mov     ebx, 8007000Eh
0x1800062e7  lea     rcx, [rsp+68h+lpSrc]
0x1800062ec  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x1800062f1  jmp     short loc_1800062F8
0x1800062f3  mov     ebx, 8000FFFFh
0x1800062f8  call    cs:__imp_RevertToSelf
0x1800062fe  jmp     short loc_180006321
0x180006300  cmp     ebx, 80070002h
0x180006306  jz      short loc_180006321
0x180006308  mov     rcx, [rsp+68h]; this
0x18000630d  lea     r8, aClientcoreDsSe_3; "clientcore\\ds\\security\\gina\\profile"...
0x180006314  mov     r9d, ebx; char *
0x180006317  mov     edx, 99h; void *
0x18000631c  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180006321  test    rsi, rsi
0x180006324  jz      short loc_18000632E
0x180006326  mov     rcx, rsi; lpMem
0x180006329  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x18000632e  mov     eax, ebx
0x180006330  add     rsp, 38h
0x180006334  pop     r15
0x180006336  pop     r14
0x180006338  pop     rdi
0x180006339  pop     rsi
0x18000633a  pop     rbp
0x18000633b  pop     rbx
0x18000633c  retn
```
