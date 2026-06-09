# SSFSendResponseHeader(ISAPI_CONTEXT *,char *,char *)

- ea: `0x180009d40`
- end: `0x180009f08`
- name: `?SSFSendResponseHeader@@YAJPEAVISAPI_CONTEXT@@PEAD1@Z`
- size: `456`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *, char *, char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x180009d40`
- `0x180013010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180009da7`
- `iisutil!PuDbgPrint` at `0x180009dff`
- `iisutil!PuDbgPrint` at `0x180009e98`
- `iisutil!PuDbgPrint` at `0x180009ef0`
- `iisutil!PuDbgPrint` at `0x180009da7`
- `iisutil!PuDbgPrint` at `0x180009dff`
- `iisutil!PuDbgPrint` at `0x180009e98`
- `iisutil!PuDbgPrint` at `0x180009ef0`

## string_xrefs

- `0x180009d8f`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180009df8`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180009e7a`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180009ee9`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`

## pseudocode

```c
__int64 __fastcall SSFSendResponseHeader(struct ISAPI_CONTEXT *a1, char *a2, char *a3)
{
  int v3; // r10d
  __int64 v7; // rcx
  int v9; // eax
  int v10; // ecx
  unsigned int v11; // edi

  v3 = g_dwDebugFlags;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      70,
      "SSFSendResponseHeader",
      "\r\n"
      "  HSE_REQ_SEND_RESPONSE_HEADER[%p]: Function Entry\r\n"
      "    Status: '%s'\r\n"
      "    Headers: '%s'\r\n"
      "  <END>\r\n"
      "\r\n",
      a1,
      a2,
      a3);
    v3 = g_dwDebugFlags;
  }
  v7 = *((_QWORD *)a1 + 24);
  if ( v7 )
  {
    if ( *((_DWORD *)a1 + 62) )
      *((_DWORD *)a1 + 63) = 1;
    v9 = (*(__int64 (__fastcall **)(__int64, bool, char *, char *, int))(*(_QWORD *)v7 + 24LL))(
           v7,
           *((_DWORD *)a1 + 63) == 0,
           a2,
           a3,
           1);
    v10 = g_dwDebugFlags;
    v11 = v9;
    if ( v9 >= 0 )
    {
      *((_DWORD *)a1 + 64) = 1;
      if ( (v10 & 0x4000000) != 0 && (v10 & 3) != 0 && (v10 & 0x200000) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
          141,
          "SSFSendResponseHeader",
          "\r\n  HSE_REQ_SEND_RESPONSE_HEADER[%p]: Succeeded\r\n  <END>\r\n\r\n",
          a1);
    }
    else if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
    {
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        122,
        "SSFSendResponseHeader",
        "\r\n  HSE_REQ_SEND_RESPONSE_HEADER[%p]: Failed\r\n    Error: 0x%08x\r\n  <END>\r\n\r\n",
        a1,
        v9);
    }
    return v11;
  }
  else
  {
    if ( (v3 & 3) != 0 && (v3 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        83,
        "SSFSendResponseHeader",
        "\r\n  HSE_REQ_SEND_RESPONSE_HEADER[%p]: Failed to get interface to server core\r\n  <END>\r\n\r\n",
        a1);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180009d40  mov     r11, rsp
0x180009d43  mov     [r11+8], rbx
0x180009d47  mov     [r11+10h], rsi
0x180009d4b  push    rdi
0x180009d4c  sub     rsp, 40h
0x180009d50  mov     r10d, cs:g_dwDebugFlags
0x180009d57  mov     rdi, r8
0x180009d5a  test    r10b, 3
0x180009d5e  mov     rsi, rdx
0x180009d61  mov     rbx, rcx
0x180009d64  setnz   r9b
0x180009d68  bt      r10d, 1Ah
0x180009d6d  setb    al
0x180009d70  test    al, r9b
0x180009d73  jz      short loc_180009DB4
0x180009d75  mov     [r11-10h], r8
0x180009d79  lea     rax, aHseReqSendResp_5; "\r\n  HSE_REQ_SEND_RESPONSE_HEADER[%p]:"...
0x180009d80  mov     [r11-18h], rdx
0x180009d84  lea     r9, aSsfsendrespons; "SSFSendResponseHeader"
0x180009d8b  mov     [r11-20h], rcx
0x180009d8f  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180009d96  mov     rcx, cs:g_pDebug
0x180009d9d  mov     r8d, 46h ; 'F'
0x180009da3  mov     [r11-28h], rax
0x180009da7  call    cs:__imp_PuDbgPrint
0x180009dad  mov     r10d, cs:g_dwDebugFlags
0x180009db4  mov     rcx, [rbx+0C0h]
0x180009dbb  test    rcx, rcx
0x180009dbe  jnz     short loc_180009E0F
0x180009dc0  test    r10b, 3
0x180009dc4  setnz   cl
0x180009dc7  bt      r10d, 14h
0x180009dcc  setb    al
0x180009dcf  test    al, cl
0x180009dd1  jz      short loc_180009E05
0x180009dd3  mov     rcx, cs:g_pDebug
0x180009dda  lea     rax, aHseReqSendResp_3; "\r\n  HSE_REQ_SEND_RESPONSE_HEADER[%p]:"...
0x180009de1  mov     [rsp+48h+var_20], rbx
0x180009de6  lea     r9, aSsfsendrespons; "SSFSendResponseHeader"
0x180009ded  mov     r8d, 53h ; 'S'
0x180009df3  mov     [rsp+48h+var_28], rax
0x180009df8  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180009dff  call    cs:__imp_PuDbgPrint
0x180009e05  mov     eax, 80070057h
0x180009e0a  jmp     loc_180009EF8
0x180009e0f  cmp     dword ptr [rbx+0F8h], 0
0x180009e16  jz      short loc_180009E22
0x180009e18  mov     dword ptr [rbx+0FCh], 1
0x180009e22  mov     rax, [rcx]
0x180009e25  xor     edx, edx
0x180009e27  cmp     [rbx+0FCh], edx
0x180009e2d  mov     r9, rdi
0x180009e30  mov     r8, rsi
0x180009e33  mov     dword ptr [rsp+48h+var_28], 1
0x180009e3b  setz    dl
0x180009e3e  mov     rax, [rax+18h]
0x180009e42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e47  mov     ecx, cs:g_dwDebugFlags
0x180009e4d  mov     edi, eax
0x180009e4f  test    eax, eax
0x180009e51  jns     short loc_180009EA0
0x180009e53  test    cl, 3
0x180009e56  setnz   dl
0x180009e59  bt      ecx, 14h
0x180009e5d  setb    cl
0x180009e60  test    cl, dl
0x180009e62  jz      loc_180009EF6
0x180009e68  mov     rcx, cs:g_pDebug
0x180009e6f  lea     r9, aSsfsendrespons; "SSFSendResponseHeader"
0x180009e76  mov     [rsp+48h+var_18], eax
0x180009e7a  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180009e81  lea     rax, aHseReqSendResp_8; "\r\n  HSE_REQ_SEND_RESPONSE_HEADER[%p]:"...
0x180009e88  mov     [rsp+48h+var_20], rbx
0x180009e8d  mov     r8d, 7Ah ; 'z'
0x180009e93  mov     [rsp+48h+var_28], rax
0x180009e98  call    cs:__imp_PuDbgPrint
0x180009e9e  jmp     short loc_180009EF6
0x180009ea0  test    cl, 3
0x180009ea3  mov     dword ptr [rbx+100h], 1
0x180009ead  setnz   dl
0x180009eb0  bt      ecx, 1Ah
0x180009eb4  setb    al
0x180009eb7  and     dl, al
0x180009eb9  bt      ecx, 15h
0x180009ebd  setb    al
0x180009ec0  test    al, dl
0x180009ec2  jz      short loc_180009EF6
0x180009ec4  mov     rcx, cs:g_pDebug
0x180009ecb  lea     rax, aHseReqSendResp_1; "\r\n  HSE_REQ_SEND_RESPONSE_HEADER[%p]:"...
0x180009ed2  mov     [rsp+48h+var_20], rbx
0x180009ed7  lea     r9, aSsfsendrespons; "SSFSendResponseHeader"
0x180009ede  mov     r8d, 8Dh
0x180009ee4  mov     [rsp+48h+var_28], rax
0x180009ee9  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180009ef0  call    cs:__imp_PuDbgPrint
0x180009ef6  mov     eax, edi
0x180009ef8  mov     rbx, [rsp+48h+arg_0]
0x180009efd  mov     rsi, [rsp+48h+arg_8]
0x180009f02  add     rsp, 40h
0x180009f06  pop     rdi
0x180009f07  retn
```
