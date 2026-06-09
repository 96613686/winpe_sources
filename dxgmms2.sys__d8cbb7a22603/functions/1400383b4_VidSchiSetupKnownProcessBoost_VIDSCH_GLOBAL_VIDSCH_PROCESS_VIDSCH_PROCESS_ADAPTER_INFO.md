# VidSchiSetupKnownProcessBoost(_VIDSCH_GLOBAL *,_VIDSCH_PROCESS *,VIDSCH_PROCESS_ADAPTER_INFO *)

- ea: `0x1400383b4`
- end: `0x140038641`
- name: `?VidSchiSetupKnownProcessBoost@@YAJPEAU_VIDSCH_GLOBAL@@PEAU_VIDSCH_PROCESS@@PEAUVIDSCH_PROCESS_ADAPTER_INFO@@@Z`
- size: `653`
- prototype: `__int64 __fastcall(struct _VIDSCH_GLOBAL *, struct _VIDSCH_PROCESS *, struct VIDSCH_PROCESS_ADAPTER_INFO *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x14011dabc`

## callees

- `0x1400383b4`
- `0x140058f50`
- `0x1400dfcdc`

## import_xrefs

- `ntoskrnl!_strnicmp` at `0x140038419`
- `ntoskrnl!_strnicmp` at `0x14003843a`
- `ntoskrnl!_strnicmp` at `0x140038419`
- `ntoskrnl!_strnicmp` at `0x14003843a`
- `ntoskrnl!RtlCheckTokenMembership` at `0x140038497`
- `ntoskrnl!RtlCheckTokenMembership` at `0x1400385ee`
- `ntoskrnl!RtlCheckTokenMembership` at `0x140038497`
- `ntoskrnl!RtlCheckTokenMembership` at `0x1400385ee`
- `ntoskrnl!SeExports` at `0x14003847c`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400384d4`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400384d4`
- `ntoskrnl!RtlInitializeSid` at `0x140038540`
- `ntoskrnl!RtlInitializeSid` at `0x140038540`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140038551`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14003856b`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140038585`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14003859f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400385b9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400385d3`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140038551`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14003856b`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140038585`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14003859f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400385b9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400385d3`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400383ed`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400383ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038518`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038622`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038518`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038622`

## pseudocode

```c
__int64 __fastcall VidSchiSetupKnownProcessBoost(
        struct _VIDSCH_GLOBAL *a1,
        struct _VIDSCH_PROCESS *a2,
        struct VIDSCH_PROCESS_ADAPTER_INFO *a3)
{
  __int64 v5; // rbx
  const char *v6; // rcx
  char v8; // di
  char v9; // si
  int v10; // ebx
  ULONG v11; // eax
  void *v12; // rax
  void *v13; // rbx
  _BYTE v14[4]; // [rsp+20h] [rbp-30h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+24h] [rbp-2Ch] BYREF
  PVOID P; // [rsp+30h] [rbp-20h] BYREF
  _BYTE v17[4]; // [rsp+38h] [rbp-18h] BYREF
  int v18; // [rsp+3Ch] [rbp-14h]

