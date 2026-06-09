# ESIMPM::CoreFSM::NetworkDiscoveryWithOptions(ESIMPM::CoreFSM::_CoreFSMEvent)

- ea: `0x140028620`
- end: `0x140028730`
- name: `?NetworkDiscoveryWithOptions@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@@Z`
- size: `272`
- prototype: ``
- caller_count: `6`
- callee_count: `8`
- tags: ``

## callers

- `0x1400297c0`
- `0x14002984c`
- `0x14002aa1c`
- `0x14002acf8`
- `0x14002b090`
- `0x14002bc98`

## callees

- `0x140002f60`
- `0x140013df8`
- `0x140020620`
- `0x140027e3c`
- `0x1400284bc`
- `0x140028620`
- `0x14002a188`
- `0x14002d7c8`

## string_xrefs

- `0x1400286db`: `Ready to scan except for radio state. Wait for it to be on`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ESIMPM::CoreFSM::NetworkDiscoveryWithOptions(__int64 a1, unsigned int a2)
{
  int v4; // ecx
  int v5; // ecx
  char HighestPriorityProfileInEuicc; // al
  unsigned int *v7; // rcx
  unsigned int v8; // edx
  _OWORD v10[2]; // [rsp+20h] [rbp-50h] BYREF
  wchar_t S2[8]; // [rsp+40h] [rbp-30h] BYREF
  __m128i si128; // [rsp+50h] [rbp-20h]

  v4 = *(_DWORD *)(*(_QWORD *)(a1 + 320) + 16LL);
  *(_OWORD *)S2 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  S2[0] = 0;
  v10[0] = 0;
  v10[1] = si128;
  LOWORD(v10[0]) = 0;
  if ( !v4 )
    goto LABEL_8;
  v5 = v4 - 1;
  if ( !v5 )
  {
    HighestPriorityProfileInEuicc = ESIMPM::CoreFSM::GetHighestPriorityProfileInEuicc(a1, S2, v10);
    v7 = (unsigned int *)a1;
    if ( HighestPriorityProfileInEuicc )
    {
      ESIMPM::CoreFSM::ScanProcedureWithEsimProfileId((ESIMPM::CoreFSM *)a1, S2, (__int64)v10, a2);
      goto LABEL_13;
    }
    v8 = 8;
LABEL_12:
    ESIMPM::CoreFSM::fsmStateTransition(v7, v8, a2);
    goto LABEL_13;
  }
  if ( v5 != 1 )
  {
LABEL_8:
    if ( *(_DWORD *)(a1 + 344) == 1 )
    {
      v8 = 1;
    }
    else
    {
      ESIMPM::Log::Info(
        "ESIMPM::CoreFSM::NetworkDiscoveryWithOptions",
        (const struct _GUID *)(a1 + 184),
        L"Ready to scan except for radio state. Wait for it to be on");
      v8 = 16;
    }
    v7 = (unsigned int *)a1;
    goto LABEL_12;
  }
  ESIMPM::CoreFSM::FindNextProfileToEnable(a1, a2, 1, 0);
LABEL_13:
  std::wstring::_Tidy_deallocate((char **)v10);
  return std::wstring::_Tidy_deallocate((char **)S2);
}

