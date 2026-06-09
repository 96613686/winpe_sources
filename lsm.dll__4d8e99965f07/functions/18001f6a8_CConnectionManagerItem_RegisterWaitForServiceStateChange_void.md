# CConnectionManagerItem::RegisterWaitForServiceStateChange(void)

- ea: `0x18001f6a8`
- end: `0x18001f7dc`
- name: `?RegisterWaitForServiceStateChange@CConnectionManagerItem@@QEAAJXZ`
- size: `308`
- prototype: `__int64 __fastcall(CConnectionManagerItem *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18002e710`

## callees

- `0x1800077a0`
- `0x18001f6a8`
- `0x18001fb7c`
- `0x18004f354`
- `0x180066ce4`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18001f7ba`
- `msvcp_win!_Mtx_unlock` at `0x18001f7ba`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18001f775`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18001f775`

## string_xrefs

- `0x18001f6e9`: `CConnectionManagerItem::RegisterWaitForServiceStateChange`
- `0x18001f6dd`: `ERROR_SERVICE_DOES_NOT_EXIST failed: 0x%x in %s`
- `0x18001f722`: `OpenServiceHandle failed: 0x%x in %s`
- `0x18001f79b`: `NotifyServiceStatusChange failed: 0x%x in %s`

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
0x18001f6a8  mov     [rsp+arg_8], rbx
0x18001f6ad  mov     [rsp+arg_10], rbp
0x18001f6b2  push    rsi
0x18001f6b3  push    rdi
0x18001f6b4  push    r14
0x18001f6b6  sub     rsp, 20h
0x18001f6ba  mov     rsi, rcx
0x18001f6bd  lea     r14, [rcx+48h]
0x18001f6c1  mov     [rsp+38h+arg_0], r14
0x18001f6c6  mov     rcx, r14; this
0x18001f6c9  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18001f6ce  nop
0x18001f6cf  cmp     dword ptr [rsi+40h], 2
0x18001f6d3  jnz     short loc_18001F6FA
0x18001f6d5  mov     edi, 80070424h
0x18001f6da  mov     r8d, edi
0x18001f6dd  lea     rdx, aErrorServiceDo; "ERROR_SERVICE_DOES_NOT_EXIST failed: 0x"...
0x18001f6e4  mov     ecx, 8; int
0x18001f6e9  lea     r9, aCconnectionman_0; "CConnectionManagerItem::RegisterWaitFor"...
0x18001f6f0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001f6f5  jmp     loc_18001F7B7
0x18001f6fa  cmp     dword ptr [rsi+0F8h], 0
0x18001f701  jz      loc_18001F7B5
0x18001f707  cmp     qword ptr [rsi+0A0h], 0
0x18001f70f  jnz     short loc_18001F72B
0x18001f711  mov     rcx, rsi; this
0x18001f714  call    ?OpenServiceHandle@CConnectionManagerItem@@QEAAJXZ; CConnectionManagerItem::OpenServiceHandle(void)
0x18001f719  mov     edi, eax
0x18001f71b  test    eax, eax
0x18001f71d  jns     short loc_18001F72D
0x18001f71f  mov     r8d, eax
0x18001f722  lea     rdx, aOpenservicehan; "OpenServiceHandle failed: 0x%x in %s"
0x18001f729  jmp     short loc_18001F6E4
0x18001f72b  xor     edi, edi
0x18001f72d  lea     rbx, [rsi+0A8h]
0x18001f734  xor     edx, edx; Val
0x18001f736  lea     r8d, [rdx+50h]; Size
0x18001f73a  mov     rcx, rbx; void *
0x18001f73d  call    memset_0
0x18001f742  mov     dword ptr [rbx], 2
0x18001f748  lea     rax, ?ServiceStatusChangeCallback@CConnectionManagerItem@@SAXPEAX@Z; CConnectionManagerItem::ServiceStatusChangeCallback(void *)
0x18001f74f  mov     [rsi+0B0h], rax
0x18001f756  mov     [rsi+0B8h], rsi
0x18001f75d  mov     edx, 1
0x18001f762  lea     ebp, [rdx+7]
0x18001f765  cmp     [rsi+40h], edx
0x18001f768  cmovnz  edx, ebp; dwNotifyMask
0x18001f76b  mov     r8, rbx; pNotifyBuffer
0x18001f76e  mov     rcx, [rsi+0A0h]; hService
0x18001f775  call    cs:__imp_NotifyServiceStatusChangeW
0x18001f77c  nop     dword ptr [rax+rax+00h]
0x18001f781  test    eax, eax
0x18001f783  jg      short loc_18001F78B
0x18001f785  jz      short loc_18001F7A9
0x18001f787  mov     edi, eax
0x18001f789  jmp     short loc_18001F794
0x18001f78b  movzx   edi, ax
0x18001f78e  or      edi, 80070000h
0x18001f794  test    edi, edi
0x18001f796  jns     short loc_18001F7B7
0x18001f798  mov     r8d, edi
0x18001f79b  lea     rdx, aNotifyservices_0; "NotifyServiceStatusChange failed: 0x%x "...
0x18001f7a2  mov     ecx, ebp
0x18001f7a4  jmp     loc_18001F6E9
0x18001f7a9  mov     dword ptr [rsi+0F8h], 0
0x18001f7b3  jmp     short loc_18001F7B7
0x18001f7b5  xor     edi, edi
0x18001f7b7  mov     rcx, r14; _Mtx_t
0x18001f7ba  call    cs:__imp__Mtx_unlock
0x18001f7c1  nop     dword ptr [rax+rax+00h]
0x18001f7c6  mov     eax, edi
0x18001f7c8  mov     rbx, [rsp+38h+arg_8]
0x18001f7cd  mov     rbp, [rsp+38h+arg_10]
0x18001f7d2  add     rsp, 20h
0x18001f7d6  pop     r14
0x18001f7d8  pop     rdi
0x18001f7d9  pop     rsi
0x18001f7da  retn
```
