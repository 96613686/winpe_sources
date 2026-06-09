# MPCHolographicInputManager::UpdateDoubleClickValues(void)

- ea: `0x1800ac9b8`
- end: `0x1800acaff`
- name: `?UpdateDoubleClickValues@MPCHolographicInputManager@@AEAAXXZ`
- size: `327`
- prototype: `void __fastcall(MPCHolographicInputManager *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18005e04c`
- `0x180107460`

## callees

- `0x180030260`
- `0x180035e08`
- `0x180035ee4`
- `0x1800ac9b8`
- `0x180106b20`
- `0x180107558`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1800aca79`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1800acaa9`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1800aca79`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1800acaa9`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800aca4d`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800aca5e`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800aca4d`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800aca5e`

## pseudocode

```c
void __fastcall MPCHolographicInputManager::UpdateDoubleClickValues(MPCHolographicInputManager *this)
{
  _QWORD *v2; // rcx
  unsigned __int8 v3; // di
  UINT v4; // ebp
  UINT v5; // r14d
  const char *v6; // r9
  unsigned __int64 v7; // rdx
  unsigned __int8 v8; // cl
  const char *v9; // r9
  ISMTracing *v10; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v12; // [rsp+48h] [rbp+10h] BYREF
  int v13; // [rsp+50h] [rbp+18h] BYREF

  if ( IsEdition(0xAu) )
  {
    v2 = (_QWORD *)*((_QWORD *)this + 450);
    if ( v2 == *((_QWORD **)this + 451)
      || (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 48LL))(*v2) == 2
      || (v3 = 1, *((_DWORD *)this + 912) != 1) )
    {
      v3 = 0;
    }
    if ( v3 != *((_BYTE *)this + 3672) )
    {
      v4 = *((_DWORD *)this + 2 * v3 + 919);
      v13 = v4;
      v5 = *((_DWORD *)this + 2 * v3 + 920);
      v12 = v5;
      if ( v3 )
      {
        *((_DWORD *)this + 919) = GetSystemMetrics(36);
        *((_DWORD *)this + 920) = GetSystemMetrics(37);
      }
      if ( !SystemParametersInfoW(0x1Du, v4, 0, 2u) )
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x5AB,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputprocessors\\devices\\mpc\\lib\\mpcholographicinputmanager.cpp",
          v6);
      if ( !SystemParametersInfoW(0x1Eu, v5, 0, 2u) )
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x5AC,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputprocessors\\devices\\mpc\\lib\\mpcholographicinputmanager.cpp",
          v9);
      *((_BYTE *)this + 3672) = v3;
      if ( ISMTracing::IsEnabled(v8, v7) )
      {
        ISMTracing::Instance();
        ISMTracing::MPCHolographicInputManager_UpdateDoubleClickValues_(v10, (const bool *)this + 3672, &v13, &v12);
      }
    }
  }
}

```

## disassembly

