# BluetoothConnection::GetBTDeviceConfig(tagBTPAN_DEVICE_ROLE *,ushort * *,ushort * *)

- ea: `0x180027ec0`
- end: `0x18002806c`
- name: `?GetBTDeviceConfig@BluetoothConnection@@UEAAJPEAW4tagBTPAN_DEVICE_ROLE@@PEAPEAG1@Z`
- size: `428`
- prototype: `__int64 __fastcall(BluetoothConnection *__hidden this, enum tagBTPAN_DEVICE_ROLE *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001710`
- `0x180004c00`
- `0x180027ec0`
- `0x180033184`
- `0x18003385c`
- `0x180033c88`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027fc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027fd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027fc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027fd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028017`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002802c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028017`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002802c`

## pseudocode

```c
__int64 __fastcall BluetoothConnection::GetBTDeviceConfig(
        BluetoothConnection *this,
        enum tagBTPAN_DEVICE_ROLE *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  int v7; // r15d
  signed int BTDeviceConfig; // ebx
  bool v9; // zf
  __int64 v10; // rax
  __int64 v11; // rcx
  unsigned __int64 v12; // r14
  unsigned __int64 v13; // r12
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rcx
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh] BYREF
  __int64 v19; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int16 v20[56]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v21[200]; // [rsp+A0h] [rbp-60h] BYREF

  v7 = 0;
  v17 = 0;
  if ( *((_DWORD *)this + 18) )
  {
    if ( a2 && a3 && a4 )
    {
      *a3 = 0;
      *a4 = 0;
      v18 = 1;
      v19 = 0;
      BTDeviceConfig = OpenBluetoothDevices(&v19, &v18);
      if ( !BTDeviceConfig )
      {
        BTDeviceConfig = IniGetBTDeviceConfig(v19, &v17, v20, v21);
        CloseBluetoothDevice(v19);
        v7 = v17;
      }
      v9 = BTDeviceConfig == 0;
      if ( BTDeviceConfig > 0 )
      {
        BTDeviceConfig = (unsigned __int16)BTDeviceConfig | 0x80070000;
        v9 = BTDeviceConfig == 0;
      }
      if ( v9 )
      {
        v10 = -1;
        v11 = -1;
        do
          ++v11;
        while ( v20[v11] );
        v12 = v11 + 1;
        do
          ++v10;
        while ( v21[v10] );
        v13 = v10 + 1;
        *a3 = (unsigned __int16 *)CoTaskMemAlloc(2 * v12);
        v14 = (unsigned __int16 *)CoTaskMemAlloc(2 * v13);
        *a4 = v14;
        v15 = *a3;
        if ( *a3 && v14 )
        {
          *(_DWORD *)a2 = v7;
          StringCchCopyW(*a3, v12, v20);
          StringCchCopyW(*a4, v13, v21);
        }
        else
        {
          BTDeviceConfig = -2147024882;
          if ( v15 )
          {
            CoTaskMemFree(v15);
            *a3 = 0;
          }
          if ( *a4 )
          {
            CoTaskMemFree(*a4);
            *a4 = 0;
          }
        }
      }
    }
    else
    {
      return (unsigned int)-2147467261;
    }
  }
  else
  {
    return (unsigned int)-2147418113;
  }
  return (unsigned int)BTDeviceConfig;
}

