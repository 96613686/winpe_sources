# CWbemClass::GetPropertyQualifierSet(ushort const *,IWbemQualifierSet * *)

- ea: `0x180002bb0`
- end: `0x180002e98`
- name: `?GetPropertyQualifierSet@CWbemClass@@UEAAJPEBGPEAPEAUIWbemQualifierSet@@@Z`
- size: `744`
- prototype: `int(CWbemClass *__hidden this, const unsigned __int16 *, struct IWbemQualifierSet **)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180002bb0`
- `0x180002ea0`
- `0x180002f8c`
- `0x180003080`
- `0x180037120`
- `0x180050490`
- `0x180091966`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180002c01`
- `wbemcomn!GetMemLogObject` at `0x180002d14`
- `wbemcomn!GetMemLogObject` at `0x180002d89`
- `wbemcomn!GetMemLogObject` at `0x180002dfd`
- `wbemcomn!GetMemLogObject` at `0x180002c01`
- `wbemcomn!GetMemLogObject` at `0x180002d14`
- `wbemcomn!GetMemLogObject` at `0x180002d89`
- `wbemcomn!GetMemLogObject` at `0x180002dfd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180002c11`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180002d24`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180002d97`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180002e08`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180002c11`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180002d24`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180002d97`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180002e08`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180002c61`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180002c61`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWbemClass::GetPropertyQualifierSet(
        CWbemClass *this,
        const unsigned __int16 *a2,
        struct IWbemQualifierSet **a3)
{
  __int64 v6; // rax
  CMemoryLog *v7; // rax
  __int64 result; // rax
  CClassPropertyQualifierSet *v9; // rax
  struct CClassPropertyQualifierSet *v10; // rdi
  int inited; // esi
  unsigned int v12; // edi
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v14; // rax
  CMemoryLog *v15; // rax
  CMemoryLog *v16; // rax
  CWbemClass *v17; // [rsp+88h] [rbp+20h] BYREF

