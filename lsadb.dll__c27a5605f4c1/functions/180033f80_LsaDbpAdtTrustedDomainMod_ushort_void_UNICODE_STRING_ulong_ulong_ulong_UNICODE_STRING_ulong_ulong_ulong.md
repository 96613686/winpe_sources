# LsaDbpAdtTrustedDomainMod(ushort,void *,_UNICODE_STRING *,ulong,ulong,ulong,_UNICODE_STRING *,ulong,ulong,ulong)

- ea: `0x180033f80`
- end: `0x180034202`
- name: `?LsaDbpAdtTrustedDomainMod@@YAJGPEAXPEAU_UNICODE_STRING@@KKK1KKK@Z`
- size: `642`
- prototype: `int(unsigned __int16, void *, struct _UNICODE_STRING *, unsigned int, unsigned int, unsigned int, struct _UNICODE_STRING *, unsigned int, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000e9f0`
- `0x18000fb10`

## callees

- `0x180001670`
- `0x180001fb8`
- `0x180002234`
- `0x180033f80`

## import_xrefs

- `LSASRV!LsapFreeLsaHeap` at `0x1800341c8`
- `LSASRV!LsapFreeLsaHeap` at `0x1800341c8`
- `LSASRV!LsapAdtWriteLog` at `0x1800341b6`
- `LSASRV!LsapAdtWriteLog` at `0x1800341b6`
- `LSASRV!LsapAuditFailed` at `0x1800341d4`
- `LSASRV!LsapAuditFailed` at `0x1800341d4`
- `LSASRV!LsapQueryClientInfo` at `0x180034012`
- `LSASRV!LsapQueryClientInfo` at `0x180034012`
- `ntdll!RtlLengthSid` at `0x18003409e`
- `ntdll!RtlLengthSid` at `0x1800340ba`
- `ntdll!RtlLengthSid` at `0x18003413d`
- `ntdll!RtlLengthSid` at `0x18003414c`
- `ntdll!RtlLengthSid` at `0x18003409e`
- `ntdll!RtlLengthSid` at `0x1800340ba`
- `ntdll!RtlLengthSid` at `0x18003413d`
- `ntdll!RtlLengthSid` at `0x18003414c`
- `ntdll!RtlEqualUnicodeString` at `0x180034114`
- `ntdll!RtlEqualUnicodeString` at `0x180034114`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledByLogonId` at `0x180034046`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledByLogonId` at `0x180034046`

## pseudocode

