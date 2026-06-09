# BootScenario::ControlUserBootScenario(BootScenario::ControlAction)

- ea: `0x180028b2c`
- end: `0x180028c24`
- name: `?ControlUserBootScenario@BootScenario@@AEAAJW4ControlAction@1@@Z`
- size: `248`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180028af4`
- `0x1800b58a0`

## callees

- `0x180028b2c`
- `0x1800cf080`

## import_xrefs

- `ntdll!EtwEventWriteEndScenario` at `0x180028be2`
- `ntdll!EtwEventWriteEndScenario` at `0x180028be2`
- `ntdll!EtwEventWriteStartScenario` at `0x180028bc4`
- `ntdll!EtwEventWriteStartScenario` at `0x180028bc4`
- `ntdll!EtwEventActivityIdControl` at `0x180028b94`
- `ntdll!EtwEventActivityIdControl` at `0x180028b94`
- `ntdll!EtwEventUnregister` at `0x180028c00`
- `ntdll!EtwEventUnregister` at `0x180028c00`
- `ntdll!EtwEventRegister` at `0x180028b72`
- `ntdll!EtwEventRegister` at `0x180028b72`

## pseudocode

```c
__int64 __fastcall BootScenario::ControlUserBootScenario(__int64 a1, int a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v5; // ebx
  int v6; // eax
  __int64 v8; // [rsp+20h] [rbp-40h] BYREF
  int v9; // [rsp+28h] [rbp-38h] BYREF
  _QWORD v10[2]; // [rsp+30h] [rbp-30h] BYREF
  GUID v11; // [rsp+40h] [rbp-20h] BYREF

  v8 = 0;
  v11 = GUID_86432a0b_3c7d_4ddf_a89c_172faa90485d;
  v3 = EtwEventRegister(&MS_Winlogon_Provider, 0, 0, &v8);
  v4 = v3;
  if ( v3 )
  {
    if ( v3 <= 0 )
      goto LABEL_13;
    v5 = (unsigned __int16)v3;
    goto LABEL_4;
  }
  EtwEventActivityIdControl(2, &v11);
  if ( a2 )
  {
    if ( a2 != 1 )
    {
LABEL_12:
      v4 = 0;
      goto LABEL_13;
    }
    v6 = EtwEventWriteEndScenario(v8, WLDiagEvt_UserBootScenario_Stop, 0, 0);
  }
  else
  {
    v10[0] = &v9;
    v9 = 0;
    v10[1] = 4;
    v6 = EtwEventWriteStartScenario(v8, WLDiagEvt_UserBootScenario_Start, 1, v10);
  }
  v4 = v6;
  if ( !v6 )
    goto LABEL_12;
  if ( v6 > 0 )
  {
    v5 = (unsigned __int16)v6;
LABEL_4:
    v4 = v5 | 0x80070000;
  }
LABEL_13:
  if ( v8 )
    EtwEventUnregister(v8);
  return v4;
}

```

## disassembly

```asm
0x180028b2c  mov     [rsp-8+arg_0], rbx
0x180028b31  mov     [rsp-8+arg_8], rdi
0x180028b36  push    rbp
0x180028b37  mov     rbp, rsp
0x180028b3a  sub     rsp, 60h
0x180028b3e  mov     rax, cs:__security_cookie
0x180028b45  xor     rax, rsp
0x180028b48  mov     [rbp+var_10], rax
0x180028b4c  movups  xmm0, xmmword ptr cs:_GUID_86432a0b_3c7d_4ddf_a89c_172faa90485d.Data1
0x180028b53  mov     edi, edx
0x180028b55  mov     [rbp+var_40], 0
0x180028b5d  lea     r9, [rbp+var_40]
0x180028b61  xor     r8d, r8d
0x180028b64  xor     edx, edx
0x180028b66  lea     rcx, MS_Winlogon_Provider
0x180028b6d  movdqu  [rbp+var_20], xmm0
0x180028b72  call    cs:__imp_EtwEventRegister
0x180028b78  mov     ebx, eax
0x180028b7a  test    eax, eax
0x180028b7c  jz      short loc_180028B8B
0x180028b7e  jle     short loc_180028BF7
0x180028b80  movzx   ebx, ax
0x180028b83  or      ebx, 80070000h
0x180028b89  jmp     short loc_180028BF7
0x180028b8b  lea     rdx, [rbp+var_20]
0x180028b8f  mov     ecx, 2
0x180028b94  call    cs:__imp_EtwEventActivityIdControl
0x180028b9a  test    edi, edi
0x180028b9c  jnz     short loc_180028BCC
0x180028b9e  mov     rcx, [rbp+var_40]
0x180028ba2  lea     rax, [rbp+var_38]
0x180028ba6  lea     r9, [rbp+var_30]
0x180028baa  mov     [rbp+var_30], rax
0x180028bae  lea     r8d, [rdi+1]
0x180028bb2  mov     [rbp+var_38], edi
0x180028bb5  lea     rdx, WLDiagEvt_UserBootScenario_Start
0x180028bbc  mov     [rbp+var_28], 4
0x180028bc4  call    cs:__imp_EtwEventWriteStartScenario
0x180028bca  jmp     short loc_180028BE8
0x180028bcc  cmp     edi, 1
0x180028bcf  jnz     short loc_180028BF5
0x180028bd1  mov     rcx, [rbp+var_40]
0x180028bd5  lea     rdx, WLDiagEvt_UserBootScenario_Stop
0x180028bdc  xor     r9d, r9d
0x180028bdf  xor     r8d, r8d
0x180028be2  call    cs:__imp_EtwEventWriteEndScenario
0x180028be8  mov     ebx, eax
0x180028bea  test    eax, eax
0x180028bec  jz      short loc_180028BF5
0x180028bee  jle     short loc_180028BF7
0x180028bf0  movzx   ebx, bx
0x180028bf3  jmp     short loc_180028B83
0x180028bf5  xor     ebx, ebx
0x180028bf7  mov     rcx, [rbp+var_40]
0x180028bfb  test    rcx, rcx
0x180028bfe  jz      short loc_180028C06
0x180028c00  call    cs:__imp_EtwEventUnregister
0x180028c06  mov     eax, ebx
0x180028c08  mov     rcx, [rbp+var_10]
0x180028c0c  xor     rcx, rsp; StackCookie
0x180028c0f  call    __security_check_cookie
0x180028c14  mov     rbx, [rsp+60h+arg_0]
0x180028c19  mov     rdi, [rsp+60h+arg_8]
0x180028c1e  add     rsp, 60h
0x180028c22  pop     rbp
0x180028c23  retn
```
