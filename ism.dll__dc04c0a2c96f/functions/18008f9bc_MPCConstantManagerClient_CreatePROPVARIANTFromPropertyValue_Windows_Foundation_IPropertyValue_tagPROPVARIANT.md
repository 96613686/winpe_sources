# MPCConstantManagerClient::CreatePROPVARIANTFromPropertyValue(Windows::Foundation::IPropertyValue *,tagPROPVARIANT *)

- ea: `0x18008f9bc`
- end: `0x18008fbe4`
- name: `?CreatePROPVARIANTFromPropertyValue@MPCConstantManagerClient@@CAJPEAUIPropertyValue@Foundation@Windows@@PEAUtagPROPVARIANT@@@Z`
- size: `552`
- prototype: `static int(struct Windows::Foundation::IPropertyValue *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800cd090`

## callees

- `0x18008dcac`
- `0x18008f9bc`
- `0x180091b30`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008fa84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008fa84`

## string_xrefs

- `0x18008f9f8`: `onecoreuap\windows\moderncore\inputv2\inputhost\components\mpcmanager\lib\mpcconstantmanagerclient.cpp`
- `0x18008fa69`: `onecoreuap\windows\moderncore\inputv2\inputhost\components\mpcmanager\lib\mpcconstantmanagerclient.cpp`
- `0x18008faa1`: `onecoreuap\windows\moderncore\inputv2\inputhost\components\mpcmanager\lib\mpcconstantmanagerclient.cpp`
- `0x18008fad8`: `onecoreuap\windows\moderncore\inputv2\inputhost\components\mpcmanager\lib\mpcconstantmanagerclient.cpp`
- `0x18008fb2e`: `onecoreuap\windows\moderncore\inputv2\inputhost\components\mpcmanager\lib\mpcconstantmanagerclient.cpp`
- `0x18008fb6c`: `onecoreuap\windows\moderncore\inputv2\inputhost\components\mpcmanager\lib\mpcconstantmanagerclient.cpp`
- `0x18008fbb8`: `onecoreuap\windows\moderncore\inputv2\inputhost\components\mpcmanager\lib\mpcconstantmanagerclient.cpp`

## pseudocode

```c
__int64 __fastcall MPCConstantManagerClient::CreatePROPVARIANTFromPropertyValue(
        struct Windows::Foundation::IPropertyValue *a1,
        struct tagPROPVARIANT *a2)
{
  int v4; // eax
  __int64 v6; // rax
  int v7; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  int inited; // eax
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // rax
  int v13; // eax
  double v14; // xmm0_8
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rax
  int v18; // eax
  HSTRING string; // [rsp+20h] [rbp-20h] BYREF
  double v20; // [rsp+28h] [rbp-18h] BYREF
  LARGE_INTEGER v21[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  char v23; // [rsp+60h] [rbp+20h] BYREF
  int v24; // [rsp+70h] [rbp+30h] BYREF
  float v25; // [rsp+78h] [rbp+38h] BYREF

  v24 = 0;
  *(_OWORD *)&a2->vt = 0;
  a2->bstrblobVal.pData = 0;
  v4 = (*(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValue *, int *))(*(_QWORD *)a1 + 48LL))(a1, &v24);
  if ( v4 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x18A,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputhost\\components\\mpcmanager\\lib\\mpcconstantmanagerclient.cpp",
      (const char *)(unsigned int)v4,
      (int)string);
  switch ( v24 )
  {
    case 7:
      v17 = *(_QWORD *)a1;
      v21[0].QuadPart = 0;
      v18 = (*(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValue *, LARGE_INTEGER *))(v17 + 112))(
              a1,
              v21);
      if ( v18 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x190,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputhost\\components\\mpcmanager\\lib\\mpcconstantmanagerclient.cpp",
          (const char *)(unsigned int)v18,
          (int)string);
      a2->hVal = v21[0];
      a2->vt = 21;
      return 0;
    case 8:
      v15 = *(_QWORD *)a1;
      v25 = 0.0;
      v16 = (*(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValue *, float *))(v15 + 120))(a1, &v25);
      if ( v16 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x19A,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputhost\\components\\mpcmanager\\lib\\mpcconstantmanagerclient.cpp",
          (const char *)(unsigned int)v16,
          (int)string);
      v14 = v25;
      goto LABEL_22;
    case 9:
      v12 = *(_QWORD *)a1;
      v20 = 0.0;
      v13 = (*(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValue *, double *))(v12 + 128))(a1, &v20);
      if ( v13 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x19F,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputhost\\components\\mpcmanager\\lib\\mpcconstantmanagerclient.cpp",
          (const char *)(unsigned int)v13,
          (int)string);
      v14 = v20;
