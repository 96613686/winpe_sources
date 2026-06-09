# ATL::CAtlExeModuleT<CcttunesvrModule>::Run(int)

- ea: `0x140005f38`
- end: `0x1400060f3`
- name: `?Run@?$CAtlExeModuleT@VCcttunesvrModule@@@ATL@@QEAAJH@Z`
- size: `443`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1400063fc`

## callees

- `0x140005f38`
- `0x140007010`

## import_xrefs

- `KERNEL32!Sleep` at `0x1400060db`
- `KERNEL32!Sleep` at `0x1400060db`
- `KERNEL32!CreateEventW` at `0x140005ff4`
- `KERNEL32!CreateEventW` at `0x140005ff4`
- `KERNEL32!CreateThread` at `0x140006030`
- `KERNEL32!CreateThread` at `0x140006030`
- `KERNEL32!CloseHandle` at `0x140006042`
- `KERNEL32!CloseHandle` at `0x140006042`
- `USER32!GetMessageW` at `0x14000608b`
- `USER32!GetMessageW` at `0x14000608b`
- `USER32!TranslateMessage` at `0x14000606f`
- `USER32!TranslateMessage` at `0x14000606f`
- `USER32!DispatchMessageW` at `0x140006079`
- `USER32!DispatchMessageW` at `0x140006079`
- `ole32!CoRevokeClassObject` at `0x1400060b7`
- `ole32!CoRevokeClassObject` at `0x1400060b7`
- `ole32!CoRegisterClassObject` at `0x140005fb3`
- `ole32!CoRegisterClassObject` at `0x140005fb3`

## pseudocode

```c
__int64 __fastcall ATL::CAtlExeModuleT<CcttunesvrModule>::Run(IUnknown *a1, DWORD a2)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 **v2; // rdi
  HRESULT v3; // ebx
  bool v4; // zf
  struct ATL::_ATL_OBJMAP_ENTRY30 *v5; // rsi
  __int64 (__fastcall *v6)(_QWORD, GUID *, LPUNKNOWN *); // rax
  struct ATL::_ATL_OBJMAP_ENTRY30 **v7; // rdi
  DWORD v8; // ecx
  MSG Msg; // [rsp+30h] [rbp-30h] BYREF
  LPUNKNOWN pUnk; // [rsp+80h] [rbp+20h] BYREF
  DWORD ThreadId; // [rsp+88h] [rbp+28h] BYREF

  ThreadId = a2;
  pUnk = a1;
  v2 = off_14000B100;
  v3 = 1;
  while ( v2 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_14000B108 )
  {
    v4 = v3 == 0;
    if ( v3 < 0 )
      goto LABEL_13;
    v5 = *v2;
    if ( *v2 )
    {
      v6 = (__int64 (__fastcall *)(_QWORD, GUID *, LPUNKNOWN *))*((_QWORD *)v5 + 2);
      pUnk = 0;
      if ( v6 )
      {
        v3 = v6(*((_QWORD *)v5 + 3), &GUID_00000000_0000_0000_c000_000000000046, &pUnk);
        if ( v3 >= 0 )
          v3 = CoRegisterClassObject(*(const IID *const *)v5, pUnk, 4u, 1u, (LPDWORD)v5 + 10);
        if ( pUnk )
          ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
      }
      else
      {
        v3 = 0;
      }
    }
    ++v2;
  }
  v4 = v3 == 0;
LABEL_13:
  if ( v4 )
  {
    if ( !byte_14000B870 )
      goto LABEL_20;
    hObject = CreateEventW(0, 0, 0, 0);
    if ( hObject )
    {
      ThreadId = 0;
      if ( CreateThread(0, 0, ATL::CAtlExeModuleT<CcttunesvrModule>::MonitorProc, &_AtlModule, 0, &ThreadId) )
        goto LABEL_20;
      CloseHandle(hObject);
    }
    v3 = -2147467259;
  }
  else
  {
    byte_14000B870 = 0;
  }
LABEL_20:
  if ( v3 )
  {
    if ( v3 < 0 )
      return (unsigned int)v3;
  }
  else
  {
    memset(&Msg, 0, sizeof(Msg));
    while ( GetMessageW(&Msg, 0, 0, 0) > 0 )
    {
      TranslateMessage(&Msg);
      DispatchMessageW(&Msg);
    }
  }
  v7 = off_14000B100;
  v3 = 0;
  while ( v7 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_14000B108 && !v3 )
  {
    if ( *v7 )
    {
      v8 = *((_DWORD *)*v7 + 10);
      if ( v8 )
        v3 = CoRevokeClassObject(v8);
    }
    ++v7;
  }
  if ( byte_14000B870 )
    Sleep(dwMilliseconds);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140005f38  mov     [rsp-18h+arg_10], rbx
