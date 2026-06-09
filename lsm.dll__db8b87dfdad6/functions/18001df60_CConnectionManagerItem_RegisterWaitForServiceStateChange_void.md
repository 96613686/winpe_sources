# CConnectionManagerItem::RegisterWaitForServiceStateChange(void)

- ea: `0x18001df60`
- end: `0x18001e087`
- name: `?RegisterWaitForServiceStateChange@CConnectionManagerItem@@QEAAJXZ`
- size: `295`
- prototype: `__int64 __fastcall(CConnectionManagerItem *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18002caf0`

## callees

- `0x1800074c0`
- `0x18001df60`
- `0x18001e3e8`
- `0x18004bf44`
- `0x180063134`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18001e06c`
- `msvcp_win!_Mtx_unlock` at `0x18001e06c`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18001e02d`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18001e02d`

## string_xrefs

- `0x18001dfa1`: `CConnectionManagerItem::RegisterWaitForServiceStateChange`
- `0x18001df95`: `ERROR_SERVICE_DOES_NOT_EXIST failed: 0x%x in %s`
- `0x18001dfda`: `OpenServiceHandle failed: 0x%x in %s`
- `0x18001e04d`: `NotifyServiceStatusChange failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CConnectionManagerItem::RegisterWaitForServiceStateChange(CConnectionManagerItem *this)
{
  struct _Mtx_internal_imp_t *v2; // r14
  unsigned int v3; // edi
  int v4; // eax
  DWORD v5; // edx
  signed int v6; // eax

  v2 = (CConnectionManagerItem *)((char *)this + 72);
  std::_Mutex_base::lock((CConnectionManagerItem *)((char *)this + 72));
  if ( *((_DWORD *)this + 16) == 2 )
  {
    v3 = -2147023836;
    _DbgPrintMessage(
      8,
      "ERROR_SERVICE_DOES_NOT_EXIST failed: 0x%x in %s",
      2147943460LL,
      "CConnectionManagerItem::RegisterWaitForServiceStateChange");
  }
  else
  {
    if ( !*((_DWORD *)this + 62) )
    {
      v3 = 0;
      goto LABEL_17;
    }
    if ( *((_QWORD *)this + 20) )
    {
      v3 = 0;
    }
    else
    {
      v4 = CConnectionManagerItem::OpenServiceHandle(this);
      v3 = v4;
      if ( v4 < 0 )
      {
        _DbgPrintMessage(
          8,
          "OpenServiceHandle failed: 0x%x in %s",
          (unsigned int)v4,
          "CConnectionManagerItem::RegisterWaitForServiceStateChange");
        goto LABEL_17;
      }
    }
    memset_0((char *)this + 168, 0, 0x50u);
    *((_DWORD *)this + 42) = 2;
    *((_QWORD *)this + 22) = CConnectionManagerItem::ServiceStatusChangeCallback;
    *((_QWORD *)this + 23) = this;
    v5 = 1;
    if ( *((_DWORD *)this + 16) != 1 )
      v5 = 8;
    v6 = NotifyServiceStatusChangeW(*((SC_HANDLE *)this + 20), v5, (PSERVICE_NOTIFYW)((char *)this + 168));
    if ( v6 > 0 )
    {
      v3 = (unsigned __int16)v6 | 0x80070000;
    }
    else
    {
      if ( !v6 )
      {
        *((_DWORD *)this + 62) = 0;
        goto LABEL_17;
      }
      v3 = v6;
    }
    _DbgPrintMessage(
      8,
      "NotifyServiceStatusChange failed: 0x%x in %s",
      v3,
      "CConnectionManagerItem::RegisterWaitForServiceStateChange");
  }
LABEL_17:
  _Mtx_unlock(v2);
  return v3;
}

