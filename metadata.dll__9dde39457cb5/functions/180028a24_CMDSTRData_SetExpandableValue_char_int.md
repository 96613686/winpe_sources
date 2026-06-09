# CMDSTRData::SetExpandableValue(char *,int)

- ea: `0x180028a24`
- end: `0x180028b81`
- name: `?SetExpandableValue@CMDSTRData@@AEAAHPEADH@Z`
- size: `349`
- prototype: `int(CMDSTRData *__hidden this, char *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180028888`

## callees

- `0x1800089c8`
- `0x1800289c4`
- `0x1800289ec`
- `0x180028a24`
- `0x1800309d0`

## import_xrefs

- `IisRTL!?Copy@STRAU@@QEAAHPEBD@Z` at `0x180028b1f`
- `IisRTL!?Copy@STRAU@@QEAAHPEBD@Z` at `0x180028b1f`
- `IisRTL!?Copy@STRAU@@QEAAHPEBG@Z` at `0x180028b17`
- `IisRTL!?Copy@STRAU@@QEAAHPEBG@Z` at `0x180028b17`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x180028a65`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x180028a65`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180028ac4`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180028ac4`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x180028a80`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x180028ab3`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x180028ad3`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x180028a80`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x180028ab3`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x180028ad3`
- `IisRTL!??0BUFFER@@QEAA@XZ` at `0x180028a4d`
- `IisRTL!??0BUFFER@@QEAA@XZ` at `0x180028a4d`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180028b2e`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180028b5c`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180028b2e`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180028b5c`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180028a8d`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180028ae0`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180028b07`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180028a8d`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180028ae0`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180028b07`

## pseudocode

```c
__int64 __fastcall CMDSTRData::SetExpandableValue(CMDSTRData *this, char *a2, int a3)
{
  STRAU *v6; // rax
  unsigned int v7; // edx
  unsigned int Size; // ebx
  char *Ptr; // rax
  unsigned int v10; // ebx
  unsigned int v11; // ebx
  char *v12; // rax
  STRAU *v13; // rbx
  const unsigned __int16 *v14; // rax
  STRAU *v17; // rcx
  _BYTE v18[48]; // [rsp+20h] [rbp-58h] BYREF

  BUFFER::BUFFER((BUFFER *)v18);
  v6 = (STRAU *)operator new(0x78u);
  if ( v6 )
    v6 = STRAU::STRAU(v6);
  *((_QWORD *)this + 23) = v6;
  if ( !v6 )
    goto LABEL_13;
  Size = BUFFER::QuerySize((BUFFER *)v18);
  Ptr = (char *)BUFFER::QueryPtr((BUFFER *)v18);
  v10 = ExpandEnvString(a2, Ptr, Size, a3);
  if ( !v10 )
    goto LABEL_13;
  if ( v10 > BUFFER::QuerySize((BUFFER *)v18) )
  {
    if ( !BUFFER::Resize((BUFFER *)v18, v10) )
      goto LABEL_13;
    v11 = BUFFER::QuerySize((BUFFER *)v18);
    v12 = (char *)BUFFER::QueryPtr((BUFFER *)v18);
    if ( !ExpandEnvString(a2, v12, v11, a3) )
      goto LABEL_13;
  }
  v13 = (STRAU *)*((_QWORD *)this + 23);
  v14 = (const unsigned __int16 *)BUFFER::QueryPtr((BUFFER *)v18);
  if ( a3 ? STRAU::Copy(v13, v14) : STRAU::Copy(v13, (const char *)v14) )
  {
    BUFFER::~BUFFER((BUFFER *)v18);
    return 1;
  }
  else
  {
LABEL_13:
    v17 = (STRAU *)*((_QWORD *)this + 23);
    if ( v17 )
    {
      STRAU::`scalar deleting destructor'(v17, v7);
      *((_QWORD *)this + 23) = 0;
    }
    BUFFER::~BUFFER((BUFFER *)v18);
    return 0;
  }
}

