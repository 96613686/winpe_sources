# EapLm::Peer::ThirdPartyDispatcherConfig::GetMethodProperties(ulong,ulong,_EAP_METHOD_TYPE *,__int64,ulong,uchar const *,ulong,uchar const *,_EAP_METHOD_PROPERTY_ARRAY *,_EAP_ERROR * *)

- ea: `0x18000db80`
- end: `0x18000dd3c`
- name: `?GetMethodProperties@ThirdPartyDispatcherConfig@Peer@EapLm@@UEAAJKKPEAU_EAP_METHOD_TYPE@@_JKPEBEK2PEAU_EAP_METHOD_PROPERTY_ARRAY@@PEAPEAU_EAP_ERROR@@@Z`
- size: `444`
- prototype: `__int64 __fastcall(EapLm::Peer::ThirdPartyDispatcherConfig *__hidden this, unsigned int, unsigned int, struct _EAP_METHOD_TYPE *, __int64, unsigned int, const unsigned __int8 *, unsigned int, const unsigned __int8 *, struct _EAP_METHOD_PROPERTY_ARRAY *, struct _EAP_ERROR **)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000cbc4`
- `0x18000ce00`
- `0x18000cf78`
- `0x18000db80`
- `0x180012a00`
- `0x180012c10`
- `0x180016e44`
- `0x180034010`

## string_xrefs

- `0x18000dcca`: `com_ref:Assign`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall EapLm::Peer::ThirdPartyDispatcherConfig::GetMethodProperties(
        EapLm::Peer::ThirdPartyDispatcherConfig *this,
        unsigned int a2,
        unsigned int a3,
        struct _EAP_METHOD_TYPE *a4,
        __int64 a5,
        unsigned int a6,
        const unsigned __int8 *a7,
        unsigned int a8,
        const unsigned __int8 *a9,
        struct _EAP_METHOD_PROPERTY_ARRAY *a10,
        struct _EAP_ERROR **a11)
{
  struct _EAP_METHOD_PROPERTY_ARRAY *v13; // rbx
  _QWORD *v15; // r10
  int *v16; // r9
  struct _EAP_METHOD_PROPERTY_ARRAY v17; // xmm1
  struct _EAP_ERROR *v18; // [rsp+40h] [rbp-88h] BYREF
  _BYTE v19[24]; // [rsp+48h] [rbp-80h] BYREF
  DWORD dwAuthorId; // [rsp+60h] [rbp-68h]
  __int128 v21; // [rsp+68h] [rbp-60h] BYREF
  _QWORD v22[2]; // [rsp+78h] [rbp-50h] BYREF
  _QWORD v23[2]; // [rsp+88h] [rbp-40h] BYREF
  const ATL::CAtlException *v24; // [rsp+98h] [rbp-30h] BYREF
  const EapHost::EapException *v25; // [rsp+A0h] [rbp-28h] BYREF
  const Exception *v26; // [rsp+A8h] [rbp-20h] BYREF
  const Exception *v27; // [rsp+B0h] [rbp-18h] BYREF

