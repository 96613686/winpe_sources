# CRunEvict::RunOperation(void)

- ea: `0x18000d740`
- end: `0x18000e108`
- name: `?RunOperation@CRunEvict@@UEAAJXZ`
- size: `2504`
- prototype: `__int64 __fastcall(CRunEvict *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18000c644`
- `0x18000c794`
- `0x18000c848`
- `0x18000d740`
- `0x180031a5c`
- `0x180038c3c`
- `0x180046494`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ded2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ded2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ddc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e095`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ddc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e095`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall CRunEvict::RunOperation(CRunEvict *this)
{
  unsigned int v2; // r13d
  struct IVolume *v3; // rdi
  __int128 v4; // xmm6
  int v5; // ebx
  __int16 v6; // ax
  char *v7; // r15
  struct IFreeSpaceManager *v8; // rcx
  __int64 (__fastcall *v9)(struct IVolume *, __int64, __int64 *); // rbx
  __int64 v10; // rcx
  struct IFreeSpaceManager *v11; // rcx
  struct IFileOperation *v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 (__fastcall *v17)(struct IVolume *, __int64, __int64 *); // rbx
  __int64 v18; // rcx
  __int64 (__fastcall *v19)(struct IVolume *, _QWORD, __int64 *); // rbx
  __int64 v20; // rcx
  unsigned int *v21; // r14
  unsigned int v22; // r12d
  __int64 (__fastcall *v23)(struct IVolume *, _QWORD, struct IFileOperation *, struct IFileOperation **); // rax
  bool v24; // sf
  unsigned __int64 v25; // r15
  CSxGlobalTracer *v26; // rcx
  unsigned int v27; // ebx
  __int16 v28; // ax
  __int64 (__fastcall *v29)(struct IVolume *, _QWORD, struct IFileOperation *, struct IFileOperation **); // rax
  void *v30; // rcx
  int v31; // eax
  unsigned int *v32; // rax
  void *v33; // rcx
  int v34; // [rsp+38h] [rbp-99h] BYREF
  __int16 v35; // [rsp+3Ch] [rbp-95h]
  __int16 v36; // [rsp+3Eh] [rbp-93h]
  struct IFileOperation *v37; // [rsp+70h] [rbp-61h] BYREF
  struct IFreeSpaceManager *v38; // [rsp+78h] [rbp-59h] BYREF
  __int64 v39; // [rsp+80h] [rbp-51h] BYREF
  __int64 v40; // [rsp+88h] [rbp-49h] BYREF
  __int64 v41; // [rsp+90h] [rbp-41h] BYREF
  unsigned int v42; // [rsp+98h] [rbp-39h] BYREF
  unsigned int v43; // [rsp+9Ch] [rbp-35h]
  int v44; // [rsp+A0h] [rbp-31h] BYREF
  int v45; // [rsp+A4h] [rbp-2Dh] BYREF
  _DWORD v46[4]; // [rsp+A8h] [rbp-29h] BYREF
  __int128 v47; // [rsp+B8h] [rbp-19h] BYREF
  struct IVolume *v48; // [rsp+C8h] [rbp-9h]
  unsigned int v49; // [rsp+138h] [rbp+67h] BYREF
  int v50; // [rsp+140h] [rbp+6Fh] BYREF
  int v51; // [rsp+148h] [rbp+77h] BYREF
  int v52; // [rsp+150h] [rbp+7Fh] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v34, "CRunEvict::RunOperation", 80, 1);
  v2 = 0;
  v48 = 0;
  v39 = 0;
  v41 = 0;
  v40 = 0;
  v37 = 0;
  v38 = 0;
  v49 = 0;
  v52 = 0;
  v42 = 0;
  v51 = 0;
  v46[0] = 0;
  v45 = 0;
  v50 = 0;
  v44 = 0;
  v3 = (struct IVolume *)*((_QWORD *)this + 93);
  if ( v3 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v3 + 8LL))(*((_QWORD *)this + 93));
  v48 = v3;
  if ( v3 )
  {
    v4 = *(_OWORD *)((char *)this + 760);
    v5 = (*(__int64 (__fastcall **)(struct IVolume *, _DWORD *, int *, int *, int *))(*(_QWORD *)v3 + 192LL))(
           v3,
           v46,
           &v45,
           &v50,
           &v44);
    v34 = v5;
    v6 = 117;
    if ( v5 >= 0 )
    {
      v35 = 117;
      v7 = (char *)this + 56;
      v5 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 6) + 24LL))(
             *((_QWORD *)this + 6),
             (char *)this + 56);
      v34 = v5;
      v6 = 120;
      if ( v5 >= 0 )
      {
        v35 = 120;
        v8 = v38;
        if ( v38 )
        {
          v38 = 0;
          (*(void (__fastcall **)(struct IFreeSpaceManager *))(*(_QWORD *)v8 + 16LL))(v8);
        }
        v5 = CFreeSpaceManager::CreateInstance(*((unsigned __int16 **)this + 87), *((_QWORD *)this + 18), &v38);
        v34 = v5;
        v6 = 124;
        if ( v5 >= 0 )
        {
          v35 = 124;
          if ( v50 && *((_DWORD *)this + 194) )
          {
            *(_QWORD *)&v47 = *((_QWORD *)this + 22);
            *((_QWORD *)&v47 + 1) = *((_QWORD *)this + 21);
            v5 = (*(__int64 (__fastcall **)(struct IFreeSpaceManager *, __int128 *))(*(_QWORD *)v38 + 48LL))(v38, &v47);
            v34 = v5;
            v6 = 131;
            if ( v5 < 0 )
              goto LABEL_13;
            v35 = 131;
          }
          v9 = *(__int64 (__fastcall **)(struct IVolume *, __int64, __int64 *))(*(_QWORD *)v3 + 104LL);
          v10 = v41;
          if ( v41 )
          {
            v41 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
          }
          v5 = v9(v3, 1, &v41);
          v34 = v5;
          v6 = 135;
          if ( v5 >= 0 )
          {
            v35 = 135;
            v17 = *(__int64 (__fastcall **)(struct IVolume *, __int64, __int64 *))(*(_QWORD *)v3 + 104LL);
            v18 = v40;
            if ( v40 )
            {
              v40 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
            }
            v5 = v17(v3, 2, &v40);
            v34 = v5;
            v6 = 136;
            if ( v5 >= 0 )
            {
              v35 = 136;
              v19 = *(__int64 (__fastcall **)(struct IVolume *, _QWORD, __int64 *))(*(_QWORD *)v3 + 104LL);
              v20 = v39;
              if ( v39 )
              {
                v39 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
              }
              v5 = v19(v3, 0, &v39);
              v34 = v5;
              v6 = 137;
              if ( v5 >= 0 )
              {
                v35 = 137;
                v5 = CDefragOperation::_SetPhase(this, 6u);
                v34 = v5;
                v6 = 140;
                if ( v5 >= 0 )
                {
                  v35 = 140;
                  (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v39 + 64LL))(v39, &v42);
                  CDefragOperation::_SetPercentComplete(this, 0);
                  v47 = v4;
                  v5 = (*(__int64 (__fastcall **)(struct IFreeSpaceManager *, __int128 *))(*(_QWORD *)v38 + 48LL))(
                         v38,
                         &v47);
                  v34 = v5;
                  v6 = 150;
                  if ( v5 >= 0 )
                  {
                    v35 = 150;
                    v5 = (*(__int64 (__fastcall **)(struct IFreeSpaceManager *))(*(_QWORD *)v38 + 24LL))(v38);
                    v34 = v5;
                    v6 = 151;
                    if ( v5 >= 0 )
                    {
                      v35 = 151;
                      v5 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v39 + 48LL))(v39, &v49);
                      v34 = v5;
                      v6 = 153;
                      if ( v5 >= 0 )
                      {
                        v21 = 0;
                        v43 = 0;
                        v22 = 0;
                        while ( 1 )
                        {
                          v35 = v6;
                          if ( v5 == 1 )
                          {
                            v26 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
                              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
                            {
                              WPP_SF_d(
                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                12,
                                WPP_845e7f8dcfba3c8575de3c2677da84f0_Traceguids,
                                v22);
                              v26 = WPP_GLOBAL_Control;
                            }
                            v27 = 0;
                            while ( v21 )
                            {
                              v34 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v39 + 32LL))(v39, *v21);
                              v28 = 253;
                              if ( v34 < 0 )
                                goto LABEL_89;
                              v35 = 253;
                              if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
                                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
                              {
                                WPP_SF_(
                                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                                  13,
                                  WPP_845e7f8dcfba3c8575de3c2677da84f0_Traceguids);
                              }
                              v29 = *(__int64 (__fastcall **)(struct IVolume *, _QWORD, struct IFileOperation *, struct IFileOperation **))(*(_QWORD *)v3 + 56LL);
                              if ( v37 )
                              {
                                v34 = v29(v3, *v21, v37, 0);
                                if ( v34 < 0 )
                                {
                                  v36 = 261;
                                  goto LABEL_102;
                                }
                                v35 = 261;
                              }
                              else
                              {
                                v34 = v29(v3, *v21, 0, &v37);
                                if ( v34 < 0 )
                                {
                                  v36 = 265;
                                  goto LABEL_102;
                                }
                                v35 = 265;
                              }
                              v34 = ((__int64 (__fastcall *)(struct IFileOperation *, struct IVolume *))v37->lpVtbl->DeleteItem)(
                                      v37,
                                      v3);
                              v28 = 269;
                              if ( v34 < 0 )
                                goto LABEL_89;
                              v35 = 269;
                              v34 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v40 + 32LL))(v40, *v21);
                              v28 = 272;
                              if ( v34 < 0
                                || (v35 = 272,
                                    v34 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v41 + 32LL))(
                                            v41,
                                            *v21),
                                    v28 = 273,
                                    v34 < 0)
                                || (v35 = 273,
                                    v34 = (*(__int64 (__fastcall **)(struct IVolume *, _QWORD))(*(_QWORD *)v3 + 152LL))(
                                            v3,
                                            *v21),
                                    v28 = 276,
                                    v34 < 0) )
                              {
LABEL_89:
                                v36 = v28;
                                goto LABEL_102;
                              }
                              ++v27;
                              v30 = v21;
                              v35 = 276;
                              v21 = (unsigned int *)*((_QWORD *)v21 + 1);
                              CoTaskMemFree(v30);
                              v26 = WPP_GLOBAL_Control;
                            }
                            if ( v26 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v26 + 7) & 0x400000) != 0 )
                              WPP_SF_d(*((_QWORD *)v26 + 2), 14, WPP_845e7f8dcfba3c8575de3c2677da84f0_Traceguids, v27);
                            v5 = CDefragOperation::_SetPercentComplete(this, 0x64u);
                            v34 = v5;
                            v6 = 285;
                            if ( v5 >= 0 )
                            {
                              v35 = 285;
                              v5 = 0;
                              goto LABEL_109;
                            }
                            goto LABEL_13;
                          }
                          v23 = *(__int64 (__fastcall **)(struct IVolume *, _QWORD, struct IFileOperation *, struct IFileOperation **))(*(_QWORD *)v3 + 56LL);
                          if ( v37 )
                          {
                            v5 = v23(v3, v49, v37, 0);
                            v34 = v5;
                            v24 = v5 < 0;
                            v6 = 158;
                          }
                          else
                          {
                            v5 = v23(v3, v49, 0, &v37);
                            v34 = v5;
                            v24 = v5 < 0;
                            v6 = 162;
                          }
                          if ( v24 )
                            goto LABEL_81;
                          v35 = v6;
                          v5 = ((__int64 (__fastcall *)(struct IFileOperation *, __int64, int *))v37->lpVtbl->SetProperties)(
                                 v37,
                                 32,
                                 &v51);
                          v34 = v5;
                          v6 = 165;
                          if ( v5 < 0 )
                            goto LABEL_81;
                          v35 = 165;
                          if ( !v51 || *((_DWORD *)this + 194) )
                          {
                            v47 = v4;
                            v5 = ((__int64 (__fastcall *)(struct IFileOperation *, __int128 *, int *))v37->lpVtbl->DeleteItems)(
                                   v37,
                                   &v47,
                                   &v52);
                            v34 = v5;
                            v6 = 171;
                            if ( v5 < 0 )
                              goto LABEL_81;
                            v35 = 171;
                            if ( v52 )
                              break;
                          }
