# CDataTransferObj::Create(CTxtEdit *,CTxtRange *,long)

- ea: `0x18005bc58`
- end: `0x18005c229`
- name: `?Create@CDataTransferObj@@SAPEAV1@PEAVCTxtEdit@@PEAVCTxtRange@@J@Z`
- size: `1489`
- prototype: `struct CDataTransferObj *__fastcall(struct CTxtEdit *, struct CTxtRange *, int)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x18006f13c`

## callees

- `0x1800274a0`
- `0x18003cc90`
- `0x180041b1c`
- `0x1800466f0`
- `0x18005bab8`
- `0x18005bc58`
- `0x18005c608`
- `0x180071974`
- `0x18008e9e0`
- `0x18008ed4c`
- `0x180093bb2`
- `0x180093c00`
- `0x180093c90`
- `0x180095010`

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
  __int64 ObjectDescriptorDataFromOleObject; // rax
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
            *(_OWORD *)(v32 + v31) = xmmword_1800A6230;
            *(_OWORD *)(v32 + v31 + 16) = xmmword_1800A6240;
            v33 = *((_QWORD *)v7 + 4);
            v34 = 32 * (v19 + 1LL);
            *(_OWORD *)(v34 + v33) = xmmword_1800A6270;
            *(_OWORD *)(v34 + v33 + 16) = xmmword_1800A6280;
            v35 = *((_QWORD *)v7 + 4);
            v36 = 32LL * (v19 + 2);
            *(_OWORD *)(v36 + v35) = xmmword_1800A62B0;
            *(_OWORD *)(v36 + v35 + 16) = xmmword_1800A62C0;
            v37 = *((_QWORD *)v7 + 4);
            v38 = 32 * (v19 + 2 + 1LL);
            *(_OWORD *)(v38 + v37) = xmmword_1800A61F0;
            *(_OWORD *)(v38 + v37 + 16) = xmmword_1800A6200;
            v39 = *((_QWORD *)v7 + 4);
            v40 = 32LL * (v19 + 4);
            *(_OWORD *)(v40 + v39) = xmmword_1800A6310;
            *(_OWORD *)(v40 + v39 + 16) = xmmword_1800A6320;
            v41 = v19 + 5;
          }
          else
          {
            *v29 = xmmword_1800A61F0;
            v29[1] = xmmword_1800A6200;
            v42 = *((_QWORD *)v7 + 4);
            *(_OWORD *)(v42 + 32) = xmmword_1800A6310;
            *(_OWORD *)(v42 + 48) = xmmword_1800A6320;
            v43 = *((_QWORD *)v7 + 4);
            *(_OWORD *)(v43 + 64) = xmmword_1800A6390;
            *(_OWORD *)(v43 + 80) = xmmword_1800A63A0;
            v44 = *((_QWORD *)v7 + 4);
            *(_OWORD *)(v44 + 96) = xmmword_1800A6350;
            *(_OWORD *)(v44 + 112) = xmmword_1800A6360;
            v45 = *((_QWORD *)v7 + 4);
            *(_OWORD *)(v45 + 128) = xmmword_1800A6330;
            *(_OWORD *)(v45 + 144) = xmmword_1800A6340;
            v41 = 5;
          }
          if ( v20 )
          {
            v46 = v41;
            v47 = *((_QWORD *)v7 + 4);
            v48 = 32 * v46;
            *(_OWORD *)(v48 + v47) = *(_OWORD *)&g_rgFETC;
            *(_OWORD *)(v48 + v47 + 16) = xmmword_1800A61E0;
            v49 = *((_QWORD *)v7 + 4);
            v50 = 32 * (v46 + 1);
            *(_OWORD *)(v50 + v49) = xmmword_1800A6210;
            *(_OWORD *)(v50 + v49 + 16) = xmmword_1800A6220;
          }
          if ( v59 )
          {
            v51 = (struct tagSIZE)*((_QWORD *)ObjectFromCp + 13);
            v52 = (struct IOleObject **)((char *)v7 + 96);
            v61 = v51;
            v53 = (unsigned int *)((char *)ObjectFromCp + 152);
            ObjectDescriptorDataFromOleObject = *((_QWORD *)v7 + 14);
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
          *v16 = xmmword_1800A6350;
          v16[1] = xmmword_1800A6360;
          v17 = *((_QWORD *)v7 + 4);
          *(_OWORD *)(v17 + 32) = xmmword_1800A6330;
          *(_OWORD *)(v17 + 48) = xmmword_1800A6340;
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
0x18005bc58  mov     [rsp-8+arg_10], rbx
0x18005bc5d  push    rbp
0x18005bc5e  push    rsi
0x18005bc5f  push    rdi
0x18005bc60  push    r12
0x18005bc62  push    r13
0x18005bc64  push    r14
0x18005bc66  push    r15
0x18005bc68  lea     rbp, [rsp-1F70h]
0x18005bc70  mov     eax, 2070h
0x18005bc75  call    _alloca_probe
0x18005bc7a  sub     rsp, rax
0x18005bc7d  mov     rax, cs:__security_cookie
0x18005bc84  xor     rax, rsp
0x18005bc87  mov     [rbp+1FA0h+var_40], rax
0x18005bc8e  mov     r13d, 40h ; '@'
0x18005bc94  mov     [rsp+20A0h+var_2058], 0
0x18005bc9c  mov     r15, rdx
0x18005bc9f  mov     rsi, rcx
0x18005bca2  mov     edx, r13d; unsigned int
0x18005bca5  mov     ebx, r8d
0x18005bca8  lea     ecx, [r13+50h]; unsigned int
0x18005bcac  call    ?PvAlloc@CW32System@@SAPEAXKI@Z; CW32System::PvAlloc(ulong,uint)
0x18005bcb1  xor     r10d, r10d
0x18005bcb4  test    rax, rax
0x18005bcb7  jz      loc_18005BFCD
0x18005bcbd  mov     rdx, rsi; struct CTxtEdit *
0x18005bcc0  mov     rcx, rax; this
0x18005bcc3  call    ??0CDataTransferObj@@AEAA@PEAVCTxtEdit@@@Z; CDataTransferObj::CDataTransferObj(CTxtEdit *)
0x18005bcc8  mov     rdi, rax
0x18005bccb  test    rax, rax
0x18005bcce  jz      loc_18005BFCD
0x18005bcd4  lea     r8, [rsp+20A0h+var_2070]; int *
0x18005bcd9  mov     [rsp+20A0h+var_2068], r10d
0x18005bcde  lea     rdx, [rsp+20A0h+var_2068]; int *
0x18005bce3  mov     [rsp+20A0h+var_2070], r10d
0x18005bce8  mov     rcx, r15; this
0x18005bceb  call    ?GetRange@CTxtRange@@QEBAJAEAJ0@Z; CTxtRange::GetRange(long &,long &)
0x18005bcf0  mov     r12d, [rsp+20A0h+var_2068]
0x18005bcf5  lea     rdx, [rsi+80h]
0x18005bcfc  mov     [rdi+80h], eax
0x18005bd02  mov     [rdi+84h], r12d
0x18005bd09  mov     [rdi+28h], ebx
0x18005bd0c  test    rdx, rdx
0x18005bd0f  jz      short loc_18005BD1F
0x18005bd11  mov     rax, [rdx]
0x18005bd14  lea     rcx, [rdi+8]
0x18005bd18  mov     [rcx+8], rax
0x18005bd1c  mov     [rdx], rcx
0x18005bd1f  mov     [rdi+88h], r10d
0x18005bd26  mov     r14, [rsi+88h]
0x18005bd2d  test    r14, r14
0x18005bd30  jz      short loc_18005BD56
0x18005bd32  mov     edx, [rsp+20A0h+var_2070]; int
0x18005bd36  mov     rcx, r14; this
0x18005bd39  call    ?FindIndexForCp@CObjectMgr@@QEAAJJ@Z; CObjectMgr::FindIndexForCp(long)
0x18005bd3e  mov     edx, r12d; int
0x18005bd41  mov     rcx, r14; this
0x18005bd44  mov     ebx, eax
0x18005bd46  call    ?FindIndexForCp@CObjectMgr@@QEAAJJ@Z; CObjectMgr::FindIndexForCp(long)
0x18005bd4b  sub     ebx, eax
0x18005bd4d  mov     [rdi+88h], ebx
0x18005bd53  xor     r10d, r10d
0x18005bd56  test    byte ptr [rsi+0B4h], 1
0x18005bd5d  jnz     short loc_18005BDC6
0x18005bd5f  mov     ecx, 2
0x18005bd64  mov     [rdi+1Ch], ecx
0x18005bd67  lea     eax, [rcx+1Eh]
0x18005bd6a  mul     rcx
0x18005bd6d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18005bd74  mov     edx, r13d; unsigned int
0x18005bd77  cmovb   rax, rcx
0x18005bd7b  mov     ecx, eax; unsigned int
0x18005bd7d  call    ?PvAlloc@CW32System@@SAPEAXKI@Z; CW32System::PvAlloc(ulong,uint)
0x18005bd82  mov     [rdi+20h], rax
0x18005bd86  test    rax, rax
0x18005bd89  jz      loc_18005BFB7
0x18005bd8f  movaps  xmm0, cs:xmmword_1800A6350
0x18005bd96  movups  xmmword ptr [rax], xmm0
0x18005bd99  movaps  xmm1, cs:xmmword_1800A6360
0x18005bda0  movups  xmmword ptr [rax+10h], xmm1
0x18005bda4  mov     rax, [rdi+20h]
0x18005bda8  movaps  xmm0, cs:xmmword_1800A6330
0x18005bdaf  movups  xmmword ptr [rax+20h], xmm0
0x18005bdb3  movaps  xmm1, cs:xmmword_1800A6340
0x18005bdba  movups  xmmword ptr [rax+30h], xmm1
0x18005bdbe  mov     rax, rdi
0x18005bdc1  jmp     loc_18005BFDB
0x18005bdc6  mov     r13d, [rsi+0C0h]
0x18005bdcd  mov     r14d, r10d
0x18005bdd0  and     r13d, 0FF8FFEFFh
0x18005bdd7  mov     [rsp+20A0h+var_2070], r10d
0x18005bddc  mov     eax, r13d
0x18005bddf  mov     rbx, r10
0x18005bde2  neg     eax
0x18005bde4  sbb     r12d, r12d
0x18005bde7  and     r12d, 2
0x18005bdeb  add     r12d, 5
0x18005bdef  cmp     [rsi+88h], r10
0x18005bdf6  jz      loc_18005BF88
0x18005bdfc  cmp     dword ptr [rdi+80h], 1
0x18005be03  jnz     loc_18005BF88
0x18005be09  mov     rax, [r15]
0x18005be0c  lea     rdx, [rsp+20A0h+var_2058]
0x18005be11  mov     rcx, r15
0x18005be14  mov     rax, [rax+48h]
0x18005be18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005be1d  test    eax, eax
0x18005be1f  jnz     loc_18005BF88
0x18005be25  cmp     [rsp+20A0h+var_2058], 0FFFCh
0x18005be2d  jnz     loc_18005BF88
0x18005be33  mov     edx, [rdi+84h]; int
0x18005be39  mov     rcx, [rsi+88h]; this
0x18005be40  call    ?GetObjectFromCp@CObjectMgr@@QEAAPEAVCOleObject@@J@Z; CObjectMgr::GetObjectFromCp(long)
0x18005be45  mov     rbx, rax
0x18005be48  mov     ecx, [rax+90h]
0x18005be4e  mov     [rdi+2Ch], ecx
0x18005be51  mov     ecx, [rax+94h]
0x18005be57  mov     [rdi+30h], ecx
0x18005be5a  mov     ecx, [rax+98h]
0x18005be60  mov     [rdi+34h], ecx
0x18005be63  mov     r9, [rax+48h]
0x18005be67  test    r9, r9
0x18005be6a  jz      loc_18005BF88
0x18005be70  mov     rcx, [r9]
0x18005be73  lea     r15, [rdi+60h]
0x18005be77  mov     r8, r15
0x18005be7a  lea     rdx, IID_IOleObject
0x18005be81  mov     rax, [rcx]
0x18005be84  mov     rcx, r9
0x18005be87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005be8c  test    eax, eax
0x18005be8e  jnz     loc_18005BF88
0x18005be94  mov     rcx, [r15]
0x18005be97  lea     r8, [rsp+20A0h+var_2068]
0x18005be9c  mov     qword ptr [rsp+20A0h+var_2068], 0
0x18005bea5  xor     edx, edx
0x18005bea7  mov     [rsp+20A0h+var_2070], 1
0x18005beaf  mov     rax, [rcx]
0x18005beb2  mov     rax, [rax+50h]
0x18005beb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bebb  test    eax, eax
0x18005bebd  js      short loc_18005BEC9
0x18005bebf  mov     rcx, qword ptr [rsp+20A0h+var_2068]
0x18005bec4  test    rcx, rcx
0x18005bec7  jnz     short loc_18005BEF1
0x18005bec9  mov     rcx, [r15]
0x18005becc  lea     r8, [rsp+20A0h+var_2068]
0x18005bed1  lea     rdx, IID_IDataObject
0x18005bed8  mov     rax, [rcx]
0x18005bedb  mov     rax, [rax]
0x18005bede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bee3  mov     rcx, qword ptr [rsp+20A0h+var_2068]
0x18005bee8  test    rcx, rcx
0x18005beeb  jz      loc_18005BF88
0x18005bef1  mov     qword ptr [rsp+20A0h+var_2060.cx], 0
0x18005befa  lea     r8, [rsp+20A0h+var_2060]
0x18005beff  mov     rax, [rcx]
0x18005bf02  mov     edx, 1
0x18005bf07  mov     rax, [rax+40h]
0x18005bf0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bf10  test    eax, eax
0x18005bf12  jns     short loc_18005BF20
0x18005bf14  test    dword ptr [rsi+0B4h], 80000h
0x18005bf1e  jz      short loc_18005BF77
0x18005bf20  mov     r10, qword ptr [rsp+20A0h+var_2060.cx]
0x18005bf25  test    r10, r10
0x18005bf28  jz      short loc_18005BF77
0x18005bf2a  mov     rcx, [r10]
0x18005bf2d  lea     r8, [rsp+20A0h+Src]
0x18005bf32  xor     r9d, r9d
0x18005bf35  movsxd  rax, r14d
0x18005bf38  shl     rax, 5
0x18005bf3c  add     r8, rax
0x18005bf3f  mov     rax, [rcx+18h]
0x18005bf43  mov     rcx, r10
0x18005bf46  lea     edx, [r9+1]
0x18005bf4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bf4f  test    eax, eax
0x18005bf51  jnz     short loc_18005BF66
0x18005bf53  inc     r14d
0x18005bf56  cmp     r14d, 100h
0x18005bf5d  jz      short loc_18005BF66
0x18005bf5f  mov     r10, qword ptr [rsp+20A0h+var_2060.cx]
0x18005bf64  jmp     short loc_18005BF2A
0x18005bf66  mov     rcx, qword ptr [rsp+20A0h+var_2060.cx]
0x18005bf6b  mov     rax, [rcx]
0x18005bf6e  mov     rax, [rax+10h]
0x18005bf72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bf77  mov     rcx, qword ptr [rsp+20A0h+var_2068]
0x18005bf7c  mov     rax, [rcx]
0x18005bf7f  mov     rax, [rax+10h]
0x18005bf83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bf88  lea     eax, [r12+r14]
0x18005bf8c  mov     ecx, eax
0x18005bf8e  mov     [rdi+1Ch], eax
0x18005bf91  mov     eax, 20h ; ' '
0x18005bf96  mul     rcx
0x18005bf99  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18005bfa0  cmovb   rax, rcx
0x18005bfa4  lea     edx, [rcx+41h]; unsigned int
0x18005bfa7  mov     ecx, eax; unsigned int
0x18005bfa9  call    ?PvAlloc@CW32System@@SAPEAXKI@Z; CW32System::PvAlloc(ulong,uint)
0x18005bfae  mov     [rdi+20h], rax
0x18005bfb2  test    rax, rax
0x18005bfb5  jnz     short loc_18005C006
0x18005bfb7  mov     rax, [rdi]
0x18005bfba  mov     rcx, rdi
0x18005bfbd  mov     dword ptr [rdi+1Ch], 0
0x18005bfc4  mov     rax, [rax+10h]
0x18005bfc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bfcd  mov     rcx, [rsi+90h]; this
0x18005bfd4  call    ?SetOutOfMemory@CCallMgr@@QEAAXXZ; CCallMgr::SetOutOfMemory(void)
0x18005bfd9  xor     eax, eax
0x18005bfdb  mov     rcx, [rbp+1FA0h+var_40]
0x18005bfe2  xor     rcx, rsp; StackCookie
0x18005bfe5  call    __security_check_cookie
0x18005bfea  mov     rbx, [rsp+20A0h+arg_10]
0x18005bff2  add     rsp, 2070h
0x18005bff9  pop     r15
0x18005bffb  pop     r14
0x18005bffd  pop     r13
0x18005bfff  pop     r12
0x18005c001  pop     rdi
0x18005c002  pop     rsi
0x18005c003  pop     rbp
0x18005c004  retn
0x18005c006  test    rbx, rbx
0x18005c009  jz      loc_18005C0E7
0x18005c00f  test    r14d, r14d
0x18005c012  jz      short loc_18005C028
0x18005c014  movsxd  r8, r14d
0x18005c017  lea     rdx, [rsp+20A0h+Src]; Src
0x18005c01c  shl     r8, 5; Size
0x18005c020  mov     rcx, rax; void *
0x18005c023  call    memcpy_0
0x18005c028  mov     rax, [rdi+20h]
0x18005c02c  lea     edx, [r14+2]
0x18005c030  movaps  xmm0, cs:xmmword_1800A6230
0x18005c037  movsxd  rcx, r14d
0x18005c03a  shl     rcx, 5
0x18005c03e  movups  xmmword ptr [rcx+rax], xmm0
0x18005c042  movaps  xmm1, cs:xmmword_1800A6240
0x18005c049  movups  xmmword ptr [rcx+rax+10h], xmm1
0x18005c04e  mov     rax, [rdi+20h]
0x18005c052  movaps  xmm0, cs:xmmword_1800A6270
0x18005c059  movsxd  rcx, r14d
0x18005c05c  inc     rcx
0x18005c05f  shl     rcx, 5
0x18005c063  movups  xmmword ptr [rcx+rax], xmm0
0x18005c067  movaps  xmm1, cs:xmmword_1800A6280
0x18005c06e  movups  xmmword ptr [rcx+rax+10h], xmm1
0x18005c073  mov     rax, [rdi+20h]
0x18005c077  movaps  xmm0, cs:xmmword_1800A62B0
0x18005c07e  movsxd  rcx, edx
0x18005c081  shl     rcx, 5
0x18005c085  movups  xmmword ptr [rcx+rax], xmm0
0x18005c089  movaps  xmm1, cs:xmmword_1800A62C0
0x18005c090  movups  xmmword ptr [rcx+rax+10h], xmm1
0x18005c095  mov     rax, [rdi+20h]
0x18005c099  movaps  xmm0, cs:xmmword_1800A61F0
0x18005c0a0  movsxd  rcx, edx
0x18005c0a3  add     edx, 2
0x18005c0a6  inc     rcx
0x18005c0a9  shl     rcx, 5
0x18005c0ad  movups  xmmword ptr [rcx+rax], xmm0
0x18005c0b1  movaps  xmm1, cs:xmmword_1800A6200
0x18005c0b8  movups  xmmword ptr [rcx+rax+10h], xmm1
0x18005c0bd  mov     rax, [rdi+20h]
0x18005c0c1  movaps  xmm0, cs:xmmword_1800A6310
0x18005c0c8  movsxd  rcx, edx
0x18005c0cb  shl     rcx, 5
0x18005c0cf  movups  xmmword ptr [rcx+rax], xmm0
0x18005c0d3  movaps  xmm1, cs:xmmword_1800A6320
0x18005c0da  movups  xmmword ptr [rcx+rax+10h], xmm1
0x18005c0df  lea     eax, [rdx+1]
0x18005c0e2  jmp     loc_18005C16F
0x18005c0e7  movaps  xmm0, cs:xmmword_1800A61F0
0x18005c0ee  movups  xmmword ptr [rax], xmm0
0x18005c0f1  movaps  xmm1, cs:xmmword_1800A6200
0x18005c0f8  movups  xmmword ptr [rax+10h], xmm1
0x18005c0fc  mov     rax, [rdi+20h]
0x18005c100  movaps  xmm0, cs:xmmword_1800A6310
0x18005c107  movups  xmmword ptr [rax+20h], xmm0
0x18005c10b  movaps  xmm1, cs:xmmword_1800A6320
0x18005c112  movups  xmmword ptr [rax+30h], xmm1
0x18005c116  mov     rax, [rdi+20h]
0x18005c11a  movaps  xmm0, cs:xmmword_1800A6390
0x18005c121  movups  xmmword ptr [rax+40h], xmm0
0x18005c125  movaps  xmm1, cs:xmmword_1800A63A0
0x18005c12c  movups  xmmword ptr [rax+50h], xmm1
0x18005c130  mov     rax, [rdi+20h]
0x18005c134  movaps  xmm0, cs:xmmword_1800A6350
0x18005c13b  movups  xmmword ptr [rax+60h], xmm0
0x18005c13f  movaps  xmm1, cs:xmmword_1800A6360
0x18005c146  movups  xmmword ptr [rax+70h], xmm1
0x18005c14a  mov     rax, [rdi+20h]
0x18005c14e  movaps  xmm0, cs:xmmword_1800A6330
0x18005c155  movups  xmmword ptr [rax+80h], xmm0
0x18005c15c  movaps  xmm1, cs:xmmword_1800A6340
  ... truncated ...
```
