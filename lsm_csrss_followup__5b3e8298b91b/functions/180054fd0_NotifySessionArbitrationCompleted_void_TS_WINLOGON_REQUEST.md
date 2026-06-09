# NotifySessionArbitrationCompleted(void *,_TS_WINLOGON_REQUEST *)

- ea: `0x180054fd0`
- end: `0x180055179`
- name: `?NotifySessionArbitrationCompleted@@YAJPEAXPEAU_TS_WINLOGON_REQUEST@@@Z`
- size: `425`
- prototype: `__int64 __fastcall(HANDLE SourceHandle, struct _TS_WINLOGON_REQUEST *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002fa00`

## callees

- `0x1800074c0`
- `0x180008f64`
- `0x180015ef8`
- `0x18002668c`
- `0x180027bd8`
- `0x18002e060`
- `0x180054fd0`
- `0x1800555e4`
- `0x1800935b8`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055140`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055150`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055140`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055150`

## string_xrefs

- `0x180055125`: `NotifySessionArbitrationCompleted`
- `0x180055040`: `CRpcUtils::DuplicateClientToken failed: 0x%x in %s`
- `0x18005506b`: `LUAIsElevatedToken failed: 0x%x in %s`
- `0x1800550a9`: `AicGetElevatedToken failed: 0x%x in %s`
- `0x1800550c0`: `LUAGetElevatedToken failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NotifySessionArbitrationCompleted(HANDLE SourceHandle, struct _TS_WINLOGON_REQUEST *a2)
{
  int SessionFromRpcClientId; // eax
  unsigned int v5; // ebx
  const char *v6; // rdx
  NTSTATUS v7; // eax
  int ElevatedToken; // eax
  int v9; // eax
  HANDLE v10; // rdi
  HANDLE hObject; // [rsp+20h] [rbp-20h] BYREF
  HANDLE NewTokenHandle; // [rsp+28h] [rbp-18h] BYREF
  __int64 v14; // [rsp+30h] [rbp-10h] BYREF
  struct ITSSession *v15; // [rsp+38h] [rbp-8h] BYREF
  int v16; // [rsp+70h] [rbp+30h] BYREF
  int v17; // [rsp+78h] [rbp+38h] BYREF

  v15 = 0;
  v14 = 0;
  NewTokenHandle = 0;
  hObject = 0;
  v17 = 0;
  v16 = 0;
  SessionFromRpcClientId = CRpcUtils::GetSessionFromRpcClientId(&v15);
  v5 = SessionFromRpcClientId;
  if ( SessionFromRpcClientId >= 0 )
  {
    SessionFromRpcClientId = CRpcUtils::DuplicateClientToken(SourceHandle, &hObject);
    v5 = SessionFromRpcClientId;
    if ( SessionFromRpcClientId >= 0 )
    {
      v7 = LUAIsElevatedToken(hObject, &v17, &v16);
      v5 = v7 | 0x10000000;
      if ( v7 < 0 )
      {
        _DbgPrintMessage(8, "LUAIsElevatedToken failed: 0x%x in %s", v5, "NotifySessionArbitrationCompleted");
        goto LABEL_21;
      }
      if ( !v16 || v17 )
      {
        v10 = hObject;
      }
      else
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
        {
          ElevatedToken = AicGetElevatedToken(hObject, &NewTokenHandle);
          v5 = ElevatedToken | 0x10000000;
          if ( ElevatedToken < 0 )
          {
            _DbgPrintMessage(8, "AicGetElevatedToken failed: 0x%x in %s", v5, "NotifySessionArbitrationCompleted");
            goto LABEL_21;
          }
        }
        else
        {
          v9 = LUAGetElevatedToken(hObject, &NewTokenHandle);
          v5 = v9 | 0x10000000;
          if ( v9 < 0 )
          {
            _DbgPrintMessage(8, "LUAGetElevatedToken failed: 0x%x in %s", v5, "NotifySessionArbitrationCompleted");
            goto LABEL_21;
          }
        }
        v10 = NewTokenHandle;
      }
      SessionFromRpcClientId = (**(__int64 (__fastcall ***)(struct ITSSession *, __int64 *, __int64 *))v15)(
                                 v15,
                                 qword_1800A2D40,
                                 &v14);
      v5 = SessionFromRpcClientId;
      if ( SessionFromRpcClientId >= 0 )
      {
        SessionFromRpcClientId = (*(__int64 (__fastcall **)(__int64, HANDLE, _QWORD))(*(_QWORD *)v14 + 512LL))(
                                   v14,
                                   v10,
                                   *(unsigned int *)a2);
        v5 = SessionFromRpcClientId;
        if ( SessionFromRpcClientId >= 0 )
          goto LABEL_21;
        v6 = "EndSessionArbitration failed: 0x%x in %s";
      }
      else
      {
        v6 = "QueryInterface on IID_ITSSessionPrivate failed: 0x%x in %s";
      }
    }
    else
    {
      v6 = "CRpcUtils::DuplicateClientToken failed: 0x%x in %s";
    }
  }
  else
  {
    v6 = "CRpcUtils::GetSessionFromRpcClientId failed: 0x%x in %s";
  }
  _DbgPrintMessage(8, v6, (unsigned int)SessionFromRpcClientId, "NotifySessionArbitrationCompleted", hObject);
LABEL_21:
  if ( hObject )
    CloseHandle(hObject);
  if ( NewTokenHandle )
    CloseHandle(NewTokenHandle);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v14);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v15);
  return v5;
}

```

