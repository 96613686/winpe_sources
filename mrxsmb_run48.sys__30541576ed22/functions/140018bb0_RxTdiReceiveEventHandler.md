# RxTdiReceiveEventHandler

- ea: `0x140018bb0`
- end: `0x140018d43`
- name: `RxTdiReceiveEventHandler`
- size: `403`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x140018bb0`
- `0x14001a354`
- `0x14003838c`
- `0x1400584cc`
- `0x140059dc0`
- `0x140059ea0`

## import_xrefs

- `ntoskrnl!IoGetActivityIdThread` at `0x140018cb2`
- `ntoskrnl!IoGetActivityIdThread` at `0x140018cb2`
- `ntoskrnl!EtwProviderEnabled` at `0x140018c78`
- `ntoskrnl!EtwProviderEnabled` at `0x140018ca6`
- `ntoskrnl!EtwProviderEnabled` at `0x140018c78`
- `ntoskrnl!EtwProviderEnabled` at `0x140018ca6`

## pseudocode

```c
__int64 __fastcall RxTdiReceiveEventHandler(
        __int64 a1,
        __int64 a2,
        int a3,
        unsigned int a4,
        __int64 a5,
        _DWORD *a6,
        __int64 a7,
        __int64 a8)
{
  unsigned int v11; // ebx
  __int16 v13; // bx
  const GUID *ActivityIdThread; // rax
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rax
  unsigned int v18; // eax
  void (__fastcall *v19)(__int64, __int64, _QWORD, __int64); // rax
  __int64 v20; // [rsp+28h] [rbp-D0h]
  int v21; // [rsp+64h] [rbp-94h] BYREF
  __int64 v22; // [rsp+68h] [rbp-90h] BYREF
  __int64 v23; // [rsp+70h] [rbp-88h] BYREF
  __int128 v24; // [rsp+78h] [rbp-80h] BYREF
  _DWORD v25[2]; // [rsp+88h] [rbp-70h] BYREF
  __int64 v26; // [rsp+90h] [rbp-68h]
  __int128 v27; // [rsp+98h] [rbp-60h]
  __int128 v28; // [rsp+A8h] [rbp-50h]

  v23 = 0;
  v21 = 0;
  v22 = 0;
  if ( (a3 & 0x10) != 0 )
    return (unsigned int)-1073741285;
  v16 = *(_QWORD *)(a2 + 392);
  v11 = -1073741823;
  if ( !v16 )
    return v11;
  if ( !*(_QWORD *)(v16 + 16) )
  {
LABEL_15:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, &WPP_a3674ba4389c303a46b98dfefa03da15_Traceguids, v11);
    }
    return v11;
  }
  v24 = 0;
  if ( (byte_1400712C4 & 0x20) != 0 )
  {
    v13 = *(_WORD *)(a2 + 320);
    if ( EtwProviderEnabled(REMOTEFS_SMB_Context, 0, 0x200000000uLL) )
    {
      EtwProviderEnabled(REMOTEFS_SMB_Context, 0, 0x800000000000uLL);
      ActivityIdThread = (const GUID *)IoGetActivityIdThread();
      if ( !ActivityIdThread )
      {
        v24 = (unsigned __int64)_InterlockedIncrement64(&Correlation);
        ActivityIdThread = (const GUID *)&v24;
      }
      Template_qqbqb_ex(REMOTEFS_SMB_Context, v15, 0x200000000LL, ActivityIdThread, v13, v20, a2 + 428, 0, a7);
    }
  }
  v17 = *(_QWORD *)(a2 + 392);
  v25[0] = a3;
  v25[1] = 0;
  v27 = 0;
  v26 = -1;
  v28 = 0;
  v18 = (*(__int64 (__fastcall **)(__int64, _DWORD *, _QWORD, _QWORD, _QWORD, _DWORD *, __int64, __int64 *, __int64 *, int *))(v17 + 16))(
          a2,
          v25,
          a4,
          (unsigned int)a5,
          0,
          a6,
          a7,
          &v23,
          &v22,
          &v21);
  v11 = v18;
  if ( v18 != -1073741802 )
  {
    if ( v18 == -1073741285 || !v18 )
      return v11;
    goto LABEL_15;
  }
  if ( (_DWORD)a5 == *a6 )
  {
    v19 = *(void (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)(a2 + 392) + 24LL);
    if ( v19 )
      v19(a2, v22, 0, 3221225667LL);
    return 0;
  }
  else
  {
    return (unsigned int)ReceiveEventPostProcessing(a2, v23, v22, v21, a8);
  }
}

