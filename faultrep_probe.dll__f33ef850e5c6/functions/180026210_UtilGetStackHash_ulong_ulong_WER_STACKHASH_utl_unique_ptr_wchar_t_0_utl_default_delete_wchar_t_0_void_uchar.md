# UtilGetStackHash(ulong,ulong,WER_STACKHASH *,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *,void * *,uchar *)

- ea: `0x180026210`
- end: `0x180026505`
- name: `?UtilGetStackHash@@YAJKKPEAUWER_STACKHASH@@PEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@PEAPEAXPEAE@Z`
- size: `757`
- prototype: `__int64 __usercall@<rax>(DWORD dwProcessId@<ecx>, DWORD dwThreadId@<edx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180015830`

## callees

- `0x180002890`
- `0x1800028b4`
- `0x180009ed8`
- `0x180009f00`
- `0x180025cf8`
- `0x180026210`
- `0x18002650c`
- `0x180026b38`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x180026490`
- `bcrypt!BCryptDestroyHash` at `0x180026490`
- `bcrypt!BCryptHashData` at `0x18002645f`
- `bcrypt!BCryptHashData` at `0x18002645f`
- `bcrypt!BCryptCreateHash` at `0x180026439`
- `bcrypt!BCryptCreateHash` at `0x180026439`
- `bcrypt!BCryptFinishHash` at `0x18002647d`
- `bcrypt!BCryptFinishHash` at `0x18002647d`

## pseudocode

```c
__int64 __fastcall UtilGetStackHash(
        DWORD dwProcessId,
        const struct std::nothrow_t *dwThreadId,
        __int64 a3,
        void **a4,
        _QWORD *a5,
        __int64 a6)
{
  DWORD v8; // r12d
  void *v10; // rcx
  int StackTrace; // eax
  const struct std::nothrow_t *v12; // rdx
  _QWORD *v13; // rcx
  unsigned int v14; // edi
  struct _WER_STACK_FRAME *v15; // rsi
  unsigned int v16; // edi
  void *v17; // rcx
  __int64 v18; // rbx
  int StackHash; // eax
  __int64 v20; // rcx
  __int64 v21; // xmm1_8
  NTSTATUS Hash; // eax
  _BYTE *v23; // r15
  unsigned int v25; // [rsp+40h] [rbp-49h] BYREF
  struct _WER_STACK_FRAME *v26; // [rsp+48h] [rbp-41h] BYREF
  UCHAR pbInput[8]; // [rsp+50h] [rbp-39h] BYREF
  __int64 v28; // [rsp+58h] [rbp-31h]
  __int128 v29; // [rsp+60h] [rbp-29h] BYREF
  __int64 v30; // [rsp+70h] [rbp-19h]
  BCRYPT_HASH_HANDLE phHash[2]; // [rsp+78h] [rbp-11h] BYREF
  __int64 v32; // [rsp+88h] [rbp-1h]

  v28 = a6;
  v26 = 0;
  v25 = 0;
  v8 = (unsigned int)dwThreadId;
  *(_QWORD *)pbInput = 0;
  v32 = 0;
  *(_OWORD *)phHash = 0;
  if ( a4 )
  {
    v10 = *a4;
    *a4 = 0;
    if ( v10 )
      operator delete(v10, dwThreadId);
  }
  StackTrace = UtilGetStackTrace(dwProcessId, v8, (void **)&v26, &v25, a4, a5, pbInput);
  v12 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
  if ( StackTrace >= 0 )
  {
    v14 = v25;
    v13 = WPP_GLOBAL_Control;
  }
  else
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        &WPP_c528859db29c31ff546031011001ad2a_Traceguids,
        (unsigned int)StackTrace);
      v13 = WPP_GLOBAL_Control;
      v12 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
    }
    v14 = 0;
  }
  v15 = v26;
  if ( a3 )
  {
    v18 = 0;
    do
    {
      v29 = 0;
      LODWORD(v29) = v18;
      v30 = 0;
      StackHash = WerpGenerateStackHash(v15, v14, (struct WER_STACKHASH *)&v29);
      if ( StackHash < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            &WPP_c528859db29c31ff546031011001ad2a_Traceguids,
            (unsigned int)StackHash);
      }
      else
      {
        v20 = 3 * v18;
        v21 = v30;
        *(_OWORD *)(a3 + 8 * v20) = v29;
        *(_QWORD *)(a3 + 8 * v20 + 16) = v21;
      }
      v18 = (unsigned int)(v18 + 1);
    }
    while ( (unsigned int)v18 < 2 );
    LogStackTrace(v8, v15, v14, a3);
    Hash = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, phHash, 0, 0, 0, 0, 0);
    v23 = (_BYTE *)v28;
    if ( Hash < 0 )
      __fastfail(7u);
    if ( BCryptHashData(phHash[0], pbInput, 8u, 0) < 0 )
      __fastfail(7u);
    if ( BCryptFinishHash(phHash[0], (PUCHAR)&phHash[1], 0x10u, 0) < 0 )
      __fastfail(7u);
    BCryptDestroyHash(phHash[0]);
    phHash[0] = 0;
    if ( v23 )
      *v23 = HIBYTE(v32)
           ^ BYTE6(v32)
           ^ BYTE5(v32)
           ^ BYTE4(v32)
           ^ BYTE3(v32)
           ^ BYTE2(v32)
           ^ BYTE1(v32)
           ^ v32
           ^ HIBYTE(phHash[1])
           ^ BYTE6(phHash[1])
           ^ BYTE5(phHash[1])
           ^ BYTE4(phHash[1])
           ^ BYTE3(phHash[1])
           ^ BYTE2(phHash[1])
           ^ BYTE1(phHash[1])
           ^ LOBYTE(phHash[1]);
    v16 = 0;
  }
  else
  {
    if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 )
    {
      WPP_SF_(v13[2], 12, &WPP_c528859db29c31ff546031011001ad2a_Traceguids);
      v13 = WPP_GLOBAL_Control;
    }
    v16 = -2147024809;
    if ( a4 )
    {
      v17 = *a4;
      *a4 = 0;
      if ( v17 )
        operator delete(v17, v12);
      v13 = WPP_GLOBAL_Control;
    }
    if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 )
      WPP_SF_d(v13[2], 11, &WPP_c528859db29c31ff546031011001ad2a_Traceguids, 2147942487LL);
  }
  if ( v15 )
    operator delete(v15, v12);
  return v16;
}

