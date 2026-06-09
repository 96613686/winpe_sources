# CWin32LoadGroupDependency::GetDependentsFromService(CHString const &,CHStringArray &)

- ea: `0x1800a42cc`
- end: `0x1800a4563`
- name: `?GetDependentsFromService@CWin32LoadGroupDependency@@AEAAJAEBVCHString@@AEAVCHStringArray@@@Z`
- size: `663`
- prototype: `__int64 __fastcall(CWin32LoadGroupDependency *__hidden this, const struct CHString *, struct CHStringArray *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800a3e60`
- `0x1800a4570`

## callees

- `0x18000ab30`
- `0x180013ae0`
- `0x18002f1cc`
- `0x18008bb9c`
- `0x1800a42cc`
- `0x1800fc980`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1800a4457`
- `msvcrt!wcsrchr` at `0x1800a4457`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800a430b`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800a4317`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800a430b`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800a4317`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800a4344`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800a442b`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800a44a5`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800a44f3`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800a4344`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800a442b`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800a44a5`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800a44f3`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x1800a4481`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x1800a44cf`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x1800a4481`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x1800a44cf`
- `framedynos!?GetLength@CHString@@QEBAHXZ` at `0x1800a43dd`
- `framedynos!?GetLength@CHString@@QEBAHXZ` at `0x1800a43dd`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x1800a42ff`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x1800a42ff`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x1800a4538`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x1800a4538`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x1800a435f`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x1800a435f`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800a432a`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800a432a`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800a43ca`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800a43ca`
- `framedynos!?Compare@CHString@@QEBAHPEBG@Z` at `0x1800a4393`
- `framedynos!?Compare@CHString@@QEBAHPEBG@Z` at `0x1800a4393`
- `framedynos!??H@YA?AVCHString@@AEBV0@PEBG@Z` at `0x1800a4472`
- `framedynos!??H@YA?AVCHString@@AEBV0@PEBG@Z` at `0x1800a44c0`
- `framedynos!??H@YA?AVCHString@@AEBV0@PEBG@Z` at `0x1800a4472`
- `framedynos!??H@YA?AVCHString@@AEBV0@PEBG@Z` at `0x1800a44c0`
- `framedynos!?Add@CHStringArray@@QEAAHPEBG@Z` at `0x1800a44b1`
- `framedynos!?Add@CHStringArray@@QEAAHPEBG@Z` at `0x1800a44ff`
- `framedynos!?Add@CHStringArray@@QEAAHPEBG@Z` at `0x1800a44b1`
- `framedynos!?Add@CHStringArray@@QEAAHPEBG@Z` at `0x1800a44ff`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x1800a437d`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x1800a437d`
- `framedynos!?Empty@CHString@@QEAAXXZ` at `0x1800a43a2`
- `framedynos!?Empty@CHString@@QEAAXXZ` at `0x1800a43a2`
- `framedynos!??YCHString@@QEAAAEBV0@AEBV0@@Z` at `0x1800a4339`
- `framedynos!??YCHString@@QEAAAEBV0@AEBV0@@Z` at `0x1800a4339`
- `framedynos!??YCHString@@QEAAAEBV0@D@Z` at `0x1800a449a`
- `framedynos!??YCHString@@QEAAAEBV0@D@Z` at `0x1800a44e8`
- `framedynos!??YCHString@@QEAAAEBV0@D@Z` at `0x1800a449a`
- `framedynos!??YCHString@@QEAAAEBV0@D@Z` at `0x1800a44e8`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800a448d`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800a44db`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800a4514`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800a4520`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800a452c`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800a448d`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800a44db`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800a4514`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800a4520`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800a452c`

## string_xrefs

- `0x1800a431e`: `SYSTEM\CurrentControlSet\Services\`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CWin32LoadGroupDependency::GetDependentsFromService(
        CWin32LoadGroupDependency *this,
        const struct CHString *a2,
        struct CHStringArray *a3)
{
  const unsigned __int16 *v6; // rax
  unsigned int CurrentKeyValue; // eax
  unsigned int v8; // esi
  unsigned __int64 v9; // r14
  __int64 v10; // rdi
  void *v11; // rbx
  const unsigned __int16 *v12; // rax
  wchar_t *v13; // rax
  wchar_t *v14; // rdi
  char *v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rdx
  const unsigned __int16 *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rdx
  const unsigned __int16 *v21; // rax
  _BYTE v23[8]; // [rsp+20h] [rbp-2D8h] BYREF
  _BYTE v24[8]; // [rsp+28h] [rbp-2D0h] BYREF
  int pExceptionObject; // [rsp+30h] [rbp-2C8h] BYREF
  _BYTE v26[8]; // [rsp+38h] [rbp-2C0h] BYREF
  _BYTE v27[8]; // [rsp+40h] [rbp-2B8h] BYREF
  void *v28; // [rsp+48h] [rbp-2B0h]
  _BYTE v29[608]; // [rsp+50h] [rbp-2A8h] BYREF

  CRegistry::CRegistry((CRegistry *)v29);
  CHString::CHString((CHString *)v24);
  CHString::CHString((CHString *)v23);
  CHString::CHString((CHString *)v26, L"SYSTEM\\CurrentControlSet\\Services\\");
  CHString::operator+=(v26, a2);
  v6 = (const unsigned __int16 *)CHString::operator unsigned short const *(v26);
  CurrentKeyValue = CRegistry::Open((CRegistry *)v29, HKEY_LOCAL_MACHINE, v6, 0x20019u);
  if ( !CurrentKeyValue )
  {
    CurrentKeyValue = CRegistry::GetCurrentKeyValue((CRegistry *)v29, L"DependOnGroup", (struct CHString *)v24);
    if ( !CurrentKeyValue )
    {
      if ( !CHString::Compare((CHString *)v24, (const unsigned __int16 *)&Data) )
        CHString::Empty((CHString *)v24);
LABEL_8:
      v8 = 0;
      goto LABEL_9;
    }
  }
  if ( CurrentKeyValue == 5 )
  {
    v8 = -2147217405;
    goto LABEL_9;
  }
  v8 = -2147217407;
  if ( CurrentKeyValue == -2147221165 )
    goto LABEL_8;
LABEL_9:
  if ( !CHString::IsEmpty((CHString *)v24) )
  {
    v9 = (unsigned int)(CHString::GetLength((CHString *)v24) + 1);
    v10 = -1;
    v11 = operator new(saturated_mul(v9, 2u));
    v28 = v11;
    if ( !v11 )
    {
      pExceptionObject = 0;
      throw (CHeap_Exception *)&pExceptionObject;
    }
    try
    {
      v12 = (const unsigned __int16 *)CHString::operator unsigned short const *(v24);
      StringCchCopyW((unsigned __int16 *)v11, v9, v12);
      do
        ++v10;
      while ( *((_WORD *)v11 + v10) );
      *((_WORD *)v11 + v10 - 1) = 0;
      while ( 1 )
      {
        v13 = wcsrchr((const wchar_t *)v11, 0xAu);
        v14 = v13;
        v15 = (char *)this + 88;
        if ( !v13 )
          break;
        v16 = operator+(v27, v15, v13 + 1);
        CHString::operator=(v23, v16);
        CHString::~CHString((CHString *)v27);
        LOBYTE(v17) = 34;
        CHString::operator+=(v23, v17);
        v18 = (const unsigned __int16 *)CHString::operator unsigned short const *(v23);
        CHStringArray::Add(a3, v18);
        *v14 = 0;
      }
      v19 = operator+(v27, v15, v11);
      CHString::operator=(v23, v19);
      CHString::~CHString((CHString *)v27);
      LOBYTE(v20) = 34;
      CHString::operator+=(v23, v20);
      v21 = (const unsigned __int16 *)CHString::operator unsigned short const *(v23);
      CHStringArray::Add(a3, v21);
    }
    catch ( ... )
    {
      operator delete(v28);
      throw;
    }
    operator delete(v11);
  }
  CHString::~CHString((CHString *)v26);
  CHString::~CHString((CHString *)v23);
  CHString::~CHString((CHString *)v24);
  CRegistry::~CRegistry((CRegistry *)v29);
  return v8;
}

```