```

## disassembly

```asm
0x140018bb0  mov     [rsp+arg_0], rbx
0x140018bb5  push    rbp
0x140018bb6  push    rsi
0x140018bb7  push    rdi
0x140018bb8  push    r12
0x140018bba  push    r13
0x140018bbc  push    r14
0x140018bbe  push    r15
0x140018bc0  sub     rsp, 0C0h
0x140018bc7  mov     rax, cs:__security_cookie
0x140018bce  xor     rax, rsp
0x140018bd1  mov     [rsp+0F8h+var_40], rax
0x140018bd9  mov     r14, [rsp+0F8h+arg_28]
0x140018be1  xor     r13d, r13d
0x140018be4  mov     rbp, [rsp+0F8h+arg_30]
0x140018bec  mov     r12d, r9d
0x140018bef  mov     r15, [rsp+0F8h+arg_38]
0x140018bf7  mov     edi, r8d
0x140018bfa  mov     [rsp+0F8h+var_88], r13
0x140018bff  mov     rsi, rdx
0x140018c02  mov     [rsp+0F8h+var_94], r13d
0x140018c07  mov     [rsp+0F8h+var_90], r13
0x140018c0c  test    r8b, 10h
0x140018c10  jz      loc_140018D1F
0x140018c16  mov     ebx, 0C000021Bh
0x140018c1b  mov     eax, ebx
0x140018c1d  mov     rcx, [rsp+0F8h+var_40]
0x140018c25  xor     rcx, rsp; StackCookie
0x140018c28  call    __security_check_cookie
0x140018c2d  mov     rbx, [rsp+0F8h+arg_0]
0x140018c35  add     rsp, 0C0h
0x140018c3c  pop     r15
0x140018c3e  pop     r14
0x140018c40  pop     r13
0x140018c42  pop     r12
0x140018c44  pop     rdi
0x140018c45  pop     rsi
0x140018c46  pop     rbp
0x140018c47  retn
0x140018c49  test    cs:byte_1400712C4, 20h
0x140018c50  xorps   xmm0, xmm0
0x140018c53  movups  [rsp+0F8h+var_80], xmm0
0x140018c58  jz      loc_14005DF78
0x140018c5e  movzx   ebx, word ptr [rdx+140h]
0x140018c65  mov     r8, 200000000h; Keyword
0x140018c6f  mov     rcx, cs:REMOTEFS_SMB_Context; RegHandle
0x140018c76  xor     edx, edx; Level
0x140018c78  call    cs:__imp_EtwProviderEnabled
0x140018c7f  nop     dword ptr [rax+rax+00h]
0x140018c84  test    al, al
0x140018c86  jz      loc_14005DF78
0x140018c8c  mov     rcx, cs:REMOTEFS_SMB_Context; RegHandle
0x140018c93  lea     r13, [rsi+1ACh]
0x140018c9a  xor     edx, edx; Level
0x140018c9c  mov     r8, 800000000000h; Keyword
0x140018ca6  call    cs:__imp_EtwProviderEnabled
0x140018cad  nop     dword ptr [rax+rax+00h]
0x140018cb2  call    cs:__imp_IoGetActivityIdThread
0x140018cb9  nop     dword ptr [rax+rax+00h]
0x140018cbe  mov     ecx, ebx
0x140018cc0  test    rax, rax
0x140018cc3  jnz     short loc_140018CE8
0x140018cc5  xorps   xmm0, xmm0
0x140018cc8  mov     eax, 1
0x140018ccd  movups  [rsp+0F8h+var_80], xmm0
0x140018cd2  lock xadd cs:Correlation, rax
0x140018cdb  inc     rax
0x140018cde  mov     qword ptr [rsp+0F8h+var_80], rax
0x140018ce3  lea     rax, [rsp+0F8h+var_80]
0x140018ce8  mov     [rsp+0F8h+var_B8], rbp
0x140018ced  mov     r9, rax
0x140018cf0  mov     dword ptr [rsp+0F8h+var_C0], 0
0x140018cf8  mov     r8, 200000000h
0x140018d02  mov     [rsp+0F8h+var_C8], r13
0x140018d07  mov     dword ptr [rsp+0F8h+var_D8], ecx
0x140018d0b  mov     rcx, cs:REMOTEFS_SMB_Context
0x140018d12  call    Template_qqbqb_ex
0x140018d17  xor     r13d, r13d
0x140018d1a  jmp     loc_14005DF78
0x140018d1f  mov     rax, [rdx+188h]
0x140018d26  mov     ebx, 0C0000001h
0x140018d2b  test    rax, rax
0x140018d2e  jz      loc_140018C1B
0x140018d34  cmp     [rax+10h], r13
0x140018d38  jz      loc_14005E01C
0x140018d3e  jmp     loc_140018C49
0x14005df78  mov     rax, [rsi+188h]
0x14005df7f  lea     rcx, [rsp+0F8h+var_94]
0x14005df84  mov     [rsp+0F8h+var_B0], rcx
0x14005df89  lea     rdx, [rsp+0F8h+var_70]
0x14005df91  mov     [rsp+0F8h+var_70], edi
0x14005df98  lea     rcx, [rsp+0F8h+var_90]
0x14005df9d  mov     edi, dword ptr [rsp+0F8h+arg_20]
0x14005dfa4  xorps   xmm0, xmm0
0x14005dfa7  mov     [rsp+0F8h+var_B8], rcx
0x14005dfac  xorps   xmm1, xmm1
0x14005dfaf  lea     rcx, [rsp+0F8h+var_88]
0x14005dfb4  mov     [rsp+0F8h+var_6C], r13d
0x14005dfbc  mov     [rsp+0F8h+var_C0], rcx
0x14005dfc1  mov     r9d, edi
0x14005dfc4  mov     [rsp+0F8h+var_C8], rbp
0x14005dfc9  mov     r8d, r12d
0x14005dfcc  movdqu  [rsp+0F8h+var_60], xmm0
0x14005dfd5  mov     [rsp+0F8h+var_68], 0FFFFFFFFFFFFFFFFh
0x14005dfe1  mov     rcx, rsi
0x14005dfe4  movdqu  [rsp+0F8h+var_50], xmm1
0x14005dfed  mov     rax, [rax+10h]
0x14005dff1  mov     [rsp+0F8h+var_D0], r14
0x14005dff6  mov     [rsp+0F8h+var_D8], r13
0x14005dffb  call    _guard_dispatch_icall
0x14005e000  mov     ebx, eax
0x14005e002  cmp     eax, 0C0000016h
0x14005e007  jz      short loc_14005E066
0x14005e009  cmp     eax, 0C000021Bh
0x14005e00e  jz      loc_140018C1B
0x14005e014  test    eax, eax
0x14005e016  jz      loc_140018C1B
0x14005e01c  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e023  lea     rax, WPP_GLOBAL_Control
0x14005e02a  cmp     rcx, rax
0x14005e02d  jz      loc_140018C1B
0x14005e033  mov     eax, [rcx+2Ch]
0x14005e036  test    al, 4
0x14005e038  jz      loc_140018C1B
0x14005e03e  cmp     byte ptr [rcx+29h], 4
0x14005e042  jb      loc_140018C1B
0x14005e048  mov     rcx, [rcx+18h]
0x14005e04c  lea     r8, WPP_a3674ba4389c303a46b98dfefa03da15_Traceguids
0x14005e053  mov     edx, 0Bh
0x14005e058  mov     r9d, ebx
0x14005e05b  call    WPP_SF_d
0x14005e060  nop
0x14005e061  jmp     loc_140018C1B
0x14005e066  cmp     edi, [r14]
0x14005e069  jnz     short loc_14005E099
0x14005e06b  mov     rax, [rsi+188h]
0x14005e072  mov     rax, [rax+18h]
0x14005e076  test    rax, rax
0x14005e079  jz      short loc_14005E091
0x14005e07b  mov     rdx, [rsp+0F8h+var_90]
0x14005e080  mov     r9d, 0C00000C3h
0x14005e086  xor     r8d, r8d
0x14005e089  mov     rcx, rsi
0x14005e08c  call    _guard_dispatch_icall
0x14005e091  mov     ebx, r13d
0x14005e094  jmp     loc_140018C1B
0x14005e099  mov     r9d, [rsp+0F8h+var_94]
0x14005e09e  mov     rcx, rsi
0x14005e0a1  mov     r8, [rsp+0F8h+var_90]
0x14005e0a6  mov     rdx, [rsp+0F8h+var_88]
0x14005e0ab  mov     [rsp+0F8h+var_D8], r15
0x14005e0b0  call    ReceiveEventPostProcessing
0x14005e0b5  mov     ebx, eax
0x14005e0b7  jmp     loc_140018C1B
```
