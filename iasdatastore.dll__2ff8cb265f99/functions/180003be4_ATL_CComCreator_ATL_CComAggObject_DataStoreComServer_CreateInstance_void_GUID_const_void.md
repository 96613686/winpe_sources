# ATL::CComCreator<ATL::CComAggObject<DataStoreComServer>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003be4`
- end: `0x180003d11`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VDataStoreComServer@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180003bd0`

## callees

- `0x180002310`
- `0x180003be4`
- `0x18000433c`
- `0x1800067a8`
- `0x180010010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<DataStoreComServer>>::CreateInstance(
        ULONG_PTR a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r15
  unsigned int v7; // edi
  struct _RTL_CRITICAL_SECTION *v8; // rax
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  int v10; // ecx
  int v11; // eax
  int v12; // ecx
  struct _RTL_CRITICAL_SECTION *v13; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = (struct _RTL_CRITICAL_SECTION *)operator new(0x68u);
    v9 = v8;
    if ( v8 )
    {
      v8->LockCount = 0;
      v8->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&ATL::CComAggObject<DataStoreComServer>::`vftable';
      DataStoreComServer::DataStoreComServer((DataStoreComServer *)&v8->LockSemaphore);
      v9->LockSemaphore = &ATL::CComContainedObject<DataStoreComServer>::`vftable';
      v9->SpinCount = a1;
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v13 = v9;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v7 = -2147024882;
    v9 = v13;
  }
  if ( v9 )
  {
    v10 = ATL::CComCriticalSection::Init(v9 + 1);
    if ( v10 >= 0 )
      LOBYTE(v9[2].DebugInfo) = 1;
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    v12 = 0;
    if ( v11 < 0 )
      v12 = v11;
    v7 = 0;
    if ( v12 < 0 )
      v7 = v12;
    if ( v7
      || (v7 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *, __int64, _QWORD *))v9->DebugInfo->Type)(
                 v9,
                 v4,
                 v3)) != 0 )
    {
      ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *, __int64))v9->DebugInfo->ProcessLocksList.Blink)(v9, 1);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180003be4  mov     [rsp+arg_0], rbx
0x180003be9  mov     [rsp+arg_10], r8
0x180003bee  mov     [rsp+arg_8], rdx
0x180003bf3  push    rsi
0x180003bf4  push    rdi
0x180003bf5  push    r12
0x180003bf7  push    r14
0x180003bf9  push    r15
0x180003bfb  sub     rsp, 30h
0x180003bff  mov     rsi, r8
0x180003c02  mov     r15, rdx
0x180003c05  mov     r12, rcx
0x180003c08  test    r8, r8
0x180003c0b  jnz     short loc_180003C17
0x180003c0d  mov     eax, 80004003h
0x180003c12  jmp     loc_180003CFF
0x180003c17  mov     qword ptr [r8], 0
0x180003c1e  mov     edi, 8007000Eh
0x180003c23  mov     [rsp+58h+arg_18], edi
0x180003c27  mov     [rsp+58h+var_38], 0
0x180003c30  mov     ecx, 68h ; 'h'; Size
0x180003c35  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003c3a  mov     rbx, rax
0x180003c3d  mov     [rsp+58h+var_30], rax
0x180003c42  test    rbx, rbx
0x180003c45  jz      short loc_180003C84
0x180003c47  mov     dword ptr [rax+8], 0
0x180003c4e  lea     rax, ??_7?$CComAggObject@VDataStoreComServer@@@ATL@@6B@; const ATL::CComAggObject<DataStoreComServer>::`vftable'
0x180003c55  mov     [rbx], rax
0x180003c58  lea     rcx, [rbx+18h]; this
0x180003c5c  call    ??0DataStoreComServer@@QEAA@XZ; DataStoreComServer::DataStoreComServer(void)
0x180003c61  lea     rax, ??_7?$CComContainedObject@VDataStoreComServer@@@ATL@@6B@; const ATL::CComContainedObject<DataStoreComServer>::`vftable'
0x180003c68  mov     [rbx+18h], rax
0x180003c6c  mov     [rbx+20h], r12
0x180003c70  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003c77  mov     rax, [rcx]
0x180003c7a  mov     rax, [rax+8]
0x180003c7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c83  nop
0x180003c84  mov     [rsp+58h+var_38], rbx
0x180003c89  jmp     short loc_180003C9E
0x180003c8b  mov     rsi, [rsp+58h+arg_10]
0x180003c90  mov     r15, [rsp+58h+arg_8]
0x180003c95  mov     edi, [rsp+58h+arg_18]
0x180003c99  mov     rbx, [rsp+58h+var_38]
0x180003c9e  test    rbx, rbx
0x180003ca1  jz      short loc_180003CFD
0x180003ca3  lea     rcx, [rbx+28h]; this
0x180003ca7  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180003cac  mov     ecx, eax
0x180003cae  test    eax, eax
0x180003cb0  js      short loc_180003CB6
0x180003cb2  mov     byte ptr [rbx+50h], 1
0x180003cb6  xor     eax, eax
0x180003cb8  test    ecx, ecx
0x180003cba  cmovs   eax, ecx
0x180003cbd  xor     ecx, ecx
0x180003cbf  test    eax, eax
0x180003cc1  cmovs   ecx, eax
0x180003cc4  xor     edi, edi
0x180003cc6  test    ecx, ecx
0x180003cc8  cmovs   edi, ecx
0x180003ccb  test    edi, edi
0x180003ccd  jnz     short loc_180003CE9
0x180003ccf  mov     rax, [rbx]
0x180003cd2  mov     r8, rsi
0x180003cd5  mov     rdx, r15
0x180003cd8  mov     rcx, rbx
0x180003cdb  mov     rax, [rax]
0x180003cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ce3  mov     edi, eax
0x180003ce5  test    eax, eax
0x180003ce7  jz      short loc_180003CFD
0x180003ce9  mov     r8, [rbx]
0x180003cec  mov     edx, 1
0x180003cf1  mov     rcx, rbx
0x180003cf4  mov     rax, [r8+18h]
0x180003cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cfd  mov     eax, edi
0x180003cff  mov     rbx, [rsp+58h+arg_0]
0x180003d04  add     rsp, 30h
0x180003d08  pop     r15
0x180003d0a  pop     r14
0x180003d0c  pop     r12
0x180003d0e  pop     rdi
0x180003d0f  pop     rsi
0x180003d10  retn
```
