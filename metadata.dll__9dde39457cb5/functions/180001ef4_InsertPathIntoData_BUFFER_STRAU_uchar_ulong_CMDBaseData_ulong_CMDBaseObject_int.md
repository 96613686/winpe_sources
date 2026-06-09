# InsertPathIntoData(BUFFER *,STRAU *,uchar * *,ulong *,CMDBaseData *,ulong,CMDBaseObject *,int)

- ea: `0x180001ef4`
- end: `0x18000229e`
- name: `?InsertPathIntoData@@YAJPEAVBUFFER@@PEAVSTRAU@@PEAPEAEPEAKPEAVCMDBaseData@@KPEAVCMDBaseObject@@H@Z`
- size: `938`
- prototype: `int(struct BUFFER *, struct STRAU *, unsigned __int8 **, unsigned int *, struct CMDBaseData *, unsigned int, struct CMDBaseObject *, int)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x180001340`
- `0x180005900`
- `0x180017a70`

## callees

- `0x180001ef4`
- `0x180002d60`
- `0x180015300`
- `0x18001e4c0`
- `0x180020814`
- `0x18003098e`
- `0x1800309d0`
- `0x180031010`

## import_xrefs

- `IisRTL!?QueryStrA@STRAU@@QEAAPEADXZ` at `0x1800021a6`
- `IisRTL!?QueryStrA@STRAU@@QEAAPEADXZ` at `0x1800021a6`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x1800020cb`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x18000225c`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x1800020cb`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x18000225c`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180001fc1`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000209b`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000210f`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180002183`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800021ea`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180001fc1`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000209b`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000210f`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180002183`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800021ea`
- `IisRTL!??0BUFFER@@QEAA@XZ` at `0x180001f4a`
- `IisRTL!??0BUFFER@@QEAA@XZ` at `0x180001f4a`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180002276`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180002276`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180001fe0`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180002068`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800020b3`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180002120`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180002153`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180002197`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800021fb`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180002233`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180001fe0`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180002068`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800020b3`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180002120`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180002153`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180002197`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800021fb`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180002233`

## pseudocode

