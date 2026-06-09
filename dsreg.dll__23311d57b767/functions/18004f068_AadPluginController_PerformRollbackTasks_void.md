# AadPluginController::PerformRollbackTasks(void)

- ea: `0x18004f068`
- end: `0x18004f259`
- name: `?PerformRollbackTasks@AadPluginController@@QEAAJXZ`
- size: `497`
- prototype: `__int64 __fastcall(AadPluginController *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180053630`

## callees

- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x1800432d0`
- `0x18004ccec`
- `0x18004e220`
- `0x18004f068`
- `0x18005035c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f151`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f151`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f1ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f1ca`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004f13e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004f13e`

## string_xrefs

- `0x18004f081`: `AadPluginController::PerformRollbackTasks`
- `0x18004f095`: `%s: m_pRollbackContext is NULL. Nothing to roll back.`
- `0x18004f0c6`: `%s: AadPluginController::UpdateIdpRegistrationKey failed with error code: 0x%08x.`
- `0x18004f15a`: `%s: ConvertSidToStringSidW failed with error code: 0x%08x.`
- `0x18004f18a`: `%s: AadPluginController::RemoveUserSidFromLocalGroup succeeded. SID: %s; Group: %s.`
- `0x18004f1af`: `%s: AadPluginController::RemoveUserSidFromLocalGroup failed with error code: 0x%08x. SID: %s; Group: %s.`
- `0x18004f209`: `%s: AadPluginController::LoadUnloadAadPluginFromLsa failed with error code: 0x%08x.`

## pseudocode

```c
__int64 __fastcall AadPluginController::PerformRollbackTasks(__int64 **this)
{
  __int64 *v1; // rax
  unsigned int v2; // ebp
  int updated; // eax
  int v5; // esi
  AadPluginController *v6; // rcx
  unsigned __int64 v7; // r14
  __int64 v8; // rsi
  __int64 v9; // r8
  unsigned __int64 v10; // r15
  int v11; // eax
  int v12; // r12d
  DWORD LastError; // eax
  __int64 v14; // rcx
  LPWSTR v15; // r8
  LPWSTR v16; // r9
  int UnloadAadPluginFromLsa; // eax
  int v18; // esi
  LPWSTR StringSid; // [rsp+60h] [rbp+8h] BYREF

  v1 = *this;
  v2 = 0;
  if ( *this )
  {
    if ( *((_DWORD *)v1 + 4) != 2 )
    {
      updated = AadPluginController::UpdateIdpRegistrationKey((AadPluginController *)this, *((_DWORD *)v1 + 4) == 1, 0);
      v5 = updated;
      if ( updated < 0 )
      {
        Logger::TraceError(
          L"%s: AadPluginController::UpdateIdpRegistrationKey failed with error code: 0x%08x.",
          L"AadPluginController::PerformRollbackTasks",
          (unsigned int)updated);
        v2 = v5;
      }
    }
    v6 = (AadPluginController *)*this;
    if ( **this && *((_QWORD *)v6 + 1) )
    {
      v7 = 0;
      v8 = 0;
      do
      {
        v9 = *(_QWORD *)v6;
        v10 = 0;
        if ( *(_QWORD *)(32 * v7 + *(_QWORD *)v6 + 16) )
        {
          do
          {
            v11 = AadPluginController::RemoveUserSidFromLocalGroup(
                    v6,
                    *(void **)(*(_QWORD *)(v9 + v8 + 8) + 8 * v10),
                    *(const unsigned __int16 **)(v8 + v9));
            StringSid = 0;
            v12 = v11;
            if ( !ConvertSidToStringSidW(*(PSID *)(*(_QWORD *)(**this + v8 + 8) + 8 * v10), &StringSid) )
            {
              StringSid = 0;
              LastError = GetLastError();
              Logger::TraceWarning(
                (wchar_t *)L"%s: ConvertSidToStringSidW failed with error code: 0x%08x.",
                L"AadPluginController::PerformRollbackTasks",
                LastError);
            }
            v14 = **this;
            if ( v12 < 0 )
            {
              v16 = L"Invalid";
              if ( StringSid )
                v16 = StringSid;
              Logger::TraceError(
                L"%s: AadPluginController::RemoveUserSidFromLocalGroup failed with error code: 0x%08x. SID: %s; Group: %s.",
                L"AadPluginController::PerformRollbackTasks",
                (unsigned int)v12,
                v16,
                *(_QWORD *)(v14 + v8));
              v2 = v12;
            }
            else
            {
              v15 = L"Invalid";
              if ( StringSid )
                v15 = StringSid;
              Logger::TraceVerbose(
                (wchar_t *)L"%s: AadPluginController::RemoveUserSidFromLocalGroup succeeded. SID: %s; Group: %s.",
                L"AadPluginController::PerformRollbackTasks",
                v15,
                *(_QWORD *)(v14 + v8));
            }
            LocalFree(StringSid);
            v6 = (AadPluginController *)*this;
            ++v10;
            v9 = **this;
          }
          while ( v10 < *(_QWORD *)(v9 + v8 + 16) );
        }
        ++v7;
        v8 += 32;
      }
      while ( v7 < *((_QWORD *)v6 + 1) );
    }
    if ( *((_DWORD *)v6 + 4) != 2 )
    {
      UnloadAadPluginFromLsa = AadPluginController::LoadUnloadAadPluginFromLsa();
      v18 = UnloadAadPluginFromLsa;
      if ( UnloadAadPluginFromLsa < 0 )
      {
        Logger::TraceError(
          L"%s: AadPluginController::LoadUnloadAadPluginFromLsa failed with error code: 0x%08x.",
          L"AadPluginController::PerformRollbackTasks",
          (unsigned int)UnloadAadPluginFromLsa);
        v2 = v18;
      }
    }
  }
  else
  {
    Logger::TraceVerbose(
      (wchar_t *)L"%s: m_pRollbackContext is NULL. Nothing to roll back.",
      L"AadPluginController::PerformRollbackTasks");
  }
  if ( *this )
    AadPluginController::_AADPLUGIN_ROLLBACK_CONTEXT::`scalar deleting destructor'((AadPluginController::_AADPLUGIN_ROLLBACK_CONTEXT *)*this);
  *this = 0;
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"AadPluginController::PerformRollbackTasks", v2);
  return v2;
}

