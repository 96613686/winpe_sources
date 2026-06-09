# CMemPropStore::_EnsureUnserializedInsideLock(void)

- ea: `0x1800113a0`
- end: `0x180011c9d`
- name: `?_EnsureUnserializedInsideLock@CMemPropStore@@AEAAJXZ`
- size: `2301`
- prototype: `__int64 __fastcall(CMemPropStore *__hidden this)`
- caller_count: `5`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800101c0`
- `0x180010550`
- `0x180011010`
- `0x180033f10`
- `0x18004a5f0`

## callees

- `0x18000b410`
- `0x18000fa10`
- `0x180010550`
- `0x1800113a0`
- `0x1800123a0`
- `0x180015dac`
- `0x180017770`
- `0x1800347e0`
- `0x18003bc6c`
- `0x18003feb0`
- `0x18006ed20`
- `0x18006fb80`
- `0x18006fb98`
- `0x18006fe52`
- `0x18008dfa4`
- `0x1800ab010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180011634`
- `ntdll!RtlNtStatusToDosError` at `0x180011812`
- `ntdll!RtlNtStatusToDosError` at `0x180011634`
- `ntdll!RtlNtStatusToDosError` at `0x180011812`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011519`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011519`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011678`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011678`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800116ef`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800118a1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011c19`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800116ef`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800118a1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011c19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011448`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011448`
- `OLEAUT32!__imp_SysFreeString` at `0x1800119a3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800119a3`

## pseudocode

