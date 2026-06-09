# SvrImpl_FWOpenPolicyStore(void *,ushort,_tag_FW_STORE_TYPE,_tag_FW_POLICY_ACCESS_RIGHT,ulong,void * *)

- ea: `0x180039644`
- end: `0x180039a75`
- name: `?SvrImpl_FWOpenPolicyStore@@YAKPEAXGW4_tag_FW_STORE_TYPE@@W4_tag_FW_POLICY_ACCESS_RIGHT@@KPEAPEAX@Z`
- size: `1073`
- prototype: ``
- caller_count: `9`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180038c1c`
- `0x180038cf0`
- `0x180057bd0`
- `0x18006d210`
- `0x180072230`
- `0x1800a9d58`
- `0x1800bb710`
- `0x1800bd854`
- `0x1800be890`

## callees

- `0x180007b58`
- `0x180008a80`
- `0x180008d60`
- `0x1800097b0`
- `0x18000a66c`
- `0x18000a710`
- `0x1800192e0`
- `0x180039644`
- `0x1800617d0`
- `0x1800bb57c`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x180039a4e`
- `fwbase!FwHResultToWindowsError` at `0x180039a4e`
- `fwbase!FwAlloc` at `0x1800396e4`
- `fwbase!FwAlloc` at `0x1800398bd`
- `fwbase!FwAlloc` at `0x1800396e4`
- `fwbase!FwAlloc` at `0x1800398bd`
- `fwbase!FwFree` at `0x180039a16`
- `fwbase!FwFree` at `0x180039a16`
- `FWPolicyIOMgr!FWGPUnlockEx` at `0x1800399f0`
- `FWPolicyIOMgr!FWGPUnlockEx` at `0x1800399f0`
- `FWPolicyIOMgr!FwOpenPolicyStore` at `0x180039966`
- `FWPolicyIOMgr!FwOpenPolicyStore` at `0x180039966`
- `FWPolicyIOMgr!FWGPLock` at `0x180039801`
- `FWPolicyIOMgr!FWGPLock` at `0x180039801`

## string_xrefs

- `0x1800397e5`: `SvrImpl_FWOpenPolicyStore`
- `0x1800399d5`: `SvrImpl_FWOpenPolicyStore`
- `0x1800399e6`: `SvrImpl_FWOpenPolicyStore`
- `0x180039a03`: `SvrImpl_FWOpenPolicyStore`

## pseudocode

