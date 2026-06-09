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
  __int64 v10; // r9
  __int64 *v11; // rcx
  __int64 v12; // rdi
  int v13; // ebx
  __int128 *v14; // rax
  __int128 v15; // xmm0
  HRESULT v16; // ebx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // r9
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 *v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 *v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r9
  __int64 *v36; // rcx
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 *v42; // rcx
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // r9
  __int64 *v48; // rcx
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // r9
  __int64 *v54; // rcx
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // rdx
  __int64 v58; // r8
  __int64 v59; // r9
  __int64 *v60; // rcx
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 v63; // rdx
  __int64 v64; // r8
  __int64 v65; // r9
  __int64 *v66; // rcx
  __int64 v67; // rax
  __int64 v68; // rax
  _BYTE v70[8]; // [rsp+30h] [rbp-39h] BYREF
  IMFMediaType *ppMFType; // [rsp+38h] [rbp-31h] BYREF
  __int64 v72; // [rsp+40h] [rbp-29h] BYREF
  __int64 v73; // [rsp+48h] [rbp-21h] BYREF
  __int64 (__fastcall ***v74)(_QWORD, const IID *, __int64 *); // [rsp+50h] [rbp-19h] BYREF
  __int64 v75; // [rsp+58h] [rbp-11h] BYREF
  _BYTE v76[16]; // [rsp+60h] [rbp-9h] BYREF

  sub_18002FEE0(v70, "CMediaSession::UpdateInputTypeUINT64", 9531);
  v11 = (__int64 *)qword_1803CEF18;
  if ( *(_BYTE *)(qword_1803CEF18 + 8) && *(_QWORD *)(a1 + 1088) )
  {
    v12 = sub_1800402C0(qword_1803CEF18);
    v13 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 1088) + 296LL))(*(_QWORD *)(a1 + 1088));
    v14 = (__int128 *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(a1 + 1088) + 280LL))(
                        *(_QWORD *)(a1 + 1088),
                        v76);
    v11 = (__int64 *)qword_1803CEF18;
    v15 = *v14;
    *(_DWORD *)(v12 + 2016) = v13;
    *(_OWORD *)(v12 + 2000) = v15;
  }
  v75 = 0;
  v74 = 0;
  v72 = 0;
  v73 = 0;
  ppMFType = 0;
  if ( *(_QWORD *)(a1 + 480) )
  {
    v16 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(**(_QWORD **)(a1 - 528 + 1008) + 320LL))(
            *(_QWORD *)(a1 - 528 + 1008),
            a2,
            &v75);
    if ( v16 >= 0 )
    {
      v16 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, const IID *, __int64 *)))(*(_QWORD *)v75 + 272LL))(
              v75,
              &v74);
      if ( v16 >= 0 )
      {
        v16 = (**v74)(v74, &stru_180367B40, &v72);
        if ( v16 >= 0 )
        {
          v16 = MFCreateMediaType(&ppMFType);
          if ( v16 >= 0 )
          {
            v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v72 + 136LL))(v72, 0, &v73);
            if ( v16 >= 0 )
            {
              v16 = (*(__int64 (__fastcall **)(__int64, IMFMediaType *))(*(_QWORD *)v73 + 256LL))(v73, ppMFType);
              if ( v16 >= 0 )
              {
                v16 = ((__int64 (__fastcall *)(IMFMediaType *, __int64, __int64))ppMFType->lpVtbl->SetUINT64)(
                        ppMFType,
                        a3,
                        a4);
                if ( v16 >= 0 )
                {
                  v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, IMFMediaType *, _QWORD))(*(_QWORD *)v72 + 120LL))(
                          v72,
                          0,
                          ppMFType,
                          0);
                  if ( v16 >= 0 )
                    goto LABEL_105;
                  v66 = (__int64 *)qword_1803CEF18;
                  if ( !qword_1803CEF18 )
                  {
                    v67 = MFGetCallStackTracingWeakReference(0, v63, v64, v65);
                    qword_1803CEF18 = v67;
                    if ( v67 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v67 + 8LL))(v67, 2032) )
                    {
                      v66 = (__int64 *)qword_1803CEF18;
                    }
                    else
                    {
                      v66 = &qword_1803CE250;
                      qword_1803CEF18 = (__int64)&qword_1803CE250;
                    }
                  }
                  if ( *((_BYTE *)v66 + 8) )
                  {
                    v68 = sub_1800402C0(v66);
                    if ( *(_DWORD *)(v68 + 1996) != v16 )
                      sub_1800EC0E0(v68, "CMediaSession::UpdateInputTypeUINT64", 9553, (unsigned int)v16);
                  }
                  if ( !byte_1803CECE8 )
                    goto LABEL_105;
                  v20 = 751;
                }
                else
                {
                  v60 = (__int64 *)qword_1803CEF18;
                  if ( !qword_1803CEF18 )
                  {
                    v61 = MFGetCallStackTracingWeakReference(0, v57, v58, v59);
                    qword_1803CEF18 = v61;
                    if ( v61 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v61 + 8LL))(v61, 2032) )
                    {
                      v60 = (__int64 *)qword_1803CEF18;
                    }
                    else
                    {
                      v60 = &qword_1803CE250;
                      qword_1803CEF18 = (__int64)&qword_1803CE250;
                    }
                  }
                  if ( *((_BYTE *)v60 + 8) )
                  {
                    v62 = sub_1800402C0(v60);
                    if ( *(_DWORD *)(v62 + 1996) != v16 )
                      sub_1800EC0E0(v62, "CMediaSession::UpdateInputTypeUINT64", 9552, (unsigned int)v16);
                  }
                  if ( !byte_1803CECE8 )
                    goto LABEL_105;
                  v20 = 750;
                }
              }
              else
              {
                v54 = (__int64 *)qword_1803CEF18;
                if ( !qword_1803CEF18 )
                {
                  v55 = MFGetCallStackTracingWeakReference(0, v51, v52, v53);
                  qword_1803CEF18 = v55;
                  if ( v55 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2032) )
                  {
                    v54 = (__int64 *)qword_1803CEF18;
                  }
                  else
                  {
                    v54 = &qword_1803CE250;
                    qword_1803CEF18 = (__int64)&qword_1803CE250;
                  }
                }
                if ( *((_BYTE *)v54 + 8) )
                {
                  v56 = sub_1800402C0(v54);
                  if ( *(_DWORD *)(v56 + 1996) != v16 )
                    sub_1800EC0E0(v56, "CMediaSession::UpdateInputTypeUINT64", 9551, (unsigned int)v16);
                }
                if ( !byte_1803CECE8 )
                  goto LABEL_105;
                v20 = 749;
              }
            }
            else
            {
              v48 = (__int64 *)qword_1803CEF18;
              if ( !qword_1803CEF18 )
              {
                v49 = MFGetCallStackTracingWeakReference(0, v45, v46, v47);
                qword_1803CEF18 = v49;
                if ( v49 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
                {
                  v48 = (__int64 *)qword_1803CEF18;
                }
                else
                {
                  v48 = &qword_1803CE250;
                  qword_1803CEF18 = (__int64)&qword_1803CE250;
                }
              }
              if ( *((_BYTE *)v48 + 8) )
              {
                v50 = sub_1800402C0(v48);
                if ( *(_DWORD *)(v50 + 1996) != v16 )
                  sub_1800EC0E0(v50, "CMediaSession::UpdateInputTypeUINT64", 9550, (unsigned int)v16);
              }
              if ( !byte_1803CECE8 )
                goto LABEL_105;
              v20 = 748;
            }
          }
          else
          {
            v42 = (__int64 *)qword_1803CEF18;
            if ( !qword_1803CEF18 )
            {
              v43 = MFGetCallStackTracingWeakReference(0, v39, v40, v41);
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
              if ( *(_DWORD *)(v44 + 1996) != v16 )
                sub_1800EC0E0(v44, "CMediaSession::UpdateInputTypeUINT64", 9549, (unsigned int)v16);
            }
            if ( !byte_1803CECE8 )
              goto LABEL_105;
            v20 = 747;
          }
        }
        else
        {
          v36 = (__int64 *)qword_1803CEF18;
          if ( !qword_1803CEF18 )
          {
            v37 = MFGetCallStackTracingWeakReference(0, v33, v34, v35);
            qword_1803CEF18 = v37;
            if ( v37 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
            {
              v36 = (__int64 *)qword_1803CEF18;
            }
            else
            {
              v36 = &qword_1803CE250;
              qword_1803CEF18 = (__int64)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v36 + 8) )
          {
            v38 = sub_1800402C0(v36);
            if ( *(_DWORD *)(v38 + 1996) != v16 )
              sub_1800EC0E0(v38, "CMediaSession::UpdateInputTypeUINT64", 9547, (unsigned int)v16);
          }
          if ( !byte_1803CECE8 )
            goto LABEL_105;
          v20 = 746;
        }
      }
      else
      {
        v30 = (__int64 *)qword_1803CEF18;
        if ( !qword_1803CEF18 )
        {
          v31 = MFGetCallStackTracingWeakReference(0, v27, v28, v29);
          qword_1803CEF18 = v31;
          if ( v31 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
          {
            v30 = (__int64 *)qword_1803CEF18;
          }
          else
          {
            v30 = &qword_1803CE250;
            qword_1803CEF18 = (__int64)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v30 + 8) )
        {
          v32 = sub_1800402C0(v30);
          if ( *(_DWORD *)(v32 + 1996) != v16 )
            sub_1800EC0E0(v32, "CMediaSession::UpdateInputTypeUINT64", 9546, (unsigned int)v16);
        }
        if ( !byte_1803CECE8 )
          goto LABEL_105;
        v20 = 745;
      }
    }
    else
    {
      v24 = (__int64 *)qword_1803CEF18;
      if ( !qword_1803CEF18 )
      {
        v25 = MFGetCallStackTracingWeakReference(0, v21, v22, v23);
        qword_1803CEF18 = v25;
        if ( v25 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
        {
          v24 = (__int64 *)qword_1803CEF18;
        }
        else
        {
          v24 = &qword_1803CE250;
          qword_1803CEF18 = (__int64)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v24 + 8) )
      {
        v26 = sub_1800402C0(v24);
        if ( *(_DWORD *)(v26 + 1996) != v16 )
          sub_1800EC0E0(v26, "CMediaSession::UpdateInputTypeUINT64", 9545, (unsigned int)v16);
      }
      if ( !byte_1803CECE8 )
        goto LABEL_105;
      v20 = 744;
    }
    v19 = a1 - 528;
    goto LABEL_104;
  }
  v16 = -1072875854;
  if ( !v11 )
  {
    v17 = MFGetCallStackTracingWeakReference(0, v8, v9, v10);
    qword_1803CEF18 = v17;
    if ( v17 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
    {
      v11 = (__int64 *)qword_1803CEF18;
    }
    else
    {
      v11 = &qword_1803CE250;
      qword_1803CEF18 = (__int64)&qword_1803CE250;
    }
  }
  if ( *((_BYTE *)v11 + 8) )
  {
    v18 = sub_1800402C0(v11);
    if ( *(_DWORD *)(v18 + 1996) != -1072875854 )
      sub_1800EC0E0(v18, "CMediaSession::UpdateInputTypeUINT64", 9542, 3222091442LL);
  }
  if ( byte_1803CECE8 )
  {
    v19 = a1 - 528;
    v20 = 743;
LABEL_104:
    sub_180050D6C(*((_QWORD *)RequestContext + 2), v20, &stru_180365588, v19, v16);
  }
LABEL_105:
  sub_180063F00(&ppMFType);
  sub_180063F00(&v73);
  sub_180063F00(&v72);
  sub_180063F00(&v74);
  sub_180063F00(&v75);
  sub_18003ECB0(v70);
  return (unsigned int)v16;
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