```c
__int64 __fastcall CMemPropStore::_EnsureUnserializedInsideLock(CMemPropStore *this)
{
  unsigned int *v1; // rsi
  signed int v2; // ebx
  __int64 result; // rax
  __int64 v5; // rax
  unsigned int *v6; // r14
  BOOL v7; // r13d
  unsigned int v8; // eax
  const WCHAR *v9; // rbx
  unsigned int v10; // r15d
  WCHAR *v11; // rax
  WCHAR *v12; // r13
  _BYTE *v13; // rcx
  NTSTATUS v14; // ebx
  __int64 v15; // rcx
  signed int v16; // eax
  GUID v17; // xmm0
  enum PSC_STATE v18; // r9d
  _BYTE *v19; // rcx
  NTSTATUS v20; // r12d
  __int64 v21; // rcx
  signed int v22; // eax
  signed int ElementCount; // r12d
  signed int v24; // r15d
  const unsigned __int16 *v25; // rax
  OLECHAR *v26; // r15
  unsigned int v27; // r15d
  __int64 v28; // r8
  VARTYPE v29; // ax
  LARGE_INTEGER v30; // rbx
  unsigned int v31; // edx
  unsigned int v32; // r15d
  __int64 v33; // r8
  VARTYPE vt; // ax
  LARGE_INTEGER hVal; // r12
  unsigned int v36; // edx
  _BYTE *v37; // rdx
  signed int v38; // r12d
  signed int v39; // r15d
  _BYTE *v40; // rdx
  struct tagCLIPDATA *v41; // [rsp+40h] [rbp-C0h] BYREF
  BOOL v42; // [rsp+48h] [rbp-B8h]
  struct tagPROPVARIANT pvar; // [rsp+50h] [rbp-B0h] BYREF
  void **v44; // [rsp+68h] [rbp-98h] BYREF
  struct _tagpropertykey v45; // [rsp+70h] [rbp-90h] BYREF
  void ***v46; // [rsp+90h] [rbp-70h] BYREF
  __int64 v47; // [rsp+98h] [rbp-68h]
  _BYTE v48[344]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE *v49; // [rsp+1F8h] [rbp+F8h]
  int v50; // [rsp+200h] [rbp+100h]
  int v51; // [rsp+204h] [rbp+104h]

  v1 = (unsigned int *)*((_QWORD *)this + 25);
  v2 = 0;
  if ( !v1 || *((_BYTE *)this + 240) )
    goto LABEL_2;
  *((_BYTE *)this + 240) = 1;
  if ( !*((_DWORD *)this + 26) && !*((_DWORD *)this + 34) )
  {
LABEL_10:
    if ( *v1 <= 0x18 )
      goto LABEL_6;
    v5 = *((_QWORD *)v1 + 1) - *(_QWORD *)&FMTID_UserDefinedProperties.Data1;
    if ( !v5 )
      v5 = *((_QWORD *)v1 + 2) - *(_QWORD *)FMTID_UserDefinedProperties.Data4;
    v6 = v1 + 6;
    v7 = v5 == 0;
    v42 = v7;
    while ( 1 )
    {
      if ( !*v6 )
      {
LABEL_42:
        v1 = (unsigned int *)((char *)v1 + *v1);
        if ( v2 < 0 )
          goto LABEL_8;
        goto LABEL_10;
      }
      memset(&pvar, 0, sizeof(pvar));
      if ( v7 )
        v8 = v6[1] + 9;
      else
        v8 = 9;
      v9 = (const WCHAR *)((char *)v6 + v8);
      v10 = *v6 - v8;
      if ( ((unsigned __int8)v9 & 7) == 0 )
      {
        v44 = &CoAllocator::`vftable';
        if ( v10 < 4 )
        {
          v20 = 13;
        }
        else
        {
          if ( ((*(_DWORD *)v9 - 67) & 0xFFFFFFF9) == 0 && *(_DWORD *)v9 != 71 )
          {
            v20 = -1073741637;
            goto LABEL_71;
          }
          v47 = 2;
          v46 = &v44;
          v51 = 1200;
          v50 = 0;
          memset_0(v48, 0, sizeof(v48));
          v19 = v48;
          v49 = v48;
          if ( (v47 & 2) == 0 || v46 )
          {
            LODWORD(v41) = 0;
            v20 = DeserializeHelper::Worker((DeserializeHelper *)&v46, v9, v10, 0, 0, 0, &pvar, (unsigned int *)&v41);
            if ( v20 < 0 || !v50 )
              goto LABEL_50;
            v32 = v10 - (_DWORD)v41;
            v33 = (unsigned int)v41;
            vt = pvar.vt;
            if ( pvar.vt == 73 )
            {
              hVal = *(LARGE_INTEGER *)(pvar.hVal.QuadPart + 16);
              *(_QWORD *)(pvar.hVal.QuadPart + 16) = 0;
              vt = pvar.vt;
            }
            else
            {
              hVal = pvar.hVal;
              pvar.hVal.QuadPart = 0;
            }
            switch ( vt )
            {
              case 0x44u:
LABEL_87:
                if ( v32 < 4 )
                {
                  v20 = -2147024883;
                  goto LABEL_50;
                }
                v36 = *(_DWORD *)((char *)v9 + v33);
                if ( v32 - 4 < v36 )
                {
                  v20 = -2147024883;
                  goto LABEL_50;
                }
                if ( (int)PropertyToVariant_BufferToStream((const unsigned __int8 *)v9 + v33 + 4, v36, &pvar.pStream) < 0 )
                {
                  v20 = -2147024883;
                  goto LABEL_50;
                }
                break;
              case 0xDu:
                goto LABEL_102;
              case 0x42u:
                goto LABEL_87;
              case 0x43u:
              case 0x45u:
              case 0x49u:
LABEL_102:
                v20 = -1073741637;
                goto LABEL_50;
            }
            ((void (__fastcall *)(void ***, LARGE_INTEGER))v44[1])(&v44, hVal);
            v20 = 0;
            goto LABEL_50;
          }
          v20 = -1073741811;
          while ( 1 )
          {
            if ( v20 < 0 && *((_DWORD *)v19 + 80) )
            {
              do
              {
                v40 = &v19[16 * --*((_DWORD *)v19 + 80)];
                (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v40 + 1) + 8LL))(
                  *((_QWORD *)v40 + 1),
                  *(_QWORD *)v40);
                v19 = v49;
              }
              while ( *((_DWORD *)v49 + 80) );
            }
            v21 = *((_QWORD *)v19 + 41);
            v49 = (_BYTE *)v21;
            if ( !v21 )
              break;
            CoTaskMemFree_0(*(LPVOID *)(v21 + 336));
            *((_QWORD *)v49 + 42) = 0;
LABEL_50:
            v19 = v49;
          }
          if ( v20 < 0 )
