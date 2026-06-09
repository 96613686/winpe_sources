# CESEventService::EventingThreadProc(void *)

- ea: `0x18004c560`
- end: `0x18004c71b`
- name: `?EventingThreadProc@CESEventService@@CAKPEAX@Z`
- size: `443`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180006b38`
- `0x18004c050`
- `0x18004c560`
- `0x18004cb6c`
- `0x1800f8010`

## import_xrefs

- `ole32!CoUninitialize` at `0x18004c6ed`
- `ole32!CoUninitialize` at `0x18004c6ed`
- `ole32!CoCreateInstance` at `0x18004c623`
- `ole32!CoCreateInstance` at `0x18004c623`
- `ole32!CoInitializeEx` at `0x18004c5ec`
- `ole32!CoInitializeEx` at `0x18004c5ec`
- `KERNEL32!GetCurrentProcess` at `0x18004c58c`
- `KERNEL32!GetCurrentProcess` at `0x18004c595`
- `KERNEL32!GetCurrentProcess` at `0x18004c58c`
- `KERNEL32!GetCurrentProcess` at `0x18004c595`
- `KERNEL32!DuplicateHandle` at `0x18004c5c0`
- `KERNEL32!DuplicateHandle` at `0x18004c5c0`
- `KERNEL32!GetLastError` at `0x18004c5ca`
- `KERNEL32!GetLastError` at `0x18004c5ca`
- `KERNEL32!CloseHandle` at `0x18004c701`
- `KERNEL32!CloseHandle` at `0x18004c701`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x18004c649`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x18004c649`
- `USER32!PeekMessageW` at `0x18004c676`
- `USER32!PeekMessageW` at `0x18004c676`
- `USER32!DispatchMessageW` at `0x18004c68a`
- `USER32!DispatchMessageW` at `0x18004c68a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
signed int __fastcall CESEventService::EventingThreadProc(LPVOID lpThreadParameter)
{
  signed int result; // eax
  HANDLE CurrentProcess; // rbx
  HANDLE v4; // rax
  DWORD v5; // eax
  CESEventData *lParam; // rbx
  unsigned int v7; // edx
  LPVOID v8; // rcx
  struct tagMSG Msg; // [rsp+40h] [rbp-30h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp+10h] BYREF
  HANDLE TargetHandle; // [rsp+88h] [rbp+18h] BYREF

  if ( !lpThreadParameter )
    return -2147467261;
  TargetHandle = (HANDLE)-1LL;
  CurrentProcess = GetCurrentProcess();
  v4 = GetCurrentProcess();
  if ( DuplicateHandle(v4, lpThreadParameter, CurrentProcess, &TargetHandle, 0, 0, 2u) )
  {
    if ( CoInitializeEx(0, 4u) >= 0 )
    {
      ppv = 0;
      if ( CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv) >= 0 )
      {
        while ( 1 )
        {
          v5 = MsgWaitForMultipleObjectsEx(1u, &TargetHandle, 0xFFFFFFFF, 0x1CFFu, 2u);
          if ( !v5 )
            break;
          if ( v5 == 1 )
          {
            memset(&Msg, 0, sizeof(Msg));
            while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
            {
              if ( Msg.message == 18 )
                goto LABEL_18;
              DispatchMessageW(&Msg);
              if ( Msg.message == 0x8000 && Msg.wParam == 4957 )
              {
                lParam = (CESEventData *)Msg.lParam;
                if ( Msg.lParam )
                {
                  CESEventData::FireESEvents((CESEventData *)Msg.lParam, (struct IGlobalInterfaceTable *)ppv);
                  CESEventData::`scalar deleting destructor'(lParam, v7);
                }
              }
            }
          }
          else if ( v5 == -1 )
          {
            break;
          }
        }
      }
LABEL_18:
      v8 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
      }
      CoUninitialize();
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
    }
    CloseHandle(TargetHandle);
    return 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18004c560  mov     [rsp-8+arg_10], rbx
0x18004c565  mov     [rsp-8+arg_18], rdi
0x18004c56a  push    rbp
0x18004c56b  mov     rbp, rsp
0x18004c56e  sub     rsp, 70h
0x18004c572  mov     rdi, rcx
0x18004c575  test    rcx, rcx
0x18004c578  jnz     short loc_18004C584
0x18004c57a  mov     eax, 80004003h
0x18004c57f  jmp     loc_18004C709
0x18004c584  mov     [rbp+TargetHandle], 0FFFFFFFFFFFFFFFFh
0x18004c58c  call    cs:__imp_GetCurrentProcess
0x18004c592  mov     rbx, rax
0x18004c595  call    cs:__imp_GetCurrentProcess
0x18004c59b  mov     [rsp+70h+dwOptions], 2; dwOptions
0x18004c5a3  mov     [rsp+70h+bInheritHandle], 0; bInheritHandle
0x18004c5ab  mov     [rsp+70h+dwDesiredAccess], 0; dwDesiredAccess
0x18004c5b3  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x18004c5b7  mov     r8, rbx; hTargetProcessHandle
0x18004c5ba  mov     rdx, rdi; hSourceHandle
0x18004c5bd  mov     rcx, rax; hSourceProcessHandle
0x18004c5c0  call    cs:__imp_DuplicateHandle
0x18004c5c6  test    eax, eax
0x18004c5c8  jnz     short loc_18004C5E5
0x18004c5ca  call    cs:__imp_GetLastError
0x18004c5d0  test    eax, eax
0x18004c5d2  jle     loc_18004C709
0x18004c5d8  movzx   eax, ax
0x18004c5db  or      eax, 80070000h
0x18004c5e0  jmp     loc_18004C709
0x18004c5e5  mov     edx, 4; dwCoInit
0x18004c5ea  xor     ecx, ecx; pvReserved
0x18004c5ec  call    cs:__imp_CoInitializeEx
0x18004c5f2  test    eax, eax
0x18004c5f4  js      loc_18004C6FD
0x18004c5fa  mov     [rbp+ppv], 0
0x18004c602  lea     rax, [rbp+ppv]
0x18004c606  mov     qword ptr [rsp+70h+dwDesiredAccess], rax; ppv
0x18004c60b  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18004c612  mov     edi, 1
0x18004c617  mov     r8d, edi; dwClsContext
0x18004c61a  xor     edx, edx; pUnkOuter
0x18004c61c  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18004c623  call    cs:__imp_CoCreateInstance
0x18004c629  test    eax, eax
0x18004c62b  js      loc_18004C6D0
0x18004c631  mov     [rsp+70h+dwDesiredAccess], 2; dwFlags
0x18004c639  mov     r9d, 1CFFh; dwWakeMask
0x18004c63f  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x18004c643  lea     rdx, [rbp+TargetHandle]; pHandles
0x18004c647  mov     ecx, edi; nCount
0x18004c649  call    cs:__imp_MsgWaitForMultipleObjectsEx
0x18004c64f  test    eax, eax
0x18004c651  jz      short loc_18004C6D0
0x18004c653  cmp     eax, edi
0x18004c655  jnz     short loc_18004C6C7
0x18004c657  xorps   xmm0, xmm0
0x18004c65a  movups  xmmword ptr [rbp+Msg.hwnd], xmm0
0x18004c65e  movups  xmmword ptr [rbp+Msg.wParam], xmm0
0x18004c662  movups  xmmword ptr [rbp+Msg.time], xmm0
0x18004c666  mov     [rsp+70h+dwDesiredAccess], edi; wRemoveMsg
0x18004c66a  xor     r9d, r9d; wMsgFilterMax
0x18004c66d  xor     r8d, r8d; wMsgFilterMin
0x18004c670  xor     edx, edx; hWnd
0x18004c672  lea     rcx, [rbp+Msg]; lpMsg
0x18004c676  call    cs:__imp_PeekMessageW
0x18004c67c  test    eax, eax
0x18004c67e  jz      short loc_18004C631
0x18004c680  cmp     [rbp+Msg.message], 12h
0x18004c684  jz      short loc_18004C6D0
0x18004c686  lea     rcx, [rbp+Msg]; lpMsg
0x18004c68a  call    cs:__imp_DispatchMessageW
0x18004c690  cmp     [rbp+Msg.message], 8000h
0x18004c697  jnz     short loc_18004C666
0x18004c699  cmp     [rbp+Msg.wParam], 135Dh
0x18004c6a1  jnz     short loc_18004C666
0x18004c6a3  mov     rbx, [rbp+Msg.lParam]
0x18004c6a7  test    rbx, rbx
0x18004c6aa  jz      short loc_18004C666
0x18004c6ac  mov     rdx, [rbp+ppv]; struct IGlobalInterfaceTable *
0x18004c6b0  mov     rcx, rbx; this
0x18004c6b3  call    ?FireESEvents@CESEventData@@QEAAXPEAUIGlobalInterfaceTable@@@Z; CESEventData::FireESEvents(IGlobalInterfaceTable *)
0x18004c6b8  test    rbx, rbx
0x18004c6bb  jz      short loc_18004C666
0x18004c6bd  mov     rcx, rbx; this
0x18004c6c0  call    ??_GCESEventData@@QEAAPEAXI@Z; CESEventData::`scalar deleting destructor'(uint)
0x18004c6c5  jmp     short loc_18004C666
0x18004c6c7  cmp     eax, 0FFFFFFFFh
0x18004c6ca  jnz     loc_18004C631
0x18004c6d0  mov     rcx, [rbp+ppv]
0x18004c6d4  test    rcx, rcx
0x18004c6d7  jz      short loc_18004C6ED
0x18004c6d9  mov     [rbp+ppv], 0
0x18004c6e1  mov     rax, [rcx]
0x18004c6e4  mov     rax, [rax+10h]
0x18004c6e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c6ed  call    cs:__imp_CoUninitialize
0x18004c6f3  nop
0x18004c6f4  lea     rcx, [rbp+ppv]
0x18004c6f8  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18004c6fd  mov     rcx, [rbp+TargetHandle]; hObject
0x18004c701  call    cs:__imp_CloseHandle
0x18004c707  xor     eax, eax
0x18004c709  lea     r11, [rsp+70h+var_s0]
0x18004c70e  mov     rbx, [r11+20h]
0x18004c712  mov     rdi, [r11+28h]
0x18004c716  mov     rsp, r11
0x18004c719  pop     rbp
0x18004c71a  retn
```
