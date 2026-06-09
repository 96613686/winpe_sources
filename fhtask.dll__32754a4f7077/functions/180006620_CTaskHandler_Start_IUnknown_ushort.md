# CTaskHandler::Start(IUnknown *,ushort *)

- ea: `0x180006620`
- end: `0x1800066b2`
- name: `?Start@CTaskHandler@@UEAAJPEAUIUnknown@@PEAG@Z`
- size: `146`
- prototype: `__int64 __fastcall(CTaskHandler *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180005ea4`
- `0x180005f58`
- `0x180006264`
- `0x180006620`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall CTaskHandler::Start(CTaskHandler *this, struct IUnknown *a2, unsigned __int16 *a3)
{
  struct IUnknown *v6; // [rsp+30h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_c432cab80fa834a8c758b8af3c384ba0_Traceguids);
  v6 = a2;
  if ( a2 )
    ((void (__fastcall *)(struct IUnknown *, struct IUnknown *, unsigned __int16 *))a2->lpVtbl->AddRef)(a2, a2, a3);
  ATL::CComPtr<ITaskHandlerStatus>::operator=<IUnknown>((char *)this + 64, &v6, a3);
  if ( a2 )
    ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->Release)(a2);
  CTaskHandler::InterlockedEnterMaintenanceMode(this);
  return 0;
}

```

## disassembly

```asm
0x180006620  mov     [rsp+arg_8], rbx
0x180006625  push    rdi
0x180006626  sub     rsp, 20h
0x18000662a  mov     rbx, rdx
0x18000662d  mov     rdi, rcx
0x180006630  lea     rax, WPP_GLOBAL_Control
0x180006637  mov     rcx, cs:WPP_GLOBAL_Control
0x18000663e  cmp     rcx, rax
0x180006641  jz      short loc_18000665F
0x180006643  test    byte ptr [rcx+1Ch], 8
0x180006647  jz      short loc_18000665F
0x180006649  mov     edx, 0Dh
0x18000664e  lea     r8, WPP_c432cab80fa834a8c758b8af3c384ba0_Traceguids
0x180006655  mov     rcx, [rcx+10h]
0x180006659  call    WPP_SF_
0x18000665e  nop
0x18000665f  mov     [rsp+28h+arg_0], rbx
0x180006664  test    rbx, rbx
0x180006667  jz      short loc_180006679
0x180006669  mov     rax, [rbx]
0x18000666c  mov     rcx, rbx
0x18000666f  mov     rax, [rax+8]
0x180006673  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006678  nop
0x180006679  lea     rcx, [rdi+40h]
0x18000667d  lea     rdx, [rsp+28h+arg_0]
0x180006682  call    ??$?4UIUnknown@@@?$CComPtr@UITaskHandlerStatus@@@ATL@@QEAAPEAUITaskHandlerStatus@@AEBV?$CComPtr@UIUnknown@@@1@@Z; ATL::CComPtr<ITaskHandlerStatus>::operator=<IUnknown>(ATL::CComPtr<IUnknown> const &)
0x180006687  nop
0x180006688  test    rbx, rbx
0x18000668b  jz      short loc_18000669D
0x18000668d  mov     rax, [rbx]
0x180006690  mov     rcx, rbx
0x180006693  mov     rax, [rax+10h]
0x180006697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000669c  nop
0x18000669d  mov     rcx, rdi; this
0x1800066a0  call    ?InterlockedEnterMaintenanceMode@CTaskHandler@@AEAAXXZ; CTaskHandler::InterlockedEnterMaintenanceMode(void)
0x1800066a5  xor     eax, eax
0x1800066a7  mov     rbx, [rsp+28h+arg_8]
0x1800066ac  add     rsp, 20h
0x1800066b0  pop     rdi
0x1800066b1  retn
```