LABEL_71:
            memset(&pvar, 0, sizeof(pvar));
        }
        v22 = RtlNtStatusToDosError(v20);
        v2 = v22;
        if ( v22 > 0 )
          v2 = (unsigned __int16)v22 | 0x80070000;
        if ( v2 < 0 )
          goto LABEL_8;
        if ( (unsigned int)IsPropVariantValidForVista(&pvar) )
        {
          if ( (pvar.vt & 0xFFF) == 0x47 )
          {
            ElementCount = PropVariantGetElementCount((const PROPVARIANT *const)&pvar);
            v24 = 0;
            while ( v24 < ElementCount )
            {
              v41 = 0;
              if ( (int)PropVariantGetElemPtr(&pvar, v24, (void **)&v41) >= 0 )
              {
                ++v24;
                if ( (unsigned int)_IsValidClipData(v41) )
                  continue;
              }
              goto LABEL_63;
            }
          }
        }
        else
        {
LABEL_63:
          PropVariantClear((PROPVARIANT *)&pvar);
          v2 = -2147467259;
        }
        goto LABEL_35;
      }
      v11 = (WCHAR *)LocalAlloc(0x40u, v10);
      v12 = v11;
      if ( !v11 )
      {
        v2 = -2147024882;
LABEL_8:
        CMemPropStore::_DeleteAllPropsFromDPAs(this);
        goto LABEL_9;
      }
      memcpy_0(v11, v9, v10);
      v44 = &CoAllocator::`vftable';
      if ( v10 < 4 )
      {
        v14 = 13;
      }
      else
      {
        if ( ((*(_DWORD *)v12 - 67) & 0xFFFFFFF9) != 0 || *(_DWORD *)v12 == 71 )
        {
          v47 = 2;
          v46 = &v44;
          v51 = 1200;
          v50 = 0;
          memset_0(v48, 0, sizeof(v48));
          v13 = v48;
          v49 = v48;
          if ( (v47 & 2) == 0 || v46 )
          {
            LODWORD(v41) = 0;
            v14 = DeserializeHelper::Worker((DeserializeHelper *)&v46, v12, v10, 0, 0, 0, &pvar, (unsigned int *)&v41);
            if ( v14 < 0 || !v50 )
              goto LABEL_25;
            v27 = v10 - (_DWORD)v41;
            v28 = (unsigned int)v41;
            v29 = pvar.vt;
            if ( pvar.vt == 73 )
            {
              v30 = *(LARGE_INTEGER *)(pvar.hVal.QuadPart + 16);
              *(_QWORD *)(pvar.hVal.QuadPart + 16) = 0;
              v29 = pvar.vt;
            }
            else
            {
              v30 = pvar.hVal;
              pvar.hVal.QuadPart = 0;
            }
            switch ( v29 )
            {
              case 0x44u:
LABEL_80:
                if ( v27 < 4 )
                {
                  v14 = -2147024883;
                  goto LABEL_25;
                }
                v31 = *(_DWORD *)((char *)v12 + v28);
                if ( v27 - 4 < v31 )
                {
                  v14 = -2147024883;
                  goto LABEL_25;
                }
                if ( (int)PropertyToVariant_BufferToStream((const unsigned __int8 *)v12 + v28 + 4, v31, &pvar.pStream) < 0 )
                {
                  v14 = -2147024883;
                  goto LABEL_25;
                }
                break;
              case 0xDu:
                goto LABEL_96;
              case 0x42u:
                goto LABEL_80;
              case 0x43u:
              case 0x45u:
              case 0x49u:
LABEL_96:
                v14 = -1073741637;
                goto LABEL_25;
            }
            ((void (__fastcall *)(void ***, LARGE_INTEGER))v44[1])(&v44, v30);
            v14 = 0;
            goto LABEL_25;
          }
          v14 = -1073741811;
          while ( 1 )
          {
            if ( v14 < 0 && *((_DWORD *)v13 + 80) )
            {
              do
              {
                v37 = &v13[16 * --*((_DWORD *)v13 + 80)];
                (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v37 + 1) + 8LL))(
                  *((_QWORD *)v37 + 1),
                  *(_QWORD *)v37);
                v13 = v49;
              }
              while ( *((_DWORD *)v49 + 80) );
            }
            v15 = *((_QWORD *)v13 + 41);
            v49 = (_BYTE *)v15;
            if ( !v15 )
              break;
            CoTaskMemFree_0(*(LPVOID *)(v15 + 336));
            *((_QWORD *)v49 + 42) = 0;
LABEL_25:
            v13 = v49;
          }
          if ( v14 >= 0 )
            goto LABEL_29;
        }
        else
        {
          v14 = -1073741637;
        }
        memset(&pvar, 0, sizeof(pvar));
      }
LABEL_29:
      v16 = RtlNtStatusToDosError(v14);
      v2 = v16;
      if ( v16 > 0 )
        v2 = (unsigned __int16)v16 | 0x80070000;
      if ( v2 >= 0 )
      {
        if ( (unsigned int)IsPropVariantValidForVista(&pvar) )
        {
          if ( (pvar.vt & 0xFFF) == 0x47 )
          {
            v38 = PropVariantGetElementCount((const PROPVARIANT *const)&pvar);
            v39 = 0;
            while ( v39 < v38 )
            {
              v41 = 0;
              if ( (int)PropVariantGetElemPtr(&pvar, v39, (void **)&v41) >= 0 )
              {
                ++v39;
                if ( (unsigned int)_IsValidClipData(v41) )
                  continue;
              }
              goto LABEL_119;
            }
          }
        }
        else
        {
LABEL_119:
          PropVariantClear((PROPVARIANT *)&pvar);
          v2 = -2147467259;
        }
      }
      LocalFree(v12);
      v7 = v42;
LABEL_35:
      if ( v2 < 0 )
        goto LABEL_8;
      if ( v7 )
      {
        v25 = CMemPropStore::s_ualSysAllocString((const unsigned __int16 *)((char *)v6 + 9));
        v26 = (OLECHAR *)v25;
        if ( v25 )
        {
          v2 = CMemPropStore::_SetNamedValueInsideLock(this, v25, &pvar);
          SysFreeString(v26);
        }
        else
        {
          v2 = -2147024882;
        }
      }
      else
      {
        v17 = *(GUID *)(v1 + 2);
        v45.pid = v6[1];
        v45.fmtid = v17;
        if ( pvar.vt )
          v18 = *((_DWORD *)this + 48) & 2;
        else
          v18 = PSC_NOTINSOURCE;
        v2 = CMemPropStore::_SetValueAndStateInsideLock(this, &v45, &pvar, v18, 1);
        if ( v2 >= 0 )
          memset(&pvar, 0, sizeof(pvar));
      }
      PropVariantClear((PROPVARIANT *)&pvar);
      v6 = (unsigned int *)((char *)v6 + *v6);
      if ( v2 < 0 )
        goto LABEL_42;
    }
  }
LABEL_6:
  CoTaskMemFree(*((LPVOID *)this + 25));
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
LABEL_9:
  *((_BYTE *)this + 240) = 0;
LABEL_2:
  result = (unsigned int)v2;
  *((_BYTE *)this + 241) = v2 >= 0;
  return result;
}

```

