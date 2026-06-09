# GetDevolutionLevelFromForestName

- ea: `0x180003640`
- end: `0x1800039ee`
- name: `GetDevolutionLevelFromForestName`
- size: `942`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH psz)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800035d4`

## callees

- `0x180003640`
- `0x1800039f4`
- `0x1800639a8`
- `0x18008b5f0`
- `0x18008b630`
- `0x1800cafec`
- `0x1800dbfe0`
- `0x1800dc9e0`
- `0x1800de650`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800038a6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800038a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000368f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000368f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003966`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003966`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18000397b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18000397b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180003795`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180003795`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180003754`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180003754`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180003990`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180003990`

## pseudocode

```c
__int64 __fastcall GetDevolutionLevelFromForestName(wchar_t *psz)
{
  __int64 v2; // rdx
  wchar_t *v3; // r9
  size_t v4; // rdi
  NTSTATUS v5; // eax
  NTSTATUS v6; // eax
  _WORD *v7; // r15
  unsigned __int16 v8; // ax
  _WORD *v9; // rdx
  unsigned __int64 v10; // rbx
  unsigned __int64 v11; // r14
  __int64 v12; // rdx
  size_t pcchLength; // [rsp+20h] [rbp-50h] BYREF
  PVOID PolicyHandle; // [rsp+28h] [rbp-48h] BYREF
  PVOID Buffer; // [rsp+30h] [rbp-40h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-38h] BYREF

  PolicyHandle = 0;
  Buffer = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  pcchLength = 0;
  EnterCriticalSection(&g_SearchListLock);
  if ( g_DevolutionLevelFromForestCached )
    goto LABEL_51;
  g_DevolutionLevelFromForestName = 0;
  if ( !psz || !*psz )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
      goto LABEL_51;
    v12 = 40;
    goto LABEL_50;
  }
  if ( StringCchLengthW(psz, 0x100u, &pcchLength) < 0 )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
      goto LABEL_51;
    v2 = 41;
    v3 = psz;
    goto LABEL_7;
  }
  v4 = pcchLength;
  if ( !pcchLength )
    goto LABEL_46;
  if ( psz[pcchLength - 1] == 46 )
    v4 = pcchLength - 1;
  if ( !v4 )
  {
LABEL_46:
    if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
      goto LABEL_51;
    v12 = 42;
    goto LABEL_50;
  }
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_(1035, 43, WPP_c97ed51ec62b33947f153285c0abcdba_Traceguids);
  v5 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
  if ( v5 < 0 )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      WPP_SF_d(1035, 44, WPP_c97ed51ec62b33947f153285c0abcdba_Traceguids, (unsigned int)v5);
    PolicyHandle = 0;
    goto LABEL_51;
  }
  v6 = LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &Buffer);
  if ( v6 < 0 || (v7 = Buffer) == 0 )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      WPP_SF_d(1035, 45, WPP_c97ed51ec62b33947f153285c0abcdba_Traceguids, (unsigned int)v6);
    goto LABEL_51;
  }
  v8 = *((_WORD *)Buffer + 16) - 2;
  g_DevolutionLevelFromForestCached = 1;
  if ( v8 > 0x1FEu
    || (v9 = (_WORD *)*((_QWORD *)Buffer + 5)) == 0
    || (v10 = (unsigned __int64)*((unsigned __int16 *)Buffer + 16) >> 1, v11 = v10, *((_WORD *)Buffer + 16) == 512)
    && v9[v11 - 1]
    || !*v9 )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
      goto LABEL_51;
    v12 = 46;
    goto LABEL_50;
  }
  memcpy_0(&g_ForestName, v9, *((unsigned __int16 *)Buffer + 16));
  if ( v7[16] < 0x200u )
  {
    if ( v11 >= 256 )
      _report_rangecheckfailure();
    *(wchar_t *)((char *)&g_ForestName + v11 * 2) = 0;
  }
  if ( !v10 )
    goto LABEL_32;
  while ( !*(&g_ForestName + v10 - 1) )
  {
    if ( !--v10 )
      goto LABEL_32;
  }
  if ( *(&g_ForestName + v10 - 1) == 46 && !--v10 )
  {
LABEL_32:
    if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
      goto LABEL_51;
    v12 = 47;
LABEL_50:
    WPP_SF_(1035, v12, WPP_c97ed51ec62b33947f153285c0abcdba_Traceguids);
    goto LABEL_51;
  }
  if ( v10 > v4 || (unsigned int)_o__wcsnicmp(&psz[v4 - v10], &g_ForestName, v10) )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    {
      v2 = 48;
      v3 = &g_ForestName;
LABEL_7:
      WPP_SF_S(1035, v2, WPP_c97ed51ec62b33947f153285c0abcdba_Traceguids, v3);
    }
  }
  else
  {
    g_DevolutionLevelFromForestName = Dns_GetDomainSuffixLevel(&g_ForestName);
    if ( g_DevolutionLevelFromForestName == 1 )
      g_DevolutionLevelFromForestName = 2;
  }
