# LdrpInitializePerUserWindowsDirectory

- ea: `0x18011a71c`
- end: `0x18011a8b1`
- name: `LdrpInitializePerUserWindowsDirectory`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180050718`

## callees

- `0x18001861c`
- `0x18001b984`
- `0x18001eb80`
- `0x180036fa0`
- `0x1800773d0`
- `0x180101ad0`
- `0x18011a71c`
- `0x18011dd64`
- `0x180162810`
- `0x18016f020`

## string_xrefs

- `0x18011a7e1`: `LdrpInitializePerUserWindowsDirectory`

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
0x18011a71c  mov     [rsp-8+arg_8], rbx
0x18011a721  push    rbp
0x18011a722  lea     rbp, [rsp-180h]
0x18011a72a  sub     rsp, 280h
0x18011a731  mov     rax, cs:__security_cookie
0x18011a738  xor     rax, rsp
0x18011a73b  mov     [rbp+180h+var_10], rax
0x18011a742  mov     rax, rcx
0x18011a745  mov     [rsp+280h+var_230], 0
0x18011a74e  xorps   xmm0, xmm0
0x18011a751  mov     dword ptr [rsp+280h+var_250+4], 0
0x18011a759  lea     rcx, [rsp+280h+var_220]
0x18011a75e  mov     edx, 104h
0x18011a763  movups  [rsp+280h+var_240], xmm0
0x18011a768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011a76d  lea     ecx, [rax-1]
0x18011a770  cmp     ecx, 102h
0x18011a776  ja      loc_18011A88E
0x18011a77c  lea     rcx, [rsp+280h+var_220]
0x18011a781  add     ax, ax
0x18011a784  cmp     qword ptr cs:RtlpSystemDirs+8, 0
0x18011a78c  mov     qword ptr [rsp+280h+var_240+8], rcx
0x18011a791  mov     ecx, 208h
0x18011a796  mov     word ptr [rsp+280h+var_240+2], cx
0x18011a79b  mov     word ptr [rsp+280h+var_240], ax
0x18011a7a0  jz      loc_18011A87F
0x18011a7a6  mov     rcx, gs:60h
0x18011a7af  xor     edx, edx
0x18011a7b1  movzx   ebx, ax
0x18011a7b4  movzx   eax, word ptr cs:RtlpSystemDirs
0x18011a7bb  add     ebx, eax
0x18011a7bd  mov     rcx, [rcx+30h]
0x18011a7c1  add     rbx, 2
0x18011a7c5  mov     r8, rbx
0x18011a7c8  call    RtlAllocateHeap_0
0x18011a7cd  mov     qword ptr [rsp+280h+var_250+8], rax
0x18011a7d2  test    rax, rax
0x18011a7d5  jnz     short loc_18011A808
0x18011a7d7  lea     rax, aFailedToReallo; "Failed to reallocate the system dirs st"...
0x18011a7de  xor     r9d, r9d; int
0x18011a7e1  lea     r8, aLdrpinitialize_10; "LdrpInitializePerUserWindowsDirectory"
0x18011a7e8  mov     [rsp+280h+Format], rax; Format
0x18011a7ed  mov     edx, 1269h; int
0x18011a7f2  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x18011a7f9  call    LdrpLogInternal
0x18011a7fe  mov     eax, 0C0000017h
0x18011a803  jmp     loc_18011A890
0x18011a808  xor     eax, eax
0x18011a80a  mov     word ptr [rsp+280h+var_250+2], bx
0x18011a80f  lea     rdx, RtlpSystemDirs
0x18011a816  mov     word ptr [rsp+280h+var_250], ax
0x18011a81b  lea     rcx, [rsp+280h+var_250]
0x18011a820  call    RtlAppendUnicodeStringToString
0x18011a825  lea     rdx, [rsp+280h+var_240]
0x18011a82a  lea     rcx, [rsp+280h+var_250]
0x18011a82f  call    RtlAppendUnicodeStringToString
0x18011a834  lea     rdx, Control; ";"
0x18011a83b  lea     rcx, [rsp+280h+var_250]
0x18011a840  call    RtlAppendUnicodeToString
0x18011a845  mov     rcx, gs:60h
0x18011a84e  xor     edx, edx
0x18011a850  mov     r8, qword ptr cs:RtlpSystemDirs+8
0x18011a857  mov     rcx, [rcx+30h]
0x18011a85b  call    RtlFreeHeap_0
0x18011a860  movups  xmm0, [rsp+280h+var_250]
0x18011a865  movdqu  cs:RtlpSystemDirs, xmm0
0x18011a86d  psrldq  xmm0, 8
0x18011a872  movq    qword ptr cs:RtlpSystem32Dirs+8, xmm0
0x18011a87a  call    RtlpSignalSystemDirsModification
0x18011a87f  lea     rdx, [rsp+280h+var_230]
0x18011a884  lea     rcx, [rsp+280h+var_240]
0x18011a889  call    LdrAddDllDirectory
0x18011a88e  xor     eax, eax
0x18011a890  mov     rcx, [rbp+180h+var_10]
0x18011a897  xor     rcx, rsp; StackCookie
0x18011a89a  call    __security_check_cookie
0x18011a89f  mov     rbx, [rsp+280h+arg_8]
0x18011a8a7  add     rsp, 280h
0x18011a8ae  pop     rbp
0x18011a8af  retn
```
