# RasConnectionBase::CacheProperties(_RASENUMENTRYDETAILS const *)

- ea: `0x18002d42c`
- end: `0x18002d695`
- name: `?CacheProperties@RasConnectionBase@@IEAAXPEBU_RASENUMENTRYDETAILS@@@Z`
- size: `617`
- prototype: `void __fastcall(RasConnectionBase *__hidden this, const struct _RASENUMENTRYDETAILS *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002ae10`
- `0x18002d69c`

## callees

- `0x1800043dc`
- `0x18000524c`
- `0x1800052b4`
- `0x1800084fc`
- `0x18002d220`
- `0x18002d42c`
- `0x180032c3c`
- `0x180034e14`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18002d45f`
- `KERNEL32!EnterCriticalSection` at `0x18002d45f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RasConnectionBase::CacheProperties(RasConnectionBase *this, const struct _RASENUMENTRYDETAILS *a2)
{
  __int64 v4; // r8
  char *v5; // r9
  char **v6; // rcx
  unsigned __int64 v7; // r14
  unsigned __int64 v8; // rdx
  char *v9; // rsi
  __int64 v10; // rbx
  __int64 v11; // r8
  char *v12; // r9
  char **v13; // rsi
  char **v14; // r15
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  _DWORD *v20; // rax
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  struct _RTL_CRITICAL_SECTION *v25; // [rsp+30h] [rbp-38h] BYREF

  if ( *(_DWORD *)a2 < 0xE58u )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  v25 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 216);
  *((_DWORD *)this + 14) = 1;
  *((_DWORD *)this + 15) = g_lRasEntryModifiedVersionEra;
  *(_OWORD *)((char *)this + 40) = *(_OWORD *)((char *)a2 + 12);
  RasConnectionBase::SetEntryName(this, (const unsigned __int16 *)a2 + 148);
  *((_DWORD *)this + 33) = *((_DWORD *)a2 + 1) & 1;
  *((_DWORD *)this + 34) = *((_DWORD *)a2 + 7);
  v5 = (char *)a2 + 40;
  v6 = (char **)((char *)this + 96);
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( *(_WORD *)&v5[2 * v8] );
  if ( v8 > *((_QWORD *)this + 15) )
  {
    ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
      v6,
      v8,
      v4,
      v5);
  }
  else
  {
    if ( *((_QWORD *)this + 15) <= 7u )
      v9 = (char *)this + 96;
    else
      v9 = *v6;
    *((_QWORD *)this + 14) = v8;
    v10 = 2 * v8;
    memmove_0(v9, (char *)a2 + 40, 2 * v8);
    *(_WORD *)&v9[v10] = 0;
  }
  *((_DWORD *)this + 36) = *((_DWORD *)a2 + 333);
  v12 = (char *)a2 + 1336;
  v13 = (char **)((char *)this + 152);
  do
    ++v7;
  while ( *(_WORD *)&v12[2 * v7] );
  if ( v7 > *((_QWORD *)this + 22) )
  {
    ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
      (char *)this + 152,
      v7,
      v11,
      v12);
  }
  else
  {
    if ( *((_QWORD *)this + 22) <= 7u )
      v14 = (char **)((char *)this + 152);
    else
      v14 = (char **)*v13;
    *((_QWORD *)this + 21) = v7;
    memmove_0(v14, (char *)a2 + 1336, 2 * v7);
    *((_WORD *)v14 + v7) = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    if ( *((_QWORD *)this + 22) > 7u )
      v13 = (char **)*v13;
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_62ccb5046d2c321286aba42ae98ece6a_Traceguids, v13);
  }
  *((_DWORD *)this + 32) = *((_DWORD *)a2 + 2) == 4;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_62ccb5046d2c321286aba42ae98ece6a_Traceguids,
      *((unsigned int *)a2 + 9),
      *((_DWORD *)a2 + 2));
  v15 = *((unsigned __int16 *)a2 + 18);
  if ( v15 <= 7 )
  {
    if ( v15 == 7 )
      goto LABEL_38;
    if ( !*((_WORD *)a2 + 18) )
      goto LABEL_38;
    v16 = v15 - 1;
    if ( !v16 )
      goto LABEL_38;
    v17 = v16 - 1;
    if ( !v17 )
    {
      v20 = (_DWORD *)((char *)this + 140);
      *((_DWORD *)this + 35) = 2;
      goto LABEL_47;
    }
    v18 = v17 - 1;
    if ( !v18 || (v19 = v18 - 1) == 0 || v19 == 2 )
    {
LABEL_38:
      v20 = (_DWORD *)((char *)this + 140);
LABEL_39:
      *v20 = 4;
      goto LABEL_47;
    }
    goto LABEL_35;
  }
  v21 = v15 - 8;
  if ( !v21 || (v22 = v21 - 1) == 0 )
  {
LABEL_45:
    v20 = (_DWORD *)((char *)this + 140);
LABEL_46:
    *v20 = 5;
    goto LABEL_47;
  }
  v23 = v22 - 3;
  if ( !v23 )
  {
LABEL_35:
    v20 = (_DWORD *)((char *)this + 140);
    if ( *((_DWORD *)a2 + 2) != 2 )
      goto LABEL_39;
    goto LABEL_46;
  }
  v24 = v23 - 1;
  if ( v24 )
  {
    if ( v24 - 1 <= 1 )
      goto LABEL_45;
    goto LABEL_35;
  }
  v20 = (_DWORD *)((char *)this + 140);
  *((_DWORD *)this + 35) = 6;
