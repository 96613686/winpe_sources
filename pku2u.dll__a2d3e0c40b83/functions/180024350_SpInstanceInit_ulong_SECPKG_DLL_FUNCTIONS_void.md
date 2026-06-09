# SpInstanceInit(ulong,_SECPKG_DLL_FUNCTIONS *,void * *)

- ea: `0x180024350`
- end: `0x180024455`
- name: `?SpInstanceInit@@YAJKPEAU_SECPKG_DLL_FUNCTIONS@@PEAPEAX@Z`
- size: `261`
- prototype: `int(unsigned int, struct _SECPKG_DLL_FUNCTIONS *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180022660`
- `0x180022b24`
- `0x180023d9c`
- `0x180024350`
- `0x18002f60c`
- `0x1800434dc`

## string_xrefs

- `0x1800243e2`: `onecore\ds\security\protocols\pku2u\userapi.cxx`

## pseudocode

```c
__int64 __fastcall SpInstanceInit(__int64 a1, struct _SECPKG_DLL_FUNCTIONS *a2, void **a3)
{
  _DWORD *v4; // rax
  __int64 v5; // rdx
  basessp::BaseSSP *v6; // rcx
  int v7; // ebx

  if ( !Pku2uGlobalBaseSSP )
  {
    v4 = operator new(0x100u, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v4 )
    {
      Pku2uGlobalBaseSSP = 0;
      return 3221225495LL;
    }
    v4[53] = 0;
    *(_QWORD *)v4 = 0x4F50535345534142LL;
    *((_QWORD *)v4 + 28) = 0;
    *((_QWORD *)v4 + 29) = 0;
    Pku2uGlobalBaseSSP = (basessp::BaseSSP *)v4;
  }
  v7 = WSTInitUserModeContextList();
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        (unsigned int)WPP_b11bc16789ec339e90a240f14eab96a8_Traceguids,
        v7,
        (__int64)"onecore\\ds\\security\\protocols\\pku2u\\userapi.cxx",
        221);
    goto LABEL_10;
  }
  v7 = basessp::BaseSSP::SpInstanceInit(v6, v5, a2);
  if ( v7 < 0 )
  {
LABEL_10:
    if ( Pku2uGlobalBaseSSP )
    {
      basessp::BaseSSP::`scalar deleting destructor'(Pku2uGlobalBaseSSP, v5);
      Pku2uGlobalBaseSSP = 0;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180024350  mov     [rsp+arg_0], rbx
0x180024355  push    rdi
0x180024356  sub     rsp, 30h
0x18002435a  cmp     cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA, 0; basessp::BaseSSP * Pku2uGlobalBaseSSP
0x180024362  mov     rdi, rdx
0x180024365  jnz     short loc_1800243BA
0x180024367  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002436e  mov     ecx, 100h; unsigned __int64
0x180024373  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180024378  mov     [rsp+38h+arg_18], rax
0x18002437d  test    rax, rax
0x180024380  jz      loc_18002440C
0x180024386  mov     rcx, 4F50535345534142h
0x180024390  mov     dword ptr [rax+0D4h], 0
0x18002439a  mov     [rax], rcx
0x18002439d  mov     qword ptr [rax+0E0h], 0
0x1800243a8  mov     qword ptr [rax+0E8h], 0
0x1800243b3  mov     cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA, rax; basessp::BaseSSP * Pku2uGlobalBaseSSP
0x1800243ba  call    ?WSTInitUserModeContextList@@YAJXZ; WSTInitUserModeContextList(void)
0x1800243bf  mov     ebx, eax
0x1800243c1  test    eax, eax
0x1800243c3  jns     short loc_18002441E
0x1800243c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800243cc  lea     rax, WPP_GLOBAL_Control
0x1800243d3  cmp     rcx, rax
0x1800243d6  jz      short loc_18002442C
0x1800243d8  test    byte ptr [rcx+1Ch], 1
0x1800243dc  jz      short loc_18002442C
0x1800243de  mov     rcx, [rcx+10h]
0x1800243e2  lea     rax, aOnecoreDsSecur_5; "onecore\\ds\\security\\protocols\\pku2u"...
0x1800243e9  mov     edx, 0Fh
0x1800243ee  mov     [rsp+38h+var_10], 0DDh
0x1800243f6  mov     r9d, ebx
0x1800243f9  mov     [rsp+38h+var_18], rax
0x1800243fe  lea     r8, WPP_b11bc16789ec339e90a240f14eab96a8_Traceguids
0x180024405  call    WPP_SF_dsd
0x18002440a  jmp     short loc_18002442C
0x18002440c  mov     cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA, 0; basessp::BaseSSP * Pku2uGlobalBaseSSP
0x180024417  mov     eax, 0C0000017h
0x18002441c  jmp     short loc_18002444A
0x18002441e  mov     r8, rdi; struct _SECPKG_DLL_FUNCTIONS *
0x180024421  call    ?SpInstanceInit@BaseSSP@basessp@@QEAAJKPEAU_SECPKG_DLL_FUNCTIONS@@@Z; basessp::BaseSSP::SpInstanceInit(ulong,_SECPKG_DLL_FUNCTIONS *)
0x180024426  mov     ebx, eax
0x180024428  test    eax, eax
0x18002442a  jns     short loc_180024448
0x18002442c  mov     rcx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x180024433  test    rcx, rcx
0x180024436  jz      short loc_180024448
0x180024438  call    ??_GBaseSSP@basessp@@QEAAPEAXI@Z; basessp::BaseSSP::`scalar deleting destructor'(uint)
0x18002443d  mov     cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA, 0; basessp::BaseSSP * Pku2uGlobalBaseSSP
0x180024448  mov     eax, ebx
0x18002444a  mov     rbx, [rsp+38h+arg_0]
0x18002444f  add     rsp, 30h
0x180024453  pop     rdi
0x180024454  retn
```
