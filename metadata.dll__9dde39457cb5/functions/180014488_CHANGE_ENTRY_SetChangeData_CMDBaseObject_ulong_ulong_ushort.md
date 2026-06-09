# CHANGE_ENTRY::SetChangeData(CMDBaseObject *,ulong,ulong,ushort *)

- ea: `0x180014488`
- end: `0x180014665`
- name: `?SetChangeData@CHANGE_ENTRY@@QEAAJPEAVCMDBaseObject@@KKPEAG@Z`
- size: `477`
- prototype: `int(CHANGE_ENTRY *__hidden this, struct CMDBaseObject *, unsigned int, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001466c`

## callees

- `0x180014488`
- `0x18001e4c0`
- `0x1800309d0`

## import_xrefs

- `IisRTL!?Copy@STRAU@@QEAAHPEBG@Z` at `0x180014595`
- `IisRTL!?Copy@STRAU@@QEAAHPEBG@Z` at `0x180014595`
- `IisRTL!?QueryCCH@STRAU@@QEAAIXZ` at `0x18001456f`
- `IisRTL!?QueryCCH@STRAU@@QEAAIXZ` at `0x1800145b0`
- `IisRTL!?QueryCCH@STRAU@@QEAAIXZ` at `0x18001456f`
- `IisRTL!?QueryCCH@STRAU@@QEAAIXZ` at `0x1800145b0`
- `IisRTL!?Copy@STRAU@@QEAAHPEBGK@Z` at `0x18001454a`
- `IisRTL!?Copy@STRAU@@QEAAHPEBGK@Z` at `0x18001454a`
- `IisRTL!?QueryStrA@STRAU@@QEAAPEADXZ` at `0x180014561`
- `IisRTL!?QueryStrA@STRAU@@QEAAPEADXZ` at `0x1800145a2`
- `IisRTL!?QueryStrA@STRAU@@QEAAPEADXZ` at `0x180014561`
- `IisRTL!?QueryStrA@STRAU@@QEAAPEADXZ` at `0x1800145a2`
- `IisRTL!?IsEmpty@STRAU@@QEAAHXZ` at `0x1800144f8`
- `IisRTL!?IsEmpty@STRAU@@QEAAHXZ` at `0x180014580`
- `IisRTL!?IsEmpty@STRAU@@QEAAHXZ` at `0x1800144f8`
- `IisRTL!?IsEmpty@STRAU@@QEAAHXZ` at `0x180014580`
- `IisRTL!?Resize@BUFFER@@QEAA_NKK@Z` at `0x18001460a`
- `IisRTL!?Resize@BUFFER@@QEAA_NKK@Z` at `0x18001460a`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800145c7`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800145c7`
- `IisRTL!??0BUFFER@@QEAA@XZ` at `0x1800144cc`
- `IisRTL!??0BUFFER@@QEAA@XZ` at `0x1800144cc`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180014637`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180014637`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180014539`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800145d8`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180014615`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180014539`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800145d8`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180014615`

## pseudocode