```c
__int64 __fastcall InsertPathIntoData(
        struct BUFFER *a1,
        struct STRAU *a2,
        unsigned __int8 **a3,
        unsigned int *a4,
        struct CMDBaseData *a5,
        unsigned int a6,
        struct CMDBaseObject *a7,
        unsigned int a8)
{
  struct STRAU *v9; // r13
  struct CMDHandle *HandleObject; // rax
  int ObjectPath; // esi
  unsigned int ObjectLevel; // eax
  struct CMDBaseObject *v13; // r9
  unsigned int v14; // edx
  __int64 v15; // rdi
  unsigned int v16; // ebx
  _WORD *Ptr; // rax
  __int64 v18; // rdx
  int v19; // eax
  int v20; // eax
  __int64 v21; // rax
  __int64 (__fastcall *v22)(struct CMDBaseData *, _QWORD, _QWORD); // rax
  const wchar_t *v23; // r15
  char *v24; // rax
  size_t v25; // r13
  __int64 v26; // rdi
  size_t v27; // rbx
  char *v28; // rdi
  char *Str; // rax
  __int64 v30; // rax
  unsigned int v31; // ebx
  unsigned __int8 *v32; // rax
  const wchar_t *v33; // r14
  char *v34; // rax
  size_t v35; // r15
  unsigned int v36; // r13d
  char *v37; // rdi
  char *StrA; // rax
  __int64 v39; // rax
  unsigned __int8 *v40; // rax
  const wchar_t *v41; // rbx
  char *v42; // rax
  char *v43; // rax
  size_t Size; // [rsp+30h] [rbp-61h] BYREF
  STRAU *v46; // [rsp+38h] [rbp-59h]
  unsigned int v47; // [rsp+40h] [rbp-51h]
  unsigned __int8 **v48; // [rsp+48h] [rbp-49h]
  unsigned int *v49; // [rsp+50h] [rbp-41h]
  _BYTE v50[48]; // [rsp+58h] [rbp-39h] BYREF

  v9 = a2;
  v49 = a4;
  v48 = a3;
  v46 = a2;
  LODWORD(Size) = 0;
  BUFFER::BUFFER((BUFFER *)v50);
  HandleObject = GetHandleObject(a6);
  if ( !HandleObject )
  {
    ObjectPath = -2146646015;
    goto LABEL_43;
  }
  CMDBaseObject::GetObjectLevel(*((CMDBaseObject **)HandleObject + 3));
  ObjectLevel = CMDBaseObject::GetObjectLevel(a7);
  if ( v14 > ObjectLevel )
  {
    ObjectPath = 837639;
    goto LABEL_43;
  }
  ObjectPath = GetObjectPath(a7, (struct BUFFER *)v50, (unsigned int *)&Size, v13, a8);
  if ( ObjectPath )
    goto LABEL_43;
  v15 = (unsigned int)Size;
  if ( !BUFFER::Resize((BUFFER *)v50, (Size + 2) * ((a8 != 0) + 1)) )
  {
LABEL_7:
    ObjectPath = -2147024882;
    goto LABEL_43;
  }
  v16 = 0;
  LODWORD(Size) = 0;
  ObjectPath = 0;
  Ptr = BUFFER::QueryPtr((BUFFER *)v50);
  if ( a8 )
  {
    Ptr[v15] = 47;
    Ptr[(unsigned int)(v15 + 1)] = 0;
  }
  else
  {
    *((_BYTE *)Ptr + v15) = 47;
    *((_BYTE *)Ptr + (unsigned int)(v15 + 1)) = 0;
  }
  v19 = (*(__int64 (__fastcall **)(struct CMDBaseData *, __int64, _WORD *))(*(_QWORD *)a5 + 8LL))(a5, v18, Ptr) - 2;
  if ( v19 )
  {
    v20 = v19 - 2;
    if ( v20 )
    {
      if ( v20 != 1 )
        goto LABEL_43;
      v21 = *(_QWORD *)a5;
      LODWORD(Size) = 0;
      v22 = *(__int64 (__fastcall **)(struct CMDBaseData *, _QWORD, _QWORD))(v21 + 24);
      if ( a8 )
      {
        v23 = (const wchar_t *)v22(a5, a8, 0);
        while ( *v23 )
        {
          v24 = (char *)BUFFER::QueryPtr((BUFFER *)v50);
          ObjectPath = MakeInsertPathData(v9, v24, v23, (unsigned int *)&Size, a8);
          if ( ObjectPath >= 0 )
          {
            v25 = (unsigned int)Size;
            v47 = v16 + Size;
            if ( BUFFER::Resize(a1, v16 + Size) )
            {
              v26 = v16;
              v27 = v25;
              v28 = (char *)BUFFER::QueryPtr(a1) + v26;
              v9 = v46;
              Str = STRAU::QueryStr(v46, a8);
              memcpy_0(v28, Str, v27);
              v16 = v47;
            }
            else
            {
              v9 = v46;
              ObjectPath = -2147024882;
            }
          }
          v30 = -1;
          do
            ++v30;
          while ( v23[v30] );
          v23 += v30 + 1;
          if ( ObjectPath < 0 )
            goto LABEL_43;
        }
        v31 = v16 + 2;
        if ( !BUFFER::Resize(a1, v31) )
          goto LABEL_7;
        v32 = (unsigned __int8 *)BUFFER::QueryPtr(a1);
        *v48 = v32;
        *(_WORD *)&v32[2 * ((unsigned __int64)v31 >> 1) - 2] = 0;
      }
      else
      {
        v33 = (const wchar_t *)v22(a5, 0, 0);
        while ( *(_BYTE *)v33 )
        {
          v34 = (char *)BUFFER::QueryPtr((BUFFER *)v50);
          ObjectPath = MakeInsertPathData(v9, v34, v33, (unsigned int *)&Size, 0);
          if ( ObjectPath >= 0 )
          {
            v35 = (unsigned int)Size;
            v36 = Size + v16;
            if ( BUFFER::Resize(a1, Size + v16) )
            {
              v37 = (char *)BUFFER::QueryPtr(a1) + v16;
              StrA = STRAU::QueryStrA(v46);
              memcpy_0(v37, StrA, v35);
              v16 = v36;
            }
            else
            {
              ObjectPath = -2147024882;
            }
            v9 = v46;
          }
          v39 = -1;
          do
            ++v39;
          while ( *((_BYTE *)v33 + v39) );
          v33 = (const wchar_t *)((char *)v33 + v39 + 1);
          if ( ObjectPath < 0 )
            goto LABEL_43;
        }
        v31 = v16 + 1;
        if ( !BUFFER::Resize(a1, v31) )
          goto LABEL_7;
        v40 = (unsigned __int8 *)BUFFER::QueryPtr(a1);
        *v48 = v40;
        v40[v31 - 1] = 0;
      }
      *v49 = v31;
      goto LABEL_43;
    }
  }
  v41 = (const wchar_t *)(*(__int64 (__fastcall **)(struct CMDBaseData *, _QWORD, _QWORD))(*(_QWORD *)a5 + 24LL))(
                           a5,
                           a8,
                           0);
  v42 = (char *)BUFFER::QueryPtr((BUFFER *)v50);
  ObjectPath = MakeInsertPathData(v9, v42, v41, (unsigned int *)&Size, a8);
  if ( ObjectPath >= 0 )
  {
    v43 = STRAU::QueryStr(v9, a8);
    *v48 = (unsigned __int8 *)v43;
    *v49 = Size;
  }
LABEL_43:
  BUFFER::~BUFFER((BUFFER *)v50);
  return (unsigned int)ObjectPath;
}

```

