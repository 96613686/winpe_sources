# DllGetClassObject

- ea: `0x18000b7b0`
- end: `0x18000b8e9`
- name: `DllGetClassObject`
- size: `313`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180004948`
- `0x18000b7b0`
- `0x180019010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000b82d`
- `KERNEL32!EnterCriticalSection` at `0x18000b82d`
- `KERNEL32!LeaveCriticalSection` at `0x18000b858`
- `KERNEL32!LeaveCriticalSection` at `0x18000b858`
- `RPCRT4!NdrDllGetClassObject` at `0x18000b8d2`
- `RPCRT4!NdrDllGetClassObject` at `0x18000b8d2`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const IID *v5; // rbp
  HRESULT ClassObject; // edi
  __int64 v7; // rbx
  const IID *const *v8; // r14
  bool v9; // sf
  const PCInterfaceStubVtblList *pStubVtblList; // rcx
  const CLSID *pclsid; // rcx

  v5 = rclsid;
  if ( ppv )
  {
    *ppv = 0;
    ClassObject = 0;
    v7 = qword_180021C48;
    if ( qword_180021C48 )
    {
      while ( *(_QWORD *)v7 )
      {
        if ( *(_QWORD *)(v7 + 16) )
        {
          rclsid = *(const IID *const *)v7;
          if ( v5->Data1 == **(_DWORD **)v7
            && *(_DWORD *)&v5->Data2 == *(_DWORD *)&rclsid->Data2
            && *(_DWORD *)v5->Data4 == *(_DWORD *)rclsid->Data4
            && *(_DWORD *)&v5->Data4[4] == *(_DWORD *)&rclsid->Data4[4] )
          {
            v8 = (const IID *const *)(v7 + 32);
            if ( !*(_QWORD *)(v7 + 32) )
            {
              EnterCriticalSection(&stru_1800212B0);
              if ( !*v8 )
                ClassObject = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v7 + 16))(
                                *(_QWORD *)(v7 + 24),
                                &GUID_00000000_0000_0000_c000_000000000046,
                                v7 + 32);
              LeaveCriticalSection(&stru_1800212B0);
            }
            rclsid = *v8;
            if ( *v8 )
              ClassObject = (**(__int64 (__fastcall ***)(const IID *const, const IID *const, LPVOID *))&rclsid->Data1)(
                              rclsid,
                              riid,
                              ppv);
            break;
          }
        }
        v7 += 72;
      }
    }
    if ( !*ppv )
    {
      v9 = ClassObject < 0;
      if ( ClassObject )
        goto LABEL_22;
      ClassObject = ATL::AtlComModuleGetClassObject((struct ATL::_ATL_COM_MODULE70 *)rclsid, v5, riid, ppv);
    }
    v9 = ClassObject < 0;
LABEL_22:
    if ( !v9 )
      return ClassObject;
  }
  pStubVtblList = aProxyFileList->pStubVtblList;
  if ( *pStubVtblList )
    pclsid = **(const CLSID ***)pStubVtblList;
  else
    pclsid = 0;
  return NdrDllGetClassObject(v5, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory);
}

```

## disassembly