LABEL_22:
      a2->dblVal = v14;
      a2->vt = 5;
      return 0;
    case 11:
      v10 = *(_QWORD *)a1;
      v23 = 0;
      v11 = (*(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValue *, char *))(v10 + 144))(a1, &v23);
      if ( v11 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x195,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputhost\\components\\mpcmanager\\lib\\mpcconstantmanagerclient.cpp",
          (const char *)(unsigned int)v11,
          (int)string);
      a2->vt = 11;
      a2->iVal = -(v23 != 0);
      break;
    case 12:
      v6 = *(_QWORD *)a1;
      string = 0;
      v7 = (*(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValue *, HSTRING *))(v6 + 152))(a1, &string);
      if ( v7 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x1A4,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputhost\\components\\mpcmanager\\lib\\mpcconstantmanagerclient.cpp",
          (const char *)(unsigned int)v7,
          (int)string);
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      inited = InitPropVariantFromString(StringRawBuffer, a2);
      if ( inited < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x1A5,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputhost\\components\\mpcmanager\\lib\\mpcconstantmanagerclient.cpp",
          (const char *)(unsigned int)inited,
          (int)string);
      break;
    default:
      return 2147942487LL;
  }
  return 0;
}

```

## disassembly

```asm
0x18008f9bc  push    rbp
0x18008f9be  push    rbx
0x18008f9bf  push    rdi
0x18008f9c0  mov     rbp, rsp
0x18008f9c3  sub     rsp, 40h
0x18008f9c7  xor     eax, eax
0x18008f9c9  mov     [rbp+arg_10], 0
0x18008f9d0  xorps   xmm0, xmm0
0x18008f9d3  mov     rbx, rdx
0x18008f9d6  movups  xmmword ptr [rdx], xmm0
0x18008f9d9  mov     [rdx+10h], rax
0x18008f9dd  mov     rdi, rcx
0x18008f9e0  mov     rax, [rcx]
0x18008f9e3  lea     rdx, [rbp+arg_10]
0x18008f9e7  mov     rax, [rax+30h]
0x18008f9eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f9f0  test    eax, eax
0x18008f9f2  jns     short loc_18008FA0D
0x18008f9f4  mov     rcx, [rbp+18h]; this
0x18008f9f8  lea     r8, aOnecoreuapWind_166; "onecoreuap\\windows\\moderncore\\inputv"...
0x18008f9ff  mov     r9d, eax; char *
0x18008fa02  mov     edx, 18Ah; void *
0x18008fa07  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18008fa0d  mov     ecx, [rbp+arg_10]
0x18008fa10  sub     ecx, 7
0x18008fa13  jz      loc_18008FB95
0x18008fa19  sub     ecx, 1
0x18008fa1c  jz      loc_18008FB4A
0x18008fa22  sub     ecx, 1
0x18008fa25  jz      loc_18008FB08
0x18008fa2b  sub     ecx, 2
0x18008fa2e  jz      loc_18008FAB6
0x18008fa34  cmp     ecx, 1
0x18008fa37  jz      short loc_18008FA43
0x18008fa39  mov     eax, 80070057h
0x18008fa3e  jmp     loc_18008FBDC
0x18008fa43  mov     rax, [rdi]
0x18008fa46  lea     rdx, [rbp+string]
0x18008fa4a  mov     rcx, rdi
0x18008fa4d  mov     [rbp+string], 0
0x18008fa55  mov     rax, [rax+98h]
0x18008fa5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fa61  test    eax, eax
0x18008fa63  jns     short loc_18008FA7E
0x18008fa65  mov     rcx, [rbp+18h]; this
0x18008fa69  lea     r8, aOnecoreuapWind_166; "onecoreuap\\windows\\moderncore\\inputv"...
0x18008fa70  mov     r9d, eax; char *
0x18008fa73  mov     edx, 1A4h; void *
0x18008fa78  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18008fa7e  mov     rcx, [rbp+string]; string
0x18008fa82  xor     edx, edx; length
0x18008fa84  call    cs:__imp_WindowsGetStringRawBuffer
0x18008fa8a  mov     rcx, rax; Src
0x18008fa8d  mov     rdx, rbx; struct tagPROPVARIANT *
0x18008fa90  call    ?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; InitPropVariantFromString(ushort const *,tagPROPVARIANT *)
0x18008fa95  test    eax, eax
0x18008fa97  jns     loc_18008FBDA
0x18008fa9d  mov     rcx, [rbp+18h]; this
0x18008faa1  lea     r8, aOnecoreuapWind_166; "onecoreuap\\windows\\moderncore\\inputv"...
0x18008faa8  mov     r9d, eax; char *
0x18008faab  mov     edx, 1A5h; void *
0x18008fab0  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18008fab6  mov     rax, [rdi]
0x18008fab9  lea     rdx, [rbp+arg_0]
0x18008fabd  mov     rcx, rdi
0x18008fac0  mov     [rbp+arg_0], 0
0x18008fac4  mov     rax, [rax+90h]
0x18008facb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fad0  test    eax, eax
0x18008fad2  jns     short loc_18008FAED
0x18008fad4  mov     rcx, [rbp+18h]; this
0x18008fad8  lea     r8, aOnecoreuapWind_166; "onecoreuap\\windows\\moderncore\\inputv"...
0x18008fadf  mov     r9d, eax; char *
0x18008fae2  mov     edx, 195h; void *
0x18008fae7  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18008faed  xor     eax, eax
0x18008faef  mov     word ptr [rbx], 0Bh
0x18008faf4  cmp     [rbp+arg_0], al
0x18008faf7  setnz   al
0x18008fafa  neg     eax
0x18008fafc  sbb     ax, ax
0x18008faff  mov     [rbx+8], ax
0x18008fb03  jmp     loc_18008FBDA
0x18008fb08  mov     rax, [rdi]
0x18008fb0b  lea     rdx, [rbp+var_18]
0x18008fb0f  xorps   xmm0, xmm0
0x18008fb12  mov     rcx, rdi
0x18008fb15  movsd   [rbp+var_18], xmm0
0x18008fb1a  mov     rax, [rax+80h]
0x18008fb21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fb26  test    eax, eax
0x18008fb28  jns     short loc_18008FB43
0x18008fb2a  mov     rcx, [rbp+18h]; this
0x18008fb2e  lea     r8, aOnecoreuapWind_166; "onecoreuap\\windows\\moderncore\\inputv"...
0x18008fb35  mov     r9d, eax; char *
0x18008fb38  mov     edx, 19Fh; void *
0x18008fb3d  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18008fb43  movsd   xmm0, [rbp+var_18]
0x18008fb48  jmp     short loc_18008FB89
0x18008fb4a  mov     rax, [rdi]
0x18008fb4d  lea     rdx, [rbp+arg_18]
0x18008fb51  mov     rcx, rdi
0x18008fb54  mov     [rbp+arg_18], 0
0x18008fb5b  mov     rax, [rax+78h]
0x18008fb5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fb64  test    eax, eax
0x18008fb66  jns     short loc_18008FB81
0x18008fb68  mov     rcx, [rbp+18h]; this
0x18008fb6c  lea     r8, aOnecoreuapWind_166; "onecoreuap\\windows\\moderncore\\inputv"...
0x18008fb73  mov     r9d, eax; char *
0x18008fb76  mov     edx, 19Ah; void *
0x18008fb7b  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18008fb81  movss   xmm0, [rbp+arg_18]
0x18008fb86  cvtps2pd xmm0, xmm0
0x18008fb89  movsd   qword ptr [rbx+8], xmm0
0x18008fb8e  mov     word ptr [rbx], 5
0x18008fb93  jmp     short loc_18008FBDA
0x18008fb95  mov     rax, [rdi]
0x18008fb98  lea     rdx, [rbp+var_10]
0x18008fb9c  mov     rcx, rdi
0x18008fb9f  mov     qword ptr [rbp+var_10], 0
0x18008fba7  mov     rax, [rax+70h]
0x18008fbab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fbb0  test    eax, eax
0x18008fbb2  jns     short loc_18008FBCD
0x18008fbb4  mov     rcx, [rbp+18h]; this
0x18008fbb8  lea     r8, aOnecoreuapWind_166; "onecoreuap\\windows\\moderncore\\inputv"...
0x18008fbbf  mov     r9d, eax; char *
0x18008fbc2  mov     edx, 190h; void *
0x18008fbc7  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18008fbcd  mov     rax, qword ptr [rbp+var_10]
0x18008fbd1  mov     [rbx+8], rax
0x18008fbd5  mov     word ptr [rbx], 15h
0x18008fbda  xor     eax, eax
0x18008fbdc  add     rsp, 40h
0x18008fbe0  pop     rdi
0x18008fbe1  pop     rbx
0x18008fbe2  pop     rbp
0x18008fbe3  retn
```
