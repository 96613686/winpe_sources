# _ProcessDeviceFinished_0

- ea: `0x180004368`
- end: `0x1800044a2`
- name: `_ProcessDeviceFinished_0`
- size: `314`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000409c`

## callees

- `0x1800027dc`
- `0x180002888`
- `0x180004368`
- `0x18000490c`
- `0x180005020`
- `0x1800067e0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x180004427`
- `ntoskrnl!RtlCompareMemory` at `0x18000446e`
- `ntoskrnl!RtlCompareMemory` at `0x180004427`
- `ntoskrnl!RtlCompareMemory` at `0x18000446e`

## pseudocode

```c
_BOOL8 __fastcall ProcessDeviceFinished_0(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v3; // rbx
  __int64 v5; // rcx
  __int128 v6; // xmm1
  _BOOL8 result; // rax
  size_t Size; // [rsp+30h] [rbp-89h]
  __int128 v9; // [rsp+40h] [rbp-79h] BYREF
  __int128 v10; // [rsp+50h] [rbp-69h]
  _OWORD v11[2]; // [rsp+60h] [rbp-59h] BYREF
  int v12[8]; // [rsp+80h] [rbp-39h] BYREF
  _BYTE Source1[32]; // [rsp+A0h] [rbp-19h] BYREF
  _BYTE v14[32]; // [rsp+C0h] [rbp+7h] BYREF

  v3 = a1;
  LOBYTE(a1) = 39;
  memset(v11, 0, sizeof(v11));
  v9 = 0;
  v10 = 0;
  result = 0;
  if ( (unsigned int)DevAuth2_ValidateMessageHeader(a1, a2, a2, a3) )
  {
    v5 = *(_QWORD *)(v3 + 1096);
    if ( v5 )
    {
      if ( (unsigned int)DevAuthGetRunningHash(v5, v12) )
      {
        if ( v3 != -1048 )
        {
          LODWORD(Size) = 32;
          if ( (unsigned int)DevAuthPesudoRandomFunction(
                               (int)"Device Finished",
                               (int)v3 + 1048,
                               48,
                               (int)v12,
                               32,
                               Source1,
                               Size) )
          {
            if ( RtlCompareMemory(Source1, (const void *)(a2 + 4), 0x20u) == 32 )
            {
              v6 = *(_OWORD *)(v3 + 308);
              v9 = *(_OWORD *)(v3 + 292);
              v10 = v6;
              GetMsftVerifyData(a2 + 4, v11, &v9, v14);
              if ( RtlCompareMemory(v14, (const void *)(a2 + 36), 0x20u) == 32 )
                return 1;
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004368  push    rbp
0x18000436a  push    rbx
0x18000436b  push    rsi
0x18000436c  push    rdi
0x18000436d  push    r14
0x18000436f  lea     rbp, [rsp-37h]
0x180004374  sub     rsp, 0F0h
0x18000437b  mov     rax, cs:__security_cookie
0x180004382  xor     rax, rsp
0x180004385  mov     [rbp+57h+var_30], rax
0x180004389  mov     rbx, rcx
0x18000438c  xorps   xmm0, xmm0
0x18000438f  xorps   xmm1, xmm1
0x180004392  mov     r9d, r8d
0x180004395  mov     r8, rdx
0x180004398  mov     cl, 27h ; '''
0x18000439a  movups  [rbp+57h+var_B0], xmm0
0x18000439e  mov     rsi, rdx
0x1800043a1  movups  [rbp+57h+var_A0], xmm0
0x1800043a5  movups  [rbp+57h+var_D0], xmm1
0x1800043a9  movups  [rbp+57h+var_C0], xmm1
0x1800043ad  call    DevAuth2_ValidateMessageHeader
0x1800043b2  test    eax, eax
0x1800043b4  jz      loc_180004485
0x1800043ba  mov     rcx, [rbx+448h]
0x1800043c1  test    rcx, rcx
0x1800043c4  jz      loc_180004485
0x1800043ca  lea     rdx, [rbp+57h+var_90]
0x1800043ce  call    DevAuthGetRunningHash
0x1800043d3  test    eax, eax
0x1800043d5  jz      loc_180004485
0x1800043db  lea     rdx, [rbx+418h]; int
0x1800043e2  test    rdx, rdx
0x1800043e5  jz      loc_180004485
0x1800043eb  mov     r14d, 20h ; ' '
0x1800043f1  lea     rax, [rbp+57h+Source1]
0x1800043f5  mov     dword ptr [rsp+110h+Size], r14d; Size
0x1800043fa  lea     r9, [rbp+57h+var_90]; int
0x1800043fe  mov     [rsp+110h+var_E8], rax; void *
0x180004403  lea     rcx, aDeviceFinished; "Device Finished"
0x18000440a  mov     [rsp+110h+var_F0], r14d; int
0x18000440f  lea     r8d, [r14+10h]; int
0x180004413  call    DevAuthPesudoRandomFunction
0x180004418  test    eax, eax
0x18000441a  jz      short loc_180004485
0x18000441c  mov     r8d, r14d; Length
0x18000441f  lea     rdx, [rsi+4]; Source2
0x180004423  lea     rcx, [rbp+57h+Source1]; Source1
0x180004427  call    cs:__imp_RtlCompareMemory
0x18000442e  nop     dword ptr [rax+rax+00h]
0x180004433  cmp     rax, r14
0x180004436  jnz     short loc_180004485
0x180004438  movups  xmm0, xmmword ptr [rbx+124h]
0x18000443f  lea     r9, [rbp+57h+var_50]
0x180004443  movups  xmm1, xmmword ptr [rbx+134h]
0x18000444a  lea     r8, [rbp+57h+var_D0]
0x18000444e  lea     rdx, [rbp+57h+var_B0]
0x180004452  lea     rcx, [rsi+4]
0x180004456  movups  [rbp+57h+var_D0], xmm0
0x18000445a  movups  [rbp+57h+var_C0], xmm1
0x18000445e  call    GetMsftVerifyData
0x180004463  lea     rdx, [rsi+24h]; Source2
0x180004467  mov     r8d, r14d; Length
0x18000446a  lea     rcx, [rbp+57h+var_50]; Source1
0x18000446e  call    cs:__imp_RtlCompareMemory
0x180004475  nop     dword ptr [rax+rax+00h]
0x18000447a  cmp     rax, r14
0x18000447d  jnz     short loc_180004485
0x18000447f  lea     eax, [r14-1Fh]
0x180004483  jmp     short loc_180004487
0x180004485  xor     eax, eax
0x180004487  mov     rcx, [rbp+57h+var_30]
0x18000448b  xor     rcx, rsp; StackCookie
0x18000448e  call    __security_check_cookie
0x180004493  add     rsp, 0F0h
0x18000449a  pop     r14
0x18000449c  pop     rdi
0x18000449d  pop     rsi
0x18000449e  pop     rbx
0x18000449f  pop     rbp
0x1800044a0  retn
```
