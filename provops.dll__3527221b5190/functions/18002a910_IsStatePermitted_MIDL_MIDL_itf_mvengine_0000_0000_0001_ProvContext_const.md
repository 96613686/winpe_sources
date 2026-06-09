# IsStatePermitted(__MIDL___MIDL_itf_mvengine_0000_0000_0001,ProvContext const &)

- ea: `0x18002a910`
- end: `0x18002aa66`
- name: `?IsStatePermitted@@YA_NW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@AEBUProvContext@@@Z`
- size: `342`
- prototype: `bool __fastcall(int, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18002a340`

## callees

- `0x1800017ec`
- `0x180003ae0`
- `0x18002a910`
- `0x18002aa6c`
- `0x18002ab40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a9ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a9ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a9c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a9c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a95b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a9b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aa20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aa58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a95b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a9b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aa20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aa58`
- `ext-ms-win-provisioning-platform-l1-1-0!GetProvisioningTargetUser` at `0x18002a9d5`
- `ext-ms-win-provisioning-platform-l1-1-0!GetProvisioningTargetUser` at `0x18002a9d5`

## string_xrefs

- `0x18002aa3b`: `Extension_RunOnce`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall IsStatePermitted(int a1, _DWORD *a2)
{
  bool v2; // di
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  char v7; // bl
  int v9; // ecx
  int v10; // ecx
  __int64 v11; // rcx
  HLOCAL v12; // rsi
  DWORD LastError; // ebx
  __int64 v14; // r9
  HLOCAL hMem; // [rsp+50h] [rbp+18h] BYREF
  HLOCAL v16; // [rsp+58h] [rbp+20h] BYREF

  hMem = 0;
  v2 = 1;
  if ( a1 > 8 )
  {
    v9 = a1 - 9;
    if ( !v9 )
      goto LABEL_8;
    v10 = v9 - 1;
    if ( v10 )
    {
      v11 = (unsigned int)(v10 - 1);
      if ( !(_DWORD)v11 )
        goto LABEL_8;
      if ( (_DWORD)v11 != 6 )
        return v2;
      if ( !(unsigned __int8)IsCheckUserConsentPresent(v11) )
        goto LABEL_25;
      v12 = hMem;
      if ( hMem )
      {
        LastError = GetLastError();
        LocalFree(v12);
        SetLastError(LastError);
      }
      hMem = 0;
      if ( (int)GetProvisioningTargetUser(&hMem) < 0 )
      {
LABEL_25:
        if ( hMem )
          LocalFree(hMem);
        return 0;
      }
      if ( *(_DWORD *)g_hProvTraceProvider > 4u )
      {
        v16 = hMem;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          g_hProvTraceProvider,
          (__int64)byte_1800414C1,
          0,
          v14,
          &v16);
      }
    }
    else if ( !(unsigned __int8)IsUpdateRelevantForState((int)L"Uicc_RunOnce") )
    {
      v2 = (unsigned __int8)IsUpdateRelevantForState((int)L"Extension_RunOnce") != 0;
    }
    if ( hMem )
      LocalFree(hMem);
    return v2;
  }
  if ( a1 == 8 || (v3 = a1 - 1) == 0 )
  {
LABEL_12:
    if ( *a2 != 3 )
      goto LABEL_8;
    return 0;
  }
  v4 = v3 - 2;
  if ( v4 )
  {
    v5 = v4 - 1;
    if ( v5 )
    {
      v6 = v5 - 2;
      if ( v6 )
      {
        if ( v6 == 1 )
          goto LABEL_8;
        return v2;
      }
      if ( *a2 == 1 )
        return v2;
      goto LABEL_12;
    }
  }
LABEL_8:
  v7 = IsUiccProvisioningEnabled();
  if ( hMem )
    LocalFree(hMem);
  return v7;
}