## disassembly

```asm
0x180054fd0  mov     [rsp-18h+arg_0], rbx
0x180054fd5  push    rbp
0x180054fd6  push    rsi
0x180054fd7  push    rdi
0x180054fd8  mov     rbp, rsp
0x180054fdb  sub     rsp, 40h
0x180054fdf  mov     rsi, rdx
0x180054fe2  mov     rdi, rcx
0x180054fe5  mov     [rbp+var_8], 0
0x180054fed  mov     [rbp+var_10], 0
0x180054ff5  mov     [rbp+NewTokenHandle], 0
0x180054ffd  mov     [rbp+hObject], 0
0x180055005  mov     [rbp+arg_18], 0
0x18005500c  mov     [rbp+arg_10], 0
0x180055013  lea     rcx, [rbp+var_8]; struct ITSSession **
0x180055017  call    ?GetSessionFromRpcClientId@CRpcUtils@@SAJPEAPEAUITSSession@@@Z; CRpcUtils::GetSessionFromRpcClientId(ITSSession * *)
0x18005501c  mov     ebx, eax
0x18005501e  test    eax, eax
0x180055020  jns     short loc_18005502E
0x180055022  lea     rdx, aCrpcutilsGetse; "CRpcUtils::GetSessionFromRpcClientId fa"...
0x180055029  jmp     loc_180055122
0x18005502e  lea     rdx, [rbp+hObject]; TargetHandle
0x180055032  mov     rcx, rdi; SourceHandle
0x180055035  call    ?DuplicateClientToken@CRpcUtils@@SAJPEAXPEAPEAX@Z; CRpcUtils::DuplicateClientToken(void *,void * *)
0x18005503a  mov     ebx, eax
0x18005503c  test    eax, eax
0x18005503e  jns     short loc_18005504C
0x180055040  lea     rdx, aCrpcutilsDupli; "CRpcUtils::DuplicateClientToken failed:"...
0x180055047  jmp     loc_180055122
0x18005504c  lea     r8, [rbp+arg_10]
0x180055050  lea     rdx, [rbp+arg_18]
0x180055054  mov     rcx, [rbp+hObject]; TokenHandle
0x180055058  call    LUAIsElevatedToken
0x18005505d  mov     ebx, eax
0x18005505f  mov     edi, 10000000h
0x180055064  or      ebx, edi
0x180055066  jge     short loc_180055077
0x180055068  mov     r8d, ebx
0x18005506b  lea     rdx, aLuaiselevatedt; "LUAIsElevatedToken failed: 0x%x in %s"
0x180055072  jmp     loc_180055125
0x180055077  cmp     [rbp+arg_10], 0
0x18005507b  jz      short loc_1800550CF
0x18005507d  cmp     [rbp+arg_18], 0
0x180055081  jnz     short loc_1800550CF
0x180055083  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x18005508a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x18005508f  lea     rdx, [rbp+NewTokenHandle]; NewTokenHandle
0x180055093  mov     rcx, [rbp+hObject]; TokenHandle
0x180055097  test    al, al
0x180055099  jz      short loc_1800550B2
0x18005509b  call    ?AicGetElevatedToken@@YAJPEAXPEAPEAX@Z; AicGetElevatedToken(void *,void * *)
0x1800550a0  mov     ebx, eax
0x1800550a2  or      ebx, edi
0x1800550a4  jge     short loc_1800550C9
0x1800550a6  mov     r8d, ebx
0x1800550a9  lea     rdx, aAicgetelevated; "AicGetElevatedToken failed: 0x%x in %s"
0x1800550b0  jmp     short loc_180055125
0x1800550b2  call    LUAGetElevatedToken
0x1800550b7  mov     ebx, eax
0x1800550b9  or      ebx, edi
0x1800550bb  jge     short loc_1800550C9
0x1800550bd  mov     r8d, ebx
0x1800550c0  lea     rdx, aLuagetelevated; "LUAGetElevatedToken failed: 0x%x in %s"
0x1800550c7  jmp     short loc_180055125
0x1800550c9  mov     rdi, [rbp+NewTokenHandle]
0x1800550cd  jmp     short loc_1800550D3
0x1800550cf  mov     rdi, [rbp+hObject]
0x1800550d3  mov     rcx, [rbp+var_8]
0x1800550d7  mov     rax, [rcx]
0x1800550da  lea     r8, [rbp+var_10]
0x1800550de  lea     rdx, qword_1800A2D40
0x1800550e5  mov     rax, [rax]
0x1800550e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800550ed  mov     ebx, eax
0x1800550ef  test    eax, eax
0x1800550f1  jns     short loc_1800550FC
0x1800550f3  lea     rdx, aQueryinterface_0; "QueryInterface on IID_ITSSessionPrivate"...
0x1800550fa  jmp     short loc_180055122
0x1800550fc  mov     rcx, [rbp+var_10]
0x180055100  mov     rax, [rcx]
0x180055103  mov     r8d, [rsi]
0x180055106  mov     rdx, rdi
0x180055109  mov     rax, [rax+200h]
0x180055110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055115  mov     ebx, eax
0x180055117  test    eax, eax
0x180055119  jns     short loc_180055137
0x18005511b  lea     rdx, aEndsessionarbi; "EndSessionArbitration failed: 0x%x in %"...
0x180055122  mov     r8d, eax
0x180055125  lea     r9, aNotifysessiona; "NotifySessionArbitrationCompleted"
0x18005512c  mov     ecx, 8; int
0x180055131  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180055136  nop
0x180055137  mov     rcx, [rbp+hObject]; hObject
0x18005513b  test    rcx, rcx
0x18005513e  jz      short loc_180055147
0x180055140  call    cs:__imp_CloseHandle
0x180055146  nop
0x180055147  mov     rcx, [rbp+NewTokenHandle]; hObject
0x18005514b  test    rcx, rcx
0x18005514e  jz      short loc_180055157
0x180055150  call    cs:__imp_CloseHandle
0x180055156  nop
0x180055157  lea     rcx, [rbp+var_10]
0x18005515b  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180055160  nop
0x180055161  lea     rcx, [rbp+var_8]
0x180055165  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005516a  mov     eax, ebx
0x18005516c  mov     rbx, [rsp+40h+arg_0]
0x180055171  add     rsp, 40h
0x180055175  pop     rdi
0x180055176  pop     rsi
0x180055177  pop     rbp
0x180055178  retn
```
