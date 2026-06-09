# IniSetBTDeviceRole

- ea: `0x180033bb8`
- end: `0x180033c44`
- name: `IniSetBTDeviceRole`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18003306c`

## callees

- `0x180001710`
- `0x180004c00`
- `0x1800339f0`
- `0x180033bb8`

## string_xrefs

- `0x180033bd4`: `Personal Ad Hoc User Service`
- `0x180033bf5`: `Personal Ad Hoc User Service`

## pseudocode

```c
__int64 IniSetBTDeviceRole()
{
  __int64 v1; // r11
  unsigned __int16 v2[56]; // [rsp+20h] [rbp-218h] BYREF
  unsigned __int16 v3[200]; // [rsp+90h] [rbp-1A8h] BYREF

  if ( (int)StringCchCopyW(v2, 0x32u, L"Personal Ad Hoc User Service") < 0
    || (int)StringCchCopyW(v3, 0xC8u, L"Personal Ad Hoc User Service") < 0 )
  {
    return 1359;
  }
  else
  {
    return IniSetBTDeviceConfig(v1, 3, v2, v3);
  }
}

```

## disassembly

```asm
0x180033bb8  sub     rsp, 238h
0x180033bbf  mov     rax, cs:__security_cookie
0x180033bc6  xor     rax, rsp
0x180033bc9  mov     [rsp+238h+var_18], rax
0x180033bd1  mov     r11, rcx
0x180033bd4  lea     r8, aPersonalAdHocU; "Personal Ad Hoc User Service"
0x180033bdb  lea     rcx, [rsp+238h+var_218]; unsigned __int16 *
0x180033be0  mov     edx, 32h ; '2'; unsigned __int64
0x180033be5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180033bea  test    eax, eax
0x180033bec  jns     short loc_180033BF5
0x180033bee  mov     eax, 54Fh
0x180033bf3  jmp     short loc_180033C2C
0x180033bf5  lea     r8, aPersonalAdHocU; "Personal Ad Hoc User Service"
0x180033bfc  mov     edx, 0C8h; unsigned __int64
0x180033c01  lea     rcx, [rsp+238h+var_1A8]; unsigned __int16 *
0x180033c09  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180033c0e  test    eax, eax
0x180033c10  js      short loc_180033BEE
0x180033c12  lea     r9, [rsp+238h+var_1A8]
0x180033c1a  mov     edx, 3
0x180033c1f  lea     r8, [rsp+238h+var_218]
0x180033c24  mov     rcx, r11
0x180033c27  call    IniSetBTDeviceConfig
0x180033c2c  mov     rcx, [rsp+238h+var_18]
0x180033c34  xor     rcx, rsp; StackCookie
0x180033c37  call    __security_check_cookie
0x180033c3c  add     rsp, 238h
0x180033c43  retn
```
