# DllGetClassObject

- ea: `0x180018770`
- end: `0x1800188c8`
- name: `DllGetClassObject`
- size: `344`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180018770`
- `0x18002cc70`
- `0x180062010`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x1800188b5`
- `RPCRT4!NdrDllGetClassObject` at `0x1800188b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001881c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001881c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018834`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018834`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const IID *v5; // rbp
  HRESULT ClassObject; // ebx
  __int64 v7; // rdi
  const IID *const *v8; // r14
  const PCInterfaceStubVtblList *pStubVtblList; // rcx
  const CLSID *pclsid; // rcx

  v5 = rclsid;
  if ( ppv )
  {
    *ppv = 0;
    ClassObject = 0;
    v7 = qword_18009BFC8;
    if ( qword_18009BFC8 )
    {
      while ( 1 )
      {
        rclsid = *(const IID *const *)v7;
        if ( !*(_QWORD *)v7 )
          break;
        if ( *(_QWORD *)(v7 + 16)
          && v5->Data1 == rclsid->Data1
          && *(_DWORD *)&v5->Data2 == *(_DWORD *)&rclsid->Data2
          && *(_DWORD *)v5->Data4 == *(_DWORD *)rclsid->Data4
          && *(_DWORD *)&v5->Data4[4] == *(_DWORD *)&rclsid->Data4[4] )
        {
          v8 = (const IID *const *)(v7 + 32);
          if ( !*(_QWORD *)(v7 + 32) )
          {
            EnterCriticalSection(&stru_18009C050);
            if ( !*v8 )
              ClassObject = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v7 + 16))(
                              *(_QWORD *)(v7 + 24),
                              &GUID_00000000_0000_0000_c000_000000000046,
                              v7 + 32);
            LeaveCriticalSection(&stru_18009C050);
          }
          rclsid = *v8;
          if ( *v8 )
            ClassObject = (**(__int64 (__fastcall ***)(const IID *const, const IID *const, LPVOID *))&rclsid->Data1)(
                            rclsid,
                            riid,
                            ppv);
          break;
        }
        v7 += 72;
      }
    }
    if ( !*ppv && !ClassObject )
      ClassObject = ATL::AtlComModuleGetClassObject((struct ATL::_ATL_COM_MODULE70 *)rclsid, v5, riid, ppv);
  }
  else
  {
    ClassObject = -2147467261;
  }
  if ( ClassObject < 0 )
  {
    pStubVtblList = aProxyFileList->pStubVtblList;
    if ( *pStubVtblList )
      pclsid = **(const CLSID ***)pStubVtblList;
    else
      pclsid = 0;
    return NdrDllGetClassObject(v5, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory);
  }
  return ClassObject;
}

```

## disassembly

