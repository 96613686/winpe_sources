# MSQAUICreateHostWindow

- ea: `0x18000ca70`
- end: `0x18000d6d6`
- name: `MSQAUICreateHostWindow`
- size: `3174`
- prototype: ``
- caller_count: `0`
- callee_count: `32`
- tags: ``

## callees

- `0x180003e60`
- `0x180003fa0`
- `0x180005740`
- `0x180007b70`
- `0x180007c80`
- `0x180007f80`
- `0x1800082f0`
- `0x180008510`
- `0x180008cd0`
- `0x180008ed0`
- `0x180009160`
- `0x1800098a0`
- `0x180009b00`
- `0x18000a090`
- `0x18000a650`
- `0x18000ca70`
- `0x180062f80`
- `0x180064230`
- `0x180076e00`
- `0x180077240`
- `0x18007a0b0`
- `0x1801a5d90`
- `0x1801a5da0`
- `0x1801a6050`
- `0x1801ad7d0`
- `0x1801ad820`
- `0x1801adc90`
- `0x1801aef70`
- `0x1801b4140`
- `0x1801b56f0`
- `0x18037a62b`
- `0x18037b520`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x18000d17c`
- `KERNEL32!lstrcmpiW` at `0x18000d17c`
- `USER32!IsGUIThread` at `0x18000cac7`
- `USER32!IsGUIThread` at `0x18000cac7`

## pseudocode

```c
__int64 __fastcall MSQAUICreateHostWindow(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4, int a5, __int64 a6)
{
  __int64 v8; // rax
  volatile signed __int32 *v9; // rbx
  volatile signed __int32 *v10; // rsi
  __int64 v12; // rax
  unsigned int v13; // ebx
  LPWSTR v14; // rcx
  __m128i si128; // xmm6
  __int64 *v16; // rax
  __int64 v17; // r12
  volatile signed __int32 *v18; // rsi
  volatile signed __int32 *v19; // r15
  _QWORD *v20; // rax
  int v21; // ecx
  _QWORD *v22; // rax
  _QWORD *v23; // rdx
  __int64 v24; // r8
  char *v25; // r8
  WCHAR *v26; // rcx
  volatile signed __int32 *v27; // rbx
  WCHAR *v28; // rdx
  LPWSTR v29; // rcx
  WCHAR *v30; // rcx
  volatile signed __int32 *v31; // rbx
  const WCHAR *v32; // rdx
  const WCHAR *v33; // rcx
  _QWORD *v34; // rax
  LPWSTR v35; // rcx
  WCHAR *v36; // rcx
  void (__fastcall *v37)(__int64, _QWORD, __int64, _BYTE *, _BYTE *, __int64, _QWORD *); // r12
  __int64 v38; // r15
  __int64 v39; // rax
  LPWSTR v40; // rcx
  __m128i v41; // xmm0
  WCHAR *v42; // rcx
  __int64 v43; // rdx
  volatile signed __int32 *v44; // rbx
  _BYTE v45[8]; // [rsp+40h] [rbp-698h] BYREF
  __int128 v46; // [rsp+48h] [rbp-690h] BYREF
  __int128 v47; // [rsp+58h] [rbp-680h] BYREF
  __m128i v48; // [rsp+68h] [rbp-670h]
  unsigned int v49; // [rsp+80h] [rbp-658h]
  __int64 v50; // [rsp+88h] [rbp-650h]
  __int64 v51; // [rsp+90h] [rbp-648h]
  __int64 v52; // [rsp+98h] [rbp-640h]
  __int128 v53; // [rsp+A0h] [rbp-638h]
  _QWORD v54[7]; // [rsp+B0h] [rbp-628h] BYREF
  _QWORD *v55; // [rsp+E8h] [rbp-5F0h]
  _BYTE v56[16]; // [rsp+F0h] [rbp-5E8h] BYREF
  _BYTE v57[32]; // [rsp+100h] [rbp-5D8h] BYREF
  _BYTE v58[16]; // [rsp+120h] [rbp-5B8h] BYREF
  _BYTE v59[64]; // [rsp+130h] [rbp-5A8h] BYREF
  _BYTE v60[160]; // [rsp+170h] [rbp-568h] BYREF
  _BYTE v61[496]; // [rsp+210h] [rbp-4C8h] BYREF
  char v62; // [rsp+400h] [rbp-2D8h]
  _BYTE v63[496]; // [rsp+410h] [rbp-2C8h] BYREF
  ULONG nSize[2]; // [rsp+600h] [rbp-D8h] BYREF
  volatile signed __int32 *v65; // [rsp+608h] [rbp-D0h]
  LPWSTR lpNameBuffer[2]; // [rsp+610h] [rbp-C8h] BYREF
  __m128i v67; // [rsp+620h] [rbp-B8h]
  LPCWSTR lpString1[2]; // [rsp+630h] [rbp-A8h] BYREF
  __m128i v69; // [rsp+640h] [rbp-98h]
  __int128 v70; // [rsp+650h] [rbp-88h] BYREF
  __int128 v71; // [rsp+660h] [rbp-78h] BYREF
  __int128 v72; // [rsp+670h] [rbp-68h]
  __int128 v73; // [rsp+680h] [rbp-58h]

  v50 = a3;
  v51 = a2;
  IsGUIThread(1);
  v46 = 0;
  sub_18000A090(&v46, a1[6]);
  v8 = v46;
  if ( (_QWORD)v46 )
  {
    v9 = (volatile signed __int32 *)*((_QWORD *)&v46 + 1);
    if ( *((_QWORD *)&v46 + 1) )
    {
      _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v46 + 1) + 8LL));
      v9 = (volatile signed __int32 *)*((_QWORD *)&v46 + 1);
      v8 = v46;
    }
    a1[9] = v8;
    v10 = (volatile signed __int32 *)a1[10];
    a1[10] = v9;
    if ( v10 )
    {
      if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
        if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
      }
      v9 = (volatile signed __int32 *)*((_QWORD *)&v46 + 1);
    }
    if ( v9 && _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
    return 2147500037LL;
  }
  *(_OWORD *)lpNameBuffer = 0;
  v67 = 0;
  v12 = sub_1801B56F0(a6);
  sub_180007C80(lpNameBuffer, a6, v12);
  v13 = sub_180076E00(a4, 0, lpNameBuffer);
  v49 = v13;
  if ( v67.m128i_i64[1] > 7uLL )
  {
    v14 = lpNameBuffer[0];
    if ( (unsigned __int64)(2 * v67.m128i_i64[1] + 2) >= 0x1000 )
    {
      v14 = (LPWSTR)*((_QWORD *)lpNameBuffer[0] - 1);
      if ( (unsigned __int64)((char *)lpNameBuffer[0] - (char *)v14 - 8) > 0x1F )
      {
        sub_1801B4140(0, 0, 0, 0, 0);
LABEL_102:
        sub_180003FA0(v57, 2147549183LL);
        sub_1801AEF70(v57, &_TI2_AVHRException_auth_mssql__);
        goto LABEL_103;
      }
    }
    _mm_lfence();
    j_Free_0(v14);
  }
  si128 = _mm_load_si128((const __m128i *)&xmmword_18041F460);
  v67 = si128;
  LOWORD(lpNameBuffer[0]) = 0;
  v53 = 0;
  v16 = (__int64 *)sub_18007A0B0(nSize, a1[6] + 32LL);
  v17 = *v16;
  v52 = v17;
  *(_QWORD *)&v53 = v17;
  v18 = (volatile signed __int32 *)v16[1];
  *((_QWORD *)&v53 + 1) = v18;
  *v16 = 0;
  v16[1] = 0;
  v19 = v65;
  if ( v65 )
  {
    if ( _InterlockedExchangeAdd(v65 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
      if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
    }
  }
  if ( !v17 )
    goto LABEL_102;
  v72 = 0;
  v73 = 0;
  v70 = 0u;
  v71 = 0u;
  v20 = (_QWORD *)sub_1801AD7D0(80);
  *v20 = v20;
  v20[1] = v20;
  *((_QWORD *)&v70 + 1) = v20;
  *((_QWORD *)&v71 + 1) = 0;
  v72 = 0;
  *(_QWORD *)&v73 = 7;
  *((_QWORD *)&v73 + 1) = 8;
  LODWORD(v70) = 1065353216;
  sub_18000A650((char *)&v71 + 8, 16, v20);
  v21 = *(_DWORD *)(a1[6] + 144LL);
  if ( (v21 & 4) == 0 )
    goto LABEL_78;
  if ( (v21 & 2) != 0 )
  {
    v47 = 0;
    v48 = 0;
    *(_QWORD *)&v47 = sub_180003E60(48);
    v48 = _mm_load_si128((const __m128i *)&xmmword_18041F4A0);
    strcpy((char *)v47, "force_prompt_for_guest_redemption");
    v22 = (_QWORD *)sub_180007F80(&v70, v56, &v47);
    sub_180009B00(*v22 + 48LL, "true");
    sub_180005740(&v47);
  }
  v23 = (_QWORD *)(a1[6] + 96LL);
  v24 = *(_QWORD *)(a1[6] + 112LL);
  if ( *(_QWORD *)(a1[6] + 120LL) <= 0xFu )
  {
    v25 = (char *)v23 + v24;
  }
  else
  {
    v25 = (char *)(*v23 + v24);
    v23 = (_QWORD *)*v23;
  }
  sub_180007B70(lpString1, v23, v25, v45);
  nSize[0] = 0;
  GetUserNameExW(NameUserPrincipal, 0, nSize);
  if ( !nSize[0] )
  {
    if ( v69.m128i_i64[1] <= 7uLL )
      goto LABEL_34;
    v26 = (WCHAR *)lpString1[0];
    if ( (unsigned __int64)(2 * v69.m128i_i64[1] + 2) < 0x1000
      || (v26 = (WCHAR *)*((_QWORD *)lpString1[0] - 1),
          (unsigned __int64)((char *)lpString1[0] - (char *)v26 - 8) <= 0x1F) )
    {
      _mm_lfence();
      j_Free_0(v26);
LABEL_34:
      v69 = si128;
      LOWORD(lpString1[0]) = 0;
      sub_180008CD0((char *)&v71 + 8);
      sub_180009160((char *)&v70 + 8);
      if ( v18 )
      {
        if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
          if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
        }
      }
      sub_180077240(v13);
      v27 = (volatile signed __int32 *)*((_QWORD *)&v46 + 1);
      if ( *((_QWORD *)&v46 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v46 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
          if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
        }
      }
      return 2147500037LL;
    }
LABEL_104:
    sub_1801B4140(0, 0, 0, 0, 0);
    __debugbreak();
  }
  sub_1800082F0(lpNameBuffer, nSize[0] - 1, 0);
  v28 = (WCHAR *)lpNameBuffer;
  if ( v67.m128i_i64[1] > 7uLL )
    v28 = lpNameBuffer[0];
  if ( GetUserNameExW(NameUserPrincipal, v28, nSize) )
  {
    v32 = (const WCHAR *)lpNameBuffer;
    if ( v67.m128i_i64[1] > 7uLL )
      v32 = lpNameBuffer[0];
    v33 = (const WCHAR *)lpString1;
    if ( v69.m128i_i64[1] > 7uLL )
      v33 = lpString1[0];
    if ( !lstrcmpiW(v33, v32) )
    {
      v47 = 0;
      v48 = _mm_load_si128((const __m128i *)&xmmword_18041F470);
      strcpy((char *)&v47, "Prompt");
      v34 = (_QWORD *)sub_180007F80(&v70, v56, &v47);
      sub_180009B00(*v34 + 48LL, "login");
      sub_180005740(&v47);
    }
    if ( v67.m128i_i64[1] > 7uLL )
    {
      v35 = lpNameBuffer[0];
      if ( (unsigned __int64)(2 * v67.m128i_i64[1] + 2) >= 0x1000 )
      {
        v35 = (LPWSTR)*((_QWORD *)lpNameBuffer[0] - 1);
        if ( (unsigned __int64)((char *)lpNameBuffer[0] - (char *)v35 - 8) > 0x1F )
          goto LABEL_103;
      }
      _mm_lfence();
      j_Free_0(v35);
    }
    v67 = si128;
    LOWORD(lpNameBuffer[0]) = 0;
    if ( v69.m128i_i64[1] > 7uLL )
    {
      v36 = (WCHAR *)lpString1[0];
      if ( (unsigned __int64)(2 * v69.m128i_i64[1] + 2) >= 0x1000 )
      {
        v36 = (WCHAR *)*((_QWORD *)lpString1[0] - 1);
        if ( (unsigned __int64)((char *)lpString1[0] - (char *)v36 - 8) > 0x1F )
          goto LABEL_104;
      }
      _mm_lfence();
      j_Free_0(v36);
    }
    v69 = si128;
    LOWORD(lpString1[0]) = 0;
LABEL_78:
    *(_QWORD *)nSize = qword_1805C4000;
    if ( (unsigned int)sub_1801A5D90(qword_1805C4000) )
      sub_1801A6050(5);
    if ( dword_1805C404C == 0x7FFFFFFF )
    {
      dword_1805C404C = 2147483646;
      sub_1801A6050(6);
    }
    v37 = *(void (__fastcall **)(__int64, _QWORD, __int64, _BYTE *, _BYTE *, __int64, _QWORD *))(*(_QWORD *)v17 + 56LL);
    v54[0] = off_18041F3C0;
    v54[1] = a1;
    v54[2] = v50;
    v54[3] = v51;
    v55 = v54;
    v38 = sub_180064230(v58, a1);
    v60[152] = 0;
    *(_OWORD *)lpString1 = 0;
    v69 = _mm_load_si128((const __m128i *)&xmmword_18041F110);
    LOBYTE(lpString1[0]) = 0;
    *(_OWORD *)lpNameBuffer = 0;
    v67 = v69;
    LOBYTE(lpNameBuffer[0]) = 0;
    v39 = sub_180062F80(
            (unsigned int)v63,
            a1[6],
            (int)a1 + 16,
            (unsigned int)lpNameBuffer,
            (__int64)lpString1,
            (__int64)&v70);
    sub_180008510(v61, v39);
    v62 = 1;
    v37(v52, v13, a1[6] + 96LL, v61, v60, v38, v54);
    if ( v62 )
      sub_1800098A0(v61);
    sub_1800098A0(v63);
    if ( v67.m128i_i64[1] > 0xFuLL )
    {
      v40 = lpNameBuffer[0];
      if ( (unsigned __int64)(v67.m128i_i64[1] + 1) >= 0x1000 )
      {
        v40 = (LPWSTR)*((_QWORD *)lpNameBuffer[0] - 1);
        if ( (unsigned __int64)((char *)lpNameBuffer[0] - (char *)v40 - 8) > 0x1F )
        {
          sub_1801B4140(0, 0, 0, 0, 0);
          goto LABEL_108;
        }
      }
      _mm_lfence();
      j_Free_0(v40);
    }
    v41 = _mm_load_si128((const __m128i *)&xmmword_18041F110);
    v67 = v41;
    LOBYTE(lpNameBuffer[0]) = 0;
    if ( v69.m128i_i64[1] <= 0xFuLL )
    {
LABEL_90:
      v69 = v41;
      LOBYTE(lpString1[0]) = 0;
      sub_180008ED0(v60);
      sub_180005740(v59);
      if ( v55 )
      {
        LOBYTE(v43) = v55 != v54;
        (*(void (__fastcall **)(_QWORD *, __int64))(*v55 + 32LL))(v55, v43);
      }
      sub_1801A5DA0(qword_1805C4000);
      sub_180008CD0((char *)&v71 + 8);
      sub_180009160((char *)&v70 + 8);
      if ( v18 )
      {
        if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
          if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
        }
      }
      sub_180077240(v13);
      v44 = (volatile signed __int32 *)*((_QWORD *)&v46 + 1);
      if ( *((_QWORD *)&v46 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v46 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v44)(v44);
          if ( _InterlockedExchangeAdd(v44 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v44 + 8LL))(v44);
        }
      }
      return 0;
    }
    v42 = (WCHAR *)lpString1[0];
    if ( (unsigned __int64)(v69.m128i_i64[1] + 1) < 0x1000
      || (v42 = (WCHAR *)*((_QWORD *)lpString1[0] - 1),
          (unsigned __int64)((char *)lpString1[0] - (char *)v42 - 8) <= 0x1F) )
    {
      _mm_lfence();
      j_Free_0(v42);
      v41 = _mm_load_si128((const __m128i *)&xmmword_18041F110);
      goto LABEL_90;
    }