```

## disassembly

```asm
0x18004f068  mov     [rsp+arg_8], rbx
0x18004f06d  mov     [rsp+arg_10], rbp
0x18004f072  push    rsi
0x18004f073  push    rdi
0x18004f074  push    r12
0x18004f076  push    r14
0x18004f078  push    r15
0x18004f07a  sub     rsp, 30h
0x18004f07e  mov     rax, [rcx]
0x18004f081  lea     rbx, aAadplugincontr_3; "AadPluginController::PerformRollbackTas"...
0x18004f088  xor     ebp, ebp
0x18004f08a  mov     rdi, rcx
0x18004f08d  test    rax, rax
0x18004f090  jnz     short loc_18004F0A6
0x18004f092  mov     rdx, rbx
0x18004f095  lea     rcx, aSMProllbackcon; "%s: m_pRollbackContext is NULL. Nothing"...
0x18004f09c  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18004f0a1  jmp     loc_18004F21A
0x18004f0a6  cmp     dword ptr [rax+10h], 2
0x18004f0aa  jz      short loc_18004F0D7
0x18004f0ac  xor     edx, edx
0x18004f0ae  cmp     dword ptr [rax+10h], 1
0x18004f0b2  setz    dl; int
0x18004f0b5  xor     r8d, r8d; struct AadPluginController::_AADPLUGIN_ROLLBACK_CONTEXT *
0x18004f0b8  call    ?UpdateIdpRegistrationKey@AadPluginController@@AEAAJHPEAU_AADPLUGIN_ROLLBACK_CONTEXT@1@@Z; AadPluginController::UpdateIdpRegistrationKey(int,AadPluginController::_AADPLUGIN_ROLLBACK_CONTEXT *)
0x18004f0bd  mov     esi, eax
0x18004f0bf  test    eax, eax
0x18004f0c1  jns     short loc_18004F0D7
0x18004f0c3  mov     r8d, eax
0x18004f0c6  lea     rcx, aSAadplugincont_3; "%s: AadPluginController::UpdateIdpRegis"...
0x18004f0cd  mov     rdx, rbx
0x18004f0d0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18004f0d5  mov     ebp, esi
0x18004f0d7  mov     rcx, [rdi]; this
0x18004f0da  cmp     qword ptr [rcx], 0
0x18004f0de  jz      loc_18004F1F5
0x18004f0e4  cmp     qword ptr [rcx+8], 0
0x18004f0e9  jbe     loc_18004F1F5
0x18004f0ef  xor     r14d, r14d
0x18004f0f2  xor     esi, esi
0x18004f0f4  mov     r8, [rcx]
0x18004f0f7  mov     rax, r14
0x18004f0fa  shl     rax, 5
0x18004f0fe  xor     r15d, r15d
0x18004f101  cmp     [rax+r8+10h], r15
0x18004f106  jbe     loc_18004F1E4
0x18004f10c  mov     rdx, [r8+rsi+8]
0x18004f111  mov     r8, [rsi+r8]; unsigned __int16 *
0x18004f115  mov     rdx, [rdx+r15*8]; void *
0x18004f119  call    ?RemoveUserSidFromLocalGroup@AadPluginController@@AEAAJPEAXPEBG@Z; AadPluginController::RemoveUserSidFromLocalGroup(void *,ushort const *)
0x18004f11e  mov     [rsp+58h+StringSid], 0
0x18004f127  lea     rdx, [rsp+58h+StringSid]; StringSid
0x18004f12c  mov     r12d, eax
0x18004f12f  mov     rax, [rdi]
0x18004f132  mov     rcx, [rax]
0x18004f135  mov     rcx, [rcx+rsi+8]
0x18004f13a  mov     rcx, [rcx+r15*8]; Sid
0x18004f13e  call    cs:__imp_ConvertSidToStringSidW
0x18004f144  test    eax, eax
0x18004f146  jnz     short loc_18004F169
0x18004f148  mov     [rsp+58h+StringSid], 0
0x18004f151  call    cs:__imp_GetLastError
0x18004f157  mov     rdx, rbx
0x18004f15a  lea     rcx, aSConvertsidtos; "%s: ConvertSidToStringSidW failed with "...
0x18004f161  mov     r8d, eax
0x18004f164  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18004f169  mov     rax, [rdi]
0x18004f16c  mov     rdx, rbx
0x18004f16f  mov     rcx, [rax]
0x18004f172  mov     rax, [rsp+58h+StringSid]
0x18004f177  test    r12d, r12d
0x18004f17a  js      short loc_18004F19C
0x18004f17c  mov     r9, [rcx+rsi]
0x18004f180  lea     r8, aInvalid_0; "Invalid"
0x18004f187  test    rax, rax
0x18004f18a  lea     rcx, aSAadplugincont; "%s: AadPluginController::RemoveUserSidF"...
0x18004f191  cmovnz  r8, rax
0x18004f195  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18004f19a  jmp     short loc_18004F1C5
0x18004f19c  mov     rcx, [rcx+rsi]
0x18004f1a0  lea     r9, aInvalid_0; "Invalid"
0x18004f1a7  test    rax, rax
0x18004f1aa  mov     [rsp+58h+var_38], rcx
0x18004f1af  lea     rcx, aSAadplugincont_2; "%s: AadPluginController::RemoveUserSidF"...
0x18004f1b6  mov     r8d, r12d
0x18004f1b9  cmovnz  r9, rax
0x18004f1bd  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18004f1c2  mov     ebp, r12d
0x18004f1c5  mov     rcx, [rsp+58h+StringSid]; hMem
0x18004f1ca  call    cs:__imp_LocalFree
0x18004f1d0  mov     rcx, [rdi]
0x18004f1d3  inc     r15
0x18004f1d6  mov     r8, [rcx]
0x18004f1d9  cmp     r15, [r8+rsi+10h]
0x18004f1de  jb      loc_18004F10C
0x18004f1e4  inc     r14
0x18004f1e7  add     rsi, 20h ; ' '
0x18004f1eb  cmp     r14, [rcx+8]
0x18004f1ef  jb      loc_18004F0F4
0x18004f1f5  cmp     dword ptr [rcx+10h], 2
0x18004f1f9  jz      short loc_18004F21A
0x18004f1fb  call    ?LoadUnloadAadPluginFromLsa@AadPluginController@@CAJXZ; AadPluginController::LoadUnloadAadPluginFromLsa(void)
0x18004f200  mov     esi, eax
0x18004f202  test    eax, eax
0x18004f204  jns     short loc_18004F21A
0x18004f206  mov     r8d, eax
0x18004f209  lea     rcx, aSAadplugincont_6; "%s: AadPluginController::LoadUnloadAadP"...
0x18004f210  mov     rdx, rbx
0x18004f213  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18004f218  mov     ebp, esi
0x18004f21a  mov     rcx, [rdi]; this
0x18004f21d  test    rcx, rcx
0x18004f220  jz      short loc_18004F227
0x18004f222  call    ??_G_AADPLUGIN_ROLLBACK_CONTEXT@AadPluginController@@QEAAPEAXI@Z; AadPluginController::_AADPLUGIN_ROLLBACK_CONTEXT::`scalar deleting destructor'(uint)
0x18004f227  mov     r8d, ebp
0x18004f22a  mov     qword ptr [rdi], 0
0x18004f231  mov     rdx, rbx
0x18004f234  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18004f23b  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18004f240  mov     rbx, [rsp+58h+arg_8]
0x18004f245  mov     eax, ebp
0x18004f247  mov     rbp, [rsp+58h+arg_10]
0x18004f24c  add     rsp, 30h
0x18004f250  pop     r15
0x18004f252  pop     r14
0x18004f254  pop     r12
0x18004f256  pop     rdi
0x18004f257  pop     rsi
0x18004f258  retn
```