  try
  {
    v17 = this;
    (*(void (__fastcall **)(CWbemClass *, __int64))(*(_QWORD *)this + 280LL))(this, 1);
    if ( !a2 )
      goto LABEL_6;
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
    if ( v6 )
    {
      if ( *a2 == 95 )
      {
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, -2147217360);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            115,
            WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
            2147749936LL);
        }
        (*(void (__fastcall **)(CWbemClass *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
        result = 2147749936LL;
      }
      else
      {
        v9 = (CClassPropertyQualifierSet *)CWin32DefaultArena::WbemMemAlloc(0x70u);
        if ( v9 )
          v10 = CClassPropertyQualifierSet::CClassPropertyQualifierSet(v9);
        else
          v10 = 0;
        if ( v10 )
        {
          inited = CClassPart::InitPropertyQualifierSet((CWbemClass *)((char *)this + 520), a2, v10);
          if ( inited < 0 )
          {
            CClassPropertyQualifierSet::`vector deleting destructor'(v10, 1u);
            *a3 = 0;
            v15 = GetMemLogObject();
            CMemoryLog::Write(v15, inited);
            if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                117,
                WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
                (unsigned int)inited);
            }
            CWbemObject::CLock::~CLock((CWbemObject::CLock *)&v17);
            result = (unsigned int)inited;
          }
          else
          {
            *a3 = 0;
            if ( !memcmp_0(&IID_IWbemQualifierSet, &IID_IWbemQualifierSet, 0x10u)
              || !memcmp_0(&IID_IWbemQualifierSet, &IID_IUnknown, 0x10u) )
            {
              (*(void (__fastcall **)(struct CClassPropertyQualifierSet *))(*(_QWORD *)v10 + 8LL))(v10);
              *a3 = (struct IWbemQualifierSet *)v10;
              v12 = 0;
            }
            else
            {
              v12 = -2147467262;
            }
            (*(void (__fastcall **)(CWbemClass *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
            result = v12;
          }
        }
        else
        {
          v14 = GetMemLogObject();
          CMemoryLog::Write(v14, -2147217402);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              116,
              WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
              2147749894LL);
          }
          CWbemObject::CLock::~CLock((CWbemObject::CLock *)&v17);
          result = 2147749894LL;
        }
      }
    }
    else
    {
LABEL_6:
      v7 = GetMemLogObject();
      CMemoryLog::Write(v7, -2147217400);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          114,
          WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
          2147749896LL);
      }
      (*(void (__fastcall **)(CWbemClass *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
      result = 2147749896LL;
    }
  }
  catch ( CX_MemoryException )
  {
    v16 = GetMemLogObject();
    CMemoryLog::Write(v16, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  return result;
}

```

## disassembly

```asm
0x180002bb0  mov     rax, rsp
0x180002bb3  push    rbx
0x180002bb4  push    rsi
0x180002bb5  push    rdi
0x180002bb6  push    r12
0x180002bb8  push    r14
0x180002bba  push    r15
0x180002bbc  sub     rsp, 38h
0x180002bc0  mov     r14, r8
0x180002bc3  mov     rsi, rdx
0x180002bc6  mov     rbx, rcx
0x180002bc9  mov     [rax+20h], rcx
0x180002bcd  mov     rax, [rcx]
0x180002bd0  mov     r12d, 1
0x180002bd6  mov     edx, r12d
0x180002bd9  mov     rax, [rax+118h]
0x180002be0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002be5  nop
0x180002be6  xor     r15d, r15d
0x180002be9  test    rsi, rsi
0x180002bec  jz      short loc_180002C01
0x180002bee  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002bf2  inc     rax
0x180002bf5  cmp     [rsi+rax*2], r15w
0x180002bfa  jnz     short loc_180002BF2
0x180002bfc  test    rax, rax
0x180002bff  jnz     short loc_180002C52
0x180002c01  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180002c07  mov     edi, 80041008h
0x180002c0c  mov     edx, edi
0x180002c0e  mov     rcx, rax
0x180002c11  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180002c17  lea     rax, WPP_GLOBAL_Control
0x180002c1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c25  cmp     rcx, rax
0x180002c28  jnz     loc_180002E5A
0x180002c2e  mov     rcx, [rbx]
0x180002c31  mov     rax, [rcx+120h]
0x180002c38  xor     edx, edx
0x180002c3a  mov     rcx, rbx
0x180002c3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c42  mov     eax, edi
0x180002c44  add     rsp, 38h
0x180002c48  pop     r15
0x180002c4a  pop     r14
0x180002c4c  pop     r12
0x180002c4e  pop     rdi
0x180002c4f  pop     rsi
0x180002c50  pop     rbx
0x180002c51  retn
0x180002c52  cmp     word ptr [rsi], 5Fh ; '_'
0x180002c56  jz      loc_180002D14
0x180002c5c  mov     ecx, 70h ; 'p'
0x180002c61  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180002c67  mov     [rsp+68h+var_48], rax
0x180002c6c  test    rax, rax
0x180002c6f  jz      loc_180002D81
0x180002c75  mov     rcx, rax; this
0x180002c78  call    ??0CClassPropertyQualifierSet@@QEAA@XZ; CClassPropertyQualifierSet::CClassPropertyQualifierSet(void)
0x180002c7d  mov     rdi, rax
0x180002c80  test    rdi, rdi
0x180002c83  jz      loc_180002D89
0x180002c89  lea     rcx, [rbx+208h]; this
0x180002c90  mov     r8, rdi; struct CClassPropertyQualifierSet *
0x180002c93  mov     rdx, rsi; unsigned __int16 *
0x180002c96  call    ?InitPropertyQualifierSet@CClassPart@@QEAAJPEBGPEAVCClassPropertyQualifierSet@@@Z; CClassPart::InitPropertyQualifierSet(ushort const *,CClassPropertyQualifierSet *)
0x180002c9b  mov     esi, eax
0x180002c9d  test    eax, eax
0x180002c9f  js      loc_180002DEF
0x180002ca5  mov     [r14], r15
0x180002ca8  mov     r12d, 10h
0x180002cae  mov     r8d, r12d; Size
0x180002cb1  lea     rsi, IID_IWbemQualifierSet
0x180002cb8  mov     rdx, rsi; Buf2
0x180002cbb  mov     rcx, rsi; Buf1
0x180002cbe  call    memcmp_0
0x180002cc3  test    eax, eax
0x180002cc5  jnz     short loc_180002CF7
0x180002cc7  mov     rax, [rdi]
0x180002cca  mov     rcx, rdi
0x180002ccd  mov     rax, [rax+8]
0x180002cd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cd6  mov     [r14], rdi
0x180002cd9  mov     edi, r15d
0x180002cdc  mov     rcx, [rbx]
0x180002cdf  mov     rax, [rcx+120h]
0x180002ce6  xor     edx, edx
0x180002ce8  mov     rcx, rbx
0x180002ceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cf0  mov     eax, edi
0x180002cf2  jmp     loc_180002C44
0x180002cf7  mov     r8, r12; Size
0x180002cfa  lea     rdx, IID_IUnknown; Buf2
0x180002d01  mov     rcx, rsi; Buf1
0x180002d04  call    memcmp_0
0x180002d09  test    eax, eax
0x180002d0b  jz      short loc_180002CC7
0x180002d0d  mov     edi, 80004002h
0x180002d12  jmp     short loc_180002CDC
0x180002d14  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180002d1a  mov     edi, 80041030h
0x180002d1f  mov     edx, edi
0x180002d21  mov     rcx, rax
0x180002d24  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180002d2a  lea     rax, WPP_GLOBAL_Control
0x180002d31  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d38  cmp     rcx, rax
0x180002d3b  jnz     short loc_180002D58
0x180002d3d  mov     rcx, [rbx]
0x180002d40  mov     rax, [rcx+120h]
0x180002d47  xor     edx, edx
0x180002d49  mov     rcx, rbx
0x180002d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d51  mov     eax, edi
0x180002d53  jmp     loc_180002C44
0x180002d58  test    [rcx+1Ch], r12b
0x180002d5c  jz      short loc_180002D3D
0x180002d5e  cmp     byte ptr [rcx+19h], 2
0x180002d62  jb      short loc_180002D3D
0x180002d64  mov     edx, 73h ; 's'
0x180002d69  mov     r9d, 80041030h
0x180002d6f  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x180002d76  mov     rcx, [rcx+10h]
0x180002d7a  call    WPP_SF_d
0x180002d7f  jmp     short loc_180002D3D
0x180002d81  mov     rdi, r15
0x180002d84  jmp     loc_180002C80
0x180002d89  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180002d8f  mov     edx, 80041006h
0x180002d94  mov     rcx, rax
0x180002d97  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180002d9d  lea     rax, WPP_GLOBAL_Control
0x180002da4  mov     rcx, cs:WPP_GLOBAL_Control
0x180002dab  cmp     rcx, rax
0x180002dae  jz      short loc_180002DD8
0x180002db0  test    [rcx+1Ch], r12b
0x180002db4  jz      short loc_180002DD8
0x180002db6  cmp     byte ptr [rcx+19h], 2
0x180002dba  jb      short loc_180002DD8
0x180002dbc  mov     edx, 74h ; 't'
0x180002dc1  mov     r9d, 80041006h
0x180002dc7  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x180002dce  mov     rcx, [rcx+10h]
0x180002dd2  call    WPP_SF_d
0x180002dd7  nop
0x180002dd8  lea     rcx, [rsp+68h+arg_18]; this
0x180002de0  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x180002de5  mov     eax, 80041006h
0x180002dea  jmp     loc_180002C44
0x180002def  mov     edx, r12d; unsigned int
0x180002df2  mov     rcx, rdi; this
0x180002df5  call    ??_ECClassPropertyQualifierSet@@UEAAPEAXI@Z; CClassPropertyQualifierSet::`vector deleting destructor'(uint)
0x180002dfa  mov     [r14], r15
0x180002dfd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180002e03  mov     edx, esi
0x180002e05  mov     rcx, rax
0x180002e08  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180002e0e  lea     rax, WPP_GLOBAL_Control
0x180002e15  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e1c  cmp     rcx, rax
0x180002e1f  jz      short loc_180002E46
0x180002e21  test    [rcx+1Ch], r12b
0x180002e25  jz      short loc_180002E46
0x180002e27  cmp     byte ptr [rcx+19h], 2
0x180002e2b  jb      short loc_180002E46
0x180002e2d  mov     edx, 75h ; 'u'
0x180002e32  mov     r9d, esi
0x180002e35  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x180002e3c  mov     rcx, [rcx+10h]
0x180002e40  call    WPP_SF_d
0x180002e45  nop
0x180002e46  lea     rcx, [rsp+68h+arg_18]; this
0x180002e4e  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x180002e53  mov     eax, esi
0x180002e55  jmp     loc_180002C44
0x180002e5a  test    [rcx+1Ch], r12b
0x180002e5e  jz      loc_180002C2E
0x180002e64  cmp     byte ptr [rcx+19h], 2
0x180002e68  jb      loc_180002C2E
0x180002e6e  mov     edx, 72h ; 'r'
0x180002e73  mov     r9d, 80041008h
0x180002e79  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x180002e80  mov     rcx, [rcx+10h]
0x180002e84  call    WPP_SF_d
0x180002e89  jmp     loc_180002C2E
0x180002e8e  mov     eax, 80041006h
0x180002e93  jmp     loc_180002C44
```
