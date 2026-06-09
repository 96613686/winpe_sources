# CSyncMLCmd::EndElement(ushort const *,ulong,ushort const *,ulong,SyncMLElemType,ushort const *,ulong,SyncMLElemType *)

- ea: `0x18000d510`
- end: `0x18000e00f`
- name: `?EndElement@CSyncMLCmd@@QEAAJPEBGK0KW4SyncMLElemType@@0KPEAW42@@Z`
- size: `2815`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180007e80`
- `0x18000d510`

## callees

- `0x180008d30`
- `0x18000d510`
- `0x1800128a0`
- `0x180014330`
- `0x1800146e4`
- `0x180014c60`
- `0x180015c87`
- `0x18001d670`
- `0x180020f24`
- `0x180021ae0`
- `0x180030010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000db55`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000dce5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000de03`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000dee2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000dfbb`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000db55`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000dce5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000de03`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000dee2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000dfbb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dbf3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dbf3`
- `DMCmnUtils!InvStrCmpNIW` at `0x18000da26`
- `DMCmnUtils!InvStrCmpNIW` at `0x18000da26`
- `DMCmnUtils!CopyString` at `0x18000dc09`
- `DMCmnUtils!CopyString` at `0x18000dc09`

## pseudocode

```c
__int64 __fastcall CSyncMLCmd::EndElement(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        unsigned int a6,
        const unsigned __int16 *a7,
        unsigned int a8,
        int *a9)
{
  __int64 v10; // rdi
  int v11; // ebx
  __int64 v12; // r10
  char *v13; // r12
  char *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // r15
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // r8
  unsigned __int64 v19; // r13
  size_t v20; // r13
  char *v21; // r14
  void *v22; // rax
  char *v23; // r8
  char *v24; // rdx
  char *v25; // rcx
  size_t v26; // r8
  __int64 v27; // rcx
  const struct std::nothrow_t *v28; // rdx
  void *v29; // rax
  __int64 v30; // r10
  char *v32; // r12
  char *v33; // rcx
  __int64 v34; // rax
  __int64 v35; // r15
  unsigned __int64 v36; // rcx
  unsigned __int64 v37; // r8
  unsigned __int64 v38; // r13
  size_t v39; // r13
  char *v40; // r14
  void *v41; // rax
  char *v42; // r8
  char *v43; // rdx
  char *v44; // rcx
  size_t v45; // r8
  __int64 v46; // rcx
  const struct std::nothrow_t *v47; // rdx
  void *v48; // rax
  unsigned int v49; // edx
  unsigned __int64 v50; // rbx
  __int64 v51; // rcx
  const unsigned __int16 *v52; // rax
  int v53; // r14d
  const unsigned __int16 **v54; // r12
  __int64 v55; // rax
  __int64 v56; // rax
  unsigned int v57; // edi
  __int64 v59; // rbx
  void (__fastcall ***v60)(_QWORD, __int64); // rcx
  __int64 v61; // rbx
  __int64 v62; // rcx
  unsigned int v63; // [rsp+50h] [rbp-B8h] BYREF
  const unsigned __int16 *v64; // [rsp+58h] [rbp-B0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v66; // [rsp+70h] [rbp-98h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+80h] [rbp-88h] BYREF
  char *v68; // [rsp+90h] [rbp-78h]
  int v69; // [rsp+98h] [rbp-70h]
  int v70; // [rsp+9Ch] [rbp-6Ch]
  unsigned int *v71; // [rsp+A0h] [rbp-68h]
  __int64 v72; // [rsp+A8h] [rbp-60h]
  const unsigned __int16 *v73; // [rsp+B0h] [rbp-58h]
  int v74; // [rsp+B8h] [rbp-50h]
  int v75; // [rsp+BCh] [rbp-4Ch]

  v63 = a3;
  *(_QWORD *)&EventDescriptor.Id = a2;
  v10 = a1;
  v66 = a1;
  v64 = a7;
  if ( (*(_DWORD *)(a1 + 144) & 1) != 0 )
  {
    v11 = CSyncMLMeta::EndElement(*(_QWORD *)(a1 + 96));
    if ( v11 >= 0 )
    {
      if ( *a9 == 23 )
        *(_DWORD *)(v10 + 144) &= ~1u;
      goto LABEL_104;
    }
    goto LABEL_102;
  }
  v12 = *(_QWORD *)(a1 + 120);
  if ( v12 )
  {
    v11 = CSyncMLItem::EndElement(v12);
    if ( v11 >= 0 )
    {
      if ( *a9 != 22 )
        goto LABEL_104;
      try
      {
        v13 = *(char **)(v10 + 16);
        v14 = *(char **)(v10 + 24);
        if ( v13 != v14 )
        {
          *(_QWORD *)v13 = *(_QWORD *)(v10 + 120);
          *(_QWORD *)(v10 + 16) += 8LL;
          goto LABEL_123;
        }
        v15 = *(_QWORD *)(v10 + 8);
        v16 = (__int64)&v13[-v15] >> 3;
        if ( v16 == 0x1FFFFFFFFFFFFFFFLL )
          std::vector<CSyncMLCmd *>::_Xlength();
        v17 = (__int64)&v14[-v15] >> 3;
        v18 = v17 >> 1;
        if ( v17 <= 0x1FFFFFFFFFFFFFFFLL - (v17 >> 1) )
        {
          v19 = v16 + 1;
          if ( v18 + v17 >= v16 + 1 )
            v19 = v18 + v17;
          if ( v19 > 0x1FFFFFFFFFFFFFFFLL )
            std::_Throw_bad_array_new_length();
          v20 = 8 * v19;
          if ( !v20 )
          {
            v21 = 0;
            goto LABEL_23;
          }
          if ( v20 < 0x1000 )
          {
            v21 = (char *)operator new(v20);
            goto LABEL_23;
          }
          if ( v20 + 39 >= v20 )
          {
            v22 = operator new(v20 + 39);
            if ( !v22 )
              goto LABEL_30;
            v21 = (char *)(((unsigned __int64)v22 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
            *((_QWORD *)v21 - 1) = v22;
LABEL_23:
            *(_QWORD *)&v21[8 * v16] = *(_QWORD *)(v10 + 120);
            v23 = *(char **)(v10 + 16);
            v24 = *(char **)(v10 + 8);
            v25 = v21;
            if ( v13 == v23 )
            {
              v26 = v23 - v24;
            }
            else
            {
              memmove_0(v21, v24, v13 - v24);
              v26 = *(_QWORD *)(v10 + 16) - (_QWORD)v13;
              v25 = &v21[8 * v16 + 8];
              v24 = v13;
            }
            memmove_0(v25, v24, v26);
            v27 = *(_QWORD *)(v10 + 8);
            if ( !v27 )
              goto LABEL_33;
            v28 = (const struct std::nothrow_t *)(8 * ((*(_QWORD *)(v10 + 24) - v27) >> 3));
            if ( (unsigned __int64)v28 < 0x1000 )
            {
              v29 = *(void **)(v10 + 8);
              goto LABEL_32;
            }
            v29 = *(void **)(v27 - 8);
            if ( (unsigned __int64)(v27 - (_QWORD)v29 - 8) <= 0x1F )
            {
              v28 = (const struct std::nothrow_t *)((char *)v28 + 39);
LABEL_32:
              operator delete(v29, v28);
LABEL_33:
              *(_QWORD *)(v10 + 8) = v21;
              *(_QWORD *)(v10 + 16) = &v21[8 * v16 + 8];
              *(_QWORD *)(v10 + 24) = &v21[v20];
              goto LABEL_123;
            }
LABEL_30:
            __fastfail(5u);
          }
        }
        std::_Throw_bad_array_new_length();
      }
      catch ( std::bad_alloc )
      {
        v59 = v66;
        v60 = *(void (__fastcall ****)(_QWORD, __int64))(v66 + 120);
        if ( v60 )
          (**v60)(v60, 1);
        *(_QWORD *)(v59 + 120) = 0;
        v63 = -2147024882;
        v11 = -2147024882;
        v10 = v66;
        goto LABEL_102;
      }
LABEL_123:
      *(_QWORD *)(v10 + 120) = 0;
      goto LABEL_104;
    }
LABEL_102:
    if ( (unsigned int)dword_18003E048 > 2 )
    {
      LODWORD(v64) = v11;
      v71 = (unsigned int *)&v64;
      v72 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_18003E050;
      UserData.Size = (unsigned __int16)*off_18003E050;
      UserData.Reserved = 2;
      v68 = &byte_18003720F;
      v69 = 36;
      v70 = 1;
      v63 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    goto LABEL_104;
  }
  v30 = *(_QWORD *)(a1 + 128);
  if ( !v30 )
  {
    if ( a4 && *a4 )
    {
      v49 = a5;
      v50 = a5;
      if ( a5 == 0xFFFFFFFFLL )
      {
        v51 = 0x7FFFFFFF;
        v52 = a4;
        do
        {
          if ( !*v52 )
          {
            v50 = 0x7FFFFFFF - v51;
            goto LABEL_73;
          }
          ++v52;
          --v51;
        }
        while ( v51 );
LABEL_78:
        if ( (unsigned int)dword_18003E048 > 2 )
        {
          v63 = v49;
          v55 = -1;
          do
            ++v55;
          while ( a4[v55] );
          v73 = a4;
          v74 = 2 * v55 + 2;
          v75 = 0;
          v71 = &v63;
          v72 = 4;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          *(_DWORD *)&EventDescriptor.Level = 2;
          EventDescriptor.Keyword = 0;
          UserData.Ptr = (ULONGLONG)off_18003E050;
          UserData.Size = (unsigned __int16)*off_18003E050;
          UserData.Reserved = 2;
          v68 = byte_1800368C9;
          v69 = 50;
          v70 = 1;
          LODWORD(v64) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
        }
        v11 = -2102788095;
        if ( *(_DWORD *)(v10 + 92) == 73 && (unsigned int)CSyncMLCmd::IsParentElementOfCmd(a6) )
        {
          v11 = 0;
          v53 = 73;
          goto LABEL_96;
        }
      }
      else
      {
LABEL_73:
        v53 = 0;
        while ( 1 )
        {
          v54 = (const unsigned __int16 **)&(&c_rgszSyncMLElem)[v53];
          if ( !InvStrCmpNIW(a4, *v54, v50) && !(*v54)[v50] )
            break;
          if ( ++v53 >= 73 )
          {
            v49 = a5;
            goto LABEL_78;
          }
        }
        v11 = 0;
        if ( v53 == *(_DWORD *)(v10 + 92) )
          goto LABEL_96;
        if ( v53 == 5 )
        {
          if ( v64 && a8 )
          {
            LocalFree(*(HLOCAL *)(v10 + 104));
            v11 = CopyString(v64, a8, (unsigned __int16 **)(v10 + 104));
            if ( v11 >= 0 )
            {
LABEL_96:
              *a9 = v53;
              goto LABEL_104;
            }
          }
          else
          {
            if ( (unsigned int)dword_18003E048 > 2 )
            {
              *(_DWORD *)&EventDescriptor.Id = 184549376;
              *(_DWORD *)&EventDescriptor.Level = 2;
              EventDescriptor.Keyword = 0;
              UserData.Ptr = (ULONGLONG)off_18003E050;
              UserData.Size = (unsigned __int16)*off_18003E050;
              UserData.Reserved = 2;
              v68 = byte_1800366CB;
              v69 = 17;
              v70 = 1;
              v63 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
              EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
            }
            v11 = -2102788095;
          }
        }
        else
        {
          v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, const unsigned __int16 *, unsigned int, unsigned int, const unsigned __int16 *, unsigned int, int *))(*(_QWORD *)v10 + 56LL))(
                  v10,
                  *(_QWORD *)&EventDescriptor.Id,
                  v63,
                  a4,
                  a5,
                  a6,
                  v64,
                  a8,
                  a9);
          if ( v11 >= 0 )
            goto LABEL_96;
        }
      }
    }
    else
    {
      v11 = -2147024809;
    }
    if ( (unsigned int)dword_18003E048 > 2 )
    {
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_18003E050;
      UserData.Size = (unsigned __int16)*off_18003E050;
      UserData.Reserved = 2;
      v68 = (char *)word_1800370EA;
      v69 = 27;
      v70 = 1;
      LODWORD(v64) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
    }
    if ( *(int *)(v10 + 56) >= 0 )
      *(_DWORD *)(v10 + 56) = v11;
    goto LABEL_102;
  }
  v11 = CSyncMLCmd::EndElement(v30);
  if ( v11 < 0 )
    goto LABEL_102;
  if ( (*(_DWORD *)(v10 + 148))-- != 1 )
    goto LABEL_104;
  try
  {
    v32 = *(char **)(v10 + 40);
    v33 = *(char **)(v10 + 48);
    if ( v32 != v33 )
    {
      *(_QWORD *)v32 = *(_QWORD *)(v10 + 128);
      *(_QWORD *)(v10 + 40) += 8LL;
      goto LABEL_128;
    }
    v34 = *(_QWORD *)(v10 + 32);
    v35 = (__int64)&v32[-v34] >> 3;
    if ( v35 == 0x1FFFFFFFFFFFFFFFLL )
      std::vector<CSyncMLCmd *>::_Xlength();
    v36 = (__int64)&v33[-v34] >> 3;
    v37 = v36 >> 1;
    if ( v36 <= 0x1FFFFFFFFFFFFFFFLL - (v36 >> 1) )
    {
      v38 = v35 + 1;
      if ( v37 + v36 >= v35 + 1 )
        v38 = v37 + v36;
      if ( v38 > 0x1FFFFFFFFFFFFFFFLL )
        std::_Throw_bad_array_new_length();
      v39 = 8 * v38;
      if ( !v39 )
      {
        v40 = 0;
        goto LABEL_53;
      }
      if ( v39 < 0x1000 )
      {
        v40 = (char *)operator new(v39);
        goto LABEL_53;
      }
      if ( v39 + 39 >= v39 )
      {
        v41 = operator new(v39 + 39);
        if ( !v41 )
          goto LABEL_60;
        v40 = (char *)(((unsigned __int64)v41 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *((_QWORD *)v40 - 1) = v41;
LABEL_53:
        *(_QWORD *)&v40[8 * v35] = *(_QWORD *)(v10 + 128);
        v42 = *(char **)(v10 + 40);
        v43 = *(char **)(v10 + 32);
        v44 = v40;
        if ( v32 == v42 )
        {
          v45 = v42 - v43;
        }
        else
        {
          memmove_0(v40, v43, v32 - v43);
          v45 = *(_QWORD *)(v10 + 40) - (_QWORD)v32;
          v44 = &v40[8 * v35 + 8];
          v43 = v32;
        }
        memmove_0(v44, v43, v45);
        v46 = *(_QWORD *)(v10 + 32);
        if ( !v46 )
          goto LABEL_63;
        v47 = (const struct std::nothrow_t *)(8 * ((*(_QWORD *)(v10 + 48) - v46) >> 3));
        if ( (unsigned __int64)v47 < 0x1000 )
        {
          v48 = *(void **)(v10 + 32);
          goto LABEL_62;
        }
        v48 = *(void **)(v46 - 8);
        if ( (unsigned __int64)(v46 - (_QWORD)v48 - 8) <= 0x1F )
        {
          v47 = (const struct std::nothrow_t *)((char *)v47 + 39);
LABEL_62:
          operator delete(v48, v47);
LABEL_63:
          *(_QWORD *)(v10 + 32) = v40;
          *(_QWORD *)(v10 + 40) = &v40[8 * v35 + 8];
          *(_QWORD *)(v10 + 48) = &v40[v39];
          goto LABEL_128;
        }
LABEL_60:
        __fastfail(5u);
      }
    }
    std::_Throw_bad_array_new_length();
  }
  catch ( std::bad_alloc )
  {
    v61 = v66;
    v62 = *(_QWORD *)(v66 + 128);
    if ( v62 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v62 + 40LL))(v62, 1);
    *(_QWORD *)(v61 + 128) = 0;
    v63 = -2147024882;
    v11 = -2147024882;
    v10 = v66;
    goto LABEL_102;
  }
LABEL_128:
  *(_QWORD *)(v10 + 128) = 0;
LABEL_104:
  v56 = *(_QWORD *)(v10 + 80);
  v57 = 0;
  if ( *(_DWORD *)(v56 + 28) )
    v57 = v11;
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    LODWORD(v64) = v57;
    v71 = (unsigned int *)&v64;
    v72 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 5;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    UserData.Size = (unsigned __int16)*off_18003E050;
    UserData.Reserved = 2;
    v68 = byte_180036DCD;
    v69 = 23;
    v70 = 1;
    v63 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  return v57;
}

```

