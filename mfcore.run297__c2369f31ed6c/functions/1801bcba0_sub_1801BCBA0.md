# sub_1801BCBA0

- ea: `0x1801bcba0`
- end: `0x1801bd34e`
- name: `sub_1801BCBA0`
- size: `1966`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x180063f00`
- `0x1800ec0e0`
- `0x1801bcba0`
- `0x180258480`
- `0x180344d40`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x1801bcf4e`
- `MFPlat!MFCreateMediaType` at `0x1801bcf4e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801bcc81`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801bcd4d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801bce05`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801bcec0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801bcf70`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801bd02a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801bd0e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801bd19c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801bd256`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801bcc81`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801bcd4d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801bce05`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801bcec0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801bcf70`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801bd02a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801bd0e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801bd19c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801bd256`

## string_xrefs

- `0x1801bcbd0`: `CMediaSession::UpdateInputTypeUINT64`
- `0x1801bccdf`: `CMediaSession::UpdateInputTypeUINT64`
- `0x1801bcdab`: `CMediaSession::UpdateInputTypeUINT64`
- `0x1801bce63`: `CMediaSession::UpdateInputTypeUINT64`
- `0x1801bcf1e`: `CMediaSession::UpdateInputTypeUINT64`
- `0x1801bcfce`: `CMediaSession::UpdateInputTypeUINT64`
- `0x1801bd088`: `CMediaSession::UpdateInputTypeUINT64`
- `0x1801bd140`: `CMediaSession::UpdateInputTypeUINT64`
- `0x1801bd1fa`: `CMediaSession::UpdateInputTypeUINT64`
- `0x1801bd2b4`: `CMediaSession::UpdateInputTypeUINT64`

## pseudocode

```c
__int64 __fastcall sub_1801BCBA0(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 *v10; // rcx
  __int64 v11; // rdi
  int v12; // ebx
  __int128 *v13; // rax
  __int128 v14; // xmm0
  HRESULT v15; // ebx
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // r9
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 *v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 *v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 *v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 *v37; // rcx
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 *v42; // rcx
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 *v47; // rcx
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 *v52; // rcx
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rdx
  __int64 v56; // r8
  __int64 *v57; // rcx
  __int64 v58; // rax
  __int64 v59; // rax
  _BYTE v61[8]; // [rsp+30h] [rbp-39h] BYREF
  IMFMediaType *ppMFType; // [rsp+38h] [rbp-31h] BYREF
  __int64 v63; // [rsp+40h] [rbp-29h] BYREF
  __int64 v64; // [rsp+48h] [rbp-21h] BYREF
  __int64 (__fastcall ***v65)(_QWORD, const IID *, __int64 *); // [rsp+50h] [rbp-19h] BYREF
  __int64 v66; // [rsp+58h] [rbp-11h] BYREF
  _BYTE v67[16]; // [rsp+60h] [rbp-9h] BYREF

  sub_18002FEE0(v61, "CMediaSession::UpdateInputTypeUINT64", 9531);
  v10 = (__int64 *)qword_1803CEF18;
  if ( *(_BYTE *)(qword_1803CEF18 + 8) && *(_QWORD *)(a1 + 1088) )
  {
    v11 = sub_1800402C0(qword_1803CEF18);
    v12 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 1088) + 296LL))(*(_QWORD *)(a1 + 1088));
    v13 = (__int128 *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(a1 + 1088) + 280LL))(
                        *(_QWORD *)(a1 + 1088),
                        v67);
    v10 = (__int64 *)qword_1803CEF18;
    v14 = *v13;
    *(_DWORD *)(v11 + 2016) = v12;
    *(_OWORD *)(v11 + 2000) = v14;
  }
  v66 = 0;
  v65 = 0;
  v63 = 0;
  v64 = 0;
  ppMFType = 0;
  if ( *(_QWORD *)(a1 + 480) )
  {
    v15 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(**(_QWORD **)(a1 - 528 + 1008) + 320LL))(
            *(_QWORD *)(a1 - 528 + 1008),
            a2,
            &v66);
    if ( v15 >= 0 )
    {
      v15 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, const IID *, __int64 *)))(*(_QWORD *)v66 + 272LL))(
              v66,
              &v65);
      if ( v15 >= 0 )
      {
        v15 = (**v65)(v65, &stru_180367B40, &v63);
        if ( v15 >= 0 )
        {
          v15 = MFCreateMediaType(&ppMFType);
          if ( v15 >= 0 )
          {
            v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v63 + 136LL))(v63, 0, &v64);
            if ( v15 >= 0 )
            {
              v15 = (*(__int64 (__fastcall **)(__int64, IMFMediaType *))(*(_QWORD *)v64 + 256LL))(v64, ppMFType);
              if ( v15 >= 0 )
              {
                v15 = ((__int64 (__fastcall *)(IMFMediaType *, __int64, __int64))ppMFType->lpVtbl->SetUINT64)(
                        ppMFType,
                        a3,
                        a4);
                if ( v15 >= 0 )
                {
                  v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, IMFMediaType *, _QWORD))(*(_QWORD *)v63 + 120LL))(
                          v63,
                          0,
                          ppMFType,
                          0);
                  if ( v15 >= 0 )
                    goto LABEL_105;
                  v57 = (__int64 *)qword_1803CEF18;
                  if ( !qword_1803CEF18 )
                  {
                    v58 = MFGetCallStackTracingWeakReference(0, v55, v56);
                    qword_1803CEF18 = v58;
                    if ( v58 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v58 + 8LL))(v58, 2032) )
                    {
                      v57 = (__int64 *)qword_1803CEF18;
                    }
                    else
                    {
                      v57 = &qword_1803CE250;
                      qword_1803CEF18 = (__int64)&qword_1803CE250;
                    }
                  }
                  if ( *((_BYTE *)v57 + 8) )
                  {
                    v59 = sub_1800402C0(v57);
                    if ( *(_DWORD *)(v59 + 1996) != v15 )
                      sub_1800EC0E0(v59, "CMediaSession::UpdateInputTypeUINT64", 9553, (unsigned int)v15);
                  }
                  if ( !byte_1803CECE8 )
                    goto LABEL_105;
                  v19 = 751;
                }
                else
                {
                  v52 = (__int64 *)qword_1803CEF18;
                  if ( !qword_1803CEF18 )
                  {
                    v53 = MFGetCallStackTracingWeakReference(0, v50, v51);
                    qword_1803CEF18 = v53;
                    if ( v53 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
                    {
                      v52 = (__int64 *)qword_1803CEF18;
                    }
                    else
                    {
                      v52 = &qword_1803CE250;
                      qword_1803CEF18 = (__int64)&qword_1803CE250;
                    }
                  }
                  if ( *((_BYTE *)v52 + 8) )
                  {
                    v54 = sub_1800402C0(v52);
                    if ( *(_DWORD *)(v54 + 1996) != v15 )
                      sub_1800EC0E0(v54, "CMediaSession::UpdateInputTypeUINT64", 9552, (unsigned int)v15);
                  }
                  if ( !byte_1803CECE8 )
                    goto LABEL_105;
                  v19 = 750;
                }
              }
              else
              {
                v47 = (__int64 *)qword_1803CEF18;
                if ( !qword_1803CEF18 )
                {
                  v48 = MFGetCallStackTracingWeakReference(0, v45, v46);
                  qword_1803CEF18 = v48;
                  if ( v48 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
                  {
                    v47 = (__int64 *)qword_1803CEF18;
                  }
                  else
                  {
                    v47 = &qword_1803CE250;
                    qword_1803CEF18 = (__int64)&qword_1803CE250;
                  }
                }
                if ( *((_BYTE *)v47 + 8) )
                {
                  v49 = sub_1800402C0(v47);
                  if ( *(_DWORD *)(v49 + 1996) != v15 )
                    sub_1800EC0E0(v49, "CMediaSession::UpdateInputTypeUINT64", 9551, (unsigned int)v15);
                }
                if ( !byte_1803CECE8 )
                  goto LABEL_105;
                v19 = 749;
              }
            }
            else
            {
              v42 = (__int64 *)qword_1803CEF18;
              if ( !qword_1803CEF18 )
              {
                v43 = MFGetCallStackTracingWeakReference(0, v40, v41);
                qword_1803CEF18 = v43;
                if ( v43 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
                {
                  v42 = (__int64 *)qword_1803CEF18;
                }
                else
                {
                  v42 = &qword_1803CE250;
                  qword_1803CEF18 = (__int64)&qword_1803CE250;
                }
              }
              if ( *((_BYTE *)v42 + 8) )
              {
                v44 = sub_1800402C0(v42);
                if ( *(_DWORD *)(v44 + 1996) != v15 )
                  sub_1800EC0E0(v44, "CMediaSession::UpdateInputTypeUINT64", 9550, (unsigned int)v15);
              }
              if ( !byte_1803CECE8 )
                goto LABEL_105;
              v19 = 748;
            }
          }
          else
          {
            v37 = (__int64 *)qword_1803CEF18;
            if ( !qword_1803CEF18 )
            {
              v38 = MFGetCallStackTracingWeakReference(0, v35, v36);
              qword_1803CEF18 = v38;
              if ( v38 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
              {
                v37 = (__int64 *)qword_1803CEF18;
              }
              else
              {
                v37 = &qword_1803CE250;
                qword_1803CEF18 = (__int64)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v37 + 8) )
            {
              v39 = sub_1800402C0(v37);
              if ( *(_DWORD *)(v39 + 1996) != v15 )
                sub_1800EC0E0(v39, "CMediaSession::UpdateInputTypeUINT64", 9549, (unsigned int)v15);
            }
            if ( !byte_1803CECE8 )
              goto LABEL_105;
            v19 = 747;
          }
        }
        else
        {
          v32 = (__int64 *)qword_1803CEF18;
          if ( !qword_1803CEF18 )
          {
            v33 = MFGetCallStackTracingWeakReference(0, v30, v31);
            qword_1803CEF18 = v33;
            if ( v33 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
            {
              v32 = (__int64 *)qword_1803CEF18;
            }
            else
            {
              v32 = &qword_1803CE250;
              qword_1803CEF18 = (__int64)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v32 + 8) )
          {
            v34 = sub_1800402C0(v32);
            if ( *(_DWORD *)(v34 + 1996) != v15 )
              sub_1800EC0E0(v34, "CMediaSession::UpdateInputTypeUINT64", 9547, (unsigned int)v15);
          }
          if ( !byte_1803CECE8 )
            goto LABEL_105;
          v19 = 746;
        }
      }
      else
      {
        v27 = (__int64 *)qword_1803CEF18;
        if ( !qword_1803CEF18 )
        {
          v28 = MFGetCallStackTracingWeakReference(0, v25, v26);
          qword_1803CEF18 = v28;
          if ( v28 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
          {
            v27 = (__int64 *)qword_1803CEF18;
          }
          else
          {
            v27 = &qword_1803CE250;
            qword_1803CEF18 = (__int64)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v27 + 8) )
        {
          v29 = sub_1800402C0(v27);
          if ( *(_DWORD *)(v29 + 1996) != v15 )
            sub_1800EC0E0(v29, "CMediaSession::UpdateInputTypeUINT64", 9546, (unsigned int)v15);
        }
        if ( !byte_1803CECE8 )
          goto LABEL_105;
        v19 = 745;
      }
    }
    else
    {
      v22 = (__int64 *)qword_1803CEF18;
      if ( !qword_1803CEF18 )
      {
        v23 = MFGetCallStackTracingWeakReference(0, v20, v21);
        qword_1803CEF18 = v23;
        if ( v23 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
        {
          v22 = (__int64 *)qword_1803CEF18;
        }
        else
        {
          v22 = &qword_1803CE250;
          qword_1803CEF18 = (__int64)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v22 + 8) )
      {
        v24 = sub_1800402C0(v22);
        if ( *(_DWORD *)(v24 + 1996) != v15 )
          sub_1800EC0E0(v24, "CMediaSession::UpdateInputTypeUINT64", 9545, (unsigned int)v15);
      }
      if ( !byte_1803CECE8 )
        goto LABEL_105;
      v19 = 744;
    }
    v18 = a1 - 528;
    goto LABEL_104;
  }
  v15 = -1072875854;
  if ( !v10 )
  {
    v16 = MFGetCallStackTracingWeakReference(0, v8, v9);
    qword_1803CEF18 = v16;
    if ( v16 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
    {
      v10 = (__int64 *)qword_1803CEF18;
    }
    else
    {
      v10 = &qword_1803CE250;
      qword_1803CEF18 = (__int64)&qword_1803CE250;
    }
  }
  if ( *((_BYTE *)v10 + 8) )
  {
    v17 = sub_1800402C0(v10);
    if ( *(_DWORD *)(v17 + 1996) != -1072875854 )
      sub_1800EC0E0(v17, "CMediaSession::UpdateInputTypeUINT64", 9542, 3222091442LL);
  }
  if ( byte_1803CECE8 )
  {
    v18 = a1 - 528;
    v19 = 743;
LABEL_104:
    sub_180050D6C(*((_QWORD *)RequestContext + 2), v19, &stru_180365588, v18, v15);
  }
LABEL_105:
  sub_180063F00(&ppMFType);
  sub_180063F00(&v64);
  sub_180063F00(&v63);
  sub_180063F00(&v65);
  sub_180063F00(&v66);
  sub_18003ECB0(v61);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1801bcba0  push    rbp
0x1801bcba2  push    rbx
0x1801bcba3  push    rsi
0x1801bcba4  push    rdi
0x1801bcba5  push    r12
0x1801bcba7  push    r13
0x1801bcba9  push    r14
0x1801bcbab  push    r15
0x1801bcbad  lea     rbp, [rsp-1Fh]
0x1801bcbb2  sub     rsp, 88h
0x1801bcbb9  mov     rax, cs:__security_cookie
0x1801bcbc0  xor     rax, rsp
0x1801bcbc3  mov     [rbp+57h+var_50], rax
0x1801bcbc7  mov     r15, r8
0x1801bcbca  mov     r14, rdx
0x1801bcbcd  mov     rsi, rcx
0x1801bcbd0  lea     rdx, aCmediasessionU_1; "CMediaSession::UpdateInputTypeUINT64"
0x1801bcbd7  mov     r8d, 253Bh
0x1801bcbdd  lea     rcx, [rbp+57h+var_90]
0x1801bcbe1  mov     r12, r9
0x1801bcbe4  call    sub_18002FEE0
0x1801bcbe9  mov     rcx, cs:qword_1803CEF18
0x1801bcbf0  xor     r13d, r13d
0x1801bcbf3  cmp     [rcx+8], r13b
0x1801bcbf7  jz      short loc_1801BCC56
0x1801bcbf9  cmp     [rsi+440h], r13
0x1801bcc00  jz      short loc_1801BCC56
0x1801bcc02  call    sub_1800402C0
0x1801bcc07  mov     rcx, [rsi+440h]
0x1801bcc0e  mov     rdi, rax
0x1801bcc11  mov     rdx, [rcx]
0x1801bcc14  mov     rax, [rdx+128h]
0x1801bcc1b  call    cs:__guard_dispatch_icall_fptr
0x1801bcc21  mov     rcx, [rsi+440h]
0x1801bcc28  mov     ebx, eax
0x1801bcc2a  mov     rdx, [rcx]
0x1801bcc2d  mov     rax, [rdx+118h]
0x1801bcc34  lea     rdx, [rbp+57h+var_60]
0x1801bcc38  call    cs:__guard_dispatch_icall_fptr
0x1801bcc3e  mov     rcx, cs:qword_1803CEF18
0x1801bcc45  movups  xmm0, xmmword ptr [rax]
0x1801bcc48  mov     [rdi+7E0h], ebx
0x1801bcc4e  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1801bcc56  mov     [rbp+57h+var_68], r13
0x1801bcc5a  mov     [rbp+57h+var_70], r13
0x1801bcc5e  mov     [rbp+57h+var_80], r13
0x1801bcc62  mov     [rbp+57h+var_78], r13
0x1801bcc66  mov     [rbp+57h+ppMFType], r13
0x1801bcc6a  cmp     [rsi+1E0h], r13
0x1801bcc71  jnz     loc_1801BCD12
0x1801bcc77  mov     ebx, 0C00D36B2h
0x1801bcc7c  test    rcx, rcx
0x1801bcc7f  jnz     short loc_1801BCCC9
0x1801bcc81  call    cs:MFGetCallStackTracingWeakReference
0x1801bcc88  nop     dword ptr [rax+rax+00h]
0x1801bcc8d  mov     cs:qword_1803CEF18, rax
0x1801bcc94  mov     rcx, rax
0x1801bcc97  test    rax, rax
0x1801bcc9a  jz      short loc_1801BCCBB
0x1801bcc9c  mov     rax, [rax]
0x1801bcc9f  mov     edx, 7F0h
0x1801bcca4  mov     rax, [rax+8]
0x1801bcca8  call    cs:__guard_dispatch_icall_fptr
0x1801bccae  test    eax, eax
0x1801bccb0  jz      short loc_1801BCCBB
0x1801bccb2  mov     rcx, cs:qword_1803CEF18
0x1801bccb9  jmp     short loc_1801BCCC9
0x1801bccbb  lea     rcx, qword_1803CE250
0x1801bccc2  mov     cs:qword_1803CEF18, rcx
0x1801bccc9  cmp     [rcx+8], r13b
0x1801bcccd  jz      short loc_1801BCCF4
0x1801bcccf  call    sub_1800402C0
0x1801bccd4  cmp     [rax+7CCh], ebx
0x1801bccda  jz      short loc_1801BCCF4
0x1801bccdc  mov     r9d, ebx
0x1801bccdf  lea     rdx, aCmediasessionU_1; "CMediaSession::UpdateInputTypeUINT64"
0x1801bcce6  mov     r8d, 2546h
0x1801bccec  mov     rcx, rax
0x1801bccef  call    sub_1800EC0E0
0x1801bccf4  cmp     cs:byte_1803CECE8, 1
0x1801bccfb  jb      loc_1801BD2F5
0x1801bcd01  lea     r9, [rsi-210h]
0x1801bcd08  mov     edx, 2E7h
0x1801bcd0d  jmp     loc_1801BD2DA
0x1801bcd12  lea     rdi, [rsi-210h]
0x1801bcd19  mov     rdx, r14
0x1801bcd1c  mov     rcx, [rdi+3F0h]
0x1801bcd23  lea     r8, [rbp+57h+var_68]
0x1801bcd27  mov     rax, [rcx]
0x1801bcd2a  mov     rax, [rax+140h]
0x1801bcd31  call    cs:__guard_dispatch_icall_fptr
0x1801bcd37  mov     ebx, eax
0x1801bcd39  test    eax, eax
0x1801bcd3b  jns     loc_1801BCDD7
0x1801bcd41  mov     rcx, cs:qword_1803CEF18
0x1801bcd48  test    rcx, rcx
0x1801bcd4b  jnz     short loc_1801BCD95
0x1801bcd4d  call    cs:MFGetCallStackTracingWeakReference
0x1801bcd54  nop     dword ptr [rax+rax+00h]
0x1801bcd59  mov     cs:qword_1803CEF18, rax
0x1801bcd60  mov     rcx, rax
0x1801bcd63  test    rax, rax
0x1801bcd66  jz      short loc_1801BCD87
0x1801bcd68  mov     rax, [rax]
0x1801bcd6b  mov     edx, 7F0h
0x1801bcd70  mov     rax, [rax+8]
0x1801bcd74  call    cs:__guard_dispatch_icall_fptr
0x1801bcd7a  test    eax, eax
0x1801bcd7c  jz      short loc_1801BCD87
0x1801bcd7e  mov     rcx, cs:qword_1803CEF18
0x1801bcd85  jmp     short loc_1801BCD95
0x1801bcd87  lea     rcx, qword_1803CE250
0x1801bcd8e  mov     cs:qword_1803CEF18, rcx
0x1801bcd95  cmp     [rcx+8], r13b
0x1801bcd99  jz      short loc_1801BCDC0
0x1801bcd9b  call    sub_1800402C0
0x1801bcda0  cmp     [rax+7CCh], ebx
0x1801bcda6  jz      short loc_1801BCDC0
0x1801bcda8  mov     r9d, ebx
0x1801bcdab  lea     rdx, aCmediasessionU_1; "CMediaSession::UpdateInputTypeUINT64"
0x1801bcdb2  mov     r8d, 2549h
0x1801bcdb8  mov     rcx, rax
0x1801bcdbb  call    sub_1800EC0E0
0x1801bcdc0  cmp     cs:byte_1803CECE8, 1
0x1801bcdc7  jb      loc_1801BD2F5
0x1801bcdcd  mov     edx, 2E8h
0x1801bcdd2  jmp     loc_1801BD2D7
0x1801bcdd7  mov     rcx, [rbp+57h+var_68]
0x1801bcddb  lea     rdx, [rbp+57h+var_70]
0x1801bcddf  mov     rax, [rcx]
0x1801bcde2  mov     rax, [rax+110h]
0x1801bcde9  call    cs:__guard_dispatch_icall_fptr
0x1801bcdef  mov     ebx, eax
0x1801bcdf1  test    eax, eax
0x1801bcdf3  jns     loc_1801BCE8F
0x1801bcdf9  mov     rcx, cs:qword_1803CEF18
0x1801bce00  test    rcx, rcx
0x1801bce03  jnz     short loc_1801BCE4D
0x1801bce05  call    cs:MFGetCallStackTracingWeakReference
0x1801bce0c  nop     dword ptr [rax+rax+00h]
0x1801bce11  mov     cs:qword_1803CEF18, rax
0x1801bce18  mov     rcx, rax
0x1801bce1b  test    rax, rax
0x1801bce1e  jz      short loc_1801BCE3F
0x1801bce20  mov     rax, [rax]
0x1801bce23  mov     edx, 7F0h
0x1801bce28  mov     rax, [rax+8]
0x1801bce2c  call    cs:__guard_dispatch_icall_fptr
0x1801bce32  test    eax, eax
0x1801bce34  jz      short loc_1801BCE3F
0x1801bce36  mov     rcx, cs:qword_1803CEF18
0x1801bce3d  jmp     short loc_1801BCE4D
0x1801bce3f  lea     rcx, qword_1803CE250
0x1801bce46  mov     cs:qword_1803CEF18, rcx
0x1801bce4d  cmp     [rcx+8], r13b
0x1801bce51  jz      short loc_1801BCE78
0x1801bce53  call    sub_1800402C0
0x1801bce58  cmp     [rax+7CCh], ebx
0x1801bce5e  jz      short loc_1801BCE78
0x1801bce60  mov     r9d, ebx
0x1801bce63  lea     rdx, aCmediasessionU_1; "CMediaSession::UpdateInputTypeUINT64"
0x1801bce6a  mov     r8d, 254Ah
0x1801bce70  mov     rcx, rax
0x1801bce73  call    sub_1800EC0E0
0x1801bce78  cmp     cs:byte_1803CECE8, 1
0x1801bce7f  jb      loc_1801BD2F5
0x1801bce85  mov     edx, 2E9h
0x1801bce8a  jmp     loc_1801BD2D7
0x1801bce8f  mov     rcx, [rbp+57h+var_70]
0x1801bce93  lea     r8, [rbp+57h+var_80]
0x1801bce97  lea     rdx, stru_180367B40
0x1801bce9e  mov     rax, [rcx]
0x1801bcea1  mov     rax, [rax]
0x1801bcea4  call    cs:__guard_dispatch_icall_fptr
0x1801bceaa  mov     ebx, eax
0x1801bceac  test    eax, eax
0x1801bceae  jns     loc_1801BCF4A
0x1801bceb4  mov     rcx, cs:qword_1803CEF18
0x1801bcebb  test    rcx, rcx
0x1801bcebe  jnz     short loc_1801BCF08
0x1801bcec0  call    cs:MFGetCallStackTracingWeakReference
0x1801bcec7  nop     dword ptr [rax+rax+00h]
0x1801bcecc  mov     cs:qword_1803CEF18, rax
0x1801bced3  mov     rcx, rax
0x1801bced6  test    rax, rax
0x1801bced9  jz      short loc_1801BCEFA
0x1801bcedb  mov     rax, [rax]
0x1801bcede  mov     edx, 7F0h
0x1801bcee3  mov     rax, [rax+8]
0x1801bcee7  call    cs:__guard_dispatch_icall_fptr
0x1801bceed  test    eax, eax
0x1801bceef  jz      short loc_1801BCEFA
0x1801bcef1  mov     rcx, cs:qword_1803CEF18
0x1801bcef8  jmp     short loc_1801BCF08
0x1801bcefa  lea     rcx, qword_1803CE250
0x1801bcf01  mov     cs:qword_1803CEF18, rcx
0x1801bcf08  cmp     [rcx+8], r13b
0x1801bcf0c  jz      short loc_1801BCF33
0x1801bcf0e  call    sub_1800402C0
0x1801bcf13  cmp     [rax+7CCh], ebx
0x1801bcf19  jz      short loc_1801BCF33
0x1801bcf1b  mov     r9d, ebx
0x1801bcf1e  lea     rdx, aCmediasessionU_1; "CMediaSession::UpdateInputTypeUINT64"
0x1801bcf25  mov     r8d, 254Bh
0x1801bcf2b  mov     rcx, rax
0x1801bcf2e  call    sub_1800EC0E0
0x1801bcf33  cmp     cs:byte_1803CECE8, 1
0x1801bcf3a  jb      loc_1801BD2F5
0x1801bcf40  mov     edx, 2EAh
0x1801bcf45  jmp     loc_1801BD2D7
0x1801bcf4a  lea     rcx, [rbp+57h+ppMFType]; ppMFType
0x1801bcf4e  call    cs:MFCreateMediaType
0x1801bcf55  nop     dword ptr [rax+rax+00h]
0x1801bcf5a  mov     ebx, eax
0x1801bcf5c  test    eax, eax
0x1801bcf5e  jns     loc_1801BCFFA
0x1801bcf64  mov     rcx, cs:qword_1803CEF18
0x1801bcf6b  test    rcx, rcx
0x1801bcf6e  jnz     short loc_1801BCFB8
0x1801bcf70  call    cs:MFGetCallStackTracingWeakReference
0x1801bcf77  nop     dword ptr [rax+rax+00h]
0x1801bcf7c  mov     cs:qword_1803CEF18, rax
0x1801bcf83  mov     rcx, rax
0x1801bcf86  test    rax, rax
0x1801bcf89  jz      short loc_1801BCFAA
0x1801bcf8b  mov     rax, [rax]
0x1801bcf8e  mov     edx, 7F0h
0x1801bcf93  mov     rax, [rax+8]
0x1801bcf97  call    cs:__guard_dispatch_icall_fptr
0x1801bcf9d  test    eax, eax
0x1801bcf9f  jz      short loc_1801BCFAA
0x1801bcfa1  mov     rcx, cs:qword_1803CEF18
0x1801bcfa8  jmp     short loc_1801BCFB8
0x1801bcfaa  lea     rcx, qword_1803CE250
0x1801bcfb1  mov     cs:qword_1803CEF18, rcx
0x1801bcfb8  cmp     [rcx+8], r13b
0x1801bcfbc  jz      short loc_1801BCFE3
0x1801bcfbe  call    sub_1800402C0
0x1801bcfc3  cmp     [rax+7CCh], ebx
0x1801bcfc9  jz      short loc_1801BCFE3
0x1801bcfcb  mov     r9d, ebx
0x1801bcfce  lea     rdx, aCmediasessionU_1; "CMediaSession::UpdateInputTypeUINT64"
0x1801bcfd5  mov     r8d, 254Dh
0x1801bcfdb  mov     rcx, rax
0x1801bcfde  call    sub_1800EC0E0
0x1801bcfe3  cmp     cs:byte_1803CECE8, 1
0x1801bcfea  jb      loc_1801BD2F5
0x1801bcff0  mov     edx, 2EBh
0x1801bcff5  jmp     loc_1801BD2D7
0x1801bcffa  mov     rcx, [rbp+57h+var_80]
0x1801bcffe  lea     r8, [rbp+57h+var_78]
0x1801bd002  xor     edx, edx
0x1801bd004  mov     rax, [rcx]
0x1801bd007  mov     rax, [rax+88h]
0x1801bd00e  call    cs:__guard_dispatch_icall_fptr
0x1801bd014  mov     ebx, eax
0x1801bd016  test    eax, eax
0x1801bd018  jns     loc_1801BD0B4
0x1801bd01e  mov     rcx, cs:qword_1803CEF18
0x1801bd025  test    rcx, rcx
0x1801bd028  jnz     short loc_1801BD072
0x1801bd02a  call    cs:MFGetCallStackTracingWeakReference
0x1801bd031  nop     dword ptr [rax+rax+00h]
0x1801bd036  mov     cs:qword_1803CEF18, rax
0x1801bd03d  mov     rcx, rax
0x1801bd040  test    rax, rax
0x1801bd043  jz      short loc_1801BD064
0x1801bd045  mov     rax, [rax]
0x1801bd048  mov     edx, 7F0h
0x1801bd04d  mov     rax, [rax+8]
0x1801bd051  call    cs:__guard_dispatch_icall_fptr
0x1801bd057  test    eax, eax
0x1801bd059  jz      short loc_1801BD064
0x1801bd05b  mov     rcx, cs:qword_1803CEF18
0x1801bd062  jmp     short loc_1801BD072
0x1801bd064  lea     rcx, qword_1803CE250
0x1801bd06b  mov     cs:qword_1803CEF18, rcx
0x1801bd072  cmp     [rcx+8], r13b
0x1801bd076  jz      short loc_1801BD09D
0x1801bd078  call    sub_1800402C0
0x1801bd07d  cmp     [rax+7CCh], ebx
0x1801bd083  jz      short loc_1801BD09D
0x1801bd085  mov     r9d, ebx
0x1801bd088  lea     rdx, aCmediasessionU_1; "CMediaSession::UpdateInputTypeUINT64"
0x1801bd08f  mov     r8d, 254Eh
0x1801bd095  mov     rcx, rax
0x1801bd098  call    sub_1800EC0E0
0x1801bd09d  cmp     cs:byte_1803CECE8, 1
0x1801bd0a4  jb      loc_1801BD2F5
0x1801bd0aa  mov     edx, 2ECh
0x1801bd0af  jmp     loc_1801BD2D7
0x1801bd0b4  mov     rcx, [rbp+57h+var_78]
0x1801bd0b8  mov     rdx, [rbp+57h+ppMFType]
0x1801bd0bc  mov     rax, [rcx]
0x1801bd0bf  mov     rax, [rax+100h]
0x1801bd0c6  call    cs:__guard_dispatch_icall_fptr
0x1801bd0cc  mov     ebx, eax
0x1801bd0ce  test    eax, eax
0x1801bd0d0  jns     loc_1801BD16C
0x1801bd0d6  mov     rcx, cs:qword_1803CEF18
  ... truncated ...
```
