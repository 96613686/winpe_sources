# sub_1800D9BBC

- ea: `0x1800d9bbc`
- end: `0x1800d9d98`
- name: `sub_1800D9BBC`
- size: `476`
- prototype: `__int64 __fastcall(DWORD dwMessageId)`
- caller_count: `5`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180089e10`
- `0x1800a3a00`
- `0x1800c65ec`
- `0x180115830`
- `0x180162cd0`

## callees

- `0x180015a80`
- `0x180016588`
- `0x180017480`
- `0x180019cd0`
- `0x180019e20`
- `0x18002a370`
- `0x180089e10`
- `0x18009fefc`
- `0x1800a3c08`
- `0x1800d8454`
- `0x1800d9bbc`
- `0x1800d9da0`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800d9c22`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800d9c22`

## string_xrefs

- `0x1800d9c42`: `URLMON.DLL`
- `0x1800d9cc0`: `URLMON.DLL`
- `0x1800d9c5e`: `WININET.DLL`
- `0x1800d9c97`: `WINHTTP.DLL`

## pseudocode

```c
__int64 __fastcall sub_1800D9BBC(DWORD dwMessageId)
{
  WCHAR *lpBuffer; // rax
  WCHAR *v3; // rsi
  __int64 *v4; // rax
  __int64 v5; // rbx
  __int64 *v6; // rcx
  int v7; // ecx
  __int64 v8; // r9
  __int64 v9; // r9
  __int64 v10; // r9
  __int64 v11; // rax
  __int64 v12; // rbx
  __int64 v14; // [rsp+68h] [rbp+10h] BYREF
  __int64 v15; // [rsp+70h] [rbp+18h] BYREF
  WCHAR *v16; // [rsp+78h] [rbp+20h]

  lpBuffer = (WCHAR *)sub_180016588(4096);
  v3 = lpBuffer;
  v16 = lpBuffer;
  if ( lpBuffer )
  {
    v7 = FormatMessageW(0x1000u, 0, dwMessageId, 0x400u, lpBuffer, 0x1000u, 0);
    if ( !v7 )
    {
      v7 = sub_1800D9DA0((__int64)L"URLMON.DLL", dwMessageId, v3, v8, 1);
      if ( !v7 )
      {
        v7 = sub_1800D9DA0((__int64)L"WININET.DLL", dwMessageId, v3, v9, 1);
        if ( !v7
          && ((dwMessageId & 0x1FFF0000) != 0x70000
           || (unsigned int)(unsigned __int16)dwMessageId - 12001 > 0xC0
           || (v7 = sub_1800D9DA0((__int64)L"WINHTTP.DLL", dwMessageId, v3, v10, 1)) == 0)
          && dwMessageId + 2146697216 <= 0x3FF )
        {
          v7 = sub_1800D9DA0((__int64)L"URLMON.DLL", dwMessageId, v3, v10, 0);
        }
      }
    }
    v15 = 0;
    v14 = 0;
    if ( v7 )
    {
      v3[v7] = 0;
      v11 = sub_180019CD0(v3);
    }
    else
    {
      v12 = sub_1800D8454(dwMessageId);
      sub_180019E20(&v15);
      v15 = v12;
      v11 = sub_180089E10(0, 3222070026LL, v12, 0, 0, 0);
    }
    v5 = v11;
    sub_180019E20(&v14);
    v14 = v5;
    sub_180017480(v3);
    v14 = 0;
    sub_180019E20(&v14);
    v6 = &v15;
  }
  else
  {
    v4 = (__int64 *)sub_18002A370(&v14, &qword_1801F7908);
    v5 = *v4;
    *v4 = 0;
    v6 = &v14;
  }
  sub_180019E20(v6);
  return v5;
}

