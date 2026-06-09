# SSFAddFragmentToCache(ISAPI_CONTEXT *,_HSE_VECTOR_ELEMENT *,ushort *)

- ea: `0x180006118`
- end: `0x18000641f`
- name: `?SSFAddFragmentToCache@@YAJPEAVISAPI_CONTEXT@@PEAU_HSE_VECTOR_ELEMENT@@PEAG@Z`
- size: `775`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *, struct _HSE_VECTOR_ELEMENT *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x180006118`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800062be`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800062be`
- `iisutil!PuDbgPrint` at `0x180006192`
- `iisutil!PuDbgPrint` at `0x18000622b`
- `iisutil!PuDbgPrint` at `0x180006339`
- `iisutil!PuDbgPrint` at `0x1800063b0`
- `iisutil!PuDbgPrint` at `0x1800063fb`
- `iisutil!PuDbgPrint` at `0x180006192`
- `iisutil!PuDbgPrint` at `0x18000622b`
- `iisutil!PuDbgPrint` at `0x180006339`
- `iisutil!PuDbgPrint` at `0x1800063b0`
- `iisutil!PuDbgPrint` at `0x1800063fb`

## string_xrefs

- `0x180006147`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180006170`: `\n  HSE_REQ_ADD_FRAGMENT_TO_CACHE[%p]: Function Entry\n    Fragment Name: '%S'\n  <END>\n\n`
- `0x180006139`: `SSFAddFragmentToCache`
- `0x1800061bb`: `\n  HSE_REQ_ADD_FRAGMENT_TO_CACHE[%p]: Failed to get interface to server core\n  <END>\n\n`
- `0x1800063d4`: `\n  HSE_REQ_ADD_FRAGMENT_TO_CACHE[%p]: Parameter validation failure\n    Vector Element Ptr: %p\n    Fragment Name: '%s'\n  <END>\n\n`
- `0x180006207`: `\n  HSE_REQ_ADD_FRAGMENT_TO_CACHE[%p]: Parameter validation failure\n    Vector Element Context: NULL\n  <END>\n\n`
- `0x180006315`: `\n  HSE_REQ_ADD_FRAGMENT_TO_CACHE[%p]: Parameter validation failure\n    Memory buffer size element invalid\n    Size: %d\n  <END>\n\n`
- `0x18000629a`: `\n  HSE_REQ_ADD_FRAGMENT_TO_CACHE[%p]: Parameter validation failure\n    Element file handle invalid\n    File Handle: %p\n  <END>\n\n`
- `0x180006262`: `\n  HSE_REQ_ADD_FRAGMENT_TO_CACHE[%p]: Parameter validation failure\n    Unknown element type: %d\n    Fragment Name: '%s'\n  <END>\n\n`
- `0x18000639c`: `\n  HSE_REQ_ADD_FRAGMENT_TO_CACHE[%p]: Failed\n    Error: 0x%08x\n  <END>\n\n`

## pseudocode

