# ESIMPM::LpaHelper::ProcessServiceInfo(LPA_SERVICE_INFO const *)

- ea: `0x140031c00`
- end: `0x140031e91`
- name: `?ProcessServiceInfo@LpaHelper@ESIMPM@@AEAAXPEBULPA_SERVICE_INFO@@@Z`
- size: `657`
- prototype: `void(ESIMPM::LpaHelper *__hidden this, const struct LPA_SERVICE_INFO *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140024790`

## callees

- `0x140002f60`
- `0x140003244`
- `0x14000327c`
- `0x140003b28`
- `0x14000dd20`
- `0x140013df8`
- `0x1400143c8`
- `0x140020620`
- `0x14002ee70`
- `0x14002efb8`
- `0x140031c00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140031c85`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140031c85`
- `luiapi!LuiRegisterForAllProfileNotifications` at `0x140031dfa`
- `luiapi!LuiRegisterForAllProfileNotifications` at `0x140031dfa`
- `luiapi!LuiRegisterForEsimNotifications` at `0x140031dd3`
- `luiapi!LuiRegisterForEsimNotifications` at `0x140031dd3`

## string_xrefs

- `0x140031c4a`: `ESIMPM::LpaHelper::ProcessServiceInfo`
- `0x140031da6`: `ESIMPM::LpaHelper::ProcessServiceInfo`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ESIMPM::LpaHelper::ProcessServiceInfo(ESIMPM::LpaHelper *this, const struct LPA_SERVICE_INFO *a2)
{
  unsigned int v4; // esi
  void *v5; // rax
  void *v6; // rdi
  void *v7; // rcx
  unsigned int i; // edi
  __int64 v9; // r15
  char *v10; // rsi
  unsigned __int64 v11; // r8
  __int128 *v12; // rdx
  __int64 v13; // r9
  unsigned __int64 j; // rcx
  __int64 v15; // r14
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned __int64 v18; // r8
  __int64 v19; // [rsp+20h] [rbp-49h]
  __int64 v20; // [rsp+28h] [rbp-41h]
  _QWORD v21[2]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v22; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v23[16]; // [rsp+50h] [rbp-19h] BYREF
  __int128 v24; // [rsp+60h] [rbp-9h] BYREF
  __int128 v25; // [rsp+70h] [rbp+7h]

  ESIMPM::Log::Info(
    "ESIMPM::LpaHelper::ProcessServiceInfo",
    0,
    L"cbSize %d, dwParams %x, dwNumESIMs %d",
    *(unsigned int *)a2,
    *((_DWORD *)a2 + 1),
    *((_DWORD *)a2 + 4));
  v4 = *(_DWORD *)a2;
  v5 = operator new[](*(unsigned int *)a2, (const struct std::nothrow_t *)std::nothrow);
  v6 = v5;
  if ( v5 )
    memset_0(v5, 0, v4);
  else
    SetLastError(8u);
  memcpy_s(v6, *(unsigned int *)a2, a2, *(unsigned int *)a2);
  v21[1] = 0;
  v7 = (void *)*((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = v6;
  if ( v7 )
    operator delete(v7);
  if ( (*((_BYTE *)a2 + 4) & 8) != 0 )
  {
    for ( i = 0; i < *((_DWORD *)a2 + 4); ++i )
    {
      v9 = 108LL * i;
      if ( (*((_BYTE *)a2 + v9 + 20) & 1) != 0 )
      {
        v21[0] = *((_QWORD *)this + 6);
        v10 = (char *)a2 + v9 + 24;
        v24 = 0;
        v25 = 0;
        v11 = -1;
        do
          ++v11;
        while ( *(_WORD *)&v10[2 * v11] );
        std::wstring::_Construct<1,unsigned short const *>(&v24, (char *)a2 + v9 + 24, v11);
        v12 = &v24;
        if ( *((_QWORD *)&v25 + 1) > 7u )
          v12 = (__int128 *)v24;
        v13 = 0xCBF29CE484222325uLL;
        for ( j = 0; j < 2 * (__int64)v25; ++j )
          v13 = 0x100000001B3LL * (*((unsigned __int8 *)v12 + j) ^ (unsigned __int64)v13);
        v15 = std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(
                (_QWORD *)this + 5,
                &v22,
                (__int64)&v24,
                v13)[1];
        if ( !v15 )
          v15 = *((_QWORD *)this + 6);
        std::wstring::_Tidy_deallocate((char **)&v24);
        LODWORD(v20) = v21[0] == v15;
        LODWORD(v19) = *(_DWORD *)((char *)a2 + v9 + 20);
        ESIMPM::Log::Info(
          "ESIMPM::LpaHelper::ProcessServiceInfo",
          0,
          L"esimInfo %s, dwParams %x, fNotFoundEsimInfo %d",
          (char *)a2 + v9 + 24,
          v19,
          v20);
        if ( v21[0] == v15 )
        {
          LODWORD(v21[0]) = 0;
          v16 = LuiRegisterForEsimNotifications(*(_QWORD *)this, 0, v10, v21);
          ESIMPM::Log::Info("ESIMPM::LpaHelper::ProcessServiceInfo", 0, L"LuiRegisterForEsimNotifications hr = %x", v16);
          v17 = LuiRegisterForAllProfileNotifications(*(_QWORD *)this, 0, v10, v21);
          ESIMPM::Log::Info(
            "ESIMPM::LpaHelper::ProcessServiceInfo",
            0,
            L"LuiRegisterForAllProfileNotifications hr = %x",
            v17);
          v24 = 0;
          v25 = 0;
          v18 = -1;
          do
            ++v18;
          while ( *(_WORD *)&v10[2 * v18] );
          std::wstring::_Construct<1,unsigned short const *>(&v24, v10, v18);
          std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(
            (float *)this + 10,
            (__int64)v23,
            &v24);
          std::wstring::_Tidy_deallocate((char **)&v24);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x140031c00  mov     [rsp-8+arg_10], rbx
0x140031c05  push    rbp
0x140031c06  push    rsi
0x140031c07  push    rdi
0x140031c08  push    r12
0x140031c0a  push    r13
0x140031c0c  push    r14
0x140031c0e  push    r15
0x140031c10  lea     rbp, [rsp-27h]
0x140031c15  sub     rsp, 90h
0x140031c1c  mov     rax, cs:__security_cookie
0x140031c23  xor     rax, rsp
0x140031c26  mov     [rbp+57h+var_40], rax
0x140031c2a  mov     rbx, rdx
0x140031c2d  mov     r12, rcx
0x140031c30  mov     eax, [rdx+10h]
0x140031c33  mov     dword ptr [rsp+0C0h+var_98], eax
0x140031c37  mov     eax, [rdx+4]
0x140031c3a  mov     dword ptr [rsp+0C0h+var_A0], eax
0x140031c3e  mov     r9d, [rdx]
0x140031c41  lea     r8, aCbsizeDDwparam_1; "cbSize %d, dwParams %x, dwNumESIMs %d"
0x140031c48  xor     edx, edx; struct _GUID *
0x140031c4a  lea     rcx, aEsimpmLpahelpe_2; "ESIMPM::LpaHelper::ProcessServiceInfo"
0x140031c51  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x140031c56  mov     esi, [rbx]
0x140031c58  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140031c5f  mov     ecx, esi; unsigned __int64
0x140031c61  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140031c66  mov     rdi, rax
0x140031c69  xor     r14d, r14d
0x140031c6c  test    rax, rax
0x140031c6f  jz      short loc_140031C80
0x140031c71  mov     r8d, esi; Size
0x140031c74  xor     edx, edx; Val
0x140031c76  mov     rcx, rax; void *
0x140031c79  call    memset_0
0x140031c7e  jmp     short loc_140031C8C
0x140031c80  mov     ecx, 8; dwErrCode
0x140031c85  call    cs:__imp_SetLastError
0x140031c8b  nop
0x140031c8c  mov     edx, [rbx]; DestinationSize
0x140031c8e  mov     r9d, edx; SourceSize
0x140031c91  mov     r8, rbx; Source
0x140031c94  mov     rcx, rdi; Destination
0x140031c97  call    memcpy_s
0x140031c9c  mov     [rbp+57h+var_88], r14
0x140031ca0  mov     rcx, [r12+10h]; Block
0x140031ca5  mov     [r12+10h], rdi
0x140031caa  test    rcx, rcx
0x140031cad  jz      short loc_140031CB4
0x140031caf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140031cb4  test    byte ptr [rbx+4], 8
0x140031cb8  jz      loc_140031E6A
0x140031cbe  mov     edi, r14d
0x140031cc1  cmp     [rbx+10h], r14d
0x140031cc5  jbe     loc_140031E6A
0x140031ccb  mov     eax, edi
0x140031ccd  imul    r15, rax, 6Ch ; 'l'
0x140031cd1  test    byte ptr [r15+rbx+14h], 1
0x140031cd7  jz      loc_140031E5F
0x140031cdd  mov     rax, [r12+30h]
0x140031ce2  mov     [rbp+57h+var_90], rax
0x140031ce6  lea     rsi, [rbx+18h]
0x140031cea  add     rsi, r15
0x140031ced  xorps   xmm0, xmm0
0x140031cf0  movups  [rbp+57h+var_60], xmm0
0x140031cf4  xorps   xmm1, xmm1
0x140031cf7  movdqu  [rbp+57h+var_50], xmm1
0x140031cfc  or      r8, 0FFFFFFFFFFFFFFFFh
0x140031d00  inc     r8
0x140031d03  cmp     [rsi+r8*2], r14w
0x140031d08  jnz     short loc_140031D00
0x140031d0a  mov     rdx, rsi
0x140031d0d  lea     rcx, [rbp+57h+var_60]
0x140031d11  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140031d16  mov     rax, qword ptr [rbp+57h+var_50]
0x140031d1a  lea     rdx, [rbp+57h+var_60]
0x140031d1e  cmp     qword ptr [rbp+57h+var_50+8], 7
0x140031d23  cmova   rdx, qword ptr [rbp+57h+var_60]
0x140031d28  mov     r9, 0CBF29CE484222325h
0x140031d32  lea     r8, [rax+rax]
0x140031d36  mov     rcx, r14
0x140031d39  test    r8, r8
0x140031d3c  jz      short loc_140031D5B
0x140031d3e  movzx   eax, byte ptr [rdx+rcx]
0x140031d42  xor     r9, rax
0x140031d45  mov     r10, 100000001B3h
0x140031d4f  imul    r9, r10
0x140031d53  inc     rcx
0x140031d56  cmp     rcx, r8
0x140031d59  jb      short loc_140031D3E
0x140031d5b  lea     r8, [rbp+57h+var_60]
0x140031d5f  lea     rdx, [rbp+57h+var_80]
0x140031d63  lea     rcx, [r12+28h]
0x140031d68  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x140031d6d  mov     r14, [rax+8]
0x140031d71  test    r14, r14
0x140031d74  jnz     short loc_140031D7B
0x140031d76  mov     r14, [r12+30h]
0x140031d7b  lea     rcx, [rbp+57h+var_60]
0x140031d7f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140031d84  xor     eax, eax
0x140031d86  cmp     [rbp+57h+var_90], r14
0x140031d8a  setz    al
0x140031d8d  mov     dword ptr [rsp+0C0h+var_98], eax
0x140031d91  mov     eax, [r15+rbx+14h]
0x140031d96  mov     dword ptr [rsp+0C0h+var_A0], eax
0x140031d9a  mov     r9, rsi
0x140031d9d  lea     r8, aEsiminfoSDwpar; "esimInfo %s, dwParams %x, fNotFoundEsim"...
0x140031da4  xor     edx, edx; struct _GUID *
0x140031da6  lea     r15, aEsimpmLpahelpe_2; "ESIMPM::LpaHelper::ProcessServiceInfo"
0x140031dad  mov     rcx, r15; char *
0x140031db0  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x140031db5  cmp     [rbp+57h+var_90], r14
0x140031db9  jnz     loc_140031E5C
0x140031dbf  xor     r14d, r14d
0x140031dc2  mov     dword ptr [rbp+57h+var_90], r14d
0x140031dc6  lea     r9, [rbp+57h+var_90]
0x140031dca  mov     r8, rsi
0x140031dcd  xor     edx, edx
0x140031dcf  mov     rcx, [r12]
0x140031dd3  call    cs:__imp_LuiRegisterForEsimNotifications
0x140031dd9  mov     r9d, eax
0x140031ddc  lea     r8, aLuiregisterfor_0; "LuiRegisterForEsimNotifications hr = %x"
0x140031de3  xor     edx, edx; struct _GUID *
0x140031de5  mov     rcx, r15; char *
0x140031de8  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x140031ded  lea     r9, [rbp+57h+var_90]
0x140031df1  mov     r8, rsi
0x140031df4  xor     edx, edx
0x140031df6  mov     rcx, [r12]
0x140031dfa  call    cs:__imp_LuiRegisterForAllProfileNotifications
0x140031e00  mov     r9d, eax
0x140031e03  lea     r8, aLuiregisterfor; "LuiRegisterForAllProfileNotifications h"...
0x140031e0a  xor     edx, edx; struct _GUID *
0x140031e0c  mov     rcx, r15; char *
0x140031e0f  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x140031e14  xorps   xmm0, xmm0
0x140031e17  movups  [rbp+57h+var_60], xmm0
0x140031e1b  xorps   xmm1, xmm1
0x140031e1e  movdqu  [rbp+57h+var_50], xmm1
0x140031e23  or      r8, 0FFFFFFFFFFFFFFFFh
0x140031e27  inc     r8
0x140031e2a  cmp     [rsi+r8*2], r14w
0x140031e2f  jnz     short loc_140031E27
0x140031e31  mov     rdx, rsi
0x140031e34  lea     rcx, [rbp+57h+var_60]
0x140031e38  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140031e3d  nop
0x140031e3e  lea     r8, [rbp+57h+var_60]
0x140031e42  lea     rdx, [rbp+57h+var_70]
0x140031e46  lea     rcx, [r12+28h]
0x140031e4b  call    ??$emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(std::wstring &&)
0x140031e50  nop
0x140031e51  lea     rcx, [rbp+57h+var_60]
0x140031e55  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140031e5a  jmp     short loc_140031E5F
0x140031e5c  xor     r14d, r14d
0x140031e5f  inc     edi
0x140031e61  cmp     edi, [rbx+10h]
0x140031e64  jb      loc_140031CCB
0x140031e6a  mov     rcx, [rbp+57h+var_40]
0x140031e6e  xor     rcx, rsp; StackCookie
0x140031e71  call    __security_check_cookie
0x140031e76  mov     rbx, [rsp+0C0h+arg_10]
0x140031e7e  add     rsp, 90h
0x140031e85  pop     r15
0x140031e87  pop     r14
0x140031e89  pop     r13
0x140031e8b  pop     r12
0x140031e8d  pop     rdi
0x140031e8e  pop     rsi
0x140031e8f  pop     rbp
0x140031e90  retn
```