```c
__int64 __fastcall SvrImpl_FWOpenPolicyStore(void *a1, __int64 a2, __int64 a3, unsigned int a4, int a5, __int64 *a6)
{
  __int64 v7; // rsi
  unsigned int v8; // r13d
  __int64 v9; // rcx
  __int64 v10; // rbx
  __int64 result; // rax
  __int64 v12; // rbp
  int v13; // ebx
  __int64 v14; // r14
  __int64 v15; // rcx
  __int64 v16; // rdx

  v7 = (int)a3;
  v8 = (unsigned __int16)a2;
  v9 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 225, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids);
      v9 = WPP_GLOBAL_Control;
    }
    if ( (_UNKNOWN *)v9 != &WPP_GLOBAL_Control && (*(_BYTE *)(v9 + 28) & 4) != 0 )
    {
      WPP_SF_DdDD(*(_QWORD *)(v9 + 16), a2, a3, v8, v7, a4, a5);
      v9 = WPP_GLOBAL_Control;
    }
  }
  if ( a5 == 16 )
  {
    v10 = FwAlloc(40);
    if ( v10 )
    {
      FwMoneisSetAppReadiness(1);
      *(_DWORD *)(v10 + 16) = v7;
      *(_DWORD *)(v10 + 24) = a4;
      *(_DWORD *)(v10 + 28) = 16;
      *(_QWORD *)(v10 + 8) = &qword_180134478[121 * v7];
      *(_WORD *)(v10 + 32) = v8;
      *(_WORD *)(v10 + 34) = v8;
      *a6 = v10;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 228, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids, 0);
      return 0;
    }
    else
    {
      *a6 = 0;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 227, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids, 14);
      return 14;
    }
  }
  v12 = 0;
  if ( (_DWORD)v7 == 5 || (a5 & 1) == 0 )
  {
    result = FwAcquireRPCSharedLock("SvrImpl_FWOpenPolicyStore");
    if ( (int)result < 0 )
      return result;
    v14 = 0;
    if ( (_DWORD)v7 == 1 )
    {
      v14 = FWGPLock();
      if ( !v14 )
      {
        v13 = -2147024894;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_Ds(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            230,
            (unsigned int)WPP_681457f4cdf23248f51377d70d9ff610_Traceguids,
            -2147024894,
            (__int64)"FWGPLock");
        goto LABEL_51;
      }
    }
    v13 = FwLock();
    if ( v13 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          231,
          WPP_681457f4cdf23248f51377d70d9ff610_Traceguids,
          (unsigned int)v13);
      goto LABEL_49;
    }
    *a6 = 0;
    v12 = FwAlloc(40);
    if ( v12 )
    {
      if ( a4 == 1 || (((_DWORD)v7 - 1) & 0xFFFFFFFD) != 0 )
      {
        if ( (((_DWORD)v7 - 5) & 0xFFFFFFFB) == 0 || (v13 = FwOpenPolicyStore((unsigned int)v7, a4, 0, v12), v13 >= 0) )
        {
          *(_DWORD *)(v12 + 16) = v7;
          *(_DWORD *)(v12 + 24) = a4;
          *(_DWORD *)(v12 + 28) = a5;
          *(_QWORD *)(v12 + 8) = &qword_180134478[121 * v7];
          *(_WORD *)(v12 + 32) = v8;
          *(_WORD *)(v12 + 34) = v8;
          *a6 = v12;
          goto LABEL_48;
        }
        v15 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_48;
        v16 = 234;
      }
      else
      {
        v13 = -2147024891;
        v15 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_48;
        v16 = 233;
      }
    }
    else
    {
      v13 = -2147024882;
      v15 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_48;
      v16 = 232;
    }
    WPP_SF_d(*(_QWORD *)(v15 + 16), v16, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids, (unsigned int)v13);
LABEL_48:
    FwUnlockInternal(a1, "SvrImpl_FWOpenPolicyStore");
LABEL_49:
    if ( v14 )
      FWGPUnlockEx(v14, "SvrImpl_FWOpenPolicyStore");
    goto LABEL_51;
  }
  v13 = -2147024809;
  if ( (_UNKNOWN *)v9 != &WPP_GLOBAL_Control && (*(_BYTE *)(v9 + 28) & 1) != 0 )
    WPP_SF_d(*(_QWORD *)(v9 + 16), 229, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids, 2147942487LL);
LABEL_51:
  FwReleaseRPCSharedLock((__int64)"SvrImpl_FWOpenPolicyStore");
  if ( v13 < 0 )
    FwFree(v12);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      235,
      WPP_681457f4cdf23248f51377d70d9ff610_Traceguids,
      (unsigned int)v13);
  return FwHResultToWindowsError((unsigned int)v13);
}

```

## disassembly

