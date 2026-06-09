# GenericTypeLibOLE::GetCompressedTypeId(ITypeInfo *,ushort * *)

- ea: `0x180051900`
- end: `0x180051afb`
- name: `?GetCompressedTypeId@GenericTypeLibOLE@@QEAAJPEAUITypeInfo@@PEAPEAG@Z`
- size: `507`
- prototype: `__int64 __fastcall(GenericTypeLibOLE *__hidden this, struct ITypeInfo *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800566bc`

## callees

- `0x18000a780`
- `0x180021dc0`
- `0x18003e360`
- `0x18004d900`
- `0x180051900`
- `0x180052440`
- `0x180059b90`
- `0x18005b630`
- `0x180063130`
- `0x18009c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x180051a3c`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x180051a74`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x180051a3c`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x180051a74`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180051a27`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180051ab4`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180051a27`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180051ab4`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180051a48`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180051a48`

## pseudocode

```c
__int64 __fastcall GenericTypeLibOLE::GetCompressedTypeId(
        struct ITypeLib *this,
        struct ITypeInfo *a2,
        unsigned __int16 **a3)
{
  struct ITypeInfoVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetContainingTypeLib)(ITypeInfo *, ITypeLib **, UINT *); // rax
  OLECHAR *v7; // rsi
  __int64 result; // rax
  int LibIdOfTypeLib; // edi
  unsigned int v10; // r14d
  wchar_t *v11; // rax
  __int64 v12; // rax
  int v13; // r14d
  BSTR v14; // rax
  unsigned __int16 *v15; // rbx
  int v16; // [rsp+30h] [rbp-39h]
  unsigned int v17; // [rsp+40h] [rbp-29h] BYREF
  unsigned int v18; // [rsp+44h] [rbp-25h] BYREF
  char *v19; // [rsp+48h] [rbp-21h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-19h] BYREF
  struct ITypeLib *v21; // [rsp+58h] [rbp-11h] BYREF
  struct NAMMGR *v22; // [rsp+60h] [rbp-9h] BYREF
  wchar_t Str[16]; // [rsp+68h] [rbp-1h] BYREF

  lpVtbl = a2->lpVtbl;
  v21 = 0;
  v18 = 0;
  bstrString = 0;
  GetContainingTypeLib = lpVtbl->GetContainingTypeLib;
  v22 = 0;
  memset(Str, 0, 28);
  v17 = 0;
  v7 = 0;
  result = ((__int64 (__fastcall *)(struct ITypeInfo *, struct ITypeLib **, unsigned int *))GetContainingTypeLib)(
             a2,
             &v21,
             &v18);
  LibIdOfTypeLib = result;
  if ( (int)result >= 0 )
  {
    if ( v21 == this )
    {
      v10 = 0xFFFF;
    }
    else
    {
      LibIdOfTypeLib = GetLibIdOfTypeLib(v21, &bstrString);
      if ( LibIdOfTypeLib < 0
        || (LibIdOfTypeLib = GenericTypeLibOLE::GetNamMgr((GenericTypeLibOLE *)this, &v22), LibIdOfTypeLib < 0) )
      {
        v7 = bstrString;
LABEL_15:
        SysFreeString(v7);
        ((void (__fastcall *)(struct ITypeLib *))v21->lpVtbl->Release)(v21);
        return (unsigned int)LibIdOfTypeLib;
      }
      v7 = bstrString;
      v19 = 0;
      LibIdOfTypeLib = ConvertStringToA(bstrString, &v19);
      if ( LibIdOfTypeLib < 0 )
        goto LABEL_15;
      LibIdOfTypeLib = NAMMGR::HlnamOfStr(v22, v19, &v17, 1, 0, 0, v16);
      ConvertStringFree(v19);
      if ( LibIdOfTypeLib )
        goto LABEL_15;
      v10 = v17;
      SysFreeString(v7);
      v7 = 0;
    }
    _o_wcscpy_s(Str, 14, L"*\\R");
    _o__ultow_s(v10, &Str[3], 11, 16);
    v11 = wcschr(Str, 0);
    *(_DWORD *)v11 = 2293802;
    _o__ultow_s(v18, v11 + 2, 14 - (v11 + 2 - Str), 16);
    v12 = -1;
    do
      ++v12;
    while ( Str[v12] );
    v13 = (unsigned __int16)v12;
    v14 = SysAllocStringLen(0, (unsigned __int16)v12);
    v15 = v14;
    if ( v14 )
    {
      _o_wcscpy_s(v14, (unsigned int)(v13 + 1), Str);
      *a3 = v15;
    }
    else
    {
      LibIdOfTypeLib = -2147024882;
    }
    goto LABEL_15;
  }
  return result;
}

