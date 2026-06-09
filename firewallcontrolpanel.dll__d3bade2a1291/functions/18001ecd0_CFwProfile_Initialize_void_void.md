# CFwProfile::Initialize(void *,void *)

- ea: `0x18001ecd0`
- end: `0x18001f037`
- name: `?Initialize@CFwProfile@@QEAAJPEAX0@Z`
- size: `871`
- prototype: `__int64 __fastcall(CFwProfile *__hidden this, void *, void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001cbd0`
- `0x18001d33c`

## callees

- `0x180009924`
- `0x18000994c`
- `0x180009a80`
- `0x18001c31c`
- `0x18001ecd0`

## import_xrefs

- `FirewallAPI!FWGetGlobalConfig` at `0x18001ef4f`
- `FirewallAPI!FWGetGlobalConfig` at `0x18001ef4f`
- `FirewallAPI!FwIsGroupPolicyEnforced` at `0x18001efa8`
- `FirewallAPI!FwIsGroupPolicyEnforced` at `0x18001efa8`
- `FirewallAPI!FWGetConfig` at `0x18001ee7e`
- `FirewallAPI!FWGetConfig` at `0x18001ee7e`
- `FirewallAPI!FwAnalyzeFirewallPolicyOnProfile` at `0x18001efcc`
- `FirewallAPI!FwAnalyzeFirewallPolicyOnProfile` at `0x18001efcc`

## pseudocode

