# NGENService::SetServiceStartType(ulong)

- ea: `0x18001ac30`
- end: `0x18001aca8`
- name: `?SetServiceStartType@NGENService@@YAJK@Z`
- size: `120`
- prototype: `__int64 __fastcall(NGENService *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18001b038`
- `0x18001b340`

## callees

- `0x1800077d0`
- `0x180007914`
- `0x18001a690`
- `0x18001ac30`
- `0x18002e308`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001ac71`
- `KERNEL32!GetLastError` at `0x18001ac71`

## string_xrefs

- `0x18001ac3e`: `SetServiceStartType(): Setting start type as %i\n`

## pseudocode

```c
__int64 __fastcall NGENService::SetServiceStartType(NGENService *this)
{
  unsigned int v1; // esi
  struct SC_HANDLE__ **v2; // rdx
  __int64 v3; // rdx
  signed int v4; // ebx
  signed int LastError; // eax
  struct SC_HANDLE__ *v7; // [rsp+78h] [rbp+10h] BYREF

  v1 = (unsigned int)this;
  NGENService::Log(
    (NGENService *)L"SetServiceStartType(): Setting start type as %i\n",
    (const unsigned __int16 *)(unsigned int)this);
  v7 = 0;
  v4 = NGENService::OpenNGENService((NGENService *)&v7, v2);
  if ( v4 >= 0 )
  {
    if ( (unsigned int)CLRChangeServiceConfig(v7, v3, v1) )
    {
      v4 = 0;
    }
    else
    {
      LastError = GetLastError();
      v4 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v4 = LastError;
    }
  }
  if ( v7 )
    CLRCloseServiceHandle(v7);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001ac30  mov     [rsp+arg_0], rbx
0x18001ac35  push    rsi
0x18001ac36  sub     rsp, 60h
0x18001ac3a  mov     esi, ecx
0x18001ac3c  mov     edx, ecx; unsigned __int16 *
0x18001ac3e  lea     rcx, aSetservicestar; "SetServiceStartType(): Setting start ty"...
0x18001ac45  call    ?Log@NGENService@@YAXPEBGZZ; NGENService::Log(ushort const *,...)
0x18001ac4a  and     [rsp+68h+arg_8], 0
0x18001ac50  lea     rcx, [rsp+68h+arg_8]; this
0x18001ac55  call    ?OpenNGENService@NGENService@@YAJPEAPEAUSC_HANDLE__@@@Z; NGENService::OpenNGENService(SC_HANDLE__ * *)
0x18001ac5a  mov     ebx, eax
0x18001ac5c  test    eax, eax
0x18001ac5e  js      short loc_18001AC89
0x18001ac60  mov     rcx, [rsp+68h+arg_8]; struct SC_HANDLE__ *
0x18001ac65  mov     r8d, esi; unsigned int
0x18001ac68  call    ?CLRChangeServiceConfig@@YAHPEAUSC_HANDLE__@@KKKPEBG1PEAK1111@Z; CLRChangeServiceConfig(SC_HANDLE__ *,ulong,ulong,ulong,ushort const *,ushort const *,ulong *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18001ac6d  test    eax, eax
0x18001ac6f  jnz     short loc_18001AC87
0x18001ac71  call    cs:__imp_GetLastError
0x18001ac77  movzx   ebx, ax
0x18001ac7a  or      ebx, 80070000h
0x18001ac80  test    eax, eax
0x18001ac82  cmovle  ebx, eax
0x18001ac85  jmp     short loc_18001AC89
0x18001ac87  xor     ebx, ebx
0x18001ac89  cmp     [rsp+68h+arg_8], 0
0x18001ac8f  jz      short loc_18001AC9B
0x18001ac91  mov     rcx, [rsp+68h+arg_8]; struct SC_HANDLE__ *
0x18001ac96  call    ?CLRCloseServiceHandle@@YAHPEAUSC_HANDLE__@@@Z; CLRCloseServiceHandle(SC_HANDLE__ *)
0x18001ac9b  mov     eax, ebx
0x18001ac9d  mov     rbx, [rsp+68h+arg_0]
0x18001aca2  add     rsp, 60h
0x18001aca6  pop     rsi
0x18001aca7  retn
```
