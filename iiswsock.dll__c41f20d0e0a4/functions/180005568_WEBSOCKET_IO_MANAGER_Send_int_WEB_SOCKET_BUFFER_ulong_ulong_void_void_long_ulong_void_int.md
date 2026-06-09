# WEBSOCKET_IO_MANAGER::Send(int,_WEB_SOCKET_BUFFER *,ulong,ulong *,void (*)(void *,long,ulong),void *,int *)

- ea: `0x180005568`
- end: `0x180005967`
- name: `?Send@WEBSOCKET_IO_MANAGER@@QEAAJHPEAT_WEB_SOCKET_BUFFER@@KPEAKP6AXPEAXJK@Z2PEAH@Z`
- size: `1023`
- prototype: `__int64 __fastcall(WEBSOCKET_IO_MANAGER *this, __int64, union _WEB_SOCKET_BUFFER *, unsigned int, unsigned int *, void (*)(void *, int, unsigned int), void *, int *)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004568`
- `0x18000477c`
- `0x180004bac`
- `0x1800050cc`

## callees

- `0x180001008`
- `0x180001048`
- `0x1800040c0`
- `0x1800050cc`
- `0x180005568`
- `0x1800085b6`
- `0x180009010`

## import_xrefs

- `msvcrt!free` at `0x1800058e9`
- `msvcrt!free` at `0x1800058e9`
- `msvcrt!malloc` at `0x1800056b4`
- `msvcrt!malloc` at `0x18000587e`
- `msvcrt!malloc` at `0x1800056b4`
- `msvcrt!malloc` at `0x18000587e`
- `iisutil!PuDbgPrint` at `0x1800055e7`
- `iisutil!PuDbgPrint` at `0x18000578d`
- `iisutil!PuDbgPrint` at `0x1800057dd`
- `iisutil!PuDbgPrint` at `0x180005842`
- `iisutil!PuDbgPrint` at `0x180005927`
- `iisutil!PuDbgPrint` at `0x1800055e7`
- `iisutil!PuDbgPrint` at `0x18000578d`
- `iisutil!PuDbgPrint` at `0x1800057dd`
- `iisutil!PuDbgPrint` at `0x180005842`
- `iisutil!PuDbgPrint` at `0x180005927`

## string_xrefs

