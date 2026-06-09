# PspSetUILimitJobObject

- ea: `0x140a06d50`
- end: `0x140a06f25`
- name: `PspSetUILimitJobObject`
- size: `469`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x1407b0620`
- `0x140a04300`

## callees

- `0x140448084`
- `0x140493b98`
- `0x1408ab8bc`
- `0x14092d614`
- `0x140a06d50`
- `0x140a06fb4`
- `0x140a073ac`
- `0x140a07eac`
- `0x140a08820`

## import_xrefs

- `ext-ms-win-ntos-win32k-l1-1-0!Win32kJobUpdateUIRestrictionsNotify` at `0x140a06e3e`
- `ext-ms-win-ntos-win32k-l1-1-0!Win32kJobUpdateUIRestrictionsNotify` at `0x140a06e3e`
- `ext-ms-win-ntos-win32k-l1-1-0!IsWin32kJobNotifyCallOutPresent` at `0x140a06e03`
- `ext-ms-win-ntos-win32k-l1-1-0!IsWin32kJobNotifyCallOutPresent` at `0x140a06e4a`
- `ext-ms-win-ntos-win32k-l1-1-0!IsWin32kJobNotifyCallOutPresent` at `0x140a06e03`
- `ext-ms-win-ntos-win32k-l1-1-0!IsWin32kJobNotifyCallOutPresent` at `0x140a06e4a`

## pseudocode

```c
__int64 __fastcall PspSetUILimitJobObject(__int64 a1, __int64 a2, unsigned int a3, char a4)
{
  __int64 v4; // r15
  unsigned int v8; // edi
  char v9; // r14
  int v10; // edi
  char v11; // r13
  _DWORD *v12; // rsi
  __int64 Win32Callouts; // rax
  unsigned int v14; // r10d
  __int128 v16; // [rsp+30h] [rbp-38h] BYREF
  __int128 v17; // [rsp+40h] [rbp-28h]
  __int64 v18; // [rsp+50h] [rbp-18h]
  unsigned int v19; // [rsp+C0h] [rbp+58h] BYREF

  v4 = a3;
  v19 = 0;
  if ( (a3 & 0xFFFFFC00) == 0 )
  {
    PspLockJobChain(a1, a2, 0);
    v9 = 1;
    v10 = a4 & 1;
    if ( !(unsigned __int8)PspDoesJobHierarchyPermitUILimits(a1) )
    {
      v8 = -1073741637;
LABEL_16:
      PspUnlockJobChain(a1, a2, 0);
      return v8;
    }
    if ( *(_DWORD *)(a1 + 840) == -2 )
    {
      v8 = -1073741790;
      goto LABEL_16;
    }
    v11 = 0;
    PspBindProcessSessionToJob(a1, KeGetCurrentThread()->ApcState.Process);
    v12 = (_DWORD *)(a1 + 808);
    v19 = *(_DWORD *)(a1 + 840);
    if ( v19 <= 0xFFFFFFFD && *v12 != (_DWORD)v4 )
    {
      if ( (unsigned __int8)IsWin32kJobNotifyCallOutPresent() )
      {
        *v12 = v4;
        _InterlockedOr((volatile signed __int32 *)(a1 + 2072), 0x10u);
        if ( v10 )
          _InterlockedOr((volatile signed __int32 *)(a1 + 2076), 0x10u);
        PspUnlockJobChain(a1, a2, 0);
        v9 = 0;
        Win32kJobUpdateUIRestrictionsNotify(a1);
      }
      else
      {
        v16 = 0;
        v17 = 0;
        PspUnlockJobChain(a1, a2, 1);
        *(_QWORD *)&v17 = a1;
        DWORD2(v17) = 0;
        v18 = v4;
        if ( !(unsigned int)PspUpdateCalloutParameters(6, &v16, 1, &v19, 0, 0) )
        {
          v8 = -1073741811;
          goto LABEL_22;
        }
        v11 = 1;
        v9 = 0;
        Win32Callouts = PsSessionGetWin32Callouts();
        v8 = ExCallCallBack(Win32Callouts, v14, &v16);
        if ( (v8 & 0x80000000) != 0 )
        {
LABEL_22:
          PspUnlockJobExclusive(a1, a2);
          return v8;
        }
      }
    }
    if ( !(unsigned __int8)IsWin32kJobNotifyCallOutPresent() )
    {
      *v12 = v4;
      _InterlockedOr((volatile signed __int32 *)(a1 + 2072), 0x10u);
    }
    v8 = 0;
    if ( v9 )
      goto LABEL_16;
    if ( !v11 )
      return v8;
    goto LABEL_22;
  }
  return (unsigned int)-1073741811;
}