```c
__int64 __fastcall LsaDbpAdtTrustedDomainMod(
        __int64 a1,
        void *a2,
        struct _UNICODE_STRING *a3,
        __int64 a4,
        unsigned int a5,
        unsigned int a6,
        struct _UNICODE_STRING *String2,
        unsigned int a8,
        unsigned int a9,
        unsigned int a10)
{
  int v12; // ebx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  int Length; // eax
  ULONG v17; // eax
  _BYTE v19[8]; // [rsp+20h] [rbp-E0h] BYREF
  PSID *v20; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v21[2]; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD v22[7]; // [rsp+40h] [rbp-C0h] BYREF
  ULONG v23; // [rsp+5Ch] [rbp-A4h]
  __int16 *v24; // [rsp+70h] [rbp-90h]
  int v25; // [rsp+78h] [rbp-88h]
  int v26; // [rsp+7Ch] [rbp-84h]
  struct _UNICODE_STRING *v27; // [rsp+90h] [rbp-70h]
  int v28; // [rsp+98h] [rbp-68h]
  int v29; // [rsp+9Ch] [rbp-64h]
  __int64 v30; // [rsp+A0h] [rbp-60h]
  int v31; // [rsp+B8h] [rbp-48h]
  int v32; // [rsp+BCh] [rbp-44h]
  struct _UNICODE_STRING *v33; // [rsp+D0h] [rbp-30h]
  int v34; // [rsp+D8h] [rbp-28h]
  ULONG v35; // [rsp+DCh] [rbp-24h]
  __int16 *v36; // [rsp+F0h] [rbp-10h]
  int v37; // [rsp+F8h] [rbp-8h]
  int v38; // [rsp+FCh] [rbp-4h]
  __int64 v39; // [rsp+100h] [rbp+0h]
  int v40; // [rsp+118h] [rbp+18h]
  int v41; // [rsp+11Ch] [rbp+1Ch]
  __int64 v42; // [rsp+120h] [rbp+20h]
  int v43; // [rsp+138h] [rbp+38h]
  int v44; // [rsp+13Ch] [rbp+3Ch]
  __int64 v45; // [rsp+140h] [rbp+40h]
  int v46; // [rsp+158h] [rbp+58h]
  int v47; // [rsp+15Ch] [rbp+5Ch]
  __int64 v48; // [rsp+160h] [rbp+60h]

  v21[0] = 0;
  v20 = 0;
  memset_0(v22, 0, 0x418u);
  v19[0] = 0;
  if ( a3 && a3->MaximumLength < a3->Length || String2 && String2->MaximumLength < String2->Length )
  {
    v12 = -1073741811;
LABEL_26:
    LsapAuditFailed((unsigned int)v12);
    return (unsigned int)v12;
  }
  v12 = LsapQueryClientInfo(&v20, v21);
  if ( v12 >= 0 )
  {
    if ( !(unsigned __int8)IsLsapAdtAuditingEnabledByLogonIdPresent(v14, v13, v15)
      || (v12 = LsapAdtAuditingEnabledByLogonId(141, v21, 8, v19), v12 >= 0) )
    {
      if ( v19[0] )
      {
        v22[0] = 6;
        v22[4] = 524429;
        v22[1] = 4716;
        v22[2] = 9;
        v22[6] = 4;
        if ( *v20 )
        {
          v23 = RtlLengthSid(*v20);
          v24 = (__int16 *)*v20;
        }
        else
        {
          v23 = RtlLengthSid(&AdtpNullSid);
          v24 = &AdtpNullSid;
        }
        v25 = 1;
        v26 = LsaDbpSubsystemName.Length + 16;
        v27 = &LsaDbpSubsystemName;
        v30 = v21[0];
        v28 = 5;
        v29 = 8;
        if ( a3 && String2 && !RtlEqualUnicodeString(a3, String2, 1u) )
        {
          Length = String2->Length;
          v31 = 1;
          v32 = Length + 16;
          v33 = String2;
        }
        v34 = 4;
        if ( a2 )
        {
          v17 = RtlLengthSid(a2);
          v36 = (__int16 *)a2;
        }
        else
        {
          v17 = RtlLengthSid(&AdtpNullSid);
          v36 = &AdtpNullSid;
        }
        v35 = v17;
        v37 = 27;
        v40 = 27;
        v43 = 27;
        v39 = a8;
        v42 = a9;
        v38 = 4;
        v41 = 4;
        v44 = 4;
        v45 = a10;
        if ( a6 != a10 )
        {
          v46 = 21;
          v47 = 4;
          v48 = 1796LL - ((a10 & 4) != 0);
        }
        v12 = LsapAdtWriteLog(v22);
      }
    }
  }
  if ( v20 )
    LsapFreeLsaHeap(v20, v13, v15);
  if ( v12 < 0 )
    goto LABEL_26;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180033f80  mov     [rsp-8+arg_0], rbx
0x180033f85  push    rbp
0x180033f86  push    rsi
0x180033f87  push    rdi
0x180033f88  push    r12
0x180033f8a  push    r14
0x180033f8c  lea     rbp, [rsp-370h]
0x180033f94  sub     rsp, 470h
0x180033f9b  mov     rax, cs:__security_cookie
0x180033fa2  xor     rax, rsp
0x180033fa5  mov     [rbp+390h+var_30], rax
0x180033fac  mov     rdi, [rbp+390h+String2]
0x180033fb3  lea     rcx, [rsp+490h+var_450]; void *
0x180033fb8  mov     rsi, r8
0x180033fbb  mov     [rsp+490h+var_460], 0
0x180033fc4  mov     r14, rdx
0x180033fc7  mov     [rsp+490h+var_468], 0
0x180033fd0  xor     edx, edx; Val
0x180033fd2  mov     r8d, 418h; Size
0x180033fd8  call    memset_0
0x180033fdd  mov     [rsp+490h+var_470], 0
0x180033fe2  test    rsi, rsi
0x180033fe5  jz      short loc_180033FF0
0x180033fe7  movzx   eax, word ptr [rsi]
0x180033fea  cmp     [rsi+2], ax
0x180033fee  jb      short loc_180033FFE
0x180033ff0  test    rdi, rdi
0x180033ff3  jz      short loc_180034008
0x180033ff5  movzx   eax, word ptr [rdi]
0x180033ff8  cmp     [rdi+2], ax
0x180033ffc  jnb     short loc_180034008
0x180033ffe  mov     ebx, 0C000000Dh
0x180034003  jmp     loc_1800341D2
0x180034008  lea     rdx, [rsp+490h+var_460]
0x18003400d  lea     rcx, [rsp+490h+var_468]
0x180034012  call    cs:__imp_LsapQueryClientInfo
0x180034018  mov     ebx, eax
0x18003401a  test    eax, eax
0x18003401c  js      loc_1800341BE
0x180034022  call    IsLsapAdtAuditingEnabledByLogonIdPresent
0x180034027  mov     ecx, 8
0x18003402c  mov     r12d, 8Dh
0x180034032  test    al, al
0x180034034  jz      short loc_180034056
0x180034036  mov     r8d, ecx
0x180034039  lea     r9, [rsp+490h+var_470]
0x18003403e  mov     ecx, r12d
0x180034041  lea     rdx, [rsp+490h+var_460]
0x180034046  call    cs:__imp_LsapAdtAuditingEnabledByLogonId
0x18003404c  mov     ebx, eax
0x18003404e  test    eax, eax
0x180034050  js      loc_1800341BE
0x180034056  cmp     [rsp+490h+var_470], 0
0x18003405b  jz      loc_1800341BE
0x180034061  mov     rax, [rsp+490h+var_468]
0x180034066  lea     r12, AdtpNullSid
0x18003406d  mov     ebx, 4
0x180034072  mov     [rsp+490h+var_450], 6
0x18003407a  mov     [rsp+490h+var_440], 8008Dh
0x180034082  mov     [rsp+490h+var_44C], 126Ch
0x18003408a  mov     [rsp+490h+var_448], 9
0x180034092  mov     [rsp+490h+var_438], ebx
0x180034096  mov     rcx, [rax]; Sid
0x180034099  test    rcx, rcx
0x18003409c  jz      short loc_1800340B7
0x18003409e  call    cs:__imp_RtlLengthSid
0x1800340a4  mov     [rsp+490h+var_434], eax
0x1800340a8  mov     rax, [rsp+490h+var_468]
0x1800340ad  mov     rcx, [rax]
0x1800340b0  mov     [rsp+490h+var_420], rcx
0x1800340b5  jmp     short loc_1800340C9
0x1800340b7  mov     rcx, r12; Sid
0x1800340ba  call    cs:__imp_RtlLengthSid
0x1800340c0  mov     [rsp+490h+var_434], eax
0x1800340c4  mov     [rsp+490h+var_420], r12
0x1800340c9  movzx   eax, cs:?LsaDbpSubsystemName@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING LsaDbpSubsystemName ...
0x1800340d0  add     eax, 10h
0x1800340d3  mov     [rsp+490h+var_418], 1
0x1800340db  mov     [rsp+490h+var_414], eax
0x1800340df  lea     rax, ?LsaDbpSubsystemName@@3U_UNICODE_STRING@@A; _UNICODE_STRING LsaDbpSubsystemName
0x1800340e6  mov     [rbp+390h+var_400], rax
0x1800340ea  mov     rax, [rsp+490h+var_460]
0x1800340ef  mov     [rbp+390h+var_3F0], rax
0x1800340f3  mov     [rbp+390h+var_3F8], 5
0x1800340fa  mov     [rbp+390h+var_3F4], 8
0x180034101  test    rsi, rsi
0x180034104  jz      short loc_180034132
0x180034106  test    rdi, rdi
0x180034109  jz      short loc_180034132
0x18003410b  mov     r8b, 1; CaseInsensitive
0x18003410e  mov     rdx, rdi; String2
0x180034111  mov     rcx, rsi; String1
0x180034114  call    cs:__imp_RtlEqualUnicodeString
0x18003411a  test    al, al
0x18003411c  jnz     short loc_180034132
0x18003411e  movzx   eax, word ptr [rdi]
0x180034121  add     eax, 10h
0x180034124  mov     [rbp+390h+var_3D8], 1
0x18003412b  mov     [rbp+390h+var_3D4], eax
0x18003412e  mov     [rbp+390h+var_3C0], rdi
0x180034132  mov     [rbp+390h+var_3B8], ebx
0x180034135  test    r14, r14
0x180034138  jz      short loc_180034149
0x18003413a  mov     rcx, r14; Sid
0x18003413d  call    cs:__imp_RtlLengthSid
0x180034143  mov     [rbp+390h+var_3A0], r14
0x180034147  jmp     short loc_180034156
0x180034149  mov     rcx, r12; Sid
0x18003414c  call    cs:__imp_RtlLengthSid
0x180034152  mov     [rbp+390h+var_3A0], r12
0x180034156  mov     ecx, 1Bh
0x18003415b  mov     [rbp+390h+var_3B4], eax
0x18003415e  mov     eax, [rbp+390h+arg_38]
0x180034164  mov     [rbp+390h+var_398], ecx
0x180034167  mov     [rbp+390h+var_378], ecx
0x18003416a  mov     [rbp+390h+var_358], ecx
0x18003416d  mov     ecx, [rbp+390h+arg_48]
0x180034173  mov     [rbp+390h+var_390], rax
0x180034177  mov     eax, [rbp+390h+arg_40]
0x18003417d  mov     [rbp+390h+var_370], rax
0x180034181  mov     [rbp+390h+var_394], ebx
0x180034184  mov     [rbp+390h+var_374], ebx
0x180034187  mov     [rbp+390h+var_354], ebx
0x18003418a  mov     [rbp+390h+var_350], rcx
0x18003418e  cmp     [rbp+390h+arg_28], ecx
0x180034194  jz      short loc_1800341B1
0x180034196  and     cl, bl
0x180034198  mov     [rbp+390h+var_338], 15h
0x18003419f  neg     cl
0x1800341a1  mov     [rbp+390h+var_334], ebx
0x1800341a4  sbb     rax, rax
0x1800341a7  add     rax, 704h
0x1800341ad  mov     [rbp+390h+var_330], rax
0x1800341b1  lea     rcx, [rsp+490h+var_450]
0x1800341b6  call    cs:__imp_LsapAdtWriteLog
0x1800341bc  mov     ebx, eax
0x1800341be  mov     rcx, [rsp+490h+var_468]
0x1800341c3  test    rcx, rcx
0x1800341c6  jz      short loc_1800341CE
0x1800341c8  call    cs:__imp_LsapFreeLsaHeap
0x1800341ce  test    ebx, ebx
0x1800341d0  jns     short loc_1800341DA
0x1800341d2  mov     ecx, ebx
0x1800341d4  call    cs:__imp_LsapAuditFailed
0x1800341da  mov     eax, ebx
0x1800341dc  mov     rcx, [rbp+390h+var_30]
0x1800341e3  xor     rcx, rsp; StackCookie
0x1800341e6  call    __security_check_cookie
0x1800341eb  mov     rbx, [rsp+490h+arg_0]
0x1800341f3  add     rsp, 470h
0x1800341fa  pop     r14
0x1800341fc  pop     r12
0x1800341fe  pop     rdi
0x1800341ff  pop     rsi
0x180034200  pop     rbp
0x180034201  retn
```