```c
__int64 __fastcall CHANGE_ENTRY::SetChangeData(
        CHANGE_ENTRY *this,
        struct CMDBaseObject *a2,
        int a3,
        int a4,
        unsigned __int16 *a5)
{
  unsigned int CCH; // ebp
  int ObjectPath; // ebx
  unsigned int v11; // ebx
  const unsigned __int16 *Ptr; // rax
  _DWORD *v13; // rax
  unsigned int v14; // r9d
  __int64 v15; // rdx
  bool v16; // bl
  _DWORD *v17; // rcx
  unsigned int v19; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v20[48]; // [rsp+38h] [rbp-60h] BYREF

  CCH = 0;
  v19 = 0;
  BUFFER::BUFFER((BUFFER *)v20);
  if ( a2 )
  {
    if ( !*((_QWORD *)this + 1) )
      *((_QWORD *)this + 1) = a2;
    *((_DWORD *)this + 4) |= a3;
    if ( STRAU::IsEmpty((CHANGE_ENTRY *)((char *)this + 192)) || (v11 = 0, a5) )
    {
      ObjectPath = GetObjectPath(a2, (struct BUFFER *)v20, &v19, g_pboMasterRoot, 1);
      if ( ObjectPath < 0 )
        goto LABEL_25;
      Ptr = (const unsigned __int16 *)BUFFER::QueryPtr((BUFFER *)v20);
      if ( !STRAU::Copy((CHANGE_ENTRY *)((char *)this + 192), Ptr, v19)
        || !STRAU::QueryStrA((CHANGE_ENTRY *)((char *)this + 192)) )
      {
        goto LABEL_9;
      }
      CCH = STRAU::QueryCCH((CHANGE_ENTRY *)((char *)this + 192));
      v11 = CCH;
    }
    if ( STRAU::IsEmpty((CHANGE_ENTRY *)((char *)this + 72)) && a5 )
    {
      if ( !STRAU::Copy((CHANGE_ENTRY *)((char *)this + 72), a5)
        || !STRAU::QueryStrA((CHANGE_ENTRY *)((char *)this + 72)) )
      {
        goto LABEL_9;
      }
      v11 = STRAU::QueryCCH((CHANGE_ENTRY *)((char *)this + 72)) + CCH;
    }
    if ( BUFFER::Resize((CHANGE_ENTRY *)((char *)this + 312), 2 * v11 + 10) )
    {
      v13 = BUFFER::QueryPtr((CHANGE_ENTRY *)((char *)this + 24));
      v14 = *((_DWORD *)this + 5);
      v15 = 0;
      if ( v14 )
      {
        while ( v13[v15] != a4 )
        {
          v15 = (unsigned int)(v15 + 1);
          if ( (unsigned int)v15 >= v14 )
            goto LABEL_21;
        }
        goto LABEL_24;
      }
LABEL_21:
      if ( (_DWORD)v15 != v14 )
      {
LABEL_24:
        ObjectPath = 0;
        goto LABEL_25;
      }
      v16 = BUFFER::Resize((CHANGE_ENTRY *)((char *)this + 24), 4 * v14 + 4, 2 * v14);
      v17 = BUFFER::QueryPtr((CHANGE_ENTRY *)((char *)this + 24));
      if ( v16 )
      {
        v17[(*((_DWORD *)this + 5))++] = a4;
        goto LABEL_24;
      }
    }
LABEL_9:
    ObjectPath = -2147024882;
    goto LABEL_25;
  }
  ObjectPath = -2147467259;
LABEL_25:
  BUFFER::~BUFFER((BUFFER *)v20);
  return (unsigned int)ObjectPath;
}

```

## disassembly

