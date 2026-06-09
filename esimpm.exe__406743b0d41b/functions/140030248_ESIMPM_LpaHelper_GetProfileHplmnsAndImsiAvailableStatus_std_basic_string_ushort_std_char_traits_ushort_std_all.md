# ESIMPM::LpaHelper::GetProfileHplmnsAndImsiAvailableStatus(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140030248`
- end: `0x140030393`
- name: `?GetProfileHplmnsAndImsiAvailableStatus@LpaHelper@ESIMPM@@QEBA?AW4ESIM_PROFILE_IMSI_HPLMNID_STATUS@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140028160`

## callees

- `0x140020620`
- `0x140030248`
- `0x1400336c8`

## string_xrefs

- `0x1400302f0`: `pmlnid %s, no imsi`
- `0x1400302f9`: `ESIMPM::LpaHelper::GetProfileHplmnsAndImsiAvailableStatus`
- `0x140030328`: `ESIMPM::LpaHelper::GetProfileHplmnsAndImsiAvailableStatus`
- `0x140030351`: `ESIMPM::LpaHelper::GetProfileHplmnsAndImsiAvailableStatus`
- `0x140030377`: `ESIMPM::LpaHelper::GetProfileHplmnsAndImsiAvailableStatus`
- `0x140030348`: `pmlnid %s, has hplmns and imsi`

## pseudocode

```c
__int64 __fastcall ESIMPM::LpaHelper::GetProfileHplmnsAndImsiAvailableStatus(__int64 a1, __int64 *a2)
{
  __int64 *v3; // rbx
  __int64 *v4; // rcx
  __int64 **v5; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 v8; // rcx
  __int64 v10; // [rsp+30h] [rbp+8h] BYREF

  v3 = **(__int64 ***)(a1 + 24);
  while ( !*((_BYTE *)v3 + 25) )
  {
    v4 = (__int64 *)v3[8];
    if ( *(_DWORD *)(*v4 + 112) )
    {
      std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<ESIMPM::LpaHelper::EsimRecord>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ESIMPM::LpaHelper::EsimRecord>>>,0>>::find(
        v4 + 1,
        &v10,
        (const wchar_t *)a2);
      if ( *(_QWORD *)(v3[8] + 8) != v10 )
      {
        v8 = *(_QWORD *)(v10 + 64);
        if ( *(_QWORD *)(v8 + 80) )
        {
          if ( *(_DWORD *)(v8 + 8) )
          {
            if ( (unsigned __int64)a2[3] > 7 )
              a2 = (__int64 *)*a2;
            ESIMPM::Log::Info(
              "ESIMPM::LpaHelper::GetProfileHplmnsAndImsiAvailableStatus",
              0,
              L"pmlnid %s, has hplmns and imsi",
              a2);
            return 0;
          }
          else
          {
            if ( (unsigned __int64)a2[3] > 7 )
              a2 = (__int64 *)*a2;
            ESIMPM::Log::Info(
              "ESIMPM::LpaHelper::GetProfileHplmnsAndImsiAvailableStatus",
              0,
              L"pmlnid %s, no hplmns",
              a2);
            return 2;
          }
        }
        else
        {
          if ( (unsigned __int64)a2[3] > 7 )
            a2 = (__int64 *)*a2;
          ESIMPM::Log::Info("ESIMPM::LpaHelper::GetProfileHplmnsAndImsiAvailableStatus", 0, L"pmlnid %s, no imsi", a2);
          return 1;
        }
      }
    }
    v5 = (__int64 **)v3[2];
    if ( *((_BYTE *)v5 + 25) )
    {
      for ( i = (__int64 *)v3[1]; !*((_BYTE *)i + 25) && v3 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v3 = i;
      v3 = i;
    }
    else
    {
      v3 = (__int64 *)v3[2];
      for ( j = *v5; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v3 = j;
    }
  }
  if ( (unsigned __int64)a2[3] > 7 )
    a2 = (__int64 *)*a2;
  ESIMPM::Log::Info(
    "ESIMPM::LpaHelper::GetProfileHplmnsAndImsiAvailableStatus",
    0,
    L"didn't find profile for pmlnid %s",
    a2);
  return 3;
}

```

## disassembly