```

## disassembly

```asm
0x140a06d50  push    rbp
0x140a06d52  push    rbx
0x140a06d53  push    rsi
0x140a06d54  push    rdi
0x140a06d55  push    r12
0x140a06d57  push    r13
0x140a06d59  push    r14
0x140a06d5b  push    r15
0x140a06d5d  mov     rbp, rsp
0x140a06d60  sub     rsp, 68h
0x140a06d64  mov     r15d, r8d
0x140a06d67  mov     edi, r9d
0x140a06d6a  mov     [rbp+arg_10], 0
0x140a06d71  mov     r12, rdx
0x140a06d74  mov     rbx, rcx
0x140a06d77  test    r8d, 0FFFFFC00h
0x140a06d7e  jz      short loc_140A06D8A
0x140a06d80  mov     edi, 0C000000Dh
0x140a06d85  jmp     loc_140A06F11
0x140a06d8a  xor     r8d, r8d
0x140a06d8d  call    PspLockJobChain
0x140a06d92  mov     r14d, 1
0x140a06d98  mov     rcx, rbx; __int64
0x140a06d9b  and     edi, r14d
0x140a06d9e  mov     edx, edi
0x140a06da0  xor     edx, r14d
0x140a06da3  add     edx, edx
0x140a06da5  call    PspDoesJobHierarchyPermitUILimits
0x140a06daa  test    al, al
0x140a06dac  jnz     short loc_140A06DB8
0x140a06dae  mov     edi, 0C00000BBh
0x140a06db3  jmp     loc_140A06E70
0x140a06db8  cmp     dword ptr [rbx+348h], 0FFFFFFFEh
0x140a06dbf  jnz     short loc_140A06DCB
0x140a06dc1  mov     edi, 0C0000022h
0x140a06dc6  jmp     loc_140A06E70
0x140a06dcb  mov     rdx, gs:188h
0x140a06dd4  mov     rcx, rbx
0x140a06dd7  xor     r13b, r13b
0x140a06dda  mov     rdx, [rdx+0B8h]
0x140a06de1  call    PspBindProcessSessionToJob
0x140a06de6  mov     r11d, [rbx+348h]
0x140a06ded  lea     rsi, [rbx+328h]
0x140a06df4  mov     [rbp+arg_10], r11d
0x140a06df8  cmp     r11d, 0FFFFFFFDh
0x140a06dfc  ja      short loc_140A06E4A
0x140a06dfe  cmp     [rsi], r15d
0x140a06e01  jz      short loc_140A06E4A
0x140a06e03  call    cs:__imp_IsWin32kJobNotifyCallOutPresent
0x140a06e0a  nop     dword ptr [rax+rax+00h]
0x140a06e0f  test    al, al
0x140a06e11  jz      short loc_140A06E83
0x140a06e13  mov     [rsi], r15d
0x140a06e16  lock or dword ptr [rbx+818h], 10h
0x140a06e1e  test    edi, edi
0x140a06e20  jz      short loc_140A06E2A
0x140a06e22  lock or dword ptr [rbx+81Ch], 10h
0x140a06e2a  xor     r8d, r8d
0x140a06e2d  mov     rdx, r12
0x140a06e30  mov     rcx, rbx
0x140a06e33  call    PspUnlockJobChain
0x140a06e38  mov     rcx, rbx
0x140a06e3b  xor     r14b, r14b
0x140a06e3e  call    cs:__imp_Win32kJobUpdateUIRestrictionsNotify
0x140a06e45  nop     dword ptr [rax+rax+00h]
0x140a06e4a  call    cs:__imp_IsWin32kJobNotifyCallOutPresent
0x140a06e51  nop     dword ptr [rax+rax+00h]
0x140a06e56  test    al, al
0x140a06e58  jnz     short loc_140A06E65
0x140a06e5a  mov     [rsi], r15d
0x140a06e5d  lock or dword ptr [rbx+818h], 10h
0x140a06e65  xor     edi, edi
0x140a06e67  test    r14b, r14b
0x140a06e6a  jz      loc_140A06F01
0x140a06e70  xor     r8d, r8d
0x140a06e73  mov     rdx, r12
0x140a06e76  mov     rcx, rbx
0x140a06e79  call    PspUnlockJobChain
0x140a06e7e  jmp     loc_140A06F11
0x140a06e83  xorps   xmm0, xmm0
0x140a06e86  xor     eax, eax
0x140a06e88  mov     r8d, r14d
0x140a06e8b  mov     dword ptr [rbp+var_18], eax
0x140a06e8e  mov     rdx, r12
0x140a06e91  mov     rcx, rbx
0x140a06e94  movups  [rbp+var_38], xmm0
0x140a06e98  movups  [rbp+var_28], xmm0
0x140a06e9c  call    PspUnlockJobChain
0x140a06ea1  xor     eax, eax
0x140a06ea3  mov     qword ptr [rbp+var_28], rbx
0x140a06ea7  mov     [rbp+var_44], rax
0x140a06eab  lea     r9, [rbp+arg_10]
0x140a06eaf  mov     r8d, r14d
0x140a06eb2  mov     dword ptr [rbp+var_28+8], 0
0x140a06eb9  lea     rdx, [rbp+var_38]
0x140a06ebd  mov     [rbp+var_18], r15
0x140a06ec1  lea     r10d, [rax+6]
0x140a06ec5  mov     [rbp-48h], rax
0x140a06ec9  mov     ecx, r10d
0x140a06ecc  call    PspUpdateCalloutParameters
0x140a06ed1  test    eax, eax
0x140a06ed3  jz      short loc_140A06EFA
0x140a06ed5  mov     r13b, r14b
0x140a06ed8  xor     r14b, r14b
0x140a06edb  call    PsSessionGetWin32Callouts
0x140a06ee0  mov     rcx, rax
0x140a06ee3  lea     r8, [rbp+var_38]
0x140a06ee7  mov     edx, r10d
0x140a06eea  call    ExCallCallBack
0x140a06eef  mov     edi, eax
0x140a06ef1  test    eax, eax
0x140a06ef3  js      short loc_140A06F06
0x140a06ef5  jmp     loc_140A06E4A
0x140a06efa  mov     edi, 0C000000Dh
0x140a06eff  jmp     short loc_140A06F06
0x140a06f01  test    r13b, r13b
0x140a06f04  jz      short loc_140A06F11
0x140a06f06  mov     rdx, r12
0x140a06f09  mov     rcx, rbx
0x140a06f0c  call    PspUnlockJobExclusive
0x140a06f11  mov     eax, edi
0x140a06f13  add     rsp, 68h
0x140a06f17  pop     r15
0x140a06f19  pop     r14
0x140a06f1b  pop     r13
0x140a06f1d  pop     r12
0x140a06f1f  pop     rdi
0x140a06f20  pop     rsi
0x140a06f21  pop     rbx
0x140a06f22  pop     rbp
0x140a06f23  retn
```
