# CSetupAPINetDevice::GetInterfaceID(_GUID *)

- ea: `0x18002a920`
- end: `0x18002a9a5`
- name: `?GetInterfaceID@CSetupAPINetDevice@@QEAAJPEAU_GUID@@@Z`
- size: `133`
- prototype: `__int64 __fastcall(CSetupAPINetDevice *this, struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18002a9ac`

## callees

- `0x18002a920`
- `0x18002ac38`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a992`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a992`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002a971`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002a971`

## pseudocode

```c
__int64 __fastcall CSetupAPINetDevice::GetInterfaceID(CSetupAPINetDevice *this, struct _GUID *a2)
{
  signed int RegPropertyWithAlloc; // ebx
  HRESULT v4; // eax
  LPCOLESTR lpsz; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v7; // [rsp+60h] [rbp+18h] BYREF
  unsigned int v8; // [rsp+68h] [rbp+20h] BYREF

  lpsz = 0;
  v8 = 0;
  v7 = 0;
  RegPropertyWithAlloc = CSetupAPIDevice::GetRegPropertyWithAlloc(
                           this,
                           (const unsigned __int16 *)a2,
                           &v8,
                           (unsigned __int8 **)&lpsz,
                           &v7);
  if ( RegPropertyWithAlloc >= 0 )
  {
    if ( v7 < 2 )
    {
      RegPropertyWithAlloc = -2147418113;
    }
    else
    {
      v4 = CLSIDFromString(lpsz, a2);
      RegPropertyWithAlloc = v4;
      if ( v4 > 0 )
        RegPropertyWithAlloc = (unsigned __int16)v4 | 0x80070000;
    }
    CoTaskMemFree((LPVOID)lpsz);
  }
  return (unsigned int)RegPropertyWithAlloc;
}

```

## disassembly

```asm
0x18002a920  mov     r11, rsp
0x18002a923  mov     [r11+8], rbx
0x18002a927  push    rdi
0x18002a928  sub     rsp, 40h
0x18002a92c  lea     rax, [r11+18h]
0x18002a930  mov     qword ptr [r11-18h], 0
0x18002a938  lea     r9, [r11-18h]; unsigned __int8 **
0x18002a93c  mov     [r11-28h], rax
0x18002a940  lea     r8, [r11+20h]; unsigned int *
0x18002a944  mov     [rsp+48h+arg_18], 0
0x18002a94c  mov     rdi, rdx
0x18002a94f  mov     [rsp+48h+arg_10], 0
0x18002a957  call    ?GetRegPropertyWithAlloc@CSetupAPIDevice@@QEAAJPEBGPEAKPEAPEAE1@Z; CSetupAPIDevice::GetRegPropertyWithAlloc(ushort const *,ulong *,uchar * *,ulong *)
0x18002a95c  mov     ebx, eax
0x18002a95e  test    eax, eax
0x18002a960  js      short loc_18002A998
0x18002a962  cmp     [rsp+48h+arg_10], 2
0x18002a967  jb      short loc_18002A988
0x18002a969  mov     rcx, [rsp+48h+lpsz]; lpsz
0x18002a96e  mov     rdx, rdi; pclsid
0x18002a971  call    cs:__imp_CLSIDFromString
0x18002a977  mov     ebx, eax
0x18002a979  test    eax, eax
0x18002a97b  jle     short loc_18002A98D
0x18002a97d  movzx   ebx, ax
0x18002a980  or      ebx, 80070000h
0x18002a986  jmp     short loc_18002A98D
0x18002a988  mov     ebx, 8000FFFFh
0x18002a98d  mov     rcx, [rsp+48h+lpsz]; pv
0x18002a992  call    cs:__imp_CoTaskMemFree
0x18002a998  mov     eax, ebx
0x18002a99a  mov     rbx, [rsp+48h+arg_0]
0x18002a99f  add     rsp, 40h
0x18002a9a3  pop     rdi
0x18002a9a4  retn
```
