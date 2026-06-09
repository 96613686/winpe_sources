# CMsftDiscFormat2Data::get_WriteProtectStatus(_IMAPI_MEDIA_WRITE_PROTECT_STATE *)

- ea: `0x180022550`
- end: `0x180022e84`
- name: `?get_WriteProtectStatus@CMsftDiscFormat2Data@@UEAAJPEAW4_IMAPI_MEDIA_WRITE_PROTECT_STATE@@@Z`
- size: `2356`
- prototype: `__int64 __fastcall(CMsftDiscFormat2Data *__hidden this, enum _IMAPI_MEDIA_WRITE_PROTECT_STATE *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180002fc8`
- `0x180009b80`
- `0x18000a804`
- `0x1800140f4`
- `0x180016778`
- `0x180022550`
- `0x1800236b4`
- `0x18004a010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800228be`
- `ole32!CoTaskMemFree` at `0x180022a41`
- `ole32!CoTaskMemFree` at `0x180022cab`
- `ole32!CoTaskMemFree` at `0x180022e0a`
- `ole32!CoTaskMemFree` at `0x1800228be`
- `ole32!CoTaskMemFree` at `0x180022a41`
- `ole32!CoTaskMemFree` at `0x180022cab`
- `ole32!CoTaskMemFree` at `0x180022e0a`

## pseudocode

