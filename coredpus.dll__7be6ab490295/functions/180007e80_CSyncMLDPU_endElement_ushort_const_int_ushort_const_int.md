# CSyncMLDPU::endElement(ushort const *,int,ushort const *,int)

- ea: `0x180007e80`
- end: `0x180008613`
- name: `?endElement@CSyncMLDPU@@AEAAJPEBGH0H@Z`
- size: `1939`
- prototype: `__int64 __fastcall(CSyncMLDPU *__hidden this, const unsigned __int16 *, int, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180007820`
- `0x18001c2d4`

## callees

- `0x180003260`
- `0x180007e80`
- `0x18000d510`
- `0x1800128a0`
- `0x180014330`
- `0x1800146e4`
- `0x180014c60`
- `0x180015c87`
- `0x180016700`
- `0x18001d670`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000807e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180008209`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800085c6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000807e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180008209`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800085c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800084ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800084ea`

## pseudocode

```c
__int64 __fastcall CSyncMLDPU::endElement(
        CSyncMLDPU *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        unsigned int a5)
{
  const unsigned __int16 *v5; // rsi
  CSyncMLDPU *v7; // rbx
  int v8; // r14d
  unsigned int v9; // eax
  const unsigned __int16 *v10; // r13
  unsigned int v11; // r12d
  __int64 v12; // rax
  __int64 v13; // rcx
  int v14; // edx
  int v15; // eax
  __int64 v16; // rax
  const OLECHAR *v17; // r8
  __int64 v18; // rcx
  int v19; // edx
  const OLECHAR *v20; // rcx
  int v21; // eax
  int v22; // eax
  int v23; // edx
  _WORD *v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rcx
  char *v27; // r15
  char *v28; // rcx
  __int64 v29; // rax
  __int64 v30; // r13
  unsigned __int64 v31; // rcx
  unsigned __int64 v32; // rdx
  unsigned __int64 v33; // r12
  size_t v34; // r12
  char *v35; // rsi
  void *v36; // rax
  char *v37; // r8
  char *v38; // rdx
  char *v39; // rcx
  size_t v40; // r8
  __int64 v41; // rcx
  const struct std::nothrow_t *v42; // rdx
  void *v43; // rax
  __int64 v44; // r10
  CSyncMLItem *v45; // r10
  __int64 v46; // r10
  __int64 v48; // rbx
  __int64 v49; // rcx
  unsigned int v50; // [rsp+50h] [rbp-F8h] BYREF
  unsigned int v51; // [rsp+54h] [rbp-F4h] BYREF
  int v52; // [rsp+58h] [rbp-F0h] BYREF
  unsigned int v53; // [rsp+5Ch] [rbp-ECh] BYREF
  unsigned int v54; // [rsp+60h] [rbp-E8h] BYREF
  unsigned int v55; // [rsp+64h] [rbp-E4h]
  EVENT_DESCRIPTOR v56; // [rsp+68h] [rbp-E0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+78h] [rbp-D0h] BYREF
  const unsigned __int16 *v58; // [rsp+88h] [rbp-C0h]
  __int64 v59; // [rsp+90h] [rbp-B8h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+A0h] [rbp-A8h] BYREF
  char *v61; // [rsp+B0h] [rbp-98h]
  int v62; // [rsp+B8h] [rbp-90h]
  int v63; // [rsp+BCh] [rbp-8Ch]
  unsigned int *v64; // [rsp+C0h] [rbp-88h]
  __int64 v65; // [rsp+C8h] [rbp-80h]
  const unsigned __int16 *v66; // [rsp+D0h] [rbp-78h]
  int v67; // [rsp+D8h] [rbp-70h]
  int v68; // [rsp+DCh] [rbp-6Ch]
  unsigned int *v69; // [rsp+E0h] [rbp-68h]
  __int64 v70; // [rsp+E8h] [rbp-60h]
  const unsigned __int16 *v71; // [rsp+F0h] [rbp-58h]
  int v72; // [rsp+F8h] [rbp-50h]
  int v73; // [rsp+FCh] [rbp-4Ch]

  v5 = a4;
  v50 = a3;
  v7 = this;
  *(_QWORD *)&EventDescriptor.Id = this;
  v8 = 0;
  v51 = 73;
  v52 = 73;
  v9 = *((_DWORD *)this + 56);
  if ( v9 >= 2 )
    v51 = *((_DWORD *)this + v9 + 22);
  v10 = 0;
  v58 = 0;
  v11 = 0;
  v59 = 0;
  if ( *((_DWORD *)this + 60) )
  {
    if ( (unsigned int)dword_18003E048 > 5 )
    {
      v51 = a5;
      v53 = a3;
      v12 = -1;
      if ( a4 )
      {
        v13 = -1;
        do
          ++v13;
        while ( a4[v13] );
        v14 = 2 * v13 + 2;
      }
      else
      {
        v5 = &word_180032B28;
        v14 = 2;
      }
      v71 = v5;
      v72 = v14;
      v73 = 0;
      v69 = &v51;
      v70 = 4;
      if ( a2 )
      {
        do
          ++v12;
        while ( a2[v12] );
        v15 = 2 * v12 + 2;
      }
      else
      {
        a2 = &word_180032B28;
        v15 = 2;
      }
      v66 = a2;
      v67 = v15;
      v68 = 0;
      v64 = &v53;
      v65 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 5;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_18003E050;
      UserData.Size = (unsigned __int16)*off_18003E050;
      UserData.Reserved = 2;
      v61 = &byte_180035D87;
      v62 = 83;
      v63 = 1;
      v54 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
    }
    --*((_DWORD *)v7 + 60);
    goto LABEL_73;
  }
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v54 = a5;
    v53 = a3;
    v16 = -1;
    if ( a4 )
    {
      v17 = a4;
      v18 = -1;
      do
        ++v18;
      while ( a4[v18] );
      v19 = 2 * v18 + 2;
      v20 = &word_180032B28;
    }
    else
    {
      v20 = &word_180032B28;
      v17 = &word_180032B28;
      v19 = 2;
    }
    v71 = v17;
    v72 = v19;
    v73 = 0;
    v69 = &v54;
    v70 = 4;
    if ( a2 )
    {
      v20 = a2;
      do
        ++v16;
      while ( a2[v16] );
      v21 = 2 * v16 + 2;
    }
    else
    {
      v21 = 2;
    }
    v66 = v20;
    v67 = v21;
    v68 = 0;
    v64 = &v53;
    v65 = 4;
    *(_DWORD *)&v56.Id = 184549376;
    *(_DWORD *)&v56.Level = 5;
    v56.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    UserData.Size = (unsigned __int16)*off_18003E050;
    UserData.Reserved = 2;
    v61 = byte_1800360AB;
    v62 = 82;
    v63 = 1;
    v55 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &v56, 0, 0, 6u, &UserData);
  }
  v22 = *((_DWORD *)v7 + 56);
  if ( !v22 )
  {
    v8 = -2147024809;
    goto LABEL_73;
  }
  v23 = *((_DWORD *)v7 + (unsigned int)(v22 - 1) + 24);
  v52 = v23;
  v24 = (_WORD *)*((_QWORD *)v7 + 42);
  if ( v24 )
  {
    if ( v23 == 21 )
    {
      v10 = (const unsigned __int16 *)*((_QWORD *)v7 + 42);
      v25 = 0x7FFFFFFF;
      while ( *v24 )
      {
        ++v24;
        if ( !--v25 )
        {
          v8 = -2147024809;
          v11 = 0;
          goto LABEL_39;
        }
      }
      v11 = 0x7FFFFFFF - v25;
LABEL_39:
      if ( v8 < 0 )
        goto LABEL_73;
    }
    else
    {
      v8 = TrimString(*((unsigned __int16 **)v7 + 42));
      if ( v8 < 0 )
        goto LABEL_73;
      v23 = v52;
      v10 = v58;
      v11 = v59;
    }
  }
  --*((_DWORD *)v7 + 56);
  v26 = *((_QWORD *)v7 + 8);
  if ( v26 )
  {
    v8 = CSyncMLCmd::EndElement(v26, (__int64)a2, v50, v5, a5, v51, v10, v11, &v52);
    if ( v8 < 0 || *((_DWORD *)v7 + 57) != *((_DWORD *)v7 + 56) )
      goto LABEL_73;
    v27 = (char *)*((_QWORD *)v7 + 10);
    v28 = (char *)*((_QWORD *)v7 + 11);
    if ( v27 != v28 )
    {
      *(_QWORD *)v27 = *((_QWORD *)v7 + 8);
      *((_QWORD *)v7 + 10) += 8LL;
LABEL_68:
      *((_QWORD *)v7 + 8) = 0;
      goto LABEL_73;
    }
    try
    {
      v29 = *((_QWORD *)v7 + 9);
      v30 = (__int64)&v27[-v29] >> 3;
      if ( v30 == 0x1FFFFFFFFFFFFFFFLL )
        std::vector<CSyncMLCmd *>::_Xlength();
      v31 = (__int64)&v28[-v29] >> 3;
      v32 = v31 >> 1;
      if ( v31 <= 0x1FFFFFFFFFFFFFFFLL - (v31 >> 1) )
      {
        v33 = v30 + 1;
        if ( v32 + v31 >= v30 + 1 )
          v33 = v32 + v31;
        if ( v33 > 0x1FFFFFFFFFFFFFFFLL )
          std::_Throw_bad_array_new_length();
        v34 = 8 * v33;
        if ( !v34 )
        {
          v35 = 0;
          goto LABEL_57;
        }
        if ( v34 < 0x1000 )
        {
          v35 = (char *)operator new(v34);
          goto LABEL_57;
        }
        if ( v34 + 39 >= v34 )
        {
          v36 = operator new(v34 + 39);
          if ( !v36 )
            goto LABEL_64;
          v35 = (char *)(((unsigned __int64)v36 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
          *((_QWORD *)v35 - 1) = v36;
LABEL_57:
          *(_QWORD *)&v35[8 * v30] = *((_QWORD *)v7 + 8);
          v37 = (char *)*((_QWORD *)v7 + 10);
          v38 = (char *)*((_QWORD *)v7 + 9);
          v39 = v35;
          if ( v27 == v37 )
          {
            v40 = v37 - v38;
          }
          else
          {
            memmove_0(v35, v38, v27 - v38);
            v40 = *((_QWORD *)v7 + 10) - (_QWORD)v27;
            v39 = &v35[8 * v30 + 8];
            v38 = v27;
          }
          memmove_0(v39, v38, v40);
          v41 = *((_QWORD *)v7 + 9);
          if ( !v41 )
            goto LABEL_67;
          v42 = (const struct std::nothrow_t *)(8 * ((*((_QWORD *)v7 + 11) - v41) >> 3));
          if ( (unsigned __int64)v42 < 0x1000 )
          {
            v43 = (void *)*((_QWORD *)v7 + 9);
            goto LABEL_66;
          }
          v43 = *(void **)(v41 - 8);
          if ( (unsigned __int64)(v41 - (_QWORD)v43 - 8) <= 0x1F )
          {
            v42 = (const struct std::nothrow_t *)((char *)v42 + 39);
LABEL_66:
            operator delete(v43, v42);
LABEL_67:
            *((_QWORD *)v7 + 9) = v35;
            *((_QWORD *)v7 + 10) = &v35[8 * v30 + 8];
            *((_QWORD *)v7 + 11) = &v35[v34];
            goto LABEL_92;
          }
LABEL_64:
          __fastfail(5u);
        }
      }
      std::_Throw_bad_array_new_length();
    }
    catch ( std::bad_alloc )
    {
      v48 = *(_QWORD *)&EventDescriptor.Id;
      v49 = *(_QWORD *)(*(_QWORD *)&EventDescriptor.Id + 64LL);
      if ( v49 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v49 + 40LL))(v49, 1);
      *(_QWORD *)(v48 + 64) = 0;
      v50 = -2147024882;
      v8 = -2147024882;
      v7 = *(CSyncMLDPU **)&EventDescriptor.Id;
      goto LABEL_73;
    }
LABEL_92:
    goto LABEL_68;
  }
  if ( v23 && v23 != 2 && v23 != 8 )
    v8 = -2102788095;
LABEL_73:
  v44 = *((_QWORD *)v7 + 8);
  if ( !v44
    || (v45 = *(CSyncMLItem **)(v44 + 120)) == 0
    || !(unsigned int)CSyncMLItem::IsDataTypeXML(v45)
    || !*(_DWORD *)(v46 + 112) )
  {
    LocalFree(*((HLOCAL *)v7 + 42));
    *((_QWORD *)v7 + 42) = 0;
  }
  if ( v8 < 0 && (unsigned int)dword_18003E048 > 2 )
  {
    v50 = v8;
    v64 = &v50;
    v65 = 4;
    *(_DWORD *)&v56.Id = 184549376;
    *(_DWORD *)&v56.Level = 2;
    v56.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    UserData.Size = (unsigned __int16)*off_18003E050;
    UserData.Reserved = 2;
    v61 = (char *)&dword_180035F2C;
    v62 = 40;
    v63 = 1;
    v55 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &v56, 0, 0, 3u, &UserData);
  }
  if ( !*((_DWORD *)v7 + 7) )
    return 0;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180007e80  push    rbx