```

## disassembly

```asm
0x180028a24  mov     [rsp+arg_18], rbx
0x180028a29  push    rbp
0x180028a2a  push    rsi
0x180028a2b  push    rdi
0x180028a2c  sub     rsp, 60h
0x180028a30  mov     rax, cs:__security_cookie
0x180028a37  xor     rax, rsp
0x180028a3a  mov     [rsp+78h+var_28], rax
0x180028a3f  mov     rdi, rcx
0x180028a42  mov     esi, r8d
0x180028a45  lea     rcx, [rsp+78h+var_58]
0x180028a4a  mov     rbp, rdx
0x180028a4d  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x180028a53  mov     ecx, 78h ; 'x'; Size
0x180028a58  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180028a5d  test    rax, rax
0x180028a60  jz      short loc_180028A6B
0x180028a62  mov     rcx, rax
0x180028a65  call    cs:__imp_??0STRAU@@QEAA@XZ; STRAU::STRAU(void)
0x180028a6b  mov     [rdi+0B8h], rax
0x180028a72  test    rax, rax
0x180028a75  jz      loc_180028B3B
0x180028a7b  lea     rcx, [rsp+78h+var_58]
0x180028a80  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180028a86  lea     rcx, [rsp+78h+var_58]
0x180028a8b  mov     ebx, eax
0x180028a8d  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180028a93  mov     r9d, esi; int
0x180028a96  mov     r8d, ebx; unsigned int
0x180028a99  mov     rdx, rax; char *
0x180028a9c  mov     rcx, rbp; char *
0x180028a9f  call    ?ExpandEnvString@@YAKPEAD0KH@Z; ExpandEnvString(char *,char *,ulong,int)
0x180028aa4  mov     ebx, eax
0x180028aa6  test    eax, eax
0x180028aa8  jz      loc_180028B3B
0x180028aae  lea     rcx, [rsp+78h+var_58]
0x180028ab3  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180028ab9  cmp     ebx, eax
0x180028abb  jbe     short loc_180028AFB
0x180028abd  mov     edx, ebx
0x180028abf  lea     rcx, [rsp+78h+var_58]
0x180028ac4  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180028aca  test    al, al
0x180028acc  jz      short loc_180028B3B
0x180028ace  lea     rcx, [rsp+78h+var_58]
0x180028ad3  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180028ad9  lea     rcx, [rsp+78h+var_58]
0x180028ade  mov     ebx, eax
0x180028ae0  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180028ae6  mov     r9d, esi; int
0x180028ae9  mov     r8d, ebx; unsigned int
0x180028aec  mov     rdx, rax; char *
0x180028aef  mov     rcx, rbp; char *
0x180028af2  call    ?ExpandEnvString@@YAKPEAD0KH@Z; ExpandEnvString(char *,char *,ulong,int)
0x180028af7  test    eax, eax
0x180028af9  jz      short loc_180028B3B
0x180028afb  mov     rbx, [rdi+0B8h]
0x180028b02  lea     rcx, [rsp+78h+var_58]
0x180028b07  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180028b0d  mov     rcx, rbx
0x180028b10  mov     rdx, rax
0x180028b13  test    esi, esi
0x180028b15  jz      short loc_180028B1F
0x180028b17  call    cs:__imp_?Copy@STRAU@@QEAAHPEBG@Z; STRAU::Copy(ushort const *)
0x180028b1d  jmp     short loc_180028B25
0x180028b1f  call    cs:__imp_?Copy@STRAU@@QEAAHPEBD@Z; STRAU::Copy(char const *)
0x180028b25  test    eax, eax
0x180028b27  jz      short loc_180028B3B
0x180028b29  lea     rcx, [rsp+78h+var_58]
0x180028b2e  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180028b34  mov     eax, 1
0x180028b39  jmp     short loc_180028B64
0x180028b3b  mov     rcx, [rdi+0B8h]; this
0x180028b42  test    rcx, rcx
0x180028b45  jz      short loc_180028B57
0x180028b47  call    ??_GSTRAU@@QEAAPEAXI@Z; STRAU::`scalar deleting destructor'(uint)
0x180028b4c  mov     qword ptr [rdi+0B8h], 0
0x180028b57  lea     rcx, [rsp+78h+var_58]
0x180028b5c  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180028b62  xor     eax, eax
0x180028b64  mov     rcx, [rsp+78h+var_28]
0x180028b69  xor     rcx, rsp; StackCookie
0x180028b6c  call    __security_check_cookie
0x180028b71  mov     rbx, [rsp+78h+arg_18]
0x180028b79  add     rsp, 60h
0x180028b7d  pop     rdi
0x180028b7e  pop     rsi
0x180028b7f  pop     rbp
0x180028b80  retn
```
