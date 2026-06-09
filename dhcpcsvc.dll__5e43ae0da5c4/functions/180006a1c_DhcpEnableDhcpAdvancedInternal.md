# DhcpEnableDhcpAdvancedInternal

- ea: `0x180006a1c`
- end: `0x180006b70`
- name: `DhcpEnableDhcpAdvancedInternal`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800068b0`

## callees

- `0x180005614`
- `0x180006a1c`
- `0x18000f4ec`
- `0x180011f50`
- `0x1800127f0`
- `0x180012a00`
- `0x180012a40`

## import_xrefs

- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180006a99`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180006af5`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180006b10`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180006a99`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180006af5`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180006b10`

## pseudocode

```c
__int64 __fastcall DhcpEnableDhcpAdvancedInternal(__int64 a1, int a2, int a3, float a4, int a5, int a6)
{
  char v9; // al
  unsigned int v10; // ebx
  LPWSTR CommandLineW; // rax
  LPWSTR v12; // rax
  double v14; // [rsp+30h] [rbp-48h]

  v9 = xmmword_18001E1E0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    v14 = a4;
    WPP_SF_qddggd(a1, a2, a3, a1, a2, a3, SLOBYTE(v14), a5, a6);
    v9 = xmmword_18001E1E0;
  }
  if ( !a1 )
  {
    v10 = 87;
    goto LABEL_9;
  }
  if ( (v9 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_S(1028, 47, WPP_e15037783097355a5233924022d92169_Traceguids, CommandLineW);
  }
  v10 = RpcCliEnableDhcpAdvanced(a1, a1, a2, a3, LODWORD(a4), a5, a6);
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    v12 = GetCommandLineW();
    WPP_SF_DS(1028, 48, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, v10, (__int64)v12);
    v9 = xmmword_18001E1E0;
LABEL_9:
    if ( (v9 & 0x10) != 0 )
      WPP_SF_d(1028, 49, WPP_e15037783097355a5233924022d92169_Traceguids, v10);
  }
  return v10;
}

```

## disassembly

```asm
0x180006a1c  mov     [rsp+arg_0], rbx
0x180006a21  mov     [rsp+arg_8], rsi
0x180006a26  push    rdi
0x180006a27  sub     rsp, 70h
0x180006a2b  movaps  [rsp+78h+var_18], xmm6
0x180006a30  movaps  xmm6, xmm3
0x180006a33  mov     edi, r8d
0x180006a36  mov     esi, edx
0x180006a38  mov     rbx, rcx
0x180006a3b  mov     al, byte ptr cs:xmmword_18001E1E0
0x180006a41  test    al, 10h
0x180006a43  jz      short loc_180006A86
0x180006a45  movss   xmm0, [rsp+78h+arg_20]
0x180006a4e  cvtps2pd xmm0, xmm0
0x180006a51  xorps   xmm1, xmm1
0x180006a54  cvtss2sd xmm1, xmm6
0x180006a58  mov     eax, [rsp+78h+arg_28]
0x180006a5f  mov     [rsp+78h+var_38], eax
0x180006a63  movsd   [rsp+78h+var_40], xmm0
0x180006a69  movsd   [rsp+78h+var_48], xmm1
0x180006a6f  mov     [rsp+78h+var_50], r8d
0x180006a74  mov     dword ptr [rsp+78h+var_58], edx
0x180006a78  mov     r9, rcx
0x180006a7b  call    WPP_SF_qddggd
0x180006a80  mov     al, byte ptr cs:xmmword_18001E1E0
0x180006a86  test    rbx, rbx
0x180006a89  jnz     short loc_180006A95
0x180006a8b  mov     ebx, 57h ; 'W'
0x180006a90  jmp     loc_180006B3A
0x180006a95  test    al, 10h
0x180006a97  jz      short loc_180006AB9
0x180006a99  call    cs:__imp_GetCommandLineW
0x180006a9f  mov     r9, rax
0x180006aa2  mov     edx, 2Fh ; '/'
0x180006aa7  mov     ecx, 404h
0x180006aac  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180006ab3  call    WPP_SF_S
0x180006ab8  nop
0x180006ab9  mov     eax, [rsp+78h+arg_28]
0x180006ac0  mov     dword ptr [rsp+78h+var_48], eax
0x180006ac4  movss   xmm0, [rsp+78h+arg_20]
0x180006acd  movss   [rsp+78h+var_50], xmm0
0x180006ad3  movss   dword ptr [rsp+78h+var_58], xmm6
0x180006ad9  mov     r9d, edi
0x180006adc  mov     r8d, esi
0x180006adf  mov     rdx, rbx
0x180006ae2  call    RpcCliEnableDhcpAdvanced
0x180006ae7  mov     ebx, eax
0x180006ae9  mov     [rsp+78h+var_28], eax
0x180006aed  jmp     short loc_180006B06
0x180006aef  mov     ebx, eax
0x180006af1  mov     [rsp+78h+var_28], eax
0x180006af5  call    cs:__imp_GetCommandLineW
0x180006afb  mov     rdx, rax
0x180006afe  mov     ecx, ebx
0x180006b00  call    TraceRpcException
0x180006b05  nop
0x180006b06  mov     al, byte ptr cs:xmmword_18001E1E0
0x180006b0c  test    al, 10h
0x180006b0e  jz      short loc_180006B57
0x180006b10  call    cs:__imp_GetCommandLineW
0x180006b16  mov     edx, 30h ; '0'
0x180006b1b  mov     ecx, 404h
0x180006b20  mov     [rsp+78h+var_58], rax
0x180006b25  mov     r9d, ebx
0x180006b28  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180006b2f  call    WPP_SF_DS
0x180006b34  mov     al, byte ptr cs:xmmword_18001E1E0
0x180006b3a  test    al, 10h
0x180006b3c  jz      short loc_180006B57
0x180006b3e  mov     edx, 31h ; '1'
0x180006b43  mov     ecx, 404h
0x180006b48  mov     r9d, ebx
0x180006b4b  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180006b52  call    WPP_SF_d
0x180006b57  mov     eax, ebx
0x180006b59  lea     r11, [rsp+78h+var_8]
0x180006b5e  mov     rbx, [r11+10h]
0x180006b62  mov     rsi, [r11+18h]
0x180006b66  movaps  xmm6, [rsp+78h+var_18]
0x180006b6b  mov     rsp, r11
0x180006b6e  pop     rdi
0x180006b6f  retn
0x180010cec  push    rbp
0x180010cee  sub     rsp, 50h
0x180010cf2  mov     rbp, rdx
0x180010cf5  mov     rcx, [rcx]
0x180010cf8  mov     ecx, [rcx]; ExceptionCode
0x180010cfa  call    cs:__imp_I_RpcExceptionFilter
0x180010d00  nop
0x180010d01  add     rsp, 50h
0x180010d05  pop     rbp
0x180010d06  retn
```