```asm
0x1800ac9b8  mov     [rsp+arg_0], rbx
0x1800ac9bd  mov     [rsp+arg_18], rbp
0x1800ac9c2  push    rsi
0x1800ac9c3  push    rdi
0x1800ac9c4  push    r14
0x1800ac9c6  sub     rsp, 20h
0x1800ac9ca  mov     rbx, rcx
0x1800ac9cd  mov     ecx, 0Ah; unsigned __int64
0x1800ac9d2  call    ?IsEdition@@YA_N_K@Z; IsEdition(unsigned __int64)
0x1800ac9d7  test    al, al
0x1800ac9d9  jz      loc_1800ACAEC
0x1800ac9df  mov     rcx, [rbx+0E10h]
0x1800ac9e6  cmp     rcx, [rbx+0E18h]
0x1800ac9ed  jz      short loc_1800ACA10
0x1800ac9ef  mov     rcx, [rcx]
0x1800ac9f2  mov     rax, [rcx]
0x1800ac9f5  mov     rax, [rax+30h]
0x1800ac9f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac9fe  cmp     eax, 2
0x1800aca01  jz      short loc_1800ACA10
0x1800aca03  mov     edi, 1
0x1800aca08  cmp     [rbx+0E40h], edi
0x1800aca0e  jz      short loc_1800ACA13
0x1800aca10  xor     dil, dil
0x1800aca13  lea     rsi, [rbx+0E58h]
0x1800aca1a  cmp     dil, [rsi]
0x1800aca1d  jz      loc_1800ACAEC
0x1800aca23  movzx   eax, dil
0x1800aca27  mov     ebp, [rbx+rax*8+0E5Ch]
0x1800aca2e  movzx   eax, dil
0x1800aca32  mov     [rsp+38h+arg_10], ebp
0x1800aca36  mov     r14d, [rbx+rax*8+0E60h]
0x1800aca3e  mov     [rsp+38h+arg_8], r14d
0x1800aca43  test    dil, dil
0x1800aca46  jz      short loc_1800ACA6A
0x1800aca48  mov     ecx, 24h ; '$'; nIndex
0x1800aca4d  call    cs:__imp_GetSystemMetrics
0x1800aca53  mov     ecx, 25h ; '%'; nIndex
0x1800aca58  mov     [rbx+0E5Ch], eax
0x1800aca5e  call    cs:__imp_GetSystemMetrics
0x1800aca64  mov     [rbx+0E60h], eax
0x1800aca6a  mov     r9d, 2; fWinIni
0x1800aca70  xor     r8d, r8d; pvParam
0x1800aca73  mov     edx, ebp; uiParam
0x1800aca75  lea     ecx, [r9+1Bh]; uiAction
0x1800aca79  call    cs:__imp_SystemParametersInfoW
0x1800aca7f  test    eax, eax
0x1800aca81  jnz     short loc_1800ACA99
0x1800aca83  mov     rcx, [rsp+38h]; this
0x1800aca88  lea     r8, aOnecoreuapWind_227; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800aca8f  mov     edx, 5ABh; void *
0x1800aca94  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800aca99  mov     r9d, 2; fWinIni
0x1800aca9f  xor     r8d, r8d; pvParam
0x1800acaa2  mov     edx, r14d; uiParam
0x1800acaa5  lea     ecx, [r9+1Ch]; uiAction
0x1800acaa9  call    cs:__imp_SystemParametersInfoW
0x1800acaaf  test    eax, eax
0x1800acab1  jnz     short loc_1800ACAC9
0x1800acab3  mov     rcx, [rsp+38h]; this
0x1800acab8  lea     r8, aOnecoreuapWind_227; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800acabf  mov     edx, 5ACh; void *
0x1800acac4  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800acac9  mov     [rsi], dil
0x1800acacc  call    ?IsEnabled@ISMTracing@@SA_NE_K@Z; ISMTracing::IsEnabled(uchar,unsigned __int64)
0x1800acad1  test    al, al
0x1800acad3  jz      short loc_1800ACAEC
0x1800acad5  call    ?Instance@ISMTracing@@KAPEAV1@XZ; ISMTracing::Instance(void)
0x1800acada  lea     r9, [rsp+38h+arg_8]; int *
0x1800acadf  mov     rdx, rsi; bool *
0x1800acae2  lea     r8, [rsp+38h+arg_10]; int *
0x1800acae7  call    ?MPCHolographicInputManager_UpdateDoubleClickValues_@ISMTracing@@QEAAXAEB_NAEBH1@Z; ISMTracing::MPCHolographicInputManager_UpdateDoubleClickValues_(bool const &,int const &,int const &)
0x1800acaec  mov     rbx, [rsp+38h+arg_0]
0x1800acaf1  mov     rbp, [rsp+38h+arg_18]
0x1800acaf6  add     rsp, 20h
0x1800acafa  pop     r14
0x1800acafc  pop     rdi
0x1800acafd  pop     rsi
0x1800acafe  retn
```
