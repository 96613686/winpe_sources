# CPDFInterface::ImportToProvider(ISimpleTableWrite *)

- ea: `0x180046e60`
- end: `0x1800470fb`
- name: `?ImportToProvider@CPDFInterface@@QEAAJPEAUISimpleTableWrite@@@Z`
- size: `667`
- prototype: `__int64 __fastcall(CPDFInterface *__hidden this, struct ISimpleTableWrite *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800465e0`

## callees

- `0x180044d94`
- `0x180046e60`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `CLBCatQ!GetSimpleTableDispenser` at `0x180046fe3`
- `CLBCatQ!GetSimpleTableDispenser` at `0x180046fe3`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180046eb9`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180046ed1`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180046eb9`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180046ed1`

## pseudocode

```c
__int64 __fastcall CPDFInterface::ImportToProvider(CPDFInterface *this, struct ISimpleTableWrite *a2)
{
  const OLECHAR *v4; // rcx
  unsigned int SimpleTableDispenser; // ebx
  unsigned int v6; // eax
  __int64 v7; // rcx
  __int64 v9; // [rsp+50h] [rbp-29h] BYREF
  int v10; // [rsp+58h] [rbp-21h] BYREF
  signed __int64 v11; // [rsp+60h] [rbp-19h] BYREF
  GUID v12; // [rsp+68h] [rbp-11h] BYREF
  GUID pclsid; // [rsp+78h] [rbp-1h] BYREF
  __int128 v14; // [rsp+88h] [rbp+Fh] BYREF
  __int128 v15; // [rsp+98h] [rbp+1Fh]
  int *v16; // [rsp+A8h] [rbp+2Fh]

  v10 = 1;
  v4 = (const OLECHAR *)*((_QWORD *)this + 4);
  pclsid = GUID_NULL;
  v16 = 0;
  v12 = GUID_NULL;
  v14 = 0;
  v15 = 0;
  SimpleTableDispenser = CLSIDFromString(v4, &pclsid);
  if ( SimpleTableDispenser )
    return SimpleTableDispenser;
  SimpleTableDispenser = CLSIDFromString(*((LPCOLESTR *)this + 1), &v12);
  if ( SimpleTableDispenser )
    return SimpleTableDispenser;
  *(_QWORD *)&v14 = &v12;
  *((_QWORD *)&v14 + 1) = *((_QWORD *)this + 13);
  *(_QWORD *)&v15 = &GUID_NULL;
  *((_QWORD *)&v15 + 1) = &pclsid;
  v16 = &v10;
  v6 = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, _QWORD, __int128 *))(*(_QWORD *)a2 + 56LL))(a2, 0, &v14);
  SimpleTableDispenser = v6;
  if ( v6 )
  {
    if ( v6 == -2146367487 )
      return (unsigned int)-2146368488;
    return SimpleTableDispenser;
  }
  SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)a2 + 128LL))(a2);
  if ( SimpleTableDispenser )
    return SimpleTableDispenser;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, _QWORD, _QWORD))(*(_QWORD *)a2 + 160LL))(
                           a2,
                           11,
                           0,
                           *((_QWORD *)this + 2));
  if ( SimpleTableDispenser )
    return SimpleTableDispenser;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)a2 + 144LL))(a2);
  if ( SimpleTableDispenser )
    return SimpleTableDispenser;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)a2 + 96LL))(a2);
  if ( SimpleTableDispenser || !*((_DWORD *)this + 18) )
    return SimpleTableDispenser;
  v7 = qword_180075518;
  v9 = 0;
  if ( qword_180075518 )
    goto LABEL_18;
  v11 = 0;
  SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v11);
  if ( (SimpleTableDispenser & 0x80000000) != 0 )
  {
LABEL_19:
    if ( (SimpleTableDispenser & 0x80000000) == 0 )
    {
      SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 24LL))(v9);
      if ( (SimpleTableDispenser & 0x80000000) == 0 )
      {
        SimpleTableDispenser = AddRolesToProvider(
                                 31,
                                 v9,
                                 *((_QWORD *)this + 13),
                                 *(const OLECHAR **)this,
                                 *((const OLECHAR **)this + 1),
                                 *((const OLECHAR **)this + 4),
                                 (__int64)this + 48);
        if ( !SimpleTableDispenser )
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 96LL))(v9);
      }
    }
    goto LABEL_23;
  }
  if ( v11 )
  {
    if ( _InterlockedCompareExchange64(&qword_180075518, v11, 0) )
      (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v11 + 16LL))(v11);
    v7 = qword_180075518;
LABEL_18:
    SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *, _QWORD, _QWORD, int, int, __int64 *))(*(_QWORD *)v7 + 24LL))(
                             v7,
                             didCOMSERVICES,
                             tidCOMSERVICES_LT_ROLESBYINTERFACE,
                             0,
                             0,
                             1,
                             12,
                             &v9);
    goto LABEL_19;
  }
  SimpleTableDispenser = -2147024882;
LABEL_23:
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  return SimpleTableDispenser;
}

```