## disassembly

```asm
0x18000d510  push    rbx
0x18000d512  push    rsi
0x18000d513  push    rdi
0x18000d514  push    r12
0x18000d516  push    r13
0x18000d518  push    r14
0x18000d51a  push    r15
0x18000d51c  sub     rsp, 0D0h
0x18000d523  mov     rax, cs:__security_cookie
0x18000d52a  xor     rax, rsp
0x18000d52d  mov     [rsp+108h+var_48], rax
0x18000d535  mov     r15, r9
0x18000d538  mov     [rsp+108h+var_B8], r8d
0x18000d53d  mov     qword ptr [rsp+108h+EventDescriptor.Id], rdx
0x18000d542  mov     rdi, rcx
0x18000d545  mov     [rsp+108h+var_98], rcx
0x18000d54a  mov     rcx, [rsp+108h+arg_30]
0x18000d552  mov     [rsp+108h+var_B0], rcx
0x18000d557  mov     r13, [rsp+108h+arg_40]
0x18000d55f  mov     eax, [rdi+90h]
0x18000d565  test    al, 1
0x18000d567  jz      short loc_18000D5CA
0x18000d569  mov     [rsp+108h+var_C8], r13
0x18000d56e  mov     eax, [rsp+108h+arg_38]
0x18000d575  mov     [rsp+108h+var_D0], eax
0x18000d579  mov     [rsp+108h+var_D8], rcx
0x18000d57e  mov     eax, [rsp+108h+arg_28]
0x18000d585  mov     dword ptr [rsp+108h+UserData], eax
0x18000d589  mov     eax, [rsp+108h+arg_20]
0x18000d590  mov     [rsp+108h+UserDataCount], eax
0x18000d594  mov     rcx, [rdi+60h]
0x18000d598  call    ?EndElement@CSyncMLMeta@@QEAAJPEBGK0KW4SyncMLElemType@@0KPEAW42@@Z; CSyncMLMeta::EndElement(ushort const *,ulong,ushort const *,ulong,SyncMLElemType,ushort const *,ulong,SyncMLElemType *)
0x18000d59d  mov     ebx, eax
0x18000d59f  test    eax, eax
0x18000d5a1  js      loc_18000D9B0
0x18000d5a7  cmp     dword ptr [r13+0], 17h
0x18000d5ac  jnz     short loc_18000D5B5
0x18000d5ae  and     dword ptr [rdi+90h], 0FFFFFFFEh
0x18000d5b5  xor     esi, esi
0x18000d5b7  lea     r15, _TraceLoggingMetadataEnd
0x18000d5be  lea     r12, _TraceLoggingMetadata
0x18000d5c5  jmp     loc_18000DEEE
0x18000d5ca  mov     r10, [rdi+78h]
0x18000d5ce  test    r10, r10
0x18000d5d1  jz      loc_18000D7C1
0x18000d5d7  mov     [rsp+108h+var_C8], r13
0x18000d5dc  mov     eax, [rsp+108h+arg_38]
0x18000d5e3  mov     [rsp+108h+var_D0], eax
0x18000d5e7  mov     [rsp+108h+var_D8], rcx
0x18000d5ec  mov     eax, [rsp+108h+arg_28]
0x18000d5f3  mov     dword ptr [rsp+108h+UserData], eax
0x18000d5f7  mov     eax, [rsp+108h+arg_20]
0x18000d5fe  mov     [rsp+108h+UserDataCount], eax
0x18000d602  mov     rcx, r10
0x18000d605  call    ?EndElement@CSyncMLItem@@QEAAJPEBGK0KW4SyncMLElemType@@0KPEAW42@@Z; CSyncMLItem::EndElement(ushort const *,ulong,ushort const *,ulong,SyncMLElemType,ushort const *,ulong,SyncMLElemType *)
0x18000d60a  mov     ebx, eax
0x18000d60c  test    eax, eax
0x18000d60e  js      loc_18000D9B0
0x18000d614  cmp     dword ptr [r13+0], 16h
0x18000d619  jnz     short loc_18000D5B5
0x18000d61b  mov     r12, [rdi+10h]
0x18000d61f  mov     rcx, [rdi+18h]
0x18000d623  cmp     r12, rcx
0x18000d626  jz      short loc_18000D63C
0x18000d628  mov     rax, [rdi+78h]
0x18000d62c  mov     [r12], rax
0x18000d630  add     qword ptr [rdi+10h], 8
0x18000d635  xor     esi, esi
0x18000d637  jmp     loc_18000D78C
0x18000d63c  mov     rax, [rdi+8]
0x18000d640  mov     r15, r12
0x18000d643  sub     r15, rax
0x18000d646  sar     r15, 3
0x18000d64a  mov     rdx, 1FFFFFFFFFFFFFFFh
0x18000d654  cmp     r15, rdx
0x18000d657  jz      loc_18000DFED
0x18000d65d  sub     rcx, rax
0x18000d660  sar     rcx, 3
0x18000d664  mov     r8, rcx
0x18000d667  shr     r8, 1
0x18000d66a  mov     rax, rdx
0x18000d66d  sub     rax, r8
0x18000d670  cmp     rcx, rax
0x18000d673  ja      loc_18000DFF8
0x18000d679  lea     r9, [r15+1]
0x18000d67d  lea     rax, [r8+rcx]
0x18000d681  mov     r13, r9
0x18000d684  cmp     rax, r9
0x18000d687  cmovnb  r13, rax
0x18000d68b  cmp     r13, rdx
0x18000d68e  ja      loc_18000DFF3
0x18000d694  lea     r13, ds:0[r13*8]
0x18000d69c  test    r13, r13
0x18000d69f  jnz     short loc_18000D6A8
0x18000d6a1  xor     esi, esi
0x18000d6a3  mov     r14d, esi
0x18000d6a6  jmp     short loc_18000D6E7
0x18000d6a8  cmp     r13, 1000h
0x18000d6af  jb      short loc_18000D6DA
0x18000d6b1  lea     rcx, [r13+27h]; Size
0x18000d6b5  cmp     rcx, r13
0x18000d6b8  jbe     loc_18000DFF8
0x18000d6be  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d6c3  test    rax, rax
0x18000d6c6  jz      loc_18000D762
0x18000d6cc  lea     r14, [rax+27h]
0x18000d6d0  and     r14, 0FFFFFFFFFFFFFFE0h
0x18000d6d4  mov     [r14-8], rax
0x18000d6d8  jmp     short loc_18000D6E5
0x18000d6da  mov     rcx, r13; Size
0x18000d6dd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d6e2  mov     r14, rax
0x18000d6e5  xor     esi, esi
0x18000d6e7  mov     rcx, [rdi+78h]
0x18000d6eb  mov     [r14+r15*8], rcx
0x18000d6ef  mov     r8, [rdi+10h]
0x18000d6f3  mov     rdx, [rdi+8]; Src
0x18000d6f7  mov     rcx, r14; void *
0x18000d6fa  cmp     r12, r8
0x18000d6fd  jnz     short loc_18000D704
0x18000d6ff  sub     r8, rdx
0x18000d702  jmp     short loc_18000D721
0x18000d704  mov     r8, r12
0x18000d707  sub     r8, rdx; Size
0x18000d70a  call    memmove_0
0x18000d70f  mov     r8, [rdi+10h]
0x18000d713  sub     r8, r12; Size
0x18000d716  lea     rcx, [r15+1]
0x18000d71a  lea     rcx, [r14+rcx*8]; void *
0x18000d71e  mov     rdx, r12; Src
0x18000d721  call    memmove_0
0x18000d726  mov     rcx, [rdi+8]
0x18000d72a  test    rcx, rcx
0x18000d72d  jz      short loc_18000D774
0x18000d72f  mov     rax, [rdi+18h]
0x18000d733  sub     rax, rcx
0x18000d736  sar     rax, 3
0x18000d73a  lea     rdx, ds:0[rax*8]; struct std::nothrow_t *
0x18000d742  cmp     rdx, 1000h
0x18000d749  jb      short loc_18000D769
0x18000d74b  mov     rax, [rcx-8]
0x18000d74f  sub     rcx, rax
0x18000d752  sub     rcx, 8
0x18000d756  cmp     rcx, 1Fh
0x18000d75a  ja      short loc_18000D762
0x18000d75c  add     rdx, 27h ; '''
0x18000d760  jmp     short loc_18000D76C
0x18000d762  mov     ecx, 5
0x18000d767  int     29h; Win8: RtlFailFast(ecx)
0x18000d769  mov     rax, rcx
0x18000d76c  mov     rcx, rax; void *
0x18000d76f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d774  mov     [rdi+8], r14
0x18000d778  lea     rax, [r15+1]
0x18000d77c  lea     rax, [r14+rax*8]
0x18000d780  mov     [rdi+10h], rax
0x18000d784  lea     rax, [r14+r13]
0x18000d788  mov     [rdi+18h], rax
0x18000d78c  mov     [rdi+78h], rsi
0x18000d790  lea     r15, _TraceLoggingMetadataEnd
0x18000d797  lea     r12, _TraceLoggingMetadata
0x18000d79e  jmp     loc_18000DEEE
0x18000d7a3  xor     esi, esi
0x18000d7a5  lea     r15, _TraceLoggingMetadataEnd
0x18000d7ac  lea     r12, _TraceLoggingMetadata
0x18000d7b3  mov     ebx, [rsp+108h+var_B8]
0x18000d7b7  mov     rdi, [rsp+108h+var_98]
0x18000d7bc  jmp     loc_18000DE20
0x18000d7c1  mov     r10, [rdi+80h]
0x18000d7c8  test    r10, r10
0x18000d7cb  jz      loc_18000D9C5
0x18000d7d1  mov     [rsp+108h+var_C8], r13
0x18000d7d6  mov     eax, [rsp+108h+arg_38]
0x18000d7dd  mov     [rsp+108h+var_D0], eax
0x18000d7e1  mov     [rsp+108h+var_D8], rcx
0x18000d7e6  mov     eax, [rsp+108h+arg_28]
0x18000d7ed  mov     dword ptr [rsp+108h+UserData], eax
0x18000d7f1  mov     eax, [rsp+108h+arg_20]
0x18000d7f8  mov     [rsp+108h+UserDataCount], eax
0x18000d7fc  mov     rcx, r10
0x18000d7ff  call    ?EndElement@CSyncMLCmd@@QEAAJPEBGK0KW4SyncMLElemType@@0KPEAW42@@Z; CSyncMLCmd::EndElement(ushort const *,ulong,ushort const *,ulong,SyncMLElemType,ushort const *,ulong,SyncMLElemType *)
0x18000d804  mov     ebx, eax
0x18000d806  test    eax, eax
0x18000d808  js      loc_18000D9B0
0x18000d80e  mov     eax, 0FFFFFFFFh
0x18000d813  add     [rdi+94h], eax
0x18000d819  jnz     loc_18000D5B5
0x18000d81f  mov     r12, [rdi+28h]
0x18000d823  mov     rcx, [rdi+30h]
0x18000d827  cmp     r12, rcx
0x18000d82a  jz      short loc_18000D843
0x18000d82c  mov     rax, [rdi+80h]
0x18000d833  mov     [r12], rax
0x18000d837  add     qword ptr [rdi+28h], 8
0x18000d83c  xor     esi, esi
0x18000d83e  jmp     loc_18000D996
0x18000d843  mov     rax, [rdi+20h]
0x18000d847  mov     r15, r12
0x18000d84a  sub     r15, rax
0x18000d84d  sar     r15, 3
0x18000d851  mov     rdx, 1FFFFFFFFFFFFFFFh
0x18000d85b  cmp     r15, rdx
0x18000d85e  jz      loc_18000DFFE
0x18000d864  sub     rcx, rax
0x18000d867  sar     rcx, 3
0x18000d86b  mov     r8, rcx
0x18000d86e  shr     r8, 1
0x18000d871  mov     rax, rdx
0x18000d874  sub     rax, r8
0x18000d877  cmp     rcx, rax
0x18000d87a  ja      loc_18000E008
0x18000d880  lea     r9, [r15+1]
0x18000d884  lea     rax, [r8+rcx]
0x18000d888  mov     r13, r9
0x18000d88b  cmp     rax, r9
0x18000d88e  cmovnb  r13, rax
0x18000d892  cmp     r13, rdx
0x18000d895  ja      loc_18000E003
0x18000d89b  lea     r13, ds:0[r13*8]
0x18000d8a3  test    r13, r13
0x18000d8a6  jnz     short loc_18000D8AF
0x18000d8a8  xor     esi, esi
0x18000d8aa  mov     r14d, esi
0x18000d8ad  jmp     short loc_18000D8EE
0x18000d8af  cmp     r13, 1000h
0x18000d8b6  jb      short loc_18000D8E1
0x18000d8b8  lea     rcx, [r13+27h]; Size
0x18000d8bc  cmp     rcx, r13
0x18000d8bf  jbe     loc_18000E008
0x18000d8c5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d8ca  test    rax, rax
0x18000d8cd  jz      loc_18000D96C
0x18000d8d3  lea     r14, [rax+27h]
0x18000d8d7  and     r14, 0FFFFFFFFFFFFFFE0h
0x18000d8db  mov     [r14-8], rax
0x18000d8df  jmp     short loc_18000D8EC
0x18000d8e1  mov     rcx, r13; Size
0x18000d8e4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d8e9  mov     r14, rax
0x18000d8ec  xor     esi, esi
0x18000d8ee  mov     rcx, [rdi+80h]
0x18000d8f5  mov     [r14+r15*8], rcx
0x18000d8f9  mov     r8, [rdi+28h]
0x18000d8fd  mov     rdx, [rdi+20h]; Src
0x18000d901  mov     rcx, r14; void *
0x18000d904  cmp     r12, r8
0x18000d907  jnz     short loc_18000D90E
0x18000d909  sub     r8, rdx
0x18000d90c  jmp     short loc_18000D92B
0x18000d90e  mov     r8, r12
0x18000d911  sub     r8, rdx; Size
0x18000d914  call    memmove_0
0x18000d919  mov     r8, [rdi+28h]
0x18000d91d  sub     r8, r12; Size
0x18000d920  lea     rcx, [r15+1]
0x18000d924  lea     rcx, [r14+rcx*8]; void *
0x18000d928  mov     rdx, r12; Src
0x18000d92b  call    memmove_0
0x18000d930  mov     rcx, [rdi+20h]
0x18000d934  test    rcx, rcx
0x18000d937  jz      short loc_18000D97E
0x18000d939  mov     rax, [rdi+30h]
0x18000d93d  sub     rax, rcx
0x18000d940  sar     rax, 3
0x18000d944  lea     rdx, ds:0[rax*8]; struct std::nothrow_t *
0x18000d94c  cmp     rdx, 1000h
0x18000d953  jb      short loc_18000D973
0x18000d955  mov     rax, [rcx-8]
0x18000d959  sub     rcx, rax
0x18000d95c  sub     rcx, 8
0x18000d960  cmp     rcx, 1Fh
0x18000d964  ja      short loc_18000D96C
0x18000d966  add     rdx, 27h ; '''
0x18000d96a  jmp     short loc_18000D976
0x18000d96c  mov     ecx, 5
0x18000d971  int     29h; Win8: RtlFailFast(ecx)
0x18000d973  mov     rax, rcx
0x18000d976  mov     rcx, rax; void *
0x18000d979  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d97e  mov     [rdi+20h], r14
0x18000d982  lea     rax, [r15+1]
0x18000d986  lea     rax, [r14+rax*8]
0x18000d98a  mov     [rdi+28h], rax
0x18000d98e  lea     rax, [r14+r13]
0x18000d992  mov     [rdi+30h], rax
0x18000d996  mov     [rdi+80h], rsi
0x18000d99d  lea     r15, _TraceLoggingMetadataEnd
0x18000d9a4  lea     r12, _TraceLoggingMetadata
0x18000d9ab  jmp     loc_18000DEEE
0x18000d9b0  xor     esi, esi
0x18000d9b2  lea     r15, _TraceLoggingMetadataEnd
0x18000d9b9  lea     r12, _TraceLoggingMetadata
0x18000d9c0  jmp     loc_18000DE20
0x18000d9c5  xor     esi, esi
0x18000d9c7  test    r15, r15
0x18000d9ca  jz      loc_18000DD4B
0x18000d9d0  cmp     si, [r9]
0x18000d9d4  jz      loc_18000DD4B
0x18000d9da  mov     edx, [rsp+108h+arg_20]
0x18000d9e1  mov     ebx, edx
  ... truncated ...
```
