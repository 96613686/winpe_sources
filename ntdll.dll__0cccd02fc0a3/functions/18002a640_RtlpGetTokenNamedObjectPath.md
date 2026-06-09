# RtlpGetTokenNamedObjectPath

- ea: `0x18002a640`
- end: `0x18002ad7d`
- name: `RtlpGetTokenNamedObjectPath`
- size: `1853`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002b040`
- `0x180101420`

## callees

- `0x180015710`
- `0x18001861c`
- `0x18001d490`
- `0x180021fe0`
- `0x18002a640`
- `0x18002ad90`
- `0x18002ae28`
- `0x18002af40`
- `0x18002b300`
- `0x180036e70`
- `0x1800526f0`
- `0x18005a9f0`
- `0x18012c830`
- `0x18015e6f0`
- `0x180162000`
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
            v36 = &dword_1801764CC;
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
0x18002a640  push    rbp
0x18002a642  push    rbx
0x18002a643  push    rsi
0x18002a644  push    rdi
0x18002a645  push    r12
0x18002a647  push    r13
0x18002a649  push    r14
0x18002a64b  lea     rbp, [rsp-5B0h]
0x18002a653  sub     rsp, 6B0h
0x18002a65a  mov     rax, cs:__security_cookie
0x18002a661  xor     rax, rsp
0x18002a664  mov     [rbp+5E0h+var_40], rax
0x18002a66b  xor     ebx, ebx
0x18002a66d  mov     [rsp+6E0h+var_690], r8d
0x18002a672  mov     r13d, r8d
0x18002a675  mov     [rsp+6E0h+var_68C], ebx
0x18002a679  mov     rdi, rdx
0x18002a67c  mov     [rsp+6E0h+var_670], rbx
0x18002a681  mov     rsi, rcx
0x18002a684  xor     edx, edx; Val
0x18002a686  mov     r8d, 50h ; 'P'; Size
0x18002a68c  lea     rcx, [rbp+5E0h+var_5D0]; void *
0x18002a690  mov     r12d, ebx
0x18002a693  mov     r14, r9
0x18002a696  call    memset$thunk$772440563353939046
0x18002a69b  xor     edx, edx; Val
0x18002a69d  mov     [rsp+6E0h+var_698], ebx
0x18002a6a1  mov     r8d, 208h; Size
0x18002a6a7  mov     [rsp+6E0h+var_688], ebx
0x18002a6ab  lea     rcx, [rbp+5E0h+var_460]; void *
0x18002a6b2  call    memset$thunk$772440563353939046
0x18002a6b7  xor     edx, edx; Val
0x18002a6b9  lea     rcx, [rbp+5E0h+var_250]; void *
0x18002a6c0  mov     r8d, 208h; Size
0x18002a6c6  call    memset$thunk$772440563353939046
0x18002a6cb  xor     edx, edx; Val
0x18002a6cd  lea     rcx, [rbp+5E0h+Sid]; void *
0x18002a6d1  mov     r8d, 58h ; 'X'; Size
0x18002a6d7  call    memset$thunk$772440563353939046
0x18002a6dc  mov     [rsp+6E0h+var_668], 40002h
0x18002a6e5  xorps   xmm0, xmm0
0x18002a6e8  lea     rax, asc_180177BA4; "\\"
0x18002a6ef  mov     [rbp+5E0h+var_660], rax
0x18002a6f3  movups  [rbp+5E0h+var_658], xmm0
0x18002a6f7  test    r14, r14
0x18002a6fa  jz      loc_18002AD73
0x18002a700  test    rsi, rsi
0x18002a703  jz      loc_18002AD73
0x18002a709  mov     [rsp+6E0h+arg_10], r15
0x18002a711  mov     r15b, 1
0x18002a714  mov     [rsp+6E0h+var_6A0], r15b
0x18002a719  xorps   xmm1, xmm1
0x18002a71c  mov     [rsp+6E0h+var_69C], ebx
0x18002a720  mov     [rsp+6E0h+var_694], ebx
0x18002a724  movups  xmmword ptr [r14], xmm0
0x18002a728  movups  xmmword ptr [rsp+6E0h+UnicodeString.Length], xmm0
0x18002a72d  movups  xmmword ptr [rbp+5E0h+var_648.Length], xmm1
0x18002a731  test    rdi, rdi
0x18002a734  jz      loc_18002AAEE
0x18002a73a  mov     [rsp+6E0h+var_69C], 1
0x18002a742  lea     rax, [rsp+6E0h+var_698]
0x18002a747  mov     r9d, 4
0x18002a74d  lea     r8, [rsp+6E0h+var_694]
0x18002a752  mov     [rsp+6E0h+var_6C0], rax
0x18002a757  mov     edx, 2Ah ; '*'
0x18002a75c  mov     rcx, rsi
0x18002a75f  call    NtQueryInformationToken
0x18002a764  mov     ebx, eax
0x18002a766  test    eax, eax
0x18002a768  js      loc_18002A9DE
0x18002a76e  cmp     [rsp+6E0h+var_694], r12d
0x18002a773  jnz     loc_18002AC3D
0x18002a779  lea     rax, [rsp+6E0h+var_698]
0x18002a77e  mov     r9d, 4
0x18002a784  lea     r8, [rsp+6E0h+var_688]
0x18002a789  mov     [rsp+6E0h+var_6C0], rax
0x18002a78e  mov     edx, 0Ch
0x18002a793  mov     rcx, rsi
0x18002a796  call    NtQueryInformationToken
0x18002a79b  mov     ebx, eax
0x18002a79d  test    eax, eax
0x18002a79f  js      loc_18002A9CC
0x18002a7a5  mov     r15d, 104h
0x18002a7ab  cmp     [rsp+6E0h+var_69C], r12d
0x18002a7b0  jnz     loc_18002AA91
0x18002a7b6  lea     rax, [rsp+6E0h+var_698]
0x18002a7bb  mov     r9d, 120h
0x18002a7c1  lea     r8, [rbp+5E0h+String]
0x18002a7c5  mov     [rsp+6E0h+var_6C0], rax
0x18002a7ca  mov     edx, 2Ch ; ','
0x18002a7cf  mov     rcx, rsi
0x18002a7d2  call    NtQueryInformationToken
0x18002a7d7  mov     ebx, eax
0x18002a7d9  test    eax, eax
0x18002a7db  js      loc_18002A9C6
0x18002a7e1  mov     edi, [rsp+6E0h+var_688]
0x18002a7e5  movzx   ebx, r13b
0x18002a7e9  mov     r13d, [rsp+6E0h+var_69C]
0x18002a7ee  and     bl, 1
0x18002a7f1  cmp     [rsp+6E0h+var_694], 0
0x18002a7f6  jz      loc_18002AAD1
0x18002a7fc  xor     al, al
0x18002a7fe  mov     rdx, r15
0x18002a801  test    bl, bl
0x18002a803  jz      loc_18002AA45
0x18002a809  test    byte ptr [rsp+6E0h+var_690], 4
0x18002a80e  jz      loc_18002AB68
0x18002a814  mov     ecx, 7FFFFFFEh
0x18002a819  lea     rax, aAppcontainerna_0; "AppContainerNamedObjects"
0x18002a820  lea     r8, [rbp+5E0h+var_460]
0x18002a827  test    rcx, rcx
0x18002a82a  jz      short loc_18002A84B
0x18002a82c  movzx   r9d, word ptr [rax]
0x18002a830  test    r9w, r9w
0x18002a834  jz      short loc_18002A84B
0x18002a836  mov     [r8], r9w
0x18002a83a  add     rax, 2
0x18002a83e  add     r8, 2
0x18002a842  dec     rcx
0x18002a845  sub     rdx, 1
0x18002a849  jnz     short loc_18002A827
0x18002a84b  test    rdx, rdx
0x18002a84e  lea     rcx, [r8-2]
0x18002a852  cmovnz  rcx, r8
0x18002a856  xor     eax, eax
0x18002a858  mov     ebx, 80000005h
0x18002a85d  test    rdx, rdx
0x18002a860  mov     [rcx], ax
0x18002a863  cmovnz  ebx, eax
0x18002a866  test    ebx, ebx
0x18002a868  js      loc_18002A9C6
0x18002a86e  mov     rcx, r15
0x18002a871  lea     rax, [rbp+5E0h+var_460]
0x18002a878  cmp     word ptr [rax], 0
0x18002a87c  jz      short loc_18002A888
0x18002a87e  add     rax, 2
0x18002a882  sub     rcx, 1
0x18002a886  jnz     short loc_18002A878
0x18002a888  xor     eax, eax
0x18002a88a  mov     ebx, 0C000000Dh
0x18002a88f  test    rcx, rcx
0x18002a892  cmovnz  ebx, eax
0x18002a895  jz      loc_18002A9C6
0x18002a89b  mov     edx, [rsp+6E0h+var_690]
0x18002a89f  sub     r15, rcx
0x18002a8a2  mov     esi, edx
0x18002a8a4  add     r15, r15
0x18002a8a7  and     edx, 8
0x18002a8aa  and     esi, 2
0x18002a8ad  mov     edi, 2
0x18002a8b2  mov     [rsp+6E0h+var_690], edx
0x18002a8b6  cmp     [rsp+6E0h+var_694], eax
0x18002a8ba  jnz     loc_18002AD59
0x18002a8c0  mov     rbx, r15
0x18002a8c3  test    r13d, r13d
0x18002a8c6  jz      short loc_18002A8D6
0x18002a8c8  movzx   ecx, [rsp+6E0h+UnicodeString.Length]
0x18002a8cd  movzx   eax, di
0x18002a8d0  add     rbx, rax
0x18002a8d3  add     rbx, rcx
0x18002a8d6  cmp     [rbp+5E0h+var_578], 0
0x18002a8da  jnz     loc_18002ABEB
0x18002a8e0  add     rbx, 2
0x18002a8e4  mov     rcx, rbx
0x18002a8e7  call    RtlpAllocateAtom
0x18002a8ec  mov     rdi, rax
0x18002a8ef  test    rax, rax
0x18002a8f2  jz      loc_18002A9C1
0x18002a8f8  mov     r8, rbx; Size
0x18002a8fb  xor     edx, edx; Val
0x18002a8fd  mov     rcx, rax; void *
0x18002a900  call    memset$thunk$772440563353939046
0x18002a905  xorps   xmm0, xmm0
0x18002a908  lea     rdx, [rbp+5E0h+var_460]
0x18002a90f  movups  xmmword ptr [r14], xmm0
0x18002a913  mov     rcx, r14
0x18002a916  mov     [r14+2], bx
0x18002a91b  mov     [r14+8], rdi
0x18002a91f  call    RtlAppendUnicodeToString
0x18002a924  mov     ebx, eax
0x18002a926  test    eax, eax
0x18002a928  js      loc_18002A9C6
0x18002a92e  cmp     [rsp+6E0h+var_694], 0
0x18002a933  jz      short loc_18002A95E
0x18002a935  test    esi, esi
0x18002a937  jnz     short loc_18002A95E
0x18002a939  lea     rdx, [rsp+6E0h+var_668]
0x18002a93e  mov     rcx, r14
0x18002a941  call    RtlAppendUnicodeStringToString
0x18002a946  mov     ebx, eax
0x18002a948  test    eax, eax
0x18002a94a  js      short loc_18002A9C6
0x18002a94c  lea     rdx, [rbp+5E0h+var_648]
0x18002a950  mov     rcx, r14
0x18002a953  call    RtlAppendUnicodeStringToString
0x18002a958  mov     ebx, eax
0x18002a95a  test    eax, eax
0x18002a95c  js      short loc_18002A9C6
0x18002a95e  cmp     [rsp+6E0h+var_69C], 0
0x18002a963  jz      short loc_18002A98B
0x18002a965  lea     rdx, [rsp+6E0h+var_668]
0x18002a96a  mov     rcx, r14
0x18002a96d  call    RtlAppendUnicodeStringToString
0x18002a972  mov     ebx, eax
0x18002a974  test    eax, eax
0x18002a976  js      short loc_18002A9C6
0x18002a978  lea     rdx, [rsp+6E0h+UnicodeString]
0x18002a97d  mov     rcx, r14
0x18002a980  call    RtlAppendUnicodeStringToString
0x18002a985  mov     ebx, eax
0x18002a987  test    eax, eax
0x18002a989  js      short loc_18002A9C6
0x18002a98b  cmp     [rbp+5E0h+var_578], 0
0x18002a98f  jz      short loc_18002A9C6
0x18002a991  cmp     [rsp+6E0h+var_690], 0
0x18002a996  jnz     short loc_18002A9C6
0x18002a998  lea     rdx, [rsp+6E0h+var_668]
0x18002a99d  mov     rcx, r14
0x18002a9a0  call    RtlAppendUnicodeStringToString
0x18002a9a5  mov     ebx, eax
0x18002a9a7  test    eax, eax
0x18002a9a9  js      short loc_18002A9C6
0x18002a9ab  lea     rdx, [rbp+5E0h+var_658]
0x18002a9af  mov     rcx, r14
0x18002a9b2  call    RtlAppendUnicodeStringToString
0x18002a9b7  movzx   r15d, [rsp+6E0h+var_6A0]
0x18002a9bd  mov     ebx, eax
0x18002a9bf  jmp     short loc_18002A9CC
0x18002a9c1  mov     ebx, 0C000009Ah
0x18002a9c6  movzx   r15d, [rsp+6E0h+var_6A0]
0x18002a9cc  mov     rcx, [rbp+5E0h+var_648.Buffer]
0x18002a9d0  test    rcx, rcx
0x18002a9d3  jz      short loc_18002A9DA
0x18002a9d5  call    RtlpSysVolFree
0x18002a9da  test    ebx, ebx
0x18002a9dc  jns     short loc_18002A9E6
0x18002a9de  mov     rcx, r14; UnicodeString
0x18002a9e1  call    RtlFreeAnsiString
0x18002a9e6  test    r15b, r15b
0x18002a9e9  mov     r15, [rsp+6E0h+arg_10]
0x18002a9f1  jz      short loc_18002AA05
0x18002a9f3  mov     rdi, [rsp+6E0h+UnicodeString.Buffer]
0x18002a9f8  test    rdi, rdi
0x18002a9fb  jz      short loc_18002AA05
0x18002a9fd  mov     rcx, rdi
0x18002aa00  call    RtlpSysVolFree
0x18002aa05  test    r12, r12
0x18002aa08  jz      short loc_18002AA21
0x18002aa0a  mov     rcx, gs:60h
0x18002aa13  mov     r8, r12
0x18002aa16  xor     edx, edx
0x18002aa18  mov     rcx, [rcx+30h]
0x18002aa1c  call    RtlFreeHeap_0
0x18002aa21  mov     eax, ebx
0x18002aa23  mov     rcx, [rbp+5E0h+var_40]
0x18002aa2a  xor     rcx, rsp; StackCookie
0x18002aa2d  call    __security_check_cookie
0x18002aa32  add     rsp, 6B0h
0x18002aa39  pop     r14
0x18002aa3b  pop     r13
0x18002aa3d  pop     r12
0x18002aa3f  pop     rdi
0x18002aa40  pop     rsi
0x18002aa41  pop     rbx
0x18002aa42  pop     rbp
0x18002aa43  retn
0x18002aa45  test    al, al
0x18002aa47  jnz     loc_18002ABA4
0x18002aa4d  test    r13d, r13d
0x18002aa50  lea     rcx, aBasenamedobjec_0; "BaseNamedObjects"
0x18002aa57  lea     rax, aAppcontainerna_0; "AppContainerNamedObjects"
0x18002aa5e  cmovz   rax, rcx
0x18002aa62  lea     r9, aSessions; "\\Sessions"
0x18002aa69  mov     [rsp+6E0h+var_6B8], rax
0x18002aa6e  lea     r8, aSLdS; "%s\\%ld\\%s"
0x18002aa75  lea     rcx, [rbp+5E0h+var_460]
0x18002aa7c  mov     dword ptr [rsp+6E0h+var_6C0], edi
0x18002aa80  call    RtlStringCchPrintfW
0x18002aa85  mov     r13d, [rsp+6E0h+var_69C]
0x18002aa8a  mov     ebx, eax
0x18002aa8c  jmp     loc_18002A866
0x18002aa91  lea     rdx, [rsp+6E0h+var_68C]
0x18002aa96  mov     rcx, rdi
0x18002aa99  call    RtlGetAppContainerSidType
0x18002aa9e  mov     ebx, eax
0x18002aaa0  test    eax, eax
0x18002aaa2  js      short loc_18002AAC9
0x18002aaa4  cmp     [rsp+6E0h+var_68C], 2
0x18002aaa9  jnz     loc_18002AC88
0x18002aaaf  mov     r8b, 1; AllocateDestinationString
0x18002aab2  lea     rcx, [rsp+6E0h+UnicodeString]; UnicodeString
0x18002aab7  mov     rdx, rdi; Sid
0x18002aaba  call    RtlConvertSidToUnicodeString
0x18002aabf  mov     ebx, eax
0x18002aac1  test    eax, eax
0x18002aac3  jns     loc_18002A7B6
0x18002aac9  mov     r15b, 1
0x18002aacc  jmp     loc_18002A9CC
0x18002aad1  test    r13d, r13d
0x18002aad4  jnz     loc_18002A7FC
  ... truncated ...
```
