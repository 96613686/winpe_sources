# Wwan::Wwan(void)

- ea: `0x180044fec`
- end: `0x1800450e6`
- name: `??0Wwan@@QEAA@XZ`
- size: `250`
- prototype: `void __fastcall(Wwan *this)`
- caller_count: `15`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180014b98`
- `0x180014f9c`
- `0x18001532c`
- `0x18001c928`
- `0x18001df00`
- `0x18002a0b4`
- `0x18002a2e8`
- `0x18002a51c`
- `0x18002a880`
- `0x18002d5f4`
- `0x18002fdd8`
- `0x1800313f8`
- `0x180042298`
- `0x180043660`
- `0x18005ffd0`

## callees

- `0x180002790`
- `0x1800032f4`
- `0x180012748`
- `0x180012770`
- `0x180013bdc`
- `0x180031c40`
- `0x180044fec`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180045050`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180045050`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Wwan::Wwan(Wwan *this)
{
  int v2; // eax
  const _EVENT_DESCRIPTOR *v3; // rdx
  unsigned int v4; // ebx
  _MCGEN_TRACE_CONTEXT *v5; // rcx
  HrException pExceptionObject; // [rsp+20h] [rbp-38h] BYREF
  unsigned int dwVersion; // [rsp+40h] [rbp-18h] BYREF

  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x18u, WPP_785cd9ea59c9302df8b87f94fe851dfa_Traceguids);
  }
  dwVersion = 0;
  v2 = WwanOpenHandle(1, 0, &dwVersion, this);
  v4 = v2;
  if ( v2 )
  {
    if ( v2 > 0 )
      v4 = (unsigned __int16)v2 | 0x80070000;
    v5 = (_MCGEN_TRACE_CONTEXT *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x19u, WPP_785cd9ea59c9302df8b87f94fe851dfa_Traceguids, v4);
    }
    if ( (Microsoft_Windows_NetworkProvisioningEnableBits[0] & 0x400) != 0 )
      McTemplateU0qd_EtwEventWriteTransfer(v5, v3, 2u, v4);
    HrException::HrException(&pExceptionObject, v4);
    throw &pExceptionObject;
  }
}

```

## disassembly

```asm
0x180044fec  mov     [rsp+arg_8], rbx
0x180044ff1  mov     [rsp+arg_10], rsi
0x180044ff6  push    rdi
0x180044ff7  sub     rsp, 50h
0x180044ffb  mov     rax, cs:__security_cookie
0x180045002  xor     rax, rsp
0x180045005  mov     [rsp+58h+var_10], rax
0x18004500a  mov     rdi, this
0x18004500d  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180045014  lea     rsi, WPP_GLOBAL_Control
0x18004501b  cmp     this, rsi
0x18004501e  jz      short loc_18004503B
0x180045020  test    byte ptr [this+1Ch], 10h
0x180045024  jz      short loc_18004503B
0x180045026  mov     this, [this+10h]; Logger
0x18004502a  lea     r8, WPP_785cd9ea59c9302df8b87f94fe851dfa_Traceguids; TraceGuid
0x180045031  mov     edx, 18h; id
0x180045036  call    WPP_SF_
0x18004503b  xor     edx, edx
0x18004503d  mov     [rsp+58h+dwVersion], 0
0x180045045  mov     r9, rdi
0x180045048  lea     r8, [rsp+58h+dwVersion]
0x18004504d  lea     ecx, [rdx+1]
0x180045050  call    cs:__imp_WwanOpenHandle
0x180045056  mov     ebx, eax
0x180045058  test    eax, eax
0x18004505a  jz      short loc_1800450C6
0x18004505c  jle     short loc_180045067
0x18004505e  movzx   ebx, ax
0x180045061  or      ebx, 80070000h
0x180045067  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18004506e  cmp     this, rsi
0x180045071  jz      short loc_180045091
0x180045073  test    byte ptr [this+1Ch], 10h
0x180045077  jz      short loc_180045091
0x180045079  mov     this, [this+10h]; Logger
0x18004507d  lea     r8, WPP_785cd9ea59c9302df8b87f94fe851dfa_Traceguids; TraceGuid
0x180045084  mov     edx, 19h; id
0x180045089  mov     r9d, ebx; _a1
0x18004508c  call    WPP_SF_d
0x180045091  test    byte ptr cs:Microsoft_Windows_NetworkProvisioningEnableBits+1, 4
0x180045098  jz      short loc_1800450A8
0x18004509a  mov     r9d, ebx; Descriptor
0x18004509d  mov     r8d, 2; Context
0x1800450a3  call    McTemplateU0qd_EtwEventWriteTransfer
0x1800450a8  mov     edx, ebx; ErrorCode
0x1800450aa  lea     this, [rsp+58h+pExceptionObject]; this
0x1800450af  call    ??0HrException@@QEAA@J@Z; HrException::HrException(long)
0x1800450b4  lea     rdx, _TI2?AVHrException@@; pThrowInfo
0x1800450bb  lea     this, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800450c0  call    _CxxThrowException_0
0x1800450c6  mov     rax, rdi
0x1800450c9  mov     this, [rsp+58h+var_10]
0x1800450ce  xor     this, rsp; StackCookie
0x1800450d1  call    __security_check_cookie
0x1800450d6  mov     rbx, [rsp+58h+arg_8]
0x1800450db  mov     rsi, [rsp+58h+arg_10]
0x1800450e0  add     rsp, 50h
0x1800450e4  pop     rdi
0x1800450e5  retn
```
