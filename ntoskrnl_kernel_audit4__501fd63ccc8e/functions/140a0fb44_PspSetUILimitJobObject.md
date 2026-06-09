# PspSetUILimitJobObject

- ea: `0x140a0fb44`
- end: `0x140a0fd19`
- name: `PspSetUILimitJobObject`
- size: `469`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x1407b3a80`
- `0x140a0d420`

## callees

- `0x14045b564`
- `0x1404a18a0`
- `0x1408e092c`
- `0x1408e2788`
- `0x140925734`
- `0x140a0fb44`
- `0x140a0fd20`
- `0x140a10410`
- `0x140a10f10`

## import_xrefs

- `ext-ms-win-ntos-win32k-l1-1-0!Win32kJobUpdateUIRestrictionsNotify` at `0x140a0fc32`
- `ext-ms-win-ntos-win32k-l1-1-0!Win32kJobUpdateUIRestrictionsNotify` at `0x140a0fc32`
- `ext-ms-win-ntos-win32k-l1-1-0!IsWin32kJobNotifyCallOutPresent` at `0x140a0fbf7`
- `ext-ms-win-ntos-win32k-l1-1-0!IsWin32kJobNotifyCallOutPresent` at `0x140a0fc3e`
- `ext-ms-win-ntos-win32k-l1-1-0!IsWin32kJobNotifyCallOutPresent` at `0x140a0fbf7`
- `ext-ms-win-ntos-win32k-l1-1-0!IsWin32kJobNotifyCallOutPresent` at `0x140a0fc3e`

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
0x140a0fb44  push    rbp
0x140a0fb46  push    rbx
0x140a0fb47  push    rsi
0x140a0fb48  push    rdi
0x140a0fb49  push    r12
0x140a0fb4b  push    r13
0x140a0fb4d  push    r14
0x140a0fb4f  push    r15
0x140a0fb51  mov     rbp, rsp
0x140a0fb54  sub     rsp, 68h
0x140a0fb58  mov     r15d, r8d
0x140a0fb5b  mov     edi, r9d
0x140a0fb5e  mov     [rbp+arg_10], 0
0x140a0fb65  mov     r12, rdx
0x140a0fb68  mov     rbx, rcx
0x140a0fb6b  test    r8d, 0FFFFFC00h
0x140a0fb72  jz      short loc_140A0FB7E
0x140a0fb74  mov     edi, 0C000000Dh
0x140a0fb79  jmp     loc_140A0FD05
0x140a0fb7e  xor     r8d, r8d
0x140a0fb81  call    PspLockJobChain
0x140a0fb86  mov     r14d, 1
0x140a0fb8c  mov     rcx, rbx; __int64
0x140a0fb8f  and     edi, r14d
0x140a0fb92  mov     edx, edi
0x140a0fb94  xor     edx, r14d
0x140a0fb97  add     edx, edx
0x140a0fb99  call    PspDoesJobHierarchyPermitUILimits
0x140a0fb9e  test    al, al
0x140a0fba0  jnz     short loc_140A0FBAC
0x140a0fba2  mov     edi, 0C00000BBh
0x140a0fba7  jmp     loc_140A0FC64
0x140a0fbac  cmp     dword ptr [rbx+348h], 0FFFFFFFEh
0x140a0fbb3  jnz     short loc_140A0FBBF
0x140a0fbb5  mov     edi, 0C0000022h
0x140a0fbba  jmp     loc_140A0FC64
0x140a0fbbf  mov     rdx, gs:188h
0x140a0fbc8  mov     rcx, rbx
0x140a0fbcb  xor     r13b, r13b
0x140a0fbce  mov     rdx, [rdx+0B8h]
0x140a0fbd5  call    PspBindProcessSessionToJob
0x140a0fbda  mov     r11d, [rbx+348h]
0x140a0fbe1  lea     rsi, [rbx+328h]
0x140a0fbe8  mov     [rbp+arg_10], r11d
0x140a0fbec  cmp     r11d, 0FFFFFFFDh
0x140a0fbf0  ja      short loc_140A0FC3E
0x140a0fbf2  cmp     [rsi], r15d
0x140a0fbf5  jz      short loc_140A0FC3E
0x140a0fbf7  call    cs:__imp_IsWin32kJobNotifyCallOutPresent
0x140a0fbfe  nop     dword ptr [rax+rax+00h]
0x140a0fc03  test    al, al
0x140a0fc05  jz      short loc_140A0FC77
0x140a0fc07  mov     [rsi], r15d
0x140a0fc0a  lock or dword ptr [rbx+818h], 10h
0x140a0fc12  test    edi, edi
0x140a0fc14  jz      short loc_140A0FC1E
0x140a0fc16  lock or dword ptr [rbx+81Ch], 10h
0x140a0fc1e  xor     r8d, r8d
0x140a0fc21  mov     rdx, r12
0x140a0fc24  mov     rcx, rbx
0x140a0fc27  call    PspUnlockJobChain
0x140a0fc2c  mov     rcx, rbx
0x140a0fc2f  xor     r14b, r14b
0x140a0fc32  call    cs:__imp_Win32kJobUpdateUIRestrictionsNotify
0x140a0fc39  nop     dword ptr [rax+rax+00h]
0x140a0fc3e  call    cs:__imp_IsWin32kJobNotifyCallOutPresent
0x140a0fc45  nop     dword ptr [rax+rax+00h]
0x140a0fc4a  test    al, al
0x140a0fc4c  jnz     short loc_140A0FC59
0x140a0fc4e  mov     [rsi], r15d
0x140a0fc51  lock or dword ptr [rbx+818h], 10h
0x140a0fc59  xor     edi, edi
0x140a0fc5b  test    r14b, r14b
0x140a0fc5e  jz      loc_140A0FCF5
0x140a0fc64  xor     r8d, r8d
0x140a0fc67  mov     rdx, r12
0x140a0fc6a  mov     rcx, rbx
0x140a0fc6d  call    PspUnlockJobChain
0x140a0fc72  jmp     loc_140A0FD05
0x140a0fc77  xorps   xmm0, xmm0
0x140a0fc7a  xor     eax, eax
0x140a0fc7c  mov     r8d, r14d
0x140a0fc7f  mov     dword ptr [rbp+var_18], eax
0x140a0fc82  mov     rdx, r12
0x140a0fc85  mov     rcx, rbx
0x140a0fc88  movups  [rbp+var_38], xmm0
0x140a0fc8c  movups  [rbp+var_28], xmm0
0x140a0fc90  call    PspUnlockJobChain
0x140a0fc95  xor     eax, eax
0x140a0fc97  mov     qword ptr [rbp+var_28], rbx
0x140a0fc9b  mov     [rbp+var_44], rax
0x140a0fc9f  lea     r9, [rbp+arg_10]
0x140a0fca3  mov     r8d, r14d
0x140a0fca6  mov     dword ptr [rbp+var_28+8], 0
0x140a0fcad  lea     rdx, [rbp+var_38]
0x140a0fcb1  mov     [rbp+var_18], r15
0x140a0fcb5  lea     r10d, [rax+6]
0x140a0fcb9  mov     [rbp-48h], rax
0x140a0fcbd  mov     ecx, r10d
0x140a0fcc0  call    PspUpdateCalloutParameters
0x140a0fcc5  test    eax, eax
0x140a0fcc7  jz      short loc_140A0FCEE
0x140a0fcc9  mov     r13b, r14b
0x140a0fccc  xor     r14b, r14b
0x140a0fccf  call    PsSessionGetWin32Callouts
0x140a0fcd4  mov     rcx, rax
0x140a0fcd7  lea     r8, [rbp+var_38]
0x140a0fcdb  mov     edx, r10d
0x140a0fcde  call    ExCallCallBack
0x140a0fce3  mov     edi, eax
0x140a0fce5  test    eax, eax
0x140a0fce7  js      short loc_140A0FCFA
0x140a0fce9  jmp     loc_140A0FC3E
0x140a0fcee  mov     edi, 0C000000Dh
0x140a0fcf3  jmp     short loc_140A0FCFA
0x140a0fcf5  test    r13b, r13b
0x140a0fcf8  jz      short loc_140A0FD05
0x140a0fcfa  mov     rdx, r12
0x140a0fcfd  mov     rcx, rbx
0x140a0fd00  call    PspUnlockJobExclusive
0x140a0fd05  mov     eax, edi
0x140a0fd07  add     rsp, 68h
0x140a0fd0b  pop     r15
0x140a0fd0d  pop     r14
0x140a0fd0f  pop     r13
0x140a0fd11  pop     r12
0x140a0fd13  pop     rdi
0x140a0fd14  pop     rsi
0x140a0fd15  pop     rbx
0x140a0fd16  pop     rbp
0x140a0fd17  retn
```