```asm
0x140030248  mov     [rsp+arg_8], rbx
0x14003024d  push    rdi
0x14003024e  sub     rsp, 20h
0x140030252  mov     rbx, [rcx+18h]
0x140030256  mov     rdi, rdx
0x140030259  mov     rbx, [rbx]
0x14003025c  cmp     byte ptr [rbx+19h], 0
0x140030260  jnz     loc_140030361
0x140030266  mov     rcx, [rbx+40h]
0x14003026a  mov     rax, [rcx]
0x14003026d  cmp     dword ptr [rax+70h], 0
0x140030271  jz      short loc_140030293
0x140030273  add     rcx, 8
0x140030277  lea     rdx, [rsp+28h+arg_0]
0x14003027c  mov     r8, rdi
0x14003027f  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UEsimRecord@LpaHelper@ESIMPM@@U?$default_delete@UEsimRecord@LpaHelper@ESIMPM@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UEsimRecord@LpaHelper@ESIMPM@@U?$default_delete@UEsimRecord@LpaHelper@ESIMPM@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UEsimRecord@LpaHelper@ESIMPM@@U?$default_delete@UEsimRecord@LpaHelper@ESIMPM@@@std@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<ESIMPM::LpaHelper::EsimRecord>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ESIMPM::LpaHelper::EsimRecord>>>,0>>::find(std::wstring const &)
0x140030284  mov     rcx, [rbx+40h]
0x140030288  mov     rax, [rsp+28h+arg_0]
0x14003028d  cmp     [rcx+8], rax
0x140030291  jnz     short loc_1400302D8
0x140030293  mov     rcx, [rbx+10h]
0x140030297  cmp     byte ptr [rcx+19h], 0
0x14003029b  jz      short loc_1400302BB
0x14003029d  mov     rax, [rbx+8]
0x1400302a1  jmp     short loc_1400302B0
0x1400302a3  cmp     rbx, [rax+10h]
0x1400302a7  jnz     short loc_1400302B6
0x1400302a9  mov     rbx, rax
0x1400302ac  mov     rax, [rax+8]
0x1400302b0  cmp     byte ptr [rax+19h], 0
0x1400302b4  jz      short loc_1400302A3
0x1400302b6  mov     rbx, rax
0x1400302b9  jmp     short loc_14003025C
0x1400302bb  mov     rbx, rcx
0x1400302be  mov     rcx, [rcx]
0x1400302c1  cmp     byte ptr [rcx+19h], 0
0x1400302c5  jnz     short loc_14003025C
0x1400302c7  mov     rax, [rcx]
0x1400302ca  mov     rbx, rcx
0x1400302cd  mov     rcx, rax
0x1400302d0  cmp     byte ptr [rax+19h], 0
0x1400302d4  jz      short loc_1400302C7
0x1400302d6  jmp     short loc_14003025C
0x1400302d8  mov     rcx, [rax+40h]
0x1400302dc  cmp     qword ptr [rcx+50h], 0
0x1400302e1  jnz     short loc_14003030C
0x1400302e3  cmp     qword ptr [rdi+18h], 7
0x1400302e8  jbe     short loc_1400302ED
0x1400302ea  mov     rdi, [rdi]
0x1400302ed  mov     r9, rdi
0x1400302f0  lea     r8, aPmlnidSNoImsi; "pmlnid %s, no imsi"
0x1400302f7  xor     edx, edx; struct _GUID *
0x1400302f9  lea     rcx, aEsimpmLpahelpe_9; "ESIMPM::LpaHelper::GetProfileHplmnsAndI"...
0x140030300  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x140030305  mov     eax, 1
0x14003030a  jmp     short loc_140030388
0x14003030c  cmp     dword ptr [rcx+8], 0
0x140030310  jnz     short loc_14003033B
0x140030312  cmp     qword ptr [rdi+18h], 7
0x140030317  jbe     short loc_14003031C
0x140030319  mov     rdi, [rdi]
0x14003031c  mov     r9, rdi
0x14003031f  lea     r8, aPmlnidSNoHplmn; "pmlnid %s, no hplmns"
0x140030326  xor     edx, edx; struct _GUID *
0x140030328  lea     rcx, aEsimpmLpahelpe_9; "ESIMPM::LpaHelper::GetProfileHplmnsAndI"...
0x14003032f  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x140030334  mov     eax, 2
0x140030339  jmp     short loc_140030388
0x14003033b  cmp     qword ptr [rdi+18h], 7
0x140030340  jbe     short loc_140030345
0x140030342  mov     rdi, [rdi]
0x140030345  mov     r9, rdi
0x140030348  lea     r8, aPmlnidSHasHplm; "pmlnid %s, has hplmns and imsi"
0x14003034f  xor     edx, edx; struct _GUID *
0x140030351  lea     rcx, aEsimpmLpahelpe_9; "ESIMPM::LpaHelper::GetProfileHplmnsAndI"...
0x140030358  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x14003035d  xor     eax, eax
0x14003035f  jmp     short loc_140030388
0x140030361  cmp     qword ptr [rdi+18h], 7
0x140030366  jbe     short loc_14003036B
0x140030368  mov     rdi, [rdi]
0x14003036b  mov     r9, rdi
0x14003036e  lea     r8, aDidnTFindProfi; "didn't find profile for pmlnid %s"
0x140030375  xor     edx, edx; struct _GUID *
0x140030377  lea     rcx, aEsimpmLpahelpe_9; "ESIMPM::LpaHelper::GetProfileHplmnsAndI"...
0x14003037e  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x140030383  mov     eax, 3
0x140030388  mov     rbx, [rsp+28h+arg_8]
0x14003038d  add     rsp, 20h
0x140030391  pop     rdi
0x140030392  retn
```