LABEL_51:
  LeaveCriticalSection(&g_SearchListLock);
  if ( Buffer )
    LsaFreeMemory(Buffer);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 49, WPP_c97ed51ec62b33947f153285c0abcdba_Traceguids, (unsigned int)g_DevolutionLevelFromForestName);
  return (unsigned int)g_DevolutionLevelFromForestName;
}

```

## disassembly

```asm
0x180003640  mov     [rsp-28h+arg_8], rbx
0x180003645  mov     [rsp-28h+arg_10], rsi
0x18000364a  push    rbp
0x18000364b  push    rdi
0x18000364c  push    r12
0x18000364e  push    r14
0x180003650  push    r15
0x180003652  mov     rbp, rsp
0x180003655  sub     rsp, 70h
0x180003659  mov     rax, cs:__security_cookie
0x180003660  xor     rax, rsp
0x180003663  mov     [rbp+var_8], rax
0x180003667  xorps   xmm0, xmm0
0x18000366a  xor     r12d, r12d
0x18000366d  mov     rsi, rcx
0x180003670  mov     [rbp+PolicyHandle], r12
0x180003674  lea     rcx, g_SearchListLock; lpCriticalSection
0x18000367b  mov     [rbp+Buffer], r12
0x18000367f  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180003683  mov     [rbp+pcchLength], r12
0x180003687  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18000368b  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000368f  call    cs:__imp_EnterCriticalSection
0x180003696  nop     dword ptr [rax+rax+00h]
0x18000369b  cmp     cs:g_DevolutionLevelFromForestCached, r12d
0x1800036a2  lea     r14, WPP_c97ed51ec62b33947f153285c0abcdba_Traceguids
0x1800036a9  mov     ebx, 40Bh
0x1800036ae  jnz     loc_18000395F
0x1800036b4  mov     cs:g_DevolutionLevelFromForestName, r12d
0x1800036bb  test    rsi, rsi
0x1800036be  jz      loc_180003947
0x1800036c4  cmp     [rsi], r12w
0x1800036c8  jz      loc_180003947
0x1800036ce  lea     r8, [rbp+pcchLength]; pcchLength
0x1800036d2  mov     edx, 100h; cchMax
0x1800036d7  mov     rcx, rsi; psz
0x1800036da  call    StringCchLengthW
0x1800036df  test    eax, eax
0x1800036e1  jns     short loc_180003707
0x1800036e3  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800036ea  jz      loc_18000395F
0x1800036f0  lea     edx, [r12+29h]
0x1800036f5  mov     ecx, ebx
0x1800036f7  mov     r9, rsi
0x1800036fa  mov     r8, r14
0x1800036fd  call    WPP_SF_S
0x180003702  jmp     loc_18000395F
0x180003707  mov     rdi, [rbp+pcchLength]
0x18000370b  test    rdi, rdi
0x18000370e  jz      loc_180003937
0x180003714  mov     eax, 2Eh ; '.'
0x180003719  cmp     [rsi+rdi*2-2], ax
0x18000371e  jnz     short loc_180003723
0x180003720  dec     rdi
0x180003723  test    rdi, rdi
0x180003726  jz      loc_180003937
0x18000372c  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180003733  jz      short loc_180003744
0x180003735  mov     edx, 2Bh ; '+'
0x18000373a  mov     ecx, ebx
0x18000373c  mov     r8, r14
0x18000373f  call    WPP_SF_
0x180003744  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x180003748  mov     r8d, 1; DesiredAccess
0x18000374e  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x180003752  xor     ecx, ecx; SystemName
0x180003754  call    cs:__imp_LsaOpenPolicy
0x18000375b  nop     dword ptr [rax+rax+00h]
0x180003760  test    eax, eax
0x180003762  jns     short loc_180003788
0x180003764  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18000376b  jz      short loc_18000377F
0x18000376d  mov     edx, 2Ch ; ','
0x180003772  mov     ecx, ebx
0x180003774  mov     r9d, eax
0x180003777  mov     r8, r14
0x18000377a  call    WPP_SF_d
0x18000377f  mov     [rbp+PolicyHandle], r12
0x180003783  jmp     loc_18000395F
0x180003788  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18000378c  lea     r8, [rbp+Buffer]; Buffer
0x180003790  mov     edx, 0Ch; InformationClass
0x180003795  call    cs:__imp_LsaQueryInformationPolicy
0x18000379c  nop     dword ptr [rax+rax+00h]
0x1800037a1  test    eax, eax
0x1800037a3  js      loc_18000391A
0x1800037a9  mov     r15, [rbp+Buffer]
0x1800037ad  test    r15, r15
0x1800037b0  jz      loc_18000391A
0x1800037b6  movzx   eax, word ptr [r15+20h]
0x1800037bb  mov     ecx, 1FEh
0x1800037c0  sub     ax, 2
0x1800037c4  mov     cs:g_DevolutionLevelFromForestCached, 1
0x1800037ce  cmp     ax, cx
0x1800037d1  ja      loc_18000390A
0x1800037d7  mov     rdx, [r15+28h]; Src
0x1800037db  test    rdx, rdx
0x1800037de  jz      loc_18000390A
0x1800037e4  movzx   r8d, word ptr [r15+20h]; Size
0x1800037e9  lea     eax, [rcx+2]
0x1800037ec  mov     ebx, r8d
0x1800037ef  shr     rbx, 1
0x1800037f2  lea     r14, [rbx+rbx]
0x1800037f6  cmp     [r15+20h], ax
0x1800037fb  jnz     short loc_180003809
0x1800037fd  cmp     [rdx+r14-2], r12w
0x180003803  jnz     loc_1800038FE
0x180003809  cmp     [rdx], r12w
0x18000380d  jz      loc_1800038FE
0x180003813  lea     rcx, g_ForestName; void *
0x18000381a  call    memcpy_0
0x18000381f  mov     eax, 200h
0x180003824  cmp     [r15+20h], ax
0x180003829  jnb     short loc_180003844
0x18000382b  cmp     r14, rax
0x18000382e  jnb     short loc_18000383E
0x180003830  lea     r15, g_ForestName
0x180003837  mov     [r14+r15], r12w
0x18000383c  jmp     short loc_18000384B
0x18000383e  call    __report_rangecheckfailure
0x180003844  lea     r15, g_ForestName
0x18000384b  test    rbx, rbx
0x18000384e  jz      short loc_18000385E
0x180003850  cmp     [r15+rbx*2-2], r12w
0x180003856  jnz     short loc_180003881
0x180003858  sub     rbx, 1
0x18000385c  jnz     short loc_180003850
0x18000385e  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180003865  jz      loc_18000395F
0x18000386b  mov     edx, 2Fh ; '/'
0x180003870  lea     r8, WPP_c97ed51ec62b33947f153285c0abcdba_Traceguids
0x180003877  mov     ecx, 40Bh
0x18000387c  jmp     loc_18000395A
0x180003881  mov     edx, 2Eh ; '.'
0x180003886  cmp     [r15+rbx*2-2], dx
0x18000388c  jnz     short loc_180003894
0x18000388e  sub     rbx, 1
0x180003892  jz      short loc_18000385E
0x180003894  cmp     rbx, rdi
0x180003897  ja      short loc_1800038DC
0x180003899  sub     rdi, rbx
0x18000389c  mov     r8, rbx
0x18000389f  mov     rdx, r15
0x1800038a2  lea     rcx, [rsi+rdi*2]
0x1800038a6  call    cs:__imp__o__wcsnicmp
0x1800038ad  nop     dword ptr [rax+rax+00h]
0x1800038b2  test    eax, eax
0x1800038b4  jnz     short loc_1800038DC
0x1800038b6  mov     rcx, r15
0x1800038b9  call    Dns_GetDomainSuffixLevel
0x1800038be  mov     cs:g_DevolutionLevelFromForestName, eax
0x1800038c4  cmp     eax, 1
0x1800038c7  jnz     loc_18000395F
0x1800038cd  mov     cs:g_DevolutionLevelFromForestName, 2
0x1800038d7  jmp     loc_18000395F
0x1800038dc  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800038e3  jz      short loc_18000395F
0x1800038e5  mov     edx, 30h ; '0'
0x1800038ea  lea     r8, WPP_c97ed51ec62b33947f153285c0abcdba_Traceguids
0x1800038f1  mov     ecx, 40Bh
0x1800038f6  mov     r9, r15
0x1800038f9  jmp     loc_1800036FD
0x1800038fe  lea     r14, WPP_c97ed51ec62b33947f153285c0abcdba_Traceguids
0x180003905  mov     ebx, 40Bh
0x18000390a  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180003911  jz      short loc_18000395F
0x180003913  mov     edx, 2Eh ; '.'
0x180003918  jmp     short loc_180003955
0x18000391a  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180003921  jz      short loc_18000395F
0x180003923  mov     edx, 2Dh ; '-'
0x180003928  mov     ecx, ebx
0x18000392a  mov     r9d, eax
0x18000392d  mov     r8, r14
0x180003930  call    WPP_SF_d
0x180003935  jmp     short loc_18000395F
0x180003937  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18000393e  jz      short loc_18000395F
0x180003940  mov     edx, 2Ah ; '*'
0x180003945  jmp     short loc_180003955
0x180003947  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18000394e  jz      short loc_18000395F
0x180003950  mov     edx, 28h ; '('
0x180003955  mov     ecx, ebx
0x180003957  mov     r8, r14
0x18000395a  call    WPP_SF_
0x18000395f  lea     rcx, g_SearchListLock; lpCriticalSection
0x180003966  call    cs:__imp_LeaveCriticalSection
0x18000396d  nop     dword ptr [rax+rax+00h]
0x180003972  mov     rcx, [rbp+Buffer]; Buffer
0x180003976  test    rcx, rcx
0x180003979  jz      short loc_180003987
0x18000397b  call    cs:__imp_LsaFreeMemory
0x180003982  nop     dword ptr [rax+rax+00h]
0x180003987  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x18000398b  test    rcx, rcx
0x18000398e  jz      short loc_18000399C
0x180003990  call    cs:__imp_LsaClose
0x180003997  nop     dword ptr [rax+rax+00h]
0x18000399c  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800039a3  jz      short loc_1800039C2
0x1800039a5  mov     r9d, cs:g_DevolutionLevelFromForestName
0x1800039ac  lea     r8, WPP_c97ed51ec62b33947f153285c0abcdba_Traceguids
0x1800039b3  mov     edx, 31h ; '1'
0x1800039b8  mov     ecx, 40Bh
0x1800039bd  call    WPP_SF_d
0x1800039c2  mov     eax, cs:g_DevolutionLevelFromForestName
0x1800039c8  mov     rcx, [rbp+var_8]
0x1800039cc  xor     rcx, rsp; StackCookie
0x1800039cf  call    __security_check_cookie
0x1800039d4  lea     r11, [rsp+70h+var_s0]
0x1800039d9  mov     rbx, [r11+38h]
0x1800039dd  mov     rsi, [r11+40h]
0x1800039e1  mov     rsp, r11
0x1800039e4  pop     r15
0x1800039e6  pop     r14
0x1800039e8  pop     r12
0x1800039ea  pop     rdi
0x1800039eb  pop     rbp
0x1800039ec  retn
```
