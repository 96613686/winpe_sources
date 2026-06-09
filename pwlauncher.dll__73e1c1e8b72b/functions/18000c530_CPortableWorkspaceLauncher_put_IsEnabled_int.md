# CPortableWorkspaceLauncher::put_IsEnabled(int)

- ea: `0x18000c530`
- end: `0x18000c604`
- name: `?put_IsEnabled@CPortableWorkspaceLauncher@@UEAAJH@Z`
- size: `212`
- prototype: `int __fastcall(CPortableWorkspaceLauncher *this, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180005528`
- `0x180005c98`
- `0x180008ac8`
- `0x18000c530`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000c587`
- `KERNEL32!GetLastError` at `0x18000c5bc`
- `KERNEL32!GetLastError` at `0x18000c587`
- `KERNEL32!GetLastError` at `0x18000c5bc`

## string_xrefs

- `0x18000c594`: `drivers\wdm\usbpw\launcher\dll\cportableworkspacelauncher.cpp`

## pseudocode

```c
int __fastcall CPortableWorkspaceLauncher::put_IsEnabled(CPortableWorkspaceLauncher *this, int a2)
{
  char LastError; // al
  int result; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_92f1f72f1bef3498f21e8df521798946_Traceguids);
  if ( (unsigned int)EnablePortableWorkspaceLauncher(a2) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_92f1f72f1bef3498f21e8df521798946_Traceguids);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        (unsigned int)&WPP_92f1f72f1bef3498f21e8df521798946_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\cportableworkspacelauncher.cpp",
        112,
        LastError);
    }
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18000c530  mov     [rsp+arg_0], rbx
0x18000c535  push    rdi
0x18000c536  sub     rsp, 30h
0x18000c53a  mov     ebx, edx
0x18000c53c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c543  lea     rdi, WPP_GLOBAL_Control
0x18000c54a  cmp     rcx, rdi
0x18000c54d  jz      short loc_18000C56A
0x18000c54f  test    byte ptr [rcx+1Ch], 8
0x18000c553  jz      short loc_18000C56A
0x18000c555  mov     rcx, [rcx+10h]
0x18000c559  lea     r8, WPP_92f1f72f1bef3498f21e8df521798946_Traceguids
0x18000c560  mov     edx, 11h
0x18000c565  call    WPP_SF_
0x18000c56a  mov     ecx, ebx; int
0x18000c56c  call    ?EnablePortableWorkspaceLauncher@@YAHH@Z; EnablePortableWorkspaceLauncher(int)
0x18000c571  test    eax, eax
0x18000c573  jnz     short loc_18000C5D0
0x18000c575  mov     rax, cs:WPP_GLOBAL_Control
0x18000c57c  cmp     rax, rdi
0x18000c57f  jz      short loc_18000C5BC
0x18000c581  test    byte ptr [rax+1Ch], 1
0x18000c585  jz      short loc_18000C5BC
0x18000c587  call    cs:__imp_GetLastError
0x18000c58d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c594  lea     r9, aDriversWdmUsbp_13; "drivers\\wdm\\usbpw\\launcher\\dll\\cpo"...
0x18000c59b  mov     [rsp+38h+var_10], eax
0x18000c59f  lea     r8, WPP_92f1f72f1bef3498f21e8df521798946_Traceguids
0x18000c5a6  mov     edx, 12h
0x18000c5ab  mov     [rsp+38h+var_18], 70h ; 'p'
0x18000c5b3  mov     rcx, [rcx+10h]
0x18000c5b7  call    WPP_SF_sdD
0x18000c5bc  call    cs:__imp_GetLastError
0x18000c5c2  test    eax, eax
0x18000c5c4  jle     short loc_18000C5F9
0x18000c5c6  movzx   eax, ax
0x18000c5c9  or      eax, 80070000h
0x18000c5ce  jmp     short loc_18000C5F9
0x18000c5d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c5d7  cmp     rcx, rdi
0x18000c5da  jz      short loc_18000C5F7
0x18000c5dc  test    byte ptr [rcx+1Ch], 8
0x18000c5e0  jz      short loc_18000C5F7
0x18000c5e2  mov     rcx, [rcx+10h]
0x18000c5e6  lea     r8, WPP_92f1f72f1bef3498f21e8df521798946_Traceguids
0x18000c5ed  mov     edx, 13h
0x18000c5f2  call    WPP_SF_
0x18000c5f7  xor     eax, eax
0x18000c5f9  mov     rbx, [rsp+38h+arg_0]
0x18000c5fe  add     rsp, 30h
0x18000c602  pop     rdi
0x18000c603  retn
```
