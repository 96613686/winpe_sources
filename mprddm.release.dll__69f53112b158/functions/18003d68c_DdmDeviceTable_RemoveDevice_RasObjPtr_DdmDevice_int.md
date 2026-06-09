# DdmDeviceTable::RemoveDevice(RasObjPtr<DdmDevice> &,int)

- ea: `0x18003d68c`
- end: `0x18003db3f`
- name: `?RemoveDevice@DdmDeviceTable@@QEAAKAEAV?$RasObjPtr@VDdmDevice@@@@H@Z`
- size: `1203`
- prototype: `__int64 __fastcall(DdmDeviceTable *this)`
- caller_count: `3`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18000d668`
- `0x18003db48`
- `0x180047350`

## callees

- `0x180007d00`
- `0x18000b040`
- `0x180031478`
- `0x18003c09c`
- `0x18003c468`
- `0x18003d654`
- `0x18003d68c`
- `0x18003e6c8`
- `0x18003e7c4`
- `0x180075588`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003d8fa`
- `msvcrt!_wcsicmp` at `0x18003d8fa`
- `KERNEL32!LeaveCriticalSection` at `0x18003dacc`
- `KERNEL32!LeaveCriticalSection` at `0x18003dacc`
- `KERNEL32!EnterCriticalSection` at `0x18003d7b3`
- `KERNEL32!EnterCriticalSection` at `0x18003d7b3`

## string_xrefs

- `0x18003d734`: `RemoveDevice: (hport: %ld)`
- `0x18003da68`: `RemoveDevice: device not found (hport: %ld)`

## pseudocode

