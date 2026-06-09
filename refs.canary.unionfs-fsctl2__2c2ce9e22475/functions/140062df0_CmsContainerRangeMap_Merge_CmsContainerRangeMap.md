# CmsContainerRangeMap::Merge(CmsContainerRangeMap *)

- ea: `0x140062df0`
- end: `0x1400635c2`
- name: `?Merge@CmsContainerRangeMap@@QEAAXPEAV1@@Z`
- size: `2002`
- prototype: `void(CmsContainerRangeMap *__hidden this, struct CmsContainerRangeMap *)`
- caller_count: `8`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140056ee0`
- `0x140064480`
- `0x140065bdc`
- `0x1400c5f44`
- `0x1400c8390`
- `0x140120088`
- `0x140120124`
- `0x140129aec`

## callees

- `0x140062510`
- `0x140062df0`
- `0x1400b78b0`
- `0x14016d9f4`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400632ae`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400632ae`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140063107`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400634a0`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140063107`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400634a0`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140063335`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140063335`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f5edd`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f5edd`
- `ntoskrnl!ExReleasePushLockEx` at `0x14006313b`
- `ntoskrnl!ExReleasePushLockEx` at `0x140063151`
- `ntoskrnl!ExReleasePushLockEx` at `0x140063266`
- `ntoskrnl!ExReleasePushLockEx` at `0x140063321`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400633ec`
- `ntoskrnl!ExReleasePushLockEx` at `0x14006344c`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400634da`
- `ntoskrnl!ExReleasePushLockEx` at `0x14006313b`
- `ntoskrnl!ExReleasePushLockEx` at `0x140063151`
- `ntoskrnl!ExReleasePushLockEx` at `0x140063266`
- `ntoskrnl!ExReleasePushLockEx` at `0x140063321`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400633ec`
- `ntoskrnl!ExReleasePushLockEx` at `0x14006344c`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400634da`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400635a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400635a4`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140063198`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400631f7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400633a9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140063198`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400631f7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400633a9`

## pseudocode

```c
void __fastcall CmsContainerRangeMap::Merge(CmsContainerRangeMap *this, struct CmsContainerRangeMap *a2)
{
  CmsContainerRangeMap *v3; // r12
  unsigned int v4; // ebx
  int v5; // r9d
  unsigned int v6; // edi
  __int64 v7; // rdx
  char v8; // r9
  __int64 *v9; // rax
  __int64 v10; // rax
  bool v11; // zf
  __int64 *v12; // rax
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rax
  int v16; // r15d
  __int64 v17; // rdx
  __int64 v18; // rcx
  _QWORD *v19; // r12
  _QWORD *v20; // r13
  volatile signed __int32 *v21; // rax
  volatile signed __int32 *v22; // r12
  signed __int64 *v23; // rdx
  _QWORD *v24; // rdx
  __int64 v25; // rax
  __int64 v26; // r14
  struct _SLIST_ENTRY *v27; // r13
  struct _PAGED_LOOKASIDE_LIST *v28; // rcx
  _QWORD *v29; // rax
  _QWORD *v30; // rdx
  volatile signed __int32 *v31; // rax
  signed __int64 *v32; // rdx
  _QWORD *v33; // rax
  __int64 v34; // rcx
  signed __int64 v35; // rax
  signed __int64 v36; // rax
  signed __int64 v37; // rax
  signed __int64 v38; // rax
  __int64 v39; // [rsp+30h] [rbp-41h]
  __int128 v40; // [rsp+38h] [rbp-39h]
  __int128 v41; // [rsp+58h] [rbp-19h]
  int v43; // [rsp+E0h] [rbp+6Fh]
  __int64 v44; // [rsp+E8h] [rbp+77h]
  _QWORD *v45; // [rsp+E8h] [rbp+77h]
  _QWORD *v46; // [rsp+E8h] [rbp+77h]
  volatile signed __int32 **v47; // [rsp+E8h] [rbp+77h]
  _QWORD *v48; // [rsp+F0h] [rbp+7Fh]
  __int64 v49; // [rsp+F0h] [rbp+7Fh]

  v3 = this;
  *(_QWORD *)&v40 = 0;
  v41 = 0;
  if ( !*((_BYTE *)a2 + 54) )
    return;
  if ( !*((_BYTE *)this + 54) )
  {
    if ( this != a2 )
    {
      CmsHashTableLite::operator=();
      *(_QWORD *)(v18 + 32) = *(_QWORD *)(v17 + 32);
      *(_DWORD *)(v18 + 48) = *(_DWORD *)(v17 + 48);
      *(_BYTE *)(v18 + 52) = *(_BYTE *)(v17 + 52);
      *(_BYTE *)(v18 + 54) = *(_BYTE *)(v17 + 54);
      *(_BYTE *)(v18 + 53) = *(_BYTE *)(v17 + 53);
      *(_QWORD *)(v17 + 32) = 0;
      *(_BYTE *)(v17 + 54) = 0;
    }
    return;
  }
  v4 = 0;
  v5 = 0;
  v6 = 0;
  v43 = 0;
  while ( 2 )
  {
    if ( v5 == 1 )
    {
      v7 = 0;
      if ( *((_QWORD *)a2 + 2 * v6) )
      {
        v12 = 0;
        while ( 1 )
        {
          if ( !v12 )
            v12 = (__int64 *)(*((_QWORD *)a2 + 2 * v6) + 24LL * v4);
          if ( *v12 != *(_QWORD *)v40 )
            break;
          if ( ++v4 == *((_DWORD *)a2 + 4 * v6 + 2) )
          {
            if ( v6 || !*((_QWORD *)a2 + 2) )
              goto LABEL_44;
            v6 = 1;
            v4 = 0;
          }
          if ( !v4 )
            v4 = 0;
          while ( 1 )
          {
            v13 = *((_QWORD *)a2 + 2 * v6);
            v11 = *(_QWORD *)(v13 + 24LL * v4 + 8) == 0;
            v12 = (__int64 *)(v13 + 24LL * v4);
            if ( !v11 )
              break;
            if ( ++v4 == -1 || v4 == *((_DWORD *)a2 + 4 * v6 + 2) )
            {
              if ( v6 || !*((_QWORD *)a2 + 2) )
              {
                v7 = 0;
LABEL_44:
                v16 = -1073741197;
                goto LABEL_39;
              }
              v6 = 1;
              v4 = 0;
            }
          }
          v7 = *v12;
          if ( *v12 )
            goto LABEL_45;
        }
        v7 = *(_QWORD *)v40;
      }
LABEL_45:
      v16 = -1073741197;
      if ( v7 )
        v16 = 0;
      goto LABEL_39;
    }
    v6 = 0;
    v43 = 1;
    if ( !(*((_DWORD *)a2 + 3) + *((_DWORD *)a2 + 7)) )
    {
      v14 = *((_QWORD *)a2 + 2);
      v15 = 12;
      v16 = -1073741197;
      LOBYTE(v6) = v14 != 0;
      if ( v14 )
        v15 = 28;
      v4 = *(_DWORD *)((char *)a2 + v15);
      goto LABEL_40;
    }
    v7 = 0;
    v4 = 0;
    if ( !*(_QWORD *)a2 )
      goto LABEL_38;
    v8 = 1;
    v9 = 0;
    while ( 1 )
    {
      if ( (v8 & 4) == 0 )
        goto LABEL_9;
      if ( !v9 )
        v9 = (__int64 *)(*((_QWORD *)a2 + 2 * v6) + 24LL * v4);
      if ( *v9 != *(_QWORD *)v40 )
        break;
      if ( ++v4 == *((_DWORD *)a2 + 4 * v6 + 2) )
      {
        if ( v6 || !*((_QWORD *)a2 + 2) )
          goto LABEL_38;
        v6 = 1;
        v4 = 0;
      }
LABEL_9:
      if ( !v4 )
        v4 = 0;
      while ( 1 )
      {
        v10 = *((_QWORD *)a2 + 2 * v6);
        v11 = *(_QWORD *)(v10 + 24LL * v4 + 8) == 0;
        v9 = (__int64 *)(v10 + 24LL * v4);
        if ( !v11 )
          break;
        if ( ++v4 == -1 || v4 == *((_DWORD *)a2 + 4 * v6 + 2) )
        {
          if ( v6 || !*((_QWORD *)a2 + 2) )
          {
            v7 = 0;
            goto LABEL_38;
          }
          v6 = 1;
          v4 = 0;
        }
      }
      v7 = *v9;
      if ( *v9 )
        goto LABEL_85;
      v8 |= 4u;
    }
    v7 = *(_QWORD *)v40;
    if ( *(_QWORD *)v40 )
    {
LABEL_85:
      v16 = 0;
      goto LABEL_39;
    }
LABEL_38:
    v16 = -1073741197;
LABEL_39:
    *(_QWORD *)&v40 = v7;
LABEL_40:
    *((_QWORD *)&v40 + 1) = __PAIR64__(v4, v6);
    if ( (_QWORD)v41 )
    {
      v44 = *(_QWORD *)(v41 + 16);
      v19 = (_QWORD *)(*(_QWORD *)v3
                     + 24
                     * ((((unsigned int)(1103515245 * v44 + 12345) >> 16)
                       | (unsigned __int64)((69069 * (_DWORD)v44 + 1) & 0xFFFF0000))
                      % *((unsigned int *)v3 + 2)));
      v20 = v19 + 2;
      ExAcquirePushLockSharedEx(v19 + 2, 4);
      if ( v19[1] )
      {
        v21 = (volatile signed __int32 *)*v19;
        v22 = (volatile signed __int32 *)*v19;
        while ( *((_QWORD *)v22 + 2) != v44 )
        {
          v22 = *(volatile signed __int32 **)v22;
          if ( v22 == v21 )
            goto LABEL_57;
        }
        ExReleasePushLockEx(v20, 0);
        v23 = *(signed __int64 **)(v41 + 32);
        if ( v23 )
        {
          _m_prefetchw((const void *)(v22 + 6));
          do
          {
            v35 = *((_QWORD *)v22 + 3);
            *v23 = v35;
            v36 = _InterlockedCompareExchange64((volatile signed __int64 *)v22 + 3, *(_QWORD *)(v41 + 24), v35);
          }
          while ( v36 != *v23 );
          if ( !v36 )
            *((_QWORD *)v22 + 4) = *(_QWORD *)(v41 + 32);
          if ( (*(_DWORD *)(v41 + 44) & 1) != 0 )
            _InterlockedOr(v22 + 11, 1u);
          _InterlockedAdd(v22 + 10, *(_DWORD *)(v41 + 40));
          _InterlockedAdd64((volatile signed __int64 *)this + 4, *(int *)(v41 + 40));
          *(_QWORD *)(v41 + 24) = 0;
          *(_QWORD *)(v41 + 32) = 0;
          *(_QWORD *)(v41 + 40) = 0;
        }
      }
      else
      {
LABEL_57:
        ExReleasePushLockEx(v20, 0);
        v22 = (volatile signed __int32 *)v41;
      }
      v45 = (_QWORD *)(*((_QWORD *)a2 + 2 * DWORD2(v41)) + 24LL * HIDWORD(v41));
      ExAcquirePushLockExclusiveEx(v45 + 2, 0);
      v24 = *(_QWORD **)(v41 + 8);
      v25 = *(_QWORD *)v41;
      *v24 = *(_QWORD *)v41;
      *(_QWORD *)(v25 + 8) = v24;
      if ( *v45 == (_QWORD)v41 )
        *v45 = v25;
      if ( v24 == (_QWORD *)v41 )
        *v45 = 0;
      --v45[1];
      _InterlockedDecrement((volatile signed __int32 *)a2 + 4 * DWORD2(v41) + 3);
      ExReleasePushLockEx(v45 + 2, 0);
      if ( v22 == (volatile signed __int32 *)v41 )
      {
        v39 = *(_QWORD *)(v41 + 16);
        v48 = (_QWORD *)(*(_QWORD *)this
                       + 24
                       * (((69069 * (_DWORD)v39 + 1) & 0xFFFF0000
                         | (unsigned __int64)((unsigned int)(1103515245 * v39 + 12345) >> 16))
                        % *((unsigned int *)this + 2)));
        v46 = v48 + 2;
        ExAcquirePushLockExclusiveEx(v48 + 2, 0);
        if ( v48[1] )
        {
          v33 = (_QWORD *)*v48;
          while ( v33[2] != v39 )
          {
            v33 = (_QWORD *)*v33;
            if ( v33 == (_QWORD *)*v48 )
              goto LABEL_78;
          }
          ExReleasePushLockEx(v46, 0);
          v49 = *(_QWORD *)(v41 + 16);
          v47 = (volatile signed __int32 **)(*(_QWORD *)this
                                           + 24
                                           * (((69069 * (_DWORD)v49 + 1) & 0xFFFF0000
                                             | (unsigned __int64)((unsigned int)(1103515245 * v49 + 12345) >> 16))
                                            % *((unsigned int *)this + 2)));
          ExAcquirePushLockSharedEx(v47 + 2, 4);
          if ( v47[1] )
          {
            v31 = *v47;
            while ( *((_QWORD *)v31 + 2) != v49 )
            {
              v31 = *(volatile signed __int32 **)v31;
              if ( v31 == *v47 )
                goto LABEL_92;
            }
            v22 = v31;
          }
LABEL_92:
          ExReleasePushLockEx(v47 + 2, 0);
          v32 = *(signed __int64 **)(v41 + 32);
          if ( v32 )
          {
            _m_prefetchw((const void *)(v22 + 6));
            do
            {
              v37 = *((_QWORD *)v22 + 3);
              *v32 = v37;
              v38 = _InterlockedCompareExchange64((volatile signed __int64 *)v22 + 3, *(_QWORD *)(v41 + 24), v37);
            }
            while ( v38 != *v32 );
            if ( !v38 )
              *((_QWORD *)v22 + 4) = *(_QWORD *)(v41 + 32);
            if ( (*(_DWORD *)(v41 + 44) & 1) != 0 )
              _InterlockedOr(v22 + 11, 1u);
            _InterlockedAdd(v22 + 10, *(_DWORD *)(v41 + 40));
            v3 = this;
            _InterlockedAdd64((volatile signed __int64 *)this + 4, *(int *)(v41 + 40));
            *(_QWORD *)(v41 + 24) = 0;
            *(_QWORD *)(v41 + 32) = 0;
            *(_QWORD *)(v41 + 40) = 0;
          }
          else
          {
            v3 = this;
          }
          CmsLookasides::Free((_QWORD *)v41);
        }
        else
        {
LABEL_78:
          v29 = (_QWORD *)*v48;
          if ( *v48 )
          {
            v30 = (_QWORD *)v29[1];
            if ( (_QWORD *)*v30 != v29 )
              __fastfail(3u);
            *(_QWORD *)v41 = v29;
            *(_QWORD *)(v41 + 8) = v30;
            *v30 = v41;
            v29[1] = v41;
          }
          else
          {
            *(_QWORD *)(v41 + 8) = v41;
            *(_QWORD *)v41 = v41;
            *v48 = v41;
          }
          ++v48[1];
          v3 = this;
          _InterlockedIncrement((volatile signed __int32 *)this + 3);
          ExReleasePushLockEx(v46, 0);
          _InterlockedAdd64((volatile signed __int64 *)this + 4, *(int *)(v41 + 40));
        }
        goto LABEL_41;
      }
      v26 = *(_QWORD *)(v41 - 16);
      v27 = (struct _SLIST_ENTRY *)(v41 - 16);
      if ( v26 )
      {
        if ( *(_BYTE *)(v26 + 8) )
        {
          v28 = (struct _PAGED_LOOKASIDE_LIST *)(v26 + 64);
          if ( !*(_BYTE *)(v26 + 9) )
          {
            ExFreeToPagedLookasideList(v28, v27);
            v3 = this;
            goto LABEL_41;
          }
          ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v28, v27);
LABEL_68:
          v3 = this;
          goto LABEL_41;
        }
        v34 = *(_QWORD *)(v26 + 88);
        if ( (int)v34 < *(_DWORD *)(v26 + 80) || SHIDWORD(v34) >= (int)v34 )
        {
          ExpInterlockedPushEntrySList((PSLIST_HEADER)(v26 + 64), v27);
          _InterlockedIncrement((volatile signed __int32 *)(v26 + 88));
          goto LABEL_68;
        }
      }
      ExFreePoolWithTag(v27, 0);
      goto LABEL_68;
    }
LABEL_41:
    v41 = v40;
    if ( !v16 )
    {
      v5 = v43;
      continue;
    }
    break;
  }
  v11 = *((_BYTE *)a2 + 53) == 0;
  *((_QWORD *)a2 + 4) = 0;
  if ( !v11 )
    CmsContainerRangeMap::UninitializeMap(a2);
}

