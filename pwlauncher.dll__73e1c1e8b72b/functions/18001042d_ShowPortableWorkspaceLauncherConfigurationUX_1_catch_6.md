# _ShowPortableWorkspaceLauncherConfigurationUX_::_1_::catch$6

- ea: `0x18001042d`
- end: `0x180010489`
- name: `_ShowPortableWorkspaceLauncherConfigurationUX_::_1_::catch$6`
- size: `92`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x180008b30`
- `0x18001042d`

## string_xrefs

- `0x180010460`: `drivers\wdm\usbpw\launcher\dll\ux.cpp`

## pseudocode

```c
__int64 ShowPortableWorkspaceLauncherConfigurationUX_::_1_::catch_6()
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      (unsigned int)&WPP_10512c3147f2350527aef22e4c614f89_Traceguids,
      (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\ux.cpp",
      102);
  return 0;
}

```

## disassembly

```asm
0x18001042d  mov     [rsp+arg_8], rdx
0x180010432  push    rbp
0x180010433  sub     rsp, 30h
0x180010437  mov     rbp, rdx
0x18001043a  lea     rax, WPP_GLOBAL_Control
0x180010441  mov     rcx, cs:WPP_GLOBAL_Control
0x180010448  cmp     rcx, rax
0x18001044b  jz      short loc_180010478
0x18001044d  test    byte ptr [rcx+1Ch], 1
0x180010451  jz      short loc_180010478
0x180010453  mov     edx, 12h
0x180010458  mov     [rsp+38h+var_18], 66h ; 'f'
0x180010460  lea     r9, aDriversWdmUsbp_6; "drivers\\wdm\\usbpw\\launcher\\dll\\ux."...
0x180010467  lea     r8, WPP_10512c3147f2350527aef22e4c614f89_Traceguids
0x18001046e  mov     rcx, [rcx+10h]
0x180010472  call    WPP_SF_sd
0x180010477  nop
0x180010478  mov     rax, 0
0x180010482  add     rsp, 30h
0x180010486  pop     rbp
0x180010487  retn
```
