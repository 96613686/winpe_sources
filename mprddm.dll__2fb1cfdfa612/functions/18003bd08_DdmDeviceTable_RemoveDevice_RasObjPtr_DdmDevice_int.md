# DdmDeviceTable::RemoveDevice(RasObjPtr<DdmDevice> &,int)

- ea: `0x18003bd08`
- end: `0x18003c1a1`
- name: `?RemoveDevice@DdmDeviceTable@@QEAAKAEAV?$RasObjPtr@VDdmDevice@@@@H@Z`
- size: `1177`
- prototype: `__int64 __fastcall(DdmDeviceTable *this)`
- caller_count: `3`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18000d258`
- `0x18003c1a8`
- `0x180046270`

## callees

- `0x180007c50`
- `0x18000adb4`
- `0x18002f03c`
- `0x18003a848`
- `0x18003ab50`
- `0x18003bcd0`
- `0x18003bd08`
- `0x18003cd94`
- `0x18003ce8c`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x18003bda5`
- `msvcrt!_itow_s` at `0x18003c0d2`
- `msvcrt!_itow_s` at `0x18003bda5`
- `msvcrt!_itow_s` at `0x18003c0d2`
- `msvcrt!_wcsicmp` at `0x18003bf72`
- `msvcrt!_wcsicmp` at `0x18003bf72`
- `KERNEL32!LeaveCriticalSection` at `0x18003c137`
- `KERNEL32!LeaveCriticalSection` at `0x18003c137`
- `KERNEL32!EnterCriticalSection` at `0x18003be2e`
- `KERNEL32!EnterCriticalSection` at `0x18003be2e`

## string_xrefs

- `0x18003bdae`: `RemoveDevice: (hport: %ld)`
- `0x18003c0db`: `RemoveDevice: device not found (hport: %ld)`

## pseudocode

