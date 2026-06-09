# MvLoadXmlFile(IStream *,ushort * *)

- ea: `0x18003795c`
- end: `0x180037bd0`
- name: `?MvLoadXmlFile@@YAJPEAUIStream@@PEAPEAG@Z`
- size: `628`
- prototype: `__int64 __fastcall(struct IStream *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180013e50`

## callees

- `0x1800098bc`
- `0x1800098dc`
- `0x180033560`
- `0x18003795c`
- `0x180037bd8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800379de`
- `msvcrt!??3@YAXPEAX@Z` at `0x180037a75`
- `msvcrt!??3@YAXPEAX@Z` at `0x180037b0d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180037b7f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180037ba9`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800379de`
- `msvcrt!??3@YAXPEAX@Z` at `0x180037a75`
- `msvcrt!??3@YAXPEAX@Z` at `0x180037b0d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180037b7f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180037ba9`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180037a47`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180037b3a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180037a47`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180037b3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037afe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037b70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037afe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037b70`

## string_xrefs

- `0x1800379f4`: `onecoreuap\admin\prov\multivariant\common\src\provxmlhelper.cpp`
- `0x180037a5c`: `onecoreuap\admin\prov\multivariant\common\src\provxmlhelper.cpp`
- `0x180037aa5`: `onecoreuap\admin\prov\multivariant\common\src\provxmlhelper.cpp`
- `0x180037adf`: `onecoreuap\admin\prov\multivariant\common\src\provxmlhelper.cpp`
- `0x180037b56`: `onecoreuap\admin\prov\multivariant\common\src\provxmlhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MvLoadXmlFile(struct IStream *a1, unsigned __int16 **a2)
{
  __int64 v2; // rcx
  const char *v3; // r9
  CHAR *v4; // rsi
  __int64 v5; // r14
  unsigned int v6; // r14d
  const CHAR *v8; // r12
  unsigned int v9; // eax
  const char *v10; // r9
  __int64 cchWideChar; // r13
  unsigned int LastError; // ebx
  int v13; // eax
  unsigned int v14; // r15d
  unsigned __int16 *v15; // rbx
  int lpWideCharStr; // [rsp+20h] [rbp-68h]
  int lpWideCharStra; // [rsp+20h] [rbp-68h]
  __int128 v18; // [rsp+30h] [rbp-58h] BYREF
  __int64 v19; // [rsp+40h] [rbp-48h]
  void *v20; // [rsp+48h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  LPVOID pv; // [rsp+A0h] [rbp+18h] BYREF

  try
  {
    v18 = 0;
    v19 = 0;
    pv = 0;
    v2 = ReadIStreamToEnd(&v20, a1);
    if ( &v18 == (__int128 *)v2 )
    {
      LODWORD(v5) = DWORD2(v18);
      v4 = (CHAR *)v18;
    }
    else
    {
      v4 = *(CHAR **)v2;
      *(_QWORD *)&v18 = *(_QWORD *)v2;
      v5 = *(_QWORD *)(v2 + 8);
      *((_QWORD *)&v18 + 1) = v5;
      v19 = *(_QWORD *)(v2 + 16);
      *(_QWORD *)v2 = 0;
      *(_QWORD *)(v2 + 8) = 0;
      *(_QWORD *)(v2 + 16) = 0;
    }
    if ( v20 )
      operator delete(v20);
  }
  catch ( ... )
  {
    LODWORD(pv) = wil::details::in1diag3::Return_CaughtException(
                    retaddr,
                    (void *)0x57,
                    (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\provxmlhelper.cpp",
                    v3);
    if ( (_QWORD)v18 )
      operator delete((void *)v18);
    return (unsigned int)pv;
  }
  v6 = v5 - (_DWORD)v4;
  if ( !v4 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x5D,
             (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\provxmlhelper.cpp",
             v3);
  v8 = v4;
  if ( v6 > 3 && *(_WORD *)v4 == 0xBBEF && v4[2] == -65 )
  {
    v8 = v4 + 3;
    v6 -= 3;
  }
  v9 = MultiByteToWideChar(0xFDE9u, 0, v8, v6, 0, 0);
  cchWideChar = v9;
  if ( !v9 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x72,
                  (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\provxmlhelper.cpp",
                  v10);
LABEL_15:
    operator delete(v4);
    return LastError;
  }
  if ( 2 * (unsigned __int64)(v9 + 1) > 0xFFFFFFFF )
  {
    LastError = -2147024362;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\provxmlhelper.cpp",
      (const char *)0x80070216LL,
      lpWideCharStr);
    goto LABEL_15;
  }
  pv = 0;
  v13 = CoAllocStringLen((const unsigned __int16 *)0xFFFFFFFFLL, v9 + 1, (unsigned __int16 **)&pv);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\provxmlhelper.cpp",
      (const char *)(unsigned int)v13,
      lpWideCharStr);
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_21;
  }
  v15 = (unsigned __int16 *)pv;
  if ( (_DWORD)cchWideChar == MultiByteToWideChar(0xFDE9u, 0, v8, v6, (LPWSTR)pv, cchWideChar) )
  {
    v15[cchWideChar] = 0;
    *a2 = v15;
LABEL_21:
    operator delete(v4);
    return v14;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x86,
    (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\provxmlhelper.cpp",
    (const char *)0x8000FFFFLL,
    lpWideCharStra);
  if ( v15 )
    CoTaskMemFree(v15);
  operator delete(v4);
  return 2147549183LL;
}

```

