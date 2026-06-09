# VfTriageSystem

- ea: `0x140c81114`
- end: `0x140c814b6`
- name: `VfTriageSystem`
- size: `930`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x140c806bc`

## callees

- `0x14020fe90`
- `0x140c81114`
- `0x140c814bc`
- `0x140c8155c`
- `0x140c81630`
- `0x140c816d4`
- `0x140ca37a0`
- `0x140ca3880`

## string_xrefs

- `0x140c8112d`: `CRASH TRIAGE: verifier triage global/registry settings %X \n`
- `0x140c81363`: `CRASH TRIAGE: triage disabled due to invalid registry rules.\n`
- `0x140c811d5`: `CRASH TRIAGE: unexpected loader extension size.\n`
- `0x140c811c1`: `CRASH TRIAGE: null loader extension.\n`

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
  _DWORD *v14; // rbx
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
        qword_140EF29E0 = v8;
        ViTriageCrashData = *(_OWORD *)v17;
        xmmword_140EF29D0 = *(_OWORD *)&v17[16];
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
        if ( (unsigned int)ViValidateTriageRules(&ViVerifyTriageRules, (unsigned int)ViVerifyTriageRulesSize) )
        {
          if ( (unsigned int)ViValidateTriageRules(&ViInternalTriageRules, 48) )
          {
            TriageRule = (_DWORD *)ViFindTriageRule(&ViVerifyTriageRules, (unsigned int)ViVerifyTriageRulesSize, v7);
            if ( TriageRule || (TriageRule = (_DWORD *)ViFindTriageRule(&ViInternalTriageRules, 48, v7)) != 0 )
            {
              v14 = 0;
              if ( *TriageRule < 0x80000u )
              {
                v14 = &ViVerifyTriageRules;
                while ( v14 < (_DWORD *)((char *)&ViVerifyTriageRules + (unsigned int)ViVerifyTriageRulesSize) )
                {
                  if ( (*v14 & 0x70000) == 0 )
                  {
                    v15 = "CRASH TRIAGE: zeroed rules structure (hit an invalid type rule).\n";
                    goto LABEL_46;
                  }
                  if ( (HIWORD(*v14) & 7) == 1 )
                  {
                    v14 = (_DWORD *)((char *)v14 + ((unsigned __int64)(unsigned int)*v14 >> 19) + 8);
                  }
                  else if ( (HIWORD(*v14) & 7) == 2 )
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
0x140c81114  push    rbp
0x140c81116  push    rbx
0x140c81117  push    rsi
0x140c81118  push    rdi
0x140c81119  push    r13
0x140c8111b  push    r14
0x140c8111d  push    r15
0x140c8111f  mov     rbp, rsp
0x140c81122  sub     rsp, 70h
0x140c81126  mov     r9d, cs:ViVerifyTriage
0x140c8112d  lea     r8, aCrashTriageVer; "CRASH TRIAGE: verifier triage global/re"...
0x140c81134  mov     r13d, 3
0x140c8113a  mov     rdi, rcx
0x140c8113d  mov     edx, r13d; Level
0x140c81140  lea     esi, [r13+5Ah]
0x140c81144  mov     ecx, esi; ComponentId
0x140c81146  call    DbgPrintEx
0x140c8114b  or      ecx, 0FFFFFFFFh
0x140c8114e  cmp     cs:MmVerifyDriverLevel, ecx
0x140c81154  jnz     loc_140C81493
0x140c8115a  cmp     cs:ViVerifyAllDrivers, 0
0x140c81161  jnz     loc_140C81493
0x140c81167  mov     eax, cs:ViVerifyTriage
0x140c8116d  cmp     eax, ecx
0x140c8116f  jnz     short loc_140C8117D
0x140c81171  lea     r8, aCrashTriageTri; "CRASH TRIAGE: triage skipped because it"...
0x140c81178  jmp     loc_140C8149A
0x140c8117d  test    eax, eax
0x140c8117f  jnz     short loc_140C8118D
0x140c81181  lea     r8, aCrashTriageTri_5; "CRASH TRIAGE: triage skipped because it"...
0x140c81188  jmp     loc_140C8149A
0x140c8118d  xor     ebx, ebx
0x140c8118f  lea     r14d, [rbx+1]
0x140c81193  test    eax, eax
0x140c81195  jns     short loc_140C811B5
0x140c81197  movzx   ebx, ax
0x140c8119a  lea     r8, aCrashTriageSim; "CRASH TRIAGE: simulated crash code %X."...
0x140c811a1  mov     r9d, ebx
0x140c811a4  mov     cs:ViVerifyTriage, r14d
0x140c811ab  mov     edx, r13d; Level
0x140c811ae  mov     ecx, esi; ComponentId
0x140c811b0  call    DbgPrintEx
0x140c811b5  mov     rax, [rdi+0F0h]
0x140c811bc  test    rax, rax
0x140c811bf  jnz     short loc_140C811CD
0x140c811c1  lea     r8, aCrashTriageNul; "CRASH TRIAGE: null loader extension.\n"
0x140c811c8  jmp     loc_140C8149A
0x140c811cd  cmp     dword ptr [rax], 1150h
0x140c811d3  jnb     short loc_140C811E1
0x140c811d5  lea     r8, aCrashTriageUne; "CRASH TRIAGE: unexpected loader extensi"...
0x140c811dc  jmp     loc_140C8149A
0x140c811e1  mov     r15, [rax+28h]
0x140c811e5  lea     r9, [rbp+var_20]
0x140c811e9  lea     rax, [rbp+var_18+8]
0x140c811ed  mov     rcx, r15
0x140c811f0  mov     [rsp+70h+var_48], rax
0x140c811f5  lea     r8, [rbp+var_30+8]
0x140c811f9  lea     rax, [rbp+var_18]
0x140c811fd  lea     rdx, [rbp+var_30]
0x140c81201  mov     [rsp+70h+var_50], rax
0x140c81206  call    TriageGetBugcheckData
0x140c8120b  test    eax, eax
0x140c8120d  jns     short loc_140C81241
0x140c8120f  test    ebx, ebx
0x140c81211  jnz     short loc_140C8121F
0x140c81213  lea     r8, aCrashTriageSta; "CRASH TRIAGE: standard retail exit poin"...
0x140c8121a  jmp     loc_140C8149A
0x140c8121f  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140c81227  lea     r8, aCrashTriageAFa; "CRASH TRIAGE: a fake crash will be simu"...
0x140c8122e  mov     esi, ebx
0x140c81230  xor     r14d, r14d
0x140c81233  mov     qword ptr [rbp+var_30], rsi
0x140c81237  movups  [rbp+var_30+8], xmm0
0x140c8123b  movups  [rbp+var_18], xmm0
0x140c8123f  jmp     short loc_140C8124C
0x140c81241  mov     rsi, qword ptr [rbp+var_30]
0x140c81245  lea     r8, aCrashTriageARe; "CRASH TRIAGE: a real crash happened.\n"
0x140c8124c  mov     edx, r13d; Level
0x140c8124f  mov     ecx, 5Dh ; ']'; ComponentId
0x140c81254  call    DbgPrintEx
0x140c81259  mov     rax, qword ptr [rbp+var_18]
0x140c8125d  lea     r8, aCrashTriagePre; "CRASH TRIAGE: previous crash was %Ix %I"...
0x140c81264  mov     rbx, qword ptr [rbp+var_18+8]
0x140c81268  mov     r9, rsi
0x140c8126b  mov     qword ptr [rsp+70h+var_40+8], rbx
0x140c81270  mov     edx, r13d; Level
0x140c81273  mov     qword ptr [rsp+70h+var_40], rax
0x140c81278  mov     ecx, 5Dh ; ']'; ComponentId
0x140c8127d  mov     rax, qword ptr [rbp+var_20]
0x140c81281  mov     [rsp+70h+var_48], rax
0x140c81286  mov     rax, qword ptr [rbp+var_30+8]
0x140c8128a  mov     [rsp+70h+var_50], rax
0x140c8128f  call    DbgPrintEx
0x140c81294  mov     cs:qword_140EF29E0, rbx
0x140c8129b  movups  xmm0, [rbp+var_30]
0x140c8129f  movups  xmm1, xmmword ptr [rbp-20h]
0x140c812a3  movups  cs:ViTriageCrashData, xmm0
0x140c812aa  movups  cs:xmmword_140EF29D0, xmm1
0x140c812b1  test    r14d, r14d
0x140c812b4  jz      loc_140C8134A
0x140c812ba  mov     rbx, [rdi+0F0h]
0x140c812c1  test    rbx, rbx
0x140c812c4  jz      short loc_140C81332
0x140c812c6  cmp     dword ptr [rbx], 1150h
0x140c812cc  jb      short loc_140C81332
0x140c812ce  mov     rbx, [rbx+28h]
0x140c812d2  lea     rax, [rbp+var_18+8]
0x140c812d6  mov     [rsp+70h+var_48], rax
0x140c812db  lea     r9, [rbp+var_20]
0x140c812df  lea     rax, [rbp+var_18]
0x140c812e3  mov     rcx, rbx
0x140c812e6  lea     r8, [rbp+var_30+8]
0x140c812ea  mov     [rsp+70h+var_50], rax
0x140c812ef  lea     rdx, [rbp+var_30]
0x140c812f3  call    TriageGetBugcheckData
0x140c812f8  test    eax, eax
0x140c812fa  js      short loc_140C81332
0x140c812fc  mov     rcx, rbx
0x140c812ff  call    TriagepVerifyDump
0x140c81304  test    al, al
0x140c81306  jz      short loc_140C81332
0x140c81308  mov     ecx, cs:TriageImagePageSize
0x140c8130e  add     rcx, rbx
0x140c81311  jz      short loc_140C81332
0x140c81313  mov     ecx, [rcx+14h]
0x140c81316  add     rcx, rbx
0x140c81319  jz      short loc_140C81332
0x140c8131b  cmp     dword ptr [rcx+0Ch], 0
0x140c8131f  jz      short loc_140C81332
0x140c81321  lea     r8, aCrashTriageTri_1; "CRASH TRIAGE: triage skipped because it"...
0x140c81328  mov     ecx, 5Dh ; ']'
0x140c8132d  jmp     loc_140C8149C
0x140c81332  mov     rdx, r15
0x140c81335  mov     rcx, rdi
0x140c81338  call    ViTriageSameDriversFromDump
0x140c8133d  test    eax, eax
0x140c8133f  jnz     short loc_140C8134A
0x140c81341  lea     r8, aCrashTriageSom; "CRASH TRIAGE: some drivers changed from"...
0x140c81348  jmp     short loc_140C81328
0x140c8134a  mov     edx, cs:ViVerifyTriageRulesSize
0x140c81350  lea     r14, ViVerifyTriageRules
0x140c81357  mov     rcx, r14
0x140c8135a  call    ViValidateTriageRules
0x140c8135f  test    eax, eax
0x140c81361  jnz     short loc_140C8136C
0x140c81363  lea     r8, aCrashTriageTri_2; "CRASH TRIAGE: triage disabled due to in"...
0x140c8136a  jmp     short loc_140C81328
0x140c8136c  mov     ebx, 30h ; '0'
0x140c81371  lea     rcx, ViInternalTriageRules
0x140c81378  mov     edx, ebx
0x140c8137a  call    ViValidateTriageRules
0x140c8137f  test    eax, eax
0x140c81381  jnz     short loc_140C8138C
0x140c81383  lea     r8, aCrashTriageTri_4; "CRASH TRIAGE: triage disabled due to in"...
0x140c8138a  jmp     short loc_140C81328
0x140c8138c  mov     edx, cs:ViVerifyTriageRulesSize
0x140c81392  mov     r8d, esi
0x140c81395  mov     rcx, r14
0x140c81398  call    ViFindTriageRule
0x140c8139d  mov     rdi, rax
0x140c813a0  test    rax, rax
0x140c813a3  jnz     short loc_140C813D9
0x140c813a5  mov     r8d, esi
0x140c813a8  lea     rcx, ViInternalTriageRules
0x140c813af  mov     rdx, rbx
0x140c813b2  call    ViFindTriageRule
0x140c813b7  mov     rdi, rax
0x140c813ba  test    rax, rax
0x140c813bd  jnz     short loc_140C813D9
0x140c813bf  mov     r9, rsi
0x140c813c2  lea     r8, aCrashTriageCra; "CRASH TRIAGE: crash code %Ix will not b"...
0x140c813c9  mov     edx, r13d; Level
0x140c813cc  lea     ecx, [rax+5Dh]; ComponentId
0x140c813cf  call    DbgPrintEx
0x140c813d4  jmp     loc_140C814A4
0x140c813d9  xor     ebx, ebx
0x140c813db  cmp     dword ptr [rdi], 80000h
0x140c813e1  jnb     short loc_140C8145C
0x140c813e3  mov     ecx, cs:ViVerifyTriageRulesSize
0x140c813e9  mov     rbx, r14
0x140c813ec  add     rcx, r14
0x140c813ef  cmp     rbx, rcx
0x140c813f2  jnb     short loc_140C8142C
0x140c813f4  mov     edx, [rbx]
0x140c813f6  mov     eax, edx
0x140c813f8  shr     eax, 10h
0x140c813fb  and     eax, 7
0x140c813fe  jz      short loc_140C81423
0x140c81400  sub     eax, 1
0x140c81403  jz      short loc_140C81413
0x140c81405  cmp     eax, 1
0x140c81408  jnz     short loc_140C813EF
0x140c8140a  lea     r8, aCrashTriageFou_0; "CRASH TRIAGE: found a `targets' rule.\n"
0x140c81411  jmp     short loc_140C81435
0x140c81413  mov     rax, rdx
0x140c81416  add     rbx, 8
0x140c8141a  shr     rax, 13h
0x140c8141e  add     rbx, rax
0x140c81421  jmp     short loc_140C813EF
0x140c81423  lea     r8, aCrashTriageZer; "CRASH TRIAGE: zeroed rules structure (h"...
0x140c8142a  jmp     short loc_140C81433
0x140c8142c  lea     r8, aCrashTriageNoT; "CRASH TRIAGE: no `targets' rule found."...
0x140c81433  xor     ebx, ebx
0x140c81435  mov     esi, 5Dh ; ']'
0x140c8143a  mov     edx, r13d; Level
0x140c8143d  mov     ecx, esi; ComponentId
0x140c8143f  call    DbgPrintEx
0x140c81444  test    rbx, rbx
0x140c81447  jz      short loc_140C81461
0x140c81449  lea     r8, aCrashTriageNoT; "CRASH TRIAGE: no `targets' rule found."...
0x140c81450  mov     edx, r13d; Level
0x140c81453  mov     ecx, esi; ComponentId
0x140c81455  call    DbgPrintEx
0x140c8145a  jmp     short loc_140C81461
0x140c8145c  mov     esi, 5Dh ; ']'
0x140c81461  cmp     dword ptr [rdi+4], 0
0x140c81465  jz      short loc_140C8148A
0x140c81467  mov     rdx, rbx
0x140c8146a  mov     rcx, rdi
0x140c8146d  call    ViMakeVerifierSettings
0x140c81472  lea     r8, aCrashTriageTri_0; "CRASH TRIAGE: triage enabled!\n"
0x140c81479  mov     edx, r13d; Level
0x140c8147c  mov     ecx, esi; ComponentId
0x140c8147e  call    DbgPrintEx
0x140c81483  mov     eax, 1
0x140c81488  jmp     short loc_140C814A6
0x140c8148a  lea     r8, aCrashTriageTri_3; "CRASH TRIAGE: triage disabled due to ru"...
0x140c81491  jmp     short loc_140C8149A
0x140c81493  lea     r8, aCrashTriageDri; "CRASH TRIAGE: driver verifier settings "...
0x140c8149a  mov     ecx, esi; ComponentId
0x140c8149c  mov     edx, r13d; Level
0x140c8149f  call    DbgPrintEx
0x140c814a4  xor     eax, eax
0x140c814a6  add     rsp, 70h
0x140c814aa  pop     r15
0x140c814ac  pop     r14
0x140c814ae  pop     r13
0x140c814b0  pop     rdi
0x140c814b1  pop     rsi
0x140c814b2  pop     rbx
0x140c814b3  pop     rbp
0x140c814b4  retn
```
