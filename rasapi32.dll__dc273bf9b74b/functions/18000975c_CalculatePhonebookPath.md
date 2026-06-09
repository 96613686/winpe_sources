# CalculatePhonebookPath

- ea: `0x18000975c`
- end: `0x180009cac`
- name: `CalculatePhonebookPath`
- size: `1360`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, int *, LPCWCH *)`
- caller_count: `3`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x18000714c`
- `0x1800083dc`
- `0x180028e34`

## callees

- `0x18000975c`
- `0x180009cb4`
- `0x180009dd0`
- `0x18000b0f4`
- `0x18000d88c`
- `0x18003f3a4`
- `0x18004e580`
- `0x18004e984`
- `0x18007e5f0`
- `0x18007e650`
- `0x1800c353c`
- `0x1800c3608`
- `0x1800ded06`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000995b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000995b`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800098d4`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800098d4`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180009884`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180009917`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180009884`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180009917`
- `rtutils!TracePrintfExA` at `0x1800098ad`
- `rtutils!TracePrintfExA` at `0x180009940`
- `rtutils!TracePrintfExA` at `0x180009c1f`
- `rtutils!TracePrintfExA` at `0x180009c6f`
- `rtutils!TracePrintfExA` at `0x1800098ad`
- `rtutils!TracePrintfExA` at `0x180009940`
- `rtutils!TracePrintfExA` at `0x180009c1f`
- `rtutils!TracePrintfExA` at `0x180009c6f`

## string_xrefs

- `0x180009939`: `full path = %s`
- `0x1800098a6`: `path = %s`

## pseudocode

```c
__int64 __fastcall CalculatePhonebookPath(__int64 a1, __int64 a2, unsigned int a3, int *a4, LPCWCH *a5)
{
  char *v9; // rbx
  unsigned int UserPreferences; // ebx
  WCHAR *v11; // rax
  int PhonebookPath; // esi
  __int64 v14; // rdx
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  int v17; // [rsp+40h] [rbp-C0h] BYREF
  LPCWCH lpWideCharStr; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v19[192]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[264]; // [rsp+110h] [rbp+10h] BYREF
  CHAR MultiByteStr[512]; // [rsp+320h] [rbp+220h] BYREF

  if ( !a1 )
  {
    v9 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_3;
    if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
      goto LABEL_34;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 728, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, a3);
    goto LABEL_50;
  }
  v9 = (char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_3;
  if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      727,
      (unsigned int)&WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids,
      a1,
      a3);
LABEL_50:
    v9 = (char *)WPP_GLOBAL_Control;
  }
LABEL_34:
  if ( v9 != (char *)&WPP_GLOBAL_Control && v9[28] < 0 && (unsigned __int8)v9[25] >= 6u )
  {
    WPP_SF_(*((_QWORD *)v9 + 2), 729, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
    v9 = (char *)WPP_GLOBAL_Control;
  }
LABEL_3:
  v17 = 0;
  memset_0(Buffer, 0, 0x20Au);
  lpWideCharStr = 0;
  memset_0(v19, 0, 0xB8u);
  if ( !a4 )
  {
    if ( v9 == (char *)&WPP_GLOBAL_Control || v9[28] >= 0 || (unsigned __int8)v9[25] < 6u )
      return 87;
    v14 = 730;
    goto LABEL_59;
  }
  if ( !a5 )
  {
    if ( v9 == (char *)&WPP_GLOBAL_Control || v9[28] >= 0 || (unsigned __int8)v9[25] < 6u )
      return 87;
    v14 = 731;
LABEL_59:
    WPP_SF_(*((_QWORD *)v9 + 2), v14, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
    return 87;
  }
  UserPreferences = 0;
  if ( a1 )
  {
    v11 = (WCHAR *)StrDup(a1);
    lpWideCharStr = v11;
    if ( !v11 )
    {
      UserPreferences = 8;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || *((char *)WPP_GLOBAL_Control + 28) >= 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_44;
      }
      v16 = 732;
      goto LABEL_65;
    }
    if ( (a3 & 0x800) != 0 )
    {
      v17 = 4;
    }
    else if ( (unsigned int)IsPublicPhonebook(v11) )
    {
      v17 = 0;
    }
    else
    {
      v17 = 2 - ((unsigned int)IsPersonalPhonebook(lpWideCharStr) != 0);
    }
  }
  else
  {
    if ( a2 )
    {
      PhonebookPath = GetPhonebookPath(a2, a3, &lpWideCharStr, &v17);
    }
    else
    {
      UserPreferences = DwGetUserPreferences(v19);
      if ( UserPreferences )
        goto LABEL_44;
      PhonebookPath = GetPhonebookPath(v19, a3, &lpWideCharStr, &v17);
      DestroyUserPreferences(v19);
    }
    if ( !PhonebookPath )
    {
      UserPreferences = 621;
      goto LABEL_44;
    }
  }
  if ( g_dwTraceId != -1 )
  {
    if ( WideCharToMultiByte(0xFDE9u, 0, lpWideCharStr, -1, MultiByteStr, 512, 0, 0) <= 0 )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "TraceW1 failed");
    }
    else if ( g_dwTraceId != -1 )
    {
      TracePrintfExA(g_dwTraceId, 0xCu, "path = %s", MultiByteStr);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 733, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, lpWideCharStr);
  }
  if ( !GetFullPathNameW(lpWideCharStr, 0x105u, Buffer, 0) )
    goto LABEL_22;
  if ( g_dwTraceId != -1 )
  {
    if ( WideCharToMultiByte(0xFDE9u, 0, Buffer, -1, MultiByteStr, 512, 0, 0) <= 0 )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "TraceW1 failed");
    }
    else if ( g_dwTraceId != -1 )
    {
      TracePrintfExA(g_dwTraceId, 0xCu, "full path = %s", MultiByteStr);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 734, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, Buffer);
  }
  GlobalFree((HGLOBAL)lpWideCharStr);
  lpWideCharStr = (LPCWCH)StrDup(Buffer);
  if ( lpWideCharStr )
  {
LABEL_22:
    *a4 = v17;
    *a5 = lpWideCharStr;
    goto LABEL_23;
  }
  UserPreferences = 8;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v16 = 735;
