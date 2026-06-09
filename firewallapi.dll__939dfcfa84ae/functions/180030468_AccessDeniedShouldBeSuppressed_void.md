# AccessDeniedShouldBeSuppressed(void)

- ea: `0x180030468`
- end: `0x1800306e5`
- name: `?AccessDeniedShouldBeSuppressed@@YAHXZ`
- size: `637`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000283c`
- `0x18003bd9c`

## callees

- `0x180005e0c`
- `0x1800090d0`
- `0x18000cc80`
- `0x18000d0f0`
- `0x18000ed70`
- `0x1800294b0`
- `0x180030468`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030655`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030655`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003061b`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003061b`
- `fwbase!FwSidDestroy` at `0x18003063b`
- `fwbase!FwSidDestroy` at `0x1800306be`
- `fwbase!FwSidDestroy` at `0x18003063b`
- `fwbase!FwSidDestroy` at `0x1800306be`
- `fwbase!FwSidCreate` at `0x1800305f9`
- `fwbase!FwSidCreate` at `0x1800305f9`

## pseudocode

```c
__int64 AccessDeniedShouldBeSuppressed(void)
{
  unsigned int v0; // ebx
  unsigned int v1; // eax
  __int64 v2; // rdx
  __int64 v3; // r8
  __int64 LastError; // r9
  FwPolicy2 *v5; // rcx
  __int64 v6; // rdx
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned __int16 v10; // ax
  int v12; // [rsp+40h] [rbp-19h]
  int v13; // [rsp+44h] [rbp-15h]
  __int64 v14; // [rsp+48h] [rbp-11h]
  __int64 v15; // [rsp+50h] [rbp-9h]
  unsigned int v16; // [rsp+58h] [rbp-1h] BYREF
  PSID SidToCheck; // [rsp+60h] [rbp+7h] BYREF
  __int64 v18; // [rsp+68h] [rbp+Fh] BYREF
  WINBOOL IsMember; // [rsp+70h] [rbp+17h] BYREF
  int v20; // [rsp+74h] [rbp+1Bh] BYREF
  int v21; // [rsp+78h] [rbp+1Fh] BYREF

  v14 = 6;
  v18 = 0;
  v21 = 0;
  v0 = 0;
  v16 = 0;
  v15 = 18;
  v20 = 4;
  v12 = 4;
  v13 = 1;
  SidToCheck = 0;
  v1 = FWOpenPolicyStore(0x221u, 0, 5u, 1u, 0, &v18);
  LastError = v1;
  if ( v1 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 73;
LABEL_5:
      WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids, LastError);
    }
  }
  else
  {
    v7 = FWGetGlobalConfig(512, 0, 5, 2, 0, (__int64)&v21, (__int64)&v20);
    LastError = v7;
    if ( v7 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 74;
        goto LABEL_5;
      }
    }
    else
    {
      IsMember = 0;
      v8 = FWGetConfig2(v18, 10, v21, 1, (__int64)&v16, (__int64)&v20, (__int64)&IsMember);
      LastError = v8;
      if ( v8 )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v6 = 75;
          goto LABEL_5;
        }
      }
      else if ( !v16 )
      {
        v16 = 0;
        v9 = 0;
        while ( 1 )
        {
          if ( v9 >= 3 )
          {
            v0 = 1;
            goto LABEL_28;
          }
          v10 = FwSidCreate((unsigned int)*(&v12 + 2 * v9), 0, &SidToCheck, LastError);
          LastError = v10;
          IsMember = 0;
          if ( v10 )
            break;
          if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
          {
            LastError = GetLastError();
            v5 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v6 = 77;
              goto LABEL_5;
            }
            goto LABEL_28;
          }
          if ( IsMember != *(&v13 + 2 * v16) )
            goto LABEL_28;
          FwSidDestroy(SidToCheck);
          v9 = v16 + 1;
          SidToCheck = 0;
          ++v16;
        }
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v6 = 76;
          goto LABEL_5;
        }
      }
    }
  }
LABEL_28:
  if ( v18 )
    FWClosePolicyStore(v18, v2, v3, LastError);
  FwSidDestroy(SidToCheck);
  return v0;
}

