# VfTriageSystem

- ea: `0x140c83f70`
- end: `0x140c84312`
- name: `VfTriageSystem`
- size: `930`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x140c83518`

## callees

- `0x1402a2f90`
- `0x140c83f70`
- `0x140c84318`
- `0x140c843b8`
- `0x140c8448c`
- `0x140c84530`
- `0x140ca62f0`
- `0x140ca63d0`

## string_xrefs

- `0x140c841bf`: `CRASH TRIAGE: triage disabled due to invalid registry rules.\n`
- `0x140c8401d`: `CRASH TRIAGE: null loader extension.\n`
- `0x140c84031`: `CRASH TRIAGE: unexpected loader extension size.\n`
- `0x140c83f89`: `CRASH TRIAGE: verifier triage global/registry settings %X \n`

## pseudocode

```c
__int64 __fastcall VfTriageSystem(__int64 a1)
{
  unsigned int v2; // ebx
  int v3; // r14d
  int v4; // r9d
  __int64 v5; // rax
  __int64 v6; // r15
  unsigned int v7; // esi
  __int64 v8; // rbx
  __int64 v9; // rbx
  __int64 v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // rcx
  _DWORD *TriageRule; // rdi
  __int64 *v14; // rbx
  const CHAR *v15; // r8
  _BYTE v17[40]; // [rsp+40h] [rbp-30h] BYREF

  DbgPrintEx(0x5Du, 3u, "CRASH TRIAGE: verifier triage global/registry settings %X \n", ViVerifyTriage);
  if ( MmVerifyDriverLevel != -1 || ViVerifyAllDrivers )
  {
    DbgPrintEx(0x5Du, 3u, "CRASH TRIAGE: driver verifier settings present.\n");
    return 0;
  }
  if ( ViVerifyTriage == -1 )
  {
    DbgPrintEx(0x5Du, 3u, "CRASH TRIAGE: triage skipped because it is not enabled by default.\n");
  }
  else if ( ViVerifyTriage )
  {
    v2 = 0;
    v3 = 1;
    if ( ViVerifyTriage < 0 )
    {
      v2 = (unsigned __int16)ViVerifyTriage;
      v4 = (unsigned __int16)ViVerifyTriage;
      ViVerifyTriage = 1;
      DbgPrintEx(0x5Du, 3u, "CRASH TRIAGE: simulated crash code %X.\n", v4);
    }
    v5 = *(_QWORD *)(a1 + 240);
    if ( v5 )
    {
      if ( *(_DWORD *)v5 >= 0x1150u )
      {
        v6 = *(_QWORD *)(v5 + 40);
        if ( (int)TriageGetBugcheckData(
                    v6,
                    (unsigned int)v17,
                    (unsigned int)&v17[8],
                    (unsigned int)&v17[16],
                    (__int64)&v17[24],
                    (__int64)&v17[32]) >= 0 )
        {
          v7 = *(_DWORD *)v17;
          DbgPrintEx(0x5Du, 3u, "CRASH TRIAGE: a real crash happened.\n");
        }
        else
        {
          if ( !v2 )
          {
            DbgPrintEx(0x5Du, 3u, "CRASH TRIAGE: standard retail exit point.\n");
            return 0;
          }
          v7 = v2;
          v3 = 0;
          *(_QWORD *)v17 = v2;
          *(__m128i *)&v17[8] = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
          *(_OWORD *)&v17[24] = *(_OWORD *)&v17[8];
          DbgPrintEx(0x5Du, 3u, "CRASH TRIAGE: a fake crash will be simulated.\n");
        }
        v8 = *(_QWORD *)&v17[32];
        DbgPrintEx(
          0x5Du,
          3u,
          "CRASH TRIAGE: previous crash was %Ix %Ix %Ix %Ix %Ix.\n",
          v7,
          *(_DWORD *)&v17[8],
          *(_DWORD *)&v17[16],
          *(_DWORD *)&v17[24],
          *(_DWORD *)&v17[32]);
        qword_140EF2B20 = v8;
        ViTriageCrashData = *(_OWORD *)v17;
        xmmword_140EF2B10 = *(_OWORD *)&v17[16];
        if ( v3 )
        {
          v9 = *(_QWORD *)(a1 + 240);
          if ( v9 )
          {
            if ( *(_DWORD *)v9 >= 0x1150u )
            {
              v10 = *(_QWORD *)(v9 + 40);
              if ( (int)TriageGetBugcheckData(
                          v10,
                          (unsigned int)v17,
                          (unsigned int)&v17[8],
                          (unsigned int)&v17[16],
                          (__int64)&v17[24],
                          (__int64)&v17[32]) >= 0 )
              {
                if ( (unsigned __int8)TriagepVerifyDump(v10) )
                {
                  v11 = v10 + (unsigned int)TriageImagePageSize;
                  if ( v11 )
                  {
                    v12 = v10 + *(unsigned int *)(v11 + 20);
                    if ( v12 )
                    {
                      if ( *(_DWORD *)(v12 + 12) )
                      {
                        DbgPrintEx(
                          0x5Du,
                          3u,
                          "CRASH TRIAGE: triage skipped because it was active in previous crash or server system.\n");
                        return 0;
                      }
                    }
                  }
                }
              }
            }
          }
          if ( !(unsigned int)ViTriageSameDriversFromDump(a1, v6) )
          {
            DbgPrintEx(0x5Du, 3u, "CRASH TRIAGE: some drivers changed from previous crash.\n");
            return 0;
          }
        }
        if ( (unsigned int)ViValidateTriageRules(ViVerifyTriageRules, (unsigned int)ViVerifyTriageRulesSize) )
        {
          if ( (unsigned int)ViValidateTriageRules(ViInternalTriageRules, 48) )
          {
            TriageRule = (_DWORD *)ViFindTriageRule(ViVerifyTriageRules, (unsigned int)ViVerifyTriageRulesSize, v7);
            if ( TriageRule || (TriageRule = (_DWORD *)ViFindTriageRule(ViInternalTriageRules, 48, v7)) != 0 )
            {
              v14 = 0;
              if ( *TriageRule < 0x80000u )
              {
                v14 = ViVerifyTriageRules;
                while ( v14 < (__int64 *)((char *)ViVerifyTriageRules + (unsigned int)ViVerifyTriageRulesSize) )
                {
                  if ( (*(_DWORD *)v14 & 0x70000) == 0 )
                  {
                    v15 = "CRASH TRIAGE: zeroed rules structure (hit an invalid type rule).\n";
                    goto LABEL_46;
                  }
                  if ( (HIWORD(*(_DWORD *)v14) & 7) == 1 )
                  {
                    v14 = (__int64 *)((char *)v14 + ((unsigned __int64)*(unsigned int *)v14 >> 19) + 8);
                  }
                  else if ( (HIWORD(*(_DWORD *)v14) & 7) == 2 )
                  {
                    v15 = "CRASH TRIAGE: found a `targets' rule.\n";
                    goto LABEL_47;
                  }
                }
                v15 = "CRASH TRIAGE: no `targets' rule found.\n";
LABEL_46:
                v14 = 0;
LABEL_47:
                DbgPrintEx(0x5Du, 3u, v15);
                if ( v14 )
                  DbgPrintEx(0x5Du, 3u, "CRASH TRIAGE: no `targets' rule found.\n");
              }
              if ( TriageRule[1] )
              {
                ViMakeVerifierSettings(TriageRule, v14);
                DbgPrintEx(0x5Du, 3u, "CRASH TRIAGE: triage enabled!\n");
                return 1;
              }
              DbgPrintEx(0x5Du, 3u, "CRASH TRIAGE: triage disabled due to rule with null features.\n");
            }
            else
            {
              DbgPrintEx(0x5Du, 3u, "CRASH TRIAGE: crash code %Ix will not be triaged.\n", v7);
            }
          }
          else
          {
            DbgPrintEx(0x5Du, 3u, "CRASH TRIAGE: triage disabled due to invalid internal rules!\n");
          }
        }
        else
        {
          DbgPrintEx(0x5Du, 3u, "CRASH TRIAGE: triage disabled due to invalid registry rules.\n");
        }
      }
      else
      {
        DbgPrintEx(0x5Du, 3u, "CRASH TRIAGE: unexpected loader extension size.\n");
      }
    }
    else
    {
      DbgPrintEx(0x5Du, 3u, "CRASH TRIAGE: null loader extension.\n");
    }
  }
  else
  {
    DbgPrintEx(0x5Du, 3u, "CRASH TRIAGE: triage skipped because it is disabled explicitely.\n");
  }
  return 0;
}

