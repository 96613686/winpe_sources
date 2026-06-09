# MRxSmbPseudoOpenTailFromFakeGFAResponse

- ea: `0x14004a4a4`
- end: `0x14004a58a`
- name: `MRxSmbPseudoOpenTailFromFakeGFAResponse`
- size: `230`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14003a5f0`
- `0x140047fb0`

## callees

- `0x1400169c0`
- `0x140049870`
- `0x14004a4a4`

## import_xrefs

- `ntoskrnl!ExLocalTimeToSystemTime` at `0x14004a52f`
- `ntoskrnl!ExLocalTimeToSystemTime` at `0x14004a52f`
- `ntoskrnl!RtlSecondsSince1970ToTime` at `0x14004a51a`
- `ntoskrnl!RtlSecondsSince1970ToTime` at `0x14004a51a`

## pseudocode

```c
__int64 __fastcall MRxSmbPseudoOpenTailFromFakeGFAResponse(__int64 a1, int a2)
{
  union _LARGE_INTEGER *v3; // rdi
  int v5; // r8d
  __int64 v6; // r15
  __int64 v7; // rdx
  __int64 v8; // r15
  union _LARGE_INTEGER Time; // [rsp+60h] [rbp+8h] BYREF

  v3 = (union _LARGE_INTEGER *)(a1 + 472);
  memset((void *)(a1 + 472), 0, 0x48u);
  if ( a2 == 1 )
    v5 = 16;
  else
    v5 = 128;
  v3[4].LowPart = v5;
  *(_DWORD *)(a1 + 528) = 1;
  v3->QuadPart = 0;
  v3[1].QuadPart = 0;
  v6 = *(_QWORD *)(a1 + 80);
  Time.QuadPart = 0;
  RtlSecondsSince1970ToTime(0, &Time);
  ExLocalTimeToSystemTime(&Time, v3 + 2);
  v8 = v6 + 400;
  if ( v8 )
    v3[2].QuadPart += *(_QWORD *)(v8 + 40);
  v3[3].QuadPart = 0;
  *(_QWORD *)(a1 + 512) = 0;
  *(_QWORD *)(a1 + 520) = 0;
  *(_BYTE *)(a1 + 533) = (v3[4].LowPart & 0x10) != 0;
  *(_DWORD *)(a1 + 552) = a2;
  return MRxSmbPseudoOpenTailFromGFAResponse(a1, v7);
}

```

## disassembly

```asm
0x14004a4a4  push    rbx
0x14004a4a6  push    rbp
0x14004a4a7  push    rsi
0x14004a4a8  push    rdi
0x14004a4a9  push    r14
0x14004a4ab  push    r15
0x14004a4ad  sub     rsp, 28h
0x14004a4b1  mov     ebp, edx
0x14004a4b3  lea     rdi, [rcx+1D8h]
0x14004a4ba  xor     edx, edx; Val
0x14004a4bc  mov     rsi, rcx
0x14004a4bf  mov     rcx, rdi; void *
0x14004a4c2  lea     r8d, [rdx+48h]; Size
0x14004a4c6  call    memset
0x14004a4cb  lea     rbx, [rsi+200h]
0x14004a4d2  cmp     ebp, 1
0x14004a4d5  jz      short loc_14004A4DF
0x14004a4d7  mov     r8d, 80h
0x14004a4dd  jmp     short loc_14004A4EC
0x14004a4df  xor     eax, eax
0x14004a4e1  cmp     ebp, 1
0x14004a4e4  lea     r8d, [rax+10h]
0x14004a4e8  cmovnz  r8d, eax
0x14004a4ec  mov     [rdi+20h], r8d
0x14004a4f0  lea     rdx, [rsp+58h+Time]; Time
0x14004a4f5  mov     dword ptr [rbx+10h], 1
0x14004a4fc  xor     ecx, ecx; ElapsedSeconds
0x14004a4fe  mov     qword ptr [rdi], 0
0x14004a505  mov     qword ptr [rdi+8], 0
0x14004a50d  mov     r15, [rsi+50h]
0x14004a511  mov     qword ptr [rsp+58h+Time], 0
0x14004a51a  call    cs:__imp_RtlSecondsSince1970ToTime
0x14004a521  nop     dword ptr [rax+rax+00h]
0x14004a526  lea     rdx, [rdi+10h]; SystemTime
0x14004a52a  lea     rcx, [rsp+58h+Time]; LocalTime
0x14004a52f  call    cs:__imp_ExLocalTimeToSystemTime
0x14004a536  nop     dword ptr [rax+rax+00h]
0x14004a53b  add     r15, 190h
0x14004a542  jz      short loc_14004A54C
0x14004a544  mov     rax, [r15+28h]
0x14004a548  add     [rdi+10h], rax
0x14004a54c  mov     qword ptr [rdi+18h], 0
0x14004a554  mov     rcx, rsi
0x14004a557  mov     qword ptr [rbx], 0
0x14004a55e  mov     qword ptr [rbx+8], 0
0x14004a566  mov     eax, [rdi+20h]
0x14004a569  shr     eax, 4
0x14004a56c  and     al, 1
0x14004a56e  mov     [rbx+15h], al
0x14004a571  mov     [rsi+228h], ebp
0x14004a577  call    MRxSmbPseudoOpenTailFromGFAResponse
0x14004a57c  add     rsp, 28h
0x14004a580  pop     r15
0x14004a582  pop     r14
0x14004a584  pop     rdi
0x14004a585  pop     rsi
0x14004a586  pop     rbp
0x14004a587  pop     rbx
0x14004a588  retn
```
