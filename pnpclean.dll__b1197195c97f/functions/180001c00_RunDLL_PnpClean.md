# RunDLL_PnpClean

- ea: `0x180001c00`
- end: `0x180001ca2`
- name: `RunDLL_PnpClean`
- size: `162`
- prototype: `const WCHAR *()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001c00`
- `0x180001cd4`

## import_xrefs

- `KERNEL32!GetCommandLineW` at `0x180001c1b`
- `KERNEL32!GetCommandLineW` at `0x180001c1b`
- `SHELL32!CommandLineToArgvW` at `0x180001c2e`
- `SHELL32!CommandLineToArgvW` at `0x180001c2e`
- `SETUPAPI!pSetupCreateTextLogSectionW` at `0x180001c60`
- `SETUPAPI!pSetupCreateTextLogSectionW` at `0x180001c60`
- `SETUPAPI!pSetupCloseTextLogSection` at `0x180001c91`
- `SETUPAPI!pSetupCloseTextLogSection` at `0x180001c91`

## string_xrefs

- `0x180001c4e`: `RunDLL_PnpClean Device and Driver Cleanup Routine`

## pseudocode

```c
const WCHAR *RunDLL_PnpClean()
{
  const WCHAR *result; // rax
  __int64 v1; // rdi
  int TextLogSectionW; // ebx
  __int64 v3; // r8
  int pNumArgs; // [rsp+20h] [rbp-18h] BYREF
  _QWORD v5[2]; // [rsp+28h] [rbp-10h] BYREF

  pNumArgs = 0;
  v5[0] = 0;
  result = GetCommandLineW();
  if ( result )
  {
    result = (const WCHAR *)CommandLineToArgvW(result, &pNumArgs);
    if ( result )
    {
      if ( pNumArgs >= 2 )
      {
        pNumArgs -= 2;
        v1 = (__int64)(result + 8);
        TextLogSectionW = pSetupCreateTextLogSectionW(0, 3, L"RunDLL_PnpClean Device and Driver Cleanup Routine", v5);
        if ( !TextLogSectionW )
          v5[0] = 1;
        result = (const WCHAR *)PnpCleanMain(pNumArgs, v1, v3, (__int64)v5);
        if ( TextLogSectionW )
          return (const WCHAR *)pSetupCloseTextLogSection(v5[0], (unsigned int)result);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180001c00  mov     [rsp+arg_0], rbx
0x180001c05  push    rdi
0x180001c06  sub     rsp, 30h
0x180001c0a  mov     [rsp+38h+pNumArgs], 0
0x180001c12  mov     [rsp+38h+var_10], 0
0x180001c1b  call    cs:__imp_GetCommandLineW
0x180001c21  test    rax, rax
0x180001c24  jz      short loc_180001C97
0x180001c26  lea     rdx, [rsp+38h+pNumArgs]; pNumArgs
0x180001c2b  mov     rcx, rax; lpCmdLine
0x180001c2e  call    cs:__imp_CommandLineToArgvW
0x180001c34  test    rax, rax
0x180001c37  jz      short loc_180001C97
0x180001c39  mov     ecx, [rsp+38h+pNumArgs]
0x180001c3d  cmp     ecx, 2
0x180001c40  jl      short loc_180001C97
0x180001c42  sub     ecx, 2
0x180001c45  lea     r9, [rsp+38h+var_10]
0x180001c4a  mov     [rsp+38h+pNumArgs], ecx
0x180001c4e  lea     r8, aRundllPnpclean_0; "RunDLL_PnpClean Device and Driver Clean"...
0x180001c55  xor     ecx, ecx
0x180001c57  lea     rdi, [rax+10h]
0x180001c5b  mov     edx, 3
0x180001c60  call    cs:__imp_pSetupCreateTextLogSectionW
0x180001c66  mov     ebx, eax
0x180001c68  test    eax, eax
0x180001c6a  jnz     short loc_180001C75
0x180001c6c  mov     [rsp+38h+var_10], 1
0x180001c75  mov     ecx, [rsp+38h+pNumArgs]
0x180001c79  lea     r9, [rsp+38h+var_10]
0x180001c7e  mov     rdx, rdi
0x180001c81  call    PnpCleanMain
0x180001c86  test    ebx, ebx
0x180001c88  jz      short loc_180001C97
0x180001c8a  mov     rcx, [rsp+38h+var_10]
0x180001c8f  mov     edx, eax
0x180001c91  call    cs:__imp_pSetupCloseTextLogSection
0x180001c97  mov     rbx, [rsp+38h+arg_0]
0x180001c9c  add     rsp, 30h
0x180001ca0  pop     rdi
0x180001ca1  retn
```
