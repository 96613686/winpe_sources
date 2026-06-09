# CAlpcPort::AlpcPost(CMsgStruct *,void *)

- ea: `0x180036d1c`
- end: `0x180036f74`
- name: `?AlpcPost@CAlpcPort@@QEAAJPEAVCMsgStruct@@PEAX@Z`
- size: `600`
- prototype: `__int64 __fastcall(CAlpcPort *__hidden this, struct CMsgStruct *, void *)`
- caller_count: `19`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18002b300`
- `0x1800319d0`
- `0x180031e1c`
- `0x180032438`
- `0x1800343e4`
- `0x180035004`
- `0x1800361d4`
- `0x180036fe0`
- `0x18003dd90`
- `0x180043a20`
- `0x18009188c`
- `0x1800924d0`
- `0x180094c34`
- `0x180096fc0`
- `0x1800c26d0`
- `0x1800c2990`
- `0x1800c2d90`
- `0x1800c31a0`
- `0x1800c3970`

## callees

- `0x180036d1c`
- `0x180036f7c`
- `0x18009eaea`
- `0x180106a60`
- `0x18010a010`

## import_xrefs

- `ntdll!NtAlpcCreatePortSection` at `0x180036ef7`
- `ntdll!NtAlpcCreatePortSection` at `0x180036ef7`
- `ntdll!NtAlpcCreateSectionView` at `0x180036f33`
- `ntdll!NtAlpcCreateSectionView` at `0x180036f33`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180036e72`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180036e72`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036d7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036dd2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036d7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036dd2`

## pseudocode

