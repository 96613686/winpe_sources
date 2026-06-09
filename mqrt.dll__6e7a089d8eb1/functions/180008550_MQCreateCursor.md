# MQCreateCursor

- ea: `0x180008550`
- end: `0x1800087cc`
- name: `MQCreateCursor`
- size: `636`
- prototype: `HRESULT __stdcall(QUEUEHANDLE hQueue, PHANDLE phCursor)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops`

## callees

- `0x1800027f4`
- `0x180005488`
- `0x1800056e8`
- `0x180008550`
- `0x1800087f8`
- `0x180008838`
- `0x18000a6c4`
- `0x180013c74`
- `0x180014458`
- `0x180017ce0`
- `0x180021010`
- `0x180023c36`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180008698`
- `KERNEL32!GetLastError` at `0x180008698`
- `KERNEL32!WaitForSingleObject` at `0x180008672`
- `KERNEL32!WaitForSingleObject` at `0x180008672`

## pseudocode

```c
HRESULT __stdcall MQCreateCursor(QUEUEHANDLE hQueue, PHANDLE phCursor)
{
  int v4; // eax
  HRESULT v5; // ebx
  _DWORD *v7; // r14
  int ThreadEvent; // eax
  int v9; // ebx
  int v10; // eax
  int v11; // esi
  DWORD v12; // edi
  int Internal; // ebx
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  DWORD LastError; // eax
  int v18; // ebx
  __int64 v19; // [rsp+0h] [rbp-C8h] BYREF
  HRESULT v20; // [rsp+40h] [rbp-88h]
  _DWORD *v21; // [rsp+48h] [rbp-80h]
  __int64 *v22; // [rsp+50h] [rbp-78h]
  int v23; // [rsp+58h] [rbp-70h]
  int v24; // [rsp+5Ch] [rbp-6Ch]
  unsigned int v25; // [rsp+60h] [rbp-68h]
  struct _OVERLAPPED v26; // [rsp+68h] [rbp-60h] BYREF
  int v27; // [rsp+E0h] [rbp+18h] BYREF

  v22 = &v19;
  v4 = RtpOneTimeThreadInit();
  v5 = v4;
  if ( v4 >= 0 )
  {
    v25 = 1;
    v27 = 0;
    v21 = 0;
    v7 = MmAllocate(0x10u);
    v21 = v7;
    memset(&v26, 0, sizeof(v26));
    ThreadEvent = GetThreadEvent(&v26.hEvent);
    if ( ThreadEvent >= 0 )
    {
      v9 = MQpDeviceIoControl(hQueue, 0x19654144u, 0, 0, &v27, 4u, &v26);
      v10 = RTpConvertToMQCode(v9, 1u);
      v11 = v10;
      v23 = v10;
      v24 = v9;
      if ( v10 == 1074659334 )
      {
        v12 = WaitForSingleObject(v26.hEvent, 0xFFFFFFFF);
        Internal = v26.Internal;
        v14 = RTpConvertToMQCode(v26.Internal, 1u);
        v11 = v14;
        v23 = v14;
        v24 = Internal;
        if ( v12 )
        {
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              10,
              &WPP_dd64c8956ad73824671d334d82a6db03_Traceguids,
              LastError);
          v14 = RTpConvertToMQCode(-1072824281, 1u);
          v11 = v14;
          v23 = v14;
          v24 = -1072824281;
        }
        v18 = v14;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, v16, hQueue, v27);
      }
      else
      {
        v18 = v10;
      }
      if ( v18 >= 0 )
      {
        *(_QWORD *)v7 = hQueue;
        v7[2] = v27;
        *phCursor = v7;
        v7 = 0;
        v21 = 0;
      }
      operator delete(v7);
      if ( v11 < 0 )
        LogMsgHR(v11, (wchar_t *)L"rt/cursor", 0x32u);
      return v11;
    }
    else
    {
      v20 = LogHR(ThreadEvent, (wchar_t *)L"rt/cursor", 0x2Du);
      local_unwind_0(v22, &loc_180008609);
      return v20;
    }
  }
  else
  {
    LogMsgHR(v4, (wchar_t *)L"rt/cursor", 0x44Eu);
    return v5;
  }
}