```

## disassembly

```asm
0x140c83f70  push    rbp
0x140c83f72  push    rbx
0x140c83f73  push    rsi
0x140c83f74  push    rdi
0x140c83f75  push    r13
0x140c83f77  push    r14
0x140c83f79  push    r15
0x140c83f7b  mov     rbp, rsp
0x140c83f7e  sub     rsp, 70h
0x140c83f82  mov     r9d, cs:ViVerifyTriage
0x140c83f89  lea     r8, aCrashTriageVer; "CRASH TRIAGE: verifier triage global/re"...
0x140c83f90  mov     r13d, 3
0x140c83f96  mov     rdi, rcx
0x140c83f99  mov     edx, r13d; Level
0x140c83f9c  lea     esi, [r13+5Ah]
0x140c83fa0  mov     ecx, esi; ComponentId
0x140c83fa2  call    DbgPrintEx
0x140c83fa7  or      ecx, 0FFFFFFFFh
0x140c83faa  cmp     cs:MmVerifyDriverLevel, ecx
0x140c83fb0  jnz     loc_140C842EF
0x140c83fb6  cmp     cs:ViVerifyAllDrivers, 0
0x140c83fbd  jnz     loc_140C842EF
0x140c83fc3  mov     eax, cs:ViVerifyTriage
0x140c83fc9  cmp     eax, ecx
0x140c83fcb  jnz     short loc_140C83FD9
0x140c83fcd  lea     r8, aCrashTriageTri; "CRASH TRIAGE: triage skipped because it"...
0x140c83fd4  jmp     loc_140C842F6
0x140c83fd9  test    eax, eax
0x140c83fdb  jnz     short loc_140C83FE9
0x140c83fdd  lea     r8, aCrashTriageTri_5; "CRASH TRIAGE: triage skipped because it"...
0x140c83fe4  jmp     loc_140C842F6
0x140c83fe9  xor     ebx, ebx
0x140c83feb  lea     r14d, [rbx+1]
0x140c83fef  test    eax, eax
0x140c83ff1  jns     short loc_140C84011
0x140c83ff3  movzx   ebx, ax
0x140c83ff6  lea     r8, aCrashTriageSim; "CRASH TRIAGE: simulated crash code %X."...
0x140c83ffd  mov     r9d, ebx
0x140c84000  mov     cs:ViVerifyTriage, r14d
0x140c84007  mov     edx, r13d; Level
0x140c8400a  mov     ecx, esi; ComponentId
0x140c8400c  call    DbgPrintEx
0x140c84011  mov     rax, [rdi+0F0h]
0x140c84018  test    rax, rax
0x140c8401b  jnz     short loc_140C84029
0x140c8401d  lea     r8, aCrashTriageNul; "CRASH TRIAGE: null loader extension.\n"
0x140c84024  jmp     loc_140C842F6
0x140c84029  cmp     dword ptr [rax], 1150h
0x140c8402f  jnb     short loc_140C8403D
0x140c84031  lea     r8, aCrashTriageUne; "CRASH TRIAGE: unexpected loader extensi"...
0x140c84038  jmp     loc_140C842F6
0x140c8403d  mov     r15, [rax+28h]
0x140c84041  lea     r9, [rbp+var_20]
0x140c84045  lea     rax, [rbp+var_18+8]
0x140c84049  mov     rcx, r15
0x140c8404c  mov     [rsp+70h+var_48], rax
0x140c84051  lea     r8, [rbp+var_30+8]
0x140c84055  lea     rax, [rbp+var_18]
0x140c84059  lea     rdx, [rbp+var_30]
0x140c8405d  mov     [rsp+70h+var_50], rax
0x140c84062  call    TriageGetBugcheckData
0x140c84067  test    eax, eax
0x140c84069  jns     short loc_140C8409D
0x140c8406b  test    ebx, ebx
0x140c8406d  jnz     short loc_140C8407B
0x140c8406f  lea     r8, aCrashTriageSta; "CRASH TRIAGE: standard retail exit poin"...
0x140c84076  jmp     loc_140C842F6
0x140c8407b  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140c84083  lea     r8, aCrashTriageAFa; "CRASH TRIAGE: a fake crash will be simu"...
0x140c8408a  mov     esi, ebx
0x140c8408c  xor     r14d, r14d
0x140c8408f  mov     qword ptr [rbp+var_30], rsi
0x140c84093  movups  [rbp+var_30+8], xmm0
0x140c84097  movups  [rbp+var_18], xmm0
0x140c8409b  jmp     short loc_140C840A8
0x140c8409d  mov     rsi, qword ptr [rbp+var_30]
0x140c840a1  lea     r8, aCrashTriageARe; "CRASH TRIAGE: a real crash happened.\n"
0x140c840a8  mov     edx, r13d; Level
0x140c840ab  mov     ecx, 5Dh ; ']'; ComponentId
0x140c840b0  call    DbgPrintEx
0x140c840b5  mov     rax, qword ptr [rbp+var_18]
0x140c840b9  lea     r8, aCrashTriagePre; "CRASH TRIAGE: previous crash was %Ix %I"...
0x140c840c0  mov     rbx, qword ptr [rbp+var_18+8]
0x140c840c4  mov     r9, rsi
0x140c840c7  mov     qword ptr [rsp+70h+var_40+8], rbx
0x140c840cc  mov     edx, r13d; Level
0x140c840cf  mov     qword ptr [rsp+70h+var_40], rax
0x140c840d4  mov     ecx, 5Dh ; ']'; ComponentId
0x140c840d9  mov     rax, qword ptr [rbp+var_20]
0x140c840dd  mov     [rsp+70h+var_48], rax
0x140c840e2  mov     rax, qword ptr [rbp+var_30+8]
0x140c840e6  mov     [rsp+70h+var_50], rax
0x140c840eb  call    DbgPrintEx
0x140c840f0  mov     cs:qword_140EF2B20, rbx
0x140c840f7  movups  xmm0, [rbp+var_30]
0x140c840fb  movups  xmm1, xmmword ptr [rbp-20h]
0x140c840ff  movups  cs:ViTriageCrashData, xmm0
0x140c84106  movups  cs:xmmword_140EF2B10, xmm1
0x140c8410d  test    r14d, r14d
0x140c84110  jz      loc_140C841A6
0x140c84116  mov     rbx, [rdi+0F0h]
0x140c8411d  test    rbx, rbx
0x140c84120  jz      short loc_140C8418E
0x140c84122  cmp     dword ptr [rbx], 1150h
0x140c84128  jb      short loc_140C8418E
0x140c8412a  mov     rbx, [rbx+28h]
0x140c8412e  lea     rax, [rbp+var_18+8]
0x140c84132  mov     [rsp+70h+var_48], rax
0x140c84137  lea     r9, [rbp+var_20]
0x140c8413b  lea     rax, [rbp+var_18]
0x140c8413f  mov     rcx, rbx
0x140c84142  lea     r8, [rbp+var_30+8]
0x140c84146  mov     [rsp+70h+var_50], rax
0x140c8414b  lea     rdx, [rbp+var_30]
0x140c8414f  call    TriageGetBugcheckData
0x140c84154  test    eax, eax
0x140c84156  js      short loc_140C8418E
0x140c84158  mov     rcx, rbx
0x140c8415b  call    TriagepVerifyDump
0x140c84160  test    al, al
0x140c84162  jz      short loc_140C8418E
0x140c84164  mov     ecx, cs:TriageImagePageSize
0x140c8416a  add     rcx, rbx
0x140c8416d  jz      short loc_140C8418E
0x140c8416f  mov     ecx, [rcx+14h]
0x140c84172  add     rcx, rbx
0x140c84175  jz      short loc_140C8418E
0x140c84177  cmp     dword ptr [rcx+0Ch], 0
0x140c8417b  jz      short loc_140C8418E
0x140c8417d  lea     r8, aCrashTriageTri_1; "CRASH TRIAGE: triage skipped because it"...
0x140c84184  mov     ecx, 5Dh ; ']'
0x140c84189  jmp     loc_140C842F8
0x140c8418e  mov     rdx, r15
0x140c84191  mov     rcx, rdi
0x140c84194  call    ViTriageSameDriversFromDump
0x140c84199  test    eax, eax
0x140c8419b  jnz     short loc_140C841A6
0x140c8419d  lea     r8, aCrashTriageSom; "CRASH TRIAGE: some drivers changed from"...
0x140c841a4  jmp     short loc_140C84184
0x140c841a6  mov     edx, cs:ViVerifyTriageRulesSize
0x140c841ac  lea     r14, ViVerifyTriageRules
0x140c841b3  mov     rcx, r14
0x140c841b6  call    ViValidateTriageRules
0x140c841bb  test    eax, eax
0x140c841bd  jnz     short loc_140C841C8
0x140c841bf  lea     r8, aCrashTriageTri_2; "CRASH TRIAGE: triage disabled due to in"...
0x140c841c6  jmp     short loc_140C84184
0x140c841c8  mov     ebx, 30h ; '0'
0x140c841cd  lea     rcx, ViInternalTriageRules
0x140c841d4  mov     edx, ebx
0x140c841d6  call    ViValidateTriageRules
0x140c841db  test    eax, eax
0x140c841dd  jnz     short loc_140C841E8
0x140c841df  lea     r8, aCrashTriageTri_4; "CRASH TRIAGE: triage disabled due to in"...
0x140c841e6  jmp     short loc_140C84184
0x140c841e8  mov     edx, cs:ViVerifyTriageRulesSize
0x140c841ee  mov     r8d, esi
0x140c841f1  mov     rcx, r14
0x140c841f4  call    ViFindTriageRule
0x140c841f9  mov     rdi, rax
0x140c841fc  test    rax, rax
0x140c841ff  jnz     short loc_140C84235
0x140c84201  mov     r8d, esi
0x140c84204  lea     rcx, ViInternalTriageRules
0x140c8420b  mov     rdx, rbx
0x140c8420e  call    ViFindTriageRule
0x140c84213  mov     rdi, rax
0x140c84216  test    rax, rax
0x140c84219  jnz     short loc_140C84235
0x140c8421b  mov     r9, rsi
0x140c8421e  lea     r8, aCrashTriageCra; "CRASH TRIAGE: crash code %Ix will not b"...
0x140c84225  mov     edx, r13d; Level
0x140c84228  lea     ecx, [rax+5Dh]; ComponentId
0x140c8422b  call    DbgPrintEx
0x140c84230  jmp     loc_140C84300
0x140c84235  xor     ebx, ebx
0x140c84237  cmp     dword ptr [rdi], 80000h
0x140c8423d  jnb     short loc_140C842B8
0x140c8423f  mov     ecx, cs:ViVerifyTriageRulesSize
0x140c84245  mov     rbx, r14
0x140c84248  add     rcx, r14
0x140c8424b  cmp     rbx, rcx
0x140c8424e  jnb     short loc_140C84288
0x140c84250  mov     edx, [rbx]
0x140c84252  mov     eax, edx
0x140c84254  shr     eax, 10h
0x140c84257  and     eax, 7
0x140c8425a  jz      short loc_140C8427F
0x140c8425c  sub     eax, 1
0x140c8425f  jz      short loc_140C8426F
0x140c84261  cmp     eax, 1
0x140c84264  jnz     short loc_140C8424B
0x140c84266  lea     r8, aCrashTriageFou_0; "CRASH TRIAGE: found a `targets' rule.\n"
0x140c8426d  jmp     short loc_140C84291
0x140c8426f  mov     rax, rdx
0x140c84272  add     rbx, 8
0x140c84276  shr     rax, 13h
0x140c8427a  add     rbx, rax
0x140c8427d  jmp     short loc_140C8424B
0x140c8427f  lea     r8, aCrashTriageZer; "CRASH TRIAGE: zeroed rules structure (h"...
0x140c84286  jmp     short loc_140C8428F
0x140c84288  lea     r8, aCrashTriageNoT; "CRASH TRIAGE: no `targets' rule found."...
0x140c8428f  xor     ebx, ebx
0x140c84291  mov     esi, 5Dh ; ']'
0x140c84296  mov     edx, r13d; Level
0x140c84299  mov     ecx, esi; ComponentId
0x140c8429b  call    DbgPrintEx
0x140c842a0  test    rbx, rbx
0x140c842a3  jz      short loc_140C842BD
0x140c842a5  lea     r8, aCrashTriageNoT; "CRASH TRIAGE: no `targets' rule found."...
0x140c842ac  mov     edx, r13d; Level
0x140c842af  mov     ecx, esi; ComponentId
0x140c842b1  call    DbgPrintEx
0x140c842b6  jmp     short loc_140C842BD
0x140c842b8  mov     esi, 5Dh ; ']'
0x140c842bd  cmp     dword ptr [rdi+4], 0
0x140c842c1  jz      short loc_140C842E6
0x140c842c3  mov     rdx, rbx
0x140c842c6  mov     rcx, rdi
0x140c842c9  call    ViMakeVerifierSettings
0x140c842ce  lea     r8, aCrashTriageTri_0; "CRASH TRIAGE: triage enabled!\n"
0x140c842d5  mov     edx, r13d; Level
0x140c842d8  mov     ecx, esi; ComponentId
0x140c842da  call    DbgPrintEx
0x140c842df  mov     eax, 1
0x140c842e4  jmp     short loc_140C84302
0x140c842e6  lea     r8, aCrashTriageTri_3; "CRASH TRIAGE: triage disabled due to ru"...
0x140c842ed  jmp     short loc_140C842F6
0x140c842ef  lea     r8, aCrashTriageDri; "CRASH TRIAGE: driver verifier settings "...
0x140c842f6  mov     ecx, esi; ComponentId
0x140c842f8  mov     edx, r13d; Level
0x140c842fb  call    DbgPrintEx
0x140c84300  xor     eax, eax
0x140c84302  add     rsp, 70h
0x140c84306  pop     r15
0x140c84308  pop     r14
0x140c8430a  pop     r13
0x140c8430c  pop     rdi
0x140c8430d  pop     rsi
0x140c8430e  pop     rbx
0x140c8430f  pop     rbp
0x140c84310  retn
```