LABEL_47:
  if ( (*((_DWORD *)a2 + 9) & 0x10000) != 0 )
    *v20 = 5;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v25);
}

```

## disassembly

```asm
0x18002d42c  mov     [rsp+arg_10], rbx
0x18002d431  mov     [rsp+arg_18], rbp
0x18002d436  push    rsi
0x18002d437  push    rdi
0x18002d438  push    r12
0x18002d43a  push    r14
0x18002d43c  push    r15
0x18002d43e  sub     rsp, 40h
0x18002d442  mov     rbp, rdx
0x18002d445  mov     rdi, rcx
0x18002d448  cmp     dword ptr [rdx], 0E58h
0x18002d44e  jnb     short loc_18002D455
0x18002d450  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002d455  lea     rbx, [rdi+0D8h]
0x18002d45c  mov     rcx, rbx; lpCriticalSection
0x18002d45f  call    cs:__imp_EnterCriticalSection
0x18002d465  mov     [rsp+68h+var_38], rbx
0x18002d46a  mov     dword ptr [rdi+38h], 1
0x18002d471  mov     eax, cs:?g_lRasEntryModifiedVersionEra@@3JA; long g_lRasEntryModifiedVersionEra
0x18002d477  mov     [rdi+3Ch], eax
0x18002d47a  movups  xmm0, xmmword ptr [rbp+0Ch]
0x18002d47e  movdqu  xmmword ptr [rdi+28h], xmm0
0x18002d483  lea     rdx, [rbp+128h]; unsigned __int16 *
0x18002d48a  mov     rcx, rdi; this
0x18002d48d  call    ?SetEntryName@RasConnectionBase@@IEAAXPEBG@Z; RasConnectionBase::SetEntryName(ushort const *)
0x18002d492  mov     eax, [rbp+4]
0x18002d495  and     eax, 1
0x18002d498  mov     [rdi+84h], eax
0x18002d49e  mov     eax, [rbp+1Ch]
0x18002d4a1  mov     [rdi+88h], eax
0x18002d4a7  lea     r9, [rbp+28h]
0x18002d4ab  lea     rcx, [rdi+60h]
0x18002d4af  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002d4b3  mov     rdx, r14
0x18002d4b6  xor     r12d, r12d
0x18002d4b9  inc     rdx
0x18002d4bc  cmp     [r9+rdx*2], r12w
0x18002d4c1  jnz     short loc_18002D4B9
0x18002d4c3  cmp     rdx, [rcx+18h]
0x18002d4c7  ja      short loc_18002D4F5
0x18002d4c9  cmp     qword ptr [rcx+18h], 7
0x18002d4ce  jbe     short loc_18002D4D5
0x18002d4d0  mov     rsi, [rcx]
0x18002d4d3  jmp     short loc_18002D4D8
0x18002d4d5  mov     rsi, rcx
0x18002d4d8  mov     [rcx+10h], rdx
0x18002d4dc  lea     rbx, [rdx+rdx]
0x18002d4e0  mov     r8, rbx; Size
0x18002d4e3  mov     rdx, r9; Src
0x18002d4e6  mov     rcx, rsi; void *
0x18002d4e9  call    memmove_0
0x18002d4ee  mov     [rbx+rsi], r12w
0x18002d4f3  jmp     short loc_18002D4FA
0x18002d4f5  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x18002d4fa  mov     eax, [rbp+534h]
0x18002d500  mov     [rdi+90h], eax
0x18002d506  lea     r9, [rbp+538h]
0x18002d50d  lea     rsi, [rdi+98h]
0x18002d514  inc     r14
0x18002d517  cmp     [r9+r14*2], r12w
0x18002d51c  jnz     short loc_18002D514
0x18002d51e  cmp     r14, [rsi+18h]
0x18002d522  ja      short loc_18002D550
0x18002d524  cmp     qword ptr [rsi+18h], 7
0x18002d529  jbe     short loc_18002D530
0x18002d52b  mov     r15, [rsi]
0x18002d52e  jmp     short loc_18002D533
0x18002d530  mov     r15, rsi
0x18002d533  mov     [rsi+10h], r14
0x18002d537  lea     rbx, [r14+r14]
0x18002d53b  mov     r8, rbx; Size
0x18002d53e  mov     rdx, r9; Src
0x18002d541  mov     rcx, r15; void *
0x18002d544  call    memmove_0
0x18002d549  mov     [rbx+r15], r12w
0x18002d54e  jmp     short loc_18002D55B
0x18002d550  mov     rdx, r14
0x18002d553  mov     rcx, rsi
0x18002d556  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x18002d55b  lea     r14, WPP_GLOBAL_Control
0x18002d562  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d569  cmp     rcx, r14
0x18002d56c  jz      short loc_18002D596
0x18002d56e  test    byte ptr [rcx+1Ch], 8
0x18002d572  jz      short loc_18002D596
0x18002d574  cmp     qword ptr [rsi+18h], 7
0x18002d579  jbe     short loc_18002D57E
0x18002d57b  mov     rsi, [rsi]
0x18002d57e  mov     edx, 0Ah
0x18002d583  mov     r9, rsi
0x18002d586  lea     r8, WPP_62ccb5046d2c321286aba42ae98ece6a_Traceguids
0x18002d58d  mov     rcx, [rcx+10h]
0x18002d591  call    WPP_SF_S
0x18002d596  mov     eax, r12d
0x18002d599  mov     ebx, 4
0x18002d59e  cmp     [rbp+8], ebx
0x18002d5a1  setz    al
0x18002d5a4  mov     [rdi+80h], eax
0x18002d5aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d5b1  cmp     rcx, r14
0x18002d5b4  jz      short loc_18002D5DA
0x18002d5b6  test    byte ptr [rcx+1Ch], 8
0x18002d5ba  jz      short loc_18002D5DA
0x18002d5bc  lea     edx, [rbx+7]
0x18002d5bf  mov     eax, [rbp+8]
0x18002d5c2  mov     [rsp+68h+var_48], eax
0x18002d5c6  mov     r9d, [rbp+24h]
0x18002d5ca  lea     r8, WPP_62ccb5046d2c321286aba42ae98ece6a_Traceguids
0x18002d5d1  mov     rcx, [rcx+10h]
0x18002d5d5  call    WPP_SF_dd
0x18002d5da  movzx   ecx, word ptr [rbp+24h]
0x18002d5de  mov     edx, 5
0x18002d5e3  cmp     ecx, 7
0x18002d5e6  ja      short loc_18002D630
0x18002d5e8  jz      short loc_18002D625
0x18002d5ea  test    ecx, ecx
0x18002d5ec  jz      short loc_18002D625
0x18002d5ee  sub     ecx, 1
0x18002d5f1  jz      short loc_18002D625
0x18002d5f3  sub     ecx, 1
0x18002d5f6  jz      short loc_18002D616
0x18002d5f8  sub     ecx, 1
0x18002d5fb  jz      short loc_18002D625
0x18002d5fd  sub     ecx, 1
0x18002d600  jz      short loc_18002D625
0x18002d602  cmp     ecx, 2
0x18002d605  jz      short loc_18002D625
0x18002d607  lea     rax, [rdi+8Ch]
0x18002d60e  cmp     dword ptr [rbp+8], 2
0x18002d612  jz      short loc_18002D655
0x18002d614  jmp     short loc_18002D62C
0x18002d616  lea     rax, [rdi+8Ch]
0x18002d61d  mov     dword ptr [rax], 2
0x18002d623  jmp     short loc_18002D657
0x18002d625  lea     rax, [rdi+8Ch]
0x18002d62c  mov     [rax], ebx
0x18002d62e  jmp     short loc_18002D657
0x18002d630  sub     ecx, 8
0x18002d633  jz      short loc_18002D64E
0x18002d635  sub     ecx, 1
0x18002d638  jz      short loc_18002D64E
0x18002d63a  sub     ecx, 3
0x18002d63d  jz      short loc_18002D607
0x18002d63f  sub     ecx, 1
0x18002d642  jz      short loc_18002D685
0x18002d644  sub     ecx, 1
0x18002d647  jz      short loc_18002D64E
0x18002d649  cmp     ecx, 1
0x18002d64c  jnz     short loc_18002D607
0x18002d64e  lea     rax, [rdi+8Ch]
0x18002d655  mov     [rax], edx
0x18002d657  test    dword ptr [rbp+24h], 10000h
0x18002d65e  jz      short loc_18002D662
0x18002d660  mov     [rax], edx
0x18002d662  lea     rcx, [rsp+68h+var_38]
0x18002d667  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002d66c  lea     r11, [rsp+68h+var_28]
0x18002d671  mov     rbx, [r11+40h]
0x18002d675  mov     rbp, [r11+48h]
0x18002d679  mov     rsp, r11
0x18002d67c  pop     r15
0x18002d67e  pop     r14
0x18002d680  pop     r12
0x18002d682  pop     rdi
0x18002d683  pop     rsi
0x18002d684  retn
0x18002d685  lea     rax, [rdi+8Ch]
0x18002d68c  mov     dword ptr [rax], 6
0x18002d692  jmp     short loc_18002D657
```
