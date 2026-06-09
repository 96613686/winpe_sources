# CMDCOM::ComMDGetChildPathsW(ulong,ushort const *,ulong,ushort *,ulong *)

- ea: `0x1800181f0`
- end: `0x1800183f3`
- name: `?ComMDGetChildPathsW@CMDCOM@@UEAAJKPEBGKPEAGPEAK@Z`
- size: `515`
- prototype: `int(CMDCOM *__hidden this, unsigned int, const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180003d30`
- `0x1800053b0`
- `0x180007810`
- `0x1800181f0`
- `0x18003098e`
- `0x1800309d0`

## import_xrefs

- `IisRTL!?Resize@BUFFER@@QEAA_NKK@Z` at `0x1800182ec`
- `IisRTL!?Resize@BUFFER@@QEAA_NKK@Z` at `0x180018345`
- `IisRTL!?Resize@BUFFER@@QEAA_NKK@Z` at `0x1800182ec`
- `IisRTL!?Resize@BUFFER@@QEAA_NKK@Z` at `0x180018345`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800183b8`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800183b8`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180018259`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180018259`
- `IisRTL!??0BUFFER@@QEAA@XZ` at `0x180018238`
- `IisRTL!??0BUFFER@@QEAA@XZ` at `0x180018238`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x1800183c2`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x1800183c2`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180018302`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180018353`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001837b`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180018302`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180018353`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001837b`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDGetChildPathsW(
        CMDCOM *this,
        unsigned int a2,
        char *a3,
        unsigned int a4,
        unsigned __int16 *a5,
        unsigned int *a6)
{
  int ObjectFromPath; // ebx
  __int64 v8; // rdi
  CMDBaseObject *i; // rax
  struct CMDBaseObject *v10; // r15
  char *Name; // r12
  __int64 v12; // rbx
  char *Ptr; // rax
  const void *v14; // rax
  CMDBaseObject *v16; // [rsp+30h] [rbp-50h] BYREF
  unsigned int v17; // [rsp+38h] [rbp-48h]
  char *v18; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v19[48]; // [rsp+48h] [rbp-38h] BYREF

  v16 = 0;
  v17 = a4;
  v18 = a3;
  BUFFER::BUFFER((BUFFER *)v19);
  if ( g_dwInitialized )
  {
    CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)&g_LockMasterResource);
    ObjectFromPath = GetObjectFromPath(&v16, a2, 1, (const CHAR **)&v18, 1);
    if ( ObjectFromPath >= 0 )
    {
      if ( v16 )
      {
        v8 = 0;
        for ( i = CMDBaseObject::NextChildObject(v16, 0); ; i = CMDBaseObject::NextChildObject(v16, v10) )
        {
          v10 = i;
          if ( !i )
            break;
          Name = CMDBaseObject::GetName(i, 1, 0);
          if ( !Name )
            goto LABEL_13;
          v12 = -1;
          do
            ++v12;
          while ( *(_WORD *)&Name[2 * v12] );
          v18 = (char *)(v12 + v8 + 1);
          if ( !BUFFER::Resize((BUFFER *)v19, 2 * (_DWORD)v18, 2 * (_DWORD)v18) )
            goto LABEL_13;
          Ptr = (char *)BUFFER::QueryPtr((BUFFER *)v19);
          memcpy_0(&Ptr[2 * v8], Name, 2 * v12 + 2);
          v8 = (__int64)v18;
        }
        if ( !v8 )
        {
          if ( !BUFFER::Resize((BUFFER *)v19, 2u, 0) )
          {
LABEL_13:
            ObjectFromPath = -2147024882;
            goto LABEL_23;
          }
          v8 = 1;
          *(_WORD *)BUFFER::QueryPtr((BUFFER *)v19) = 0;
        }
        if ( v17 < (unsigned __int64)(v8 + 1) )
        {
          ObjectFromPath = -2147024774;
          if ( a6 )
            *a6 = v8 + 1;
        }
        else if ( a5 )
        {
          v14 = BUFFER::QueryPtr((BUFFER *)v19);
          memcpy_0(a5, v14, 2 * v8);
          a5[v8] = 0;
          ObjectFromPath = 0;
        }
        else
        {
          ObjectFromPath = -2147024736;
        }
      }
      else
      {
        ObjectFromPath = -2147467259;
      }
    }