```

## disassembly

```asm
0x140028620  mov     [rsp-8+arg_10], rbx
0x140028625  mov     [rsp-8+arg_18], rdi
0x14002862a  push    rbp
0x14002862b  mov     rbp, rsp
0x14002862e  sub     rsp, 70h
0x140028632  mov     rax, cs:__security_cookie
0x140028639  xor     rax, rsp
0x14002863c  mov     [rbp+var_10], rax
0x140028640  mov     edi, edx
0x140028642  mov     rbx, rcx
0x140028645  mov     rax, [rcx+140h]
0x14002864c  mov     ecx, [rax+10h]
0x14002864f  xorps   xmm0, xmm0
0x140028652  movups  xmmword ptr [rbp+S2], xmm0
0x140028656  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14002865e  movdqu  [rbp+var_20], xmm1
0x140028663  xor     eax, eax
0x140028665  mov     [rbp+S2], ax
0x140028669  movups  [rbp+var_50], xmm0
0x14002866d  movdqu  [rbp+var_40], xmm1
0x140028672  mov     word ptr [rbp+var_50], ax
0x140028676  test    ecx, ecx
0x140028678  jz      short loc_1400286C4
0x14002867a  sub     ecx, 1
0x14002867d  jz      short loc_140028694
0x14002867f  cmp     ecx, 1
0x140028682  jnz     short loc_1400286C4
0x140028684  xor     r9d, r9d
0x140028687  mov     r8b, cl
0x14002868a  mov     rcx, rbx
0x14002868d  call    ?FindNextProfileToEnable@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@_N1@Z; ESIMPM::CoreFSM::FindNextProfileToEnable(ESIMPM::CoreFSM::_CoreFSMEvent,bool,bool)
0x140028692  jmp     short loc_1400286FF
0x140028694  lea     r8, [rbp+var_50]
0x140028698  lea     rdx, [rbp+S2]
0x14002869c  mov     rcx, rbx
0x14002869f  call    ?GetHighestPriorityProfileInEuicc@CoreFSM@ESIMPM@@AEAA_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; ESIMPM::CoreFSM::GetHighestPriorityProfileInEuicc(std::wstring &,std::wstring &)
0x1400286a4  mov     rcx, rbx; this
0x1400286a7  test    al, al
0x1400286a9  jz      short loc_1400286BD
0x1400286ab  mov     r9d, edi
0x1400286ae  lea     r8, [rbp+var_50]
0x1400286b2  lea     rdx, [rbp+S2]; S2
0x1400286b6  call    ?ScanProcedureWithEsimProfileId@CoreFSM@ESIMPM@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0W4_CoreFSMEvent@12@@Z; ESIMPM::CoreFSM::ScanProcedureWithEsimProfileId(std::wstring const &,std::wstring const &,ESIMPM::CoreFSM::_CoreFSMEvent)
0x1400286bb  jmp     short loc_1400286FF
0x1400286bd  mov     edx, 8
0x1400286c2  jmp     short loc_1400286F6
0x1400286c4  cmp     dword ptr [rbx+158h], 1
0x1400286cb  jnz     short loc_1400286D4
0x1400286cd  mov     edx, 1
0x1400286d2  jmp     short loc_1400286F3
0x1400286d4  lea     rdx, [rbx+0B8h]; struct _GUID *
0x1400286db  lea     r8, aReadyToScanExc; "Ready to scan except for radio state. W"...
0x1400286e2  lea     rcx, aEsimpmCorefsmN; "ESIMPM::CoreFSM::NetworkDiscoveryWithOp"...
0x1400286e9  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x1400286ee  mov     edx, 10h
0x1400286f3  mov     rcx, rbx
0x1400286f6  mov     r8d, edi
0x1400286f9  call    ?fsmStateTransition@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMState@12@W4_CoreFSMEvent@12@K@Z; ESIMPM::CoreFSM::fsmStateTransition(ESIMPM::CoreFSM::_CoreFSMState,ESIMPM::CoreFSM::_CoreFSMEvent,ulong)
0x1400286fe  nop
0x1400286ff  lea     rcx, [rbp+var_50]
0x140028703  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140028708  nop
0x140028709  lea     rcx, [rbp+S2]
0x14002870d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140028712  mov     rcx, [rbp+var_10]
0x140028716  xor     rcx, rsp; StackCookie
0x140028719  call    __security_check_cookie
0x14002871e  lea     r11, [rsp+70h+var_s0]
0x140028723  mov     rbx, [r11+20h]
0x140028727  mov     rdi, [r11+28h]
0x14002872b  mov     rsp, r11
0x14002872e  pop     rbp
0x14002872f  retn
```
