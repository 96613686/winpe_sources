# WPP_RECORDER_AND_TRACE_SF_qLLDDDDDDDDDDDLLLLLLL

- ea: `0x18000d6e4`
- end: `0x18000da9f`
- name: `WPP_RECORDER_AND_TRACE_SF_qLLDDDDDDDDDDDLLLLLLL`
- size: `955`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000d3a4`

## callees

- `0x18000d6e4`
- `0x180027c80`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x18000d8cb`
- `WppRecorder!WppAutoLogTrace` at `0x18000d8cb`

## pseudocode

```c
_UNKNOWN **__fastcall WPP_RECORDER_AND_TRACE_SF_qLLDDDDDDDDDDDLLLLLLL(
        __int64 a1,
        char a2,
        char a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        int a8,
        char a9,
        char a10,
        char a11,
        char a12,
        char a13,
        char a14,
        char a15,
        char a16,
        char a17,
        char a18,
        char a19,
        char a20,
        char a21,
        char a22,
        char a23,
        char a24,
        char a25,
        char a26,
        char a27,
        char a28,
        char a29)
{
  _UNKNOWN **result; // rax
  int v32; // [rsp+28h] [rbp-1E0h]
  _UNKNOWN *retaddr; // [rsp+1B0h] [rbp-58h] BYREF

  result = &retaddr;
  if ( a2 )
    result = (_UNKNOWN **)((__int64 (__fastcall *)(__int64, __int64, __int64 *, __int64, char *, __int64, char *, __int64, char *, __int64, char *, __int64, char *, __int64, char *, __int64, char *, __int64, char *, __int64, char *, __int64, char *, __int64, char *, __int64, char *, __int64, char *, __int64, char *, __int64, char *, __int64, char *, __int64, char *, __int64, char *, __int64, char *, __int64, char *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
                            a1,
                            43,
                            WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
                            90,
                            &a9,
                            8,
                            &a10,
                            4,
                            &a11,
                            4,
                            &a12,
                            4,
                            &a13,
                            4,
                            &a14,
                            4,
                            &a15,
                            4,
                            &a16,
                            4,
                            &a17,
                            4,
                            &a18,
                            4,
                            &a19,
                            4,
                            &a20,
                            4,
                            &a21,
                            4,
                            &a22,
                            4,
                            &a23,
                            4,
                            &a24,
                            4,
                            &a25,
                            4,
                            &a26,
                            4,
                            &a27,
                            4,
                            &a28,
                            4,
                            &a29,
                            4,
                            0);
  if ( a3 )
  {
    LOWORD(v32) = 90;
    return (_UNKNOWN **)WppAutoLogTrace(
                          a4,
                          4,
                          9,
                          WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
                          v32,
                          &a9,
                          8,
                          &a10,
                          4,
                          &a11,
                          4,
                          &a12,
                          4,
                          &a13,
                          4,
                          &a14,
                          4,
                          &a15,
                          4,
                          &a16,
                          4,
                          &a17,
                          4,
                          &a18,
                          4,
                          &a19,
                          4,
                          &a20,
                          4,
                          &a21,
                          4,
                          &a22,
                          4,
                          &a23,
                          4,
                          &a24,
                          4,
                          &a25,
                          4,
                          &a26,
                          4,
                          &a27,
                          4,
                          &a28,
                          4,
                          &a29,
                          4,
                          0);
  }
  return result;
}

```

## disassembly

