# CMsftWriteEngine2::WriteSection(IStream *,long,long)

- ea: `0x180033b60`
- end: `0x1800342f4`
- name: `?WriteSection@CMsftWriteEngine2@@UEAAJPEAUIStream@@JJ@Z`
- size: `1940`
- prototype: `__int64 __fastcall(CMsftWriteEngine2 *this, struct IStream *, const struct _GUID *, int)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180002fc8`
- `0x18000ebd4`
- `0x18000ed90`
- `0x18000fdd4`
- `0x1800140f4`
- `0x180014134`
- `0x180016778`
- `0x180033b60`
- `0x180034e10`
- `0x180034e9c`
- `0x180035254`
- `0x180035580`
- `0x180035fe0`
- `0x180049880`
- `0x18004a010`

## import_xrefs

- `USER32!MsgWaitForMultipleObjects` at `0x180033f6f`
- `USER32!MsgWaitForMultipleObjects` at `0x180033f6f`
- `KERNEL32!SetEvent` at `0x180033f2b`
- `KERNEL32!SetEvent` at `0x180033f2b`
- `KERNEL32!ResetEvent` at `0x180033f1e`
- `KERNEL32!ResetEvent` at `0x180033f8d`
- `KERNEL32!ResetEvent` at `0x180033f1e`
- `KERNEL32!ResetEvent` at `0x180033f8d`

## pseudocode

