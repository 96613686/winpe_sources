# DavShouldStartWebclientService

- ea: `0x1800051e0`
- end: `0x1800056ce`
- name: `DavShouldStartWebclientService`
- size: `1262`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, service_task`

## callers

- `0x180004340`
- `0x180007ad0`

## callees

- `0x1800051e0`
- `0x1800056e0`
- `0x180005a50`
- `0x180006130`
- `0x180010a14`
- `0x180010be8`
- `0x180010c28`
- `0x180011340`
- `0x1800117f0`
- `0x180011e76`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800054d4`
- `msvcrt!_wcsicmp` at `0x1800054d4`
- `ntdll!RtlReleaseResource` at `0x180005511`
- `ntdll!RtlReleaseResource` at `0x180005565`
- `ntdll!RtlReleaseResource` at `0x180005511`
- `ntdll!RtlReleaseResource` at `0x180005565`
- `ntdll!RtlAcquireResourceShared` at `0x18000549f`
- `ntdll!RtlAcquireResourceShared` at `0x18000549f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000535a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000535a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053a5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180005484`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180005484`
- `KERNEL32!LocalAlloc` at `0x1800052cb`
- `KERNEL32!LocalAlloc` at `0x18000534c`
- `KERNEL32!LocalAlloc` at `0x1800052cb`
- `KERNEL32!LocalAlloc` at `0x18000534c`
- `KERNEL32!LocalFree` at `0x180005675`
- `KERNEL32!LocalFree` at `0x1800056a1`
- `KERNEL32!LocalFree` at `0x1800056bc`
- `KERNEL32!LocalFree` at `0x180005675`
- `KERNEL32!LocalFree` at `0x1800056a1`
- `KERNEL32!LocalFree` at `0x1800056bc`
- `DAVHLPR!DavParseUncServerName` at `0x18000544e`
- `DAVHLPR!DavParseUncServerName` at `0x18000544e`

## pseudocode

```c
__int64 __fastcall DavShouldStartWebclientService(__int64 a1)
{
  unsigned int v2; // r12d
  char *v3; // rbx
  unsigned __int8 v4; // bp
  char *v5; // r14
  _QWORD *v6; // rcx
  __int16 v7; // dx
  unsigned __int64 v8; // rax
  const void *v9; // rsi
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdi
  char *v14; // rax
  DWORD LastError; // eax
  unsigned int v16; // eax
  unsigned int v17; // edi
  char *v18; // rax
  DWORD v19; // eax
  __int64 v20; // rdx
  _QWORD *v21; // rcx
  char *v22; // rdi
  int v23; // edi
  wchar_t *v24; // rsi
  ULONGLONG TickCount64; // r15
  __int64 v26; // r13
  int v27; // r8d
  DWORD DoesServerDoDav; // eax
  int v29; // r8d
  __int64 v30; // rcx
  const char *v31; // r9
  unsigned __int8 v33; // [rsp+80h] [rbp+8h] BYREF
  bool v34; // [rsp+88h] [rbp+10h] BYREF
  unsigned int v35; // [rsp+90h] [rbp+18h] BYREF
  wchar_t *String2; // [rsp+98h] [rbp+20h] BYREF

  v2 = 0;
  v3 = 0;
  v34 = 0;
  v4 = 0;
  v33 = 0;
  v5 = 0;
  String2 = 0;
  v35 = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_db9184fc95f634e81eb114a7689fd6a6_Traceguids, a1);
    v6 = WPP_GLOBAL_Control;
  }
  v7 = *(_WORD *)(a1 + 4);
  v8 = a1 + 4;
  v9 = (const void *)(a1 + 4);
  if ( v7 == 92 )
    goto LABEL_83;
  do
  {
    if ( !v7 )
      break;
    v7 = *(_WORD *)(v8 + 2);
    v8 += 2LL;
  }
  while ( v7 != 92 );
  if ( v8 >= (unsigned __int64)v9 )
  {
LABEL_83:
    v10 = (__int64)(v8 - (_QWORD)v9) >> 1;
    if ( v10 <= 0x104 )
    {
      v11 = v10 + 1;
      if ( v11 > 0x105 )
      {
        if ( v6 == &WPP_GLOBAL_Control )
          goto LABEL_76;
        if ( (*((_BYTE *)v6 + 28) & 1) != 0 )
        {
          v12 = 12;
LABEL_67:
          WPP_SF_(v6[2], v12, WPP_db9184fc95f634e81eb114a7689fd6a6_Traceguids);
          goto LABEL_68;
        }
        goto LABEL_69;
      }
      v13 = 2 * v11;
      v14 = (char *)LocalAlloc(0x40u, 2 * v11);
      v3 = v14;
      if ( !v14 )
      {
        LastError = GetLastError();
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_76;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_69;
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_db9184fc95f634e81eb114a7689fd6a6_Traceguids, LastError);
LABEL_68:
        v6 = WPP_GLOBAL_Control;
        goto LABEL_69;
      }
      memcpy_0(v14, v9, v13 - 2);
      *(_WORD *)&v3[v13 - 2] = 0;
      v16 = DavConvertIDNToPunyCode(v3, 0, 0);
      v17 = v16;
      if ( v16 )
      {
        v18 = (char *)LocalAlloc(0x40u, 2LL * v16);
        v5 = v18;
        if ( !v18 )
        {
          v19 = GetLastError();
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_69;
            v20 = 14;
            goto LABEL_22;
          }
          goto LABEL_75;
        }
        DavConvertIDNToPunyCode(v3, v18, v17);
        v19 = GetLastError();
        if ( v19 )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_69;
            v20 = 15;
LABEL_22:
            WPP_SF_d(v6[2], v20, WPP_db9184fc95f634e81eb114a7689fd6a6_Traceguids, v19);
            goto LABEL_68;
          }
