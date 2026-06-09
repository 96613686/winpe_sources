# PeapReadUserData(int,uchar *,ulong,_PEAP_USER_PROPERTIES * *)

- ea: `0x1800042dc`
- end: `0x1800045e0`
- name: `?PeapReadUserData@@YAKHPEAEKPEAPEAU_PEAP_USER_PROPERTIES@@@Z`
- size: `772`
- prototype: `__int64 __fastcall(int, unsigned __int8 *, unsigned int, BYTE **)`
- caller_count: `6`
- callee_count: `6`
- tags: ``

## callers

- `0x180002490`
- `0x180004c10`
- `0x180032670`
- `0x1800555d0`
- `0x180059200`
- `0x18005e7f0`

## callees

- `0x1800042dc`
- `0x180004bd0`
- `0x1800075b0`
- `0x18003623c`
- `0x18007664c`
- `0x1800767cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004349`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004407`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000448b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004562`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004349`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004407`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000448b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004562`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000433b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800043f9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000447d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004554`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000433b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800043f9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000447d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004554`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800045b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800045c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800045b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800045c0`
- `rtutils!TraceDumpExA` at `0x180004540`
- `rtutils!TraceDumpExA` at `0x180004540`

## pseudocode

```c
__int64 __fastcall PeapReadUserData(int a1, unsigned __int8 *a2, unsigned int a3, BYTE **a4)
{
  unsigned __int64 v5; // rdi
  char *v8; // rsi
  BYTE *v9; // rax
  BYTE *v10; // rbx
  DWORD LastError; // eax
  unsigned int v12; // edi
  struct _EAPTLS_CONTROL_BLOCK *v13; // rcx
  __int64 v14; // rdx
  char *v15; // rax
  char *v16; // rax
  BYTE *v17; // rax
  unsigned int v19; // [rsp+80h] [rbp+18h] BYREF

  v5 = a3;
  v8 = 0;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids, a3);
  if ( (unsigned int)v5 >= 0x28 )
  {
    if ( *(_DWORD *)a2 > 1u )
    {
      v19 = 0;
      v17 = (BYTE *)LocalAlloc(0x40u, v5);
      v10 = v17;
      if ( !v17 )
      {
        LastError = GetLastError();
        v12 = LastError;
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_40;
        v14 = 24;
        goto LABEL_7;
      }
      memcpy_0(v17, a2, v5);
      if ( (unsigned int)IsPeapUserDataValid(v10, v5, &v19) )
      {
        *((_DWORD *)v10 + 9) = v19;
        goto LABEL_39;
      }
    }
    else
    {
      v10 = 0;
      v15 = (char *)LocalAlloc(0x40u, v5);
      v8 = v15;
      if ( !v15 )
      {
        LastError = GetLastError();
        v12 = LastError;
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_40;
        v14 = 22;
        goto LABEL_7;
      }
      memcpy_0(v15, a2, v5);
      if ( (unsigned int)v5 >= 0x38
        && *((_DWORD *)v8 + 1) == (_DWORD)v5
        && *((_DWORD *)v8 + 3) <= 0x14u
        && (unsigned __int64)*((unsigned int *)v8 + 10) + 36 <= v5
        && (unsigned int)IsPeapEntryArrayInPeapUserPropValid(
                           (struct _PEAP_ENTRY_USER_PROPERTIES *)(v8 + 36),
                           (int)v5 - 36,
                           0) )
      {
        v16 = (char *)LocalAlloc(0x40u, v5 + 4);
        v10 = (BYTE *)v16;
        if ( !v16 )
        {
          LastError = GetLastError();
          v12 = LastError;
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            goto LABEL_40;
          v14 = 23;
          goto LABEL_7;
        }
        *(_DWORD *)v16 = 2;
        *((_DWORD *)v16 + 1) = v5 + 4;
        *((_DWORD *)v16 + 2) = *((_DWORD *)v8 + 2);
        *(_OWORD *)(v16 + 12) = *(_OWORD *)(v8 + 12);
        *(_QWORD *)(v16 + 28) = *(_QWORD *)(v8 + 28);
        *((_DWORD *)v16 + 9) = 1;
        memcpy_0(v16 + 40, v8 + 36, *((unsigned int *)v8 + 10));
LABEL_39:
        v12 = 0;
        *a4 = v10;
        v10 = 0;
        goto LABEL_40;
      }
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          33,
          WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids,
          (unsigned int)v5);
      if ( (unsigned int)v5 >= 0x100 )
        LODWORD(v5) = 256;
      TraceDumpExA(g_dwEapTlsTraceId, 1u, (LPBYTE)v8, v5, 1u, 1, 0);
    }
    v12 = 13;
    goto LABEL_40;
  }
  v9 = (BYTE *)LocalAlloc(0x40u, 0x3Cu);
  v10 = v9;
  if ( v9 )
  {
    *(_DWORD *)v9 = 2;
    *((_DWORD *)v9 + 9) = 1;
    *((_DWORD *)v9 + 10) = 1;
    if ( a1 )
    {
      *((_DWORD *)v9 + 2) = 3;
      *((_DWORD *)v9 + 11) = 16;
    }
    else
    {
      *((_DWORD *)v9 + 11) = 20;
      if ( !a2 )
      {
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids);
        *((_DWORD *)v10 + 2) |= 8u;
      }
    }
    *((_DWORD *)v10 + 1) = *((_DWORD *)v10 + 11) + 40;
    *((_DWORD *)v10 + 12) = 26;
    goto LABEL_39;
  }
  LastError = GetLastError();
  v12 = LastError;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    v14 = 20;
LABEL_7:
    WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids, LastError);
  }
LABEL_40:
  LocalFree(v10);
  LocalFree(v8);
  return v12;
}

```

