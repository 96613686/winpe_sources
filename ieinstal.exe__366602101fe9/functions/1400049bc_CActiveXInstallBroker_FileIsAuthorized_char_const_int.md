# CActiveXInstallBroker::FileIsAuthorized(char const *,int)

- ea: `0x1400049bc`
- end: `0x140004a10`
- name: `?FileIsAuthorized@CActiveXInstallBroker@@AEAAJPEBDH@Z`
- size: `84`
- prototype: `__int64 __fastcall(CActiveXInstallBroker *__hidden this, const char *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140004738`
- `0x1400048c0`

## callees

- `0x1400049bc`
- `0x140004a18`
- `0x14000b150`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1400049f6`
- `ole32!CoTaskMemFree` at `0x1400049f6`

## pseudocode

```c
__int64 __fastcall CActiveXInstallBroker::FileIsAuthorized(CActiveXInstallBroker *this, const char *a2)
{
  int IsAuthorized; // ebx
  LPVOID pv; // [rsp+48h] [rbp+20h] BYREF

  pv = 0;
  IsAuthorized = SZtoWSZ((__int64)this, a2, (unsigned __int16 **)&pv);
  if ( IsAuthorized >= 0 )
  {
    IsAuthorized = CActiveXInstallBroker::FileIsAuthorized(this, (const unsigned __int16 *)pv);
    CoTaskMemFree(pv);
  }
  return (unsigned int)IsAuthorized;
}

```

## disassembly

```asm
0x1400049bc  mov     [rsp+arg_0], rbx
0x1400049c1  push    rdi
0x1400049c2  sub     rsp, 20h
0x1400049c6  lea     r8, [rsp+28h+pv]; unsigned __int16 **
0x1400049cb  mov     [rsp+28h+pv], 0
0x1400049d4  mov     rdi, rcx
0x1400049d7  call    ?SZtoWSZ@@YAJIPEBDPEAPEAG@Z; SZtoWSZ(uint,char const *,ushort * *)
0x1400049dc  mov     ebx, eax
0x1400049de  test    eax, eax
0x1400049e0  js      short loc_140004A02
0x1400049e2  mov     rdx, [rsp+28h+pv]; unsigned __int16 *
0x1400049e7  mov     rcx, rdi; this
0x1400049ea  call    ?FileIsAuthorized@CActiveXInstallBroker@@AEAAJPEBGH@Z; CActiveXInstallBroker::FileIsAuthorized(ushort const *,int)
0x1400049ef  mov     rcx, [rsp+28h+pv]; pv
0x1400049f4  mov     ebx, eax
0x1400049f6  call    cs:__imp_CoTaskMemFree
0x1400049fd  nop     dword ptr [rax+rax+00h]
0x140004a02  mov     eax, ebx
0x140004a04  mov     rbx, [rsp+28h+arg_0]
0x140004a09  add     rsp, 20h
0x140004a0d  pop     rdi
0x140004a0e  retn
```
