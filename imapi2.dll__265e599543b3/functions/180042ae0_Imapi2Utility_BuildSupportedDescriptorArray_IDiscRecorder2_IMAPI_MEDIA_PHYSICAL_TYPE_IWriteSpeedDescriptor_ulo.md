# Imapi2Utility::BuildSupportedDescriptorArray(IDiscRecorder2 *,_IMAPI_MEDIA_PHYSICAL_TYPE,IWriteSpeedDescriptor * * *,ulong * *,ulong *)

- ea: `0x180042ae0`
- end: `0x18004316b`
- name: `?BuildSupportedDescriptorArray@Imapi2Utility@@YAJPEAUIDiscRecorder2@@W4_IMAPI_MEDIA_PHYSICAL_TYPE@@PEAPEAPEAUIWriteSpeedDescriptor@@PEAPEAKPEAK@Z`
- size: `1675`
- prototype: `__int64 __usercall@<rax>(Imapi2Utility *__hidden this@<rcx>, struct IDiscRecorder2 *@<rdx>, enum _IMAPI_MEDIA_PHYSICAL_TYPE@<r8d>, struct IWriteSpeedDescriptor ***@<r9>, unsigned int **, unsigned int *)`
- caller_count: `3`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180044698`
- `0x18004499c`
- `0x180047cd8`

## callees

- `0x18000ae3c`
- `0x1800140f4`
- `0x180016778`
- `0x180042ae0`
- `0x1800432c0`
- `0x180043a90`
- `0x180043b20`
- `0x180043f38`
- `0x180047948`
- `0x18004984a`
- `0x180049880`
- `0x18004a010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180042b5b`
- `KERNEL32!LocalAlloc` at `0x180042c7b`
- `KERNEL32!LocalAlloc` at `0x180042c93`
- `KERNEL32!LocalAlloc` at `0x180042e1a`
- `KERNEL32!LocalAlloc` at `0x180042e31`
- `KERNEL32!LocalAlloc` at `0x180042b5b`
- `KERNEL32!LocalAlloc` at `0x180042c7b`
- `KERNEL32!LocalAlloc` at `0x180042c93`
- `KERNEL32!LocalAlloc` at `0x180042e1a`
- `KERNEL32!LocalAlloc` at `0x180042e31`
- `KERNEL32!LocalFree` at `0x180042dfc`
- `KERNEL32!LocalFree` at `0x180043120`
- `KERNEL32!LocalFree` at `0x18004312e`
- `KERNEL32!LocalFree` at `0x180042dfc`
- `KERNEL32!LocalFree` at `0x180043120`
- `KERNEL32!LocalFree` at `0x18004312e`

## pseudocode

```c
__int64 __fastcall Imapi2Utility::BuildSupportedDescriptorArray(
        void (__fastcall ***this)(Imapi2Utility *, GUID *, __int64 *),
        struct IDiscRecorder2 *a2,
        _QWORD *a3,
        struct IWriteSpeedDescriptor ***a4,
        unsigned int **a5)
{
  unsigned int v5; // r13d
  void (__fastcall **v6)(Imapi2Utility *, GUID *, __int64 *); // rax
  unsigned int v7; // ebx
  Imapi2Utility *v8; // r14
  void (__fastcall *v9)(Imapi2Utility *, GUID *, __int64 *); // rax
  void *v10; // r12
  _QWORD *v11; // r15
  unsigned __int64 v12; // rsi
  int v13; // eax
  int *v14; // r9
  int Instance; // edi
  unsigned __int64 v16; // rdx
  struct IWriteSpeedDescriptor **v17; // r14
  _QWORD *v18; // rax
  _BYTE *v19; // rbx
  unsigned int v20; // r14d
  struct IWriteSpeedDescriptor **v21; // r12
  unsigned int *v22; // r9
  __int64 v23; // rcx
  int v24; // eax
  int v25; // eax
  struct IWriteSpeedDescriptor **v26; // r12
  _QWORD *v27; // rax
  unsigned int *v28; // r9
  unsigned int v29; // r12d
  __int64 v30; // rcx
  enum _IMAPI_MEDIA_PHYSICAL_TYPE v31; // edx
  unsigned int v32; // r14d
  int v33; // ecx
  int v34; // eax
  __int64 v35; // rcx
  __int16 v36; // ax
  int v37; // eax
  __int64 v38; // rcx
  __int64 v39; // rax
  PVOID *v40; // rcx
  struct IWriteSpeedDescriptor ***v41; // rcx
  __int64 v42; // rcx
  char v44; // [rsp+50h] [rbp-91h]
  unsigned __int8 v45; // [rsp+50h] [rbp-91h]
  char v46; // [rsp+50h] [rbp-91h]
  unsigned int v47; // [rsp+54h] [rbp-8Dh] BYREF
  unsigned __int8 v48; // [rsp+58h] [rbp-89h]
  unsigned __int8 v49; // [rsp+59h] [rbp-88h]
  _BYTE v50[20]; // [rsp+60h] [rbp-81h] BYREF
  unsigned int v51[2]; // [rsp+78h] [rbp-69h] BYREF
  unsigned int v52; // [rsp+80h] [rbp-61h] BYREF
  Imapi2Utility *v53; // [rsp+88h] [rbp-59h]
  struct IWriteSpeedDescriptor **v54; // [rsp+90h] [rbp-51h]
  __int64 v55; // [rsp+98h] [rbp-49h] BYREF
  _QWORD *v56; // [rsp+A0h] [rbp-41h]
  struct IWriteSpeedDescriptor ***v57; // [rsp+A8h] [rbp-39h]
  unsigned int **v58; // [rsp+B0h] [rbp-31h]
  __int128 v59; // [rsp+B8h] [rbp-29h] BYREF
  union _CDB v60; // [rsp+C8h] [rbp-19h] BYREF
  __int16 v61; // [rsp+D8h] [rbp-9h]

  v5 = (unsigned int)a2;
  v58 = a5;
  v6 = *this;
  v7 = 0;
  v56 = a3;
  v8 = (Imapi2Utility *)this;
  v57 = a4;
  v53 = (Imapi2Utility *)this;
  v9 = *v6;
  v55 = 0;
  v9((Imapi2Utility *)this, &GUID_27354132_7f64_5b0f_8f00_5d77afbe261e, &v55);
  v61 = 0;
  v59 = 0;
  v60 = 0;
  *(_QWORD *)v51 = LocalAlloc(0x40u, 0x208u);
  v10 = *(void **)v51;
  v52 = 0;
  if ( *(_QWORD *)v51 )
  {
    v54 = 0;
    v44 = 0;
    v61 = 0;
    v11 = 0;
    v59 = 0;
    LODWORD(v12) = 0;
    v60 = 0;
    memset_0(*(void **)v51, 0, 0x208u);
    LOBYTE(v59) = -84;
    *(_WORD *)((char *)&v59 + 9) = 800;
    v13 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64, union _CDB *, int, _QWORD, int, unsigned int *))(*(_QWORD *)v55 + 40LL))(
            v55,
            &v59,
            12,
            &v60,
            10,
            *(_QWORD *)v51,
            520,
            &v52);
    *(_DWORD *)v50 = v13;
    Instance = v13;
    if ( v13 >= 0 )
    {
      if ( v13 == 11141632 )
      {
        Imapi2Utility::TranslateSenseInfoToHResult((Imapi2Utility *)&v59, &v60, (const struct _SENSE_DATA *)v50, v14);
        Instance = *(_DWORD *)v50;
      }
      else if ( v52 >= 8
             && (v16 = *(unsigned __int8 *)(*(_QWORD *)v51 + 3LL)
                     | ((*(unsigned __int8 *)(*(_QWORD *)v51 + 2LL)
                       | ((*(unsigned __int8 *)(*(_QWORD *)v51 + 1LL)
                         | ((unsigned __int64)(unsigned __int8)**(_BYTE **)v51 << 8)) << 8)) << 8),
                 v16 + 4 <= v52) )
      {
        v12 = (v16 - 4) >> 4;
        if ( (unsigned int)v12 > 0x20 )
          v12 = 32;
        v17 = (struct IWriteSpeedDescriptor **)LocalAlloc(0x40u, 4 * v12);
        v54 = v17;
        v18 = LocalAlloc(0x40u, 8 * v12);
        v11 = v18;
        if ( v17 && v18 )
        {
          v19 = (_BYTE *)(*(_QWORD *)v51 + 8LL);
          v20 = 0;
          if ( (_DWORD)v12 )
          {
            v21 = v54;
            do
            {
              v45 = v19[12];
              v48 = v19[13];
              v49 = v19[14];
              LOBYTE(v47) = v19[15];
              *(_DWORD *)v50 = 0;
              *(_QWORD *)&v50[8] = 0;
              Instance = ATL::CComObject<CMsftWriteSpeedDescriptor>::CreateInstance(&v50[8]);
              if ( Instance >= 0 )
              {
                *(_DWORD *)&v50[16] = (unsigned __int8)v47 | ((v49 | ((v48 | (v45 << 8)) << 8)) << 8);
                Instance = Imapi2Utility::FuzzyConvert_KBps2SectorsPerSecond(
                             (Imapi2Utility *)v5,
                             *(enum _IMAPI_MEDIA_PHYSICAL_TYPE *)&v50[16],
                             (unsigned int)v50,
                             v22);
                if ( Instance >= 0 )
                {
                  v23 = *(_QWORD *)&v50[8];
                  v24 = *(_DWORD *)v50;
                  if ( *(_DWORD *)v50 > 0x7FFFFFFFu )
                    v24 = 0x7FFFFFFF;
                  *(_DWORD *)(*(_QWORD *)&v50[8] + 64LL) = v24;
                  *(_WORD *)(v23 + 68) = ((*v19 & 0x18) != 8) - 1;
                  *(_DWORD *)(v23 + 72) = v5;
                  *(_QWORD *)&v50[8] = 0;
                  Instance = (**(__int64 (__fastcall ***)(__int64, GUID *, _BYTE *))v23)(
                               v23,
                               &GUID_27354144_7f64_5b0f_8f00_5d77afbe261e,
                               &v50[8]);
                  v25 = *(_DWORD *)&v50[16];
                  v11[v20] = *(_QWORD *)&v50[8];
                  *((_DWORD *)v21 + v20) = v25;
                }
              }
              v19 += 16;
              ++v20;
            }
            while ( v20 < (unsigned int)v12 );
            v10 = *(void **)v51;
          }
          v44 = 1;
          v7 = 0;
        }
        else
        {
          Instance = -2147024882;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 111, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids);
          }
        }
        v8 = v53;
      }
      else
      {
        Instance = -1062599937;
      }
    }
    LocalFree(v10);
    if ( v44 )
    {
LABEL_75:
      if ( Instance < 0 )
        goto LABEL_82;
      v41 = v57;
      *v56 = v11;
      *v41 = v54;
      *(_DWORD *)v58 = v12;
      goto LABEL_91;
    }
  }
  LODWORD(v12) = 0;
  Instance = 0;
  v26 = (struct IWriteSpeedDescriptor **)LocalAlloc(0x40u, 0x190u);
  v54 = v26;
  v27 = LocalAlloc(0x40u, 0x320u);
  v11 = v27;
  if ( !v26 || !v27 )
  {
    Instance = -2147024882;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids);
    }
    goto LABEL_83;
  }
  v29 = -1;
  v46 = 0;
  *(_DWORD *)v50 = 0;
  v51[0] = 0;
  if ( v5 - 1 <= 2 )
  {
    v30 = v5;
    goto LABEL_44;
  }
  if ( v5 - 4 <= 7 )
  {
    v7 = 250;
    v31 = 680;
    v30 = v5;
    goto LABEL_45;
  }
  if ( v5 - 17 <= 2 )
  {
    v7 = 1000;
    goto LABEL_46;
  }
  if ( !v5 )
  {
    v30 = 0;
LABEL_44:
    v7 = 50;
    v31 = IMAPI_MEDIA_TYPE_DVDDASHR_DUALLAYER|0x40;
    goto LABEL_45;
  }
  if ( v5 == 12 )
  {
    v7 = 250;
    v31 = 680;
    v30 = 12;
LABEL_45:
    Instance = Imapi2Utility::FuzzyConvert_SectorsPerSecond2KBps((Imapi2Utility *)v30, v31, (unsigned int)v51, v28);
    goto LABEL_46;
  }
  Instance = -2147467259;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids, v5);
  }