  if ( !*((_BYTE *)a1 + 7940) )
    return 0;
  v5 = *((_QWORD *)a2 + 332);
  if ( v5 != PsGetCurrentProcess() )
    return 0;
  v6 = (const char *)*((_QWORD *)a2 + 331);
  if ( !v6 )
    return 0;
  if ( !_strnicmp(v6, "audiodg.exe", 0xBu) )
  {
    v8 = 0;
    v9 = 1;
  }
  else
  {
    if ( _strnicmp(*((const char **)a2 + 331), "svchost.exe", 0xBu) )
      return 0;
    v9 = 0;
    v8 = 1;
  }
  v14[0] = 0;
  v10 = RtlCheckTokenMembership(0, SeExports->SeLocalServiceSid, v14);
  if ( v10 >= 0 && v14[0] )
  {
    if ( v8 )
    {
      P = 0;
      v18 = 0;
      v11 = RtlLengthRequiredSid(6u);
      v12 = (void *)PagedPoolZeroedArray<unsigned char,1>::AllocateElements(&P, v11);
      v13 = v12;
      if ( !v12 )
      {
        v10 = -1073741801;
        goto LABEL_15;
      }
      *(_DWORD *)IdentifierAuthority.Value = 0;
      *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
      RtlInitializeSid(v12, &IdentifierAuthority, 6u);
      *RtlSubAuthoritySid(v13, 0) = 80;
      *RtlSubAuthoritySid(v13, 1u) = -379073292;
      *RtlSubAuthoritySid(v13, 2u) = 2104103821;
      *RtlSubAuthoritySid(v13, 3u) = -1247697674;
      *RtlSubAuthoritySid(v13, 4u) = 1811662266;
      *RtlSubAuthoritySid(v13, 5u) = 774708259;
      v10 = RtlCheckTokenMembership(0, v13, v14);
      if ( v10 < 0 || !v14[0] )
      {
        v10 = 0;
LABEL_15:
        if ( P != v17 )
        {
          if ( P )
            ExFreePoolWithTag(P, 0);
        }
        return (unsigned int)v10;
      }
      if ( P != v17 && P )
        ExFreePoolWithTag(P, 0);
    }
    *((_BYTE *)a3 + 5) = v9;
    *((_BYTE *)a3 + 4) = v8;
  }
  else
  {
    return 0;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400383b4  mov     [rsp-18h+arg_0], rbx
0x1400383b9  mov     [rsp-18h+arg_18], rsi
0x1400383be  push    rbp
0x1400383bf  push    rdi
0x1400383c0  push    r14
0x1400383c2  mov     rbp, rsp
0x1400383c5  sub     rsp, 50h
0x1400383c9  mov     rax, cs:__security_cookie
0x1400383d0  xor     rax, rsp
0x1400383d3  mov     [rbp+var_10], rax
0x1400383d7  cmp     byte ptr [rcx+1F04h], 0
0x1400383de  mov     r14, r8
0x1400383e1  mov     rdi, rdx
0x1400383e4  jz      short loc_14003844A
0x1400383e6  mov     rbx, [rdx+0A60h]
0x1400383ed  call    cs:__imp_PsGetCurrentProcess
0x1400383f4  nop     dword ptr [rax+rax+00h]
0x1400383f9  cmp     rbx, rax
0x1400383fc  jnz     short loc_14003844A
0x1400383fe  mov     rcx, [rdi+0A58h]; Str1
0x140038405  test    rcx, rcx
0x140038408  jz      short loc_14003844A
0x14003840a  mov     ebx, 0Bh
0x14003840f  lea     rdx, Str2; "audiodg.exe"
0x140038416  mov     r8d, ebx; MaxCount
0x140038419  call    cs:__imp__strnicmp
0x140038420  nop     dword ptr [rax+rax+00h]
0x140038425  test    eax, eax
0x140038427  jz      short loc_14003846E
0x140038429  mov     rcx, [rdi+0A58h]; Str1
0x140038430  lea     rdx, aSvchostExe; "svchost.exe"
0x140038437  mov     r8d, ebx; MaxCount
0x14003843a  call    cs:__imp__strnicmp
0x140038441  nop     dword ptr [rax+rax+00h]
0x140038446  test    eax, eax
0x140038448  jz      short loc_140038476
0x14003844a  xor     eax, eax
0x14003844c  mov     rcx, [rbp+var_10]
0x140038450  xor     rcx, rsp; StackCookie
0x140038453  call    __security_check_cookie
0x140038458  lea     r11, [rsp+50h+var_s0]
0x14003845d  mov     rbx, [r11+20h]
0x140038461  mov     rsi, [r11+38h]
0x140038465  mov     rsp, r11
0x140038468  pop     r14
0x14003846a  pop     rdi
0x14003846b  pop     rbp
0x14003846c  retn
0x14003846e  xor     dil, dil
0x140038471  mov     sil, 1
0x140038474  jmp     short loc_14003847C
0x140038476  xor     sil, sil
0x140038479  mov     dil, 1
0x14003847c  mov     rax, cs:__imp_SeExports
0x140038483  lea     r8, [rbp+var_30]
0x140038487  mov     [rbp+var_30], 0
0x14003848b  xor     ecx, ecx
0x14003848d  mov     rdx, [rax]
0x140038490  mov     rdx, [rdx+180h]
0x140038497  call    cs:__imp_RtlCheckTokenMembership
0x14003849e  nop     dword ptr [rax+rax+00h]
0x1400384a3  mov     ebx, eax
0x1400384a5  test    eax, eax
0x1400384a7  js      loc_140038638
0x1400384ad  cmp     [rbp+var_30], 0
0x1400384b1  jz      loc_140038638
0x1400384b7  test    dil, dil
0x1400384ba  jz      loc_14003862E
0x1400384c0  mov     ecx, 6; SubAuthorityCount
0x1400384c5  mov     [rbp+P], 0
0x1400384cd  mov     [rbp+var_14], 0
0x1400384d4  call    cs:__imp_RtlLengthRequiredSid
0x1400384db  nop     dword ptr [rax+rax+00h]
0x1400384e0  mov     edx, eax
0x1400384e2  lea     rcx, [rbp+P]
0x1400384e6  call    ?AllocateElements@?$PagedPoolZeroedArray@E$00@@QEAAPEAEI@Z; PagedPoolZeroedArray<uchar,1>::AllocateElements(uint)
0x1400384eb  mov     rbx, rax
0x1400384ee  test    rax, rax
0x1400384f1  jnz     short loc_140038529
0x1400384f3  mov     ebx, 0C0000017h
0x1400384f8  jmp     short loc_1400384FC
0x1400384fa  xor     ebx, ebx
0x1400384fc  mov     rcx, [rbp+P]; P
0x140038500  lea     rax, [rbp+var_18]
0x140038504  cmp     rcx, rax
0x140038507  jz      loc_14003863A
0x14003850d  test    rcx, rcx
0x140038510  jz      loc_14003863A
0x140038516  xor     edx, edx; Tag
0x140038518  call    cs:__imp_ExFreePoolWithTag
0x14003851f  nop     dword ptr [rax+rax+00h]
0x140038524  jmp     loc_14003863A
0x140038529  mov     r8b, 6; SubAuthorityCount
0x14003852c  mov     dword ptr [rbp+IdentifierAuthority.Value], 0
0x140038533  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x140038537  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x14003853d  mov     rcx, rbx; Sid
0x140038540  call    cs:__imp_RtlInitializeSid
0x140038547  nop     dword ptr [rax+rax+00h]
0x14003854c  xor     edx, edx; SubAuthority
0x14003854e  mov     rcx, rbx; Sid
0x140038551  call    cs:__imp_RtlSubAuthoritySid
0x140038558  nop     dword ptr [rax+rax+00h]
0x14003855d  mov     edx, 1; SubAuthority
0x140038562  mov     rcx, rbx; Sid
0x140038565  mov     dword ptr [rax], 50h ; 'P'
0x14003856b  call    cs:__imp_RtlSubAuthoritySid
0x140038572  nop     dword ptr [rax+rax+00h]
0x140038577  mov     edx, 2; SubAuthority
0x14003857c  mov     rcx, rbx; Sid
0x14003857f  mov     dword ptr [rax], 0E967CCF4h
0x140038585  call    cs:__imp_RtlSubAuthoritySid
0x14003858c  nop     dword ptr [rax+rax+00h]
0x140038591  mov     edx, 3; SubAuthority
0x140038596  mov     rcx, rbx; Sid
0x140038599  mov     dword ptr [rax], 7D6A138Dh
0x14003859f  call    cs:__imp_RtlSubAuthoritySid
0x1400385a6  nop     dword ptr [rax+rax+00h]
0x1400385ab  mov     edx, 4; SubAuthority
0x1400385b0  mov     rcx, rbx; Sid
0x1400385b3  mov     dword ptr [rax], 0B5A1A4F6h
0x1400385b9  call    cs:__imp_RtlSubAuthoritySid
0x1400385c0  nop     dword ptr [rax+rax+00h]
0x1400385c5  mov     edx, 5; SubAuthority
0x1400385ca  mov     rcx, rbx; Sid
0x1400385cd  mov     dword ptr [rax], 6BFBC5BAh
0x1400385d3  call    cs:__imp_RtlSubAuthoritySid
0x1400385da  nop     dword ptr [rax+rax+00h]
0x1400385df  lea     r8, [rbp+var_30]
0x1400385e3  mov     rdx, rbx
0x1400385e6  xor     ecx, ecx
0x1400385e8  mov     dword ptr [rax], 2E2D1C23h
0x1400385ee  call    cs:__imp_RtlCheckTokenMembership
0x1400385f5  nop     dword ptr [rax+rax+00h]
0x1400385fa  mov     ebx, eax
0x1400385fc  test    eax, eax
0x1400385fe  js      loc_1400384FA
0x140038604  cmp     [rbp+var_30], 0
0x140038608  jz      loc_1400384FA
0x14003860e  mov     rcx, [rbp+P]; P
0x140038612  lea     rax, [rbp+var_18]
0x140038616  cmp     rcx, rax
0x140038619  jz      short loc_14003862E
0x14003861b  test    rcx, rcx
0x14003861e  jz      short loc_14003862E
0x140038620  xor     edx, edx; Tag
0x140038622  call    cs:__imp_ExFreePoolWithTag
0x140038629  nop     dword ptr [rax+rax+00h]
0x14003862e  mov     [r14+5], sil
0x140038632  mov     [r14+4], dil
0x140038636  jmp     short loc_14003863A
0x140038638  xor     ebx, ebx
0x14003863a  mov     eax, ebx
0x14003863c  jmp     loc_14003844C
```
