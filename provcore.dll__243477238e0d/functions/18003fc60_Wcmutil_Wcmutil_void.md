# Wcmutil::Wcmutil(void)

- ea: `0x18003fc60`
- end: `0x18003fd45`
- name: `??0Wcmutil@@QEAA@XZ`
- size: `229`
- prototype: `void __fastcall(Wcmutil *this)`
- caller_count: `12`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001c928`
- `0x18001df00`
- `0x18002a0b4`
- `0x18002a2e8`
- `0x18002a51c`
- `0x18002a880`
- `0x18002d5f4`
- `0x180030380`
- `0x180042298`
- `0x180043660`
- `0x180045a2c`
- `0x180045be8`

## callees

- `0x180002790`
- `0x1800032f4`
- `0x1800042c8`
- `0x180013bdc`
- `0x180031c40`
- `0x18003fc60`

## import_xrefs

- `ext-ms-win-networking-wcmapi-l1-1-0!WcmOpenHandle` at `0x18003fcd7`
- `ext-ms-win-networking-wcmapi-l1-1-0!WcmOpenHandle` at `0x18003fcd7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Wcmutil::Wcmutil(Wcmutil *this)
{
  const _EVENT_DESCRIPTOR *v2; // rdx
  _MCGEN_TRACE_CONTEXT *v3; // rcx
  int v4; // eax
  unsigned int v5; // ebx
  HrException pExceptionObject; // [rsp+20h] [rbp-38h] BYREF
  unsigned int dwVersion; // [rsp+40h] [rbp-18h] BYREF

  this->m_hWcm = 0;
  dwVersion = 0;
  if ( !IsWcmQueryPropertyPresent()
    || !IsWcmQueryPropertyPresent()
    || !IsWcmQueryPropertyPresent()
    || !IsWcmQueryPropertyPresent()
    || !IsWcmQueryPropertyPresent()
    || !IsWcmQueryPropertyPresent()
    || !IsWcmQueryPropertyPresent() )
  {
    LOWORD(v5) = 50;
LABEL_13:
    v5 = (unsigned __int16)v5 | 0x80070000;
LABEL_14:
    if ( (Microsoft_Windows_NetworkProvisioningEnableBits[0] & 0x400) != 0 )
      McTemplateU0qd_EtwEventWriteTransfer(v3, v2, 3u, v5);
    HrException::HrException(&pExceptionObject, v5);
    throw &pExceptionObject;
  }
  v4 = WcmOpenHandle(1, 0, &dwVersion, this);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 <= 0 )
      goto LABEL_14;
    goto LABEL_13;
  }
}

```

## disassembly

```asm
0x18003fc60  mov     [rsp+arg_8], rbx
0x18003fc65  push    rdi
0x18003fc66  sub     rsp, 50h
0x18003fc6a  mov     rax, cs:__security_cookie
0x18003fc71  xor     rax, rsp
0x18003fc74  mov     [rsp+58h+var_10], rax
0x18003fc79  mov     rdi, this
0x18003fc7c  mov     qword ptr [this], 0
0x18003fc83  mov     [rsp+58h+dwVersion], 0
0x18003fc8b  call    IsWcmQueryPropertyPresent
0x18003fc90  test    al, al
0x18003fc92  jz      short loc_18003FD02
0x18003fc94  call    IsWcmQueryPropertyPresent
0x18003fc99  test    al, al
0x18003fc9b  jz      short loc_18003FD02
0x18003fc9d  call    IsWcmQueryPropertyPresent
0x18003fca2  test    al, al
0x18003fca4  jz      short loc_18003FD02
0x18003fca6  call    IsWcmQueryPropertyPresent
0x18003fcab  test    al, al
0x18003fcad  jz      short loc_18003FD02
0x18003fcaf  call    IsWcmQueryPropertyPresent
0x18003fcb4  test    al, al
0x18003fcb6  jz      short loc_18003FD02
0x18003fcb8  call    IsWcmQueryPropertyPresent
0x18003fcbd  test    al, al
0x18003fcbf  jz      short loc_18003FD02
0x18003fcc1  call    IsWcmQueryPropertyPresent
0x18003fcc6  test    al, al
0x18003fcc8  jz      short loc_18003FD02
0x18003fcca  xor     edx, edx
0x18003fccc  lea     r8, [rsp+58h+dwVersion]
0x18003fcd1  mov     r9, rdi
0x18003fcd4  lea     ecx, [rdx+1]
0x18003fcd7  call    cs:__imp_WcmOpenHandle
0x18003fcdd  mov     ebx, eax
0x18003fcdf  test    eax, eax
0x18003fce1  jz      short loc_18003FCE7
0x18003fce3  jle     short loc_18003FD10
0x18003fce5  jmp     short loc_18003FD07
0x18003fce7  mov     rax, rdi
0x18003fcea  mov     this, [rsp+58h+var_10]
0x18003fcef  xor     this, rsp; StackCookie
0x18003fcf2  call    __security_check_cookie
0x18003fcf7  mov     rbx, [rsp+58h+arg_8]
0x18003fcfc  add     rsp, 50h
0x18003fd00  pop     rdi
0x18003fd01  retn
0x18003fd02  mov     ebx, 32h ; '2'
0x18003fd07  movzx   ebx, bx
0x18003fd0a  or      ebx, 80070000h
0x18003fd10  test    byte ptr cs:Microsoft_Windows_NetworkProvisioningEnableBits+1, 4
0x18003fd17  jz      short loc_18003FD27
0x18003fd19  mov     r9d, ebx; Descriptor
0x18003fd1c  mov     r8d, 3; Context
0x18003fd22  call    McTemplateU0qd_EtwEventWriteTransfer
0x18003fd27  mov     edx, ebx; ErrorCode
0x18003fd29  lea     this, [rsp+58h+pExceptionObject]; this
0x18003fd2e  call    ??0HrException@@QEAA@J@Z; HrException::HrException(long)
0x18003fd33  lea     rdx, _TI2?AVHrException@@; pThrowInfo
0x18003fd3a  lea     this, [rsp+58h+pExceptionObject]; pExceptionObject
0x18003fd3f  call    _CxxThrowException_0
```
