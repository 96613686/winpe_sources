# CPropertyDescriptionList::_AddPropListToArray(ushort const *,CCoSimpleArray<ATL::CComPtr<IPropertyDescription>,4294967294,CSimpleArrayStandardCompareHelper<ATL::CComPtr<IPropertyDescription>>> &)

- ea: `0x18002e238`
- end: `0x18002e6de`
- name: `?_AddPropListToArray@CPropertyDescriptionList@@AEAAJPEBGAEAV?$CCoSimpleArray@V?$CComPtr@UIPropertyDescription@@@ATL@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@V?$CComPtr@UIPropertyDescription@@@ATL@@@@@@@Z`
- size: `1190`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, _QWORD *)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002f180`
- `0x180032014`
- `0x180057610`

## callees

- `0x18002e238`
- `0x18002e8b0`
- `0x18002ecc0`
- `0x18002ef54`
- `0x18006522c`
- `0x18006ed20`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x18002e65f`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x18002e65f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x18002e4c3`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x18002e4c3`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18002e514`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18002e514`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18002e57a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18002e57a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e477`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e477`

## pseudocode

```c
__int64 __fastcall CPropertyDescriptionList::_AddPropListToArray(__int64 a1, const WCHAR *a2, _QWORD *a3)
{
  const WCHAR *v4; // rbx
  int v5; // r13d
  __int64 v6; // r14
  _WORD *v7; // r15
  unsigned int v8; // edi
  const WCHAR *v9; // rbx
  int v10; // esi
  wchar_t *v11; // rcx
  int v12; // ebx
  bool v13; // sf
  __int64 v14; // rcx
  int LocalMachineSchemaView; // esi
  unsigned int v16; // esi
  unsigned int v17; // edi
  void *v18; // rdi
  __int64 v19; // rdx
  _QWORD *v20; // rdx
  PWSTR v22; // rax
  int v23; // edx
  int v24; // ecx
  PWSTR v25; // r9
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx
  int v34; // ecx
  int v35; // ecx
  int v36; // ecx
  const wchar_t *v37; // rbx
  GUID *v38; // [rsp+20h] [rbp-60h]
  int v39; // [rsp+40h] [rbp-40h]
  unsigned int v40; // [rsp+48h] [rbp-38h]
  void *v42; // [rsp+58h] [rbp-28h] BYREF
  __int64 v43; // [rsp+60h] [rbp-20h] BYREF
  __int64 v44; // [rsp+68h] [rbp-18h] BYREF
  wchar_t *EndPtr; // [rsp+70h] [rbp-10h] BYREF

  v4 = a2;
  v5 = 0;
  LODWORD(v6) = 0;
  while ( 1 )
  {
    v7 = 0;
    v42 = 0;
    if ( (_DWORD)v6 )
      goto LABEL_3;
    if ( !StrCmpNICW(v4, L"prop:", 5) )
    {
      LODWORD(v6) = 5;
LABEL_3:
      v39 = 0;
      LODWORD(v43) = 0;
      v8 = 0;
      v40 = 0;
      v9 = &v4[(unsigned int)v6];
      v10 = 1;
      while ( 1 )
      {
        while ( 1 )
        {
          if ( !v10 )
          {
            v22 = StrChrW(v9, 0x3Bu);
            v25 = v22;
            if ( v22 )
            {
              LODWORD(v6) = v22 - a2 + 1;
            }
            else
            {
              v24 = lstrlenW(v9);
              v25 = (PWSTR)&v9[v24];
              v6 = v25 - a2;
            }
            v12 = _AllocStringWorker<CTCoAllocPolicy>(v24, v23, (_DWORD)v9, v25 - v9, (_DWORD)v38, (__int64)&v42);
            v7 = v42;
            goto LABEL_9;
          }
          v11 = (wchar_t *)*v9;
          if ( (unsigned int)v11 <= 0x2F )
            break;
          v26 = (_DWORD)v11 - 48;
          if ( !v26 )
          {
            v8 |= 0x1C0u;
            goto LABEL_52;
          }
          v27 = v26 - 1;
          if ( !v27 )
          {
            v8 |= 0x180u;
            goto LABEL_52;
          }
          v28 = v27 - 1;
          if ( v28 )
          {
            v29 = v28 - 1;
            if ( v29 )
            {
              v30 = v29 - 43;
              if ( v30 )
              {
                v31 = v30 - 30;
                if ( v31 )
                {
                  if ( v31 == 2 )
                  {
                    v8 |= 0x200u;
                    goto LABEL_52;
                  }
                  goto LABEL_76;
                }
                v8 |= 1u;
              }
              else
              {
                v8 |= 4u;
              }
            }
            else
            {
              v8 |= 0x800u;
            }
          }
          else
          {
            v8 |= 0x100u;
          }
LABEL_52:
          ++v9;
        }
        if ( (_DWORD)v11 == 47 )
        {
          v8 |= 2u;
          goto LABEL_52;
        }
        if ( !*v9 )
          goto LABEL_8;
        v32 = (_DWORD)v11 - 33;
        if ( !v32 )
        {
          v8 |= 0x1000u;
          goto LABEL_52;
        }
        v33 = v32 - 2;
        if ( !v33 )
        {
          v8 |= 8u;
          goto LABEL_52;
        }
        v34 = v33 - 5;
        if ( v34 )
        {
          v35 = v34 - 2;
          if ( !v35 )
          {
            v39 = 1;
            goto LABEL_52;
          }
          v36 = v35 - 1;
          if ( !v36 )
          {
            LODWORD(v43) = 1;
            goto LABEL_52;
          }
          if ( v36 == 2 )
          {
            v8 |= 0x10u;
            goto LABEL_52;
          }
LABEL_76:
          v10 = 0;
        }
        else
        {
          v37 = v9 + 1;
          EndPtr = 0;
          v40 = wcstol(v37, &EndPtr, 10);
          v11 = EndPtr;
          if ( EndPtr == v37 || *EndPtr != 41 )
          {
LABEL_8:
            v12 = 1;
            goto LABEL_9;
          }
          v9 = EndPtr + 1;
        }
      }
    }
    v8 = 0;
    v39 = 0;
    LODWORD(v43) = 0;
    v40 = 0;
    v12 = -2147467259;
LABEL_9:
    v13 = v12 < 0;
    if ( v12 )
      break;
    if ( *v7 )
    {
      v44 = 0;
      if ( (byte_1800F1382 & 0x10) != 0 )
        McTemplateU0z_EtwEventWriteTransfer(
          v11,
          ShellTraceId_PropertyDescription_SHGetPropertyDescriptionByName_Start,
          v7);
      v44 = 0;
      v42 = 0;
      LocalMachineSchemaView = SchemaCache_GetLocalMachineSchemaView(&GUID_a8765599_6915_4a84_ab8c_3bf8927b06c6, &v42);
      if ( LocalMachineSchemaView >= 0 )
      {
        LocalMachineSchemaView = (*(__int64 (__fastcall **)(void *, _WORD *, GUID *, __int64 *))(*(_QWORD *)v42 + 32LL))(
                                   v42,
                                   v7,
                                   &GUID_6f79d558_3e96_4549_a1d1_7d75d2288814,
                                   &v44);
        (*(void (__fastcall **)(void *))(*(_QWORD *)v42 + 16LL))(v42);
      }
      if ( (byte_1800F1382 & 0x10) != 0 )
        McTemplateU0z_EtwEventWriteTransfer(
          v14,
          ShellTraceId_PropertyDescription_SHGetPropertyDescriptionByName_Stop,
          v7);
      if ( LocalMachineSchemaView < 0 )
      {
        v5 = 1;
      }
      else
      {
        v16 = v8 | 0x20;
        if ( !v39 )
          v16 = v8;
        v17 = v16 | 0x10;
        if ( !(_DWORD)v43 )
          v17 = v16;
        v43 = 0;
        v12 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v44)(
                v44,
                &GUID_b5316cf2_ae74_45d1_994f_f3795e912655,
                &v43);
        if ( v12 >= 0 )
        {
          v42 = 0;
          v38 = &GUID_6f79d558_3e96_4549_a1d1_7d75d2288814;
          v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v43 + 24LL))(v43, v17, v16, v40);
          if ( v12 >= 0 )
          {
            v18 = v42;
            if ( v42 )
              (*(void (__fastcall **)(void *))(*(_QWORD *)v42 + 8LL))(v42);
            v12 = 0;
            v19 = a3[1];
            if ( v19 != a3[3]
              || (v12 = CTSimpleArray<ATL::CComPtr<IPropertyDescription>,4294967294,CTPolicyCoTaskMem<ATL::CComPtr<IPropertyDescription>>,CSimpleArrayStandardCompareHelper<ATL::CComPtr<IPropertyDescription>>,CSimpleArrayStandardMergeHelper<ATL::CComPtr<IPropertyDescription>>>::_EnsureCapacity(
                          a3,
                          v19 + 1),
                  v12 >= 0) )
            {
              v20 = (_QWORD *)(*a3 + 8 * a3[1]++);
              if ( v20 )
              {
                *v20 = v18;
                if ( v18 )
                  (*(void (__fastcall **)(void *))(*(_QWORD *)v18 + 8LL))(v18);
              }
            }
            if ( v18 )
              (*(void (__fastcall **)(void *))(*(_QWORD *)v18 + 16LL))(v18);
            (*(void (__fastcall **)(void *))(*(_QWORD *)v42 + 16LL))(v42);
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
      }
      CoTaskMemFree(v7);
      v13 = v12 < 0;
      if ( v12 )
        break;
    }
    v4 = a2;
  }
  if ( !v13 )
    return v5 != 0 ? 0x401A0u : 0;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18002e238  mov     [rsp-38h+arg_0], rbx
0x18002e23d  push    rbp
0x18002e23e  push    rsi
0x18002e23f  push    rdi
0x18002e240  push    r12
0x18002e242  push    r13
0x18002e244  push    r14
0x18002e246  push    r15
0x18002e248  mov     rbp, rsp
0x18002e24b  sub     rsp, 80h
0x18002e252  mov     rax, cs:__security_cookie
0x18002e259  xor     rax, rsp
0x18002e25c  mov     [rbp+var_8], rax
0x18002e260  mov     r12, r8
0x18002e263  mov     rbx, rdx
0x18002e266  mov     [rbp+var_30], rdx
0x18002e26a  xor     r13d, r13d
0x18002e26d  xor     r14d, r14d
0x18002e270  xor     r15d, r15d
0x18002e273  mov     [rbp+var_28], r15
0x18002e277  test    r14d, r14d
0x18002e27a  jz      loc_18002E504
0x18002e280  mov     [rbp+var_40], r15d
0x18002e284  mov     dword ptr [rbp+var_20], r15d
0x18002e288  xor     edi, edi
0x18002e28a  mov     dword ptr [rbp+var_38], edi
0x18002e28d  mov     eax, r14d
0x18002e290  lea     rbx, [rbx+rax*2]
0x18002e294  lea     esi, [rdi+1]
0x18002e297  test    esi, esi
0x18002e299  jz      loc_18002E4BB
0x18002e29f  movzx   ecx, word ptr [rbx]
0x18002e2a2  cmp     ecx, 2Fh ; '/'
0x18002e2a5  ja      loc_18002E52B
0x18002e2ab  jz      loc_18002E699
0x18002e2b1  test    ecx, ecx
0x18002e2b3  jnz     loc_18002E596
0x18002e2b9  mov     ebx, 1
0x18002e2be  test    ebx, ebx
0x18002e2c0  jnz     loc_18002E485
0x18002e2c6  xor     eax, eax
0x18002e2c8  cmp     ax, [r15]
0x18002e2cc  jz      loc_18002E634
0x18002e2d2  mov     [rbp+var_18], rax
0x18002e2d6  test    cs:byte_1800F1382, 10h
0x18002e2dd  jnz     loc_18002E6CA
0x18002e2e3  mov     [rbp+var_18], 0
0x18002e2eb  mov     [rbp+var_28], 0
0x18002e2f3  lea     rdx, [rbp+var_28]; void **
0x18002e2f7  lea     rcx, _GUID_a8765599_6915_4a84_ab8c_3bf8927b06c6; struct _GUID *
0x18002e2fe  call    ?SchemaCache_GetLocalMachineSchemaView@@YAJAEBU_GUID@@PEAPEAX@Z; SchemaCache_GetLocalMachineSchemaView(_GUID const &,void * *)
0x18002e303  mov     esi, eax
0x18002e305  test    eax, eax
0x18002e307  js      short loc_18002E339
0x18002e309  mov     rcx, [rbp+var_28]
0x18002e30d  mov     rax, [rcx]
0x18002e310  lea     r9, [rbp+var_18]
0x18002e314  lea     r8, _GUID_6f79d558_3e96_4549_a1d1_7d75d2288814
0x18002e31b  mov     rdx, r15
0x18002e31e  mov     rax, [rax+20h]
0x18002e322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e327  mov     esi, eax
0x18002e329  mov     rcx, [rbp+var_28]
0x18002e32d  mov     rax, [rcx]
0x18002e330  mov     rax, [rax+10h]
0x18002e334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e339  test    cs:byte_1800F1382, 10h
0x18002e340  jnz     loc_18002E620
0x18002e346  xor     eax, eax
0x18002e348  test    esi, esi
0x18002e34a  js      loc_18002E615
0x18002e350  mov     esi, edi
0x18002e352  or      esi, 20h
0x18002e355  cmp     [rbp+var_40], eax
0x18002e358  cmovz   esi, edi
0x18002e35b  mov     edi, esi
0x18002e35d  or      edi, 10h
0x18002e360  cmp     dword ptr [rbp+var_20], eax
0x18002e363  cmovz   edi, esi
0x18002e366  mov     [rbp+var_20], rax
0x18002e36a  mov     rcx, [rbp+var_18]
0x18002e36e  mov     rax, [rcx]
0x18002e371  lea     r8, [rbp+var_20]
0x18002e375  lea     rdx, _GUID_b5316cf2_ae74_45d1_994f_f3795e912655
0x18002e37c  mov     rax, [rax]
0x18002e37f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e384  mov     ebx, eax
0x18002e386  test    eax, eax
0x18002e388  js      loc_18002E464
0x18002e38e  mov     [rbp+var_28], 0
0x18002e396  mov     rcx, [rbp+var_20]
0x18002e39a  mov     rax, [rcx]
0x18002e39d  lea     rdx, [rbp+var_28]
0x18002e3a1  mov     [rsp+80h+var_58], rdx
0x18002e3a6  lea     rdx, _GUID_6f79d558_3e96_4549_a1d1_7d75d2288814
0x18002e3ad  mov     [rsp+80h+var_60], rdx
0x18002e3b2  mov     r9d, dword ptr [rbp+var_38]
0x18002e3b6  mov     r8d, esi
0x18002e3b9  mov     edx, edi
0x18002e3bb  mov     rax, [rax+18h]
0x18002e3bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e3c4  mov     ebx, eax
0x18002e3c6  test    eax, eax
0x18002e3c8  js      loc_18002E454
0x18002e3ce  mov     rdi, [rbp+var_28]
0x18002e3d2  mov     [rbp+var_38], rdi
0x18002e3d6  test    rdi, rdi
0x18002e3d9  jz      short loc_18002E3EB
0x18002e3db  mov     rax, [rdi]
0x18002e3de  mov     rcx, rdi
0x18002e3e1  mov     rax, [rax+8]
0x18002e3e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e3ea  nop
0x18002e3eb  xor     ebx, ebx
0x18002e3ed  mov     rdx, [r12+8]
0x18002e3f2  cmp     rdx, [r12+18h]
0x18002e3f7  jz      loc_18002E5D4
0x18002e3fd  inc     qword ptr [r12+8]
0x18002e402  mov     rdx, [r12+8]
0x18002e407  mov     rax, [r12]
0x18002e40b  dec     rdx
0x18002e40e  lea     rdx, [rax+rdx*8]
0x18002e412  test    rdx, rdx
0x18002e415  jz      short loc_18002E42F
0x18002e417  mov     [rdx], rdi
0x18002e41a  test    rdi, rdi
0x18002e41d  jz      short loc_18002E42F
0x18002e41f  mov     rax, [rdi]
0x18002e422  mov     rcx, rdi
0x18002e425  mov     rax, [rax+8]
0x18002e429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e42e  nop
0x18002e42f  test    rdi, rdi
0x18002e432  jz      short loc_18002E444
0x18002e434  mov     rax, [rdi]
0x18002e437  mov     rcx, rdi
0x18002e43a  mov     rax, [rax+10h]
0x18002e43e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e443  nop
0x18002e444  mov     rcx, [rbp+var_28]
0x18002e448  mov     rax, [rcx]
0x18002e44b  mov     rax, [rax+10h]
0x18002e44f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e454  mov     rcx, [rbp+var_20]
0x18002e458  mov     rax, [rcx]
0x18002e45b  mov     rax, [rax+10h]
0x18002e45f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e464  mov     rcx, [rbp+var_18]
0x18002e468  mov     rax, [rcx]
0x18002e46b  mov     rax, [rax+10h]
0x18002e46f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e474  mov     rcx, r15; pv
0x18002e477  call    cs:__imp_CoTaskMemFree
0x18002e47d  test    ebx, ebx
0x18002e47f  jz      loc_18002E634
0x18002e485  js      short loc_18002E492
0x18002e487  neg     r13d
0x18002e48a  sbb     ebx, ebx
0x18002e48c  and     ebx, 401A0h
0x18002e492  mov     eax, ebx
0x18002e494  mov     rcx, [rbp+var_8]
0x18002e498  xor     rcx, rsp; StackCookie
0x18002e49b  call    __security_check_cookie
0x18002e4a0  mov     rbx, [rsp+80h+arg_0]
0x18002e4a8  add     rsp, 80h
0x18002e4af  pop     r15
0x18002e4b1  pop     r14
0x18002e4b3  pop     r13
0x18002e4b5  pop     r12
0x18002e4b7  pop     rdi
0x18002e4b8  pop     rsi
0x18002e4b9  pop     rbp
0x18002e4ba  retn
0x18002e4bb  mov     edx, 3Bh ; ';'; wMatch
0x18002e4c0  mov     rcx, rbx; pszStart
0x18002e4c3  call    cs:__imp_StrChrW
0x18002e4c9  mov     r9, rax
0x18002e4cc  test    rax, rax
0x18002e4cf  jz      loc_18002E577
0x18002e4d5  mov     r14, rax
0x18002e4d8  sub     r14, [rbp+var_30]
0x18002e4dc  sar     r14, 1
0x18002e4df  inc     r14d
0x18002e4e2  sub     r9, rbx
0x18002e4e5  sar     r9, 1
0x18002e4e8  lea     rax, [rbp+var_28]
0x18002e4ec  mov     [rsp+80h+var_58], rax
0x18002e4f1  mov     r8, rbx
0x18002e4f4  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18002e4f9  mov     ebx, eax
0x18002e4fb  mov     r15, [rbp+var_28]
0x18002e4ff  jmp     loc_18002E2BE
0x18002e504  mov     r8d, 5; nChar
0x18002e50a  lea     rdx, aProp; "prop:"
0x18002e511  mov     rcx, rbx; pszStr1
0x18002e514  call    cs:__imp_StrCmpNICW
0x18002e51a  test    eax, eax
0x18002e51c  jnz     loc_18002E5BF
0x18002e522  lea     r14d, [rax+5]
0x18002e526  jmp     loc_18002E280
0x18002e52b  sub     ecx, 30h ; '0'
0x18002e52e  jz      loc_18002E60A
0x18002e534  sub     ecx, 1
0x18002e537  jz      loc_18002E5FF
0x18002e53d  sub     ecx, 1
0x18002e540  jz      loc_18002E6C1
0x18002e546  sub     ecx, 1
0x18002e549  jz      loc_18002E6B8
0x18002e54f  sub     ecx, 2Bh ; '+'
0x18002e552  jz      loc_18002E6B0
0x18002e558  sub     ecx, 1Eh
0x18002e55b  jz      loc_18002E6A8
0x18002e561  cmp     ecx, 2
0x18002e564  jnz     loc_18002E6A1
0x18002e56a  bts     edi, 9
0x18002e56e  add     rbx, 2
0x18002e572  jmp     loc_18002E297
0x18002e577  mov     rcx, rbx; lpString
0x18002e57a  call    cs:__imp_lstrlenW
0x18002e580  movsxd  rcx, eax
0x18002e583  lea     r9, [rbx+rcx*2]
0x18002e587  mov     r14, r9
0x18002e58a  sub     r14, [rbp+var_30]
0x18002e58e  sar     r14, 1
0x18002e591  jmp     loc_18002E4E2
0x18002e596  sub     ecx, 21h ; '!'
0x18002e599  jz      loc_18002E690
0x18002e59f  sub     ecx, 2
0x18002e5a2  jz      loc_18002E688
0x18002e5a8  sub     ecx, 5
0x18002e5ab  jz      loc_18002E64A
0x18002e5b1  sub     ecx, 2
0x18002e5b4  jnz     short loc_18002E5EE
0x18002e5b6  mov     [rbp+var_40], 1
0x18002e5bd  jmp     short loc_18002E56E
0x18002e5bf  xor     edi, edi
0x18002e5c1  mov     [rbp+var_40], edi
0x18002e5c4  mov     dword ptr [rbp+var_20], edi
0x18002e5c7  mov     dword ptr [rbp+var_38], edi
0x18002e5ca  mov     ebx, 80004005h
0x18002e5cf  jmp     loc_18002E2BE
0x18002e5d4  inc     rdx
0x18002e5d7  mov     rcx, r12
0x18002e5da  call    ?_EnsureCapacity@?$CTSimpleArray@V?$CComPtr@UIPropertyDescription@@@ATL@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$CComPtr@UIPropertyDescription@@@ATL@@@@V?$CSimpleArrayStandardCompareHelper@V?$CComPtr@UIPropertyDescription@@@ATL@@@@V?$CSimpleArrayStandardMergeHelper@V?$CComPtr@UIPropertyDescription@@@ATL@@@@@@QEAAJ_K0@Z; CTSimpleArray<ATL::CComPtr<IPropertyDescription>,4294967294,CTPolicyCoTaskMem<ATL::CComPtr<IPropertyDescription>>,CSimpleArrayStandardCompareHelper<ATL::CComPtr<IPropertyDescription>>,CSimpleArrayStandardMergeHelper<ATL::CComPtr<IPropertyDescription>>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x18002e5df  mov     ebx, eax
0x18002e5e1  test    eax, eax
0x18002e5e3  jns     loc_18002E3FD
0x18002e5e9  jmp     loc_18002E42F
0x18002e5ee  sub     ecx, 1
0x18002e5f1  jnz     short loc_18002E63D
0x18002e5f3  mov     dword ptr [rbp+var_20], 1
0x18002e5fa  jmp     loc_18002E56E
0x18002e5ff  or      edi, 180h
0x18002e605  jmp     loc_18002E56E
0x18002e60a  or      edi, 1C0h
0x18002e610  jmp     loc_18002E56E
0x18002e615  mov     r13d, 1
0x18002e61b  jmp     loc_18002E474
0x18002e620  mov     r8, r15
0x18002e623  lea     rdx, ShellTraceId_PropertyDescription_SHGetPropertyDescriptionByName_Stop
0x18002e62a  call    McTemplateU0z_EtwEventWriteTransfer
0x18002e62f  jmp     loc_18002E346
0x18002e634  mov     rbx, [rbp+var_30]
0x18002e638  jmp     loc_18002E270
0x18002e63d  cmp     ecx, 2
0x18002e640  jnz     short loc_18002E6A1
0x18002e642  or      edi, 10h
0x18002e645  jmp     loc_18002E56E
0x18002e64a  add     rbx, 2
0x18002e64e  mov     [rbp+EndPtr], r15
0x18002e652  mov     r8d, 0Ah; Radix
0x18002e658  lea     rdx, [rbp+EndPtr]; EndPtr
0x18002e65c  mov     rcx, rbx; String
0x18002e65f  call    cs:__imp_wcstol
0x18002e665  mov     dword ptr [rbp+var_38], eax
0x18002e668  mov     rcx, [rbp+EndPtr]
0x18002e66c  cmp     rcx, rbx
0x18002e66f  jz      loc_18002E2B9
0x18002e675  cmp     word ptr [rcx], 29h ; ')'
0x18002e679  jnz     loc_18002E2B9
0x18002e67f  lea     rbx, [rcx+2]
0x18002e683  jmp     loc_18002E297
0x18002e688  or      edi, 8
0x18002e68b  jmp     loc_18002E56E
0x18002e690  bts     edi, 0Ch
0x18002e694  jmp     loc_18002E56E
0x18002e699  or      edi, 2
0x18002e69c  jmp     loc_18002E56E
0x18002e6a1  xor     esi, esi
0x18002e6a3  jmp     loc_18002E297
0x18002e6a8  or      edi, 1
0x18002e6ab  jmp     loc_18002E56E
0x18002e6b0  or      edi, 4
0x18002e6b3  jmp     loc_18002E56E
0x18002e6b8  bts     edi, 0Bh
0x18002e6bc  jmp     loc_18002E56E
0x18002e6c1  bts     edi, 8
0x18002e6c5  jmp     loc_18002E56E
0x18002e6ca  mov     r8, r15
0x18002e6cd  lea     rdx, ShellTraceId_PropertyDescription_SHGetPropertyDescriptionByName_Start
  ... truncated ...
```
