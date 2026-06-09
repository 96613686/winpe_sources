# Microsoft::HostGuardian::Client::Plugin::AttestationHandler::AttestShsInternal(std::vector<AttestationResultType,std::allocator<AttestationResultType>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,uint,ShsAttestationFlag &,uint *,AttestationResult * *)

- ea: `0x180008d18`
- end: `0x180008e34`
- name: `?AttestShsInternal@AttestationHandler@Plugin@Client@HostGuardian@Microsoft@@AEAA?AW4AttestationError@@AEBV?$vector@W4AttestationResultType@@V?$allocator@W4AttestationResultType@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@8@IAEAW4ShsAttestationFlag@@PEAIPEAPEAUAttestationResult@@@Z`
- size: `284`
- prototype: `__int64 __fastcall(int, int, int, int, _DWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008bd0`

## callees

- `0x180001520`
- `0x180008d18`
- `0x180008e3c`

## import_xrefs

- `tbs!Tbsi_GetDeviceInfo` at `0x180008d82`
- `tbs!Tbsi_GetDeviceInfo` at `0x180008d82`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::Plugin::AttestationHandler::AttestShsInternal(
        int a1,
        int a2,
        int a3,
        int a4,
        _DWORD *a5,
        __int64 a6,
        __int64 a7)
{
  char v7; // di
  __int64 result; // rax
  char v13; // cl
  __int128 v14; // [rsp+40h] [rbp-58h] BYREF

  v7 = 0;
  if ( !*a5 )
  {
    *a5 = 2;
    v14 = 0;
    v7 = 1;
    if ( !(unsigned int)Tbsi_GetDeviceInfo(16, &v14) && DWORD1(v14) == 2 )
      *a5 = 1;
  }
  result = Microsoft::HostGuardian::Client::Plugin::AttestationHandler::AttestShsInternalRaw(
             a1,
             a2,
             *a5,
             a3,
             a4,
             a6,
             a7);
  if ( (_DWORD)result == -2063720448 )
  {
    *a5 = 2;
  }
  else
  {
    v13 = 0;
    if ( (_DWORD)result == -2063720447 )
    {
      *a5 = 1;
      goto LABEL_12;
    }
    if ( (_DWORD)result != -2063720446 )
      goto LABEL_12;
    *a5 = 3;
  }
  v13 = 1;
LABEL_12:
  if ( v7 )
  {
    if ( v13 )
      return Microsoft::HostGuardian::Client::Plugin::AttestationHandler::AttestShsInternalRaw(
               a1,
               a2,
               *a5,
               a3,
               a4,
               a6,
               a7);
  }
  return result;
}