```asm
0x180018770  push    rbx
0x180018772  push    rbp
0x180018773  push    rsi
0x180018774  push    rdi
0x180018775  push    r14
0x180018777  push    r15
0x180018779  sub     rsp, 38h
0x18001877d  mov     rsi, r8
0x180018780  mov     r15, rdx
0x180018783  mov     rbp, rcx
0x180018786  test    r8, r8
0x180018789  jz      loc_180018842
0x18001878f  mov     qword ptr [r8], 0
0x180018796  xor     ebx, ebx
0x180018798  mov     rdi, cs:qword_18009BFC8
0x18001879f  test    rdi, rdi
0x1800187a2  jz      short loc_1800187FB
0x1800187a4  mov     rcx, [rdi]
0x1800187a7  test    rcx, rcx
0x1800187aa  jz      short loc_1800187FB
0x1800187ac  cmp     [rdi+10h], rbx
0x1800187b0  jz      short loc_1800187B9
0x1800187b2  mov     eax, [rcx]
0x1800187b4  cmp     [rbp+0], eax
0x1800187b7  jz      short loc_1800187BF
0x1800187b9  add     rdi, 48h ; 'H'
0x1800187bd  jmp     short loc_1800187A4
0x1800187bf  mov     eax, [rcx+4]
0x1800187c2  cmp     [rbp+4], eax
0x1800187c5  jnz     short loc_1800187B9
0x1800187c7  mov     eax, [rcx+8]
0x1800187ca  cmp     [rbp+8], eax
0x1800187cd  jnz     short loc_1800187B9
0x1800187cf  mov     eax, [rcx+0Ch]
0x1800187d2  cmp     [rbp+0Ch], eax
0x1800187d5  jnz     short loc_1800187B9
0x1800187d7  lea     r14, [rdi+20h]
0x1800187db  cmp     [r14], rbx
0x1800187de  jz      short loc_180018815
0x1800187e0  mov     rcx, [r14]
0x1800187e3  test    rcx, rcx
0x1800187e6  jz      short loc_1800187FB
0x1800187e8  mov     rax, [rcx]
0x1800187eb  mov     r8, rsi
0x1800187ee  mov     rdx, r15
0x1800187f1  mov     rax, [rax]
0x1800187f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187f9  mov     ebx, eax
0x1800187fb  cmp     qword ptr [rsi], 0
0x1800187ff  jz      short loc_180018864
0x180018801  test    ebx, ebx
0x180018803  js      short loc_18001887A
0x180018805  mov     eax, ebx
0x180018807  add     rsp, 38h
0x18001880b  pop     r15
0x18001880d  pop     r14
0x18001880f  pop     rdi
0x180018810  pop     rsi
0x180018811  pop     rbp
0x180018812  pop     rbx
0x180018813  retn
0x180018815  lea     rcx, stru_18009C050; lpCriticalSection
0x18001881c  call    cs:__imp_EnterCriticalSection
0x180018823  nop     dword ptr [rax+rax+00h]
0x180018828  cmp     [r14], rbx
0x18001882b  jz      short loc_180018849
0x18001882d  lea     rcx, stru_18009C050; lpCriticalSection
0x180018834  call    cs:__imp_LeaveCriticalSection
0x18001883b  nop     dword ptr [rax+rax+00h]
0x180018840  jmp     short loc_1800187E0
0x180018842  mov     ebx, 80004003h
0x180018847  jmp     short loc_180018801
0x180018849  mov     r8, r14
0x18001884c  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180018853  mov     rcx, [rdi+18h]
0x180018857  mov     rax, [rdi+10h]
0x18001885b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018860  mov     ebx, eax
0x180018862  jmp     short loc_18001882D
0x180018864  test    ebx, ebx
0x180018866  jnz     short loc_180018801
0x180018868  mov     r9, rsi; void **
0x18001886b  mov     r8, r15; struct _GUID *
0x18001886e  mov     rdx, rbp; struct _GUID *
0x180018871  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x180018876  mov     ebx, eax
0x180018878  jmp     short loc_180018801
0x18001887a  mov     rax, cs:aProxyFileList
0x180018881  mov     rcx, [rax+8]
0x180018885  mov     rax, [rcx]
0x180018888  test    rax, rax
0x18001888b  jz      short loc_180018892
0x18001888d  mov     rcx, [rax]
0x180018890  jmp     short loc_180018894
0x180018892  xor     ecx, ecx
0x180018894  lea     rax, gPFactory
0x18001889b  mov     [rsp+68h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x1800188a0  mov     [rsp+68h+pclsid], rcx; pclsid
0x1800188a5  lea     r9, aProxyFileList; pProxyFileList
0x1800188ac  mov     r8, rsi; ppv
0x1800188af  mov     rdx, r15; riid
0x1800188b2  mov     rcx, rbp; rclsid
0x1800188b5  call    cs:__imp_NdrDllGetClassObject
0x1800188bc  nop     dword ptr [rax+rax+00h]
0x1800188c1  mov     ebx, eax
0x1800188c3  jmp     loc_180018805
```
