# CFileAccessor::BindToFilter(IFilter * *)

- ea: `0x1800064a0`
- end: `0x180006654`
- name: `?BindToFilter@CFileAccessor@@UEAAJPEAPEAUIFilter@@@Z`
- size: `436`
- prototype: `__int64 __fastcall(CFileAccessor *__hidden this, struct IFilter **)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005a50`
- `0x1800064a0`
- `0x180006660`
- `0x180006ad0`
- `0x180006b20`
- `0x1800070b8`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180006548`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180006548`
- `ntdll!RtlIsPartialPlaceholder` at `0x180006575`
- `ntdll!RtlIsPartialPlaceholder` at `0x180006575`

## pseudocode

```c
__int64 __fastcall CFileAccessor::BindToFilter(CFileAccessor *this, struct IFilter **a2)
{
  __int64 v4; // rcx
  __int64 result; // rax
  CDirFltr *v6; // rsi
  int v7; // ecx
  LCID SystemDefaultLCID; // eax
  signed int v9; // ebx
  CDirFltr *v10; // rsi
  CDirFltr *v11; // [rsp+60h] [rbp+8h] BYREF

  *a2 = 0;
  if ( *((_DWORD *)this + 214) )
  {
    v4 = *((unsigned int *)this + 226);
    if ( (v4 & 0x10) == 0 )
    {
LABEL_6:
      v11 = 0;
      result = ATL::CComObject<CFileFltr>::CreateInstance(&v11);
      if ( (int)result < 0 )
        return result;
      v6 = v11;
      if ( v11 )
        (*(void (__fastcall **)(CDirFltr *))(*(_QWORD *)v11 + 8LL))(v11);
      v7 = *((_DWORD *)this + 226);
      *((_QWORD *)v6 + 10) = *((_QWORD *)this + 108);
      *((_QWORD *)v6 + 11) = *((_QWORD *)this + 109);
      *((_QWORD *)v6 + 12) = *((_QWORD *)this + 110);
      *((_DWORD *)v6 + 16) = v7;
      SystemDefaultLCID = GetSystemDefaultLCID();
      *((_DWORD *)v6 + 19) = 255;
      *((_DWORD *)v6 + 18) = SystemDefaultLCID;
      if ( (unsigned int)CFileAccessor::IsOplockBroken(this) )
      {
        v9 = -2147024864;
      }
      else
      {
        v9 = 0;
        (*(void (__fastcall **)(CDirFltr *))(*(_QWORD *)v6 + 8LL))(v6);
        *a2 = (struct IFilter *)v6;
      }
      goto LABEL_17;
    }
  }
  else
  {
    if ( (*((_BYTE *)this + 904) & 0x10) == 0 )
      return 2147549183LL;
    v4 = *((unsigned int *)this + 226);
  }
  if ( (*((_BYTE *)this + 860) & 6) != 0 || (unsigned __int8)RtlIsPartialPlaceholder(v4, *((unsigned int *)this + 23)) )
    goto LABEL_6;
  v11 = 0;
  result = ATL::CComObject<CDirFltr>::CreateInstance(&v11);
  if ( (int)result < 0 )
    return result;
  v10 = v11;
  if ( v11 )
    (*(void (__fastcall **)(CDirFltr *))(*(_QWORD *)v11 + 8LL))(v11);
  v9 = CDirFltr::Init(
         v10,
         *((const wchar_t **)this + 88),
         *((_DWORD *)this + 226),
         (const struct _FILETIME *)this + 108,
         (const struct _FILETIME *)this + 109,
         (const struct _FILETIME *)this + 110);
  if ( v9 >= 0 )
  {
    (*(void (__fastcall **)(CDirFltr *))(*(_QWORD *)v10 + 8LL))(v10);
    *a2 = (struct IFilter *)v10;
  }
LABEL_17:
  TComPointer<CFileStream>::~TComPointer<CFileStream>(&v11);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800064a0  mov     [rsp+arg_8], rbx
0x1800064a5  mov     [rsp+arg_10], rbp
0x1800064aa  push    rsi
0x1800064ab  push    rdi
0x1800064ac  push    r14
0x1800064ae  sub     rsp, 40h
0x1800064b2  xor     ebp, ebp
0x1800064b4  mov     r14, rdx
0x1800064b7  mov     [rdx], rbp
0x1800064ba  mov     rdi, rcx
0x1800064bd  cmp     [rcx+358h], ebp
0x1800064c3  jz      loc_180006620
0x1800064c9  mov     ecx, [rcx+388h]
0x1800064cf  test    cl, 10h
0x1800064d2  jnz     short loc_1800064DC
0x1800064d4  jmp     short loc_1800064E9
0x1800064d6  mov     ecx, [rcx+388h]
0x1800064dc  test    byte ptr [rdi+35Ch], 6
0x1800064e3  jz      loc_180006572
0x1800064e9  lea     rcx, [rsp+58h+arg_0]
0x1800064ee  mov     [rsp+58h+arg_0], rbp
0x1800064f3  call    ?CreateInstance@?$CComObject@VCFileFltr@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CFileFltr>::CreateInstance(ATL::CComObject<CFileFltr> * *)
0x1800064f8  test    eax, eax
0x1800064fa  js      loc_18000660D
0x180006500  mov     rsi, [rsp+58h+arg_0]
0x180006505  mov     [rsp+58h+arg_0], rsi
0x18000650a  test    rsi, rsi
0x18000650d  jz      short loc_18000651E
0x18000650f  mov     rax, [rsi]
0x180006512  mov     rcx, rsi
0x180006515  mov     rax, [rax+8]
0x180006519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000651e  mov     rax, [rdi+360h]
0x180006525  mov     ecx, [rdi+388h]
0x18000652b  mov     [rsi+50h], rax
0x18000652f  mov     rax, [rdi+368h]
0x180006536  mov     [rsi+58h], rax
0x18000653a  mov     rax, [rdi+370h]
0x180006541  mov     [rsi+60h], rax
0x180006545  mov     [rsi+40h], ecx
0x180006548  call    cs:__imp_GetSystemDefaultLCID
0x18000654e  mov     rcx, rdi; this
0x180006551  mov     dword ptr [rsi+4Ch], 0FFh
0x180006558  mov     [rsi+48h], eax
0x18000655b  call    ?IsOplockBroken@CFileAccessor@@AEAAHXZ; CFileAccessor::IsOplockBroken(void)
0x180006560  test    eax, eax
0x180006562  jz      loc_180006634
0x180006568  mov     ebx, 80070020h
0x18000656d  jmp     loc_180006648
0x180006572  mov     edx, [rdi+5Ch]
0x180006575  call    cs:__imp_RtlIsPartialPlaceholder
0x18000657b  test    al, al
0x18000657d  jnz     loc_1800064E9
0x180006583  lea     rcx, [rsp+58h+arg_0]
0x180006588  mov     [rsp+58h+arg_0], rbp
0x18000658d  call    ?CreateInstance@?$CComObject@VCDirFltr@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CDirFltr>::CreateInstance(ATL::CComObject<CDirFltr> * *)
0x180006592  test    eax, eax
0x180006594  js      short loc_18000660D
0x180006596  mov     rsi, [rsp+58h+arg_0]
0x18000659b  mov     [rsp+58h+arg_0], rsi
0x1800065a0  test    rsi, rsi
0x1800065a3  jz      short loc_1800065B4
0x1800065a5  mov     rax, [rsi]
0x1800065a8  mov     rcx, rsi
0x1800065ab  mov     rax, [rax+8]
0x1800065af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065b4  mov     r8d, [rdi+388h]; unsigned int
0x1800065bb  lea     rax, [rdi+370h]
0x1800065c2  mov     rdx, [rdi+2C0h]; wchar_t *
0x1800065c9  lea     rcx, [rdi+368h]
0x1800065d0  mov     [rsp+58h+var_30], rax; struct _FILETIME *
0x1800065d5  lea     r9, [rdi+360h]; struct _FILETIME *
0x1800065dc  mov     [rsp+58h+var_38], rcx; struct _FILETIME *
0x1800065e1  mov     rcx, rsi; this
0x1800065e4  call    ?Init@CDirFltr@@QEAAJPEB_WKAEBU_FILETIME@@111H@Z; CDirFltr::Init(wchar_t const *,ulong,_FILETIME const &,_FILETIME const &,_FILETIME const &,_FILETIME const &,int)
0x1800065e9  mov     ebx, eax
0x1800065eb  test    eax, eax
0x1800065ed  js      short loc_180006601
0x1800065ef  mov     rcx, [rsi]
0x1800065f2  mov     rax, [rcx+8]
0x1800065f6  mov     rcx, rsi
0x1800065f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065fe  mov     [r14], rsi
0x180006601  lea     rcx, [rsp+58h+arg_0]
0x180006606  call    ??1?$TComPointer@VCFileStream@@@@QEAA@XZ; TComPointer<CFileStream>::~TComPointer<CFileStream>(void)
0x18000660b  mov     eax, ebx
0x18000660d  mov     rbx, [rsp+58h+arg_8]
0x180006612  mov     rbp, [rsp+58h+arg_10]
0x180006617  add     rsp, 40h
0x18000661b  pop     r14
0x18000661d  pop     rdi
0x18000661e  pop     rsi
0x18000661f  retn
0x180006620  test    byte ptr [rcx+388h], 10h
0x180006627  jnz     loc_1800064D6
0x18000662d  mov     eax, 8000FFFFh
0x180006632  jmp     short loc_18000660D
0x180006634  mov     rcx, [rsi]
0x180006637  mov     ebx, ebp
0x180006639  mov     rax, [rcx+8]
0x18000663d  mov     rcx, rsi
0x180006640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006645  mov     [r14], rsi
0x180006648  lea     rcx, [rsp+58h+arg_0]
0x18000664d  call    ??1?$TComPointer@VCFileStream@@@@QEAA@XZ; TComPointer<CFileStream>::~TComPointer<CFileStream>(void)
0x180006652  jmp     short loc_18000660B
```
