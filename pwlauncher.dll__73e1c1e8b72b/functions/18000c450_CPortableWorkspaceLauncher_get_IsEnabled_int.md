# CPortableWorkspaceLauncher::get_IsEnabled(int *)

- ea: `0x18000c450`
- end: `0x18000c526`
- name: `?get_IsEnabled@CPortableWorkspaceLauncher@@UEAAJPEAH@Z`
- size: `214`
- prototype: `int __fastcall(CPortableWorkspaceLauncher *this, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180005528`
- `0x1800070ec`
- `0x180008ac8`
- `0x18000c450`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000c4a9`
- `KERNEL32!GetLastError` at `0x18000c4de`
- `KERNEL32!GetLastError` at `0x18000c4a9`
- `KERNEL32!GetLastError` at `0x18000c4de`

## string_xrefs

- `0x18000c4b6`: `drivers\wdm\usbpw\launcher\dll\cportableworkspacelauncher.cpp`

## pseudocode

```c
int __fastcall CPortableWorkspaceLauncher::get_IsEnabled(CPortableWorkspaceLauncher *this, int *a2)
{
  char LastError; // al
  int result; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_92f1f72f1bef3498f21e8df521798946_Traceguids);
  if ( (unsigned int)IsPortableWorkspaceLauncherEnabled(a2) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_92f1f72f1bef3498f21e8df521798946_Traceguids);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        (unsigned int)&WPP_92f1f72f1bef3498f21e8df521798946_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\cportableworkspacelauncher.cpp",
        95,
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
0x18000c450  mov     [rsp+arg_0], rbx
0x18000c455  push    rdi
0x18000c456  sub     rsp, 30h
0x18000c45a  mov     rbx, rdx
0x18000c45d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c464  lea     rdi, WPP_GLOBAL_Control
0x18000c46b  cmp     rcx, rdi
0x18000c46e  jz      short loc_18000C48B
0x18000c470  test    byte ptr [rcx+1Ch], 8
0x18000c474  jz      short loc_18000C48B
0x18000c476  mov     rcx, [rcx+10h]
0x18000c47a  lea     r8, WPP_92f1f72f1bef3498f21e8df521798946_Traceguids
0x18000c481  mov     edx, 0Eh
0x18000c486  call    WPP_SF_
0x18000c48b  mov     rcx, rbx; int *
0x18000c48e  call    ?IsPortableWorkspaceLauncherEnabled@@YAHPEAH@Z; IsPortableWorkspaceLauncherEnabled(int *)
0x18000c493  test    eax, eax
0x18000c495  jnz     short loc_18000C4F2
0x18000c497  mov     rax, cs:WPP_GLOBAL_Control
0x18000c49e  cmp     rax, rdi
0x18000c4a1  jz      short loc_18000C4DE
0x18000c4a3  test    byte ptr [rax+1Ch], 1
0x18000c4a7  jz      short loc_18000C4DE
0x18000c4a9  call    cs:__imp_GetLastError
0x18000c4af  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4b6  lea     r9, aDriversWdmUsbp_13; "drivers\\wdm\\usbpw\\launcher\\dll\\cpo"...
0x18000c4bd  mov     [rsp+38h+var_10], eax
0x18000c4c1  lea     r8, WPP_92f1f72f1bef3498f21e8df521798946_Traceguids
0x18000c4c8  mov     edx, 0Fh
0x18000c4cd  mov     [rsp+38h+var_18], 5Fh ; '_'
0x18000c4d5  mov     rcx, [rcx+10h]
0x18000c4d9  call    WPP_SF_sdD
0x18000c4de  call    cs:__imp_GetLastError
0x18000c4e4  test    eax, eax
0x18000c4e6  jle     short loc_18000C51B
0x18000c4e8  movzx   eax, ax
0x18000c4eb  or      eax, 80070000h
0x18000c4f0  jmp     short loc_18000C51B
0x18000c4f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4f9  cmp     rcx, rdi
0x18000c4fc  jz      short loc_18000C519
0x18000c4fe  test    byte ptr [rcx+1Ch], 8
0x18000c502  jz      short loc_18000C519
0x18000c504  mov     rcx, [rcx+10h]
0x18000c508  lea     r8, WPP_92f1f72f1bef3498f21e8df521798946_Traceguids
0x18000c50f  mov     edx, 10h
0x18000c514  call    WPP_SF_
0x18000c519  xor     eax, eax
0x18000c51b  mov     rbx, [rsp+38h+arg_0]
0x18000c520  add     rsp, 30h
0x18000c524  pop     rdi
0x18000c525  retn
```
