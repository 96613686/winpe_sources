# UninstallTunnelInterface

- ea: `0x180046fec`
- end: `0x180047131`
- name: `UninstallTunnelInterface`
- size: `325`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180043e98`
- `0x180046e00`
- `0x1800591f0`
- `0x1800598cc`
- `0x180059cb8`

## callees

- `0x18000d7c0`
- `0x180046fec`
- `0x18004b5f0`
- `0x18004c188`

## import_xrefs

- `IPHLPAPI!ConvertGuidToStringW` at `0x180047036`
- `IPHLPAPI!ConvertGuidToStringW` at `0x180047036`
- `NetSetupApi!NetSetupClose` at `0x1800470ef`
- `NetSetupApi!NetSetupClose` at `0x1800470ef`
- `NetSetupApi!NetSetupCommit` at `0x1800470c7`
- `NetSetupApi!NetSetupCommit` at `0x1800470c7`
- `NetSetupApi!NetSetupInitialize` at `0x180047061`
- `NetSetupApi!NetSetupInitialize` at `0x180047061`
- `NetSetupApi!NetSetupDeleteObject` at `0x18004709c`
- `NetSetupApi!NetSetupDeleteObject` at `0x18004709c`

## string_xrefs

- `0x1800470d7`: `Failed to commit transaction 0x%x`
- `0x18004704e`: `Entering UninstallTunnelInterface for %ws`
- `0x1800470b4`: `Failed to delete interface %ws: 0x%x`
- `0x1800470fb`: `Leaving UninstallTunnelInterface`

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
0x180046fec  mov     [rsp+arg_8], rbx
0x180046ff1  mov     [rsp+arg_10], rsi
0x180046ff6  push    rdi
0x180046ff7  sub     rsp, 0A0h
0x180046ffe  mov     rax, cs:__security_cookie
0x180047005  xor     rax, rsp
0x180047008  mov     [rsp+0A8h+var_18], rax
0x180047010  xor     ebx, ebx
0x180047012  mov     rdi, rcx
0x180047015  xor     edx, edx; Val
0x180047017  mov     [rsp+0A8h+var_88], rbx
0x18004701c  lea     rcx, [rsp+0A8h+var_68]; void *
0x180047021  lea     r8d, [rbx+4Eh]; Size
0x180047025  call    memset_0
0x18004702a  lea     r8d, [rbx+27h]
0x18004702e  mov     rcx, rdi
0x180047031  lea     rdx, [rsp+0A8h+var_68]
0x180047036  call    cs:__imp_ConvertGuidToStringW
0x18004703d  nop     dword ptr [rax+rax+00h]
0x180047042  mov     esi, 800000h
0x180047047  lea     r8, [rsp+0A8h+var_68]
0x18004704c  mov     ecx, esi
0x18004704e  lea     rdx, aEnteringUninst; "Entering UninstallTunnelInterface for %"...
0x180047055  call    EventWrite0
0x18004705a  lea     rdx, [rsp+0A8h+var_88]
0x18004705f  xor     ecx, ecx
0x180047061  call    cs:__imp_NetSetupInitialize
0x180047068  nop     dword ptr [rax+rax+00h]
0x18004706d  test    eax, eax
0x18004706f  jns     short loc_180047084
0x180047071  lea     rdx, aFailedToInitia; "Failed to initialize NetSetup 0x%x"
0x180047078  mov     r8d, eax
0x18004707b  mov     ecx, esi
0x18004707d  call    EventWrite0
0x180047082  jmp     short loc_1800470E5
0x180047084  movups  xmm0, xmmword ptr [rdi]
0x180047087  mov     rcx, [rsp+0A8h+var_88]
0x18004708c  lea     r8, [rsp+0A8h+var_78]
0x180047091  mov     edx, 2
0x180047096  movdqu  [rsp+0A8h+var_78], xmm0
0x18004709c  call    cs:__imp_NetSetupDeleteObject
0x1800470a3  nop     dword ptr [rax+rax+00h]
0x1800470a8  test    eax, eax
0x1800470aa  jns     short loc_1800470C2
0x1800470ac  mov     r9d, eax
0x1800470af  lea     r8, [rsp+0A8h+var_68]
0x1800470b4  lea     rdx, aFailedToDelete_0; "Failed to delete interface %ws: 0x%x"
0x1800470bb  mov     ecx, esi
0x1800470bd  call    EventWrite0
0x1800470c2  mov     rcx, [rsp+0A8h+var_88]
0x1800470c7  call    cs:__imp_NetSetupCommit
0x1800470ce  nop     dword ptr [rax+rax+00h]
0x1800470d3  test    eax, eax
0x1800470d5  jns     short loc_1800470E0
0x1800470d7  lea     rdx, aFailedToCommit; "Failed to commit transaction 0x%x"
0x1800470de  jmp     short loc_180047078
0x1800470e0  mov     ebx, 1
0x1800470e5  mov     rcx, [rsp+0A8h+var_88]
0x1800470ea  test    rcx, rcx
0x1800470ed  jz      short loc_1800470FB
0x1800470ef  call    cs:__imp_NetSetupClose
0x1800470f6  nop     dword ptr [rax+rax+00h]
0x1800470fb  lea     rdx, aLeavingUninsta; "Leaving UninstallTunnelInterface"
0x180047102  mov     ecx, esi
0x180047104  call    EventWrite0
0x180047109  mov     eax, ebx
0x18004710b  mov     rcx, [rsp+0A8h+var_18]
0x180047113  xor     rcx, rsp; StackCookie
0x180047116  call    __security_check_cookie
0x18004711b  lea     r11, [rsp+0A8h+var_8]
0x180047123  mov     rbx, [r11+18h]
0x180047127  mov     rsi, [r11+20h]
0x18004712b  mov     rsp, r11
0x18004712e  pop     rdi
0x18004712f  retn
```
