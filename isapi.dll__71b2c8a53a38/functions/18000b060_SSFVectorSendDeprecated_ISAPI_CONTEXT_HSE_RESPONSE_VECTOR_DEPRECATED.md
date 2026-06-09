# SSFVectorSendDeprecated(ISAPI_CONTEXT *,_HSE_RESPONSE_VECTOR_DEPRECATED *)

- ea: `0x18000b060`
- end: `0x18000b2e1`
- name: `?SSFVectorSendDeprecated@@YAJPEAVISAPI_CONTEXT@@PEAU_HSE_RESPONSE_VECTOR_DEPRECATED@@@Z`
- size: `641`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *this, struct _HSE_RESPONSE_VECTOR_DEPRECATED *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x18000a820`
- `0x18000b060`
- `0x180012482`
- `0x1800124c0`

## import_xrefs

- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000b1ac`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000b1ac`
- `iisutil!PuDbgPrint` at `0x18000b10e`
- `iisutil!PuDbgPrint` at `0x18000b15c`
- `iisutil!PuDbgPrint` at `0x18000b2aa`
- `iisutil!PuDbgPrint` at `0x18000b10e`
- `iisutil!PuDbgPrint` at `0x18000b15c`
- `iisutil!PuDbgPrint` at `0x18000b2aa`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000b2b5`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000b2b5`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000b193`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000b193`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18000b0c5`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18000b0c5`

## string_xrefs

- `0x18000b107`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x18000b155`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x18000b28c`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`

## pseudocode

```c
__int64 __fastcall SSFVectorSendDeprecated(struct ISAPI_CONTEXT *this, struct _HSE_RESPONSE_VECTOR_DEPRECATED *a2)
{
  int v4; // edx
  unsigned int v5; // ebx
  DWORD v6; // edx
  CHAR *v7; // rax
  struct _HSE_VECTOR_ELEMENT *Ptr; // rax
  unsigned int v9; // r8d
  LPHSE_VECTOR_ELEMENT lpElementArray; // rcx
  unsigned __int64 v11; // rdx
  int v12; // eax
  _HSE_RESPONSE_VECTOR v14; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v15[56]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int8 v16[512]; // [rsp+A0h] [rbp-60h] BYREF

  memset(&v14, 0, sizeof(v14));
  memset_0(v16, 0, sizeof(v16));
  BUFFER::BUFFER((BUFFER *)v15, v16, 0x200u);
  v4 = g_dwDebugFlags;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      2764,
      "SSFVectorSendDeprecated",
      "\r\n  HSE_REQ_VECTOR_SEND_DEPRECATED[%p]: Function Entry\r\n  <END>\r\n\r\n",
      this);
    v4 = g_dwDebugFlags;
  }
  if ( a2 )
  {
    v6 = *((_DWORD *)a2 + 6);
    v14.dwFlags = *(_DWORD *)a2;
    v14.pszStatus = (LPSTR)*((_QWORD *)a2 + 1);
    v7 = (CHAR *)*((_QWORD *)a2 + 2);
    v14.nElementCount = v6;
    v14.pszHeaders = v7;
    if ( BUFFER::Resize((BUFFER *)v15, 32 * v6) )
    {
      Ptr = (struct _HSE_VECTOR_ELEMENT *)BUFFER::QueryPtr((BUFFER *)v15);
      v9 = 0;
      v14.lpElementArray = Ptr;
      lpElementArray = Ptr;
      if ( *((_DWORD *)a2 + 6) )
      {
        while ( 1 )
        {
          v11 = v9;
          if ( *(_QWORD *)(v11 * 32 + *((_QWORD *)a2 + 4)) )
          {
            lpElementArray[v11].ElementType = 0;
            v14.lpElementArray[v11].pvContext = *(PVOID *)(v11 * 32 + *((_QWORD *)a2 + 4));
          }
          else
          {
            lpElementArray[v11].ElementType = 1;
            v14.lpElementArray[v11].pvContext = *(PVOID *)(v11 * 32 + *((_QWORD *)a2 + 4) + 8);
            v14.lpElementArray[v11].cbOffset = *(_QWORD *)(v11 * 32 + *((_QWORD *)a2 + 4) + 16);
          }
          ++v9;
          v14.lpElementArray[v11].cbSize = *(_QWORD *)(v11 * 32 + *((_QWORD *)a2 + 4) + 24);
          if ( v9 >= *((_DWORD *)a2 + 6) )
            break;
          lpElementArray = v14.lpElementArray;
        }
      }
      v12 = SSFVectorSend(this, &v14);
      v5 = v12;
      if ( v12 < 0 && (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
          2822,
          "SSFVectorSendDeprecated",
          "\r\n  HSE_REQ_VECTOR_SEND_DEPRECATED[%p]: Failed\r\n    Error: 0x%08x\r\n  <END>\r\n\r\n",
          this,
          v12);
    }
    else
    {
      v5 = -2147024888;
    }
  }
  else
  {
    if ( (v4 & 3) != 0 && (v4 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        2776,
        "SSFVectorSendDeprecated",
        "\r\n"
        "  HSE_REQ_VECTOR_SEND_DEPRECATED[%p]: Parameter validation failure\r\n"
        "    Response Vector Ptr: NULL\r\n"
        "  <END>\r\n"
        "\r\n",
        this);
    v5 = -2147024809;
  }
  BUFFER::~BUFFER((BUFFER *)v15);
  return v5;
}

```