## disassembly

```asm
0x18003795c  mov     rax, rsp
0x18003795f  mov     [rax+8], rbx
0x180037963  mov     [rax+20h], rsi
0x180037967  mov     [rax+10h], rdx
0x18003796b  push    rdi
0x18003796c  push    r12
0x18003796e  push    r13
0x180037970  push    r14
0x180037972  push    r15
0x180037974  sub     rsp, 60h
0x180037978  xorps   xmm0, xmm0
0x18003797b  movdqu  xmmword ptr [rax-58h], xmm0
0x180037980  xor     edi, edi
0x180037982  mov     [rax-48h], rdi
0x180037986  mov     [rax+18h], rdi
0x18003798a  mov     rdx, rcx
0x18003798d  lea     rcx, [rax-40h]
0x180037991  call    ?ReadIStreamToEnd@@YA?AV?$vector@EV?$allocator@E@std@@@std@@PEAUIStream@@@Z; ReadIStreamToEnd(IStream *)
0x180037996  mov     rcx, rax
0x180037999  lea     rax, [rsp+88h+var_58]
0x18003799e  cmp     rax, rcx
0x1800379a1  jz      short loc_1800379CA
0x1800379a3  mov     rsi, [rcx]
0x1800379a6  mov     [rsp+88h+var_58], rsi
0x1800379ab  mov     r14, [rcx+8]
0x1800379af  mov     [rsp+88h+var_50], r14
0x1800379b4  mov     rax, [rcx+10h]
0x1800379b8  mov     [rsp+88h+var_48], rax
0x1800379bd  mov     [rcx], rdi
0x1800379c0  mov     [rcx+8], rdi
0x1800379c4  mov     [rcx+10h], rdi
0x1800379c8  jmp     short loc_1800379D4
0x1800379ca  mov     r14, [rsp+88h+var_50]
0x1800379cf  mov     rsi, [rsp+88h+var_58]
0x1800379d4  mov     rcx, [rsp+88h+var_40]
0x1800379d9  test    rcx, rcx
0x1800379dc  jz      short loc_1800379E4
0x1800379de  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800379e4  sub     r14d, esi
0x1800379e7  test    rsi, rsi
0x1800379ea  jnz     short loc_180037A09
0x1800379ec  mov     rcx, [rsp+88h]; this
0x1800379f4  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800379fb  lea     edx, [rsi+5Dh]; void *
0x1800379fe  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180037a03  nop
0x180037a04  jmp     loc_180037BB6
0x180037a09  mov     r12, rsi
0x180037a0c  cmp     r14d, 3
0x180037a10  jbe     short loc_180037A31
0x180037a12  movzx   eax, cs:word_18004C970
0x180037a19  cmp     ax, [rsi]
0x180037a1c  jnz     short loc_180037A31
0x180037a1e  mov     al, cs:byte_18004C972
0x180037a24  cmp     al, [rsi+2]
0x180037a27  jnz     short loc_180037A31
0x180037a29  lea     r12, [rsi+3]
0x180037a2d  add     r14d, 0FFFFFFFDh
0x180037a31  mov     [rsp+88h+cchWideChar], edi; cchWideChar
0x180037a35  mov     [rsp+88h+lpWideCharStr], rdi; int
0x180037a3a  mov     r9d, r14d; cbMultiByte
0x180037a3d  mov     r8, r12; lpMultiByteStr
0x180037a40  xor     edx, edx; dwFlags
0x180037a42  mov     ecx, 0FDE9h; CodePage
0x180037a47  call    cs:__imp_MultiByteToWideChar
0x180037a4d  mov     r13d, eax
0x180037a50  test    eax, eax
0x180037a52  jnz     short loc_180037A82
0x180037a54  mov     rcx, [rsp+88h]; this
0x180037a5c  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180037a63  lea     edx, [rax+72h]; void *
0x180037a66  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180037a6b  mov     ebx, eax
0x180037a6d  test    rsi, rsi
0x180037a70  jz      short loc_180037A7B
0x180037a72  mov     rcx, rsi
0x180037a75  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180037a7b  mov     eax, ebx
0x180037a7d  jmp     loc_180037BB6
0x180037a82  lea     eax, [r13+1]
0x180037a86  mov     edx, eax; unsigned __int64
0x180037a88  add     rax, rax
0x180037a8b  mov     ecx, 0FFFFFFFFh; unsigned __int16 *
0x180037a90  cmp     rax, rcx
0x180037a93  jbe     short loc_180037AB8
0x180037a95  mov     rcx, [rsp+88h]; this
0x180037a9d  mov     ebx, 80070216h
0x180037aa2  mov     r9d, ebx; char *
0x180037aa5  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180037aac  mov     edx, 76h ; 'v'; void *
0x180037ab1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037ab6  jmp     short loc_180037A6D
0x180037ab8  mov     [rsp+88h+pv], rdi
0x180037ac0  lea     r8, [rsp+88h+pv]; unsigned __int16 **
0x180037ac8  call    ?CoAllocStringLen@@YAJPEBG_KPEAPEAG@Z; CoAllocStringLen(ushort const *,unsigned __int64,ushort * *)
0x180037acd  mov     r15d, eax
0x180037ad0  test    eax, eax
0x180037ad2  jns     short loc_180037B1B
0x180037ad4  mov     rcx, [rsp+88h]; this
0x180037adc  mov     r9d, eax; char *
0x180037adf  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180037ae6  mov     edx, 79h ; 'y'; void *
0x180037aeb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037af0  nop
0x180037af1  mov     rcx, [rsp+88h+pv]; pv
0x180037af9  test    rcx, rcx
0x180037afc  jz      short loc_180037B05
0x180037afe  call    cs:__imp_CoTaskMemFree
0x180037b04  nop
0x180037b05  test    rsi, rsi
0x180037b08  jz      short loc_180037B13
0x180037b0a  mov     rcx, rsi
0x180037b0d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180037b13  mov     eax, r15d
0x180037b16  jmp     loc_180037BB6
0x180037b1b  mov     [rsp+88h+cchWideChar], r13d; cchWideChar
0x180037b20  mov     rbx, [rsp+88h+pv]
0x180037b28  mov     [rsp+88h+lpWideCharStr], rbx; int
0x180037b2d  mov     r9d, r14d; cbMultiByte
0x180037b30  mov     r8, r12; lpMultiByteStr
0x180037b33  xor     edx, edx; dwFlags
0x180037b35  mov     ecx, 0FDE9h; CodePage
0x180037b3a  call    cs:__imp_MultiByteToWideChar
0x180037b40  cmp     r13d, eax
0x180037b43  jz      short loc_180037B8A
0x180037b45  mov     rcx, [rsp+88h]; this
0x180037b4d  mov     r14d, 8000FFFFh
0x180037b53  mov     r9d, r14d; char *
0x180037b56  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180037b5d  mov     edx, 86h; void *
0x180037b62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037b67  nop
0x180037b68  test    rbx, rbx
0x180037b6b  jz      short loc_180037B77
0x180037b6d  mov     rcx, rbx; pv
0x180037b70  call    cs:__imp_CoTaskMemFree
0x180037b76  nop
0x180037b77  test    rsi, rsi
0x180037b7a  jz      short loc_180037B85
0x180037b7c  mov     rcx, rsi
0x180037b7f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180037b85  mov     eax, r14d
0x180037b88  jmp     short loc_180037BB6
0x180037b8a  mov     [rbx+r13*2], di
0x180037b8f  mov     rax, [rsp+88h+arg_8]
0x180037b97  mov     [rax], rbx
0x180037b9a  jmp     loc_180037B05
0x180037b9f  mov     rcx, [rsp+88h+var_58]
0x180037ba4  test    rcx, rcx
0x180037ba7  jz      short loc_180037BAF
0x180037ba9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180037baf  mov     eax, dword ptr [rsp+88h+pv]
0x180037bb6  lea     r11, [rsp+88h+var_28]
0x180037bbb  mov     rbx, [r11+30h]
0x180037bbf  mov     rsi, [r11+48h]
0x180037bc3  mov     rsp, r11
0x180037bc6  pop     r15
0x180037bc8  pop     r14
0x180037bca  pop     r13
0x180037bcc  pop     r12
0x180037bce  pop     rdi
0x180037bcf  retn
```