```c
__int64 __fastcall SSFAddFragmentToCache(struct ISAPI_CONTEXT *a1, struct _HSE_VECTOR_ELEMENT *a2, const char *a3)
{
  int v3; // r10d
  __int64 v4; // r14
  PVOID pvContext; // rcx
  ULONGLONG cbSize; // rax
  __int64 result; // rax
  unsigned int v11; // ebx
  __int64 v12; // [rsp+30h] [rbp-30h]
  __int128 v13; // [rsp+40h] [rbp-20h] BYREF
  __int128 v14; // [rsp+50h] [rbp-10h]
  union _LARGE_INTEGER FileSize; // [rsp+90h] [rbp+30h] BYREF

  v3 = g_dwDebugFlags;
  v4 = *((_QWORD *)a1 + 24);
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      3886,
      "SSFAddFragmentToCache",
      "\r\n  HSE_REQ_ADD_FRAGMENT_TO_CACHE[%p]: Function Entry\r\n    Fragment Name: '%S'\r\n  <END>\r\n\r\n",
      a1,
      (const wchar_t *)a3);
    v3 = g_dwDebugFlags;
  }
  if ( !v4 )
  {
    if ( (v3 & 3) != 0 && (v3 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        3897,
        "SSFAddFragmentToCache",
        "\r\n  HSE_REQ_ADD_FRAGMENT_TO_CACHE[%p]: Failed to get interface to server core\r\n  <END>\r\n\r\n",
        a1);
    return 2147942487LL;
  }
  if ( !a2 || !a3 )
  {
    if ( (v3 & 3) != 0 && (v3 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        3920,
        "SSFAddFragmentToCache",
        "\r\n"
        "  HSE_REQ_ADD_FRAGMENT_TO_CACHE[%p]: Parameter validation failure\r\n"
        "    Vector Element Ptr: %p\r\n"
        "    Fragment Name: '%s'\r\n"
        "  <END>\r\n"
        "\r\n",
        a1,
        a2,
        a3);
    return 2147942487LL;
  }
  pvContext = a2->pvContext;
  v13 = 0;
  v14 = 0;
  if ( !pvContext )
  {
    if ( (v3 & 3) != 0 && (v3 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        3938,
        "SSFAddFragmentToCache",
        "\r\n"
        "  HSE_REQ_ADD_FRAGMENT_TO_CACHE[%p]: Parameter validation failure\r\n"
        "    Vector Element Context: NULL\r\n"
        "  <END>\r\n"
        "\r\n",
        a1);
    return 2147942487LL;
  }
  if ( a2->ElementType )
  {
    if ( a2->ElementType != 1 )
    {
      if ( (v3 & 3) != 0 && (v3 & 0x100000) != 0 )
      {
        LODWORD(v12) = a2->ElementType;
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
          4015,
          "SSFAddFragmentToCache",
          "\r\n"
          "  HSE_REQ_ADD_FRAGMENT_TO_CACHE[%p]: Parameter validation failure\r\n"
          "    Unknown element type: %d\r\n"
          "    Fragment Name: '%s'\r\n"
          "  <END>\r\n"
          "\r\n",
          a1,
          v12);
      }
      return 2147942487LL;
    }
    if ( pvContext == (PVOID)-1LL )
    {
      if ( (v3 & 3) != 0 && (v3 & 0x100000) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
          3981,
          "SSFAddFragmentToCache",
          "\r\n"
          "  HSE_REQ_ADD_FRAGMENT_TO_CACHE[%p]: Parameter validation failure\r\n"
          "    Element file handle invalid\r\n"
          "    File Handle: %p\r\n"
          "  <END>\r\n"
          "\r\n",
          a1,
          -1);
      return 2147942487LL;
    }
    cbSize = a2->cbSize;
    FileSize.QuadPart = cbSize;
    if ( !cbSize )
    {
      FileSize.QuadPart = 0;
      GetFileSizeEx(pvContext, &FileSize);
      LODWORD(cbSize) = FileSize.LowPart;
      a2->cbSize = FileSize.QuadPart;
    }
    *((_QWORD *)&v14 + 1) = a2->pvContext;
    *((_QWORD *)&v13 + 1) = a2->cbOffset;
    LODWORD(v13) = 1;
    DWORD1(v14) = FileSize.HighPart;
  }
  else
  {
    if ( a2->cbSize > 0xFFFFFFFF )
    {
      if ( (v3 & 3) != 0 && (v3 & 0x100000) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
          3958,
          "SSFAddFragmentToCache",
          "\r\n"
          "  HSE_REQ_ADD_FRAGMENT_TO_CACHE[%p]: Parameter validation failure\r\n"
          "    Memory buffer size element invalid\r\n"
          "    Size: %d\r\n"
          "  <END>\r\n"
          "\r\n",
          a1,
          a2->cbSize);
      return 2147942487LL;
    }
    LODWORD(cbSize) = a2->cbSize;
    *((_QWORD *)&v13 + 1) = pvContext;
  }
  LODWORD(v14) = cbSize;
  result = (*(__int64 (__fastcall **)(__int64, __int128 *, const char *))(*(_QWORD *)v4 + 160LL))(v4, &v13, a3);
  v11 = result;
  if ( (int)result < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        4034,
        "SSFAddFragmentToCache",
        "\r\n  HSE_REQ_ADD_FRAGMENT_TO_CACHE[%p]: Failed\r\n    Error: 0x%08x\r\n  <END>\r\n\r\n",
        a1,
        result);
    return v11;
  }
  return result;
}

```

## disassembly

