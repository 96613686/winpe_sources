# AdapterData::Update(void)

- ea: `0x180019320`
- end: `0x180019bae`
- name: `?Update@AdapterData@@QEAAKXZ`
- size: `2190`
- prototype: `unsigned int __fastcall(AdapterData *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x180019074`

## callees

- `0x18000e36c`
- `0x180011a58`
- `0x1800181a0`
- `0x180019320`
- `0x180019bb4`
- `0x180019c0c`
- `0x180019e2c`
- `0x180019ff0`
- `0x18001a1f4`
- `0x18001a5dc`
- `0x18003eca8`
- `0x180047240`
- `0x18004731c`
- `0x180047f78`
- `0x18006cb6c`

## import_xrefs

- `NSI!NsiGetParameter` at `0x180019493`
- `NSI!NsiGetParameter` at `0x180019493`
- `NSI!NsiAllocateAndGetTable` at `0x180019740`
- `NSI!NsiAllocateAndGetTable` at `0x1800197bf`
- `NSI!NsiAllocateAndGetTable` at `0x180019740`
- `NSI!NsiAllocateAndGetTable` at `0x1800197bf`
- `NSI!NsiFreeTable` at `0x18001992c`
- `NSI!NsiFreeTable` at `0x1800199b2`
- `NSI!NsiFreeTable` at `0x1800199ed`
- `NSI!NsiFreeTable` at `0x180019aa7`
- `NSI!NsiFreeTable` at `0x18001992c`
- `NSI!NsiFreeTable` at `0x1800199b2`
- `NSI!NsiFreeTable` at `0x1800199ed`
- `NSI!NsiFreeTable` at `0x180019aa7`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
unsigned int __fastcall AdapterData::Update(AdapterData *this)
{
  AdapterData *v1; // r12
  unsigned int result; // eax
  _QWORD *v3; // r14
  __int64 v4; // r15
  __int64 v5; // rsi
  unsigned int v6; // edi
  unsigned int Parameter; // eax
  unsigned __int16 v8; // ax
  unsigned int i; // eax
  _OWORD *v10; // rcx
  char *v11; // rax
  __int64 v12; // rdx
  unsigned __int8 v13; // r10
  char v14; // r11
  char v15; // bl
  int v16; // eax
  int v17; // edx
  __int64 j; // r9
  __int64 v19; // r8
  int v20; // r8d
  int v21; // r10d
  _QWORD *v22; // rax
  _QWORD *v23; // rcx
  unsigned int Table; // eax
  unsigned int v25; // edi
  unsigned int v26; // ebx
  __int64 k; // r8
  __int64 v28; // r10
  unsigned int m; // edx
  unsigned int n; // edx
  __int64 *v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  int v35; // [rsp+60h] [rbp-A0h]
  __int128 v37; // [rsp+80h] [rbp-80h] BYREF
  __int64 v38; // [rsp+90h] [rbp-70h]
  char v39; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v40; // [rsp+2B8h] [rbp+1B8h]
  __int64 v41; // [rsp+330h] [rbp+230h] BYREF
  __int64 v42; // [rsp+338h] [rbp+238h] BYREF
  __int64 v43; // [rsp+340h] [rbp+240h] BYREF
  __int64 v44; // [rsp+348h] [rbp+248h] BYREF
  __int128 v45; // [rsp+350h] [rbp+250h] BYREF
  __int64 v46; // [rsp+360h] [rbp+260h]
  unsigned int v47; // [rsp+368h] [rbp+268h] BYREF
  unsigned int v48; // [rsp+36Ch] [rbp+26Ch] BYREF
  __int64 v49; // [rsp+370h] [rbp+270h] BYREF
  __int64 v50; // [rsp+378h] [rbp+278h]
  _OWORD v51[3]; // [rsp+380h] [rbp+280h] BYREF
  __int128 v52; // [rsp+3B0h] [rbp+2B0h]
  __int128 v53; // [rsp+3C0h] [rbp+2C0h]
  __int128 v54; // [rsp+3D0h] [rbp+2D0h]
  _WORD v55[258]; // [rsp+3E0h] [rbp+2E0h] BYREF
  int v56; // [rsp+5E4h] [rbp+4E4h]

  v1 = this;
  result = GetAdaptersAddressesHelper::Update(this);
  if ( !result )
  {
    v37 = 0;
    v38 = 0;
    NdisInterfaceInformation::NdisInterfaceInformation((NdisInterfaceInformation *)&v37);
    v45 = 0;
    v46 = 0;
    std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>(&v45);
    if ( *((_DWORD *)v1 + 7) )
      v3 = *(_QWORD **)v1;
    else
      v3 = 0;
    v4 = *((_QWORD *)&v37 + 1);
    v5 = v37;
    if ( v3 )
    {
      v6 = v38;
      do
      {
        v49 = 0;
        v50 = 0;
        memset(v51, 0, sizeof(v51));
        v52 = 0;
        v53 = 0;
        v54 = 0;
        __builtin_array_init_helper_eh<PER_ADAPTER_FAMILY_DATA>(v51);
        v56 = 0;
        memset_0(v55, 0, 0x208u);
        v49 = v3[28];
        Parameter = NsiGetParameter(1, &NPI_MS_NDIS_MODULEID, 0, v3 + 28, 8, 0, v55, 516, 570);
        if ( Parameter )
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0
            && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
          {
            WPP_SF_d(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              42,
              WPP_a0784bf9df183de1a5c82e50f5cc1506_Traceguids,
              Parameter);
          }
        }
        else
        {
          v8 = v55[0] >> 1;
          if ( (unsigned __int16)(v55[0] >> 1) > 0x100u )
            v8 = 256;
          v55[v8 + 1] = 0;
        }
        if ( v5 && v4 )
        {
          for ( i = 0; i < v6; ++i )
          {
            if ( *(_QWORD *)(v5 + 8LL * i) == v3[28] )
            {
              v10 = (_OWORD *)(v4 + 656LL * i);
              v11 = &v39;
              v12 = 5;
              do
              {
                *(_OWORD *)v11 = *v10;
                *((_OWORD *)v11 + 1) = v10[1];
                *((_OWORD *)v11 + 2) = v10[2];
                *((_OWORD *)v11 + 3) = v10[3];
                *((_OWORD *)v11 + 4) = v10[4];
                *((_OWORD *)v11 + 5) = v10[5];
                *((_OWORD *)v11 + 6) = v10[6];
                *((_OWORD *)v11 + 7) = v10[7];
                v11 += 128;
                v10 += 8;
                --v12;
              }
              while ( v12 );
              *(_OWORD *)v11 = *v10;
              v50 = v40;
              break;
            }
          }
        }
        v13 = 0;
        v14 = 0;
        v15 = 0;
        v16 = 0;
        v17 = 0;
        for ( j = v3[3]; j; j = *(_QWORD *)(j + 8) )
        {
          if ( *(_DWORD *)(j + 40) == 4 )
          {
            v19 = *(_QWORD *)(j + 16);
            if ( *(_WORD *)v19 == 2 )
            {
              v13 = 1;
              v16 |= 1 << (*(_BYTE *)(j + 36) & 0xEF);
            }
            else if ( *(_WORD *)v19 == 23 )
            {
              v14 = 1;
              if ( (*(_BYTE *)(v19 + 8) & 0xF0) != 0 && (*(_BYTE *)(v19 + 8) & 0xF0) != 0xF0 )
              {
                v15 = 1;
                v17 |= 1 << (*(_BYTE *)(j + 36) & 0xEF);
              }
            }
          }
        }
        LOWORD(v51[0]) = v13;
        DWORD2(v51[0]) = v16;
        LOBYTE(v52) = v14;
        BYTE1(v52) = v15;
        HIDWORD(v52) = v17;
        if ( *((_QWORD *)&v45 + 1) == v46 )
        {
          std::vector<PER_ADAPTER_ADDITIONAL_DATA>::_Emplace_reallocate<PER_ADAPTER_ADDITIONAL_DATA const &>(
            &v45,
            *((_QWORD *)&v45 + 1),
            &v49);
        }
        else
        {
          std::construct_at<PER_ADAPTER_ADDITIONAL_DATA,PER_ADAPTER_ADDITIONAL_DATA const &>(
            *((_QWORD *)&v45 + 1),
            &v49);
          *((_QWORD *)&v45 + 1) += 632LL;
        }
        `eh vector destructor iterator'(
          v51,
          0x30u,
          2u,
          (void (*)(void *))PER_ADAPTER_FAMILY_DATA::~PER_ADAPTER_FAMILY_DATA);
        v3 = (_QWORD *)v3[1];
      }
      while ( v3 );
      v1 = this;
    }
    v20 = 0;
    v21 = *((_DWORD *)v1 + 7);
    if ( v21 )
    {
      v22 = *(_QWORD **)v1;
      if ( *(_QWORD *)v1 )
      {
        do
        {
          ++v20;
          v22 = (_QWORD *)v22[1];
        }
        while ( v22 );
      }
    }
    if ( 0x9B8B577E613716AFuLL * ((__int64)(*((_QWORD *)&v45 + 1) - v45) >> 3) == v20 )
    {
      if ( v21 )
        v23 = *(_QWORD **)v1;
      else
        v23 = 0;
      GetGatewayMacs(v23, &v45);
      v43 = 0;
      v41 = 0;
      v47 = 0;
      Table = NsiAllocateAndGetTable(1, &NPI_MS_IPV6_MODULEID, 7, &v43, 8, &v41, 240, 0, 0, 0, 0, &v47, 0);
      v25 = Table;
      if ( Table
        && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 43, WPP_a0784bf9df183de1a5c82e50f5cc1506_Traceguids, Table);
      }
      v44 = 0;
      v42 = 0;
      v48 = 0;
      LOBYTE(v35) = 0;
      v26 = NsiAllocateAndGetTable(1, &NPI_MS_IPV4_MODULEID, 7, &v44, 8, &v42, 240, 0, 0, 0, 0, &v48, v35);
      if ( v26
        && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 44, WPP_a0784bf9df183de1a5c82e50f5cc1506_Traceguids, v26);
      }
      v28 = *((_QWORD *)&v45 + 1);
      for ( k = v45; k != v28; k += 632 )
      {
        if ( !v25 )
        {
          for ( m = 0; m < v47; ++m )
          {
            if ( *(_QWORD *)k == *(_QWORD *)(v43 + 8LL * m) )
            {
              *(_BYTE *)(k + 67) = *(_BYTE *)(240LL * m + v41 + 1) != 0;
              *(_BYTE *)(k + 66) = *(_BYTE *)(240LL * m + v41 + 165) != 0;
              *(_BYTE *)(k + 68) = *(_BYTE *)(240LL * m + v41 + 152) != 0;
              break;
            }
          }
        }
        if ( !v26 )
        {
          for ( n = 0; n < v48; ++n )
          {
            if ( *(_QWORD *)k == *(_QWORD *)(v44 + 8LL * n) )
            {
              *(_BYTE *)(k + 19) = *(_BYTE *)(240LL * n + v42 + 1) != 0;
              *(_BYTE *)(k + 18) = *(_BYTE *)(240LL * n + v42 + 165) != 0;
              *(_BYTE *)(k + 20) = *(_BYTE *)(240LL * n + v42 + 152) != 0;
              break;
            }
          }
        }
      }
      if ( !v25 )
      {
        NsiFreeTable(v43, v41, 0, 0);
        v43 = 0;
        v41 = 0;
      }
      if ( !v26 )
      {
        NsiFreeTable(v44, v42, 0, 0);
        v44 = 0;
        v42 = 0;
      }
      v31 = (__int64 *)((char *)v1 + 32);
      if ( (__int128 *)((char *)v1 + 32) != &v45 )
      {
        v32 = *v31;
        *v31 = v45;
        *(_QWORD *)&v45 = v32;
        v33 = *((_QWORD *)v1 + 5);
        *((_QWORD *)v1 + 5) = *((_QWORD *)&v45 + 1);
        *((_QWORD *)&v45 + 1) = v33;
        v34 = *((_QWORD *)v1 + 6);
        *((_QWORD *)v1 + 6) = v46;
        v46 = v34;
      }
      *((_DWORD *)v1 + 14) = GetZeroSpecialTickCount();
      if ( (_QWORD)v45 )
      {
        std::_Destroy_range<std::allocator<PER_ADAPTER_ADDITIONAL_DATA>>(v45, *((_QWORD *)&v45 + 1));
        std::_Deallocate<16>((void *)v45, 8 * ((v46 - (__int64)v45) >> 3));
        v45 = 0;
        v46 = 0;
      }
      NsiFreeTable(v5, 0, v4, 0);
      return 0;
    }
    else
    {
      if ( (_QWORD)v45 )
      {
        ((void (*)(void))std::_Destroy_range<std::allocator<PER_ADAPTER_ADDITIONAL_DATA>>)();
        std::_Deallocate<16>((void *)v45, 8 * ((v46 - (__int64)v45) >> 3));
        v45 = 0;
        v46 = 0;
      }
      NsiFreeTable(v5, 0, v4, 0);
      return 14;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180019320  push    rbp
0x180019322  push    rbx
0x180019323  push    rsi
0x180019324  push    rdi
0x180019325  push    r12
0x180019327  push    r13
0x180019329  push    r14
0x18001932b  push    r15
0x18001932d  lea     rbp, [rsp-508h]
0x180019335  sub     rsp, 608h
0x18001933c  mov     rax, cs:__security_cookie
0x180019343  xor     rax, rsp
0x180019346  mov     [rbp+540h+var_50], rax
0x18001934d  mov     r12, rcx
0x180019350  mov     [rsp+640h+var_5C8], rcx
0x180019355  call    ?Update@GetAdaptersAddressesHelper@@QEAAKXZ; GetAdaptersAddressesHelper::Update(void)
0x18001935a  test    eax, eax
0x18001935c  jnz     loc_1800199BA
0x180019362  xorps   xmm0, xmm0
0x180019365  xor     eax, eax
0x180019367  movups  [rbp+540h+var_5C0], xmm0
0x18001936b  mov     [rbp+540h+var_5B0], rax
0x18001936f  lea     rcx, [rbp+540h+var_5C0]; this
0x180019373  call    ??0NdisInterfaceInformation@@QEAA@XZ; NdisInterfaceInformation::NdisInterfaceInformation(void)
0x180019378  nop
0x180019379  xorps   xmm0, xmm0
0x18001937c  xor     eax, eax
0x18001937e  movups  [rbp+540h+var_2F0], xmm0
0x180019385  mov     [rbp+540h+var_2E0], rax
0x18001938c  lea     rcx, [rbp+540h+var_2F0]
0x180019393  call    ??0?$vector@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@V?$allocator@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@3@@std@@QEAA@XZ; std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t>>::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t>>(void)
0x180019398  nop
0x180019399  xor     r13d, r13d
0x18001939c  cmp     [r12+1Ch], r13d
0x1800193a1  jz      loc_180019A83
0x1800193a7  mov     r14, [r12]
0x1800193ab  lea     rbx, WPP_GLOBAL_Control
0x1800193b2  mov     r15, qword ptr [rbp+540h+var_5C0+8]
0x1800193b6  mov     rsi, qword ptr [rbp+540h+var_5C0]
0x1800193ba  test    r14, r14
0x1800193bd  jz      loc_18001965C
0x1800193c3  mov     [rsp+640h+var_5D0], 17h
0x1800193cb  mov     rdi, [rbp+540h+var_5B0]
0x1800193cf  mov     r12d, 2
0x1800193d5  nop     word ptr [rax+rax+00000000h]
0x1800193e0  xor     eax, eax
0x1800193e2  mov     [rbp+540h+var_2D0], rax
0x1800193e9  mov     [rbp+540h+var_2C8], r13
0x1800193f0  xorps   xmm0, xmm0
0x1800193f3  movups  [rbp+540h+var_2C0], xmm0
0x1800193fa  movups  [rbp+540h+var_2B0], xmm0
0x180019401  movups  [rbp+540h+var_2A0], xmm0
0x180019408  movups  [rbp+540h+var_290], xmm0
0x18001940f  movups  [rbp+540h+var_280], xmm0
0x180019416  movups  [rbp+540h+var_270], xmm0
0x18001941d  lea     rcx, [rbp+540h+var_2C0]
0x180019424  call    ??$__builtin_array_init_helper_eh@UPER_ADAPTER_FAMILY_DATA@@@@YAXPEAUPER_ADAPTER_FAMILY_DATA@@_KP6AXPEAX@Z@Z; __builtin_array_init_helper_eh<PER_ADAPTER_FAMILY_DATA>(PER_ADAPTER_FAMILY_DATA *,unsigned __int64,void (*)(void *))
0x180019429  nop
0x18001942a  xor     eax, eax
0x18001942c  mov     [rbp+540h+var_5C], eax
0x180019432  xor     edx, edx; Val
0x180019434  mov     r8d, 208h; Size
0x18001943a  lea     rcx, [rbp+540h+var_260]; void *
0x180019441  call    memset_0
0x180019446  mov     rax, [r14+0E0h]
0x18001944d  mov     [rbp+540h+var_2D0], rax
0x180019454  mov     [rsp+640h+var_600], 23Ah
0x18001945c  mov     dword ptr [rsp+640h+var_608], 204h
0x180019464  lea     rax, [rbp+540h+var_260]
0x18001946b  mov     [rsp+640h+var_610], rax
0x180019470  mov     dword ptr [rsp+640h+var_618], r13d
0x180019475  mov     [rsp+640h+var_620], 8
0x18001947d  lea     r9, [r14+0E0h]
0x180019484  xor     r8d, r8d
0x180019487  lea     rdx, NPI_MS_NDIS_MODULEID
0x18001948e  mov     ecx, 1
0x180019493  call    cs:__imp_NsiGetParameter
0x180019499  test    eax, eax
0x18001949b  jnz     loc_180019AC0
0x1800194a1  movzx   eax, [rbp+540h+var_260]
0x1800194a8  shr     ax, 1
0x1800194ab  mov     ecx, 100h
0x1800194b0  cmp     cx, ax
0x1800194b3  cmovb   ax, cx
0x1800194b7  movzx   ecx, ax
0x1800194ba  mov     [rbp+rcx*2+540h+var_25E], r13w
0x1800194c3  test    rsi, rsi
0x1800194c6  jz      loc_180019576
0x1800194cc  test    r15, r15
0x1800194cf  jz      loc_180019576
0x1800194d5  mov     eax, r13d
0x1800194d8  cmp     eax, edi
0x1800194da  jnb     loc_180019576
0x1800194e0  mov     edx, eax
0x1800194e2  mov     rcx, [r14+0E0h]
0x1800194e9  cmp     [rsi+rdx*8], rcx
0x1800194ed  jz      short loc_1800194F3
0x1800194ef  inc     eax
0x1800194f1  jmp     short loc_1800194D8
0x1800194f3  imul    rcx, rdx, 290h
0x1800194fa  add     rcx, r15
0x1800194fd  lea     rax, [rbp+540h+var_5A0]
0x180019501  mov     edx, 5
0x180019506  movups  xmm0, xmmword ptr [rcx]
0x180019509  movups  xmmword ptr [rax], xmm0
0x18001950c  movups  xmm1, xmmword ptr [rcx+10h]
0x180019510  movups  xmmword ptr [rax+10h], xmm1
0x180019514  movups  xmm0, xmmword ptr [rcx+20h]
0x180019518  movups  xmmword ptr [rax+20h], xmm0
0x18001951c  movups  xmm1, xmmword ptr [rcx+30h]
0x180019520  movups  xmmword ptr [rax+30h], xmm1
0x180019524  movups  xmm0, xmmword ptr [rcx+40h]
0x180019528  movups  xmmword ptr [rax+40h], xmm0
0x18001952c  movups  xmm1, xmmword ptr [rcx+50h]
0x180019530  movups  xmmword ptr [rax+50h], xmm1
0x180019534  movups  xmm0, xmmword ptr [rcx+60h]
0x180019538  movups  xmmword ptr [rax+60h], xmm0
0x18001953c  movups  xmm1, xmmword ptr [rcx+70h]
0x180019540  movups  xmmword ptr [rax+70h], xmm1
0x180019544  lea     rax, [rax+80h]
0x18001954b  lea     rcx, [rcx+80h]
0x180019552  sub     rdx, 1
0x180019556  jnz     short loc_180019506
0x180019558  movups  xmm0, xmmword ptr [rcx]
0x18001955b  movups  xmmword ptr [rax], xmm0
0x18001955e  mov     eax, dword ptr [rbp+540h+var_388]
0x180019564  mov     dword ptr [rbp+540h+var_2C8], eax
0x18001956a  mov     eax, dword ptr [rbp+540h+var_388+4]
0x180019570  mov     dword ptr [rbp+540h+var_2C8+4], eax
0x180019576  xor     r10b, r10b
0x180019579  xor     r11b, r11b
0x18001957c  xor     bl, bl
0x18001957e  mov     eax, r13d
0x180019581  mov     edx, r13d
0x180019584  mov     r9, [r14+18h]
0x180019588  test    r9, r9
0x18001958b  jz      short loc_1800195D2
0x18001958d  cmp     dword ptr [r9+28h], 4
0x180019592  jnz     short loc_1800195C9
0x180019594  mov     r8, [r9+10h]
0x180019598  movzx   ecx, word ptr [r8]
0x18001959c  cmp     r12w, cx
0x1800195a0  jz      loc_18001982F
0x1800195a6  cmp     word ptr [rsp+640h+var_5D0], cx
0x1800195ab  jnz     short loc_1800195C9
0x1800195ad  mov     r11b, 1
0x1800195b0  movzx   ecx, byte ptr [r8+8]
0x1800195b5  and     ecx, 0F0h
0x1800195bb  jz      short loc_1800195C9
0x1800195bd  cmp     ecx, 0F0h
0x1800195c3  jnz     loc_180019B08
0x1800195c9  mov     r9, [r9+8]
0x1800195cd  test    r9, r9
0x1800195d0  jnz     short loc_18001958D
0x1800195d2  mov     byte ptr [rbp+540h+var_2C0], r10b
0x1800195d9  mov     dword ptr [rbp+540h+var_2C0+8], eax
0x1800195df  mov     byte ptr [rbp+540h+var_290], r11b
0x1800195e6  mov     byte ptr [rbp+540h+var_2C0+1], 0
0x1800195ed  mov     byte ptr [rbp+540h+var_290+1], bl
0x1800195f3  mov     dword ptr [rbp+540h+var_290+0Ch], edx
0x1800195f9  mov     rax, qword ptr [rbp+540h+var_2F0+8]
0x180019600  cmp     rax, [rbp+540h+var_2E0]
0x180019607  jz      loc_180019814
0x18001960d  lea     rdx, [rbp+540h+var_2D0]
0x180019614  mov     rcx, rax
0x180019617  call    ??$construct_at@UPER_ADAPTER_ADDITIONAL_DATA@@AEBU1@@std@@YAPEAUPER_ADAPTER_ADDITIONAL_DATA@@QEAU1@AEBU1@@Z; std::construct_at<PER_ADAPTER_ADDITIONAL_DATA,PER_ADAPTER_ADDITIONAL_DATA const &>(PER_ADAPTER_ADDITIONAL_DATA * const,PER_ADAPTER_ADDITIONAL_DATA const &)
0x18001961c  add     qword ptr [rbp+540h+var_2F0+8], 278h
0x180019627  lea     r9, ??1PER_ADAPTER_FAMILY_DATA@@QEAA@XZ; void (*)(void *)
0x18001962e  mov     r8, r12; unsigned __int64
0x180019631  mov     edx, 30h ; '0'; unsigned __int64
0x180019636  lea     rcx, [rbp+540h+var_2C0]; void *
0x18001963d  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180019642  nop
0x180019643  mov     r14, [r14+8]
0x180019647  test    r14, r14
0x18001964a  jnz     loc_1800193E0
0x180019650  mov     r12, [rsp+640h+var_5C8]
0x180019655  lea     rbx, WPP_GLOBAL_Control
0x18001965c  mov     rdx, qword ptr [rbp+540h+var_2F0+8]
0x180019663  mov     r9, rdx
0x180019666  mov     rcx, qword ptr [rbp+540h+var_2F0]
0x18001966d  sub     r9, rcx
0x180019670  sar     r9, 3
0x180019674  mov     r14, 9B8B577E613716AFh
0x18001967e  imul    r9, r14
0x180019682  mov     r8d, r13d
0x180019685  mov     r10d, [r12+1Ch]
0x18001968a  test    r10d, r10d
0x18001968d  jz      short loc_1800196AC
0x18001968f  mov     rax, [r12]
0x180019693  test    rax, rax
0x180019696  jz      short loc_1800196AC
0x180019698  nop     dword ptr [rax+rax+00000000h]
0x1800196a0  inc     r8d
0x1800196a3  mov     rax, [rax+8]
0x1800196a7  test    rax, rax
0x1800196aa  jnz     short loc_1800196A0
0x1800196ac  mov     eax, r8d
0x1800196af  cmp     r9, rax
0x1800196b2  jnz     loc_1800199DD
0x1800196b8  test    r10d, r10d
0x1800196bb  jz      loc_180019A8B
0x1800196c1  mov     rcx, [r12]
0x1800196c5  lea     rdx, [rbp+540h+var_2F0]
0x1800196cc  call    ?GetGatewayMacs@@YAXPEBU_IP_ADAPTER_ADDRESSES_LH@@AEAV?$vector@UPER_ADAPTER_ADDITIONAL_DATA@@V?$allocator@UPER_ADAPTER_ADDITIONAL_DATA@@@std@@@std@@@Z; GetGatewayMacs(_IP_ADAPTER_ADDRESSES_LH const *,std::vector<PER_ADAPTER_ADDITIONAL_DATA> &)
0x1800196d1  mov     [rbp+540h+var_300], r13
0x1800196d8  mov     [rbp+540h+var_310], r13
0x1800196df  mov     [rbp+540h+var_2D8], r13d
0x1800196e6  mov     byte ptr [rsp+640h+var_5E0], 0
0x1800196eb  lea     rax, [rbp+540h+var_2D8]
0x1800196f2  mov     [rsp+640h+var_5E8], rax
0x1800196f7  mov     [rsp+640h+var_5F0], r13d
0x1800196fc  mov     [rsp+640h+var_5F8], r13
0x180019701  mov     [rsp+640h+var_600], r13d
0x180019706  mov     [rsp+640h+var_608], r13
0x18001970b  mov     dword ptr [rsp+640h+var_610], 0F0h
0x180019713  lea     rax, [rbp+540h+var_310]
0x18001971a  mov     [rsp+640h+var_618], rax
0x18001971f  mov     [rsp+640h+var_620], 8
0x180019727  lea     r9, [rbp+540h+var_300]
0x18001972e  mov     r8d, 7
0x180019734  lea     rdx, NPI_MS_IPV6_MODULEID
0x18001973b  mov     ecx, 1
0x180019740  call    cs:__imp_NsiAllocateAndGetTable
0x180019746  mov     edi, eax
0x180019748  test    eax, eax
0x18001974a  jnz     loc_180019B24
0x180019750  mov     [rbp+540h+var_2F8], r13
0x180019757  mov     [rbp+540h+var_308], r13
0x18001975e  mov     [rbp+540h+var_2D4], r13d
0x180019765  mov     byte ptr [rsp+640h+var_5E0], 0
0x18001976a  lea     rax, [rbp+540h+var_2D4]
0x180019771  mov     [rsp+640h+var_5E8], rax
0x180019776  mov     [rsp+640h+var_5F0], r13d
0x18001977b  mov     [rsp+640h+var_5F8], r13
0x180019780  mov     [rsp+640h+var_600], r13d
0x180019785  mov     [rsp+640h+var_608], r13
0x18001978a  mov     dword ptr [rsp+640h+var_610], 0F0h
0x180019792  lea     rax, [rbp+540h+var_308]
0x180019799  mov     [rsp+640h+var_618], rax
0x18001979e  mov     [rsp+640h+var_620], 8
0x1800197a6  lea     r9, [rbp+540h+var_2F8]
0x1800197ad  mov     r8d, 7
0x1800197b3  lea     rdx, NPI_MS_IPV4_MODULEID
0x1800197ba  mov     ecx, 1
0x1800197bf  call    cs:__imp_NsiAllocateAndGetTable
0x1800197c5  mov     ebx, eax
0x1800197c7  test    eax, eax
0x1800197c9  jnz     loc_180019B65
0x1800197cf  mov     r8, qword ptr [rbp+540h+var_2F0]
0x1800197d6  mov     r10, qword ptr [rbp+540h+var_2F0+8]
0x1800197dd  cmp     r8, r10
0x1800197e0  jz      loc_18001990C
0x1800197e6  test    edi, edi
0x1800197e8  jnz     loc_180019890
0x1800197ee  mov     edx, r13d
0x1800197f1  cmp     edx, [rbp+540h+var_2D8]
0x1800197f7  jnb     loc_180019890
0x1800197fd  mov     r9d, edx
0x180019800  mov     rax, [rbp+540h+var_300]
0x180019807  mov     rcx, [rax+r9*8]
0x18001980b  cmp     [r8], rcx
0x18001980e  jz      short loc_18001984A
0x180019810  inc     edx
0x180019812  jmp     short loc_1800197F1
0x180019814  lea     r8, [rbp+540h+var_2D0]
0x18001981b  mov     rdx, rax
0x18001981e  lea     rcx, [rbp+540h+var_2F0]
0x180019825  call    ??$_Emplace_reallocate@AEBUPER_ADAPTER_ADDITIONAL_DATA@@@?$vector@UPER_ADAPTER_ADDITIONAL_DATA@@V?$allocator@UPER_ADAPTER_ADDITIONAL_DATA@@@std@@@std@@AEAAPEAUPER_ADAPTER_ADDITIONAL_DATA@@QEAU2@AEBU2@@Z; std::vector<PER_ADAPTER_ADDITIONAL_DATA>::_Emplace_reallocate<PER_ADAPTER_ADDITIONAL_DATA const &>(PER_ADAPTER_ADDITIONAL_DATA * const,PER_ADAPTER_ADDITIONAL_DATA const &)
0x18001982a  jmp     loc_180019627
0x18001982f  mov     r10b, 1
0x180019832  mov     ecx, [r9+24h]
0x180019836  and     ecx, 0FFFFFFEFh
0x180019839  mov     r8d, 1
0x18001983f  shl     r8d, cl
0x180019842  or      eax, r8d
0x180019845  jmp     loc_1800195C9
0x18001984a  imul    rcx, r9, 0F0h
0x180019851  mov     rax, [rbp+540h+var_310]
0x180019858  cmp     byte ptr [rcx+rax+1], 0
0x18001985d  setnz   al
0x180019860  mov     [r8+43h], al
0x180019864  mov     rax, [rbp+540h+var_310]
0x18001986b  cmp     byte ptr [rcx+rax+0A5h], 0
0x180019873  setnz   al
0x180019876  mov     [r8+42h], al
0x18001987a  mov     rax, [rbp+540h+var_310]
0x180019881  cmp     byte ptr [rcx+rax+98h], 0
0x180019889  setnz   al
0x18001988c  mov     [r8+44h], al
0x180019890  test    ebx, ebx
0x180019892  jnz     short loc_1800198FC
0x180019894  mov     edx, r13d
0x180019897  cmp     edx, [rbp+540h+var_2D4]
0x18001989d  jnb     short loc_1800198FC
0x18001989f  mov     r9d, edx
0x1800198a2  mov     rax, [rbp+540h+var_2F8]
0x1800198a9  mov     rcx, [rax+r9*8]
0x1800198ad  cmp     [r8], rcx
0x1800198b0  jz      short loc_1800198B6
  ... truncated ...
```
