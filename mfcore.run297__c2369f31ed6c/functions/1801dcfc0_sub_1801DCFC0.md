# sub_1801DCFC0

- ea: `0x1801dcfc0`
- end: `0x1801dd771`
- name: `sub_1801DCFC0`
- size: `1969`
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
- `0x1801dcfc0`
- `0x180258480`
- `0x180344d40`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x1801dd36e`
- `MFPlat!MFCreateMediaType` at `0x1801dd36e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd0a1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd16d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd225`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd2e0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd390`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd44a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd502`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd5bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd679`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd0a1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd16d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd225`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd2e0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd390`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd44a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd502`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd5bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd679`

## string_xrefs

- `0x1801dcff0`: `CMediaSession::UpdateOutputTypeGUID`
- `0x1801dd0ff`: `CMediaSession::UpdateOutputTypeGUID`
- `0x1801dd1cb`: `CMediaSession::UpdateOutputTypeGUID`
- `0x1801dd283`: `CMediaSession::UpdateOutputTypeGUID`
- `0x1801dd33e`: `CMediaSession::UpdateOutputTypeGUID`
- `0x1801dd3ee`: `CMediaSession::UpdateOutputTypeGUID`
- `0x1801dd4a8`: `CMediaSession::UpdateOutputTypeGUID`
- `0x1801dd560`: `CMediaSession::UpdateOutputTypeGUID`
- `0x1801dd61a`: `CMediaSession::UpdateOutputTypeGUID`
- `0x1801dd6d7`: `CMediaSession::UpdateOutputTypeGUID`

## pseudocode