```

## disassembly

```asm
0x180051900  push    rbp
0x180051902  push    rbx
0x180051903  push    rsi
0x180051904  push    rdi
0x180051905  push    r13
0x180051907  push    r14
0x180051909  push    r15
0x18005190b  lea     rbp, [rsp-27h]
0x180051910  sub     rsp, 90h
0x180051917  mov     rax, cs:__security_cookie
0x18005191e  xor     rax, rsp
0x180051921  mov     [rbp+57h+var_38], rax
0x180051925  mov     rax, [rdx]
0x180051928  xor     r13d, r13d
0x18005192b  mov     r9, rdx
0x18005192e  mov     [rbp+57h+var_68], r13
0x180051932  xorps   xmm0, xmm0
0x180051935  mov     [rbp+57h+var_7C], r13d
0x180051939  mov     r15, r8
0x18005193c  mov     [rbp+57h+bstrString], r13
0x180051940  mov     rax, [rax+90h]
0x180051947  lea     r8, [rbp+57h+var_7C]
0x18005194b  mov     rbx, rcx
0x18005194e  mov     [rbp+57h+var_60], r13
0x180051952  movups  xmmword ptr [rbp+57h+Str], xmm0
0x180051956  lea     rdx, [rbp+57h+var_68]
0x18005195a  mov     [rbp+57h+var_80], r13d
0x18005195e  mov     rcx, r9
0x180051961  mov     esi, r13d
0x180051964  movups  xmmword ptr [rbp+57h+Str+0Ch], xmm0
0x180051968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005196d  mov     edi, eax
0x18005196f  test    eax, eax
0x180051971  js      loc_180051ADD
0x180051977  mov     rcx, [rbp+57h+var_68]; struct ITypeLib *
0x18005197b  cmp     rcx, rbx
0x18005197e  jnz     short loc_18005198B
0x180051980  mov     r14d, 0FFFFh
0x180051986  jmp     loc_180051A15
0x18005198b  lea     rdx, [rbp+57h+bstrString]; unsigned __int16 **
0x18005198f  call    GetLibIdOfTypeLib
0x180051994  mov     edi, eax
0x180051996  test    eax, eax
0x180051998  js      loc_180051ABF
0x18005199e  lea     rdx, [rbp+57h+var_60]; struct NAMMGR **
0x1800519a2  mov     rcx, rbx; this
0x1800519a5  call    ?GetNamMgr@GenericTypeLibOLE@@QEAAJPEAPEAVNAMMGR@@@Z; GenericTypeLibOLE::GetNamMgr(NAMMGR * *)
0x1800519aa  mov     edi, eax
0x1800519ac  test    eax, eax
0x1800519ae  js      loc_180051ABF
0x1800519b4  mov     rsi, [rbp+57h+bstrString]
0x1800519b8  lea     rdx, [rbp+57h+var_78]; char **
0x1800519bc  mov     rcx, rsi; lpWideCharStr
0x1800519bf  mov     [rbp+57h+var_78], r13
0x1800519c3  call    ?ConvertStringToA@@YAJPEBGPEAPEAD@Z; ConvertStringToA(ushort const *,char * *)
0x1800519c8  mov     edi, eax
0x1800519ca  test    eax, eax
0x1800519cc  js      loc_180051AC3
0x1800519d2  mov     rdx, [rbp+57h+var_78]; char *
0x1800519d6  lea     r8, [rbp+57h+var_80]; unsigned int *
0x1800519da  mov     rcx, [rbp+57h+var_60]; this
0x1800519de  mov     r9d, 1; int
0x1800519e4  mov     [rsp+0C0h+var_98], r13d; int
0x1800519e9  mov     [rsp+0C0h+var_A0], r13; int *
0x1800519ee  call    ?HlnamOfStr@NAMMGR@@QEAAJPEBDPEAIHPEAHHH@Z; NAMMGR::HlnamOfStr(char const *,uint *,int,int *,int,int)
0x1800519f3  mov     rcx, [rbp+57h+var_78]; char *
0x1800519f7  mov     edi, eax
0x1800519f9  call    ?ConvertStringFree@@YAXPEAD@Z; ConvertStringFree(char *)
0x1800519fe  test    edi, edi
0x180051a00  jnz     loc_180051AC3
0x180051a06  mov     r14d, [rbp+57h+var_80]
0x180051a0a  mov     rcx, rsi; bstrString
0x180051a0d  call    SysFreeString
0x180051a12  mov     rsi, r13
0x180051a15  mov     ebx, 0Eh
0x180051a1a  lea     r8, aR; "*\\R"
0x180051a21  mov     edx, ebx
0x180051a23  lea     rcx, [rbp+57h+Str]
0x180051a27  call    cs:__imp__o_wcscpy_s
0x180051a2d  lea     r9d, [rbx+2]
0x180051a31  mov     ecx, r14d
0x180051a34  lea     r8d, [rbx-3]
0x180051a38  lea     rdx, [rbp+57h+Str+6]
0x180051a3c  call    cs:__imp__o__ultow_s
0x180051a42  xor     edx, edx; Ch
0x180051a44  lea     rcx, [rbp+57h+Str]; Str
0x180051a48  call    cs:__imp_wcschr
0x180051a4e  lea     rcx, [rbp+57h+Str]
0x180051a52  mov     r9d, 10h
0x180051a58  mov     dword ptr [rax], 23002Ah
0x180051a5e  lea     rdx, [rax+4]
0x180051a62  mov     rax, rdx
0x180051a65  sub     rax, rcx
0x180051a68  mov     ecx, [rbp+57h+var_7C]
0x180051a6b  sar     rax, 1
0x180051a6e  sub     rbx, rax
0x180051a71  mov     r8, rbx
0x180051a74  call    cs:__imp__o__ultow_s
0x180051a7a  lea     rcx, [rbp+57h+Str]
0x180051a7e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180051a82  inc     rax
0x180051a85  cmp     [rcx+rax*2], r13w
0x180051a8a  jnz     short loc_180051A82
0x180051a8c  movzx   r14d, ax
0x180051a90  xor     ecx, ecx; strIn
0x180051a92  mov     edx, r14d; ui
0x180051a95  call    SysAllocStringLen
0x180051a9a  mov     rbx, rax
0x180051a9d  test    rax, rax
0x180051aa0  jnz     short loc_180051AA9
0x180051aa2  mov     edi, 8007000Eh
0x180051aa7  jmp     short loc_180051AC3
0x180051aa9  lea     edx, [r14+1]
0x180051aad  mov     rcx, rbx
0x180051ab0  lea     r8, [rbp+57h+Str]
0x180051ab4  call    cs:__imp__o_wcscpy_s
0x180051aba  mov     [r15], rbx
0x180051abd  jmp     short loc_180051AC3
0x180051abf  mov     rsi, [rbp+57h+bstrString]
0x180051ac3  mov     rcx, rsi; bstrString
0x180051ac6  call    SysFreeString
0x180051acb  mov     rcx, [rbp+57h+var_68]
0x180051acf  mov     rax, [rcx]
0x180051ad2  mov     rax, [rax+10h]
0x180051ad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051adb  mov     eax, edi
0x180051add  mov     rcx, [rbp+57h+var_38]
0x180051ae1  xor     rcx, rsp; StackCookie
0x180051ae4  call    __security_check_cookie
0x180051ae9  add     rsp, 90h
0x180051af0  pop     r15
0x180051af2  pop     r14
0x180051af4  pop     r13
0x180051af6  pop     rdi
0x180051af7  pop     rsi
0x180051af8  pop     rbx
0x180051af9  pop     rbp
0x180051afa  retn
```