```

## disassembly

```asm
0x1800d9bbc  push    rbx
0x1800d9bbe  push    rsi
0x1800d9bbf  push    rdi
0x1800d9bc0  sub     rsp, 40h
0x1800d9bc4  mov     ebx, ecx
0x1800d9bc6  mov     ecx, 1000h
0x1800d9bcb  call    sub_180016588
0x1800d9bd0  mov     rsi, rax
0x1800d9bd3  mov     [rsp+58h+arg_18], rax
0x1800d9bd8  xor     edi, edi
0x1800d9bda  test    rax, rax
0x1800d9bdd  jnz     short loc_1800D9C00
0x1800d9bdf  lea     rdx, qword_1801F7908
0x1800d9be6  lea     rcx, [rsp+58h+arg_8]
0x1800d9beb  call    sub_18002A370
0x1800d9bf0  mov     rbx, [rax]
0x1800d9bf3  mov     [rax], rdi
0x1800d9bf6  lea     rcx, [rsp+58h+arg_8]
0x1800d9bfb  jmp     loc_1800D9D87
0x1800d9c00  mov     [rsp+58h+Arguments], rdi; Arguments
0x1800d9c05  mov     [rsp+58h+nSize], 1000h; nSize
0x1800d9c0d  mov     [rsp+58h+lpBuffer], rsi; lpBuffer
0x1800d9c12  mov     r9d, 400h; dwLanguageId
0x1800d9c18  mov     r8d, ebx; dwMessageId
0x1800d9c1b  xor     edx, edx; lpSource
0x1800d9c1d  mov     ecx, 1000h; dwFlags
0x1800d9c22  call    cs:FormatMessageW
0x1800d9c29  nop     dword ptr [rax+rax+00h]
0x1800d9c2e  mov     ecx, eax
0x1800d9c30  test    eax, eax
0x1800d9c32  jnz     loc_1800D9CCE
0x1800d9c38  mov     byte ptr [rsp+58h+lpBuffer], 1
0x1800d9c3d  mov     r8, rsi
0x1800d9c40  mov     edx, ebx
0x1800d9c42  lea     rcx, aUrlmonDll_0; "URLMON.DLL"
0x1800d9c49  call    sub_1800D9DA0
0x1800d9c4e  mov     ecx, eax
0x1800d9c50  test    eax, eax
0x1800d9c52  jnz     short loc_1800D9CCE
0x1800d9c54  mov     byte ptr [rsp+58h+lpBuffer], 1
0x1800d9c59  mov     r8, rsi
0x1800d9c5c  mov     edx, ebx
0x1800d9c5e  lea     rcx, aWininetDll_0; "WININET.DLL"
0x1800d9c65  call    sub_1800D9DA0
0x1800d9c6a  mov     ecx, eax
0x1800d9c6c  test    eax, eax
0x1800d9c6e  jnz     short loc_1800D9CCE
0x1800d9c70  mov     eax, ebx
0x1800d9c72  and     eax, 1FFF0000h
0x1800d9c77  cmp     eax, 70000h
0x1800d9c7c  jnz     short loc_1800D9CA9
0x1800d9c7e  movzx   eax, bx
0x1800d9c81  sub     eax, 2EE1h
0x1800d9c86  cmp     eax, 0C0h
0x1800d9c8b  ja      short loc_1800D9CA9
0x1800d9c8d  mov     byte ptr [rsp+58h+lpBuffer], 1
0x1800d9c92  mov     r8, rsi
0x1800d9c95  mov     edx, ebx
0x1800d9c97  lea     rcx, aWinhttpDll_0; "WINHTTP.DLL"
0x1800d9c9e  call    sub_1800D9DA0
0x1800d9ca3  mov     ecx, eax
0x1800d9ca5  test    eax, eax
0x1800d9ca7  jnz     short loc_1800D9CCE
0x1800d9ca9  lea     eax, [rbx+7FF40000h]
0x1800d9caf  cmp     eax, 3FFh
0x1800d9cb4  ja      short loc_1800D9CCE
0x1800d9cb6  mov     byte ptr [rsp+58h+lpBuffer], dil
0x1800d9cbb  mov     r8, rsi
0x1800d9cbe  mov     edx, ebx
0x1800d9cc0  lea     rcx, aUrlmonDll_0; "URLMON.DLL"
0x1800d9cc7  call    sub_1800D9DA0
0x1800d9ccc  mov     ecx, eax
0x1800d9cce  mov     [rsp+58h+arg_10], rdi
0x1800d9cd3  mov     [rsp+58h+arg_8], rdi
0x1800d9cd8  test    ecx, ecx
0x1800d9cda  jz      short loc_1800D9CEC
0x1800d9cdc  mov     eax, ecx
0x1800d9cde  mov     [rsi+rax*2], di
0x1800d9ce2  mov     rcx, rsi; Src
0x1800d9ce5  call    sub_180019CD0
0x1800d9cea  jmp     short loc_1800D9D21
0x1800d9cec  mov     ecx, ebx
0x1800d9cee  call    sub_1800D8454
0x1800d9cf3  mov     rbx, rax
0x1800d9cf6  lea     rcx, [rsp+58h+arg_10]
0x1800d9cfb  call    sub_180019E20
0x1800d9d00  mov     [rsp+58h+arg_10], rbx
0x1800d9d05  mov     qword ptr [rsp+58h+nSize], rdi
0x1800d9d0a  mov     [rsp+58h+lpBuffer], rdi
0x1800d9d0f  xor     r9d, r9d
0x1800d9d12  mov     r8, rbx
0x1800d9d15  mov     edx, 0C00CE30Ah
0x1800d9d1a  xor     ecx, ecx
0x1800d9d1c  call    sub_180089E10
0x1800d9d21  mov     rbx, rax
0x1800d9d24  lea     rcx, [rsp+58h+arg_8]
0x1800d9d29  call    sub_180019E20
0x1800d9d2e  mov     [rsp+58h+arg_8], rbx
0x1800d9d33  jmp     short loc_1800D9D6B
0x1800d9d35  call    sub_1800A3C08
0x1800d9d3a  cmp     [rsp+58h+arg_10], 0
0x1800d9d40  jz      short loc_1800D9D4E
0x1800d9d42  xor     edx, edx
0x1800d9d44  lea     rcx, [rsp+58h+arg_10]
0x1800d9d49  call    sub_180015A80
0x1800d9d4e  lea     rdx, qword_1801F7908
0x1800d9d55  lea     rcx, [rsp+58h+arg_8]
0x1800d9d5a  call    sub_180015A80
0x1800d9d5f  xor     edi, edi
0x1800d9d61  mov     rsi, [rsp+58h+arg_18]
0x1800d9d66  mov     rbx, [rsp+58h+arg_8]
0x1800d9d6b  mov     rcx, rsi; lpMem
0x1800d9d6e  call    sub_180017480
0x1800d9d73  mov     [rsp+58h+arg_8], rdi
0x1800d9d78  lea     rcx, [rsp+58h+arg_8]
0x1800d9d7d  call    sub_180019E20
0x1800d9d82  lea     rcx, [rsp+58h+arg_10]
0x1800d9d87  call    sub_180019E20
0x1800d9d8c  mov     rax, rbx
0x1800d9d8f  add     rsp, 40h
0x1800d9d93  pop     rdi
0x1800d9d94  pop     rsi
0x1800d9d95  pop     rbx
0x1800d9d96  retn
0x180182ac7  push    rbp
0x180182ac9  sub     rsp, 40h
0x180182acd  mov     rbp, rdx
0x180182ad0  call    sub_18009FEFC
0x180182ad5  nop
0x180182ad6  add     rsp, 40h
0x180182ada  pop     rbp
0x180182adb  retn
```
