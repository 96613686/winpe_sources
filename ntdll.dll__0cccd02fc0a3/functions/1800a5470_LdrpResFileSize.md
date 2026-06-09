# LdrpResFileSize

- ea: `0x1800a5470`
- end: `0x1800a5602`
- name: `LdrpResFileSize`
- size: `402`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800a1cc8`
- `0x1800a6dcc`

## callees

- `0x1800526f0`
- `0x1800a5470`
- `0x1800a5b48`
- `0x18015e4f0`
- `0x180162000`

## string_xrefs

- `0x1800a54b9`: `LdrResGetRCConfig Exit`
- `0x1800a54a1`: `LdrResGetRCConfig Enter`

## pseudocode

```c
__int64 __fastcall LdrpResFileSize(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rbp
  __int64 v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rcx
  __int64 result; // rax
  unsigned int v15; // edi
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  _QWORD v20[2]; // [rsp+30h] [rbp-68h] BYREF
  _QWORD v21[2]; // [rsp+40h] [rbp-58h] BYREF
  __int128 v22; // [rsp+50h] [rbp-48h] BYREF
  __int128 v23; // [rsp+60h] [rbp-38h] BYREF
  __int64 v24; // [rsp+70h] [rbp-28h]

  v20[0] = 3145774;
  v24 = 0;
  v21[0] = 3014700;
  v20[1] = L"LdrResGetRCConfig Enter";
  v21[1] = L"LdrResGetRCConfig Exit";
  v22 = 0;
  v23 = 0;
  v10 = 2147353477;
  if ( (unsigned int)RtlGetCurrentServiceSessionId(a1, a2, a3, a4) )
    v11 = (__int64)NtCurrentPeb()->SharedData + 555;
  else
    v11 = 2147353477;
  v12 = 2147353476;
  if ( (*(_BYTE *)v11 & 1) != 0 )
  {
    if ( (unsigned int)RtlGetCurrentServiceSessionId(v7, v6, v8, v9) )
      v13 = (__int64)NtCurrentPeb()->SharedData + 554;
    else
      v13 = 2147353476;
    LdrpTraceLoadMUIDll(v20, *(unsigned __int8 *)v13);
  }
  if ( a2 && (unsigned __int64)(a1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    result = NtQueryInformationFile(a1, &v22, &v23, 24, 5);
    v15 = result;
    if ( (int)result < 0 )
      return result;
    *a2 = *((_QWORD *)&v23 + 1);
  }
  else
  {
    v15 = -1073741811;
  }
  if ( (unsigned int)RtlGetCurrentServiceSessionId(v7, v6, v8, v9) )
    v10 = (__int64)NtCurrentPeb()->SharedData + 555;
  if ( (*(_BYTE *)v10 & 1) != 0 )
  {
    if ( (unsigned int)RtlGetCurrentServiceSessionId(v17, v16, v18, v19) )
      v12 = (__int64)NtCurrentPeb()->SharedData + 554;
    LdrpTraceLoadMUIDll(v21, *(unsigned __int8 *)v12);
  }
  return v15;
}

```

## disassembly

```asm
0x1800a5470  mov     [rsp+arg_10], rbx
0x1800a5475  push    rbp
0x1800a5476  push    rsi
0x1800a5477  push    rdi
0x1800a5478  sub     rsp, 80h
0x1800a547f  mov     rax, cs:__security_cookie
0x1800a5486  xor     rax, rsp
0x1800a5489  mov     [rsp+98h+var_20], rax
0x1800a548e  xor     eax, eax
0x1800a5490  mov     [rsp+98h+var_68], 30002Eh
0x1800a5499  mov     [rsp+98h+var_28], rax
0x1800a549e  xorps   xmm0, xmm0
0x1800a54a1  lea     rax, aLdrresgetrccon_0; "LdrResGetRCConfig Enter"
0x1800a54a8  mov     [rsp+98h+var_58], 2E002Ch
0x1800a54b1  mov     [rsp+98h+var_60], rax
0x1800a54b6  xorps   xmm1, xmm1
0x1800a54b9  lea     rax, aLdrresgetrccon_1; "LdrResGetRCConfig Exit"
0x1800a54c0  mov     rsi, rdx
0x1800a54c3  mov     [rsp+98h+var_50], rax
0x1800a54c8  mov     rdi, rcx
0x1800a54cb  movups  [rsp+98h+var_48], xmm0
0x1800a54d0  movups  [rsp+98h+var_38], xmm1
0x1800a54d5  call    RtlGetCurrentServiceSessionId
0x1800a54da  mov     ebp, 7FFE0385h
0x1800a54df  test    eax, eax
0x1800a54e1  jz      loc_1800A55FA
0x1800a54e7  mov     rax, gs:60h
0x1800a54f0  mov     rax, [rax+90h]
0x1800a54f7  add     rax, 22Bh
0x1800a54fd  test    byte ptr [rax], 1
0x1800a5500  mov     ebx, 7FFE0384h
0x1800a5505  jz      short loc_1800A5538
0x1800a5507  call    RtlGetCurrentServiceSessionId
0x1800a550c  test    eax, eax
0x1800a550e  jz      loc_1800A55F2
0x1800a5514  mov     rax, gs:60h
0x1800a551d  mov     rcx, [rax+90h]
0x1800a5524  add     rcx, 22Ah
0x1800a552b  movzx   edx, byte ptr [rcx]
0x1800a552e  lea     rcx, [rsp+98h+var_68]
0x1800a5533  call    LdrpTraceLoadMUIDll
0x1800a5538  test    rsi, rsi
0x1800a553b  jz      short loc_1800A5577
0x1800a553d  lea     rax, [rdi-1]
0x1800a5541  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800a5545  ja      short loc_1800A5577
0x1800a5547  mov     r9d, 18h
0x1800a554d  mov     [rsp+98h+var_78], 5
0x1800a5555  lea     r8, [rsp+98h+var_38]
0x1800a555a  mov     rcx, rdi
0x1800a555d  lea     rdx, [rsp+98h+var_48]
0x1800a5562  call    NtQueryInformationFile
0x1800a5567  mov     edi, eax
0x1800a5569  test    eax, eax
0x1800a556b  js      short loc_1800A55D1
0x1800a556d  mov     rax, qword ptr [rsp+98h+var_38+8]
0x1800a5572  mov     [rsi], rax
0x1800a5575  jmp     short loc_1800A557C
0x1800a5577  mov     edi, 0C000000Dh
0x1800a557c  call    RtlGetCurrentServiceSessionId
0x1800a5581  test    eax, eax
0x1800a5583  jz      short loc_1800A559C
0x1800a5585  mov     rax, gs:60h
0x1800a558e  mov     rbp, [rax+90h]
0x1800a5595  add     rbp, 22Bh
0x1800a559c  test    byte ptr [rbp+0], 1
0x1800a55a0  jz      short loc_1800A55CF
0x1800a55a2  call    RtlGetCurrentServiceSessionId
0x1800a55a7  test    eax, eax
0x1800a55a9  jz      short loc_1800A55C2
0x1800a55ab  mov     rax, gs:60h
0x1800a55b4  mov     rbx, [rax+90h]
0x1800a55bb  add     rbx, 22Ah
0x1800a55c2  movzx   edx, byte ptr [rbx]
0x1800a55c5  lea     rcx, [rsp+98h+var_58]
0x1800a55ca  call    LdrpTraceLoadMUIDll
0x1800a55cf  mov     eax, edi
0x1800a55d1  mov     rcx, [rsp+98h+var_20]
0x1800a55d6  xor     rcx, rsp; StackCookie
0x1800a55d9  call    __security_check_cookie
0x1800a55de  mov     rbx, [rsp+98h+arg_10]
0x1800a55e6  add     rsp, 80h
0x1800a55ed  pop     rdi
0x1800a55ee  pop     rsi
0x1800a55ef  pop     rbp
0x1800a55f0  retn
0x1800a55f2  mov     rcx, rbx
0x1800a55f5  jmp     loc_1800A552B
0x1800a55fa  mov     rax, rbp
0x1800a55fd  jmp     loc_1800A54FD
```