```asm
0x180006118  mov     r11, rsp
0x18000611b  mov     [r11+10h], rbx
0x18000611f  mov     [r11+18h], rsi
0x180006123  push    rbp
0x180006124  push    rdi
0x180006125  push    r12
0x180006127  push    r14
0x180006129  push    r15
0x18000612b  mov     rbp, rsp
0x18000612e  sub     rsp, 60h
0x180006132  mov     r10d, cs:g_dwDebugFlags
0x180006139  lea     r15, aSsfaddfragment; "SSFAddFragmentToCache"
0x180006140  mov     r14, [rcx+0C0h]
0x180006147  lea     r12, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000614e  test    r10b, 3
0x180006152  mov     rsi, r8
0x180006155  mov     rbx, rdx
0x180006158  mov     rdi, rcx
0x18000615b  setnz   r9b
0x18000615f  bt      r10d, 1Ah
0x180006164  setb    al
0x180006167  test    al, r9b
0x18000616a  jz      short loc_18000619F
0x18000616c  mov     [r11-58h], r8
0x180006170  lea     rax, aHseReqAddFragm_7; "\r\n  HSE_REQ_ADD_FRAGMENT_TO_CACHE[%p]"...
0x180006177  mov     [r11-60h], rcx
0x18000617b  mov     r9, r15
0x18000617e  mov     rcx, cs:g_pDebug
0x180006185  mov     r8d, 0F2Eh
0x18000618b  mov     rdx, r12
0x18000618e  mov     [r11-68h], rax
0x180006192  call    cs:__imp_PuDbgPrint
0x180006198  mov     r10d, cs:g_dwDebugFlags
0x18000619f  test    r14, r14
0x1800061a2  jnz     short loc_1800061CA
0x1800061a4  test    r10b, 3
0x1800061a8  setnz   cl
0x1800061ab  bt      r10d, 14h
0x1800061b0  setb    al
0x1800061b3  test    al, cl
0x1800061b5  jz      loc_180006401
0x1800061bb  lea     rax, aHseReqAddFragm_4; "\r\n  HSE_REQ_ADD_FRAGMENT_TO_CACHE[%p]"...
0x1800061c2  mov     r8d, 0F39h
0x1800061c8  jmp     short loc_180006214
0x1800061ca  test    rbx, rbx
0x1800061cd  jz      loc_1800063BA
0x1800061d3  test    rsi, rsi
0x1800061d6  jz      loc_1800063BA
0x1800061dc  mov     rcx, [rbx+8]; hFile
0x1800061e0  xorps   xmm0, xmm0
0x1800061e3  movups  [rbp+var_20], xmm0
0x1800061e7  movups  [rbp+var_10], xmm0
0x1800061eb  test    rcx, rcx
0x1800061ee  jnz     short loc_180006236
0x1800061f0  test    r10b, 3
0x1800061f4  setnz   cl
0x1800061f7  bt      r10d, 14h
0x1800061fc  setb    al
0x1800061ff  test    al, cl
0x180006201  jz      loc_180006401
0x180006207  lea     rax, aHseReqAddFragm_3; "\r\n  HSE_REQ_ADD_FRAGMENT_TO_CACHE[%p]"...
0x18000620e  mov     r8d, 0F62h
0x180006214  mov     rcx, cs:g_pDebug
0x18000621b  mov     r9, r15
0x18000621e  mov     [rsp+60h+var_38], rdi
0x180006223  mov     rdx, r12
0x180006226  mov     [rsp+60h+var_40], rax
0x18000622b  call    cs:__imp_PuDbgPrint
0x180006231  jmp     loc_180006401
0x180006236  mov     edx, [rbx]
0x180006238  mov     eax, edx
0x18000623a  test    edx, edx
0x18000623c  jz      loc_1800062EB
0x180006242  cmp     eax, 1
0x180006245  jz      short loc_180006274
0x180006247  test    r10b, 3
0x18000624b  setnz   cl
0x18000624e  bt      r10d, 14h
0x180006253  setb    al
0x180006256  test    al, cl
0x180006258  jz      loc_180006401
0x18000625e  mov     dword ptr [rsp+60h+var_30], edx
0x180006262  lea     rax, aHseReqAddFragm_5; "\r\n  HSE_REQ_ADD_FRAGMENT_TO_CACHE[%p]"...
0x180006269  mov     r8d, 0FAFh
0x18000626f  jmp     loc_180006322
0x180006274  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180006278  jnz     short loc_1800062A9
0x18000627a  test    r10b, 3
0x18000627e  setnz   cl
0x180006281  bt      r10d, 14h
0x180006286  setb    al
0x180006289  test    al, cl
0x18000628b  jz      loc_180006401
0x180006291  mov     [rsp+60h+var_30], 0FFFFFFFFFFFFFFFFh
0x18000629a  lea     rax, aHseReqAddFragm_0; "\r\n  HSE_REQ_ADD_FRAGMENT_TO_CACHE[%p]"...
0x1800062a1  mov     r8d, 0F8Dh
0x1800062a7  jmp     short loc_180006322
0x1800062a9  mov     rax, [rbx+18h]
0x1800062ad  mov     qword ptr [rbp+FileSize], rax
0x1800062b1  test    rax, rax
0x1800062b4  jnz     short loc_1800062CC
0x1800062b6  lea     rdx, [rbp+FileSize]; lpFileSize
0x1800062ba  mov     qword ptr [rbp+FileSize], rax
0x1800062be  call    cs:__imp_GetFileSizeEx
0x1800062c4  mov     rax, qword ptr [rbp+FileSize]
0x1800062c8  mov     [rbx+18h], rax
0x1800062cc  mov     rdx, [rbx+8]
0x1800062d0  mov     ecx, dword ptr [rbp+FileSize+4]
0x1800062d3  mov     qword ptr [rbp+var_10+8], rdx
0x1800062d7  mov     rdx, [rbx+10h]
0x1800062db  mov     qword ptr [rbp+var_20+8], rdx
0x1800062df  mov     dword ptr [rbp+var_20], 1
0x1800062e6  mov     dword ptr [rbp+var_10+4], ecx
0x1800062e9  jmp     short loc_18000634B
0x1800062eb  mov     rdx, [rbx+18h]
0x1800062ef  mov     eax, 0FFFFFFFFh
0x1800062f4  cmp     rdx, rax
0x1800062f7  jbe     short loc_180006344
0x1800062f9  test    r10b, 3
0x1800062fd  setnz   cl
0x180006300  bt      r10d, 14h
0x180006305  setb    al
0x180006308  test    al, cl
0x18000630a  jz      loc_180006401
0x180006310  mov     [rsp+60h+var_30], rdx
0x180006315  lea     rax, aHseReqAddFragm_2; "\r\n  HSE_REQ_ADD_FRAGMENT_TO_CACHE[%p]"...
0x18000631c  mov     r8d, 0F76h
0x180006322  mov     rcx, cs:g_pDebug
0x180006329  mov     r9, r15
0x18000632c  mov     [rsp+60h+var_38], rdi
0x180006331  mov     rdx, r12
0x180006334  mov     [rsp+60h+var_40], rax
0x180006339  call    cs:__imp_PuDbgPrint
0x18000633f  jmp     loc_180006401
0x180006344  mov     eax, [rbx+18h]
0x180006347  mov     qword ptr [rbp+var_20+8], rcx
0x18000634b  mov     dword ptr [rbp+var_10], eax
0x18000634e  lea     rdx, [rbp+var_20]
0x180006352  mov     rax, [r14]
0x180006355  mov     r8, rsi
0x180006358  mov     rcx, r14
0x18000635b  mov     rax, [rax+0A0h]
0x180006362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006367  mov     ebx, eax
0x180006369  test    eax, eax
0x18000636b  jns     loc_180006406
0x180006371  mov     ecx, cs:g_dwDebugFlags
0x180006377  test    cl, 3
0x18000637a  setnz   dl
0x18000637d  bt      ecx, 14h
0x180006381  setb    cl
0x180006384  test    cl, dl
0x180006386  jz      short loc_1800063B6
0x180006388  mov     rcx, cs:g_pDebug
0x18000638f  mov     r9, r15
0x180006392  mov     dword ptr [rsp+60h+var_30], eax
0x180006396  mov     r8d, 0FC2h
0x18000639c  lea     rax, aHseReqAddFragm_1; "\r\n  HSE_REQ_ADD_FRAGMENT_TO_CACHE[%p]"...
0x1800063a3  mov     [rsp+60h+var_38], rdi
0x1800063a8  mov     rdx, r12
0x1800063ab  mov     [rsp+60h+var_40], rax
0x1800063b0  call    cs:__imp_PuDbgPrint
0x1800063b6  mov     eax, ebx
0x1800063b8  jmp     short loc_180006406
0x1800063ba  test    r10b, 3
0x1800063be  setnz   cl
0x1800063c1  bt      r10d, 14h
0x1800063c6  setb    al
0x1800063c9  test    al, cl
0x1800063cb  jz      short loc_180006401
0x1800063cd  mov     rcx, cs:g_pDebug
0x1800063d4  lea     rax, aHseReqAddFragm_6; "\r\n  HSE_REQ_ADD_FRAGMENT_TO_CACHE[%p]"...
0x1800063db  mov     [rsp+60h+var_28], rsi
0x1800063e0  mov     r9, r15
0x1800063e3  mov     [rsp+60h+var_30], rbx
0x1800063e8  mov     r8d, 0F50h
0x1800063ee  mov     [rsp+60h+var_38], rdi
0x1800063f3  mov     rdx, r12
0x1800063f6  mov     [rsp+60h+var_40], rax
0x1800063fb  call    cs:__imp_PuDbgPrint
0x180006401  mov     eax, 80070057h
0x180006406  lea     r11, [rsp+60h+var_s0]
0x18000640b  mov     rbx, [r11+38h]
0x18000640f  mov     rsi, [r11+40h]
0x180006413  mov     rsp, r11
0x180006416  pop     r15
0x180006418  pop     r14
0x18000641a  pop     r12
0x18000641c  pop     rdi
0x18000641d  pop     rbp
0x18000641e  retn
```
