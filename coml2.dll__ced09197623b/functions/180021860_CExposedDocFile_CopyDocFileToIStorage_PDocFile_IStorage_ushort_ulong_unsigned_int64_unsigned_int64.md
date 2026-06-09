# CExposedDocFile::CopyDocFileToIStorage(PDocFile *,IStorage *,ushort * *,ulong,unsigned __int64 *,unsigned __int64 *)

- ea: `0x180021860`
- end: `0x180021ce8`
- name: `?CopyDocFileToIStorage@CExposedDocFile@@AEAAJPEAVPDocFile@@PEAUIStorage@@PEAPEAGKPEA_K3@Z`
- size: `1160`
- prototype: `__int64 __fastcall(CExposedDocFile *__hidden this, struct PDocFile *, struct IStorage *, unsigned __int16 **, unsigned int, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021860`
- `0x18003abf0`

## callees

- `0x180017204`
- `0x180018914`
- `0x1800192e0`
- `0x18001a880`
- `0x18001bf68`
- `0x18001e2f0`
- `0x180021860`
- `0x18002200c`
- `0x1800222fc`
- `0x18002268c`
- `0x18002e288`
- `0x18002e42c`
- `0x180060410`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021883`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021883`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021b10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021b10`

## pseudocode

```c
__int64 __fastcall CExposedDocFile::CopyDocFileToIStorage(
        CExposedDocFile *this,
        struct PDocFile *a2,
        struct IStorage *a3,
        unsigned __int16 **a4,
        unsigned int a5,
        unsigned __int64 *a6,
        unsigned __int64 *a7)
{
  char *v10; // rax
  char *v11; // rbx
  _QWORD *v12; // rcx
  _QWORD *v13; // rdx
  int Class; // edi
  _QWORD *v15; // rcx
  _QWORD *v16; // rdx
  _QWORD *v17; // rcx
  _QWORD *v18; // rdx
  int GreaterEntry; // eax
  int v20; // eax
  int v21; // eax
  _QWORD *v22; // rcx
  _QWORD *v23; // rdx
  char *v24; // r12
  struct IStream **v25; // r15
  int v26; // eax
  CSafeMultiHeap *v27; // rcx
  PBasicEntry *v28; // rcx
  _QWORD *v30; // rcx
  _QWORD *v31; // rdx
  int v32; // eax
  struct IStream *v33; // rcx
  PBasicEntry *v34; // rcx
  unsigned __int64 *v35; // [rsp+28h] [rbp-80h]
  _BYTE v36[16]; // [rsp+40h] [rbp-68h] BYREF
  _BYTE v37[88]; // [rsp+50h] [rbp-58h] BYREF

  v10 = (char *)CoTaskMemAlloc(0x100u);
  v11 = v10;
  if ( !v10 )
  {
    Class = -2147287032;
    v11 = 0;
    goto LABEL_20;
  }
  *((_WORD *)v10 + 58) = 0;
  *((_WORD *)v10 + 92) = 0;
  v12 = (_QWORD *)*((_QWORD *)this + 22);
  v13 = (_QWORD *)*((_QWORD *)this + 21);
  v13[4] = v12[2];
  v13[5] = v12[3];
  v13[6] = v12[4];
  Class = PDocFile::GetClass(a2, (struct _GUID *)(v10 + 36));
  if ( Class >= 0 )
  {
    Class = ((__int64 (__fastcall *)(struct IStorage *, char *))a3->lpVtbl->SetClass)(a3, v11 + 36);
    if ( (int)(Class + 0x80000000) < 0 || Class == -2147287039 )
    {
      v15 = (_QWORD *)*((_QWORD *)this + 22);
      v16 = (_QWORD *)*((_QWORD *)this + 21);
      v16[4] = v15[2];
      v16[5] = v15[3];
      v16[6] = v15[4];
      Class = PDocFile::GetStateBits(a2, (unsigned int *)v11 + 8);
      if ( Class >= 0 )
      {
        Class = ((__int64 (__fastcall *)(struct IStorage *, _QWORD, __int64))a3->lpVtbl->SetStateBits)(
                  a3,
                  *((unsigned int *)v11 + 8),
                  0xFFFFFFFFLL);
        if ( ((Class + 0x80000000) & 0x80000000) != 0 || Class == -2147287039 )
        {
          while ( 1 )
          {
            while ( 1 )
            {
              do
              {
                v17 = (_QWORD *)*((_QWORD *)this + 22);
                v18 = (_QWORD *)*((_QWORD *)this + 21);
                v18[4] = v17[2];
                v18[5] = v17[3];
                v18[6] = v17[4];
                GreaterEntry = PDocFile::FindGreaterEntry(
                                 a2,
                                 (const struct CDfName *)(v11 + 52),
                                 (struct SIterBuffer *)(v11 + 120),
                                 0);
                Class = GreaterEntry;
                if ( GreaterEntry == -2147287022 )
                {
                  Class = 0;
                  goto LABEL_20;
                }
                if ( GreaterEntry < 0 )
                  goto LABEL_20;
                CDfName::Set((CDfName *)(v11 + 52), (const struct CDfName *)(v11 + 120));
              }
              while ( a4 && !(unsigned int)NameInSNB((const struct CDfName *)(v11 + 120), a4) );
              v20 = *((_DWORD *)v11 + 47);
              if ( v20 == 1 )
                break;
              if ( v20 != 2 || (a5 & 2) != 0 )
              {
                v21 = v20 - 1;
                if ( !v21 )
                  goto LABEL_29;
                if ( v21 == 1 )
                {
                  v22 = (_QWORD *)*((_QWORD *)this + 22);
                  v23 = (_QWORD *)*((_QWORD *)this + 21);
                  v23[4] = v22[2];
                  v23[5] = v22[3];
                  v23[6] = v22[4];
                  Class = PDocFile::GetStream(a2, (const struct CDfName *)(v11 + 120), 0x40u, (struct PSStream **)v11);
                  if ( Class < 0 )
                    goto LABEL_20;
                  v24 = v11 + 192;
                  StringCbCopyW((unsigned __int16 *)v11 + 96, 0x40u, (const unsigned __int16 *)v11 + 60);
                  CSafeMultiHeap::CSafeMultiHeap((CSafeMultiHeap *)v37, *((struct CPerContext **)this + 22));
                  v25 = (struct IStream **)(v11 + 8);
                  v26 = ((__int64 (__fastcall *)(struct IStorage *, char *, __int64, _QWORD, _DWORD, char *))a3->lpVtbl->CreateStream)(
                          a3,
                          v11 + 192,
                          4113,
                          0,
                          0,
                          v11 + 8);
                  v27 = (CSafeMultiHeap *)v37;
                  Class = v26;
                  if ( v26 < 0 )
                    goto LABEL_40;
                  CSafeMultiHeap::~CSafeMultiHeap((CSafeMultiHeap *)v37);
                  Class = CExposedDocFile::CopySStreamToIStream(this, *(struct PSStream **)v11, *v25, a6, a7);
                  if ( Class < 0 )
                  {
                    v25 = (struct IStream **)(v11 + 24);
LABEL_36:
                    if ( *((_DWORD *)v11 + 47) == 1 )
                      v33 = *v25;
                    else
                      v33 = (struct IStream *)*((_QWORD *)v11 + 1);
                    (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v33 + 16LL))(v33);
                    ((void (__fastcall *)(struct IStorage *, char *))a3->lpVtbl->DestroyElement)(a3, v24);
LABEL_41:
                    if ( *((_DWORD *)v11 + 47) == 1 )
                      v34 = (PBasicEntry *)*((_QWORD *)v11 + 2);
                    else
                      v34 = *(PBasicEntry **)v11;
                    PBasicEntry::Release(v34);
                    goto LABEL_20;
                  }
                  v28 = *(PBasicEntry **)v11;
LABEL_18:
                  PBasicEntry::Release(v28);
                  (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)*v25 + 16LL))(*v25);
                }
              }
            }
            if ( (a5 & 1) != 0 )
            {
LABEL_29:
              v30 = (_QWORD *)*((_QWORD *)this + 22);
              v31 = (_QWORD *)*((_QWORD *)this + 21);
              v31[4] = v30[2];
              v31[5] = v30[3];
              v31[6] = v30[4];
              Class = PDocFile::GetDocFile(a2, (const struct CDfName *)(v11 + 120), 0x40u, (struct PDocFile **)v11 + 2);
              if ( Class < 0 )
                break;
              v24 = v11 + 192;
              StringCbCopyW((unsigned __int16 *)v11 + 96, 0x40u, (const unsigned __int16 *)v11 + 60);
              CSafeMultiHeap::CSafeMultiHeap((CSafeMultiHeap *)v36, *((struct CPerContext **)this + 22));
              v25 = (struct IStream **)(v11 + 24);
              v35 = (unsigned __int64 *)(v11 + 24);
              v32 = ((__int64 (__fastcall *)(struct IStorage *, char *, __int64))a3->lpVtbl->CreateStorage)(
                      a3,
                      v11 + 192,
                      17);
              Class = v32;
              if ( v32 == -2147286960 )
              {
                LODWORD(v35) = 0;
                v32 = ((__int64 (__fastcall *)(struct IStorage *, char *, _QWORD, __int64, _QWORD, unsigned __int64 *, char *))a3->lpVtbl->OpenStorage)(
                        a3,
                        v11 + 192,
                        0,
                        18,
                        0,
                        v35,
                        v11 + 24);
                Class = v32;
              }
              v27 = (CSafeMultiHeap *)v36;
              if ( v32 < 0 )
              {
LABEL_40:
                CSafeMultiHeap::~CSafeMultiHeap(v27);
                goto LABEL_41;
              }
              CSafeMultiHeap::~CSafeMultiHeap((CSafeMultiHeap *)v36);
              Class = CExposedDocFile::CopyDocFileToIStorage(
                        this,
                        *((struct PDocFile **)v11 + 2),
                        (struct IStorage *)*v25,
                        0,
                        a5,
                        a6,
                        a7);
              if ( Class < 0 )
                goto LABEL_36;
              v28 = (PBasicEntry *)*((_QWORD *)v11 + 2);
              goto LABEL_18;
            }
          }
        }
      }
    }
  }