```c
__int64 __fastcall CMsftWriteEngine2::WriteSection(
        CMsftWriteEngine2 *this,
        struct IStream *a2,
        const struct _GUID *a3,
        int a4)
{
  int v5; // r15d
  signed int v8; // ebx
  PVOID *v9; // rcx
  CWriteEngineSectionResources *v10; // rax
  CWriteEngineSectionResources *v11; // rax
  unsigned int v12; // r9d
  CWriteEngineSectionResources *v13; // rsi
  int v14; // eax
  int v15; // eax
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  CWriteEngineSectionParameters *v18; // rax
  CWriteEngineSectionParameters *v19; // rax
  CWriteEngineSectionParameters *v20; // rbp
  signed int v21; // eax
  __int64 v22; // rsi
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r9
  int v26; // eax
  int v27; // eax
  _QWORD *v28; // rcx
  __int64 v29; // rdx
  _QWORD *v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v35; // [rsp+50h] [rbp-78h] BYREF
  HANDLE pHandles[3]; // [rsp+58h] [rbp-70h] BYREF

  v35 = 0;
  *((_QWORD *)this + 19) = 0;
  v5 = (int)a3;
  v8 = 0;
  if ( a2 )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 10, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    v8 = -2147467261;
  }
  if ( !*((_QWORD *)this + 14) )
  {
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 228) & 4) != 0 && *((_BYTE *)v9 + 225) >= 3u )
      WPP_SF_(v9[27], 11, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids);
    v8 = -1062600701;
    goto LABEL_108;
  }
  if ( v8 < 0 )
    goto LABEL_108;
  if ( *((_QWORD *)this + 16) )
    goto LABEL_25;
  v10 = (CWriteEngineSectionResources *)operator new(0x60u);
  if ( v10 )
  {
    v11 = CWriteEngineSectionResources::CWriteEngineSectionResources(v10);
    v13 = v11;
    if ( v11 )
    {
      v14 = CWriteEngineSectionResources::Init(
              v11,
              this,
              *((struct CWriteEngineStaticDriveInformation **)this + 15),
              v12,
              *((void **)this + 25),
              *((void **)this + 28));
      v8 = v14;
      if ( v14 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            13,
            WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids,
            (unsigned int)v14);
        }
        (*(void (__fastcall **)(CWriteEngineSectionResources *))(*(_QWORD *)v13 + 8LL))(v13);
        goto LABEL_108;
      }
      *((_QWORD *)this + 16) = v13;
LABEL_25:
      v15 = CWriteEngineSectionResources::Reset(*((CWriteEngineSectionResources **)this + 16));
      v8 = v15;
      if ( v15 < 0 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 225) < 3u )
        {
          goto LABEL_108;
        }
        v17 = 14;
        goto LABEL_42;
      }
      v18 = (CWriteEngineSectionParameters *)operator new(0x48u);
      if ( v18 && (v19 = CWriteEngineSectionParameters::CWriteEngineSectionParameters(v18), (v20 = v19) != 0) )
      {
        v15 = CWriteEngineSectionParameters::Init(
                v19,
                *((struct CWriteEngineStaticDriveInformation **)this + 15),
                *((_WORD *)this + 123) != 0,
                *((_DWORD *)this + 62),
                *((_DWORD *)this + 63),
                v5,
                a4,
                *((_DWORD *)this + 64),
                a2);
        v8 = v15;
        if ( v15 < 0 )
        {
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 225) < 3u )
          {
            goto LABEL_108;
          }
          v17 = 16;
LABEL_42:
          WPP_SF_d(v16[27], v17, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids, (unsigned int)v15);
          goto LABEL_108;
        }
        v21 = ATL::CComObject<CWriteEngineEventArgs>::CreateInstance(&v35);
        v22 = v35;
        v8 = v21;
        if ( !v35 )
        {
          v8 = -2147024882;
          v23 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 225) < 3u )
          {
            goto LABEL_108;
          }
          v24 = (unsigned int)(v35 + 17);
          goto LABEL_107;
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 8LL))(v35);
        if ( v8 < 0 )
          goto LABEL_108;
        *(_DWORD *)(v22 + 64) = v5;
        *(_DWORD *)(v22 + 68) = a4;
        *(_DWORD *)(v22 + 72) = v5;
        *(_DWORD *)(v22 + 76) = v5;
        *(_QWORD *)(v22 + 80) = 0x200000;
        *(_QWORD *)(v22 + 88) = 0x80000;
        *(_DWORD *)(v22 + 88) = *(_DWORD *)(*((_QWORD *)this + 16) + 32LL) * *(_DWORD *)(*((_QWORD *)this + 16) + 72LL);
        *((_QWORD *)this + 18) = v22;
        *((_QWORD *)this + 17) = v20;
        *((_DWORD *)this + 38) = -2147467259;
        *((_DWORD *)this + 39) = -2147467259;
        *((_WORD *)this + 122) = -1;
        CMsftWriteEngine2::UpdateProgress(this);
        ResetEvent(*((HANDLE *)this + 23));
        SetEvent(*((HANDLE *)this + 21));
        pHandles[0] = *((HANDLE *)this + 23);
        pHandles[1] = *((HANDLE *)this + 25);
        pHandles[2] = *((HANDLE *)this + 28);
        while ( MsgWaitForMultipleObjects(3u, pHandles, 0, 0x1F4u, 0) == 258 )
          CMsftWriteEngine2::UpdateProgress(this);
        ResetEvent(*((HANDLE *)this + 23));
        CMsftWriteEngine2::UpdateProgress(this);
        v25 = *((unsigned int *)this + 38);
        v8 = -1062600702;
        if ( (int)v25 >= 0 )
        {
          if ( *((int *)this + 39) >= 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 19, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids);
            }
            v8 = 0;
            goto LABEL_108;
          }
LABEL_70:
          v27 = *((_DWORD *)this + 39);
          if ( v27 == -1062600702 )
          {
            if ( (int)v25 >= 0 )
            {
              v23 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 225) < 3u )
              {
                goto LABEL_108;
              }
              v24 = 22;
              goto LABEL_107;
            }
            v28 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 225) < 3u )
            {
LABEL_81:
              v8 = *((_DWORD *)this + 38);
              goto LABEL_108;
            }
            v29 = 23;
LABEL_80:
            WPP_SF_d(v28[27], v29, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids, v25);
            goto LABEL_81;
          }
          if ( v27 >= 0 )
          {
            v28 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 225) < 3u )
            {
              goto LABEL_81;
            }
            v29 = 27;
            goto LABEL_80;
          }
          if ( (_DWORD)v25 == -1062600702 )
          {
            v30 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 225) < 3u )
            {
              goto LABEL_98;
            }
            v31 = 24;
          }
          else
          {
            if ( (int)v25 < 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u )
              {
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 27),
                  25,
                  WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids,
                  v25,
                  *((_DWORD *)this + 39));
              }
              goto LABEL_98;
            }
            v30 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 225) < 3u )
            {
LABEL_98:
              v8 = *((_DWORD *)this + 39);
              goto LABEL_108;
            }
            v31 = 26;
          }
          WPP_SF_d(v30[27], v31, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids, (unsigned int)v27);
          goto LABEL_98;
        }
        if ( (_DWORD)v25 != -1062600702 )
          goto LABEL_70;
        v26 = *((_DWORD *)this + 39);
        if ( v26 == -1062600702 )
        {
          v23 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 225) < 3u )
          {
            goto LABEL_108;
          }
          v24 = 20;
        }
        else
        {
          if ( v26 < 0 )
            goto LABEL_70;
          v23 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 225) < 3u )
          {
            goto LABEL_108;
          }
          v24 = 21;
        }
      }
      else
      {
        v8 = -2147024882;
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 225) < 3u )
        {
          goto LABEL_108;
        }
        v24 = 15;
      }
LABEL_107:
      WPP_SF_(v23[27], v24, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids);
      goto LABEL_108;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 12, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids);
  }
  v8 = -2147024882;
LABEL_108:
  v32 = *((_QWORD *)this + 17);
  *((_WORD *)this + 122) = 0;
  if ( v32 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 8LL))(v32);
    *((_QWORD *)this + 17) = 0;
  }
  v33 = *((_QWORD *)this + 18);
  if ( v33 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    *((_QWORD *)this + 18) = 0;
  }
  if ( (v8 & 0x80FF0000) == 0x80AA0000 )
    Imapi2Utility::SetErrorDescription(v8, (int)&CLSID_MsftWriteEngine2, a3);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180033b60  push    rbx
0x180033b62  push    rbp
0x180033b63  push    rsi
0x180033b64  push    rdi
0x180033b65  push    r12
0x180033b67  push    r13
0x180033b69  push    r14
0x180033b6b  push    r15
0x180033b6d  sub     rsp, 88h
0x180033b74  mov     rax, cs:__security_cookie
0x180033b7b  xor     rax, rsp
0x180033b7e  mov     [rsp+0C8h+var_58], rax
0x180033b83  xor     r13d, r13d
0x180033b86  lea     rsi, WPP_GLOBAL_Control
0x180033b8d  mov     [rsp+0C8h+var_78], r13
0x180033b92  mov     r12d, r9d
0x180033b95  mov     [rcx+98h], r13
0x180033b9c  mov     r15d, r8d
0x180033b9f  lea     rbp, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids
0x180033ba6  mov     r14, rdx
0x180033ba9  mov     rdi, rcx
0x180033bac  mov     ebx, r13d
0x180033baf  test    rdx, rdx
0x180033bb2  jnz     short loc_180033BF3
0x180033bb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180033bbb  cmp     rcx, rsi
0x180033bbe  jz      short loc_180033BEC
0x180033bc0  test    byte ptr [rcx+0E4h], 4
0x180033bc7  jz      short loc_180033BEC
0x180033bc9  cmp     byte ptr [rcx+0E1h], 3
0x180033bd0  jb      short loc_180033BEC
0x180033bd2  mov     rcx, [rcx+0D8h]
0x180033bd9  lea     edx, [r14+0Ah]
0x180033bdd  mov     r8, rbp
0x180033be0  call    WPP_SF_
0x180033be5  mov     rcx, cs:WPP_GLOBAL_Control
0x180033bec  mov     ebx, 80004003h
0x180033bf1  jmp     short loc_180033BFA
0x180033bf3  mov     rcx, cs:WPP_GLOBAL_Control
0x180033bfa  cmp     [rdi+70h], r13
0x180033bfe  jnz     short loc_180033C35
0x180033c00  cmp     rcx, rsi
0x180033c03  jz      short loc_180033C2B
0x180033c05  test    byte ptr [rcx+0E4h], 4
0x180033c0c  jz      short loc_180033C2B
0x180033c0e  cmp     byte ptr [rcx+0E1h], 3
0x180033c15  jb      short loc_180033C2B
0x180033c17  mov     rcx, [rcx+0D8h]
0x180033c1e  mov     edx, 0Bh
0x180033c23  mov     r8, rbp
0x180033c26  call    WPP_SF_
0x180033c2b  mov     ebx, 0C0AA0003h
0x180033c30  jmp     loc_18003426F
0x180033c35  test    ebx, ebx
0x180033c37  js      loc_18003426F
0x180033c3d  cmp     [rdi+80h], r13
0x180033c44  jnz     loc_180033CFC
0x180033c4a  mov     ecx, 60h ; '`'; Size
0x180033c4f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180033c54  test    rax, rax
0x180033c57  jz      loc_180033D4C
0x180033c5d  mov     rcx, rax; this
0x180033c60  call    ??0CWriteEngineSectionResources@@QEAA@XZ; CWriteEngineSectionResources::CWriteEngineSectionResources(void)
0x180033c65  mov     rsi, rax
0x180033c68  test    rax, rax
0x180033c6b  jz      loc_180033D45
0x180033c71  mov     rax, [rdi+0E0h]
0x180033c78  mov     rdx, rdi; struct CMsftWriteEngine2 *
0x180033c7b  mov     r8, [rdi+78h]; struct CWriteEngineStaticDriveInformation *
0x180033c7f  mov     rcx, rsi; this
0x180033c82  mov     [rsp+0C8h+var_A0], rax; void *
0x180033c87  mov     rax, [rdi+0C8h]
0x180033c8e  mov     qword ptr [rsp+0C8h+dwWakeMask], rax; void *
0x180033c93  call    ?Init@CWriteEngineSectionResources@@QEAAJPEAVCMsftWriteEngine2@@PEAVCWriteEngineStaticDriveInformation@@KPEAX2@Z; CWriteEngineSectionResources::Init(CMsftWriteEngine2 *,CWriteEngineStaticDriveInformation *,ulong,void *,void *)
0x180033c98  mov     ebx, eax
0x180033c9a  test    eax, eax
0x180033c9c  jns     short loc_180033CEE
0x180033c9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180033ca5  lea     rdx, WPP_GLOBAL_Control
0x180033cac  cmp     rcx, rdx
0x180033caf  jz      short loc_180033CDA
0x180033cb1  test    byte ptr [rcx+0E4h], 4
0x180033cb8  jz      short loc_180033CDA
0x180033cba  cmp     byte ptr [rcx+0E1h], 3
0x180033cc1  jb      short loc_180033CDA
0x180033cc3  mov     rcx, [rcx+0D8h]
0x180033cca  mov     edx, 0Dh
0x180033ccf  mov     r9d, eax
0x180033cd2  mov     r8, rbp
0x180033cd5  call    WPP_SF_d
0x180033cda  mov     rax, [rsi]
0x180033cdd  mov     rcx, rsi
0x180033ce0  mov     rax, [rax+8]
0x180033ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033ce9  jmp     loc_18003426F
0x180033cee  mov     [rdi+80h], rsi
0x180033cf5  lea     rsi, WPP_GLOBAL_Control
0x180033cfc  mov     rcx, [rdi+80h]; this
0x180033d03  call    ?Reset@CWriteEngineSectionResources@@QEAAJXZ; CWriteEngineSectionResources::Reset(void)
0x180033d08  mov     ebx, eax
0x180033d0a  test    eax, eax
0x180033d0c  jns     short loc_180033D88
0x180033d0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180033d15  cmp     rcx, rsi
0x180033d18  jz      loc_18003426F
0x180033d1e  test    byte ptr [rcx+0E4h], 4
0x180033d25  jz      loc_18003426F
0x180033d2b  cmp     byte ptr [rcx+0E1h], 3
0x180033d32  jb      loc_18003426F
0x180033d38  mov     edx, 0Eh
0x180033d3d  mov     r8, rbp
0x180033d40  jmp     loc_180033E30
0x180033d45  lea     rsi, WPP_GLOBAL_Control
0x180033d4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180033d53  cmp     rcx, rsi
0x180033d56  jz      short loc_180033D7E
0x180033d58  test    byte ptr [rcx+0E4h], 4
0x180033d5f  jz      short loc_180033D7E
0x180033d61  cmp     byte ptr [rcx+0E1h], 3
0x180033d68  jb      short loc_180033D7E
0x180033d6a  mov     rcx, [rcx+0D8h]
0x180033d71  mov     edx, 0Ch
0x180033d76  mov     r8, rbp
0x180033d79  call    WPP_SF_
0x180033d7e  mov     ebx, 8007000Eh
0x180033d83  jmp     loc_18003426F
0x180033d88  mov     ecx, 48h ; 'H'; Size
0x180033d8d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180033d92  test    rax, rax
0x180033d95  jz      loc_180034238
0x180033d9b  mov     rcx, rax; this
0x180033d9e  call    ??0CWriteEngineSectionParameters@@QEAA@XZ; CWriteEngineSectionParameters::CWriteEngineSectionParameters(void)
0x180033da3  mov     rbp, rax
0x180033da6  test    rax, rax
0x180033da9  jz      loc_180034231
0x180033daf  mov     ecx, [rdi+100h]
0x180033db5  mov     r8d, r13d
0x180033db8  cmp     [rdi+0F6h], r13w
0x180033dc0  mov     r9d, [rdi+0F8h]; int
0x180033dc7  mov     rdx, [rdi+78h]; struct CWriteEngineStaticDriveInformation *
0x180033dcb  setnz   r8b; __int16
0x180033dcf  mov     [rsp+0C8h+var_88], r14; struct IStream *
0x180033dd4  mov     [rsp+0C8h+var_90], ecx; int
0x180033dd8  mov     ecx, [rdi+0FCh]
0x180033dde  mov     [rsp+0C8h+var_98], r12d; int
0x180033de3  mov     dword ptr [rsp+0C8h+var_A0], r15d; int
0x180033de8  mov     [rsp+0C8h+dwWakeMask], ecx; int
0x180033dec  mov     rcx, rax; this
0x180033def  call    ?Init@CWriteEngineSectionParameters@@QEAAJPEAVCWriteEngineStaticDriveInformation@@FJJJJJPEAUIStream@@@Z; CWriteEngineSectionParameters::Init(CWriteEngineStaticDriveInformation *,short,long,long,long,long,long,IStream *)
0x180033df4  mov     ebx, eax
0x180033df6  test    eax, eax
0x180033df8  jns     short loc_180033E44
0x180033dfa  mov     rcx, cs:WPP_GLOBAL_Control
0x180033e01  cmp     rcx, rsi
0x180033e04  jz      loc_18003426F
0x180033e0a  test    byte ptr [rcx+0E4h], 4
0x180033e11  jz      loc_18003426F
0x180033e17  cmp     byte ptr [rcx+0E1h], 3
0x180033e1e  jb      loc_18003426F
0x180033e24  mov     edx, 10h
0x180033e29  lea     r8, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids
0x180033e30  mov     rcx, [rcx+0D8h]
0x180033e37  mov     r9d, eax
0x180033e3a  call    WPP_SF_d
0x180033e3f  jmp     loc_18003426F
0x180033e44  lea     rcx, [rsp+0C8h+var_78]
0x180033e49  call    ?CreateInstance@?$CComObject@VCWriteEngineEventArgs@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CWriteEngineEventArgs>::CreateInstance(ATL::CComObject<CWriteEngineEventArgs> * *)
0x180033e4e  mov     rsi, [rsp+0C8h+var_78]
0x180033e53  mov     ebx, eax
0x180033e55  test    rsi, rsi
0x180033e58  jnz     short loc_180033E9F
0x180033e5a  mov     ebx, 8007000Eh
0x180033e5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180033e66  lea     rdx, WPP_GLOBAL_Control
0x180033e6d  cmp     rcx, rdx
0x180033e70  jz      loc_18003426F
0x180033e76  test    byte ptr [rcx+0E4h], 4
0x180033e7d  jz      loc_18003426F
0x180033e83  cmp     byte ptr [rcx+0E1h], 3
0x180033e8a  jb      loc_18003426F
0x180033e90  lea     edx, [rsi+11h]
0x180033e93  lea     r8, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids
0x180033e9a  jmp     loc_180034263
0x180033e9f  mov     rax, [rsi]
0x180033ea2  mov     rcx, rsi
0x180033ea5  mov     rax, [rax+8]
0x180033ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033eae  test    ebx, ebx
0x180033eb0  js      loc_18003426F
0x180033eb6  mov     [rsi+40h], r15d
0x180033eba  mov     [rsi+44h], r12d
0x180033ebe  mov     [rsi+48h], r15d
0x180033ec2  mov     [rsi+4Ch], r15d
0x180033ec6  mov     qword ptr [rsi+50h], 200000h
0x180033ece  mov     qword ptr [rsi+58h], 80000h
0x180033ed6  mov     rax, [rdi+80h]
0x180033edd  mov     ecx, [rax+48h]
0x180033ee0  imul    ecx, [rax+20h]
0x180033ee4  mov     eax, 80004005h
0x180033ee9  mov     [rsi+58h], ecx
0x180033eec  mov     rcx, rdi; this
0x180033eef  mov     [rdi+90h], rsi
0x180033ef6  mov     [rdi+88h], rbp
0x180033efd  mov     [rdi+98h], eax
0x180033f03  mov     [rdi+9Ch], eax
0x180033f09  mov     word ptr [rdi+0F4h], 0FFFFh
0x180033f12  call    ?UpdateProgress@CMsftWriteEngine2@@QEAAXXZ; CMsftWriteEngine2::UpdateProgress(void)
0x180033f17  mov     rcx, [rdi+0B8h]; hEvent
0x180033f1e  call    cs:__imp_ResetEvent
0x180033f24  mov     rcx, [rdi+0A8h]; hEvent
0x180033f2b  call    cs:__imp_SetEvent
0x180033f31  mov     rax, [rdi+0B8h]
0x180033f38  mov     esi, 3
0x180033f3d  mov     [rsp+0C8h+pHandles], rax
0x180033f42  mov     rax, [rdi+0C8h]
0x180033f49  mov     [rsp+0C8h+var_68], rax
0x180033f4e  mov     rax, [rdi+0E0h]
0x180033f55  mov     [rsp+0C8h+var_60], rax
0x180033f5a  mov     r9d, 1F4h; dwMilliseconds
0x180033f60  mov     [rsp+0C8h+dwWakeMask], r13d; dwWakeMask
0x180033f65  xor     r8d, r8d; fWaitAll
0x180033f68  lea     rdx, [rsp+0C8h+pHandles]; pHandles
0x180033f6d  mov     ecx, esi; nCount
0x180033f6f  call    cs:__imp_MsgWaitForMultipleObjects
0x180033f75  cmp     eax, 102h
0x180033f7a  jnz     short loc_180033F86
0x180033f7c  mov     rcx, rdi; this
0x180033f7f  call    ?UpdateProgress@CMsftWriteEngine2@@QEAAXXZ; CMsftWriteEngine2::UpdateProgress(void)
0x180033f84  jmp     short loc_180033F5A
0x180033f86  mov     rcx, [rdi+0B8h]; hEvent
0x180033f8d  call    cs:__imp_ResetEvent
0x180033f93  mov     rcx, rdi; this
0x180033f96  call    ?UpdateProgress@CMsftWriteEngine2@@QEAAXXZ; CMsftWriteEngine2::UpdateProgress(void)
0x180033f9b  mov     r9d, [rdi+98h]
0x180033fa2  mov     ebx, 0C0AA0002h
0x180033fa7  test    r9d, r9d
0x180033faa  js      short loc_180033FFE
0x180033fac  cmp     [rdi+9Ch], r13d
0x180033fb3  jl      loc_18003408B
0x180033fb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180033fc0  lea     rdx, WPP_GLOBAL_Control
0x180033fc7  cmp     rcx, rdx
0x180033fca  jz      short loc_180033FF6
0x180033fcc  test    byte ptr [rcx+0E4h], 4
0x180033fd3  jz      short loc_180033FF6
0x180033fd5  cmp     byte ptr [rcx+0E1h], 4
0x180033fdc  jb      short loc_180033FF6
0x180033fde  mov     rcx, [rcx+0D8h]
0x180033fe5  lea     r8, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids
0x180033fec  mov     edx, 13h
0x180033ff1  call    WPP_SF_
0x180033ff6  mov     ebx, r13d
0x180033ff9  jmp     loc_18003426F
0x180033ffe  cmp     r9d, ebx
0x180034001  jnz     loc_18003408B
0x180034007  mov     eax, [rdi+9Ch]
0x18003400d  cmp     eax, ebx
0x18003400f  jnz     short loc_18003404C
0x180034011  mov     rcx, cs:WPP_GLOBAL_Control
0x180034018  lea     rdx, WPP_GLOBAL_Control
0x18003401f  cmp     rcx, rdx
0x180034022  jz      loc_18003426F
0x180034028  test    byte ptr [rcx+0E4h], 4
0x18003402f  jz      loc_18003426F
0x180034035  cmp     [rcx+0E1h], sil
0x18003403c  jb      loc_18003426F
0x180034042  mov     edx, 14h
0x180034047  jmp     loc_180033E93
0x18003404c  test    eax, eax
0x18003404e  js      short loc_18003408B
0x180034050  mov     rcx, cs:WPP_GLOBAL_Control
0x180034057  lea     rdx, WPP_GLOBAL_Control
0x18003405e  cmp     rcx, rdx
0x180034061  jz      loc_18003426F
0x180034067  test    byte ptr [rcx+0E4h], 4
0x18003406e  jz      loc_18003426F
0x180034074  cmp     [rcx+0E1h], sil
0x18003407b  jb      loc_18003426F
0x180034081  mov     edx, 15h
0x180034086  jmp     loc_180033E93
0x18003408b  mov     eax, [rdi+9Ch]
0x180034091  cmp     eax, ebx
0x180034093  jnz     loc_180034121
0x180034099  test    r9d, r9d
0x18003409c  js      short loc_1800340D9
0x18003409e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800340a5  lea     rdx, WPP_GLOBAL_Control
0x1800340ac  cmp     rcx, rdx
0x1800340af  jz      loc_18003426F
0x1800340b5  test    byte ptr [rcx+0E4h], 4
0x1800340bc  jz      loc_18003426F
0x1800340c2  cmp     [rcx+0E1h], sil
0x1800340c9  jb      loc_18003426F
0x1800340cf  mov     edx, 16h
0x1800340d4  jmp     loc_180033E93
0x1800340d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800340e0  lea     rdx, WPP_GLOBAL_Control
0x1800340e7  cmp     rcx, rdx
0x1800340ea  jz      short loc_180034116
0x1800340ec  test    byte ptr [rcx+0E4h], 4
  ... truncated ...
```
