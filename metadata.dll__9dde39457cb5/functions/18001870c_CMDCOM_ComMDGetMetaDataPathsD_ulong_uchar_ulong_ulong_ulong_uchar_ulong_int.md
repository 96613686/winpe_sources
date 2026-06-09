# CMDCOM::ComMDGetMetaDataPathsD(ulong,uchar *,ulong,ulong,ulong,uchar *,ulong *,int)

- ea: `0x18001870c`
- end: `0x180018a0e`
- name: `?ComMDGetMetaDataPathsD@CMDCOM@@QEAAJKPEAEKKK0PEAKH@Z`
- size: `770`
- prototype: `int(CMDCOM *__hidden this, unsigned int, unsigned __int8 *, unsigned int, unsigned int, unsigned int, unsigned __int8 *, unsigned int *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800186c0`
- `0x180018a20`

## callees

- `0x180002d60`
- `0x180003d30`
- `0x180015234`
- `0x18001870c`
- `0x18001e4c0`
- `0x18003098e`
- `0x1800309d0`

## import_xrefs

- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800189d8`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800189d8`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800187ad`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800187ad`
- `IisRTL!??0BUFFER@@QEAA@XZ` at `0x1800187de`
- `IisRTL!??0BUFFER@@QEAA@XZ` at `0x1800187e8`
- `IisRTL!??0BUFFER@@QEAA@XZ` at `0x1800187de`
- `IisRTL!??0BUFFER@@QEAA@XZ` at `0x1800187e8`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x1800189c1`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x1800189cb`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x1800189c1`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x1800189cb`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001885e`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800188f4`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001885e`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800188f4`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDGetMetaDataPathsD(
        CMDCOM *this,
        unsigned int a2,
        char *a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned __int8 *a7,
        unsigned int *a8,
        int a9)
{
  int v10; // esi
  unsigned int v12; // r15d
  int ObjectFromPath; // edi
  struct CMDHandle *HandleObject; // rax
  unsigned __int8 *v15; // r13
  unsigned __int8 *v16; // r14
  struct CMDBaseObject *v17; // rbx
  struct CMDBaseObject **Ptr; // r10
  unsigned int v19; // eax
  int ObjectPath; // eax
  unsigned int v21; // ebx
  const void *v22; // rax
  unsigned int v23; // ecx
  __int64 v24; // rax
  unsigned __int8 *v25; // rcx
  unsigned int v27; // [rsp+30h] [rbp-99h] BYREF
  unsigned int v28; // [rsp+34h] [rbp-95h] BYREF
  struct CMDBaseObject *v29; // [rsp+38h] [rbp-91h] BYREF
  char *v30; // [rsp+40h] [rbp-89h] BYREF
  struct CMDBaseObject *v31; // [rsp+48h] [rbp-81h]
  struct CMDBaseObject **v32; // [rsp+50h] [rbp-79h]
  unsigned __int8 *v33; // [rsp+58h] [rbp-71h]
  unsigned int *v34; // [rsp+60h] [rbp-69h]
  _BYTE v35[48]; // [rsp+68h] [rbp-61h] BYREF
  _BYTE v36[48]; // [rsp+98h] [rbp-31h] BYREF

  v10 = (int)a7;
  v33 = a7;
  v34 = a8;
  v12 = (a9 != 0) + 1;
  v29 = 0;
  v30 = a3;
  if ( g_dwInitialized )
  {
    if ( a6 && !a7 || a5 >= 6 || !a8 )
      return (unsigned int)-2147024809;
    CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)&g_LockMasterResource);
    ObjectFromPath = GetObjectFromPath(&v29, a2, 1, (const CHAR **)&v30, a9);
    if ( ObjectFromPath < 0 )
      goto LABEL_40;
    BUFFER::BUFFER((BUFFER *)v36);
    BUFFER::BUFFER((BUFFER *)v35);
    HandleObject = GetHandleObject(a2);
    if ( HandleObject )
    {
      v31 = (struct CMDBaseObject *)*((_QWORD *)HandleObject + 3);
      v28 = 0;
      ObjectFromPath = CMDBaseObject::GetDataRecursive(v29, (struct BUFFER *)v35, a4, a5, &v28);
      if ( ObjectFromPath >= 0 )
      {
        v15 = &a7[a6 * v12];
        if ( v28 )
        {
          v16 = a7;
          v17 = (struct CMDBaseObject *)a7;
          Ptr = (struct CMDBaseObject **)BUFFER::QueryPtr((BUFFER *)v35);
          v32 = Ptr;
          v19 = 0;
          LODWORD(v30) = 0;
          if ( v28 )
          {
            do
            {
              if ( ((ObjectFromPath + 0x80000000) & 0x80000000) == 0 && ObjectFromPath != -2147024774 )
                break;
              v27 = 0;
              ObjectPath = GetObjectPath(Ptr[v19], (struct BUFFER *)v36, &v27, v31, a9);
              if ( ObjectPath >= 0 )
              {
                v29 = (struct CMDBaseObject *)&v16[v12 * (v27 + 2)];
                if ( v15 >= (unsigned __int8 *)v29 )
                {
                  v21 = v27 * v12;
                  v22 = BUFFER::QueryPtr((BUFFER *)v36);
                  memcpy_0(v16, v22, v21);
                  v23 = v27;
                  v17 = v29;
                  if ( a9 )
                  {
                    *(_WORD *)&v16[2 * v27] = 47;
                    *(_WORD *)&v16[2 * v23 + 2] = 0;
                  }
                  else
                  {
                    v24 = v27 + 1;
                    v16[v27] = 47;
                    v16[v24] = 0;
                  }
                }
                else
                {
                  ObjectFromPath = -2147024774;
                  v17 = (struct CMDBaseObject *)&v16[v12 * (v27 + 2)];
                }
              }
              else
              {
                ObjectFromPath = ObjectPath;
              }
              v16 = (unsigned __int8 *)v17;
              Ptr = v32;
              v19 = (_DWORD)v30 + 1;
              LODWORD(v30) = v19;
            }
            while ( v19 < v28 );
            v10 = (int)v33;
          }
          v25 = &v16[v12];
          if ( ObjectFromPath >= 0 )
          {
            if ( v25 > v15 )
            {
              ObjectFromPath = -2147024774;
            }
            else if ( a9 )
            {
              *(_WORD *)v16 = 0;
            }
            else
            {
              *v16 = 0;
            }
          }
          if ( ObjectFromPath != -2147024774 )
            goto LABEL_39;
        }
        else
        {
          if ( !a7 )
            goto LABEL_39;
          v25 = &a7[2 * v12];
          if ( v25 <= v15 )
          {
            if ( a9 )
              *(_DWORD *)a7 = 0;
            else
              *(_WORD *)a7 = 0;
            goto LABEL_39;
          }
          ObjectFromPath = -2147024774;
        }
        *v34 = ((int)v25 - v10) / v12;
      }
    }
    else
    {
      ObjectFromPath = -2146646015;
    }
