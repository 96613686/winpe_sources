# DllGetClassObject

- ea: `0x180007870`
- end: `0x1800079c8`
- name: `DllGetClassObject`
- size: `344`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007870`
- `0x1800093c0`
- `0x18001b10c`
- `0x180049010`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180007954`
- `RPCRT4!NdrDllGetClassObject` at `0x180007954`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007963`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007963`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007975`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007975`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  __int64 v6; // rcx
  int ClassObject; // edi
  __int64 v8; // rbx
  __int64 *v9; // r14
  const PCInterfaceStubVtblList *pStubVtblList; // rcx
  const CLSID *pclsid; // rcx

  InitOleacc();
  if ( ppv )
  {
    *ppv = 0;
    ClassObject = 0;
    v8 = qword_1800619B8;
    if ( qword_1800619B8 )
    {
      while ( 1 )
      {
        v6 = *(_QWORD *)v8;
        if ( !*(_QWORD *)v8 )
          break;
        if ( *(_QWORD *)(v8 + 16)
          && rclsid->Data1 == *(_DWORD *)v6
          && *(_DWORD *)&rclsid->Data2 == *(_DWORD *)(v6 + 4)
          && *(_DWORD *)rclsid->Data4 == *(_DWORD *)(v6 + 8)
          && *(_DWORD *)&rclsid->Data4[4] == *(_DWORD *)(v6 + 12) )
        {
          v9 = (__int64 *)(v8 + 32);
          if ( !*(_QWORD *)(v8 + 32) )
          {
            EnterCriticalSection(&CriticalSection);
            if ( !*v9 )
              ClassObject = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v8 + 16))(
                              *(_QWORD *)(v8 + 24),
                              &GUID_00000000_0000_0000_c000_000000000046,
                              v8 + 32);
            LeaveCriticalSection(&CriticalSection);
          }
          v6 = *v9;
          if ( *v9 )
            ClassObject = (**(__int64 (__fastcall ***)(__int64, const IID *const, LPVOID *))v6)(v6, riid, ppv);
          break;
        }
        v8 += 72;
      }
    }
    if ( !*ppv && !ClassObject )
      ClassObject = ATL::AtlComModuleGetClassObject((struct ATL::_ATL_COM_MODULE70 *)v6, rclsid, riid, ppv);
  }
  else
  {
    ClassObject = -2147467261;
  }
  if ( !ClassObject )
    return 0;
  pStubVtblList = aProxyFileList->pStubVtblList;
  if ( *pStubVtblList )
    pclsid = **(const CLSID ***)pStubVtblList;
  else
    pclsid = 0;
  return NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory);
}

```

## disassembly

```asm
0x180007870  push    rbx
0x180007872  push    rbp
0x180007873  push    rsi
0x180007874  push    rdi
0x180007875  push    r14
0x180007877  push    r15
0x180007879  sub     rsp, 38h
0x18000787d  mov     rsi, r8
0x180007880  mov     r15, rdx
0x180007883  mov     rbp, rcx
0x180007886  call    ?InitOleacc@@YAHXZ; InitOleacc(void)
0x18000788b  nop
0x18000788c  test    rsi, rsi
0x18000788f  jz      loc_180007985
0x180007895  mov     qword ptr [rsi], 0
0x18000789c  xor     edi, edi
0x18000789e  mov     rbx, cs:qword_1800619B8
0x1800078a5  test    rbx, rbx
0x1800078a8  jz      short loc_180007901
0x1800078aa  mov     rcx, [rbx]
0x1800078ad  test    rcx, rcx
0x1800078b0  jz      short loc_180007901
0x1800078b2  cmp     [rbx+10h], rdi
0x1800078b6  jz      short loc_1800078BF
0x1800078b8  mov     eax, [rcx]
0x1800078ba  cmp     [rbp+0], eax
0x1800078bd  jz      short loc_1800078C5
0x1800078bf  add     rbx, 48h ; 'H'
0x1800078c3  jmp     short loc_1800078AA
0x1800078c5  mov     eax, [rcx+4]
0x1800078c8  cmp     [rbp+4], eax
0x1800078cb  jnz     short loc_1800078BF
0x1800078cd  mov     eax, [rcx+8]
0x1800078d0  cmp     [rbp+8], eax
0x1800078d3  jnz     short loc_1800078BF
0x1800078d5  mov     eax, [rcx+0Ch]
0x1800078d8  cmp     [rbp+0Ch], eax
0x1800078db  jnz     short loc_1800078BF
0x1800078dd  lea     r14, [rbx+20h]
0x1800078e1  cmp     [r14], rdi
0x1800078e4  jz      short loc_18000795C
0x1800078e6  mov     rcx, [r14]
0x1800078e9  test    rcx, rcx
0x1800078ec  jz      short loc_180007901
0x1800078ee  mov     rax, [rcx]
0x1800078f1  mov     r8, rsi
0x1800078f4  mov     rdx, r15
0x1800078f7  mov     rax, [rax]
0x1800078fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078ff  mov     edi, eax
0x180007901  cmp     qword ptr [rsi], 0
0x180007905  jz      loc_1800079AA
0x18000790b  test    edi, edi
0x18000790d  jnz     short loc_18000791E
0x18000790f  xor     eax, eax
0x180007911  add     rsp, 38h
0x180007915  pop     r15
0x180007917  pop     r14
0x180007919  pop     rdi
0x18000791a  pop     rsi
0x18000791b  pop     rbp
0x18000791c  pop     rbx
0x18000791d  retn
0x18000791e  mov     rax, cs:aProxyFileList
0x180007925  mov     rcx, [rax+8]
0x180007929  mov     rax, [rcx]
0x18000792c  test    rax, rax
0x18000792f  jnz     short loc_180007980
0x180007931  xor     ecx, ecx
0x180007933  lea     rax, gPFactory
0x18000793a  mov     [rsp+68h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x18000793f  mov     [rsp+68h+pclsid], rcx; pclsid
0x180007944  lea     r9, aProxyFileList; pProxyFileList
0x18000794b  mov     r8, rsi; ppv
0x18000794e  mov     rdx, r15; riid
0x180007951  mov     rcx, rbp; rclsid
0x180007954  call    cs:__imp_NdrDllGetClassObject
0x18000795a  jmp     short loc_180007911
0x18000795c  lea     rcx, CriticalSection; lpCriticalSection
0x180007963  call    cs:__imp_EnterCriticalSection
0x180007969  cmp     [r14], rdi
0x18000796c  jz      short loc_18000798F
0x18000796e  lea     rcx, CriticalSection; lpCriticalSection
0x180007975  call    cs:__imp_LeaveCriticalSection
0x18000797b  jmp     loc_1800078E6
0x180007980  mov     rcx, [rax]
0x180007983  jmp     short loc_180007933
0x180007985  mov     edi, 80004003h
0x18000798a  jmp     loc_18000790B
0x18000798f  mov     r8, r14
0x180007992  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180007999  mov     rcx, [rbx+18h]
0x18000799d  mov     rax, [rbx+10h]
0x1800079a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079a6  mov     edi, eax
0x1800079a8  jmp     short loc_18000796E
0x1800079aa  test    edi, edi
0x1800079ac  jnz     loc_18000790B
0x1800079b2  mov     r9, rsi; void **
0x1800079b5  mov     r8, r15; struct _GUID *
0x1800079b8  mov     rdx, rbp; struct _GUID *
0x1800079bb  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x1800079c0  mov     edi, eax
0x1800079c2  jmp     loc_18000790B
```
