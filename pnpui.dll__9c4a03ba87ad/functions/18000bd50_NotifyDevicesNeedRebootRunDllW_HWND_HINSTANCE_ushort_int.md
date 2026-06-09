# NotifyDevicesNeedRebootRunDllW(HWND__ *,HINSTANCE__ *,ushort *,int)

- ea: `0x18000bd50`
- end: `0x18000bddc`
- name: `?NotifyDevicesNeedRebootRunDllW@@YAXPEAUHWND__@@PEAUHINSTANCE__@@PEAGH@Z`
- size: `140`
- prototype: `void __fastcall(HWND, HINSTANCE, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b868`
- `0x18000bd50`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000bdb7`
- `msvcrt!_wcsicmp` at `0x18000bdb7`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18000bd61`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18000bd61`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x18000bd74`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x18000bd74`

## pseudocode

```c
void __fastcall NotifyDevicesNeedRebootRunDllW(HWND a1, HINSTANCE a2, unsigned __int16 *a3)
{
  const WCHAR *CommandLineW; // rax
  LPWSTR *v4; // rsi
  int v5; // ecx
  int v6; // edi
  int i; // ebx
  LPWSTR v8; // rdx
  int v9; // eax
  int pNumArgs[14]; // [rsp+20h] [rbp-38h] BYREF

  pNumArgs[0] = 0;
  CommandLineW = GetCommandLineW();
  if ( CommandLineW )
  {
    v4 = CommandLineToArgvW(CommandLineW, pNumArgs);
    if ( v4 )
    {
      v5 = pNumArgs[0];
      v6 = 0;
      for ( i = 2; i < v5; ++i )
      {
        v8 = v4[i];
        if ( ((*v8 - 45) & 0xFFFD) == 0 )
        {
          v9 = _wcsicmp(v8 + 1, L"reset");
          v5 = pNumArgs[0];
          if ( !v9 )
            v6 = 1;
        }
      }
      NotifyDevicesNeedReboot(v6);
    }
  }
}

```

## disassembly

```asm
0x18000bd50  push    rbx
0x18000bd52  push    rbp
0x18000bd53  push    rsi
0x18000bd54  push    rdi
0x18000bd55  sub     rsp, 38h
0x18000bd59  mov     [rsp+58h+pNumArgs], 0
0x18000bd61  call    cs:__imp_GetCommandLineW
0x18000bd67  test    rax, rax
0x18000bd6a  jz      short loc_18000BDD3
0x18000bd6c  lea     rdx, [rsp+58h+pNumArgs]; pNumArgs
0x18000bd71  mov     rcx, rax; lpCmdLine
0x18000bd74  call    cs:__imp_CommandLineToArgvW
0x18000bd7a  mov     rsi, rax
0x18000bd7d  test    rax, rax
0x18000bd80  jz      short loc_18000BDD3
0x18000bd82  mov     ecx, [rsp+58h+pNumArgs]
0x18000bd86  xor     edi, edi
0x18000bd88  lea     ebx, [rdi+2]
0x18000bd8b  cmp     ecx, ebx
0x18000bd8d  jle     short loc_18000BDCC
0x18000bd8f  lea     ebp, [rdi+1]
0x18000bd92  movsxd  rax, ebx
0x18000bd95  mov     r8d, 0FFFDh
0x18000bd9b  mov     rdx, [rsi+rax*8]
0x18000bd9f  movzx   eax, word ptr [rdx]
0x18000bda2  sub     ax, 2Dh ; '-'
0x18000bda6  test    r8w, ax
0x18000bdaa  jnz     short loc_18000BDC6
0x18000bdac  lea     rcx, [rdx+2]; String1
0x18000bdb0  lea     rdx, aReset; "reset"
0x18000bdb7  call    cs:__imp__wcsicmp
0x18000bdbd  mov     ecx, [rsp+58h+pNumArgs]
0x18000bdc1  test    eax, eax
0x18000bdc3  cmovz   edi, ebp
0x18000bdc6  add     ebx, ebp
0x18000bdc8  cmp     ebx, ecx
0x18000bdca  jl      short loc_18000BD92
0x18000bdcc  mov     ecx, edi; int
0x18000bdce  call    ?NotifyDevicesNeedReboot@@YAJH@Z; NotifyDevicesNeedReboot(int)
0x18000bdd3  add     rsp, 38h
0x18000bdd7  pop     rdi
0x18000bdd8  pop     rsi
0x18000bdd9  pop     rbp
0x18000bdda  pop     rbx
0x18000bddb  retn
```