- `0x1800055d6`: `No of Buffers = %08x, Expect Inline Completion = %1d\n`
- `0x1800055c8`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\wsio.cxx`
- `0x180005774`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\wsio.cxx`
- `0x1800057c0`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\wsio.cxx`
- `0x18000583b`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\wsio.cxx`
- `0x18000591a`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\wsio.cxx`
- `0x1800057d1`: `CompletionExpected = %1d\n`
- `0x180005822`: `WriteCompletedInline\n`

## pseudocode

```c
__int64 __fastcall WEBSOCKET_IO_MANAGER::Send(
        WEBSOCKET_IO_MANAGER *this,
        __int64 a2,
        union _WEB_SOCKET_BUFFER *a3,
        unsigned int a4,
        unsigned int *a5,
        void (*a6)(void *, int, unsigned int),
        void *a7,
        int *a8)
{
  int *v8; // r12
  __int64 v10; // r15
  _BYTE *v12; // r13
  __int64 v13; // rbx
  int v14; // edi
  _QWORD *v15; // rax
  void *v16; // rbx
  _BYTE *v17; // rax
  _BYTE *v18; // r8
  unsigned int v19; // r9d
  __int64 v20; // r10
  __int64 v21; // rdx
  __int64 v22; // rcx
  int v23; // eax
  _DWORD *v24; // rax
  _DWORD *v25; // r14
  void *v26; // rax
  void *v27; // rdx
  __int64 v29; // [rsp+60h] [rbp-51h] BYREF
  __int64 v30; // [rsp+68h] [rbp-49h] BYREF
  _BYTE Block[112]; // [rsp+78h] [rbp-39h] BYREF
  int v32; // [rsp+F8h] [rbp+47h]
  unsigned int v33; // [rsp+100h] [rbp+4Fh] BYREF
  void *Src; // [rsp+108h] [rbp+57h]

  Src = a3;
  v8 = a8;
  v10 = a4;
  v33 = 0;
  v12 = 0;
  v32 = 0;
  v30 = 0;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\wsio.cxx",
      64,
      "WEBSOCKET_IO_MANAGER::Send",
      "No of Buffers = %08x, Expect Inline Completion = %1d\n",
      a4,
      a8 != 0);
  v13 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 32LL))(*((_QWORD *)this + 1));
  v29 = 0;
  v14 = (*(__int64 (__fastcall **)(struct IHttpServer *, _QWORD, __int64 *))(*(_QWORD *)g_pGlobalInfo + 200LL))(
          g_pGlobalInfo,
          0,
          &v29);
  if ( v14 < 0 )
    goto LABEL_29;
  v14 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64, GUID *, __int64 *))(*(_QWORD *)v29 + 224LL))(
          v29,
          &GUID_7e1c6b38_628f_4e6c_95dc_41237eb7f95e,
          v13,
          &GUID_0822c871_f14e_4974_a1e6_5b3c1f09b76a,
          &v30);
  if ( v14 < 0 )
    goto LABEL_29;
  v15 = operator new(0x18u);
  v16 = v15;
  if ( !v15 )
  {
    v14 = -2147024882;
LABEL_29:
    v16 = 0;
    goto LABEL_30;
  }
  *v15 = this;
  v15[1] = a6;
  v15[2] = a7;
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)this + 6, 1, 0) )
  {
    v32 = 1;
    _InterlockedAdd((volatile signed __int32 *)this + 4, 1u);
    if ( (unsigned int)v10 <= 2 )
    {
      v12 = Block;
      v19 = 0;
      v18 = Block;
      if ( !(_DWORD)v10 )
        goto LABEL_13;
      goto LABEL_11;
    }
    v17 = malloc(32 * v10);
    v12 = v17;
    if ( v17 )
    {
      v18 = v17;
      v19 = 0;
LABEL_11:
      v20 = 0;
      do
      {
        v21 = 32 * v20;
        v22 = 2 * v20;
        ++v19;
        ++v20;
        *(_DWORD *)&v18[v21] = 0;
        *(_DWORD *)&v18[v21 + 16] = *((_DWORD *)a3 + 2 * v22 + 2);
        *(_QWORD *)&v18[v21 + 8] = *((_QWORD *)a3 + v22);
      }
      while ( v19 < (unsigned int)v10 );
LABEL_13:
      v23 = (*(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, __int64, int, void *, void *, unsigned int *, int *))(*(_QWORD *)v30 + 224LL))(
              v30,
              v12,
              (unsigned int)v10,
              1,
              1,
              &WEBSOCKET_IO_MANAGER::OnWriteCompletion,
              v16,
              &v33,
              v8);
      v14 = v23;
      if ( v23 >= 0 )
      {
        if ( v8 )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\wsio.cxx",
              198,
              "WEBSOCKET_IO_MANAGER::Send",
              "CompletionExpected = %1d\n",
              *v8);
          if ( !*v8 )
          {
            _InterlockedDecrement((volatile signed __int32 *)this + 4);
            _InterlockedCompareExchange((volatile signed __int32 *)this + 6, 0, 1);
            WEBSOCKET_IO_MANAGER::InitiateNextQueuedSend(this);
            operator delete(v16);
            v16 = 0;
            if ( (g_dwDebugFlags & 3) != 0 )
              PuDbgPrint(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\wsio.cxx",
                231,
                "WEBSOCKET_IO_MANAGER::Send",
                "WriteCompletedInline\n");
          }
        }
      }
      else
      {
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\wsio.cxx",
            178,
            "WEBSOCKET_IO_MANAGER::Send",
            "ERROR = %08x\n",
            v23);
        _InterlockedDecrement((volatile signed __int32 *)this + 4);
      }
      goto LABEL_30;
    }
