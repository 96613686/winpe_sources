# CDataTransferObj::Create(CTxtEdit *,CTxtRange *,long)

- ea: `0x18005a618`
- end: `0x18005abe8`
- name: `?Create@CDataTransferObj@@SAPEAV1@PEAVCTxtEdit@@PEAVCTxtRange@@J@Z`
- size: `1488`
- prototype: `struct CDataTransferObj *__fastcall(CObjectMgr **, struct CTxtRange *, int)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x18006d38c`

## callees

- `0x180022780`
- `0x18003c4f4`
- `0x180040f98`
- `0x1800455c4`
- `0x18005a484`
- `0x18005a618`
- `0x18005afc8`
- `0x18006fb00`
- `0x18008c2dc`
- `0x18008c63c`
- `0x1800910f2`
- `0x180091140`
- `0x1800911d0`
- `0x180092010`

## pseudocode

```c
struct CDataTransferObj *__fastcall CDataTransferObj::Create(CObjectMgr **a1, struct CTxtRange *a2, int a3)
{
  CDataTransferObj *v6; // rax
  CDataTransferObj *v7; // rdi
  int v8; // r10d
  int Range; // eax
  struct COleObject *v10; // r10
  int v11; // r12d
  _QWORD *v12; // rdx
  CObjectMgr *v13; // r14
  int IndexForCp; // ebx
  unsigned int v15; // eax
  _OWORD *v16; // rax
  __int64 v17; // rax
  int v19; // r14d
  unsigned int v20; // r13d
  struct COleObject *ObjectFromCp; // rbx
  int v22; // r12d
  unsigned int (__fastcall ***v23)(_QWORD, GUID *, char *); // r9
  _QWORD *v24; // r15
  void (__fastcall ***v25)(_QWORD, GUID *, int *); // rcx
  __int64 v26; // rcx
  struct tagSIZE v27; // r10
  unsigned int v28; // eax
  _OWORD *v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rcx
  __int64 v37; // rax
  __int64 v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rcx
  int v41; // eax
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rdx
  __int64 v47; // rax
  __int64 v48; // rcx
  __int64 v49; // rax
  __int64 v50; // rcx
  struct tagSIZE v51; // rax
  struct IOleObject **v52; // rsi
  unsigned int *v53; // rbx
  void *ObjectDescriptorDataFromOleObject; // rax
  struct IOleObject *v55; // rdx
  struct IStorage *DataForEmbeddedObject; // rax
  struct IOleObject *v57; // rcx
  struct tagDVTARGETDEVICE *v58; // r9
  int v59; // [rsp+30h] [rbp-D0h] BYREF
  int v60[2]; // [rsp+38h] [rbp-C8h] BYREF
  struct tagSIZE v61; // [rsp+40h] [rbp-C0h] BYREF
  int v62[6]; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD Src[512]; // [rsp+60h] [rbp-A0h] BYREF

  v62[0] = 0;
  v6 = (CDataTransferObj *)CW32System::PvAlloc(0x90u, 0x40u);
  if ( v6 )
  {
    v7 = CDataTransferObj::CDataTransferObj(v6, (struct CTxtEdit *)a1);
    if ( v7 )
    {
      v60[0] = v8;
      v59 = v8;
      Range = CTxtRange::GetRange(a2, v60, &v59);
      v11 = v60[0];
      v12 = a1 + 16;
      *((_DWORD *)v7 + 32) = Range;
      *((_DWORD *)v7 + 33) = v11;
      *((_DWORD *)v7 + 10) = a3;
      if ( a1 != (CObjectMgr **)-128LL )
      {
        *((_QWORD *)v7 + 2) = *v12;
        *v12 = (char *)v7 + 8;
      }
      *((_DWORD *)v7 + 34) = (_DWORD)v10;
      v13 = a1[17];
      if ( v13 )
      {
        IndexForCp = CObjectMgr::FindIndexForCp(a1[17], v59);
        *((_DWORD *)v7 + 34) = IndexForCp - CObjectMgr::FindIndexForCp(v13, v11);
        v10 = 0;
      }
      if ( (*((_BYTE *)a1 + 180) & 1) != 0 )
      {
        v19 = (int)v10;
        v20 = (_DWORD)a1[24] & 0xFF8FFEFF;
        v59 = (int)v10;
        ObjectFromCp = v10;
        v22 = v20 != 0 ? 7 : 5;
        if ( a1[17] != v10
          && *((_DWORD *)v7 + 32) == 1
          && !(*(unsigned int (__fastcall **)(struct CTxtRange *, int *))(*(_QWORD *)a2 + 72LL))(a2, v62)
          && v62[0] == 65532 )
        {
          ObjectFromCp = CObjectMgr::GetObjectFromCp(a1[17], *((_DWORD *)v7 + 33));
          *((_DWORD *)v7 + 11) = *((_DWORD *)ObjectFromCp + 36);
          *((_DWORD *)v7 + 12) = *((_DWORD *)ObjectFromCp + 37);
          *((_DWORD *)v7 + 13) = *((_DWORD *)ObjectFromCp + 38);
          v23 = (unsigned int (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)ObjectFromCp + 9);
          if ( v23 )
          {
            v24 = (_QWORD *)((char *)v7 + 96);
            if ( !(**v23)(v23, &IID_IOleObject, (char *)v7 + 96) )
            {
              if ( (v25 = (void (__fastcall ***)(_QWORD, GUID *, int *))*v24,
                    *(_QWORD *)v60 = 0,
                    v59 = 1,
                    ((int (__fastcall *)(_QWORD, _QWORD, int *))(*v25)[10])(v25, 0, v60) >= 0)
                && (v26 = *(_QWORD *)v60) != 0
                || ((**(void (__fastcall ***)(_QWORD, GUID *, int *))*v24)(*v24, &IID_IDataObject, v60),
                    (v26 = *(_QWORD *)v60) != 0) )
              {
                v61 = 0;
                if ( (*(int (__fastcall **)(__int64, __int64, struct tagSIZE *))(*(_QWORD *)v26 + 64LL))(v26, 1, &v61) >= 0
                  || (*((_DWORD *)a1 + 45) & 0x80000) != 0 )
                {
                  v27 = v61;
                  if ( v61 )
                  {
                    while ( !(*(unsigned int (__fastcall **)(struct tagSIZE, __int64, _OWORD *))(**(_QWORD **)&v27 + 24LL))(
                               v27,
                               1,
                               &Src[2 * v19]) )
                    {
                      if ( ++v19 == 256 )
                        break;
                      v27 = v61;
                    }
                    (*(void (__fastcall **)(struct tagSIZE))(**(_QWORD **)&v61 + 16LL))(v61);
                  }
                }
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v60 + 16LL))(*(_QWORD *)v60);
              }
            }
          }
        }
        *((_DWORD *)v7 + 7) = v22 + v19;
        v28 = 32 * (v22 + v19);
        if ( !is_mul_ok((unsigned int)(v22 + v19), 0x20u) )
          v28 = -1;
        v29 = CW32System::PvAlloc(v28, 0x40u);
        *((_QWORD *)v7 + 4) = v29;
        if ( v29 )
        {
          if ( ObjectFromCp )
          {
            if ( v19 )
              memcpy_0(v29, Src, 32LL * v19);
            v31 = *((_QWORD *)v7 + 4);
            v32 = 32LL * v19;
            *(_OWORD *)(v32 + v31) = xmmword_1800A3130;
            *(_OWORD *)(v32 + v31 + 16) = xmmword_1800A3140;
            v33 = *((_QWORD *)v7 + 4);
            v34 = 32 * (v19 + 1LL);
            *(_OWORD *)(v34 + v33) = xmmword_1800A3170;
            *(_OWORD *)(v34 + v33 + 16) = xmmword_1800A3180;
            v35 = *((_QWORD *)v7 + 4);
            v36 = 32LL * (v19 + 2);
            *(_OWORD *)(v36 + v35) = xmmword_1800A31B0;
            *(_OWORD *)(v36 + v35 + 16) = xmmword_1800A31C0;
            v37 = *((_QWORD *)v7 + 4);
            v38 = 32 * (v19 + 2 + 1LL);
            *(_OWORD *)(v38 + v37) = xmmword_1800A30F0;
            *(_OWORD *)(v38 + v37 + 16) = xmmword_1800A3100;
            v39 = *((_QWORD *)v7 + 4);
            v40 = 32LL * (v19 + 4);
            *(_OWORD *)(v40 + v39) = xmmword_1800A3210;
            *(_OWORD *)(v40 + v39 + 16) = xmmword_1800A3220;
            v41 = v19 + 5;
          }
          else
          {
            *v29 = xmmword_1800A30F0;
            v29[1] = xmmword_1800A3100;
            v42 = *((_QWORD *)v7 + 4);
            *(_OWORD *)(v42 + 32) = xmmword_1800A3210;
            *(_OWORD *)(v42 + 48) = xmmword_1800A3220;
            v43 = *((_QWORD *)v7 + 4);
            *(_OWORD *)(v43 + 64) = xmmword_1800A3290;
            *(_OWORD *)(v43 + 80) = xmmword_1800A32A0;
            v44 = *((_QWORD *)v7 + 4);
            *(_OWORD *)(v44 + 96) = xmmword_1800A3250;
            *(_OWORD *)(v44 + 112) = xmmword_1800A3260;
            v45 = *((_QWORD *)v7 + 4);
            *(_OWORD *)(v45 + 128) = xmmword_1800A3230;
            *(_OWORD *)(v45 + 144) = xmmword_1800A3240;
            v41 = 5;
          }
          if ( v20 )
          {
            v46 = v41;
            v47 = *((_QWORD *)v7 + 4);
            v48 = 32 * v46;
            *(_OWORD *)(v48 + v47) = *(_OWORD *)&g_rgFETC;
            *(_OWORD *)(v48 + v47 + 16) = xmmword_1800A30E0;
            v49 = *((_QWORD *)v7 + 4);
            v50 = 32 * (v46 + 1);
            *(_OWORD *)(v50 + v49) = xmmword_1800A3110;
            *(_OWORD *)(v50 + v49 + 16) = xmmword_1800A3120;
          }
          if ( v59 )
          {
            v51 = (struct tagSIZE)*((_QWORD *)ObjectFromCp + 13);
            v52 = (struct IOleObject **)((char *)v7 + 96);
            v61 = v51;
            v53 = (unsigned int *)((char *)ObjectFromCp + 152);
            ObjectDescriptorDataFromOleObject = (void *)*((_QWORD *)v7 + 14);
            if ( !ObjectDescriptorDataFromOleObject )
              ObjectDescriptorDataFromOleObject = OleGetObjectDescriptorDataFromOleObject(*v52, *v53, 0, &v61);
            v55 = *v52;
            *((_QWORD *)v7 + 14) = ObjectDescriptorDataFromOleObject;
            DataForEmbeddedObject = CDataTransferObj::GetDataForEmbeddedObject(v7, v55, 0);
            v57 = *v52;
            *((_QWORD *)v7 + 13) = DataForEmbeddedObject;
            *((_QWORD *)v7 + 15) = OleStdGetMetafilePictFromOleObject(v57, *v53, 0, v58);
          }
          return v7;
        }
      }
      else
      {
        *((_DWORD *)v7 + 7) = 2;
        v15 = 64;
        if ( !is_mul_ok(2u, 0x20u) )
          v15 = -1;
        v16 = CW32System::PvAlloc(v15, 0x40u);
        *((_QWORD *)v7 + 4) = v16;
        if ( v16 )
        {
          *v16 = xmmword_1800A3250;
          v16[1] = xmmword_1800A3260;
          v17 = *((_QWORD *)v7 + 4);
          *(_OWORD *)(v17 + 32) = xmmword_1800A3230;
          *(_OWORD *)(v17 + 48) = xmmword_1800A3240;
          return v7;
        }
      }
      v30 = *(_QWORD *)v7;
      *((_DWORD *)v7 + 7) = 0;
      (*(void (__fastcall **)(CDataTransferObj *))(v30 + 16))(v7);
    }
  }
  CCallMgr::SetOutOfMemory(a1[18]);
  return 0;
}

```

