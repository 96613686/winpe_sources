# WebRuntimeDiagnostics::LCIEDiagnosticsSession::IAS_PopulateIsoCreationData(_GUID const &,ushort const *,SIsoScopeCreationData *,SImmutableApplicationState *)

- ea: `0x180068f10`
- end: `0x180069090`
- name: `?IAS_PopulateIsoCreationData@LCIEDiagnosticsSession@WebRuntimeDiagnostics@@AEAAJAEBU_GUID@@PEBGPEAUSIsoScopeCreationData@@PEAUSImmutableApplicationState@@@Z`
- size: `384`
- prototype: `__int64 __fastcall(WebRuntimeDiagnostics::LCIEDiagnosticsSession *__hidden this, const struct _GUID *, const unsigned __int16 *, struct SIsoScopeCreationData *, struct SImmutableApplicationState *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006915c`

## callees

- `0x180018b54`
- `0x180068f10`

## import_xrefs

- `iertutil!__imp_GetUserPrivateNamespaceName` at `0x180068f4b`
- `iertutil!__imp_GetUserPrivateNamespaceName` at `0x180068f4b`
- `iertutil!__imp_?IAS_Query@@YAJAEBU_GUID@@PEBGPEAUSImmutableApplicationState@@@Z` at `0x180068f3b`
- `iertutil!__imp_?IAS_Query@@YAJAEBU_GUID@@PEBGPEAUSImmutableApplicationState@@@Z` at `0x180068f3b`
- `iertutil!__imp_GetValue` at `0x180068fd7`
- `iertutil!__imp_GetValue` at `0x180069064`
- `iertutil!__imp_GetValue` at `0x180068fd7`
- `iertutil!__imp_GetValue` at `0x180069064`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180068fe2`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180068ff0`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180068fe2`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180068ff0`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180068f5a`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180068f5a`

## pseudocode

```c
__int64 __fastcall WebRuntimeDiagnostics::LCIEDiagnosticsSession::IAS_PopulateIsoCreationData(
        WebRuntimeDiagnostics::LCIEDiagnosticsSession *this,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        struct SIsoScopeCreationData *a4,
        struct SImmutableApplicationState *a5)
{
  struct SImmutableApplicationState *v5; // rsi
  unsigned int v7; // ebx
  int DWORD; // eax
  int v9; // ecx
  bool v10; // al
  _DWORD v12[6]; // [rsp+40h] [rbp-18h] BYREF
  WebRuntimeDiagnostics::LCIEDiagnosticsSession *v13; // [rsp+60h] [rbp+8h] BYREF

  v13 = this;
  v5 = a5;
  v7 = IAS_Query(a2, a3, a5);
  if ( !v7 )
  {
    *((_QWORD *)a4 + 2) = GetUserPrivateNamespaceName();
    DWORD = IEConfiguration_GetDWORD(536870930);
    LODWORD(v13) = 0;
    *((_DWORD *)a4 + 6) = DWORD;
    *((_DWORD *)a4 + 7) = *((_DWORD *)v5 + 292);
    *((_QWORD *)a4 + 5) = (char *)v5 + 2736;
    *((_QWORD *)a4 + 4) = (char *)v5 + 652;
    *((_QWORD *)a4 + 6) = (char *)v5 + 1176;
    GetBOOL((__int64 *)SettingStore::IEVALUE_RAC_Policy_AllowMRACPrivateNetworkAccess[0], &v13);
    *((_BYTE *)a4 + 56) = (_DWORD)v13 != 0;
    GetValue((__int64 *)SettingStore::IEVALUE_RAC_Policy_LaunchFlags[0], 1, 1, (char *)a4 + 60, 4, 0, 0);
    *((_BYTE *)a4 + 66) = IEConfiguration_GetBool(536870917);
    *((_BYTE *)a4 + 67) = IEConfiguration_GetBool(536870916);
    v9 = *((_DWORD *)v5 + 25);
    v12[0] = 0;
    *((_BYTE *)a4 + 72) = ((v9 - 29) & 0xFFFFFFDF) == 0;
    *((_BYTE *)a4 + 73) = v9 == 13;
    v10 = v9 == 16;
    LOBYTE(v9) = (v9 & 4) != 0;
    *((_BYTE *)a4 + 74) = v10;
    *((_BYTE *)a4 + 10) = v9;
    *((_BYTE *)a4 + 9) = v9;
    *((_BYTE *)a4 + 75) = *((_BYTE *)v5 + 66);
    *((_BYTE *)a4 + 76) = *((_BYTE *)v5 + 44);
    GetValue((__int64 *)SettingStore::IEVALUE_CodeIntegrity_NoCompatExemption, 1, 1, v12, 4, 0, 0);
    *((_BYTE *)a4 + 77) = v12[0] != 0;
    *(_QWORD *)a4 = (char *)v5 + 2222;
  }
  return v7;
}

```

## disassembly