```c
__int64 __fastcall DdmDeviceTable::RemoveDevice(__int64 **this, _QWORD *a2, int a3)
{
  __int64 v6; // rcx
  int v7; // ecx
  unsigned int v8; // r15d
  int v9; // r13d
  int v10; // ecx
  int v11; // r14d
  __int64 *v12; // rdx
  __int64 v13; // r9
  __int64 *v14; // rax
  int *v15; // rcx
  unsigned __int64 v16; // r11
  __int64 *v17; // r8
  unsigned __int64 v18; // r8
  __int64 *v19; // rdx
  __int64 *v20; // rcx
  __int64 *v21; // rax
  __int64 *v22; // rdx
  __int64 *v23; // rcx
  __int64 *v24; // rax
  int v25; // eax
  __int64 v26; // r8
  __int64 *v27; // rbx
  __int64 v28; // rcx
  unsigned int v29; // eax
  signed __int32 v30; // edx
  __int64 *i; // rax
  __int64 *v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rdx
  unsigned int v36; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v37; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Buffer[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v39; // [rsp+4Ch] [rbp-B4h]
  __int128 v40; // [rsp+5Ch] [rbp-A4h]
  int v41; // [rsp+6Ch] [rbp-94h]
  int v42; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v43[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v42 = 0;
  memset_0(v43, 0, sizeof(v43));
  *(_DWORD *)Buffer = 0;
  v39 = 0;
  v41 = 0;
  v40 = 0;
  v37 = 0;
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    v6 = *a2;
    LOWORD(v42) = 0;
    Buffer[0] = 0;
    if ( v6 )
    {
      v7 = *(_DWORD *)(v6 + 96);
      if ( v7 != -1 )
        _itow_s(v7, Buffer, 0x14u, 10);
    }
    FormatRRASErrorString(&v42, L"RemoveDevice: (hport: %ld)", *(_QWORD *)(*a2 + 96LL));
    if ( (byte_1800C8404 & 0x10) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v42,
        (unsigned int)&v37,
        0,
        (__int64)Buffer);
  }
  v8 = 0;
  v9 = 0;
  v36 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 296LL))(*a2);
  DdmDeviceTable::AcquireExclusive((DdmDeviceTable *)this);
  if ( a3 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(*a2 + 16LL));
    v10 = *(_DWORD *)(*a2 + 132LL);
    if ( (v10 & 8) != 0 )
    {
      *(_DWORD *)(*a2 + 132LL) = v10 | 0x400;
      v11 = 0;
LABEL_73:
      LeaveCriticalSection((LPCRITICAL_SECTION)(*a2 + 16LL));
      goto LABEL_74;
    }
  }
  v12 = this[2];
  v11 = 1;
  v13 = *a2;
  v14 = (__int64 *)v12[1];
  v15 = (int *)(*a2 + 96LL);
  if ( !*((_BYTE *)v14 + 41) )
  {
    v16 = *(_QWORD *)v15;
    v17 = this[2];
    do
    {
      if ( v14[3] >= v16 )
      {
        v17 = v14;
        v14 = (__int64 *)*v14;
      }
      else
      {
        v14 = (__int64 *)v14[2];
      }
    }
    while ( !*((_BYTE *)v14 + 41) );
    if ( v17 != v12 && v16 >= v17[3] )
    {
      std::_Tree<std::_Tmap_traits<void *,RasObjPtr<DdmConnection>,std::less<void *>,std::allocator<std::pair<void * const,RasObjPtr<DdmConnection>>>,0>>::erase(
        this + 1,
        *a2 + 96LL);
      v18 = *(_QWORD *)(*a2 + 120LL);
      if ( v18 )
      {
        v19 = this[6];
        v20 = v19;
        v21 = (__int64 *)v19[1];
        if ( !*((_BYTE *)v21 + 41) )
        {
          do
          {
            if ( v21[3] >= v18 )
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
          if ( v20 != v19 && v18 >= v20[3] )
            std::_Tree<std::_Tmap_traits<void *,RasObjPtr<DdmConnection>,std::less<void *>,std::allocator<std::pair<void * const,RasObjPtr<DdmConnection>>>,0>>::erase(
              this + 5,
              *a2 + 120LL);
        }
      }
      if ( v36 )
      {
        v22 = this[10];
        v23 = v22;
        v24 = (__int64 *)v22[1];
        if ( *((_BYTE *)v24 + 41) )
          goto LABEL_80;
        do
        {
          if ( *((_DWORD *)v24 + 6) >= v36 )
          {
            v23 = v24;
            v24 = (__int64 *)*v24;
          }
          else
          {
            v24 = (__int64 *)v24[2];
          }
        }
        while ( !*((_BYTE *)v24 + 41) );
        if ( v23 == v22 || v36 < *((_DWORD *)v23 + 6) )
        {
LABEL_80:
          if ( a3 )
          {
            v25 = *(_DWORD *)(*a2 + 132LL);
            if ( (v25 & 0x400000) != 0 )
              *(_DWORD *)(*a2 + 132LL) = v25 | 0x800000;
          }
        }
        else
        {
          std::_Tree<std::_Tmap_traits<unsigned long,RasObjPtr<DdmDevice>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,RasObjPtr<DdmDevice>>>,0>>::erase(
            this + 9,
            &v36);
        }
      }
      if ( _wcsicmp((const wchar_t *)(*a2 + 782LL), L"PPPoE") && !dword_1800C8654 )
        --g_totalPortCount;
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 208LL))(*a2);
      if ( (*(_BYTE *)(*a2 + 132LL) & 0x40) != 0 )
        MediaObjRemoveFromTable((wchar_t *)(*a2 + 782LL));
      v26 = 0;
      v27 = (__int64 *)*this[2];
      while ( 1 )
      {
        while ( 1 )
        {
          do
          {
            if ( v27 == this[2] )
            {
LABEL_63:
              if ( *(_DWORD *)this )
              {
                v36 = *(_DWORD *)(*a2 + 96LL) % *(_DWORD *)this;
                v33 = std::map<unsigned long,std::set<void *>>::operator[](this + 16, &v36, v26);
                std::_Tree<std::_Tset_traits<void *,std::less<void *>,std::allocator<void *>,0>>::erase(v33, *a2 + 96LL);
              }
              goto LABEL_72;
            }
            v28 = v27[4];
            if ( v28 )
              _InterlockedAdd((volatile signed __int32 *)(v28 + 8), 1u);
            v29 = *(_DWORD *)(v28 + 136) & 0xFFFF0000;
            v30 = _InterlockedDecrement((volatile signed __int32 *)(v28 + 8));
            if ( v29 != 0x20000 )
            {
              v9 = 1;
              if ( !v30 )
                (**(void (__fastcall ***)(__int64, __int64, _QWORD))v28)(v28, 1, 0);
              goto LABEL_63;
            }
            if ( !v30 )
            {
              (**(void (__fastcall ***)(__int64, __int64, _QWORD))v28)(v28, 1, 0);
              v26 = 0;
            }
          }
          while ( *((_BYTE *)v27 + 41) );
          i = (__int64 *)v27[2];
          if ( !*((_BYTE *)i + 41) )
            break;
          for ( i = (__int64 *)v27[1]; !*((_BYTE *)i + 41) && v27 == (__int64 *)i[2]; i = (__int64 *)i[1] )
            v27 = i;
LABEL_60:
          v27 = i;
        }
        v32 = (__int64 *)*i;
        if ( *(_BYTE *)(*i + 41) )
          goto LABEL_60;
        do
        {
          v27 = v32;
          v32 = (__int64 *)*v32;
        }
        while ( !*((_BYTE *)v32 + 41) );
      }
    }
  }
  if ( (byte_1800C8404 & 8) != 0 )
  {
    LOWORD(v42) = 0;
    Buffer[0] = 0;
    if ( v13 && *v15 != -1 )
      _itow_s(*v15, Buffer, 0x14u, 10);
    FormatRRASErrorString(&v42, L"RemoveDevice: device not found (hport: %ld)", *(_QWORD *)(*a2 + 96LL));
    if ( (byte_1800C8404 & 8) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (unsigned int)&v42,
        (unsigned int)&v37,
        0,
        (__int64)Buffer);
  }
  v8 = 1168;
LABEL_72:
  if ( a3 )
    goto LABEL_73;
LABEL_74:
  DdmDeviceTable::ReleaseExclusive((DdmDeviceTable *)this);
  if ( v11 && !v8 )
  {
    ((void (*)(void))qword_1800C8570)();
    LOBYTE(v34) = v9 != 0;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)g_pIDimInterfaceTable + 32LL))(g_pIDimInterfaceTable, v34);
  }
  return v8;
}

```