LABEL_75:
          LocalFree(v3);
          goto LABEL_76;
        }
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_db9184fc95f634e81eb114a7689fd6a6_Traceguids, v5);
          v21 = WPP_GLOBAL_Control;
        }
        v22 = v5;
      }
      else
      {
        v21 = WPP_GLOBAL_Control;
        v22 = v3;
      }
      if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 2) != 0 )
        WPP_SF_S(v21[2], 17, WPP_db9184fc95f634e81eb114a7689fd6a6_Traceguids, v22);
      if ( (unsigned int)DavParseUncServerName(v22, &v33, &String2, &v35) )
        goto LABEL_68;
      v23 = v35;
      if ( !v35 )
      {
        v23 = 80;
        if ( v33 )
          v23 = 443;
      }
      v24 = String2;
      TickCount64 = GetTickCount64();
      if ( !v24 )
      {
LABEL_53:
        DoesServerDoDav = DavDoesServerDoDav(String2, v35, v33, &v34);
        if ( v34
          || DoesServerDoDav == 12015
          || DoesServerDoDav == 5
          || DoesServerDoDav == 12044
          || DoesServerDoDav == 12175
          || DoesServerDoDav == 1920 )
        {
          v4 = 1;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_Sl(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, v29, (_DWORD)String2, v23);
          RefreshDavclientCache(String2);
        }
        goto LABEL_68;
      }
      RtlAcquireResourceShared(&DavclientCacheLock, 1u);
      while ( 1 )
      {
        if ( v2 >= 0xA )
          goto LABEL_52;
        v26 = 67LL * v2;
        if ( BYTE4(DavclientCache[v26 + 66]) )
        {
          if ( !_wcsicmp((const wchar_t *)&DavclientCache[v26 + 1], v24) && LODWORD(DavclientCache[v26 + 66]) == v23 )
            break;
        }
        ++v2;
      }
      if ( TickCount64 > 0x493E0 && TickCount64 - 300000 > DavclientCache[67 * v2] )
      {
LABEL_52:
        RtlReleaseResource(&DavclientCacheLock);
        goto LABEL_53;
      }
      RtlReleaseResource(&DavclientCacheLock);
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_75;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_Sl(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, v27, (_DWORD)String2, v23);
        goto LABEL_68;
      }
      goto LABEL_69;
    }
  }
  if ( v6 == &WPP_GLOBAL_Control )
    goto LABEL_76;
  if ( (*((_BYTE *)v6 + 28) & 1) != 0 )
  {
    v12 = 11;
    goto LABEL_67;
  }
