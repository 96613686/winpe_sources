# CscService_ApplyOfflineRenameDeleteSettings(void)

- ea: `0x180054a68`
- end: `0x180054c3c`
- name: `?CscService_ApplyOfflineRenameDeleteSettings@@YAJXZ`
- size: `468`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800563e0`
- `0x180056510`

## callees

- `0x18001b150`
- `0x180025210`
- `0x18002af38`
- `0x18002b6c8`
- `0x180036394`
- `0x1800391b8`
- `0x180039204`
- `0x18003c488`
- `0x180054a68`
- `0x180056928`
- `0x18005696c`
- `0x18005732c`
- `0x180080b88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054bd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054bd2`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180054acc`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180054acc`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180054baf`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180054baf`
- `KERNEL32!LocalFree` at `0x180054b7d`
- `KERNEL32!LocalFree` at `0x180054b7d`

## pseudocode

```c
__int64 CscService_ApplyOfflineRenameDeleteSettings(void)
{
  CAuthInfoListIter *v0; // rax
  CAuthInfoListIter *v1; // rbx
  unsigned int i; // edi
  CRefCounted *v3; // rdi
  int v4; // eax
  const unsigned __int16 *v5; // rax
  int v6; // eax
  DWORD LastError; // eax
  __int64 v9; // [rsp+20h] [rbp-58h] BYREF
  HLOCAL hMem; // [rsp+28h] [rbp-50h]
  struct tagVARIANT v11[3]; // [rsp+30h] [rbp-48h] BYREF
  CRefCounted *v12; // [rsp+A0h] [rbp+28h] BYREF

  v0 = (CAuthInfoListIter *)operator new(0x18u);
  v1 = v0;
  if ( v0 )
  {
    v12 = 0;
    *(_QWORD *)v0 = &g_AgentAuthInfo;
    *((_QWORD *)v0 + 1) = &stru_1800B6A90;
    for ( i = CAuthInfoListIter::Next(v0, &v12); !i; i = CAuthInfoListIter::Next(v1, &v12) )
    {
      v3 = v12;
      if ( ImpersonateLoggedOnUser(*((HANDLE *)v12 + 4)) )
      {
        COfflineRenameDeleteConfig::COfflineRenameDeleteConfig((COfflineRenameDeleteConfig *)v11);
        v4 = COfflineRenameDeleteConfig::_Load(v11, 0);
        if ( v4 < 0 )
        {
          if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              29,
              WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids,
              (unsigned int)v4);
          }
        }
        else
        {
          v9 = *((_QWORD *)v3 + 7);
          hMem = 0;
          if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            v5 = CSidString::Get((CSidString *)&v9);
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids, v5);
          }
          v6 = COfflineRenameDeleteConfig::Apply((COfflineRenameDeleteConfig *)v11, 0);
          if ( v6 < 0
            && WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              28,
              WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids,
              (unsigned int)v6);
          }
          LocalFree(hMem);
        }
        RevertToSelf();
        COfflineRenameDeleteConfig::_Clear((COfflineRenameDeleteConfig *)v11);
      }
      else if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids, LastError);
      }
      CRefCounted::ReleaseReference(v3);
    }
    CAuthInfoListIter::~CAuthInfoListIter(v1);
    operator delete(v1, 0x18u);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return i;
}