LABEL_20:
  CoTaskMemFree(v11);
  return (unsigned int)Class;
}

```

## disassembly

```asm
0x180021860  mov     [rsp+arg_18], r9
0x180021865  push    rbx
0x180021866  push    rbp
0x180021867  push    rsi
0x180021868  push    rdi
0x180021869  push    r12
0x18002186b  push    r13
0x18002186d  push    r14
0x18002186f  push    r15
0x180021871  sub     rsp, 68h
0x180021875  mov     rsi, rcx
0x180021878  mov     r14, r8
0x18002187b  mov     ecx, 100h; cb
0x180021880  mov     r13, rdx
0x180021883  call    cs:__imp_CoTaskMemAlloc
0x180021889  mov     rbx, rax
0x18002188c  test    rax, rax
0x18002188f  jz      loc_180021B06
0x180021895  xor     eax, eax
0x180021897  mov     [rbx+74h], ax
0x18002189b  mov     [rbx+0B8h], ax
0x1800218a2  mov     rcx, [rsi+0B0h]
0x1800218a9  mov     rdx, [rsi+0A8h]
0x1800218b0  mov     rax, [rcx+10h]
0x1800218b4  mov     [rdx+20h], rax
0x1800218b8  mov     rax, [rcx+18h]
0x1800218bc  mov     [rdx+28h], rax
0x1800218c0  mov     rax, [rcx+20h]
0x1800218c4  mov     rcx, r13; this
0x1800218c7  mov     [rdx+30h], rax
0x1800218cb  lea     rdx, [rbx+24h]; struct _GUID *
0x1800218cf  call    ?GetClass@PDocFile@@QEAAJPEAU_GUID@@@Z; PDocFile::GetClass(_GUID *)
0x1800218d4  mov     edi, eax
0x1800218d6  test    eax, eax
0x1800218d8  js      loc_180021B0D
0x1800218de  mov     rax, [r14]
0x1800218e1  lea     rdx, [rbx+24h]
0x1800218e5  mov     rcx, r14
0x1800218e8  mov     rax, [rax+78h]
0x1800218ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218f1  mov     ebp, 80000000h
0x1800218f6  mov     edi, eax
0x1800218f8  add     eax, ebp
0x1800218fa  mov     r12d, 80030001h
0x180021900  test    ebp, eax
0x180021902  jz      loc_180021B29
0x180021908  mov     rcx, [rsi+0B0h]
0x18002190f  mov     rdx, [rsi+0A8h]
0x180021916  mov     rax, [rcx+10h]
0x18002191a  mov     [rdx+20h], rax
0x18002191e  mov     rax, [rcx+18h]
0x180021922  mov     [rdx+28h], rax
0x180021926  mov     rax, [rcx+20h]
0x18002192a  mov     rcx, r13; this
0x18002192d  mov     [rdx+30h], rax
0x180021931  lea     rdx, [rbx+20h]; unsigned int *
0x180021935  call    ?GetStateBits@PDocFile@@QEAAJPEAK@Z; PDocFile::GetStateBits(ulong *)
0x18002193a  mov     edi, eax
0x18002193c  test    eax, eax
0x18002193e  js      loc_180021B0D
0x180021944  mov     rax, [r14]
0x180021947  or      r8d, 0FFFFFFFFh
0x18002194b  mov     edx, [rbx+20h]
0x18002194e  mov     rcx, r14
0x180021951  mov     rax, [rax+80h]
0x180021958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002195d  mov     edi, eax
0x18002195f  add     eax, ebp
0x180021961  test    ebp, eax
0x180021963  jz      loc_180021B34
0x180021969  lea     rbp, [rbx+78h]
0x18002196d  mov     r15d, [rsp+0A8h+arg_20]
0x180021975  lea     r12, [rbx+34h]
0x180021979  mov     rcx, [rsi+0B0h]
0x180021980  xor     r9d, r9d; struct tagSTATSTG *
0x180021983  mov     rdx, [rsi+0A8h]
0x18002198a  mov     r8, rbp; struct SIterBuffer *
0x18002198d  mov     rax, [rcx+10h]
0x180021991  mov     [rdx+20h], rax
0x180021995  mov     rax, [rcx+18h]
0x180021999  mov     [rdx+28h], rax
0x18002199d  mov     rax, [rcx+20h]
0x1800219a1  mov     rcx, r13; this
0x1800219a4  mov     [rdx+30h], rax
0x1800219a8  mov     rdx, r12; struct CDfName *
0x1800219ab  call    ?FindGreaterEntry@PDocFile@@QEAAJPEBVCDfName@@PEAUSIterBuffer@@PEAUtagSTATSTG@@@Z; PDocFile::FindGreaterEntry(CDfName const *,SIterBuffer *,tagSTATSTG *)
0x1800219b0  mov     edi, eax
0x1800219b2  cmp     eax, 80030012h
0x1800219b7  jz      loc_180021B3F
0x1800219bd  test    eax, eax
0x1800219bf  js      loc_180021B0D
0x1800219c5  mov     rdx, rbp; struct CDfName *
0x1800219c8  mov     rcx, r12; this
0x1800219cb  call    ?Set@CDfName@@QEAAXPEBV1@@Z; CDfName::Set(CDfName const *)
0x1800219d0  mov     rax, [rsp+0A8h+arg_18]
0x1800219d8  test    rax, rax
0x1800219db  jnz     loc_180021B43
0x1800219e1  mov     eax, [rbx+0BCh]
0x1800219e7  cmp     eax, 1
0x1800219ea  jz      loc_180021B5B
0x1800219f0  cmp     eax, 2
0x1800219f3  jnz     short loc_1800219FE
0x1800219f5  test    al, r15b
0x1800219f8  jz      loc_180021979
0x1800219fe  sub     eax, 1
0x180021a01  jz      loc_180021B65
0x180021a07  cmp     eax, 1
0x180021a0a  jnz     loc_180021979
0x180021a10  mov     rcx, [rsi+0B0h]
0x180021a17  mov     r15d, 40h ; '@'
0x180021a1d  mov     rdx, [rsi+0A8h]
0x180021a24  mov     r9, rbx; struct PSStream **
0x180021a27  mov     r8d, r15d; unsigned int
0x180021a2a  mov     rax, [rcx+10h]
0x180021a2e  mov     [rdx+20h], rax
0x180021a32  mov     rax, [rcx+18h]
0x180021a36  mov     [rdx+28h], rax
0x180021a3a  mov     rax, [rcx+20h]
0x180021a3e  mov     rcx, r13; this
0x180021a41  mov     [rdx+30h], rax
0x180021a45  mov     rdx, rbp; struct CDfName *
0x180021a48  call    ?GetStream@PDocFile@@QEAAJPEBVCDfName@@KPEAPEAVPSStream@@@Z; PDocFile::GetStream(CDfName const *,ulong,PSStream * *)
0x180021a4d  mov     edi, eax
0x180021a4f  test    eax, eax
0x180021a51  js      loc_180021B0D
0x180021a57  lea     r12, [rbx+0C0h]
0x180021a5e  mov     r8, rbp; unsigned __int16 *
0x180021a61  mov     rcx, r12; unsigned __int16 *
0x180021a64  mov     edx, r15d; unsigned __int64
0x180021a67  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180021a6c  mov     rdx, [rsi+0B0h]; struct CPerContext *
0x180021a73  lea     rcx, [rsp+0A8h+var_58]; this
0x180021a78  call    ??0CSafeMultiHeap@@QEAA@PEAVCPerContext@@@Z; CSafeMultiHeap::CSafeMultiHeap(CPerContext *)
0x180021a7d  mov     rax, [r14]
0x180021a80  lea     r15, [rbx+8]
0x180021a84  mov     [rsp+0A8h+var_80], r15
0x180021a89  xor     r9d, r9d
0x180021a8c  mov     r8d, 1011h
0x180021a92  mov     dword ptr [rsp+0A8h+var_88], 0
0x180021a9a  mov     rdx, r12
0x180021a9d  mov     rcx, r14
0x180021aa0  mov     rax, [rax+18h]
0x180021aa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021aa9  lea     rcx, [rsp+0A8h+var_58]; this
0x180021aae  mov     edi, eax
0x180021ab0  test    eax, eax
0x180021ab2  js      loc_180021CC7
0x180021ab8  call    ??1CSafeMultiHeap@@QEAA@XZ; CSafeMultiHeap::~CSafeMultiHeap(void)
0x180021abd  mov     rax, [rsp+0A8h+arg_30]
0x180021ac5  mov     rcx, rsi; this
0x180021ac8  mov     r9, [rsp+0A8h+arg_28]; unsigned __int64 *
0x180021ad0  mov     r8, [r15]; struct IStream *
0x180021ad3  mov     rdx, [rbx]; struct PSStream *
0x180021ad6  mov     [rsp+0A8h+var_88], rax; unsigned __int64 *
0x180021adb  call    ?CopySStreamToIStream@CExposedDocFile@@AEAAJPEAVPSStream@@PEAUIStream@@PEA_K2@Z; CExposedDocFile::CopySStreamToIStream(PSStream *,IStream *,unsigned __int64 *,unsigned __int64 *)
0x180021ae0  mov     edi, eax
0x180021ae2  test    eax, eax
0x180021ae4  js      loc_180021C91
0x180021aea  mov     rcx, [rbx]; this
0x180021aed  call    ?Release@PBasicEntry@@QEAAXXZ; PBasicEntry::Release(void)
0x180021af2  mov     rcx, [r15]
0x180021af5  mov     rax, [rcx]
0x180021af8  mov     rax, [rax+10h]
0x180021afc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b01  jmp     loc_18002196D
0x180021b06  mov     edi, 80030008h
0x180021b0b  xor     ebx, ebx
0x180021b0d  mov     rcx, rbx; pv
0x180021b10  call    cs:__imp_CoTaskMemFree
0x180021b16  mov     eax, edi
0x180021b18  add     rsp, 68h
0x180021b1c  pop     r15
0x180021b1e  pop     r14
0x180021b20  pop     r13
0x180021b22  pop     r12
0x180021b24  pop     rdi
0x180021b25  pop     rsi
0x180021b26  pop     rbp
0x180021b27  pop     rbx
0x180021b28  retn
0x180021b29  cmp     edi, r12d
0x180021b2c  jz      loc_180021908
0x180021b32  jmp     short loc_180021B0D
0x180021b34  cmp     edi, r12d
0x180021b37  jz      loc_180021969
0x180021b3d  jmp     short loc_180021B0D
0x180021b3f  xor     edi, edi
0x180021b41  jmp     short loc_180021B0D
0x180021b43  mov     rdx, rax; unsigned __int16 **
0x180021b46  mov     rcx, rbp; struct CDfName *
0x180021b49  call    ?NameInSNB@@YAJPEBVCDfName@@PEAPEAG@Z; NameInSNB(CDfName const *,ushort * *)
0x180021b4e  test    eax, eax
0x180021b50  jz      loc_180021979
0x180021b56  jmp     loc_1800219E1
0x180021b5b  test    r15b, 1
0x180021b5f  jz      loc_180021979
0x180021b65  mov     rcx, [rsi+0B0h]
0x180021b6c  lea     r9, [rbx+10h]; struct PDocFile **
0x180021b70  mov     rdx, [rsi+0A8h]
0x180021b77  mov     r15d, 40h ; '@'
0x180021b7d  mov     r8d, r15d; unsigned int
0x180021b80  mov     rax, [rcx+10h]
0x180021b84  mov     [rdx+20h], rax
0x180021b88  mov     rax, [rcx+18h]
0x180021b8c  mov     [rdx+28h], rax
0x180021b90  mov     rax, [rcx+20h]
0x180021b94  mov     rcx, r13; this
0x180021b97  mov     [rdx+30h], rax
0x180021b9b  mov     rdx, rbp; struct CDfName *
0x180021b9e  call    ?GetDocFile@PDocFile@@QEAAJPEBVCDfName@@KPEAPEAV1@@Z; PDocFile::GetDocFile(CDfName const *,ulong,PDocFile * *)
0x180021ba3  mov     edi, eax
0x180021ba5  test    eax, eax
0x180021ba7  js      loc_180021B0D
0x180021bad  lea     r12, [rbx+0C0h]
0x180021bb4  mov     r8, rbp; unsigned __int16 *
0x180021bb7  mov     rcx, r12; unsigned __int16 *
0x180021bba  mov     edx, r15d; unsigned __int64
0x180021bbd  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180021bc2  mov     rdx, [rsi+0B0h]; struct CPerContext *
0x180021bc9  lea     rcx, [rsp+0A8h+var_68]; this
0x180021bce  call    ??0CSafeMultiHeap@@QEAA@PEAVCPerContext@@@Z; CSafeMultiHeap::CSafeMultiHeap(CPerContext *)
0x180021bd3  mov     rax, [r14]
0x180021bd6  lea     r15, [rbx+18h]
0x180021bda  xor     r9d, r9d
0x180021bdd  mov     [rsp+0A8h+var_80], r15
0x180021be2  mov     rdx, r12
0x180021be5  mov     dword ptr [rsp+0A8h+var_88], 0
0x180021bed  mov     rcx, r14
0x180021bf0  mov     rax, [rax+28h]
0x180021bf4  lea     r8d, [r9+11h]
0x180021bf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021bfd  mov     edi, eax
0x180021bff  cmp     eax, 80030050h
0x180021c04  jnz     short loc_180021C39
0x180021c06  mov     rax, [r14]
0x180021c09  mov     r9d, 12h
0x180021c0f  mov     [rsp+0A8h+var_78], r15
0x180021c14  xor     r8d, r8d
0x180021c17  mov     dword ptr [rsp+0A8h+var_80], 0
0x180021c1f  mov     rdx, r12
0x180021c22  mov     rcx, r14
0x180021c25  mov     [rsp+0A8h+var_88], 0
0x180021c2e  mov     rax, [rax+30h]
0x180021c32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c37  mov     edi, eax
0x180021c39  lea     rcx, [rsp+0A8h+var_68]; this
0x180021c3e  test    eax, eax
0x180021c40  js      loc_180021CC7
0x180021c46  call    ??1CSafeMultiHeap@@QEAA@XZ; CSafeMultiHeap::~CSafeMultiHeap(void)
0x180021c4b  mov     rax, [rsp+0A8h+arg_30]
0x180021c53  xor     r9d, r9d; unsigned __int16 **
0x180021c56  mov     r8, [r15]; struct IStorage *
0x180021c59  mov     rcx, rsi; this
0x180021c5c  mov     rdx, [rbx+10h]; struct PDocFile *
0x180021c60  mov     [rsp+0A8h+var_78], rax; unsigned __int64 *
0x180021c65  mov     rax, [rsp+0A8h+arg_28]
0x180021c6d  mov     [rsp+0A8h+var_80], rax; unsigned __int64 *
0x180021c72  mov     eax, [rsp+0A8h+arg_20]
0x180021c79  mov     dword ptr [rsp+0A8h+var_88], eax; unsigned int
0x180021c7d  call    ?CopyDocFileToIStorage@CExposedDocFile@@AEAAJPEAVPDocFile@@PEAUIStorage@@PEAPEAGKPEA_K3@Z; CExposedDocFile::CopyDocFileToIStorage(PDocFile *,IStorage *,ushort * *,ulong,unsigned __int64 *,unsigned __int64 *)
0x180021c82  mov     edi, eax
0x180021c84  test    eax, eax
0x180021c86  js      short loc_180021C95
0x180021c88  mov     rcx, [rbx+10h]
0x180021c8c  jmp     loc_180021AED
0x180021c91  lea     r15, [rbx+18h]
0x180021c95  cmp     dword ptr [rbx+0BCh], 1
0x180021c9c  jnz     short loc_180021CA3
0x180021c9e  mov     rcx, [r15]
0x180021ca1  jmp     short loc_180021CA7
0x180021ca3  mov     rcx, [rbx+8]
0x180021ca7  mov     rax, [rcx]
0x180021caa  mov     rax, [rax+10h]
0x180021cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021cb3  mov     rax, [r14]
0x180021cb6  mov     rdx, r12
0x180021cb9  mov     rcx, r14
0x180021cbc  mov     rax, [rax+60h]
0x180021cc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021cc5  jmp     short loc_180021CCC
0x180021cc7  call    ??1CSafeMultiHeap@@QEAA@XZ; CSafeMultiHeap::~CSafeMultiHeap(void)
0x180021ccc  cmp     dword ptr [rbx+0BCh], 1
0x180021cd3  jnz     short loc_180021CDB
0x180021cd5  mov     rcx, [rbx+10h]
0x180021cd9  jmp     short loc_180021CDE
0x180021cdb  mov     rcx, [rbx]; this
0x180021cde  call    ?Release@PBasicEntry@@QEAAXXZ; PBasicEntry::Release(void)
0x180021ce3  jmp     loc_180021B0D
```
