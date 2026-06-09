# EtwReportPropertyRetrievalFailureInEtwEvent

- ea: `0x18001ffc0`
- end: `0x1800200fe`
- name: `EtwReportPropertyRetrievalFailureInEtwEvent`
- size: `318`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, loader_planting`

## callers

- `0x18001fcc0`
- `0x18001fd80`

## callees

- `0x180006e64`
- `0x180007c80`
- `0x180020778`
- `0x180044880`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180020072`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180020072`

## string_xrefs

- `0x180020066`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall EtwReportPropertyRetrievalFailureInEtwEvent(__int64 a1, unsigned int a2)
{
  HMODULE ModuleHandleA; // rax
  int v5; // [rsp+20h] [rbp-138h]
  int v6; // [rsp+28h] [rbp-130h]
  int v7; // [rsp+30h] [rbp-128h]
  int v8; // [rsp+38h] [rbp-120h]
  int v9; // [rsp+40h] [rbp-118h]
  int v10; // [rsp+48h] [rbp-110h]
  int v11; // [rsp+50h] [rbp-108h]
  int v12; // [rsp+58h] [rbp-100h]
  int v13; // [rsp+60h] [rbp-F8h]
  int v14; // [rsp+68h] [rbp-F0h]
  wchar_t pszDest[80]; // [rsp+80h] [rbp-D8h] BYREF

  v14 = *(unsigned __int8 *)(a1 + 39);
  v13 = *(unsigned __int8 *)(a1 + 38);
  v12 = *(unsigned __int8 *)(a1 + 37);
  v11 = *(unsigned __int8 *)(a1 + 36);
  v10 = *(unsigned __int8 *)(a1 + 35);
  v9 = *(unsigned __int8 *)(a1 + 34);
  v8 = *(unsigned __int8 *)(a1 + 33);
  v7 = *(unsigned __int8 *)(a1 + 32);
  v6 = *(unsigned __int16 *)(a1 + 30);
  v5 = *(unsigned __int16 *)(a1 + 28);
  StringCchPrintfW(
    pszDest,
    0x50u,
    L"{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
    *(unsigned int *)(a1 + 24),
    v5,
    v6,
    v7,
    v8,
    v9,
    v10,
    v11,
    v12,
    v13,
    v14);
  ModuleHandleA = GetModuleHandleA("mpunits.dll");
  Intlstr_FormatString_FormatMessage(ModuleHandleA, 2125, a2);
  return MI_ReportErrorDetails_ForCustomError(11, (int)L"ETW Normalizer", 0, 0);
}

```

## disassembly

```asm
0x18001ffc0  mov     [rsp+arg_10], rbx
0x18001ffc5  push    rbp
0x18001ffc6  push    rsi
0x18001ffc7  push    rdi
0x18001ffc8  push    r14
0x18001ffca  push    r15
0x18001ffcc  sub     rsp, 130h
0x18001ffd3  mov     rax, cs:__security_cookie
0x18001ffda  xor     rax, rsp
0x18001ffdd  mov     [rsp+158h+var_38], rax
0x18001ffe5  movzx   r8d, byte ptr [rcx+25h]
0x18001ffea  mov     rbp, rcx
0x18001ffed  movzx   eax, byte ptr [rcx+27h]
0x18001fff1  mov     r15d, edx
0x18001fff4  movzx   edx, byte ptr [rcx+26h]
0x18001fff8  movzx   r10d, byte ptr [rcx+24h]
0x18001fffd  movzx   r11d, byte ptr [rcx+23h]
0x180020002  mov     r9d, [rcx+18h]
0x180020006  movzx   r14d, word ptr [rcx+28h]
0x18002000b  movzx   ecx, byte ptr [rcx+22h]
0x18002000f  movzx   ebx, byte ptr [rbp+21h]
0x180020013  movzx   edi, byte ptr [rbp+20h]
0x180020017  movzx   esi, word ptr [rbp+1Eh]
0x18002001b  movzx   ebp, word ptr [rbp+1Ch]
0x18002001f  mov     [rsp+158h+var_F0], eax
0x180020023  mov     [rsp+158h+var_F8], edx
0x180020027  mov     edx, 50h ; 'P'; cchDest
0x18002002c  mov     [rsp+158h+var_100], r8d
0x180020031  lea     r8, a08x04x04x02x02; "{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%0"...
0x180020038  mov     [rsp+158h+var_108], r10d
0x18002003d  mov     [rsp+158h+var_110], r11d
0x180020042  mov     [rsp+158h+var_118], ecx
0x180020046  lea     rcx, [rsp+158h+pszDest]; pszDest
0x18002004e  mov     [rsp+158h+var_120], ebx
0x180020052  mov     [rsp+158h+var_128], edi
0x180020056  mov     dword ptr [rsp+158h+var_130], esi
0x18002005a  mov     dword ptr [rsp+158h+var_138], ebp
0x18002005e  call    StringCchPrintfW
0x180020063  xorps   xmm0, xmm0
0x180020066  lea     rcx, ModuleName; "mpunits.dll"
0x18002006d  movups  [rsp+158h+var_E8], xmm0
0x180020072  call    cs:__imp_GetModuleHandleA
0x180020078  lea     r9, [rsp+158h+pszDest]
0x180020080  mov     dword ptr [rsp+158h+var_138], r14d
0x180020085  mov     rcx, rax
0x180020088  mov     r8d, r15d
0x18002008b  mov     edx, 84Dh
0x180020090  call    _Intlstr_FormatString_FormatMessage
0x180020095  mov     qword ptr [rsp+158h+var_E8], rax
0x18002009a  lea     r9, [rsp+158h+var_E8]
0x18002009f  mov     byte ptr [rsp+158h+var_E8+8], 1
0x1800200a4  lea     rdx, aEtwNormalizer; "ETW Normalizer"
0x1800200ab  movaps  xmm0, [rsp+158h+var_E8]
0x1800200b0  mov     r8d, 0Ah
0x1800200b6  mov     [rsp+158h+var_130], 0; __int64
0x1800200bf  movdqa  [rsp+158h+var_E8], xmm0
0x1800200c5  mov     [rsp+158h+var_138], 0; __int64
0x1800200ce  lea     ecx, [r8+1]; int
0x1800200d2  call    MI_ReportErrorDetails_ForCustomError
0x1800200d7  mov     rcx, [rsp+158h+var_38]
0x1800200df  xor     rcx, rsp; StackCookie
0x1800200e2  call    __security_check_cookie
0x1800200e7  mov     rbx, [rsp+158h+arg_10]
0x1800200ef  add     rsp, 130h
0x1800200f6  pop     r15
0x1800200f8  pop     r14
0x1800200fa  pop     rdi
0x1800200fb  pop     rsi
0x1800200fc  pop     rbp
0x1800200fd  retn
```