## disassembly

```asm
0x18000b060  mov     [rsp-8+arg_10], rbx
0x18000b065  mov     [rsp-8+arg_18], rdi
0x18000b06a  push    rbp
0x18000b06b  lea     rbp, [rsp-1B0h]
0x18000b073  sub     rsp, 2B0h
0x18000b07a  mov     rax, cs:__security_cookie
0x18000b081  xor     rax, rsp
0x18000b084  mov     [rbp+1B0h+var_10], rax
0x18000b08b  xorps   xmm0, xmm0
0x18000b08e  mov     rbx, rdx
0x18000b091  mov     rdi, rcx
0x18000b094  xor     eax, eax
0x18000b096  xor     edx, edx; Val
0x18000b098  mov     [rsp+2B0h+var_270.lpElementArray], rax
0x18000b09d  lea     rcx, [rbp+1B0h+var_210]; void *
0x18000b0a1  mov     r8d, 200h; Size
0x18000b0a7  movups  xmmword ptr [rsp+2B0h+var_270.dwFlags], xmm0
0x18000b0ac  movups  xmmword ptr [rsp+2B0h+var_270.pszHeaders], xmm0
0x18000b0b1  call    memset_0
0x18000b0b6  mov     r8d, 200h
0x18000b0bc  lea     rdx, [rbp+1B0h+var_210]
0x18000b0c0  lea     rcx, [rsp+2B0h+var_248]
0x18000b0c5  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x18000b0cb  mov     edx, cs:g_dwDebugFlags
0x18000b0d1  test    dl, 3
0x18000b0d4  setnz   cl
0x18000b0d7  bt      edx, 1Ah
0x18000b0db  setb    al
0x18000b0de  test    al, cl
0x18000b0e0  jz      short loc_18000B11A
0x18000b0e2  mov     rcx, cs:g_pDebug
0x18000b0e9  lea     rax, aHseReqVectorSe_7; "\r\n  HSE_REQ_VECTOR_SEND_DEPRECATED[%p"...
0x18000b0f0  mov     [rsp+2B0h+var_288], rdi
0x18000b0f5  lea     r9, aSsfvectorsendd; "SSFVectorSendDeprecated"
0x18000b0fc  mov     r8d, 0ACCh
0x18000b102  mov     [rsp+2B0h+var_290], rax
0x18000b107  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000b10e  call    cs:__imp_PuDbgPrint
0x18000b114  mov     edx, cs:g_dwDebugFlags
0x18000b11a  test    rbx, rbx
0x18000b11d  jnz     short loc_18000B16C
0x18000b11f  test    dl, 3
0x18000b122  setnz   cl
0x18000b125  bt      edx, 14h
0x18000b129  setb    al
0x18000b12c  test    al, cl
0x18000b12e  jz      short loc_18000B162
0x18000b130  mov     rcx, cs:g_pDebug
0x18000b137  lea     rax, aHseReqVectorSe; "\r\n  HSE_REQ_VECTOR_SEND_DEPRECATED[%p"...
0x18000b13e  mov     [rsp+2B0h+var_288], rdi
0x18000b143  lea     r9, aSsfvectorsendd; "SSFVectorSendDeprecated"
0x18000b14a  mov     r8d, 0AD8h
0x18000b150  mov     [rsp+2B0h+var_290], rax
0x18000b155  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000b15c  call    cs:__imp_PuDbgPrint
0x18000b162  mov     ebx, 80070057h
0x18000b167  jmp     loc_18000B2B0
0x18000b16c  mov     eax, [rbx]
0x18000b16e  lea     rcx, [rsp+2B0h+var_248]
0x18000b173  mov     edx, [rbx+18h]
0x18000b176  mov     [rsp+2B0h+var_270.dwFlags], eax
0x18000b17a  mov     rax, [rbx+8]
0x18000b17e  mov     [rsp+2B0h+var_270.pszStatus], rax
0x18000b183  mov     rax, [rbx+10h]
0x18000b187  mov     [rsp+2B0h+var_270.nElementCount], edx
0x18000b18b  shl     edx, 5
0x18000b18e  mov     [rsp+2B0h+var_270.pszHeaders], rax
0x18000b193  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000b199  test    al, al
0x18000b19b  jnz     short loc_18000B1A7
0x18000b19d  mov     ebx, 80070008h
0x18000b1a2  jmp     loc_18000B2B0
0x18000b1a7  lea     rcx, [rsp+2B0h+var_248]
0x18000b1ac  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000b1b2  xor     r8d, r8d
0x18000b1b5  mov     [rsp+2B0h+var_270.lpElementArray], rax
0x18000b1ba  mov     rcx, rax
0x18000b1bd  cmp     [rbx+18h], r8d
0x18000b1c1  jbe     loc_18000B250
0x18000b1c7  mov     rax, [rbx+20h]
0x18000b1cb  mov     edx, r8d
0x18000b1ce  shl     rdx, 5
0x18000b1d2  cmp     qword ptr [rdx+rax], 0
0x18000b1d7  jz      short loc_18000B1FD
0x18000b1d9  mov     dword ptr [rdx+rcx], 0
0x18000b1e0  mov     rax, [rbx+20h]
0x18000b1e4  mov     rcx, [rdx+rax]
0x18000b1e8  mov     rax, [rsp+2B0h+var_270.lpElementArray]
0x18000b1ed  mov     [rdx+rax+8], rcx
0x18000b1f2  mov     rax, [rbx+20h]
0x18000b1f6  mov     rcx, [rdx+rax+18h]
0x18000b1fb  jmp     short loc_18000B233
0x18000b1fd  mov     dword ptr [rdx+rcx], 1
0x18000b204  mov     rax, [rbx+20h]
0x18000b208  mov     rcx, [rdx+rax+8]
0x18000b20d  mov     rax, [rsp+2B0h+var_270.lpElementArray]
0x18000b212  mov     [rdx+rax+8], rcx
0x18000b217  mov     rax, [rbx+20h]
0x18000b21b  mov     rcx, [rdx+rax+10h]
0x18000b220  mov     rax, [rsp+2B0h+var_270.lpElementArray]
0x18000b225  mov     [rdx+rax+10h], rcx
0x18000b22a  mov     rax, [rbx+20h]
0x18000b22e  mov     rcx, [rax+rdx+18h]
0x18000b233  mov     rax, [rsp+2B0h+var_270.lpElementArray]
0x18000b238  inc     r8d
0x18000b23b  mov     [rdx+rax+18h], rcx
0x18000b240  cmp     r8d, [rbx+18h]
0x18000b244  jnb     short loc_18000B250
0x18000b246  mov     rcx, [rsp+2B0h+var_270.lpElementArray]
0x18000b24b  jmp     loc_18000B1C7
0x18000b250  lea     rdx, [rsp+2B0h+var_270]; struct _HSE_RESPONSE_VECTOR *
0x18000b255  mov     rcx, rdi; this
0x18000b258  call    ?SSFVectorSend@@YAJPEAVISAPI_CONTEXT@@PEAU_HSE_RESPONSE_VECTOR@@@Z; SSFVectorSend(ISAPI_CONTEXT *,_HSE_RESPONSE_VECTOR *)
0x18000b25d  mov     ebx, eax
0x18000b25f  test    eax, eax
0x18000b261  jns     short loc_18000B2B0
0x18000b263  mov     ecx, cs:g_dwDebugFlags
0x18000b269  test    cl, 3
0x18000b26c  setnz   dl
0x18000b26f  bt      ecx, 14h
0x18000b273  setb    cl
0x18000b276  test    cl, dl
0x18000b278  jz      short loc_18000B2B0
0x18000b27a  mov     rcx, cs:g_pDebug
0x18000b281  lea     r9, aSsfvectorsendd; "SSFVectorSendDeprecated"
0x18000b288  mov     [rsp+2B0h+var_280], eax
0x18000b28c  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000b293  lea     rax, aHseReqVectorSe_14; "\r\n  HSE_REQ_VECTOR_SEND_DEPRECATED[%p"...
0x18000b29a  mov     [rsp+2B0h+var_288], rdi
0x18000b29f  mov     r8d, 0B06h
0x18000b2a5  mov     [rsp+2B0h+var_290], rax
0x18000b2aa  call    cs:__imp_PuDbgPrint
0x18000b2b0  lea     rcx, [rsp+2B0h+var_248]
0x18000b2b5  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000b2bb  mov     eax, ebx
0x18000b2bd  mov     rcx, [rbp+1B0h+var_10]
0x18000b2c4  xor     rcx, rsp; StackCookie
0x18000b2c7  call    __security_check_cookie
0x18000b2cc  lea     r11, [rsp+2B0h+var_s0]
0x18000b2d4  mov     rbx, [r11+20h]
0x18000b2d8  mov     rdi, [r11+28h]
0x18000b2dc  mov     rsp, r11
0x18000b2df  pop     rbp
0x18000b2e0  retn
```
