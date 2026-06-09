# OnClickAllUserProfile

- ea: `0x180011bc0`
- end: `0x180011dcd`
- name: `OnClickAllUserProfile`
- size: `525`
- prototype: `__int64 __fastcall(__int64, HWND, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180013330`
- `0x18001a480`

## callees

- `0x180010684`
- `0x18001077c`
- `0x180010928`
- `0x180010fe0`
- `0x180011bc0`
- `0x18002b204`
- `0x18002b2b0`
- `0x180030010`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x180011c47`
- `rtutils!TracePrintfExA` at `0x180011ce1`
- `rtutils!TracePrintfExA` at `0x180011cfd`
- `rtutils!TracePrintfExA` at `0x180011d23`
- `rtutils!TracePrintfExA` at `0x180011d91`
- `rtutils!TracePrintfExA` at `0x180011c47`
- `rtutils!TracePrintfExA` at `0x180011ce1`
- `rtutils!TracePrintfExA` at `0x180011cfd`
- `rtutils!TracePrintfExA` at `0x180011d23`
- `rtutils!TracePrintfExA` at `0x180011d91`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011c23`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011c23`

## string_xrefs

- `0x180011c3b`: `OnClickAllUserProfile:Failed to create CoCreateInstance for IID_IGlobalInterfaceTable. hr = %#x`
- `0x180011d17`: `OnClickAllUserProfile:Failed to create NtlCoCreateInstanceAsNetConfigOpOrAdmin for IID_IRasGcwLUA. hr = %#x`

## pseudocode

```c
__int64 __fastcall OnClickAllUserProfile(__int64 a1, HWND a2, int a3)
{
  HRESULT v6; // eax
  int *v7; // rdx
  unsigned int v9; // r14d
  const struct _GUID *v10; // rdx
  signed int v11; // ebx
  const struct _GUID *v12; // r8
  const struct _GUID *v13; // r9
  HRESULT v14; // eax
  int v15; // eax
  int v16; // eax
  void *v17; // [rsp+30h] [rbp-10h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-8h] BYREF
  int v19; // [rsp+78h] [rbp+38h] BYREF

  ppv = 0;
  if ( (unsigned int)FIsUserAdmin() || (unsigned int)FIsUserGroupMember(0x22Cu) )
    return 1;
  v6 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &IID_IGlobalInterfaceTable, &ppv);
  if ( v6 >= 0 )
  {
    if ( a3 )
    {
      v9 = 0;
      v17 = 0;
      v19 = 0;
      v11 = IsUserMemberOfNCO(&v19, v7);
      if ( v11 < 0
        || (!v19
          ? (v14 = CoCreateInstanceAsAdmin(a2, v10, v12, &v17))
          : (v14 = CoCreateInstanceElevated(a2, v10, (const unsigned __int16 *)v12, v13, &v17)),
            v11 = v14,
            v14 < 0) )
      {
        if ( g_dwTraceId == -1
          || (TracePrintfExA(
                g_dwTraceId,
                0xCu,
                "OnClickAllUserProfile:Failed to create NtlCoCreateInstanceAsNetConfigOpOrAdmin for IID_IRasGcwLUA. hr = %#x",
                v11),
              v11 < 0) )
        {
          if ( v11 != -2147023673 )
            ThrowErrorBox(a2, v11);
        }
      }
      else
      {
        v15 = (*(__int64 (__fastcall **)(LPVOID, void *, GUID *, __int64))(*(_QWORD *)ppv + 24LL))(
                ppv,
                v17,
                &IID_IRasGcwLUA,
                a1 + 8);
        if ( v15 < 0 )
        {
          if ( g_dwTraceId != -1 )
            TracePrintfExA(
              g_dwTraceId,
              0xCu,
              "OnClickAllUserProfile:Failed to add interface to RegisterInterfaceInGlobal for IID_IRasGcwLUA. hr = %#x",
              v15);
          *(_DWORD *)(a1 + 8) = 0;
        }
        else
        {
          v9 = 1;
          if ( g_dwTraceId != -1 )
            TracePrintfExA(
              g_dwTraceId,
              0xCu,
              "OnClickAllUserProfile:Successfully add RegisterInterfaceInGlobal for IID_IRasGcwLUA");
        }
      }
      if ( v17 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v17 + 16LL))(v17);
    }
    else
    {
      v9 = 1;
      if ( *(_DWORD *)(a1 + 8) )
      {
        v16 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 32LL))(ppv);
        if ( v16 < 0 && g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "OnClickAllUserProfile:RevokeInterfaceFromGlobal failed. hr = %#x", v16);
        *(_DWORD *)(a1 + 8) = 0;
      }
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return v9;
  }
  else
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(
        g_dwTraceId,
        0xCu,
        "OnClickAllUserProfile:Failed to create CoCreateInstance for IID_IGlobalInterfaceTable. hr = %#x",
        v6);
    return 0;
  }
}

```

