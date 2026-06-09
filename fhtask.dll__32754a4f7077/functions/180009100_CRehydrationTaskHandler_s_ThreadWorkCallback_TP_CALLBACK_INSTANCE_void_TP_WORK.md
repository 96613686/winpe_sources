# CRehydrationTaskHandler::s_ThreadWorkCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180009100`
- end: `0x1800091fa`
- name: `?s_ThreadWorkCallback@CRehydrationTaskHandler@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `250`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, HANDLE *Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callees

- `0x180005ea4`
- `0x1800067a0`
- `0x180007ba0`
- `0x180009100`
- `0x180009308`
- `0x180009340`
- `0x18000b010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1800091cb`
- `KERNEL32!SetEvent` at `0x1800091cb`
- `ole32!CoInitializeEx` at `0x18000914c`
- `ole32!CoInitializeEx` at `0x18000914c`
- `ole32!CoUninitialize` at `0x1800091bc`
- `ole32!CoUninitialize` at `0x1800091bc`

## pseudocode

```c
void __fastcall CRehydrationTaskHandler::s_ThreadWorkCallback(
        PTP_CALLBACK_INSTANCE Instance,
        HANDLE *Context,
        PTP_WORK Work)
{
  void *v4; // rcx
  HRESULT v5; // eax
  unsigned int v6; // ebx
  int v7; // eax

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_8158daeccbd13eff1bb477c819869c69_Traceguids);
  McGenEventRegister_EventRegister(v4, Context, Work);
  v5 = CoInitializeEx(0, 2u);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v7 = PerformRehydration((struct CRehydrationTaskHandler *)Context);
    v6 = v7;
    if ( v7 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        66,
        &WPP_8158daeccbd13eff1bb477c819869c69_Traceguids,
        (unsigned int)v7);
    }
    CoUninitialize();
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      65,
      &WPP_8158daeccbd13eff1bb477c819869c69_Traceguids,
      (unsigned int)v5);
  }
  McGenEventUnregister_EventUnregister();
  SetEvent(Context[10]);
  if ( !*((_BYTE *)Context + 88) )
    (*(void (__fastcall **)(HANDLE, _QWORD))(*(_QWORD *)Context[8] + 32LL))(Context[8], v6);
}

```

## disassembly

```asm
0x180009100  mov     [rsp+arg_0], rbx
0x180009105  mov     [rsp+arg_8], rsi
0x18000910a  push    rdi
0x18000910b  sub     rsp, 20h
0x18000910f  mov     rdi, rdx
0x180009112  lea     rsi, WPP_GLOBAL_Control
0x180009119  mov     rcx, cs:WPP_GLOBAL_Control
0x180009120  cmp     rcx, rsi
0x180009123  jz      short loc_180009140
0x180009125  test    byte ptr [rcx+1Ch], 8
0x180009129  jz      short loc_180009140
0x18000912b  mov     edx, 40h ; '@'
0x180009130  lea     r8, WPP_8158daeccbd13eff1bb477c819869c69_Traceguids
0x180009137  mov     rcx, [rcx+10h]
0x18000913b  call    WPP_SF_
0x180009140  call    McGenEventRegister_EventRegister
0x180009145  mov     edx, 2; dwCoInit
0x18000914a  xor     ecx, ecx; pvReserved
0x18000914c  call    cs:__imp_CoInitializeEx
0x180009152  mov     ebx, eax
0x180009154  test    eax, eax
0x180009156  jns     short loc_180009184
0x180009158  mov     rcx, cs:WPP_GLOBAL_Control
0x18000915f  cmp     rcx, rsi
0x180009162  jz      short loc_1800091C2
0x180009164  test    byte ptr [rcx+1Ch], 1
0x180009168  jz      short loc_1800091C2
0x18000916a  mov     edx, 41h ; 'A'
0x18000916f  mov     r9d, eax
0x180009172  lea     r8, WPP_8158daeccbd13eff1bb477c819869c69_Traceguids
0x180009179  mov     rcx, [rcx+10h]
0x18000917d  call    WPP_SF_d
0x180009182  jmp     short loc_1800091C2
0x180009184  mov     rcx, rdi; struct CRehydrationTaskHandler *
0x180009187  call    ?PerformRehydration@@YAJPEAVCRehydrationTaskHandler@@@Z; PerformRehydration(CRehydrationTaskHandler *)
0x18000918c  mov     ebx, eax
0x18000918e  test    eax, eax
0x180009190  jns     short loc_1800091BC
0x180009192  mov     rcx, cs:WPP_GLOBAL_Control
0x180009199  cmp     rcx, rsi
0x18000919c  jz      short loc_1800091BC
0x18000919e  test    byte ptr [rcx+1Ch], 1
0x1800091a2  jz      short loc_1800091BC
0x1800091a4  mov     edx, 42h ; 'B'
0x1800091a9  mov     r9d, eax
0x1800091ac  lea     r8, WPP_8158daeccbd13eff1bb477c819869c69_Traceguids
0x1800091b3  mov     rcx, [rcx+10h]
0x1800091b7  call    WPP_SF_d
0x1800091bc  call    cs:__imp_CoUninitialize
0x1800091c2  call    McGenEventUnregister_EventUnregister
0x1800091c7  mov     rcx, [rdi+50h]; hEvent
0x1800091cb  call    cs:__imp_SetEvent
0x1800091d1  cmp     byte ptr [rdi+58h], 0
0x1800091d5  jnz     short loc_1800091EA
0x1800091d7  mov     rcx, [rdi+40h]
0x1800091db  mov     rax, [rcx]
0x1800091de  mov     edx, ebx
0x1800091e0  mov     rax, [rax+20h]
0x1800091e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091e9  nop
0x1800091ea  mov     rbx, [rsp+28h+arg_0]
0x1800091ef  mov     rsi, [rsp+28h+arg_8]
0x1800091f4  add     rsp, 20h
0x1800091f8  pop     rdi
0x1800091f9  retn
```