```asm
0x18000b7b0  push    rbx
0x18000b7b2  push    rbp
0x18000b7b3  push    rsi
0x18000b7b4  push    rdi
0x18000b7b5  push    r14
0x18000b7b7  push    r15
0x18000b7b9  sub     rsp, 38h
0x18000b7bd  mov     rsi, r8
0x18000b7c0  mov     r15, rdx
0x18000b7c3  mov     rbp, rcx
0x18000b7c6  test    r8, r8
0x18000b7c9  jz      loc_18000B897
0x18000b7cf  mov     qword ptr [r8], 0
0x18000b7d6  xor     edi, edi
0x18000b7d8  mov     rbx, cs:qword_180021C48
0x18000b7df  test    rbx, rbx
0x18000b7e2  jz      loc_18000B879
0x18000b7e8  jmp     short loc_18000B816
0x18000b7ea  cmp     [rbx+10h], rdi
0x18000b7ee  jz      short loc_18000B812
0x18000b7f0  mov     rcx, [rbx]
0x18000b7f3  mov     eax, [rcx]
0x18000b7f5  cmp     [rbp+0], eax
0x18000b7f8  jnz     short loc_18000B812
0x18000b7fa  mov     eax, [rcx+4]
0x18000b7fd  cmp     [rbp+4], eax
0x18000b800  jnz     short loc_18000B812
0x18000b802  mov     eax, [rcx+8]
0x18000b805  cmp     [rbp+8], eax
0x18000b808  jnz     short loc_18000B812
0x18000b80a  mov     eax, [rcx+0Ch]
0x18000b80d  cmp     [rbp+0Ch], eax
0x18000b810  jz      short loc_18000B81D
0x18000b812  add     rbx, 48h ; 'H'
0x18000b816  cmp     [rbx], rdi
0x18000b819  jnz     short loc_18000B7EA
0x18000b81b  jmp     short loc_18000B879
0x18000b81d  lea     r14, [rbx+20h]
0x18000b821  cmp     [r14], rdi
0x18000b824  jnz     short loc_18000B85E
0x18000b826  lea     rcx, stru_1800212B0; lpCriticalSection
0x18000b82d  call    cs:__imp_EnterCriticalSection
0x18000b833  cmp     [r14], rdi
0x18000b836  jnz     short loc_18000B851
0x18000b838  mov     rcx, [rbx+18h]
0x18000b83c  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000b843  mov     rax, [rbx+10h]
0x18000b847  mov     r8, r14
0x18000b84a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b84f  mov     edi, eax
0x18000b851  lea     rcx, stru_1800212B0; lpCriticalSection
0x18000b858  call    cs:__imp_LeaveCriticalSection
0x18000b85e  mov     rcx, [r14]
0x18000b861  test    rcx, rcx
0x18000b864  jz      short loc_18000B879
0x18000b866  mov     rax, [rcx]
0x18000b869  mov     r8, rsi
0x18000b86c  mov     rdx, r15
0x18000b86f  mov     rax, [rax]
0x18000b872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b877  mov     edi, eax
0x18000b879  cmp     qword ptr [rsi], 0
0x18000b87d  jnz     short loc_18000B893
0x18000b87f  test    edi, edi
0x18000b881  jnz     short loc_18000B895
0x18000b883  mov     r9, rsi; void **
0x18000b886  mov     r8, r15; struct _GUID *
0x18000b889  mov     rdx, rbp; struct _GUID *
0x18000b88c  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x18000b891  mov     edi, eax
0x18000b893  test    edi, edi
0x18000b895  jns     short loc_18000B8DA
0x18000b897  mov     rax, cs:aProxyFileList
0x18000b89e  mov     rcx, [rax+8]
0x18000b8a2  mov     rax, [rcx]
0x18000b8a5  test    rax, rax
0x18000b8a8  jz      short loc_18000B8AF
0x18000b8aa  mov     rcx, [rax]
0x18000b8ad  jmp     short loc_18000B8B1
0x18000b8af  xor     ecx, ecx
0x18000b8b1  lea     rax, gPFactory
0x18000b8b8  mov     r8, rsi; ppv
0x18000b8bb  mov     [rsp+68h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x18000b8c0  lea     r9, aProxyFileList; pProxyFileList
0x18000b8c7  mov     [rsp+68h+pclsid], rcx; pclsid
0x18000b8cc  mov     rdx, r15; riid
0x18000b8cf  mov     rcx, rbp; rclsid
0x18000b8d2  call    cs:__imp_NdrDllGetClassObject
0x18000b8d8  mov     edi, eax
0x18000b8da  mov     eax, edi
0x18000b8dc  add     rsp, 38h
0x18000b8e0  pop     r15
0x18000b8e2  pop     r14
0x18000b8e4  pop     rdi
0x18000b8e5  pop     rsi
0x18000b8e6  pop     rbp
0x18000b8e7  pop     rbx
0x18000b8e8  retn
```