## disassembly

```asm
0x1800042dc  mov     [rsp+arg_0], rbx
0x1800042e1  mov     [rsp+arg_8], rsi
0x1800042e6  push    rdi
0x1800042e7  push    r12
0x1800042e9  push    r13
0x1800042eb  push    r14
0x1800042ed  push    r15
0x1800042ef  sub     rsp, 40h
0x1800042f3  mov     r12, r9
0x1800042f6  mov     edi, r8d
0x1800042f9  mov     r15, rdx
0x1800042fc  mov     r14d, ecx
0x1800042ff  xor     esi, esi
0x180004301  mov     rcx, cs:WPP_GLOBAL_Control
0x180004308  lea     r13, WPP_GLOBAL_Control
0x18000430f  cmp     rcx, r13
0x180004312  jz      short loc_18000432A
0x180004314  mov     rcx, [rcx+10h]
0x180004318  lea     edx, [rsi+13h]
0x18000431b  mov     r9d, edi
0x18000431e  lea     r8, WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids
0x180004325  call    WPP_SF_d
0x18000432a  mov     ecx, 40h ; '@'; uFlags
0x18000432f  cmp     edi, 28h ; '('
0x180004332  jnb     loc_1800043EA
0x180004338  lea     edx, [rcx-4]; uBytes
0x18000433b  call    cs:__imp_LocalAlloc
0x180004341  mov     rbx, rax
0x180004344  test    rax, rax
0x180004347  jnz     short loc_18000437C
0x180004349  call    cs:__imp_GetLastError
0x18000434f  mov     edi, eax
0x180004351  mov     rcx, cs:WPP_GLOBAL_Control
0x180004358  cmp     rcx, r13
0x18000435b  jz      loc_1800045B4
0x180004361  lea     edx, [rbx+14h]
0x180004364  mov     rcx, [rcx+10h]
0x180004368  lea     r8, WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids
0x18000436f  mov     r9d, eax
0x180004372  call    WPP_SF_d
0x180004377  jmp     loc_1800045B4
0x18000437c  mov     dword ptr [rax], 2
0x180004382  mov     dword ptr [rax+24h], 1
0x180004389  mov     dword ptr [rax+28h], 1
0x180004390  test    r14d, r14d
0x180004393  jz      short loc_1800043A5
0x180004395  mov     dword ptr [rax+8], 3
0x18000439c  mov     dword ptr [rax+2Ch], 10h
0x1800043a3  jmp     short loc_1800043D5
0x1800043a5  mov     dword ptr [rax+2Ch], 14h
0x1800043ac  test    r15, r15
0x1800043af  jnz     short loc_1800043D5
0x1800043b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800043b8  cmp     rcx, r13
0x1800043bb  jz      short loc_1800043D1
0x1800043bd  mov     rcx, [rcx+10h]
0x1800043c1  lea     edx, [r15+15h]
0x1800043c5  lea     r8, WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids
0x1800043cc  call    WPP_SF_
0x1800043d1  or      dword ptr [rbx+8], 8
0x1800043d5  mov     eax, [rbx+2Ch]
0x1800043d8  add     eax, 28h ; '('
0x1800043db  mov     [rbx+4], eax
0x1800043de  mov     dword ptr [rbx+30h], 1Ah
0x1800043e5  jmp     loc_1800045AC
0x1800043ea  cmp     dword ptr [r15], 1
0x1800043ee  mov     rdx, rdi; uBytes
0x1800043f1  ja      loc_18000454D
0x1800043f7  xor     ebx, ebx
0x1800043f9  call    cs:__imp_LocalAlloc
0x1800043ff  mov     rsi, rax
0x180004402  test    rax, rax
0x180004405  jnz     short loc_180004427
0x180004407  call    cs:__imp_GetLastError
0x18000440d  mov     edi, eax
0x18000440f  mov     rcx, cs:WPP_GLOBAL_Control
0x180004416  cmp     rcx, r13
0x180004419  jz      loc_1800045B4
0x18000441f  lea     edx, [rbx+16h]
0x180004422  jmp     loc_180004364
0x180004427  mov     r8, rdi; Size
0x18000442a  mov     rdx, r15; Src
0x18000442d  mov     rcx, rsi; void *
0x180004430  call    memcpy_0
0x180004435  cmp     edi, 38h ; '8'
0x180004438  jb      loc_1800044EC
0x18000443e  cmp     [rsi+4], edi
0x180004441  jnz     loc_1800044EC
0x180004447  cmp     dword ptr [rsi+0Ch], 14h
0x18000444b  ja      loc_1800044EC
0x180004451  mov     eax, [rsi+28h]
0x180004454  add     rax, 24h ; '$'
0x180004458  cmp     rax, rdi
0x18000445b  ja      loc_1800044EC
0x180004461  lea     edx, [rdi-24h]; unsigned int
0x180004464  xor     r8d, r8d; unsigned int *
0x180004467  lea     rcx, [rsi+24h]; struct _PEAP_ENTRY_USER_PROPERTIES *
0x18000446b  call    ?IsPeapEntryArrayInPeapUserPropValid@@YAHPEFAU_PEAP_ENTRY_USER_PROPERTIES@@KPEAK@Z; IsPeapEntryArrayInPeapUserPropValid(_PEAP_ENTRY_USER_PROPERTIES *,ulong,ulong *)
0x180004470  test    eax, eax
0x180004472  jz      short loc_1800044EC
0x180004474  lea     rdx, [rdi+4]; uBytes
0x180004478  mov     ecx, 40h ; '@'; uFlags
0x18000447d  call    cs:__imp_LocalAlloc
0x180004483  mov     rbx, rax
0x180004486  test    rax, rax
0x180004489  jnz     short loc_1800044AB
0x18000448b  call    cs:__imp_GetLastError
0x180004491  mov     edi, eax
0x180004493  mov     rcx, cs:WPP_GLOBAL_Control
0x18000449a  cmp     rcx, r13
0x18000449d  jz      loc_1800045B4
0x1800044a3  lea     edx, [rbx+17h]
0x1800044a6  jmp     loc_180004364
0x1800044ab  mov     dword ptr [rax], 2
0x1800044b1  lea     rcx, [rbx+28h]; void *
0x1800044b5  lea     eax, [rdi+4]
0x1800044b8  mov     [rbx+4], eax
0x1800044bb  lea     rdx, [rsi+24h]; Src
0x1800044bf  mov     eax, [rsi+8]
0x1800044c2  mov     [rbx+8], eax
0x1800044c5  movups  xmm0, xmmword ptr [rsi+0Ch]
0x1800044c9  movups  xmmword ptr [rbx+0Ch], xmm0
0x1800044cd  movsd   xmm1, qword ptr [rsi+1Ch]
0x1800044d2  movsd   qword ptr [rbx+1Ch], xmm1
0x1800044d7  mov     dword ptr [rbx+24h], 1
0x1800044de  mov     r8d, [rsi+28h]; Size
0x1800044e2  call    memcpy_0
0x1800044e7  jmp     loc_1800045AC
0x1800044ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044f3  cmp     rcx, r13
0x1800044f6  jz      short loc_180004510
0x1800044f8  mov     rcx, [rcx+10h]
0x1800044fc  lea     r8, WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids
0x180004503  mov     edx, 21h ; '!'
0x180004508  mov     r9d, edi
0x18000450b  call    WPP_SF_d
0x180004510  mov     ecx, cs:?g_dwEapTlsTraceId@@3KA; dwTraceID
0x180004516  mov     eax, 100h
0x18000451b  cmp     edi, eax
0x18000451d  mov     [rsp+68h+lpszPrefix], rbx; lpszPrefix
0x180004522  mov     [rsp+68h+bAddressPrefix], 1; bAddressPrefix
0x18000452a  mov     r8, rsi; lpbBytes
0x18000452d  cmovnb  edi, eax
0x180004530  mov     [rsp+68h+dwGroupSize], 1; dwGroupSize
0x180004538  mov     r9d, edi; dwByteCount
0x18000453b  mov     edx, 1; dwFlags
0x180004540  call    cs:__imp_TraceDumpExA
0x180004546  mov     edi, 0Dh
0x18000454b  jmp     short loc_1800045B4
0x18000454d  mov     [rsp+68h+arg_10], esi
0x180004554  call    cs:__imp_LocalAlloc
0x18000455a  mov     rbx, rax
0x18000455d  test    rax, rax
0x180004560  jnz     short loc_18000457E
0x180004562  call    cs:__imp_GetLastError
0x180004568  mov     edi, eax
0x18000456a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004571  cmp     rcx, r13
0x180004574  jz      short loc_1800045B4
0x180004576  lea     edx, [rbx+18h]
0x180004579  jmp     loc_180004364
0x18000457e  mov     r8, rdi; Size
0x180004581  mov     rdx, r15; Src
0x180004584  mov     rcx, rbx; void *
0x180004587  call    memcpy_0
0x18000458c  lea     r8, [rsp+68h+arg_10]; unsigned int *
0x180004594  mov     edx, edi; unsigned int
0x180004596  mov     rcx, rbx; lpbBytes
0x180004599  call    ?IsPeapUserDataValid@@YAHPEAU_PEAP_USER_PROPERTIES@@KPEAK@Z; IsPeapUserDataValid(_PEAP_USER_PROPERTIES *,ulong,ulong *)
0x18000459e  test    eax, eax
0x1800045a0  jz      short loc_180004546
0x1800045a2  mov     eax, [rsp+68h+arg_10]
0x1800045a9  mov     [rbx+24h], eax
0x1800045ac  xor     edi, edi
0x1800045ae  mov     [r12], rbx
0x1800045b2  xor     ebx, ebx
0x1800045b4  mov     rcx, rbx; hMem
0x1800045b7  call    cs:__imp_LocalFree
0x1800045bd  mov     rcx, rsi; hMem
0x1800045c0  call    cs:__imp_LocalFree
0x1800045c6  mov     rbx, [rsp+68h+arg_0]
0x1800045cb  mov     eax, edi
0x1800045cd  mov     rsi, [rsp+68h+arg_8]
0x1800045d2  add     rsp, 40h
0x1800045d6  pop     r15
0x1800045d8  pop     r14
0x1800045da  pop     r13
0x1800045dc  pop     r12
0x1800045de  pop     rdi
0x1800045df  retn
```