```c
__int64 __fastcall CAlpcPort::AlpcPost(CAlpcPort *this, struct CMsgStruct *a2, void *a3)
{
  __int64 v6; // rax
  int v7; // edi
  __int64 v8; // rbx
  __int16 v9; // di
  int v10; // ebx
  __int64 v12; // rcx
  __int64 v13; // rax
  unsigned int v14; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v16; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD v17[11]; // [rsp+60h] [rbp-A0h] BYREF
  DWORD CurrentThreadId; // [rsp+8Ch] [rbp-74h]
  int v19; // [rsp+9Ch] [rbp-64h]
  _BYTE *v20; // [rsp+A0h] [rbp-60h]
  _BYTE v21[440]; // [rsp+A8h] [rbp-58h] BYREF

  if ( !*((_QWORD *)this + 1) )
    return (unsigned int)-2147467259;
  memset_0(v17, 0, 0x48u);
  v17[0] = 4718624;
  CurrentThreadId = GetCurrentThreadId();
  memset_0(v21, 0, sizeof(v21));
  v6 = *(_QWORD *)a2;
  v14 = 0;
  v7 = (*(__int64 (__fastcall **)(struct CMsgStruct *, unsigned int *))(v6 + 40))(a2, &v14);
  if ( v7 >= 0 )
  {
    v8 = v14;
    v9 = v14 + 72;
    if ( v14 + 72 != (__int16)(v14 + 72) )
      return (unsigned int)-2147418113;
    CurrentThreadId = GetCurrentThreadId();
    *(_DWORD *)(*((_QWORD *)this + 2) + 4LL) = 0;
    if ( (unsigned int)v8 > 0x1B8 )
    {
      v12 = *((_QWORD *)this + 1);
      HIWORD(v17[0]) = 72;
      v20 = 0;
      v15 = 0;
      v16 = 0;
      if ( !(unsigned int)NtAlpcCreatePortSection(v12, 0, 0, v8, &v15, &v16) )
      {
        *(_QWORD *)(*((_QWORD *)this + 4) + 8LL) = v15;
        *(_QWORD *)(*((_QWORD *)this + 4) + 16LL) = 0;
        *(_QWORD *)(*((_QWORD *)this + 4) + 24LL) = v8;
        **((_DWORD **)this + 4) = 0;
        if ( (int)NtAlpcCreateSectionView(*((_QWORD *)this + 1), 0, *((_QWORD *)this + 4)) >= 0 )
        {
          v13 = *((_QWORD *)this + 4);
          if ( *(_QWORD *)(v13 + 16) )
          {
            v20 = *(_BYTE **)(v13 + 16);
            *(_DWORD *)v13 = 0x20000;
            *(_DWORD *)(*((_QWORD *)this + 2) + 4LL) |= 0x40000000u;
          }
        }
      }
    }
    else
    {
      HIWORD(v17[0]) = v9;
      v20 = v21;
    }
    v19 = v8;
    LOWORD(v17[0]) = HIWORD(v17[0]) - 40;
    if ( (_DWORD)v8 )
    {
      if ( !v20 )
        return (unsigned int)-2147467259;
    }
    v7 = (*(__int64 (__fastcall **)(struct CMsgStruct *, _DWORD *))(*(_QWORD *)a2 + 16LL))(a2, v17);
    if ( v7 >= 0 )
    {
      if ( a3 )
      {
        *(_QWORD *)(*((_QWORD *)this + 3) + 8LL) = a3;
        *(_DWORD *)(*((_QWORD *)this + 2) + 4LL) |= 0x20000000u;
      }
      v10 = NtAlpcSendWaitReceivePort(
              *((_QWORD *)this + 1),
              (v17[10] >> 8) & 0x10000,
              v17,
              *((_QWORD *)this + 2),
              0,
              0,
              0,
              0);
      CAlpcPort::ClearAlpcDataViewAttr(this);
      if ( v10 )
        return (unsigned int)-2147467259;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180036d1c  mov     [rsp-8+arg_10], rbx
0x180036d21  push    rbp
0x180036d22  push    rsi
0x180036d23  push    rdi
0x180036d24  push    r12
0x180036d26  push    r13
0x180036d28  push    r14
0x180036d2a  push    r15
0x180036d2c  lea     rbp, [rsp-170h]
0x180036d34  sub     rsp, 270h
0x180036d3b  mov     rax, cs:__security_cookie
0x180036d42  xor     rax, rsp
0x180036d45  mov     [rbp+1A0h+var_40], rax
0x180036d4c  xor     r12d, r12d
0x180036d4f  mov     r14, r8
0x180036d52  mov     r15, rdx
0x180036d55  mov     rsi, rcx
0x180036d58  cmp     [rcx+8], r12
0x180036d5c  jz      loc_180036E86
0x180036d62  lea     r13d, [r12+48h]
0x180036d67  xor     edx, edx; Val
0x180036d69  mov     r8d, r13d; Size
0x180036d6c  lea     rcx, [rsp+2A0h+var_240]; void *
0x180036d71  call    memset_0
0x180036d76  mov     [rsp+2A0h+var_240], 480020h
0x180036d7e  call    cs:__imp_GetCurrentThreadId
0x180036d84  xor     edx, edx; Val
0x180036d86  lea     rcx, [rbp+1A0h+var_1F8]; void *
0x180036d8a  mov     r8d, 1B8h; Size
0x180036d90  mov     [rbp+1A0h+var_214], eax
0x180036d93  call    memset_0
0x180036d98  mov     rax, [r15]
0x180036d9b  lea     rdx, [rsp+2A0h+var_260]
0x180036da0  mov     rcx, r15
0x180036da3  mov     [rsp+2A0h+var_260], r12d
0x180036da8  mov     rax, [rax+28h]
0x180036dac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036db1  mov     edi, eax
0x180036db3  test    eax, eax
0x180036db5  js      loc_180036E8B
0x180036dbb  mov     ebx, [rsp+2A0h+var_260]
0x180036dbf  lea     eax, [rbx+r13]
0x180036dc3  movzx   edi, ax
0x180036dc6  lea     ecx, [rbx+48h]
0x180036dc9  cwde
0x180036dca  cmp     ecx, eax
0x180036dcc  jnz     loc_180036F6A
0x180036dd2  call    cs:__imp_GetCurrentThreadId
0x180036dd8  mov     [rbp+1A0h+var_214], eax
0x180036ddb  mov     rax, [rsi+10h]
0x180036ddf  mov     [rax+4], r12d
0x180036de3  cmp     ebx, 1B8h
0x180036de9  ja      loc_180036EC3
0x180036def  lea     rax, [rbp+1A0h+var_1F8]
0x180036df3  mov     word ptr [rsp+2A0h+var_240+2], di
0x180036df8  mov     [rbp+1A0h+var_200], rax
0x180036dfc  movzx   eax, word ptr [rsp+2A0h+var_240+2]
0x180036e01  sub     ax, 28h ; '('
0x180036e05  mov     [rbp+1A0h+var_204], ebx
0x180036e08  mov     word ptr [rsp+2A0h+var_240], ax
0x180036e0d  test    ebx, ebx
0x180036e0f  jnz     loc_180036EB7
0x180036e15  mov     rax, [r15]
0x180036e18  lea     rdx, [rsp+2A0h+var_240]
0x180036e1d  mov     rcx, r15
0x180036e20  mov     rax, [rax+10h]
0x180036e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036e29  mov     edi, eax
0x180036e2b  test    eax, eax
0x180036e2d  js      short loc_180036E8B
0x180036e2f  test    r14, r14
0x180036e32  jz      short loc_180036E45
0x180036e34  mov     rax, [rsi+18h]
0x180036e38  mov     [rax+8], r14
0x180036e3c  mov     rax, [rsi+10h]
0x180036e40  bts     dword ptr [rax+4], 1Dh
0x180036e45  mov     edx, [rbp+1A0h+var_218]
0x180036e48  lea     r8, [rsp+2A0h+var_240]
0x180036e4d  mov     r9, [rsi+10h]
0x180036e51  mov     rcx, [rsi+8]
0x180036e55  mov     [rsp+2A0h+var_268], r12
0x180036e5a  shr     edx, 8
0x180036e5d  mov     [rsp+2A0h+var_270], r12
0x180036e62  and     edx, 10000h
0x180036e68  mov     [rsp+2A0h+var_278], r12
0x180036e6d  mov     [rsp+2A0h+var_280], r12
0x180036e72  call    cs:__imp_NtAlpcSendWaitReceivePort
0x180036e78  mov     rcx, rsi; this
0x180036e7b  mov     ebx, eax
0x180036e7d  call    ?ClearAlpcDataViewAttr@CAlpcPort@@IEAAXXZ; CAlpcPort::ClearAlpcDataViewAttr(void)
0x180036e82  test    ebx, ebx
0x180036e84  jz      short loc_180036E8B
0x180036e86  mov     edi, 80004005h
0x180036e8b  mov     eax, edi
0x180036e8d  mov     rcx, [rbp+1A0h+var_40]
0x180036e94  xor     rcx, rsp; StackCookie
0x180036e97  call    __security_check_cookie
0x180036e9c  mov     rbx, [rsp+2A0h+arg_10]
0x180036ea4  add     rsp, 270h
0x180036eab  pop     r15
0x180036ead  pop     r14
0x180036eaf  pop     r13
0x180036eb1  pop     r12
0x180036eb3  pop     rdi
0x180036eb4  pop     rsi
0x180036eb5  pop     rbp
0x180036eb6  retn
0x180036eb7  cmp     [rbp+1A0h+var_200], r12
0x180036ebb  jnz     loc_180036E15
0x180036ec1  jmp     short loc_180036E86
0x180036ec3  mov     rcx, [rsi+8]
0x180036ec7  lea     rax, [rsp+2A0h+var_250]
0x180036ecc  mov     [rsp+2A0h+var_278], rax
0x180036ed1  mov     r9, rbx
0x180036ed4  lea     rax, [rsp+2A0h+var_258]
0x180036ed9  mov     word ptr [rsp+2A0h+var_240+2], r13w
0x180036edf  xor     r8d, r8d
0x180036ee2  mov     [rsp+2A0h+var_280], rax
0x180036ee7  xor     edx, edx
0x180036ee9  mov     [rbp+1A0h+var_200], r12
0x180036eed  mov     [rsp+2A0h+var_258], r12
0x180036ef2  mov     [rsp+2A0h+var_250], r12
0x180036ef7  call    cs:__imp_NtAlpcCreatePortSection
0x180036efd  test    eax, eax
0x180036eff  jnz     loc_180036DFC
0x180036f05  mov     rcx, [rsi+20h]
0x180036f09  xor     edx, edx
0x180036f0b  mov     rax, [rsp+2A0h+var_258]
0x180036f10  mov     [rcx+8], rax
0x180036f14  mov     rax, [rsi+20h]
0x180036f18  mov     [rax+10h], r12
0x180036f1c  mov     rax, [rsi+20h]
0x180036f20  mov     [rax+18h], rbx
0x180036f24  mov     rax, [rsi+20h]
0x180036f28  mov     [rax], r12d
0x180036f2b  mov     r8, [rsi+20h]
0x180036f2f  mov     rcx, [rsi+8]
0x180036f33  call    cs:__imp_NtAlpcCreateSectionView
0x180036f39  test    eax, eax
0x180036f3b  js      loc_180036DFC
0x180036f41  mov     rax, [rsi+20h]
0x180036f45  mov     rcx, [rax+10h]
0x180036f49  test    rcx, rcx
0x180036f4c  jz      loc_180036DFC
0x180036f52  mov     [rbp+1A0h+var_200], rcx
0x180036f56  mov     dword ptr [rax], 20000h
0x180036f5c  mov     rax, [rsi+10h]
0x180036f60  bts     dword ptr [rax+4], 1Eh
0x180036f65  jmp     loc_180036DFC
0x180036f6a  mov     edi, 8000FFFFh
0x180036f6f  jmp     loc_180036E8B
```
