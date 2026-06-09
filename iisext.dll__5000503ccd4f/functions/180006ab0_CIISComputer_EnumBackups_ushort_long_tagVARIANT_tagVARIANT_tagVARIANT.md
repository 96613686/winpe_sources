# CIISComputer::EnumBackups(ushort *,long,tagVARIANT *,tagVARIANT *,tagVARIANT *)

- ea: `0x180006ab0`
- end: `0x180006c60`
- name: `?EnumBackups@CIISComputer@@UEAAJPEAGJPEAUtagVARIANT@@11@Z`
- size: `432`
- prototype: `int __fastcall(CIISComputer *this, unsigned __int16 *, int, struct tagVARIANT *, struct tagVARIANT *pvarg, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006ab0`
- `0x1800111e0`
- `0x180012010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180006b74`
- `msvcrt!wcscpy_s` at `0x180006b74`
- `KERNEL32!GetLastError` at `0x180006bd7`
- `KERNEL32!GetLastError` at `0x180006c02`
- `KERNEL32!GetLastError` at `0x180006bd7`
- `KERNEL32!GetLastError` at `0x180006c02`
- `KERNEL32!FileTimeToDosDateTime` at `0x180006bc8`
- `KERNEL32!FileTimeToDosDateTime` at `0x180006bc8`
- `OLEAUT32!__imp_SysAllocString` at `0x180006c22`
- `OLEAUT32!__imp_SysAllocString` at `0x180006c22`
- `OLEAUT32!__imp_SysStringLen` at `0x180006b53`
- `OLEAUT32!__imp_SysStringLen` at `0x180006b53`
- `OLEAUT32!__imp_VariantInit` at `0x180006b2c`
- `OLEAUT32!__imp_VariantInit` at `0x180006b35`
- `OLEAUT32!__imp_VariantInit` at `0x180006b3e`
- `OLEAUT32!__imp_VariantInit` at `0x180006b2c`
- `OLEAUT32!__imp_VariantInit` at `0x180006b35`
- `OLEAUT32!__imp_VariantInit` at `0x180006b3e`
- `OLEAUT32!__imp_DosDateTimeToVariantTime` at `0x180006bf8`
- `OLEAUT32!__imp_DosDateTimeToVariantTime` at `0x180006bf8`

## pseudocode

