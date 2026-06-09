# TaskDialogSecurityWarningDlgProc(HWND__ *,uint,unsigned __int64,__int64,__int64)

- ea: `0x18002fb40`
- end: `0x18002fc2e`
- name: `?TaskDialogSecurityWarningDlgProc@@YAJPEAUHWND__@@I_K_J2@Z`
- size: `238`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18002ec84`
- `0x18002fb40`

## import_xrefs

- `USER32!SendMessageW` at `0x18002fb61`
- `USER32!SendMessageW` at `0x18002fb61`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fbe2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fbe2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002fbce`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002fbce`

## string_xrefs

- `0x18002fbc7`: `DisableLegacyPointAndPrintAdminSecurityWarning`

## pseudocode

```c
__int64 __fastcall TaskDialogSecurityWarningDlgProc(HWND a1, int a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  unsigned int v5; // ebp
  _DWORD *v6; // rdi
  int v7; // ebx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  int Data; // [rsp+58h] [rbp+10h] BYREF

  v5 = 0;
  if ( a2 )
  {
    if ( a2 == 2 )
    {
      if ( a3 == 1 )
      {
        v6 = a5;
        v7 = 0;
        if ( !a5[1] || !a5[2] )
          goto LABEL_12;
        hKey = 0;
        Data = 1;
        v7 = CreateRegistryKeyWithSecurity(0, &hKey);
        if ( !v7 )
          v7 = RegSetValueExW(hKey, L"DisableLegacyPointAndPrintAdminSecurityWarning", 0, 4u, (const BYTE *)&Data, 4u);
        if ( hKey )
          RegCloseKey(hKey);
        if ( v7 )
          return 1;
        else
LABEL_12:
          *v6 = v7;
      }
    }
    else if ( a2 == 8 )
    {
      a5[2] = a3 == 1;
    }
  }
  else
  {
    SendMessageW(a1, 0x473u, 1u, 1);
  }
  return v5;
}

```

## disassembly

```asm
0x18002fb40  mov     [rsp+arg_0], rbx
0x18002fb45  mov     [rsp+arg_10], rbp
0x18002fb4a  push    rdi
0x18002fb4b  sub     rsp, 40h
0x18002fb4f  xor     ebp, ebp
0x18002fb51  test    edx, edx
0x18002fb53  jnz     short loc_18002FB6C
0x18002fb55  lea     r9d, [rbp+1]; lParam
0x18002fb59  mov     edx, 473h; Msg
0x18002fb5e  mov     r8d, r9d; wParam
0x18002fb61  call    cs:__imp_SendMessageW
0x18002fb67  jmp     loc_18002FC1C
0x18002fb6c  cmp     edx, 2
0x18002fb6f  jnz     loc_18002FC06
0x18002fb75  cmp     r8, 1
0x18002fb79  jnz     loc_18002FC1C
0x18002fb7f  mov     rdi, [rsp+48h+arg_20]
0x18002fb84  xor     ebx, ebx
0x18002fb86  cmp     [rdi+4], ebx
0x18002fb89  jz      short loc_18002FBEC
0x18002fb8b  cmp     [rdi+8], ebx
0x18002fb8e  jz      short loc_18002FBEC
0x18002fb90  lea     rdx, [rsp+48h+hKey]; HKEY *
0x18002fb95  mov     [rsp+48h+hKey], rbx
0x18002fb9a  xor     ecx, ecx; int
0x18002fb9c  mov     [rsp+48h+Data], r8d
0x18002fba1  call    ?CreateRegistryKeyWithSecurity@@YAKHPEAPEAUHKEY__@@@Z; CreateRegistryKeyWithSecurity(int,HKEY__ * *)
0x18002fba6  mov     ebx, eax
0x18002fba8  test    eax, eax
0x18002fbaa  jnz     short loc_18002FBD6
0x18002fbac  mov     rcx, [rsp+48h+hKey]; hKey
0x18002fbb1  lea     r9d, [rax+4]; dwType
0x18002fbb5  lea     rax, [rsp+48h+Data]
0x18002fbba  mov     [rsp+48h+cbData], r9d; cbData
0x18002fbbf  xor     r8d, r8d; Reserved
0x18002fbc2  mov     [rsp+48h+lpData], rax; lpData
0x18002fbc7  lea     rdx, ValueName; "DisableLegacyPointAndPrintAdminSecurity"...
0x18002fbce  call    cs:__imp_RegSetValueExW
0x18002fbd4  mov     ebx, eax
0x18002fbd6  cmp     [rsp+48h+hKey], rbp
0x18002fbdb  jz      short loc_18002FBE8
0x18002fbdd  mov     rcx, [rsp+48h+hKey]; hKey
0x18002fbe2  call    cs:__imp_RegCloseKey
0x18002fbe8  test    ebx, ebx
0x18002fbea  jnz     short loc_18002FBF0
0x18002fbec  mov     [rdi], ebx
0x18002fbee  jmp     short loc_18002FC1C
0x18002fbf0  jle     short loc_18002FBFB
0x18002fbf2  movzx   ebx, bx
0x18002fbf5  or      ebx, 80070000h
0x18002fbfb  test    ebx, ebx
0x18002fbfd  jns     short loc_18002FBEC
0x18002fbff  mov     ebp, 1
0x18002fc04  jmp     short loc_18002FC1C
0x18002fc06  cmp     edx, 8
0x18002fc09  jnz     short loc_18002FC1C
0x18002fc0b  mov     rcx, [rsp+48h+arg_20]
0x18002fc10  xor     edx, edx
0x18002fc12  cmp     r8, 1
0x18002fc16  setz    dl
0x18002fc19  mov     [rcx+8], edx
0x18002fc1c  mov     rbx, [rsp+48h+arg_0]
0x18002fc21  mov     eax, ebp
0x18002fc23  mov     rbp, [rsp+48h+arg_10]
0x18002fc28  add     rsp, 40h
0x18002fc2c  pop     rdi
0x18002fc2d  retn
```