```asm
0x18000d6e4  mov     rax, rsp
0x18000d6e7  push    rbp
0x18000d6e8  push    rbx
0x18000d6e9  push    rsi
0x18000d6ea  push    rdi
0x18000d6eb  push    r15
0x18000d6ed  lea     rbp, [rax+58h]
0x18000d6f1  sub     rsp, 180h
0x18000d6f8  mov     esi, 4
0x18000d6fd  mov     rdi, r9
0x18000d700  mov     bl, r8b
0x18000d703  lea     r15d, [rsi+56h]
0x18000d707  test    dl, dl
0x18000d709  jnz     loc_18000D8E6
0x18000d70f  test    bl, bl
0x18000d711  jz      loc_18000D8D7
0x18000d717  mov     qword ptr [rsp+178h], 0
0x18000d723  lea     rax, [rbp-60h+arg_E0]
0x18000d72a  mov     [rsp+1A0h+var_30], rsi
0x18000d732  lea     r9, WPP_c0d00459c274326499e63e8337aee7d7_Traceguids
0x18000d739  mov     [rsp+1A0h+var_38], rax
0x18000d741  mov     r8d, 9
0x18000d747  mov     [rsp+1A0h+var_40], rsi
0x18000d74f  lea     rax, [rbp-60h+arg_D8]
0x18000d756  mov     [rsp+1A0h+var_48], rax
0x18000d75e  mov     edx, esi
0x18000d760  mov     [rsp+1A0h+var_50], rsi
0x18000d768  lea     rax, [rbp-60h+arg_D0]
0x18000d76f  mov     [rsp+1A0h+var_58], rax
0x18000d777  mov     rcx, rdi
0x18000d77a  mov     [rsp+1A0h+var_60], rsi
0x18000d782  lea     rax, [rbp-60h+arg_C8]
0x18000d786  mov     [rsp+1A0h+var_68], rax
0x18000d78e  lea     rax, [rbp-60h+arg_C0]
0x18000d792  mov     [rsp+1A0h+var_70], rsi
0x18000d79a  mov     [rsp+1A0h+var_78], rax
0x18000d7a2  lea     rax, [rbp-60h+arg_B8]
0x18000d7a6  mov     [rsp+1A0h+var_80], rsi
0x18000d7ae  mov     [rsp+1A0h+var_88], rax
0x18000d7b6  lea     rax, [rbp-60h+arg_B0]
0x18000d7ba  mov     [rsp+1A0h+var_90], rsi
0x18000d7c2  mov     [rsp+1A0h+var_98], rax
0x18000d7ca  lea     rax, [rbp-60h+arg_A8]
0x18000d7ce  mov     [rsp+1A0h+var_A0], rsi
0x18000d7d6  mov     [rsp+1A0h+var_A8], rax
0x18000d7de  lea     rax, [rbp-60h+arg_A0]
0x18000d7e2  mov     [rsp+1A0h+var_B0], rsi
0x18000d7ea  mov     [rsp+1A0h+var_B8], rax
0x18000d7f2  lea     rax, [rbp-60h+arg_98]
0x18000d7f6  mov     [rsp+1A0h+var_C0], rsi
0x18000d7fe  mov     [rsp+1A0h+var_C8], rax
0x18000d806  lea     rax, [rbp-60h+arg_90]
0x18000d80a  mov     [rsp+1A0h+var_D0], rsi
0x18000d812  mov     [rsp+1A0h+var_D8], rax
0x18000d81a  lea     rax, [rbp-60h+arg_88]
0x18000d81e  mov     [rsp+1A0h+var_E0], rsi
0x18000d826  mov     [rsp+1A0h+var_E8], rax
0x18000d82e  lea     rax, [rbp-60h+arg_80]
0x18000d832  mov     [rsp+1A0h+var_F0], rsi
0x18000d83a  mov     [rsp+1A0h+var_F8], rax
0x18000d842  lea     rax, [rbp-60h+arg_78]
0x18000d846  mov     [rsp+1A0h+var_100], rsi
0x18000d84e  mov     [rsp+1A0h+var_108], rax
0x18000d856  lea     rax, [rbp-60h+arg_70]
0x18000d85a  mov     [rsp+1A0h+var_110], rsi
0x18000d862  mov     [rsp+1A0h+var_118], rax
0x18000d86a  lea     rax, [rbp-60h+arg_68]
0x18000d86e  mov     [rsp+1A0h+var_120], rsi
0x18000d876  mov     [rsp+1A0h+var_128], rax
0x18000d87b  lea     rax, [rbp-60h+arg_60]
0x18000d87f  mov     [rsp+1A0h+var_130], rsi
0x18000d884  mov     [rsp+1A0h+var_138], rax
0x18000d889  lea     rax, [rbp-60h+arg_58]
0x18000d88d  mov     [rsp+1A0h+var_140], rsi
0x18000d892  mov     [rsp+1A0h+var_148], rax
0x18000d897  lea     rax, [rbp-60h+arg_50]
0x18000d89b  mov     [rsp+1A0h+var_150], rsi
0x18000d8a0  mov     [rsp+1A0h+var_158], rax
0x18000d8a5  lea     rax, [rbp-60h+arg_48]
0x18000d8a9  mov     [rsp+1A0h+var_160], rsi
0x18000d8ae  mov     [rsp+1A0h+var_168], rax
0x18000d8b3  lea     rax, [rbp-60h+arg_40]
0x18000d8b7  mov     [rsp+1A0h+var_170], 8
0x18000d8c0  mov     [rsp+1A0h+var_178], rax
0x18000d8c5  mov     word ptr [rsp+1A0h+var_180], r15w
0x18000d8cb  call    cs:__imp_WppAutoLogTrace
0x18000d8d2  nop     dword ptr [rax+rax+00h]
0x18000d8d7  add     rsp, 180h
0x18000d8de  pop     r15
0x18000d8e0  pop     rdi
0x18000d8e1  pop     rsi
0x18000d8e2  pop     rbx
0x18000d8e3  pop     rbp
0x18000d8e4  retn
0x18000d8e6  mov     [rsp+1A0h+var_30], 0
0x18000d8f2  lea     rdx, [rbp-60h+arg_E0]
0x18000d8f9  mov     [rsp+1A0h+var_38], rsi
0x18000d901  lea     r8, WPP_c0d00459c274326499e63e8337aee7d7_Traceguids
0x18000d908  mov     [rsp+1A0h+var_40], rdx
0x18000d910  mov     r9d, r15d
0x18000d913  mov     [rsp+1A0h+var_48], rsi
0x18000d91b  lea     rdx, [rbp-60h+arg_D8]
0x18000d922  mov     [rsp+1A0h+var_50], rdx
0x18000d92a  lea     rdx, [rbp-60h+arg_D0]
0x18000d931  mov     [rsp+1A0h+var_58], rsi
0x18000d939  mov     [rsp+1A0h+var_60], rdx
0x18000d941  lea     rdx, [rbp-60h+arg_C8]
0x18000d945  mov     [rsp+1A0h+var_68], rsi
0x18000d94d  mov     [rsp+1A0h+var_70], rdx
0x18000d955  lea     rdx, [rbp-60h+arg_C0]
0x18000d959  mov     [rsp+1A0h+var_78], rsi
0x18000d961  mov     [rsp+1A0h+var_80], rdx
0x18000d969  lea     rdx, [rbp-60h+arg_B8]
0x18000d96d  mov     rax, cs:pfnWppTraceMessage
0x18000d974  mov     [rsp+1A0h+var_88], rsi
0x18000d97c  mov     [rsp+1A0h+var_90], rdx
0x18000d984  lea     rdx, [rbp-60h+arg_B0]
0x18000d988  mov     [rsp+1A0h+var_98], rsi
0x18000d990  mov     [rsp+1A0h+var_A0], rdx
0x18000d998  lea     rdx, [rbp-60h+arg_A8]
0x18000d99c  mov     [rsp+1A0h+var_A8], rsi
0x18000d9a4  mov     [rsp+1A0h+var_B0], rdx
0x18000d9ac  lea     rdx, [rbp-60h+arg_A0]
0x18000d9b0  mov     [rsp+1A0h+var_B8], rsi
0x18000d9b8  mov     [rsp+1A0h+var_C0], rdx
0x18000d9c0  lea     rdx, [rbp-60h+arg_98]
0x18000d9c4  mov     [rsp+1A0h+var_C8], rsi
0x18000d9cc  mov     [rsp+1A0h+var_D0], rdx
0x18000d9d4  lea     rdx, [rbp-60h+arg_90]
0x18000d9d8  mov     [rsp+1A0h+var_D8], rsi
0x18000d9e0  mov     [rsp+1A0h+var_E0], rdx
0x18000d9e8  lea     rdx, [rbp-60h+arg_88]
0x18000d9ec  mov     [rsp+1A0h+var_E8], rsi
0x18000d9f4  mov     [rsp+1A0h+var_F0], rdx
0x18000d9fc  lea     rdx, [rbp-60h+arg_80]
0x18000da00  mov     [rsp+1A0h+var_F8], rsi
0x18000da08  mov     [rsp+1A0h+var_100], rdx
0x18000da10  lea     rdx, [rbp-60h+arg_78]
0x18000da14  mov     [rsp+1A0h+var_108], rsi
0x18000da1c  mov     [rsp+1A0h+var_110], rdx
0x18000da24  lea     rdx, [rbp-60h+arg_70]
0x18000da28  mov     [rsp+1A0h+var_118], rsi
0x18000da30  mov     [rsp+1A0h+var_120], rdx
0x18000da38  lea     rdx, [rbp-60h+arg_68]
0x18000da3c  mov     [rsp+1A0h+var_128], rsi
0x18000da41  mov     [rsp+1A0h+var_130], rdx
0x18000da46  lea     rdx, [rbp-60h+arg_60]
0x18000da4a  mov     [rsp+1A0h+var_138], rsi
0x18000da4f  mov     [rsp+1A0h+var_140], rdx
0x18000da54  lea     rdx, [rbp-60h+arg_58]
0x18000da58  mov     [rsp+1A0h+var_148], rsi
0x18000da5d  mov     [rsp+1A0h+var_150], rdx
0x18000da62  lea     rdx, [rbp-60h+arg_50]
0x18000da66  mov     [rsp+1A0h+var_158], rsi
0x18000da6b  mov     [rsp+1A0h+var_160], rdx
0x18000da70  lea     rdx, [rbp-60h+arg_48]
0x18000da74  mov     [rsp+1A0h+var_168], rsi
0x18000da79  mov     [rsp+1A0h+var_170], rdx
0x18000da7e  lea     rdx, [rbp-60h+arg_40]
0x18000da82  mov     [rsp+1A0h+var_178], 8
0x18000da8b  mov     [rsp+1A0h+var_180], rdx
0x18000da90  mov     edx, 2Bh ; '+'
0x18000da95  call    _guard_dispatch_icall
0x18000da9a  jmp     loc_18000D70F
```