```c
__int64 __fastcall sub_1801DCFC0(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
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

  sub_18002FEE0(v61, "CMediaSession::UpdateOutputTypeGUID", 9562);
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
            v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v63 + 144LL))(v63, 0, &v64);
            if ( v15 >= 0 )
            {
              v15 = (*(__int64 (__fastcall **)(__int64, IMFMediaType *))(*(_QWORD *)v64 + 256LL))(v64, ppMFType);
              if ( v15 >= 0 )
              {
                v15 = ((__int64 (__fastcall *)(IMFMediaType *, __int64, __int64))ppMFType->lpVtbl->SetGUID)(
                        ppMFType,
                        a3,
                        a4);
                if ( v15 >= 0 )
                {
                  v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, IMFMediaType *, _QWORD))(*(_QWORD *)v63 + 128LL))(
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
                      sub_1800EC0E0(v59, "CMediaSession::UpdateOutputTypeGUID", 9584, (unsigned int)v15);
                  }
                  if ( !byte_1803CECE8 )
                    goto LABEL_105;
                  v19 = 760;
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
                      sub_1800EC0E0(v54, "CMediaSession::UpdateOutputTypeGUID", 9583, (unsigned int)v15);
                  }
                  if ( !byte_1803CECE8 )
                    goto LABEL_105;
                  v19 = 759;
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
                    sub_1800EC0E0(v49, "CMediaSession::UpdateOutputTypeGUID", 9582, (unsigned int)v15);
                }
                if ( !byte_1803CECE8 )
                  goto LABEL_105;
                v19 = 758;
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
                  sub_1800EC0E0(v44, "CMediaSession::UpdateOutputTypeGUID", 9581, (unsigned int)v15);
              }
              if ( !byte_1803CECE8 )
                goto LABEL_105;
              v19 = 757;
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
                sub_1800EC0E0(v39, "CMediaSession::UpdateOutputTypeGUID", 9580, (unsigned int)v15);
            }
            if ( !byte_1803CECE8 )
              goto LABEL_105;
            v19 = 756;
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
              sub_1800EC0E0(v34, "CMediaSession::UpdateOutputTypeGUID", 9578, (unsigned int)v15);
          }
          if ( !byte_1803CECE8 )
            goto LABEL_105;
          v19 = 755;
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
            sub_1800EC0E0(v29, "CMediaSession::UpdateOutputTypeGUID", 9577, (unsigned int)v15);
        }
        if ( !byte_1803CECE8 )
          goto LABEL_105;
        v19 = 754;
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
          sub_1800EC0E0(v24, "CMediaSession::UpdateOutputTypeGUID", 9576, (unsigned int)v15);
      }
      if ( !byte_1803CECE8 )
        goto LABEL_105;
      v19 = 753;
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
      sub_1800EC0E0(v17, "CMediaSession::UpdateOutputTypeGUID", 9573, 3222091442LL);
  }
  if ( byte_1803CECE8 )
  {
    v18 = a1 - 528;
    v19 = 752;
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
0x1801dcfc0  push    rbp
0x1801dcfc2  push    rbx
0x1801dcfc3  push    rsi
0x1801dcfc4  push    rdi
0x1801dcfc5  push    r12
0x1801dcfc7  push    r13
0x1801dcfc9  push    r14
0x1801dcfcb  push    r15
0x1801dcfcd  lea     rbp, [rsp-1Fh]
0x1801dcfd2  sub     rsp, 88h
0x1801dcfd9  mov     rax, cs:__security_cookie
0x1801dcfe0  xor     rax, rsp
0x1801dcfe3  mov     [rbp+57h+var_50], rax
0x1801dcfe7  mov     r15, r8
0x1801dcfea  mov     r14, rdx
0x1801dcfed  mov     rsi, rcx
0x1801dcff0  lea     rdx, aCmediasessionU_2; "CMediaSession::UpdateOutputTypeGUID"
0x1801dcff7  mov     r8d, 255Ah
0x1801dcffd  lea     rcx, [rbp+57h+var_90]
0x1801dd001  mov     r12, r9
0x1801dd004  call    sub_18002FEE0
0x1801dd009  mov     rcx, cs:qword_1803CEF18
0x1801dd010  xor     r13d, r13d
0x1801dd013  cmp     [rcx+8], r13b
0x1801dd017  jz      short loc_1801DD076
0x1801dd019  cmp     [rsi+440h], r13
0x1801dd020  jz      short loc_1801DD076
0x1801dd022  call    sub_1800402C0
0x1801dd027  mov     rcx, [rsi+440h]
0x1801dd02e  mov     rdi, rax
0x1801dd031  mov     rdx, [rcx]
0x1801dd034  mov     rax, [rdx+128h]
0x1801dd03b  call    cs:__guard_dispatch_icall_fptr
0x1801dd041  mov     rcx, [rsi+440h]
0x1801dd048  mov     ebx, eax
0x1801dd04a  mov     rdx, [rcx]
0x1801dd04d  mov     rax, [rdx+118h]
0x1801dd054  lea     rdx, [rbp+57h+var_60]
0x1801dd058  call    cs:__guard_dispatch_icall_fptr
0x1801dd05e  mov     rcx, cs:qword_1803CEF18
0x1801dd065  movups  xmm0, xmmword ptr [rax]
0x1801dd068  mov     [rdi+7E0h], ebx
0x1801dd06e  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1801dd076  mov     [rbp+57h+var_68], r13
0x1801dd07a  mov     [rbp+57h+var_70], r13
0x1801dd07e  mov     [rbp+57h+var_80], r13
0x1801dd082  mov     [rbp+57h+var_78], r13
0x1801dd086  mov     [rbp+57h+ppMFType], r13
0x1801dd08a  cmp     [rsi+1E0h], r13
0x1801dd091  jnz     loc_1801DD132
0x1801dd097  mov     ebx, 0C00D36B2h
0x1801dd09c  test    rcx, rcx
0x1801dd09f  jnz     short loc_1801DD0E9
0x1801dd0a1  call    cs:MFGetCallStackTracingWeakReference
0x1801dd0a8  nop     dword ptr [rax+rax+00h]
0x1801dd0ad  mov     cs:qword_1803CEF18, rax
0x1801dd0b4  mov     rcx, rax
0x1801dd0b7  test    rax, rax
0x1801dd0ba  jz      short loc_1801DD0DB
0x1801dd0bc  mov     rax, [rax]
0x1801dd0bf  mov     edx, 7F0h
0x1801dd0c4  mov     rax, [rax+8]
0x1801dd0c8  call    cs:__guard_dispatch_icall_fptr
0x1801dd0ce  test    eax, eax
0x1801dd0d0  jz      short loc_1801DD0DB
0x1801dd0d2  mov     rcx, cs:qword_1803CEF18
0x1801dd0d9  jmp     short loc_1801DD0E9
0x1801dd0db  lea     rcx, qword_1803CE250
0x1801dd0e2  mov     cs:qword_1803CEF18, rcx
0x1801dd0e9  cmp     [rcx+8], r13b
0x1801dd0ed  jz      short loc_1801DD114
0x1801dd0ef  call    sub_1800402C0
0x1801dd0f4  cmp     [rax+7CCh], ebx
0x1801dd0fa  jz      short loc_1801DD114
0x1801dd0fc  mov     r9d, ebx
0x1801dd0ff  lea     rdx, aCmediasessionU_2; "CMediaSession::UpdateOutputTypeGUID"
0x1801dd106  mov     r8d, 2565h
0x1801dd10c  mov     rcx, rax
0x1801dd10f  call    sub_1800EC0E0
0x1801dd114  cmp     cs:byte_1803CECE8, 1
0x1801dd11b  jb      loc_1801DD718
0x1801dd121  lea     r9, [rsi-210h]
0x1801dd128  mov     edx, 2F0h
0x1801dd12d  jmp     loc_1801DD6FD
0x1801dd132  lea     rdi, [rsi-210h]
0x1801dd139  mov     rdx, r14
0x1801dd13c  mov     rcx, [rdi+3F0h]
0x1801dd143  lea     r8, [rbp+57h+var_68]
0x1801dd147  mov     rax, [rcx]
0x1801dd14a  mov     rax, [rax+140h]
0x1801dd151  call    cs:__guard_dispatch_icall_fptr
0x1801dd157  mov     ebx, eax
0x1801dd159  test    eax, eax
0x1801dd15b  jns     loc_1801DD1F7
0x1801dd161  mov     rcx, cs:qword_1803CEF18
0x1801dd168  test    rcx, rcx
0x1801dd16b  jnz     short loc_1801DD1B5
0x1801dd16d  call    cs:MFGetCallStackTracingWeakReference
0x1801dd174  nop     dword ptr [rax+rax+00h]
0x1801dd179  mov     cs:qword_1803CEF18, rax
0x1801dd180  mov     rcx, rax
0x1801dd183  test    rax, rax
0x1801dd186  jz      short loc_1801DD1A7
0x1801dd188  mov     rax, [rax]
0x1801dd18b  mov     edx, 7F0h
0x1801dd190  mov     rax, [rax+8]
0x1801dd194  call    cs:__guard_dispatch_icall_fptr
0x1801dd19a  test    eax, eax
0x1801dd19c  jz      short loc_1801DD1A7
0x1801dd19e  mov     rcx, cs:qword_1803CEF18
0x1801dd1a5  jmp     short loc_1801DD1B5
0x1801dd1a7  lea     rcx, qword_1803CE250
0x1801dd1ae  mov     cs:qword_1803CEF18, rcx
0x1801dd1b5  cmp     [rcx+8], r13b
0x1801dd1b9  jz      short loc_1801DD1E0
0x1801dd1bb  call    sub_1800402C0
0x1801dd1c0  cmp     [rax+7CCh], ebx
0x1801dd1c6  jz      short loc_1801DD1E0
0x1801dd1c8  mov     r9d, ebx
0x1801dd1cb  lea     rdx, aCmediasessionU_2; "CMediaSession::UpdateOutputTypeGUID"
0x1801dd1d2  mov     r8d, 2568h
0x1801dd1d8  mov     rcx, rax
0x1801dd1db  call    sub_1800EC0E0
0x1801dd1e0  cmp     cs:byte_1803CECE8, 1
0x1801dd1e7  jb      loc_1801DD718
0x1801dd1ed  mov     edx, 2F1h
0x1801dd1f2  jmp     loc_1801DD6FA
0x1801dd1f7  mov     rcx, [rbp+57h+var_68]
0x1801dd1fb  lea     rdx, [rbp+57h+var_70]
0x1801dd1ff  mov     rax, [rcx]
0x1801dd202  mov     rax, [rax+110h]
0x1801dd209  call    cs:__guard_dispatch_icall_fptr
0x1801dd20f  mov     ebx, eax
0x1801dd211  test    eax, eax
0x1801dd213  jns     loc_1801DD2AF
0x1801dd219  mov     rcx, cs:qword_1803CEF18
0x1801dd220  test    rcx, rcx
0x1801dd223  jnz     short loc_1801DD26D
0x1801dd225  call    cs:MFGetCallStackTracingWeakReference
0x1801dd22c  nop     dword ptr [rax+rax+00h]
0x1801dd231  mov     cs:qword_1803CEF18, rax
0x1801dd238  mov     rcx, rax
0x1801dd23b  test    rax, rax
0x1801dd23e  jz      short loc_1801DD25F
0x1801dd240  mov     rax, [rax]
0x1801dd243  mov     edx, 7F0h
0x1801dd248  mov     rax, [rax+8]
0x1801dd24c  call    cs:__guard_dispatch_icall_fptr
0x1801dd252  test    eax, eax
0x1801dd254  jz      short loc_1801DD25F
0x1801dd256  mov     rcx, cs:qword_1803CEF18
0x1801dd25d  jmp     short loc_1801DD26D
0x1801dd25f  lea     rcx, qword_1803CE250
0x1801dd266  mov     cs:qword_1803CEF18, rcx
0x1801dd26d  cmp     [rcx+8], r13b
0x1801dd271  jz      short loc_1801DD298
0x1801dd273  call    sub_1800402C0
0x1801dd278  cmp     [rax+7CCh], ebx
0x1801dd27e  jz      short loc_1801DD298
0x1801dd280  mov     r9d, ebx
0x1801dd283  lea     rdx, aCmediasessionU_2; "CMediaSession::UpdateOutputTypeGUID"
0x1801dd28a  mov     r8d, 2569h
0x1801dd290  mov     rcx, rax
0x1801dd293  call    sub_1800EC0E0
0x1801dd298  cmp     cs:byte_1803CECE8, 1
0x1801dd29f  jb      loc_1801DD718
0x1801dd2a5  mov     edx, 2F2h
0x1801dd2aa  jmp     loc_1801DD6FA
0x1801dd2af  mov     rcx, [rbp+57h+var_70]
0x1801dd2b3  lea     r8, [rbp+57h+var_80]
0x1801dd2b7  lea     rdx, stru_180367B40
0x1801dd2be  mov     rax, [rcx]
0x1801dd2c1  mov     rax, [rax]
0x1801dd2c4  call    cs:__guard_dispatch_icall_fptr
0x1801dd2ca  mov     ebx, eax
0x1801dd2cc  test    eax, eax
0x1801dd2ce  jns     loc_1801DD36A
0x1801dd2d4  mov     rcx, cs:qword_1803CEF18
0x1801dd2db  test    rcx, rcx
0x1801dd2de  jnz     short loc_1801DD328
0x1801dd2e0  call    cs:MFGetCallStackTracingWeakReference
0x1801dd2e7  nop     dword ptr [rax+rax+00h]
0x1801dd2ec  mov     cs:qword_1803CEF18, rax
0x1801dd2f3  mov     rcx, rax
0x1801dd2f6  test    rax, rax
0x1801dd2f9  jz      short loc_1801DD31A
0x1801dd2fb  mov     rax, [rax]
0x1801dd2fe  mov     edx, 7F0h
0x1801dd303  mov     rax, [rax+8]
0x1801dd307  call    cs:__guard_dispatch_icall_fptr
0x1801dd30d  test    eax, eax
0x1801dd30f  jz      short loc_1801DD31A
0x1801dd311  mov     rcx, cs:qword_1803CEF18
0x1801dd318  jmp     short loc_1801DD328
0x1801dd31a  lea     rcx, qword_1803CE250
0x1801dd321  mov     cs:qword_1803CEF18, rcx
0x1801dd328  cmp     [rcx+8], r13b
0x1801dd32c  jz      short loc_1801DD353
0x1801dd32e  call    sub_1800402C0
0x1801dd333  cmp     [rax+7CCh], ebx
0x1801dd339  jz      short loc_1801DD353
0x1801dd33b  mov     r9d, ebx
0x1801dd33e  lea     rdx, aCmediasessionU_2; "CMediaSession::UpdateOutputTypeGUID"
0x1801dd345  mov     r8d, 256Ah
0x1801dd34b  mov     rcx, rax
0x1801dd34e  call    sub_1800EC0E0
0x1801dd353  cmp     cs:byte_1803CECE8, 1
0x1801dd35a  jb      loc_1801DD718
0x1801dd360  mov     edx, 2F3h
0x1801dd365  jmp     loc_1801DD6FA
0x1801dd36a  lea     rcx, [rbp+57h+ppMFType]; ppMFType
0x1801dd36e  call    cs:MFCreateMediaType
0x1801dd375  nop     dword ptr [rax+rax+00h]
0x1801dd37a  mov     ebx, eax
0x1801dd37c  test    eax, eax
0x1801dd37e  jns     loc_1801DD41A
0x1801dd384  mov     rcx, cs:qword_1803CEF18
0x1801dd38b  test    rcx, rcx
0x1801dd38e  jnz     short loc_1801DD3D8
0x1801dd390  call    cs:MFGetCallStackTracingWeakReference
0x1801dd397  nop     dword ptr [rax+rax+00h]
0x1801dd39c  mov     cs:qword_1803CEF18, rax
0x1801dd3a3  mov     rcx, rax
0x1801dd3a6  test    rax, rax
0x1801dd3a9  jz      short loc_1801DD3CA
0x1801dd3ab  mov     rax, [rax]
0x1801dd3ae  mov     edx, 7F0h
0x1801dd3b3  mov     rax, [rax+8]
0x1801dd3b7  call    cs:__guard_dispatch_icall_fptr
0x1801dd3bd  test    eax, eax
0x1801dd3bf  jz      short loc_1801DD3CA
0x1801dd3c1  mov     rcx, cs:qword_1803CEF18
0x1801dd3c8  jmp     short loc_1801DD3D8
0x1801dd3ca  lea     rcx, qword_1803CE250
0x1801dd3d1  mov     cs:qword_1803CEF18, rcx
0x1801dd3d8  cmp     [rcx+8], r13b
0x1801dd3dc  jz      short loc_1801DD403
0x1801dd3de  call    sub_1800402C0
0x1801dd3e3  cmp     [rax+7CCh], ebx
0x1801dd3e9  jz      short loc_1801DD403
0x1801dd3eb  mov     r9d, ebx
0x1801dd3ee  lea     rdx, aCmediasessionU_2; "CMediaSession::UpdateOutputTypeGUID"
0x1801dd3f5  mov     r8d, 256Ch
0x1801dd3fb  mov     rcx, rax
0x1801dd3fe  call    sub_1800EC0E0
0x1801dd403  cmp     cs:byte_1803CECE8, 1
0x1801dd40a  jb      loc_1801DD718
0x1801dd410  mov     edx, 2F4h
0x1801dd415  jmp     loc_1801DD6FA
0x1801dd41a  mov     rcx, [rbp+57h+var_80]
0x1801dd41e  lea     r8, [rbp+57h+var_78]
0x1801dd422  xor     edx, edx
0x1801dd424  mov     rax, [rcx]
0x1801dd427  mov     rax, [rax+90h]
0x1801dd42e  call    cs:__guard_dispatch_icall_fptr
0x1801dd434  mov     ebx, eax
0x1801dd436  test    eax, eax
0x1801dd438  jns     loc_1801DD4D4
0x1801dd43e  mov     rcx, cs:qword_1803CEF18
0x1801dd445  test    rcx, rcx
0x1801dd448  jnz     short loc_1801DD492
0x1801dd44a  call    cs:MFGetCallStackTracingWeakReference
0x1801dd451  nop     dword ptr [rax+rax+00h]
0x1801dd456  mov     cs:qword_1803CEF18, rax
0x1801dd45d  mov     rcx, rax
0x1801dd460  test    rax, rax
0x1801dd463  jz      short loc_1801DD484
0x1801dd465  mov     rax, [rax]
0x1801dd468  mov     edx, 7F0h
0x1801dd46d  mov     rax, [rax+8]
0x1801dd471  call    cs:__guard_dispatch_icall_fptr
0x1801dd477  test    eax, eax
0x1801dd479  jz      short loc_1801DD484
0x1801dd47b  mov     rcx, cs:qword_1803CEF18
0x1801dd482  jmp     short loc_1801DD492
0x1801dd484  lea     rcx, qword_1803CE250
0x1801dd48b  mov     cs:qword_1803CEF18, rcx
0x1801dd492  cmp     [rcx+8], r13b
0x1801dd496  jz      short loc_1801DD4BD
0x1801dd498  call    sub_1800402C0
0x1801dd49d  cmp     [rax+7CCh], ebx
0x1801dd4a3  jz      short loc_1801DD4BD
0x1801dd4a5  mov     r9d, ebx
0x1801dd4a8  lea     rdx, aCmediasessionU_2; "CMediaSession::UpdateOutputTypeGUID"
0x1801dd4af  mov     r8d, 256Dh
0x1801dd4b5  mov     rcx, rax
0x1801dd4b8  call    sub_1800EC0E0
0x1801dd4bd  cmp     cs:byte_1803CECE8, 1
0x1801dd4c4  jb      loc_1801DD718
0x1801dd4ca  mov     edx, 2F5h
0x1801dd4cf  jmp     loc_1801DD6FA
0x1801dd4d4  mov     rcx, [rbp+57h+var_78]
0x1801dd4d8  mov     rdx, [rbp+57h+ppMFType]
0x1801dd4dc  mov     rax, [rcx]
0x1801dd4df  mov     rax, [rax+100h]
0x1801dd4e6  call    cs:__guard_dispatch_icall_fptr
0x1801dd4ec  mov     ebx, eax
0x1801dd4ee  test    eax, eax
0x1801dd4f0  jns     loc_1801DD58C
0x1801dd4f6  mov     rcx, cs:qword_1803CEF18
  ... truncated ...
```