```asm
0x180014488  mov     [rsp+arg_10], rbx
0x18001448d  mov     [rsp+arg_18], rbp
0x180014492  push    rsi
0x180014493  push    rdi
0x180014494  push    r12
0x180014496  push    r14
0x180014498  push    r15
0x18001449a  sub     rsp, 70h
0x18001449e  mov     rax, cs:__security_cookie
0x1800144a5  xor     rax, rsp
0x1800144a8  mov     [rsp+98h+var_30], rax
0x1800144ad  mov     r15, [rsp+98h+arg_20]
0x1800144b5  mov     rdi, rcx
0x1800144b8  xor     ebp, ebp
0x1800144ba  lea     rcx, [rsp+98h+var_60]
0x1800144bf  mov     [rsp+98h+var_68], ebp
0x1800144c3  mov     r12d, r9d
0x1800144c6  mov     ebx, r8d
0x1800144c9  mov     r14, rdx
0x1800144cc  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x1800144d2  test    r14, r14
0x1800144d5  jnz     short loc_1800144E1
0x1800144d7  mov     ebx, 80004005h
0x1800144dc  jmp     loc_180014632
0x1800144e1  cmp     [rdi+8], rbp
0x1800144e5  jnz     short loc_1800144EB
0x1800144e7  mov     [rdi+8], r14
0x1800144eb  or      [rdi+10h], ebx
0x1800144ee  lea     rsi, [rdi+0C0h]
0x1800144f5  mov     rcx, rsi
0x1800144f8  call    cs:__imp_?IsEmpty@STRAU@@QEAAHXZ; STRAU::IsEmpty(void)
0x1800144fe  test    eax, eax
0x180014500  jnz     short loc_180014509
0x180014502  xor     ebx, ebx
0x180014504  test    r15, r15
0x180014507  jz      short loc_180014579
0x180014509  mov     r9, cs:?g_pboMasterRoot@@3PEAVCMDBaseObject@@EA; struct CMDBaseObject *
0x180014510  lea     r8, [rsp+98h+var_68]; unsigned int *
0x180014515  lea     rdx, [rsp+98h+var_60]; struct BUFFER *
0x18001451a  mov     [rsp+98h+var_78], 1; int
0x180014522  mov     rcx, r14; this
0x180014525  call    ?GetObjectPath@@YAJPEAVCMDBaseObject@@PEAVBUFFER@@PEAK0H@Z; GetObjectPath(CMDBaseObject *,BUFFER *,ulong *,CMDBaseObject *,int)
0x18001452a  mov     ebx, eax
0x18001452c  test    eax, eax
0x18001452e  js      loc_180014632
0x180014534  lea     rcx, [rsp+98h+var_60]
0x180014539  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001453f  mov     r8d, [rsp+98h+var_68]
0x180014544  mov     rcx, rsi
0x180014547  mov     rdx, rax
0x18001454a  call    cs:__imp_?Copy@STRAU@@QEAAHPEBGK@Z; STRAU::Copy(ushort const *,ulong)
0x180014550  test    eax, eax
0x180014552  jnz     short loc_18001455E
0x180014554  mov     ebx, 8007000Eh
0x180014559  jmp     loc_180014632
0x18001455e  mov     rcx, rsi
0x180014561  call    cs:__imp_?QueryStrA@STRAU@@QEAAPEADXZ; STRAU::QueryStrA(void)
0x180014567  test    rax, rax
0x18001456a  jz      short loc_180014554
0x18001456c  mov     rcx, rsi
0x18001456f  call    cs:__imp_?QueryCCH@STRAU@@QEAAIXZ; STRAU::QueryCCH(void)
0x180014575  mov     ebp, eax
0x180014577  mov     ebx, eax
0x180014579  lea     rsi, [rdi+48h]
0x18001457d  mov     rcx, rsi
0x180014580  call    cs:__imp_?IsEmpty@STRAU@@QEAAHXZ; STRAU::IsEmpty(void)
0x180014586  test    eax, eax
0x180014588  jz      short loc_1800145B9
0x18001458a  test    r15, r15
0x18001458d  jz      short loc_1800145B9
0x18001458f  mov     rdx, r15
0x180014592  mov     rcx, rsi
0x180014595  call    cs:__imp_?Copy@STRAU@@QEAAHPEBG@Z; STRAU::Copy(ushort const *)
0x18001459b  test    eax, eax
0x18001459d  jz      short loc_180014554
0x18001459f  mov     rcx, rsi
0x1800145a2  call    cs:__imp_?QueryStrA@STRAU@@QEAAPEADXZ; STRAU::QueryStrA(void)
0x1800145a8  test    rax, rax
0x1800145ab  jz      short loc_180014554
0x1800145ad  mov     rcx, rsi
0x1800145b0  call    cs:__imp_?QueryCCH@STRAU@@QEAAIXZ; STRAU::QueryCCH(void)
0x1800145b6  lea     ebx, [rax+rbp]
0x1800145b9  lea     edx, ds:0Ah[rbx*2]
0x1800145c0  lea     rcx, [rdi+138h]
0x1800145c7  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800145cd  test    al, al
0x1800145cf  jz      short loc_180014554
0x1800145d1  lea     rsi, [rdi+18h]
0x1800145d5  mov     rcx, rsi
0x1800145d8  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800145de  mov     r9d, [rdi+14h]
0x1800145e2  xor     edx, edx
0x1800145e4  test    r9d, r9d
0x1800145e7  jz      short loc_1800145F6
0x1800145e9  cmp     [rax+rdx*4], r12d
0x1800145ed  jz      short loc_180014630
0x1800145ef  inc     edx
0x1800145f1  cmp     edx, r9d
0x1800145f4  jb      short loc_1800145E9
0x1800145f6  cmp     edx, r9d
0x1800145f9  jnz     short loc_180014630
0x1800145fb  lea     r8d, [r9+r9]
0x1800145ff  mov     rcx, rsi
0x180014602  lea     edx, ds:4[r9*4]
0x18001460a  call    cs:__imp_?Resize@BUFFER@@QEAA_NKK@Z; BUFFER::Resize(ulong,ulong)
0x180014610  mov     rcx, rsi
0x180014613  mov     bl, al
0x180014615  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001461b  mov     rcx, rax
0x18001461e  test    bl, bl
0x180014620  jz      loc_180014554
0x180014626  mov     eax, [rdi+14h]
0x180014629  mov     [rcx+rax*4], r12d
0x18001462d  inc     dword ptr [rdi+14h]
0x180014630  xor     ebx, ebx
0x180014632  lea     rcx, [rsp+98h+var_60]
0x180014637  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18001463d  mov     eax, ebx
0x18001463f  mov     rcx, [rsp+98h+var_30]
0x180014644  xor     rcx, rsp; StackCookie
0x180014647  call    __security_check_cookie
0x18001464c  lea     r11, [rsp+98h+var_28]
0x180014651  mov     rbx, [r11+40h]
0x180014655  mov     rbp, [r11+48h]
0x180014659  mov     rsp, r11
0x18001465c  pop     r15
0x18001465e  pop     r14
0x180014660  pop     r12
0x180014662  pop     rdi
0x180014663  pop     rsi
0x180014664  retn
```