```c
int __fastcall CIISComputer::EnumBackups(
        CIISComputer *this,
        unsigned __int16 *a2,
        int a3,
        struct tagVARIANT *a4,
        struct tagVARIANT *pvarg,
        struct tagVARIANT *a6)
{
  int result; // eax
  bool v11; // sf
  bool v12; // sf
  BSTR v13; // rax
  WORD FatTime[2]; // [rsp+30h] [rbp-D0h] BYREF
  WORD FatDate; // [rsp+34h] [rbp-CCh] BYREF
  LONG v16; // [rsp+38h] [rbp-C8h] BYREF
  FILETIME FileTime; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t Destination[256]; // [rsp+50h] [rbp-B0h] BYREF

  FileTime = 0;
  FatDate = 0;
  FatTime[0] = 0;
  v16 = 0;
  if ( !a4 || !pvarg || !a6 )
    return -2147467261;
  VariantInit(a4);
  VariantInit(pvarg);
  VariantInit(a6);
  Destination[0] = 0;
  if ( a2 )
  {
    if ( SysStringLen(a2) >= 0x100 )
      return -2147024809;
    wcscpy_s(Destination, 0x100u, a2);
  }
  result = (*(__int64 (__fastcall **)(_QWORD, wchar_t *, LONG *, FILETIME *, int))(**((_QWORD **)this + 15) + 240LL))(
             *((_QWORD *)this + 15),
             Destination,
             &v16,
             &FileTime,
             a3);
  if ( result >= 0 )
  {
    a4->vt = 3;
    pvarg->vt = 8;
    a6->vt = 7;
    if ( FileTimeToDosDateTime(&FileTime, &FatDate, FatTime) )
      goto LABEL_16;
    result = GetLastError();
    v11 = result < 0;
    if ( result > 0 )
    {
      result = (unsigned __int16)result | 0x80070000;
      v11 = result < 0;
    }
    if ( !v11 )
    {
LABEL_16:
      if ( DosDateTimeToVariantTime(FatDate, FatTime[0], &a6->dblVal) )
        goto LABEL_17;
      result = GetLastError();
      v12 = result < 0;
      if ( result > 0 )
      {
        result = (unsigned __int16)result | 0x80070000;
        v12 = result < 0;
      }
      if ( !v12 )
      {
LABEL_17:
        a4->lVal = v16;
        v13 = SysAllocString(Destination);
        pvarg->llVal = (LONGLONG)v13;
        return v13 == 0 ? 0x8007000E : 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006ab0  push    rbp
0x180006ab2  push    rbx
0x180006ab3  push    rsi
0x180006ab4  push    rdi
0x180006ab5  push    r12
0x180006ab7  push    r14
0x180006ab9  push    r15
0x180006abb  lea     rbp, [rsp-160h]
0x180006ac3  sub     rsp, 260h
0x180006aca  mov     rax, cs:__security_cookie
0x180006ad1  xor     rax, rsp
0x180006ad4  mov     [rbp+190h+var_40], rax
0x180006adb  mov     rbx, [rbp+190h+arg_28]
0x180006ae2  xor     eax, eax
0x180006ae4  mov     rdi, [rbp+190h+pvarg]
0x180006aeb  mov     r14, r9
0x180006aee  mov     qword ptr [rsp+290h+FileTime.dwLowDateTime], 0
0x180006af7  mov     r12d, r8d
0x180006afa  mov     [rsp+290h+FatDate], ax
0x180006aff  mov     rsi, rdx
0x180006b02  mov     [rsp+290h+FatTime], ax
0x180006b07  mov     r15, rcx
0x180006b0a  mov     [rsp+290h+var_258], eax
0x180006b0e  test    r9, r9
0x180006b11  jz      loc_180006C3A
0x180006b17  test    rdi, rdi
0x180006b1a  jz      loc_180006C3A
0x180006b20  test    rbx, rbx
0x180006b23  jz      loc_180006C3A
0x180006b29  mov     rcx, r9; pvarg
0x180006b2c  call    cs:__imp_VariantInit
0x180006b32  mov     rcx, rdi; pvarg
0x180006b35  call    cs:__imp_VariantInit
0x180006b3b  mov     rcx, rbx; pvarg
0x180006b3e  call    cs:__imp_VariantInit
0x180006b44  xor     eax, eax
0x180006b46  mov     [rsp+290h+Destination], ax
0x180006b4b  test    rsi, rsi
0x180006b4e  jz      short loc_180006B7A
0x180006b50  mov     rcx, rsi; pbstr
0x180006b53  call    cs:__imp_SysStringLen
0x180006b59  mov     edx, 100h; SizeInWords
0x180006b5e  cmp     eax, edx
0x180006b60  jb      short loc_180006B6C
0x180006b62  mov     eax, 80070057h
0x180006b67  jmp     loc_180006C3F
0x180006b6c  mov     r8, rsi; Source
0x180006b6f  lea     rcx, [rsp+290h+Destination]; Destination
0x180006b74  call    cs:__imp_wcscpy_s
0x180006b7a  mov     rcx, [r15+78h]
0x180006b7e  lea     r9, [rsp+290h+FileTime]
0x180006b83  lea     r8, [rsp+290h+var_258]
0x180006b88  mov     [rsp+290h+var_270], r12d
0x180006b8d  lea     rdx, [rsp+290h+Destination]
0x180006b92  mov     rax, [rcx]
0x180006b95  mov     rax, [rax+0F0h]
0x180006b9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ba1  test    eax, eax
0x180006ba3  js      loc_180006C3F
0x180006ba9  mov     word ptr [r14], 3
0x180006baf  lea     r8, [rsp+290h+FatTime]; lpFatTime
0x180006bb4  mov     word ptr [rdi], 8
0x180006bb9  lea     rdx, [rsp+290h+FatDate]; lpFatDate
0x180006bbe  lea     rcx, [rsp+290h+FileTime]; lpFileTime
0x180006bc3  mov     word ptr [rbx], 7
0x180006bc8  call    cs:__imp_FileTimeToDosDateTime
0x180006bce  mov     esi, 80070000h
0x180006bd3  test    eax, eax
0x180006bd5  jnz     short loc_180006BEA
0x180006bd7  call    cs:__imp_GetLastError
0x180006bdd  test    eax, eax
0x180006bdf  jle     short loc_180006BE8
0x180006be1  movzx   eax, ax
0x180006be4  or      eax, esi
0x180006be6  test    eax, eax
0x180006be8  js      short loc_180006C3F
0x180006bea  movzx   edx, [rsp+290h+FatTime]; wDosTime
0x180006bef  lea     r8, [rbx+8]; pvtime
0x180006bf3  movzx   ecx, [rsp+290h+FatDate]; wDosDate
0x180006bf8  call    cs:__imp_DosDateTimeToVariantTime
0x180006bfe  test    eax, eax
0x180006c00  jnz     short loc_180006C15
0x180006c02  call    cs:__imp_GetLastError
0x180006c08  test    eax, eax
0x180006c0a  jle     short loc_180006C13
0x180006c0c  movzx   eax, ax
0x180006c0f  or      eax, esi
0x180006c11  test    eax, eax
0x180006c13  js      short loc_180006C3F
0x180006c15  mov     eax, [rsp+290h+var_258]
0x180006c19  lea     rcx, [rsp+290h+Destination]; psz
0x180006c1e  mov     [r14+8], eax
0x180006c22  call    cs:__imp_SysAllocString
0x180006c28  mov     [rdi+8], rax
0x180006c2c  neg     rax
0x180006c2f  sbb     eax, eax
0x180006c31  not     eax
0x180006c33  and     eax, 8007000Eh
0x180006c38  jmp     short loc_180006C3F
0x180006c3a  mov     eax, 80004003h
0x180006c3f  mov     rcx, [rbp+190h+var_40]
0x180006c46  xor     rcx, rsp; StackCookie
0x180006c49  call    __security_check_cookie
0x180006c4e  add     rsp, 260h
0x180006c55  pop     r15
0x180006c57  pop     r14
0x180006c59  pop     r12
0x180006c5b  pop     rdi
0x180006c5c  pop     rsi
0x180006c5d  pop     rbx
0x180006c5e  pop     rbp
0x180006c5f  retn
```