```c
__int64 __fastcall DdmDeviceTable::RemoveDevice(__int64 **this, _QWORD *a2, int a3)
{
  unsigned int v6; // r12d
  unsigned int v7; // r14d
  __int64 v8; // rax
  __int64 v9; // rdx
  int v10; // r15d
  int v11; // eax
  __int64 *v12; // rcx
  __int64 v13; // rdx
  __int64 *v14; // rax
  unsigned __int64 v15; // r8
  __int64 v16; // r8
  unsigned __int64 v17; // rdx
  __int64 *v18; // rcx
  __int64 *v19; // rax
  __int64 *v20; // rcx
  __int64 *v21; // rax
  int v22; // eax
  __int64 *j; // rbx
  __int64 v24; // rcx
  unsigned int v25; // eax
  signed __int32 v26; // r8d
  __int64 **v27; // rax
  __int64 *v28; // rcx
  __int64 *i; // rax
  __int64 v30; // rax
  __int64 v31; // rdx
  unsigned int v33; // [rsp+30h] [rbp-D0h] BYREF
  int v34; // [rsp+34h] [rbp-CCh]
  __int128 v35; // [rsp+38h] [rbp-C8h] BYREF
  int v36; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v37; // [rsp+4Ch] [rbp-B4h]
  __int128 v38; // [rsp+5Ch] [rbp-A4h]
  int v39; // [rsp+6Ch] [rbp-94h]
  int v40; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v41[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v34 = 0;
  v40 = 0;
  v6 = 0;
  memset_0(v41, 0, sizeof(v41));
  v36 = 0;
  v7 = -1;
  v37 = 0;
  v39 = 0;
  v38 = 0;
  v35 = 0;
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    v8 = *a2;
    LOWORD(v40) = 0;
    LOWORD(v36) = 0;
    v9 = v8 ? *(unsigned int *)(v8 + 96) : 0xFFFFFFFFLL;
    ConvertPortNoToString(&v36, v9);
    FormatRRASErrorString(&v40, L"RemoveDevice: (hport: %ld)", *(_QWORD *)(*a2 + 96LL));
    if ( (byte_1800CF404 & 0x10) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v40,
        (unsigned int)&v35,
        0,
        (__int64)&v36);
  }
  v33 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 296LL))(*a2);
  v10 = 1;
  DdmDeviceTable::AcquireExclusive((DdmDeviceTable *)this);
  if ( a3 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(*a2 + 16LL));
    v11 = *(_DWORD *)(*a2 + 132LL);
    if ( (v11 & 8) != 0 )
    {
      *(_DWORD *)(*a2 + 132LL) = v11 | 0x400;
      v10 = 0;
LABEL_72:
      LeaveCriticalSection((LPCRITICAL_SECTION)(*a2 + 16LL));
      goto LABEL_73;
    }
  }
  v12 = this[2];
  v13 = *a2;
  v14 = (__int64 *)v12[1];
  if ( *((_BYTE *)v14 + 41) )
    goto LABEL_65;
  v15 = *(_QWORD *)(v13 + 96);
  do
  {
    if ( v14[3] >= v15 )
    {
      v12 = v14;
      v14 = (__int64 *)*v14;
    }
    else
    {
      v14 = (__int64 *)v14[2];
    }
  }
  while ( !*((_BYTE *)v14 + 41) );
  if ( v12 == this[2] || v15 < v12[3] )
  {
LABEL_65:
    if ( (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v40) = 0;
      LOWORD(v36) = 0;
      if ( v13 )
        v7 = *(_DWORD *)(v13 + 96);
      ConvertPortNoToString(&v36, v7);
      FormatRRASErrorString(&v40, L"RemoveDevice: device not found (hport: %ld)", *(_QWORD *)(*a2 + 96LL));
      if ( (byte_1800CF404 & 8) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceError,
          (unsigned int)&v40,
          (unsigned int)&v35,
          0,
          (__int64)&v36);
    }
    v6 = 1168;
  }
  else
  {
    std::_Tree<std::_Tmap_traits<void *,RasObjPtr<DdmConnection>,std::less<void *>,std::allocator<std::pair<void * const,RasObjPtr<DdmConnection>>>,0>>::erase(
      this + 1,
      v13 + 96,
      v15,
      0);
    v16 = *a2;
    v17 = *(_QWORD *)(*a2 + 120LL);
    if ( v17 )
    {
      v18 = this[6];
      v19 = (__int64 *)v18[1];
      if ( !*((_BYTE *)v19 + 41) )
      {
        do
        {
          if ( v19[3] >= v17 )
          {
            v18 = v19;
            v19 = (__int64 *)*v19;
          }
          else
          {
            v19 = (__int64 *)v19[2];
          }
        }
        while ( !*((_BYTE *)v19 + 41) );
        if ( v18 != this[6] && v17 >= v18[3] )
          std::_Tree<std::_Tmap_traits<void *,RasObjPtr<DdmConnection>,std::less<void *>,std::allocator<std::pair<void * const,RasObjPtr<DdmConnection>>>,0>>::erase(
            this + 5,
            v16 + 120,
            v16,
            0);
      }
    }
    if ( v33 )
    {
      v20 = this[10];
      v21 = (__int64 *)v20[1];
      if ( *((_BYTE *)v21 + 41) )
        goto LABEL_79;
      do
      {
        if ( *((_DWORD *)v21 + 6) >= v33 )
        {
          v20 = v21;
          v21 = (__int64 *)*v21;
        }
        else
        {
          v21 = (__int64 *)v21[2];
        }
      }
      while ( !*((_BYTE *)v21 + 41) );
      if ( v20 == this[10] || v33 < *((_DWORD *)v20 + 6) )
      {
LABEL_79:
        if ( a3 )
        {
          v22 = *(_DWORD *)(*a2 + 132LL);
          if ( (v22 & 0x400000) != 0 )
            *(_DWORD *)(*a2 + 132LL) = v22 | 0x800000;
        }
      }
      else
      {
        std::_Tree<std::_Tmap_traits<unsigned long,RasObjPtr<DdmDevice>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,RasObjPtr<DdmDevice>>>,0>>::erase(
          this + 9,
          &v33,
          v16,
          0);
      }
    }
    if ( _wcsicmp((const wchar_t *)(*a2 + 782LL), L"PPPoE") && !dword_1800CF654 )
      --g_totalPortCount;
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 208LL))(*a2);
    if ( (*(_BYTE *)(*a2 + 132LL) & 0x40) != 0 )
      MediaObjRemoveFromTable((wchar_t *)(*a2 + 782LL));
    j = (__int64 *)*this[2];
    while ( j != this[2] )
    {
      v24 = j[4];
      if ( v24 )
        _InterlockedAdd((volatile signed __int32 *)(v24 + 8), 1u);
      v25 = *(_DWORD *)(v24 + 136) & 0xFFFF0000;
      v26 = _InterlockedDecrement((volatile signed __int32 *)(v24 + 8));
      if ( v25 != 0x20000 )
      {
        v34 = 1;
        if ( !v26 )
          (**(void (__fastcall ***)(__int64, __int64))v24)(v24, 1);
        break;
      }
      if ( !v26 )
        (**(void (__fastcall ***)(__int64, __int64))v24)(v24, 1);
      if ( !*((_BYTE *)j + 41) )
      {
        v27 = (__int64 **)j[2];
        if ( *((_BYTE *)v27 + 41) )
        {
          for ( i = (__int64 *)j[1]; !*((_BYTE *)i + 41) && j == (__int64 *)i[2]; i = (__int64 *)i[1] )
            j = i;
          j = i;
        }
        else
        {
          v28 = *v27;
          for ( j = (__int64 *)j[2]; !*((_BYTE *)v28 + 41); v28 = (__int64 *)*v28 )
            j = v28;
        }
      }
    }
    if ( *(_DWORD *)this )
    {
      v33 = *(_DWORD *)(*a2 + 96LL) % *(_DWORD *)this;
      v30 = std::map<unsigned long,std::set<void *>>::operator[](this + 16, &v33);
      std::_Tree<std::_Tset_traits<void *,std::less<void *>,std::allocator<void *>,0>>::erase(v30, *a2 + 96LL);
    }
  }
  if ( a3 )
    goto LABEL_72;
LABEL_73:
  DdmDeviceTable::ReleaseExclusive((DdmDeviceTable *)this);
  if ( v10 && !v6 )
  {
    ((void (*)(void))qword_1800CF570)();
    LOBYTE(v31) = v34 != 0;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)g_pIDimInterfaceTable + 32LL))(g_pIDimInterfaceTable, v31);
  }
  return v6;
}

```

