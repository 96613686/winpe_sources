# RtlpGetTokenNamedObjectPath

- ea: `0x180036690`
- end: `0x180036dcd`
- name: `RtlpGetTokenNamedObjectPath`
- size: `1853`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800371d0`
- `0x1800380b0`

## callees

- `0x180015710`
- `0x18001861c`
- `0x18001d490`
- `0x180021fd0`
- `0x180035fd0`
- `0x180036690`
- `0x180036fa0`
- `0x180037038`
- `0x1800370d0`
- `0x180037430`
- `0x18006f0d0`
- `0x1800773d0`
- `0x18012d320`
- `0x18015ef00`
- `0x180162810`
- `0x18016f030`

## pseudocode

```c
__int64 __fastcall RtlpGetTokenNamedObjectPath(__int64 a1, _DWORD *a2, int a3, UNICODE_STRING *a4)
{
  char v4; // r13
  PSID v7; // r12
  char v9; // r15
  NTSTATUS appended; // ebx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  unsigned int v15; // edi
  char v16; // bl
  int v17; // r13d
  char v18; // bl
  bool v19; // al
  __int64 v20; // rdx
  __int64 v21; // rcx
  const wchar_t *v22; // rax
  _WORD *v23; // r8
  _WORD *v24; // rcx
  __int64 v25; // rcx
  _WORD *v26; // rax
  int v27; // edx
  int v28; // esi
  __int64 v29; // rbx
  size_t v30; // rbx
  wchar_t *Atom; // rax
  wchar_t *v32; // rdi
  const wchar_t *v34; // rax
  NTSTATUS v35; // eax
  int *v36; // rax
  NTSTATUS v37; // eax
  __int64 v38; // rcx
  const wchar_t *v39; // r8
  _WORD *v40; // rax
  size_t v41; // rax
  int AppContainerParent; // eax
  int v43; // eax
  wchar_t *Buffer; // rdi
  size_t v45; // rax
  __int64 v46; // [rsp+20h] [rbp-E0h]
  __int64 v47; // [rsp+20h] [rbp-E0h]
  int v48; // [rsp+28h] [rbp-D8h]
  int v49; // [rsp+30h] [rbp-D0h]
  int v50; // [rsp+38h] [rbp-C8h]
  char v51; // [rsp+40h] [rbp-C0h]
  int v52; // [rsp+44h] [rbp-BCh] BYREF
  int v53; // [rsp+48h] [rbp-B8h] BYREF
  int v54; // [rsp+4Ch] [rbp-B4h] BYREF
  int v55; // [rsp+50h] [rbp-B0h]
  int v56; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v57; // [rsp+58h] [rbp-A8h] BYREF
  UNICODE_STRING UnicodeString; // [rsp+60h] [rbp-A0h] BYREF
  PSID v59; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v60[2]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v61; // [rsp+88h] [rbp-78h] BYREF
  UNICODE_STRING v62; // [rsp+98h] [rbp-68h] BYREF
  PSID Sid[12]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v64[10]; // [rsp+110h] [rbp+10h] BYREF
  wchar_t *String; // [rsp+160h] [rbp+60h] BYREF
  char v66; // [rsp+168h] [rbp+68h]
  _BYTE v67[528]; // [rsp+280h] [rbp+180h] BYREF
  wchar_t v68[264]; // [rsp+490h] [rbp+390h] BYREF

  v55 = a3;
  v4 = a3;
  v56 = 0;
  v59 = 0;
  v7 = 0;
  memset_thunk_772440563353939046(v64, 0, 0x50u);
  v53 = 0;
  v57 = 0;
  memset_thunk_772440563353939046(v67, 0, 0x208u);
  memset_thunk_772440563353939046(v68, 0, 0x208u);
  memset_thunk_772440563353939046(Sid, 0, 0x58u);
  v60[0] = 262146;
  v60[1] = L"\\";
  v61 = 0;
  if ( !a4 || !a1 )
    return 3221225485LL;
  v9 = 1;
  v51 = 1;
  v52 = 0;
  v54 = 0;
  *a4 = 0;
  UnicodeString = 0;
  v62 = 0;
  if ( a2 )
  {
    v52 = 1;
  }
  else
  {
    appended = NtQueryInformationToken(a1, 29, &v52, 4, &v53);
    if ( appended < 0 )
      goto LABEL_50;
    a2 = 0;
    if ( v52 )
    {
      appended = NtQueryInformationToken(a1, 31, v64, 80, &v53);
      if ( appended < 0 )
        goto LABEL_50;
      a2 = (_DWORD *)v64[0];
      if ( !v64[0] )
      {
        appended = -1073741823;
        goto LABEL_50;
      }
    }
  }
  appended = NtQueryInformationToken(a1, 42, &v54, 4, &v53);
  if ( appended >= 0 )
  {
    if ( !v54 )
    {
LABEL_7:
      appended = NtQueryInformationToken(a1, 12, &v57, 4, &v53);
      if ( appended < 0 )
        goto LABEL_47;
      if ( !v52 )
      {
LABEL_9:
        appended = NtQueryInformationToken(a1, 44, &String, 288, &v53);
        if ( appended < 0 )
        {
LABEL_46:
          v9 = v51;
          goto LABEL_47;
        }
        v15 = v57;
        v16 = v4;
        v17 = v52;
        v18 = v16 & 1;
        v19 = !v54 && !v52 && v15 == (unsigned int)RtlGetCurrentServiceSessionId(v12, v11, v13, v14);
        v20 = 260;
        if ( v18 )
        {
          if ( (v55 & 4) != 0 )
          {
            v21 = 2147483646;
            v22 = L"AppContainerNamedObjects";
            v23 = v67;
            do
            {
              if ( !v21 )
                break;
              if ( !*v22 )
                break;
              *v23++ = *v22++;
              --v21;
              --v20;
            }
            while ( v20 );
            v24 = v23 - 1;
            if ( v20 )
              v24 = v23;
LABEL_20:
            appended = -2147483643;
            *v24 = 0;
            if ( v20 )
              appended = 0;
            goto LABEL_22;
          }
          v36 = (int *)L"\\AppContainerNamedObjects";
          if ( !v17 )
            v36 = &dword_18017664C;
          v37 = RtlStringCchPrintfW(v67, 260, L"Global\\Session\\%ld%s", v15, v36);
          v17 = v52;
          appended = v37;
        }
        else
        {
          if ( v19 )
          {
            v38 = 2147483646;
            v39 = L"\\BaseNamedObjects";
            v40 = v67;
            do
            {
              if ( !v38 )
                break;
              if ( !*v39 )
                break;
              *v40++ = *v39++;
              --v38;
              --v20;
            }
            while ( v20 );
            v24 = v40 - 1;
            if ( v20 )
              v24 = v40;
            goto LABEL_20;
          }
          v34 = L"AppContainerNamedObjects";
          if ( !v17 )
            v34 = L"BaseNamedObjects";
          LODWORD(v47) = v15;
          v35 = RtlStringCchPrintfW(v67, 260, L"%s\\%ld\\%s", L"\\Sessions", v47, v34);
          v17 = v52;
          appended = v35;
        }
LABEL_22:
        if ( appended >= 0 )
        {
          v25 = 260;
          v26 = v67;
          do
          {
            if ( !*v26 )
              break;
            ++v26;
            --v25;
          }
          while ( v25 );
          appended = -1073741811;
          if ( v25 )
          {
            v27 = v55 & 8;
            v28 = v55 & 2;
            v55 = v27;
            if ( !v54 || v28 )
              v29 = 2 * (260 - v25);
            else
              v29 = 2 * (260 - v25) + v62.Length + 2;
            if ( v17 )
              v29 += UnicodeString.Length + 2LL;
            if ( v66 && !v27 )
            {
              LOWORD(v41) = 0;
              *(_QWORD *)&v61 = 0;
              *((_QWORD *)&v61 + 1) = String;
              if ( String )
              {
                v41 = 2 * wcslen(String);
                if ( v41 >= 0xFFFE )
                  LOWORD(v41) = -4;
                LOWORD(v61) = v41;
                WORD1(v61) = v41 + 2;
              }
              v29 += (unsigned __int16)v41 + 2LL;
            }
            v30 = v29 + 2;
            Atom = (wchar_t *)RtlpAllocateAtom(v30);
            v32 = Atom;
            if ( Atom )
            {
              memset_thunk_772440563353939046(Atom, 0, v30);
              *a4 = 0;
              a4->MaximumLength = v30;
              a4->Buffer = v32;
              appended = RtlAppendUnicodeToString(a4, v67);
              if ( appended >= 0 )
              {
                if ( !v54
                  || v28
                  || (appended = RtlAppendUnicodeStringToString(a4, v60), appended >= 0)
                  && (appended = RtlAppendUnicodeStringToString(a4, &v62), appended >= 0) )
                {
                  if ( !v52
                    || (appended = RtlAppendUnicodeStringToString(a4, v60), appended >= 0)
                    && (appended = RtlAppendUnicodeStringToString(a4, &UnicodeString), appended >= 0) )
                  {
                    if ( v66 )
                    {
                      if ( !v55 )
                      {
                        appended = RtlAppendUnicodeStringToString(a4, v60);
                        if ( appended >= 0 )
                        {
                          v9 = v51;
                          appended = RtlAppendUnicodeStringToString(a4, &v61);
                          goto LABEL_47;
                        }
                      }
                    }
                  }
                }
              }
            }
            else
            {
              appended = -1073741670;
            }
          }
        }
        goto LABEL_46;
      }
      appended = RtlGetAppContainerSidType(a2, &v56);
      if ( appended >= 0 )
      {
        if ( v56 == 2 )
        {
          appended = RtlConvertSidToUnicodeString(&UnicodeString, a2, 1u);
          if ( appended >= 0 )
            goto LABEL_9;
        }
        else
        {
          AppContainerParent = RtlGetAppContainerParent(a2, &v59);
          v7 = v59;
          appended = AppContainerParent;
          if ( AppContainerParent >= 0 )
          {
            appended = RtlConvertSidToUnicodeString(&UnicodeString, v59, 1u);
            if ( appended >= 0 )
            {
              v50 = a2[13];
              v49 = a2[12];
              v48 = a2[11];
              v43 = a2[10];
              Buffer = UnicodeString.Buffer;
              LODWORD(v46) = v43;
              appended = RtlStringCchPrintfW(v68, 260, L"%s\\%u-%u-%u-%u", UnicodeString.Buffer, v46, v48, v49, v50);
              if ( appended >= 0 )
              {
                if ( Buffer )
                  RtlpSysVolFree(Buffer);
                *(_DWORD *)(&UnicodeString.MaximumLength + 1) = 0;
                UnicodeString.Buffer = v68;
                v45 = 2 * wcslen(v68);
                v51 = 0;
                if ( v45 >= 0xFFFE )
                  LOWORD(v45) = -4;
                UnicodeString.Length = v45;
                UnicodeString.MaximumLength = v45 + 2;
                goto LABEL_9;
              }
            }
          }
        }
      }
      v9 = 1;
LABEL_47:
      if ( v62.Buffer )
        RtlpSysVolFree(v62.Buffer);
      if ( appended >= 0 )
        goto LABEL_51;
      goto LABEL_50;
    }
    appended = NtQueryInformationToken(a1, 1, Sid, 88, &v53);
    if ( appended >= 0 )
    {
      appended = RtlConvertSidToUnicodeString(&v62, Sid[0], 1u);
      if ( appended < 0 )
        goto LABEL_47;
      goto LABEL_7;
    }
  }
LABEL_50:
  RtlFreeAnsiString(a4);
LABEL_51:
  if ( v9 && UnicodeString.Buffer )
    RtlpSysVolFree(UnicodeString.Buffer);
  if ( v7 )
    RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v7);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180036690  push    rbp
