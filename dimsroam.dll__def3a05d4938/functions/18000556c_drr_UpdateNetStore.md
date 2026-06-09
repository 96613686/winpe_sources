# _drr_UpdateNetStore

- ea: `0x18000556c`
- end: `0x180005a27`
- name: `_drr_UpdateNetStore`
- size: `1211`
- prototype: `__int64 __fastcall(__int64 *, __int64 *, __int64 *, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180006230`

## callees

- `0x18000556c`
- `0x18000702c`
- `0x18000d34c`
- `0x18000d892`
- `0x18000d8d0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800056f7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000577e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800056f7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000577e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800059cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800059cc`
- `ntdll!EtwEventWrite` at `0x1800059c3`
- `ntdll!EtwEventWrite` at `0x1800059c3`

## pseudocode

```c
__int64 __fastcall drr_UpdateNetStore(__int64 *a1, __int64 *a2, __int64 *a3, void *a4)
{
  __int64 v4; // rdi
  unsigned int v6; // r13d
  unsigned int i; // r14d
  __int64 v10; // rbx
  DWORD v11; // eax
  DWORD v12; // eax
  __int64 result; // rax
  __int64 v14; // rax
  DWORD v15; // eax
  __int64 v16; // rdx
  _WORD *v17; // rdi
  _WORD *v18; // rax
  _OWORD *v19; // rax
  _OWORD *v20; // rcx
  _OWORD *v21; // rcx
  __int64 v22; // rax
  _QWORD *v23; // rcx
  DWORD v24; // eax
  DWORD v25; // ecx
  int v26; // eax
  HLOCAL v27; // rbx
  __int64 v28; // rax
  int v29; // eax
  __int64 v30; // rcx
  __int64 *v31; // rdx
  int v32; // eax
  __int64 v33; // rax
  int v34; // eax
  __int64 v35; // r8
  unsigned int j; // edx
  unsigned int k; // ecx
  _DWORD *v38; // r9
  _OWORD *v39; // [rsp+20h] [rbp-58h] BYREF
  DWORD v40; // [rsp+28h] [rbp-50h] BYREF
  HLOCAL hMem; // [rsp+30h] [rbp-48h]
  __int64 v42; // [rsp+38h] [rbp-40h]
  DWORD *v43; // [rsp+40h] [rbp-38h] BYREF
  __int64 v44; // [rsp+48h] [rbp-30h]
  __int64 *v45; // [rsp+50h] [rbp-28h]
  int v46; // [rsp+58h] [rbp-20h]
  int v47; // [rsp+5Ch] [rbp-1Ch]

  v4 = *a2;
  v6 = *((_DWORD *)a2 + 2);
  hMem = a4;
  v40 = 0;
  v39 = 0;
  while ( 1 )
  {
    v42 = v4;
    for ( i = 0; i < v6; ++i )
    {
      v10 = *(_QWORD *)(v4 + 8LL * i);
      if ( (*(_BYTE *)(v10 + 4) & 5) != 0 )
        continue;
      if ( ((*(_DWORD *)v10 - 3) & 0xFFFFFFFD) == 0 )
      {
        v11 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*a1 + 32))(a1, *(_QWORD *)(v10 + 8));
        if ( (v11 & 0x1FFF0000) == 0x70000 )
          v11 = (unsigned __int16)v11;
        v40 = v11;
        if ( v11 )
          return 0;
      }
      if ( *(_DWORD *)v10 == 1 )
      {
        v12 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*a1 + 24))(a1, *(_QWORD *)(v10 + 8));
        if ( (v12 & 0x1FFF0000) == 0x70000 )
          v12 = (unsigned __int16)v12;
        v40 = v12;
        if ( v12 )
          return 0;
        continue;
      }
      if ( ((*(_DWORD *)v10 - 3) & 0xFFFFFFFD) != 0 )
        continue;
      v14 = *a1;
      v39 = 0;
      v15 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _OWORD **))(v14 + 40))(a1, *(_QWORD *)(v10 + 8), &v39);
      if ( (v15 & 0x1FFF0000) == 0x70000 )
        v15 = (unsigned __int16)v15;
      v40 = v15;
      if ( v15 && v15 != 1168 )
        return 0;
      if ( *(_DWORD *)v10 == 3 )
      {
        if ( v15 != 1168 )
        {
          v16 = *((unsigned __int16 *)v39 + 53);
          if ( (_WORD)v16 )
          {
            v18 = LocalAlloc(0, *(unsigned int *)(*(_QWORD *)(v10 + 8) + 128LL) + v16 + 132);
            v17 = v18;
            if ( !v18 )
              return 0;
            memcpy_0(v18, *(const void **)(v10 + 8), *(unsigned int *)(*(_QWORD *)(v10 + 8) + 128LL) + 132LL);
            v17[53] = *((_WORD *)v39 + 53);
            memcpy_0(
              (char *)v17 + *(unsigned int *)(*(_QWORD *)(v10 + 8) + 128LL) + 132,
              (char *)v39 + *((unsigned int *)v39 + 32) + 132,
              *((unsigned __int16 *)v39 + 53));
            DRR_SecureFreeRoamingToken(v39);
            v39 = v17;
            goto LABEL_32;
          }
          DRR_SecureFreeRoamingToken(v39);
          v39 = 0;
        }
        v17 = *(_WORD **)(v10 + 8);
      }
      else
      {
        if ( v15 == 1168 )
        {
          v19 = LocalAlloc(0, 0x84u);
          v39 = v19;
          if ( !v19 )
            return 0;
          v20 = *(_OWORD **)(v10 + 8);
          *v19 = *v20;
          v19[1] = v20[1];
          v19[2] = v20[2];
          v19[3] = v20[3];
          v19[4] = v20[4];
          v19[5] = v20[5];
          *((_WORD *)v39 + 53) = 0;
          v21 = v39;
          *(_OWORD *)((char *)v39 + 108) = xmmword_18000FCD0;
          *((_DWORD *)v21 + 31) = 151509167;
          *((_DWORD *)v39 + 32) = 0;
        }
        v22 = *(_QWORD *)(v10 + 8);
        v23 = hMem;
        if ( (*(_BYTE *)(v22 + 104) & 1) != 0 )
          v23 = (_QWORD *)(v22 + 96);
        *((_QWORD *)v39 + 12) = *v23;
        *((_WORD *)v39 + 52) = 1;
        v17 = v39;
      }
LABEL_32:
      v24 = (*(__int64 (__fastcall **)(__int64 *, _WORD *))(*a1 + 24))(a1, v17);
      if ( (v24 & 0x1FFF0000) == 0x70000 )
        v24 = (unsigned __int16)v24;
      v40 = v24;
      if ( v24 )
        return 0;
      DRR_SecureFreeRoamingToken(v39);
      v4 = v42;
      v39 = 0;
    }
    if ( v4 == *a3 )
      break;
    v4 = *a3;
    v6 = *((_DWORD *)a3 + 2);
  }
  v25 = (*(__int64 (__fastcall **)(__int64 *, HLOCAL))(*a1 + 80))(a1, hMem);
  if ( (v25 & 0x1FFF0000) == 0x70000 )
    v25 = (unsigned __int16)v25;
  v40 = v25;
  if ( v25 )
  {
    if ( v25 == 8202 )
    {
      if ( (unsigned int)g_dwLoglevel <= 1 )
        return 0;
      hMem = 0;
      v43 = &v40;
      v44 = 4;
      v26 = LogErrorCodeAndText(0x200Au);
      v27 = hMem;
      if ( v26 && hMem )
      {
        v28 = -1;
        do
          ++v28;
        while ( *((_WORD *)hMem + v28) );
        v45 = (__int64 *)hMem;
        v29 = 2 * v28 + 2;
      }
      else
      {
        v45 = &qword_18000FCA0;
        v29 = 2;
      }
      v30 = qword_1800138C8;
      v46 = v29;
      v47 = 0;
      if ( !qword_1800138C8 )
      {
LABEL_63:
        LocalFree(v27);
        return 0;
      }
      v31 = DRR_LOG_ERROR_NOATTRIBUTE;
LABEL_62:
      EtwEventWrite(v30, v31, 2, &v43);
      goto LABEL_63;
    }
    result = 0;
    if ( (unsigned int)g_dwLoglevel > 1 )
    {
      hMem = 0;
      v43 = &v40;
      v44 = 4;
      v32 = LogErrorCodeAndText(v25);
      v27 = hMem;
      if ( v32 && hMem )
      {
        v33 = -1;
        do
          ++v33;
        while ( *((_WORD *)hMem + v33) );
        v45 = (__int64 *)hMem;
        v34 = 2 * v33 + 2;
      }
      else
      {
        v45 = &qword_18000FCA0;
        v34 = 2;
      }
      v30 = qword_1800138C8;
      v46 = v34;
      v47 = 0;
      if ( !qword_1800138C8 )
        goto LABEL_63;
      v31 = DRR_LOG_ERROR_NETSTOREWRITE;
      goto LABEL_62;
    }
  }
  else
  {
    v35 = *a2;
    for ( j = *((_DWORD *)a2 + 2); ; j = *((_DWORD *)a3 + 2) )
    {
      for ( k = 0; k < j; ++k )
      {
        v38 = *(_DWORD **)(v35 + 8LL * k);
        if ( (v38[1] & 5) == 0 && ((*v38 - 1) & 0xFFFFFFF9) == 0 && *v38 != 7 )
          v38[1] = 1;
      }
      result = 1;
      if ( v35 == *a3 )
        break;
      v35 = *a3;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000556c  push    rbp
0x18000556e  push    rbx
0x18000556f  push    rsi
0x180005570  push    rdi
0x180005571  push    r12
0x180005573  push    r13
0x180005575  push    r14
0x180005577  push    r15
0x180005579  mov     rbp, rsp
0x18000557c  sub     rsp, 78h
0x180005580  mov     rax, cs:__security_cookie
0x180005587  xor     rax, rsp
0x18000558a  mov     [rbp+var_18], rax
0x18000558e  mov     rdi, [rdx]
0x180005591  mov     rsi, rcx
0x180005594  mov     r13d, [rdx+8]
0x180005598  xor     ecx, ecx
0x18000559a  mov     [rbp+hMem], r9
0x18000559e  mov     r15, r8
0x1800055a1  mov     r12, rdx
0x1800055a4  mov     [rbp+var_50], ecx
0x1800055a7  mov     [rbp+var_58], rcx
0x1800055ab  lea     ebx, [rcx+1]
0x1800055ae  mov     [rbp+var_40], rdi
0x1800055b2  mov     r14d, ecx
0x1800055b5  test    r13d, r13d
0x1800055b8  jz      loc_18000586A
0x1800055be  mov     eax, r14d
0x1800055c1  mov     rbx, [rdi+rax*8]
0x1800055c5  test    byte ptr [rbx+4], 5
0x1800055c9  jnz     loc_180005859
0x1800055cf  mov     eax, [rbx]
0x1800055d1  sub     eax, 3
0x1800055d4  test    eax, 0FFFFFFFDh
0x1800055d9  jnz     short loc_18000560A
0x1800055db  mov     rax, [rsi]
0x1800055de  mov     rcx, rsi
0x1800055e1  mov     rdx, [rbx+8]
0x1800055e5  mov     rax, [rax+20h]
0x1800055e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055ee  mov     ecx, eax
0x1800055f0  and     ecx, 1FFF0000h
0x1800055f6  cmp     ecx, 70000h
0x1800055fc  jnz     short loc_180005601
0x1800055fe  movzx   eax, ax
0x180005601  xor     ecx, ecx
0x180005603  mov     [rbp+var_50], eax
0x180005606  test    eax, eax
0x180005608  jnz     short loc_180005644
0x18000560a  mov     eax, [rbx]
0x18000560c  cmp     eax, 1
0x18000560f  jnz     short loc_180005663
0x180005611  mov     rax, [rsi]
0x180005614  mov     rcx, rsi
0x180005617  mov     rdx, [rbx+8]
0x18000561b  mov     rax, [rax+18h]
0x18000561f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005624  mov     ecx, eax
0x180005626  and     ecx, 1FFF0000h
0x18000562c  cmp     ecx, 70000h
0x180005632  jnz     short loc_180005637
0x180005634  movzx   eax, ax
0x180005637  xor     ecx, ecx
0x180005639  mov     [rbp+var_50], eax
0x18000563c  test    eax, eax
0x18000563e  jz      loc_180005859
0x180005644  mov     eax, ecx
0x180005646  mov     rcx, [rbp+var_18]
0x18000564a  xor     rcx, rsp; StackCookie
0x18000564d  call    __security_check_cookie
0x180005652  add     rsp, 78h
0x180005656  pop     r15
0x180005658  pop     r14
0x18000565a  pop     r13
0x18000565c  pop     r12
0x18000565e  pop     rdi
0x18000565f  pop     rsi
0x180005660  pop     rbx
0x180005661  pop     rbp
0x180005662  retn
0x180005663  add     eax, 0FFFFFFFDh
0x180005666  test    eax, 0FFFFFFFDh
0x18000566b  jnz     loc_180005859
0x180005671  mov     rax, [rsi]
0x180005674  lea     r8, [rbp+var_58]
0x180005678  mov     [rbp+var_58], rcx
0x18000567c  mov     rcx, rsi
0x18000567f  mov     rdx, [rbx+8]
0x180005683  mov     rax, [rax+28h]
0x180005687  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000568c  mov     ecx, eax
0x18000568e  and     ecx, 1FFF0000h
0x180005694  cmp     ecx, 70000h
0x18000569a  jnz     short loc_18000569F
0x18000569c  movzx   eax, ax
0x18000569f  xor     edi, edi
0x1800056a1  mov     [rbp+var_50], eax
0x1800056a4  mov     ecx, 490h
0x1800056a9  test    eax, eax
0x1800056ab  jz      short loc_1800056B5
0x1800056ad  cmp     eax, ecx
0x1800056af  jnz     loc_1800059D2
0x1800056b5  cmp     dword ptr [rbx], 3
0x1800056b8  jnz     loc_180005773
0x1800056be  cmp     eax, ecx
0x1800056c0  jz      short loc_1800056D8
0x1800056c2  mov     rcx, [rbp+var_58]
0x1800056c6  movzx   edx, word ptr [rcx+6Ah]
0x1800056ca  test    dx, dx
0x1800056cd  jnz     short loc_1800056E1
0x1800056cf  call    DRR_SecureFreeRoamingToken
0x1800056d4  mov     [rbp+var_58], rdi
0x1800056d8  mov     rdi, [rbx+8]
0x1800056dc  jmp     loc_18000581A
0x1800056e1  mov     rax, [rbx+8]
0x1800056e5  add     rdx, 84h
0x1800056ec  mov     ecx, [rax+80h]
0x1800056f2  add     rdx, rcx; uBytes
0x1800056f5  xor     ecx, ecx; uFlags
0x1800056f7  call    cs:__imp_LocalAlloc
0x1800056fd  mov     rdi, rax
0x180005700  test    rax, rax
0x180005703  jz      loc_18000587B
0x180005709  mov     rdx, [rbx+8]; Src
0x18000570d  mov     rcx, rax; void *
0x180005710  mov     r8d, [rdx+80h]
0x180005717  add     r8, 84h; Size
0x18000571e  call    memcpy_0
0x180005723  mov     rax, [rbp+var_58]
0x180005727  movzx   ecx, word ptr [rax+6Ah]
0x18000572b  mov     [rdi+6Ah], cx
0x18000572f  mov     rcx, [rbp+var_58]
0x180005733  mov     eax, [rcx+80h]
0x180005739  lea     rdx, [rcx+84h]
0x180005740  movzx   r8d, word ptr [rcx+6Ah]; Size
0x180005745  add     rdx, rax; Src
0x180005748  mov     rax, [rbx+8]
0x18000574c  mov     ecx, [rax+80h]
0x180005752  add     rcx, 84h
0x180005759  add     rcx, rdi; void *
0x18000575c  call    memcpy_0
0x180005761  mov     rcx, [rbp+var_58]
0x180005765  call    DRR_SecureFreeRoamingToken
0x18000576a  mov     [rbp+var_58], rdi
0x18000576e  jmp     loc_18000581A
0x180005773  cmp     eax, ecx
0x180005775  jnz     short loc_1800057ED
0x180005777  mov     edx, 84h; uBytes
0x18000577c  xor     ecx, ecx; uFlags
0x18000577e  call    cs:__imp_LocalAlloc
0x180005784  mov     [rbp+var_58], rax
0x180005788  test    rax, rax
0x18000578b  jz      loc_1800059D2
0x180005791  mov     rcx, [rbx+8]
0x180005795  movups  xmm0, xmmword ptr [rcx]
0x180005798  movups  xmmword ptr [rax], xmm0
0x18000579b  movups  xmm1, xmmword ptr [rcx+10h]
0x18000579f  movups  xmmword ptr [rax+10h], xmm1
0x1800057a3  movups  xmm0, xmmword ptr [rcx+20h]
0x1800057a7  movups  xmmword ptr [rax+20h], xmm0
0x1800057ab  movups  xmm1, xmmword ptr [rcx+30h]
0x1800057af  movups  xmmword ptr [rax+30h], xmm1
0x1800057b3  movups  xmm0, xmmword ptr [rcx+40h]
0x1800057b7  movups  xmmword ptr [rax+40h], xmm0
0x1800057bb  movups  xmm1, xmmword ptr [rcx+50h]
0x1800057bf  movups  xmmword ptr [rax+50h], xmm1
0x1800057c3  mov     rax, [rbp+var_58]
0x1800057c7  mov     [rax+6Ah], di
0x1800057cb  mov     rcx, [rbp+var_58]
0x1800057cf  movups  xmm0, cs:xmmword_18000FCD0
0x1800057d6  movups  xmmword ptr [rcx+6Ch], xmm0
0x1800057da  mov     eax, cs:dword_18000FCE0
0x1800057e0  mov     [rcx+7Ch], eax
0x1800057e3  mov     rax, [rbp+var_58]
0x1800057e7  mov     [rax+80h], edi
0x1800057ed  mov     rax, [rbx+8]
0x1800057f1  mov     edx, 1
0x1800057f6  mov     rcx, [rbp+hMem]
0x1800057fa  test    [rax+68h], dl
0x1800057fd  jz      short loc_180005803
0x1800057ff  lea     rcx, [rax+60h]
0x180005803  mov     rax, [rbp+var_58]
0x180005807  mov     rcx, [rcx]
0x18000580a  mov     [rax+60h], rcx
0x18000580e  mov     rax, [rbp+var_58]
0x180005812  mov     [rax+68h], dx
0x180005816  mov     rdi, [rbp+var_58]
0x18000581a  mov     rax, [rsi]
0x18000581d  mov     rdx, rdi
0x180005820  mov     rcx, rsi
0x180005823  mov     rax, [rax+18h]
0x180005827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000582c  mov     ecx, eax
0x18000582e  and     ecx, 1FFF0000h
0x180005834  cmp     ecx, 70000h
0x18000583a  jnz     short loc_18000583F
0x18000583c  movzx   eax, ax
0x18000583f  mov     [rbp+var_50], eax
0x180005842  test    eax, eax
0x180005844  jnz     short loc_18000587B
0x180005846  mov     rcx, [rbp+var_58]
0x18000584a  call    DRR_SecureFreeRoamingToken
0x18000584f  mov     rdi, [rbp+var_40]
0x180005853  xor     ecx, ecx
0x180005855  mov     [rbp+var_58], rcx
0x180005859  mov     ebx, 1
0x18000585e  add     r14d, ebx
0x180005861  cmp     r14d, r13d
0x180005864  jb      loc_1800055BE
0x18000586a  cmp     rdi, [r15]
0x18000586d  jz      short loc_180005882
0x18000586f  mov     rdi, [r15]
0x180005872  mov     r13d, [r15+8]
0x180005876  jmp     loc_1800055AE
0x18000587b  xor     eax, eax
0x18000587d  jmp     loc_180005646
0x180005882  mov     rax, [rsi]
0x180005885  mov     rcx, rsi
0x180005888  mov     rdx, [rbp+hMem]
0x18000588c  mov     rax, [rax+50h]
0x180005890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005895  mov     ecx, eax
0x180005897  and     eax, 1FFF0000h
0x18000589c  cmp     eax, 70000h
0x1800058a1  jnz     short loc_1800058A6
0x1800058a3  movzx   ecx, cx; dwMessageId
0x1800058a6  xor     edi, edi
0x1800058a8  mov     [rbp+var_50], ecx
0x1800058ab  test    ecx, ecx
0x1800058ad  jz      loc_1800059D9
0x1800058b3  cmp     ecx, 200Ah
0x1800058b9  jnz     loc_180005940
0x1800058bf  cmp     cs:g_dwLoglevel, ebx
0x1800058c5  jbe     loc_1800059D2
0x1800058cb  lea     rax, [rbp+var_50]
0x1800058cf  mov     [rbp+hMem], rdi
0x1800058d3  lea     rdx, [rbp+hMem]
0x1800058d7  mov     [rbp+var_38], rax
0x1800058db  mov     [rbp+var_30], 4
0x1800058e3  call    _LogErrorCodeAndText
0x1800058e8  mov     rbx, [rbp+hMem]
0x1800058ec  lea     r8d, [rdi+2]
0x1800058f0  test    eax, eax
0x1800058f2  jz      short loc_180005913
0x1800058f4  test    rbx, rbx
0x1800058f7  jz      short loc_180005913
0x1800058f9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800058fd  inc     rax
0x180005900  cmp     [rbx+rax*2], di
0x180005904  jnz     short loc_1800058FD
0x180005906  mov     [rbp+var_28], rbx
0x18000590a  lea     eax, ds:2[rax*2]
0x180005911  jmp     short loc_180005921
0x180005913  lea     rax, qword_18000FCA0
0x18000591a  mov     [rbp+var_28], rax
0x18000591e  mov     eax, r8d
0x180005921  mov     rcx, cs:qword_1800138C8
0x180005928  mov     [rbp+var_20], eax
0x18000592b  mov     [rbp+var_1C], edi
0x18000592e  test    rcx, rcx
0x180005931  jz      loc_1800059C9
0x180005937  lea     rdx, DRR_LOG_ERROR_NOATTRIBUTE
0x18000593e  jmp     short loc_1800059BF
0x180005940  cmp     cs:g_dwLoglevel, ebx
0x180005946  mov     eax, edi
0x180005948  jbe     loc_180005646
0x18000594e  lea     rax, [rbp+var_50]
0x180005952  mov     [rbp+hMem], rdi
0x180005956  lea     rdx, [rbp+hMem]
0x18000595a  mov     [rbp+var_38], rax
0x18000595e  mov     [rbp+var_30], 4
0x180005966  call    _LogErrorCodeAndText
0x18000596b  mov     rbx, [rbp+hMem]
0x18000596f  mov     r8d, 2
0x180005975  test    eax, eax
0x180005977  jz      short loc_180005998
0x180005979  test    rbx, rbx
0x18000597c  jz      short loc_180005998
0x18000597e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005982  inc     rax
0x180005985  cmp     [rbx+rax*2], di
0x180005989  jnz     short loc_180005982
0x18000598b  mov     [rbp+var_28], rbx
0x18000598f  lea     eax, ds:2[rax*2]
0x180005996  jmp     short loc_1800059A6
0x180005998  lea     rax, qword_18000FCA0
0x18000599f  mov     [rbp+var_28], rax
0x1800059a3  mov     eax, r8d
0x1800059a6  mov     rcx, cs:qword_1800138C8
0x1800059ad  mov     [rbp+var_20], eax
0x1800059b0  mov     [rbp+var_1C], edi
0x1800059b3  test    rcx, rcx
0x1800059b6  jz      short loc_1800059C9
0x1800059b8  lea     rdx, DRR_LOG_ERROR_NETSTOREWRITE
0x1800059bf  lea     r9, [rbp+var_38]
0x1800059c3  call    cs:__imp_EtwEventWrite
0x1800059c9  mov     rcx, rbx; hMem
0x1800059cc  call    cs:__imp_LocalFree
0x1800059d2  mov     eax, edi
0x1800059d4  jmp     loc_180005646
  ... truncated ...
```
