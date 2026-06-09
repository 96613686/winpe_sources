# PeapReadUserData(int,uchar *,ulong,_PEAP_USER_PROPERTIES * *)

- ea: `0x180004688`
- end: `0x1800049d3`
- name: `?PeapReadUserData@@YAKHPEAEKPEAPEAU_PEAP_USER_PROPERTIES@@@Z`
- size: `843`
- prototype: `unsigned int(int, unsigned __int8 *, unsigned int, struct _PEAP_USER_PROPERTIES **)`
- caller_count: `6`
- callee_count: `6`
- tags: ``

## callers

- `0x180002500`
- `0x180005060`
- `0x180034f2c`
- `0x180058618`
- `0x18005c4f0`
- `0x180061fc4`

## callees

- `0x180004688`
- `0x180005010`
- `0x180007d00`
- `0x180038e4c`
- `0x18007b950`
- `0x18007bae0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004859`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004942`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004859`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004942`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800046e7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800047b1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004845`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000492e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800046e7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800047b1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004845`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000492e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000499d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800049ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000499d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800049ac`
- `rtutils!TraceDumpExA` at `0x180004914`
- `rtutils!TraceDumpExA` at `0x180004914`

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
0x180004688  mov     [rsp+arg_0], rbx
0x18000468d  mov     [rsp+arg_8], rsi
0x180004692  push    rdi
0x180004693  push    r12
0x180004695  push    r13
0x180004697  push    r14
0x180004699  push    r15
0x18000469b  sub     rsp, 40h
0x18000469f  mov     r12, r9
0x1800046a2  mov     edi, r8d
0x1800046a5  mov     r15, rdx
0x1800046a8  mov     r14d, ecx
0x1800046ab  xor     esi, esi
0x1800046ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800046b4  lea     r13, WPP_GLOBAL_Control
0x1800046bb  cmp     rcx, r13
0x1800046be  jz      short loc_1800046D6
0x1800046c0  mov     rcx, [rcx+10h]
0x1800046c4  lea     edx, [rsi+13h]
0x1800046c7  mov     r9d, edi
0x1800046ca  lea     r8, WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids
0x1800046d1  call    WPP_SF_d
0x1800046d6  mov     ecx, 40h ; '@'; uFlags
0x1800046db  cmp     edi, 28h ; '('
0x1800046de  jnb     loc_1800047A2
0x1800046e4  lea     edx, [rcx-4]; uBytes
0x1800046e7  call    cs:__imp_LocalAlloc
0x1800046ee  nop     dword ptr [rax+rax+00h]
0x1800046f3  mov     rbx, rax
0x1800046f6  test    rax, rax
0x1800046f9  jnz     short loc_180004734
0x1800046fb  call    cs:__imp_GetLastError
0x180004702  nop     dword ptr [rax+rax+00h]
0x180004707  mov     edi, eax
0x180004709  mov     rcx, cs:WPP_GLOBAL_Control
0x180004710  cmp     rcx, r13
0x180004713  jz      loc_18000499A
0x180004719  lea     edx, [rbx+14h]
0x18000471c  mov     rcx, [rcx+10h]
0x180004720  lea     r8, WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids
0x180004727  mov     r9d, eax
0x18000472a  call    WPP_SF_d
0x18000472f  jmp     loc_18000499A
0x180004734  mov     dword ptr [rax], 2
0x18000473a  mov     dword ptr [rax+24h], 1
0x180004741  mov     dword ptr [rax+28h], 1
0x180004748  test    r14d, r14d
0x18000474b  jz      short loc_18000475D
0x18000474d  mov     dword ptr [rax+8], 3
0x180004754  mov     dword ptr [rax+2Ch], 10h
0x18000475b  jmp     short loc_18000478D
0x18000475d  mov     dword ptr [rax+2Ch], 14h
0x180004764  test    r15, r15
0x180004767  jnz     short loc_18000478D
0x180004769  mov     rcx, cs:WPP_GLOBAL_Control
0x180004770  cmp     rcx, r13
0x180004773  jz      short loc_180004789
0x180004775  mov     rcx, [rcx+10h]
0x180004779  lea     edx, [r15+15h]
0x18000477d  lea     r8, WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids
0x180004784  call    WPP_SF_
0x180004789  or      dword ptr [rbx+8], 8
0x18000478d  mov     eax, [rbx+2Ch]
0x180004790  add     eax, 28h ; '('
0x180004793  mov     [rbx+4], eax
0x180004796  mov     dword ptr [rbx+30h], 1Ah
0x18000479d  jmp     loc_180004992
0x1800047a2  cmp     dword ptr [r15], 1
0x1800047a6  mov     rdx, rdi; uBytes
0x1800047a9  ja      loc_180004927
0x1800047af  xor     ebx, ebx
0x1800047b1  call    cs:__imp_LocalAlloc
0x1800047b8  nop     dword ptr [rax+rax+00h]
0x1800047bd  mov     rsi, rax
0x1800047c0  test    rax, rax
0x1800047c3  jnz     short loc_1800047EB
0x1800047c5  call    cs:__imp_GetLastError
0x1800047cc  nop     dword ptr [rax+rax+00h]
0x1800047d1  mov     edi, eax
0x1800047d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800047da  cmp     rcx, r13
0x1800047dd  jz      loc_18000499A
0x1800047e3  lea     edx, [rbx+16h]
0x1800047e6  jmp     loc_18000471C
0x1800047eb  mov     r8, rdi; Size
0x1800047ee  mov     rdx, r15; Src
0x1800047f1  mov     rcx, rsi; void *
0x1800047f4  call    memcpy_0
0x1800047f9  cmp     edi, 38h ; '8'
0x1800047fc  jb      loc_1800048C0
0x180004802  cmp     [rsi+4], edi
0x180004805  jnz     loc_1800048C0
0x18000480b  cmp     dword ptr [rsi+0Ch], 14h
0x18000480f  ja      loc_1800048C0
0x180004815  mov     eax, [rsi+28h]
0x180004818  add     rax, 24h ; '$'
0x18000481c  cmp     rax, rdi
0x18000481f  ja      loc_1800048C0
0x180004825  lea     edx, [rdi-24h]; unsigned int
0x180004828  xor     r8d, r8d; unsigned int *
0x18000482b  lea     rcx, [rsi+24h]; struct _PEAP_ENTRY_USER_PROPERTIES *
0x18000482f  call    ?IsPeapEntryArrayInPeapUserPropValid@@YAHPEFAU_PEAP_ENTRY_USER_PROPERTIES@@KPEAK@Z; IsPeapEntryArrayInPeapUserPropValid(_PEAP_ENTRY_USER_PROPERTIES *,ulong,ulong *)
0x180004834  test    eax, eax
0x180004836  jz      loc_1800048C0
0x18000483c  lea     rdx, [rdi+4]; uBytes
0x180004840  mov     ecx, 40h ; '@'; uFlags
0x180004845  call    cs:__imp_LocalAlloc
0x18000484c  nop     dword ptr [rax+rax+00h]
0x180004851  mov     rbx, rax
0x180004854  test    rax, rax
0x180004857  jnz     short loc_18000487F
0x180004859  call    cs:__imp_GetLastError
0x180004860  nop     dword ptr [rax+rax+00h]
0x180004865  mov     edi, eax
0x180004867  mov     rcx, cs:WPP_GLOBAL_Control
0x18000486e  cmp     rcx, r13
0x180004871  jz      loc_18000499A
0x180004877  lea     edx, [rbx+17h]
0x18000487a  jmp     loc_18000471C
0x18000487f  mov     dword ptr [rax], 2
0x180004885  lea     rcx, [rbx+28h]; void *
0x180004889  lea     eax, [rdi+4]
0x18000488c  mov     [rbx+4], eax
0x18000488f  lea     rdx, [rsi+24h]; Src
0x180004893  mov     eax, [rsi+8]
0x180004896  mov     [rbx+8], eax
0x180004899  movups  xmm0, xmmword ptr [rsi+0Ch]
0x18000489d  movups  xmmword ptr [rbx+0Ch], xmm0
0x1800048a1  movsd   xmm1, qword ptr [rsi+1Ch]
0x1800048a6  movsd   qword ptr [rbx+1Ch], xmm1
0x1800048ab  mov     dword ptr [rbx+24h], 1
0x1800048b2  mov     r8d, [rsi+28h]; Size
0x1800048b6  call    memcpy_0
0x1800048bb  jmp     loc_180004992
0x1800048c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800048c7  cmp     rcx, r13
0x1800048ca  jz      short loc_1800048E4
0x1800048cc  mov     rcx, [rcx+10h]
0x1800048d0  lea     r8, WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids
0x1800048d7  mov     edx, 21h ; '!'
0x1800048dc  mov     r9d, edi
0x1800048df  call    WPP_SF_d
0x1800048e4  mov     ecx, cs:?g_dwEapTlsTraceId@@3KA; dwTraceID
0x1800048ea  mov     eax, 100h
0x1800048ef  cmp     edi, eax
0x1800048f1  mov     [rsp+68h+lpszPrefix], rbx; lpszPrefix
0x1800048f6  mov     [rsp+68h+bAddressPrefix], 1; bAddressPrefix
0x1800048fe  mov     r8, rsi; lpbBytes
0x180004901  cmovnb  edi, eax
0x180004904  mov     [rsp+68h+dwGroupSize], 1; dwGroupSize
0x18000490c  mov     r9d, edi; dwByteCount
0x18000490f  mov     edx, 1; dwFlags
0x180004914  call    cs:__imp_TraceDumpExA
0x18000491b  nop     dword ptr [rax+rax+00h]
0x180004920  mov     edi, 0Dh
0x180004925  jmp     short loc_18000499A
0x180004927  mov     [rsp+68h+arg_10], esi
0x18000492e  call    cs:__imp_LocalAlloc
0x180004935  nop     dword ptr [rax+rax+00h]
0x18000493a  mov     rbx, rax
0x18000493d  test    rax, rax
0x180004940  jnz     short loc_180004964
0x180004942  call    cs:__imp_GetLastError
0x180004949  nop     dword ptr [rax+rax+00h]
0x18000494e  mov     edi, eax
0x180004950  mov     rcx, cs:WPP_GLOBAL_Control
0x180004957  cmp     rcx, r13
0x18000495a  jz      short loc_18000499A
0x18000495c  lea     edx, [rbx+18h]
0x18000495f  jmp     loc_18000471C
0x180004964  mov     r8, rdi; Size
0x180004967  mov     rdx, r15; Src
0x18000496a  mov     rcx, rbx; void *
0x18000496d  call    memcpy_0
0x180004972  lea     r8, [rsp+68h+arg_10]; unsigned int *
0x18000497a  mov     edx, edi; unsigned int
0x18000497c  mov     rcx, rbx; lpbBytes
0x18000497f  call    ?IsPeapUserDataValid@@YAHPEAU_PEAP_USER_PROPERTIES@@KPEAK@Z; IsPeapUserDataValid(_PEAP_USER_PROPERTIES *,ulong,ulong *)
0x180004984  test    eax, eax
0x180004986  jz      short loc_180004920
0x180004988  mov     eax, [rsp+68h+arg_10]
0x18000498f  mov     [rbx+24h], eax
0x180004992  xor     edi, edi
0x180004994  mov     [r12], rbx
0x180004998  xor     ebx, ebx
0x18000499a  mov     rcx, rbx; hMem
0x18000499d  call    cs:__imp_LocalFree
0x1800049a4  nop     dword ptr [rax+rax+00h]
0x1800049a9  mov     rcx, rsi; hMem
0x1800049ac  call    cs:__imp_LocalFree
0x1800049b3  nop     dword ptr [rax+rax+00h]
0x1800049b8  mov     rbx, [rsp+68h+arg_0]
0x1800049bd  mov     eax, edi
0x1800049bf  mov     rsi, [rsp+68h+arg_8]
0x1800049c4  add     rsp, 40h
0x1800049c8  pop     r15
0x1800049ca  pop     r14
0x1800049cc  pop     r13
0x1800049ce  pop     r12
0x1800049d0  pop     rdi
0x1800049d1  retn
```