```

## disassembly

```asm
0x180030468  push    rbp
0x18003046a  push    rbx
0x18003046b  push    rsi
0x18003046c  push    rdi
0x18003046d  lea     rbp, [rsp-3Fh]
0x180030472  sub     rsp, 98h
0x180030479  mov     rax, cs:__security_cookie
0x180030480  xor     rax, rsp
0x180030483  mov     [rbp+57h+var_30], rax
0x180030487  xor     edi, edi
0x180030489  mov     [rbp+57h+var_68], 6
0x180030491  mov     ecx, 221h
0x180030496  mov     [rbp+57h+var_48], rdi
0x18003049a  xor     edx, edx
0x18003049c  mov     [rbp+57h+var_38], edi
0x18003049f  mov     ebx, edi
0x1800304a1  mov     [rbp+57h+var_58], edi
0x1800304a4  lea     eax, [rdi+4]
0x1800304a7  mov     [rbp+57h+var_60], 12h
0x1800304af  mov     [rbp+57h+var_3C], eax
0x1800304b2  lea     esi, [rdi+1]
0x1800304b5  mov     [rbp+57h+var_70], eax
0x1800304b8  lea     r8d, [rdi+5]
0x1800304bc  lea     rax, [rbp+57h+var_48]
0x1800304c0  mov     [rbp+57h+var_6C], esi
0x1800304c3  mov     [rsp+0B0h+var_88], rax
0x1800304c8  mov     r9d, esi
0x1800304cb  mov     dword ptr [rsp+0B0h+var_90], edi
0x1800304cf  mov     [rbp+57h+SidToCheck], rdi
0x1800304d3  call    FWOpenPolicyStore
0x1800304d8  mov     r9d, eax
0x1800304db  test    eax, eax
0x1800304dd  jz      short loc_180030518
0x1800304df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800304e6  lea     rax, WPP_GLOBAL_Control
0x1800304ed  cmp     rcx, rax
0x1800304f0  jz      loc_1800306AC
0x1800304f6  test    [rcx+1Ch], sil
0x1800304fa  jz      loc_1800306AC
0x180030500  lea     edx, [rdi+49h]
0x180030503  mov     rcx, [rcx+10h]
0x180030507  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x18003050e  call    WPP_SF_d
0x180030513  jmp     loc_1800306AC
0x180030518  xor     edx, edx
0x18003051a  lea     rax, [rbp+57h+var_3C]
0x18003051e  mov     [rsp+0B0h+var_80], rax
0x180030523  mov     ecx, 200h
0x180030528  lea     rax, [rbp+57h+var_38]
0x18003052c  mov     [rsp+0B0h+var_88], rax
0x180030531  lea     r9d, [rdx+2]
0x180030535  mov     dword ptr [rsp+0B0h+var_90], edi
0x180030539  lea     r8d, [rdx+5]
0x18003053d  call    FWGetGlobalConfig
0x180030542  mov     r9d, eax
0x180030545  test    eax, eax
0x180030547  jz      short loc_180030571
0x180030549  mov     rcx, cs:WPP_GLOBAL_Control
0x180030550  lea     rax, WPP_GLOBAL_Control
0x180030557  cmp     rcx, rax
0x18003055a  jz      loc_1800306AC
0x180030560  test    [rcx+1Ch], sil
0x180030564  jz      loc_1800306AC
0x18003056a  mov     edx, 4Ah ; 'J'
0x18003056f  jmp     short loc_180030503
0x180030571  mov     r8d, [rbp+57h+var_38]
0x180030575  lea     rax, [rbp+57h+IsMember]
0x180030579  mov     rcx, [rbp+57h+var_48]
0x18003057d  mov     r9d, esi
0x180030580  mov     [rsp+0B0h+var_80], rax
0x180030585  mov     edx, 0Ah
0x18003058a  lea     rax, [rbp+57h+var_3C]
0x18003058e  mov     [rbp+57h+IsMember], edi
0x180030591  mov     [rsp+0B0h+var_88], rax
0x180030596  lea     rax, [rbp+57h+var_58]
0x18003059a  mov     [rsp+0B0h+var_90], rax
0x18003059f  call    FWGetConfig2
0x1800305a4  mov     r9d, eax
0x1800305a7  test    eax, eax
0x1800305a9  jz      short loc_1800305D6
0x1800305ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800305b2  lea     rax, WPP_GLOBAL_Control
0x1800305b9  cmp     rcx, rax
0x1800305bc  jz      loc_1800306AC
0x1800305c2  test    [rcx+1Ch], sil
0x1800305c6  jz      loc_1800306AC
0x1800305cc  mov     edx, 4Bh ; 'K'
0x1800305d1  jmp     loc_180030503
0x1800305d6  cmp     [rbp+57h+var_58], edi
0x1800305d9  jnz     loc_1800306AC
0x1800305df  mov     [rbp+57h+var_58], edi
0x1800305e2  mov     eax, edi
0x1800305e4  cmp     eax, 3
0x1800305e7  jnb     loc_1800306AA
0x1800305ed  mov     ecx, eax
0x1800305ef  lea     r8, [rbp+57h+SidToCheck]
0x1800305f3  xor     edx, edx
0x1800305f5  mov     ecx, [rbp+rcx*8+57h+var_70]
0x1800305f9  call    cs:__imp_FwSidCreate
0x180030600  nop     dword ptr [rax+rax+00h]
0x180030605  movzx   r9d, ax
0x180030609  mov     [rbp+57h+IsMember], edi
0x18003060c  test    r9d, r9d
0x18003060f  jnz     short loc_180030687
0x180030611  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x180030615  lea     r8, [rbp+57h+IsMember]; IsMember
0x180030619  xor     ecx, ecx; TokenHandle
0x18003061b  call    cs:__imp_CheckTokenMembership
0x180030622  nop     dword ptr [rax+rax+00h]
0x180030627  test    eax, eax
0x180030629  jz      short loc_180030655
0x18003062b  mov     eax, [rbp+57h+var_58]
0x18003062e  mov     ecx, [rbp+rax*8+57h+var_6C]
0x180030632  cmp     [rbp+57h+IsMember], ecx
0x180030635  jnz     short loc_1800306AC
0x180030637  mov     rcx, [rbp+57h+SidToCheck]
0x18003063b  call    cs:__imp_FwSidDestroy
0x180030642  nop     dword ptr [rax+rax+00h]
0x180030647  mov     eax, [rbp+57h+var_58]
0x18003064a  add     eax, esi
0x18003064c  mov     [rbp+57h+SidToCheck], rdi
0x180030650  mov     [rbp+57h+var_58], eax
0x180030653  jmp     short loc_1800305E4
0x180030655  call    cs:__imp_GetLastError
0x18003065c  nop     dword ptr [rax+rax+00h]
0x180030661  mov     r9d, eax
0x180030664  mov     rcx, cs:WPP_GLOBAL_Control
0x18003066b  lea     rax, WPP_GLOBAL_Control
0x180030672  cmp     rcx, rax
0x180030675  jz      short loc_1800306AC
0x180030677  test    [rcx+1Ch], sil
0x18003067b  jz      short loc_1800306AC
0x18003067d  mov     edx, 4Dh ; 'M'
0x180030682  jmp     loc_180030503
0x180030687  mov     rcx, cs:WPP_GLOBAL_Control
0x18003068e  lea     rax, WPP_GLOBAL_Control
0x180030695  cmp     rcx, rax
0x180030698  jz      short loc_1800306AC
0x18003069a  test    [rcx+1Ch], sil
0x18003069e  jz      short loc_1800306AC
0x1800306a0  mov     edx, 4Ch ; 'L'
0x1800306a5  jmp     loc_180030503
0x1800306aa  mov     ebx, esi
0x1800306ac  mov     rcx, [rbp+57h+var_48]
0x1800306b0  test    rcx, rcx
0x1800306b3  jz      short loc_1800306BA
0x1800306b5  call    FWClosePolicyStore
0x1800306ba  mov     rcx, [rbp+57h+SidToCheck]
0x1800306be  call    cs:__imp_FwSidDestroy
0x1800306c5  nop     dword ptr [rax+rax+00h]
0x1800306ca  mov     eax, ebx
0x1800306cc  mov     rcx, [rbp+57h+var_30]
0x1800306d0  xor     rcx, rsp; StackCookie
0x1800306d3  call    __security_check_cookie
0x1800306d8  add     rsp, 98h
0x1800306df  pop     rdi
0x1800306e0  pop     rsi
0x1800306e1  pop     rbx
0x1800306e2  pop     rbp
0x1800306e3  retn
```
