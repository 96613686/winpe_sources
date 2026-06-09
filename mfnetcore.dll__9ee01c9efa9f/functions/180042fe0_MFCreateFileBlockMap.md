# MFCreateFileBlockMap

- ea: `0x180042fe0`
- end: `0x180043554`
- name: `MFCreateFileBlockMap`
- size: `1396`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x1800427cc`

## callees

- `0x18000d210`
- `0x180038768`
- `0x18003d3e0`
- `0x18003f28c`
- `0x180042fe0`
- `0x180043f14`
- `0x1800cd268`
- `0x1800edcb8`
- `0x1800ef6a0`
- `0x1800ef9b8`
- `0x1800f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004302b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043046`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004315d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043178`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043326`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043341`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043454`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004346f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004302b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043046`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004315d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043178`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043326`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043341`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043454`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004346f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800430b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800431e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800433ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800434da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800430b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800431e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800433ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800434da`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180043036`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180043168`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180043331`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004345f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180043036`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180043168`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180043331`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004345f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004305c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004318e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800432d4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043357`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800433fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043485`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004305c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004318e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800432d4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043357`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800433fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043485`

## string_xrefs

- `0x180043017`: `MFCreateFileBlockMap`
- `0x1800430bd`: `MFCreateFileBlockMap`
- `0x1800431f4`: `MFCreateFileBlockMap`
- `0x1800433bd`: `MFCreateFileBlockMap`
- `0x1800434eb`: `MFCreateFileBlockMap`

## pseudocode

```c
__int64 __fastcall MFCreateFileBlockMap(
        __int64 a1,
        const WCHAR *a2,
        int a3,
        int a4,
        __int64 a5,
        int a6,
        int a7,
        __int64 *a8)
{
  __int64 v8; // rdi
  unsigned int v12; // r15d
  const char *v13; // rcx
  _QWORD *v14; // rbx
  DWORD LastError; // esi
  _QWORD *Value; // rax
  __int64 *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 *v22; // rsi
  int v23; // ebx
  _DWORD *v24; // rsi
  DWORD v25; // ebp
  _DWORD *v26; // rax
  __int64 *v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rdi
  __int64 v34; // rcx
  __int64 *v35; // rdi
  __int64 v36; // rax
  __int64 *v37; // rsi
  DWORD v38; // ebp
  __int64 *v39; // rax
  __int64 *v40; // rcx
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rdx
  __int64 *v44; // rdi
  __int64 v45; // rax
  __int64 *v46; // rsi
  DWORD v47; // ebp
  __int64 *v48; // rax
  __int64 *v49; // rcx
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 v53; // [rsp+40h] [rbp-58h]
  __int64 v54[9]; // [rsp+50h] [rbp-48h] BYREF

  v8 = qword_180124958;
  v12 = a1;
  if ( !qword_180124958 )
  {
    sub_1800EDCB8(a1);
    v8 = qword_180124958;
  }
  v13 = "MFCreateFileBlockMap";
  if ( *(_BYTE *)(v8 + 8) )
  {
    v14 = (_QWORD *)(v8 + 208);
    LastError = GetLastError();
    Value = TlsGetValue(*(_DWORD *)(v8 + 12));
    if ( Value )
    {
      v14 = Value;
    }
    else if ( !GetLastError() )
    {
      v17 = (__int64 *)qword_180124958;
      if ( !qword_180124958 )
      {
        v18 = MFGetCallStackTracingWeakReference(0);
        qword_180124958 = v18;
        if ( v18 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
        {
          v17 = (__int64 *)qword_180124958;
        }
        else
        {
          v17 = &qword_180123EB0;
          qword_180124958 = (__int64)&qword_180123EB0;
        }
      }
      v19 = (*(__int64 (__fastcall **)(__int64 *))*v17)(v17);
      if ( v19 )
        v14 = (_QWORD *)v19;
    }
    SetLastError(LastError);
    v20 = *((unsigned int *)v14 + 497);
    v13 = "MFCreateFileBlockMap";
    v8 = qword_180124958;
    if ( (unsigned int)v20 < *((_DWORD *)v14 + 498) )
    {
      v21 = 2 * v20;
      v14[v21] = "MFCreateFileBlockMap";
      LODWORD(v14[v21 + 1]) = 52;
    }
    ++*((_DWORD *)v14 + 497);
  }
  if ( (unsigned __int8)byte_18012480C >= 0x20u )
  {
    sub_1800EF9B8(*((_QWORD *)RequestContext + 22), 10, a3, v12, (__int64)a2, a3);
    v8 = qword_180124958;
  }
  v22 = a8;
  v54[0] = 0;
  if ( a8 )
  {
    *a8 = 0;
    v30 = sub_1800CD268(368);
    if ( v30 && (v32 = sub_1800EF6A0(v30), (v33 = v32) != 0) )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 8LL))(v32);
      v54[0] = v33;
      v23 = sub_180043F14(v33, v12, a2, a3, a4, a5, a6, a7, v53, 0);
      if ( v23 >= 0 )
      {
        *v22 = v33;
        goto LABEL_83;
      }
      v35 = (__int64 *)qword_180124958;
      if ( !qword_180124958 )
      {
        v36 = MFGetCallStackTracingWeakReference(v34);
        qword_180124958 = v36;
        if ( v36 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
        {
          v35 = (__int64 *)qword_180124958;
        }
        else
        {
          v35 = &qword_180123EB0;
          qword_180124958 = (__int64)&qword_180123EB0;
        }
      }
      if ( *((_BYTE *)v35 + 8) )
      {
        v37 = v35 + 26;
        v38 = GetLastError();
        v39 = (__int64 *)TlsGetValue(*((_DWORD *)v35 + 3));
        if ( v39 )
        {
          v37 = v39;
        }
        else if ( !GetLastError() )
        {
          v40 = (__int64 *)qword_180124958;
          if ( !qword_180124958 )
          {
            v41 = MFGetCallStackTracingWeakReference(0);
            qword_180124958 = v41;
            if ( v41 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
            {
              v40 = (__int64 *)qword_180124958;
            }
            else
            {
              v40 = &qword_180123EB0;
              qword_180124958 = (__int64)&qword_180123EB0;
            }
          }
          v42 = (*(__int64 (__fastcall **)(__int64 *))*v40)(v40);
          if ( v42 )
            v37 = (__int64 *)v42;
        }
        SetLastError(v38);
        if ( *((_DWORD *)v37 + 499) != v23 )
          sub_18003D3E0(v37, "MFCreateFileBlockMap", 84, (unsigned int)v23);
      }
      if ( !byte_180124808 )
      {
LABEL_82:
        sub_180038768(v54);
        goto LABEL_83;
      }
      v43 = 13;
    }
    else
    {
      v44 = (__int64 *)qword_180124958;
      if ( !qword_180124958 )
      {
        v45 = MFGetCallStackTracingWeakReference(v31);
        qword_180124958 = v45;
        if ( v45 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
        {
          v44 = (__int64 *)qword_180124958;
        }
        else
        {
          v44 = &qword_180123EB0;
          qword_180124958 = (__int64)&qword_180123EB0;
        }
      }
      v23 = -2147024882;
      if ( *((_BYTE *)v44 + 8) )
      {
        v46 = v44 + 26;
        v47 = GetLastError();
        v48 = (__int64 *)TlsGetValue(*((_DWORD *)v44 + 3));
        if ( v48 )
        {
          v46 = v48;
        }
        else if ( !GetLastError() )
        {
          v49 = (__int64 *)qword_180124958;
          if ( !qword_180124958 )
          {
            v50 = MFGetCallStackTracingWeakReference(0);
            qword_180124958 = v50;
            if ( v50 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
            {
              v49 = (__int64 *)qword_180124958;
            }
            else
            {
              v49 = &qword_180123EB0;
              qword_180124958 = (__int64)&qword_180123EB0;
            }
          }
          v51 = (*(__int64 (__fastcall **)(__int64 *))*v49)(v49);
          if ( v51 )
            v46 = (__int64 *)v51;
        }
        SetLastError(v47);
        if ( *((_DWORD *)v46 + 499) != -2147024882 )
          sub_18003D3E0(v46, "MFCreateFileBlockMap", 69, 2147942414LL);
      }
      if ( !byte_180124808 )
        goto LABEL_82;
      v43 = 12;
    }
    sub_18003F28C(*((_QWORD *)RequestContext + 2), v43, &stru_18010A930, 0, v23);
    goto LABEL_82;
  }
  if ( !v8 )
  {
    sub_1800EDCB8(v13);
    v8 = qword_180124958;
  }
  v23 = -2147467261;
  if ( *(_BYTE *)(v8 + 8) )
  {
    v24 = (_DWORD *)(v8 + 208);
    v25 = GetLastError();
    v26 = TlsGetValue(*(_DWORD *)(v8 + 12));
    if ( v26 )
    {
      v24 = v26;
    }
    else if ( !GetLastError() )
    {
      v27 = (__int64 *)qword_180124958;
      if ( !qword_180124958 )
      {
        v28 = MFGetCallStackTracingWeakReference(0);
        qword_180124958 = v28;
        if ( v28 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
        {
          v27 = (__int64 *)qword_180124958;
        }
        else
        {
          v27 = &qword_180123EB0;
          qword_180124958 = (__int64)&qword_180123EB0;
        }
      }
      v29 = (*(__int64 (__fastcall **)(__int64 *))*v27)(v27);
      if ( v29 )
        v24 = (_DWORD *)v29;
    }
    SetLastError(v25);
    if ( v24[499] != -2147467261 )
      sub_18003D3E0(v24, "MFCreateFileBlockMap", 61, 2147500035LL);
  }
  if ( byte_180124808 )
    sub_18003F28C(*((_QWORD *)RequestContext + 2), 11, &stru_18010A930, 0, -2147467261);
LABEL_83:
  sub_18000D210(&a8);
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x180042fe0  push    rbx
0x180042fe2  push    rbp
0x180042fe3  push    rsi
0x180042fe4  push    rdi
0x180042fe5  push    r12
0x180042fe7  push    r14
0x180042fe9  push    r15
0x180042feb  sub     rsp, 60h
0x180042fef  mov     rdi, cs:qword_180124958
0x180042ff6  mov     r12d, r9d
0x180042ff9  mov     ebp, r8d
0x180042ffc  mov     r14, rdx
0x180042fff  mov     r15d, ecx
0x180043002  test    rdi, rdi
0x180043005  jnz     short loc_180043013
0x180043007  call    sub_1800EDCB8
0x18004300c  mov     rdi, cs:qword_180124958
0x180043013  cmp     byte ptr [rdi+8], 0
0x180043017  lea     rcx, aMfcreatefilebl_0; "MFCreateFileBlockMap"
0x18004301e  jz      loc_1800430E8
0x180043024  lea     rbx, [rdi+0D0h]
0x18004302b  call    cs:GetLastError
0x180043031  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180043034  mov     esi, eax
0x180043036  call    cs:TlsGetValue
0x18004303c  test    rax, rax
0x18004303f  jz      short loc_180043046
0x180043041  mov     rbx, rax
0x180043044  jmp     short loc_1800430AF
0x180043046  call    cs:GetLastError
0x18004304c  test    eax, eax
0x18004304e  jnz     short loc_1800430AF
0x180043050  mov     rcx, cs:qword_180124958
0x180043057  test    rcx, rcx
0x18004305a  jnz     short loc_18004309D
0x18004305c  call    cs:MFGetCallStackTracingWeakReference
0x180043062  mov     cs:qword_180124958, rax
0x180043069  mov     rcx, rax
0x18004306c  test    rax, rax
0x18004306f  jz      short loc_18004308F
0x180043071  mov     rax, [rax]
0x180043074  mov     edx, 7F0h
0x180043079  mov     rax, [rax+8]
0x18004307d  call    j__guard_dispatch_icall
0x180043082  test    eax, eax
0x180043084  jz      short loc_18004308F
0x180043086  mov     rcx, cs:qword_180124958
0x18004308d  jmp     short loc_18004309D
0x18004308f  lea     rcx, qword_180123EB0
0x180043096  mov     cs:qword_180124958, rcx
0x18004309d  mov     rax, [rcx]
0x1800430a0  mov     rax, [rax]
0x1800430a3  call    j__guard_dispatch_icall
0x1800430a8  test    rax, rax
0x1800430ab  cmovnz  rbx, rax
0x1800430af  mov     ecx, esi; dwErrCode
0x1800430b1  call    cs:SetLastError
0x1800430b7  mov     eax, [rbx+7C4h]
0x1800430bd  lea     rcx, aMfcreatefilebl_0; "MFCreateFileBlockMap"
0x1800430c4  mov     rdi, cs:qword_180124958
0x1800430cb  cmp     eax, [rbx+7C8h]
0x1800430d1  jnb     short loc_1800430E2
0x1800430d3  add     rax, rax
0x1800430d6  mov     [rbx+rax*8], rcx
0x1800430da  mov     dword ptr [rbx+rax*8+8], 34h ; '4'
0x1800430e2  inc     dword ptr [rbx+7C4h]
0x1800430e8  cmp     cs:byte_18012480C, 20h ; ' '
0x1800430ef  jb      short loc_18004311C
0x1800430f1  mov     rcx, cs:RequestContext
0x1800430f8  mov     edx, 0Ah
0x1800430fd  mov     dword ptr [rsp+98h+var_70], ebp
0x180043101  mov     r9d, r15d
0x180043104  mov     [rsp+98h+var_78], r14
0x180043109  mov     rcx, [rcx+0B0h]
0x180043110  call    sub_1800EF9B8
0x180043115  mov     rdi, cs:qword_180124958
0x18004311c  mov     rsi, [rsp+98h+arg_38]
0x180043124  mov     [rsp+98h+var_48], 0
0x18004312d  test    rsi, rsi
0x180043130  jnz     loc_18004323E
0x180043136  test    rdi, rdi
0x180043139  jnz     short loc_180043147
0x18004313b  call    sub_1800EDCB8
0x180043140  mov     rdi, cs:qword_180124958
0x180043147  cmp     byte ptr [rdi+8], 0
0x18004314b  mov     ebx, 80004003h
0x180043150  jz      loc_180043209
0x180043156  lea     rsi, [rdi+0D0h]
0x18004315d  call    cs:GetLastError
0x180043163  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180043166  mov     ebp, eax
0x180043168  call    cs:TlsGetValue
0x18004316e  test    rax, rax
0x180043171  jz      short loc_180043178
0x180043173  mov     rsi, rax
0x180043176  jmp     short loc_1800431E1
0x180043178  call    cs:GetLastError
0x18004317e  test    eax, eax
0x180043180  jnz     short loc_1800431E1
0x180043182  mov     rcx, cs:qword_180124958
0x180043189  test    rcx, rcx
0x18004318c  jnz     short loc_1800431CF
0x18004318e  call    cs:MFGetCallStackTracingWeakReference
0x180043194  mov     cs:qword_180124958, rax
0x18004319b  mov     rcx, rax
0x18004319e  test    rax, rax
0x1800431a1  jz      short loc_1800431C1
0x1800431a3  mov     rax, [rax]
0x1800431a6  mov     edx, 7F0h
0x1800431ab  mov     rax, [rax+8]
0x1800431af  call    j__guard_dispatch_icall
0x1800431b4  test    eax, eax
0x1800431b6  jz      short loc_1800431C1
0x1800431b8  mov     rcx, cs:qword_180124958
0x1800431bf  jmp     short loc_1800431CF
0x1800431c1  lea     rcx, qword_180123EB0
0x1800431c8  mov     cs:qword_180124958, rcx
0x1800431cf  mov     rax, [rcx]
0x1800431d2  mov     rax, [rax]
0x1800431d5  call    j__guard_dispatch_icall
0x1800431da  test    rax, rax
0x1800431dd  cmovnz  rsi, rax
0x1800431e1  mov     ecx, ebp; dwErrCode
0x1800431e3  call    cs:SetLastError
0x1800431e9  cmp     [rsi+7CCh], ebx
0x1800431ef  jz      short loc_180043209
0x1800431f1  mov     r9d, ebx
0x1800431f4  lea     rdx, aMfcreatefilebl_0; "MFCreateFileBlockMap"
0x1800431fb  mov     r8d, 3Dh ; '='
0x180043201  mov     rcx, rsi
0x180043204  call    sub_18003D3E0
0x180043209  cmp     cs:byte_180124808, 1
0x180043210  jb      loc_180043536
0x180043216  mov     rcx, cs:RequestContext
0x18004321d  lea     r8, stru_18010A930
0x180043224  mov     edx, 0Bh
0x180043229  mov     dword ptr [rsp+98h+var_78], ebx
0x18004322d  xor     r9d, r9d
0x180043230  mov     rcx, [rcx+10h]
0x180043234  call    sub_18003F28C
0x180043239  jmp     loc_180043536
0x18004323e  mov     ecx, 170h
0x180043243  mov     qword ptr [rsi], 0
0x18004324a  call    sub_1800CD268
0x18004324f  test    rax, rax
0x180043252  jz      loc_1800433F1
0x180043258  mov     rcx, rax
0x18004325b  call    sub_1800EF6A0
0x180043260  mov     rdi, rax
0x180043263  test    rax, rax
0x180043266  jz      loc_1800433F1
0x18004326c  mov     rcx, [rax]
0x18004326f  mov     rax, [rcx+8]
0x180043273  mov     rcx, rdi
0x180043276  call    j__guard_dispatch_icall
0x18004327b  mov     ecx, [rsp+98h+arg_30]
0x180043282  mov     r9d, ebp
0x180043285  mov     rax, [rsp+98h+arg_20]
0x18004328d  mov     r8, r14
0x180043290  mov     [rsp+98h+var_50], 0
0x180043295  mov     edx, r15d
0x180043298  mov     [rsp+98h+var_60], ecx
0x18004329c  mov     ecx, [rsp+98h+arg_28]
0x1800432a3  mov     [rsp+98h+var_68], ecx
0x1800432a7  mov     rcx, rdi
0x1800432aa  mov     [rsp+98h+var_70], rax
0x1800432af  mov     dword ptr [rsp+98h+var_78], r12d
0x1800432b4  mov     [rsp+98h+var_48], rdi
0x1800432b9  call    sub_180043F14
0x1800432be  mov     ebx, eax
0x1800432c0  test    eax, eax
0x1800432c2  jns     loc_1800433E9
0x1800432c8  mov     rdi, cs:qword_180124958
0x1800432cf  test    rdi, rdi
0x1800432d2  jnz     short loc_180043315
0x1800432d4  call    cs:MFGetCallStackTracingWeakReference
0x1800432da  mov     cs:qword_180124958, rax
0x1800432e1  mov     rcx, rax
0x1800432e4  test    rax, rax
0x1800432e7  jz      short loc_180043307
0x1800432e9  mov     rax, [rax]
0x1800432ec  mov     edx, 7F0h
0x1800432f1  mov     rax, [rax+8]
0x1800432f5  call    j__guard_dispatch_icall
0x1800432fa  test    eax, eax
0x1800432fc  jz      short loc_180043307
0x1800432fe  mov     rdi, cs:qword_180124958
0x180043305  jmp     short loc_180043315
0x180043307  lea     rdi, qword_180123EB0
0x18004330e  mov     cs:qword_180124958, rdi
0x180043315  cmp     byte ptr [rdi+8], 0
0x180043319  jz      loc_1800433D2
0x18004331f  lea     rsi, [rdi+0D0h]
0x180043326  call    cs:GetLastError
0x18004332c  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18004332f  mov     ebp, eax
0x180043331  call    cs:TlsGetValue
0x180043337  test    rax, rax
0x18004333a  jz      short loc_180043341
0x18004333c  mov     rsi, rax
0x18004333f  jmp     short loc_1800433AA
0x180043341  call    cs:GetLastError
0x180043347  test    eax, eax
0x180043349  jnz     short loc_1800433AA
0x18004334b  mov     rcx, cs:qword_180124958
0x180043352  test    rcx, rcx
0x180043355  jnz     short loc_180043398
0x180043357  call    cs:MFGetCallStackTracingWeakReference
0x18004335d  mov     cs:qword_180124958, rax
0x180043364  mov     rcx, rax
0x180043367  test    rax, rax
0x18004336a  jz      short loc_18004338A
0x18004336c  mov     rax, [rax]
0x18004336f  mov     edx, 7F0h
0x180043374  mov     rax, [rax+8]
0x180043378  call    j__guard_dispatch_icall
0x18004337d  test    eax, eax
0x18004337f  jz      short loc_18004338A
0x180043381  mov     rcx, cs:qword_180124958
0x180043388  jmp     short loc_180043398
0x18004338a  lea     rcx, qword_180123EB0
0x180043391  mov     cs:qword_180124958, rcx
0x180043398  mov     rax, [rcx]
0x18004339b  mov     rax, [rax]
0x18004339e  call    j__guard_dispatch_icall
0x1800433a3  test    rax, rax
0x1800433a6  cmovnz  rsi, rax
0x1800433aa  mov     ecx, ebp; dwErrCode
0x1800433ac  call    cs:SetLastError
0x1800433b2  cmp     [rsi+7CCh], ebx
0x1800433b8  jz      short loc_1800433D2
0x1800433ba  mov     r9d, ebx
0x1800433bd  lea     rdx, aMfcreatefilebl_0; "MFCreateFileBlockMap"
0x1800433c4  mov     r8d, 54h ; 'T'
0x1800433ca  mov     rcx, rsi
0x1800433cd  call    sub_18003D3E0
0x1800433d2  cmp     cs:byte_180124808, 1
0x1800433d9  jb      loc_18004352C
0x1800433df  mov     edx, 0Dh
0x1800433e4  jmp     loc_18004350E
0x1800433e9  mov     [rsi], rdi
0x1800433ec  jmp     loc_180043536
0x1800433f1  mov     rdi, cs:qword_180124958
0x1800433f8  test    rdi, rdi
0x1800433fb  jnz     short loc_18004343E
0x1800433fd  call    cs:MFGetCallStackTracingWeakReference
0x180043403  mov     cs:qword_180124958, rax
0x18004340a  mov     rcx, rax
0x18004340d  test    rax, rax
0x180043410  jz      short loc_180043430
0x180043412  mov     rax, [rax]
0x180043415  mov     edx, 7F0h
0x18004341a  mov     rax, [rax+8]
0x18004341e  call    j__guard_dispatch_icall
0x180043423  test    eax, eax
0x180043425  jz      short loc_180043430
0x180043427  mov     rdi, cs:qword_180124958
0x18004342e  jmp     short loc_18004343E
0x180043430  lea     rdi, qword_180123EB0
0x180043437  mov     cs:qword_180124958, rdi
0x18004343e  cmp     byte ptr [rdi+8], 0
0x180043442  mov     ebx, 8007000Eh
0x180043447  jz      loc_180043500
0x18004344d  lea     rsi, [rdi+0D0h]
0x180043454  call    cs:GetLastError
0x18004345a  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18004345d  mov     ebp, eax
0x18004345f  call    cs:TlsGetValue
0x180043465  test    rax, rax
0x180043468  jz      short loc_18004346F
0x18004346a  mov     rsi, rax
0x18004346d  jmp     short loc_1800434D8
0x18004346f  call    cs:GetLastError
0x180043475  test    eax, eax
0x180043477  jnz     short loc_1800434D8
0x180043479  mov     rcx, cs:qword_180124958
0x180043480  test    rcx, rcx
0x180043483  jnz     short loc_1800434C6
0x180043485  call    cs:MFGetCallStackTracingWeakReference
0x18004348b  mov     cs:qword_180124958, rax
0x180043492  mov     rcx, rax
0x180043495  test    rax, rax
0x180043498  jz      short loc_1800434B8
0x18004349a  mov     rax, [rax]
0x18004349d  mov     edx, 7F0h
0x1800434a2  mov     rax, [rax+8]
0x1800434a6  call    j__guard_dispatch_icall
0x1800434ab  test    eax, eax
0x1800434ad  jz      short loc_1800434B8
0x1800434af  mov     rcx, cs:qword_180124958
0x1800434b6  jmp     short loc_1800434C6
0x1800434b8  lea     rcx, qword_180123EB0
0x1800434bf  mov     cs:qword_180124958, rcx
0x1800434c6  mov     rax, [rcx]
0x1800434c9  mov     rax, [rax]
0x1800434cc  call    j__guard_dispatch_icall
0x1800434d1  test    rax, rax
0x1800434d4  cmovnz  rsi, rax
0x1800434d8  mov     ecx, ebp; dwErrCode
0x1800434da  call    cs:SetLastError
  ... truncated ...
```
