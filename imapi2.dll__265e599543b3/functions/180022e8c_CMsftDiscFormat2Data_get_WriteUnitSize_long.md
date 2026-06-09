# CMsftDiscFormat2Data::get_WriteUnitSize(long *)

- ea: `0x180022e8c`
- end: `0x180023314`
- name: `?get_WriteUnitSize@CMsftDiscFormat2Data@@QEAAJPEAJ@Z`
- size: `1160`
- prototype: `__int64 __fastcall(CMsftDiscFormat2Data *__hidden this, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180024900`

## callees

- `0x180002fc8`
- `0x180009b80`
- `0x18000a804`
- `0x1800140f4`
- `0x180016778`
- `0x180022e8c`
- `0x18004a010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800232c7`
- `ole32!CoTaskMemFree` at `0x1800232d9`
- `ole32!CoTaskMemFree` at `0x1800232c7`
- `ole32!CoTaskMemFree` at `0x1800232d9`

## pseudocode

```c
__int64 __fastcall CMsftDiscFormat2Data::get_WriteUnitSize(struct IDiscRecorder2Ex **this, unsigned int *a2)
{
  signed int v4; // edi
  __int64 v5; // r8
  int v6; // eax
  __int64 v7; // r8
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  unsigned int v10; // r12d
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  int v13; // eax
  enum _IMAPI_MEDIA_PHYSICAL_TYPE *v14; // r8
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  int CurrentPhysicalMediaType; // eax
  const struct _GUID *v18; // r8
  LPVOID v20[2]; // [rsp+30h] [rbp-10h] BYREF
  int v22; // [rsp+88h] [rbp+48h] BYREF
  struct IDiscRecorder2Ex v23; // [rsp+90h] [rbp+50h] BYREF
  LPVOID pv; // [rsp+98h] [rbp+58h] BYREF

  pv = 0;
  v20[0] = 0;
  v22 = 0;
  LODWORD(v23.lpVtbl) = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 37), 298, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
    }
    v4 = -2147467261;
    goto LABEL_80;
  }
  v4 = CMsftDiscFormat2Data::ValidateRecorderSet((CMsftDiscFormat2Data *)this);
  if ( v4 < 0 )
    goto LABEL_80;
  *a2 = 0;
  LOBYTE(v5) = 1;
  v6 = ((__int64 (__fastcall *)(struct IDiscRecorder2Ex *, __int64, __int64, LPVOID *, int *))this[27]->lpVtbl->GetFeaturePage)(
         this[27],
         32,
         v5,
         &pv,
         &v22);
  v4 = v6;
  if ( v6 == -1062600182 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
    {
      v9 = 299;
LABEL_34:
      WPP_SF_(v8[37], v9, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
    }
  }
  else if ( v6 == -1062600181 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
    {
      v9 = 300;
      goto LABEL_34;
    }
  }
  else if ( v6 >= 0 )
  {
    v10 = *((unsigned __int8 *)pv + 13) | (*((unsigned __int8 *)pv + 12) << 8);
    if ( v10 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 305) < 4u )
      {
        goto LABEL_29;
      }
      v12 = 302;
      goto LABEL_28;
    }
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
    {
      v9 = 303;
      goto LABEL_34;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 37),
      301,
      &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
      (unsigned int)v6);
  }
  LOBYTE(v7) = 1;
  v13 = ((__int64 (__fastcall *)(struct IDiscRecorder2Ex *, __int64, __int64, LPVOID *, int *))this[27]->lpVtbl->GetFeaturePage)(
          this[27],
          37,
          v7,
          v20,
          &v22);
  v4 = v13;
  if ( v13 == -1062600182 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
    {
      v16 = 304;
LABEL_59:
      WPP_SF_(v15[37], v16, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
      goto LABEL_60;
    }
    goto LABEL_60;
  }
  if ( v13 != -1062600181 )
  {
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 37),
          306,
          &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
          (unsigned int)v13);
      }
      goto LABEL_60;
    }
    v10 = *((unsigned __int8 *)v20[0] + 9) | (*((unsigned __int8 *)v20[0] + 8) << 8);
    if ( !v10 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
      {
        v16 = 308;
        goto LABEL_59;
      }
      goto LABEL_60;
    }
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 305) < 4u )
    {
LABEL_29:
      *a2 = v10;
      goto LABEL_80;
    }
    v12 = 307;
LABEL_28:
    WPP_SF_d(v11[37], v12, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, v10);
    goto LABEL_29;
  }
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
  {
    v16 = 305;
    goto LABEL_59;
  }
LABEL_60:
  CurrentPhysicalMediaType = Imapi2Utility::GetCurrentPhysicalMediaType(this[27], &v23, v14);
  v4 = CurrentPhysicalMediaType;
  if ( CurrentPhysicalMediaType >= 0 )
  {
    if ( SLODWORD(v23.lpVtbl) <= 9 )
    {
      if ( LODWORD(v23.lpVtbl) != 9
        && (LODWORD(v23.lpVtbl) == 2
         || LODWORD(v23.lpVtbl) == 3
         || LODWORD(v23.lpVtbl) != 5 && LODWORD(v23.lpVtbl) != 6 && (unsigned int)(LODWORD(v23.lpVtbl) - 7) >= 2) )
      {
        goto LABEL_72;
      }
LABEL_79:
      *a2 = 16;
      goto LABEL_80;
    }
    if ( LODWORD(v23.lpVtbl) == 10 || LODWORD(v23.lpVtbl) == 11 )
      goto LABEL_79;
    if ( LODWORD(v23.lpVtbl) != 12 )
    {
      if ( LODWORD(v23.lpVtbl) == 13 )
        goto LABEL_79;
      if ( (unsigned int)(LODWORD(v23.lpVtbl) - 18) <= 1 )
      {
        *a2 = 32;
        goto LABEL_80;
      }
    }
LABEL_72:
    *a2 = 1;
    goto LABEL_80;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 37),
      309,
      &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
      (unsigned int)CurrentPhysicalMediaType);
  }
LABEL_80:
  CoTaskMemFree(pv);
  pv = 0;
  CoTaskMemFree(v20[0]);
  v20[0] = 0;
  if ( (v4 & 0x80FF0000) == 0x80AA0000 )
    Imapi2Utility::SetErrorDescription(v4, (int)&CLSID_MsftDiscFormat2Data, v18);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180022e8c  mov     [rsp-38h+arg_0], rcx
0x180022e91  push    rbp
0x180022e92  push    rbx
0x180022e93  push    rsi
0x180022e94  push    rdi
0x180022e95  push    r12
0x180022e97  push    r14
0x180022e99  push    r15
0x180022e9b  mov     rbp, rsp
0x180022e9e  sub     rsp, 40h
0x180022ea2  xor     r14d, r14d
0x180022ea5  mov     r15, rdx
0x180022ea8  mov     [rbp+pv], r14
0x180022eac  mov     rbx, rcx
0x180022eaf  mov     [rbp+var_10], r14
0x180022eb3  mov     [rbp+arg_8], r14d
0x180022eb7  mov     dword ptr [rbp+arg_10.lpVtbl], r14d
0x180022ebb  test    rdx, rdx
0x180022ebe  jnz     short loc_180022F08
0x180022ec0  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ec7  lea     rsi, WPP_GLOBAL_Control
0x180022ece  cmp     rcx, rsi
0x180022ed1  jz      short loc_180022EFE
0x180022ed3  mov     bl, 4
0x180022ed5  test    [rcx+134h], bl
0x180022edb  jz      short loc_180022EFE
0x180022edd  cmp     byte ptr [rcx+131h], 3
0x180022ee4  jb      short loc_180022EFE
0x180022ee6  mov     rcx, [rcx+128h]
0x180022eed  lea     r8, WPP_539367e8d73e3780733cc4391ef3a150_Traceguids
0x180022ef4  mov     edx, 12Ah
0x180022ef9  call    WPP_SF_
0x180022efe  mov     edi, 80004003h
0x180022f03  jmp     loc_1800232C3
0x180022f08  call    ?ValidateRecorderSet@CMsftDiscFormat2Data@@AEAAJXZ; CMsftDiscFormat2Data::ValidateRecorderSet(void)
0x180022f0d  mov     edi, eax
0x180022f0f  test    eax, eax
0x180022f11  js      loc_1800232C3
0x180022f17  mov     [r15], r14d
0x180022f1a  lea     rdx, [rbp+arg_8]
0x180022f1e  mov     rcx, [rbx+0D8h]
0x180022f25  lea     r9, [rbp+pv]
0x180022f29  mov     [rsp+40h+var_20], rdx
0x180022f2e  mov     r8b, 1
0x180022f31  mov     edx, 20h ; ' '
0x180022f36  mov     rax, [rcx]
0x180022f39  mov     rax, [rax+60h]
0x180022f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f42  lea     r14, WPP_539367e8d73e3780733cc4391ef3a150_Traceguids
0x180022f49  mov     edi, eax
0x180022f4b  mov     bl, 4
0x180022f4d  cmp     eax, 0C0AA020Ah
0x180022f52  jnz     short loc_180022F8D
0x180022f54  mov     rcx, cs:WPP_GLOBAL_Control
0x180022f5b  lea     rsi, WPP_GLOBAL_Control
0x180022f62  cmp     rcx, rsi
0x180022f65  jz      loc_1800230AD
0x180022f6b  test    [rcx+134h], bl
0x180022f71  jz      loc_1800230AD
0x180022f77  cmp     [rcx+131h], bl
0x180022f7d  jb      loc_1800230AD
0x180022f83  mov     edx, 12Bh
0x180022f88  jmp     loc_18002309E
0x180022f8d  cmp     eax, 0C0AA020Bh
0x180022f92  jnz     short loc_180022FCD
0x180022f94  mov     rcx, cs:WPP_GLOBAL_Control
0x180022f9b  lea     rsi, WPP_GLOBAL_Control
0x180022fa2  cmp     rcx, rsi
0x180022fa5  jz      loc_1800230AD
0x180022fab  test    [rcx+134h], bl
0x180022fb1  jz      loc_1800230AD
0x180022fb7  cmp     [rcx+131h], bl
0x180022fbd  jb      loc_1800230AD
0x180022fc3  mov     edx, 12Ch
0x180022fc8  jmp     loc_18002309E
0x180022fcd  test    eax, eax
0x180022fcf  jns     short loc_18002301D
0x180022fd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180022fd8  lea     rsi, WPP_GLOBAL_Control
0x180022fdf  cmp     rcx, rsi
0x180022fe2  jz      loc_1800230AD
0x180022fe8  test    [rcx+134h], bl
0x180022fee  jz      loc_1800230AD
0x180022ff4  cmp     byte ptr [rcx+131h], 3
0x180022ffb  jb      loc_1800230AD
0x180023001  mov     rcx, [rcx+128h]
0x180023008  mov     edx, 12Dh
0x18002300d  mov     r9d, eax
0x180023010  mov     r8, r14
0x180023013  call    WPP_SF_d
0x180023018  jmp     loc_1800230AD
0x18002301d  mov     rax, [rbp+pv]
0x180023021  movzx   r12d, byte ptr [rax+0Ch]
0x180023026  movzx   eax, byte ptr [rax+0Dh]
0x18002302a  shl     r12d, 8
0x18002302e  or      r12d, eax
0x180023031  jz      short loc_180023075
0x180023033  mov     rcx, cs:WPP_GLOBAL_Control
0x18002303a  lea     rsi, WPP_GLOBAL_Control
0x180023041  cmp     rcx, rsi
0x180023044  jz      short loc_18002306D
0x180023046  test    [rcx+134h], bl
0x18002304c  jz      short loc_18002306D
0x18002304e  cmp     [rcx+131h], bl
0x180023054  jb      short loc_18002306D
0x180023056  mov     edx, 12Eh
0x18002305b  mov     rcx, [rcx+128h]
0x180023062  mov     r9d, r12d
0x180023065  mov     r8, r14
0x180023068  call    WPP_SF_d
0x18002306d  mov     [r15], r12d
0x180023070  jmp     loc_1800232C3
0x180023075  mov     rcx, cs:WPP_GLOBAL_Control
0x18002307c  lea     rsi, WPP_GLOBAL_Control
0x180023083  cmp     rcx, rsi
0x180023086  jz      short loc_1800230AD
0x180023088  test    [rcx+134h], bl
0x18002308e  jz      short loc_1800230AD
0x180023090  cmp     byte ptr [rcx+131h], 3
0x180023097  jb      short loc_1800230AD
0x180023099  mov     edx, 12Fh
0x18002309e  mov     rcx, [rcx+128h]
0x1800230a5  mov     r8, r14
0x1800230a8  call    WPP_SF_
0x1800230ad  mov     rcx, [rbp+arg_0]
0x1800230b1  lea     rdx, [rbp+arg_8]
0x1800230b5  mov     [rsp+40h+var_20], rdx
0x1800230ba  lea     r9, [rbp+var_10]
0x1800230be  mov     r8b, 1
0x1800230c1  mov     edx, 25h ; '%'
0x1800230c6  mov     rcx, [rcx+0D8h]
0x1800230cd  mov     rax, [rcx]
0x1800230d0  mov     rax, [rax+60h]
0x1800230d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230d9  mov     edi, eax
0x1800230db  cmp     eax, 0C0AA020Ah
0x1800230e0  jnz     short loc_180023114
0x1800230e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800230e9  cmp     rcx, rsi
0x1800230ec  jz      loc_18002320C
0x1800230f2  test    [rcx+134h], bl
0x1800230f8  jz      loc_18002320C
0x1800230fe  cmp     [rcx+131h], bl
0x180023104  jb      loc_18002320C
0x18002310a  mov     edx, 130h
0x18002310f  jmp     loc_1800231FD
0x180023114  cmp     eax, 0C0AA020Bh
0x180023119  jnz     short loc_18002314D
0x18002311b  mov     rcx, cs:WPP_GLOBAL_Control
0x180023122  cmp     rcx, rsi
0x180023125  jz      loc_18002320C
0x18002312b  test    [rcx+134h], bl
0x180023131  jz      loc_18002320C
0x180023137  cmp     [rcx+131h], bl
0x18002313d  jb      loc_18002320C
0x180023143  mov     edx, 131h
0x180023148  jmp     loc_1800231FD
0x18002314d  test    eax, eax
0x18002314f  jns     short loc_180023193
0x180023151  mov     rcx, cs:WPP_GLOBAL_Control
0x180023158  cmp     rcx, rsi
0x18002315b  jz      loc_18002320C
0x180023161  test    [rcx+134h], bl
0x180023167  jz      loc_18002320C
0x18002316d  cmp     byte ptr [rcx+131h], 3
0x180023174  jb      loc_18002320C
0x18002317a  mov     rcx, [rcx+128h]
0x180023181  mov     edx, 132h
0x180023186  mov     r9d, eax
0x180023189  mov     r8, r14
0x18002318c  call    WPP_SF_d
0x180023191  jmp     short loc_18002320C
0x180023193  mov     rax, [rbp+var_10]
0x180023197  movzx   r12d, byte ptr [rax+8]
0x18002319c  movzx   eax, byte ptr [rax+9]
0x1800231a0  shl     r12d, 8
0x1800231a4  or      r12d, eax
0x1800231a7  jz      short loc_1800231DB
0x1800231a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800231b0  cmp     rcx, rsi
0x1800231b3  jz      loc_18002306D
0x1800231b9  test    [rcx+134h], bl
0x1800231bf  jz      loc_18002306D
0x1800231c5  cmp     [rcx+131h], bl
0x1800231cb  jb      loc_18002306D
0x1800231d1  mov     edx, 133h
0x1800231d6  jmp     loc_18002305B
0x1800231db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800231e2  cmp     rcx, rsi
0x1800231e5  jz      short loc_18002320C
0x1800231e7  test    [rcx+134h], bl
0x1800231ed  jz      short loc_18002320C
0x1800231ef  cmp     byte ptr [rcx+131h], 3
0x1800231f6  jb      short loc_18002320C
0x1800231f8  mov     edx, 134h
0x1800231fd  mov     rcx, [rcx+128h]
0x180023204  mov     r8, r14
0x180023207  call    WPP_SF_
0x18002320c  mov     rax, [rbp+arg_0]
0x180023210  lea     rdx, [rbp+arg_10]; struct IDiscRecorder2Ex *
0x180023214  mov     rcx, [rax+0D8h]; this
0x18002321b  call    ?GetCurrentPhysicalMediaType@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@PEAW4_IMAPI_MEDIA_PHYSICAL_TYPE@@@Z; Imapi2Utility::GetCurrentPhysicalMediaType(IDiscRecorder2Ex *,_IMAPI_MEDIA_PHYSICAL_TYPE *)
0x180023220  mov     edi, eax
0x180023222  test    eax, eax
0x180023224  jns     short loc_180023264
0x180023226  mov     rcx, cs:WPP_GLOBAL_Control
0x18002322d  cmp     rcx, rsi
0x180023230  jz      loc_1800232C3
0x180023236  test    [rcx+134h], bl
0x18002323c  jz      loc_1800232C3
0x180023242  cmp     byte ptr [rcx+131h], 3
0x180023249  jb      short loc_1800232C3
0x18002324b  mov     rcx, [rcx+128h]
0x180023252  mov     edx, 135h
0x180023257  mov     r9d, eax
0x18002325a  mov     r8, r14
0x18002325d  call    WPP_SF_d
0x180023262  jmp     short loc_1800232C3
0x180023264  mov     ecx, dword ptr [rbp+arg_10.lpVtbl]
0x180023267  cmp     ecx, 9
0x18002326a  jg      short loc_180023295
0x18002326c  jz      short loc_1800232BC
0x18002326e  sub     ecx, 2
0x180023271  jz      short loc_18002328C
0x180023273  sub     ecx, 1
0x180023276  jz      short loc_18002328C
0x180023278  sub     ecx, 2
0x18002327b  jz      short loc_1800232BC
0x18002327d  sub     ecx, 1
0x180023280  jz      short loc_1800232BC
0x180023282  sub     ecx, 1
0x180023285  jz      short loc_1800232BC
0x180023287  cmp     ecx, 1
0x18002328a  jz      short loc_1800232BC
0x18002328c  mov     dword ptr [r15], 1
0x180023293  jmp     short loc_1800232C3
0x180023295  sub     ecx, 0Ah
0x180023298  jz      short loc_1800232BC
0x18002329a  sub     ecx, 1
0x18002329d  jz      short loc_1800232BC
0x18002329f  sub     ecx, 1
0x1800232a2  jz      short loc_18002328C
0x1800232a4  sub     ecx, 1
0x1800232a7  jz      short loc_1800232BC
0x1800232a9  sub     ecx, 5
0x1800232ac  jz      short loc_1800232B3
0x1800232ae  cmp     ecx, 1
0x1800232b1  jnz     short loc_18002328C
0x1800232b3  mov     dword ptr [r15], 20h ; ' '
0x1800232ba  jmp     short loc_1800232C3
0x1800232bc  mov     dword ptr [r15], 10h
0x1800232c3  mov     rcx, [rbp+pv]; pv
0x1800232c7  call    cs:__imp_CoTaskMemFree
0x1800232cd  mov     rcx, [rbp+var_10]; pv
0x1800232d1  mov     [rbp+pv], 0
0x1800232d9  call    cs:__imp_CoTaskMemFree
0x1800232df  mov     eax, edi
0x1800232e1  mov     [rbp+var_10], 0
0x1800232e9  and     eax, 80FF0000h
0x1800232ee  cmp     eax, 80AA0000h
0x1800232f3  jnz     short loc_180023303
0x1800232f5  lea     rdx, CLSID_MsftDiscFormat2Data; int
0x1800232fc  mov     ecx, edi; dwMessageId
0x1800232fe  call    ?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z; Imapi2Utility::SetErrorDescription(long,_GUID const &)
0x180023303  mov     eax, edi
0x180023305  add     rsp, 40h
0x180023309  pop     r15
0x18002330b  pop     r14
0x18002330d  pop     r12
0x18002330f  pop     rdi
0x180023310  pop     rsi
0x180023311  pop     rbx
0x180023312  pop     rbp
0x180023313  retn
```