LABEL_39:
    BUFFER::~BUFFER((BUFFER *)v35);
    BUFFER::~BUFFER((BUFFER *)v36);
LABEL_40:
    CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)&g_LockMasterResource);
    return (unsigned int)ObjectFromPath;
  }
  return (unsigned int)-2146646016;
}

```

## disassembly

```asm
0x18001870c  mov     [rsp-8+arg_0], rbx
0x180018711  push    rbp
0x180018712  push    rsi
0x180018713  push    rdi
0x180018714  push    r12
0x180018716  push    r13
0x180018718  push    r14
0x18001871a  push    r15
0x18001871c  lea     rbp, [rsp-7]
0x180018721  sub     rsp, 0D0h
0x180018728  mov     rax, cs:__security_cookie
0x18001872f  xor     rax, rsp
0x180018732  mov     [rbp+37h+var_38], rax
0x180018736  mov     r14d, [rbp+37h+arg_40]
0x18001873d  mov     r13d, r9d
0x180018740  mov     rsi, [rbp+37h+arg_30]
0x180018744  mov     eax, r14d
0x180018747  mov     rcx, [rbp+37h+arg_38]
0x18001874b  neg     eax
0x18001874d  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x180018753  mov     r12d, edx
0x180018756  sbb     r15d, r15d
0x180018759  mov     [rbp+37h+var_A8], rsi
0x18001875d  neg     r15d
0x180018760  mov     [rbp+37h+var_A0], rcx
0x180018764  inc     r15d
0x180018767  mov     [rsp+100h+var_C8], 0
0x180018770  mov     [rsp+100h+var_C0], r8
0x180018775  test    eax, eax
0x180018777  jnz     short loc_180018783
0x180018779  mov     edi, 800CC800h
0x18001877e  jmp     loc_1800189E5
0x180018783  mov     ebx, [rbp+37h+arg_28]
0x180018786  test    ebx, ebx
0x180018788  jz      short loc_180018793
0x18001878a  test    rsi, rsi
0x18001878d  jz      loc_1800189E0
0x180018793  cmp     [rbp+37h+arg_20], 6
0x180018797  jnb     loc_1800189E0
0x18001879d  test    rcx, rcx
0x1800187a0  jz      loc_1800189E0
0x1800187a6  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x1800187ad  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x1800187b3  lea     r9, [rsp+100h+var_C0]; char **
0x1800187b8  mov     dword ptr [rsp+100h+var_E0], r14d; int
0x1800187bd  mov     r8d, 1; unsigned int
0x1800187c3  lea     rcx, [rsp+100h+var_C8]; struct CMDBaseObject **
0x1800187c8  mov     edx, r12d; unsigned int
0x1800187cb  call    ?GetObjectFromPath@@YAJAEAPEAVCMDBaseObject@@KKAEAPEADH@Z; GetObjectFromPath(CMDBaseObject * &,ulong,ulong,char * &,int)
0x1800187d0  mov     edi, eax
0x1800187d2  test    eax, eax
0x1800187d4  js      loc_1800189D1
0x1800187da  lea     rcx, [rbp+37h+var_68]
0x1800187de  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x1800187e4  lea     rcx, [rbp+37h+var_98]
0x1800187e8  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x1800187ee  mov     ecx, r12d; unsigned int
0x1800187f1  call    ?GetHandleObject@@YAPEAVCMDHandle@@K@Z; GetHandleObject(ulong)
0x1800187f6  xor     r12d, r12d
0x1800187f9  test    rax, rax
0x1800187fc  jnz     short loc_180018808
0x1800187fe  mov     edi, 800CC801h
0x180018803  jmp     loc_1800189BD
0x180018808  mov     rax, [rax+18h]
0x18001880c  lea     rdx, [rbp+37h+var_98]; struct BUFFER *
0x180018810  mov     r9d, [rbp+37h+arg_20]; unsigned int
0x180018814  mov     r8d, r13d; unsigned int
0x180018817  mov     rcx, [rsp+100h+var_C8]; this
0x18001881c  mov     [rsp+100h+var_B8], rax
0x180018821  lea     rax, [rsp+100h+var_CC]
0x180018826  mov     [rsp+100h+var_E0], rax; unsigned int *
0x18001882b  mov     [rsp+100h+var_CC], r12d
0x180018830  call    ?GetDataRecursive@CMDBaseObject@@QEAAJPEAVBUFFER@@KKAEAK@Z; CMDBaseObject::GetDataRecursive(BUFFER *,ulong,ulong,ulong &)
0x180018835  mov     edi, eax
0x180018837  test    eax, eax
0x180018839  js      loc_1800189BD
0x18001883f  mov     r13d, r15d
0x180018842  imul    r13d, ebx
0x180018846  add     r13, rsi
0x180018849  cmp     [rsp+100h+var_CC], r12d
0x18001884e  jz      loc_180018988
0x180018854  lea     rcx, [rbp+37h+var_98]
0x180018858  mov     r14, rsi
0x18001885b  mov     rbx, rsi
0x18001885e  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180018864  mov     r10, rax
0x180018867  mov     [rbp+37h+var_B0], rax
0x18001886b  mov     eax, r12d
0x18001886e  mov     r12d, 8007007Ah
0x180018874  mov     dword ptr [rsp+100h+var_C0], eax
0x180018878  cmp     [rsp+100h+var_CC], eax
0x18001887c  jbe     loc_180018958
0x180018882  mov     esi, [rbp+37h+arg_40]
0x180018888  mov     edx, 80000000h
0x18001888d  lea     ecx, [rdi+rdx]
0x180018890  test    edx, ecx
0x180018892  jnz     short loc_18001889D
0x180018894  cmp     edi, r12d
0x180018897  jnz     loc_180018954
0x18001889d  mov     r9, [rsp+100h+var_B8]; struct CMDBaseObject *
0x1800188a2  lea     r8, [rsp+100h+var_D0]; unsigned int *
0x1800188a7  mov     ecx, eax
0x1800188a9  lea     rdx, [rbp+37h+var_68]; struct BUFFER *
0x1800188ad  mov     [rsp+100h+var_D0], 0
0x1800188b5  mov     dword ptr [rsp+100h+var_E0], esi; int
0x1800188b9  mov     rcx, [r10+rcx*8]; this
0x1800188bd  call    ?GetObjectPath@@YAJPEAVCMDBaseObject@@PEAVBUFFER@@PEAK0H@Z; GetObjectPath(CMDBaseObject *,BUFFER *,ulong *,CMDBaseObject *,int)
0x1800188c2  test    eax, eax
0x1800188c4  jns     short loc_1800188CA
0x1800188c6  mov     edi, eax
0x1800188c8  jmp     short loc_180018934
0x1800188ca  mov     ecx, [rsp+100h+var_D0]
0x1800188ce  lea     eax, [rcx+2]
0x1800188d1  imul    eax, r15d
0x1800188d5  add     rax, r14
0x1800188d8  mov     [rsp+100h+var_C8], rax
0x1800188dd  cmp     r13, rax
0x1800188e0  jnb     short loc_1800188EA
0x1800188e2  mov     edi, r12d
0x1800188e5  mov     rbx, rax
0x1800188e8  jmp     short loc_180018934
0x1800188ea  mov     ebx, r15d
0x1800188ed  imul    ebx, ecx
0x1800188f0  lea     rcx, [rbp+37h+var_68]
0x1800188f4  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800188fa  mov     r8d, ebx; Size
0x1800188fd  mov     rcx, r14; void *
0x180018900  mov     rdx, rax; Src
0x180018903  call    memcpy_0
0x180018908  mov     ecx, [rsp+100h+var_D0]
0x18001890c  mov     rbx, [rsp+100h+var_C8]
0x180018911  test    esi, esi
0x180018913  jz      short loc_180018927
0x180018915  mov     word ptr [r14+rcx*2], 2Fh ; '/'
0x18001891c  inc     ecx
0x18001891e  xor     eax, eax
0x180018920  mov     [r14+rcx*2], ax
0x180018925  jmp     short loc_180018934
0x180018927  lea     eax, [rcx+1]
0x18001892a  mov     byte ptr [rcx+r14], 2Fh ; '/'
0x18001892f  mov     byte ptr [rax+r14], 0
0x180018934  mov     eax, dword ptr [rsp+100h+var_C0]
0x180018938  mov     r14, rbx
0x18001893b  mov     r10, [rbp+37h+var_B0]
0x18001893f  inc     eax
0x180018941  mov     edx, 80000000h
0x180018946  mov     dword ptr [rsp+100h+var_C0], eax
0x18001894a  cmp     eax, [rsp+100h+var_CC]
0x18001894e  jb      loc_18001888D
0x180018954  mov     rsi, [rbp+37h+var_A8]
0x180018958  mov     ecx, r15d
0x18001895b  add     rcx, r14
0x18001895e  test    edi, edi
0x180018960  js      short loc_180018981
0x180018962  cmp     rcx, r13
0x180018965  ja      short loc_18001897E
0x180018967  cmp     [rbp+37h+arg_40], 0
0x18001896e  jz      short loc_180018978
0x180018970  xor     eax, eax
0x180018972  mov     [r14], ax
0x180018976  jmp     short loc_180018981
0x180018978  mov     byte ptr [r14], 0
0x18001897c  jmp     short loc_180018981
0x18001897e  mov     edi, r12d
0x180018981  cmp     edi, r12d
0x180018984  jnz     short loc_1800189BD
0x180018986  jmp     short loc_1800189AE
0x180018988  test    rsi, rsi
0x18001898b  jz      short loc_1800189BD
0x18001898d  lea     ecx, [r15+r15]
0x180018991  add     rcx, rsi
0x180018994  cmp     rcx, r13
0x180018997  ja      short loc_1800189A9
0x180018999  test    r14d, r14d
0x18001899c  jz      short loc_1800189A3
0x18001899e  mov     [rsi], r12d
0x1800189a1  jmp     short loc_1800189BD
0x1800189a3  mov     [rsi], r12w
0x1800189a7  jmp     short loc_1800189BD
0x1800189a9  mov     edi, 8007007Ah
0x1800189ae  sub     ecx, esi
0x1800189b0  xor     edx, edx
0x1800189b2  mov     eax, ecx
0x1800189b4  div     r15d
0x1800189b7  mov     rdx, [rbp+37h+var_A0]
0x1800189bb  mov     [rdx], eax
0x1800189bd  lea     rcx, [rbp+37h+var_98]
0x1800189c1  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800189c7  lea     rcx, [rbp+37h+var_68]
0x1800189cb  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800189d1  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x1800189d8  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x1800189de  jmp     short loc_1800189E5
0x1800189e0  mov     edi, 80070057h
0x1800189e5  mov     eax, edi
0x1800189e7  mov     rcx, [rbp+37h+var_38]
0x1800189eb  xor     rcx, rsp; StackCookie
0x1800189ee  call    __security_check_cookie
0x1800189f3  mov     rbx, [rsp+100h+arg_0]
0x1800189fb  add     rsp, 0D0h
0x180018a02  pop     r15
0x180018a04  pop     r14
0x180018a06  pop     r13
0x180018a08  pop     r12
0x180018a0a  pop     rdi
0x180018a0b  pop     rsi
0x180018a0c  pop     rbp
0x180018a0d  retn
```
