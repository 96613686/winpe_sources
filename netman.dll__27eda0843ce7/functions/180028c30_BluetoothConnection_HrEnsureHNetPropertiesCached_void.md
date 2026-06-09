# BluetoothConnection::HrEnsureHNetPropertiesCached(void)

- ea: `0x180028c30`
- end: `0x180028d2f`
- name: `?HrEnsureHNetPropertiesCached@BluetoothConnection@@AEAAJXZ`
- size: `255`
- prototype: `__int64 __fastcall(BluetoothConnection *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180028250`

## callees

- `0x180001710`
- `0x180028c30`
- `0x180029078`
- `0x1800306f8`
- `0x180032c3c`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028ce1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028ce1`

## pseudocode

```c
__int64 __fastcall BluetoothConnection::HrEnsureHNetPropertiesCached(BluetoothConnection *this)
{
  unsigned int v2; // ecx
  int v3; // ebx
  struct IUnknown *v5; // [rsp+20h] [rbp-28h] BYREF
  LPVOID v6; // [rsp+28h] [rbp-20h] BYREF

  if ( *((_DWORD *)this + 26) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( !*((_DWORD *)this + 44) || (v2 = 0, *((_DWORD *)this + 45) != g_lHNetModifiedEra) )
  {
    if ( _InterlockedExchange((volatile __int32 *)this + 46, 1) )
    {
      return 1;
    }
    else
    {
      v5 = 0;
      v6 = 0;
      if ( (int)BluetoothConnection::HrGetIHNetConnection(this, (struct IHNetConnection **)&v5) < 0
        || (v3 = ((__int64 (__fastcall *)(struct IUnknown *, LPVOID *))v5->lpVtbl[2].AddRef)(v5, &v6),
            ReleaseObj(v5),
            v3 < 0) )
      {
        v2 = 1;
      }
      else
      {
        v6 = (LPVOID)_InterlockedExchange64((volatile __int64 *)this + 24, (__int64)v6);
        CoTaskMemFree(v6);
        v2 = 0;
        _InterlockedExchange((volatile __int32 *)this + 45, g_lHNetModifiedEra);
        *((_DWORD *)this + 44) = 1;
      }
      _InterlockedExchange((volatile __int32 *)this + 46, 0);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180028c30  mov     [rsp+arg_8], rbx
0x180028c35  push    rdi
0x180028c36  sub     rsp, 40h
0x180028c3a  mov     rax, cs:__security_cookie
0x180028c41  xor     rax, rsp
0x180028c44  mov     [rsp+48h+var_18], rax
0x180028c49  cmp     dword ptr [rcx+68h], 1
0x180028c4d  mov     rdi, rcx
0x180028c50  jz      short loc_180028C57
0x180028c52  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180028c57  cmp     dword ptr [rdi+0B0h], 0
0x180028c5e  jz      short loc_180028C74
0x180028c60  mov     eax, cs:?g_lHNetModifiedEra@@3JA; long g_lHNetModifiedEra
0x180028c66  xor     ecx, ecx
0x180028c68  cmp     [rdi+0B4h], eax
0x180028c6e  jz      loc_180028D15
0x180028c74  mov     eax, 1
0x180028c79  xchg    eax, [rdi+0B8h]
0x180028c7f  test    eax, eax
0x180028c81  jnz     loc_180028D10
0x180028c87  lea     rdx, [rsp+48h+var_28]; struct IHNetConnection **
0x180028c8c  mov     [rsp+48h+var_28], 0
0x180028c95  mov     rcx, rdi; this
0x180028c98  mov     [rsp+48h+var_20], 0
0x180028ca1  call    ?HrGetIHNetConnection@BluetoothConnection@@AEAAJPEAPEAUIHNetConnection@@@Z; BluetoothConnection::HrGetIHNetConnection(IHNetConnection * *)
0x180028ca6  test    eax, eax
0x180028ca8  js      short loc_180028D01
0x180028caa  mov     rcx, [rsp+48h+var_28]
0x180028caf  lea     rdx, [rsp+48h+var_20]
0x180028cb4  mov     rax, [rcx]
0x180028cb7  mov     rax, [rax+38h]
0x180028cbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028cc0  mov     rcx, [rsp+48h+var_28]; struct IUnknown *
0x180028cc5  mov     ebx, eax
0x180028cc7  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x180028ccc  test    ebx, ebx
0x180028cce  js      short loc_180028D01
0x180028cd0  mov     rcx, [rsp+48h+var_20]
0x180028cd5  xchg    rcx, [rdi+0C0h]; pv
0x180028cdc  mov     [rsp+48h+var_20], rcx
0x180028ce1  call    cs:__imp_CoTaskMemFree
0x180028ce7  mov     eax, cs:?g_lHNetModifiedEra@@3JA; long g_lHNetModifiedEra
0x180028ced  xor     ecx, ecx
0x180028cef  xchg    eax, [rdi+0B4h]
0x180028cf5  mov     dword ptr [rdi+0B0h], 1
0x180028cff  jmp     short loc_180028D06
0x180028d01  mov     ecx, 1
0x180028d06  xor     eax, eax
0x180028d08  xchg    eax, [rdi+0B8h]
0x180028d0e  jmp     short loc_180028D15
0x180028d10  mov     ecx, 1
0x180028d15  mov     eax, ecx
0x180028d17  mov     rcx, [rsp+48h+var_18]
0x180028d1c  xor     rcx, rsp; StackCookie
0x180028d1f  call    __security_check_cookie
0x180028d24  mov     rbx, [rsp+48h+arg_8]
0x180028d29  add     rsp, 40h
0x180028d2d  pop     rdi
0x180028d2e  retn
```