## disassembly

```asm
0x18003d68c  mov     [rsp-8+arg_10], rbx
0x18003d691  push    rbp
0x18003d692  push    rsi
0x18003d693  push    rdi
0x18003d694  push    r12
0x18003d696  push    r13
0x18003d698  push    r14
0x18003d69a  push    r15
0x18003d69c  lea     rbp, [rsp-780h]
0x18003d6a4  sub     rsp, 880h
0x18003d6ab  mov     rax, cs:__security_cookie
0x18003d6b2  xor     rax, rsp
0x18003d6b5  mov     [rbp+7B0h+var_40], rax
0x18003d6bc  xor     ebx, ebx
0x18003d6be  mov     r13d, r8d
0x18003d6c1  mov     rsi, rdx
0x18003d6c4  mov     [rsp+8B0h+var_87C], ebx
0x18003d6c8  mov     rdi, rcx
0x18003d6cb  mov     [rsp+8B0h+var_840], ebx
0x18003d6cf  xor     edx, edx; Val
0x18003d6d1  lea     rcx, [rsp+8B0h+var_83C]; void *
0x18003d6d6  mov     r8d, 7FCh; Size
0x18003d6dc  mov     r12d, ebx
0x18003d6df  call    memset_0
0x18003d6e4  xorps   xmm0, xmm0
0x18003d6e7  mov     [rsp+8B0h+var_868], ebx
0x18003d6eb  xor     eax, eax
0x18003d6ed  or      r14d, 0FFFFFFFFh
0x18003d6f1  test    cs:byte_1800CF404, 10h
0x18003d6f8  movups  [rsp+8B0h+var_864], xmm0
0x18003d6fd  mov     [rsp+8B0h+var_844], eax
0x18003d701  movups  [rsp+8B0h+var_854], xmm0
0x18003d706  movups  [rsp+8B0h+var_878], xmm0
0x18003d70b  jz      short loc_18003D77E
0x18003d70d  mov     rax, [rsi]
0x18003d710  mov     word ptr [rsp+8B0h+var_840], bx
0x18003d715  mov     word ptr [rsp+8B0h+var_868], bx
0x18003d71a  test    rax, rax
0x18003d71d  jz      short loc_18003D724
0x18003d71f  mov     edx, [rax+60h]
0x18003d722  jmp     short loc_18003D727
0x18003d724  mov     edx, r14d
0x18003d727  lea     rcx, [rsp+8B0h+var_868]
0x18003d72c  call    ConvertPortNoToString
0x18003d731  mov     r8, [rsi]
0x18003d734  lea     rdx, aRemovedeviceHp; "RemoveDevice: (hport: %ld)"
0x18003d73b  lea     rcx, [rsp+8B0h+var_840]
0x18003d740  mov     r8, [r8+60h]
0x18003d744  call    FormatRRASErrorString
0x18003d749  test    cs:byte_1800CF404, 10h
0x18003d750  jz      short loc_18003D77E
0x18003d752  lea     rax, [rsp+8B0h+var_868]
0x18003d757  mov     [rsp+8B0h+var_888], rax
0x18003d75c  lea     r9, [rsp+8B0h+var_878]
0x18003d761  lea     r8, [rsp+8B0h+var_840]
0x18003d766  mov     [rsp+8B0h+var_890], rbx
0x18003d76b  lea     rdx, RasDdmParamTraceInfo
0x18003d772  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003d779  call    McTemplateU0zjzz_EventWriteTransfer
0x18003d77e  mov     rcx, [rsi]
0x18003d781  mov     rax, [rcx]
0x18003d784  mov     rax, [rax+128h]
0x18003d78b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d790  mov     rcx, rdi; this
0x18003d793  mov     [rsp+8B0h+var_880], eax
0x18003d797  mov     ebx, eax
0x18003d799  mov     r15d, 1
0x18003d79f  call    ?AcquireExclusive@DdmDeviceTable@@AEAAXXZ; DdmDeviceTable::AcquireExclusive(void)
0x18003d7a4  xor     r9d, r9d
0x18003d7a7  test    r13d, r13d
0x18003d7aa  jz      short loc_18003D7E4
0x18003d7ac  mov     rcx, [rsi]
0x18003d7af  add     rcx, 10h; lpCriticalSection
0x18003d7b3  call    cs:__imp_EnterCriticalSection
0x18003d7ba  nop     dword ptr [rax+rax+00h]
0x18003d7bf  mov     rcx, [rsi]
0x18003d7c2  mov     eax, [rcx+84h]
0x18003d7c8  test    al, 8
0x18003d7ca  jz      short loc_18003D7E1
0x18003d7cc  bts     eax, 0Ah
0x18003d7d0  xor     r14d, r14d
0x18003d7d3  mov     [rcx+84h], eax
0x18003d7d9  mov     r15d, r14d
0x18003d7dc  jmp     loc_18003DAC5
0x18003d7e1  xor     r9d, r9d
0x18003d7e4  mov     rcx, [rdi+10h]
0x18003d7e8  mov     rdx, [rsi]
0x18003d7eb  mov     rax, [rcx+8]
0x18003d7ef  cmp     [rax+29h], r9b
0x18003d7f3  jnz     loc_18003DA3A
0x18003d7f9  mov     r8, [rdx+60h]
0x18003d7fd  cmp     [rax+18h], r8
0x18003d801  jnb     short loc_18003D809
0x18003d803  mov     rax, [rax+10h]
0x18003d807  jmp     short loc_18003D80F
0x18003d809  mov     rcx, rax
0x18003d80c  mov     rax, [rax]
0x18003d80f  cmp     [rax+29h], r9b
0x18003d813  jz      short loc_18003D7FD
0x18003d815  cmp     rcx, [rdi+10h]
0x18003d819  jz      loc_18003DA3A
0x18003d81f  cmp     r8, [rcx+18h]
0x18003d823  jb      loc_18003DA3A
0x18003d829  add     rdx, 60h ; '`'
0x18003d82d  lea     rcx, [rdi+8]
0x18003d831  call    ?erase@?$_Tree@V?$_Tmap_traits@PEAXV?$RasObjPtr@VDdmConnection@@@@U?$less@PEAX@std@@V?$allocator@U?$pair@QEAXV?$RasObjPtr@VDdmConnection@@@@@std@@@3@$0A@@std@@@std@@QEAA_KAEBQEAX@Z; std::_Tree<std::_Tmap_traits<void *,RasObjPtr<DdmConnection>,std::less<void *>,std::allocator<std::pair<void * const,RasObjPtr<DdmConnection>>>,0>>::erase(void * const &)
0x18003d836  mov     r8, [rsi]
0x18003d839  xor     r9d, r9d
0x18003d83c  mov     rdx, [r8+78h]
0x18003d840  test    rdx, rdx
0x18003d843  jz      short loc_18003D887
0x18003d845  mov     rcx, [rdi+30h]
0x18003d849  mov     rax, [rcx+8]
0x18003d84d  cmp     [rax+29h], r9b
0x18003d851  jnz     short loc_18003D887
0x18003d853  cmp     [rax+18h], rdx
0x18003d857  jnb     short loc_18003D85F
0x18003d859  mov     rax, [rax+10h]
0x18003d85d  jmp     short loc_18003D865
0x18003d85f  mov     rcx, rax
0x18003d862  mov     rax, [rax]
0x18003d865  cmp     [rax+29h], r9b
0x18003d869  jz      short loc_18003D853
0x18003d86b  cmp     rcx, [rdi+30h]
0x18003d86f  jz      short loc_18003D887
0x18003d871  cmp     rdx, [rcx+18h]
0x18003d875  jb      short loc_18003D887
0x18003d877  lea     rdx, [r8+78h]
0x18003d87b  lea     rcx, [rdi+28h]
0x18003d87f  call    ?erase@?$_Tree@V?$_Tmap_traits@PEAXV?$RasObjPtr@VDdmConnection@@@@U?$less@PEAX@std@@V?$allocator@U?$pair@QEAXV?$RasObjPtr@VDdmConnection@@@@@std@@@3@$0A@@std@@@std@@QEAA_KAEBQEAX@Z; std::_Tree<std::_Tmap_traits<void *,RasObjPtr<DdmConnection>,std::less<void *>,std::allocator<std::pair<void * const,RasObjPtr<DdmConnection>>>,0>>::erase(void * const &)
0x18003d884  xor     r9d, r9d
0x18003d887  test    ebx, ebx
0x18003d889  jz      short loc_18003D8E9
0x18003d88b  mov     rcx, [rdi+50h]
0x18003d88f  mov     rax, [rcx+8]
0x18003d893  cmp     [rax+29h], r9b
0x18003d897  jnz     short loc_18003D8CB
0x18003d899  cmp     [rax+18h], ebx
0x18003d89c  jnb     short loc_18003D8A4
0x18003d89e  mov     rax, [rax+10h]
0x18003d8a2  jmp     short loc_18003D8AA
0x18003d8a4  mov     rcx, rax
0x18003d8a7  mov     rax, [rax]
0x18003d8aa  cmp     [rax+29h], r9b
0x18003d8ae  jz      short loc_18003D899
0x18003d8b0  cmp     rcx, [rdi+50h]
0x18003d8b4  jz      short loc_18003D8CB
0x18003d8b6  cmp     ebx, [rcx+18h]
0x18003d8b9  jb      short loc_18003D8CB
0x18003d8bb  lea     rcx, [rdi+48h]
0x18003d8bf  lea     rdx, [rsp+8B0h+var_880]
0x18003d8c4  call    ?erase@?$_Tree@V?$_Tmap_traits@KV?$RasObjPtr@VDdmDevice@@@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$RasObjPtr@VDdmDevice@@@@@std@@@3@$0A@@std@@@std@@QEAA_KAEBK@Z; std::_Tree<std::_Tmap_traits<ulong,RasObjPtr<DdmDevice>,std::less<ulong>,std::allocator<std::pair<ulong const,RasObjPtr<DdmDevice>>>,0>>::erase(ulong const &)
0x18003d8c9  jmp     short loc_18003D8E9
0x18003d8cb  test    r13d, r13d
0x18003d8ce  jz      short loc_18003D8E9
0x18003d8d0  mov     rcx, [rsi]
0x18003d8d3  mov     eax, [rcx+84h]
0x18003d8d9  bt      eax, 16h
0x18003d8dd  jnb     short loc_18003D8E9
0x18003d8df  bts     eax, 17h
0x18003d8e3  mov     [rcx+84h], eax
0x18003d8e9  mov     rcx, [rsi]
0x18003d8ec  lea     rdx, aPppoe; "PPPoE"
0x18003d8f3  add     rcx, 30Eh; String1
0x18003d8fa  call    cs:__imp__wcsicmp
0x18003d901  nop     dword ptr [rax+rax+00h]
0x18003d906  test    eax, eax
0x18003d908  jz      short loc_18003D91A
0x18003d90a  cmp     cs:dword_1800CF654, r12d
0x18003d911  jnz     short loc_18003D91A
0x18003d913  add     cs:g_totalPortCount, r14d
0x18003d91a  mov     rcx, [rsi]
0x18003d91d  mov     rax, [rcx]
0x18003d920  mov     rax, [rax+0D0h]
0x18003d927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d92c  mov     rcx, [rsi]
0x18003d92f  test    byte ptr [rcx+84h], 40h
0x18003d936  jz      short loc_18003D944
0x18003d938  add     rcx, 30Eh; String2
0x18003d93f  call    ?MediaObjRemoveFromTable@@YAXPEAG@Z; MediaObjRemoveFromTable(ushort *)
0x18003d944  mov     rbx, [rdi+10h]
0x18003d948  xor     r14d, r14d
0x18003d94b  mov     rbx, [rbx]
0x18003d94e  cmp     rbx, [rdi+10h]
0x18003d952  jz      loc_18003D9FE
0x18003d958  mov     rcx, [rbx+20h]
0x18003d95c  test    rcx, rcx
0x18003d95f  jz      short loc_18003D966
0x18003d961  lock add [rcx+8], r15d
0x18003d966  mov     eax, [rcx+88h]
0x18003d96c  and     eax, 0FFFF0000h
0x18003d971  or      r8d, 0FFFFFFFFh
0x18003d975  lock xadd [rcx+8], r8d
0x18003d97b  dec     r8d
0x18003d97e  cmp     eax, 20000h
0x18003d983  jnz     short loc_18003D9E6
0x18003d985  test    r8d, r8d
0x18003d988  jnz     short loc_18003D998
0x18003d98a  mov     rax, [rcx]
0x18003d98d  mov     edx, r15d
0x18003d990  mov     rax, [rax]
0x18003d993  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d998  cmp     [rbx+29h], r14b
0x18003d99c  jnz     short loc_18003D94E
0x18003d99e  mov     rax, [rbx+10h]
0x18003d9a2  cmp     [rax+29h], r14b
0x18003d9a6  jnz     short loc_18003D9C5
0x18003d9a8  mov     rcx, [rax]
0x18003d9ab  mov     rbx, rax
0x18003d9ae  cmp     [rcx+29h], r14b
0x18003d9b2  jnz     short loc_18003D94E
0x18003d9b4  mov     rax, [rcx]
0x18003d9b7  mov     rbx, rcx
0x18003d9ba  mov     rcx, rax
0x18003d9bd  cmp     [rax+29h], r14b
0x18003d9c1  jz      short loc_18003D9B4
0x18003d9c3  jmp     short loc_18003D94E
0x18003d9c5  mov     rax, [rbx+8]
0x18003d9c9  jmp     short loc_18003D9D8
0x18003d9cb  cmp     rbx, [rax+10h]
0x18003d9cf  jnz     short loc_18003D9DE
0x18003d9d1  mov     rbx, rax
0x18003d9d4  mov     rax, [rax+8]
0x18003d9d8  cmp     [rax+29h], r14b
0x18003d9dc  jz      short loc_18003D9CB
0x18003d9de  mov     rbx, rax
0x18003d9e1  jmp     loc_18003D94E
0x18003d9e6  mov     [rsp+8B0h+var_87C], r15d
0x18003d9eb  test    r8d, r8d
0x18003d9ee  jnz     short loc_18003D9FE
0x18003d9f0  mov     rax, [rcx]
0x18003d9f3  mov     edx, r15d
0x18003d9f6  mov     rax, [rax]
0x18003d9f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d9fe  cmp     [rdi], r14d
0x18003da01  jbe     loc_18003DAC0
0x18003da07  mov     rax, [rsi]
0x18003da0a  lea     rcx, [rdi+80h]
0x18003da11  xor     edx, edx
0x18003da13  mov     eax, [rax+60h]
0x18003da16  div     dword ptr [rdi]
0x18003da18  mov     [rsp+8B0h+var_880], edx
0x18003da1c  lea     rdx, [rsp+8B0h+var_880]
0x18003da21  call    ??A?$map@KV?$set@PEAXU?$less@PEAX@std@@V?$allocator@PEAX@2@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$set@PEAXU?$less@PEAX@std@@V?$allocator@PEAX@2@@std@@@std@@@2@@std@@QEAAAEAV?$set@PEAXU?$less@PEAX@std@@V?$allocator@PEAX@2@@1@$$QEAK@Z; std::map<ulong,std::set<void *>>::operator[](ulong &&)
0x18003da26  mov     rdx, [rsi]
0x18003da29  mov     rcx, rax
0x18003da2c  add     rdx, 60h ; '`'
0x18003da30  call    ?erase@?$_Tree@V?$_Tset_traits@PEAXU?$less@PEAX@std@@V?$allocator@PEAX@2@$0A@@std@@@std@@QEAA_KAEBQEAX@Z; std::_Tree<std::_Tset_traits<void *,std::less<void *>,std::allocator<void *>,0>>::erase(void * const &)
0x18003da35  jmp     loc_18003DAC0
0x18003da3a  test    cs:byte_1800CF404, 8
0x18003da41  jz      short loc_18003DAB7
0x18003da43  mov     word ptr [rsp+8B0h+var_840], r9w
0x18003da49  mov     word ptr [rsp+8B0h+var_868], r9w
0x18003da4f  test    rdx, rdx
0x18003da52  jz      short loc_18003DA58
0x18003da54  mov     r14d, [rdx+60h]
0x18003da58  mov     edx, r14d
0x18003da5b  lea     rcx, [rsp+8B0h+var_868]
0x18003da60  call    ConvertPortNoToString
0x18003da65  mov     r8, [rsi]
0x18003da68  lea     rdx, aRemovedeviceDe; "RemoveDevice: device not found (hport: "...
0x18003da6f  lea     rcx, [rsp+8B0h+var_840]
0x18003da74  mov     r8, [r8+60h]
0x18003da78  call    FormatRRASErrorString
0x18003da7d  xor     r14d, r14d
0x18003da80  test    cs:byte_1800CF404, 8
0x18003da87  jz      short loc_18003DABA
0x18003da89  lea     rax, [rsp+8B0h+var_868]
0x18003da8e  mov     [rsp+8B0h+var_888], rax
0x18003da93  lea     r9, [rsp+8B0h+var_878]
0x18003da98  lea     r8, [rsp+8B0h+var_840]
0x18003da9d  mov     [rsp+8B0h+var_890], r14
0x18003daa2  lea     rdx, RasDdmParamTraceError
0x18003daa9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003dab0  call    McTemplateU0zjzz_EventWriteTransfer
0x18003dab5  jmp     short loc_18003DABA
0x18003dab7  xor     r14d, r14d
0x18003daba  mov     r12d, 490h
0x18003dac0  test    r13d, r13d
0x18003dac3  jz      short loc_18003DAD8
0x18003dac5  mov     rcx, [rsi]
0x18003dac8  add     rcx, 10h; lpCriticalSection
0x18003dacc  call    cs:__imp_LeaveCriticalSection
0x18003dad3  nop     dword ptr [rax+rax+00h]
0x18003dad8  mov     rcx, rdi; this
0x18003dadb  call    ?ReleaseExclusive@DdmDeviceTable@@AEAAXXZ; DdmDeviceTable::ReleaseExclusive(void)
0x18003dae0  test    r15d, r15d
0x18003dae3  jz      short loc_18003DB11
0x18003dae5  test    r12d, r12d
0x18003dae8  jnz     short loc_18003DB11
0x18003daea  mov     rax, cs:qword_1800CF570
0x18003daf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003daf6  mov     rcx, cs:g_pIDimInterfaceTable
0x18003dafd  cmp     [rsp+8B0h+var_87C], r14d
0x18003db02  setnz   dl
0x18003db05  mov     r8, [rcx]
0x18003db08  mov     rax, [r8+20h]
0x18003db0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003db11  mov     eax, r12d
0x18003db14  mov     rcx, [rbp+7B0h+var_40]
  ... truncated ...
```
