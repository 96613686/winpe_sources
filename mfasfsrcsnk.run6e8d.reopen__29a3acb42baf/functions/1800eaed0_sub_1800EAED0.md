# sub_1800EAED0

- ea: `0x1800eaed0`
- end: `0x1800eb750`
- name: `sub_1800EAED0`
- size: `2176`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: ``

## callers

- `0x1800ec014`
- `0x1800ec27c`

## callees

- `0x180001870`
- `0x180005880`
- `0x180009440`
- `0x18000a580`
- `0x18003d740`
- `0x18004f390`
- `0x18005ef9c`
- `0x18007fdd0`
- `0x1800d7188`
- `0x1800ea888`
- `0x1800eaed0`
- `0x1800eb758`
- `0x1800ebb88`
- `0x1800ec4cc`
- `0x18013e2e0`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eb058`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eb11e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eb1d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eb290`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eb355`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eb410`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eb4c5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eb5b9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eb663`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eb058`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eb11e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eb1d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eb290`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eb355`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eb410`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eb4c5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eb5b9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eb663`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800eb03c`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800eb03c`

## string_xrefs

- `0x1800eaf05`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`
- `0x1800eb01c`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`
- `0x1800eb468`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`
- `0x1800eb51d`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`
- `0x1800eb611`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`
- `0x1800eb6bb`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`

## pseudocode