LABEL_46:
  while ( Instance >= 0 )
  {
    Instance = Imapi2Utility::SetCurrentDriveWriteSpeed(v8, (struct IDiscRecorder2 *)v29, 0, (unsigned int)v28);
    if ( Instance < 0 )
      goto LABEL_73;
    LOWORD(v47) = 0;
    *(_DWORD *)&v50[8] = 0;
    *(_DWORD *)&v50[16] = 0;
    Instance = Imapi2Utility::GetCurrentDriveSpeedProperties(
                 v8,
                 (struct IDiscRecorder2 *)v5,
                 (unsigned int *)&v50[16],
                 (_IMAPI_MEDIA_PHYSICAL_TYPE *)&v50[8],
                 &v47);
    if ( Instance < 0 )
      goto LABEL_73;
    v32 = *(_DWORD *)&v50[8];
    v33 = *(_DWORD *)v50;
    if ( *(_DWORD *)&v50[8] == *(_DWORD *)v50 )
      goto LABEL_70;
    *(_QWORD *)&v50[8] = 0;
    Instance = ATL::CComObject<CMsftWriteSpeedDescriptor>::CreateInstance(&v50[8]);
    if ( Instance >= 0 )
    {
      v34 = *(_DWORD *)&v50[16];
      v35 = *(_QWORD *)&v50[8];
      if ( *(_DWORD *)&v50[16] > 0x7FFFFFFFu )
        v34 = 0x7FFFFFFF;
      *(_DWORD *)(*(_QWORD *)&v50[8] + 64LL) = v34;
      if ( (_WORD)v47 )
        v36 = -1;
      else
        v36 = 0;
      *(_WORD *)(v35 + 68) = v36;
      *(_DWORD *)(v35 + 72) = v5;
      *(_QWORD *)v50 = 0;
      v37 = (**(__int64 (__fastcall ***)(__int64, GUID *, _BYTE *))v35)(
              v35,
              &GUID_27354144_7f64_5b0f_8f00_5d77afbe261e,
              v50);
      v38 = (unsigned int)v12;
      Instance = v37;
      v39 = *(_QWORD *)v50;
      LODWORD(v12) = v12 + 1;
      v29 = v32;
      *(_DWORD *)v50 = v32;
      v11[v38] = v39;
      *((_DWORD *)v54 + v38) = v32;
      goto LABEL_61;
    }
    v40 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        114,
        &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
        (unsigned int)Instance);