```

## disassembly

```asm
0x18001df60  mov     [rsp+arg_8], rbx
0x18001df65  mov     [rsp+arg_10], rbp
0x18001df6a  push    rsi
0x18001df6b  push    rdi
0x18001df6c  push    r14
0x18001df6e  sub     rsp, 20h
0x18001df72  mov     rsi, rcx
0x18001df75  lea     r14, [rcx+48h]
0x18001df79  mov     [rsp+38h+arg_0], r14
0x18001df7e  mov     rcx, r14; this
0x18001df81  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18001df86  nop
0x18001df87  cmp     dword ptr [rsi+40h], 2
0x18001df8b  jnz     short loc_18001DFB2
0x18001df8d  mov     edi, 80070424h
0x18001df92  mov     r8d, edi
0x18001df95  lea     rdx, aErrorServiceDo; "ERROR_SERVICE_DOES_NOT_EXIST failed: 0x"...
0x18001df9c  mov     ecx, 8; int
0x18001dfa1  lea     r9, aCconnectionman_0; "CConnectionManagerItem::RegisterWaitFor"...
0x18001dfa8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001dfad  jmp     loc_18001E069
0x18001dfb2  cmp     dword ptr [rsi+0F8h], 0
0x18001dfb9  jz      loc_18001E067
0x18001dfbf  cmp     qword ptr [rsi+0A0h], 0
0x18001dfc7  jnz     short loc_18001DFE3
0x18001dfc9  mov     rcx, rsi; this
0x18001dfcc  call    ?OpenServiceHandle@CConnectionManagerItem@@QEAAJXZ; CConnectionManagerItem::OpenServiceHandle(void)
0x18001dfd1  mov     edi, eax
0x18001dfd3  test    eax, eax
0x18001dfd5  jns     short loc_18001DFE5
0x18001dfd7  mov     r8d, eax
0x18001dfda  lea     rdx, aOpenservicehan; "OpenServiceHandle failed: 0x%x in %s"
0x18001dfe1  jmp     short loc_18001DF9C
0x18001dfe3  xor     edi, edi
0x18001dfe5  lea     rbx, [rsi+0A8h]
0x18001dfec  xor     edx, edx; Val
0x18001dfee  lea     r8d, [rdx+50h]; Size
0x18001dff2  mov     rcx, rbx; void *
0x18001dff5  call    memset_0
0x18001dffa  mov     dword ptr [rbx], 2
0x18001e000  lea     rax, ?ServiceStatusChangeCallback@CConnectionManagerItem@@SAXPEAX@Z; CConnectionManagerItem::ServiceStatusChangeCallback(void *)
0x18001e007  mov     [rsi+0B0h], rax
0x18001e00e  mov     [rsi+0B8h], rsi
0x18001e015  mov     edx, 1
0x18001e01a  lea     ebp, [rdx+7]
0x18001e01d  cmp     [rsi+40h], edx
0x18001e020  cmovnz  edx, ebp; dwNotifyMask
0x18001e023  mov     r8, rbx; pNotifyBuffer
0x18001e026  mov     rcx, [rsi+0A0h]; hService
0x18001e02d  call    cs:__imp_NotifyServiceStatusChangeW
0x18001e033  test    eax, eax
0x18001e035  jg      short loc_18001E03D
0x18001e037  jz      short loc_18001E05B
0x18001e039  mov     edi, eax
0x18001e03b  jmp     short loc_18001E046
0x18001e03d  movzx   edi, ax
0x18001e040  or      edi, 80070000h
0x18001e046  test    edi, edi
0x18001e048  jns     short loc_18001E069
0x18001e04a  mov     r8d, edi
0x18001e04d  lea     rdx, aNotifyservices_0; "NotifyServiceStatusChange failed: 0x%x "...
0x18001e054  mov     ecx, ebp
0x18001e056  jmp     loc_18001DFA1
0x18001e05b  mov     dword ptr [rsi+0F8h], 0
0x18001e065  jmp     short loc_18001E069
0x18001e067  xor     edi, edi
0x18001e069  mov     rcx, r14; _Mtx_t
0x18001e06c  call    cs:__imp__Mtx_unlock
0x18001e072  mov     eax, edi
0x18001e074  mov     rbx, [rsp+38h+arg_8]
0x18001e079  mov     rbp, [rsp+38h+arg_10]
0x18001e07e  add     rsp, 20h
0x18001e082  pop     r14
0x18001e084  pop     rdi
0x18001e085  pop     rsi
0x18001e086  retn
```
