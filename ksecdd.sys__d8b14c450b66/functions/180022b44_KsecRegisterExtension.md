# KsecRegisterExtension

- ea: `0x180022b44`
- end: `0x180022bca`
- name: `KsecRegisterExtension`
- size: `134`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180026f68`

## callees

- `0x18002262c`
- `0x180022b44`

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
      if ( !WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink )
      {
        WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink = a2;
        return result;
      }
      return 3221225528LL;
    case 3:
      if ( !WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink )
      {
        WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink = a2;
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
0x180022b44  sub     rsp, 28h
0x180022b48  xor     r8d, r8d
0x180022b4b  mov     eax, r8d
0x180022b4e  test    ecx, ecx
0x180022b50  jnz     short loc_180022B64
0x180022b52  cmp     qword ptr cs:WPP_MAIN_CB.SectorSize, r8
0x180022b59  jnz     short loc_180022BA9
0x180022b5b  mov     qword ptr cs:WPP_MAIN_CB.SectorSize, rdx
0x180022b62  jmp     short loc_180022BC4
0x180022b64  cmp     ecx, 1
0x180022b67  jnz     short loc_180022B7B
0x180022b69  cmp     cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink, r8
0x180022b70  jnz     short loc_180022BA9
0x180022b72  mov     cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink, rdx
0x180022b79  jmp     short loc_180022BC4
0x180022b7b  cmp     ecx, 3
0x180022b7e  jnz     short loc_180022B92
0x180022b80  cmp     cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink, r8
0x180022b87  jnz     short loc_180022BA9
0x180022b89  mov     cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink, rdx
0x180022b90  jmp     short loc_180022BC4
0x180022b92  cmp     ecx, 4
0x180022b95  jnz     short loc_180022BB0
0x180022b97  cmp     cs:WPP_MAIN_CB.DeviceObjectExtension, r8
0x180022b9e  jnz     short loc_180022BA9
0x180022ba0  mov     cs:WPP_MAIN_CB.DeviceObjectExtension, rdx
0x180022ba7  jmp     short loc_180022BC4
0x180022ba9  mov     eax, 0C0000038h
0x180022bae  jmp     short loc_180022BC4
0x180022bb0  cmp     ecx, 2
0x180022bb3  jnz     short loc_180022BBF
0x180022bb5  mov     rcx, rdx
0x180022bb8  call    KsecInstallBuiltinPackages
0x180022bbd  jmp     short loc_180022BC4
0x180022bbf  mov     eax, 0C000000Dh
0x180022bc4  add     rsp, 28h
0x180022bc8  retn
```