```c
__int64 __fastcall CFwProfile::Initialize(CFwProfile *this, void *a2, void *a3)
{
  unsigned int i; // r14d
  int v7; // r15d
  void *v8; // rcx
  int v9; // eax
  signed int IsGroupPolicyEnforced; // ebx
  BOOL v11; // ecx
  CFwCplLua *v12; // rcx
  __int64 v13; // rdx
  int v14; // eax
  __int64 v15; // rdx
  int v17; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v18[3]; // [rsp+44h] [rbp-BCh] BYREF
  _DWORD v19[2]; // [rsp+50h] [rbp-B0h]
  char *v20; // [rsp+58h] [rbp-A8h]
  __int64 v21; // [rsp+60h] [rbp-A0h]
  int v22; // [rsp+68h] [rbp-98h]
  char *v23; // [rsp+70h] [rbp-90h]
  __int64 v24; // [rsp+78h] [rbp-88h]
  int v25; // [rsp+80h] [rbp-80h]
  char *v26; // [rsp+88h] [rbp-78h]
  __int64 v27; // [rsp+90h] [rbp-70h]
  int v28; // [rsp+98h] [rbp-68h]
  char *v29; // [rsp+A0h] [rbp-60h]
  __int64 v30; // [rsp+A8h] [rbp-58h]
  int v31; // [rsp+B0h] [rbp-50h]
  char *v32; // [rsp+B8h] [rbp-48h]
  __int64 v33; // [rsp+C0h] [rbp-40h]
  int v34; // [rsp+C8h] [rbp-38h]
  char *v35; // [rsp+D0h] [rbp-30h]
  __int64 v36; // [rsp+D8h] [rbp-28h]
  int v37; // [rsp+E0h] [rbp-20h]
  char *v38; // [rsp+E8h] [rbp-18h]
  __int64 v39; // [rsp+F0h] [rbp-10h]
  int v40; // [rsp+F8h] [rbp-8h]
  char *v41; // [rsp+100h] [rbp+0h]
  __int64 v42; // [rsp+108h] [rbp+8h]
  int v43; // [rsp+110h] [rbp+10h]
  char *v44; // [rsp+118h] [rbp+18h]
  int v45; // [rsp+120h] [rbp+20h]
  int v46; // [rsp+124h] [rbp+24h]
  int v47; // [rsp+128h] [rbp+28h]
  char *v48; // [rsp+130h] [rbp+30h]
  int v49; // [rsp+138h] [rbp+38h]
  int v50; // [rsp+13Ch] [rbp+3Ch]
  int v51; // [rsp+140h] [rbp+40h]
  char *v52; // [rsp+148h] [rbp+48h]
  int v53; // [rsp+150h] [rbp+50h]
  int v54; // [rsp+154h] [rbp+54h]
  _BYTE v55[64]; // [rsp+160h] [rbp+60h] BYREF
  int v56; // [rsp+1B0h] [rbp+B0h] BYREF
  int v57; // [rsp+1C8h] [rbp+C8h] BYREF

  v57 = 4;
  v56 = 0;
  v17 = 0;
  v18[0] = 0;
  if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_3eafb88137b43a797d412ab5cad0a360_Traceguids);
  v21 = 0;
  v19[0] = 1;
  v20 = (char *)this + 64;
  v24 = 0;
  v23 = (char *)this + 72;
  v22 = 3;
  v26 = (char *)this + 80;
  v29 = (char *)this + 84;
  v32 = (char *)this + 96;
  v35 = (char *)this + 112;
  v38 = (char *)this + 108;
  v41 = (char *)this + 116;
  v44 = (char *)this + 68;
  v48 = (char *)this + 76;
  v47 = 3;
  v52 = (char *)this + 100;
  v25 = 17;
  v27 = 1;
  v28 = 16;
  v30 = 1;
  v31 = 10;
  v33 = 1;
  v34 = 12;
  v36 = 0;
  v37 = 11;
  v39 = 0;
  v40 = 13;
  v42 = 0;
  v43 = 1;
  v45 = 0;
  v46 = 1;
  v49 = 0;
  v50 = 1;
  v51 = 10;
  v53 = 1;
  v54 = 1;
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
    (__int64)v55,
    (struct _RTL_CRITICAL_SECTION *)((char *)this + 24));
  for ( i = 0; ; ++i )
  {
    if ( i >= 0xB )
    {
      v14 = FWGetGlobalConfig(545, 0, 5, 2);
      IsGroupPolicyEnforced = v14;
      if ( v14 > 0 )
        IsGroupPolicyEnforced = (unsigned __int16)v14 | 0x80070000;
      if ( IsGroupPolicyEnforced >= 0 )
      {
        v15 = *((unsigned int *)this + 4);
        *((_DWORD *)this + 23) = ((unsigned int)v15 & v56) != 0;
        IsGroupPolicyEnforced = FwIsGroupPolicyEnforced(0, v15, &v17);
        if ( IsGroupPolicyEnforced >= 0 )
        {
          *((_DWORD *)this + 22) = v17;
        }
        else
        {
          *((_DWORD *)this + 22) = 0;
          IsGroupPolicyEnforced = 0;
        }
        FwAnalyzeFirewallPolicyOnProfile(*((unsigned int *)this + 4), v18);
        *((_DWORD *)this + 26) = v18[0] == 0;
      }
      else
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control )
          goto LABEL_38;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_35;
        v13 = 12;
LABEL_23:
        WPP_SF_d(
          *((_QWORD *)v12 + 2),
          v13,
          WPP_3eafb88137b43a797d412ab5cad0a360_Traceguids,
          (unsigned int)IsGroupPolicyEnforced);
      }
      v12 = WPP_GLOBAL_Control;
      goto LABEL_35;
    }
    v7 = *((_DWORD *)&v21 + 6 * i + 1);
    if ( v7 && !a3 )
    {
      *(_DWORD *)(&v20)[3 * i] = 0;
      continue;
    }
    v8 = a3;
    if ( !v7 )
      v8 = a2;
    v9 = FWGetConfig(v8, (unsigned int)v19[6 * i], *((unsigned int *)this + 4), 0, &v56, &v57);
    IsGroupPolicyEnforced = v9;
    if ( v9 > 0 )
      IsGroupPolicyEnforced = (unsigned __int16)v9 | 0x80070000;
    if ( v7 )
    {
      *(_DWORD *)(&v20)[3 * i] = IsGroupPolicyEnforced != -2147024894;
      continue;
    }
    if ( IsGroupPolicyEnforced < 0 )
      break;
    v11 = v56 == 0;
    if ( !*((_DWORD *)&v21 + 6 * i) )
      v11 = v56 != 0;
    *(_DWORD *)(&v20)[3 * i] = v11;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control )
    goto LABEL_38;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v13 = 11;
    goto LABEL_23;
  }
LABEL_35:
  if ( v12 != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)v12 + 2),
      13,
      WPP_3eafb88137b43a797d412ab5cad0a360_Traceguids,
      (unsigned int)IsGroupPolicyEnforced);
LABEL_38:
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)v55);
  return (unsigned int)IsGroupPolicyEnforced;
}

```

