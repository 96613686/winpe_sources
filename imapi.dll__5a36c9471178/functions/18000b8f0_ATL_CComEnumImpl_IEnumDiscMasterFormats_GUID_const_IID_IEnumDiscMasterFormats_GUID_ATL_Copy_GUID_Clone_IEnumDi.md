# ATL::CComEnumImpl<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>>::Clone(IEnumDiscMasterFormats * *)

- ea: `0x18000b8f0`
- end: `0x18000ba96`
- name: `?Clone@?$CComEnumImpl@UIEnumDiscMasterFormats@@$1?IID_IEnumDiscMasterFormats@@3U_GUID@@BU3@V?$_Copy@U_GUID@@@ATL@@@ATL@@UEAAJPEAPEAUIEnumDiscMasterFormats@@@Z`
- size: `422`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000b8a0`

## callees

- `0x18000115c`
- `0x180002f5c`
- `0x180002f84`
- `0x18000b10c`
- `0x18000b8f0`
- `0x18000c438`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComEnumImpl<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>>::Clone(
        __int64 a1,
        char **a2)
{
  int Interface; // ebx
  void *v5; // rax
  __int64 v6; // rax
  char *v7; // r14
  int v8; // ecx
  int v9; // eax
  __int64 v10; // rdi
  char v11; // bp
  __int64 v12; // rbx
  __int64 v13; // rsi
  __int64 v15; // [rsp+68h] [rbp+10h]

  LODWORD(v15) = 0;
  Interface = -2147467261;
  if ( a2 )
  {
    *a2 = 0;
    Interface = -2147024882;
    v5 = operator new(0x90u);
    if ( v5 )
    {
      v6 = ATL::CComObject<ATL::CComEnum<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>,ATL::CComMultiThreadModel>>::CComObject<ATL::CComEnum<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>,ATL::CComMultiThreadModel>>(v5);
      v7 = (char *)v6;
      if ( v6 )
      {
        v8 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)(v6 + 56));
        if ( v8 >= 0 )
          v7[96] = 1;
        v9 = 0;
        if ( v8 < 0 )
          v9 = v8;
        Interface = 0;
        if ( v9 < 0 )
          Interface = v9;
        if ( Interface )
          goto LABEL_25;
        if ( (*(_BYTE *)(a1 + 40) & 2) != 0 )
        {
          v10 = a1;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
          v11 = 1;
          LODWORD(v12) = a1;
          v13 = v15;
        }
        else
        {
          v12 = *(_QWORD *)(a1 + 8);
          v13 = v12;
          if ( v12 )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v12 + 8LL))(*(_QWORD *)(a1 + 8));
          v10 = v15;
          v11 = 2;
        }
        Interface = ATL::CComEnumImpl<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>>::Init(
                      (_DWORD)v7,
                      *(_QWORD *)(a1 + 16),
                      *(_QWORD *)(a1 + 24),
                      v12,
                      0);
        if ( (v11 & 2) != 0 )
        {
          v11 &= ~2u;
          if ( v13 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        }
        if ( (v11 & 1) != 0 && v10 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        if ( Interface < 0
          || (*((_QWORD *)v7 + 4) = *(_QWORD *)(a1 + 32),
              Interface = ATL::CComObjectRootBase::InternalQueryInterface(
                            v7,
                            (const struct ATL::_ATL_INTMAP_ENTRY *)&`ATL::CComEnum<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>,ATL::CComMultiThreadModel>::_GetEntries'::`2'::_entries,
                            &IID_IEnumDiscMasterFormats,
                            a2),
              Interface < 0) )
        {
          if ( v7 )
LABEL_25:
            (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v7 + 56LL))(v7, 1);
        }
      }
    }
  }
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x18000b8f0  mov     [rsp+arg_0], rbx
0x18000b8f5  mov     [rsp+arg_10], rbp
0x18000b8fa  push    rsi
0x18000b8fb  push    rdi
0x18000b8fc  push    r12
0x18000b8fe  push    r14
0x18000b900  push    r15
0x18000b902  sub     rsp, 30h
0x18000b906  mov     dword ptr [rsp+58h+arg_8], 0
0x18000b90e  mov     r12, rdx
0x18000b911  mov     r15, rcx
0x18000b914  mov     ebx, 80004003h
0x18000b919  test    rdx, rdx
0x18000b91c  jz      loc_18000BA7D
0x18000b922  mov     ecx, 90h; Size
0x18000b927  mov     qword ptr [rdx], 0
0x18000b92e  mov     ebx, 8007000Eh
0x18000b933  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b938  test    rax, rax
0x18000b93b  jz      loc_18000BA7D
0x18000b941  mov     rcx, rax
0x18000b944  call    ??0?$CComObject@V?$CComEnum@UIEnumDiscMasterFormats@@$1?IID_IEnumDiscMasterFormats@@3U_GUID@@BU3@V?$_Copy@U_GUID@@@ATL@@VCComMultiThreadModel@5@@ATL@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<ATL::CComEnum<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>,ATL::CComMultiThreadModel>>::CComObject<ATL::CComEnum<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>,ATL::CComMultiThreadModel>>(void *)
0x18000b949  mov     r14, rax
0x18000b94c  test    rax, rax
0x18000b94f  jz      loc_18000BA7D
0x18000b955  lea     rcx, [rax+38h]; this
0x18000b959  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000b95e  mov     ecx, eax
0x18000b960  mov     esi, 1
0x18000b965  test    eax, eax
0x18000b967  js      short loc_18000B96D
0x18000b969  mov     [r14+60h], sil
0x18000b96d  xor     eax, eax
0x18000b96f  test    ecx, ecx
0x18000b971  cmovs   eax, ecx
0x18000b974  xor     ebx, ebx
0x18000b976  test    eax, eax
0x18000b978  cmovs   ebx, eax
0x18000b97b  test    ebx, ebx
0x18000b97d  jz      short loc_18000B99B
0x18000b97f  mov     rax, [r14]
0x18000b982  mov     edx, esi
0x18000b984  mov     rcx, r14
0x18000b987  mov     rax, [rax+38h]
0x18000b98b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b990  xor     r14d, r14d
0x18000b993  test    ebx, ebx
0x18000b995  js      loc_18000BA7D
0x18000b99b  test    byte ptr [r15+28h], 2
0x18000b9a0  jz      short loc_18000B9C0
0x18000b9a2  mov     rax, [r15]
0x18000b9a5  mov     rcx, r15
0x18000b9a8  mov     rdi, r15
0x18000b9ab  mov     rax, [rax+8]
0x18000b9af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9b4  mov     ebp, esi
0x18000b9b6  mov     rbx, r15
0x18000b9b9  mov     rsi, [rsp+58h+arg_8]
0x18000b9be  jmp     short loc_18000B9E5
0x18000b9c0  mov     rbx, [r15+8]
0x18000b9c4  mov     rsi, rbx
0x18000b9c7  test    rbx, rbx
0x18000b9ca  jz      short loc_18000B9DB
0x18000b9cc  mov     rax, [rbx]
0x18000b9cf  mov     rcx, rbx
0x18000b9d2  mov     rax, [rax+8]
0x18000b9d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9db  mov     rdi, [rsp+58h+arg_8]
0x18000b9e0  mov     ebp, 2
0x18000b9e5  mov     r8, [r15+18h]
0x18000b9e9  mov     r9, rbx
0x18000b9ec  mov     rdx, [r15+10h]
0x18000b9f0  mov     rcx, r14
0x18000b9f3  mov     [rsp+58h+var_38], 0
0x18000b9fb  call    ?Init@?$CComEnumImpl@UIEnumDiscMasterFormats@@$1?IID_IEnumDiscMasterFormats@@3U_GUID@@BU3@V?$_Copy@U_GUID@@@ATL@@@ATL@@QEAAJPEAU_GUID@@0PEAUIUnknown@@W4CComEnumFlags@2@@Z; ATL::CComEnumImpl<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>>::Init(_GUID *,_GUID *,IUnknown *,ATL::CComEnumFlags)
0x18000ba00  mov     ebx, eax
0x18000ba02  test    bpl, 2
0x18000ba06  jz      short loc_18000BA1F
0x18000ba08  and     ebp, 0FFFFFFFDh
0x18000ba0b  test    rsi, rsi
0x18000ba0e  jz      short loc_18000BA1F
0x18000ba10  mov     rcx, [rsi]
0x18000ba13  mov     rax, [rcx+10h]
0x18000ba17  mov     rcx, rsi
0x18000ba1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba1f  test    bpl, 1
0x18000ba23  jz      short loc_18000BA39
0x18000ba25  test    rdi, rdi
0x18000ba28  jz      short loc_18000BA39
0x18000ba2a  mov     rax, [rdi]
0x18000ba2d  mov     rcx, rdi
0x18000ba30  mov     rax, [rax+10h]
0x18000ba34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba39  test    ebx, ebx
0x18000ba3b  js      short loc_18000BA64
0x18000ba3d  mov     rax, [r15+20h]
0x18000ba41  lea     r8, IID_IEnumDiscMasterFormats; struct _GUID *
0x18000ba48  mov     r9, r12; void **
0x18000ba4b  mov     [r14+20h], rax
0x18000ba4f  lea     rdx, ?_entries@?1??_GetEntries@?$CComEnum@UIEnumDiscMasterFormats@@$1?IID_IEnumDiscMasterFormats@@3U_GUID@@BU3@V?$_Copy@U_GUID@@@ATL@@VCComMultiThreadModel@5@@ATL@@SAPEBU_ATL_INTMAP_ENTRY@3@XZ@4QBU43@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000ba56  mov     rcx, r14; void *
0x18000ba59  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x18000ba5e  mov     ebx, eax
0x18000ba60  test    eax, eax
0x18000ba62  jns     short loc_18000BA7D
0x18000ba64  test    r14, r14
0x18000ba67  jz      short loc_18000BA7D
0x18000ba69  mov     rax, [r14]
0x18000ba6c  mov     edx, 1
0x18000ba71  mov     rcx, r14
0x18000ba74  mov     rax, [rax+38h]
0x18000ba78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba7d  mov     rbp, [rsp+58h+arg_10]
0x18000ba82  mov     eax, ebx
0x18000ba84  mov     rbx, [rsp+58h+arg_0]
0x18000ba89  add     rsp, 30h
0x18000ba8d  pop     r15
0x18000ba8f  pop     r14
0x18000ba91  pop     r12
0x18000ba93  pop     rdi
0x18000ba94  pop     rsi
0x18000ba95  retn
```