```c
__int64 __fastcall CMsftDiscFormat2Data::get_WriteProtectStatus(
        struct IDiscRecorder2Ex **this,
        enum _IMAPI_MEDIA_WRITE_PROTECT_STATE *a2)
{
  signed int v4; // edi
  int v5; // eax
  const struct _GUID *v6; // r8
  int CurrentPhysicalMediaType; // eax
  int lpVtbl; // eax
  __int64 *v10; // r12
  enum _IMAPI_MEDIA_WRITE_PROTECT_STATE v11; // r15d
  __int64 v12; // rcx
  int v13; // eax
  char v14; // al
  PVOID *v15; // rcx
  __int64 v16; // rcx
  int v17; // eax
  __int64 *v18; // rcx
  __int64 v19; // rcx
  int v20; // eax
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  char *v23; // r12
  char v24; // al
  PVOID *v25; // rcx
  __int64 v26; // rcx
  int v27; // eax
  int v28; // [rsp+28h] [rbp-28h]
  int v29; // [rsp+30h] [rbp-20h]
  LPVOID pv; // [rsp+40h] [rbp-10h] BYREF
  LPVOID v31; // [rsp+48h] [rbp-8h] BYREF
  struct IDiscRecorder2Ex v33; // [rsp+A0h] [rbp+50h] BYREF
  unsigned int v34; // [rsp+A8h] [rbp+58h] BYREF

  LODWORD(v33.lpVtbl) = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 37), 262, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
    }
    return (unsigned int)-2147467261;
  }
  v5 = CMsftDiscFormat2Data::ValidateRecorderSet((CMsftDiscFormat2Data *)this);
  v6 = 0;
  v4 = v5;
  if ( v5 < 0 )
  {
    lpVtbl = (int)v33.lpVtbl;
    goto LABEL_21;
  }
  *a2 = 0;
  CurrentPhysicalMediaType = Imapi2Utility::GetCurrentPhysicalMediaType(this[27], &v33, 0);
  v6 = 0;
  v4 = CurrentPhysicalMediaType;
  if ( CurrentPhysicalMediaType < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 37),
        263,
        &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
        (unsigned int)CurrentPhysicalMediaType);
    }
    goto LABEL_164;
  }
  lpVtbl = (int)v33.lpVtbl;
  if ( LODWORD(v33.lpVtbl) != 1 && LODWORD(v33.lpVtbl) != 4 )
  {
LABEL_21:
    if ( v4 < 0 )
    {
LABEL_164:
      if ( (v4 & 0x80FF0000) == 0x80AA0000 )
        Imapi2Utility::SetErrorDescription(v4, (int)&CLSID_MsftDiscFormat2Data, v6);
      return (unsigned int)v4;
    }
    v10 = (__int64 *)(this + 27);
    v11 = 0;
    v31 = this + 27;
    if ( lpVtbl == 5 )
    {
      v12 = *v10;
      pv = 0;
      v34 = 0;
      v13 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v12 + 48LL))(v12, 9, 0);
      v4 = v13;
      if ( v13 == -1062600178 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 37), 265, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
        }
        v4 = 0;
      }
      else if ( v13 >= 0 )
      {
        if ( v34 >= 4 )
        {
          v14 = *(_BYTE *)pv;
          if ( (*(_BYTE *)pv & 2) != 0 )
          {
            v15 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 37), 268, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
              v14 = *(_BYTE *)pv;
              v15 = (PVOID *)WPP_GLOBAL_Control;
            }
            v11 = IMAPI_WRITEPROTECTED_BY_SOFTWARE_WRITE_PROTECT;
          }
          else
          {
            v15 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( (v14 & 4) != 0 )
          {
            if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 308) & 4) != 0 && *((_BYTE *)v15 + 305) >= 4u )
            {
              WPP_SF_(v15[37], 269, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
              v14 = *(_BYTE *)pv;
              v15 = (PVOID *)WPP_GLOBAL_Control;
            }
            v11 |= 2u;
          }
          if ( (v14 & 8) != 0 )
          {
            if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 308) & 4) != 0 && *((_BYTE *)v15 + 305) >= 4u )
              WPP_SF_(v15[37], 270, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
            v11 |= 4u;
          }
          v10 = (__int64 *)(this + 27);
        }
        else
        {
          v4 = -1062599937;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
          {
            WPP_SF_DDDd(*((_QWORD *)WPP_GLOBAL_Control + 37), 267, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
          }
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 37),
          266,
          &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
          (unsigned int)v13);
      }
      CoTaskMemFree(pv);
      v6 = 0;
      if ( v4 < 0 )
        goto LABEL_164;
      lpVtbl = (int)v33.lpVtbl;
    }
    if ( (unsigned int)(lpVtbl - 6) > 1 )
    {
      v18 = v10;
    }
    else
    {
      v16 = *v10;
      pv = 0;
      v34 = 0;
      v17 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v16 + 48LL))(v16, 48, 1464091392);
      v4 = v17;
      if ( v17 == -1062600178 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 37), 271, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
        }
        v4 = 0;
      }
      else if ( v17 >= 0 )
      {
        if ( v34 >= 0x30 )
        {
          if ( (*((_BYTE *)pv + 47) & 3) != 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 37),
                274,
                &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
                *((_BYTE *)pv + 47) & 3);
            }
            v11 |= 0x10u;
          }
        }
        else
        {
          v4 = -1062599937;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
          {
            WPP_SF_DDDd(*((_QWORD *)WPP_GLOBAL_Control + 37), 273, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
          }
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 37),
          272,
          &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
          (unsigned int)v17);
      }
      CoTaskMemFree(pv);
      v6 = 0;
      if ( v4 < 0 )
        goto LABEL_164;
      v18 = (__int64 *)(this + 27);
    }
    v19 = *v18;
    pv = 0;
    v34 = 0;
    v20 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _DWORD, LPVOID *, unsigned int *))(*(_QWORD *)v19 + 48LL))(
            v19,
            192,
            0,
            0,
            0,
            &pv,
            &v34);
    v4 = v20;
    if ( v20 == -1062600178 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 305) < 4u )
      {
        goto LABEL_98;
      }
      v22 = 275;
    }
    else
    {
      if ( v20 != -1062600174 )
      {
        if ( v20 >= 0 )
        {
          if ( v34 >= 4 )
          {
            v23 = (char *)pv;
            v24 = *(_BYTE *)pv;
            if ( (*(_BYTE *)pv & 1) != 0 )
            {
              v25 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 37), 279, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
                v24 = *v23;
                v25 = (PVOID *)WPP_GLOBAL_Control;
              }
              v11 |= 1u;
            }
            else
            {
              v25 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( (v24 & 2) != 0 )
            {
              if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 308) & 4) != 0 && *((_BYTE *)v25 + 305) >= 4u )
              {
                WPP_SF_(v25[37], 280, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
                v24 = *v23;
                v25 = (PVOID *)WPP_GLOBAL_Control;
              }
              v11 |= 8u;
            }
            if ( (v24 & 4) != 0 )
            {
              if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 308) & 4) != 0 && *((_BYTE *)v25 + 305) >= 4u )
              {
                WPP_SF_(v25[37], 281, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
                v24 = *v23;
                v25 = (PVOID *)WPP_GLOBAL_Control;
              }
              v11 |= 2u;
            }
            if ( (v24 & 8) != 0 )
            {
              if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 308) & 4) != 0 && *((_BYTE *)v25 + 305) >= 4u )
                WPP_SF_(v25[37], 282, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
              v11 |= 4u;
            }
            v10 = (__int64 *)v31;
          }
          else
          {
            v4 = -1062599937;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
            {
              v29 = 4;
              v28 = 4;
              WPP_SF_DDDd(*((_QWORD *)WPP_GLOBAL_Control + 37), 278, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
            }
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 37),
            277,
            &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
            (unsigned int)v20);
        }
        goto LABEL_135;
      }
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 305) < 4u )
      {
LABEL_98:
        v4 = 0;
LABEL_135:
        CoTaskMemFree(pv);
        if ( v4 >= 0 )
        {
          v26 = *v10;
          v31 = 0;
          v34 = 0;
          v27 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, LPVOID *, unsigned int *, int, int))(*(_QWORD *)v26 + 104LL))(
                  v26,
                  29,
                  0,
                  &v31,
                  &v34,
                  v28,
                  v29);
          v4 = v27;
          if ( v27 == -1062600191 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 37), 283, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
            }
            v4 = 0;
          }
          else if ( v27 >= 0 )
          {
            if ( v34 >= 0xA )
            {
              if ( (*((_BYTE *)v31 + 4) & 1) != 0 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 37), 286, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
                }
                v11 |= 1u;
              }
            }
            else
            {
              v4 = -1062599937;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
              {
                WPP_SF_DDDd(*((_QWORD *)WPP_GLOBAL_Control + 37), 285, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
              }
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 37),
              284,
              &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
              (unsigned int)v27);
          }
          CoTaskMemFree(v31);
          if ( v4 >= 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 37),
                287,
                &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
                (unsigned int)v11);
            }
            *a2 = v11;
          }
        }
        goto LABEL_164;
      }
      v22 = 276;
    }
    WPP_SF_(v21[37], v22, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
    goto LABEL_98;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 37),
      264,
      &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
      LODWORD(v33.lpVtbl));
  }
  *a2 = IMAPI_WRITEPROTECTED_READ_ONLY_MEDIA;
  return 0;
}

```