## disassembly

```asm
0x18001ecd0  mov     [rsp-8+arg_8], rbx
0x18001ecd5  push    rbp
0x18001ecd6  push    rsi
0x18001ecd7  push    rdi
0x18001ecd8  push    r12
0x18001ecda  push    r13
0x18001ecdc  push    r14
0x18001ecde  push    r15
0x18001ece0  lea     rbp, [rsp-70h]
0x18001ece5  sub     rsp, 170h
0x18001ecec  xor     r15d, r15d
0x18001ecef  mov     [rbp+0A0h+arg_18], 4
0x18001ecf9  mov     [rbp+0A0h+arg_0], r15d
0x18001ed00  mov     r12, r8
0x18001ed03  mov     [rsp+1A0h+var_160], r15d
0x18001ed08  mov     r13, rdx
0x18001ed0b  mov     [rsp+1A0h+var_15C], r15d
0x18001ed10  mov     rdi, rcx
0x18001ed13  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ed1a  lea     rax, WPP_GLOBAL_Control
0x18001ed21  lea     ebx, [r15+0Ah]
0x18001ed25  cmp     rcx, rax
0x18001ed28  jz      short loc_18001ED42
0x18001ed2a  test    byte ptr [rcx+1Ch], 8
0x18001ed2e  jz      short loc_18001ED42
0x18001ed30  mov     rcx, [rcx+10h]
0x18001ed34  lea     r8, WPP_3eafb88137b43a797d412ab5cad0a360_Traceguids
0x18001ed3b  mov     edx, ebx
0x18001ed3d  call    WPP_SF_
0x18001ed42  mov     esi, 1
0x18001ed47  mov     [rsp+1A0h+var_140], r15
0x18001ed4c  lea     rax, [rdi+40h]
0x18001ed50  mov     [rsp+1A0h+var_150], esi
0x18001ed54  mov     [rsp+1A0h+var_148], rax
0x18001ed59  lea     rdx, [rdi+18h]
0x18001ed5d  lea     rax, [rdi+48h]
0x18001ed61  mov     [rsp+1A0h+var_128], r15
0x18001ed66  mov     [rsp+1A0h+var_130], rax
0x18001ed6b  lea     ecx, [rsi+2]
0x18001ed6e  lea     rax, [rdi+50h]
0x18001ed72  mov     [rsp+1A0h+var_138], ecx
0x18001ed76  mov     [rbp+0A0h+var_118], rax
0x18001ed7a  lea     rax, [rdi+54h]
0x18001ed7e  mov     [rbp+0A0h+var_100], rax
0x18001ed82  lea     rax, [rdi+60h]
0x18001ed86  mov     [rbp+0A0h+var_E8], rax
0x18001ed8a  lea     rax, [rdi+70h]
0x18001ed8e  mov     [rbp+0A0h+var_D0], rax
0x18001ed92  lea     rax, [rdi+6Ch]
0x18001ed96  mov     [rbp+0A0h+var_B8], rax
0x18001ed9a  lea     rax, [rdi+74h]
0x18001ed9e  mov     [rbp+0A0h+var_A0], rax
0x18001eda2  lea     rax, [rdi+44h]
0x18001eda6  mov     [rbp+0A0h+var_88], rax
0x18001edaa  lea     rax, [rdi+4Ch]
0x18001edae  mov     [rbp+0A0h+var_70], rax
0x18001edb2  lea     rax, [rdi+64h]
0x18001edb6  mov     [rbp+0A0h+var_78], ecx
0x18001edb9  lea     rcx, [rbp+0A0h+var_40]
0x18001edbd  mov     [rbp+0A0h+var_58], rax
0x18001edc1  mov     [rbp+0A0h+var_120], 11h
0x18001edc8  mov     [rbp+0A0h+var_110], rsi
0x18001edcc  mov     [rbp+0A0h+var_108], 10h
0x18001edd3  mov     [rbp+0A0h+var_F8], rsi
0x18001edd7  mov     [rbp+0A0h+var_F0], ebx
0x18001edda  mov     [rbp+0A0h+var_E0], rsi
0x18001edde  mov     [rbp+0A0h+var_D8], 0Ch
0x18001ede5  mov     [rbp+0A0h+var_C8], r15
0x18001ede9  mov     [rbp+0A0h+var_C0], 0Bh
0x18001edf0  mov     [rbp+0A0h+var_B0], r15
0x18001edf4  mov     [rbp+0A0h+var_A8], 0Dh
0x18001edfb  mov     [rbp+0A0h+var_98], r15
0x18001edff  mov     [rbp+0A0h+var_90], esi
0x18001ee02  mov     [rbp+0A0h+var_80], r15d
0x18001ee06  mov     [rbp+0A0h+var_7C], esi
0x18001ee09  mov     [rbp+0A0h+var_68], r15d
0x18001ee0d  mov     [rbp+0A0h+var_64], esi
0x18001ee10  mov     [rbp+0A0h+var_60], ebx
0x18001ee13  mov     [rbp+0A0h+var_50], esi
0x18001ee16  mov     [rbp+0A0h+var_4C], esi
0x18001ee19  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x18001ee1e  mov     r14d, r15d
0x18001ee21  cmp     r14d, 0Bh
0x18001ee25  jnb     loc_18001EF23
0x18001ee2b  mov     eax, r14d
0x18001ee2e  lea     rsi, [rax+rax*2]
0x18001ee32  mov     r15d, dword ptr [rsp+rsi*8+1A0h+var_140+4]
0x18001ee37  test    r15d, r15d
0x18001ee3a  jz      short loc_18001EE51
0x18001ee3c  test    r12, r12
0x18001ee3f  jnz     short loc_18001EE51
0x18001ee41  mov     rax, [rsp+rsi*8+1A0h+var_148]
0x18001ee46  xor     r15d, r15d
0x18001ee49  mov     [rax], r15d
0x18001ee4c  jmp     loc_18001EED8
0x18001ee51  mov     r8d, [rdi+10h]
0x18001ee55  lea     rax, [rbp+0A0h+arg_18]
0x18001ee5c  mov     edx, [rsp+rsi*8+1A0h+var_150]
0x18001ee60  test    r15d, r15d
0x18001ee63  mov     [rsp+1A0h+var_178], rax
0x18001ee68  mov     rcx, r12
0x18001ee6b  cmovz   rcx, r13
0x18001ee6f  lea     rax, [rbp+0A0h+arg_0]
0x18001ee76  xor     r9d, r9d
0x18001ee79  mov     [rsp+1A0h+var_180], rax
0x18001ee7e  call    cs:__imp_FWGetConfig
0x18001ee84  mov     ebx, eax
0x18001ee86  test    eax, eax
0x18001ee88  jle     short loc_18001EE93
0x18001ee8a  movzx   ebx, ax
0x18001ee8d  or      ebx, 80070000h
0x18001ee93  test    r15d, r15d
0x18001ee96  jz      short loc_18001EEB0
0x18001ee98  mov     rcx, [rsp+rsi*8+1A0h+var_148]
0x18001ee9d  xor     r15d, r15d
0x18001eea0  mov     eax, r15d
0x18001eea3  cmp     ebx, 80070002h
0x18001eea9  setnz   al
0x18001eeac  mov     [rcx], eax
0x18001eeae  jmp     short loc_18001EED8
0x18001eeb0  xor     r15d, r15d
0x18001eeb3  test    ebx, ebx
0x18001eeb5  js      short loc_18001EEE5
0x18001eeb7  cmp     [rbp+0A0h+arg_0], r15d
0x18001eebe  mov     eax, r15d
0x18001eec1  setnz   al
0x18001eec4  mov     ecx, eax
0x18001eec6  xor     ecx, 1
0x18001eec9  cmp     dword ptr [rsp+rsi*8+1A0h+var_140], r15d
0x18001eece  cmovz   ecx, eax
0x18001eed1  mov     rax, [rsp+rsi*8+1A0h+var_148]
0x18001eed6  mov     [rax], ecx
0x18001eed8  mov     esi, 1
0x18001eedd  add     r14d, esi
0x18001eee0  jmp     loc_18001EE21
0x18001eee5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eeec  lea     rdi, WPP_GLOBAL_Control
0x18001eef3  cmp     rcx, rdi
0x18001eef6  jz      loc_18001F011
0x18001eefc  test    byte ptr [rcx+1Ch], 1
0x18001ef00  jz      loc_18001EFEE
0x18001ef06  mov     edx, 0Bh
0x18001ef0b  mov     rcx, [rcx+10h]
0x18001ef0f  lea     r8, WPP_3eafb88137b43a797d412ab5cad0a360_Traceguids
0x18001ef16  mov     r9d, ebx
0x18001ef19  call    WPP_SF_d
0x18001ef1e  jmp     loc_18001EFE7
0x18001ef23  xor     edx, edx
0x18001ef25  lea     rax, [rbp+0A0h+arg_18]
0x18001ef2c  mov     [rsp+1A0h+var_170], rax
0x18001ef31  mov     ecx, 221h
0x18001ef36  lea     rax, [rbp+0A0h+arg_0]
0x18001ef3d  mov     [rsp+1A0h+var_178], rax
0x18001ef42  lea     r9d, [rdx+2]
0x18001ef46  mov     dword ptr [rsp+1A0h+var_180], r15d
0x18001ef4b  lea     r8d, [rdx+5]
0x18001ef4f  call    cs:__imp_FWGetGlobalConfig
0x18001ef55  mov     ebx, eax
0x18001ef57  test    eax, eax
0x18001ef59  jle     short loc_18001EF64
0x18001ef5b  movzx   ebx, ax
0x18001ef5e  or      ebx, 80070000h
0x18001ef64  test    ebx, ebx
0x18001ef66  jns     short loc_18001EF8F
0x18001ef68  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ef6f  lea     rdi, WPP_GLOBAL_Control
0x18001ef76  cmp     rcx, rdi
0x18001ef79  jz      loc_18001F011
0x18001ef7f  test    [rcx+1Ch], sil
0x18001ef83  jz      short loc_18001EFEE
0x18001ef85  mov     edx, 0Ch
0x18001ef8a  jmp     loc_18001EF0B
0x18001ef8f  mov     edx, [rdi+10h]
0x18001ef92  lea     r8, [rsp+1A0h+var_160]
0x18001ef97  test    [rbp+0A0h+arg_0], edx
0x18001ef9d  mov     eax, r15d
0x18001efa0  setnbe  al
0x18001efa3  xor     ecx, ecx
0x18001efa5  mov     [rdi+5Ch], eax
0x18001efa8  call    cs:__imp_FwIsGroupPolicyEnforced
0x18001efae  mov     ebx, eax
0x18001efb0  test    eax, eax
0x18001efb2  jns     short loc_18001EFBD
0x18001efb4  mov     [rdi+58h], r15d
0x18001efb8  mov     ebx, r15d
0x18001efbb  jmp     short loc_18001EFC4
0x18001efbd  mov     eax, [rsp+1A0h+var_160]
0x18001efc1  mov     [rdi+58h], eax
0x18001efc4  mov     ecx, [rdi+10h]
0x18001efc7  lea     rdx, [rsp+1A0h+var_15C]
0x18001efcc  call    cs:__imp_FwAnalyzeFirewallPolicyOnProfile
0x18001efd2  cmp     [rsp+1A0h+var_15C], r15d
0x18001efd7  mov     eax, r15d
0x18001efda  setz    al
0x18001efdd  mov     [rdi+68h], eax
0x18001efe0  lea     rdi, WPP_GLOBAL_Control
0x18001efe7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001efee  cmp     rcx, rdi
0x18001eff1  jz      short loc_18001F011
0x18001eff3  test    byte ptr [rcx+1Ch], 8
0x18001eff7  jz      short loc_18001F011
0x18001eff9  mov     rcx, [rcx+10h]
0x18001effd  lea     r8, WPP_3eafb88137b43a797d412ab5cad0a360_Traceguids
0x18001f004  mov     edx, 0Dh
0x18001f009  mov     r9d, ebx
0x18001f00c  call    WPP_SF_d
0x18001f011  lea     rcx, [rbp+0A0h+var_40]
0x18001f015  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18001f01a  mov     eax, ebx
0x18001f01c  mov     rbx, [rsp+1A0h+arg_8]
0x18001f024  add     rsp, 170h
0x18001f02b  pop     r15
0x18001f02d  pop     r14
0x18001f02f  pop     r13
0x18001f031  pop     r12
0x18001f033  pop     rdi
0x18001f034  pop     rsi
0x18001f035  pop     rbp
0x18001f036  retn
```