LABEL_23:
    CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)&g_LockMasterResource);
  }
  else
  {
    ObjectFromPath = -2146646016;
  }
  BUFFER::~BUFFER((BUFFER *)v19);
  return (unsigned int)ObjectFromPath;
}

```

## disassembly

```asm
0x1800181f0  mov     [rsp-28h+arg_0], rbx
0x1800181f5  mov     [rsp-28h+arg_18], rdi
0x1800181fa  push    rbp
0x1800181fb  push    r12
0x1800181fd  push    r13
0x1800181ff  push    r14
0x180018201  push    r15
0x180018203  mov     rbp, rsp
0x180018206  sub     rsp, 80h
0x18001820d  mov     rax, cs:__security_cookie
0x180018214  xor     rax, rsp
0x180018217  mov     [rbp+var_8], rax
0x18001821b  mov     r14, [rbp+arg_20]
0x18001821f  lea     rcx, [rbp+var_38]
0x180018223  mov     r13, [rbp+arg_28]
0x180018227  xor     r12d, r12d
0x18001822a  mov     [rbp+var_50], r12
0x18001822e  mov     ebx, edx
0x180018230  mov     [rbp+var_48], r9d
0x180018234  mov     [rbp+var_40], r8
0x180018238  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x18001823e  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x180018244  test    eax, eax
0x180018246  jnz     short loc_180018252
0x180018248  mov     ebx, 800CC800h
0x18001824d  jmp     loc_1800183BE
0x180018252  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180018259  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18001825f  lea     r9, [rbp+var_40]; char **
0x180018263  mov     [rsp+80h+var_60], 1; int
0x18001826b  mov     r8d, 1; unsigned int
0x180018271  lea     rcx, [rbp+var_50]; struct CMDBaseObject **
0x180018275  mov     edx, ebx; unsigned int
0x180018277  call    ?GetObjectFromPath@@YAJAEAPEAVCMDBaseObject@@KKAEAPEADH@Z; GetObjectFromPath(CMDBaseObject * &,ulong,ulong,char * &,int)
0x18001827c  mov     ebx, eax
0x18001827e  test    eax, eax
0x180018280  js      loc_1800183B1
0x180018286  cmp     [rbp+var_50], r12
0x18001828a  jnz     short loc_180018296
0x18001828c  mov     ebx, 80004005h
0x180018291  jmp     loc_1800183B1
0x180018296  mov     rcx, [rbp+var_50]; this
0x18001829a  xor     edx, edx; struct CMDBaseObject *
0x18001829c  mov     rdi, r12
0x18001829f  call    ?NextChildObject@CMDBaseObject@@QEAAPEAV1@PEAV1@@Z; CMDBaseObject::NextChildObject(CMDBaseObject *)
0x1800182a4  mov     r15, rax
0x1800182a7  test    rax, rax
0x1800182aa  jz      loc_180018336
0x1800182b0  xor     r8d, r8d; unsigned int *
0x1800182b3  mov     rcx, rax; this
0x1800182b6  lea     edx, [r8+1]; int
0x1800182ba  call    ?GetName@CMDBaseObject@@QEAAPEADHPEAK@Z; CMDBaseObject::GetName(int,ulong *)
0x1800182bf  mov     r12, rax
0x1800182c2  xor     eax, eax
0x1800182c4  test    r12, r12
0x1800182c7  jz      short loc_18001832F
0x1800182c9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800182cd  inc     rbx
0x1800182d0  cmp     [r12+rbx*2], ax
0x1800182d5  jnz     short loc_1800182CD
0x1800182d7  lea     rax, [rdi+1]
0x1800182db  add     rax, rbx
0x1800182de  lea     rcx, [rbp+var_38]
0x1800182e2  mov     [rbp+var_40], rax
0x1800182e6  lea     edx, [rax+rax]
0x1800182e9  mov     r8d, edx
0x1800182ec  call    cs:__imp_?Resize@BUFFER@@QEAA_NKK@Z; BUFFER::Resize(ulong,ulong)
0x1800182f2  test    al, al
0x1800182f4  jz      short loc_18001832F
0x1800182f6  lea     rcx, [rbp+var_38]
0x1800182fa  lea     rbx, ds:2[rbx*2]
0x180018302  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180018308  mov     r8, rbx; Size
0x18001830b  mov     rdx, r12; Src
0x18001830e  lea     rcx, [rax+rdi*2]; void *
0x180018312  call    memcpy_0
0x180018317  mov     rcx, [rbp+var_50]; this
0x18001831b  mov     rdx, r15; struct CMDBaseObject *
0x18001831e  mov     rdi, [rbp+var_40]
0x180018322  call    ?NextChildObject@CMDBaseObject@@QEAAPEAV1@PEAV1@@Z; CMDBaseObject::NextChildObject(CMDBaseObject *)
0x180018327  xor     r12d, r12d
0x18001832a  jmp     loc_1800182A4
0x18001832f  mov     ebx, 8007000Eh
0x180018334  jmp     short loc_1800183B1
0x180018336  test    rdi, rdi
0x180018339  jnz     short loc_180018362
0x18001833b  xor     r8d, r8d
0x18001833e  lea     edx, [rdi+2]
0x180018341  lea     rcx, [rbp+var_38]
0x180018345  call    cs:__imp_?Resize@BUFFER@@QEAA_NKK@Z; BUFFER::Resize(ulong,ulong)
0x18001834b  test    al, al
0x18001834d  jz      short loc_18001832F
0x18001834f  lea     rcx, [rbp+var_38]
0x180018353  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180018359  mov     edi, 1
0x18001835e  mov     [rax], r12w
0x180018362  mov     eax, [rbp+var_48]
0x180018365  lea     rcx, [rdi+1]
0x180018369  cmp     rax, rcx
0x18001836c  jb      short loc_1800183A0
0x18001836e  test    r14, r14
0x180018371  jz      short loc_180018399
0x180018373  lea     rcx, [rbp+var_38]
0x180018377  lea     rbx, [rdi+rdi]
0x18001837b  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180018381  mov     r8, rbx; Size
0x180018384  mov     rcx, r14; void *
0x180018387  mov     rdx, rax; Src
0x18001838a  call    memcpy_0
0x18001838f  mov     [rbx+r14], r12w
0x180018394  mov     ebx, r12d
0x180018397  jmp     short loc_1800183B1
0x180018399  mov     ebx, 800700A0h
0x18001839e  jmp     short loc_1800183B1
0x1800183a0  mov     ebx, 8007007Ah
0x1800183a5  test    r13, r13
0x1800183a8  jz      short loc_1800183B1
0x1800183aa  lea     eax, [rdi+1]
0x1800183ad  mov     [r13+0], eax
0x1800183b1  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x1800183b8  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x1800183be  lea     rcx, [rbp+var_38]
0x1800183c2  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800183c8  mov     eax, ebx
0x1800183ca  mov     rcx, [rbp+var_8]
0x1800183ce  xor     rcx, rsp; StackCookie
0x1800183d1  call    __security_check_cookie
0x1800183d6  lea     r11, [rsp+80h+var_s0]
0x1800183de  mov     rbx, [r11+30h]
0x1800183e2  mov     rdi, [r11+48h]
0x1800183e6  mov     rsp, r11
0x1800183e9  pop     r15
0x1800183eb  pop     r14
0x1800183ed  pop     r13
0x1800183ef  pop     r12
0x1800183f1  pop     rbp
0x1800183f2  retn
```