LABEL_46:
                          v5 = (*(__int64 (__fastcall **)(CRunEvict *))(*(_QWORD *)this + 32LL))(this);
                          v34 = v5;
                          v6 = 219;
                          if ( v5 < 0 )
                            goto LABEL_81;
                          ++v2;
                          v35 = 219;
                          if ( v42 )
                          {
                            v25 = 100 * (unsigned __int64)v2 / v42;
                            if ( (unsigned int)v25 > 0x64 )
                              LODWORD(v25) = 100;
                          }
                          else
                          {
                            LODWORD(v25) = 100;
                          }
                          if ( (unsigned int)v25 > v43 )
                          {
                            v5 = CDefragOperation::_SetPercentComplete(this, v25);
                            v34 = v5;
                            v6 = 236;
                            if ( v5 < 0 )
                              goto LABEL_81;
                            v35 = 236;
                            v43 = v25;
                          }
                          v5 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v39 + 56LL))(v39, &v49);
                          v34 = v5;
                          v6 = 240;
                          if ( v5 < 0 )
                            goto LABEL_81;
                          v7 = (char *)this + 56;
                        }
                        if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
                          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
                        {
                          WPP_SF_(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            10,
                            WPP_845e7f8dcfba3c8575de3c2677da84f0_Traceguids);
                        }
                        v31 = CDefragOperation::_Defragment(this, 1, v37, v3, v38, 0);
                        v5 = v31;
                        if ( v31 == -1996488682 )
                        {
                          if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
                            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
                          {
                            WPP_SF_(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              11,
                              WPP_845e7f8dcfba3c8575de3c2677da84f0_Traceguids);
                            ++v22;
LABEL_77:
                            v5 = ((__int64 (__fastcall *)(struct IFileOperation *, struct IVolume *, struct IFreeSpaceManager *, char *))v37->lpVtbl->RenameItems)(
                                   v37,
                                   v3,
                                   v38,
                                   v7);
                            v34 = v5;
                            v6 = 197;
                            if ( v5 < 0 )
                              goto LABEL_81;
                            v35 = 197;
                            if ( v5 == 1 )
                            {
                              v32 = (unsigned int *)CoTaskMemAlloc(0x10u);
                              if ( !v32 )
                              {
                                v5 = -2147024882;
                                v34 = -2147024882;
                                v6 = 204;
LABEL_81:
                                v36 = v6;
                                if ( v21 )
                                {
                                  do
                                  {
LABEL_102:
                                    v33 = v21;
                                    v21 = (unsigned int *)*((_QWORD *)v21 + 1);
                                    CoTaskMemFree(v33);
                                  }
                                  while ( v21 );
                                  v5 = v34;
                                }
                                goto LABEL_14;
                              }
                              v34 = 0;
                              v35 = 204;
                              *v32 = v49;
                              *((_QWORD *)v32 + 1) = v21;
                              v21 = v32;
                            }
                            goto LABEL_46;
                          }
                        }
                        else
                        {
                          v34 = v31;
                          v6 = 184;
                          if ( v5 < 0 )
                            goto LABEL_81;
                          v35 = 184;
                        }
                        ++v22;
                        if ( v5 == 150995204 )
                          goto LABEL_46;
                        goto LABEL_77;
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
LABEL_13:
    v36 = v6;
  }
  else
  {
    v5 = -2147467259;
    v36 = 111;
LABEL_109:
    v34 = v5;
  }