## disassembly

```asm
0x180001ef4  push    rbp
0x180001ef6  push    rbx
0x180001ef7  push    rsi
0x180001ef8  push    rdi
0x180001ef9  push    r12
0x180001efb  push    r13
0x180001efd  push    r14
0x180001eff  push    r15
0x180001f01  lea     rbp, [rsp-7]
0x180001f06  sub     rsp, 98h
0x180001f0d  mov     rax, cs:__security_cookie
0x180001f14  xor     rax, rsp
0x180001f17  mov     [rbp+3Fh+var_48], rax
0x180001f1b  mov     r15, [rbp+3Fh+arg_20]
0x180001f1f  mov     r12, rcx
0x180001f22  mov     ebx, [rbp+3Fh+arg_28]
0x180001f25  lea     rcx, [rbp+3Fh+var_78]
0x180001f29  mov     rdi, [rbp+3Fh+arg_30]
0x180001f2d  mov     r13, rdx
0x180001f30  mov     r14d, [rbp+3Fh+arg_38]
0x180001f37  mov     [rbp+3Fh+var_80], r9
0x180001f3b  mov     [rbp+3Fh+var_88], r8
0x180001f3f  mov     [rbp+3Fh+var_98], rdx
0x180001f43  mov     dword ptr [rbp+3Fh+Size], 0
0x180001f4a  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x180001f50  mov     ecx, ebx; unsigned int
0x180001f52  call    ?GetHandleObject@@YAPEAVCMDHandle@@K@Z; GetHandleObject(ulong)
0x180001f57  test    rax, rax
0x180001f5a  jnz     short loc_180001F66
0x180001f5c  mov     esi, 800CC801h
0x180001f61  jmp     loc_180002272
0x180001f66  mov     r9, [rax+18h]
0x180001f6a  mov     rcx, r9; this
0x180001f6d  call    ?GetObjectLevel@CMDBaseObject@@QEAAKXZ; CMDBaseObject::GetObjectLevel(void)
0x180001f72  mov     rcx, rdi; this
0x180001f75  mov     edx, eax
0x180001f77  call    ?GetObjectLevel@CMDBaseObject@@QEAAKXZ; CMDBaseObject::GetObjectLevel(void)
0x180001f7c  cmp     edx, eax
0x180001f7e  jbe     short loc_180001F8A
0x180001f80  mov     esi, 0CC807h
0x180001f85  jmp     loc_180002272
0x180001f8a  lea     r8, [rbp+3Fh+Size]; unsigned int *
0x180001f8e  mov     [rsp+0D0h+var_B0], r14d; int
0x180001f93  lea     rdx, [rbp+3Fh+var_78]; struct BUFFER *
0x180001f97  mov     rcx, rdi; this
0x180001f9a  call    ?GetObjectPath@@YAJPEAVCMDBaseObject@@PEAVBUFFER@@PEAK0H@Z; GetObjectPath(CMDBaseObject *,BUFFER *,ulong *,CMDBaseObject *,int)
0x180001f9f  mov     esi, eax
0x180001fa1  test    eax, eax
0x180001fa3  jnz     loc_180002272
0x180001fa9  mov     edi, dword ptr [rbp+3Fh+Size]
0x180001fac  lea     rcx, [rbp+3Fh+var_78]
0x180001fb0  mov     eax, r14d
0x180001fb3  neg     eax
0x180001fb5  sbb     edx, edx
0x180001fb7  lea     eax, [rdi+2]
0x180001fba  neg     edx
0x180001fbc  inc     edx
0x180001fbe  imul    edx, eax
0x180001fc1  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180001fc7  test    al, al
0x180001fc9  jnz     short loc_180001FD5
0x180001fcb  mov     esi, 8007000Eh
0x180001fd0  jmp     loc_180002272
0x180001fd5  xor     ebx, ebx
0x180001fd7  lea     rcx, [rbp+3Fh+var_78]
0x180001fdb  mov     dword ptr [rbp+3Fh+Size], ebx
0x180001fde  xor     esi, esi
0x180001fe0  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180001fe6  mov     r8, rax
0x180001fe9  test    r14d, r14d
0x180001fec  jz      short loc_180001FFF
0x180001fee  mov     word ptr [rax+rdi*2], 2Fh ; '/'
0x180001ff4  lea     ecx, [rdi+1]
0x180001ff7  xor     edi, edi
0x180001ff9  mov     [rax+rcx*2], di
0x180001ffd  jmp     short loc_18000200C
0x180001fff  mov     byte ptr [rdi+rax], 2Fh ; '/'
0x180002003  lea     eax, [rdi+1]
0x180002006  xor     edi, edi
0x180002008  mov     [rax+r8], dil
0x18000200c  mov     rax, [r15]
0x18000200f  mov     rcx, r15
0x180002012  mov     rax, [rax+8]
0x180002016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000201b  sub     eax, 2
0x18000201e  jz      loc_180002217
0x180002024  sub     eax, 2
0x180002027  jz      loc_180002217
0x18000202d  cmp     eax, 1
0x180002030  jnz     loc_180002272
0x180002036  mov     rax, [r15]
0x180002039  xor     r8d, r8d
0x18000203c  mov     dword ptr [rbp+3Fh+Size], edi
0x18000203f  mov     rcx, r15
0x180002042  mov     rax, [rax+18h]
0x180002046  test    r14d, r14d
0x180002049  jz      loc_18000213C
0x18000204f  mov     edx, r14d
0x180002052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002057  mov     r15, rax
0x18000205a  cmp     [r15], di
0x18000205e  jz      loc_180002107
0x180002064  lea     rcx, [rbp+3Fh+var_78]
0x180002068  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000206e  lea     r9, [rbp+3Fh+Size]; unsigned int *
0x180002072  mov     [rsp+0D0h+var_B0], r14d; int
0x180002077  mov     rdx, rax; char *
0x18000207a  mov     r8, r15; char *
0x18000207d  mov     rcx, r13; struct STRAU *
0x180002080  call    ?MakeInsertPathData@@YAJPEAVSTRAU@@PEAD1PEAKH@Z; MakeInsertPathData(STRAU *,char *,char *,ulong *,int)
0x180002085  mov     esi, eax
0x180002087  test    eax, eax
0x180002089  js      short loc_1800020E4
0x18000208b  mov     r13d, dword ptr [rbp+3Fh+Size]
0x18000208f  mov     rcx, r12
0x180002092  lea     eax, [rbx+r13]
0x180002096  mov     edx, eax
0x180002098  mov     [rbp+3Fh+var_90], eax
0x18000209b  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800020a1  test    al, al
0x1800020a3  jnz     short loc_1800020B0
0x1800020a5  mov     r13, [rbp+3Fh+var_98]
0x1800020a9  mov     esi, 8007000Eh
0x1800020ae  jmp     short loc_1800020E4
0x1800020b0  mov     rcx, r12
0x1800020b3  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800020b9  mov     edi, ebx
0x1800020bb  mov     edx, r14d
0x1800020be  mov     rbx, r13
0x1800020c1  add     rdi, rax
0x1800020c4  mov     r13, [rbp+3Fh+var_98]
0x1800020c8  mov     rcx, r13
0x1800020cb  call    cs:__imp_?QueryStr@STRAU@@QEAAPEADH@Z; STRAU::QueryStr(int)
0x1800020d1  mov     r8, rbx; Size
0x1800020d4  mov     rcx, rdi; void *
0x1800020d7  mov     rdx, rax; Src
0x1800020da  call    memcpy_0
0x1800020df  mov     ebx, [rbp+3Fh+var_90]
0x1800020e2  xor     edi, edi
0x1800020e4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800020e8  inc     rax
0x1800020eb  cmp     [r15+rax*2], di
0x1800020f0  jnz     short loc_1800020E8
0x1800020f2  lea     r15, [r15+rax*2]
0x1800020f6  add     r15, 2
0x1800020fa  test    esi, esi
0x1800020fc  jns     loc_18000205A
0x180002102  jmp     loc_180002272
0x180002107  add     ebx, 2
0x18000210a  mov     rcx, r12
0x18000210d  mov     edx, ebx
0x18000210f  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180002115  test    al, al
0x180002117  jz      loc_180001FCB
0x18000211d  mov     rcx, r12
0x180002120  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180002126  mov     rcx, [rbp+3Fh+var_88]
0x18000212a  mov     edx, ebx
0x18000212c  shr     rdx, 1
0x18000212f  mov     [rcx], rax
0x180002132  mov     [rax+rdx*2-2], di
0x180002137  jmp     loc_18000220F
0x18000213c  xor     edx, edx
0x18000213e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002143  mov     r14, rax
0x180002146  cmp     [r14], dil
0x180002149  jz      loc_1800021E3
0x18000214f  lea     rcx, [rbp+3Fh+var_78]
0x180002153  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180002159  lea     r9, [rbp+3Fh+Size]; unsigned int *
0x18000215d  mov     [rsp+0D0h+var_B0], edi; int
0x180002161  mov     rdx, rax; char *
0x180002164  mov     r8, r14; char *
0x180002167  mov     rcx, r13; struct STRAU *
0x18000216a  call    ?MakeInsertPathData@@YAJPEAVSTRAU@@PEAD1PEAKH@Z; MakeInsertPathData(STRAU *,char *,char *,ulong *,int)
0x18000216f  mov     esi, eax
0x180002171  test    eax, eax
0x180002173  js      short loc_1800021C3
0x180002175  mov     r15d, dword ptr [rbp+3Fh+Size]
0x180002179  mov     rcx, r12
0x18000217c  lea     r13d, [r15+rbx]
0x180002180  mov     edx, r13d
0x180002183  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180002189  test    al, al
0x18000218b  jnz     short loc_180002194
0x18000218d  mov     esi, 8007000Eh
0x180002192  jmp     short loc_1800021BF
0x180002194  mov     rcx, r12
0x180002197  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000219d  mov     rcx, [rbp+3Fh+var_98]
0x1800021a1  mov     edi, ebx
0x1800021a3  add     rdi, rax
0x1800021a6  call    cs:__imp_?QueryStrA@STRAU@@QEAAPEADXZ; STRAU::QueryStrA(void)
0x1800021ac  mov     r8, r15; Size
0x1800021af  mov     rcx, rdi; void *
0x1800021b2  mov     rdx, rax; Src
0x1800021b5  call    memcpy_0
0x1800021ba  xor     edi, edi
0x1800021bc  mov     ebx, r13d
0x1800021bf  mov     r13, [rbp+3Fh+var_98]
0x1800021c3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800021c7  inc     rax
0x1800021ca  cmp     [r14+rax], dil
0x1800021ce  jnz     short loc_1800021C7
0x1800021d0  inc     r14
0x1800021d3  add     r14, rax
0x1800021d6  test    esi, esi
0x1800021d8  jns     loc_180002146
0x1800021de  jmp     loc_180002272
0x1800021e3  inc     ebx
0x1800021e5  mov     rcx, r12
0x1800021e8  mov     edx, ebx
0x1800021ea  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800021f0  test    al, al
0x1800021f2  jz      loc_180001FCB
0x1800021f8  mov     rcx, r12
0x1800021fb  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180002201  mov     rcx, [rbp+3Fh+var_88]
0x180002205  mov     [rcx], rax
0x180002208  lea     ecx, [rbx-1]
0x18000220b  mov     [rcx+rax], dil
0x18000220f  mov     rcx, [rbp+3Fh+var_80]
0x180002213  mov     [rcx], ebx
0x180002215  jmp     short loc_180002272
0x180002217  mov     rax, [r15]
0x18000221a  xor     r8d, r8d
0x18000221d  mov     edx, r14d
0x180002220  mov     rcx, r15
0x180002223  mov     rax, [rax+18h]
0x180002227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000222c  lea     rcx, [rbp+3Fh+var_78]
0x180002230  mov     rbx, rax
0x180002233  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180002239  lea     r9, [rbp+3Fh+Size]; unsigned int *
0x18000223d  mov     [rsp+0D0h+var_B0], r14d; int
0x180002242  mov     rdx, rax; char *
0x180002245  mov     r8, rbx; char *
0x180002248  mov     rcx, r13; struct STRAU *
0x18000224b  call    ?MakeInsertPathData@@YAJPEAVSTRAU@@PEAD1PEAKH@Z; MakeInsertPathData(STRAU *,char *,char *,ulong *,int)
0x180002250  mov     esi, eax
0x180002252  test    eax, eax
0x180002254  js      short loc_180002272
0x180002256  mov     edx, r14d
0x180002259  mov     rcx, r13
0x18000225c  call    cs:__imp_?QueryStr@STRAU@@QEAAPEADH@Z; STRAU::QueryStr(int)
0x180002262  mov     rcx, [rbp+3Fh+var_88]
0x180002266  mov     [rcx], rax
0x180002269  mov     rcx, [rbp+3Fh+var_80]
0x18000226d  mov     eax, dword ptr [rbp+3Fh+Size]
0x180002270  mov     [rcx], eax
0x180002272  lea     rcx, [rbp+3Fh+var_78]
0x180002276  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000227c  mov     eax, esi
0x18000227e  mov     rcx, [rbp+3Fh+var_48]
0x180002282  xor     rcx, rsp; StackCookie
0x180002285  call    __security_check_cookie
0x18000228a  add     rsp, 98h
0x180002291  pop     r15
0x180002293  pop     r14
0x180002295  pop     r13
0x180002297  pop     r12
0x180002299  pop     rdi
0x18000229a  pop     rsi
0x18000229b  pop     rbx
0x18000229c  pop     rbp
0x18000229d  retn
```
