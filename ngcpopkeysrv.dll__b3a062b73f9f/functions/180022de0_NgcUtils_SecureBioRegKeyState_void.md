# NgcUtils::SecureBioRegKeyState(void)

- ea: `0x180022de0`
- end: `0x180022e8b`
- name: `?SecureBioRegKeyState@NgcUtils@@YA?AW4_NGC_ENABLED_STATE@@XZ`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022af0`

## callees

- `0x18001069c`
- `0x180022de0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180022e32`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180022e32`

## string_xrefs

- `0x180022e5f`: `onecore\ds\security\ngc\utils\bio\lib\securebioutils.cpp`

## pseudocode

```c
__int64 NgcUtils::SecureBioRegKeyState()
{
  unsigned int v0; // edi
  LSTATUS ValueW; // ebx
  unsigned __int64 v2; // r9
  int v4; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v6; // [rsp+50h] [rbp+8h] BYREF
  DWORD v7; // [rsp+58h] [rbp+10h] BYREF

  v6 = 0;
  v7 = 4;
  v0 = 2;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Control\\DeviceGuard\\Scenarios\\SecureBiometrics",
             L"Enabled",
             0x10u,
             0,
             &v6,
             &v7);
  if ( ValueW > 0 )
    v2 = (unsigned __int16)ValueW | 0x80070000;
  else
    v2 = (unsigned int)ValueW;
  if ( (ValueW & 0xFFFFFFFD) != 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x259,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\bio\\lib\\securebioutils.cpp",
      (const char *)v2,
      v4);
  if ( !ValueW )
    return v6 != 0;
  return v0;
}

```

## disassembly

```asm
0x180022de0  mov     r11, rsp
0x180022de3  mov     [r11+18h], rbx
0x180022de7  push    rdi
0x180022de8  sub     rsp, 40h
0x180022dec  lea     rax, [r11+10h]
0x180022df0  mov     [rsp+48h+arg_0], 0
0x180022df8  mov     [r11-18h], rax
0x180022dfc  lea     r8, aEnabled; "Enabled"
0x180022e03  lea     rax, [r11+8]
0x180022e07  mov     [rsp+48h+arg_8], 4
0x180022e0f  mov     [r11-20h], rax
0x180022e13  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Dev"...
0x180022e1a  mov     edi, 2
0x180022e1f  mov     qword ptr [r11-28h], 0
0x180022e27  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180022e2e  lea     r9d, [rdi+0Eh]; dwFlags
0x180022e32  call    cs:__imp_RegGetValueW
0x180022e38  test    eax, 0FFFFFFFDh
0x180022e3d  mov     ebx, eax
0x180022e3f  setnz   al
0x180022e42  test    ebx, ebx
0x180022e44  jg      short loc_180022E4B
0x180022e46  mov     r9d, ebx
0x180022e49  jmp     short loc_180022E56
0x180022e4b  movzx   r9d, bx
0x180022e4f  or      r9d, 80070000h; char *
0x180022e56  test    al, al
0x180022e58  jz      short loc_180022E70
0x180022e5a  mov     rcx, [rsp+48h]; this
0x180022e5f  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x180022e66  mov     edx, 259h; void *
0x180022e6b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180022e70  test    ebx, ebx
0x180022e72  jnz     short loc_180022E7E
0x180022e74  xor     edi, edi
0x180022e76  cmp     [rsp+48h+arg_0], edi
0x180022e7a  setnz   dil
0x180022e7e  mov     rbx, [rsp+48h+arg_10]
0x180022e83  mov     eax, edi
0x180022e85  add     rsp, 40h
0x180022e89  pop     rdi
0x180022e8a  retn
```
