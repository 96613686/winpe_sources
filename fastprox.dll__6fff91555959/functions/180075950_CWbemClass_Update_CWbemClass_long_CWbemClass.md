# CWbemClass::Update(CWbemClass *,long,CWbemClass * *)

- ea: `0x180075950`
- end: `0x180075c14`
- name: `?Update@CWbemClass@@QEAAJPEAV1@JPEAPEAV1@@Z`
- size: `708`
- prototype: `__int64 __fastcall(CWbemClass *__hidden this, struct CWbemClass *, int, struct CWbemClass **)`
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180075c20`
- `0x180076010`

## callees

- `0x18001a4c0`
- `0x1800205d0`
- `0x1800290a0`
- `0x180031f60`
- `0x180035b08`
- `0x180037120`
- `0x180045400`
- `0x180060a34`
- `0x18006fa4c`
- `0x180075950`
- `0x1800919b0`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800759b7`
- `wbemcomn!GetMemLogObject` at `0x180075ba1`
- `wbemcomn!GetMemLogObject` at `0x1800759b7`
- `wbemcomn!GetMemLogObject` at `0x180075ba1`
- `wbemcomn!?IsNull@CVar@@QEAAHXZ` at `0x180075a9b`
- `wbemcomn!?IsNull@CVar@@QEAAHXZ` at `0x180075a9b`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180075a78`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180075a78`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800759c5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180075bac`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800759c5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180075bac`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180075b82`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180075b82`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180075a21`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180075a21`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWbemClass::Update(CWbemClass *this, unsigned int **a2, int a3, struct CWbemClass **a4)
{
  int v8; // ebx
  unsigned int v9; // ebx
  CMemoryLog *MemLogObject; // rax
  unsigned __int8 *v11; // rax
  unsigned __int8 *v12; // rsi
  int v13; // eax
  int v14; // eax
  CMemoryLog *v15; // rax
  __int64 result; // rax
  CMemoryLog *v17; // rax
  struct CWbemClass *v18; // [rsp+38h] [rbp-1F0h] BYREF
  int pExceptionObject; // [rsp+40h] [rbp-1E8h] BYREF
  void *v20[2]; // [rsp+48h] [rbp-1E0h] BYREF
  _BYTE v21[40]; // [rsp+58h] [rbp-1D0h] BYREF
  _BYTE v22[352]; // [rsp+80h] [rbp-1A8h] BYREF

  try
  {
    v8 = -2147217400;
    if ( (((a3 & 0x60) - 32) & 0xFFFFFFDF) != 0 )
      goto LABEL_28;
    v9 = (*((__int64 (__fastcall **)(unsigned int **))*a2 + 104))(a2);
    if ( v9 + 4 < v9 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          172,
          WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
          "SafeIntException(ERROR_ARITHMETIC_OVERFLOW)");
      }
      pExceptionObject = 534;
      throw (SafeIntException *)&pExceptionObject;
    }
    v11 = (unsigned __int8 *)CWin32DefaultArena::WbemMemAlloc(v9 + 4);
    v12 = v11;
    v20[0] = v11;
    v20[1] = 0;
    if ( v11 )
    {
      v8 = (*((__int64 (__fastcall **)(unsigned int **, unsigned __int8 *, _QWORD, _QWORD))*a2 + 105))(a2, v11, v9, 0);
      if ( v8 >= 0 )
      {
        v18 = 0;
        CVar::CVar((CVar *)v21);
        (*(void (__fastcall **)(CWbemClass *, _BYTE *))(*(_QWORD *)this + 1096LL))(this, v21);
        if ( CVar::IsNull((CVar *)v21) )
          v13 = (*(__int64 (__fastcall **)(CWbemClass *, struct CWbemClass **))(*(_QWORD *)this + 96LL))(this, &v18);
        else
          v13 = CWbemClass::CreateDerivedClass(this, &v18);
        v8 = v13;
        if ( v13 >= 0 )
        {
          CClassAndMethods::CClassAndMethods((CClassAndMethods *)v22);
          CClassAndMethods::SetDataWithNumProps((CClassAndMethods *)v22, v12, (struct CWbemClass *)a2, *a2[84], 0);
          v14 = CClassAndMethods::Update((struct CWbemClass *)((char *)v18 + 504), (struct CClassAndMethods *)v22, a3);
          v8 = v14;
          if ( v14 < 0 )
          {
            switch ( v14 )
            {
              case -2147217403:
                v8 = -2147217326;
                break;
              case -2147217382:
                v8 = -2147217325;
                break;
              case -2147217356:
                v8 = -2147217324;
                break;
            }
            (*(void (__fastcall **)(struct CWbemClass *))(*(_QWORD *)v18 + 16LL))(v18);
          }
          else
          {
            *a4 = v18;
          }
          CClassAndMethods::~CClassAndMethods((CClassAndMethods *)v22);
        }
        CVar::~CVar((CVar *)v21);
      }
    }
    else
    {
      v8 = -2147217402;
    }
    CVectorDeleteMe<unsigned char>::~CVectorDeleteMe<unsigned char>(v20);
    if ( v8 < 0 )
    {
LABEL_28:
      v15 = GetMemLogObject();
      CMemoryLog::Write(v15, v8);
    }
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        173,
        WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
        (unsigned int)v8);
    }
    result = (unsigned int)v8;
  }
  catch ( CX_MemoryException )
  {
    v17 = GetMemLogObject();
    CMemoryLog::Write(v17, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 174, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  return result;
}

```

## disassembly

```asm
0x180075950  push    rbx
0x180075952  push    rsi
0x180075953  push    rdi
0x180075954  push    r12
0x180075956  push    r14
0x180075958  push    r15
0x18007595a  sub     rsp, 1F8h
0x180075961  mov     rax, cs:__security_cookie
0x180075968  xor     rax, rsp
0x18007596b  mov     [rsp+228h+var_48], rax
0x180075973  mov     r12, r9
0x180075976  mov     r15d, r8d
0x180075979  mov     r14, rdx
0x18007597c  mov     rdi, rcx
0x18007597f  mov     ebx, 80041008h
0x180075984  mov     [rsp+228h+var_1F8], ebx
0x180075988  mov     eax, r8d
0x18007598b  and     eax, 60h
0x18007598e  sub     eax, 20h ; ' '
0x180075991  test    eax, 0FFFFFFDFh
0x180075996  jnz     loc_180075BA1
0x18007599c  mov     rax, [rdx]
0x18007599f  mov     rcx, rdx
0x1800759a2  mov     rax, [rax+340h]
0x1800759a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800759ae  mov     ebx, eax
0x1800759b0  add     eax, 4
0x1800759b3  cmp     eax, ebx
0x1800759b5  jnb     short loc_180075A1F
0x1800759b7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800759bd  mov     edx, 0FFFFFFFEh
0x1800759c2  mov     rcx, rax
0x1800759c5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800759cb  lea     rax, WPP_GLOBAL_Control
0x1800759d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800759d9  cmp     rcx, rax
0x1800759dc  jz      short loc_180075A06
0x1800759de  test    byte ptr [rcx+1Ch], 1
0x1800759e2  jz      short loc_180075A06
0x1800759e4  cmp     byte ptr [rcx+19h], 2
0x1800759e8  jb      short loc_180075A06
0x1800759ea  mov     edx, 0ACh
0x1800759ef  lea     r9, aSafeintexcepti_1; "SafeIntException(ERROR_ARITHMETIC_OVERF"...
0x1800759f6  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x1800759fd  mov     rcx, [rcx+10h]
0x180075a01  call    WPP_SF_s
0x180075a06  mov     [rsp+228h+pExceptionObject], 216h
0x180075a0e  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x180075a15  lea     rcx, [rsp+228h+pExceptionObject]; pExceptionObject
0x180075a1a  call    _CxxThrowException_0
0x180075a1f  mov     ecx, eax
0x180075a21  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180075a27  mov     rsi, rax
0x180075a2a  mov     [rsp+228h+var_1E0], rax
0x180075a2f  mov     [rsp+228h+var_1D8], 0
0x180075a38  test    rax, rax
0x180075a3b  jz      loc_180075B8A
0x180075a41  mov     rax, [r14]
0x180075a44  xor     r9d, r9d
0x180075a47  mov     r8d, ebx
0x180075a4a  mov     rdx, rsi
0x180075a4d  mov     rcx, r14
0x180075a50  mov     rax, [rax+348h]
0x180075a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075a5c  mov     ebx, eax
0x180075a5e  mov     [rsp+228h+var_1F8], eax
0x180075a62  test    eax, eax
0x180075a64  js      loc_180075B93
0x180075a6a  mov     [rsp+228h+var_1F0], 0
0x180075a73  lea     rcx, [rsp+228h+var_1D0]
0x180075a78  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x180075a7e  nop
0x180075a7f  mov     rax, [rdi]
0x180075a82  lea     rdx, [rsp+228h+var_1D0]
0x180075a87  mov     rcx, rdi
0x180075a8a  mov     rax, [rax+448h]
0x180075a91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075a96  lea     rcx, [rsp+228h+var_1D0]
0x180075a9b  call    cs:__imp_?IsNull@CVar@@QEAAHXZ; CVar::IsNull(void)
0x180075aa1  lea     rdx, [rsp+228h+var_1F0]; struct CWbemClass **
0x180075aa6  mov     rcx, rdi; this
0x180075aa9  test    eax, eax
0x180075aab  jz      short loc_180075ABB
0x180075aad  mov     rax, [rdi]
0x180075ab0  mov     rax, [rax+60h]
0x180075ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075ab9  jmp     short loc_180075AC0
0x180075abb  call    ?CreateDerivedClass@CWbemClass@@QEAAJPEAPEAV1@@Z; CWbemClass::CreateDerivedClass(CWbemClass * *)
0x180075ac0  mov     [rsp+228h+var_1F8], eax
0x180075ac4  mov     ebx, eax
0x180075ac6  test    eax, eax
0x180075ac8  js      loc_180075B7D
0x180075ace  lea     rcx, [rsp+228h+var_1A8]; this
0x180075ad6  call    ??0CClassAndMethods@@QEAA@XZ; CClassAndMethods::CClassAndMethods(void)
0x180075adb  nop
0x180075adc  mov     r9, [r14+2A0h]
0x180075ae3  mov     [rsp+228h+var_208], 0; struct CClassAndMethods *
0x180075aec  mov     r9d, [r9]; unsigned int
0x180075aef  mov     r8, r14; struct CWbemClass *
0x180075af2  mov     rdx, rsi; unsigned __int8 *
0x180075af5  lea     rcx, [rsp+228h+var_1A8]; this
0x180075afd  call    ?SetDataWithNumProps@CClassAndMethods@@QEAAXPEAEPEAVCWbemClass@@KPEAV1@@Z; CClassAndMethods::SetDataWithNumProps(uchar *,CWbemClass *,ulong,CClassAndMethods *)
0x180075b02  mov     rcx, [rsp+228h+var_1F0]
0x180075b07  add     rcx, 1F8h; struct CClassAndMethods *
0x180075b0e  mov     r8d, r15d; int
0x180075b11  lea     rdx, [rsp+228h+var_1A8]; struct CClassAndMethods *
0x180075b19  call    ?Update@CClassAndMethods@@SAJAEAV1@0J@Z; CClassAndMethods::Update(CClassAndMethods &,CClassAndMethods &,long)
0x180075b1e  mov     ebx, eax
0x180075b20  mov     [rsp+228h+var_1F8], eax
0x180075b24  test    eax, eax
0x180075b26  js      short loc_180075B33
0x180075b28  mov     rax, [rsp+228h+var_1F0]
0x180075b2d  mov     [r12], rax
0x180075b31  jmp     short loc_180075B6F
0x180075b33  cmp     eax, 80041005h
0x180075b38  jz      short loc_180075B54
0x180075b3a  cmp     eax, 8004101Ah
0x180075b3f  jz      short loc_180075B4D
0x180075b41  cmp     eax, 80041034h
0x180075b46  jnz     short loc_180075B5D
0x180075b48  lea     ebx, [rax+20h]
0x180075b4b  jmp     short loc_180075B59
0x180075b4d  mov     ebx, 80041053h
0x180075b52  jmp     short loc_180075B59
0x180075b54  mov     ebx, 80041052h
0x180075b59  mov     [rsp+228h+var_1F8], ebx
0x180075b5d  mov     rcx, [rsp+228h+var_1F0]
0x180075b62  mov     rax, [rcx]
0x180075b65  mov     rax, [rax+10h]
0x180075b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075b6e  nop
0x180075b6f  lea     rcx, [rsp+228h+var_1A8]; this
0x180075b77  call    ??1CClassAndMethods@@QEAA@XZ; CClassAndMethods::~CClassAndMethods(void)
0x180075b7c  nop
0x180075b7d  lea     rcx, [rsp+228h+var_1D0]
0x180075b82  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180075b88  jmp     short loc_180075B93
0x180075b8a  mov     ebx, 80041006h
0x180075b8f  mov     [rsp+228h+var_1F8], ebx
0x180075b93  lea     rcx, [rsp+228h+var_1E0]
0x180075b98  call    ??1?$CVectorDeleteMe@E@@QEAA@XZ; CVectorDeleteMe<uchar>::~CVectorDeleteMe<uchar>(void)
0x180075b9d  test    ebx, ebx
0x180075b9f  jns     short loc_180075BB2
0x180075ba1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180075ba7  mov     edx, ebx
0x180075ba9  mov     rcx, rax
0x180075bac  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180075bb2  lea     rax, WPP_GLOBAL_Control
0x180075bb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180075bc0  cmp     rcx, rax
0x180075bc3  jz      short loc_180075BE9
0x180075bc5  test    byte ptr [rcx+1Ch], 1
0x180075bc9  jz      short loc_180075BE9
0x180075bcb  cmp     byte ptr [rcx+19h], 2
0x180075bcf  jb      short loc_180075BE9
0x180075bd1  mov     edx, 0ADh
0x180075bd6  mov     r9d, ebx
0x180075bd9  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x180075be0  mov     rcx, [rcx+10h]
0x180075be4  call    WPP_SF_d
0x180075be9  mov     eax, ebx
0x180075beb  jmp     short loc_180075BF2
0x180075bed  mov     eax, 80041006h
0x180075bf2  mov     rcx, [rsp+228h+var_48]
0x180075bfa  xor     rcx, rsp; StackCookie
0x180075bfd  call    __security_check_cookie
0x180075c02  add     rsp, 1F8h
0x180075c09  pop     r15
0x180075c0b  pop     r14
0x180075c0d  pop     r12
0x180075c0f  pop     rdi
0x180075c10  pop     rsi
0x180075c11  pop     rbx
0x180075c12  retn
```