```asm
0x180039644  mov     [rsp+arg_8], rbx
0x180039649  mov     [rsp+arg_10], rbp
0x18003964e  mov     [rsp+arg_0], rcx
0x180039653  push    rsi
0x180039654  push    r12
0x180039656  push    r13
0x180039658  push    r14
0x18003965a  push    r15
0x18003965c  sub     rsp, 40h
0x180039660  mov     r12d, r9d
0x180039663  movsxd  rsi, r8d
0x180039666  movzx   r13d, dx
0x18003966a  mov     rcx, cs:WPP_GLOBAL_Control
0x180039671  lea     r14, WPP_GLOBAL_Control
0x180039678  mov     r15d, [rsp+68h+arg_20]
0x180039680  lea     rbp, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x180039687  cmp     rcx, r14
0x18003968a  jz      short loc_1800396D6
0x18003968c  test    byte ptr [rcx+1Ch], 8
0x180039690  jz      short loc_1800396AA
0x180039692  mov     rcx, [rcx+10h]
0x180039696  mov     edx, 0E1h
0x18003969b  mov     r8, rbp
0x18003969e  call    WPP_SF_
0x1800396a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800396aa  cmp     rcx, r14
0x1800396ad  jz      short loc_1800396D6
0x1800396af  test    byte ptr [rcx+1Ch], 4
0x1800396b3  jz      short loc_1800396D6
0x1800396b5  mov     rcx, [rcx+10h]
0x1800396b9  mov     r9d, r13d
0x1800396bc  mov     [rsp+68h+var_38], r15d
0x1800396c1  mov     [rsp+68h+var_40], r12d
0x1800396c6  mov     dword ptr [rsp+68h+var_48], esi
0x1800396ca  call    WPP_SF_DdDD
0x1800396cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800396d6  cmp     r15d, 10h
0x1800396da  jnz     loc_1800397A3
0x1800396e0  lea     ecx, [r15+18h]
0x1800396e4  call    cs:__imp_FwAlloc
0x1800396eb  nop     dword ptr [rax+rax+00h]
0x1800396f0  mov     rbx, rax
0x1800396f3  test    rax, rax
0x1800396f6  jnz     short loc_180039734
0x1800396f8  mov     rax, [rsp+68h+arg_28]
0x180039700  mov     [rax], rbx
0x180039703  mov     rcx, cs:WPP_GLOBAL_Control
0x18003970a  lea     ebx, [r15-2]
0x18003970e  cmp     rcx, r14
0x180039711  jz      short loc_18003972D
0x180039713  test    byte ptr [rcx+1Ch], 4
0x180039717  jz      short loc_18003972D
0x180039719  mov     rcx, [rcx+10h]
0x18003971d  mov     edx, 0E3h
0x180039722  mov     r9d, ebx
0x180039725  mov     r8, rbp
0x180039728  call    WPP_SF_d
0x18003972d  mov     eax, ebx
0x18003972f  jmp     loc_180039A5A
0x180039734  mov     ecx, 1
0x180039739  call    FwMoneisSetAppReadiness
0x18003973e  lea     rax, qword_180134478
0x180039745  mov     [rbx+10h], esi
0x180039748  imul    rcx, rsi, 3C8h
0x18003974f  mov     [rbx+18h], r12d
0x180039753  add     rcx, rax
0x180039756  mov     dword ptr [rbx+1Ch], 10h
0x18003975d  mov     rax, [rsp+68h+arg_28]
0x180039765  mov     [rbx+8], rcx
0x180039769  mov     [rbx+20h], r13w
0x18003976e  mov     [rbx+22h], r13w
0x180039773  mov     [rax], rbx
0x180039776  mov     rcx, cs:WPP_GLOBAL_Control
0x18003977d  cmp     rcx, r14
0x180039780  jz      short loc_18003979C
0x180039782  test    byte ptr [rcx+1Ch], 4
0x180039786  jz      short loc_18003979C
0x180039788  mov     rcx, [rcx+10h]
0x18003978c  mov     edx, 0E4h
0x180039791  xor     r9d, r9d
0x180039794  mov     r8, rbp
0x180039797  call    WPP_SF_d
0x18003979c  xor     eax, eax
0x18003979e  jmp     loc_180039A5A
0x1800397a3  xor     ebp, ebp
0x1800397a5  cmp     esi, 5
0x1800397a8  jz      short loc_1800397E5
0x1800397aa  test    r15b, 1
0x1800397ae  jz      short loc_1800397E5
0x1800397b0  mov     ebx, 80070057h
0x1800397b5  cmp     rcx, r14
0x1800397b8  jz      loc_180039A03
0x1800397be  test    byte ptr [rcx+1Ch], 1
0x1800397c2  jz      loc_180039A03
0x1800397c8  mov     rcx, [rcx+10h]
0x1800397cc  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x1800397d3  mov     edx, 0E5h
0x1800397d8  mov     r9d, ebx
0x1800397db  call    WPP_SF_d
0x1800397e0  jmp     loc_180039A03
0x1800397e5  lea     rcx, aSvrimplFwopenp; "SvrImpl_FWOpenPolicyStore"
0x1800397ec  call    FwAcquireRPCSharedLock
0x1800397f1  test    eax, eax
0x1800397f3  js      loc_180039A5A
0x1800397f9  xor     r14d, r14d
0x1800397fc  cmp     esi, 1
0x1800397ff  jnz     short loc_180039864
0x180039801  call    cs:__imp_FWGPLock
0x180039808  nop     dword ptr [rax+rax+00h]
0x18003980d  mov     r14, rax
0x180039810  test    rax, rax
0x180039813  jnz     short loc_180039864
0x180039815  mov     ebx, 80070002h
0x18003981a  mov     rcx, cs:WPP_GLOBAL_Control
0x180039821  lea     r14, WPP_GLOBAL_Control
0x180039828  cmp     rcx, r14
0x18003982b  jz      loc_180039A03
0x180039831  test    [rcx+1Ch], sil
0x180039835  jz      loc_180039A03
0x18003983b  mov     rcx, [rcx+10h]
0x18003983f  lea     rax, aFwgplock_0; "FWGPLock"
0x180039846  mov     edx, 0E6h
0x18003984b  mov     [rsp+68h+var_48], rax
0x180039850  mov     r9d, ebx
0x180039853  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x18003985a  call    WPP_SF_Ds
0x18003985f  jmp     loc_180039A03
0x180039864  call    FwLock
0x180039869  mov     ebx, eax
0x18003986b  test    eax, eax
0x18003986d  jns     short loc_1800398AD
0x18003986f  mov     rcx, cs:WPP_GLOBAL_Control
0x180039876  lea     rax, WPP_GLOBAL_Control
0x18003987d  cmp     rcx, rax
0x180039880  jz      loc_1800399E1
0x180039886  test    byte ptr [rcx+1Ch], 1
0x18003988a  jz      loc_1800399E1
0x180039890  mov     rcx, [rcx+10h]
0x180039894  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x18003989b  mov     edx, 0E7h
0x1800398a0  mov     r9d, ebx
0x1800398a3  call    WPP_SF_d
0x1800398a8  jmp     loc_1800399E1
0x1800398ad  mov     rax, [rsp+68h+arg_28]
0x1800398b5  mov     ecx, 28h ; '('
0x1800398ba  mov     [rax], rbp
0x1800398bd  call    cs:__imp_FwAlloc
0x1800398c4  nop     dword ptr [rax+rax+00h]
0x1800398c9  mov     rbp, rax
0x1800398cc  test    rax, rax
0x1800398cf  jnz     short loc_180039914
0x1800398d1  mov     ebx, 8007000Eh
0x1800398d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800398dd  lea     rax, WPP_GLOBAL_Control
0x1800398e4  cmp     rcx, rax
0x1800398e7  jz      loc_1800399D0
0x1800398ed  test    byte ptr [rcx+1Ch], 1
0x1800398f1  jz      loc_1800399D0
0x1800398f7  mov     edx, 0E8h
0x1800398fc  mov     rcx, [rcx+10h]
0x180039900  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x180039907  mov     r9d, ebx
0x18003990a  call    WPP_SF_d
0x18003990f  jmp     loc_1800399D0
0x180039914  cmp     r12d, 1
0x180039918  jz      short loc_180039951
0x18003991a  lea     eax, [rsi-1]
0x18003991d  test    eax, 0FFFFFFFDh
0x180039922  jnz     short loc_180039951
0x180039924  mov     ebx, 80070005h
0x180039929  mov     rcx, cs:WPP_GLOBAL_Control
0x180039930  lea     rax, WPP_GLOBAL_Control
0x180039937  cmp     rcx, rax
0x18003993a  jz      loc_1800399D0
0x180039940  test    byte ptr [rcx+1Ch], 1
0x180039944  jz      loc_1800399D0
0x18003994a  mov     edx, 0E9h
0x18003994f  jmp     short loc_1800398FC
0x180039951  lea     eax, [rsi-5]
0x180039954  test    eax, 0FFFFFFFBh
0x180039959  jz      short loc_18003999B
0x18003995b  mov     r9, rbp
0x18003995e  xor     r8d, r8d
0x180039961  mov     edx, r12d
0x180039964  mov     ecx, esi
0x180039966  call    cs:__imp_FwOpenPolicyStore
0x18003996d  nop     dword ptr [rax+rax+00h]
0x180039972  mov     ebx, eax
0x180039974  test    eax, eax
0x180039976  jns     short loc_18003999B
0x180039978  mov     rcx, cs:WPP_GLOBAL_Control
0x18003997f  lea     rax, WPP_GLOBAL_Control
0x180039986  cmp     rcx, rax
0x180039989  jz      short loc_1800399D0
0x18003998b  test    byte ptr [rcx+1Ch], 1
0x18003998f  jz      short loc_1800399D0
0x180039991  mov     edx, 0EAh
0x180039996  jmp     loc_1800398FC
0x18003999b  lea     rax, qword_180134478
0x1800399a2  mov     [rbp+10h], esi
0x1800399a5  imul    rcx, rsi, 3C8h
0x1800399ac  mov     [rbp+18h], r12d
0x1800399b0  add     rcx, rax
0x1800399b3  mov     [rbp+1Ch], r15d
0x1800399b7  mov     rax, [rsp+68h+arg_28]
0x1800399bf  mov     [rbp+8], rcx
0x1800399c3  mov     [rbp+20h], r13w
0x1800399c8  mov     [rbp+22h], r13w
0x1800399cd  mov     [rax], rbp
0x1800399d0  mov     rcx, [rsp+68h+arg_0]; void *
0x1800399d5  lea     rdx, aSvrimplFwopenp; "SvrImpl_FWOpenPolicyStore"
0x1800399dc  call    FwUnlockInternal
0x1800399e1  test    r14, r14
0x1800399e4  jz      short loc_1800399FC
0x1800399e6  lea     rdx, aSvrimplFwopenp; "SvrImpl_FWOpenPolicyStore"
0x1800399ed  mov     rcx, r14
0x1800399f0  call    cs:__imp_FWGPUnlockEx
0x1800399f7  nop     dword ptr [rax+rax+00h]
0x1800399fc  lea     r14, WPP_GLOBAL_Control
0x180039a03  lea     rcx, aSvrimplFwopenp; "SvrImpl_FWOpenPolicyStore"
0x180039a0a  call    FwReleaseRPCSharedLock
0x180039a0f  test    ebx, ebx
0x180039a11  jns     short loc_180039A22
0x180039a13  mov     rcx, rbp
0x180039a16  call    cs:__imp_FwFree
0x180039a1d  nop     dword ptr [rax+rax+00h]
0x180039a22  mov     rcx, cs:WPP_GLOBAL_Control
0x180039a29  cmp     rcx, r14
0x180039a2c  jz      short loc_180039A4C
0x180039a2e  test    byte ptr [rcx+1Ch], 8
0x180039a32  jz      short loc_180039A4C
0x180039a34  mov     rcx, [rcx+10h]
0x180039a38  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x180039a3f  mov     edx, 0EBh
0x180039a44  mov     r9d, ebx
0x180039a47  call    WPP_SF_d
0x180039a4c  mov     ecx, ebx
0x180039a4e  call    cs:__imp_FwHResultToWindowsError
0x180039a55  nop     dword ptr [rax+rax+00h]
0x180039a5a  lea     r11, [rsp+68h+var_28]
0x180039a5f  mov     rbx, [r11+38h]
0x180039a63  mov     rbp, [r11+40h]
0x180039a67  mov     rsp, r11
0x180039a6a  pop     r15
0x180039a6c  pop     r14
0x180039a6e  pop     r13
0x180039a70  pop     r12
0x180039a72  pop     rsi
0x180039a73  retn
```
