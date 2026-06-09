# LanConnection::HrEnsureHNetPropertiesCached(void)

- ea: `0x180025734`
- end: `0x180025833`
- name: `?HrEnsureHNetPropertiesCached@LanConnection@@AEAAJXZ`
- size: `255`
- prototype: `__int64 __fastcall(LanConnection *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024978`
- `0x180024db0`
- `0x180025020`

## callees

- `0x180001710`
- `0x180025734`
- `0x18002587c`
- `0x1800306f8`
- `0x180032c3c`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800257e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800257e5`

## pseudocode

```c
__int64 __fastcall LanConnection::HrEnsureHNetPropertiesCached(LanConnection *this)
{
  int v2; // edi
  struct IUnknown *v4; // [rsp+20h] [rbp-28h] BYREF
  LPVOID v5; // [rsp+28h] [rbp-20h] BYREF

  if ( !*((_DWORD *)this + 24) )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( !*((_DWORD *)this + 38) || (v2 = 0, *((_DWORD *)this + 39) != g_lHNetModifiedEra) )
  {
    if ( _InterlockedExchange((volatile __int32 *)this + 40, 1) )
    {
      return 1;
    }
    else
    {
      v4 = 0;
      v5 = 0;
      if ( (int)LanConnection::HrGetIHNetConnection(this, (struct IHNetConnection **)&v4) < 0 )
      {
        v2 = 1;
      }
      else
      {
        v2 = ((__int64 (__fastcall *)(struct IUnknown *, LPVOID *))v4->lpVtbl[2].AddRef)(v4, &v5);
        ReleaseObj(v4);
        if ( v2 >= 0 )
        {
          v5 = (LPVOID)_InterlockedExchange64((volatile __int64 *)this + 21, (__int64)v5);
          CoTaskMemFree(v5);
          v2 = 0;
          _InterlockedExchange((volatile __int32 *)this + 39, g_lHNetModifiedEra);
          *((_DWORD *)this + 38) = 1;
        }
      }
      _InterlockedExchange((volatile __int32 *)this + 40, 0);
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180025734  mov     [rsp+arg_8], rbx
0x180025739  push    rdi
0x18002573a  sub     rsp, 40h
0x18002573e  mov     rax, cs:__security_cookie
0x180025745  xor     rax, rsp
0x180025748  mov     [rsp+48h+var_18], rax
0x18002574d  cmp     dword ptr [rcx+60h], 0
0x180025751  mov     rbx, rcx
0x180025754  jnz     short loc_18002575B
0x180025756  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002575b  cmp     dword ptr [rbx+98h], 0
0x180025762  jz      short loc_180025778
0x180025764  mov     eax, cs:?g_lHNetModifiedEra@@3JA; long g_lHNetModifiedEra
0x18002576a  xor     edi, edi
0x18002576c  cmp     [rbx+9Ch], eax
0x180025772  jz      loc_180025819
0x180025778  mov     eax, 1
0x18002577d  xchg    eax, [rbx+0A0h]
0x180025783  test    eax, eax
0x180025785  jnz     loc_180025814
0x18002578b  lea     rdx, [rsp+48h+var_28]; struct IHNetConnection **
0x180025790  mov     [rsp+48h+var_28], 0
0x180025799  mov     rcx, rbx; this
0x18002579c  mov     [rsp+48h+var_20], 0
0x1800257a5  call    ?HrGetIHNetConnection@LanConnection@@AEAAJPEAPEAUIHNetConnection@@@Z; LanConnection::HrGetIHNetConnection(IHNetConnection * *)
0x1800257aa  test    eax, eax
0x1800257ac  js      short loc_180025805
0x1800257ae  mov     rcx, [rsp+48h+var_28]
0x1800257b3  lea     rdx, [rsp+48h+var_20]
0x1800257b8  mov     rax, [rcx]
0x1800257bb  mov     rax, [rax+38h]
0x1800257bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800257c4  mov     rcx, [rsp+48h+var_28]; struct IUnknown *
0x1800257c9  mov     edi, eax
0x1800257cb  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x1800257d0  test    edi, edi
0x1800257d2  js      short loc_18002580A
0x1800257d4  mov     rcx, [rsp+48h+var_20]
0x1800257d9  xchg    rcx, [rbx+0A8h]; pv
0x1800257e0  mov     [rsp+48h+var_20], rcx
0x1800257e5  call    cs:__imp_CoTaskMemFree
0x1800257eb  mov     eax, cs:?g_lHNetModifiedEra@@3JA; long g_lHNetModifiedEra
0x1800257f1  xor     edi, edi
0x1800257f3  xchg    eax, [rbx+9Ch]
0x1800257f9  mov     dword ptr [rbx+98h], 1
0x180025803  jmp     short loc_18002580A
0x180025805  mov     edi, 1
0x18002580a  xor     eax, eax
0x18002580c  xchg    eax, [rbx+0A0h]
0x180025812  jmp     short loc_180025819
0x180025814  mov     edi, 1
0x180025819  mov     eax, edi
0x18002581b  mov     rcx, [rsp+48h+var_18]
0x180025820  xor     rcx, rsp; StackCookie
0x180025823  call    __security_check_cookie
0x180025828  mov     rbx, [rsp+48h+arg_8]
0x18002582d  add     rsp, 40h
0x180025831  pop     rdi
0x180025832  retn
```