```

## disassembly

```asm
0x18002a910  mov     [rsp+arg_0], rbx
0x18002a915  mov     [rsp+arg_8], rsi
0x18002a91a  push    rdi
0x18002a91b  sub     rsp, 30h
0x18002a91f  mov     [rsp+38h+hMem], 0
0x18002a928  mov     edi, 1
0x18002a92d  cmp     ecx, 8
0x18002a930  jg      short loc_18002A980
0x18002a932  jz      short loc_18002A977
0x18002a934  sub     ecx, edi
0x18002a936  jz      short loc_18002A977
0x18002a938  sub     ecx, 2
0x18002a93b  jz      short loc_18002A94A
0x18002a93d  sub     ecx, edi
0x18002a93f  jz      short loc_18002A94A
0x18002a941  sub     ecx, 2
0x18002a944  jz      short loc_18002A973
0x18002a946  cmp     ecx, edi
0x18002a948  jnz     short loc_18002A996
0x18002a94a  call    IsUiccProvisioningEnabled
0x18002a94f  mov     bl, al
0x18002a951  mov     rcx, [rsp+38h+hMem]; hMem
0x18002a956  test    rcx, rcx
0x18002a959  jz      short loc_18002A961
0x18002a95b  call    cs:__imp_LocalFree
0x18002a961  mov     al, bl
0x18002a963  mov     rbx, [rsp+38h+arg_0]
0x18002a968  mov     rsi, [rsp+38h+arg_8]
0x18002a96d  add     rsp, 30h
0x18002a971  pop     rdi
0x18002a972  retn
0x18002a973  cmp     [rdx], edi
0x18002a975  jz      short loc_18002A996
0x18002a977  cmp     dword ptr [rdx], 3
0x18002a97a  jnz     short loc_18002A94A
0x18002a97c  xor     al, al
0x18002a97e  jmp     short loc_18002A963
0x18002a980  sub     ecx, 9
0x18002a983  jz      short loc_18002A94A
0x18002a985  sub     ecx, edi
0x18002a987  jz      loc_18002AA2B
0x18002a98d  sub     ecx, edi
0x18002a98f  jz      short loc_18002A94A
0x18002a991  cmp     ecx, 6
0x18002a994  jz      short loc_18002A99B
0x18002a996  jmp     loc_18002AA5E
0x18002a99b  call    IsCheckUserConsentPresent
0x18002a9a0  test    al, al
0x18002a9a2  jz      short loc_18002AA12
0x18002a9a4  mov     rsi, [rsp+38h+hMem]
0x18002a9a9  test    rsi, rsi
0x18002a9ac  jz      short loc_18002A9C7
0x18002a9ae  call    cs:__imp_GetLastError
0x18002a9b4  mov     ebx, eax
0x18002a9b6  mov     rcx, rsi; hMem
0x18002a9b9  call    cs:__imp_LocalFree
0x18002a9bf  mov     ecx, ebx; dwErrCode
0x18002a9c1  call    cs:__imp_SetLastError
0x18002a9c7  mov     [rsp+38h+hMem], 0
0x18002a9d0  lea     rcx, [rsp+38h+hMem]
0x18002a9d5  call    cs:__imp_GetProvisioningTargetUser
0x18002a9db  test    eax, eax
0x18002a9dd  js      short loc_18002AA12
0x18002a9df  mov     rcx, cs:g_hProvTraceProvider
0x18002a9e6  mov     eax, [rcx]
0x18002a9e8  cmp     eax, 4
0x18002a9eb  jbe     short loc_18002AA4E
0x18002a9ed  mov     rax, [rsp+38h+hMem]
0x18002a9f2  mov     [rsp+38h+arg_18], rax
0x18002a9f7  lea     rax, [rsp+38h+arg_18]
0x18002a9fc  mov     [rsp+38h+var_18], rax
0x18002aa01  xor     r8d, r8d
0x18002aa04  lea     rdx, byte_1800414C1
0x18002aa0b  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18002aa10  jmp     short loc_18002AA4E
0x18002aa12  mov     rcx, [rsp+38h+hMem]; hMem
0x18002aa17  test    rcx, rcx
0x18002aa1a  jz      loc_18002A97C
0x18002aa20  call    cs:__imp_LocalFree
0x18002aa26  jmp     loc_18002A97C
0x18002aa2b  lea     rcx, ?gc_wszMVStateUiccRunOnce@@3QBGB; "Uicc_RunOnce"
0x18002aa32  call    IsUpdateRelevantForState
0x18002aa37  test    al, al
0x18002aa39  jnz     short loc_18002AA4E
0x18002aa3b  lea     rcx, ?gc_wszMVStateExtensionRunOnce@@3QBGB; "Extension_RunOnce"
0x18002aa42  call    IsUpdateRelevantForState
0x18002aa47  test    al, al
0x18002aa49  jnz     short loc_18002AA4E
0x18002aa4b  xor     dil, dil
0x18002aa4e  mov     rcx, [rsp+38h+hMem]; hMem
0x18002aa53  test    rcx, rcx
0x18002aa56  jz      short loc_18002AA5E
0x18002aa58  call    cs:__imp_LocalFree
0x18002aa5e  mov     al, dil
0x18002aa61  jmp     loc_18002A963
```
