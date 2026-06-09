# CDataIntegrityScanTaskHandler::SystemScanCompleted(long,uchar)

- ea: `0x1800063e0`
- end: `0x18000646a`
- name: `?SystemScanCompleted@CDataIntegrityScanTaskHandler@@UEAAXJE@Z`
- size: `138`
- prototype: `void __fastcall(CDataIntegrityScanTaskHandler *__hidden this, int, unsigned __int8)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800063e0`
- `0x180006820`

## import_xrefs

- `KERNEL32!SubmitThreadpoolWork` at `0x180006463`
- `KERNEL32!GetModuleHandleExW` at `0x180006447`
- `KERNEL32!GetModuleHandleExW` at `0x180006447`

## pseudocode

```c
void __fastcall CDataIntegrityScanTaskHandler::SystemScanCompleted(
        CDataIntegrityScanTaskHandler *this,
        __int64 a2,
        __int64 a3)
{
  char v3; // di
  int v4; // esi

  v3 = a3;
  v4 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_dl(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, (unsigned int)a2, (unsigned __int8)a3);
  }
  *((_BYTE *)this + 400) = v3;
  *((_DWORD *)this + 101) = v4;
  GetModuleHandleExW(4u, (LPCWSTR)CDataIntegrityScanTaskHandler::ScanTaskCompletedCallback, (HMODULE *)this + 51);
  SubmitThreadpoolWork(*((PTP_WORK *)this + 32));
}

```

## disassembly

```asm
0x1800063e0  mov     [rsp+arg_0], rbx
0x1800063e5  mov     [rsp+arg_8], rsi
0x1800063ea  push    rdi
0x1800063eb  sub     rsp, 30h
0x1800063ef  movzx   edi, r8b
0x1800063f3  mov     esi, edx
0x1800063f5  mov     rbx, rcx
0x1800063f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800063ff  lea     rax, WPP_GLOBAL_Control
0x180006406  cmp     rcx, rax
0x180006409  jz      short loc_180006427
0x18000640b  test    byte ptr [rcx+1Ch], 1
0x18000640f  jz      short loc_180006427
0x180006411  cmp     byte ptr [rcx+19h], 4
0x180006415  jb      short loc_180006427
0x180006417  mov     rcx, [rcx+10h]
0x18000641b  mov     r9d, edx
0x18000641e  mov     [rsp+38h+var_18], edi
0x180006422  call    WPP_SF_dl
0x180006427  lea     r8, [rbx+198h]; phModule
0x18000642e  mov     [rbx+190h], dil
0x180006435  lea     rdx, ?ScanTaskCompletedCallback@CDataIntegrityScanTaskHandler@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; lpModuleName
0x18000643c  mov     [rbx+194h], esi
0x180006442  mov     ecx, 4; dwFlags
0x180006447  call    cs:__imp_GetModuleHandleExW
0x18000644d  mov     rcx, [rbx+100h]
0x180006454  mov     rbx, [rsp+38h+arg_0]
0x180006459  mov     rsi, [rsp+38h+arg_8]
0x18000645e  add     rsp, 30h
0x180006462  pop     rdi
0x180006463  jmp     cs:__imp_SubmitThreadpoolWork
```
