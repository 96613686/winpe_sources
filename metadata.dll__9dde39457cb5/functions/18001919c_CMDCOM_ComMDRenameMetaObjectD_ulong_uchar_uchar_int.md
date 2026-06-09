# CMDCOM::ComMDRenameMetaObjectD(ulong,uchar *,uchar *,int)

- ea: `0x18001919c`
- end: `0x180019403`
- name: `?ComMDRenameMetaObjectD@CMDCOM@@QEAAJKPEAE0H@Z`
- size: `615`
- prototype: `int(CMDCOM *__hidden this, unsigned int, unsigned __int8 *, unsigned __int8 *, int)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180019180`
- `0x180019410`

## callees

- `0x180002d60`
- `0x180003d30`
- `0x180004290`
- `0x1800147a4`
- `0x180014e58`
- `0x1800151f0`
- `0x180015560`
- `0x18001919c`
- `0x18001a0d0`
- `0x18001da80`
- `0x18001e4c0`
- `0x1800309d0`

## import_xrefs

- `msvcrt!_mbschr` at `0x180019220`
- `msvcrt!_mbschr` at `0x180019235`
- `msvcrt!_mbschr` at `0x180019220`
- `msvcrt!_mbschr` at `0x180019235`
- `msvcrt!wcschr` at `0x180019203`
- `msvcrt!wcschr` at `0x180019218`
- `msvcrt!wcschr` at `0x180019203`
- `msvcrt!wcschr` at `0x180019218`
- `IisRTL!?SafeCopy@STRAU@@QEAAHPEBD@Z` at `0x180019348`
- `IisRTL!?SafeCopy@STRAU@@QEAAHPEBD@Z` at `0x180019348`
- `IisRTL!?SafeCopy@STRAU@@QEAAHPEBG@Z` at `0x180019340`
- `IisRTL!?SafeCopy@STRAU@@QEAAHPEBG@Z` at `0x180019340`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800193d3`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800193d3`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180019270`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180019270`
- `IisRTL!??0BUFFER@@QEAA@XZ` at `0x1800192f6`
- `IisRTL!??0BUFFER@@QEAA@XZ` at `0x1800192f6`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x1800193c6`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x1800193c6`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180019392`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180019392`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDRenameMetaObjectD(CMDCOM *this, unsigned int a2, char *a3, wchar_t *a4, int a5)
{
  int NameFromPath; // edi
  void *v8; // rax
  struct CMDBaseObject *v9; // r14
  CMDBaseObject *v10; // rbx
  struct CMDBaseObject *ChildObject; // rax
  CMDBaseObject *v12; // rcx
  STRAU *v13; // rcx
  int v14; // eax
  struct CMDHandle *HandleObject; // rax
  CMDHandle *v16; // rbx
  unsigned __int16 *Ptr; // rax
  char *v19; // [rsp+30h] [rbp-D0h] BYREF
  struct CMDBaseObject *v20; // [rsp+38h] [rbp-C8h] BYREF
  char *v21; // [rsp+40h] [rbp-C0h] BYREF
  char v22[56]; // [rsp+48h] [rbp-B8h] BYREF
  char v23[512]; // [rsp+80h] [rbp-80h] BYREF

  v19 = a3;
  if ( !g_dwInitialized )
    return (unsigned int)-2146646016;
  if ( !a4 )
    return (unsigned int)-2147024809;
  if ( a5 )
  {
    if ( !wcschr(a4, 0x2Fu) )
    {
      v8 = wcschr(a4, 0x5Cu);
      goto LABEL_9;
    }
    return (unsigned int)-2147024809;
  }
  if ( _mbschr((const unsigned __int8 *)a4, 0x2Fu) )
    return (unsigned int)-2147024809;
  v8 = _mbschr((const unsigned __int8 *)a4, 0x5Cu);
LABEL_9:
  if ( v8 )
    return (unsigned int)-2147024809;
  v21 = (char *)a4;
  v20 = (struct CMDBaseObject *)a4;
  NameFromPath = ExtractNameFromPath((char **)&v20, v23, a5);
  if ( NameFromPath >= 0 )
  {
    CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)&g_LockMasterResource);
    v20 = 0;
    LODWORD(v19) = GetObjectFromPath(&v20, a2, 2, (const CHAR **)&v19, a5);
    NameFromPath = (int)v19;
    if ( (int)v19 >= 0 )
    {
      v9 = v20;
      v10 = (CMDBaseObject *)*((_QWORD *)v20 + 23);
      if ( v10 )
      {
        ChildObject = CMDBaseObject::GetChildObject(*((CMDBaseObject **)v20 + 23), &v21, (int *)&v19, a5);
        NameFromPath = (int)v19;
        if ( ChildObject )
          NameFromPath = -2147024713;
        if ( NameFromPath >= 0 )
        {
          BUFFER::BUFFER((BUFFER *)v22);
          LODWORD(v19) = 0;
          NameFromPath = GetObjectPath(v9, (struct BUFFER *)v22, (unsigned int *)&v19, g_pboMasterRoot, a5);
          if ( NameFromPath >= 0 )
          {
            CMDBaseObject::RemoveChildObjectFromHash(v12, v9);
            v13 = (struct CMDBaseObject *)((char *)v9 + 8);
            if ( a5 )
              v14 = STRAU::SafeCopy(v13, a4);
            else
              v14 = STRAU::SafeCopy(v13, (const char *)a4);
            if ( v14 && CMDBaseObject::GenerateKey(v9) )
            {
              NameFromPath = CMDBaseObject::AddChildObjectToHash(v10, v9);
              HandleObject = GetHandleObject(a2);
              ++*(_DWORD *)&g_dwSystemChangeNumber;
              v16 = HandleObject;
              INCREMENT_SCHEMA_CHANGE_NUMBER(a2, HandleObject, (char *)a4, a5);
              Ptr = (unsigned __int16 *)BUFFER::QueryPtr((BUFFER *)v22);
              CMDHandle::SetChangeData(v16, v9, 0x10u, 0, Ptr);
            }
            else
            {
              NameFromPath = -2147024882;
              CMDBaseObject::AddChildObjectToHash(v10, v9);
            }
          }
          BUFFER::~BUFFER((BUFFER *)v22);
        }
      }
      else
      {
        NameFromPath = -2147024809;
      }
    }
    CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)&g_LockMasterResource);
  }
  return (unsigned int)NameFromPath;
}