## disassembly

```asm
0x1800113a0  push    rbp
0x1800113a2  push    rbx
0x1800113a3  push    rsi
0x1800113a4  push    rdi
0x1800113a5  lea     rbp, [rsp-138h]
0x1800113ad  sub     rsp, 238h
0x1800113b4  mov     rax, cs:__security_cookie
0x1800113bb  xor     rax, rsp
0x1800113be  mov     [rbp+150h+var_30], rax
0x1800113c5  mov     rsi, [rcx+0C8h]
0x1800113cc  xor     ebx, ebx
0x1800113ce  mov     rdi, rcx
0x1800113d1  test    rsi, rsi
0x1800113d4  jnz     short loc_180011401
0x1800113d6  mov     ecx, ebx
0x1800113d8  mov     eax, ebx
0x1800113da  shr     ecx, 1Fh
0x1800113dd  xor     cl, 1
0x1800113e0  mov     [rdi+0F1h], cl
0x1800113e6  mov     rcx, [rbp+150h+var_30]
0x1800113ed  xor     rcx, rsp; StackCookie
0x1800113f0  call    __security_check_cookie
0x1800113f5  add     rsp, 238h
0x1800113fc  pop     rdi
0x1800113fd  pop     rsi
0x1800113fe  pop     rbx
0x1800113ff  pop     rbp
0x180011400  retn
0x180011401  cmp     [rcx+0F0h], bl
0x180011407  jnz     short loc_1800113D6
0x180011409  mov     [rsp+250h+arg_8], r12
0x180011411  mov     [rsp+250h+arg_10], r13
0x180011419  mov     [rsp+250h+arg_18], r14
0x180011421  mov     [rsp+250h+var_20], r15
0x180011429  mov     byte ptr [rcx+0F0h], 1
0x180011430  cmp     [rcx+68h], ebx
0x180011433  jnz     short loc_180011441
0x180011435  cmp     [rcx+88h], ebx
0x18001143b  jz      loc_180011B59
0x180011441  mov     rcx, [rdi+0C8h]; pv
0x180011448  call    cs:__imp_CoTaskMemFree
0x18001144e  mov     qword ptr [rdi+0C8h], 0
0x180011459  mov     qword ptr [rdi+0D0h], 0
0x180011464  jmp     short loc_180011473
0x180011466  mov     ebx, 8007000Eh
0x18001146b  mov     rcx, rdi; this
0x18001146e  call    ?_DeleteAllPropsFromDPAs@CMemPropStore@@AEAAXXZ; CMemPropStore::_DeleteAllPropsFromDPAs(void)
0x180011473  mov     r15, [rsp+250h+var_20]
0x18001147b  mov     r14, [rsp+250h+arg_18]
0x180011483  mov     r13, [rsp+250h+arg_10]
0x18001148b  mov     r12, [rsp+250h+arg_8]
0x180011493  mov     byte ptr [rdi+0F0h], 0
0x18001149a  jmp     loc_1800113D6
0x1800114a0  cmp     dword ptr [rsi], 18h
0x1800114a3  jbe     short loc_180011441
0x1800114a5  mov     rax, [rsi+8]
0x1800114a9  sub     rax, qword ptr cs:FMTID_UserDefinedProperties.Data1
0x1800114b0  jnz     short loc_1800114BD
0x1800114b2  mov     rax, [rsi+10h]
0x1800114b6  sub     rax, qword ptr cs:FMTID_UserDefinedProperties.Data4
0x1800114bd  xor     r13d, r13d
0x1800114c0  lea     r14, [rsi+18h]
0x1800114c4  test    rax, rax
0x1800114c7  setz    r13b
0x1800114cb  mov     [rsp+250h+var_208], r13d
0x1800114d0  cmp     dword ptr [r14], 0
0x1800114d4  jz      loc_18001170A
0x1800114da  xor     eax, eax
0x1800114dc  xorps   xmm0, xmm0
0x1800114df  mov     [rsp+250h+var_1F0], rax
0x1800114e4  movups  xmmword ptr [rsp+250h+pvar], xmm0
0x1800114e9  test    r13d, r13d
0x1800114ec  jnz     loc_1800118F6
0x1800114f2  mov     eax, 9
0x1800114f7  mov     r15d, [r14]
0x1800114fa  mov     ebx, eax
0x1800114fc  add     rbx, r14
0x1800114ff  sub     r15d, ebx
0x180011502  add     r15d, r14d
0x180011505  test    bl, 7
0x180011508  jz      loc_18001171C
0x18001150e  mov     edx, r15d; uBytes
0x180011511  mov     ecx, 40h ; '@'; uFlags
0x180011516  mov     r12d, r15d
0x180011519  call    cs:__imp_LocalAlloc
0x18001151f  mov     r13, rax
0x180011522  test    rax, rax
0x180011525  jz      loc_180011466
0x18001152b  mov     r8d, r12d; Size
0x18001152e  mov     rdx, rbx; Src
0x180011531  mov     rcx, rax; void *
0x180011534  call    memcpy_0
0x180011539  lea     rax, ??_7CoAllocator@@6B@; const CoAllocator::`vftable'
0x180011540  mov     [rsp+250h+var_1E8], rax
0x180011545  cmp     r15d, 4
0x180011549  jb      loc_180011B65
0x18001154f  mov     ecx, [r13+0]
0x180011553  lea     eax, [rcx-43h]
0x180011556  test    eax, 0FFFFFFF9h
0x18001155b  jz      loc_1800118B1
0x180011561  lea     rax, [rsp+250h+var_1E8]
0x180011566  mov     [rbp+150h+var_1B8], 2
0x18001156e  xor     edx, edx; Val
0x180011570  mov     [rbp+150h+var_1C0], rax
0x180011574  mov     r8d, 158h; Size
0x18001157a  mov     [rbp+150h+var_4C], 4B0h
0x180011584  lea     rcx, [rbp+150h+var_1B0]; void *
0x180011588  mov     [rbp+150h+var_50], 0
0x180011592  call    memset_0
0x180011597  test    byte ptr [rbp+150h+var_1B8], 2
0x18001159b  lea     rcx, [rbp+150h+var_1B0]
0x18001159f  mov     [rbp+150h+var_58], rcx
0x1800115a6  jz      short loc_1800115B3
0x1800115a8  cmp     [rbp+150h+var_1C0], 0
0x1800115ad  jz      loc_180011956
0x1800115b3  lea     rax, [rsp+250h+var_210]
0x1800115b8  mov     dword ptr [rsp+250h+var_210], 0
0x1800115c0  mov     [rsp+250h+var_218], rax; unsigned int *
0x1800115c5  lea     rcx, [rbp+150h+var_1C0]; this
0x1800115c9  lea     rax, [rsp+250h+pvar]
0x1800115ce  xor     r9d, r9d; int
0x1800115d1  mov     [rsp+250h+var_220], rax; struct tagPROPVARIANT *
0x1800115d6  mov     r8d, r15d; unsigned int
0x1800115d9  mov     [rsp+250h+var_228], 0; int
0x1800115e1  mov     rdx, r13; struct tagSERIALIZEDPROPERTYVALUE *
0x1800115e4  mov     [rsp+250h+var_230], 0; int
0x1800115ec  call    ?Worker@DeserializeHelper@@QEAAJPEBUtagSERIALIZEDPROPERTYVALUE@@KHHHPEAUtagPROPVARIANT@@PEAK@Z; DeserializeHelper::Worker(tagSERIALIZEDPROPERTYVALUE const *,ulong,int,int,int,tagPROPVARIANT *,ulong *)
0x1800115f1  mov     ebx, eax
0x1800115f3  test    eax, eax
0x1800115f5  js      short loc_180011604
0x1800115f7  cmp     [rbp+150h+var_50], 0
0x1800115fe  jnz     loc_1800119AE
0x180011604  mov     rcx, [rbp+150h+var_58]
0x18001160b  test    ebx, ebx
0x18001160d  js      loc_180011B83
0x180011613  mov     rcx, [rcx+148h]
0x18001161a  mov     [rbp+150h+var_58], rcx
0x180011621  test    rcx, rcx
0x180011624  jnz     loc_1800118D3
0x18001162a  test    ebx, ebx
0x18001162c  js      loc_1800118BF
0x180011632  mov     ecx, ebx; Status
0x180011634  call    cs:__imp_RtlNtStatusToDosError
0x18001163a  mov     ebx, eax
0x18001163c  test    eax, eax
0x18001163e  jg      loc_180011902
0x180011644  test    ebx, ebx
0x180011646  js      short loc_180011675
0x180011648  lea     rcx, [rsp+250h+pvar]; struct tagPROPVARIANT *
0x18001164d  call    ?IsPropVariantValidForVista@@YAHAEBUtagPROPVARIANT@@@Z; IsPropVariantValidForVista(tagPROPVARIANT const &)
0x180011652  test    eax, eax
0x180011654  jz      loc_180011C14
0x18001165a  movzx   eax, word ptr [rsp+250h+pvar]
0x18001165f  mov     ecx, 0FFFh
0x180011664  and     ax, cx
0x180011667  mov     ecx, 47h ; 'G'
0x18001166c  cmp     cx, ax
0x18001166f  jz      loc_180011BCB
0x180011675  mov     rcx, r13; hMem
0x180011678  call    cs:__imp_LocalFree
0x18001167e  mov     r13d, [rsp+250h+var_208]
0x180011683  test    ebx, ebx
0x180011685  js      loc_18001146B
0x18001168b  test    r13d, r13d
0x18001168e  jnz     loc_180011979
0x180011694  movups  xmm0, xmmword ptr [rsi+8]
0x180011698  mov     eax, [r14+4]
0x18001169c  mov     [rbp+150h+var_1E0.pid], eax
0x18001169f  movups  xmmword ptr [rsp+250h+var_1E0.fmtid.Data1], xmm0
0x1800116a4  cmp     word ptr [rsp+250h+pvar], r13w
0x1800116aa  jz      loc_180011C92
0x1800116b0  mov     r9d, [rdi+0C0h]
0x1800116b7  and     r9d, 2; enum PSC_STATE
0x1800116bb  lea     r8, [rsp+250h+pvar]; struct tagPROPVARIANT *
0x1800116c0  mov     [rsp+250h+var_230], 1; int
0x1800116c8  lea     rdx, [rsp+250h+var_1E0]; struct _tagpropertykey *
0x1800116cd  mov     rcx, rdi; this
0x1800116d0  call    ?_SetValueAndStateInsideLock@CMemPropStore@@AEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@W4PSC_STATE@@H@Z; CMemPropStore::_SetValueAndStateInsideLock(_tagpropertykey const &,tagPROPVARIANT *,PSC_STATE,int)
0x1800116d5  mov     ebx, eax
0x1800116d7  test    eax, eax
0x1800116d9  js      short loc_1800116EA
0x1800116db  xorps   xmm0, xmm0
0x1800116de  xor     eax, eax
0x1800116e0  movups  xmmword ptr [rsp+250h+pvar], xmm0
0x1800116e5  mov     [rsp+250h+var_1F0], rax
0x1800116ea  lea     rcx, [rsp+250h+pvar]; pvar
0x1800116ef  call    cs:__imp_PropVariantClear
0x1800116f5  mov     eax, [r14]
0x1800116f8  lea     rcx, ??_7CoAllocator@@6B@; const CoAllocator::`vftable'
0x1800116ff  add     r14, rax
0x180011702  test    ebx, ebx
0x180011704  jns     loc_1800114D0
0x18001170a  mov     eax, [rsi]
0x18001170c  add     rsi, rax
0x18001170f  test    ebx, ebx
0x180011711  jns     loc_1800114A0
0x180011717  jmp     loc_18001146B
0x18001171c  mov     [rsp+250h+var_1E8], rcx
0x180011721  cmp     r15d, 4
0x180011725  jb      loc_180011C29
0x18001172b  mov     ecx, [rbx]
0x18001172d  lea     eax, [rcx-43h]
0x180011730  test    eax, 0FFFFFFF9h
0x180011735  jz      loc_180011910
0x18001173b  lea     rax, [rsp+250h+var_1E8]
0x180011740  mov     [rbp+150h+var_1B8], 2
0x180011748  xor     edx, edx; Val
0x18001174a  mov     [rbp+150h+var_1C0], rax
0x18001174e  mov     r8d, 158h; Size
0x180011754  mov     [rbp+150h+var_4C], 4B0h
0x18001175e  lea     rcx, [rbp+150h+var_1B0]; void *
0x180011762  mov     [rbp+150h+var_50], 0
0x18001176c  call    memset_0
0x180011771  test    byte ptr [rbp+150h+var_1B8], 2
0x180011775  lea     rcx, [rbp+150h+var_1B0]
0x180011779  mov     [rbp+150h+var_58], rcx
0x180011780  jz      short loc_18001178D
0x180011782  cmp     [rbp+150h+var_1C0], 0
0x180011787  jz      loc_18001196E
0x18001178d  lea     rax, [rsp+250h+var_210]
0x180011792  mov     dword ptr [rsp+250h+var_210], 0
0x18001179a  mov     [rsp+250h+var_218], rax; unsigned int *
0x18001179f  lea     rcx, [rbp+150h+var_1C0]; this
0x1800117a3  lea     rax, [rsp+250h+pvar]
0x1800117a8  xor     r9d, r9d; int
0x1800117ab  mov     [rsp+250h+var_220], rax; struct tagPROPVARIANT *
0x1800117b0  mov     r8d, r15d; unsigned int
0x1800117b3  mov     [rsp+250h+var_228], 0; int
0x1800117bb  mov     rdx, rbx; struct tagSERIALIZEDPROPERTYVALUE *
0x1800117be  mov     [rsp+250h+var_230], 0; int
0x1800117c6  call    ?Worker@DeserializeHelper@@QEAAJPEBUtagSERIALIZEDPROPERTYVALUE@@KHHHPEAUtagPROPVARIANT@@PEAK@Z; DeserializeHelper::Worker(tagSERIALIZEDPROPERTYVALUE const *,ulong,int,int,int,tagPROPVARIANT *,ulong *)
0x1800117cb  mov     r12d, eax
0x1800117ce  test    eax, eax
0x1800117d0  js      short loc_1800117DF
0x1800117d2  cmp     [rbp+150h+var_50], 0
0x1800117d9  jnz     loc_180011A31
0x1800117df  mov     rcx, [rbp+150h+var_58]
0x1800117e6  test    r12d, r12d
0x1800117e9  js      loc_180011C4A
0x1800117ef  mov     rcx, [rcx+148h]
0x1800117f6  mov     [rbp+150h+var_58], rcx
0x1800117fd  test    rcx, rcx
0x180011800  jnz     loc_180011933
0x180011806  test    r12d, r12d
0x180011809  js      loc_18001191F
0x18001180f  mov     ecx, r12d; Status
0x180011812  call    cs:__imp_RtlNtStatusToDosError
0x180011818  mov     ebx, eax
0x18001181a  test    eax, eax
0x18001181c  jg      loc_180011960
0x180011822  test    ebx, ebx
0x180011824  js      loc_18001146B
0x18001182a  lea     rcx, [rsp+250h+pvar]; struct tagPROPVARIANT *
0x18001182f  call    ?IsPropVariantValidForVista@@YAHAEBUtagPROPVARIANT@@@Z; IsPropVariantValidForVista(tagPROPVARIANT const &)
0x180011834  test    eax, eax
0x180011836  jz      short loc_18001189C
0x180011838  movzx   eax, word ptr [rsp+250h+pvar]
0x18001183d  mov     ecx, 0FFFh
0x180011842  and     ax, cx
0x180011845  mov     ecx, 47h ; 'G'
0x18001184a  cmp     cx, ax
0x18001184d  jnz     loc_180011683
0x180011853  lea     rcx, [rsp+250h+pvar]; propvar
0x180011858  call    PropVariantGetElementCount
0x18001185d  mov     r12d, eax
0x180011860  xor     r15d, r15d
0x180011863  cmp     r15d, r12d
0x180011866  jge     loc_180011683
0x18001186c  lea     r8, [rsp+250h+var_210]; void **
0x180011871  mov     [rsp+250h+var_210], 0
0x18001187a  mov     edx, r15d; unsigned int
0x18001187d  lea     rcx, [rsp+250h+pvar]; struct tagPROPVARIANT *
0x180011882  call    ?PropVariantGetElemPtr@@YAJAEBUtagPROPVARIANT@@KPEAPEAX@Z; PropVariantGetElemPtr(tagPROPVARIANT const &,ulong,void * *)
0x180011887  test    eax, eax
0x180011889  js      short loc_18001189C
0x18001188b  mov     rcx, [rsp+250h+var_210]; struct tagCLIPDATA *
0x180011890  call    ?_IsValidClipData@@YAHPEAUtagCLIPDATA@@@Z; _IsValidClipData(tagCLIPDATA *)
0x180011895  inc     r15d
0x180011898  test    eax, eax
0x18001189a  jnz     short loc_180011863
0x18001189c  lea     rcx, [rsp+250h+pvar]; pvar
0x1800118a1  call    cs:__imp_PropVariantClear
0x1800118a7  mov     ebx, 80004005h
0x1800118ac  jmp     loc_180011683
0x1800118b1  cmp     ecx, 47h ; 'G'
0x1800118b4  jz      loc_180011561
0x1800118ba  mov     ebx, 0C00000BBh
0x1800118bf  xorps   xmm0, xmm0
0x1800118c2  xor     eax, eax
0x1800118c4  movups  xmmword ptr [rsp+250h+pvar], xmm0
0x1800118c9  mov     [rsp+250h+var_1F0], rax
0x1800118ce  jmp     loc_180011632
0x1800118d3  mov     rcx, [rcx+150h]; pv
0x1800118da  call    CoTaskMemFree_0
0x1800118df  mov     rax, [rbp+150h+var_58]
0x1800118e6  mov     qword ptr [rax+150h], 0
0x1800118f1  jmp     loc_180011604
0x1800118f6  mov     eax, [r14+4]
0x1800118fa  add     eax, 9
0x1800118fd  jmp     loc_1800114F7
  ... truncated ...
```