0x180007e82  push    rsi
0x180007e83  push    rdi
0x180007e84  push    r12
0x180007e86  push    r13
0x180007e88  push    r14
0x180007e8a  push    r15
0x180007e8c  sub     rsp, 110h
0x180007e93  mov     rax, cs:__security_cookie
0x180007e9a  xor     rax, rsp
0x180007e9d  mov     [rsp+148h+var_48], rax
0x180007ea5  mov     rsi, r9
0x180007ea8  mov     [rsp+148h+var_F8], r8d
0x180007ead  mov     r15, rdx
0x180007eb0  mov     rbx, rcx
0x180007eb3  mov     qword ptr [rsp+148h+EventDescriptor.Id], rcx
0x180007eb8  xor     edi, edi
0x180007eba  mov     r14d, edi
0x180007ebd  mov     ecx, 49h ; 'I'
0x180007ec2  mov     [rsp+148h+var_F4], ecx
0x180007ec6  mov     [rsp+148h+var_F0], ecx
0x180007eca  mov     eax, [rbx+0E0h]
0x180007ed0  cmp     eax, 2
0x180007ed3  jb      short loc_180007EE0
0x180007ed5  add     eax, 0FFFFFFFEh
0x180007ed8  mov     eax, [rbx+rax*4+60h]
0x180007edc  mov     [rsp+148h+var_F4], eax
0x180007ee0  mov     r13, rdi
0x180007ee3  mov     [rsp+148h+var_C0], rdi
0x180007eeb  mov     r12, rdi
0x180007eee  mov     [rsp+148h+var_B8], rdi
0x180007ef6  cmp     [rbx+0F0h], edi
0x180007efc  mov     eax, cs:dword_18003E048
0x180007f02  jbe     loc_180008095
0x180007f08  cmp     eax, 5
0x180007f0b  jbe     loc_18000808A
0x180007f11  mov     eax, [rsp+148h+arg_20]
0x180007f18  mov     [rsp+148h+var_F4], eax
0x180007f1c  mov     [rsp+148h+var_EC], r8d
0x180007f21  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180007f28  test    rsi, rsi
0x180007f2b  jz      short loc_180007F4B
0x180007f2d  mov     rcx, rax
0x180007f30  lea     rcx, [rcx+1]
0x180007f34  cmp     [r9+rcx*2], di
0x180007f39  jnz     short loc_180007F30
0x180007f3b  lea     edx, ds:2[rcx*2]
0x180007f42  lea     rcx, word_180032B28
0x180007f49  jmp     short loc_180007F5A
0x180007f4b  lea     rcx, word_180032B28
0x180007f52  mov     rsi, rcx
0x180007f55  mov     edx, 2
0x180007f5a  mov     [rsp+148h+var_58], rsi
0x180007f62  mov     [rsp+148h+var_50], edx
0x180007f69  mov     [rsp+148h+var_4C], edi
0x180007f70  lea     rdx, [rsp+148h+var_F4]
0x180007f75  mov     [rsp+148h+var_68], rdx
0x180007f7d  mov     [rsp+148h+var_60], 4
0x180007f89  test    r15, r15
0x180007f8c  jz      short loc_180007FA4
0x180007f8e  xchg    ax, ax
0x180007f90  lea     rax, [rax+1]
0x180007f94  cmp     [r15+rax*2], di
0x180007f99  jnz     short loc_180007F90
0x180007f9b  lea     eax, ds:2[rax*2]
0x180007fa2  jmp     short loc_180007FAC
0x180007fa4  mov     r15, rcx
0x180007fa7  mov     eax, 2
0x180007fac  mov     [rsp+148h+var_78], r15
0x180007fb4  mov     [rsp+148h+var_70], eax
0x180007fbb  mov     [rsp+148h+var_6C], edi
0x180007fc2  lea     rax, [rsp+148h+var_EC]
0x180007fc7  mov     [rsp+148h+var_88], rax
0x180007fcf  mov     [rsp+148h+var_80], 4
0x180007fdb  mov     dword ptr [rsp+148h+EventDescriptor.Id], 0B000000h
0x180007fe3  movzx   eax, cs:word_180035D7D
0x180007fea  mov     dword ptr [rsp+148h+EventDescriptor.Level], eax
0x180007fee  mov     [rsp+148h+EventDescriptor.Keyword], rdi
0x180007ff6  mov     rax, cs:off_18003E050
0x180007ffd  mov     [rsp+148h+var_A8.Ptr], rax
0x180008005  movzx   eax, word ptr [rax]
0x180008008  mov     [rsp+148h+var_A8.Size], eax
0x18000800f  mov     dword ptr [rsp+148h+var_A8.0Ch], 2
0x18000801a  lea     rax, byte_180035D87
0x180008021  mov     [rsp+148h+var_98], rax
0x180008029  mov     [rsp+148h+var_90], 53h ; 'S'
0x180008034  mov     [rsp+148h+var_8C], 1
0x18000803f  lea     rax, _TraceLoggingMetadataEnd
0x180008046  lea     rsi, _TraceLoggingMetadata
0x18000804d  sub     eax, esi
0x18000804f  mov     [rsp+148h+var_E8], eax
0x180008053  mov     eax, [rsp+148h+var_E8]
0x180008057  lea     rax, [rsp+148h+var_A8]
0x18000805f  mov     [rsp+148h+UserData], rax; UserData
0x180008064  mov     [rsp+148h+UserDataCount], 6; UserDataCount
0x18000806c  xor     r9d, r9d; RelatedActivityId
0x18000806f  xor     r8d, r8d; ActivityId
0x180008072  lea     rdx, [rsp+148h+EventDescriptor]; EventDescriptor
0x180008077  mov     rcx, cs:RegHandle; RegHandle
0x18000807e  call    cs:__imp_EventWriteTransfer
0x180008085  nop     dword ptr [rax+rax+00h]
0x18000808a  dec     dword ptr [rbx+0F0h]
0x180008090  jmp     loc_1800084B0
0x180008095  cmp     eax, 5
0x180008098  jbe     loc_180008215
0x18000809e  mov     eax, [rsp+148h+arg_20]
0x1800080a5  mov     [rsp+148h+var_E8], eax
0x1800080a9  mov     [rsp+148h+var_EC], r8d
0x1800080ae  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800080b5  test    rsi, rsi
0x1800080b8  jz      short loc_1800080DB
0x1800080ba  mov     r8, rsi
0x1800080bd  mov     rcx, rax
0x1800080c0  lea     rcx, [rcx+1]
0x1800080c4  cmp     [r9+rcx*2], di
0x1800080c9  jnz     short loc_1800080C0
0x1800080cb  lea     edx, ds:2[rcx*2]
0x1800080d2  lea     rcx, word_180032B28
0x1800080d9  jmp     short loc_1800080EA
0x1800080db  lea     rcx, word_180032B28
0x1800080e2  mov     r8, rcx
0x1800080e5  mov     edx, 2
0x1800080ea  mov     [rsp+148h+var_58], r8
0x1800080f2  mov     [rsp+148h+var_50], edx
0x1800080f9  mov     [rsp+148h+var_4C], edi
0x180008100  lea     rdx, [rsp+148h+var_E8]
0x180008105  mov     [rsp+148h+var_68], rdx
0x18000810d  mov     [rsp+148h+var_60], 4
0x180008119  test    r15, r15
0x18000811c  jz      short loc_180008135
0x18000811e  mov     rcx, r15
0x180008121  lea     rax, [rax+1]
0x180008125  cmp     [r15+rax*2], di
0x18000812a  jnz     short loc_180008121
0x18000812c  lea     eax, ds:2[rax*2]
0x180008133  jmp     short loc_18000813A
0x180008135  mov     eax, 2
0x18000813a  mov     [rsp+148h+var_78], rcx
0x180008142  mov     [rsp+148h+var_70], eax
0x180008149  mov     [rsp+148h+var_6C], edi
0x180008150  lea     rax, [rsp+148h+var_EC]
0x180008155  mov     [rsp+148h+var_88], rax
0x18000815d  mov     [rsp+148h+var_80], 4
0x180008169  mov     dword ptr [rsp+148h+var_E0.Id], 0B000000h
0x180008171  movzx   eax, cs:word_1800360A1
0x180008178  mov     dword ptr [rsp+148h+var_E0.Level], eax
0x18000817c  mov     [rsp+148h+var_E0.Keyword], rdi
0x180008181  mov     rax, cs:off_18003E050
0x180008188  mov     [rsp+148h+var_A8.Ptr], rax
0x180008190  movzx   eax, word ptr [rax]
0x180008193  mov     [rsp+148h+var_A8.Size], eax
0x18000819a  mov     dword ptr [rsp+148h+var_A8.0Ch], 2
0x1800081a5  lea     rax, byte_1800360AB
0x1800081ac  mov     [rsp+148h+var_98], rax
0x1800081b4  mov     [rsp+148h+var_90], 52h ; 'R'
0x1800081bf  mov     [rsp+148h+var_8C], 1
0x1800081ca  lea     rax, _TraceLoggingMetadataEnd
0x1800081d1  lea     rcx, _TraceLoggingMetadata
0x1800081d8  sub     eax, ecx
0x1800081da  mov     [rsp+148h+var_E4], eax
0x1800081de  mov     eax, [rsp+148h+var_E4]
0x1800081e2  lea     rax, [rsp+148h+var_A8]
0x1800081ea  mov     [rsp+148h+UserData], rax; UserData
0x1800081ef  mov     [rsp+148h+UserDataCount], 6; UserDataCount
0x1800081f7  xor     r9d, r9d; RelatedActivityId
0x1800081fa  xor     r8d, r8d; ActivityId
0x1800081fd  lea     rdx, [rsp+148h+var_E0]; EventDescriptor
0x180008202  mov     rcx, cs:RegHandle; RegHandle
0x180008209  call    cs:__imp_EventWriteTransfer
0x180008210  nop     dword ptr [rax+rax+00h]
0x180008215  mov     eax, [rbx+0E0h]
0x18000821b  test    eax, eax
0x18000821d  jnz     short loc_18000822A
0x18000821f  mov     r14d, 80070057h
0x180008225  jmp     loc_1800084B0
0x18000822a  dec     eax
0x18000822c  mov     edx, [rbx+rax*4+60h]
0x180008230  mov     [rsp+148h+var_F0], edx
0x180008234  mov     rax, [rbx+150h]
0x18000823b  test    rax, rax
0x18000823e  jz      short loc_1800082B6
0x180008240  cmp     edx, 15h
0x180008243  jz      short loc_180008283
0x180008245  lea     r9, [rsp+148h+var_B8]
0x18000824d  lea     r8, [rsp+148h+var_C0]
0x180008255  mov     edx, 0FFFFFFFFh
0x18000825a  mov     rcx, rax; unsigned __int16 *
0x18000825d  call    TrimString
0x180008262  mov     r14d, eax
0x180008265  test    eax, eax
0x180008267  js      loc_1800084B0
0x18000826d  mov     edx, [rsp+148h+var_F0]
0x180008271  mov     r13, [rsp+148h+var_C0]
0x180008279  mov     r12, [rsp+148h+var_B8]
0x180008281  jmp     short loc_1800082B6
0x180008283  mov     r13, rax
0x180008286  mov     r12d, 7FFFFFFFh
0x18000828c  mov     ecx, r12d
0x18000828f  nop
0x180008290  cmp     [rax], di
0x180008293  jz      short loc_1800082AA
0x180008295  add     rax, 2
0x180008299  sub     rcx, 1
0x18000829d  jnz     short loc_180008290
0x18000829f  mov     r14d, 80070057h
0x1800082a5  mov     r12, rdi
0x1800082a8  jmp     short loc_1800082AD
0x1800082aa  sub     r12, rcx
0x1800082ad  test    r14d, r14d
0x1800082b0  js      loc_1800084B0
0x1800082b6  dec     dword ptr [rbx+0E0h]
0x1800082bc  mov     rcx, [rbx+40h]
0x1800082c0  test    rcx, rcx
0x1800082c3  jz      loc_18000849C
0x1800082c9  lea     rax, [rsp+148h+var_F0]
0x1800082ce  mov     [rsp+148h+var_108], rax
0x1800082d3  mov     [rsp+148h+var_110], r12d
0x1800082d8  mov     [rsp+148h+var_118], r13
0x1800082dd  mov     eax, [rsp+148h+var_F4]
0x1800082e1  mov     dword ptr [rsp+148h+UserData], eax
0x1800082e5  mov     eax, [rsp+148h+arg_20]
0x1800082ec  mov     [rsp+148h+UserDataCount], eax
0x1800082f0  mov     r9, rsi
0x1800082f3  mov     r8d, [rsp+148h+var_F8]
0x1800082f8  mov     rdx, r15
0x1800082fb  call    ?EndElement@CSyncMLCmd@@QEAAJPEBGK0KW4SyncMLElemType@@0KPEAW42@@Z; CSyncMLCmd::EndElement(ushort const *,ulong,ushort const *,ulong,SyncMLElemType,ushort const *,ulong,SyncMLElemType *)
0x180008300  mov     r14d, eax
0x180008303  test    eax, eax
0x180008305  js      loc_1800084B0
0x18000830b  mov     eax, [rbx+0E0h]
0x180008311  cmp     [rbx+0E4h], eax
0x180008317  jnz     loc_1800084B0
0x18000831d  mov     r15, [rbx+50h]
0x180008321  mov     rcx, [rbx+58h]
0x180008325  cmp     r15, rcx
0x180008328  jz      short loc_18000833B
0x18000832a  mov     rax, [rbx+40h]
0x18000832e  mov     [r15], rax
0x180008331  add     qword ptr [rbx+50h], 8
0x180008336  jmp     loc_180008488
0x18000833b  mov     rax, [rbx+48h]
0x18000833f  mov     r13, r15
0x180008342  sub     r13, rax
0x180008345  sar     r13, 3
0x180008349  mov     r9, 1FFFFFFFFFFFFFFFh
0x180008353  cmp     r13, r9
0x180008356  jz      loc_180008601
0x18000835c  sub     rcx, rax
0x18000835f  sar     rcx, 3
0x180008363  mov     rdx, rcx
0x180008366  shr     rdx, 1
0x180008369  mov     rax, r9
0x18000836c  sub     rax, rdx
0x18000836f  cmp     rcx, rax
0x180008372  ja      loc_18000860C
0x180008378  lea     r8, [r13+1]
0x18000837c  lea     rax, [rdx+rcx]
0x180008380  mov     r12, r8
0x180008383  cmp     rax, r8
0x180008386  cmovnb  r12, rax
0x18000838a  cmp     r12, r9
0x18000838d  ja      loc_180008607
0x180008393  lea     r12, ds:0[r12*8]
0x18000839b  test    r12, r12
0x18000839e  jnz     short loc_1800083A5
0x1800083a0  mov     rsi, rdi
0x1800083a3  jmp     short loc_1800083E3
0x1800083a5  cmp     r12, 1000h
0x1800083ac  jb      short loc_1800083D8
0x1800083ae  lea     rcx, [r12+27h]; Size
0x1800083b3  cmp     rcx, r12
0x1800083b6  jbe     loc_18000860C
0x1800083bc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800083c1  test    rax, rax
0x1800083c4  jz      loc_18000845E
0x1800083ca  lea     rsi, [rax+27h]
0x1800083ce  and     rsi, 0FFFFFFFFFFFFFFE0h
0x1800083d2  mov     [rsi-8], rax
0x1800083d6  jmp     short loc_1800083E3
0x1800083d8  mov     rcx, r12; Size
0x1800083db  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800083e0  mov     rsi, rax
0x1800083e3  mov     rcx, [rbx+40h]
0x1800083e7  mov     [rsi+r13*8], rcx
0x1800083eb  mov     r8, [rbx+50h]
0x1800083ef  mov     rdx, [rbx+48h]; Src
0x1800083f3  mov     rcx, rsi; void *
0x1800083f6  cmp     r15, r8
0x1800083f9  jnz     short loc_180008400
0x1800083fb  sub     r8, rdx
0x1800083fe  jmp     short loc_18000841D
0x180008400  mov     r8, r15
0x180008403  sub     r8, rdx; Size
0x180008406  call    memmove_0
0x18000840b  mov     r8, [rbx+50h]
0x18000840f  sub     r8, r15; Size
0x180008412  lea     rcx, [r13+1]
0x180008416  lea     rcx, [rsi+rcx*8]; void *
0x18000841a  mov     rdx, r15; Src
0x18000841d  call    memmove_0
  ... truncated ...
```