```

## disassembly

```asm
0x180008550  push    rbx
0x180008552  push    rsi
0x180008553  push    rdi
0x180008554  push    r12
0x180008556  push    r14
0x180008558  push    r15
0x18000855a  sub     rsp, 98h
0x180008561  mov     [rsp+0C8h+var_78], rsp
0x180008566  mov     r12, rdx
0x180008569  mov     r15, rcx
0x18000856c  call    ?RtpOneTimeThreadInit@@YAJXZ; RtpOneTimeThreadInit(void)
0x180008571  mov     ebx, eax
0x180008573  test    eax, eax
0x180008575  jns     short loc_180008592
0x180008577  mov     r8d, 44Eh; unsigned __int16
0x18000857d  lea     rdx, aRtCursor; "rt/cursor"
0x180008584  mov     ecx, eax; int
0x180008586  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18000858b  mov     eax, ebx
0x18000858d  jmp     loc_1800087BB
0x180008592  mov     [rsp+0C8h+var_68], 1
0x18000859a  mov     [rsp+0C8h+arg_10], 0
0x1800085a5  mov     [rsp+0C8h+var_80], 0
0x1800085ae  mov     ecx, 10h; unsigned __int64
0x1800085b3  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800085b8  mov     r14, rax
0x1800085bb  mov     [rsp+0C8h+var_80], rax
0x1800085c0  xorps   xmm0, xmm0
0x1800085c3  movups  xmmword ptr [rsp+0C8h+var_60.Internal], xmm0
0x1800085c8  movups  xmmword ptr [rsp+0C8h+var_60.10h], xmm0
0x1800085cd  lea     rcx, [rsp+0C8h+var_60.hEvent]; void **
0x1800085d5  call    ?GetThreadEvent@@YAJAEAPEAX@Z; GetThreadEvent(void * &)
0x1800085da  test    eax, eax
0x1800085dc  jns     short loc_180008612
0x1800085de  mov     r8d, 2Dh ; '-'; unsigned __int16
0x1800085e4  lea     rdx, aRtCursor; "rt/cursor"
0x1800085eb  mov     ecx, eax; int
0x1800085ed  call    ?LogHR@@YAJJPEA_WG@Z; LogHR(long,wchar_t *,ushort)
0x1800085f2  mov     [rsp+0C8h+var_88], eax
0x1800085f6  lea     rdx, loc_180008609
0x1800085fd  mov     rcx, [rsp+0C8h+var_78]
0x180008602  call    _local_unwind_0
0x180008607  nop
0x180008608  nop
0x180008609  mov     eax, [rsp+0C8h+var_88]
0x18000860d  jmp     loc_1800087BB
0x180008612  lea     rax, [rsp+0C8h+var_60]
0x180008617  mov     [rsp+0C8h+var_98], rax; struct _OVERLAPPED *
0x18000861c  mov     [rsp+0C8h+var_A0], 4; unsigned int
0x180008624  lea     rax, [rsp+0C8h+arg_10]
0x18000862c  mov     [rsp+0C8h+var_A8], rax; void *
0x180008631  xor     r9d, r9d; unsigned int
0x180008634  xor     r8d, r8d; void *
0x180008637  mov     edx, 19654144h; unsigned int
0x18000863c  mov     rcx, r15; void *
0x18000863f  call    ?MQpDeviceIoControl@@YAJPEAXK0K0KPEAU_OVERLAPPED@@@Z; MQpDeviceIoControl(void *,ulong,void *,ulong,void *,ulong,_OVERLAPPED *)
0x180008644  mov     ebx, eax
0x180008646  mov     edx, 1; unsigned int
0x18000864b  mov     ecx, eax; int
0x18000864d  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x180008652  mov     esi, eax
0x180008654  mov     [rsp+0C8h+var_70], eax
0x180008658  mov     [rsp+0C8h+var_6C], ebx
0x18000865c  cmp     eax, 400E0006h
0x180008661  jnz     loc_180008720
0x180008667  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000866a  mov     rcx, [rsp+0C8h+var_60.hEvent]; hHandle
0x180008672  call    cs:__imp_WaitForSingleObject
0x180008678  mov     edi, eax
0x18000867a  mov     ebx, dword ptr [rsp+0C8h+var_60.Internal]
0x18000867e  mov     edx, 1; unsigned int
0x180008683  mov     ecx, ebx; int
0x180008685  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18000868a  mov     esi, eax
0x18000868c  mov     [rsp+0C8h+var_70], eax
0x180008690  mov     [rsp+0C8h+var_6C], ebx
0x180008694  test    edi, edi
0x180008696  jz      short loc_1800086EC
0x180008698  call    cs:__imp_GetLastError
0x18000869e  lea     rdi, WPP_GLOBAL_Control
0x1800086a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086ac  cmp     rcx, rdi
0x1800086af  jz      short loc_1800086CF
0x1800086b1  test    byte ptr [rcx+1Ch], 1
0x1800086b5  jz      short loc_1800086CF
0x1800086b7  mov     edx, 0Ah
0x1800086bc  mov     r9d, eax
0x1800086bf  lea     r8, WPP_dd64c8956ad73824671d334d82a6db03_Traceguids
0x1800086c6  mov     rcx, [rcx+10h]
0x1800086ca  call    WPP_SF_d
0x1800086cf  mov     edx, 1; unsigned int
0x1800086d4  mov     ebx, 0C00E0027h
0x1800086d9  mov     ecx, ebx; int
0x1800086db  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x1800086e0  mov     esi, eax
0x1800086e2  mov     [rsp+0C8h+var_70], eax
0x1800086e6  mov     [rsp+0C8h+var_6C], ebx
0x1800086ea  jmp     short loc_1800086F3
0x1800086ec  lea     rdi, WPP_GLOBAL_Control
0x1800086f3  mov     ebx, eax
0x1800086f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086fc  cmp     rcx, rdi
0x1800086ff  jz      short loc_180008722
0x180008701  test    byte ptr [rcx+1Ch], 4
0x180008705  jz      short loc_180008722
0x180008707  mov     eax, [rsp+0C8h+arg_10]
0x18000870e  mov     dword ptr [rsp+0C8h+var_A8], eax
0x180008712  mov     r9, r15
0x180008715  mov     rcx, [rcx+10h]
0x180008719  call    WPP_SF_qD
0x18000871e  jmp     short loc_180008722
0x180008720  mov     ebx, eax
0x180008722  test    ebx, ebx
0x180008724  js      short loc_180008740
0x180008726  mov     [r14], r15
0x180008729  mov     eax, [rsp+0C8h+arg_10]
0x180008730  mov     [r14+8], eax
0x180008734  mov     [r12], r14
0x180008738  xor     r14d, r14d
0x18000873b  mov     [rsp+0C8h+var_80], r14
0x180008740  mov     rcx, r14; void *
0x180008743  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008748  jmp     short loc_1800087A1
0x18000874a  mov     r8d, 28h ; '('; unsigned __int16
0x180008750  lea     rdx, aRtCursor; "rt/cursor"
0x180008757  mov     ecx, 0C00E0027h; int
0x18000875c  call    ?LogHR@@YAJJPEA_WG@Z; LogHR(long,wchar_t *,ushort)
0x180008761  mov     [rsp+0C8h+var_84], eax
0x180008765  lea     rdx, loc_180008778
0x18000876c  mov     rcx, [rsp+0C8h+var_78]
0x180008771  call    _local_unwind_0
0x180008776  nop
0x180008777  nop
0x180008778  mov     eax, [rsp+0C8h+var_84]
0x18000877c  jmp     short loc_1800087BB
0x18000877e  mov     ecx, eax
0x180008780  test    eax, eax
0x180008782  js      short loc_180008796
0x180008784  mov     eax, 0C00E000Bh
0x180008789  mov     edx, 0C0000008h
0x18000878e  cmp     ecx, 6
0x180008791  cmovz   eax, edx
0x180008794  mov     ecx, eax; int
0x180008796  mov     edx, [rsp+0C8h+var_68]; unsigned int
0x18000879a  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18000879f  mov     esi, eax
0x1800087a1  test    esi, esi
0x1800087a3  jns     short loc_1800087B9
0x1800087a5  mov     r8d, 32h ; '2'; unsigned __int16
0x1800087ab  lea     rdx, aRtCursor; "rt/cursor"
0x1800087b2  mov     ecx, esi; int
0x1800087b4  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800087b9  mov     eax, esi
0x1800087bb  add     rsp, 98h
0x1800087c2  pop     r15
0x1800087c4  pop     r14
0x1800087c6  pop     r12
0x1800087c8  pop     rdi
0x1800087c9  pop     rsi
0x1800087ca  pop     rbx
0x1800087cb  retn
0x180024242  push    rbp
0x180024244  sub     rsp, 40h
0x180024248  mov     rbp, rdx
0x18002424b  mov     rcx, [rbp+48h]; void *
0x18002424f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024254  nop
0x180024255  add     rsp, 40h
0x180024259  pop     rbp
0x18002425a  retn
```
