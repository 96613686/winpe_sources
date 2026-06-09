# LdrpInitializePerUserWindowsDirectory

- ea: `0x180119c2c`
- end: `0x180119dc1`
- name: `LdrpInitializePerUserWindowsDirectory`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x1800d6508`

## callees

- `0x18001861c`
- `0x18001b984`
- `0x18001eb80`
- `0x18002ad90`
- `0x18005a9f0`
- `0x1801014d0`
- `0x180119c2c`
- `0x18011d274`
- `0x180162000`
- `0x18016f020`

## string_xrefs

- `0x180119cf1`: `LdrpInitializePerUserWindowsDirectory`

## pseudocode

```c
__int64 __fastcall LdrpInitializePerUserWindowsDirectory(__int64 (__fastcall *a1)(_BYTE *, __int64))
{
  int v1; // eax
  unsigned __int16 v2; // ax
  __int16 v3; // bx
  char v5; // [rsp+28h] [rbp-D8h]
  __m128i v6; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v7; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v8; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v9[528]; // [rsp+60h] [rbp-A0h] BYREF

  v8 = 0;
  v6.m128i_i32[1] = 0;
  v7 = 0;
  v1 = a1(v9, 260);
  if ( (unsigned int)(v1 - 1) <= 0x102 )
  {
    v2 = 2 * v1;
    *((_QWORD *)&v7 + 1) = v9;
    WORD1(v7) = 520;
    LOWORD(v7) = v2;
    if ( *((_QWORD *)&RtlpSystemDirs + 1) )
    {
      v3 = RtlpSystemDirs + v2 + 2;
      v6.m128i_i64[1] = RtlAllocateHeap_0(
                          NtCurrentPeb()->ProcessHeap,
                          0,
                          (unsigned __int16)RtlpSystemDirs + (unsigned int)v2 + 2LL);
      if ( !v6.m128i_i64[1] )
      {
        LdrpLogInternal(
          (int)"minkernel\\ldr\\ldrinit.c",
          4713,
          (int)"LdrpInitializePerUserWindowsDirectory",
          0,
          "Failed to reallocate the system dirs string !\n",
          v5);
        return 3221225495LL;
      }
      v6.m128i_i16[1] = v3;
      v6.m128i_i16[0] = 0;
      RtlAppendUnicodeStringToString(&v6, &RtlpSystemDirs);
      RtlAppendUnicodeStringToString(&v6, &v7);
      RtlAppendUnicodeToString(&v6, L";");
      RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, *((_QWORD *)&RtlpSystemDirs + 1));
      RtlpSystemDirs = (__int128)v6;
      *((_QWORD *)&RtlpSystem32Dirs + 1) = _mm_srli_si128(v6, 8).m128i_u64[0];
      RtlpSignalSystemDirsModification();
    }
    LdrAddDllDirectory(&v7, &v8);
  }
  return 0;
}

```

## disassembly

```asm
0x180119c2c  mov     [rsp-8+arg_8], rbx
0x180119c31  push    rbp
0x180119c32  lea     rbp, [rsp-180h]
0x180119c3a  sub     rsp, 280h
0x180119c41  mov     rax, cs:__security_cookie
0x180119c48  xor     rax, rsp
0x180119c4b  mov     [rbp+180h+var_10], rax
0x180119c52  mov     rax, rcx
0x180119c55  mov     [rsp+280h+var_230], 0
0x180119c5e  xorps   xmm0, xmm0
0x180119c61  mov     dword ptr [rsp+280h+var_250+4], 0
0x180119c69  lea     rcx, [rsp+280h+var_220]
0x180119c6e  mov     edx, 104h
0x180119c73  movups  [rsp+280h+var_240], xmm0
0x180119c78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119c7d  lea     ecx, [rax-1]
0x180119c80  cmp     ecx, 102h
0x180119c86  ja      loc_180119D9E
0x180119c8c  lea     rcx, [rsp+280h+var_220]
0x180119c91  add     ax, ax
0x180119c94  cmp     qword ptr cs:RtlpSystemDirs+8, 0
0x180119c9c  mov     qword ptr [rsp+280h+var_240+8], rcx
0x180119ca1  mov     ecx, 208h
0x180119ca6  mov     word ptr [rsp+280h+var_240+2], cx
0x180119cab  mov     word ptr [rsp+280h+var_240], ax
0x180119cb0  jz      loc_180119D8F
0x180119cb6  mov     rcx, gs:60h
0x180119cbf  xor     edx, edx
0x180119cc1  movzx   ebx, ax
0x180119cc4  movzx   eax, word ptr cs:RtlpSystemDirs
0x180119ccb  add     ebx, eax
0x180119ccd  mov     rcx, [rcx+30h]
0x180119cd1  add     rbx, 2
0x180119cd5  mov     r8, rbx
0x180119cd8  call    RtlAllocateHeap_0
0x180119cdd  mov     qword ptr [rsp+280h+var_250+8], rax
0x180119ce2  test    rax, rax
0x180119ce5  jnz     short loc_180119D18
0x180119ce7  lea     rax, aFailedToReallo; "Failed to reallocate the system dirs st"...
0x180119cee  xor     r9d, r9d; int
0x180119cf1  lea     r8, aLdrpinitialize_10; "LdrpInitializePerUserWindowsDirectory"
0x180119cf8  mov     [rsp+280h+Format], rax; Format
0x180119cfd  mov     edx, 1269h; int
0x180119d02  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x180119d09  call    LdrpLogInternal
0x180119d0e  mov     eax, 0C0000017h
0x180119d13  jmp     loc_180119DA0
0x180119d18  xor     eax, eax
0x180119d1a  mov     word ptr [rsp+280h+var_250+2], bx
0x180119d1f  lea     rdx, RtlpSystemDirs
0x180119d26  mov     word ptr [rsp+280h+var_250], ax
0x180119d2b  lea     rcx, [rsp+280h+var_250]
0x180119d30  call    RtlAppendUnicodeStringToString
0x180119d35  lea     rdx, [rsp+280h+var_240]
0x180119d3a  lea     rcx, [rsp+280h+var_250]
0x180119d3f  call    RtlAppendUnicodeStringToString
0x180119d44  lea     rdx, Control; ";"
0x180119d4b  lea     rcx, [rsp+280h+var_250]
0x180119d50  call    RtlAppendUnicodeToString
0x180119d55  mov     rcx, gs:60h
0x180119d5e  xor     edx, edx
0x180119d60  mov     r8, qword ptr cs:RtlpSystemDirs+8
0x180119d67  mov     rcx, [rcx+30h]
0x180119d6b  call    RtlFreeHeap_0
0x180119d70  movups  xmm0, [rsp+280h+var_250]
0x180119d75  movdqu  cs:RtlpSystemDirs, xmm0
0x180119d7d  psrldq  xmm0, 8
0x180119d82  movq    qword ptr cs:RtlpSystem32Dirs+8, xmm0
0x180119d8a  call    RtlpSignalSystemDirsModification
0x180119d8f  lea     rdx, [rsp+280h+var_230]
0x180119d94  lea     rcx, [rsp+280h+var_240]
0x180119d99  call    LdrAddDllDirectory
0x180119d9e  xor     eax, eax
0x180119da0  mov     rcx, [rbp+180h+var_10]
0x180119da7  xor     rcx, rsp; StackCookie
0x180119daa  call    __security_check_cookie
0x180119daf  mov     rbx, [rsp+280h+arg_8]
0x180119db7  add     rsp, 280h
0x180119dbe  pop     rbp
0x180119dbf  retn
```