0x140005f3d  mov     [rsp-18h+ThreadId], edx
0x140005f41  mov     [rsp-18h+pUnk], rcx
0x140005f46  push    rbp
0x140005f47  push    rsi
0x140005f48  push    rdi
0x140005f49  mov     rbp, rsp
0x140005f4c  sub     rsp, 60h
0x140005f50  mov     rdi, cs:off_14000B100
0x140005f57  mov     ebx, 1
0x140005f5c  jmp     short loc_140005FD4
0x140005f5e  test    ebx, ebx
0x140005f60  js      short loc_140005FDF
0x140005f62  mov     rsi, [rdi]
0x140005f65  test    rsi, rsi
0x140005f68  jz      short loc_140005FD0
0x140005f6a  mov     rax, [rsi+10h]
0x140005f6e  mov     [rbp+pUnk], 0
0x140005f76  test    rax, rax
0x140005f79  jnz     short loc_140005F7F
0x140005f7b  xor     ebx, ebx
0x140005f7d  jmp     short loc_140005FD0
0x140005f7f  mov     rcx, [rsi+18h]
0x140005f83  lea     r8, [rbp+pUnk]
0x140005f87  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x140005f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f93  mov     ebx, eax
0x140005f95  test    eax, eax
0x140005f97  js      short loc_140005FBB
0x140005f99  mov     rdx, [rbp+pUnk]; pUnk
0x140005f9d  lea     rax, [rsi+28h]
0x140005fa1  mov     rcx, [rsi]; rclsid
0x140005fa4  mov     r9d, 1; flags
0x140005faa  mov     [rsp+60h+lpdwRegister], rax; lpdwRegister
0x140005faf  lea     r8d, [r9+3]; dwClsContext
0x140005fb3  call    cs:__imp_CoRegisterClassObject
0x140005fb9  mov     ebx, eax
0x140005fbb  mov     rcx, [rbp+pUnk]
0x140005fbf  test    rcx, rcx
0x140005fc2  jz      short loc_140005FD0
0x140005fc4  mov     rax, [rcx]
0x140005fc7  mov     rax, [rax+10h]
0x140005fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005fd0  add     rdi, 8
0x140005fd4  cmp     rdi, cs:off_14000B108
0x140005fdb  jb      short loc_140005F5E
0x140005fdd  test    ebx, ebx
0x140005fdf  jnz     short loc_14000604F
0x140005fe1  cmp     cs:byte_14000B870, 0
0x140005fe8  jz      short loc_140006056
0x140005fea  xor     r9d, r9d; lpName
0x140005fed  xor     r8d, r8d; bInitialState
0x140005ff0  xor     edx, edx; bManualReset
0x140005ff2  xor     ecx, ecx; lpEventAttributes
0x140005ff4  call    cs:__imp_CreateEventW
0x140005ffa  mov     cs:hObject, rax
0x140006001  test    rax, rax
0x140006004  jz      short loc_140006048
0x140006006  lea     rax, [rbp+ThreadId]
0x14000600a  mov     [rbp+ThreadId], 0
0x140006011  mov     [rsp+60h+lpThreadId], rax; lpThreadId
0x140006016  lea     r9, ?_AtlModule@@3VCcttunesvrModule@@A; lpParameter
0x14000601d  lea     r8, ?MonitorProc@?$CAtlExeModuleT@VCcttunesvrModule@@@ATL@@SAKPEAX@Z; lpStartAddress
0x140006024  mov     dword ptr [rsp+60h+lpdwRegister], 0; dwCreationFlags
0x14000602c  xor     edx, edx; dwStackSize
0x14000602e  xor     ecx, ecx; lpThreadAttributes
0x140006030  call    cs:__imp_CreateThread
0x140006036  test    rax, rax
0x140006039  jnz     short loc_140006056
0x14000603b  mov     rcx, cs:hObject; hObject
0x140006042  call    cs:__imp_CloseHandle
0x140006048  mov     ebx, 80004005h
0x14000604d  jmp     short loc_140006056
0x14000604f  mov     cs:byte_14000B870, 0
0x140006056  test    ebx, ebx
0x140006058  jnz     short loc_140006097
0x14000605a  xorps   xmm0, xmm0
0x14000605d  movups  xmmword ptr [rbp+Msg.hwnd], xmm0
0x140006061  movups  xmmword ptr [rbp+Msg.wParam], xmm0
0x140006065  movups  xmmword ptr [rbp+Msg.time], xmm0
0x140006069  jmp     short loc_14000607F
0x14000606b  lea     rcx, [rbp+Msg]; lpMsg
0x14000606f  call    cs:__imp_TranslateMessage
0x140006075  lea     rcx, [rbp+Msg]; lpMsg
0x140006079  call    cs:__imp_DispatchMessageW
0x14000607f  xor     r9d, r9d; wMsgFilterMax
0x140006082  lea     rcx, [rbp+Msg]; lpMsg
0x140006086  xor     r8d, r8d; wMsgFilterMin
0x140006089  xor     edx, edx; hWnd
0x14000608b  call    cs:__imp_GetMessageW
0x140006091  test    eax, eax
0x140006093  jg      short loc_14000606B
0x140006095  jmp     short loc_140006099
0x140006097  js      short loc_1400060E1
0x140006099  mov     rdi, cs:off_14000B100
0x1400060a0  xor     ebx, ebx
0x1400060a2  jmp     short loc_1400060C3
0x1400060a4  test    ebx, ebx
0x1400060a6  jnz     short loc_1400060CC
0x1400060a8  mov     rax, [rdi]
0x1400060ab  test    rax, rax
0x1400060ae  jz      short loc_1400060BF
0x1400060b0  mov     ecx, [rax+28h]; dwRegister
0x1400060b3  test    ecx, ecx
0x1400060b5  jz      short loc_1400060BF
0x1400060b7  call    cs:__imp_CoRevokeClassObject
0x1400060bd  mov     ebx, eax
0x1400060bf  add     rdi, 8
0x1400060c3  cmp     rdi, cs:off_14000B108
0x1400060ca  jb      short loc_1400060A4
0x1400060cc  cmp     cs:byte_14000B870, 0
0x1400060d3  jz      short loc_1400060E1
0x1400060d5  mov     ecx, cs:dwMilliseconds; dwMilliseconds
0x1400060db  call    cs:__imp_Sleep
0x1400060e1  mov     eax, ebx
0x1400060e3  mov     rbx, [rsp+60h+arg_10]
0x1400060eb  add     rsp, 60h
0x1400060ef  pop     rdi
0x1400060f0  pop     rsi
0x1400060f1  pop     rbp
0x1400060f2  retn
```
