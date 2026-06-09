# CModule::Init(HINSTANCE__ *)

- ea: `0x180002bb0`
- end: `0x180002cb6`
- name: `?Init@CModule@@QEAA_NPEAUHINSTANCE__@@@Z`
- size: `262`
- prototype: `char __fastcall(CModule *this, HINSTANCE)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000a5dc`

## callees

- `0x180002bb0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180002bce`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180002bce`
- `ntdll!EtwRegisterTraceGuidsW` at `0x180002c62`
- `ntdll!EtwRegisterTraceGuidsW` at `0x180002c62`
- `ntdll!EtwEventRegister` at `0x180002c83`
- `ntdll!EtwEventRegister` at `0x180002c83`

## pseudocode

```c
char __fastcall CModule::Init(CModule *this, HINSTANCE a2)
{
  char result; // al
  __int64 *v4; // rbx
  __int64 *v5; // rdi
  __int64 v6; // r8
  _QWORD v7[7]; // [rsp+40h] [rbp-38h] BYREF

  result = byte_180011024;
  if ( !byte_180011024 )
  {
    if ( DisableThreadLibraryCalls(a2) )
    {
      qword_180011958 = 0;
      WPP_MAIN_CB = 0;
      qword_180011960 = 1;
      WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_CtlGuid;
      v4 = &WPP_MAIN_CB;
      WPP_GLOBAL_Control = &WPP_MAIN_CB;
      v5 = &WPP_REGISTRATION_GUIDS;
      do
      {
        v6 = *v5++;
        v7[0] = v6;
        v7[1] = 0;
        v4[4] = v6;
        ((void (__fastcall *)(__int64 (__fastcall *)(), __int64 *, __int64, __int64, _QWORD *, _QWORD, _QWORD, __int64 *))EtwRegisterTraceGuidsW)(
          WppControlCallback,
          v4,
          v6,
          1,
          v7,
          0,
          0,
          v4 + 1);
        v4 = (__int64 *)*v4;
      }
      while ( v4 );
      if ( (unsigned int)EtwEventRegister(DIMS_LOG, 0, 0, &qword_180011978) )
        qword_180011978 = 0;
      hModule = a2;
      byte_180011024 = 1;
      return 1;
    }
    else
    {
      return byte_180011024;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002bb0  push    rbx
0x180002bb2  push    rbp
0x180002bb3  push    rsi
0x180002bb4  push    rdi
0x180002bb5  sub     rsp, 58h
0x180002bb9  mov     rsi, rdx
0x180002bbc  movzx   eax, cs:byte_180011024
0x180002bc3  test    al, al
0x180002bc5  jnz     loc_180002CA4
0x180002bcb  mov     rcx, rdx; hLibModule
0x180002bce  call    cs:__imp_DisableThreadLibraryCalls
0x180002bd4  test    eax, eax
0x180002bd6  jz      loc_180002CAD
0x180002bdc  xor     ebp, ebp
0x180002bde  mov     cs:qword_180011958, rbp
0x180002be5  mov     cs:WPP_MAIN_CB, rbp
0x180002bec  mov     cs:qword_180011960, 1
0x180002bf7  lea     rax, WPP_ThisDir_CTLGUID_CtlGuid
0x180002bfe  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180002c05  lea     rbx, WPP_MAIN_CB
0x180002c0c  mov     cs:WPP_GLOBAL_Control, rbx
0x180002c13  lea     rdi, WPP_REGISTRATION_GUIDS
0x180002c1a  nop     word ptr [rax+rax+00h]
0x180002c20  mov     r8, [rdi]
0x180002c23  lea     rdi, [rdi+8]
0x180002c27  mov     [rsp+78h+var_38], r8
0x180002c2c  mov     [rsp+78h+var_30], rbp
0x180002c31  mov     [rbx+20h], r8
0x180002c35  lea     rax, [rbx+8]
0x180002c39  mov     [rsp+78h+var_40], rax
0x180002c3e  mov     [rsp+78h+var_48], rbp
0x180002c43  mov     [rsp+78h+var_50], rbp
0x180002c48  lea     rax, [rsp+78h+var_38]
0x180002c4d  mov     [rsp+78h+var_58], rax
0x180002c52  mov     r9d, 1
0x180002c58  mov     rdx, rbx
0x180002c5b  lea     rcx, WppControlCallback
0x180002c62  call    cs:__imp_EtwRegisterTraceGuidsW
0x180002c68  mov     rbx, [rbx]
0x180002c6b  test    rbx, rbx
0x180002c6e  jnz     short loc_180002C20
0x180002c70  lea     r9, qword_180011978
0x180002c77  xor     r8d, r8d
0x180002c7a  xor     edx, edx
0x180002c7c  lea     rcx, DIMS_LOG
0x180002c83  call    cs:__imp_EtwEventRegister
0x180002c89  test    eax, eax
0x180002c8b  jz      short loc_180002C94
0x180002c8d  mov     cs:qword_180011978, rbp
0x180002c94  mov     cs:hModule, rsi
0x180002c9b  mov     cs:byte_180011024, 1
0x180002ca2  mov     al, 1
0x180002ca4  add     rsp, 58h
0x180002ca8  pop     rdi
0x180002ca9  pop     rsi
0x180002caa  pop     rbp
0x180002cab  pop     rbx
0x180002cac  retn
0x180002cad  movzx   eax, cs:byte_180011024
0x180002cb4  jmp     short loc_180002CA4
```
