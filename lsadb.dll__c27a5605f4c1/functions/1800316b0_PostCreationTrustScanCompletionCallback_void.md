# PostCreationTrustScanCompletionCallback(void *)

- ea: `0x1800316b0`
- end: `0x1800318c3`
- name: `?PostCreationTrustScanCompletionCallback@@YAJPEAX@Z`
- size: `531`
- prototype: `__int64 __fastcall(struct _POSTCREATION_TRUSTSCAN_CONTEXT *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000fd18`
- `0x18000fd40`
- `0x18002f640`
- `0x18002f8f4`
- `0x180030650`
- `0x1800316b0`
- `0x1800328b8`
- `0x180032958`

## import_xrefs

- `LSASRV!LsaIRegisterNotification` at `0x180031863`
- `LSASRV!LsaIRegisterNotification` at `0x180031863`
- `LSASRV!LsaICancelNotification` at `0x180031708`
- `LSASRV!LsaICancelNotification` at `0x180031708`

## pseudocode

```c
__int64 __fastcall PostCreationTrustScanCompletionCallback(struct _POSTCREATION_TRUSTSCAN_CONTEXT *a1)
{
  unsigned int v2; // edi
  int v3; // r8d
  int v4; // eax
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned int v10; // esi
  __int64 v11; // rax
  __int64 v12; // r8
  int v14; // [rsp+60h] [rbp+8h] BYREF
  int v15; // [rsp+68h] [rbp+10h] BYREF

  v14 = 0;
  v15 = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_844d483327f83d00fc717282eb3891a9_Traceguids);
  if ( !a1 )
  {
    v2 = -1073741811;
    goto LABEL_32;
  }
  LsaICancelNotification(*((_QWORD *)a1 + 5));
  *((_QWORD *)a1 + 5) = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_DSD(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, v3, *(_DWORD *)a1, *((_QWORD *)a1 + 1), *((_DWORD *)a1 + 4));
  v4 = CheckTrustScannerEligibility(&v14);
  v2 = v4;
  if ( v4 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_32;
    v6 = 89;
LABEL_10:
    WPP_SF_d(v5[2], v6, &WPP_844d483327f83d00fc717282eb3891a9_Traceguids, (unsigned int)v4);
    goto LABEL_32;
  }
  if ( !v14 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_32;
    v8 = 90;
LABEL_14:
    WPP_SF_(v7[2], v8, &WPP_844d483327f83d00fc717282eb3891a9_Traceguids);
    goto LABEL_32;
  }
  v4 = CheckPostCreationScanTrustEligibility(a1, &v15);
  v2 = v4;
  if ( v4 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_32;
    v6 = 91;
    goto LABEL_10;
  }
  if ( !v15 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_32;
    v8 = 92;
    goto LABEL_14;
  }
  if ( ++*(_DWORD *)a1 > 3u )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_32;
    v8 = 93;
    goto LABEL_14;
  }
  v10 = 300 * *(_DWORD *)a1;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, v9, v10, 300 * *(_DWORD *)a1);
  v11 = LsaIRegisterNotification(PostCreationTrustScanTimerCallback, a1, 1);
  *((_QWORD *)a1 + 5) = v11;
  if ( !v11 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_32;
    v8 = 95;
    goto LABEL_14;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, v12, v10, v10);
  a1 = 0;
LABEL_32:
  FreePostTrustCreationScanContext(a1);
  return v2;
}

```

## disassembly