LABEL_61:
      v40 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (unsigned int)v12 >= 0x64 )
    {
      if ( v40 != &WPP_GLOBAL_Control && (*((_BYTE *)v40 + 28) & 4) != 0 && *((_BYTE *)v40 + 25) >= 4u )
        WPP_SF_d(v40[2], 115, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids, 100);
      v46 = 1;
    }
    if ( Instance >= 0 )
    {
      v33 = *(_DWORD *)v50;
LABEL_70:
      v29 -= v7;
      if ( v29 <= v51[0] || !v33 )
      {
LABEL_74:
        v7 = 0;
        goto LABEL_75;
      }
    }
    v8 = v53;
LABEL_73:
    if ( v46 )
      goto LABEL_74;
  }
  v7 = 0;
LABEL_82:
  v26 = v54;
LABEL_83:
  if ( v11 )
  {
    if ( (_DWORD)v12 )
    {
      do
      {
        v42 = v11[v7];
        if ( v42 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
          v11[v7] = 0;
        }
        ++v7;
      }
      while ( v7 < (unsigned int)v12 );
    }
    LocalFree(v11);
  }
  if ( v26 )
    LocalFree(v26);
LABEL_91:
  if ( v55 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180042ae0  push    rbp
0x180042ae2  push    rbx
0x180042ae3  push    rsi
0x180042ae4  push    rdi
0x180042ae5  push    r12
0x180042ae7  push    r13
0x180042ae9  push    r14
0x180042aeb  push    r15
0x180042aed  lea     rbp, [rsp-17h]
0x180042af2  sub     rsp, 0F8h
0x180042af9  mov     rax, cs:__security_cookie
0x180042b00  xor     rax, rsp
0x180042b03  mov     [rbp+4Fh+var_50], rax
0x180042b07  mov     rax, [rbp+4Fh+arg_20]
0x180042b0b  mov     r13d, edx
0x180042b0e  mov     [rbp+4Fh+var_80], rax
0x180042b12  lea     rdx, _GUID_27354132_7f64_5b0f_8f00_5d77afbe261e
0x180042b19  mov     rax, [rcx]
0x180042b1c  xor     ebx, ebx
0x180042b1e  mov     [rbp+4Fh+var_90], r8
0x180042b22  mov     r14, rcx
0x180042b25  lea     r8, [rbp+4Fh+var_98]
0x180042b29  mov     [rbp+4Fh+var_88], r9
0x180042b2d  mov     [rbp+4Fh+var_A8], rcx
0x180042b31  mov     rax, [rax]
0x180042b34  mov     [rbp+4Fh+var_98], rbx
0x180042b38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042b3d  xorps   xmm0, xmm0
0x180042b40  lea     ecx, [rbx+40h]; uFlags
0x180042b43  xorps   xmm1, xmm1
0x180042b46  xor     eax, eax
0x180042b48  mov     edi, 208h
0x180042b4d  mov     [rbp+4Fh+var_58], ax
0x180042b51  mov     edx, edi; uBytes
0x180042b53  movups  [rbp+4Fh+var_78], xmm0
0x180042b57  movups  xmmword ptr [rbp+4Fh+var_68], xmm1
0x180042b5b  call    cs:__imp_LocalAlloc
0x180042b61  mov     qword ptr [rbp+4Fh+var_B8], rax
0x180042b65  mov     r12, rax
0x180042b68  mov     [rbp+4Fh+var_B0], ebx
0x180042b6b  test    rax, rax
0x180042b6e  jz      loc_180042E0C
0x180042b74  xorps   xmm0, xmm0
0x180042b77  mov     [rbp+4Fh+var_A0], rbx
0x180042b7b  xorps   xmm1, xmm1
0x180042b7e  mov     [rsp+130h+var_E0], bl
0x180042b82  xor     eax, eax
0x180042b84  mov     r8d, edi; Size
0x180042b87  xor     edx, edx; Val
0x180042b89  mov     [rbp+4Fh+var_58], ax
0x180042b8d  mov     rcx, r12; void *
0x180042b90  mov     r15d, ebx
0x180042b93  movups  [rbp+4Fh+var_78], xmm0
0x180042b97  mov     esi, ebx
0x180042b99  movups  xmmword ptr [rbp+4Fh+var_68], xmm1
0x180042b9d  call    memset_0
0x180042ba2  mov     rcx, [rbp+4Fh+var_98]
0x180042ba6  lea     rdx, [rbp+4Fh+var_B0]
0x180042baa  mov     [rsp+130h+var_F8], rdx
0x180042baf  lea     r9, [rbp+4Fh+var_68]
0x180042bb3  mov     byte ptr [rbp+4Fh+var_78], 0ACh
0x180042bb7  lea     r8d, [rbx+0Ch]
0x180042bbb  mov     word ptr [rbp+4Fh+var_78+9], 320h
0x180042bc1  lea     rdx, [rbp+4Fh+var_78]
0x180042bc5  mov     rax, [rcx]
0x180042bc8  mov     [rsp+130h+var_100], edi
0x180042bcc  mov     [rsp+130h+var_108], r12; __int16 *
0x180042bd1  mov     dword ptr [rsp+130h+var_110], 0Ah
0x180042bd9  mov     rax, [rax+28h]
0x180042bdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042be2  mov     dword ptr [rsp+130h+var_D0], eax
0x180042be6  mov     edi, eax
0x180042be8  test    eax, eax
0x180042bea  js      loc_180042DF9
0x180042bf0  cmp     eax, 0AA0200h
0x180042bf5  jnz     short loc_180042C12
0x180042bf7  lea     r8, [rsp+130h+var_D0]; struct _SENSE_DATA *
0x180042bfc  lea     rdx, [rbp+4Fh+var_68]; union _CDB *
0x180042c00  lea     rcx, [rbp+4Fh+var_78]; this
0x180042c04  call    ?TranslateSenseInfoToHResult@Imapi2Utility@@YA?BEPEBT_CDB@@PEBU_SENSE_DATA@@PEAJ@Z; Imapi2Utility::TranslateSenseInfoToHResult(_CDB const *,_SENSE_DATA const *,long *)
0x180042c09  mov     edi, dword ptr [rsp+130h+var_D0]
0x180042c0d  jmp     loc_180042DF9
0x180042c12  cmp     [rbp+4Fh+var_B0], 8
0x180042c16  jb      short loc_180042C50
0x180042c18  movzx   eax, byte ptr [r12+1]
0x180042c1e  movzx   edx, byte ptr [r12]
0x180042c23  shl     rdx, 8
0x180042c27  or      rdx, rax
0x180042c2a  movzx   eax, byte ptr [r12+2]
0x180042c30  shl     rdx, 8
0x180042c34  or      rdx, rax
0x180042c37  movzx   eax, byte ptr [r12+3]
0x180042c3d  shl     rdx, 8
0x180042c41  or      rdx, rax
0x180042c44  mov     eax, [rbp+4Fh+var_B0]
0x180042c47  lea     rcx, [rdx+4]
0x180042c4b  cmp     rcx, rax
0x180042c4e  jbe     short loc_180042C5A
0x180042c50  mov     edi, 0C0AA02FFh
0x180042c55  jmp     loc_180042DF9
0x180042c5a  mov     eax, 20h ; ' '
0x180042c5f  lea     rsi, [rdx-4]
0x180042c63  shr     rsi, 4
0x180042c67  cmp     esi, eax
0x180042c69  cmova   esi, eax
0x180042c6c  lea     r15d, [rax+20h]
0x180042c70  mov     ecx, r15d; uFlags
0x180042c73  lea     rdx, ds:0[rsi*4]; uBytes
0x180042c7b  call    cs:__imp_LocalAlloc
0x180042c81  lea     rdx, ds:0[rsi*8]; uBytes
0x180042c89  mov     ecx, r15d; uFlags
0x180042c8c  mov     r14, rax
0x180042c8f  mov     [rbp+4Fh+var_A0], rax
0x180042c93  call    cs:__imp_LocalAlloc
0x180042c99  mov     r15, rax
0x180042c9c  test    r14, r14
0x180042c9f  jz      loc_180042DBC
0x180042ca5  test    rax, rax
0x180042ca8  jz      loc_180042DBC
0x180042cae  xor     r8d, r8d
0x180042cb1  lea     rbx, [r12+8]
0x180042cb6  mov     r14d, r8d
0x180042cb9  test    esi, esi
0x180042cbb  jz      loc_180042DB3
0x180042cc1  mov     r12, [rbp+4Fh+var_A0]
0x180042cc5  mov     al, [rbx+0Ch]
0x180042cc8  lea     rcx, [rbp+4Fh+var_D0+8]
0x180042ccc  mov     [rsp+130h+var_E0], al
0x180042cd0  mov     al, [rbx+0Dh]
0x180042cd3  mov     [rsp+130h+var_D8], al
0x180042cd7  mov     al, [rbx+0Eh]
0x180042cda  mov     [rsp+130h+var_D7], al
0x180042cde  mov     al, [rbx+0Fh]
0x180042ce1  mov     byte ptr [rsp+130h+var_DC], al
0x180042ce5  mov     dword ptr [rsp+130h+var_D0], r8d
0x180042cea  mov     qword ptr [rbp+4Fh+var_D0+8], r8
0x180042cee  call    ?CreateInstance@?$CComObject@VCMsftWriteSpeedDescriptor@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CMsftWriteSpeedDescriptor>::CreateInstance(ATL::CComObject<CMsftWriteSpeedDescriptor> * *)
0x180042cf3  xor     r8d, r8d
0x180042cf6  mov     edi, eax
0x180042cf8  test    eax, eax
0x180042cfa  js      loc_180042D9F
0x180042d00  movzx   eax, [rsp+130h+var_D8]
0x180042d05  lea     r8, [rsp+130h+var_D0]; unsigned int
0x180042d0a  movzx   ecx, [rsp+130h+var_E0]
0x180042d0f  shl     ecx, 8
0x180042d12  or      ecx, eax
0x180042d14  movzx   eax, [rsp+130h+var_D7]
0x180042d19  shl     ecx, 8
0x180042d1c  or      ecx, eax
0x180042d1e  movzx   eax, byte ptr [rsp+130h+var_DC]
0x180042d23  shl     ecx, 8
0x180042d26  or      ecx, eax
0x180042d28  mov     dword ptr [rbp+4Fh+var_D0+10h], ecx
0x180042d2b  mov     edx, ecx; enum _IMAPI_MEDIA_PHYSICAL_TYPE
0x180042d2d  mov     ecx, r13d; this
0x180042d30  call    ?FuzzyConvert_KBps2SectorsPerSecond@Imapi2Utility@@YAJW4_IMAPI_MEDIA_PHYSICAL_TYPE@@KPEAK@Z; Imapi2Utility::FuzzyConvert_KBps2SectorsPerSecond(_IMAPI_MEDIA_PHYSICAL_TYPE,ulong,ulong *)
0x180042d35  xor     r8d, r8d
0x180042d38  mov     edi, eax
0x180042d3a  test    eax, eax
0x180042d3c  js      short loc_180042D9F
0x180042d3e  mov     rcx, qword ptr [rbp+4Fh+var_D0+8]
0x180042d42  mov     edx, 7FFFFFFFh
0x180042d47  mov     eax, dword ptr [rsp+130h+var_D0]
0x180042d4b  cmp     eax, edx
0x180042d4d  cmova   eax, edx
0x180042d50  mov     edx, r8d
0x180042d53  mov     [rcx+40h], eax
0x180042d56  mov     al, [rbx]
0x180042d58  and     al, 18h
0x180042d5a  cmp     al, 8
0x180042d5c  lea     eax, [r8+1]
0x180042d60  setnz   dl
0x180042d63  sub     dx, ax
0x180042d66  mov     [rcx+44h], dx
0x180042d6a  lea     rdx, _GUID_27354144_7f64_5b0f_8f00_5d77afbe261e
0x180042d71  mov     [rcx+48h], r13d
0x180042d75  mov     qword ptr [rbp+4Fh+var_D0+8], r8
0x180042d79  lea     r8, [rbp+4Fh+var_D0+8]
0x180042d7d  mov     rax, [rcx]
0x180042d80  mov     rax, [rax]
0x180042d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042d88  mov     rcx, qword ptr [rbp+4Fh+var_D0+8]
0x180042d8c  mov     edi, eax
0x180042d8e  mov     eax, dword ptr [rbp+4Fh+var_D0+10h]
0x180042d91  xor     r8d, r8d
0x180042d94  mov     edx, r14d
0x180042d97  mov     [r15+rdx*8], rcx
0x180042d9b  mov     [r12+rdx*4], eax
0x180042d9f  add     rbx, 10h
0x180042da3  inc     r14d
0x180042da6  cmp     r14d, esi
0x180042da9  jb      loc_180042CC5
0x180042daf  mov     r12, qword ptr [rbp+4Fh+var_B8]
0x180042db3  mov     [rsp+130h+var_E0], 1
0x180042db8  xor     ebx, ebx
0x180042dba  jmp     short loc_180042DF5
0x180042dbc  mov     edi, 8007000Eh
0x180042dc1  mov     rcx, cs:WPP_GLOBAL_Control
0x180042dc8  lea     rax, WPP_GLOBAL_Control
0x180042dcf  cmp     rcx, rax
0x180042dd2  jz      short loc_180042DF5
0x180042dd4  test    byte ptr [rcx+1Ch], 4
0x180042dd8  jz      short loc_180042DF5
0x180042dda  cmp     byte ptr [rcx+19h], 4
0x180042dde  jb      short loc_180042DF5
0x180042de0  mov     rcx, [rcx+10h]
0x180042de4  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180042deb  mov     edx, 6Fh ; 'o'
0x180042df0  call    WPP_SF_
0x180042df5  mov     r14, [rbp+4Fh+var_A8]
0x180042df9  mov     rcx, r12; hMem
0x180042dfc  call    cs:__imp_LocalFree
0x180042e02  cmp     [rsp+130h+var_E0], bl
0x180042e06  jnz     loc_18004308C
0x180042e0c  mov     edx, 190h; uBytes
0x180042e11  mov     ecx, 40h ; '@'; uFlags
0x180042e16  mov     esi, ebx
0x180042e18  mov     edi, ebx
0x180042e1a  call    cs:__imp_LocalAlloc
0x180042e20  mov     edx, 320h; uBytes
0x180042e25  mov     ecx, 40h ; '@'; uFlags
0x180042e2a  mov     r12, rax
0x180042e2d  mov     [rbp+4Fh+var_A0], rax
0x180042e31  call    cs:__imp_LocalAlloc
0x180042e37  mov     r15, rax
0x180042e3a  test    r12, r12
0x180042e3d  jz      loc_1800430AD
0x180042e43  test    rax, rax
0x180042e46  jz      loc_1800430AD
0x180042e4c  or      r12d, 0FFFFFFFFh
0x180042e50  mov     [rsp+130h+var_E0], bl
0x180042e54  lea     eax, [r13-1]
0x180042e58  mov     dword ptr [rsp+130h+var_D0], ebx
0x180042e5c  mov     [rbp+4Fh+var_B8], ebx
0x180042e5f  cmp     eax, 2
0x180042e62  jbe     loc_180042EEC
0x180042e68  lea     eax, [r13-4]
0x180042e6c  cmp     eax, 7
0x180042e6f  jbe     short loc_180042EDD
0x180042e71  lea     eax, [r13-11h]
0x180042e75  cmp     eax, 2
0x180042e78  jbe     short loc_180042ED6
0x180042e7a  test    r13d, r13d
0x180042e7d  jnz     short loc_180042E83
0x180042e7f  xor     ecx, ecx
0x180042e81  jmp     short loc_180042EEF
0x180042e83  cmp     r13d, 0Ch
0x180042e87  jnz     short loc_180042E98
0x180042e89  mov     ebx, 0FAh
0x180042e8e  mov     edx, 2A8h
0x180042e93  mov     ecx, r13d
0x180042e96  jmp     short loc_180042EF7
0x180042e98  mov     edi, 80004005h
0x180042e9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180042ea4  lea     rax, WPP_GLOBAL_Control
0x180042eab  cmp     rcx, rax
0x180042eae  jz      short loc_180042F02
0x180042eb0  test    byte ptr [rcx+1Ch], 4
0x180042eb4  jz      short loc_180042F02
0x180042eb6  cmp     byte ptr [rcx+19h], 4
0x180042eba  jb      short loc_180042F02
0x180042ebc  mov     rcx, [rcx+10h]
0x180042ec0  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180042ec7  mov     edx, 71h ; 'q'
0x180042ecc  mov     r9d, r13d
0x180042ecf  call    WPP_SF_d
0x180042ed4  jmp     short loc_180042F02
0x180042ed6  mov     ebx, 3E8h
0x180042edb  jmp     short loc_180042F02
0x180042edd  mov     ebx, 0FAh
0x180042ee2  mov     edx, 2A8h
0x180042ee7  mov     ecx, r13d
0x180042eea  jmp     short loc_180042EF7
0x180042eec  mov     ecx, r13d; this
0x180042eef  mov     ebx, 32h ; '2'
0x180042ef4  lea     edx, [rbx+19h]; enum _IMAPI_MEDIA_PHYSICAL_TYPE
0x180042ef7  lea     r8, [rbp+4Fh+var_B8]; unsigned int
0x180042efb  call    ?FuzzyConvert_SectorsPerSecond2KBps@Imapi2Utility@@YAJW4_IMAPI_MEDIA_PHYSICAL_TYPE@@KPEAK@Z; Imapi2Utility::FuzzyConvert_SectorsPerSecond2KBps(_IMAPI_MEDIA_PHYSICAL_TYPE,ulong,ulong *)
0x180042f00  mov     edi, eax
0x180042f02  test    edi, edi
0x180042f04  js      loc_1800430E8
0x180042f0a  xor     r8d, r8d; unsigned int
0x180042f0d  mov     edx, r12d; struct IDiscRecorder2 *
0x180042f10  mov     rcx, r14; this
0x180042f13  call    ?SetCurrentDriveWriteSpeed@Imapi2Utility@@YAJPEAUIDiscRecorder2@@KK@Z; Imapi2Utility::SetCurrentDriveWriteSpeed(IDiscRecorder2 *,ulong,ulong)
0x180042f18  xor     edx, edx
0x180042f1a  mov     edi, eax
0x180042f1c  test    eax, eax
0x180042f1e  js      loc_180043080
0x180042f24  mov     word ptr [rsp+130h+var_DC], dx
0x180042f29  lea     rax, [rsp+130h+var_DC]
0x180042f2e  mov     dword ptr [rbp+4Fh+var_D0+8], edx
0x180042f31  lea     r9, [rbp+4Fh+var_D0+8]; unsigned int *
0x180042f35  mov     dword ptr [rbp+4Fh+var_D0+10h], edx
0x180042f38  lea     r8, [rbp+4Fh+var_D0+10h]; enum _IMAPI_MEDIA_PHYSICAL_TYPE
0x180042f3c  mov     edx, r13d; struct IDiscRecorder2 *
0x180042f3f  mov     [rsp+130h+var_110], rax; unsigned int *
0x180042f44  mov     rcx, r14; this
0x180042f47  call    ?GetCurrentDriveSpeedProperties@Imapi2Utility@@YAJPEAUIDiscRecorder2@@W4_IMAPI_MEDIA_PHYSICAL_TYPE@@PEAK2PEAF@Z; Imapi2Utility::GetCurrentDriveSpeedProperties(IDiscRecorder2 *,_IMAPI_MEDIA_PHYSICAL_TYPE,ulong *,ulong *,short *)
0x180042f4c  xor     edx, edx
  ... truncated ...
```
