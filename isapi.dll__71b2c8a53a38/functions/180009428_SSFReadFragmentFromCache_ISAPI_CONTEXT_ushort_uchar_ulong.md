# SSFReadFragmentFromCache(ISAPI_CONTEXT *,ushort *,uchar *,ulong *)

- ea: `0x180009428`
- end: `0x1800095fc`
- name: `?SSFReadFragmentFromCache@@YAJPEAVISAPI_CONTEXT@@PEAGPEAEPEAK@Z`
- size: `468`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *, unsigned __int16 *, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x180009428`
- `0x180013010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180009493`
- `iisutil!PuDbgPrint` at `0x1800094e8`
- `iisutil!PuDbgPrint` at `0x18000957f`
- `iisutil!PuDbgPrint` at `0x1800095e6`
- `iisutil!PuDbgPrint` at `0x180009493`
- `iisutil!PuDbgPrint` at `0x1800094e8`
- `iisutil!PuDbgPrint` at `0x18000957f`
- `iisutil!PuDbgPrint` at `0x1800095e6`

## string_xrefs

- `0x180009481`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x1800094e1`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180009561`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x1800095ba`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180009467`: `\n  HSE_REQ_READ_FRAGMENT_FROM_CACHE[%p]: Function Entry\n    Fragment Name: '%S'\n  <END>\n\n`
- `0x180009473`: `SSFReadFragmentFromCache`
- `0x1800094cf`: `SSFReadFragmentFromCache`
- `0x180009556`: `SSFReadFragmentFromCache`
- `0x1800095ae`: `SSFReadFragmentFromCache`
- `0x1800094c3`: `\n  HSE_REQ_READ_FRAGMENT_FROM_CACHE[%p]: Failed to get interface to server core\n  <END>\n\n`
- `0x1800095d0`: `\n  HSE_REQ_READ_FRAGMENT_FROM_CACHE[%p]: Parameter validation failure\n    Fragment Name: '%s'\n    Size Ptr: %p\n    Size: %d\n    Buffer Ptr: %p\n  <END>\n\n`
- `0x180009568`: `\n  HSE_REQ_READ_FRAGMENT_FROM_CACHE[%p]: Failed\n    Error: 0x%08x\n  <END>\n\n`

## pseudocode

```c
__int64 __fastcall SSFReadFragmentFromCache(
        struct ISAPI_CONTEXT *a1,
        const char *a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  __int64 v4; // r14
  int v6; // r9d
  __int64 result; // rax
  unsigned int v11; // ebx
  int v12; // eax

  v4 = *((_QWORD *)a1 + 24);
  v6 = g_dwDebugFlags;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      4081,
      "SSFReadFragmentFromCache",
      "\r\n  HSE_REQ_READ_FRAGMENT_FROM_CACHE[%p]: Function Entry\r\n    Fragment Name: '%S'\r\n  <END>\r\n\r\n",
      a1,
      (const wchar_t *)a2);
    v6 = g_dwDebugFlags;
  }
  if ( !v4 )
  {
    if ( (v6 & 3) != 0 && (v6 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        4092,
        "SSFReadFragmentFromCache",
        "\r\n  HSE_REQ_READ_FRAGMENT_FROM_CACHE[%p]: Failed to get interface to server core\r\n  <END>\r\n\r\n",
        a1);
    return 2147942487LL;
  }
  if ( !a2 || !a4 || !a3 && *a4 )
  {
    if ( (v6 & 3) != 0 && (v6 & 0x100000) != 0 )
    {
      if ( a4 )
        v12 = *a4;
      else
        v12 = 0;
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        4120,
        "SSFReadFragmentFromCache",
        "\r\n"
        "  HSE_REQ_READ_FRAGMENT_FROM_CACHE[%p]: Parameter validation failure\r\n"
        "    Fragment Name: '%s'\r\n"
        "    Size Ptr: %p\r\n"
        "    Size: %d\r\n"
        "    Buffer Ptr: %p\r\n"
        "  <END>\r\n"
        "\r\n",
        a1,
        a2,
        a4,
        v12,
        a3);
    }
    return 2147942487LL;
  }
  result = (*(__int64 (__fastcall **)(__int64, const char *, unsigned __int8 *, _QWORD, unsigned int *))(*(_QWORD *)v4 + 168LL))(
             v4,
             a2,
             a3,
             *a4,
             a4);
  v11 = result;
  if ( (int)result < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        4141,
        "SSFReadFragmentFromCache",
        "\r\n  HSE_REQ_READ_FRAGMENT_FROM_CACHE[%p]: Failed\r\n    Error: 0x%08x\r\n  <END>\r\n\r\n",
        a1,
        result);
    return v11;
  }
  return result;
}

