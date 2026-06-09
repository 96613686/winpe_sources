# NgcUtils::SecureBioRegKeyState(void)

- ea: `0x18001a014`
- end: `0x18001a0bf`
- name: `?SecureBioRegKeyState@NgcUtils@@YA?AW4_NGC_ENABLED_STATE@@XZ`
- size: `171`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800189d4`

## callees

- `0x18000ebc0`
- `0x18001a014`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a066`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a066`

## string_xrefs

- `0x18001a093`: `onecore\ds\security\ngc\utils\bio\lib\securebioutils.cpp`

## pseudocode

```c
__int64 NgcUtils::SecureBioRegKeyState()
{
  unsigned int v0; // edi
  LSTATUS ValueW; // ebx
  unsigned __int64 v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v5; // [rsp+50h] [rbp+8h] BYREF
  DWORD v6; // [rsp+58h] [rbp+10h] BYREF

  v5 = 0;
  v6 = 4;
  v0 = 2;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Control\\DeviceGuard\\Scenarios\\SecureBiometrics",
             L"Enabled",
             0x10u,
             0,
             &v5,
             &v6);
  if ( ValueW > 0 )
    v2 = (unsigned __int16)ValueW | 0x80070000;
  else
    v2 = (unsigned int)ValueW;
  if ( (ValueW & 0xFFFFFFFD) != 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x259,
      (int)"onecore\\ds\\security\\ngc\\utils\\bio\\lib\\securebioutils.cpp",
      (const char *)v2);
  if ( !ValueW )
    return v5 != 0;
  return v0;
}

```

## disassembly

```asm
0x18001a014  mov     r11, rsp
0x18001a017  mov     [r11+18h], rbx
0x18001a01b  push    rdi
0x18001a01c  sub     rsp, 40h
0x18001a020  lea     rax, [r11+10h]
0x18001a024  mov     [rsp+48h+arg_0], 0
0x18001a02c  mov     [r11-18h], rax
0x18001a030  lea     r8, aEnabled; "Enabled"
0x18001a037  lea     rax, [r11+8]
0x18001a03b  mov     [rsp+48h+arg_8], 4
0x18001a043  mov     [r11-20h], rax
0x18001a047  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Dev"...
0x18001a04e  mov     edi, 2
0x18001a053  mov     qword ptr [r11-28h], 0
0x18001a05b  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001a062  lea     r9d, [rdi+0Eh]; dwFlags
0x18001a066  call    cs:__imp_RegGetValueW
0x18001a06c  test    eax, 0FFFFFFFDh
0x18001a071  mov     ebx, eax
0x18001a073  setnz   al
0x18001a076  test    ebx, ebx
0x18001a078  jg      short loc_18001A07F
0x18001a07a  mov     r9d, ebx
0x18001a07d  jmp     short loc_18001A08A
0x18001a07f  movzx   r9d, bx
0x18001a083  or      r9d, 80070000h; char *
0x18001a08a  test    al, al
0x18001a08c  jz      short loc_18001A0A4
0x18001a08e  mov     rcx, [rsp+48h]; this
0x18001a093  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x18001a09a  mov     edx, 259h; void *
0x18001a09f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001a0a4  test    ebx, ebx
0x18001a0a6  jnz     short loc_18001A0B2
0x18001a0a8  xor     edi, edi
0x18001a0aa  cmp     [rsp+48h+arg_0], edi
0x18001a0ae  setnz   dil
0x18001a0b2  mov     rbx, [rsp+48h+arg_10]
0x18001a0b7  mov     eax, edi
0x18001a0b9  add     rsp, 40h
0x18001a0bd  pop     rdi
0x18001a0be  retn
```