```

## disassembly

```asm
0x140062df0  mov     rax, rsp
0x140062df3  mov     [rax+8], rcx
0x140062df7  push    rbp
0x140062df8  push    rsi
0x140062df9  push    r12
0x140062dfb  lea     rbp, [rax-5Fh]
0x140062dff  sub     rsp, 0B0h
0x140062e06  cmp     byte ptr [rdx+36h], 0
0x140062e0a  xorps   xmm0, xmm0
0x140062e0d  movaps  xmmword ptr [rax-58h], xmm6
0x140062e11  mov     rsi, rdx
0x140062e14  xorps   xmm6, xmm6
0x140062e17  mov     r12, rcx
0x140062e1a  movups  [rbp+57h+var_90], xmm6
0x140062e1e  movups  [rbp+57h+var_80], xmm6
0x140062e22  movups  [rbp+57h+var_70], xmm0
0x140062e26  jz      loc_140062F3F
0x140062e2c  cmp     byte ptr [rcx+36h], 0
0x140062e30  jz      loc_14006307F
0x140062e36  mov     [rax-20h], rbx
0x140062e3a  xor     r10d, r10d
0x140062e3d  mov     ebx, dword ptr [rbp+57h+var_90+0Ch]
0x140062e40  mov     r9d, r10d
0x140062e43  mov     [rax-28h], rdi
0x140062e47  mov     edi, dword ptr [rbp+57h+var_90+8]
0x140062e4a  mov     [rax-30h], r13
0x140062e4e  mov     [rax-38h], r14
0x140062e52  mov     [rax-40h], r15
0x140062e56  mov     [rbp+57h+arg_8], r10d
0x140062e5a  mov     edx, 1Ch
0x140062e5f  cmp     r9d, 1
0x140062e63  jz      loc_140062F51
0x140062e69  mov     eax, [rsi+1Ch]
0x140062e6c  mov     edi, r10d
0x140062e6f  mov     [rbp+57h+arg_8], 1
0x140062e76  add     eax, [rsi+0Ch]
0x140062e79  jz      loc_140062FE1
0x140062e7f  cmp     qword ptr [rsi], 0
0x140062e83  mov     rdx, r10
0x140062e86  mov     qword ptr [rbp+57h+var_90+8], 0
0x140062e8e  mov     ebx, r10d
0x140062e91  mov     qword ptr [rbp+57h+var_80], r10
0x140062e95  jz      loc_140063006
0x140062e9b  mov     r11, qword ptr [rbp+57h+var_90]
0x140062e9f  mov     r9d, 1
0x140062ea5  mov     rax, r10
0x140062ea8  test    r9b, 4
0x140062eac  jnz     loc_1400632C6
0x140062eb2  test    ebx, ebx
0x140062eb4  cmovz   ebx, r10d
0x140062eb8  nop     dword ptr [rax+rax+00000000h]
0x140062ec0  mov     eax, ebx
0x140062ec2  mov     edx, edi
0x140062ec4  add     rdx, rdx
0x140062ec7  lea     rcx, [rax+rax*2]
0x140062ecb  mov     rax, [rsi+rdx*8]
0x140062ecf  cmp     qword ptr [rax+rcx*8+8], 0
0x140062ed5  lea     rax, [rax+rcx*8]
0x140062ed9  jnz     loc_14006306A
0x140062edf  inc     ebx
0x140062ee1  cmp     ebx, 0FFFFFFFFh
0x140062ee4  jnb     short loc_140062EEC
0x140062ee6  cmp     ebx, [rsi+rdx*8+8]
0x140062eea  jnz     short loc_140062EC0
0x140062eec  test    edi, edi
0x140062eee  jnz     loc_140063003
0x140062ef4  cmp     qword ptr [rsi+10h], 0
0x140062ef9  jz      loc_140063003
0x140062eff  mov     edi, 1
0x140062f04  mov     ebx, r10d
0x140062f07  jmp     short loc_140062EC0
0x140062f09  cmp     byte ptr [rsi+35h], 0
0x140062f0d  mov     [rsi+20h], r10
0x140062f11  jnz     loc_1400635B5
0x140062f17  mov     r15, [rsp+0C0h+var_38]
0x140062f1f  mov     r13, [rsp+0C0h+var_28]
0x140062f27  mov     rdi, [rsp+0C0h+var_20]
0x140062f2f  mov     rbx, [rsp+0A8h]
0x140062f37  mov     r14, [rsp+0C0h+var_30]
0x140062f3f  movaps  xmm6, [rsp+0C0h+var_58+8]
0x140062f44  add     rsp, 0B0h
0x140062f4b  pop     r12
0x140062f4d  pop     rsi
0x140062f4e  pop     rbp
0x140062f4f  retn
0x140062f51  mov     eax, edi
0x140062f53  mov     rdx, r10
0x140062f56  add     rax, rax
0x140062f59  cmp     qword ptr [rsi+rax*8], 0
0x140062f5e  jz      loc_14006304C
0x140062f64  mov     r11, qword ptr [rbp+57h+var_90]
0x140062f68  mov     rax, r10
0x140062f6b  mov     r8d, edi
0x140062f6e  add     r8, r8
0x140062f71  test    rax, rax
0x140062f74  jz      loc_140063507
0x140062f7a  mov     rcx, [r11]
0x140062f7d  cmp     [rax], rcx
0x140062f80  jnz     loc_14006353A
0x140062f86  inc     ebx
0x140062f88  cmp     ebx, [rsi+r8*8+8]
0x140062f8d  jz      loc_14006351A
0x140062f93  test    ebx, ebx
0x140062f95  cmovz   ebx, r10d
0x140062f99  nop     dword ptr [rax+00000000h]
0x140062fa0  mov     eax, ebx
0x140062fa2  mov     edx, edi
0x140062fa4  add     rdx, rdx
0x140062fa7  lea     rcx, [rax+rax*2]
0x140062fab  mov     rax, [rsi+rdx*8]
0x140062faf  cmp     qword ptr [rax+rcx*8+8], 0
0x140062fb5  lea     rax, [rax+rcx*8]
0x140062fb9  jnz     loc_14006305C
0x140062fbf  inc     ebx
0x140062fc1  cmp     ebx, 0FFFFFFFFh
0x140062fc4  jnb     short loc_140062FCC
0x140062fc6  cmp     ebx, [rsi+rdx*8+8]
0x140062fca  jnz     short loc_140062FA0
0x140062fcc  test    edi, edi
0x140062fce  jnz     short loc_140063041
0x140062fd0  cmp     qword ptr [rsi+10h], 0
0x140062fd5  jz      short loc_140063041
0x140062fd7  mov     edi, 1
0x140062fdc  mov     ebx, r10d
0x140062fdf  jmp     short loc_140062FA0
0x140062fe1  mov     rcx, [rsi+10h]
0x140062fe5  mov     eax, 0Ch
0x140062fea  test    rcx, rcx
0x140062fed  mov     r15d, 0C0000273h
0x140062ff3  setnz   dil
0x140062ff7  test    rcx, rcx
0x140062ffa  cmovnz  rax, rdx
0x140062ffe  mov     ebx, [rax+rsi]
0x140063001  jmp     short loc_140063014
0x140063003  mov     rdx, r10
0x140063006  mov     r15d, 0C0000273h
0x14006300c  movups  xmm6, [rbp+57h+var_80]
0x140063010  mov     qword ptr [rbp+57h+var_90], rdx
0x140063014  mov     r14, qword ptr [rbp+57h+var_70]
0x140063018  mov     dword ptr [rbp+57h+var_90+8], edi
0x14006301b  mov     dword ptr [rbp+57h+var_90+0Ch], ebx
0x14006301e  test    r14, r14
0x140063021  jnz     loc_1400630C1
0x140063027  movups  xmm0, [rbp+57h+var_90]
0x14006302b  movups  [rbp+57h+var_70], xmm0
0x14006302f  test    r15d, r15d
0x140063032  jnz     loc_140062F09
0x140063038  mov     r9d, [rbp+57h+arg_8]
0x14006303c  jmp     loc_140062E5A
0x140063041  mov     rdx, r10
0x140063044  mov     r15d, 0C0000273h
0x14006304a  jmp     short loc_140063010
0x14006304c  mov     r15d, 0C0000273h
0x140063052  test    rdx, rdx
0x140063055  jz      short loc_140063010
0x140063057  mov     r15d, r10d
0x14006305a  jmp     short loc_140063010
0x14006305c  mov     rdx, [rax]
0x14006305f  test    rdx, rdx
0x140063062  jz      loc_140062F6B
0x140063068  jmp     short loc_14006304C
0x14006306a  mov     rdx, [rax]
0x14006306d  test    rdx, rdx
0x140063070  jnz     loc_14006343E
0x140063076  or      r9d, 4
0x14006307a  jmp     loc_140062EA8
0x14006307f  cmp     rcx, rsi
0x140063082  jz      loc_140062F3F
0x140063088  call    ??4CmsHashTableLite@@QEAAAEAV0@$$QEAV0@@Z; CmsHashTableLite::operator=(CmsHashTableLite &&)
0x14006308d  mov     rax, [rdx+20h]
0x140063091  mov     [rcx+20h], rax
0x140063095  mov     eax, [rdx+30h]
0x140063098  mov     [rcx+30h], eax
0x14006309b  movzx   eax, byte ptr [rdx+34h]
0x14006309f  mov     [rcx+34h], al
0x1400630a2  movzx   eax, byte ptr [rdx+36h]
0x1400630a6  mov     [rcx+36h], al
0x1400630a9  movzx   eax, byte ptr [rdx+35h]
0x1400630ad  mov     [rcx+35h], al
0x1400630b0  mov     qword ptr [rdx+20h], 0
0x1400630b8  mov     byte ptr [rdx+36h], 0
0x1400630bc  jmp     loc_140062F3F
0x1400630c1  mov     rcx, [r14+10h]
0x1400630c5  xor     edx, edx
0x1400630c7  imul    eax, ecx, 10DCDh
0x1400630cd  mov     [rbp+57h+arg_10], rcx
0x1400630d1  imul    ecx, 41C64E6Dh
0x1400630d7  inc     eax
0x1400630d9  and     eax, 0FFFF0000h
0x1400630de  add     ecx, 3039h
0x1400630e4  shr     ecx, 10h
0x1400630e7  or      eax, ecx
0x1400630e9  div     dword ptr [r12+8]
0x1400630ee  mov     rax, [r12]
0x1400630f2  lea     rdx, [rdx+rdx*2]
0x1400630f6  lea     r12, [rax+rdx*8]
0x1400630fa  mov     edx, 4
0x1400630ff  lea     r13, [r12+10h]
0x140063104  mov     rcx, r13
0x140063107  call    cs:__imp_ExAcquirePushLockSharedEx
0x14006310e  nop     dword ptr [rax+rax+00h]
0x140063113  cmp     qword ptr [r12+8], 0
0x140063119  jbe     short loc_140063136
0x14006311b  mov     rax, [r12]
0x14006311f  mov     rcx, [rbp+57h+arg_10]
0x140063123  mov     r12, rax
0x140063126  cmp     [r12+10h], rcx
0x14006312b  jz      short loc_14006314C
0x14006312d  mov     r12, [r12]
0x140063131  cmp     r12, rax
0x140063134  jnz     short loc_140063126
0x140063136  xor     edx, edx
0x140063138  mov     rcx, r13
0x14006313b  call    cs:__imp_ExReleasePushLockEx
0x140063142  nop     dword ptr [rax+rax+00h]
0x140063147  mov     r12, r14
0x14006314a  jmp     short loc_14006316A
0x14006314c  xor     edx, edx
0x14006314e  mov     rcx, r13
0x140063151  call    cs:__imp_ExReleasePushLockEx
0x140063158  nop     dword ptr [rax+rax+00h]
0x14006315d  mov     rdx, [r14+20h]
0x140063161  test    rdx, rdx
0x140063164  jnz     loc_14006355D
0x14006316a  mov     rax, [r14+10h]
0x14006316e  mov     [rbp+57h+arg_18], rax
0x140063172  mov     rax, qword ptr [rbp+57h+var_70+8]
0x140063176  mov     edx, eax
0x140063178  add     rdx, rdx
0x14006317b  mov     [rbp+57h+var_A0], rax
0x14006317f  mov     eax, dword ptr [rbp+57h+var_70+0Ch]
0x140063182  lea     rcx, [rax+rax*2]
0x140063186  mov     rax, [rsi+rdx*8]
0x14006318a  lea     rdx, [rax+rcx*8]
0x14006318e  mov     [rbp+57h+arg_10], rdx
0x140063192  lea     rcx, [rdx+10h]
0x140063196  xor     edx, edx
0x140063198  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14006319f  nop     dword ptr [rax+rax+00h]
0x1400631a4  mov     r13, r14
0x1400631a7  test    r14, r14
0x1400631aa  jnz     loc_14006340C
0x1400631b0  mov     rcx, [rbp+57h+arg_18]
0x1400631b4  xor     edx, edx
0x1400631b6  imul    eax, ecx, 10DCDh
0x1400631bc  imul    ecx, 41C64E6Dh
0x1400631c2  mov     dword ptr [rbp+57h+var_A0], r14d
0x1400631c6  inc     eax
0x1400631c8  and     eax, 0FFFF0000h
0x1400631cd  add     ecx, 3039h
0x1400631d3  shr     ecx, 10h
0x1400631d6  or      eax, ecx
0x1400631d8  div     dword ptr [rsi+8]
0x1400631db  mov     rax, [rsi]
0x1400631de  lea     rdx, [rdx+rdx*2]
0x1400631e2  lea     rdx, [rax+rdx*8]
0x1400631e6  lea     rax, [rdx+10h]
0x1400631ea  mov     [rbp+57h+arg_10], rdx
0x1400631ee  mov     rcx, rax
0x1400631f1  mov     [rbp+57h+var_98], rax
0x1400631f5  xor     edx, edx
0x1400631f7  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400631fe  nop     dword ptr [rax+rax+00h]
0x140063203  mov     rcx, [rbp+57h+arg_10]
0x140063207  cmp     [rcx+8], r14
0x14006320b  jbe     loc_14006331B
0x140063211  mov     rax, [rcx]
0x140063214  mov     rdx, [rbp+57h+arg_18]
0x140063218  mov     r13, rax
0x14006321b  cmp     [r13+10h], rdx
0x14006321f  jnz     loc_14006330E
0x140063225  test    r13, r13
0x140063228  jz      loc_14006332D
0x14006322e  mov     rdx, [r13+8]
0x140063232  mov     rax, [r13+0]
0x140063236  mov     [rdx], rax
0x140063239  mov     [rax+8], rdx
0x14006323d  cmp     [rcx], r13
0x140063240  jnz     short loc_140063245
0x140063242  mov     [rcx], rax
0x140063245  cmp     rdx, r13
0x140063248  jz      loc_14006334D
0x14006324e  dec     qword ptr [rcx+8]
0x140063252  xor     edx, edx
0x140063254  mov     eax, dword ptr [rbp+57h+var_A0]
0x140063257  nop
0x140063258  shl     rax, 4
0x14006325c  add     rcx, 10h
0x140063260  lock dec dword ptr [rax+rsi+0Ch]
0x140063265  nop
0x140063266  call    cs:__imp_ExReleasePushLockEx
0x14006326d  nop     dword ptr [rax+rax+00h]
0x140063272  cmp     r12, r14
0x140063275  jz      loc_140063359
0x14006327b  test    r13, r13
0x14006327e  jz      short loc_1400632BA
0x140063280  mov     r14, [r13-10h]
0x140063284  add     r13, 0FFFFFFFFFFFFFFF0h
0x140063288  test    r14, r14
0x14006328b  jz      loc_14006359F
  ... truncated ...
```