## disassembly

```asm
0x180022550  mov     [rsp-38h+arg_0], rbx
0x180022555  mov     [rsp-38h+arg_8], rdx
0x18002255a  push    rbp
0x18002255b  push    rsi
0x18002255c  push    rdi
0x18002255d  push    r12
0x18002255f  push    r13
0x180022561  push    r14
0x180022563  push    r15
0x180022565  mov     rbp, rsp
0x180022568  sub     rsp, 50h
0x18002256c  mov     dword ptr [rbp+arg_10.lpVtbl], 0
0x180022573  mov     r15, rdx
0x180022576  mov     r13, rcx
0x180022579  test    rdx, rdx
0x18002257c  jnz     short loc_1800225C7
0x18002257e  mov     rcx, cs:WPP_GLOBAL_Control
0x180022585  lea     rsi, WPP_GLOBAL_Control
0x18002258c  cmp     rcx, rsi
0x18002258f  jz      short loc_1800225BD
0x180022591  lea     ebx, [rdx+4]
0x180022594  test    [rcx+134h], bl
0x18002259a  jz      short loc_1800225BD
0x18002259c  cmp     byte ptr [rcx+131h], 3
0x1800225a3  jb      short loc_1800225BD
0x1800225a5  mov     rcx, [rcx+128h]
0x1800225ac  lea     r8, WPP_539367e8d73e3780733cc4391ef3a150_Traceguids
0x1800225b3  mov     edx, 106h
0x1800225b8  call    WPP_SF_
0x1800225bd  mov     edi, 80004003h
0x1800225c2  jmp     loc_180022E6A
0x1800225c7  call    ?ValidateRecorderSet@CMsftDiscFormat2Data@@AEAAJXZ; CMsftDiscFormat2Data::ValidateRecorderSet(void)
0x1800225cc  xor     r8d, r8d; enum _IMAPI_MEDIA_PHYSICAL_TYPE *
0x1800225cf  mov     edi, eax
0x1800225d1  mov     ebx, 4
0x1800225d6  test    eax, eax
0x1800225d8  js      loc_1800226A2
0x1800225de  mov     [r15], r8d
0x1800225e1  lea     rdx, [rbp+arg_10]; struct IDiscRecorder2Ex *
0x1800225e5  mov     rcx, [r13+0D8h]; this
0x1800225ec  call    ?GetCurrentPhysicalMediaType@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@PEAW4_IMAPI_MEDIA_PHYSICAL_TYPE@@@Z; Imapi2Utility::GetCurrentPhysicalMediaType(IDiscRecorder2Ex *,_IMAPI_MEDIA_PHYSICAL_TYPE *)
0x1800225f1  xor     r8d, r8d
0x1800225f4  mov     edi, eax
0x1800225f6  test    eax, eax
0x1800225f8  jns     short loc_18002264A
0x1800225fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180022601  lea     rsi, WPP_GLOBAL_Control
0x180022608  cmp     rcx, rsi
0x18002260b  jz      loc_180022E4E
0x180022611  test    [rcx+134h], bl
0x180022617  jz      loc_180022E4E
0x18002261d  cmp     byte ptr [rcx+131h], 3
0x180022624  jb      loc_180022E4E
0x18002262a  mov     rcx, [rcx+128h]
0x180022631  lea     r8, WPP_539367e8d73e3780733cc4391ef3a150_Traceguids
0x180022638  mov     edx, 107h
0x18002263d  mov     r9d, eax
0x180022640  call    WPP_SF_d
0x180022645  jmp     loc_180022E4E
0x18002264a  mov     eax, dword ptr [rbp+arg_10.lpVtbl]
0x18002264d  cmp     eax, 1
0x180022650  jz      short loc_180022656
0x180022652  cmp     eax, ebx
0x180022654  jnz     short loc_1800226A5
0x180022656  mov     rcx, cs:WPP_GLOBAL_Control
0x18002265d  lea     rsi, WPP_GLOBAL_Control
0x180022664  cmp     rcx, rsi
0x180022667  jz      short loc_180022694
0x180022669  test    [rcx+134h], bl
0x18002266f  jz      short loc_180022694
0x180022671  cmp     [rcx+131h], bl
0x180022677  jb      short loc_180022694
0x180022679  mov     rcx, [rcx+128h]
0x180022680  lea     r8, WPP_539367e8d73e3780733cc4391ef3a150_Traceguids
0x180022687  mov     edx, 108h
0x18002268c  mov     r9d, eax
0x18002268f  call    WPP_SF_d
0x180022694  mov     dword ptr [r15], 4000h
0x18002269b  xor     eax, eax
0x18002269d  jmp     loc_180022E6C
0x1800226a2  mov     eax, dword ptr [rbp+arg_10.lpVtbl]
0x1800226a5  test    edi, edi
0x1800226a7  js      loc_180022E4E
0x1800226ad  lea     r12, [r13+0D8h]
0x1800226b4  mov     r15d, r8d
0x1800226b7  mov     [rbp+var_8], r12
0x1800226bb  lea     rsi, WPP_GLOBAL_Control
0x1800226c2  lea     r14, WPP_539367e8d73e3780733cc4391ef3a150_Traceguids
0x1800226c9  cmp     eax, 5
0x1800226cc  jnz     loc_1800228D2
0x1800226d2  mov     rcx, [r12]
0x1800226d6  lea     rdx, [rbp+arg_18]
0x1800226da  mov     qword ptr [rsp+50h+var_20], rdx
0x1800226df  xor     r9d, r9d
0x1800226e2  mov     [rbp+pv], r8
0x1800226e6  lea     rdx, [rbp+pv]
0x1800226ea  mov     [rbp+arg_18], r8d
0x1800226ee  mov     rax, [rcx]
0x1800226f1  mov     [rsp+50h+var_28], rdx
0x1800226f6  lea     edx, [r9+9]
0x1800226fa  mov     dword ptr [rsp+50h+var_30], r8d
0x1800226ff  xor     r8d, r8d
0x180022702  mov     rax, [rax+30h]
0x180022706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002270b  mov     edi, eax
0x18002270d  cmp     eax, 0C0AA020Eh
0x180022712  jnz     short loc_18002274B
0x180022714  mov     rcx, cs:WPP_GLOBAL_Control
0x18002271b  cmp     rcx, rsi
0x18002271e  jz      short loc_180022744
0x180022720  test    [rcx+134h], bl
0x180022726  jz      short loc_180022744
0x180022728  cmp     [rcx+131h], bl
0x18002272e  jb      short loc_180022744
0x180022730  mov     rcx, [rcx+128h]
0x180022737  mov     edx, 109h
0x18002273c  mov     r8, r14
0x18002273f  call    WPP_SF_
0x180022744  xor     edi, edi
0x180022746  jmp     loc_1800228BA
0x18002274b  test    eax, eax
0x18002274d  jns     short loc_180022794
0x18002274f  mov     rcx, cs:WPP_GLOBAL_Control
0x180022756  cmp     rcx, rsi
0x180022759  jz      loc_1800228BA
0x18002275f  test    [rcx+134h], bl
0x180022765  jz      loc_1800228BA
0x18002276b  cmp     byte ptr [rcx+131h], 3
0x180022772  jb      loc_1800228BA
0x180022778  mov     rcx, [rcx+128h]
0x18002277f  mov     edx, 10Ah
0x180022784  mov     r9d, eax
0x180022787  mov     r8, r14
0x18002278a  call    WPP_SF_d
0x18002278f  jmp     loc_1800228BA
0x180022794  mov     r9d, [rbp+arg_18]
0x180022798  cmp     r9d, ebx
0x18002279b  jnb     short loc_1800227F1
0x18002279d  mov     edi, 0C0AA02FFh
0x1800227a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800227a9  cmp     rcx, rsi
0x1800227ac  jz      loc_1800228BA
0x1800227b2  test    [rcx+134h], bl
0x1800227b8  jz      loc_1800228BA
0x1800227be  cmp     byte ptr [rcx+131h], 3
0x1800227c5  jb      loc_1800228BA
0x1800227cb  mov     rcx, [rcx+128h]
0x1800227d2  mov     edx, 10Bh
0x1800227d7  mov     [rsp+50h+var_20], ebx
0x1800227db  mov     r8, r14
0x1800227de  mov     dword ptr [rsp+50h+var_28], ebx
0x1800227e2  mov     dword ptr [rsp+50h+var_30], r9d
0x1800227e7  call    WPP_SF_DDDd
0x1800227ec  jmp     loc_1800228BA
0x1800227f1  mov     r12, [rbp+pv]
0x1800227f5  mov     al, [r12]
0x1800227f9  test    al, 2
0x1800227fb  jz      short loc_180022840
0x1800227fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180022804  cmp     rcx, rsi
0x180022807  jz      short loc_180022838
0x180022809  test    [rcx+134h], bl
0x18002280f  jz      short loc_180022838
0x180022811  cmp     [rcx+131h], bl
0x180022817  jb      short loc_180022838
0x180022819  mov     rcx, [rcx+128h]
0x180022820  mov     edx, 10Ch
0x180022825  mov     r8, r14
0x180022828  call    WPP_SF_
0x18002282d  mov     al, [r12]
0x180022831  mov     rcx, cs:WPP_GLOBAL_Control
0x180022838  mov     r15d, 8
0x18002283e  jmp     short loc_180022847
0x180022840  mov     rcx, cs:WPP_GLOBAL_Control
0x180022847  test    bl, al
0x180022849  jz      short loc_180022883
0x18002284b  cmp     rcx, rsi
0x18002284e  jz      short loc_18002287F
0x180022850  test    [rcx+134h], bl
0x180022856  jz      short loc_18002287F
0x180022858  cmp     [rcx+131h], bl
0x18002285e  jb      short loc_18002287F
0x180022860  mov     rcx, [rcx+128h]
0x180022867  mov     edx, 10Dh
0x18002286c  mov     r8, r14
0x18002286f  call    WPP_SF_
0x180022874  mov     al, [r12]
0x180022878  mov     rcx, cs:WPP_GLOBAL_Control
0x18002287f  or      r15d, 2
0x180022883  test    al, 8
0x180022885  jz      short loc_1800228B3
0x180022887  cmp     rcx, rsi
0x18002288a  jz      short loc_1800228B0
0x18002288c  test    [rcx+134h], bl
0x180022892  jz      short loc_1800228B0
0x180022894  cmp     [rcx+131h], bl
0x18002289a  jb      short loc_1800228B0
0x18002289c  mov     rcx, [rcx+128h]
0x1800228a3  mov     edx, 10Eh
0x1800228a8  mov     r8, r14
0x1800228ab  call    WPP_SF_
0x1800228b0  or      r15d, ebx
0x1800228b3  lea     r12, [r13+0D8h]
0x1800228ba  mov     rcx, [rbp+pv]; pv
0x1800228be  call    cs:__imp_CoTaskMemFree
0x1800228c4  xor     r8d, r8d
0x1800228c7  test    edi, edi
0x1800228c9  js      loc_180022E4E
0x1800228cf  mov     eax, dword ptr [rbp+arg_10.lpVtbl]
0x1800228d2  add     eax, 0FFFFFFFAh
0x1800228d5  cmp     eax, 1
0x1800228d8  ja      loc_180022A5B
0x1800228de  mov     rcx, [r12]
0x1800228e2  lea     rdx, [rbp+arg_18]
0x1800228e6  mov     qword ptr [rsp+50h+var_20], rdx
0x1800228eb  xor     r9d, r9d
0x1800228ee  mov     [rbp+pv], r8
0x1800228f2  lea     rdx, [rbp+pv]
0x1800228f6  mov     [rbp+arg_18], r8d
0x1800228fa  mov     rax, [rcx]
0x1800228fd  mov     [rsp+50h+var_28], rdx
0x180022902  lea     edx, [r9+30h]
0x180022906  mov     dword ptr [rsp+50h+var_30], r8d
0x18002290b  mov     r8d, 57444300h
0x180022911  mov     rax, [rax+30h]
0x180022915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002291a  mov     edi, eax
0x18002291c  cmp     eax, 0C0AA020Eh
0x180022921  jnz     short loc_18002295A
0x180022923  mov     rcx, cs:WPP_GLOBAL_Control
0x18002292a  cmp     rcx, rsi
0x18002292d  jz      short loc_180022953
0x18002292f  test    [rcx+134h], bl
0x180022935  jz      short loc_180022953
0x180022937  cmp     [rcx+131h], bl
0x18002293d  jb      short loc_180022953
0x18002293f  mov     rcx, [rcx+128h]
0x180022946  mov     edx, 10Fh
0x18002294b  mov     r8, r14
0x18002294e  call    WPP_SF_
0x180022953  xor     edi, edi
0x180022955  jmp     loc_180022A3D
0x18002295a  test    eax, eax
0x18002295c  jns     short loc_1800229A3
0x18002295e  mov     rcx, cs:WPP_GLOBAL_Control
0x180022965  cmp     rcx, rsi
0x180022968  jz      loc_180022A3D
0x18002296e  test    [rcx+134h], bl
0x180022974  jz      loc_180022A3D
0x18002297a  cmp     byte ptr [rcx+131h], 3
0x180022981  jb      loc_180022A3D
0x180022987  mov     rcx, [rcx+128h]
0x18002298e  mov     edx, 110h
0x180022993  mov     r9d, eax
0x180022996  mov     r8, r14
0x180022999  call    WPP_SF_d
0x18002299e  jmp     loc_180022A3D
0x1800229a3  mov     r9d, [rbp+arg_18]
0x1800229a7  mov     eax, 30h ; '0'
0x1800229ac  cmp     r9d, eax
0x1800229af  jnb     short loc_1800229F6
0x1800229b1  mov     edi, 0C0AA02FFh
0x1800229b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800229bd  cmp     rcx, rsi
0x1800229c0  jz      short loc_180022A3D
0x1800229c2  test    [rcx+134h], bl
0x1800229c8  jz      short loc_180022A3D
0x1800229ca  cmp     byte ptr [rcx+131h], 3
0x1800229d1  jb      short loc_180022A3D
0x1800229d3  mov     rcx, [rcx+128h]
0x1800229da  mov     edx, 111h
0x1800229df  mov     [rsp+50h+var_20], eax
0x1800229e3  mov     r8, r14
0x1800229e6  mov     dword ptr [rsp+50h+var_28], eax
0x1800229ea  mov     dword ptr [rsp+50h+var_30], r9d
0x1800229ef  call    WPP_SF_DDDd
0x1800229f4  jmp     short loc_180022A3D
0x1800229f6  mov     rax, [rbp+pv]
0x1800229fa  test    byte ptr [rax+2Fh], 3
0x1800229fe  jz      short loc_180022A3D
0x180022a00  mov     rcx, cs:WPP_GLOBAL_Control
0x180022a07  cmp     rcx, rsi
0x180022a0a  jz      short loc_180022A39
0x180022a0c  test    [rcx+134h], bl
0x180022a12  jz      short loc_180022A39
0x180022a14  cmp     [rcx+131h], bl
0x180022a1a  jb      short loc_180022A39
0x180022a1c  movzx   r9d, byte ptr [rax+2Fh]
0x180022a21  mov     edx, 112h
0x180022a26  mov     rcx, [rcx+128h]
0x180022a2d  and     r9d, 3
0x180022a31  mov     r8, r14
0x180022a34  call    WPP_SF_d
0x180022a39  or      r15d, 10h
0x180022a3d  mov     rcx, [rbp+pv]; pv
0x180022a41  call    cs:__imp_CoTaskMemFree
0x180022a47  xor     r8d, r8d
0x180022a4a  test    edi, edi
0x180022a4c  js      loc_180022E4E
0x180022a52  lea     rcx, [r13+0D8h]
  ... truncated ...
```