```

## disassembly

```asm
0x180026210  push    rbp
0x180026212  push    rbx
0x180026213  push    rsi
0x180026214  push    rdi
0x180026215  push    r12
0x180026217  push    r14
0x180026219  push    r15
0x18002621b  lea     rbp, [rsp-17h]
0x180026220  sub     rsp, 0A0h
0x180026227  mov     rax, cs:__security_cookie
0x18002622e  xor     rax, rsp
0x180026231  mov     [rbp+47h+var_40], rax
0x180026235  mov     r15, [rbp+47h+arg_28]
0x180026239  xor     eax, eax
0x18002623b  mov     rsi, [rbp+47h+arg_20]
0x18002623f  xorps   xmm0, xmm0
0x180026242  mov     [rbp+47h+var_78], r15
0x180026246  mov     rbx, r9
0x180026249  mov     [rbp+47h+var_88], 0
0x180026251  mov     r14, r8
0x180026254  mov     [rbp+47h+var_90], 0
0x18002625b  mov     r12d, edx
0x18002625e  mov     qword ptr [rbp+47h+pbInput], 0
0x180026266  mov     edi, ecx
0x180026268  mov     [rbp+47h+var_48], rax
0x18002626c  movups  xmmword ptr [rbp+47h+phHash], xmm0
0x180026270  test    r9, r9
0x180026273  jz      short loc_180026285
0x180026275  mov     rcx, [r9]; void *
0x180026278  mov     [r9], rax
0x18002627b  test    rcx, rcx
0x18002627e  jz      short loc_180026285
0x180026280  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180026285  lea     rax, [rbp+47h+pbInput]
0x180026289  mov     edx, r12d; dwThreadId
0x18002628c  mov     qword ptr [rsp+0D0h+dwFlags], rax; __int64
0x180026291  lea     r9, [rbp+47h+var_90]
0x180026295  mov     qword ptr [rsp+0D0h+cbSecret], rsi; __int64
0x18002629a  lea     r8, [rbp+47h+var_88]
0x18002629e  mov     ecx, edi; dwProcessId
0x1800262a0  mov     [rsp+0D0h+pbSecret], rbx; __int64
0x1800262a5  call    ?UtilGetStackTrace@@YAJKKPEAV?$unique_ptr@$$BY0A@U_WER_STACK_FRAME@@U?$default_delete@$$BY0A@U_WER_STACK_FRAME@@@utl@@@utl@@PEAKPEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@2@PEAPEAX3@Z; UtilGetStackTrace(ulong,ulong,utl::unique_ptr<_WER_STACK_FRAME [0],utl::default_delete<_WER_STACK_FRAME [0]>> *,ulong *,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *,void * *,void * *)
0x1800262aa  lea     rdx, WPP_GLOBAL_Control
0x1800262b1  test    eax, eax
0x1800262b3  jns     short loc_1800262F1
0x1800262b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800262bc  cmp     rcx, rdx
0x1800262bf  jz      short loc_1800262ED
0x1800262c1  test    byte ptr [rcx+1Ch], 2
0x1800262c5  jz      short loc_1800262ED
0x1800262c7  mov     rcx, [rcx+10h]
0x1800262cb  lea     r8, WPP_c528859db29c31ff546031011001ad2a_Traceguids
0x1800262d2  mov     edx, 0Ah
0x1800262d7  mov     r9d, eax
0x1800262da  call    WPP_SF_d
0x1800262df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800262e6  lea     rdx, WPP_GLOBAL_Control
0x1800262ed  xor     edi, edi
0x1800262ef  jmp     short loc_1800262FB
0x1800262f1  mov     edi, [rbp+47h+var_90]
0x1800262f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800262fb  mov     rsi, [rbp+47h+var_88]
0x1800262ff  test    r14, r14
0x180026302  jnz     loc_18002638A
0x180026308  cmp     rcx, rdx
0x18002630b  jz      short loc_18002632E
0x18002630d  test    byte ptr [rcx+1Ch], 1
0x180026311  jz      short loc_18002632E
0x180026313  mov     rcx, [rcx+10h]
0x180026317  lea     edx, [r14+0Ch]
0x18002631b  lea     r8, WPP_c528859db29c31ff546031011001ad2a_Traceguids
0x180026322  call    WPP_SF_
0x180026327  mov     rcx, cs:WPP_GLOBAL_Control
0x18002632e  mov     edi, 80070057h
0x180026333  test    rbx, rbx
0x180026336  jz      short loc_180026353
0x180026338  mov     rcx, [rbx]; void *
0x18002633b  mov     qword ptr [rbx], 0
0x180026342  test    rcx, rcx
0x180026345  jz      short loc_18002634C
0x180026347  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002634c  mov     rcx, cs:WPP_GLOBAL_Control
0x180026353  lea     rax, WPP_GLOBAL_Control
0x18002635a  cmp     rcx, rax
0x18002635d  jz      loc_1800264D8
0x180026363  test    byte ptr [rcx+1Ch], 1
0x180026367  jz      loc_1800264D8
0x18002636d  mov     rcx, [rcx+10h]
0x180026371  lea     r8, WPP_c528859db29c31ff546031011001ad2a_Traceguids
0x180026378  mov     edx, 0Bh
0x18002637d  mov     r9d, edi
0x180026380  call    WPP_SF_d
0x180026385  jmp     loc_1800264D8
0x18002638a  xor     ebx, ebx
0x18002638c  lea     r15, WPP_GLOBAL_Control
0x180026393  xorps   xmm0, xmm0
0x180026396  lea     r8, [rbp+47h+var_70]; struct WER_STACKHASH *
0x18002639a  xor     eax, eax
0x18002639c  mov     edx, edi; unsigned int
0x18002639e  movups  [rbp+47h+var_70], xmm0
0x1800263a2  mov     rcx, rsi; struct _WER_STACK_FRAME *
0x1800263a5  mov     dword ptr [rbp+47h+var_70], ebx
0x1800263a8  mov     [rbp+47h+var_60], rax
0x1800263ac  call    ?WerpGenerateStackHash@@YAJPEAU_WER_STACK_FRAME@@KPEAUWER_STACKHASH@@@Z; WerpGenerateStackHash(_WER_STACK_FRAME *,ulong,WER_STACKHASH *)
0x1800263b1  test    eax, eax
0x1800263b3  js      short loc_1800263D0
0x1800263b5  movups  xmm0, [rbp+47h+var_70]
0x1800263b9  lea     rcx, [rbx+rbx*2]
0x1800263bd  movsd   xmm1, [rbp+47h+var_60]
0x1800263c2  movups  xmmword ptr [r14+rcx*8], xmm0
0x1800263c7  movsd   qword ptr [r14+rcx*8+10h], xmm1
0x1800263ce  jmp     short loc_1800263FA
0x1800263d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800263d7  cmp     rcx, r15
0x1800263da  jz      short loc_1800263FA
0x1800263dc  test    byte ptr [rcx+1Ch], 2
0x1800263e0  jz      short loc_1800263FA
0x1800263e2  mov     rcx, [rcx+10h]
0x1800263e6  lea     r8, WPP_c528859db29c31ff546031011001ad2a_Traceguids
0x1800263ed  mov     edx, 0Dh
0x1800263f2  mov     r9d, eax
0x1800263f5  call    WPP_SF_d
0x1800263fa  inc     ebx
0x1800263fc  cmp     ebx, 2
0x1800263ff  jb      short loc_180026393
0x180026401  mov     r9, r14
0x180026404  mov     r8d, edi
0x180026407  mov     rdx, rsi
0x18002640a  mov     ecx, r12d
0x18002640d  call    LogStackTrace
0x180026412  xor     r9d, r9d; cbHashObject
0x180026415  mov     [rsp+0D0h+dwFlags], 0; dwFlags
0x18002641d  mov     [rsp+0D0h+cbSecret], 0; cbSecret
0x180026425  lea     rdx, [rbp+47h+phHash]; phHash
0x180026429  xor     r8d, r8d; pbHashObject
0x18002642c  mov     [rsp+0D0h+pbSecret], 0; pbSecret
0x180026435  lea     ecx, [r9+21h]; hAlgorithm
0x180026439  call    cs:__imp_BCryptCreateHash
0x18002643f  mov     r15, [rbp+47h+var_78]
0x180026443  mov     ebx, 7
0x180026448  test    eax, eax
0x18002644a  jns     short loc_180026450
0x18002644c  mov     ecx, ebx
0x18002644e  int     29h; Win8: RtlFailFast(ecx)
0x180026450  mov     rcx, [rbp+47h+phHash]; hHash
0x180026454  lea     rdx, [rbp+47h+pbInput]; pbInput
0x180026458  xor     r9d, r9d; dwFlags
0x18002645b  lea     r8d, [r9+8]; cbInput
0x18002645f  call    cs:__imp_BCryptHashData
0x180026465  test    eax, eax
0x180026467  jns     short loc_18002646E
0x180026469  mov     rcx, rbx
0x18002646c  int     29h; Win8: RtlFailFast(ecx)
0x18002646e  mov     rcx, [rbp+47h+phHash]; hHash
0x180026472  lea     rdx, [rbp+47h+phHash+8]; pbOutput
0x180026476  xor     r9d, r9d; dwFlags
0x180026479  lea     r8d, [r9+10h]; cbOutput
0x18002647d  call    cs:__imp_BCryptFinishHash
0x180026483  test    eax, eax
0x180026485  jns     short loc_18002648C
0x180026487  mov     rcx, rbx
0x18002648a  int     29h; Win8: RtlFailFast(ecx)
0x18002648c  mov     rcx, [rbp+47h+phHash]; hHash
0x180026490  call    cs:__imp_BCryptDestroyHash
0x180026496  mov     [rbp+47h+phHash], 0
0x18002649e  test    r15, r15
0x1800264a1  jz      short loc_1800264D6
0x1800264a3  mov     al, byte ptr [rbp+47h+phHash+8]
0x1800264a6  xor     al, byte ptr [rbp+47h+phHash+9]
0x1800264a9  xor     al, byte ptr [rbp+47h+phHash+0Ah]
0x1800264ac  xor     al, byte ptr [rbp+47h+phHash+0Bh]
0x1800264af  xor     al, byte ptr [rbp+47h+phHash+0Ch]
0x1800264b2  xor     al, byte ptr [rbp+47h+phHash+0Dh]
0x1800264b5  xor     al, byte ptr [rbp+47h+phHash+0Eh]
0x1800264b8  xor     al, byte ptr [rbp+47h+phHash+0Fh]
0x1800264bb  xor     al, byte ptr [rbp+47h+var_48]
0x1800264be  xor     al, byte ptr [rbp+47h+var_48+1]
0x1800264c1  xor     al, byte ptr [rbp+47h+var_48+2]
0x1800264c4  xor     al, byte ptr [rbp+47h+var_48+3]
0x1800264c7  xor     al, byte ptr [rbp+47h+var_48+4]
0x1800264ca  xor     al, byte ptr [rbp+47h+var_48+5]
0x1800264cd  xor     al, byte ptr [rbp+47h+var_48+6]
0x1800264d0  xor     al, byte ptr [rbp+47h+var_48+7]
0x1800264d3  mov     [r15], al
0x1800264d6  xor     edi, edi
0x1800264d8  test    rsi, rsi
0x1800264db  jz      short loc_1800264E5
0x1800264dd  mov     rcx, rsi; void *
0x1800264e0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800264e5  mov     eax, edi
0x1800264e7  mov     rcx, [rbp+47h+var_40]
0x1800264eb  xor     rcx, rsp; StackCookie
0x1800264ee  call    __security_check_cookie
0x1800264f3  add     rsp, 0A0h
0x1800264fa  pop     r15
0x1800264fc  pop     r14
0x1800264fe  pop     r12
0x180026500  pop     rdi
0x180026501  pop     rsi
0x180026502  pop     rbx
0x180026503  pop     rbp
0x180026504  retn
```
