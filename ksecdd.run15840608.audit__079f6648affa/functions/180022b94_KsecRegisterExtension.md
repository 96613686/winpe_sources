# KsecRegisterExtension

- ea: `0x180022b94`
- end: `0x180022c1a`
- name: `KsecRegisterExtension`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180026fb8`

## callees

- `0x18002267c`
- `0x180022b94`

## pseudocode

```c
__int64 __fastcall KsecRegisterExtension(int a1, struct _LIST_ENTRY *a2)
{
  __int64 result; // rax

  result = 0;
  switch ( a1 )
  {
    case 0:
      if ( !*(_QWORD *)&WPP_MAIN_CB.SectorSize )
      {
        *(_QWORD *)&WPP_MAIN_CB.SectorSize = a2;
        return result;
      }
      return 3221225528LL;
    case 1:
      if ( !WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink )
      {
        WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink = a2;
        return result;
      }
      return 3221225528LL;
    case 3:
      if ( !WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink )
      {
        WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink = a2;
        return result;
      }
      return 3221225528LL;
    case 4:
      if ( !WPP_MAIN_CB.DeviceObjectExtension )
      {
        WPP_MAIN_CB.DeviceObjectExtension = (struct _DEVOBJ_EXTENSION *)a2;
        return result;
      }
      return 3221225528LL;
    case 2:
      return KsecInstallBuiltinPackages((__int64)a2);
    default:
      return 3221225485LL;
  }
}

```

## disassembly

```asm
0x180022b94  sub     rsp, 28h
0x180022b98  xor     r8d, r8d
0x180022b9b  mov     eax, r8d
0x180022b9e  test    ecx, ecx
0x180022ba0  jnz     short loc_180022BB4
0x180022ba2  cmp     qword ptr cs:WPP_MAIN_CB.SectorSize, r8
0x180022ba9  jnz     short loc_180022BF9
0x180022bab  mov     qword ptr cs:WPP_MAIN_CB.SectorSize, rdx
0x180022bb2  jmp     short loc_180022C14
0x180022bb4  cmp     ecx, 1
0x180022bb7  jnz     short loc_180022BCB
0x180022bb9  cmp     cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink, r8
0x180022bc0  jnz     short loc_180022BF9
0x180022bc2  mov     cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink, rdx
0x180022bc9  jmp     short loc_180022C14
0x180022bcb  cmp     ecx, 3
0x180022bce  jnz     short loc_180022BE2
0x180022bd0  cmp     cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink, r8
0x180022bd7  jnz     short loc_180022BF9
0x180022bd9  mov     cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink, rdx
0x180022be0  jmp     short loc_180022C14
0x180022be2  cmp     ecx, 4
0x180022be5  jnz     short loc_180022C00
0x180022be7  cmp     cs:WPP_MAIN_CB.DeviceObjectExtension, r8
0x180022bee  jnz     short loc_180022BF9
0x180022bf0  mov     cs:WPP_MAIN_CB.DeviceObjectExtension, rdx
0x180022bf7  jmp     short loc_180022C14
0x180022bf9  mov     eax, 0C0000038h
0x180022bfe  jmp     short loc_180022C14
0x180022c00  cmp     ecx, 2
0x180022c03  jnz     short loc_180022C0F
0x180022c05  mov     rcx, rdx
0x180022c08  call    KsecInstallBuiltinPackages
0x180022c0d  jmp     short loc_180022C14
0x180022c0f  mov     eax, 0C000000Dh
0x180022c14  add     rsp, 28h
0x180022c18  retn
```