```

## disassembly

```asm
0x180054a68  push    rbp
0x180054a6a  push    rbx
0x180054a6b  push    rsi
0x180054a6c  push    rdi
0x180054a6d  mov     rbp, rsp
0x180054a70  sub     rsp, 78h
0x180054a74  mov     ecx, 18h; Size
0x180054a79  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180054a7e  mov     rbx, rax
0x180054a81  test    rax, rax
0x180054a84  jz      loc_180054C2C
0x180054a8a  lea     rax, ?g_AgentAuthInfo@@3VCAuthInfoList@@A; CAuthInfoList g_AgentAuthInfo
0x180054a91  mov     [rbp+arg_0], 0
0x180054a99  mov     [rbx], rax
0x180054a9c  lea     rdx, [rbp+arg_0]; struct CAuthInfo **
0x180054aa0  lea     rax, stru_1800B6A90
0x180054aa7  mov     rcx, rbx; this
0x180054aaa  mov     [rbx+8], rax
0x180054aae  call    ?Next@CAuthInfoListIter@@QEAAJPEAPEAVCAuthInfo@@@Z; CAuthInfoListIter::Next(CAuthInfo * *)
0x180054ab3  mov     edi, eax
0x180054ab5  test    eax, eax
0x180054ab7  jnz     loc_180054C15
0x180054abd  lea     rsi, WPP_GLOBAL_Control
0x180054ac4  mov     rdi, [rbp+arg_0]
0x180054ac8  mov     rcx, [rdi+20h]; hToken
0x180054acc  call    cs:__imp_ImpersonateLoggedOnUser
0x180054ad2  test    eax, eax
0x180054ad4  jz      loc_180054BC0
0x180054ada  lea     rcx, [rbp+var_48]; this
0x180054ade  call    ??0COfflineRenameDeleteConfig@@QEAA@XZ; COfflineRenameDeleteConfig::COfflineRenameDeleteConfig(void)
0x180054ae3  xor     edx, edx; int
0x180054ae5  lea     rcx, [rbp+var_48]; this
0x180054ae9  call    ?_Load@COfflineRenameDeleteConfig@@AEAAJH@Z; COfflineRenameDeleteConfig::_Load(int)
0x180054aee  test    eax, eax
0x180054af0  js      loc_180054B85
0x180054af6  mov     rax, [rdi+38h]
0x180054afa  mov     [rbp+var_58], rax
0x180054afe  mov     [rbp+hMem], 0
0x180054b06  mov     rax, cs:WPP_GLOBAL_Control
0x180054b0d  cmp     rax, rsi
0x180054b10  jz      short loc_180054B40
0x180054b12  test    byte ptr [rax+1Ch], 8
0x180054b16  jz      short loc_180054B40
0x180054b18  lea     rcx, [rbp+var_58]; this
0x180054b1c  call    ?Get@CSidString@@QEBAPEBGXZ; CSidString::Get(void)
0x180054b21  mov     rcx, cs:WPP_GLOBAL_Control
0x180054b28  lea     r8, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids
0x180054b2f  mov     edx, 1Bh
0x180054b34  mov     r9, rax
0x180054b37  mov     rcx, [rcx+10h]
0x180054b3b  call    WPP_SF_S
0x180054b40  xor     edx, edx; int *
0x180054b42  lea     rcx, [rbp+var_48]; this
0x180054b46  call    ?Apply@COfflineRenameDeleteConfig@@QEAAJPEAH@Z; COfflineRenameDeleteConfig::Apply(int *)
0x180054b4b  test    eax, eax
0x180054b4d  jns     short loc_180054B79
0x180054b4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180054b56  cmp     rcx, rsi
0x180054b59  jz      short loc_180054B79
0x180054b5b  test    byte ptr [rcx+1Ch], 2
0x180054b5f  jz      short loc_180054B79
0x180054b61  mov     rcx, [rcx+10h]
0x180054b65  lea     r8, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids
0x180054b6c  mov     edx, 1Ch
0x180054b71  mov     r9d, eax
0x180054b74  call    WPP_SF_d
0x180054b79  mov     rcx, [rbp+hMem]; hMem
0x180054b7d  call    cs:__imp_LocalFree
0x180054b83  jmp     short loc_180054BAF
0x180054b85  mov     rcx, cs:WPP_GLOBAL_Control
0x180054b8c  cmp     rcx, rsi
0x180054b8f  jz      short loc_180054BAF
0x180054b91  test    byte ptr [rcx+1Ch], 2
0x180054b95  jz      short loc_180054BAF
0x180054b97  mov     rcx, [rcx+10h]
0x180054b9b  lea     r8, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids
0x180054ba2  mov     edx, 1Dh
0x180054ba7  mov     r9d, eax
0x180054baa  call    WPP_SF_d
0x180054baf  call    cs:__imp_RevertToSelf
0x180054bb5  lea     rcx, [rbp+var_48]; this
0x180054bb9  call    ?_Clear@COfflineRenameDeleteConfig@@AEAAXXZ; COfflineRenameDeleteConfig::_Clear(void)
0x180054bbe  jmp     short loc_180054BF7
0x180054bc0  mov     rax, cs:WPP_GLOBAL_Control
0x180054bc7  cmp     rax, rsi
0x180054bca  jz      short loc_180054BF7
0x180054bcc  test    byte ptr [rax+1Ch], 2
0x180054bd0  jz      short loc_180054BF7
0x180054bd2  call    cs:__imp_GetLastError
0x180054bd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180054bdf  lea     r8, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids
0x180054be6  mov     edx, 1Eh
0x180054beb  mov     r9d, eax
0x180054bee  mov     rcx, [rcx+10h]
0x180054bf2  call    WPP_SF_d
0x180054bf7  mov     rcx, rdi; this
0x180054bfa  call    ?ReleaseReference@CRefCounted@@QEAAXXZ; CRefCounted::ReleaseReference(void)
0x180054bff  lea     rdx, [rbp+arg_0]; struct CAuthInfo **
0x180054c03  mov     rcx, rbx; this
0x180054c06  call    ?Next@CAuthInfoListIter@@QEAAJPEAPEAVCAuthInfo@@@Z; CAuthInfoListIter::Next(CAuthInfo * *)
0x180054c0b  mov     edi, eax
0x180054c0d  test    eax, eax
0x180054c0f  jz      loc_180054AC4
0x180054c15  mov     rcx, rbx; this
0x180054c18  call    ??1CAuthInfoListIter@@QEAA@XZ; CAuthInfoListIter::~CAuthInfoListIter(void)
0x180054c1d  mov     edx, 18h; unsigned __int64
0x180054c22  mov     rcx, rbx; void *
0x180054c25  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180054c2a  jmp     short loc_180054C31
0x180054c2c  mov     edi, 8007000Eh
0x180054c31  mov     eax, edi
0x180054c33  add     rsp, 78h
0x180054c37  pop     rdi
0x180054c38  pop     rsi
0x180054c39  pop     rbx
0x180054c3a  pop     rbp
0x180054c3b  retn
```