## disassembly

```asm
0x18005a618  mov     [rsp-8+arg_10], rbx
0x18005a61d  push    rbp
0x18005a61e  push    rsi
0x18005a61f  push    rdi
0x18005a620  push    r12
0x18005a622  push    r13
0x18005a624  push    r14
0x18005a626  push    r15
0x18005a628  lea     rbp, [rsp-1F70h]
0x18005a630  mov     eax, 2070h
0x18005a635  call    _alloca_probe
0x18005a63a  sub     rsp, rax
0x18005a63d  mov     rax, cs:__security_cookie
0x18005a644  xor     rax, rsp
0x18005a647  mov     [rbp+1FA0h+var_40], rax
0x18005a64e  mov     r13d, 40h ; '@'
0x18005a654  mov     [rsp+20A0h+var_2058], 0
0x18005a65c  mov     r15, rdx
0x18005a65f  mov     rsi, rcx
0x18005a662  mov     edx, r13d; unsigned int
0x18005a665  mov     ebx, r8d
0x18005a668  lea     ecx, [r13+50h]; unsigned int
0x18005a66c  call    ?PvAlloc@CW32System@@SAPEAXKI@Z; CW32System::PvAlloc(ulong,uint)
0x18005a671  xor     r10d, r10d
0x18005a674  test    rax, rax
0x18005a677  jz      loc_18005A98D
0x18005a67d  mov     rdx, rsi; struct CTxtEdit *
0x18005a680  mov     rcx, rax; this
0x18005a683  call    ??0CDataTransferObj@@AEAA@PEAVCTxtEdit@@@Z; CDataTransferObj::CDataTransferObj(CTxtEdit *)
0x18005a688  mov     rdi, rax
0x18005a68b  test    rax, rax
0x18005a68e  jz      loc_18005A98D
0x18005a694  lea     r8, [rsp+20A0h+var_2070]; int *
0x18005a699  mov     [rsp+20A0h+var_2068], r10d
0x18005a69e  lea     rdx, [rsp+20A0h+var_2068]; int *
0x18005a6a3  mov     [rsp+20A0h+var_2070], r10d
0x18005a6a8  mov     rcx, r15; this
0x18005a6ab  call    ?GetRange@CTxtRange@@QEBAJAEAJ0@Z; CTxtRange::GetRange(long &,long &)
0x18005a6b0  mov     r12d, [rsp+20A0h+var_2068]
0x18005a6b5  lea     rdx, [rsi+80h]
0x18005a6bc  mov     [rdi+80h], eax
0x18005a6c2  mov     [rdi+84h], r12d
0x18005a6c9  mov     [rdi+28h], ebx
0x18005a6cc  test    rdx, rdx
0x18005a6cf  jz      short loc_18005A6DF
0x18005a6d1  mov     rax, [rdx]
0x18005a6d4  lea     rcx, [rdi+8]
0x18005a6d8  mov     [rcx+8], rax
0x18005a6dc  mov     [rdx], rcx
0x18005a6df  mov     [rdi+88h], r10d
0x18005a6e6  mov     r14, [rsi+88h]
0x18005a6ed  test    r14, r14
0x18005a6f0  jz      short loc_18005A716
0x18005a6f2  mov     edx, [rsp+20A0h+var_2070]; int
0x18005a6f6  mov     rcx, r14; this
0x18005a6f9  call    ?FindIndexForCp@CObjectMgr@@QEAAJJ@Z; CObjectMgr::FindIndexForCp(long)
0x18005a6fe  mov     edx, r12d; int
0x18005a701  mov     rcx, r14; this
0x18005a704  mov     ebx, eax
0x18005a706  call    ?FindIndexForCp@CObjectMgr@@QEAAJJ@Z; CObjectMgr::FindIndexForCp(long)
0x18005a70b  sub     ebx, eax
0x18005a70d  mov     [rdi+88h], ebx
0x18005a713  xor     r10d, r10d
0x18005a716  test    byte ptr [rsi+0B4h], 1
0x18005a71d  jnz     short loc_18005A786
0x18005a71f  mov     ecx, 2
0x18005a724  mov     [rdi+1Ch], ecx
0x18005a727  lea     eax, [rcx+1Eh]
0x18005a72a  mul     rcx
0x18005a72d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18005a734  mov     edx, r13d; unsigned int
0x18005a737  cmovb   rax, rcx
0x18005a73b  mov     ecx, eax; unsigned int
0x18005a73d  call    ?PvAlloc@CW32System@@SAPEAXKI@Z; CW32System::PvAlloc(ulong,uint)
0x18005a742  mov     [rdi+20h], rax
0x18005a746  test    rax, rax
0x18005a749  jz      loc_18005A977
0x18005a74f  movaps  xmm0, cs:xmmword_1800A3250
0x18005a756  movups  xmmword ptr [rax], xmm0
0x18005a759  movaps  xmm1, cs:xmmword_1800A3260
0x18005a760  movups  xmmword ptr [rax+10h], xmm1
0x18005a764  mov     rax, [rdi+20h]
0x18005a768  movaps  xmm0, cs:xmmword_1800A3230
0x18005a76f  movups  xmmword ptr [rax+20h], xmm0
0x18005a773  movaps  xmm1, cs:xmmword_1800A3240
0x18005a77a  movups  xmmword ptr [rax+30h], xmm1
0x18005a77e  mov     rax, rdi
0x18005a781  jmp     loc_18005A99B
0x18005a786  mov     r13d, [rsi+0C0h]
0x18005a78d  mov     r14d, r10d
0x18005a790  and     r13d, 0FF8FFEFFh
0x18005a797  mov     [rsp+20A0h+var_2070], r10d
0x18005a79c  mov     eax, r13d
0x18005a79f  mov     rbx, r10
0x18005a7a2  neg     eax
0x18005a7a4  sbb     r12d, r12d
0x18005a7a7  and     r12d, 2
0x18005a7ab  add     r12d, 5
0x18005a7af  cmp     [rsi+88h], r10
0x18005a7b6  jz      loc_18005A948
0x18005a7bc  cmp     dword ptr [rdi+80h], 1
0x18005a7c3  jnz     loc_18005A948
0x18005a7c9  mov     rax, [r15]
0x18005a7cc  lea     rdx, [rsp+20A0h+var_2058]
0x18005a7d1  mov     rcx, r15
0x18005a7d4  mov     rax, [rax+48h]
0x18005a7d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a7dd  test    eax, eax
0x18005a7df  jnz     loc_18005A948
0x18005a7e5  cmp     [rsp+20A0h+var_2058], 0FFFCh
0x18005a7ed  jnz     loc_18005A948
0x18005a7f3  mov     edx, [rdi+84h]; int
0x18005a7f9  mov     rcx, [rsi+88h]; this
0x18005a800  call    ?GetObjectFromCp@CObjectMgr@@QEAAPEAVCOleObject@@J@Z; CObjectMgr::GetObjectFromCp(long)
0x18005a805  mov     rbx, rax
0x18005a808  mov     ecx, [rax+90h]
0x18005a80e  mov     [rdi+2Ch], ecx
0x18005a811  mov     ecx, [rax+94h]
0x18005a817  mov     [rdi+30h], ecx
0x18005a81a  mov     ecx, [rax+98h]
0x18005a820  mov     [rdi+34h], ecx
0x18005a823  mov     r9, [rax+48h]
0x18005a827  test    r9, r9
0x18005a82a  jz      loc_18005A948
0x18005a830  mov     rcx, [r9]
0x18005a833  lea     r15, [rdi+60h]
0x18005a837  mov     r8, r15
0x18005a83a  lea     rdx, IID_IOleObject
0x18005a841  mov     rax, [rcx]
0x18005a844  mov     rcx, r9
0x18005a847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a84c  test    eax, eax
0x18005a84e  jnz     loc_18005A948
0x18005a854  mov     rcx, [r15]
0x18005a857  lea     r8, [rsp+20A0h+var_2068]
0x18005a85c  mov     qword ptr [rsp+20A0h+var_2068], 0
0x18005a865  xor     edx, edx
0x18005a867  mov     [rsp+20A0h+var_2070], 1
0x18005a86f  mov     rax, [rcx]
0x18005a872  mov     rax, [rax+50h]
0x18005a876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a87b  test    eax, eax
0x18005a87d  js      short loc_18005A889
0x18005a87f  mov     rcx, qword ptr [rsp+20A0h+var_2068]
0x18005a884  test    rcx, rcx
0x18005a887  jnz     short loc_18005A8B1
0x18005a889  mov     rcx, [r15]
0x18005a88c  lea     r8, [rsp+20A0h+var_2068]
0x18005a891  lea     rdx, IID_IDataObject
0x18005a898  mov     rax, [rcx]
0x18005a89b  mov     rax, [rax]
0x18005a89e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a8a3  mov     rcx, qword ptr [rsp+20A0h+var_2068]
0x18005a8a8  test    rcx, rcx
0x18005a8ab  jz      loc_18005A948
0x18005a8b1  mov     qword ptr [rsp+20A0h+var_2060.cx], 0
0x18005a8ba  lea     r8, [rsp+20A0h+var_2060]
0x18005a8bf  mov     rax, [rcx]
0x18005a8c2  mov     edx, 1
0x18005a8c7  mov     rax, [rax+40h]
0x18005a8cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a8d0  test    eax, eax
0x18005a8d2  jns     short loc_18005A8E0
0x18005a8d4  test    dword ptr [rsi+0B4h], 80000h
0x18005a8de  jz      short loc_18005A937
0x18005a8e0  mov     r10, qword ptr [rsp+20A0h+var_2060.cx]
0x18005a8e5  test    r10, r10
0x18005a8e8  jz      short loc_18005A937
0x18005a8ea  mov     rcx, [r10]
0x18005a8ed  lea     r8, [rsp+20A0h+Src]
0x18005a8f2  xor     r9d, r9d
0x18005a8f5  movsxd  rax, r14d
0x18005a8f8  shl     rax, 5
0x18005a8fc  add     r8, rax
0x18005a8ff  mov     rax, [rcx+18h]
0x18005a903  mov     rcx, r10
0x18005a906  lea     edx, [r9+1]
0x18005a90a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a90f  test    eax, eax
0x18005a911  jnz     short loc_18005A926
0x18005a913  inc     r14d
0x18005a916  cmp     r14d, 100h
0x18005a91d  jz      short loc_18005A926
0x18005a91f  mov     r10, qword ptr [rsp+20A0h+var_2060.cx]
0x18005a924  jmp     short loc_18005A8EA
0x18005a926  mov     rcx, qword ptr [rsp+20A0h+var_2060.cx]
0x18005a92b  mov     rax, [rcx]
0x18005a92e  mov     rax, [rax+10h]
0x18005a932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a937  mov     rcx, qword ptr [rsp+20A0h+var_2068]
0x18005a93c  mov     rax, [rcx]
0x18005a93f  mov     rax, [rax+10h]
0x18005a943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a948  lea     eax, [r12+r14]
0x18005a94c  mov     ecx, eax
0x18005a94e  mov     [rdi+1Ch], eax
0x18005a951  mov     eax, 20h ; ' '
0x18005a956  mul     rcx
0x18005a959  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18005a960  cmovb   rax, rcx
0x18005a964  lea     edx, [rcx+41h]; unsigned int
0x18005a967  mov     ecx, eax; unsigned int
0x18005a969  call    ?PvAlloc@CW32System@@SAPEAXKI@Z; CW32System::PvAlloc(ulong,uint)
0x18005a96e  mov     [rdi+20h], rax
0x18005a972  test    rax, rax
0x18005a975  jnz     short loc_18005A9C5
0x18005a977  mov     rax, [rdi]
0x18005a97a  mov     rcx, rdi
0x18005a97d  mov     dword ptr [rdi+1Ch], 0
0x18005a984  mov     rax, [rax+10h]
0x18005a988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a98d  mov     rcx, [rsi+90h]; this
0x18005a994  call    ?SetOutOfMemory@CCallMgr@@QEAAXXZ; CCallMgr::SetOutOfMemory(void)
0x18005a999  xor     eax, eax
0x18005a99b  mov     rcx, [rbp+1FA0h+var_40]
0x18005a9a2  xor     rcx, rsp; StackCookie
0x18005a9a5  call    __security_check_cookie
0x18005a9aa  mov     rbx, [rsp+20A0h+arg_10]
0x18005a9b2  add     rsp, 2070h
0x18005a9b9  pop     r15
0x18005a9bb  pop     r14
0x18005a9bd  pop     r13
0x18005a9bf  pop     r12
0x18005a9c1  pop     rdi
0x18005a9c2  pop     rsi
0x18005a9c3  pop     rbp
0x18005a9c4  retn
0x18005a9c5  test    rbx, rbx
0x18005a9c8  jz      loc_18005AAA6
0x18005a9ce  test    r14d, r14d
0x18005a9d1  jz      short loc_18005A9E7
0x18005a9d3  movsxd  r8, r14d
0x18005a9d6  lea     rdx, [rsp+20A0h+Src]; Src
0x18005a9db  shl     r8, 5; Size
0x18005a9df  mov     rcx, rax; void *
0x18005a9e2  call    memcpy_0
0x18005a9e7  mov     rax, [rdi+20h]
0x18005a9eb  lea     edx, [r14+2]
0x18005a9ef  movaps  xmm0, cs:xmmword_1800A3130
0x18005a9f6  movsxd  rcx, r14d
0x18005a9f9  shl     rcx, 5
0x18005a9fd  movups  xmmword ptr [rcx+rax], xmm0
0x18005aa01  movaps  xmm1, cs:xmmword_1800A3140
0x18005aa08  movups  xmmword ptr [rcx+rax+10h], xmm1
0x18005aa0d  mov     rax, [rdi+20h]
0x18005aa11  movaps  xmm0, cs:xmmword_1800A3170
0x18005aa18  movsxd  rcx, r14d
0x18005aa1b  inc     rcx
0x18005aa1e  shl     rcx, 5
0x18005aa22  movups  xmmword ptr [rcx+rax], xmm0
0x18005aa26  movaps  xmm1, cs:xmmword_1800A3180
0x18005aa2d  movups  xmmword ptr [rcx+rax+10h], xmm1
0x18005aa32  mov     rax, [rdi+20h]
0x18005aa36  movaps  xmm0, cs:xmmword_1800A31B0
0x18005aa3d  movsxd  rcx, edx
0x18005aa40  shl     rcx, 5
0x18005aa44  movups  xmmword ptr [rcx+rax], xmm0
0x18005aa48  movaps  xmm1, cs:xmmword_1800A31C0
0x18005aa4f  movups  xmmword ptr [rcx+rax+10h], xmm1
0x18005aa54  mov     rax, [rdi+20h]
0x18005aa58  movaps  xmm0, cs:xmmword_1800A30F0
0x18005aa5f  movsxd  rcx, edx
0x18005aa62  add     edx, 2
0x18005aa65  inc     rcx
0x18005aa68  shl     rcx, 5
0x18005aa6c  movups  xmmword ptr [rcx+rax], xmm0
0x18005aa70  movaps  xmm1, cs:xmmword_1800A3100
0x18005aa77  movups  xmmword ptr [rcx+rax+10h], xmm1
0x18005aa7c  mov     rax, [rdi+20h]
0x18005aa80  movaps  xmm0, cs:xmmword_1800A3210
0x18005aa87  movsxd  rcx, edx
0x18005aa8a  shl     rcx, 5
0x18005aa8e  movups  xmmword ptr [rcx+rax], xmm0
0x18005aa92  movaps  xmm1, cs:xmmword_1800A3220
0x18005aa99  movups  xmmword ptr [rcx+rax+10h], xmm1
0x18005aa9e  lea     eax, [rdx+1]
0x18005aaa1  jmp     loc_18005AB2E
0x18005aaa6  movaps  xmm0, cs:xmmword_1800A30F0
0x18005aaad  movups  xmmword ptr [rax], xmm0
0x18005aab0  movaps  xmm1, cs:xmmword_1800A3100
0x18005aab7  movups  xmmword ptr [rax+10h], xmm1
0x18005aabb  mov     rax, [rdi+20h]
0x18005aabf  movaps  xmm0, cs:xmmword_1800A3210
0x18005aac6  movups  xmmword ptr [rax+20h], xmm0
0x18005aaca  movaps  xmm1, cs:xmmword_1800A3220
0x18005aad1  movups  xmmword ptr [rax+30h], xmm1
0x18005aad5  mov     rax, [rdi+20h]
0x18005aad9  movaps  xmm0, cs:xmmword_1800A3290
0x18005aae0  movups  xmmword ptr [rax+40h], xmm0
0x18005aae4  movaps  xmm1, cs:xmmword_1800A32A0
0x18005aaeb  movups  xmmword ptr [rax+50h], xmm1
0x18005aaef  mov     rax, [rdi+20h]
0x18005aaf3  movaps  xmm0, cs:xmmword_1800A3250
0x18005aafa  movups  xmmword ptr [rax+60h], xmm0
0x18005aafe  movaps  xmm1, cs:xmmword_1800A3260
0x18005ab05  movups  xmmword ptr [rax+70h], xmm1
0x18005ab09  mov     rax, [rdi+20h]
0x18005ab0d  movaps  xmm0, cs:xmmword_1800A3230
0x18005ab14  movups  xmmword ptr [rax+80h], xmm0
0x18005ab1b  movaps  xmm1, cs:xmmword_1800A3240
  ... truncated ...
```