LABEL_27:
    v14 = -2147024882;
    goto LABEL_30;
  }
  v24 = operator new(0x38u);
  v25 = v24;
  if ( !v24 )
    goto LABEL_27;
  v24[6] = 0;
  v24[10] = 0;
  *((_QWORD *)v24 + 6) = 0;
  *(_QWORD *)v24 = &SEND_QUEUE_RECORD::`vftable';
  v26 = malloc(16 * v10);
  *((_QWORD *)v25 + 4) = v26;
  if ( !v26 )
    goto LABEL_27;
  v27 = Src;
  v25[10] = v10;
  memcpy_0(v26, v27, 16 * v10);
  *((_QWORD *)v25 + 6) = v16;
  v14 = 0;
  QUEUE::Enqueue((WEBSOCKET_IO_MANAGER *)((char *)this + 40), (struct QUEUE_RECORD *)v25);
  if ( v8 )
    *v8 = 1;
LABEL_30:
  if ( a5 )
    *a5 = v33;
  if ( v12 != Block )
    free(v12);
  if ( v14 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\wsio.cxx",
        249,
        "WEBSOCKET_IO_MANAGER::Send",
        "Error = %08x\n",
        v14);
    if ( v32 )
      _InterlockedCompareExchange((volatile signed __int32 *)this + 6, 0, 1);
    if ( v16 )
      operator delete(v16);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180005568  mov     rax, rsp
0x18000556b  mov     [rax+20h], rbx
0x18000556f  mov     [rax+18h], r8
0x180005573  mov     [rax+10h], edx
0x180005576  push    rbp
0x180005577  push    rsi
0x180005578  push    rdi
0x180005579  push    r12
0x18000557b  push    r13
0x18000557d  push    r14
0x18000557f  push    r15
0x180005581  lea     rbp, [rax-3Fh]
0x180005585  sub     rsp, 0B0h
0x18000558c  mov     r12, [rbp+37h+arg_38]
0x180005590  xor     edi, edi
0x180005592  test    byte ptr cs:g_dwDebugFlags, 3
0x180005599  mov     r14, r8
0x18000559c  mov     r15d, r9d
0x18000559f  mov     rsi, rcx
0x1800055a2  mov     [rbp+37h+arg_8], edi
0x1800055a5  mov     r13d, edi
0x1800055a8  mov     [rbp+37h+arg_0], edi
0x1800055ab  mov     [rbp+37h+var_80], rdi
0x1800055af  jz      short loc_1800055ED
0x1800055b1  mov     rcx, cs:g_pDebug
0x1800055b8  lea     r9, aWebsocketIoMan_2; "WEBSOCKET_IO_MANAGER::Send"
0x1800055bf  mov     eax, edi
0x1800055c1  lea     r8d, [rdi+40h]
0x1800055c5  test    r12, r12
0x1800055c8  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800055cf  setnz   al
0x1800055d2  mov     dword ptr [rsp+0E0h+var_B0], eax
0x1800055d6  lea     rax, aNoOfBuffers08x; "No of Buffers = %08x, Expect Inline Com"...
0x1800055dd  mov     dword ptr [rsp+0E0h+var_B8], r15d
0x1800055e2  mov     [rsp+0E0h+var_C0], rax
0x1800055e7  call    cs:__imp_PuDbgPrint
0x1800055ed  mov     rcx, [rsi+8]
0x1800055f1  mov     rax, [rcx]
0x1800055f4  mov     rax, [rax+20h]
0x1800055f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055fd  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180005604  lea     r8, [rbp+37h+var_88]
0x180005608  mov     rbx, rax
0x18000560b  mov     [rbp+37h+var_88], rdi
0x18000560f  xor     edx, edx
0x180005611  mov     rax, [rcx]
0x180005614  mov     rax, [rax+0C8h]
0x18000561b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005620  mov     edi, eax
0x180005622  test    eax, eax
0x180005624  js      loc_1800058CD
0x18000562a  mov     rcx, [rbp+37h+var_88]
0x18000562e  lea     rdx, [rbp+37h+var_80]
0x180005632  mov     [rsp+0E0h+var_C0], rdx
0x180005637  lea     r9, _GUID_0822c871_f14e_4974_a1e6_5b3c1f09b76a
0x18000563e  mov     r8, rbx
0x180005641  lea     rdx, _GUID_7e1c6b38_628f_4e6c_95dc_41237eb7f95e
0x180005648  mov     rax, [rcx]
0x18000564b  mov     rax, [rax+0E0h]
0x180005652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005657  mov     edi, eax
0x180005659  test    eax, eax
0x18000565b  js      loc_1800058CD
0x180005661  mov     ecx, 18h; Size
0x180005666  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000566b  xor     edi, edi
0x18000566d  mov     rbx, rax
0x180005670  test    rax, rax
0x180005673  jz      loc_1800058C8
0x180005679  mov     [rax], rsi
0x18000567c  lea     r11d, [rdi+1]
0x180005680  mov     rax, [rbp+37h+arg_28]
0x180005684  mov     [rbx+8], rax
0x180005688  mov     rax, [rbp+37h+arg_30]
0x18000568c  mov     [rbx+10h], rax
0x180005690  xor     eax, eax
0x180005692  lock cmpxchg [rsi+18h], r11d
0x180005698  jnz     loc_18000584D
0x18000569e  mov     [rbp+37h+arg_0], r11d
0x1800056a2  lock add [rsi+10h], r11d
0x1800056a7  cmp     r15d, 2
0x1800056ab  jbe     short loc_1800056D2
0x1800056ad  mov     rcx, r15
0x1800056b0  shl     rcx, 5; Size
0x1800056b4  call    cs:__imp_malloc
0x1800056ba  mov     r13, rax
0x1800056bd  test    rax, rax
0x1800056c0  jz      loc_1800058C1
0x1800056c6  mov     r8, rax
0x1800056c9  lea     r11d, [rdi+1]
0x1800056cd  mov     r9d, edi
0x1800056d0  jmp     short loc_1800056E1
0x1800056d2  lea     r13, [rbp+37h+Block]
0x1800056d6  mov     r9d, edi
0x1800056d9  mov     r8, r13
0x1800056dc  test    r15d, r15d
0x1800056df  jz      short loc_180005713
0x1800056e1  mov     r10, rdi
0x1800056e4  mov     rdx, r10
0x1800056e7  mov     rcx, r10
0x1800056ea  shl     rdx, 5
0x1800056ee  add     rcx, rcx
0x1800056f1  add     r9d, r11d
0x1800056f4  add     r10, r11
0x1800056f7  mov     [rdx+r8], edi
0x1800056fb  mov     eax, [r14+rcx*8+8]
0x180005700  mov     [rdx+r8+10h], eax
0x180005705  mov     rax, [r14+rcx*8]
0x180005709  mov     [rdx+r8+8], rax
0x18000570e  cmp     r9d, r15d
0x180005711  jb      short loc_1800056E4
0x180005713  mov     rcx, [rbp+37h+var_80]
0x180005717  lea     rdx, [rbp+37h+arg_8]
0x18000571b  mov     [rsp+40h], r12
0x180005720  mov     r9d, r11d
0x180005723  mov     [rsp+0E0h+var_A8], rdx
0x180005728  mov     r8d, r15d
0x18000572b  lea     rdx, ?OnWriteCompletion@WEBSOCKET_IO_MANAGER@@CA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext3@@PEAVIHttpCompletionInfo2@@PEAX@Z; WEBSOCKET_IO_MANAGER::OnWriteCompletion(IHttpContext3 *,IHttpCompletionInfo2 *,void *)
0x180005732  mov     [rsp+0E0h+var_B0], rbx
0x180005737  mov     rax, [rcx]
0x18000573a  mov     [rsp+0E0h+var_B8], rdx
0x18000573f  mov     rdx, r13
0x180005742  mov     dword ptr [rsp+0E0h+var_C0], r11d
0x180005747  mov     rax, [rax+0E0h]
0x18000574e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005753  mov     edi, eax
0x180005755  test    eax, eax
0x180005757  jns     short loc_18000579C
0x180005759  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005760  jz      short loc_180005793
0x180005762  mov     rcx, cs:g_pDebug
0x180005769  lea     r9, aWebsocketIoMan_2; "WEBSOCKET_IO_MANAGER::Send"
0x180005770  mov     dword ptr [rsp+0E0h+var_B8], eax
0x180005774  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000577b  lea     rax, aError08x; "ERROR = %08x\n"
0x180005782  mov     r8d, 0B2h
0x180005788  mov     [rsp+0E0h+var_C0], rax
0x18000578d  call    cs:__imp_PuDbgPrint
0x180005793  lock dec dword ptr [rsi+10h]
0x180005797  jmp     loc_1800058CF
0x18000579c  test    r12, r12
0x18000579f  jz      loc_1800058CF
0x1800057a5  test    byte ptr cs:g_dwDebugFlags, 3
0x1800057ac  jz      short loc_1800057E3
0x1800057ae  mov     eax, [r12]
0x1800057b2  lea     r9, aWebsocketIoMan_2; "WEBSOCKET_IO_MANAGER::Send"
0x1800057b9  mov     rcx, cs:g_pDebug
0x1800057c0  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800057c7  mov     dword ptr [rsp+0E0h+var_B8], eax
0x1800057cb  mov     r8d, 0C6h
0x1800057d1  lea     rax, aCompletionexpe; "CompletionExpected = %1d\n"
0x1800057d8  mov     [rsp+0E0h+var_C0], rax
0x1800057dd  call    cs:__imp_PuDbgPrint
0x1800057e3  cmp     dword ptr [r12], 0
0x1800057e8  jnz     loc_1800058CF
0x1800057ee  lock dec dword ptr [rsi+10h]
0x1800057f2  xor     edx, edx
0x1800057f4  lea     eax, [rdx+1]
0x1800057f7  lock cmpxchg [rsi+18h], edx
0x1800057fc  mov     rcx, rsi; this
0x1800057ff  call    ?InitiateNextQueuedSend@WEBSOCKET_IO_MANAGER@@AEAAJXZ; WEBSOCKET_IO_MANAGER::InitiateNextQueuedSend(void)
0x180005804  mov     rcx, rbx; Block
0x180005807  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000580c  xor     ebx, ebx
0x18000580e  test    byte ptr cs:g_dwDebugFlags, 3
0x180005815  jz      loc_1800058CF
0x18000581b  mov     rcx, cs:g_pDebug
0x180005822  lea     rax, aWritecompleted; "WriteCompletedInline\n"
0x180005829  lea     r9, aWebsocketIoMan_2; "WEBSOCKET_IO_MANAGER::Send"
0x180005830  mov     [rsp+0E0h+var_C0], rax
0x180005835  mov     r8d, 0E7h
0x18000583b  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005842  call    cs:__imp_PuDbgPrint
0x180005848  jmp     loc_1800058CF
0x18000584d  mov     ecx, 38h ; '8'; Size
0x180005852  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005857  mov     r14, rax
0x18000585a  test    rax, rax
0x18000585d  jz      short loc_1800058C1
0x18000585f  mov     [rax+18h], edi
0x180005862  lea     rax, ??_7SEND_QUEUE_RECORD@@6B@; const SEND_QUEUE_RECORD::`vftable'
0x180005869  mov     [r14+28h], edi
0x18000586d  mov     [r14+30h], rdi
0x180005871  mov     rdi, r15
0x180005874  shl     rdi, 4
0x180005878  mov     rcx, rdi; Size
0x18000587b  mov     [r14], rax
0x18000587e  call    cs:__imp_malloc
0x180005884  mov     [r14+20h], rax
0x180005888  test    rax, rax
0x18000588b  jz      short loc_1800058C1
0x18000588d  mov     rdx, [rbp+37h+Src]; Src
0x180005891  mov     r8, rdi; Size
0x180005894  mov     rcx, rax; void *
0x180005897  mov     [r14+28h], r15d
0x18000589b  call    memcpy_0
0x1800058a0  lea     rcx, [rsi+28h]; this
0x1800058a4  mov     [r14+30h], rbx
0x1800058a8  mov     rdx, r14; struct QUEUE_RECORD *
0x1800058ab  xor     edi, edi
0x1800058ad  call    ?Enqueue@QUEUE@@QEAAXPEAVQUEUE_RECORD@@@Z; QUEUE::Enqueue(QUEUE_RECORD *)
0x1800058b2  test    r12, r12
0x1800058b5  jz      short loc_1800058CF
0x1800058b7  mov     dword ptr [r12], 1
0x1800058bf  jmp     short loc_1800058CF
0x1800058c1  mov     edi, 8007000Eh
0x1800058c6  jmp     short loc_1800058CF
0x1800058c8  mov     edi, 8007000Eh
0x1800058cd  xor     ebx, ebx
0x1800058cf  mov     rcx, [rbp+37h+arg_20]
0x1800058d3  test    rcx, rcx
0x1800058d6  jz      short loc_1800058DD
0x1800058d8  mov     eax, [rbp+37h+arg_8]
0x1800058db  mov     [rcx], eax
0x1800058dd  lea     rax, [rbp+37h+Block]
0x1800058e1  cmp     r13, rax
0x1800058e4  jz      short loc_1800058EF
0x1800058e6  mov     rcx, r13; Block
0x1800058e9  call    cs:__imp_free
0x1800058ef  test    edi, edi
0x1800058f1  jns     short loc_18000594A
0x1800058f3  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800058fa  jz      short loc_18000592D
0x1800058fc  lea     rcx, aError08x_0; "Error = %08x\n"
0x180005903  mov     dword ptr [rsp+0E0h+var_B8], edi
0x180005907  mov     [rsp+0E0h+var_C0], rcx
0x18000590c  lea     r9, aWebsocketIoMan_2; "WEBSOCKET_IO_MANAGER::Send"
0x180005913  mov     rcx, cs:g_pDebug
0x18000591a  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005921  mov     r8d, 0F9h
0x180005927  call    cs:__imp_PuDbgPrint
0x18000592d  cmp     [rbp+37h+arg_0], 0
0x180005931  jz      short loc_18000593D
0x180005933  xor     ecx, ecx
0x180005935  lea     eax, [rcx+1]
0x180005938  lock cmpxchg [rsi+18h], ecx
0x18000593d  test    rbx, rbx
0x180005940  jz      short loc_18000594A
0x180005942  mov     rcx, rbx; Block
0x180005945  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000594a  mov     rbx, [rsp+0E0h+arg_18]
0x180005952  mov     eax, edi
0x180005954  add     rsp, 0B0h
0x18000595b  pop     r15
0x18000595d  pop     r14
0x18000595f  pop     r13
0x180005961  pop     r12
0x180005963  pop     rdi
0x180005964  pop     rsi
0x180005965  pop     rbp
0x180005966  retn
```