```asm
0x180068f10  mov     [rsp+arg_8], rbx
0x180068f15  mov     [rsp+arg_10], rsi
0x180068f1a  mov     [rsp+arg_0], rcx
0x180068f1f  push    rdi
0x180068f20  sub     rsp, 50h
0x180068f24  mov     rsi, [rsp+58h+arg_20]
0x180068f2c  mov     rax, r8
0x180068f2f  mov     rcx, rdx
0x180068f32  mov     r8, rsi
0x180068f35  mov     rdx, rax
0x180068f38  mov     rdi, r9
0x180068f3b  call    cs:__imp_?IAS_Query@@YAJAEBU_GUID@@PEBGPEAUSImmutableApplicationState@@@Z; IAS_Query(_GUID const &,ushort const *,SImmutableApplicationState *)
0x180068f41  mov     ebx, eax
0x180068f43  test    eax, eax
0x180068f45  jnz     loc_18006907E
0x180068f4b  call    cs:__imp_GetUserPrivateNamespaceName
0x180068f51  mov     ecx, 20000012h
0x180068f56  mov     [rdi+10h], rax
0x180068f5a  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x180068f60  lea     rdx, [rsp+58h+arg_0]
0x180068f65  mov     dword ptr [rsp+58h+arg_0], ebx
0x180068f69  mov     [rdi+18h], eax
0x180068f6c  lea     rax, [rsi+0AB0h]
0x180068f73  mov     ecx, [rsi+490h]
0x180068f79  mov     [rdi+1Ch], ecx
0x180068f7c  lea     rcx, [rsi+28Ch]
0x180068f83  mov     [rdi+28h], rax
0x180068f87  lea     rax, [rsi+498h]
0x180068f8e  mov     [rdi+20h], rcx
0x180068f92  mov     rcx, cs:?IEVALUE_RAC_Policy_AllowMRACPrivateNetworkAccess@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_RAC_Policy_AllowMRACPrivateNetworkAccess
0x180068f99  mov     [rdi+30h], rax
0x180068f9d  call    GetBOOL
0x180068fa2  cmp     dword ptr [rsp+58h+arg_0], ebx
0x180068fa6  lea     edx, [rbx+1]
0x180068fa9  mov     rcx, cs:?IEVALUE_RAC_Policy_LaunchFlags@SettingStore@@3U?$VALUEID@K@1@B; SettingStore::VALUEID<ulong> const SettingStore::IEVALUE_RAC_Policy_LaunchFlags
0x180068fb0  lea     r9, [rdi+3Ch]
0x180068fb4  setnz   al
0x180068fb7  mov     [rsp+58h+var_28], 0
0x180068fc0  mov     [rsp+58h+var_30], 0
0x180068fc9  mov     r8d, edx
0x180068fcc  mov     [rdi+38h], al
0x180068fcf  mov     [rsp+58h+var_38], 4
0x180068fd7  call    cs:__imp_GetValue
0x180068fdd  mov     ecx, 20000005h
0x180068fe2  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180068fe8  mov     ecx, 20000004h
0x180068fed  mov     [rdi+42h], al
0x180068ff0  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180068ff6  lea     edx, [rbx+1]
0x180068ff9  mov     [rsp+58h+var_28], 0
0x180069002  mov     [rdi+43h], al
0x180069005  lea     r9, [rsp+58h+var_18]
0x18006900a  mov     ecx, [rsi+64h]
0x18006900d  mov     r8d, edx
0x180069010  mov     [rsp+58h+var_30], 0
0x180069019  mov     [rsp+58h+var_18], ebx
0x18006901d  mov     [rsp+58h+var_38], 4
0x180069025  lea     eax, [rcx-1Dh]
0x180069028  test    eax, 0FFFFFFDFh
0x18006902d  setz    al
0x180069030  cmp     ecx, 0Dh
0x180069033  mov     [rdi+48h], al
0x180069036  setz    al
0x180069039  cmp     ecx, 10h
0x18006903c  mov     [rdi+49h], al
0x18006903f  setz    al
0x180069042  shr     ecx, 2
0x180069045  and     cl, 1
0x180069048  mov     [rdi+4Ah], al
0x18006904b  mov     [rdi+0Ah], cl
0x18006904e  mov     [rdi+9], cl
0x180069051  mov     al, [rsi+42h]
0x180069054  mov     rcx, cs:?IEVALUE_CodeIntegrity_NoCompatExemption@SettingStore@@3U?$VALUEID@K@1@B; SettingStore::VALUEID<ulong> const SettingStore::IEVALUE_CodeIntegrity_NoCompatExemption
0x18006905b  mov     [rdi+4Bh], al
0x18006905e  mov     al, [rsi+2Ch]
0x180069061  mov     [rdi+4Ch], al
0x180069064  call    cs:__imp_GetValue
0x18006906a  cmp     [rsp+58h+var_18], ebx
0x18006906e  setnz   al
0x180069071  mov     [rdi+4Dh], al
0x180069074  lea     rax, [rsi+8AEh]
0x18006907b  mov     [rdi], rax
0x18006907e  mov     rsi, [rsp+58h+arg_10]
0x180069083  mov     eax, ebx
0x180069085  mov     rbx, [rsp+58h+arg_8]
0x18006908a  add     rsp, 50h
0x18006908e  pop     rdi
0x18006908f  retn
```
