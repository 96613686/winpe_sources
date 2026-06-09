# CRASHookPage::OnCommit(void)

- ea: `0x18001ea60`
- end: `0x18001eca9`
- name: `?OnCommit@CRASHookPage@@UEAAJXZ`
- size: `585`
- prototype: `__int64 __fastcall(CRASHookPage *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x18001213c`
- `0x18001ea60`
- `0x180030010`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x18001ea99`
- `rtutils!TracePrintfExA` at `0x18001eac4`
- `rtutils!TracePrintfExA` at `0x18001eb3f`
- `rtutils!TracePrintfExA` at `0x18001eb78`
- `rtutils!TracePrintfExA` at `0x18001ebc2`
- `rtutils!TracePrintfExA` at `0x18001ec08`
- `rtutils!TracePrintfExA` at `0x18001ec58`
- `rtutils!TracePrintfExA` at `0x18001ea99`
- `rtutils!TracePrintfExA` at `0x18001eac4`
- `rtutils!TracePrintfExA` at `0x18001eb3f`
- `rtutils!TracePrintfExA` at `0x18001eb78`
- `rtutils!TracePrintfExA` at `0x18001ebc2`
- `rtutils!TracePrintfExA` at `0x18001ec08`
- `rtutils!TracePrintfExA` at `0x18001ec58`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001eafb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001eafb`

## string_xrefs

- `0x18001eaba`: `CRASHookPage::OnCommit: Graceful exit of OnCommit as the data is not still valid.`
- `0x18001ea8f`: `CRASHookPage::OnCommit.`
- `0x18001eb6e`: `CRASHookPage::OnCommit:Failed to do CoCreateInstance for IID_IGlobalInterfaceTable. hr = %#x`
- `0x18001eb35`: `CRASHookPage::OnCommit:GetInterfaceFromGlobal failed for IRasGcwLUA. hr = %#x`
- `0x18001ebfe`: `CRASHookPage::OnCommit:SetRASCredentials result. hr = %#x`
- `0x18001ebb8`: `CRASHookPage::OnCommit:CommitRASEntry result. hr = %#x`
- `0x18001ec4e`: `CRASHookPage::OnCommit:SetAsDefaultInternetConnection result. hr = %#x`

## pseudocode

```c
__int64 __fastcall CRASHookPage::OnCommit(CRASHookPage *this)
{
  DWORD v2; // ecx
  int v3; // edi
  HRESULT v4; // eax
  int v5; // eax
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rdx
  int v9; // eax
  _DWORD *v10; // rdx
  int v11; // eax
  __int64 v13; // [rsp+60h] [rbp+30h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp+38h] BYREF

  v2 = g_dwTraceId;
  v13 = 0;
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "CRASHookPage::OnCommit.");
    v2 = g_dwTraceId;
  }
  if ( *(_DWORD *)(*((_QWORD *)this + 7) + 4952LL) )
  {
    v3 = 0;
    if ( *((_DWORD *)this + 12) )
    {
      ppv = 0;
      v4 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &IID_IGlobalInterfaceTable, &ppv);
      if ( v4 < 0 )
      {
        if ( g_dwTraceId != -1 )
          TracePrintfExA(
            g_dwTraceId,
            0xCu,
            "CRASHookPage::OnCommit:Failed to do CoCreateInstance for IID_IGlobalInterfaceTable. hr = %#x",
            v4);
      }
      else
      {
        v5 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, __int64 *))(*(_QWORD *)ppv + 40LL))(
               ppv,
               *((unsigned int *)this + 12),
               &IID_IRasGcwLUA,
               &v13);
        if ( v5 < 0 )
        {
          if ( g_dwTraceId != -1 )
            TracePrintfExA(
              g_dwTraceId,
              0xCu,
              "CRASHookPage::OnCommit:GetInterfaceFromGlobal failed for IRasGcwLUA. hr = %#x",
              v5);
          v13 = 0;
        }
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        v3 = 1;
      }
      v6 = v13;
    }
    else
    {
      v6 = *((_QWORD *)this + 8);
      v13 = v6;
    }
    if ( v6 )
    {
      if ( *((_DWORD *)this + 18) )
      {
        v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v6 + 40LL))(v6, *((_QWORD *)this + 7));
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "CRASHookPage::OnCommit:CommitRASEntry result. hr = %#x", v7);
        v6 = v13;
      }
      v8 = *((_QWORD *)this + 7);
      if ( !*(_DWORD *)(v8 + 1816) && *(_WORD *)(v8 + 1820) )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v6 + 48LL))(v6, v8, 0);
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "CRASHookPage::OnCommit:SetRASCredentials result. hr = %#x", v9);
        v6 = v13;
        *((_DWORD *)this + 19) = 1;
      }
      v10 = (_DWORD *)*((_QWORD *)this + 7);
      if ( *v10 == 5 || *v10 == 1 && v10[1] == 2 )
      {
        v11 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 56LL))(v6, (__int64)v10 + 1038);
        if ( g_dwTraceId != -1 )
          TracePrintfExA(
            g_dwTraceId,
            0xCu,
            "CRASHookPage::OnCommit:SetAsDefaultInternetConnection result. hr = %#x",
            v11);
      }
    }
    UpdateUserContextParameter((char *)this + 8, *((_QWORD *)this + 4), *((_QWORD *)this + 7) + 1038LL);
    if ( v3 && v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  else if ( v2 != -1 )
  {
    TracePrintfExA(v2, 0xCu, "CRASHookPage::OnCommit: Graceful exit of OnCommit as the data is not still valid.");
  }
  return 0;
}

```

