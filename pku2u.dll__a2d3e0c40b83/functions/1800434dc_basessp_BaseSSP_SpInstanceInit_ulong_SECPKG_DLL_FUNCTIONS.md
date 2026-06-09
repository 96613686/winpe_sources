# basessp::BaseSSP::SpInstanceInit(ulong,_SECPKG_DLL_FUNCTIONS *)

- ea: `0x1800434dc`
- end: `0x1800435d7`
- name: `?SpInstanceInit@BaseSSP@basessp@@QEAAJKPEAU_SECPKG_DLL_FUNCTIONS@@@Z`
- size: `251`
- prototype: `__int64 __fastcall(basessp::BaseSSP *__hidden this, unsigned int, struct _SECPKG_DLL_FUNCTIONS *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180024350`

## callees

- `0x180023d9c`
- `0x1800434dc`
- `0x1800435e0`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x180043597`
- `ntdll!RtlFreeSid` at `0x1800435b4`
- `ntdll!RtlFreeSid` at `0x180043597`
- `ntdll!RtlFreeSid` at `0x1800435b4`

## string_xrefs

- `0x180043533`: `onecore\ds\security\protocols\basessp\basessp.cxx`

## pseudocode

```c
__int64 __fastcall basessp::BaseSSP::SpInstanceInit(
        basessp::BaseSSP *this,
        __int64 a2,
        struct _SECPKG_DLL_FUNCTIONS *a3)
{
  basessp::BaseSSP *v3; // rbx
  int v5; // edi
  void *v6; // rcx
  void *v7; // rcx

  v3 = Pku2uGlobalBaseSSP;
  if ( *((_DWORD *)Pku2uGlobalBaseSSP + 53) )
  {
    if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 2 )
    {
      v5 = -1073741637;
      goto LABEL_10;
    }
  }
  else
  {
    *((_DWORD *)Pku2uGlobalBaseSSP + 52) = 2;
  }
  v5 = basessp::BaseSSP::WSTInitGlobalVariables(v3);
  if ( v5 >= 0 )
  {
    *((_QWORD *)v3 + 31) = a3;
    *((_DWORD *)v3 + 53) = 1;
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_dsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)WPP_2e2180da8fc733d68501c61250259024_Traceguids,
      v5,
      (__int64)"onecore\\ds\\security\\protocols\\basessp\\basessp.cxx",
      136);
  }
LABEL_10:
  if ( !*((_DWORD *)v3 + 53) && v5 < 0 )
  {
    v6 = (void *)*((_QWORD *)v3 + 28);
    if ( v6 )
    {
      RtlFreeSid(v6);
      *((_QWORD *)v3 + 28) = 0;
    }
    v7 = (void *)*((_QWORD *)v3 + 29);
    if ( v7 )
    {
      RtlFreeSid(v7);
      *((_QWORD *)v3 + 29) = 0;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800434dc  mov     [rsp+arg_0], rbx
0x1800434e1  mov     [rsp+arg_8], rsi
0x1800434e6  push    rdi
0x1800434e7  sub     rsp, 30h
0x1800434eb  mov     rbx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; basessp::BaseSSP * Pku2uGlobalBaseSSP
0x1800434f2  mov     rsi, r8
0x1800434f5  cmp     dword ptr [rbx+0D4h], 0
0x1800434fc  jnz     short loc_18004355D
0x1800434fe  mov     dword ptr [rbx+0D0h], 2
0x180043508  mov     rcx, rbx; this
0x18004350b  call    ?WSTInitGlobalVariables@BaseSSP@basessp@@AEAAJXZ; basessp::BaseSSP::WSTInitGlobalVariables(void)
0x180043510  mov     edi, eax
0x180043512  test    eax, eax
0x180043514  jns     short loc_18004356D
0x180043516  mov     rcx, cs:WPP_GLOBAL_Control
0x18004351d  lea     rax, WPP_GLOBAL_Control
0x180043524  cmp     rcx, rax
0x180043527  jz      short loc_18004357E
0x180043529  test    byte ptr [rcx+1Ch], 1
0x18004352d  jz      short loc_18004357E
0x18004352f  mov     rcx, [rcx+10h]
0x180043533  lea     rax, aOnecoreDsSecur_1; "onecore\\ds\\security\\protocols\\bases"...
0x18004353a  mov     edx, 0Ah
0x18004353f  mov     [rsp+38h+var_10], 88h
0x180043547  mov     r9d, edi
0x18004354a  mov     [rsp+38h+var_18], rax
0x18004354f  lea     r8, WPP_2e2180da8fc733d68501c61250259024_Traceguids
0x180043556  call    WPP_SF_dsd
0x18004355b  jmp     short loc_18004357E
0x18004355d  cmp     dword ptr [rbx+0D0h], 2
0x180043564  jnz     short loc_180043508
0x180043566  mov     edi, 0C00000BBh
0x18004356b  jmp     short loc_18004357E
0x18004356d  mov     [rbx+0F8h], rsi
0x180043574  mov     dword ptr [rbx+0D4h], 1
0x18004357e  cmp     dword ptr [rbx+0D4h], 0
0x180043585  jnz     short loc_1800435C5
0x180043587  test    edi, edi
0x180043589  jns     short loc_1800435C5
0x18004358b  mov     rcx, [rbx+0E0h]; Sid
0x180043592  test    rcx, rcx
0x180043595  jz      short loc_1800435A8
0x180043597  call    cs:__imp_RtlFreeSid
0x18004359d  mov     qword ptr [rbx+0E0h], 0
0x1800435a8  mov     rcx, [rbx+0E8h]; Sid
0x1800435af  test    rcx, rcx
0x1800435b2  jz      short loc_1800435C5
0x1800435b4  call    cs:__imp_RtlFreeSid
0x1800435ba  mov     qword ptr [rbx+0E8h], 0
0x1800435c5  mov     rbx, [rsp+38h+arg_0]
0x1800435ca  mov     eax, edi
0x1800435cc  mov     rsi, [rsp+38h+arg_8]
0x1800435d1  add     rsp, 30h
0x1800435d5  pop     rdi
0x1800435d6  retn
```