## disassembly

```asm
0x18003bd08  mov     [rsp-8+arg_10], rbx
0x18003bd0d  push    rbp
0x18003bd0e  push    rsi
0x18003bd0f  push    rdi
0x18003bd10  push    r12
0x18003bd12  push    r13
0x18003bd14  push    r14
0x18003bd16  push    r15
0x18003bd18  lea     rbp, [rsp-780h]
0x18003bd20  sub     rsp, 880h
0x18003bd27  mov     rax, cs:__security_cookie
0x18003bd2e  xor     rax, rsp
0x18003bd31  mov     [rbp+7B0h+var_40], rax
0x18003bd38  mov     r12d, r8d
0x18003bd3b  mov     rdi, rdx
0x18003bd3e  mov     rsi, rcx
0x18003bd41  xor     eax, eax
0x18003bd43  xor     edx, edx; Val
0x18003bd45  mov     [rsp+8B0h+var_840], eax
0x18003bd49  mov     r8d, 7FCh; Size
0x18003bd4f  lea     rcx, [rsp+8B0h+var_83C]; void *
0x18003bd54  call    memset_0
0x18003bd59  xor     eax, eax
0x18003bd5b  xorps   xmm0, xmm0
0x18003bd5e  test    cs:byte_1800C8404, 10h
0x18003bd65  mov     dword ptr [rsp+8B0h+Buffer], eax
0x18003bd69  movups  [rsp+8B0h+var_864], xmm0
0x18003bd6e  mov     [rsp+8B0h+var_844], eax
0x18003bd72  movups  [rsp+8B0h+var_854], xmm0
0x18003bd77  movups  [rsp+8B0h+var_878], xmm0
0x18003bd7c  jz      short loc_18003BDFC
0x18003bd7e  mov     rcx, [rdi]
0x18003bd81  mov     word ptr [rsp+8B0h+var_840], ax
0x18003bd86  mov     [rsp+8B0h+Buffer], ax
0x18003bd8b  test    rcx, rcx
0x18003bd8e  jz      short loc_18003BDAB
0x18003bd90  mov     ecx, [rcx+60h]; Value
0x18003bd93  cmp     ecx, 0FFFFFFFFh
0x18003bd96  jz      short loc_18003BDAB
0x18003bd98  lea     r9d, [rax+0Ah]; Radix
0x18003bd9c  lea     r8d, [rax+14h]; BufferCount
0x18003bda0  lea     rdx, [rsp+8B0h+Buffer]; Buffer
0x18003bda5  call    cs:__imp__itow_s
0x18003bdab  mov     r8, [rdi]
0x18003bdae  lea     rdx, aRemovedeviceHp; "RemoveDevice: (hport: %ld)"
0x18003bdb5  lea     rcx, [rsp+8B0h+var_840]
0x18003bdba  mov     r8, [r8+60h]
0x18003bdbe  call    FormatRRASErrorString
0x18003bdc3  test    cs:byte_1800C8404, 10h
0x18003bdca  jz      short loc_18003BDFC
0x18003bdcc  lea     rax, [rsp+8B0h+Buffer]
0x18003bdd1  mov     [rsp+8B0h+var_888], rax
0x18003bdd6  lea     r9, [rsp+8B0h+var_878]
0x18003bddb  lea     r8, [rsp+8B0h+var_840]
0x18003bde0  mov     [rsp+8B0h+var_890], 0
0x18003bde9  lea     rdx, RasDdmParamTraceInfo
0x18003bdf0  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003bdf7  call    McTemplateU0zjzz_EventWriteTransfer
0x18003bdfc  mov     rcx, [rdi]
0x18003bdff  xor     r15d, r15d
0x18003be02  xor     r13d, r13d
0x18003be05  mov     rax, [rcx]
0x18003be08  mov     rax, [rax+128h]
0x18003be0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be14  mov     rcx, rsi; this
0x18003be17  mov     [rsp+8B0h+var_880], eax
0x18003be1b  mov     ebx, eax
0x18003be1d  call    ?AcquireExclusive@DdmDeviceTable@@AEAAXXZ; DdmDeviceTable::AcquireExclusive(void)
0x18003be22  test    r12d, r12d
0x18003be25  jz      short loc_18003BE54
0x18003be27  mov     rcx, [rdi]
0x18003be2a  add     rcx, 10h; lpCriticalSection
0x18003be2e  call    cs:__imp_EnterCriticalSection
0x18003be34  mov     rdx, [rdi]
0x18003be37  mov     ecx, [rdx+84h]
0x18003be3d  test    cl, 8
0x18003be40  jz      short loc_18003BE54
0x18003be42  bts     ecx, 0Ah
0x18003be46  mov     [rdx+84h], ecx
0x18003be4c  xor     r14d, r14d
0x18003be4f  jmp     loc_18003C130
0x18003be54  mov     rdx, [rsi+10h]
0x18003be58  mov     r14d, 1
0x18003be5e  mov     r9, [rdi]
0x18003be61  mov     rax, [rdx+8]
0x18003be65  lea     rcx, [r9+60h]
0x18003be69  cmp     [rax+29h], r13b
0x18003be6d  jnz     loc_18003C0A4
0x18003be73  mov     r11, [rcx]
0x18003be76  mov     r8, rdx
0x18003be79  cmp     [rax+18h], r11
0x18003be7d  jnb     short loc_18003BE85
0x18003be7f  mov     rax, [rax+10h]
0x18003be83  jmp     short loc_18003BE8B
0x18003be85  mov     r8, rax
0x18003be88  mov     rax, [rax]
0x18003be8b  cmp     [rax+29h], r13b
0x18003be8f  jz      short loc_18003BE79
0x18003be91  cmp     r8, rdx
0x18003be94  jz      loc_18003C0A4
0x18003be9a  cmp     r11, [r8+18h]
0x18003be9e  jb      loc_18003C0A4
0x18003bea4  mov     rdx, rcx
0x18003bea7  lea     rcx, [rsi+8]
0x18003beab  call    ?erase@?$_Tree@V?$_Tmap_traits@PEAXV?$RasObjPtr@VDdmConnection@@@@U?$less@PEAX@std@@V?$allocator@U?$pair@QEAXV?$RasObjPtr@VDdmConnection@@@@@std@@@3@$0A@@std@@@std@@QEAA_KAEBQEAX@Z; std::_Tree<std::_Tmap_traits<void *,RasObjPtr<DdmConnection>,std::less<void *>,std::allocator<std::pair<void * const,RasObjPtr<DdmConnection>>>,0>>::erase(void * const &)
0x18003beb0  mov     r10, [rdi]
0x18003beb3  mov     r8, [r10+78h]
0x18003beb7  test    r8, r8
0x18003beba  jz      short loc_18003BEFD
0x18003bebc  mov     rdx, [rsi+30h]
0x18003bec0  mov     rcx, rdx
0x18003bec3  mov     rax, [rdx+8]
0x18003bec7  cmp     [rax+29h], r13b
0x18003becb  jnz     short loc_18003BEFD
0x18003becd  cmp     [rax+18h], r8
0x18003bed1  jnb     short loc_18003BED9
0x18003bed3  mov     rax, [rax+10h]
0x18003bed7  jmp     short loc_18003BEDF
0x18003bed9  mov     rcx, rax
0x18003bedc  mov     rax, [rax]
0x18003bedf  cmp     [rax+29h], r13b
0x18003bee3  jz      short loc_18003BECD
0x18003bee5  cmp     rcx, rdx
0x18003bee8  jz      short loc_18003BEFD
0x18003beea  cmp     r8, [rcx+18h]
0x18003beee  jb      short loc_18003BEFD
0x18003bef0  lea     rdx, [r10+78h]
0x18003bef4  lea     rcx, [rsi+28h]
0x18003bef8  call    ?erase@?$_Tree@V?$_Tmap_traits@PEAXV?$RasObjPtr@VDdmConnection@@@@U?$less@PEAX@std@@V?$allocator@U?$pair@QEAXV?$RasObjPtr@VDdmConnection@@@@@std@@@3@$0A@@std@@@std@@QEAA_KAEBQEAX@Z; std::_Tree<std::_Tmap_traits<void *,RasObjPtr<DdmConnection>,std::less<void *>,std::allocator<std::pair<void * const,RasObjPtr<DdmConnection>>>,0>>::erase(void * const &)
0x18003befd  test    ebx, ebx
0x18003beff  jz      short loc_18003BF61
0x18003bf01  mov     rdx, [rsi+50h]
0x18003bf05  mov     rcx, rdx
0x18003bf08  mov     rax, [rdx+8]
0x18003bf0c  cmp     [rax+29h], r13b
0x18003bf10  jnz     short loc_18003BF43
0x18003bf12  cmp     [rax+18h], ebx
0x18003bf15  jnb     short loc_18003BF1D
0x18003bf17  mov     rax, [rax+10h]
0x18003bf1b  jmp     short loc_18003BF23
0x18003bf1d  mov     rcx, rax
0x18003bf20  mov     rax, [rax]
0x18003bf23  cmp     [rax+29h], r13b
0x18003bf27  jz      short loc_18003BF12
0x18003bf29  cmp     rcx, rdx
0x18003bf2c  jz      short loc_18003BF43
0x18003bf2e  cmp     ebx, [rcx+18h]
0x18003bf31  jb      short loc_18003BF43
0x18003bf33  lea     rdx, [rsp+8B0h+var_880]
0x18003bf38  lea     rcx, [rsi+48h]
0x18003bf3c  call    ?erase@?$_Tree@V?$_Tmap_traits@KV?$RasObjPtr@VDdmDevice@@@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$RasObjPtr@VDdmDevice@@@@@std@@@3@$0A@@std@@@std@@QEAA_KAEBK@Z; std::_Tree<std::_Tmap_traits<ulong,RasObjPtr<DdmDevice>,std::less<ulong>,std::allocator<std::pair<ulong const,RasObjPtr<DdmDevice>>>,0>>::erase(ulong const &)
0x18003bf41  jmp     short loc_18003BF61
0x18003bf43  test    r12d, r12d
0x18003bf46  jz      short loc_18003BF61
0x18003bf48  mov     rcx, [rdi]
0x18003bf4b  mov     eax, [rcx+84h]
0x18003bf51  bt      eax, 16h
0x18003bf55  jnb     short loc_18003BF61
0x18003bf57  bts     eax, 17h
0x18003bf5b  mov     [rcx+84h], eax
0x18003bf61  mov     rcx, [rdi]
0x18003bf64  lea     rdx, aPppoe; "PPPoE"
0x18003bf6b  add     rcx, 30Eh; String1
0x18003bf72  call    cs:__imp__wcsicmp
0x18003bf78  test    eax, eax
0x18003bf7a  jz      short loc_18003BF8B
0x18003bf7c  cmp     cs:dword_1800C8654, r13d
0x18003bf83  jnz     short loc_18003BF8B
0x18003bf85  dec     cs:g_totalPortCount
0x18003bf8b  mov     rcx, [rdi]
0x18003bf8e  mov     rax, [rcx]
0x18003bf91  mov     rax, [rax+0D0h]
0x18003bf98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bf9d  mov     rcx, [rdi]
0x18003bfa0  test    byte ptr [rcx+84h], 40h
0x18003bfa7  jz      short loc_18003BFB5
0x18003bfa9  add     rcx, 30Eh; String2
0x18003bfb0  call    ?MediaObjRemoveFromTable@@YAXPEAG@Z; MediaObjRemoveFromTable(ushort *)
0x18003bfb5  mov     rbx, [rsi+10h]
0x18003bfb9  xor     r8d, r8d
0x18003bfbc  mov     rbx, [rbx]
0x18003bfbf  cmp     rbx, [rsi+10h]
0x18003bfc3  jz      loc_18003C068
0x18003bfc9  mov     rcx, [rbx+20h]
0x18003bfcd  test    rcx, rcx
0x18003bfd0  jz      short loc_18003BFD7
0x18003bfd2  lock add [rcx+8], r14d
0x18003bfd7  mov     eax, [rcx+88h]
0x18003bfdd  and     eax, 0FFFF0000h
0x18003bfe2  or      edx, 0FFFFFFFFh
0x18003bfe5  lock xadd [rcx+8], edx
0x18003bfea  dec     edx
0x18003bfec  cmp     eax, 20000h
0x18003bff1  jnz     short loc_18003C053
0x18003bff3  test    edx, edx
0x18003bff5  jnz     short loc_18003C008
0x18003bff7  mov     rax, [rcx]
0x18003bffa  mov     edx, r14d
0x18003bffd  mov     rax, [rax]
0x18003c000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c005  xor     r8d, r8d
0x18003c008  cmp     [rbx+29h], r8b
0x18003c00c  jnz     short loc_18003BFBF
0x18003c00e  mov     rax, [rbx+10h]
0x18003c012  cmp     [rax+29h], r8b
0x18003c016  jnz     short loc_18003C032
0x18003c018  mov     rcx, [rax]
0x18003c01b  cmp     [rcx+29h], r8b
0x18003c01f  jnz     short loc_18003C04B
0x18003c021  mov     rax, [rcx]
0x18003c024  mov     rbx, rcx
0x18003c027  mov     rcx, rax
0x18003c02a  cmp     [rax+29h], r8b
0x18003c02e  jz      short loc_18003C021
0x18003c030  jmp     short loc_18003BFBF
0x18003c032  mov     rax, [rbx+8]
0x18003c036  jmp     short loc_18003C045
0x18003c038  cmp     rbx, [rax+10h]
0x18003c03c  jnz     short loc_18003C04B
0x18003c03e  mov     rbx, rax
0x18003c041  mov     rax, [rax+8]
0x18003c045  cmp     [rax+29h], r8b
0x18003c049  jz      short loc_18003C038
0x18003c04b  mov     rbx, rax
0x18003c04e  jmp     loc_18003BFBF
0x18003c053  mov     r13d, r14d
0x18003c056  test    edx, edx
0x18003c058  jnz     short loc_18003C068
0x18003c05a  mov     rax, [rcx]
0x18003c05d  mov     edx, r14d
0x18003c060  mov     rax, [rax]
0x18003c063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c068  cmp     [rsi], r15d
0x18003c06b  jbe     loc_18003C12B
0x18003c071  mov     rax, [rdi]
0x18003c074  lea     rcx, [rsi+80h]
0x18003c07b  xor     edx, edx
0x18003c07d  mov     eax, [rax+60h]
0x18003c080  div     dword ptr [rsi]
0x18003c082  mov     [rsp+8B0h+var_880], edx
0x18003c086  lea     rdx, [rsp+8B0h+var_880]
0x18003c08b  call    ??A?$map@KV?$set@PEAXU?$less@PEAX@std@@V?$allocator@PEAX@2@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$set@PEAXU?$less@PEAX@std@@V?$allocator@PEAX@2@@std@@@std@@@2@@std@@QEAAAEAV?$set@PEAXU?$less@PEAX@std@@V?$allocator@PEAX@2@@1@$$QEAK@Z; std::map<ulong,std::set<void *>>::operator[](ulong &&)
0x18003c090  mov     rdx, [rdi]
0x18003c093  mov     rcx, rax
0x18003c096  add     rdx, 60h ; '`'
0x18003c09a  call    ?erase@?$_Tree@V?$_Tset_traits@PEAXU?$less@PEAX@std@@V?$allocator@PEAX@2@$0A@@std@@@std@@QEAA_KAEBQEAX@Z; std::_Tree<std::_Tset_traits<void *,std::less<void *>,std::allocator<void *>,0>>::erase(void * const &)
0x18003c09f  jmp     loc_18003C12B
0x18003c0a4  test    cs:byte_1800C8404, 8
0x18003c0ab  jz      short loc_18003C125
0x18003c0ad  xor     eax, eax
0x18003c0af  mov     word ptr [rsp+8B0h+var_840], ax
0x18003c0b4  mov     [rsp+8B0h+Buffer], ax
0x18003c0b9  test    r9, r9
0x18003c0bc  jz      short loc_18003C0D8
0x18003c0be  cmp     dword ptr [rcx], 0FFFFFFFFh
0x18003c0c1  jz      short loc_18003C0D8
0x18003c0c3  mov     ecx, [rcx]; Value
0x18003c0c5  lea     r9d, [rax+0Ah]; Radix
0x18003c0c9  lea     r8d, [rax+14h]; BufferCount
0x18003c0cd  lea     rdx, [rsp+8B0h+Buffer]; Buffer
0x18003c0d2  call    cs:__imp__itow_s
0x18003c0d8  mov     r8, [rdi]
0x18003c0db  lea     rdx, aRemovedeviceDe; "RemoveDevice: device not found (hport: "...
0x18003c0e2  lea     rcx, [rsp+8B0h+var_840]
0x18003c0e7  mov     r8, [r8+60h]
0x18003c0eb  call    FormatRRASErrorString
0x18003c0f0  test    cs:byte_1800C8404, 8
0x18003c0f7  jz      short loc_18003C125
0x18003c0f9  lea     rax, [rsp+8B0h+Buffer]
0x18003c0fe  mov     [rsp+8B0h+var_888], rax
0x18003c103  lea     r9, [rsp+8B0h+var_878]
0x18003c108  lea     r8, [rsp+8B0h+var_840]
0x18003c10d  mov     [rsp+8B0h+var_890], r13
0x18003c112  lea     rdx, RasDdmParamTraceError
0x18003c119  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003c120  call    McTemplateU0zjzz_EventWriteTransfer
0x18003c125  mov     r15d, 490h
0x18003c12b  test    r12d, r12d
0x18003c12e  jz      short loc_18003C13D
0x18003c130  mov     rcx, [rdi]
0x18003c133  add     rcx, 10h; lpCriticalSection
0x18003c137  call    cs:__imp_LeaveCriticalSection
0x18003c13d  mov     rcx, rsi; this
0x18003c140  call    ?ReleaseExclusive@DdmDeviceTable@@AEAAXXZ; DdmDeviceTable::ReleaseExclusive(void)
0x18003c145  test    r14d, r14d
0x18003c148  jz      short loc_18003C174
0x18003c14a  test    r15d, r15d
0x18003c14d  jnz     short loc_18003C174
0x18003c14f  mov     rax, cs:qword_1800C8570
0x18003c156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c15b  mov     rcx, cs:g_pIDimInterfaceTable
0x18003c162  test    r13d, r13d
0x18003c165  setnz   dl
0x18003c168  mov     r8, [rcx]
0x18003c16b  mov     rax, [r8+20h]
0x18003c16f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c174  mov     eax, r15d
0x18003c177  mov     rcx, [rbp+7B0h+var_40]
0x18003c17e  xor     rcx, rsp; StackCookie
0x18003c181  call    __security_check_cookie
  ... truncated ...
```