```

## disassembly

```asm
0x180008d18  mov     [rsp+arg_18], rbx
0x180008d1d  push    rbp
0x180008d1e  push    rsi
0x180008d1f  push    rdi
0x180008d20  push    r12
0x180008d22  push    r13
0x180008d24  push    r14
0x180008d26  push    r15
0x180008d28  sub     rsp, 60h
0x180008d2c  mov     rax, cs:__security_cookie
0x180008d33  xor     rax, rsp
0x180008d36  mov     [rsp+98h+var_48], rax
0x180008d3b  mov     rbx, [rsp+98h+arg_20]
0x180008d43  xor     dil, dil
0x180008d46  mov     r12, [rsp+98h+arg_28]
0x180008d4e  mov     esi, r9d
0x180008d51  mov     r13, [rsp+98h+arg_30]
0x180008d59  mov     r15, r8
0x180008d5c  mov     r14, rdx
0x180008d5f  mov     rbp, rcx
0x180008d62  cmp     dword ptr [rbx], 0
0x180008d65  jnz     short loc_180008D99
0x180008d67  xorps   xmm0, xmm0
0x180008d6a  mov     dword ptr [rbx], 2
0x180008d70  lea     rdx, [rsp+98h+var_58]
0x180008d75  mov     ecx, 10h
0x180008d7a  movups  [rsp+98h+var_58], xmm0
0x180008d7f  mov     dil, 1
0x180008d82  call    cs:__imp_Tbsi_GetDeviceInfo
0x180008d88  test    eax, eax
0x180008d8a  jnz     short loc_180008D99
0x180008d8c  cmp     dword ptr [rsp+98h+var_58+4], 2
0x180008d91  jnz     short loc_180008D99
0x180008d93  mov     dword ptr [rbx], 1
0x180008d99  mov     r8d, [rbx]
0x180008d9c  mov     r9, r15
0x180008d9f  mov     [rsp+98h+var_68], r13
0x180008da4  mov     rdx, r14
0x180008da7  mov     [rsp+98h+var_70], r12
0x180008dac  mov     rcx, rbp
0x180008daf  mov     [rsp+98h+var_78], esi
0x180008db3  call    ?AttestShsInternalRaw@AttestationHandler@Plugin@Client@HostGuardian@Microsoft@@AEAA?AW4AttestationError@@AEBV?$vector@W4AttestationResultType@@V?$allocator@W4AttestationResultType@@@std@@@std@@W4ShsAttestationFlag@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@8@IPEAIPEAPEAUAttestationResult@@@Z; Microsoft::HostGuardian::Client::Plugin::AttestationHandler::AttestShsInternalRaw(std::vector<AttestationResultType> const &,ShsAttestationFlag,std::wstring const &,uint,uint *,AttestationResult * *)
0x180008db8  cmp     eax, 84FE2000h
0x180008dbd  jz      short loc_180008DDF
0x180008dbf  xor     cl, cl
0x180008dc1  cmp     eax, 84FE2001h
0x180008dc6  jz      short loc_180008DD7
0x180008dc8  cmp     eax, 84FE2002h
0x180008dcd  jnz     short loc_180008DE7
0x180008dcf  mov     dword ptr [rbx], 3
0x180008dd5  jmp     short loc_180008DE5
0x180008dd7  mov     dword ptr [rbx], 1
0x180008ddd  jmp     short loc_180008DE7
0x180008ddf  mov     dword ptr [rbx], 2
0x180008de5  mov     cl, 1
0x180008de7  test    dil, dil
0x180008dea  jz      short loc_180008E0F
0x180008dec  test    cl, cl
0x180008dee  jz      short loc_180008E0F
0x180008df0  mov     r8d, [rbx]
0x180008df3  mov     r9, r15
0x180008df6  mov     [rsp+98h+var_68], r13
0x180008dfb  mov     rdx, r14
0x180008dfe  mov     [rsp+98h+var_70], r12
0x180008e03  mov     rcx, rbp
0x180008e06  mov     [rsp+98h+var_78], esi
0x180008e0a  call    ?AttestShsInternalRaw@AttestationHandler@Plugin@Client@HostGuardian@Microsoft@@AEAA?AW4AttestationError@@AEBV?$vector@W4AttestationResultType@@V?$allocator@W4AttestationResultType@@@std@@@std@@W4ShsAttestationFlag@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@8@IPEAIPEAPEAUAttestationResult@@@Z; Microsoft::HostGuardian::Client::Plugin::AttestationHandler::AttestShsInternalRaw(std::vector<AttestationResultType> const &,ShsAttestationFlag,std::wstring const &,uint,uint *,AttestationResult * *)
0x180008e0f  mov     rcx, [rsp+98h+var_48]
0x180008e14  xor     rcx, rsp; StackCookie
0x180008e17  call    __security_check_cookie
0x180008e1c  mov     rbx, [rsp+98h+arg_18]
0x180008e24  add     rsp, 60h
0x180008e28  pop     r15
0x180008e2a  pop     r14
0x180008e2c  pop     r13
0x180008e2e  pop     r12
0x180008e30  pop     rdi
0x180008e31  pop     rsi
0x180008e32  pop     rbp
0x180008e33  retn
```