```c
__int64 __fastcall sub_1800EAED0(__int64 a1, int a2, int a3, _QWORD *a4)
{
  __int64 v8; // rdi
  int v9; // ebx
  __int128 v10; // xmm0
  __int64 v11; // rdx
  HRESULT v12; // ebx
  __int64 (__fastcall ***v13)(); // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 (__fastcall ***v18)(); // rcx
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 (__fastcall ***v22)(); // rcx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 (__fastcall ***v26)(); // rcx
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rdx
  __int64 (__fastcall ***v30)(); // rcx
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rdi
  __int64 v34; // rdx
  __int64 v35; // r14
  __int64 (__fastcall ***v36)(); // rcx
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rdx
  __int64 (__fastcall ***v40)(); // rcx
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 (__fastcall ***v45)(); // rcx
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rdx
  __int64 (__fastcall ***v49)(); // rcx
  __int64 v50; // rax
  __int64 v51; // rax
  _BYTE v53[8]; // [rsp+40h] [rbp-C0h] BYREF
  void *ppv; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v55; // [rsp+50h] [rbp-B0h] BYREF
  int v56[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v57; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v58; // [rsp+70h] [rbp-90h]
  PROPVARIANT pvar; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v60[12]; // [rsp+90h] [rbp-70h]
  _BYTE v61[16]; // [rsp+F0h] [rbp-10h] BYREF

  v60[1] = L"dummy.asf";
  ppv = 0;
  v60[0] = 0;
  v60[2] = L"dummy.mp3";
  *(_QWORD *)v56 = 0;
  v60[3] = L"dummy.mp4";
  v55 = 0;
  v60[4] = L"dummy.avi";
  v60[5] = L"dummy.m2ts";
  v60[6] = L"dummy.wav";
  v60[7] = L"dummy.adts";
  v60[8] = L"dummy.ac3";
  v60[9] = L"dummy.mkv";
  v60[10] = L"dummy.flac";
  v58 = 0;
  v57 = 0;
  memset(&pvar, 0, sizeof(pvar));
  sub_18000A580(v53, "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver", 416);
  if ( *(_BYTE *)(qword_180169350 + 8) && *(_QWORD *)(a1 + 400) )
  {
    v8 = sub_180001870(qword_180169350);
    v9 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 400) + 296LL))(*(_QWORD *)(a1 + 400));
    v10 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(a1 + 400) + 280LL))(
                       *(_QWORD *)(a1 + 400),
                       v61);
    *(_DWORD *)(v8 + 2016) = v9;
    *(_OWORD *)(v8 + 2000) = v10;
  }
  *a4 = 0;
  sub_18005EF9C(&ppv);
  v12 = PSCreateMemoryPropertyStore(&stru_18014F050, &ppv);
  if ( v12 >= 0 )
  {
    LOWORD(v57) = 11;
    WORD4(v57) = -1;
    v12 = (*(__int64 (__fastcall **)(void *, __int64 *, __int128 *))(*(_QWORD *)ppv + 48LL))(ppv, qword_180151350, &v57);
    if ( v12 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(void *, __int64 *, __int128 *))(*(_QWORD *)ppv + 48LL))(
              ppv,
              qword_18015A720,
              &v57);
      if ( v12 >= 0 )
      {
        if ( *(_DWORD *)(a1 + 28) == 5
          && (v12 = (*(__int64 (__fastcall **)(void *, __int64 *, __int128 *))(*(_QWORD *)ppv + 48LL))(
                      ppv,
                      qword_18015A708,
                      &v57),
              v12 < 0) )
        {
          v26 = (__int64 (__fastcall ***)())qword_180169350;
          if ( !qword_180169350 )
          {
            v27 = MFGetCallStackTracingWeakReference(0, v25);
            qword_180169350 = v27;
            if ( v27 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
            {
              v26 = (__int64 (__fastcall ***)())qword_180169350;
            }
            else
            {
              v26 = &off_1801683B0;
              qword_180169350 = (__int64)&off_1801683B0;
            }
          }
          if ( *((_BYTE *)v26 + 8) )
          {
            v28 = sub_180001870(v26);
            if ( *(_DWORD *)(v28 + 1996) != v12 )
              sub_18007FDD0(
                v28,
                "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver",
                434,
                (unsigned int)v12);
          }
          if ( byte_1801692C8 )
          {
            v16 = 31;
            goto LABEL_106;
          }
        }
        else
        {
          sub_1800D7188(&pvar, *(_QWORD *)(a1 + 400));
          v12 = (*(__int64 (__fastcall **)(void *, __int64 *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                  ppv,
                  qword_18014E870,
                  &pvar);
          if ( v12 >= 0 )
          {
            LODWORD(v33) = 0;
            if ( *(_DWORD *)(a1 + 28) < 0xBu )
              v33 = v60[*(int *)(a1 + 28)];
            v35 = sub_1800EC4CC(a1);
            if ( v35 < *(_QWORD *)(a1 + 360) )
            {
              sub_18005EF9C(v56);
              v12 = sub_1800EB758(*(_QWORD *)(a1 + 400), v56);
              if ( v12 >= 0 )
              {
                sub_18005EF9C(&v55);
                v12 = sub_1800EBB88(
                        v56[0],
                        a3,
                        a2,
                        v33,
                        (__int64)ppv,
                        (*(_DWORD *)(a1 + 360) - (int)v35) / 10000,
                        (__int64)&v55);
                if ( v12 >= 0 )
                {
                  v12 = sub_1800EA888(a1, v55, v44, a4);
                  if ( v12 < 0 )
                  {
                    v49 = (__int64 (__fastcall ***)())qword_180169350;
                    if ( !qword_180169350 )
                    {
                      v50 = MFGetCallStackTracingWeakReference(0, v48);
                      qword_180169350 = v50;
                      if ( v50 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
                      {
                        v49 = (__int64 (__fastcall ***)())qword_180169350;
                      }
                      else
                      {
                        v49 = &off_1801683B0;
                        qword_180169350 = (__int64)&off_1801683B0;
                      }
                    }
                    if ( *((_BYTE *)v49 + 8) )
                    {
                      v51 = sub_180001870(v49);
                      if ( *(_DWORD *)(v51 + 1996) != v12 )
                        sub_18007FDD0(
                          v51,
                          "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver",
                          457,
                          (unsigned int)v12);
                    }
                    if ( byte_1801692C8 )
                    {
                      v16 = 36;
                      goto LABEL_106;
                    }
                  }
                }
                else
                {
                  v45 = (__int64 (__fastcall ***)())qword_180169350;
                  if ( !qword_180169350 )
                  {
                    v46 = MFGetCallStackTracingWeakReference(0, v43);
                    qword_180169350 = v46;
                    if ( v46 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
                    {
                      v45 = (__int64 (__fastcall ***)())qword_180169350;
                    }
                    else
                    {
                      v45 = &off_1801683B0;
                      qword_180169350 = (__int64)&off_1801683B0;
                    }
                  }
                  if ( *((_BYTE *)v45 + 8) )
                  {
                    v47 = sub_180001870(v45);
                    if ( *(_DWORD *)(v47 + 1996) != v12 )
                      sub_18007FDD0(
                        v47,
                        "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver",
                        455,
                        (unsigned int)v12);
                  }
                  if ( byte_1801692C8 )
                  {
                    v16 = 35;
                    goto LABEL_106;
                  }
                }
              }
              else
              {
                v40 = (__int64 (__fastcall ***)())qword_180169350;
                if ( !qword_180169350 )
                {
                  v41 = MFGetCallStackTracingWeakReference(0, v39);
                  qword_180169350 = v41;
                  if ( v41 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
                  {
                    v40 = (__int64 (__fastcall ***)())qword_180169350;
                  }
                  else
                  {
                    v40 = &off_1801683B0;
                    qword_180169350 = (__int64)&off_1801683B0;
                  }
                }
                if ( *((_BYTE *)v40 + 8) )
                {
                  v42 = sub_180001870(v40);
                  if ( *(_DWORD *)(v42 + 1996) != v12 )
                    sub_18007FDD0(
                      v42,
                      "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver",
                      453,
                      (unsigned int)v12);
                }
                if ( byte_1801692C8 )
                {
                  v16 = 34;
                  goto LABEL_106;
                }
              }
            }
            else
            {
              v36 = (__int64 (__fastcall ***)())qword_180169350;
              v12 = -2147418113;
              if ( !qword_180169350 )
              {
                v37 = MFGetCallStackTracingWeakReference(0, v34);
                qword_180169350 = v37;
                if ( v37 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
                {
                  v36 = (__int64 (__fastcall ***)())qword_180169350;
                }
                else
                {
                  v36 = &off_1801683B0;
                  qword_180169350 = (__int64)&off_1801683B0;
                }
              }
              if ( *((_BYTE *)v36 + 8) )
              {
                v38 = sub_180001870(v36);
                if ( *(_DWORD *)(v38 + 1996) != -2147418113 )
                  sub_18007FDD0(v38, "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver", 450, 2147549183LL);
              }
              if ( byte_1801692C8 )
              {
                v16 = 33;
                goto LABEL_106;
              }
            }
          }
          else
          {
            v30 = (__int64 (__fastcall ***)())qword_180169350;
            if ( !qword_180169350 )
            {
              v31 = MFGetCallStackTracingWeakReference(0, v29);
              qword_180169350 = v31;
              if ( v31 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
              {
                v30 = (__int64 (__fastcall ***)())qword_180169350;
              }
              else
              {
                v30 = &off_1801683B0;
                qword_180169350 = (__int64)&off_1801683B0;
              }
            }
            if ( *((_BYTE *)v30 + 8) )
            {
              v32 = sub_180001870(v30);
              if ( *(_DWORD *)(v32 + 1996) != v12 )
                sub_18007FDD0(
                  v32,
                  "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver",
                  439,
                  (unsigned int)v12);
            }
            if ( byte_1801692C8 )
            {
              v16 = 32;
              goto LABEL_106;
            }
          }
        }
      }
      else
      {
        v22 = (__int64 (__fastcall ***)())qword_180169350;
        if ( !qword_180169350 )
        {
          v23 = MFGetCallStackTracingWeakReference(0, v21);
          qword_180169350 = v23;
          if ( v23 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
          {
            v22 = (__int64 (__fastcall ***)())qword_180169350;
          }
          else
          {
            v22 = &off_1801683B0;
            qword_180169350 = (__int64)&off_1801683B0;
          }
        }
        if ( *((_BYTE *)v22 + 8) )
        {
          v24 = sub_180001870(v22);
          if ( *(_DWORD *)(v24 + 1996) != v12 )
            sub_18007FDD0(v24, "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver", 429, (unsigned int)v12);
        }
        if ( byte_1801692C8 )
        {
          v16 = 30;
          goto LABEL_106;
        }
      }
    }
    else
    {
      v18 = (__int64 (__fastcall ***)())qword_180169350;
      if ( !qword_180169350 )
      {
        v19 = MFGetCallStackTracingWeakReference(0, v17);
        qword_180169350 = v19;
        if ( v19 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
        {
          v18 = (__int64 (__fastcall ***)())qword_180169350;
        }
        else
        {
          v18 = &off_1801683B0;
          qword_180169350 = (__int64)&off_1801683B0;
        }
      }
      if ( *((_BYTE *)v18 + 8) )
      {
        v20 = sub_180001870(v18);
        if ( *(_DWORD *)(v20 + 1996) != v12 )
          sub_18007FDD0(v20, "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver", 426, (unsigned int)v12);
      }
      if ( byte_1801692C8 )
      {
        v16 = 29;
        goto LABEL_106;
      }
    }
  }
  else
  {
    v13 = (__int64 (__fastcall ***)())qword_180169350;
    if ( !qword_180169350 )
    {
      v14 = MFGetCallStackTracingWeakReference(0, v11);
      qword_180169350 = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
      {
        v13 = (__int64 (__fastcall ***)())qword_180169350;
      }
      else
      {
        v13 = &off_1801683B0;
        qword_180169350 = (__int64)&off_1801683B0;
      }
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      v15 = sub_180001870(v13);
      if ( *(_DWORD *)(v15 + 1996) != v12 )
        sub_18007FDD0(v15, "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver", 420, (unsigned int)v12);
    }
    if ( byte_1801692C8 )
    {
      v16 = 28;
LABEL_106:
      sub_18004F390(*((_QWORD *)RequestContext + 2), v16, &stru_18015A6F8, a1, v12);
    }
  }
  sub_180005880(v53);
  sub_18005EF9C(&v55);
  sub_180009440(&pvar);
  sub_18005EF9C(v56);
  sub_18005EF9C(&ppv);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800eaed0  push    rbp
0x1800eaed2  push    rbx
0x1800eaed3  push    rsi
0x1800eaed4  push    rdi
0x1800eaed5  push    r12
0x1800eaed7  push    r13
0x1800eaed9  push    r14
0x1800eaedb  push    r15
0x1800eaedd  lea     rbp, [rsp-18h]
0x1800eaee2  sub     rsp, 118h
0x1800eaee9  mov     rax, cs:__security_cookie
0x1800eaef0  xor     rax, rsp
0x1800eaef3  mov     [rbp+50h+var_50], rax
0x1800eaef7  xor     r14d, r14d
0x1800eaefa  lea     rax, aDummyAsf; "dummy.asf"
0x1800eaf01  mov     [rbp+50h+var_B8], rax
0x1800eaf05  lea     rdi, aCmfvideothumbn_4; "CMFVideoThumbnail::CreateAsyncSourceRea"...
0x1800eaf0c  xorps   xmm0, xmm0
0x1800eaf0f  mov     [rsp+150h+ppv], r14
0x1800eaf14  lea     rax, aDummyMp3; "dummy.mp3"
0x1800eaf1b  mov     [rbp+50h+var_C0], r14
0x1800eaf1f  mov     [rbp+50h+var_B0], rax
0x1800eaf23  mov     r13, r8
0x1800eaf26  lea     rax, aDummyMp4; "dummy.mp4"
0x1800eaf2d  mov     qword ptr [rsp+150h+var_F8], r14
0x1800eaf32  mov     [rbp+50h+var_A8], rax
0x1800eaf36  mov     r12, rdx
0x1800eaf39  lea     rax, aDummyAvi; "dummy.avi"
0x1800eaf40  mov     [rsp+150h+var_100], r14
0x1800eaf45  mov     [rbp+50h+var_A0], rax
0x1800eaf49  mov     rsi, rcx
0x1800eaf4c  lea     rax, aDummyM2ts; "dummy.m2ts"
0x1800eaf53  mov     r8d, 1A0h
0x1800eaf59  mov     [rbp+50h+var_98], rax
0x1800eaf5d  lea     rcx, [rsp+150h+var_110]
0x1800eaf62  lea     rax, aDummyWav; "dummy.wav"
0x1800eaf69  mov     rdx, rdi
0x1800eaf6c  mov     [rbp+50h+var_90], rax
0x1800eaf70  mov     r15, r9
0x1800eaf73  lea     rax, aDummyAdts; "dummy.adts"
0x1800eaf7a  mov     [rbp+50h+var_88], rax
0x1800eaf7e  lea     rax, aDummyAc3; "dummy.ac3"
0x1800eaf85  mov     [rbp+50h+var_80], rax
0x1800eaf89  lea     rax, aDummyMkv; "dummy.mkv"
0x1800eaf90  mov     [rbp+50h+var_78], rax
0x1800eaf94  lea     rax, aDummyFlac; "dummy.flac"
0x1800eaf9b  mov     [rbp+50h+var_70], rax
0x1800eaf9f  xor     eax, eax
0x1800eafa1  mov     [rsp+150h+var_E0], rax
0x1800eafa6  mov     qword ptr [rbp+50h+pvar+10h], rax
0x1800eafaa  movups  [rsp+150h+var_F0], xmm0
0x1800eafaf  movups  xmmword ptr [rsp+150h+pvar], xmm0
0x1800eafb4  call    sub_18000A580
0x1800eafb9  mov     rcx, cs:qword_180169350
0x1800eafc0  cmp     [rcx+8], r14b
0x1800eafc4  jz      short loc_1800EB023
0x1800eafc6  cmp     [rsi+190h], r14
0x1800eafcd  jz      short loc_1800EB023
0x1800eafcf  call    sub_180001870
0x1800eafd4  mov     rcx, [rsi+190h]
0x1800eafdb  mov     rdi, rax
0x1800eafde  mov     rdx, [rcx]
0x1800eafe1  mov     rax, [rdx+128h]
0x1800eafe8  call    cs:__guard_dispatch_icall_fptr
0x1800eafee  mov     rcx, [rsi+190h]
0x1800eaff5  mov     ebx, eax
0x1800eaff7  mov     rdx, [rcx]
0x1800eaffa  mov     rax, [rdx+118h]
0x1800eb001  lea     rdx, [rbp+50h+var_60]
0x1800eb005  call    cs:__guard_dispatch_icall_fptr
0x1800eb00b  movups  xmm0, xmmword ptr [rax]
0x1800eb00e  mov     [rdi+7E0h], ebx
0x1800eb014  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800eb01c  lea     rdi, aCmfvideothumbn_4; "CMFVideoThumbnail::CreateAsyncSourceRea"...
0x1800eb023  lea     rcx, [rsp+150h+ppv]
0x1800eb028  mov     [r15], r14
0x1800eb02b  call    sub_18005EF9C
0x1800eb030  lea     rdx, [rsp+150h+ppv]; ppv
0x1800eb035  lea     rcx, stru_18014F050; riid
0x1800eb03c  call    cs:PSCreateMemoryPropertyStore
0x1800eb042  mov     ebx, eax
0x1800eb044  test    eax, eax
0x1800eb046  jns     loc_1800EB0D8
0x1800eb04c  mov     rcx, cs:qword_180169350
0x1800eb053  test    rcx, rcx
0x1800eb056  jnz     short loc_1800EB09A
0x1800eb058  call    cs:MFGetCallStackTracingWeakReference
0x1800eb05e  mov     cs:qword_180169350, rax
0x1800eb065  mov     rcx, rax
0x1800eb068  test    rax, rax
0x1800eb06b  jz      short loc_1800EB08C
0x1800eb06d  mov     rax, [rax]
0x1800eb070  mov     edx, 7F0h
0x1800eb075  mov     rax, [rax+8]
0x1800eb079  call    cs:__guard_dispatch_icall_fptr
0x1800eb07f  test    eax, eax
0x1800eb081  jz      short loc_1800EB08C
0x1800eb083  mov     rcx, cs:qword_180169350
0x1800eb08a  jmp     short loc_1800EB09A
0x1800eb08c  lea     rcx, off_1801683B0
0x1800eb093  mov     cs:qword_180169350, rcx
0x1800eb09a  cmp     [rcx+8], r14b
0x1800eb09e  jz      short loc_1800EB0C1
0x1800eb0a0  call    sub_180001870
0x1800eb0a5  cmp     [rax+7CCh], ebx
0x1800eb0ab  jz      short loc_1800EB0C1
0x1800eb0ad  mov     r9d, ebx
0x1800eb0b0  mov     r8d, 1A4h
0x1800eb0b6  mov     rdx, rdi
0x1800eb0b9  mov     rcx, rax
0x1800eb0bc  call    sub_18007FDD0
0x1800eb0c1  cmp     cs:byte_1801692C8, 1
0x1800eb0c8  jb      loc_1800EB6FC
0x1800eb0ce  mov     edx, 1Ch
0x1800eb0d3  jmp     loc_1800EB6DE
0x1800eb0d8  mov     rcx, [rsp+150h+ppv]
0x1800eb0dd  lea     r8, [rsp+150h+var_F0]
0x1800eb0e2  mov     eax, 0Bh
0x1800eb0e7  lea     rdx, qword_180151350
0x1800eb0ee  mov     word ptr [rsp+150h+var_F0], ax
0x1800eb0f3  or      eax, 0FFFFFFFFh
0x1800eb0f6  mov     word ptr [rsp+150h+var_F0+8], ax
0x1800eb0fb  mov     rax, [rcx]
0x1800eb0fe  mov     rax, [rax+30h]
0x1800eb102  call    cs:__guard_dispatch_icall_fptr
0x1800eb108  mov     ebx, eax
0x1800eb10a  test    eax, eax
0x1800eb10c  jns     loc_1800EB19E
0x1800eb112  mov     rcx, cs:qword_180169350
0x1800eb119  test    rcx, rcx
0x1800eb11c  jnz     short loc_1800EB160
0x1800eb11e  call    cs:MFGetCallStackTracingWeakReference
0x1800eb124  mov     cs:qword_180169350, rax
0x1800eb12b  mov     rcx, rax
0x1800eb12e  test    rax, rax
0x1800eb131  jz      short loc_1800EB152
0x1800eb133  mov     rax, [rax]
0x1800eb136  mov     edx, 7F0h
0x1800eb13b  mov     rax, [rax+8]
0x1800eb13f  call    cs:__guard_dispatch_icall_fptr
0x1800eb145  test    eax, eax
0x1800eb147  jz      short loc_1800EB152
0x1800eb149  mov     rcx, cs:qword_180169350
0x1800eb150  jmp     short loc_1800EB160
0x1800eb152  lea     rcx, off_1801683B0
0x1800eb159  mov     cs:qword_180169350, rcx
0x1800eb160  cmp     [rcx+8], r14b
0x1800eb164  jz      short loc_1800EB187
0x1800eb166  call    sub_180001870
0x1800eb16b  cmp     [rax+7CCh], ebx
0x1800eb171  jz      short loc_1800EB187
0x1800eb173  mov     r9d, ebx
0x1800eb176  mov     r8d, 1AAh
0x1800eb17c  mov     rdx, rdi
0x1800eb17f  mov     rcx, rax
0x1800eb182  call    sub_18007FDD0
0x1800eb187  cmp     cs:byte_1801692C8, 1
0x1800eb18e  jb      loc_1800EB6FC
0x1800eb194  mov     edx, 1Dh
0x1800eb199  jmp     loc_1800EB6DE
0x1800eb19e  mov     rcx, [rsp+150h+ppv]
0x1800eb1a3  lea     r8, [rsp+150h+var_F0]
0x1800eb1a8  lea     rdx, qword_18015A720
0x1800eb1af  mov     rax, [rcx]
0x1800eb1b2  mov     rax, [rax+30h]
0x1800eb1b6  call    cs:__guard_dispatch_icall_fptr
0x1800eb1bc  mov     ebx, eax
0x1800eb1be  test    eax, eax
0x1800eb1c0  jns     loc_1800EB252
0x1800eb1c6  mov     rcx, cs:qword_180169350
0x1800eb1cd  test    rcx, rcx
0x1800eb1d0  jnz     short loc_1800EB214
0x1800eb1d2  call    cs:MFGetCallStackTracingWeakReference
0x1800eb1d8  mov     cs:qword_180169350, rax
0x1800eb1df  mov     rcx, rax
0x1800eb1e2  test    rax, rax
0x1800eb1e5  jz      short loc_1800EB206
0x1800eb1e7  mov     rax, [rax]
0x1800eb1ea  mov     edx, 7F0h
0x1800eb1ef  mov     rax, [rax+8]
0x1800eb1f3  call    cs:__guard_dispatch_icall_fptr
0x1800eb1f9  test    eax, eax
0x1800eb1fb  jz      short loc_1800EB206
0x1800eb1fd  mov     rcx, cs:qword_180169350
0x1800eb204  jmp     short loc_1800EB214
0x1800eb206  lea     rcx, off_1801683B0
0x1800eb20d  mov     cs:qword_180169350, rcx
0x1800eb214  cmp     [rcx+8], r14b
0x1800eb218  jz      short loc_1800EB23B
0x1800eb21a  call    sub_180001870
0x1800eb21f  cmp     [rax+7CCh], ebx
0x1800eb225  jz      short loc_1800EB23B
0x1800eb227  mov     r9d, ebx
0x1800eb22a  mov     r8d, 1ADh
0x1800eb230  mov     rdx, rdi
0x1800eb233  mov     rcx, rax
0x1800eb236  call    sub_18007FDD0
0x1800eb23b  cmp     cs:byte_1801692C8, 1
0x1800eb242  jb      loc_1800EB6FC
0x1800eb248  mov     edx, 1Eh
0x1800eb24d  jmp     loc_1800EB6DE
0x1800eb252  cmp     dword ptr [rsi+1Ch], 5
0x1800eb256  jnz     loc_1800EB310
0x1800eb25c  mov     rcx, [rsp+150h+ppv]
0x1800eb261  lea     r8, [rsp+150h+var_F0]
0x1800eb266  lea     rdx, qword_18015A708
0x1800eb26d  mov     rax, [rcx]
0x1800eb270  mov     rax, [rax+30h]
0x1800eb274  call    cs:__guard_dispatch_icall_fptr
0x1800eb27a  mov     ebx, eax
0x1800eb27c  test    eax, eax
0x1800eb27e  jns     loc_1800EB310
0x1800eb284  mov     rcx, cs:qword_180169350
0x1800eb28b  test    rcx, rcx
0x1800eb28e  jnz     short loc_1800EB2D2
0x1800eb290  call    cs:MFGetCallStackTracingWeakReference
0x1800eb296  mov     cs:qword_180169350, rax
0x1800eb29d  mov     rcx, rax
0x1800eb2a0  test    rax, rax
0x1800eb2a3  jz      short loc_1800EB2C4
0x1800eb2a5  mov     rax, [rax]
0x1800eb2a8  mov     edx, 7F0h
0x1800eb2ad  mov     rax, [rax+8]
0x1800eb2b1  call    cs:__guard_dispatch_icall_fptr
0x1800eb2b7  test    eax, eax
0x1800eb2b9  jz      short loc_1800EB2C4
0x1800eb2bb  mov     rcx, cs:qword_180169350
0x1800eb2c2  jmp     short loc_1800EB2D2
0x1800eb2c4  lea     rcx, off_1801683B0
0x1800eb2cb  mov     cs:qword_180169350, rcx
0x1800eb2d2  cmp     [rcx+8], r14b
0x1800eb2d6  jz      short loc_1800EB2F9
0x1800eb2d8  call    sub_180001870
0x1800eb2dd  cmp     [rax+7CCh], ebx
0x1800eb2e3  jz      short loc_1800EB2F9
0x1800eb2e5  mov     r9d, ebx
0x1800eb2e8  mov     r8d, 1B2h
0x1800eb2ee  mov     rdx, rdi
0x1800eb2f1  mov     rcx, rax
0x1800eb2f4  call    sub_18007FDD0
0x1800eb2f9  cmp     cs:byte_1801692C8, 1
0x1800eb300  jb      loc_1800EB6FC
0x1800eb306  mov     edx, 1Fh
0x1800eb30b  jmp     loc_1800EB6DE
0x1800eb310  mov     rdx, [rsi+190h]
0x1800eb317  lea     rcx, [rsp+150h+pvar]
0x1800eb31c  call    sub_1800D7188
0x1800eb321  mov     rcx, [rsp+150h+ppv]
0x1800eb326  lea     r8, [rsp+150h+pvar]
0x1800eb32b  lea     rdx, qword_18014E870
0x1800eb332  mov     rax, [rcx]
0x1800eb335  mov     rax, [rax+30h]
0x1800eb339  call    cs:__guard_dispatch_icall_fptr
0x1800eb33f  mov     ebx, eax
0x1800eb341  test    eax, eax
0x1800eb343  jns     loc_1800EB3D5
0x1800eb349  mov     rcx, cs:qword_180169350
0x1800eb350  test    rcx, rcx
0x1800eb353  jnz     short loc_1800EB397
0x1800eb355  call    cs:MFGetCallStackTracingWeakReference
0x1800eb35b  mov     cs:qword_180169350, rax
0x1800eb362  mov     rcx, rax
0x1800eb365  test    rax, rax
0x1800eb368  jz      short loc_1800EB389
0x1800eb36a  mov     rax, [rax]
0x1800eb36d  mov     edx, 7F0h
0x1800eb372  mov     rax, [rax+8]
0x1800eb376  call    cs:__guard_dispatch_icall_fptr
0x1800eb37c  test    eax, eax
0x1800eb37e  jz      short loc_1800EB389
0x1800eb380  mov     rcx, cs:qword_180169350
0x1800eb387  jmp     short loc_1800EB397
0x1800eb389  lea     rcx, off_1801683B0
0x1800eb390  mov     cs:qword_180169350, rcx
0x1800eb397  cmp     [rcx+8], r14b
0x1800eb39b  jz      short loc_1800EB3BE
0x1800eb39d  call    sub_180001870
0x1800eb3a2  cmp     [rax+7CCh], ebx
0x1800eb3a8  jz      short loc_1800EB3BE
0x1800eb3aa  mov     r9d, ebx
0x1800eb3ad  mov     r8d, 1B7h
0x1800eb3b3  mov     rdx, rdi
0x1800eb3b6  mov     rcx, rax
0x1800eb3b9  call    sub_18007FDD0
0x1800eb3be  cmp     cs:byte_1801692C8, 1
0x1800eb3c5  jb      loc_1800EB6FC
0x1800eb3cb  mov     edx, 20h ; ' '
0x1800eb3d0  jmp     loc_1800EB6DE
0x1800eb3d5  cmp     dword ptr [rsi+1Ch], 0Bh
0x1800eb3d9  mov     rdi, r14
0x1800eb3dc  jnb     short loc_1800EB3E7
0x1800eb3de  movsxd  rax, dword ptr [rsi+1Ch]
0x1800eb3e2  mov     rdi, [rbp+rax*8+50h+var_C0]
0x1800eb3e7  mov     rcx, rsi
0x1800eb3ea  call    sub_1800EC4CC
0x1800eb3ef  mov     r14, rax
0x1800eb3f2  cmp     rax, [rsi+168h]
0x1800eb3f9  jl      loc_1800EB494
0x1800eb3ff  mov     rcx, cs:qword_180169350
0x1800eb406  mov     ebx, 8000FFFFh
  ... truncated ...
```