```

## disassembly

```asm
0x18001919c  push    rbp
0x18001919e  push    rbx
0x18001919f  push    rsi
0x1800191a0  push    rdi
0x1800191a1  push    r12
0x1800191a3  push    r14
0x1800191a5  push    r15
0x1800191a7  lea     rbp, [rsp-190h]
0x1800191af  sub     rsp, 290h
0x1800191b6  mov     rax, cs:__security_cookie
0x1800191bd  xor     rax, rsp
0x1800191c0  mov     [rbp+1C0h+var_40], rax
0x1800191c7  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x1800191cd  mov     rsi, r9
0x1800191d0  mov     r15d, [rbp+1C0h+arg_20]
0x1800191d7  mov     r12d, edx
0x1800191da  mov     [rsp+2C0h+var_290], r8
0x1800191df  test    eax, eax
0x1800191e1  jnz     short loc_1800191ED
0x1800191e3  mov     edi, 800CC800h
0x1800191e8  jmp     loc_1800193E0
0x1800191ed  test    rsi, rsi
0x1800191f0  jz      loc_1800193DB
0x1800191f6  mov     edx, 2Fh ; '/'; C
0x1800191fb  mov     rcx, rsi; Str
0x1800191fe  test    r15d, r15d
0x180019201  jz      short loc_180019220
0x180019203  call    cs:__imp_wcschr
0x180019209  test    rax, rax
0x18001920c  jnz     loc_1800193DB
0x180019212  lea     edx, [rax+5Ch]; Ch
0x180019215  mov     rcx, rsi; Str
0x180019218  call    cs:__imp_wcschr
0x18001921e  jmp     short loc_18001923B
0x180019220  call    cs:__imp__mbschr
0x180019226  test    rax, rax
0x180019229  jnz     loc_1800193DB
0x18001922f  lea     edx, [rax+5Ch]; C
0x180019232  mov     rcx, rsi; Str
0x180019235  call    cs:__imp__mbschr
0x18001923b  test    rax, rax
0x18001923e  jnz     loc_1800193DB
0x180019244  mov     r8d, r15d; int
0x180019247  mov     [rsp+2C0h+var_280], rsi
0x18001924c  lea     rdx, [rbp+1C0h+var_240]; char *
0x180019250  mov     [rsp+2C0h+var_288], rsi
0x180019255  lea     rcx, [rsp+2C0h+var_288]; char **
0x18001925a  call    ?ExtractNameFromPath@@YAJAEAPEADPEADH@Z; ExtractNameFromPath(char * &,char *,int)
0x18001925f  mov     edi, eax
0x180019261  test    eax, eax
0x180019263  js      loc_1800193E0
0x180019269  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180019270  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180019276  lea     r9, [rsp+2C0h+var_290]; char **
0x18001927b  mov     [rsp+2C0h+var_288], 0
0x180019284  mov     r8d, 2; unsigned int
0x18001928a  mov     dword ptr [rsp+2C0h+var_2A0], r15d; int
0x18001928f  mov     edx, r12d; unsigned int
0x180019292  lea     rcx, [rsp+2C0h+var_288]; struct CMDBaseObject **
0x180019297  call    ?GetObjectFromPath@@YAJAEAPEAVCMDBaseObject@@KKAEAPEADH@Z; GetObjectFromPath(CMDBaseObject * &,ulong,ulong,char * &,int)
0x18001929c  mov     dword ptr [rsp+2C0h+var_290], eax
0x1800192a0  mov     edi, eax
0x1800192a2  test    eax, eax
0x1800192a4  js      loc_1800193CC
0x1800192aa  mov     r14, [rsp+2C0h+var_288]
0x1800192af  mov     rbx, [r14+0B8h]
0x1800192b6  test    rbx, rbx
0x1800192b9  jnz     short loc_1800192C5
0x1800192bb  mov     edi, 80070057h
0x1800192c0  jmp     loc_1800193CC
0x1800192c5  mov     r9d, r15d; int
0x1800192c8  lea     r8, [rsp+2C0h+var_290]; int *
0x1800192cd  lea     rdx, [rsp+2C0h+var_280]; char **
0x1800192d2  mov     rcx, rbx; this
0x1800192d5  call    ?GetChildObject@CMDBaseObject@@QEAAPEAV1@AEAPEADPEAJH@Z; CMDBaseObject::GetChildObject(char * &,long *,int)
0x1800192da  mov     edi, dword ptr [rsp+2C0h+var_290]
0x1800192de  test    rax, rax
0x1800192e1  mov     ecx, 800700B7h
0x1800192e6  cmovnz  edi, ecx
0x1800192e9  test    edi, edi
0x1800192eb  js      loc_1800193CC
0x1800192f1  lea     rcx, [rsp+2C0h+var_278]
0x1800192f6  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x1800192fc  mov     r9, cs:?g_pboMasterRoot@@3PEAVCMDBaseObject@@EA; struct CMDBaseObject *
0x180019303  lea     r8, [rsp+2C0h+var_290]; unsigned int *
0x180019308  lea     rdx, [rsp+2C0h+var_278]; struct BUFFER *
0x18001930d  mov     dword ptr [rsp+2C0h+var_290], 0
0x180019315  mov     rcx, r14; this
0x180019318  mov     dword ptr [rsp+2C0h+var_2A0], r15d; int
0x18001931d  call    ?GetObjectPath@@YAJPEAVCMDBaseObject@@PEAVBUFFER@@PEAK0H@Z; GetObjectPath(CMDBaseObject *,BUFFER *,ulong *,CMDBaseObject *,int)
0x180019322  mov     edi, eax
0x180019324  test    eax, eax
0x180019326  js      loc_1800193C1
0x18001932c  mov     rdx, r14; struct CMDBaseObject *
0x18001932f  call    ?RemoveChildObjectFromHash@CMDBaseObject@@QEAAXPEAV1@@Z; CMDBaseObject::RemoveChildObjectFromHash(CMDBaseObject *)
0x180019334  lea     rcx, [r14+8]
0x180019338  mov     rdx, rsi
0x18001933b  test    r15d, r15d
0x18001933e  jz      short loc_180019348
0x180019340  call    cs:__imp_?SafeCopy@STRAU@@QEAAHPEBG@Z; STRAU::SafeCopy(ushort const *)
0x180019346  jmp     short loc_18001934E
0x180019348  call    cs:__imp_?SafeCopy@STRAU@@QEAAHPEBD@Z; STRAU::SafeCopy(char const *)
0x18001934e  test    eax, eax
0x180019350  jz      short loc_1800193B1
0x180019352  mov     rcx, r14; this
0x180019355  call    ?GenerateKey@CMDBaseObject@@AEAA_NXZ; CMDBaseObject::GenerateKey(void)
0x18001935a  test    al, al
0x18001935c  jz      short loc_1800193B1
0x18001935e  mov     rdx, r14; struct CMDBaseObject *
0x180019361  mov     rcx, rbx; this
0x180019364  call    ?AddChildObjectToHash@CMDBaseObject@@QEAAJPEAV1@@Z; CMDBaseObject::AddChildObjectToHash(CMDBaseObject *)
0x180019369  mov     ecx, r12d; unsigned int
0x18001936c  mov     edi, eax
0x18001936e  call    ?GetHandleObject@@YAPEAVCMDHandle@@K@Z; GetHandleObject(ulong)
0x180019373  inc     cs:?g_dwSystemChangeNumber@@3KA; ulong g_dwSystemChangeNumber
0x180019379  mov     r9d, r15d; int
0x18001937c  mov     r8, rsi; char *
0x18001937f  mov     rdx, rax; struct CMDHandle *
0x180019382  mov     ecx, r12d; unsigned int
0x180019385  mov     rbx, rax
0x180019388  call    ?INCREMENT_SCHEMA_CHANGE_NUMBER@@YAXKPEAVCMDHandle@@PEADH@Z; INCREMENT_SCHEMA_CHANGE_NUMBER(ulong,CMDHandle *,char *,int)
0x18001938d  lea     rcx, [rsp+2C0h+var_278]
0x180019392  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180019398  xor     r9d, r9d; unsigned int
0x18001939b  mov     rdx, r14; struct CMDBaseObject *
0x18001939e  mov     rcx, rbx; this
0x1800193a1  mov     [rsp+2C0h+var_2A0], rax; unsigned __int16 *
0x1800193a6  lea     r8d, [r9+10h]; unsigned int
0x1800193aa  call    ?SetChangeData@CMDHandle@@QEAAJPEAVCMDBaseObject@@KKPEAG@Z; CMDHandle::SetChangeData(CMDBaseObject *,ulong,ulong,ushort *)
0x1800193af  jmp     short loc_1800193C1
0x1800193b1  mov     rdx, r14; struct CMDBaseObject *
0x1800193b4  mov     rcx, rbx; this
0x1800193b7  mov     edi, 8007000Eh
0x1800193bc  call    ?AddChildObjectToHash@CMDBaseObject@@QEAAJPEAV1@@Z; CMDBaseObject::AddChildObjectToHash(CMDBaseObject *)
0x1800193c1  lea     rcx, [rsp+2C0h+var_278]
0x1800193c6  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800193cc  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x1800193d3  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x1800193d9  jmp     short loc_1800193E0
0x1800193db  mov     edi, 80070057h
0x1800193e0  mov     eax, edi
0x1800193e2  mov     rcx, [rbp+1C0h+var_40]
0x1800193e9  xor     rcx, rsp; StackCookie
0x1800193ec  call    __security_check_cookie
0x1800193f1  add     rsp, 290h
0x1800193f8  pop     r15
0x1800193fa  pop     r14
0x1800193fc  pop     r12
0x1800193fe  pop     rdi
0x1800193ff  pop     rsi
0x180019400  pop     rbx
0x180019401  pop     rbp
0x180019402  retn
```