## disassembly

```asm
0x1800a42cc  push    rbx
0x1800a42ce  push    rsi
0x1800a42cf  push    rdi
0x1800a42d0  push    r12
0x1800a42d2  push    r13
0x1800a42d4  push    r14
0x1800a42d6  push    r15
0x1800a42d8  sub     rsp, 2C0h
0x1800a42df  mov     rax, cs:__security_cookie
0x1800a42e6  xor     rax, rsp
0x1800a42e9  mov     [rsp+2F8h+var_48], rax
0x1800a42f1  mov     r12, r8
0x1800a42f4  mov     rbx, rdx
0x1800a42f7  mov     r15, rcx
0x1800a42fa  lea     rcx, [rsp+2F8h+var_2A8]
0x1800a42ff  call    cs:__imp_??0CRegistry@@QEAA@XZ; CRegistry::CRegistry(void)
0x1800a4305  nop
0x1800a4306  lea     rcx, [rsp+2F8h+var_2D0]
0x1800a430b  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800a4311  nop
0x1800a4312  lea     rcx, [rsp+2F8h+var_2D8]
0x1800a4317  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800a431d  nop
0x1800a431e  lea     rdx, aSystemCurrentc_7; "SYSTEM\\CurrentControlSet\\Services\\"
0x1800a4325  lea     rcx, [rsp+2F8h+var_2C0]
0x1800a432a  call    cs:__imp_??0CHString@@QEAA@PEBG@Z; CHString::CHString(ushort const *)
0x1800a4330  nop
0x1800a4331  mov     rdx, rbx
0x1800a4334  lea     rcx, [rsp+2F8h+var_2C0]
0x1800a4339  call    cs:__imp_??YCHString@@QEAAAEBV0@AEBV0@@Z; CHString::operator+=(CHString const &)
0x1800a433f  lea     rcx, [rsp+2F8h+var_2C0]
0x1800a4344  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x1800a434a  mov     r8, rax
0x1800a434d  mov     rdx, 0FFFFFFFF80000002h
0x1800a4354  mov     r9d, 20019h
0x1800a435a  lea     rcx, [rsp+2F8h+var_2A8]
0x1800a435f  call    cs:__imp_?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong)
0x1800a4365  xor     r13d, r13d
0x1800a4368  test    eax, eax
0x1800a436a  jnz     short loc_1800A43AA
0x1800a436c  lea     r8, [rsp+2F8h+var_2D0]
0x1800a4371  lea     rdx, aDependongroup; "DependOnGroup"
0x1800a4378  lea     rcx, [rsp+2F8h+var_2A8]
0x1800a437d  call    cs:__imp_?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z; CRegistry::GetCurrentKeyValue(ushort const *,CHString &)
0x1800a4383  test    eax, eax
0x1800a4385  jnz     short loc_1800A43AA
0x1800a4387  lea     rdx, Data
0x1800a438e  lea     rcx, [rsp+2F8h+var_2D0]
0x1800a4393  call    cs:__imp_?Compare@CHString@@QEBAHPEBG@Z; CHString::Compare(ushort const *)
0x1800a4399  test    eax, eax
0x1800a439b  jnz     short loc_1800A43C2
0x1800a439d  lea     rcx, [rsp+2F8h+var_2D0]
0x1800a43a2  call    cs:__imp_?Empty@CHString@@QEAAXXZ; CHString::Empty(void)
0x1800a43a8  jmp     short loc_1800A43C2
0x1800a43aa  cmp     eax, 5
0x1800a43ad  jnz     short loc_1800A43B6
0x1800a43af  mov     esi, 80041003h
0x1800a43b4  jmp     short loc_1800A43C5
0x1800a43b6  cmp     eax, 80040153h
0x1800a43bb  mov     esi, 80041001h
0x1800a43c0  jnz     short loc_1800A43C5
0x1800a43c2  mov     esi, r13d
0x1800a43c5  lea     rcx, [rsp+2F8h+var_2D0]
0x1800a43ca  call    cs:__imp_?IsEmpty@CHString@@QEBAHXZ; CHString::IsEmpty(void)
0x1800a43d0  test    eax, eax
0x1800a43d2  jnz     loc_1800A450F
0x1800a43d8  lea     rcx, [rsp+2F8h+var_2D0]
0x1800a43dd  call    cs:__imp_?GetLength@CHString@@QEBAHXZ; CHString::GetLength(void)
0x1800a43e3  lea     r14d, [rax+1]
0x1800a43e7  mov     eax, 2
0x1800a43ec  mul     r14
0x1800a43ef  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x1800a43f6  cmovb   rax, rdi
0x1800a43fa  mov     rcx, rax; unsigned __int64
0x1800a43fd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a4402  mov     rbx, rax
0x1800a4405  mov     [rsp+2F8h+var_2B0], rax
0x1800a440a  test    rax, rax
0x1800a440d  jnz     short loc_1800A4426
0x1800a440f  mov     [rsp+2F8h+pExceptionObject], r13d
0x1800a4414  lea     rdx, _TI1?AVCHeap_Exception@@; pThrowInfo
0x1800a441b  lea     rcx, [rsp+2F8h+pExceptionObject]; pExceptionObject
0x1800a4420  call    _CxxThrowException_0
0x1800a4426  lea     rcx, [rsp+2F8h+var_2D0]
0x1800a442b  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x1800a4431  mov     r8, rax; unsigned __int16 *
0x1800a4434  mov     rdx, r14; unsigned __int64
0x1800a4437  mov     rcx, rbx; unsigned __int16 *
0x1800a443a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a443f  inc     rdi
0x1800a4442  cmp     [rbx+rdi*2], r13w
0x1800a4447  jnz     short loc_1800A443F
0x1800a4449  mov     [rbx+rdi*2-2], r13w
0x1800a444f  mov     edx, 0Ah; Ch
0x1800a4454  mov     rcx, rbx; Str
0x1800a4457  call    cs:__imp_wcsrchr
0x1800a445d  mov     rdi, rax
0x1800a4460  lea     rdx, [r15+58h]
0x1800a4464  lea     rcx, [rsp+2F8h+var_2B8]
0x1800a4469  test    rax, rax
0x1800a446c  jz      short loc_1800A44BD
0x1800a446e  lea     r8, [rax+2]
0x1800a4472  call    cs:__imp_??H@YA?AVCHString@@AEBV0@PEBG@Z; operator+(CHString const &,ushort const *)
0x1800a4478  nop
0x1800a4479  mov     rdx, rax
0x1800a447c  lea     rcx, [rsp+2F8h+var_2D8]
0x1800a4481  call    cs:__imp_??4CHString@@QEAAAEBV0@AEBV0@@Z; CHString::operator=(CHString const &)
0x1800a4487  nop
0x1800a4488  lea     rcx, [rsp+2F8h+var_2B8]
0x1800a448d  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800a4493  mov     dl, 22h ; '"'
0x1800a4495  lea     rcx, [rsp+2F8h+var_2D8]
0x1800a449a  call    cs:__imp_??YCHString@@QEAAAEBV0@D@Z; CHString::operator+=(char)
0x1800a44a0  lea     rcx, [rsp+2F8h+var_2D8]
0x1800a44a5  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x1800a44ab  mov     rdx, rax
0x1800a44ae  mov     rcx, r12
0x1800a44b1  call    cs:__imp_?Add@CHStringArray@@QEAAHPEBG@Z; CHStringArray::Add(ushort const *)
0x1800a44b7  mov     [rdi], r13w
0x1800a44bb  jmp     short loc_1800A444F
0x1800a44bd  mov     r8, rbx
0x1800a44c0  call    cs:__imp_??H@YA?AVCHString@@AEBV0@PEBG@Z; operator+(CHString const &,ushort const *)
0x1800a44c6  nop
0x1800a44c7  mov     rdx, rax
0x1800a44ca  lea     rcx, [rsp+2F8h+var_2D8]
0x1800a44cf  call    cs:__imp_??4CHString@@QEAAAEBV0@AEBV0@@Z; CHString::operator=(CHString const &)
0x1800a44d5  nop
0x1800a44d6  lea     rcx, [rsp+2F8h+var_2B8]
0x1800a44db  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800a44e1  mov     dl, 22h ; '"'
0x1800a44e3  lea     rcx, [rsp+2F8h+var_2D8]
0x1800a44e8  call    cs:__imp_??YCHString@@QEAAAEBV0@D@Z; CHString::operator+=(char)
0x1800a44ee  lea     rcx, [rsp+2F8h+var_2D8]
0x1800a44f3  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x1800a44f9  mov     rdx, rax
0x1800a44fc  mov     rcx, r12
0x1800a44ff  call    cs:__imp_?Add@CHStringArray@@QEAAHPEBG@Z; CHStringArray::Add(ushort const *)
0x1800a4505  nop
0x1800a4506  mov     rcx, rbx; void *
0x1800a4509  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a450e  nop
0x1800a450f  lea     rcx, [rsp+2F8h+var_2C0]
0x1800a4514  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800a451a  nop
0x1800a451b  lea     rcx, [rsp+2F8h+var_2D8]
0x1800a4520  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800a4526  nop
0x1800a4527  lea     rcx, [rsp+2F8h+var_2D0]
0x1800a452c  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800a4532  nop
0x1800a4533  lea     rcx, [rsp+2F8h+var_2A8]
0x1800a4538  call    cs:__imp_??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x1800a453e  mov     eax, esi
0x1800a4540  mov     rcx, [rsp+2F8h+var_48]
0x1800a4548  xor     rcx, rsp; StackCookie
0x1800a454b  call    __security_check_cookie
0x1800a4550  add     rsp, 2C0h
0x1800a4557  pop     r15
0x1800a4559  pop     r14
0x1800a455b  pop     r13
0x1800a455d  pop     r12
0x1800a455f  pop     rdi
0x1800a4560  pop     rsi
0x1800a4561  pop     rbx
0x1800a4562  retn
```
