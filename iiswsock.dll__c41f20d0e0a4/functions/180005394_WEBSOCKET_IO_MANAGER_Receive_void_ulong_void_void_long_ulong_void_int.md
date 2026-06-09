# WEBSOCKET_IO_MANAGER::Receive(void *,ulong,void (*)(void *,long,ulong),void *,int *)

- ea: `0x180005394`
- end: `0x18000555f`
- name: `?Receive@WEBSOCKET_IO_MANAGER@@QEAAJPEAXKP6AX0JK@Z0PEAH@Z`
- size: `459`
- prototype: `__int64 __fastcall(WEBSOCKET_IO_MANAGER *__hidden this, void *, unsigned int, void (*)(void *, int, unsigned int), void *, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000477c`
- `0x180004bac`

## callees

- `0x180001008`
- `0x180001048`
- `0x180005394`
- `0x180009010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180005472`
- `iisutil!PuDbgPrint` at `0x18000553a`
- `iisutil!PuDbgPrint` at `0x180005472`
- `iisutil!PuDbgPrint` at `0x18000553a`

## string_xrefs

- `0x18000546b`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\wsio.cxx`
- `0x180005533`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\wsio.cxx`

## pseudocode

```c
__int64 __fastcall WEBSOCKET_IO_MANAGER::Receive(
        WEBSOCKET_IO_MANAGER *this,
        void *a2,
        unsigned int a3,
        void (*a4)(void *, int, unsigned int),
        void *a5,
        int *a6)
{
  __int64 v7; // rcx
  __int64 v10; // rbx
  int v11; // edi
  _QWORD *v12; // rax
  void *v13; // rbx
  __int64 v15; // [rsp+70h] [rbp+8h] BYREF
  int v16; // [rsp+88h] [rbp+20h]
  int v17; // [rsp+8Ch] [rbp+24h]

  v17 = HIDWORD(a4);
  v16 = 0;
  v7 = *((_QWORD *)this + 1);
  a6 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 24LL))(v7);
  v15 = 0;
  v11 = (*(__int64 (__fastcall **)(struct IHttpServer *, _QWORD, __int64 *))(*(_QWORD *)g_pGlobalInfo + 200LL))(
          g_pGlobalInfo,
          0,
          &v15);
  if ( v11 < 0 )
    goto LABEL_9;
  v11 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64, GUID *, int **))(*(_QWORD *)v15 + 224LL))(
          v15,
          &GUID_e8698f7e_576e_4cac_a309_67435355faef,
          v10,
          &GUID_b32e4e0f_4057_4feb_aeab_7b69c03c6314,
          &a6);
  if ( v11 < 0 )
    goto LABEL_9;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\wsio.cxx",
      357,
      "WEBSOCKET_IO_MANAGER::Receive",
      "Initiating Receive IO\n");
  v12 = operator new(0x18u);
  v13 = v12;
  if ( !v12 )
  {
    v11 = -2147024882;
LABEL_9:
    v13 = 0;
    goto LABEL_10;
  }
  *v12 = this;
  v12[1] = WEBSOCKET_WRAPPER::ReceiveLoopCompletionCallback;
  v12[2] = a5;
  _InterlockedAdd((volatile signed __int32 *)this + 4, 1u);
  v11 = (*(__int64 (__fastcall **)(int *, void *, _QWORD))(*(_QWORD *)a6 + 200LL))(a6, a2, a3);
  if ( v11 >= 0 )
    return (unsigned int)v11;
  _InterlockedDecrement((volatile signed __int32 *)this + 4);
LABEL_10:
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\wsio.cxx",
      397,
      "WEBSOCKET_IO_MANAGER::Receive",
      "ERROR = %08x\n",
      v11);
  operator delete(v13);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180005394  mov     rax, rsp
0x180005397  mov     [rax+10h], rbx
0x18000539b  mov     [rax+18h], rbp
0x18000539f  mov     [rax+20h], r9
0x1800053a3  push    rsi
0x1800053a4  push    rdi
0x1800053a5  push    r14
0x1800053a7  sub     rsp, 50h
0x1800053ab  mov     dword ptr [rax+20h], 0
0x1800053b2  mov     rsi, rcx
0x1800053b5  mov     rcx, [rcx+8]
0x1800053b9  mov     ebp, r8d
0x1800053bc  mov     qword ptr [rax+30h], 0
0x1800053c4  mov     r14, rdx
0x1800053c7  mov     rax, [rcx]
0x1800053ca  mov     rax, [rax+18h]
0x1800053ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053d3  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x1800053da  lea     r8, [rsp+68h+arg_0]
0x1800053df  mov     rbx, rax
0x1800053e2  mov     [rsp+68h+arg_0], 0
0x1800053eb  mov     rdx, [rcx]
0x1800053ee  mov     rax, [rdx+0C8h]
0x1800053f5  xor     edx, edx
0x1800053f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053fc  mov     edi, eax
0x1800053fe  test    eax, eax
0x180005400  js      loc_180005504
0x180005406  mov     rcx, [rsp+68h+arg_0]
0x18000540b  lea     rdx, [rsp+68h+arg_28]
0x180005413  mov     [rsp+68h+var_48], rdx
0x180005418  lea     r9, _GUID_b32e4e0f_4057_4feb_aeab_7b69c03c6314
0x18000541f  mov     r8, rbx
0x180005422  lea     rdx, _GUID_e8698f7e_576e_4cac_a309_67435355faef
0x180005429  mov     rax, [rcx]
0x18000542c  mov     rax, [rax+0E0h]
0x180005433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005438  mov     edi, eax
0x18000543a  test    eax, eax
0x18000543c  js      loc_180005504
0x180005442  test    byte ptr cs:g_dwDebugFlags, 3
0x180005449  jz      short loc_180005478
0x18000544b  mov     rcx, cs:g_pDebug
0x180005452  lea     rax, aInitiatingRece; "Initiating Receive IO\n"
0x180005459  lea     r9, aWebsocketIoMan_0; "WEBSOCKET_IO_MANAGER::Receive"
0x180005460  mov     [rsp+68h+var_48], rax
0x180005465  mov     r8d, 165h
0x18000546b  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005472  call    cs:__imp_PuDbgPrint
0x180005478  mov     ecx, 18h; Size
0x18000547d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005482  mov     rbx, rax
0x180005485  test    rax, rax
0x180005488  jz      short loc_1800054FF
0x18000548a  mov     [rax], rsi
0x18000548d  mov     r9d, 1
0x180005493  lea     rax, ?ReceiveLoopCompletionCallback@WEBSOCKET_WRAPPER@@CAXPEAXJK@Z; WEBSOCKET_WRAPPER::ReceiveLoopCompletionCallback(void *,long,ulong)
0x18000549a  mov     [rbx+8], rax
0x18000549e  mov     rax, [rsp+68h+arg_20]
0x1800054a6  mov     [rbx+10h], rax
0x1800054aa  lock add [rsi+10h], r9d
0x1800054af  mov     rcx, [rsp+68h+arg_28]
0x1800054b7  lea     rdx, [rsp+68h+arg_18]
0x1800054bf  mov     [rsp+68h+var_30], 0
0x1800054c8  mov     r8d, ebp
0x1800054cb  mov     [rsp+68h+var_38], rdx
0x1800054d0  lea     rdx, ?OnReadCompletion@WEBSOCKET_IO_MANAGER@@CA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext3@@PEAVIHttpCompletionInfo2@@PEAX@Z; WEBSOCKET_IO_MANAGER::OnReadCompletion(IHttpContext3 *,IHttpCompletionInfo2 *,void *)
0x1800054d7  mov     [rsp+68h+var_40], rbx
0x1800054dc  mov     rax, [rcx]
0x1800054df  mov     [rsp+68h+var_48], rdx
0x1800054e4  mov     rdx, r14
0x1800054e7  mov     rax, [rax+0C8h]
0x1800054ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054f3  mov     edi, eax
0x1800054f5  test    eax, eax
0x1800054f7  jns     short loc_180005548
0x1800054f9  lock dec dword ptr [rsi+10h]
0x1800054fd  jmp     short loc_180005506
0x1800054ff  mov     edi, 8007000Eh
0x180005504  xor     ebx, ebx
0x180005506  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000550d  jz      short loc_180005540
0x18000550f  mov     rcx, cs:g_pDebug
0x180005516  lea     rax, aError08x; "ERROR = %08x\n"
0x18000551d  mov     dword ptr [rsp+68h+var_40], edi
0x180005521  lea     r9, aWebsocketIoMan_0; "WEBSOCKET_IO_MANAGER::Receive"
0x180005528  mov     r8d, 18Dh
0x18000552e  mov     [rsp+68h+var_48], rax
0x180005533  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000553a  call    cs:__imp_PuDbgPrint
0x180005540  mov     rcx, rbx; Block
0x180005543  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005548  lea     r11, [rsp+68h+var_18]
0x18000554d  mov     eax, edi
0x18000554f  mov     rbx, [r11+28h]
0x180005553  mov     rbp, [r11+30h]
0x180005557  mov     rsp, r11
0x18000555a  pop     r14
0x18000555c  pop     rdi
0x18000555d  pop     rsi
0x18000555e  retn
```