## disassembly

```asm
0x180046e60  mov     [rsp-8+arg_10], rbx
0x180046e65  push    rbp
0x180046e66  push    rsi
0x180046e67  push    rdi
0x180046e68  lea     rbp, [rsp-47h]
0x180046e6d  sub     rsp, 0C0h
0x180046e74  mov     rax, cs:__security_cookie
0x180046e7b  xor     rax, rsp
0x180046e7e  mov     [rbp+57h+var_20], rax
0x180046e82  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180046e89  mov     rdi, rdx
0x180046e8c  mov     [rbp+57h+var_78], 1
0x180046e93  mov     rsi, rcx
0x180046e96  lea     rdx, [rbp+57h+pclsid]; pclsid
0x180046e9a  mov     rcx, [rcx+20h]; lpsz
0x180046e9e  xor     eax, eax
0x180046ea0  movdqu  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x180046ea5  mov     [rbp+57h+var_28], rax
0x180046ea9  movdqu  xmmword ptr [rbp+57h+var_68.Data1], xmm0
0x180046eae  xorps   xmm0, xmm0
0x180046eb1  movups  [rbp+57h+var_48], xmm0
0x180046eb5  movups  [rbp+57h+var_38], xmm0
0x180046eb9  call    cs:__imp_CLSIDFromString
0x180046ebf  mov     ebx, eax
0x180046ec1  test    eax, eax
0x180046ec3  jnz     loc_1800470DA
0x180046ec9  mov     rcx, [rsi+8]; lpsz
0x180046ecd  lea     rdx, [rbp+57h+var_68]; pclsid
0x180046ed1  call    cs:__imp_CLSIDFromString
0x180046ed7  mov     ebx, eax
0x180046ed9  test    eax, eax
0x180046edb  jnz     loc_1800470DA
0x180046ee1  lea     rax, [rbp+57h+var_68]
0x180046ee5  xor     edx, edx
0x180046ee7  mov     qword ptr [rbp+57h+var_48], rax
0x180046eeb  lea     r8, [rbp+57h+var_48]
0x180046eef  mov     rax, [rsi+68h]
0x180046ef3  mov     rcx, rdi
0x180046ef6  mov     qword ptr [rbp+57h+var_48+8], rax
0x180046efa  lea     rax, GUID_NULL
0x180046f01  mov     qword ptr [rbp+57h+var_38], rax
0x180046f05  lea     rax, [rbp+57h+pclsid]
0x180046f09  mov     qword ptr [rbp+57h+var_38+8], rax
0x180046f0d  lea     rax, [rbp+57h+var_78]
0x180046f11  mov     [rbp+57h+var_28], rax
0x180046f15  mov     rax, [rdi]
0x180046f18  mov     rax, [rax+38h]
0x180046f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046f21  mov     ebx, eax
0x180046f23  test    eax, eax
0x180046f25  jz      short loc_180046F3C
0x180046f27  cmp     eax, 80110801h
0x180046f2c  jnz     loc_1800470DA
0x180046f32  mov     ebx, 80110418h
0x180046f37  jmp     loc_1800470DA
0x180046f3c  mov     rax, [rdi]
0x180046f3f  mov     rcx, rdi
0x180046f42  mov     rax, [rax+80h]
0x180046f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046f4e  mov     ebx, eax
0x180046f50  test    eax, eax
0x180046f52  jnz     loc_1800470DA
0x180046f58  mov     rax, [rdi]
0x180046f5b  lea     edx, [rbx+0Bh]
0x180046f5e  mov     r9, [rsi+10h]
0x180046f62  xor     r8d, r8d
0x180046f65  mov     rcx, rdi
0x180046f68  mov     rax, [rax+0A0h]
0x180046f6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046f74  mov     ebx, eax
0x180046f76  test    eax, eax
0x180046f78  jnz     loc_1800470DA
0x180046f7e  mov     rax, [rdi]
0x180046f81  mov     rcx, rdi
0x180046f84  mov     rax, [rax+90h]
0x180046f8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046f90  mov     ebx, eax
0x180046f92  test    eax, eax
0x180046f94  jnz     loc_1800470DA
0x180046f9a  mov     rax, [rdi]
0x180046f9d  mov     rcx, rdi
0x180046fa0  mov     rax, [rax+60h]
0x180046fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046fa9  mov     ebx, eax
0x180046fab  test    eax, eax
0x180046fad  jnz     loc_1800470DA
0x180046fb3  lea     rdi, [rsi+30h]
0x180046fb7  cmp     [rdi+18h], eax
0x180046fba  jz      loc_1800470DA
0x180046fc0  mov     rcx, cs:qword_180075518
0x180046fc7  mov     [rbp+57h+var_80], 0
0x180046fcf  test    rcx, rcx
0x180046fd2  jnz     short loc_180047026
0x180046fd4  mov     [rbp+57h+var_70], rcx
0x180046fd8  lea     rdx, [rbp+57h+var_70]
0x180046fdc  lea     rcx, IID_ISimpleTableDispenser
0x180046fe3  call    cs:__imp_GetSimpleTableDispenser
0x180046fe9  mov     ebx, eax
0x180046feb  test    eax, eax
0x180046fed  js      short loc_180047067
0x180046fef  mov     rcx, [rbp+57h+var_70]
0x180046ff3  test    rcx, rcx
0x180046ff6  jnz     short loc_180047002
0x180046ff8  mov     ebx, 8007000Eh
0x180046ffd  jmp     loc_1800470C5
0x180047002  xor     eax, eax
0x180047004  lock cmpxchg cs:qword_180075518, rcx
0x18004700d  jz      short loc_18004701F
0x18004700f  mov     rcx, [rbp+57h+var_70]
0x180047013  mov     rax, [rcx]
0x180047016  mov     rax, [rax+10h]
0x18004701a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004701f  mov     rcx, cs:qword_180075518
0x180047026  mov     rax, [rcx]
0x180047029  lea     rdx, [rbp+57h+var_80]
0x18004702d  mov     [rsp+0D0h+var_98], rdx
0x180047032  lea     r8, tidCOMSERVICES_LT_ROLESBYINTERFACE
0x180047039  mov     dword ptr [rsp+0D0h+var_A0], 0Ch
0x180047041  lea     rdx, didCOMSERVICES
0x180047048  mov     dword ptr [rsp+0D0h+var_A8], 1
0x180047050  xor     r9d, r9d
0x180047053  mov     rax, [rax+18h]
0x180047057  mov     [rsp+0D0h+var_B0], 0
0x180047060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047065  mov     ebx, eax
0x180047067  test    ebx, ebx
0x180047069  js      short loc_1800470C5
0x18004706b  mov     rcx, [rbp+57h+var_80]
0x18004706f  mov     rax, [rcx]
0x180047072  mov     rax, [rax+18h]
0x180047076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004707b  mov     ebx, eax
0x18004707d  test    eax, eax
0x18004707f  js      short loc_1800470C5
0x180047081  mov     rax, [rsi+20h]
0x180047085  mov     ecx, 1Fh
0x18004708a  mov     r9, [rsi]
0x18004708d  mov     r8, [rsi+68h]
0x180047091  mov     rdx, [rbp+57h+var_80]
0x180047095  mov     [rsp+0D0h+var_A0], rdi
0x18004709a  mov     [rsp+0D0h+var_A8], rax
0x18004709f  mov     rax, [rsi+8]
0x1800470a3  mov     [rsp+0D0h+var_B0], rax
0x1800470a8  call    ?AddRolesToProvider@@YAJHPEAUISimpleTableWrite@@AEBU_GUID@@PEBG22AEAV?$CList@VCString@@AEAV1@@@@Z; AddRolesToProvider(int,ISimpleTableWrite *,_GUID const &,ushort const *,ushort const *,ushort const *,CList<CString,CString &> &)
0x1800470ad  mov     ebx, eax
0x1800470af  test    eax, eax
0x1800470b1  jnz     short loc_1800470C5
0x1800470b3  mov     rcx, [rbp+57h+var_80]
0x1800470b7  mov     rax, [rcx]
0x1800470ba  mov     rax, [rax+60h]
0x1800470be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800470c3  mov     ebx, eax
0x1800470c5  mov     rcx, [rbp+57h+var_80]
0x1800470c9  test    rcx, rcx
0x1800470cc  jz      short loc_1800470DA
0x1800470ce  mov     rax, [rcx]
0x1800470d1  mov     rax, [rax+10h]
0x1800470d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800470da  mov     eax, ebx
0x1800470dc  mov     rcx, [rbp+57h+var_20]
0x1800470e0  xor     rcx, rsp; StackCookie
0x1800470e3  call    __security_check_cookie
0x1800470e8  mov     rbx, [rsp+0D0h+arg_10]
0x1800470f0  add     rsp, 0C0h
0x1800470f7  pop     rdi
0x1800470f8  pop     rsi
0x1800470f9  pop     rbp
0x1800470fa  retn
```
