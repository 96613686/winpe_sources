# HbEvtpProcessSystemDiagLog

- ea: `0x140013ef0`
- end: `0x140014057`
- name: `HbEvtpProcessSystemDiagLog`
- size: `359`
- prototype: `void __fastcall(char)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000e010`
- `0x140013480`

## callees

- `0x140001230`
- `0x140012c40`
- `0x140013ef0`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14001402c`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001402c`
- `ntoskrnl!ExTryToAcquireFastMutex` at `0x140013f39`
- `ntoskrnl!ExTryToAcquireFastMutex` at `0x140013f39`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140013f0b`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140013f0b`
- `ntoskrnl!ExAcquireFastMutex` at `0x140013f2b`
- `ntoskrnl!ExAcquireFastMutex` at `0x140013f2b`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14001403f`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14001403f`

## pseudocode

```c
void __fastcall HbEvtpProcessSystemDiagLog(char a1)
{
  __int64 *v2; // rbx
  unsigned int v3; // r8d
  unsigned int v4; // eax
  unsigned __int64 v5; // r9
  __int64 v6; // rdx
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // [rsp+38h] [rbp+10h] BYREF
  __int64 *v9; // [rsp+40h] [rbp+18h] BYREF

  v9 = 0;
  if ( ExAcquireRundownProtection(&stru_140009408) )
  {
    if ( a1 )
    {
      ExAcquireFastMutex(&stru_140009428);
    }
    else if ( !ExTryToAcquireFastMutex(&stru_140009428) )
    {
LABEL_22:
      ExReleaseRundownProtection(&stru_140009408);
      return;
    }
    if ( (int)HbEvtpGetLogConfiguration(2, &v9) >= 0 )
    {
      v2 = v9;
LABEL_7:
      v8 = 0;
      do
      {
        v3 = dword_14000948C;
        if ( dword_14000948C == -1 )
        {
          v4 = 0;
          v5 = -1;
          if ( !*((_DWORD *)v2 + 2) )
            break;
          do
          {
            v6 = *(_QWORD *)(112LL * v4 + v2[4]);
            v7 = *(_QWORD *)(v6 + 16);
            if ( v7 > qword_140009480 && v7 < v5 )
            {
              v5 = *(_QWORD *)(v6 + 16);
              v3 = v4;
            }
            ++v4;
          }
          while ( v4 < *((_DWORD *)v2 + 2) );
          if ( v3 == -1 )
          {
            v3 = dword_14000948C;
          }
          else
          {
            dword_14000948C = v3;
            qword_140009480 = v5;
            dword_140009488 = 72;
          }
          if ( v3 == -1 )
            break;
        }
        if ( !(unsigned __int8)HbEvtpProcessSystemDiagLogBuffer(v2, v2[4] + 112LL * v3, &v8) )
          break;
        if ( a1 )
          goto LABEL_7;
      }
      while ( v8 < 0x1F4 );
    }
    ExReleaseFastMutex(&stru_140009428);
    goto LABEL_22;
  }
}

```

## disassembly

```asm
0x140013ef0  mov     [rsp+arg_18], rsi
0x140013ef5  push    rdi
0x140013ef6  sub     rsp, 20h
0x140013efa  movzx   edi, cl
0x140013efd  xor     esi, esi
0x140013eff  lea     rcx, stru_140009408; RunRef
0x140013f06  mov     [rsp+28h+arg_10], rsi
0x140013f0b  call    cs:__imp_ExAcquireRundownProtection
0x140013f12  nop     dword ptr [rax+rax+00h]
0x140013f17  test    al, al
0x140013f19  jz      loc_14001404B
0x140013f1f  lea     rcx, stru_140009428; FastMutex
0x140013f26  test    dil, dil
0x140013f29  jz      short loc_140013F39
0x140013f2b  call    cs:__imp_ExAcquireFastMutex
0x140013f32  nop     dword ptr [rax+rax+00h]
0x140013f37  jmp     short loc_140013F4D
0x140013f39  call    cs:__imp_ExTryToAcquireFastMutex
0x140013f40  nop     dword ptr [rax+rax+00h]
0x140013f45  test    al, al
0x140013f47  jz      loc_140014038
0x140013f4d  lea     rdx, [rsp+28h+arg_10]
0x140013f52  mov     ecx, 2
0x140013f57  call    HbEvtpGetLogConfiguration
0x140013f5c  test    eax, eax
0x140013f5e  js      loc_140014025
0x140013f64  mov     [rsp+28h+arg_0], rbx
0x140013f69  mov     rbx, [rsp+28h+arg_10]
0x140013f6e  mov     [rsp+28h+arg_8], rsi
0x140013f73  mov     r8d, cs:dword_14000948C
0x140013f7a  cmp     r8d, 0FFFFFFFFh
0x140013f7e  jnz     short loc_140013FEC
0x140013f80  mov     eax, esi
0x140013f82  mov     r9, 0FFFFFFFFFFFFFFFFh
0x140013f89  cmp     [rbx+8], eax
0x140013f8c  jbe     loc_140014020
0x140013f92  mov     ecx, eax
0x140013f94  imul    rdx, rcx, 70h ; 'p'
0x140013f98  mov     rcx, [rbx+20h]
0x140013f9c  mov     rdx, [rdx+rcx]
0x140013fa0  mov     rcx, [rdx+10h]
0x140013fa4  cmp     rcx, cs:qword_140009480
0x140013fab  jbe     short loc_140013FB8
0x140013fad  cmp     rcx, r9
0x140013fb0  jnb     short loc_140013FB8
0x140013fb2  mov     r9, rcx
0x140013fb5  mov     r8d, eax
0x140013fb8  inc     eax
0x140013fba  cmp     eax, [rbx+8]
0x140013fbd  jb      short loc_140013F92
0x140013fbf  cmp     r8d, 0FFFFFFFFh
0x140013fc3  jz      short loc_140013FDF
0x140013fc5  mov     cs:dword_14000948C, r8d
0x140013fcc  mov     cs:qword_140009480, r9
0x140013fd3  mov     cs:dword_140009488, 48h ; 'H'
0x140013fdd  jmp     short loc_140013FE6
0x140013fdf  mov     r8d, cs:dword_14000948C
0x140013fe6  cmp     r8d, 0FFFFFFFFh
0x140013fea  jz      short loc_140014020
0x140013fec  mov     eax, r8d
0x140013fef  mov     rcx, rbx
0x140013ff2  imul    rdx, rax, 70h ; 'p'
0x140013ff6  lea     r8, [rsp+28h+arg_8]
0x140013ffb  add     rdx, [rbx+20h]
0x140013fff  call    HbEvtpProcessSystemDiagLogBuffer
0x140014004  test    al, al
0x140014006  jz      short loc_140014020
0x140014008  test    dil, dil
0x14001400b  jnz     loc_140013F6E
0x140014011  cmp     [rsp+28h+arg_8], 1F4h
0x14001401a  jb      loc_140013F73
0x140014020  mov     rbx, [rsp+28h+arg_0]
0x140014025  lea     rcx, stru_140009428; FastMutex
0x14001402c  call    cs:__imp_ExReleaseFastMutex
0x140014033  nop     dword ptr [rax+rax+00h]
0x140014038  lea     rcx, stru_140009408; RunRef
0x14001403f  call    cs:__imp_ExReleaseRundownProtection
0x140014046  nop     dword ptr [rax+rax+00h]
0x14001404b  mov     rsi, [rsp+28h+arg_18]
0x140014050  add     rsp, 20h
0x140014054  pop     rdi
0x140014055  retn
```
