# UninstallTunnelInterface

- ea: `0x18004702c`
- end: `0x180047171`
- name: `UninstallTunnelInterface`
- size: `325`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180043ed8`
- `0x180046e40`
- `0x1800591d0`
- `0x1800598ac`
- `0x180059c98`

## callees

- `0x18000d7b0`
- `0x18004702c`
- `0x18004b630`
- `0x18004c1c8`

## import_xrefs

- `IPHLPAPI!ConvertGuidToStringW` at `0x180047076`
- `IPHLPAPI!ConvertGuidToStringW` at `0x180047076`
- `NetSetupApi!NetSetupClose` at `0x18004712f`
- `NetSetupApi!NetSetupClose` at `0x18004712f`
- `NetSetupApi!NetSetupCommit` at `0x180047107`
- `NetSetupApi!NetSetupCommit` at `0x180047107`
- `NetSetupApi!NetSetupInitialize` at `0x1800470a1`
- `NetSetupApi!NetSetupInitialize` at `0x1800470a1`
- `NetSetupApi!NetSetupDeleteObject` at `0x1800470dc`
- `NetSetupApi!NetSetupDeleteObject` at `0x1800470dc`

## string_xrefs

- `0x180047117`: `Failed to commit transaction 0x%x`
- `0x18004708e`: `Entering UninstallTunnelInterface for %ws`
- `0x1800470f4`: `Failed to delete interface %ws: 0x%x`
- `0x18004713b`: `Leaving UninstallTunnelInterface`

## pseudocode

```c
__int64 __fastcall UninstallTunnelInterface(__int128 *a1)
{
  unsigned int v1; // ebx
  int v3; // eax
  int v4; // eax
  int v5; // eax
  __int64 v7; // [rsp+20h] [rbp-88h] BYREF
  __int128 v8; // [rsp+30h] [rbp-78h] BYREF
  _BYTE v9[80]; // [rsp+40h] [rbp-68h] BYREF

  v1 = 0;
  v7 = 0;
  memset_0(v9, 0, 0x4Eu);
  ConvertGuidToStringW(a1, v9, 39);
  EventWrite0(0x800000, L"Entering UninstallTunnelInterface for %ws", v9);
  v3 = NetSetupInitialize(0, &v7);
  if ( v3 >= 0 )
  {
    v8 = *a1;
    v4 = NetSetupDeleteObject(v7, 2, &v8);
    if ( v4 < 0 )
      EventWrite0(0x800000, L"Failed to delete interface %ws: 0x%x", v9, (unsigned int)v4);
    v5 = NetSetupCommit(v7);
    if ( v5 >= 0 )
      v1 = 1;
    else
      EventWrite0(0x800000, L"Failed to commit transaction 0x%x", (unsigned int)v5);
  }
  else
  {
    EventWrite0(0x800000, L"Failed to initialize NetSetup 0x%x", (unsigned int)v3);
  }
  if ( v7 )
    NetSetupClose();
  EventWrite0(0x800000, L"Leaving UninstallTunnelInterface");
  return v1;
}

```

## disassembly

```asm
0x18004702c  mov     [rsp+arg_8], rbx
0x180047031  mov     [rsp+arg_10], rsi
0x180047036  push    rdi
0x180047037  sub     rsp, 0A0h
0x18004703e  mov     rax, cs:__security_cookie
0x180047045  xor     rax, rsp
0x180047048  mov     [rsp+0A8h+var_18], rax
0x180047050  xor     ebx, ebx
0x180047052  mov     rdi, rcx
0x180047055  xor     edx, edx; Val
0x180047057  mov     [rsp+0A8h+var_88], rbx
0x18004705c  lea     rcx, [rsp+0A8h+var_68]; void *
0x180047061  lea     r8d, [rbx+4Eh]; Size
0x180047065  call    memset_0
0x18004706a  lea     r8d, [rbx+27h]
0x18004706e  mov     rcx, rdi
0x180047071  lea     rdx, [rsp+0A8h+var_68]
0x180047076  call    cs:__imp_ConvertGuidToStringW
0x18004707d  nop     dword ptr [rax+rax+00h]
0x180047082  mov     esi, 800000h
0x180047087  lea     r8, [rsp+0A8h+var_68]
0x18004708c  mov     ecx, esi
0x18004708e  lea     rdx, aEnteringUninst; "Entering UninstallTunnelInterface for %"...
0x180047095  call    EventWrite0
0x18004709a  lea     rdx, [rsp+0A8h+var_88]
0x18004709f  xor     ecx, ecx
0x1800470a1  call    cs:__imp_NetSetupInitialize
0x1800470a8  nop     dword ptr [rax+rax+00h]
0x1800470ad  test    eax, eax
0x1800470af  jns     short loc_1800470C4
0x1800470b1  lea     rdx, aFailedToInitia; "Failed to initialize NetSetup 0x%x"
0x1800470b8  mov     r8d, eax
0x1800470bb  mov     ecx, esi
0x1800470bd  call    EventWrite0
0x1800470c2  jmp     short loc_180047125
0x1800470c4  movups  xmm0, xmmword ptr [rdi]
0x1800470c7  mov     rcx, [rsp+0A8h+var_88]
0x1800470cc  lea     r8, [rsp+0A8h+var_78]
0x1800470d1  mov     edx, 2
0x1800470d6  movdqu  [rsp+0A8h+var_78], xmm0
0x1800470dc  call    cs:__imp_NetSetupDeleteObject
0x1800470e3  nop     dword ptr [rax+rax+00h]
0x1800470e8  test    eax, eax
0x1800470ea  jns     short loc_180047102
0x1800470ec  mov     r9d, eax
0x1800470ef  lea     r8, [rsp+0A8h+var_68]
0x1800470f4  lea     rdx, aFailedToDelete_0; "Failed to delete interface %ws: 0x%x"
0x1800470fb  mov     ecx, esi
0x1800470fd  call    EventWrite0
0x180047102  mov     rcx, [rsp+0A8h+var_88]
0x180047107  call    cs:__imp_NetSetupCommit
0x18004710e  nop     dword ptr [rax+rax+00h]
0x180047113  test    eax, eax
0x180047115  jns     short loc_180047120
0x180047117  lea     rdx, aFailedToCommit; "Failed to commit transaction 0x%x"
0x18004711e  jmp     short loc_1800470B8
0x180047120  mov     ebx, 1
0x180047125  mov     rcx, [rsp+0A8h+var_88]
0x18004712a  test    rcx, rcx
0x18004712d  jz      short loc_18004713B
0x18004712f  call    cs:__imp_NetSetupClose
0x180047136  nop     dword ptr [rax+rax+00h]
0x18004713b  lea     rdx, aLeavingUninsta; "Leaving UninstallTunnelInterface"
0x180047142  mov     ecx, esi
0x180047144  call    EventWrite0
0x180047149  mov     eax, ebx
0x18004714b  mov     rcx, [rsp+0A8h+var_18]
0x180047153  xor     rcx, rsp; StackCookie
0x180047156  call    __security_check_cookie
0x18004715b  lea     r11, [rsp+0A8h+var_8]
0x180047163  mov     rbx, [r11+18h]
0x180047167  mov     rsi, [r11+20h]
0x18004716b  mov     rsp, r11
0x18004716e  pop     rdi
0x18004716f  retn
```