LABEL_108:
    sub_1801B4140(0, 0, 0, 0, 0);
    JUMPOUT(0x18000D6D4LL);
  }
  if ( v67.m128i_i64[1] > 7uLL )
  {
    v29 = lpNameBuffer[0];
    if ( (unsigned __int64)(2 * v67.m128i_i64[1] + 2) < 0x1000
      || (v29 = (LPWSTR)*((_QWORD *)lpNameBuffer[0] - 1),
          (unsigned __int64)((char *)lpNameBuffer[0] - (char *)v29 - 8) <= 0x1F) )
    {
      _mm_lfence();
      j_Free_0(v29);
      goto LABEL_50;
    }
LABEL_103:
    sub_1801B4140(0, 0, 0, 0, 0);
    goto LABEL_104;
  }
LABEL_50:
  v67 = si128;
  LOWORD(lpNameBuffer[0]) = 0;
  if ( v69.m128i_i64[1] > 7uLL )
  {
    v30 = (WCHAR *)lpString1[0];
    if ( (unsigned __int64)(2 * v69.m128i_i64[1] + 2) >= 0x1000 )
    {
      v30 = (WCHAR *)*((_QWORD *)lpString1[0] - 1);
      if ( (unsigned __int64)((char *)lpString1[0] - (char *)v30 - 8) > 0x1F )
        goto LABEL_104;
    }
    _mm_lfence();
    j_Free_0(v30);
  }
  v69 = si128;
  LOWORD(lpString1[0]) = 0;
  sub_180008CD0((char *)&v71 + 8);
  sub_180009160((char *)&v70 + 8);
  if ( v18 )
  {
    if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
      if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
    }
  }
  sub_180077240(v13);
  v31 = (volatile signed __int32 *)*((_QWORD *)&v46 + 1);
  if ( *((_QWORD *)&v46 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v46 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
      if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
    }
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x18000ca70  mov     [rsp+arg_8], rbx
0x18000ca75  mov     [rsp+arg_10], rsi
0x18000ca7a  push    rdi
0x18000ca7b  push    r12
0x18000ca7d  push    r13
0x18000ca7f  push    r14
0x18000ca81  push    r15
0x18000ca83  sub     rsp, 6B0h
0x18000ca8a  movaps  [rsp+6D8h+var_38], xmm6
0x18000ca92  mov     rax, cs:__security_cookie
0x18000ca99  xor     rax, rsp
0x18000ca9c  mov     [rsp+6D8h+var_48], rax
0x18000caa4  mov     rdi, r9
0x18000caa7  mov     [rsp+6D8h+var_650], r8
0x18000caaf  mov     [rsp+6D8h+var_648], rdx
0x18000cab7  mov     r13, rcx
0x18000caba  mov     rbx, [rsp+6D8h+arg_28]
0x18000cac2  mov     ecx, 1; bConvert
0x18000cac7  call    cs:IsGUIThread
0x18000cacd  xorps   xmm0, xmm0
0x18000cad0  movups  [rsp+6D8h+var_690], xmm0
0x18000cad5  mov     rdx, [r13+30h]
0x18000cad9  lea     rcx, [rsp+6D8h+var_690]
0x18000cade  call    sub_18000A090
0x18000cae3  nop
0x18000cae4  mov     rax, qword ptr [rsp+6D8h+var_690]
0x18000cae9  test    rax, rax
0x18000caec  jz      loc_18000CBA0
0x18000caf2  mov     rbx, qword ptr [rsp+6D8h+var_690+8]
0x18000caf7  test    rbx, rbx
0x18000cafa  jz      short loc_18000CB0A
0x18000cafc  lock inc dword ptr [rbx+8]
0x18000cb00  mov     rbx, qword ptr [rsp+6D8h+var_690+8]
0x18000cb05  mov     rax, qword ptr [rsp+6D8h+var_690]
0x18000cb0a  mov     [r13+48h], rax
0x18000cb0e  mov     rsi, [r13+50h]
0x18000cb12  mov     [r13+50h], rbx
0x18000cb16  mov     edi, 0FFFFFFFFh
0x18000cb1b  test    rsi, rsi
0x18000cb1e  jz      short loc_18000CB5C
0x18000cb20  mov     eax, edi
0x18000cb22  lock xadd [rsi+8], eax
0x18000cb27  cmp     eax, 1
0x18000cb2a  jnz     short loc_18000CB57
0x18000cb2c  mov     rax, [rsi]
0x18000cb2f  mov     rcx, rsi
0x18000cb32  mov     rax, [rax]
0x18000cb35  call    cs:__guard_dispatch_icall_fptr
0x18000cb3b  mov     eax, edi
0x18000cb3d  lock xadd [rsi+0Ch], eax
0x18000cb42  cmp     eax, 1
0x18000cb45  jnz     short loc_18000CB57
0x18000cb47  mov     rax, [rsi]
0x18000cb4a  mov     rcx, rsi
0x18000cb4d  mov     rax, [rax+8]
0x18000cb51  call    cs:__guard_dispatch_icall_fptr
0x18000cb57  mov     rbx, qword ptr [rsp+6D8h+var_690+8]
0x18000cb5c  test    rbx, rbx
0x18000cb5f  jz      short loc_18000CB96
0x18000cb61  mov     eax, edi
0x18000cb63  lock xadd [rbx+8], eax
0x18000cb68  cmp     eax, 1
0x18000cb6b  jnz     short loc_18000CB96
0x18000cb6d  mov     rax, [rbx]
0x18000cb70  mov     rcx, rbx
0x18000cb73  mov     rax, [rax]
0x18000cb76  call    cs:__guard_dispatch_icall_fptr
0x18000cb7c  lock xadd [rbx+0Ch], edi
0x18000cb81  cmp     edi, 1
0x18000cb84  jnz     short loc_18000CB96
0x18000cb86  mov     rax, [rbx]
0x18000cb89  mov     rcx, rbx
0x18000cb8c  mov     rax, [rax+8]
0x18000cb90  call    cs:__guard_dispatch_icall_fptr
0x18000cb96  mov     eax, 80004005h
0x18000cb9b  jmp     loc_18000D5F1
0x18000cba0  xorps   xmm0, xmm0
0x18000cba3  movups  xmmword ptr [rsp+6D8h+lpNameBuffer], xmm0
0x18000cbab  xorps   xmm1, xmm1
0x18000cbae  movdqu  [rsp+6D8h+var_B8], xmm1
0x18000cbb7  mov     rcx, rbx
0x18000cbba  call    sub_1801B56F0
0x18000cbbf  mov     r8, rax
0x18000cbc2  mov     rdx, rbx
0x18000cbc5  lea     rcx, [rsp+6D8h+lpNameBuffer]
0x18000cbcd  call    sub_180007C80
0x18000cbd2  lea     r8, [rsp+6D8h+lpNameBuffer]
0x18000cbda  xor     edx, edx
0x18000cbdc  mov     rcx, rdi
0x18000cbdf  call    sub_180076E00
0x18000cbe4  mov     ebx, eax
0x18000cbe6  mov     [rsp+6D8h+var_658], eax
0x18000cbed  mov     rdx, qword ptr [rsp+6D8h+var_B8+8]
0x18000cbf5  cmp     rdx, 7
0x18000cbf9  jbe     short loc_18000CC38
0x18000cbfb  lea     rdx, ds:2[rdx*2]
0x18000cc03  mov     rcx, [rsp+6D8h+lpNameBuffer]
0x18000cc0b  mov     rax, rcx
0x18000cc0e  cmp     rdx, 1000h
0x18000cc15  jb      short loc_18000CC30
0x18000cc17  add     rdx, 27h ; '''
0x18000cc1b  mov     rcx, [rcx-8]; lpMem
0x18000cc1f  sub     rax, rcx
0x18000cc22  sub     rax, 8
0x18000cc26  cmp     rax, 1Fh
0x18000cc2a  ja      loc_18000D623
0x18000cc30  lfence
0x18000cc33  call    j_Free_0
0x18000cc38  movdqa  xmm6, cs:xmmword_18041F460
0x18000cc40  movdqu  [rsp+6D8h+var_B8], xmm6
0x18000cc49  xor     r14d, r14d
0x18000cc4c  mov     word ptr [rsp+6D8h+lpNameBuffer], r14w
0x18000cc55  xorps   xmm0, xmm0
0x18000cc58  movups  [rsp+6D8h+var_638], xmm0
0x18000cc60  mov     rdx, [r13+30h]
0x18000cc64  add     rdx, 20h ; ' '
0x18000cc68  lea     rcx, [rsp+6D8h+nSize]
0x18000cc70  call    sub_18007A0B0
0x18000cc75  mov     r12, [rax]
0x18000cc78  mov     [rsp+6D8h+var_640], r12
0x18000cc80  mov     qword ptr [rsp+6D8h+var_638], r12
0x18000cc88  mov     rsi, [rax+8]
0x18000cc8c  mov     qword ptr [rsp+6D8h+var_638+8], rsi
0x18000cc94  mov     [rax], r14
0x18000cc97  mov     [rax+8], r14
0x18000cc9b  mov     r15, [rsp+6D8h+var_D0]
0x18000cca3  mov     edi, 0FFFFFFFFh
0x18000cca8  test    r15, r15
0x18000ccab  jz      short loc_18000CCE6
0x18000ccad  mov     eax, edi
0x18000ccaf  lock xadd [r15+8], eax
0x18000ccb5  cmp     eax, 1
0x18000ccb8  jnz     short loc_18000CCE6
0x18000ccba  mov     rax, [r15]
0x18000ccbd  mov     rcx, r15
0x18000ccc0  mov     rax, [rax]
0x18000ccc3  call    cs:__guard_dispatch_icall_fptr
0x18000ccc9  mov     eax, edi
0x18000cccb  lock xadd [r15+0Ch], eax
0x18000ccd1  cmp     eax, 1
0x18000ccd4  jnz     short loc_18000CCE6
0x18000ccd6  mov     rax, [r15]
0x18000ccd9  mov     rcx, r15
0x18000ccdc  mov     rax, [rax+8]
0x18000cce0  call    cs:__guard_dispatch_icall_fptr
0x18000cce6  test    r12, r12
0x18000cce9  jz      loc_18000D63B
0x18000ccef  xorps   xmm0, xmm0
0x18000ccf2  movups  [rsp+6D8h+var_88], xmm0
0x18000ccfa  movups  [rsp+6D8h+var_78], xmm0
0x18000cd02  movups  [rsp+6D8h+var_68], xmm0
0x18000cd0a  movups  [rsp+6D8h+var_58], xmm0
0x18000cd12  mov     dword ptr [rsp+6D8h+var_88], 0
0x18000cd1d  mov     qword ptr [rsp+6D8h+var_88+8], r14
0x18000cd25  mov     qword ptr [rsp+6D8h+var_78], r14
0x18000cd2d  mov     ecx, 50h ; 'P'
0x18000cd32  call    sub_1801AD7D0
0x18000cd37  mov     [rax], rax
0x18000cd3a  mov     [rax+8], rax
0x18000cd3e  mov     qword ptr [rsp+6D8h+var_88+8], rax
0x18000cd46  mov     qword ptr [rsp+6D8h+var_78+8], r14
0x18000cd4e  xorps   xmm0, xmm0
0x18000cd51  movdqa  [rsp+6D8h+var_68], xmm0
0x18000cd5a  mov     qword ptr [rsp+6D8h+var_58], 7
0x18000cd66  mov     qword ptr [rsp+6D8h+var_58+8], 8
0x18000cd72  mov     dword ptr [rsp+6D8h+var_88], 3F800000h
0x18000cd7d  mov     r8, rax
0x18000cd80  mov     edx, 10h
0x18000cd85  lea     rcx, [rsp+6D8h+var_78+8]
0x18000cd8d  call    sub_18000A650
0x18000cd92  nop
0x18000cd93  mov     rax, [r13+30h]
0x18000cd97  mov     ecx, [rax+90h]
0x18000cd9d  test    cl, 4
0x18000cda0  jz      loc_18000D2AA
0x18000cda6  test    cl, 2
0x18000cda9  jz      loc_18000CE3B
0x18000cdaf  xorps   xmm0, xmm0
0x18000cdb2  movups  [rsp+6D8h+var_680], xmm0
0x18000cdb7  xorps   xmm1, xmm1
0x18000cdba  movdqu  [rsp+6D8h+var_670], xmm1
0x18000cdc0  mov     ecx, 30h ; '0'
0x18000cdc5  call    sub_180003E60
0x18000cdca  mov     rcx, rax
0x18000cdcd  mov     qword ptr [rsp+6D8h+var_680], rax
0x18000cdd2  movdqa  xmm0, cs:xmmword_18041F4A0
0x18000cdda  movdqu  [rsp+6D8h+var_670], xmm0
0x18000cde0  movups  xmm0, cs:xmmword_18041F308
0x18000cde7  movups  xmmword ptr [rax], xmm0
0x18000cdea  movups  xmm1, cs:xmmword_18041F318
0x18000cdf1  movups  xmmword ptr [rax+10h], xmm1
0x18000cdf5  movzx   eax, cs:byte_18041F328
0x18000cdfc  mov     [rcx+20h], al
0x18000cdff  mov     byte ptr [rcx+21h], 0
0x18000ce03  lea     r8, [rsp+6D8h+var_680]
0x18000ce08  lea     rdx, [rsp+6D8h+var_5E8]
0x18000ce10  lea     rcx, [rsp+6D8h+var_88]
0x18000ce18  call    sub_180007F80
0x18000ce1d  mov     rcx, [rax]
0x18000ce20  add     rcx, 30h ; '0'
0x18000ce24  lea     rdx, aTrue; "true"
0x18000ce2b  call    sub_180009B00
0x18000ce30  nop
0x18000ce31  lea     rcx, [rsp+6D8h+var_680]
0x18000ce36  call    sub_180005740
0x18000ce3b  mov     rdx, [r13+30h]
0x18000ce3f  add     rdx, 60h ; '`'
0x18000ce43  mov     r8, [rdx+10h]
0x18000ce47  cmp     qword ptr [rdx+18h], 0Fh
0x18000ce4c  jbe     short loc_18000CE56
0x18000ce4e  add     r8, [rdx]
0x18000ce51  mov     rdx, [rdx]
0x18000ce54  jmp     short loc_18000CE59
0x18000ce56  add     r8, rdx
0x18000ce59  lea     r9, [rsp+6D8h+var_698]
0x18000ce5e  lea     rcx, [rsp+6D8h+lpString1]
0x18000ce66  call    sub_180007B70
0x18000ce6b  nop
0x18000ce6c  mov     [rsp+6D8h+nSize], r14d
0x18000ce74  lea     r8, [rsp+6D8h+nSize]; nSize
0x18000ce7c  xor     edx, edx; lpNameBuffer
0x18000ce7e  mov     ecx, 8; NameFormat
0x18000ce83  call    GetUserNameExW
0x18000ce88  mov     eax, [rsp+6D8h+nSize]
0x18000ce8f  test    eax, eax
0x18000ce91  jnz     loc_18000CF9D
0x18000ce97  mov     rdx, [rsp+6D8h+var_90]
0x18000ce9f  cmp     rdx, 7
0x18000cea3  jbe     short loc_18000CEE2
0x18000cea5  lea     rdx, ds:2[rdx*2]
0x18000cead  mov     rcx, [rsp+6D8h+lpString1]
0x18000ceb5  mov     rax, rcx
0x18000ceb8  cmp     rdx, 1000h
0x18000cebf  jb      short loc_18000CEDA
0x18000cec1  add     rdx, 27h ; '''
0x18000cec5  mov     rcx, [rcx-8]; lpMem
0x18000cec9  sub     rax, rcx
0x18000cecc  sub     rax, 8
0x18000ced0  cmp     rax, 1Fh
0x18000ced4  ja      loc_18000D677
0x18000ceda  lfence
0x18000cedd  call    j_Free_0
0x18000cee2  movdqu  xmmword ptr [rsp+640h], xmm6
0x18000ceeb  mov     word ptr [rsp+6D8h+lpString1], r14w
0x18000cef4  lea     rcx, [rsp+6D8h+var_78+8]
0x18000cefc  call    sub_180008CD0
0x18000cf01  lea     rcx, [rsp+6D8h+var_88+8]
0x18000cf09  call    sub_180009160
0x18000cf0e  nop
0x18000cf0f  test    rsi, rsi
0x18000cf12  jz      short loc_18000CF4C
0x18000cf14  mov     eax, edi
0x18000cf16  lock xadd [rsi+8], eax
0x18000cf1b  cmp     eax, 1
0x18000cf1e  jnz     short loc_18000CF4C
0x18000cf20  mov     rax, [rsi]
0x18000cf23  mov     rcx, rsi
0x18000cf26  mov     rax, [rax]
0x18000cf29  call    cs:__guard_dispatch_icall_fptr
0x18000cf2f  mov     eax, edi
0x18000cf31  lock xadd [rsi+0Ch], eax
0x18000cf36  cmp     eax, 1
0x18000cf39  jnz     short loc_18000CF4C
0x18000cf3b  mov     rax, [rsi]
0x18000cf3e  mov     rcx, rsi
0x18000cf41  mov     rax, [rax+8]
0x18000cf45  call    cs:__guard_dispatch_icall_fptr
0x18000cf4b  nop
0x18000cf4c  mov     ecx, ebx
0x18000cf4e  call    sub_180077240
0x18000cf53  nop
0x18000cf54  mov     rbx, qword ptr [rsp+6D8h+var_690+8]
0x18000cf59  test    rbx, rbx
0x18000cf5c  jz      short loc_18000CF93
0x18000cf5e  mov     eax, edi
0x18000cf60  lock xadd [rbx+8], eax
0x18000cf65  cmp     eax, 1
0x18000cf68  jnz     short loc_18000CF93
0x18000cf6a  mov     rax, [rbx]
0x18000cf6d  mov     rcx, rbx
0x18000cf70  mov     rax, [rax]
0x18000cf73  call    cs:__guard_dispatch_icall_fptr
0x18000cf79  lock xadd [rbx+0Ch], edi
0x18000cf7e  cmp     edi, 1
0x18000cf81  jnz     short loc_18000CF93
0x18000cf83  mov     rax, [rbx]
0x18000cf86  mov     rcx, rbx
0x18000cf89  mov     rax, [rax+8]
0x18000cf8d  call    cs:__guard_dispatch_icall_fptr
0x18000cf93  mov     eax, 80004005h
0x18000cf98  jmp     loc_18000D5F1
0x18000cf9d  xor     r8d, r8d
0x18000cfa0  lea     edx, [rax-1]
0x18000cfa3  lea     rcx, [rsp+6D8h+lpNameBuffer]
0x18000cfab  call    sub_1800082F0
0x18000cfb0  nop
0x18000cfb1  lea     rdx, [rsp+6D8h+lpNameBuffer]
0x18000cfb9  cmp     qword ptr [rsp+6D8h+var_B8+8], 7
0x18000cfc2  cmova   rdx, [rsp+6D8h+lpNameBuffer]; lpNameBuffer
0x18000cfcb  lea     r8, [rsp+6D8h+nSize]; nSize
  ... truncated ...
```
