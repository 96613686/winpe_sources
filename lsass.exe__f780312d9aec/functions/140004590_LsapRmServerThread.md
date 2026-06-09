# LsapRmServerThread

- ea: `0x140004590`
- end: `0x14000471c`
- name: `LsapRmServerThread`
- size: `396`
- prototype: `void __fastcall __noreturn(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002a02`
- `0x140004590`
- `0x140006010`

## import_xrefs

- `ntdll!NtAlpcCancelMessage` at `0x140004707`
- `ntdll!NtAlpcCancelMessage` at `0x140004707`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x140004643`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x140004643`

## pseudocode

```c
void __fastcall __noreturn LsapRmServerThread(PVOID Parameter)
{
  int *v1; // rbx
  __int16 v2; // di
  int v3; // eax
  __int64 v4; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v5[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v6; // [rsp+68h] [rbp-98h]
  int v7; // [rsp+70h] [rbp-90h] BYREF
  __int16 v8; // [rsp+74h] [rbp-8Ch]
  __int128 v9; // [rsp+76h] [rbp-8Ah]
  __int128 v10; // [rsp+86h] [rbp-7Ah]
  __int16 v11; // [rsp+96h] [rbp-6Ah]
  _DWORD v12[118]; // [rsp+98h] [rbp-68h] BYREF
  int v13; // [rsp+270h] [rbp+170h] BYREF
  __int16 v14; // [rsp+274h] [rbp+174h]
  __int128 v15; // [rsp+276h] [rbp+176h]
  __int128 v16; // [rsp+286h] [rbp+186h]
  __int16 v17; // [rsp+296h] [rbp+196h]

  memset_0(&v13, 0, 0x200u);
  memset_0(&v7, 0, 0x200u);
  while ( 1 )
  {
LABEL_2:
    v1 = 0;
    while ( 1 )
    {
      v6 = 0;
      v4 = 512;
      memset(v5, 0, sizeof(v5));
      LODWORD(v5[0]) = 0x20000000;
      if ( (int)((__int64 (__fastcall *)(__int64, _QWORD, int *, _QWORD, int *, __int64 *, _OWORD *, _QWORD))NtAlpcSendWaitReceivePort)(
                  gLsapCommandPortHandle,
                  v1 != 0 ? 0x10000 : 0,
                  v1,
                  0,
                  &v13,
                  &v4,
                  v5,
                  0) < 0 )
        break;
      v2 = v14;
      if ( (((unsigned __int8)v14 - 1) & 0xFFFFFFFD) != 0 )
        goto LABEL_9;
      memset_0(v12, 0, sizeof(v12));
      v7 = v13;
      v11 = v17;
      v3 = gLsapRmExtension;
      v8 = v2;
      v9 = v15;
      v10 = v16;
      if ( gLsapRmExtension )
      {
        v3 = (*(__int64 (__fastcall **)(int *, int *))gLsapRmExtension)(&v13, &v7);
        if ( v3 == 259 )
          goto LABEL_2;
        v2 = v14;
      }
      v12[0] = v3;
      if ( (unsigned __int8)v2 == 3 )
      {
LABEL_9:
        v1 = 0;
        if ( (v2 & 0x2000) != 0 )
          NtAlpcCancelMessage(gLsapCommandPortHandle, 0, (char *)v5 + 8);
      }
      else
      {
        v1 = &v7;
      }
    }
  }
}

```

## disassembly