LABEL_69:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 )
  {
    v30 = v6[2];
    v31 = "TRUE";
    if ( !v34 )
      v31 = "FALSE";
    WPP_SF_s(v30, 20, WPP_db9184fc95f634e81eb114a7689fd6a6_Traceguids, v31);
  }
  if ( v3 )
    goto LABEL_75;
LABEL_76:
  if ( String2 )
  {
    LocalFree(String2);
    String2 = 0;
  }
  if ( v5 )
    LocalFree(v5);
  return v4;
}

```

## disassembly

```asm
0x1800051e0  mov     rax, rsp
0x1800051e3  push    rbp
0x1800051e4  push    r14
0x1800051e6  sub     rsp, 68h
0x1800051ea  mov     [rax-18h], rbx
0x1800051ee  mov     [rax-20h], rsi
0x1800051f2  mov     [rax-28h], rdi
0x1800051f6  mov     rdi, rcx
0x1800051f9  mov     [rax-30h], r12
0x1800051fd  xor     r12d, r12d
0x180005200  mov     ebx, r12d
0x180005203  mov     [rax-38h], r13
0x180005207  mov     [rax+10h], bl
0x18000520a  xor     bpl, bpl
0x18000520d  mov     [rax+8], bl
0x180005210  mov     r14d, r12d
0x180005213  mov     [rax+20h], r12
0x180005217  mov     [rax+18h], r12d
0x18000521b  mov     rcx, cs:WPP_GLOBAL_Control
0x180005222  lea     r13, WPP_GLOBAL_Control
0x180005229  cmp     rcx, r13
0x18000522c  jz      short loc_180005253
0x18000522e  test    byte ptr [rcx+1Ch], 20h
0x180005232  jz      short loc_180005253
0x180005234  mov     rcx, [rcx+10h]
0x180005238  lea     r8, WPP_db9184fc95f634e81eb114a7689fd6a6_Traceguids
0x18000523f  mov     edx, 0Ah
0x180005244  mov     r9, rdi
0x180005247  call    WPP_SF_S
0x18000524c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005253  movzx   edx, word ptr [rdi+4]
0x180005257  lea     rax, [rdi+4]
0x18000525b  mov     [rsp+78h+var_40], r15
0x180005260  mov     rsi, rax
0x180005263  cmp     dx, 5Ch ; '\'
0x180005267  jz      short loc_180005285
0x180005269  test    dx, dx
0x18000526c  jz      short loc_18000527C
0x18000526e  movzx   edx, word ptr [rax+2]
0x180005272  add     rax, 2
0x180005276  cmp     dx, 5Ch ; '\'
0x18000527a  jnz     short loc_180005269
0x18000527c  cmp     rax, rsi
0x18000527f  jb      loc_180005607
0x180005285  sub     rax, rsi
0x180005288  sar     rax, 1
0x18000528b  cmp     rax, 104h
0x180005291  ja      loc_180005607
0x180005297  inc     rax
0x18000529a  cmp     rax, 105h
0x1800052a0  jbe     short loc_1800052BF
0x1800052a2  cmp     rcx, r13
0x1800052a5  jz      loc_18000567B
0x1800052ab  test    byte ptr [rcx+1Ch], 1
0x1800052af  jz      loc_18000562E
0x1800052b5  mov     edx, 0Ch
0x1800052ba  jmp     loc_180005617
0x1800052bf  lea     rdi, [rax+rax]
0x1800052c3  mov     ecx, 40h ; '@'; uFlags
0x1800052c8  mov     rdx, rdi; uBytes
0x1800052cb  call    cs:__imp_LocalAlloc
0x1800052d1  mov     rbx, rax
0x1800052d4  test    rax, rax
0x1800052d7  jnz     short loc_180005316
0x1800052d9  call    cs:__imp_GetLastError
0x1800052df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800052e6  cmp     rcx, r13
0x1800052e9  jz      loc_18000567B
0x1800052ef  test    byte ptr [rcx+1Ch], 1
0x1800052f3  jz      loc_18000562E
0x1800052f9  mov     rcx, [rcx+10h]
0x1800052fd  lea     r8, WPP_db9184fc95f634e81eb114a7689fd6a6_Traceguids
0x180005304  mov     edx, 0Dh
0x180005309  mov     r9d, eax
0x18000530c  call    WPP_SF_d
0x180005311  jmp     loc_180005627
0x180005316  lea     r8, [rdi-2]; Size
0x18000531a  mov     rdx, rsi; Src
0x18000531d  mov     rcx, rbx; void *
0x180005320  call    memcpy_0
0x180005325  xor     r8d, r8d
0x180005328  mov     [rdi+rbx-2], r12w
0x18000532e  xor     edx, edx
0x180005330  mov     rcx, rbx
0x180005333  call    DavConvertIDNToPunyCode
0x180005338  mov     edi, eax
0x18000533a  test    eax, eax
0x18000533c  jz      loc_180005406
0x180005342  mov     edx, edi
0x180005344  mov     ecx, 40h ; '@'; uFlags
0x180005349  add     rdx, rdx; uBytes
0x18000534c  call    cs:__imp_LocalAlloc
0x180005352  mov     r14, rax
0x180005355  test    rax, rax
0x180005358  jnz     short loc_180005397
0x18000535a  call    cs:__imp_GetLastError
0x180005360  mov     rcx, cs:WPP_GLOBAL_Control
0x180005367  cmp     rcx, r13
0x18000536a  jz      loc_180005672
0x180005370  test    byte ptr [rcx+1Ch], 1
0x180005374  jz      loc_18000562E
0x18000537a  mov     edx, 0Eh
0x18000537f  mov     rcx, [rcx+10h]
0x180005383  lea     r8, WPP_db9184fc95f634e81eb114a7689fd6a6_Traceguids
0x18000538a  mov     r9d, eax
0x18000538d  call    WPP_SF_d
0x180005392  jmp     loc_180005627
0x180005397  mov     r8d, edi
0x18000539a  mov     rdx, r14
0x18000539d  mov     rcx, rbx
0x1800053a0  call    DavConvertIDNToPunyCode
0x1800053a5  call    cs:__imp_GetLastError
0x1800053ab  test    eax, eax
0x1800053ad  jz      short loc_1800053D0
0x1800053af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800053b6  cmp     rcx, r13
0x1800053b9  jz      loc_180005672
0x1800053bf  test    byte ptr [rcx+1Ch], 1
0x1800053c3  jz      loc_18000562E
0x1800053c9  mov     edx, 0Fh
0x1800053ce  jmp     short loc_18000537F
0x1800053d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800053d7  cmp     rcx, r13
0x1800053da  jz      short loc_180005401
0x1800053dc  test    byte ptr [rcx+1Ch], 2
0x1800053e0  jz      short loc_180005401
0x1800053e2  mov     rcx, [rcx+10h]
0x1800053e6  lea     r8, WPP_db9184fc95f634e81eb114a7689fd6a6_Traceguids
0x1800053ed  mov     edx, 10h
0x1800053f2  mov     r9, r14
0x1800053f5  call    WPP_SF_S
0x1800053fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180005401  mov     rdi, r14
0x180005404  jmp     short loc_180005410
0x180005406  mov     rcx, cs:WPP_GLOBAL_Control
0x18000540d  mov     rdi, rbx
0x180005410  cmp     rcx, r13
0x180005413  jz      short loc_180005433
0x180005415  test    byte ptr [rcx+1Ch], 2
0x180005419  jz      short loc_180005433
0x18000541b  mov     rcx, [rcx+10h]
0x18000541f  lea     r8, WPP_db9184fc95f634e81eb114a7689fd6a6_Traceguids
0x180005426  mov     edx, 11h
0x18000542b  mov     r9, rdi
0x18000542e  call    WPP_SF_S
0x180005433  lea     r9, [rsp+78h+arg_10]
0x18000543b  mov     rcx, rdi
0x18000543e  lea     r8, [rsp+78h+String2]
0x180005446  lea     rdx, [rsp+78h+arg_0]
0x18000544e  call    cs:__imp_DavParseUncServerName
0x180005454  test    eax, eax
0x180005456  jnz     loc_180005627
0x18000545c  mov     edi, [rsp+78h+arg_10]
0x180005463  test    edi, edi
0x180005465  jnz     short loc_18000547C
0x180005467  cmp     [rsp+78h+arg_0], bpl
0x18000546f  mov     edi, 50h ; 'P'
0x180005474  mov     eax, 1BBh
0x180005479  cmovnz  edi, eax
0x18000547c  mov     rsi, [rsp+78h+String2]
0x180005484  call    cs:__imp_GetTickCount64
0x18000548a  mov     r15, rax
0x18000548d  test    rsi, rsi
0x180005490  jz      loc_180005575
0x180005496  mov     dl, 1; Wait
0x180005498  lea     rcx, DavclientCacheLock; Resource
0x18000549f  call    cs:__imp_RtlAcquireResourceShared
0x1800054a5  lea     rcx, DavclientCache
0x1800054ac  cmp     r12d, 0Ah
0x1800054b0  jnb     loc_18000555E
0x1800054b6  mov     eax, r12d
0x1800054b9  imul    r13, rax, 218h
0x1800054c0  cmp     [rcx+r13+214h], bpl
0x1800054c8  jz      short loc_1800054EF
0x1800054ca  add     rcx, 8
0x1800054ce  mov     rdx, rsi; String2
0x1800054d1  add     rcx, r13; String1
0x1800054d4  call    cs:__imp__wcsicmp
0x1800054da  lea     rcx, DavclientCache
0x1800054e1  test    eax, eax
0x1800054e3  jnz     short loc_1800054EF
0x1800054e5  cmp     [rcx+r13+210h], edi
0x1800054ed  jz      short loc_1800054F4
0x1800054ef  inc     r12d
0x1800054f2  jmp     short loc_1800054AC
0x1800054f4  cmp     r15, 493E0h
0x1800054fb  jbe     short loc_18000550A
0x1800054fd  lea     rax, [r15-493E0h]
0x180005504  cmp     rax, [rcx+r13]
0x180005508  ja      short loc_18000555E
0x18000550a  lea     rcx, DavclientCacheLock; Resource
0x180005511  call    cs:__imp_RtlReleaseResource
0x180005517  mov     rcx, cs:WPP_GLOBAL_Control
0x18000551e  lea     r13, WPP_GLOBAL_Control
0x180005525  cmp     rcx, r13
0x180005528  jz      loc_18000566F
0x18000552e  test    byte ptr [rcx+1Ch], 2
0x180005532  jz      short loc_180005556
0x180005534  mov     r9, [rsp+78h+String2]
0x18000553c  mov     edx, 12h
0x180005541  mov     rcx, [rcx+10h]
0x180005545  mov     [rsp+78h+var_58], edi
0x180005549  call    WPP_SF_Sl
0x18000554e  xor     r12d, r12d
0x180005551  jmp     loc_180005627
0x180005556  xor     r12d, r12d
0x180005559  jmp     loc_18000562E
0x18000555e  lea     rcx, DavclientCacheLock; Resource
0x180005565  call    cs:__imp_RtlReleaseResource
0x18000556b  xor     r12d, r12d
0x18000556e  lea     r13, WPP_GLOBAL_Control
0x180005575  movzx   r8d, [rsp+78h+arg_0]
0x18000557e  lea     r9, [rsp+78h+arg_8]
0x180005586  mov     edx, [rsp+78h+arg_10]
0x18000558d  mov     rcx, [rsp+78h+String2]; pswzServerName
0x180005595  call    DavDoesServerDoDav
0x18000559a  cmp     [rsp+78h+arg_8], bpl
0x1800055a2  jnz     short loc_180005602
0x1800055a4  cmp     eax, 2EEFh
0x1800055a9  jz      short loc_180005602
0x1800055ab  cmp     eax, 5
0x1800055ae  jz      short loc_180005602
0x1800055b0  cmp     eax, 2F0Ch
0x1800055b5  jz      short loc_180005602
0x1800055b7  cmp     eax, 2F8Fh
0x1800055bc  jz      short loc_180005602
0x1800055be  cmp     eax, 780h
0x1800055c3  jz      short loc_180005602
0x1800055c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800055cc  cmp     rcx, r13
0x1800055cf  jz      short loc_1800055F1
0x1800055d1  test    byte ptr [rcx+1Ch], 2
0x1800055d5  jz      short loc_1800055F1
0x1800055d7  mov     r9, [rsp+78h+String2]
0x1800055df  mov     edx, 13h
0x1800055e4  mov     rcx, [rcx+10h]
0x1800055e8  mov     [rsp+78h+var_58], edi
0x1800055ec  call    WPP_SF_Sl
0x1800055f1  mov     rcx, [rsp+78h+String2]; pszSrc
0x1800055f9  mov     edx, edi
0x1800055fb  call    RefreshDavclientCache
0x180005600  jmp     short loc_180005627
0x180005602  mov     bpl, 1
0x180005605  jmp     short loc_180005627
0x180005607  cmp     rcx, r13
0x18000560a  jz      short loc_18000567B
0x18000560c  test    byte ptr [rcx+1Ch], 1
0x180005610  jz      short loc_18000562E
0x180005612  mov     edx, 0Bh
0x180005617  mov     rcx, [rcx+10h]
0x18000561b  lea     r8, WPP_db9184fc95f634e81eb114a7689fd6a6_Traceguids
0x180005622  call    WPP_SF_
0x180005627  mov     rcx, cs:WPP_GLOBAL_Control
0x18000562e  cmp     rcx, r13
0x180005631  jz      short loc_180005668
0x180005633  test    byte ptr [rcx+1Ch], 2
0x180005637  jz      short loc_180005668
0x180005639  cmp     [rsp+78h+arg_8], 0
0x180005641  lea     rax, aFalse; "FALSE"
0x180005648  mov     rcx, [rcx+10h]
0x18000564c  lea     r9, aTrue; "TRUE"
0x180005653  cmovz   r9, rax
0x180005657  lea     r8, WPP_db9184fc95f634e81eb114a7689fd6a6_Traceguids
0x18000565e  mov     edx, 14h
0x180005663  call    WPP_SF_s
0x180005668  test    rbx, rbx
0x18000566b  jnz     short loc_180005672
0x18000566d  jmp     short loc_18000567B
0x18000566f  xor     r12d, r12d
0x180005672  mov     rcx, rbx; hMem
0x180005675  call    cs:__imp_LocalFree
0x18000567b  mov     rcx, [rsp+78h+String2]; hMem
0x180005683  mov     r15, [rsp+78h+var_40]
0x180005688  mov     r13, [rsp+78h+var_38]
0x18000568d  mov     rdi, [rsp+78h+var_28]
0x180005692  mov     rsi, [rsp+78h+var_20]
0x180005697  mov     rbx, [rsp+78h+var_18]
0x18000569c  test    rcx, rcx
0x18000569f  jz      short loc_1800056AF
0x1800056a1  call    cs:__imp_LocalFree
0x1800056a7  mov     [rsp+78h+String2], r12
0x1800056af  mov     r12, [rsp+78h+var_30]
0x1800056b4  test    r14, r14
0x1800056b7  jz      short loc_1800056C2
0x1800056b9  mov     rcx, r14; hMem
0x1800056bc  call    cs:__imp_LocalFree
0x1800056c2  movzx   eax, bpl
0x1800056c6  add     rsp, 68h
0x1800056ca  pop     r14
0x1800056cc  pop     rbp
0x1800056cd  retn
```