0x180036692  push    rbx
0x180036693  push    rsi
0x180036694  push    rdi
0x180036695  push    r12
0x180036697  push    r13
0x180036699  push    r14
0x18003669b  lea     rbp, [rsp-5B0h]
0x1800366a3  sub     rsp, 6B0h
0x1800366aa  mov     rax, cs:__security_cookie
0x1800366b1  xor     rax, rsp
0x1800366b4  mov     [rbp+5E0h+var_40], rax
0x1800366bb  xor     ebx, ebx
0x1800366bd  mov     [rsp+6E0h+var_690], r8d
0x1800366c2  mov     r13d, r8d
0x1800366c5  mov     [rsp+6E0h+var_68C], ebx
0x1800366c9  mov     rdi, rdx
0x1800366cc  mov     [rsp+6E0h+var_670], rbx
0x1800366d1  mov     rsi, rcx
0x1800366d4  xor     edx, edx; Val
0x1800366d6  mov     r8d, 50h ; 'P'; Size
0x1800366dc  lea     rcx, [rbp+5E0h+var_5D0]; void *
0x1800366e0  mov     r12d, ebx
0x1800366e3  mov     r14, r9
0x1800366e6  call    memset$thunk$772440563353939046
0x1800366eb  xor     edx, edx; Val
0x1800366ed  mov     [rsp+6E0h+var_698], ebx
0x1800366f1  mov     r8d, 208h; Size
0x1800366f7  mov     [rsp+6E0h+var_688], ebx
0x1800366fb  lea     rcx, [rbp+5E0h+var_460]; void *
0x180036702  call    memset$thunk$772440563353939046
0x180036707  xor     edx, edx; Val
0x180036709  lea     rcx, [rbp+5E0h+var_250]; void *
0x180036710  mov     r8d, 208h; Size
0x180036716  call    memset$thunk$772440563353939046
0x18003671b  xor     edx, edx; Val
0x18003671d  lea     rcx, [rbp+5E0h+Sid]; void *
0x180036721  mov     r8d, 58h ; 'X'; Size
0x180036727  call    memset$thunk$772440563353939046
0x18003672c  mov     [rsp+6E0h+var_668], 40002h
0x180036735  xorps   xmm0, xmm0
0x180036738  lea     rax, asc_180178554; "\\"
0x18003673f  mov     [rbp+5E0h+var_660], rax
0x180036743  movups  [rbp+5E0h+var_658], xmm0
0x180036747  test    r14, r14
0x18003674a  jz      loc_180036DC3
0x180036750  test    rsi, rsi
0x180036753  jz      loc_180036DC3
0x180036759  mov     [rsp+6E0h+arg_10], r15
0x180036761  mov     r15b, 1
0x180036764  mov     [rsp+6E0h+var_6A0], r15b
0x180036769  xorps   xmm1, xmm1
0x18003676c  mov     [rsp+6E0h+var_69C], ebx
0x180036770  mov     [rsp+6E0h+var_694], ebx
0x180036774  movups  xmmword ptr [r14], xmm0
0x180036778  movups  xmmword ptr [rsp+6E0h+UnicodeString.Length], xmm0
0x18003677d  movups  xmmword ptr [rbp+5E0h+var_648.Length], xmm1
0x180036781  test    rdi, rdi
0x180036784  jz      loc_180036B3E
0x18003678a  mov     [rsp+6E0h+var_69C], 1
0x180036792  lea     rax, [rsp+6E0h+var_698]
0x180036797  mov     r9d, 4
0x18003679d  lea     r8, [rsp+6E0h+var_694]
0x1800367a2  mov     [rsp+6E0h+var_6C0], rax
0x1800367a7  mov     edx, 2Ah ; '*'
0x1800367ac  mov     rcx, rsi
0x1800367af  call    NtQueryInformationToken
0x1800367b4  mov     ebx, eax
0x1800367b6  test    eax, eax
0x1800367b8  js      loc_180036A2E
0x1800367be  cmp     [rsp+6E0h+var_694], r12d
0x1800367c3  jnz     loc_180036C8D
0x1800367c9  lea     rax, [rsp+6E0h+var_698]
0x1800367ce  mov     r9d, 4
0x1800367d4  lea     r8, [rsp+6E0h+var_688]
0x1800367d9  mov     [rsp+6E0h+var_6C0], rax
0x1800367de  mov     edx, 0Ch
0x1800367e3  mov     rcx, rsi
0x1800367e6  call    NtQueryInformationToken
0x1800367eb  mov     ebx, eax
0x1800367ed  test    eax, eax
0x1800367ef  js      loc_180036A1C
0x1800367f5  mov     r15d, 104h
0x1800367fb  cmp     [rsp+6E0h+var_69C], r12d
0x180036800  jnz     loc_180036AE1
0x180036806  lea     rax, [rsp+6E0h+var_698]
0x18003680b  mov     r9d, 120h
0x180036811  lea     r8, [rbp+5E0h+String]
0x180036815  mov     [rsp+6E0h+var_6C0], rax
0x18003681a  mov     edx, 2Ch ; ','
0x18003681f  mov     rcx, rsi
0x180036822  call    NtQueryInformationToken
0x180036827  mov     ebx, eax
0x180036829  test    eax, eax
0x18003682b  js      loc_180036A16
0x180036831  mov     edi, [rsp+6E0h+var_688]
0x180036835  movzx   ebx, r13b
0x180036839  mov     r13d, [rsp+6E0h+var_69C]
0x18003683e  and     bl, 1
0x180036841  cmp     [rsp+6E0h+var_694], 0
0x180036846  jz      loc_180036B21
0x18003684c  xor     al, al
0x18003684e  mov     rdx, r15
0x180036851  test    bl, bl
0x180036853  jz      loc_180036A95
0x180036859  test    byte ptr [rsp+6E0h+var_690], 4
0x18003685e  jz      loc_180036BB8
0x180036864  mov     ecx, 7FFFFFFEh
0x180036869  lea     rax, aAppcontainerna_0; "AppContainerNamedObjects"
0x180036870  lea     r8, [rbp+5E0h+var_460]
0x180036877  test    rcx, rcx
0x18003687a  jz      short loc_18003689B
0x18003687c  movzx   r9d, word ptr [rax]
0x180036880  test    r9w, r9w
0x180036884  jz      short loc_18003689B
0x180036886  mov     [r8], r9w
0x18003688a  add     rax, 2
0x18003688e  add     r8, 2
0x180036892  dec     rcx
0x180036895  sub     rdx, 1
0x180036899  jnz     short loc_180036877
0x18003689b  test    rdx, rdx
0x18003689e  lea     rcx, [r8-2]
0x1800368a2  cmovnz  rcx, r8
0x1800368a6  xor     eax, eax
0x1800368a8  mov     ebx, 80000005h
0x1800368ad  test    rdx, rdx
0x1800368b0  mov     [rcx], ax
0x1800368b3  cmovnz  ebx, eax
0x1800368b6  test    ebx, ebx
0x1800368b8  js      loc_180036A16
0x1800368be  mov     rcx, r15
0x1800368c1  lea     rax, [rbp+5E0h+var_460]
0x1800368c8  cmp     word ptr [rax], 0
0x1800368cc  jz      short loc_1800368D8
0x1800368ce  add     rax, 2
0x1800368d2  sub     rcx, 1
0x1800368d6  jnz     short loc_1800368C8
0x1800368d8  xor     eax, eax
0x1800368da  mov     ebx, 0C000000Dh
0x1800368df  test    rcx, rcx
0x1800368e2  cmovnz  ebx, eax
0x1800368e5  jz      loc_180036A16
0x1800368eb  mov     edx, [rsp+6E0h+var_690]
0x1800368ef  sub     r15, rcx
0x1800368f2  mov     esi, edx
0x1800368f4  add     r15, r15
0x1800368f7  and     edx, 8
0x1800368fa  and     esi, 2
0x1800368fd  mov     edi, 2
0x180036902  mov     [rsp+6E0h+var_690], edx
0x180036906  cmp     [rsp+6E0h+var_694], eax
0x18003690a  jnz     loc_180036DA9
0x180036910  mov     rbx, r15
0x180036913  test    r13d, r13d
0x180036916  jz      short loc_180036926
0x180036918  movzx   ecx, [rsp+6E0h+UnicodeString.Length]
0x18003691d  movzx   eax, di
0x180036920  add     rbx, rax
0x180036923  add     rbx, rcx
0x180036926  cmp     [rbp+5E0h+var_578], 0
0x18003692a  jnz     loc_180036C3B
0x180036930  add     rbx, 2
0x180036934  mov     rcx, rbx
0x180036937  call    RtlpAllocateAtom
0x18003693c  mov     rdi, rax
0x18003693f  test    rax, rax
0x180036942  jz      loc_180036A11
0x180036948  mov     r8, rbx; Size
0x18003694b  xor     edx, edx; Val
0x18003694d  mov     rcx, rax; void *
0x180036950  call    memset$thunk$772440563353939046
0x180036955  xorps   xmm0, xmm0
0x180036958  lea     rdx, [rbp+5E0h+var_460]
0x18003695f  movups  xmmword ptr [r14], xmm0
0x180036963  mov     rcx, r14
0x180036966  mov     [r14+2], bx
0x18003696b  mov     [r14+8], rdi
0x18003696f  call    RtlAppendUnicodeToString
0x180036974  mov     ebx, eax
0x180036976  test    eax, eax
0x180036978  js      loc_180036A16
0x18003697e  cmp     [rsp+6E0h+var_694], 0
0x180036983  jz      short loc_1800369AE
0x180036985  test    esi, esi
0x180036987  jnz     short loc_1800369AE
0x180036989  lea     rdx, [rsp+6E0h+var_668]
0x18003698e  mov     rcx, r14
0x180036991  call    RtlAppendUnicodeStringToString
0x180036996  mov     ebx, eax
0x180036998  test    eax, eax
0x18003699a  js      short loc_180036A16
0x18003699c  lea     rdx, [rbp+5E0h+var_648]
0x1800369a0  mov     rcx, r14
0x1800369a3  call    RtlAppendUnicodeStringToString
0x1800369a8  mov     ebx, eax
0x1800369aa  test    eax, eax
0x1800369ac  js      short loc_180036A16
0x1800369ae  cmp     [rsp+6E0h+var_69C], 0
0x1800369b3  jz      short loc_1800369DB
0x1800369b5  lea     rdx, [rsp+6E0h+var_668]
0x1800369ba  mov     rcx, r14
0x1800369bd  call    RtlAppendUnicodeStringToString
0x1800369c2  mov     ebx, eax
0x1800369c4  test    eax, eax
0x1800369c6  js      short loc_180036A16
0x1800369c8  lea     rdx, [rsp+6E0h+UnicodeString]
0x1800369cd  mov     rcx, r14
0x1800369d0  call    RtlAppendUnicodeStringToString
0x1800369d5  mov     ebx, eax
0x1800369d7  test    eax, eax
0x1800369d9  js      short loc_180036A16
0x1800369db  cmp     [rbp+5E0h+var_578], 0
0x1800369df  jz      short loc_180036A16
0x1800369e1  cmp     [rsp+6E0h+var_690], 0
0x1800369e6  jnz     short loc_180036A16
0x1800369e8  lea     rdx, [rsp+6E0h+var_668]
0x1800369ed  mov     rcx, r14
0x1800369f0  call    RtlAppendUnicodeStringToString
0x1800369f5  mov     ebx, eax
0x1800369f7  test    eax, eax
0x1800369f9  js      short loc_180036A16
0x1800369fb  lea     rdx, [rbp+5E0h+var_658]
0x1800369ff  mov     rcx, r14
0x180036a02  call    RtlAppendUnicodeStringToString
0x180036a07  movzx   r15d, [rsp+6E0h+var_6A0]
0x180036a0d  mov     ebx, eax
0x180036a0f  jmp     short loc_180036A1C
0x180036a11  mov     ebx, 0C000009Ah
0x180036a16  movzx   r15d, [rsp+6E0h+var_6A0]
0x180036a1c  mov     rcx, [rbp+5E0h+var_648.Buffer]
0x180036a20  test    rcx, rcx
0x180036a23  jz      short loc_180036A2A
0x180036a25  call    RtlpSysVolFree
0x180036a2a  test    ebx, ebx
0x180036a2c  jns     short loc_180036A36
0x180036a2e  mov     rcx, r14; UnicodeString
0x180036a31  call    RtlFreeAnsiString
0x180036a36  test    r15b, r15b
0x180036a39  mov     r15, [rsp+6E0h+arg_10]
0x180036a41  jz      short loc_180036A55
0x180036a43  mov     rdi, [rsp+6E0h+UnicodeString.Buffer]
0x180036a48  test    rdi, rdi
0x180036a4b  jz      short loc_180036A55
0x180036a4d  mov     rcx, rdi
0x180036a50  call    RtlpSysVolFree
0x180036a55  test    r12, r12
0x180036a58  jz      short loc_180036A71
0x180036a5a  mov     rcx, gs:60h
0x180036a63  mov     r8, r12
0x180036a66  xor     edx, edx
0x180036a68  mov     rcx, [rcx+30h]
0x180036a6c  call    RtlFreeHeap_0
0x180036a71  mov     eax, ebx
0x180036a73  mov     rcx, [rbp+5E0h+var_40]
0x180036a7a  xor     rcx, rsp; StackCookie
0x180036a7d  call    __security_check_cookie
0x180036a82  add     rsp, 6B0h
0x180036a89  pop     r14
0x180036a8b  pop     r13
0x180036a8d  pop     r12
0x180036a8f  pop     rdi
0x180036a90  pop     rsi
0x180036a91  pop     rbx
0x180036a92  pop     rbp
0x180036a93  retn
0x180036a95  test    al, al
0x180036a97  jnz     loc_180036BF4
0x180036a9d  test    r13d, r13d
0x180036aa0  lea     rcx, aBasenamedobjec_0; "BaseNamedObjects"
0x180036aa7  lea     rax, aAppcontainerna_0; "AppContainerNamedObjects"
0x180036aae  cmovz   rax, rcx
0x180036ab2  lea     r9, aSessions; "\\Sessions"
0x180036ab9  mov     [rsp+6E0h+var_6B8], rax
0x180036abe  lea     r8, aSLdS; "%s\\%ld\\%s"
0x180036ac5  lea     rcx, [rbp+5E0h+var_460]
0x180036acc  mov     dword ptr [rsp+6E0h+var_6C0], edi
0x180036ad0  call    RtlStringCchPrintfW
0x180036ad5  mov     r13d, [rsp+6E0h+var_69C]
0x180036ada  mov     ebx, eax
0x180036adc  jmp     loc_1800368B6
0x180036ae1  lea     rdx, [rsp+6E0h+var_68C]
0x180036ae6  mov     rcx, rdi
0x180036ae9  call    RtlGetAppContainerSidType
0x180036aee  mov     ebx, eax
0x180036af0  test    eax, eax
0x180036af2  js      short loc_180036B19
0x180036af4  cmp     [rsp+6E0h+var_68C], 2
0x180036af9  jnz     loc_180036CD8
0x180036aff  mov     r8b, 1; AllocateDestinationString
0x180036b02  lea     rcx, [rsp+6E0h+UnicodeString]; UnicodeString
0x180036b07  mov     rdx, rdi; Sid
0x180036b0a  call    RtlConvertSidToUnicodeString
0x180036b0f  mov     ebx, eax
0x180036b11  test    eax, eax
0x180036b13  jns     loc_180036806
0x180036b19  mov     r15b, 1
0x180036b1c  jmp     loc_180036A1C
0x180036b21  test    r13d, r13d
0x180036b24  jnz     loc_18003684C
  ... truncated ...
```