LABEL_14:
  v11 = v38;
  if ( v38 )
  {
    v38 = 0;
    (*(void (__fastcall **)(struct IFreeSpaceManager *))(*(_QWORD *)v11 + 16LL))(v11);
  }
  v12 = v37;
  if ( v37 )
  {
    v37 = 0;
    ((void (__fastcall *)(struct IFileOperation *))v12->lpVtbl->Release)(v12);
  }
  v13 = v40;
  if ( v40 )
  {
    v40 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  v14 = v41;
  if ( v41 )
  {
    v41 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  v15 = v39;
  if ( v39 )
  {
    v39 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  if ( v3 )
    (*(void (__fastcall **)(struct IVolume *))(*(_QWORD *)v3 + 16LL))(v3);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v34);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000d740  mov     rax, rsp
0x18000d743  push    rbp
0x18000d744  push    rbx
0x18000d745  push    rsi
0x18000d746  push    rdi
0x18000d747  push    r12
0x18000d749  push    r13
0x18000d74b  push    r14
0x18000d74d  push    r15
0x18000d74f  lea     rbp, [rax-5Fh]
0x18000d753  sub     rsp, 0E8h
0x18000d75a  movaps  xmmword ptr [rax-58h], xmm6
0x18000d75e  mov     rsi, rcx
0x18000d761  mov     r14d, 1
0x18000d767  mov     r9d, r14d; unsigned __int16
0x18000d76a  lea     r8d, [r14+4Fh]; unsigned __int16
0x18000d76e  lea     rdx, aCrunevictRunop; "CRunEvict::RunOperation"
0x18000d775  lea     rcx, [rsp+120h+var_F0]; this
0x18000d77a  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000d77f  nop
0x18000d780  xor     r13d, r13d
0x18000d783  mov     [rbp+57h+var_60], r13
0x18000d787  mov     [rbp+57h+var_A8], r13
0x18000d78b  mov     [rbp+57h+var_98], r13
0x18000d78f  mov     [rbp+57h+var_A0], r13
0x18000d793  mov     [rbp+57h+var_B8], r13
0x18000d797  mov     [rbp+57h+var_B0], r13
0x18000d79b  mov     [rbp+57h+arg_0], r13d
0x18000d79f  mov     [rbp+57h+arg_18], r13d
0x18000d7a3  mov     [rbp+57h+var_90], r13d
0x18000d7a7  mov     [rbp+57h+arg_10], r13d
0x18000d7ab  mov     [rbp+57h+var_80], r13d
0x18000d7af  mov     [rbp+57h+var_84], r13d
0x18000d7b3  mov     [rbp+57h+arg_8], r13d
0x18000d7b7  mov     [rbp+57h+var_88], r13d
0x18000d7bb  mov     rdi, [rsi+2E8h]
0x18000d7c2  test    rdi, rdi
0x18000d7c5  jz      short loc_18000D7D7
0x18000d7c7  mov     rax, [rdi]
0x18000d7ca  mov     rcx, rdi
0x18000d7cd  mov     rax, [rax+8]
0x18000d7d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7d6  nop
0x18000d7d7  mov     [rbp+57h+var_60], rdi
0x18000d7db  test    rdi, rdi
0x18000d7de  jz      loc_18000DF9B
0x18000d7e4  movups  xmm6, xmmword ptr [rsi+2F8h]
0x18000d7eb  mov     rax, [rdi]
0x18000d7ee  lea     rcx, [rbp+57h+var_88]
0x18000d7f2  mov     [rsp+120h+var_100], rcx
0x18000d7f7  lea     r9, [rbp+57h+arg_8]
0x18000d7fb  lea     r8, [rbp+57h+var_84]
0x18000d7ff  lea     rdx, [rbp+57h+var_80]
0x18000d803  mov     rcx, rdi
0x18000d806  mov     rax, [rax+0C0h]
0x18000d80d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d812  mov     ebx, eax
0x18000d814  mov     [rsp+120h+var_F0], eax
0x18000d818  test    eax, eax
0x18000d81a  mov     eax, 75h ; 'u'
0x18000d81f  js      loc_18000D8EE
0x18000d825  mov     [rsp+120h+var_EC], ax
0x18000d82a  mov     rcx, [rsi+30h]
0x18000d82e  lea     r15, [rsi+38h]
0x18000d832  mov     rax, [rcx]
0x18000d835  mov     rdx, r15
0x18000d838  mov     rax, [rax+18h]
0x18000d83c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d841  mov     ebx, eax
0x18000d843  mov     [rsp+120h+var_F0], eax
0x18000d847  test    eax, eax
0x18000d849  mov     eax, 78h ; 'x'
0x18000d84e  js      loc_18000D8EE
0x18000d854  mov     [rsp+120h+var_EC], ax
0x18000d859  mov     rcx, [rbp+57h+var_B0]
0x18000d85d  test    rcx, rcx
0x18000d860  jz      short loc_18000D873
0x18000d862  mov     [rbp+57h+var_B0], r13
0x18000d866  mov     rax, [rcx]
0x18000d869  mov     rax, [rax+10h]
0x18000d86d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d872  nop
0x18000d873  lea     r8, [rbp+57h+var_B0]; struct IFreeSpaceManager **
0x18000d877  mov     rdx, [rsi+90h]; unsigned __int64
0x18000d87e  mov     rcx, [rsi+2B8h]; unsigned __int16 *
0x18000d885  call    ?CreateInstance@CFreeSpaceManager@@SAJPEAG_KPEAPEAUIFreeSpaceManager@@@Z; CFreeSpaceManager::CreateInstance(ushort *,unsigned __int64,IFreeSpaceManager * *)
0x18000d88a  mov     ebx, eax
0x18000d88c  mov     [rsp+120h+var_F0], eax
0x18000d890  test    eax, eax
0x18000d892  mov     eax, 7Ch ; '|'
0x18000d897  js      short loc_18000D8EE
0x18000d899  mov     [rsp+120h+var_EC], ax
0x18000d89e  cmp     [rbp+57h+arg_8], r13d
0x18000d8a2  jnz     loc_18000DFAF
0x18000d8a8  mov     rax, [rdi]
0x18000d8ab  mov     rbx, [rax+68h]
0x18000d8af  mov     rcx, [rbp+57h+var_98]
0x18000d8b3  test    rcx, rcx
0x18000d8b6  jz      short loc_18000D8C9
0x18000d8b8  mov     [rbp+57h+var_98], r13
0x18000d8bc  mov     rdx, [rcx]
0x18000d8bf  mov     rax, [rdx+10h]
0x18000d8c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8c8  nop
0x18000d8c9  lea     r8, [rbp+57h+var_98]
0x18000d8cd  mov     edx, r14d
0x18000d8d0  mov     rcx, rdi
0x18000d8d3  mov     rax, rbx
0x18000d8d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8db  mov     ebx, eax
0x18000d8dd  mov     [rsp+120h+var_F0], eax
0x18000d8e1  test    eax, eax
0x18000d8e3  mov     eax, 87h
0x18000d8e8  jns     loc_18000D9B2
0x18000d8ee  mov     [rsp+120h+var_EA], ax
0x18000d8f3  mov     rcx, [rbp+57h+var_B0]
0x18000d8f7  test    rcx, rcx
0x18000d8fa  jz      short loc_18000D90D
0x18000d8fc  mov     [rbp+57h+var_B0], r13
0x18000d900  mov     rax, [rcx]
0x18000d903  mov     rax, [rax+10h]
0x18000d907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d90c  nop
0x18000d90d  mov     rcx, [rbp+57h+var_B8]
0x18000d911  test    rcx, rcx
0x18000d914  jz      short loc_18000D927
0x18000d916  mov     [rbp+57h+var_B8], r13
0x18000d91a  mov     rax, [rcx]
0x18000d91d  mov     rax, [rax+10h]
0x18000d921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d926  nop
0x18000d927  mov     rcx, [rbp+57h+var_A0]
0x18000d92b  test    rcx, rcx
0x18000d92e  jz      short loc_18000D941
0x18000d930  mov     [rbp+57h+var_A0], r13
0x18000d934  mov     rax, [rcx]
0x18000d937  mov     rax, [rax+10h]
0x18000d93b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d940  nop
0x18000d941  mov     rcx, [rbp+57h+var_98]
0x18000d945  test    rcx, rcx
0x18000d948  jz      short loc_18000D95B
0x18000d94a  mov     [rbp+57h+var_98], r13
0x18000d94e  mov     rax, [rcx]
0x18000d951  mov     rax, [rax+10h]
0x18000d955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d95a  nop
0x18000d95b  mov     rcx, [rbp+57h+var_A8]
0x18000d95f  test    rcx, rcx
0x18000d962  jz      short loc_18000D975
0x18000d964  mov     [rbp+57h+var_A8], r13
0x18000d968  mov     rax, [rcx]
0x18000d96b  mov     rax, [rax+10h]
0x18000d96f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d974  nop
0x18000d975  test    rdi, rdi
0x18000d978  jz      short loc_18000D98A
0x18000d97a  mov     rdx, [rdi]
0x18000d97d  mov     rcx, rdi
0x18000d980  mov     rax, [rdx+10h]
0x18000d984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d989  nop
0x18000d98a  lea     rcx, [rsp+120h+var_F0]; this
0x18000d98f  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000d994  mov     eax, ebx
0x18000d996  movaps  xmm6, [rsp+120h+var_58+8]
0x18000d99e  add     rsp, 0E8h
0x18000d9a5  pop     r15
0x18000d9a7  pop     r14
0x18000d9a9  pop     r13
0x18000d9ab  pop     r12
0x18000d9ad  pop     rdi
0x18000d9ae  pop     rsi
0x18000d9af  pop     rbx
0x18000d9b0  pop     rbp
0x18000d9b1  retn
0x18000d9b2  mov     [rsp+120h+var_EC], ax
0x18000d9b7  mov     rax, [rdi]
0x18000d9ba  mov     rbx, [rax+68h]
0x18000d9be  mov     rcx, [rbp+57h+var_A0]
0x18000d9c2  test    rcx, rcx
0x18000d9c5  jz      short loc_18000D9D8
0x18000d9c7  mov     [rbp+57h+var_A0], r13
0x18000d9cb  mov     rdx, [rcx]
0x18000d9ce  mov     rax, [rdx+10h]
0x18000d9d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9d7  nop
0x18000d9d8  lea     r8, [rbp+57h+var_A0]
0x18000d9dc  mov     edx, 2
0x18000d9e1  mov     rcx, rdi
0x18000d9e4  mov     rax, rbx
0x18000d9e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9ec  mov     ebx, eax
0x18000d9ee  mov     [rsp+120h+var_F0], eax
0x18000d9f2  test    eax, eax
0x18000d9f4  mov     eax, 88h
0x18000d9f9  js      loc_18000D8EE
0x18000d9ff  mov     [rsp+120h+var_EC], ax
0x18000da04  mov     rax, [rdi]
0x18000da07  mov     rbx, [rax+68h]
0x18000da0b  mov     rcx, [rbp+57h+var_A8]
0x18000da0f  test    rcx, rcx
0x18000da12  jz      short loc_18000DA25
0x18000da14  mov     [rbp+57h+var_A8], r13
0x18000da18  mov     rdx, [rcx]
0x18000da1b  mov     rax, [rdx+10h]
0x18000da1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da24  nop
0x18000da25  lea     r8, [rbp+57h+var_A8]
0x18000da29  xor     edx, edx
0x18000da2b  mov     rcx, rdi
0x18000da2e  mov     rax, rbx
0x18000da31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da36  mov     ebx, eax
0x18000da38  mov     [rsp+120h+var_F0], eax
0x18000da3c  test    eax, eax
0x18000da3e  mov     eax, 89h
0x18000da43  js      loc_18000D8EE
0x18000da49  mov     [rsp+120h+var_EC], ax
0x18000da4e  mov     edx, 6
0x18000da53  mov     rcx, rsi
0x18000da56  call    ?_SetPhase@CDefragOperation@@IEAAJW4__MIDL___MIDL_itf_dfengine_0000_0000_0001@@@Z; CDefragOperation::_SetPhase(__MIDL___MIDL_itf_dfengine_0000_0000_0001)
0x18000da5b  mov     ebx, eax
0x18000da5d  mov     [rsp+120h+var_F0], eax
0x18000da61  test    eax, eax
0x18000da63  mov     eax, 8Ch
0x18000da68  js      loc_18000D8EE
0x18000da6e  mov     [rsp+120h+var_EC], ax
0x18000da73  mov     rcx, [rbp+57h+var_A8]
0x18000da77  mov     rax, [rcx]
0x18000da7a  lea     rdx, [rbp+57h+var_90]
0x18000da7e  mov     rax, [rax+40h]
0x18000da82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da87  xor     edx, edx; unsigned int
0x18000da89  mov     rcx, rsi; this
0x18000da8c  call    ?_SetPercentComplete@CDefragOperation@@IEAAJK@Z; CDefragOperation::_SetPercentComplete(ulong)
0x18000da91  mov     rcx, [rbp+57h+var_B0]
0x18000da95  movdqa  [rbp+57h+var_70], xmm6
0x18000da9a  mov     rax, [rcx]
0x18000da9d  lea     rdx, [rbp+57h+var_70]
0x18000daa1  mov     rax, [rax+30h]
0x18000daa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000daaa  mov     ebx, eax
0x18000daac  mov     [rsp+120h+var_F0], eax
0x18000dab0  test    eax, eax
0x18000dab2  mov     eax, 96h
0x18000dab7  js      loc_18000D8EE
0x18000dabd  mov     [rsp+120h+var_EC], ax
0x18000dac2  mov     rcx, [rbp+57h+var_B0]
0x18000dac6  mov     rax, [rcx]
0x18000dac9  mov     rax, [rax+18h]
0x18000dacd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dad2  mov     ebx, eax
0x18000dad4  mov     [rsp+120h+var_F0], eax
0x18000dad8  test    eax, eax
0x18000dada  mov     eax, 97h
0x18000dadf  js      loc_18000D8EE
0x18000dae5  mov     [rsp+120h+var_EC], ax
0x18000daea  mov     rcx, [rbp+57h+var_A8]
0x18000daee  mov     rax, [rcx]
0x18000daf1  lea     rdx, [rbp+57h+arg_0]
0x18000daf5  mov     rax, [rax+30h]
0x18000daf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dafe  mov     ebx, eax
0x18000db00  mov     [rsp+120h+var_F0], eax
0x18000db04  test    eax, eax
0x18000db06  mov     eax, 99h
0x18000db0b  js      loc_18000D8EE
0x18000db11  mov     r14, r13
0x18000db14  mov     [rbp+57h+var_8C], r13d
0x18000db18  mov     r12d, r13d
0x18000db1b  mov     [rsp+120h+var_EC], ax
0x18000db20  cmp     ebx, 1
0x18000db23  jz      loc_18000DC6A
0x18000db29  mov     rax, [rdi]
0x18000db2c  mov     rax, [rax+38h]
0x18000db30  mov     r8, [rbp+57h+var_B8]
0x18000db34  test    r8, r8
0x18000db37  jz      loc_18000DDEF
0x18000db3d  xor     r9d, r9d
0x18000db40  mov     edx, [rbp+57h+arg_0]
0x18000db43  mov     rcx, rdi
0x18000db46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db4b  mov     ebx, eax
0x18000db4d  mov     [rsp+120h+var_F0], eax
0x18000db51  test    eax, eax
0x18000db53  mov     eax, 9Eh
0x18000db58  js      loc_18000DEEF
0x18000db5e  mov     [rsp+120h+var_EC], ax
0x18000db63  mov     rcx, [rbp+57h+var_B8]
0x18000db67  mov     rax, [rcx]
0x18000db6a  lea     r8, [rbp+57h+arg_10]
0x18000db6e  mov     edx, 20h ; ' '
0x18000db73  mov     rax, [rax+40h]
0x18000db77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db7c  mov     ebx, eax
0x18000db7e  mov     [rsp+120h+var_F0], eax
0x18000db82  test    eax, eax
0x18000db84  mov     eax, 0A5h
0x18000db89  js      loc_18000DEEF
  ... truncated ...
```