```asm
0x140004590  push    rbp
0x140004592  push    rbx
0x140004593  push    rdi
0x140004594  push    r14
0x140004596  lea     rbp, [rsp-388h]
0x14000459e  sub     rsp, 488h
0x1400045a5  mov     rax, cs:__security_cookie
0x1400045ac  xor     rax, rsp
0x1400045af  mov     [rbp+3A0h+var_30], rax
0x1400045b6  mov     r14d, 200h
0x1400045bc  lea     rcx, [rbp+3A0h+var_230]; void *
0x1400045c3  mov     r8d, r14d; Size
0x1400045c6  xor     edx, edx; Val
0x1400045c8  call    memset_0
0x1400045cd  mov     r8d, r14d; Size
0x1400045d0  lea     rcx, [rsp+4A0h+var_430]; void *
0x1400045d5  xor     edx, edx; Val
0x1400045d7  call    memset_0
0x1400045dc  xor     ebx, ebx
0x1400045de  mov     rcx, cs:gLsapCommandPortHandle
0x1400045e5  xor     eax, eax
0x1400045e7  mov     [rsp+4A0h+var_438], rax
0x1400045ec  xorps   xmm0, xmm0
0x1400045ef  sub     rax, rbx
0x1400045f2  mov     [rsp+4A0h+var_468], 0
0x1400045fb  neg     rax
0x1400045fe  mov     [rsp+4A0h+var_460], r14
0x140004603  lea     rax, [rsp+4A0h+var_458]
0x140004608  mov     r8, rbx
0x14000460b  mov     [rsp+4A0h+var_470], rax
0x140004610  sbb     edx, edx
0x140004612  lea     rax, [rsp+4A0h+var_460]
0x140004617  and     edx, 10000h
0x14000461d  mov     [rsp+4A0h+var_478], rax
0x140004622  xor     r9d, r9d
0x140004625  lea     rax, [rbp+3A0h+var_230]
0x14000462c  movups  [rsp+4A0h+var_458], xmm0
0x140004631  mov     [rsp+4A0h+var_480], rax
0x140004636  movups  [rsp+4A0h+var_448], xmm0
0x14000463b  mov     dword ptr [rsp+4A0h+var_458], 20000000h
0x140004643  call    cs:__imp_NtAlpcSendWaitReceivePort
0x140004649  test    eax, eax
0x14000464b  js      short loc_1400045DC
0x14000464d  movzx   edi, [rbp+3A0h+var_22C]
0x140004654  mov     eax, edi
0x140004656  and     eax, 0FFFF00FFh
0x14000465b  dec     eax
0x14000465d  test    eax, 0FFFFFFFDh
0x140004662  jnz     loc_1400046EC
0x140004668  xor     edx, edx; Val
0x14000466a  lea     rcx, [rbp+3A0h+var_408]; void *
0x14000466e  mov     r8d, 1D8h; Size
0x140004674  call    memset_0
0x140004679  mov     eax, [rbp+3A0h+var_230]
0x14000467f  movups  xmm0, [rbp+3A0h+var_22A]
0x140004686  mov     [rsp+4A0h+var_430], eax
0x14000468a  movzx   eax, [rbp+3A0h+var_20A]
0x140004691  movups  xmm1, [rbp+3A0h+var_21A]
0x140004698  mov     [rbp+3A0h+var_40A], ax
0x14000469c  mov     rax, cs:gLsapRmExtension
0x1400046a3  mov     [rsp+4A0h+var_42C], di
0x1400046a8  movups  [rsp+4A0h+var_42A], xmm0
0x1400046ad  movups  [rbp+3A0h+var_41A], xmm1
0x1400046b1  test    rax, rax
0x1400046b4  jz      short loc_1400046DC
0x1400046b6  mov     rax, [rax]
0x1400046b9  lea     rdx, [rsp+4A0h+var_430]
0x1400046be  lea     rcx, [rbp+3A0h+var_230]
0x1400046c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400046ca  cmp     eax, 103h
0x1400046cf  jz      loc_1400045DC
0x1400046d5  movzx   edi, [rbp+3A0h+var_22C]
0x1400046dc  mov     [rbp+3A0h+var_408], eax
0x1400046df  movzx   eax, di
0x1400046e2  and     eax, 0FFFF00FFh
0x1400046e7  cmp     eax, 3
0x1400046ea  jnz     short loc_140004712
0x1400046ec  xor     ebx, ebx
0x1400046ee  bt      di, 0Dh
0x1400046f3  jnb     loc_1400045DE
0x1400046f9  mov     rcx, cs:gLsapCommandPortHandle
0x140004700  lea     r8, [rsp+4A0h+var_458+8]
0x140004705  xor     edx, edx
0x140004707  call    cs:__imp_NtAlpcCancelMessage
0x14000470d  jmp     loc_1400045DE
0x140004712  lea     rbx, [rsp+4A0h+var_430]
0x140004717  jmp     loc_1400045DE
```