```asm
0x1800316b0  mov     [rsp+arg_10], rbx
0x1800316b5  push    rsi
0x1800316b6  push    rdi
0x1800316b7  push    r15
0x1800316b9  sub     rsp, 40h
0x1800316bd  mov     rbx, rcx
0x1800316c0  mov     [rsp+58h+arg_0], 0
0x1800316c8  mov     [rsp+58h+arg_8], 0
0x1800316d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800316d7  lea     r15, WPP_844d483327f83d00fc717282eb3891a9_Traceguids
0x1800316de  test    byte ptr [rcx+1Ch], 10h
0x1800316e2  jz      short loc_1800316F5
0x1800316e4  mov     rcx, [rcx+10h]
0x1800316e8  mov     edx, 57h ; 'W'
0x1800316ed  mov     r8, r15
0x1800316f0  call    WPP_SF_
0x1800316f5  test    rbx, rbx
0x1800316f8  jnz     short loc_180031704
0x1800316fa  mov     edi, 0C000000Dh
0x1800316ff  jmp     loc_1800318AB
0x180031704  mov     rcx, [rbx+28h]
0x180031708  call    cs:__imp_LsaICancelNotification
0x18003170e  mov     qword ptr [rbx+28h], 0
0x180031716  mov     rcx, cs:WPP_GLOBAL_Control
0x18003171d  test    byte ptr [rcx+1Ch], 10h
0x180031721  jz      short loc_180031744
0x180031723  mov     eax, [rbx+10h]
0x180031726  mov     edx, 58h ; 'X'
0x18003172b  mov     r9d, [rbx]
0x18003172e  mov     rcx, [rcx+10h]
0x180031732  mov     [rsp+58h+var_30], eax
0x180031736  mov     rax, [rbx+8]
0x18003173a  mov     [rsp+58h+var_38], rax
0x18003173f  call    WPP_SF_DSD
0x180031744  lea     rcx, [rsp+58h+arg_0]; int *
0x180031749  call    ?CheckTrustScannerEligibility@@YAJPEAH@Z; CheckTrustScannerEligibility(int *)
0x18003174e  mov     edi, eax
0x180031750  test    eax, eax
0x180031752  jns     short loc_18003177E
0x180031754  mov     rcx, cs:WPP_GLOBAL_Control
0x18003175b  test    byte ptr [rcx+1Ch], 10h
0x18003175f  jz      loc_1800318AB
0x180031765  mov     edx, 59h ; 'Y'
0x18003176a  mov     rcx, [rcx+10h]
0x18003176e  mov     r9d, eax
0x180031771  mov     r8, r15
0x180031774  call    WPP_SF_d
0x180031779  jmp     loc_1800318AB
0x18003177e  cmp     [rsp+58h+arg_0], 0
0x180031783  jnz     short loc_1800317AC
0x180031785  mov     rcx, cs:WPP_GLOBAL_Control
0x18003178c  test    byte ptr [rcx+1Ch], 10h
0x180031790  jz      loc_1800318AB
0x180031796  mov     edx, 5Ah ; 'Z'
0x18003179b  mov     rcx, [rcx+10h]
0x18003179f  mov     r8, r15
0x1800317a2  call    WPP_SF_
0x1800317a7  jmp     loc_1800318AB
0x1800317ac  lea     rdx, [rsp+58h+arg_8]; int *
0x1800317b1  mov     rcx, rbx; struct _POSTCREATION_TRUSTSCAN_CONTEXT *
0x1800317b4  call    ?CheckPostCreationScanTrustEligibility@@YAJPEAU_POSTCREATION_TRUSTSCAN_CONTEXT@@PEAH@Z; CheckPostCreationScanTrustEligibility(_POSTCREATION_TRUSTSCAN_CONTEXT *,int *)
0x1800317b9  mov     edi, eax
0x1800317bb  test    eax, eax
0x1800317bd  jns     short loc_1800317D7
0x1800317bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800317c6  test    byte ptr [rcx+1Ch], 10h
0x1800317ca  jz      loc_1800318AB
0x1800317d0  mov     edx, 5Bh ; '['
0x1800317d5  jmp     short loc_18003176A
0x1800317d7  cmp     [rsp+58h+arg_8], 0
0x1800317dc  jnz     short loc_1800317F6
0x1800317de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800317e5  test    byte ptr [rcx+1Ch], 10h
0x1800317e9  jz      loc_1800318AB
0x1800317ef  mov     edx, 5Ch ; '\'
0x1800317f4  jmp     short loc_18003179B
0x1800317f6  inc     dword ptr [rbx]
0x1800317f8  cmp     dword ptr [rbx], 3
0x1800317fb  jbe     short loc_180031815
0x1800317fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180031804  test    byte ptr [rcx+1Ch], 10h
0x180031808  jz      loc_1800318AB
0x18003180e  mov     edx, 5Dh ; ']'
0x180031813  jmp     short loc_18003179B
0x180031815  imul    esi, [rbx], 12Ch
0x18003181b  mov     rcx, cs:WPP_GLOBAL_Control
0x180031822  test    byte ptr [rcx+1Ch], 10h
0x180031826  jz      short loc_18003183D
0x180031828  mov     rcx, [rcx+10h]
0x18003182c  mov     edx, 5Eh ; '^'
0x180031831  mov     r9d, esi
0x180031834  mov     dword ptr [rsp+58h+var_38], esi
0x180031838  call    WPP_SF_Dd
0x18003183d  xor     r9d, r9d
0x180031840  mov     [rsp+58h+var_28], 0
0x180031849  mov     [rsp+58h+var_30], esi
0x18003184d  lea     rcx, ?PostCreationTrustScanTimerCallback@@YAJPEAX@Z; PostCreationTrustScanTimerCallback(void *)
0x180031854  mov     rdx, rbx
0x180031857  mov     dword ptr [rsp+58h+var_38], 2
0x18003185f  lea     r8d, [r9+1]
0x180031863  call    cs:__imp_LsaIRegisterNotification
0x180031869  mov     [rbx+28h], rax
0x18003186d  test    rax, rax
0x180031870  jnz     short loc_180031887
0x180031872  mov     rcx, cs:WPP_GLOBAL_Control
0x180031879  test    byte ptr [rcx+1Ch], 10h
0x18003187d  jz      short loc_1800318AB
0x18003187f  lea     edx, [rax+5Fh]
0x180031882  jmp     loc_18003179B
0x180031887  mov     rcx, cs:WPP_GLOBAL_Control
0x18003188e  test    byte ptr [rcx+1Ch], 10h
0x180031892  jz      short loc_1800318A9
0x180031894  mov     rcx, [rcx+10h]
0x180031898  mov     edx, 60h ; '`'
0x18003189d  mov     r9d, esi
0x1800318a0  mov     dword ptr [rsp+58h+var_38], esi
0x1800318a4  call    WPP_SF_Dd
0x1800318a9  xor     ebx, ebx
0x1800318ab  mov     rcx, rbx; hMem
0x1800318ae  call    ?FreePostTrustCreationScanContext@@YAXPEAU_POSTCREATION_TRUSTSCAN_CONTEXT@@@Z; FreePostTrustCreationScanContext(_POSTCREATION_TRUSTSCAN_CONTEXT *)
0x1800318b3  mov     rbx, [rsp+58h+arg_10]
0x1800318b8  mov     eax, edi
0x1800318ba  add     rsp, 40h
0x1800318be  pop     r15
0x1800318c0  pop     rdi
0x1800318c1  pop     rsi
0x1800318c2  retn
```