## disassembly

```asm
0x180011bc0  mov     [rsp-18h+arg_0], rbx
0x180011bc5  mov     [rsp-18h+arg_8], rsi
0x180011bca  push    rbp
0x180011bcb  push    r14
0x180011bcd  push    r15
0x180011bcf  mov     rbp, rsp
0x180011bd2  sub     rsp, 40h
0x180011bd6  mov     ebx, r8d
0x180011bd9  mov     [rbp+var_8], 0
0x180011be1  mov     rsi, rdx
0x180011be4  mov     r15, rcx
0x180011be7  call    FIsUserAdmin
0x180011bec  test    eax, eax
0x180011bee  jnz     loc_180011DB4
0x180011bf4  mov     ecx, 22Ch; nSubAuthority1
0x180011bf9  call    FIsUserGroupMember
0x180011bfe  test    eax, eax
0x180011c00  jnz     loc_180011DB4
0x180011c06  xor     edx, edx; pUnkOuter
0x180011c08  lea     rax, [rbp+var_8]
0x180011c0c  lea     r9, IID_IGlobalInterfaceTable; riid
0x180011c13  mov     [rsp+40h+ppv], rax; ppv
0x180011c18  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180011c1f  lea     r8d, [rdx+1]; dwClsContext
0x180011c23  call    cs:__imp_CoCreateInstance
0x180011c29  test    eax, eax
0x180011c2b  jns     short loc_180011C54
0x180011c2d  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180011c33  cmp     ecx, 0FFFFFFFFh
0x180011c36  jz      short loc_180011C4D
0x180011c38  mov     r9d, eax
0x180011c3b  lea     r8, aOnclickalluser_1; "OnClickAllUserProfile:Failed to create "...
0x180011c42  mov     edx, 0Ch; dwFlags
0x180011c47  call    cs:__imp_TracePrintfExA
0x180011c4d  xor     eax, eax
0x180011c4f  jmp     loc_180011DB9
0x180011c54  test    ebx, ebx
0x180011c56  jz      loc_180011D56
0x180011c5c  xor     r14d, r14d
0x180011c5f  lea     rcx, [rbp+arg_18]; int *
0x180011c63  mov     [rbp+var_10], r14
0x180011c67  mov     [rbp+arg_18], r14d
0x180011c6b  call    ?IsUserMemberOfNCO@@YAJPEAH0@Z; IsUserMemberOfNCO(int *,int *)
0x180011c70  mov     ebx, eax
0x180011c72  test    eax, eax
0x180011c74  js      loc_180011D09
0x180011c7a  mov     rcx, rsi; HWND
0x180011c7d  cmp     [rbp+arg_18], r14d
0x180011c81  jz      short loc_180011C93
0x180011c83  lea     rax, [rbp+var_10]
0x180011c87  mov     [rsp+40h+ppv], rax; ppv
0x180011c8c  call    ?CoCreateInstanceElevated@@YAJPEAUHWND__@@AEBU_GUID@@PEBG1PEAPEAX@Z; CoCreateInstanceElevated(HWND__ *,_GUID const &,ushort const *,_GUID const &,void * *)
0x180011c91  jmp     short loc_180011C9C
0x180011c93  lea     r9, [rbp+var_10]; void **
0x180011c97  call    ?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z; CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)
0x180011c9c  mov     ebx, eax
0x180011c9e  test    eax, eax
0x180011ca0  js      short loc_180011D09
0x180011ca2  mov     rcx, [rbp+var_8]
0x180011ca6  lea     r9, [r15+8]
0x180011caa  mov     rdx, [rbp+var_10]
0x180011cae  lea     r8, IID_IRasGcwLUA
0x180011cb5  mov     rax, [rcx]
0x180011cb8  mov     rax, [rax+18h]
0x180011cbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cc1  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180011cc7  test    eax, eax
0x180011cc9  js      short loc_180011CE9
0x180011ccb  mov     r14d, 1
0x180011cd1  cmp     ecx, 0FFFFFFFFh
0x180011cd4  jz      short loc_180011D3F
0x180011cd6  lea     r8, aOnclickalluser; "OnClickAllUserProfile:Successfully add "...
0x180011cdd  lea     edx, [r14+0Bh]; dwFlags
0x180011ce1  call    cs:__imp_TracePrintfExA
0x180011ce7  jmp     short loc_180011D3F
0x180011ce9  cmp     ecx, 0FFFFFFFFh
0x180011cec  jz      short loc_180011D03
0x180011cee  mov     r9d, eax
0x180011cf1  lea     r8, aOnclickalluser_3; "OnClickAllUserProfile:Failed to add int"...
0x180011cf8  mov     edx, 0Ch; dwFlags
0x180011cfd  call    cs:__imp_TracePrintfExA
0x180011d03  mov     [r15+8], r14d
0x180011d07  jmp     short loc_180011D3F
0x180011d09  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180011d0f  cmp     ecx, 0FFFFFFFFh
0x180011d12  jz      short loc_180011D2D
0x180011d14  mov     r9d, ebx
0x180011d17  lea     r8, aOnclickalluser_2; "OnClickAllUserProfile:Failed to create "...
0x180011d1e  mov     edx, 0Ch; dwFlags
0x180011d23  call    cs:__imp_TracePrintfExA
0x180011d29  test    ebx, ebx
0x180011d2b  jns     short loc_180011D3F
0x180011d2d  cmp     ebx, 800704C7h
0x180011d33  jz      short loc_180011D3F
0x180011d35  mov     edx, ebx; dwMessageId
0x180011d37  mov     rcx, rsi; hwndOwner
0x180011d3a  call    ?ThrowErrorBox@@YAXQEAUHWND__@@J@Z; ThrowErrorBox(HWND__ * const,long)
0x180011d3f  mov     rcx, [rbp+var_10]
0x180011d43  test    rcx, rcx
0x180011d46  jz      short loc_180011D9F
0x180011d48  mov     rax, [rcx]
0x180011d4b  mov     rax, [rax+10h]
0x180011d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d54  jmp     short loc_180011D9F
0x180011d56  mov     edx, [r15+8]
0x180011d5a  mov     r14d, 1
0x180011d60  test    edx, edx
0x180011d62  jz      short loc_180011D9F
0x180011d64  mov     rcx, [rbp+var_8]
0x180011d68  mov     rax, [rcx]
0x180011d6b  mov     rax, [rax+20h]
0x180011d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d74  test    eax, eax
0x180011d76  jns     short loc_180011D97
0x180011d78  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180011d7e  cmp     ecx, 0FFFFFFFFh
0x180011d81  jz      short loc_180011D97
0x180011d83  mov     r9d, eax
0x180011d86  lea     r8, aOnclickalluser_0; "OnClickAllUserProfile:RevokeInterfaceFr"...
0x180011d8d  lea     edx, [r14+0Bh]; dwFlags
0x180011d91  call    cs:__imp_TracePrintfExA
0x180011d97  mov     dword ptr [r15+8], 0
0x180011d9f  mov     rcx, [rbp+var_8]
0x180011da3  mov     rdx, [rcx]
0x180011da6  mov     rax, [rdx+10h]
0x180011daa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011daf  mov     eax, r14d
0x180011db2  jmp     short loc_180011DB9
0x180011db4  mov     eax, 1
0x180011db9  mov     rbx, [rsp+40h+arg_0]
0x180011dbe  mov     rsi, [rsp+40h+arg_8]
0x180011dc3  add     rsp, 40h
0x180011dc7  pop     r15
0x180011dc9  pop     r14
0x180011dcb  pop     rbp
0x180011dcc  retn
```