## disassembly

```asm
0x18001ea60  mov     [rsp-28h+arg_10], rbx
0x18001ea65  push    rbp
0x18001ea66  push    rsi
0x18001ea67  push    rdi
0x18001ea68  push    r14
0x18001ea6a  push    r15
0x18001ea6c  mov     rbp, rsp
0x18001ea6f  sub     rsp, 30h
0x18001ea73  xor     esi, esi
0x18001ea75  mov     rbx, rcx
0x18001ea78  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001ea7e  or      r14d, 0FFFFFFFFh
0x18001ea82  mov     [rbp+arg_0], rsi
0x18001ea86  lea     r15d, [rsi+0Ch]
0x18001ea8a  cmp     ecx, r14d
0x18001ea8d  jz      short loc_18001EAA5
0x18001ea8f  lea     r8, aCrashookpageOn_18; "CRASHookPage::OnCommit."
0x18001ea96  mov     edx, r15d; dwFlags
0x18001ea99  call    cs:__imp_TracePrintfExA
0x18001ea9f  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001eaa5  mov     rax, [rbx+38h]
0x18001eaa9  cmp     [rax+1358h], esi
0x18001eaaf  jnz     short loc_18001EACF
0x18001eab1  cmp     ecx, r14d
0x18001eab4  jz      loc_18001EC96
0x18001eaba  lea     r8, aCrashookpageOn; "CRASHookPage::OnCommit: Graceful exit o"...
0x18001eac1  mov     edx, r15d; dwFlags
0x18001eac4  call    cs:__imp_TracePrintfExA
0x18001eaca  jmp     loc_18001EC96
0x18001eacf  mov     edi, esi
0x18001ead1  cmp     [rbx+30h], esi
0x18001ead4  jz      loc_18001EB84
0x18001eada  xor     edx, edx; pUnkOuter
0x18001eadc  mov     [rbp+arg_8], rsi
0x18001eae0  lea     rax, [rbp+arg_8]
0x18001eae4  lea     r9, IID_IGlobalInterfaceTable; riid
0x18001eaeb  mov     [rsp+30h+ppv], rax; ppv
0x18001eaf0  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18001eaf7  lea     r8d, [rdx+1]; dwClsContext
0x18001eafb  call    cs:__imp_CoCreateInstance
0x18001eb01  test    eax, eax
0x18001eb03  js      short loc_18001EB60
0x18001eb05  mov     rcx, [rbp+arg_8]
0x18001eb09  lea     r9, [rbp+arg_0]
0x18001eb0d  mov     edx, [rbx+30h]
0x18001eb10  lea     r8, IID_IRasGcwLUA
0x18001eb17  mov     rax, [rcx]
0x18001eb1a  mov     rax, [rax+28h]
0x18001eb1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb23  test    eax, eax
0x18001eb25  jns     short loc_18001EB49
0x18001eb27  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001eb2d  cmp     ecx, r14d
0x18001eb30  jz      short loc_18001EB45
0x18001eb32  mov     r9d, eax
0x18001eb35  lea     r8, aCrashookpageOn_11; "CRASHookPage::OnCommit:GetInterfaceFrom"...
0x18001eb3c  mov     edx, r15d; dwFlags
0x18001eb3f  call    cs:__imp_TracePrintfExA
0x18001eb45  mov     [rbp+arg_0], rsi
0x18001eb49  mov     rcx, [rbp+arg_8]
0x18001eb4d  mov     rax, [rcx]
0x18001eb50  mov     rax, [rax+10h]
0x18001eb54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb59  mov     edi, 1
0x18001eb5e  jmp     short loc_18001EB7E
0x18001eb60  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001eb66  cmp     ecx, r14d
0x18001eb69  jz      short loc_18001EB7E
0x18001eb6b  mov     r9d, eax
0x18001eb6e  lea     r8, aCrashookpageOn_5; "CRASHookPage::OnCommit:Failed to do CoC"...
0x18001eb75  mov     edx, r15d; dwFlags
0x18001eb78  call    cs:__imp_TracePrintfExA
0x18001eb7e  mov     rcx, [rbp+arg_0]
0x18001eb82  jmp     short loc_18001EB8C
0x18001eb84  mov     rcx, [rbx+40h]
0x18001eb88  mov     [rbp+arg_0], rcx
0x18001eb8c  test    rcx, rcx
0x18001eb8f  jz      loc_18001EC5E
0x18001eb95  cmp     [rbx+48h], esi
0x18001eb98  jz      short loc_18001EBCC
0x18001eb9a  mov     rax, [rcx]
0x18001eb9d  mov     rdx, [rbx+38h]
0x18001eba1  mov     rax, [rax+28h]
0x18001eba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebaa  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001ebb0  cmp     ecx, r14d
0x18001ebb3  jz      short loc_18001EBC8
0x18001ebb5  mov     r9d, eax
0x18001ebb8  lea     r8, aCrashookpageOn_12; "CRASHookPage::OnCommit:CommitRASEntry r"...
0x18001ebbf  mov     edx, r15d; dwFlags
0x18001ebc2  call    cs:__imp_TracePrintfExA
0x18001ebc8  mov     rcx, [rbp+arg_0]
0x18001ebcc  mov     rdx, [rbx+38h]
0x18001ebd0  cmp     [rdx+718h], esi
0x18001ebd6  jnz     short loc_18001EC19
0x18001ebd8  cmp     [rdx+71Ch], si
0x18001ebdf  jz      short loc_18001EC19
0x18001ebe1  mov     rax, [rcx]
0x18001ebe4  xor     r8d, r8d
0x18001ebe7  mov     rax, [rax+30h]
0x18001ebeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebf0  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001ebf6  cmp     ecx, r14d
0x18001ebf9  jz      short loc_18001EC0E
0x18001ebfb  mov     r9d, eax
0x18001ebfe  lea     r8, aCrashookpageOn_15; "CRASHookPage::OnCommit:SetRASCredential"...
0x18001ec05  mov     edx, r15d; dwFlags
0x18001ec08  call    cs:__imp_TracePrintfExA
0x18001ec0e  mov     rcx, [rbp+arg_0]
0x18001ec12  mov     dword ptr [rbx+4Ch], 1
0x18001ec19  mov     rdx, [rbx+38h]
0x18001ec1d  cmp     dword ptr [rdx], 5
0x18001ec20  jz      short loc_18001EC2D
0x18001ec22  cmp     dword ptr [rdx], 1
0x18001ec25  jnz     short loc_18001EC5E
0x18001ec27  cmp     dword ptr [rdx+4], 2
0x18001ec2b  jnz     short loc_18001EC5E
0x18001ec2d  mov     rax, [rcx]
0x18001ec30  add     rdx, 40Eh
0x18001ec37  mov     rax, [rax+38h]
0x18001ec3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec40  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001ec46  cmp     ecx, r14d
0x18001ec49  jz      short loc_18001EC5E
0x18001ec4b  mov     r9d, eax
0x18001ec4e  lea     r8, aCrashookpageOn_10; "CRASHookPage::OnCommit:SetAsDefaultInte"...
0x18001ec55  mov     edx, r15d; dwFlags
0x18001ec58  call    cs:__imp_TracePrintfExA
0x18001ec5e  mov     r8, [rbx+38h]
0x18001ec62  lea     rcx, [rbx+8]
0x18001ec66  mov     eax, [rbx+48h]
0x18001ec69  add     r8, 40Eh
0x18001ec70  mov     rdx, [rbx+20h]
0x18001ec74  mov     dword ptr [rsp+30h+ppv], eax
0x18001ec78  call    UpdateUserContextParameter
0x18001ec7d  test    edi, edi
0x18001ec7f  jz      short loc_18001EC96
0x18001ec81  mov     rcx, [rbp+arg_0]
0x18001ec85  test    rcx, rcx
0x18001ec88  jz      short loc_18001EC96
0x18001ec8a  mov     rax, [rcx]
0x18001ec8d  mov     rax, [rax+10h]
0x18001ec91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec96  mov     rbx, [rsp+30h+arg_10]
0x18001ec9b  xor     eax, eax
0x18001ec9d  add     rsp, 30h
0x18001eca1  pop     r15
0x18001eca3  pop     r14
0x18001eca5  pop     rdi
0x18001eca6  pop     rsi
0x18001eca7  pop     rbp
0x18001eca8  retn
```