  LODWORD(v18) = 0;
  v21 = 0;
  v13 = a10;
  if ( a10 )
  {
    v15 = (_QWORD *)*((_QWORD *)this - 12);
    v19[8] = a4->eapType.type;
    *(_DWORD *)&v19[12] = a4->eapType.dwVendorId;
    *(_DWORD *)&v19[16] = a4->eapType.dwVendorType;
    if ( v19[8] != 0xFE )
      *(_QWORD *)&v19[12] = 0;
    try
    {
      *(_QWORD *)v19 = &EapHost::EapMethodType::`vftable';
      dwAuthorId = a4->dwAuthorId;
      EapLm::Peer::EapLibraryManagerConfig::GetEapMethodConfig(v15, (ReferenceCounted *)&a10, (__int64)v19);
      *(_QWORD *)v19 = &EapHost::EapType::`vftable';
      v23[1] = a6;
      v23[0] = a7;
      v22[1] = a8;
      v22[0] = a9;
      (*(void (__fastcall **)(struct _EAP_METHOD_PROPERTY_ARRAY *, _QWORD, _QWORD, __int64, _QWORD *, _QWORD *, __int128 *))(*(_QWORD *)&a10->dwNumberOfProperties + 120LL))(
        a10,
        a2,
        a3,
        a5,
        v23,
        v22,
        &v21);
      *(_OWORD *)v19 = 0;
      *(_QWORD *)&v19[16] = 1;
      if ( !Copy<TaskAllocator>((__int64)v19, (unsigned int *)&v21) )
      {
        try
        {
          LowMemoryError::Throw(L"com_ref:Assign");
        }
        catch ( const Exception *v27 )
        {
          Free<TaskAllocator>((__int64)v19);
          throw;
        }
      }
    }
    catch ( std::bad_alloc )
    {
      LODWORD(v18) = -2147024882;
      if ( a11 )
        *a11 = 0;
      goto LABEL_9;
    }
    catch ( const ATL::CAtlException *v24 )
    {
      LODWORD(v18) = *(_DWORD *)v24;
      if ( a11 )
        *a11 = 0;
      goto LABEL_9;
    }
    catch ( const EapHost::EapException *v25 )
    {
      EapHost::EapException2EapErrorOle(v25, (const struct EapHost::EapException *)a11, &v18, v16);
      goto LABEL_9;
    }
    catch ( const Exception *v26 )
    {
      EapHost::Exception2EapErrorOle(v26, (const struct Exception *)a11, &v18, v16);
      goto LABEL_9;
    }
    v17 = *(struct _EAP_METHOD_PROPERTY_ARRAY *)v19;
    *(_OWORD *)v19 = 0;
    *(_QWORD *)&v19[16] = 1;
    *v13 = v17;
    Free<TaskAllocator>((__int64)v19);
    if ( a10 )
      ReferenceCounted::Release((ReferenceCounted *)a10);
LABEL_9:
    Free<HeapAllocator>(&v21);
    return (unsigned int)v18;
  }
  else
  {
    Free<HeapAllocator>(&v21);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x18000db80  mov     rax, rsp
0x18000db83  mov     [rax+8], rbx
0x18000db87  mov     [rax+10h], rsi
0x18000db8b  push    rdi
0x18000db8c  sub     rsp, 0C0h
0x18000db93  mov     edi, r8d
0x18000db96  mov     esi, edx
0x18000db98  mov     dword ptr [rsp+0C8h+var_88], 0
0x18000dba0  xorps   xmm0, xmm0
0x18000dba3  movups  xmmword ptr [rax-60h], xmm0
0x18000dba7  mov     rbx, [rsp+0C8h+arg_48]
0x18000dbaf  test    rbx, rbx
0x18000dbb2  jnz     short loc_18000DBC7
0x18000dbb4  lea     rcx, [rax-60h]
0x18000dbb8  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_METHOD_PROPERTY_ARRAY@@@Z; Free<HeapAllocator>(_EAP_METHOD_PROPERTY_ARRAY &)
0x18000dbbd  mov     eax, 80004003h
0x18000dbc2  jmp     loc_18000DD27
0x18000dbc7  mov     r10, [rcx-60h]
0x18000dbcb  mov     cl, [r9]
0x18000dbce  mov     byte ptr [rsp+0C8h+var_80+8], cl
0x18000dbd2  mov     eax, [r9+4]
0x18000dbd6  mov     dword ptr [rsp+0C8h+var_80+0Ch], eax
0x18000dbda  mov     eax, [r9+8]
0x18000dbde  mov     dword ptr [rsp+0C8h+var_70], eax
0x18000dbe2  cmp     cl, 0FEh
0x18000dbe5  jz      short loc_18000DBF0
0x18000dbe7  mov     qword ptr [rsp+0C8h+var_80+0Ch], 0
0x18000dbf0  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18000dbf7  mov     qword ptr [rsp+0C8h+var_80], rax
0x18000dbfc  mov     eax, [r9+0Ch]
0x18000dc00  mov     [rsp+0C8h+var_68], eax
0x18000dc04  lea     r8, [rsp+0C8h+var_80]
0x18000dc09  lea     rdx, [rsp+0C8h+arg_48]
0x18000dc11  mov     rcx, r10
0x18000dc14  call    ?GetEapMethodConfig@EapLibraryManagerConfig@Peer@EapLm@@QEAA?AV?$SmartPointer@UIEapMethodConfig@Peer@EapLm@@@@AEBVEapMethodType@EapHost@@@Z; EapLm::Peer::EapLibraryManagerConfig::GetEapMethodConfig(EapHost::EapMethodType const &)
0x18000dc19  nop
0x18000dc1a  lea     rax, ??_7EapType@EapHost@@6B@; const EapHost::EapType::`vftable'
0x18000dc21  mov     qword ptr [rsp+0C8h+var_80], rax
0x18000dc26  mov     eax, [rsp+0C8h+arg_28]
0x18000dc2d  mov     [rsp+0C8h+var_38], rax
0x18000dc35  mov     rax, [rsp+0C8h+arg_30]
0x18000dc3d  mov     [rsp+0C8h+var_40], rax
0x18000dc45  mov     eax, [rsp+0C8h+arg_38]
0x18000dc4c  mov     [rsp+0C8h+var_48], rax
0x18000dc54  mov     rax, [rsp+0C8h+arg_40]
0x18000dc5c  mov     [rsp+0C8h+var_50], rax
0x18000dc61  mov     rcx, [rsp+0C8h+arg_48]
0x18000dc69  mov     rax, [rcx]
0x18000dc6c  lea     rdx, [rsp+0C8h+var_60]
0x18000dc71  mov     [rsp+0C8h+var_98], rdx
0x18000dc76  lea     rdx, [rsp+0C8h+var_50]
0x18000dc7b  mov     [rsp+0C8h+var_A0], rdx
0x18000dc80  lea     rdx, [rsp+0C8h+var_40]
0x18000dc88  mov     [rsp+0C8h+var_A8], rdx
0x18000dc8d  mov     r9, [rsp+0C8h+arg_20]
0x18000dc95  mov     r8d, edi
0x18000dc98  mov     edx, esi
0x18000dc9a  mov     rax, [rax+78h]
0x18000dc9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dca3  xorps   xmm0, xmm0
0x18000dca6  xor     eax, eax
0x18000dca8  movups  [rsp+0C8h+var_80], xmm0
0x18000dcad  mov     [rsp+0C8h+var_70], rax
0x18000dcb2  mov     byte ptr [rsp+0C8h+var_70], 1
0x18000dcb7  lea     rdx, [rsp+0C8h+var_60]
0x18000dcbc  lea     rcx, [rsp+0C8h+var_80]
0x18000dcc1  call    ??$Copy@VTaskAllocator@@@@YA_NAEAU_EAP_METHOD_PROPERTY_ARRAY@@AEBU0@@Z; Copy<TaskAllocator>(_EAP_METHOD_PROPERTY_ARRAY &,_EAP_METHOD_PROPERTY_ARRAY const &)
0x18000dcc6  test    al, al
0x18000dcc8  jnz     short loc_18000DCD6
0x18000dcca  lea     rcx, aComRefAssign; "com_ref:Assign"
0x18000dcd1  call    ?Throw@LowMemoryError@@SAXPEB_W@Z; LowMemoryError::Throw(wchar_t const *)
0x18000dcd6  movups  xmm1, [rsp+0C8h+var_80]
0x18000dcdb  xorps   xmm0, xmm0
0x18000dcde  xor     eax, eax
0x18000dce0  movups  [rsp+0C8h+var_80], xmm0
0x18000dce5  mov     [rsp+0C8h+var_70], rax
0x18000dcea  mov     byte ptr [rsp+0C8h+var_70], 1
0x18000dcef  movdqu  xmmword ptr [rbx], xmm1
0x18000dcf3  lea     rcx, [rsp+0C8h+var_80]
0x18000dcf8  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_METHOD_PROPERTY_ARRAY@@@Z; Free<TaskAllocator>(_EAP_METHOD_PROPERTY_ARRAY &)
0x18000dcfd  nop
0x18000dcfe  mov     rcx, [rsp+0C8h+arg_48]; this
0x18000dd06  test    rcx, rcx
0x18000dd09  jz      short loc_18000DD11
0x18000dd0b  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x18000dd10  nop
0x18000dd11  jmp     short loc_18000DD19
0x18000dd13  jmp     short loc_18000DD19
0x18000dd15  jmp     short loc_18000DD19
0x18000dd17  jmp     short $+2
0x18000dd19  lea     rcx, [rsp+0C8h+var_60]
0x18000dd1e  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_METHOD_PROPERTY_ARRAY@@@Z; Free<HeapAllocator>(_EAP_METHOD_PROPERTY_ARRAY &)
0x18000dd23  mov     eax, dword ptr [rsp+0C8h+var_88]
0x18000dd27  lea     r11, [rsp+0C8h+var_8]
0x18000dd2f  mov     rbx, [r11+10h]
0x18000dd33  mov     rsi, [r11+18h]
0x18000dd37  mov     rsp, r11
0x18000dd3a  pop     rdi
0x18000dd3b  retn
```