LABEL_65:
    WPP_SF_d(v15[2], v16, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 8);
  }
LABEL_44:
  Free0(lpWideCharStr);
LABEL_23:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      736,
      &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids,
      UserPreferences);
  }
  return UserPreferences;
}

```

## disassembly

```asm
0x18000975c  push    rbp
0x18000975e  push    rbx
0x18000975f  push    rsi
0x180009760  push    rdi
0x180009761  push    r12
0x180009763  push    r13
0x180009765  push    r14
0x180009767  push    r15
0x180009769  lea     rbp, [rsp-438h]
0x180009771  sub     rsp, 538h
0x180009778  mov     rax, cs:__security_cookie
0x18000977f  xor     rax, rsp
0x180009782  mov     [rbp+470h+var_50], rax
0x180009789  mov     r12, [rbp+470h+arg_20]
0x180009790  mov     r13, r9
0x180009793  mov     esi, r8d
0x180009796  mov     r15, rdx
0x180009799  mov     r14, rcx
0x18000979c  test    rcx, rcx
0x18000979f  jnz     loc_180009A1F
0x1800097a5  mov     rbx, cs:WPP_GLOBAL_Control
0x1800097ac  lea     rdi, WPP_GLOBAL_Control
0x1800097b3  cmp     rbx, rdi
0x1800097b6  jnz     loc_180009B07
0x1800097bc  xor     edx, edx; Val
0x1800097be  mov     [rsp+570h+var_530], 0
0x1800097c6  mov     r8d, 20Ah; Size
0x1800097cc  lea     rcx, [rbp+470h+Buffer]; void *
0x1800097d0  call    memset_0
0x1800097d5  xor     edx, edx; Val
0x1800097d7  mov     [rsp+570h+lpWideCharStr], 0
0x1800097e0  mov     r8d, 0B8h; Size
0x1800097e6  lea     rcx, [rsp+570h+var_520]; void *
0x1800097eb  call    memset_0
0x1800097f0  test    r13, r13
0x1800097f3  jz      loc_180009B3F
0x1800097f9  test    r12, r12
0x1800097fc  jz      loc_180009B57
0x180009802  xor     ebx, ebx
0x180009804  test    r14, r14
0x180009807  jz      loc_180009A98
0x18000980d  mov     rcx, r14
0x180009810  call    StrDup
0x180009815  xor     r14d, r14d
0x180009818  mov     [rsp+570h+lpWideCharStr], rax
0x18000981d  test    rax, rax
0x180009820  jz      loc_180009B87
0x180009826  bt      esi, 0Bh
0x18000982a  jb      loc_1800099BA
0x180009830  mov     rcx, rax
0x180009833  call    IsPublicPhonebook
0x180009838  test    eax, eax
0x18000983a  jz      loc_180009A7E
0x180009840  mov     [rsp+570h+var_530], r14d
0x180009845  or      esi, 0FFFFFFFFh
0x180009848  mov     r15d, 0Ch
0x18000984e  cmp     cs:g_dwTraceId, esi
0x180009854  jz      short loc_1800098B3
0x180009856  mov     r8, [rsp+570h+lpWideCharStr]; lpWideCharStr
0x18000985b  lea     rax, [rbp+470h+MultiByteStr]
0x180009862  mov     [rsp+570h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x180009867  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000986b  mov     [rsp+570h+lpDefaultChar], r14; lpDefaultChar
0x180009870  xor     edx, edx; dwFlags
0x180009872  mov     [rsp+570h+cbMultiByte], 200h; cbMultiByte
0x18000987a  mov     ecx, 0FDE9h; CodePage
0x18000987f  mov     [rsp+570h+lpMultiByteStr], rax; lpMultiByteStr
0x180009884  call    cs:__imp_WideCharToMultiByte
0x18000988a  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180009890  test    eax, eax
0x180009892  jle     loc_180009C0D
0x180009898  cmp     ecx, esi
0x18000989a  jz      short loc_1800098B3
0x18000989c  lea     r9, [rbp+470h+MultiByteStr]
0x1800098a3  mov     edx, r15d; dwFlags
0x1800098a6  lea     r8, aPathS; "path = %s"
0x1800098ad  call    cs:__imp_TracePrintfExA
0x1800098b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800098ba  cmp     rcx, rdi
0x1800098bd  jnz     loc_180009C2A
0x1800098c3  mov     rcx, [rsp+570h+lpWideCharStr]; lpFileName
0x1800098c8  lea     r8, [rbp+470h+Buffer]; lpBuffer
0x1800098cc  xor     r9d, r9d; lpFilePart
0x1800098cf  mov     edx, 105h; nBufferLength
0x1800098d4  call    cs:__imp_GetFullPathNameW
0x1800098da  test    eax, eax
0x1800098dc  jz      loc_180009978
0x1800098e2  cmp     cs:g_dwTraceId, esi
0x1800098e8  jz      short loc_180009946
0x1800098ea  mov     [rsp+570h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x1800098ef  lea     rax, [rbp+470h+MultiByteStr]
0x1800098f6  mov     [rsp+570h+lpDefaultChar], r14; lpDefaultChar
0x1800098fb  lea     r8, [rbp+470h+Buffer]; lpWideCharStr
0x1800098ff  mov     [rsp+570h+cbMultiByte], 200h; cbMultiByte
0x180009907  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000990b  xor     edx, edx; dwFlags
0x18000990d  mov     [rsp+570h+lpMultiByteStr], rax; lpMultiByteStr
0x180009912  mov     ecx, 0FDE9h; CodePage
0x180009917  call    cs:__imp_WideCharToMultiByte
0x18000991d  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180009923  test    eax, eax
0x180009925  jle     loc_180009C5D
0x18000992b  cmp     ecx, esi
0x18000992d  jz      short loc_180009946
0x18000992f  lea     r9, [rbp+470h+MultiByteStr]
0x180009936  mov     edx, r15d; dwFlags
0x180009939  lea     r8, aFullPathS; "full path = %s"
0x180009940  call    cs:__imp_TracePrintfExA
0x180009946  mov     rcx, cs:WPP_GLOBAL_Control
0x18000994d  cmp     rcx, rdi
0x180009950  jnz     loc_1800099ED
0x180009956  mov     rcx, [rsp+570h+lpWideCharStr]; hMem
0x18000995b  call    cs:__imp_GlobalFree
0x180009961  lea     rcx, [rbp+470h+Buffer]
0x180009965  call    StrDup
0x18000996a  mov     [rsp+570h+lpWideCharStr], rax
0x18000996f  test    rax, rax
0x180009972  jz      loc_180009C7A
0x180009978  mov     eax, [rsp+570h+var_530]
0x18000997c  mov     [r13+0], eax
0x180009980  mov     rax, [rsp+570h+lpWideCharStr]
0x180009985  mov     [r12], rax
0x180009989  mov     rcx, cs:WPP_GLOBAL_Control
0x180009990  cmp     rcx, rdi
0x180009993  jnz     short loc_1800099C7
0x180009995  mov     eax, ebx
0x180009997  mov     rcx, [rbp+470h+var_50]
0x18000999e  xor     rcx, rsp; StackCookie
0x1800099a1  call    __security_check_cookie
0x1800099a6  add     rsp, 538h
0x1800099ad  pop     r15
0x1800099af  pop     r14
0x1800099b1  pop     r13
0x1800099b3  pop     r12
0x1800099b5  pop     rdi
0x1800099b6  pop     rsi
0x1800099b7  pop     rbx
0x1800099b8  pop     rbp
0x1800099b9  retn
0x1800099ba  mov     [rsp+570h+var_530], 4
0x1800099c2  jmp     loc_180009845
0x1800099c7  test    byte ptr [rcx+1Ch], 80h
0x1800099cb  jz      short loc_180009995
0x1800099cd  cmp     byte ptr [rcx+19h], 6
0x1800099d1  jb      short loc_180009995
0x1800099d3  mov     rcx, [rcx+10h]
0x1800099d7  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x1800099de  mov     edx, 2E0h
0x1800099e3  mov     r9d, ebx
0x1800099e6  call    WPP_SF_d
0x1800099eb  jmp     short loc_180009995
0x1800099ed  test    byte ptr [rcx+1Ch], 80h
0x1800099f1  jz      loc_180009956
0x1800099f7  cmp     byte ptr [rcx+19h], 5
0x1800099fb  jb      loc_180009956
0x180009a01  mov     rcx, [rcx+10h]
0x180009a05  lea     r9, [rbp+470h+Buffer]
0x180009a09  mov     edx, 2DEh
0x180009a0e  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180009a15  call    WPP_SF_S
0x180009a1a  jmp     loc_180009956
0x180009a1f  mov     rbx, cs:WPP_GLOBAL_Control
0x180009a26  lea     rdi, WPP_GLOBAL_Control
0x180009a2d  cmp     rbx, rdi
0x180009a30  jz      loc_1800097BC
0x180009a36  test    byte ptr [rbx+1Ch], 80h
0x180009a3a  jnz     loc_180009ADF
0x180009a40  cmp     rbx, rdi
0x180009a43  jz      loc_1800097BC
0x180009a49  test    byte ptr [rbx+1Ch], 80h
0x180009a4d  jz      loc_1800097BC
0x180009a53  cmp     byte ptr [rbx+19h], 6
0x180009a57  jb      loc_1800097BC
0x180009a5d  mov     rcx, [rbx+10h]
0x180009a61  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180009a68  mov     edx, 2D9h
0x180009a6d  call    WPP_SF_
0x180009a72  mov     rbx, cs:WPP_GLOBAL_Control
0x180009a79  jmp     loc_1800097BC
0x180009a7e  mov     rcx, [rsp+570h+lpWideCharStr]; lpString2
0x180009a83  call    IsPersonalPhonebook
0x180009a88  neg     eax
0x180009a8a  sbb     ecx, ecx
0x180009a8c  add     ecx, 2
0x180009a8f  mov     [rsp+570h+var_530], ecx
0x180009a93  jmp     loc_180009845
0x180009a98  test    r15, r15
0x180009a9b  jz      loc_180009BD0
0x180009aa1  lea     r9, [rsp+570h+var_530]
0x180009aa6  mov     edx, esi
0x180009aa8  lea     r8, [rsp+570h+lpWideCharStr]
0x180009aad  mov     rcx, r15
0x180009ab0  call    GetPhonebookPath
0x180009ab5  mov     esi, eax
0x180009ab7  test    esi, esi
0x180009ab9  jnz     loc_180009845
0x180009abf  mov     ebx, 26Dh
0x180009ac4  jmp     short loc_180009AD0
0x180009ac6  cmp     byte ptr [rcx+19h], 2
0x180009aca  jnb     loc_180009BAF
0x180009ad0  mov     rcx, [rsp+570h+lpWideCharStr]
0x180009ad5  call    Free0
0x180009ada  jmp     loc_180009989
0x180009adf  cmp     byte ptr [rbx+19h], 6
0x180009ae3  jb      loc_180009A40
0x180009ae9  mov     rcx, [rbx+10h]
0x180009aed  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180009af4  mov     edx, 2D7h
0x180009af9  mov     dword ptr [rsp+570h+lpMultiByteStr], esi
0x180009afd  mov     r9, r14
0x180009b00  call    WPP_SF_Sd
0x180009b05  jmp     short loc_180009B33
0x180009b07  test    byte ptr [rbx+1Ch], 80h
0x180009b0b  jz      loc_180009A40
0x180009b11  cmp     byte ptr [rbx+19h], 6
0x180009b15  jb      loc_180009A40
0x180009b1b  mov     rcx, [rbx+10h]
0x180009b1f  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180009b26  mov     edx, 2D8h
0x180009b2b  mov     r9d, esi
0x180009b2e  call    WPP_SF_d
0x180009b33  mov     rbx, cs:WPP_GLOBAL_Control
0x180009b3a  jmp     loc_180009A40
0x180009b3f  cmp     rbx, rdi
0x180009b42  jz      short loc_180009B7D
0x180009b44  test    byte ptr [rbx+1Ch], 80h
0x180009b48  jz      short loc_180009B7D
0x180009b4a  cmp     byte ptr [rbx+19h], 6
0x180009b4e  jb      short loc_180009B7D
0x180009b50  mov     edx, 2DAh
0x180009b55  jmp     short loc_180009B6D
0x180009b57  cmp     rbx, rdi
0x180009b5a  jz      short loc_180009B7D
0x180009b5c  test    byte ptr [rbx+1Ch], 80h
0x180009b60  jz      short loc_180009B7D
0x180009b62  cmp     byte ptr [rbx+19h], 6
0x180009b66  jb      short loc_180009B7D
0x180009b68  mov     edx, 2DBh
0x180009b6d  mov     rcx, [rbx+10h]
0x180009b71  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180009b78  call    WPP_SF_
0x180009b7d  mov     eax, 57h ; 'W'
0x180009b82  jmp     loc_180009997
0x180009b87  mov     r9d, 8
0x180009b8d  mov     ebx, r9d
0x180009b90  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b97  cmp     rcx, rdi
0x180009b9a  jz      loc_180009AD0
0x180009ba0  test    byte ptr [rcx+1Ch], 80h
0x180009ba4  jz      loc_180009AD0
0x180009baa  jmp     loc_180009AC6
0x180009baf  mov     edx, 2DCh
0x180009bb4  jmp     short loc_180009BBB
0x180009bb6  mov     edx, 2DFh
0x180009bbb  mov     rcx, [rcx+10h]
0x180009bbf  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180009bc6  call    WPP_SF_d
0x180009bcb  jmp     loc_180009AD0
0x180009bd0  xor     edx, edx
0x180009bd2  lea     rcx, [rsp+570h+var_520]; void *
0x180009bd7  call    DwGetUserPreferences
0x180009bdc  mov     ebx, eax
0x180009bde  test    eax, eax
0x180009be0  jnz     loc_180009AD0
0x180009be6  lea     r9, [rsp+570h+var_530]
0x180009beb  mov     edx, esi
0x180009bed  lea     r8, [rsp+570h+lpWideCharStr]
0x180009bf2  lea     rcx, [rsp+570h+var_520]
0x180009bf7  call    GetPhonebookPath
0x180009bfc  lea     rcx, [rsp+570h+var_520]; void *
0x180009c01  mov     esi, eax
0x180009c03  call    DestroyUserPreferences
0x180009c08  jmp     loc_180009AB7
0x180009c0d  cmp     ecx, esi
0x180009c0f  jz      loc_1800098B3
0x180009c15  lea     r8, aTracew1Failed; "TraceW1 failed"
0x180009c1c  mov     edx, r15d; dwFlags
0x180009c1f  call    cs:__imp_TracePrintfExA
0x180009c25  jmp     loc_1800098B3
0x180009c2a  test    byte ptr [rcx+1Ch], 80h
0x180009c2e  jz      loc_1800098C3
0x180009c34  cmp     byte ptr [rcx+19h], 5
0x180009c38  jb      loc_1800098C3
0x180009c3e  mov     r9, [rsp+570h+lpWideCharStr]
0x180009c43  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180009c4a  mov     rcx, [rcx+10h]
0x180009c4e  mov     edx, 2DDh
0x180009c53  call    WPP_SF_S
0x180009c58  jmp     loc_1800098C3
0x180009c5d  cmp     ecx, esi
0x180009c5f  jz      loc_180009946
0x180009c65  lea     r8, aTracew1Failed; "TraceW1 failed"
0x180009c6c  mov     edx, r15d; dwFlags
0x180009c6f  call    cs:__imp_TracePrintfExA
0x180009c75  jmp     loc_180009946
0x180009c7a  mov     r9d, 8
0x180009c80  mov     ebx, r9d
0x180009c83  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c8a  cmp     rcx, rdi
0x180009c8d  jz      loc_180009AD0
  ... truncated ...
```