```

## disassembly

```asm
0x180009428  push    rbx
0x18000942a  push    rbp
0x18000942b  push    rsi
0x18000942c  push    rdi
0x18000942d  push    r14
0x18000942f  sub     rsp, 50h
0x180009433  mov     r14, [rcx+0C0h]
0x18000943a  mov     rbx, r9
0x18000943d  mov     r9d, cs:g_dwDebugFlags
0x180009444  mov     rbp, r8
0x180009447  test    r9b, 3
0x18000944b  mov     rsi, rdx
0x18000944e  mov     rdi, rcx
0x180009451  setnz   r10b
0x180009455  bt      r9d, 1Ah
0x18000945a  setb    al
0x18000945d  test    al, r10b
0x180009460  jz      short loc_1800094A0
0x180009462  mov     [rsp+78h+var_48], rdx
0x180009467  lea     rax, aHseReqReadFrag_1; "\r\n  HSE_REQ_READ_FRAGMENT_FROM_CACHE["...
0x18000946e  mov     [rsp+78h+var_50], rcx
0x180009473  lea     r9, aSsfreadfragmen; "SSFReadFragmentFromCache"
0x18000947a  mov     rcx, cs:g_pDebug
0x180009481  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180009488  mov     r8d, 0FF1h
0x18000948e  mov     [rsp+78h+var_58], rax
0x180009493  call    cs:__imp_PuDbgPrint
0x180009499  mov     r9d, cs:g_dwDebugFlags
0x1800094a0  test    r14, r14
0x1800094a3  jnz     short loc_1800094F3
0x1800094a5  test    r9b, 3
0x1800094a9  setnz   cl
0x1800094ac  bt      r9d, 14h
0x1800094b1  setb    al
0x1800094b4  test    al, cl
0x1800094b6  jz      loc_1800095EC
0x1800094bc  mov     rcx, cs:g_pDebug
0x1800094c3  lea     rax, aHseReqReadFrag_3; "\r\n  HSE_REQ_READ_FRAGMENT_FROM_CACHE["...
0x1800094ca  mov     [rsp+78h+var_50], rdi
0x1800094cf  lea     r9, aSsfreadfragmen; "SSFReadFragmentFromCache"
0x1800094d6  mov     r8d, 0FFCh
0x1800094dc  mov     [rsp+78h+var_58], rax
0x1800094e1  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800094e8  call    cs:__imp_PuDbgPrint
0x1800094ee  jmp     loc_1800095EC
0x1800094f3  test    rsi, rsi
0x1800094f6  jz      loc_180009589
0x1800094fc  test    rbx, rbx
0x1800094ff  jz      loc_180009589
0x180009505  test    rbp, rbp
0x180009508  jnz     short loc_18000950E
0x18000950a  cmp     [rbx], ebp
0x18000950c  jnz     short loc_180009589
0x18000950e  mov     rax, [r14]
0x180009511  mov     r8, rbp
0x180009514  mov     r9d, [rbx]
0x180009517  mov     rdx, rsi
0x18000951a  mov     rcx, r14
0x18000951d  mov     [rsp+78h+var_58], rbx
0x180009522  mov     rax, [rax+0A8h]
0x180009529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000952e  mov     ebx, eax
0x180009530  test    eax, eax
0x180009532  jns     loc_1800095F1
0x180009538  mov     ecx, cs:g_dwDebugFlags
0x18000953e  test    cl, 3
0x180009541  setnz   dl
0x180009544  bt      ecx, 14h
0x180009548  setb    cl
0x18000954b  test    cl, dl
0x18000954d  jz      short loc_180009585
0x18000954f  mov     rcx, cs:g_pDebug
0x180009556  lea     r9, aSsfreadfragmen; "SSFReadFragmentFromCache"
0x18000955d  mov     dword ptr [rsp+78h+var_48], eax
0x180009561  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180009568  lea     rax, aHseReqReadFrag_2; "\r\n  HSE_REQ_READ_FRAGMENT_FROM_CACHE["...
0x18000956f  mov     [rsp+78h+var_50], rdi
0x180009574  mov     r8d, 102Dh
0x18000957a  mov     [rsp+78h+var_58], rax
0x18000957f  call    cs:__imp_PuDbgPrint
0x180009585  mov     eax, ebx
0x180009587  jmp     short loc_1800095F1
0x180009589  test    r9b, 3
0x18000958d  setnz   cl
0x180009590  bt      r9d, 14h
0x180009595  setb    al
0x180009598  test    al, cl
0x18000959a  jz      short loc_1800095EC
0x18000959c  test    rbx, rbx
0x18000959f  jz      short loc_1800095A5
0x1800095a1  mov     eax, [rbx]
0x1800095a3  jmp     short loc_1800095A7
0x1800095a5  xor     eax, eax
0x1800095a7  mov     rcx, cs:g_pDebug
0x1800095ae  lea     r9, aSsfreadfragmen; "SSFReadFragmentFromCache"
0x1800095b5  mov     [rsp+78h+var_30], rbp
0x1800095ba  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800095c1  mov     [rsp+78h+var_38], eax
0x1800095c5  mov     r8d, 1018h
0x1800095cb  mov     [rsp+78h+var_40], rbx
0x1800095d0  lea     rax, aHseReqReadFrag; "\r\n  HSE_REQ_READ_FRAGMENT_FROM_CACHE["...
0x1800095d7  mov     [rsp+78h+var_48], rsi
0x1800095dc  mov     [rsp+78h+var_50], rdi
0x1800095e1  mov     [rsp+78h+var_58], rax
0x1800095e6  call    cs:__imp_PuDbgPrint
0x1800095ec  mov     eax, 80070057h
0x1800095f1  add     rsp, 50h
0x1800095f5  pop     r14
0x1800095f7  pop     rdi
0x1800095f8  pop     rsi
0x1800095f9  pop     rbp
0x1800095fa  pop     rbx
0x1800095fb  retn
```
