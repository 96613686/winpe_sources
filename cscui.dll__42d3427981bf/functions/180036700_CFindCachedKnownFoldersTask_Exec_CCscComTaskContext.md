# CFindCachedKnownFoldersTask::_Exec(CCscComTaskContext *)

- ea: `0x180036700`
- end: `0x18003690e`
- name: `?_Exec@CFindCachedKnownFoldersTask@@EEAAJPEAVCCscComTaskContext@@@Z`
- size: `526`
- prototype: `int(CFindCachedKnownFoldersTask *__hidden this, struct CCscComTaskContext *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003c20`
- `0x180005190`
- `0x180006020`
- `0x180027b90`
- `0x180036700`
- `0x18004d010`

## import_xrefs

- `SHLWAPI!PathIsUNCW` at `0x180036839`
- `SHLWAPI!PathIsUNCW` at `0x180036839`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003688c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800368d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003688c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800368d9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003676a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003676a`

## pseudocode

```c
__int64 __fastcall CFindCachedKnownFoldersTask::_Exec(CFindCachedKnownFoldersTask *this, struct CCscComTaskContext *a2)
{
  HRESULT CscCacheObject; // ebx
  unsigned int *v4; // rsi
  unsigned __int64 v5; // rcx
  void *v6; // r9
  unsigned int v7; // r14d
  void *v8; // rdx
  void *v10; // [rsp+30h] [rbp-10h] BYREF
  __int64 v11; // [rsp+38h] [rbp-8h] BYREF
  LPCWSTR pszPath; // [rsp+88h] [rbp+48h] BYREF
  LPVOID ppv; // [rsp+90h] [rbp+50h] BYREF
  __int64 i; // [rsp+98h] [rbp+58h] BYREF

  CscCacheObject = -2147467259;
  if ( !a2 )
    goto LABEL_18;
  v10 = 0;
  CscCacheObject = CCscComTaskContext::GetCscCacheObject(a2, (const struct _GUID *)a2, &v10);
  if ( CscCacheObject < 0 )
    goto LABEL_18;
  ppv = 0;
  CscCacheObject = CoCreateInstance(&CLSID_KnownFolderManager, 0, 1u, &GUID_8be2d872_86aa_4d47_b776_32cca40c7018, &ppv);
  if ( CscCacheObject >= 0 )
  {
    v4 = (unsigned int *)((char *)this + 32);
    CscCacheObject = (*(__int64 (__fastcall **)(LPVOID, char *, char *))(*(_QWORD *)ppv + 40LL))(
                       ppv,
                       (char *)this + 16,
                       (char *)this + 32);
    if ( CscCacheObject >= 0 )
    {
      v5 = *v4;
      *((_QWORD *)this + 3) = 0;
      pszPath = 0;
      CscCacheObject = ULongLongMult(v5, 4u, (unsigned __int64 *)&pszPath);
      if ( CscCacheObject >= 0 )
        CscCacheObject = CscUtil_HeapAlloc((SIZE_T)pszPath, 1, (void **)this + 3, v6);
      if ( CscCacheObject >= 0 )
      {
        v7 = 0;
        for ( i = 0; v7 < *v4; ++v7 )
        {
          if ( (*(unsigned int (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 48LL))(
                 ppv,
                 *((_QWORD *)this + 2) + 16LL * v7,
                 &i) )
          {
            break;
          }
          pszPath = 0;
          if ( (*(int (__fastcall **)(__int64, _QWORD, LPCWSTR *))(*(_QWORD *)i + 48LL))(i, 0, &pszPath) >= 0 )
          {
            if ( PathIsUNCW(pszPath) )
            {
              v11 = 0;
              if ( (*(int (__fastcall **)(void *, LPCWSTR, __int64, __int64 *))(*(_QWORD *)v10 + 80LL))(
                     v10,
                     pszPath,
                     16,
                     &v11) >= 0 )
              {
                *(_DWORD *)(*((_QWORD *)this + 3) + 4LL * v7) = 1;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
              }
            }
            CoTaskMemFree((LPVOID)pszPath);
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)i + 16LL))(i);
        }
      }
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  (*(void (__fastcall **)(void *))(*(_QWORD *)v10 + 16LL))(v10);
  if ( CscCacheObject < 0 )
  {
LABEL_18:
    CoTaskMemFree(*((LPVOID *)this + 2));
    CscUtil_HeapFree(*((void **)this + 3), v8);
    *((_QWORD *)this + 2) = 0;
    *((_QWORD *)this + 3) = 0;
    *((_DWORD *)this + 8) = 0;
  }
  return (unsigned int)CscCacheObject;
}

```

## disassembly

```asm
0x180036700  mov     [rsp-38h+arg_0], rbx
0x180036705  push    rbp
0x180036706  push    rsi
0x180036707  push    rdi
0x180036708  push    r12
0x18003670a  push    r13
0x18003670c  push    r14
0x18003670e  push    r15
0x180036710  mov     rbp, rsp
0x180036713  sub     rsp, 40h
0x180036717  xor     r12d, r12d
0x18003671a  mov     rdi, rcx
0x18003671d  mov     ebx, 80004005h
0x180036722  test    rdx, rdx
0x180036725  jz      loc_1800368D5
0x18003672b  lea     r8, [rbp+var_10]; void **
0x18003672f  mov     [rbp+var_10], r12
0x180036733  mov     rcx, rdx; this
0x180036736  call    ?GetCscCacheObject@CCscComTaskContext@@QEAAJAEBU_GUID@@PEAPEAX@Z; CCscComTaskContext::GetCscCacheObject(_GUID const &,void * *)
0x18003673b  mov     ebx, eax
0x18003673d  test    eax, eax
0x18003673f  js      loc_1800368D5
0x180036745  lea     rax, [rbp+arg_10]
0x180036749  mov     [rbp+arg_10], r12
0x18003674d  lea     r14d, [r12+1]
0x180036752  mov     [rsp+40h+ppv], rax; ppv
0x180036757  mov     r8d, r14d; dwClsContext
0x18003675a  lea     r9, _GUID_8be2d872_86aa_4d47_b776_32cca40c7018; riid
0x180036761  xor     edx, edx; pUnkOuter
0x180036763  lea     rcx, CLSID_KnownFolderManager; rclsid
0x18003676a  call    cs:__imp_CoCreateInstance
0x180036770  mov     ebx, eax
0x180036772  test    eax, eax
0x180036774  js      loc_1800368C1
0x18003677a  mov     rcx, [rbp+arg_10]
0x18003677e  lea     rsi, [rdi+20h]
0x180036782  mov     r8, rsi
0x180036785  lea     rdx, [rdi+10h]
0x180036789  mov     rax, [rcx]
0x18003678c  mov     rax, [rax+28h]
0x180036790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036795  mov     ebx, eax
0x180036797  test    eax, eax
0x180036799  js      loc_1800368B1
0x18003679f  mov     ecx, [rsi]; unsigned __int64
0x1800367a1  lea     r15, [rdi+18h]
0x1800367a5  lea     r8, [rbp+pszPath]; unsigned __int64 *
0x1800367a9  mov     [r15], r12
0x1800367ac  lea     edx, [r12+4]; unsigned __int64
0x1800367b1  mov     [rbp+pszPath], r12
0x1800367b5  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800367ba  mov     ebx, eax
0x1800367bc  test    eax, eax
0x1800367be  js      short loc_1800367D1
0x1800367c0  mov     rcx, [rbp+pszPath]; dwBytes
0x1800367c4  mov     r8, r15; void **
0x1800367c7  mov     edx, r14d; int
0x1800367ca  call    ?CscUtil_HeapAlloc@@YAJ_KHPEAPEAXPEAX@Z; CscUtil_HeapAlloc(unsigned __int64,int,void * *,void *)
0x1800367cf  mov     ebx, eax
0x1800367d1  test    ebx, ebx
0x1800367d3  js      loc_1800368B1
0x1800367d9  mov     r14d, r12d
0x1800367dc  mov     [rbp+arg_18], r12
0x1800367e0  cmp     [rsi], r12d
0x1800367e3  jbe     loc_1800368B1
0x1800367e9  mov     rcx, [rbp+arg_10]
0x1800367ed  lea     r8, [rbp+arg_18]
0x1800367f1  mov     edx, r14d
0x1800367f4  shl     rdx, 4
0x1800367f8  add     rdx, [rdi+10h]
0x1800367fc  mov     rax, [rcx]
0x1800367ff  mov     r12d, r14d
0x180036802  mov     rax, [rax+30h]
0x180036806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003680b  test    eax, eax
0x18003680d  jnz     loc_1800368AE
0x180036813  mov     rcx, [rbp+arg_18]
0x180036817  lea     r8, [rbp+pszPath]
0x18003681b  mov     [rbp+pszPath], 0
0x180036823  xor     edx, edx
0x180036825  mov     rax, [rcx]
0x180036828  mov     rax, [rax+30h]
0x18003682c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036831  test    eax, eax
0x180036833  js      short loc_180036892
0x180036835  mov     rcx, [rbp+pszPath]; pszPath
0x180036839  call    cs:__imp_PathIsUNCW
0x18003683f  test    eax, eax
0x180036841  jz      short loc_180036888
0x180036843  mov     rcx, [rbp+var_10]
0x180036847  lea     r9, [rbp+var_8]
0x18003684b  mov     rdx, [rbp+pszPath]
0x18003684f  mov     r8d, 10h
0x180036855  mov     [rbp+var_8], 0
0x18003685d  mov     rax, [rcx]
0x180036860  mov     rax, [rax+50h]
0x180036864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036869  test    eax, eax
0x18003686b  js      short loc_180036888
0x18003686d  mov     rax, [r15]
0x180036870  mov     dword ptr [rax+r12*4], 1
0x180036878  mov     rcx, [rbp+var_8]
0x18003687c  mov     rax, [rcx]
0x18003687f  mov     rax, [rax+10h]
0x180036883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036888  mov     rcx, [rbp+pszPath]; pv
0x18003688c  call    cs:__imp_CoTaskMemFree
0x180036892  mov     rcx, [rbp+arg_18]
0x180036896  mov     rax, [rcx]
0x180036899  mov     rax, [rax+10h]
0x18003689d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800368a2  inc     r14d
0x1800368a5  cmp     r14d, [rsi]
0x1800368a8  jb      loc_1800367E9
0x1800368ae  xor     r12d, r12d
0x1800368b1  mov     rcx, [rbp+arg_10]
0x1800368b5  mov     rax, [rcx]
0x1800368b8  mov     rax, [rax+10h]
0x1800368bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800368c1  mov     rcx, [rbp+var_10]
0x1800368c5  mov     rax, [rcx]
0x1800368c8  mov     rax, [rax+10h]
0x1800368cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800368d1  test    ebx, ebx
0x1800368d3  jns     short loc_1800368F4
0x1800368d5  mov     rcx, [rdi+10h]; pv
0x1800368d9  call    cs:__imp_CoTaskMemFree
0x1800368df  mov     rcx, [rdi+18h]; lpMem
0x1800368e3  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x1800368e8  mov     [rdi+10h], r12
0x1800368ec  mov     [rdi+18h], r12
0x1800368f0  mov     [rdi+20h], r12d
0x1800368f4  mov     eax, ebx
0x1800368f6  mov     rbx, [rsp+40h+arg_0]
0x1800368fe  add     rsp, 40h
0x180036902  pop     r15
0x180036904  pop     r14
0x180036906  pop     r13
0x180036908  pop     r12
0x18003690a  pop     rdi
0x18003690b  pop     rsi
0x18003690c  pop     rbp
0x18003690d  retn
```