```

## disassembly

```asm
0x180027ec0  mov     [rsp-8+arg_0], rbx
0x180027ec5  push    rbp
0x180027ec6  push    rsi
0x180027ec7  push    rdi
0x180027ec8  push    r12
0x180027eca  push    r13
0x180027ecc  push    r14
0x180027ece  push    r15
0x180027ed0  lea     rbp, [rsp-140h]
0x180027ed8  sub     rsp, 240h
0x180027edf  mov     rax, cs:__security_cookie
0x180027ee6  xor     rax, rsp
0x180027ee9  mov     [rbp+170h+var_40], rax
0x180027ef0  xor     r12d, r12d
0x180027ef3  mov     rdi, r9
0x180027ef6  mov     rsi, r8
0x180027ef9  mov     r13, rdx
0x180027efc  mov     r15d, r12d
0x180027eff  mov     [rsp+270h+var_250], r12d
0x180027f04  cmp     [rcx+48h], r12d
0x180027f08  jnz     short loc_180027F14
0x180027f0a  mov     ebx, 8000FFFFh
0x180027f0f  jmp     loc_180028040
0x180027f14  test    r13, r13
0x180027f17  jz      loc_18002803B
0x180027f1d  test    rsi, rsi
0x180027f20  jz      loc_18002803B
0x180027f26  test    rdi, rdi
0x180027f29  jz      loc_18002803B
0x180027f2f  mov     [r8], r12
0x180027f32  lea     rdx, [rsp+270h+var_24C]
0x180027f37  lea     rcx, [rsp+270h+var_248]
0x180027f3c  mov     [r9], r12
0x180027f3f  mov     [rsp+270h+var_24C], 1
0x180027f47  mov     [rsp+270h+var_248], r12
0x180027f4c  call    OpenBluetoothDevices
0x180027f51  mov     ebx, eax
0x180027f53  test    eax, eax
0x180027f55  jnz     short loc_180027F80
0x180027f57  mov     rcx, [rsp+270h+var_248]
0x180027f5c  lea     r9, [rbp+170h+var_1D0]
0x180027f60  lea     r8, [rsp+270h+var_240]
0x180027f65  lea     rdx, [rsp+270h+var_250]
0x180027f6a  call    IniGetBTDeviceConfig
0x180027f6f  mov     rcx, [rsp+270h+var_248]
0x180027f74  mov     ebx, eax
0x180027f76  call    CloseBluetoothDevice
0x180027f7b  mov     r15d, [rsp+270h+var_250]
0x180027f80  test    ebx, ebx
0x180027f82  jle     short loc_180027F8F
0x180027f84  movzx   ebx, bx
0x180027f87  or      ebx, 80070000h
0x180027f8d  test    ebx, ebx
0x180027f8f  jnz     loc_180028040
0x180027f95  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027f99  lea     rdx, [rsp+270h+var_240]
0x180027f9e  mov     rcx, rax
0x180027fa1  inc     rcx
0x180027fa4  cmp     [rdx+rcx*2], r12w
0x180027fa9  jnz     short loc_180027FA1
0x180027fab  lea     r14, [rcx+1]
0x180027faf  lea     rcx, [rbp+170h+var_1D0]
0x180027fb3  inc     rax
0x180027fb6  cmp     [rcx+rax*2], r12w
0x180027fbb  jnz     short loc_180027FB3
0x180027fbd  lea     rcx, [r14+r14]; cb
0x180027fc1  lea     r12, [rax+1]
0x180027fc5  call    cs:__imp_CoTaskMemAlloc
0x180027fcb  lea     rcx, [r12+r12]; cb
0x180027fcf  mov     [rsi], rax
0x180027fd2  call    cs:__imp_CoTaskMemAlloc
0x180027fd8  mov     [rdi], rax
0x180027fdb  mov     rcx, [rsi]; pv
0x180027fde  test    rcx, rcx
0x180027fe1  jz      short loc_18002800D
0x180027fe3  test    rax, rax
0x180027fe6  jz      short loc_18002800D
0x180027fe8  mov     [r13+0], r15d
0x180027fec  lea     r8, [rsp+270h+var_240]; unsigned __int16 *
0x180027ff1  mov     rcx, [rsi]; unsigned __int16 *
0x180027ff4  mov     rdx, r14; unsigned __int64
0x180027ff7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180027ffc  mov     rcx, [rdi]; unsigned __int16 *
0x180027fff  lea     r8, [rbp+170h+var_1D0]; unsigned __int16 *
0x180028003  mov     rdx, r12; unsigned __int64
0x180028006  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002800b  jmp     short loc_180028040
0x18002800d  mov     ebx, 8007000Eh
0x180028012  test    rcx, rcx
0x180028015  jz      short loc_180028024
0x180028017  call    cs:__imp_CoTaskMemFree
0x18002801d  mov     qword ptr [rsi], 0
0x180028024  mov     rcx, [rdi]; pv
0x180028027  test    rcx, rcx
0x18002802a  jz      short loc_180028040
0x18002802c  call    cs:__imp_CoTaskMemFree
0x180028032  mov     qword ptr [rdi], 0
0x180028039  jmp     short loc_180028040
0x18002803b  mov     ebx, 80004003h
0x180028040  mov     eax, ebx
0x180028042  mov     rcx, [rbp+170h+var_40]
0x180028049  xor     rcx, rsp; StackCookie
0x18002804c  call    __security_check_cookie
0x180028051  mov     rbx, [rsp+270h+arg_0]
0x180028059  add     rsp, 240h
0x180028060  pop     r15
0x180028062  pop     r14
0x180028064  pop     r13
0x180028066  pop     r12
0x180028068  pop     rdi
0x180028069  pop     rsi
0x18002806a  pop     rbp
0x18002806b  retn
```
