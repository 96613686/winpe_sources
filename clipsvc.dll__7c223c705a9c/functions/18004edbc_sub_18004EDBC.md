# sub_18004EDBC

- ea: `0x18004edbc`
- end: `0x18004efe6`
- name: `sub_18004EDBC`
- size: `554`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18004de4c`

## callees

- `0x18000bfdc`
- `0x18000e0c0`
- `0x18004073c`
- `0x18004edbc`
- `0x1800a6b00`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004eee1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ef3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ef95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004efa7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004eee1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ef3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ef95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004efa7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004ef0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004ef6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004ef0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004ef6c`

## pseudocode

```c
__int64 __fastcall sub_18004EDBC(__int64 a1, __int64 a2, char a3, int a4, int a5, __int64 a6, int *a7)
{
  int v10; // edi
  unsigned int v11; // ebx
  __int64 v12; // rcx
  int v13; // eax
  int v14; // esi
  int i; // eax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 (__fastcall *v19)(__int64, HSTRING *); // rbx
  PCWSTR v20; // rax
  HSTRING v22; // [rsp+20h] [rbp-20h] BYREF
  HSTRING string; // [rsp+28h] [rbp-18h] BYREF
  __int64 v24; // [rsp+30h] [rbp-10h] BYREF
  int v25; // [rsp+70h] [rbp+30h] BYREF
  int v26; // [rsp+74h] [rbp+34h]
  int v27; // [rsp+80h] [rbp+40h] BYREF

  v26 = HIDWORD(a1);
  v27 = 0;
  v25 = 0;
  v24 = 0;
  string = 0;
  v22 = 0;
  v10 = a3 & 8;
  if ( (a3 & 8) != 0 && (a3 & 4) != 0 )
  {
    v11 = -2147024809;
    v12 = 2147942487LL;
LABEL_4:
    sub_18000BFDC(v12);
    goto LABEL_26;
  }
  v11 = 0;
  if ( (a3 & 1) != 0 )
  {
    v13 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a2 + 1000LL))(a2, &v27);
    v11 = v13;
    if ( v13 < 0 )
    {
LABEL_7:
      v12 = (unsigned int)v13;
      goto LABEL_4;
    }
    v14 = 0;
    for ( i = 0; i < 5; ++i )
    {
      if ( (a4 & qword_1800B78E0[i]) != 0 && v27 == HIDWORD(qword_1800B78E0[i]) )
        goto LABEL_13;
    }
  }
  else
  {
LABEL_13:
    v14 = 1;
    if ( (a3 & 2) == 0 )
      goto LABEL_16;
    v13 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a2 + 128LL))(a2, &v25);
    v11 = v13;
    if ( v13 < 0 )
      goto LABEL_7;
    v14 = a5 & v25;
    if ( (a5 & v25) != 0 )
    {
LABEL_16:
      if ( v10 )
      {
        v13 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 72LL))(a2, &v24);
        v11 = v13;
        if ( v13 < 0 )
          goto LABEL_7;
        v16 = v24;
        v17 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v24 + 88LL);
        WindowsDeleteString(string);
        string = 0;
        v13 = v17(v16, &string);
        v11 = v13;
        if ( v13 < 0 )
          goto LABEL_7;
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        if ( !(unsigned int)sub_18004073C(StringRawBuffer, a6) )
        {
          v14 = 0;
          goto LABEL_25;
        }
        if ( !v14 )
          goto LABEL_25;
      }
      if ( (a3 & 4) != 0 )
      {
        v19 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 112LL);
        WindowsDeleteString(v22);
        v22 = 0;
        v13 = v19(a2, &v22);
        v11 = v13;
        if ( v13 < 0 )
          goto LABEL_7;
        v20 = WindowsGetStringRawBuffer(v22, 0);
        v14 = (unsigned int)sub_18004073C(v20, a6) != 0 ? v14 : 0;
      }
    }
  }
LABEL_25:
  *a7 = v14;
LABEL_26:
  sub_18000E0C0(v11);
  WindowsDeleteString(v22);
  v22 = 0;
  WindowsDeleteString(string);
  string = 0;
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  return v11;
}

```

## disassembly

```asm
0x18004edbc  mov     [rsp-28h+arg_8], rbx
0x18004edc1  mov     [rsp-28h+arg_18], rsi
0x18004edc6  mov     [rsp-28h+arg_0], rcx
0x18004edcb  push    rbp
0x18004edcc  push    rdi
0x18004edcd  push    r12
0x18004edcf  push    r14
0x18004edd1  push    r15
0x18004edd3  mov     rbp, rsp
0x18004edd6  sub     rsp, 40h
0x18004edda  mov     edi, r8d
0x18004eddd  mov     [rbp+arg_10], 0
0x18004ede4  mov     dword ptr [rbp+arg_0], 0
0x18004edeb  mov     r12d, r9d
0x18004edee  mov     [rbp+var_10], 0
0x18004edf6  mov     r14d, r8d
0x18004edf9  mov     [rbp+string], 0
0x18004ee01  mov     r15, rdx
0x18004ee04  mov     [rbp+var_20], 0
0x18004ee0c  and     edi, 8
0x18004ee0f  jz      short loc_18004EE28
0x18004ee11  test    r14b, 4
0x18004ee15  jz      short loc_18004EE28
0x18004ee17  mov     ebx, 80070057h
0x18004ee1c  mov     ecx, ebx
0x18004ee1e  call    sub_18000BFDC
0x18004ee23  jmp     loc_18004EF8A
0x18004ee28  xor     ebx, ebx
0x18004ee2a  test    r14b, 1
0x18004ee2e  jz      short loc_18004EE7C
0x18004ee30  mov     rax, [rdx]
0x18004ee33  mov     rcx, r15
0x18004ee36  lea     rdx, [rbp+arg_10]
0x18004ee3a  mov     rax, [rax+3E8h]
0x18004ee41  call    cs:__guard_dispatch_icall_fptr
0x18004ee47  mov     ebx, eax
0x18004ee49  test    eax, eax
0x18004ee4b  jns     short loc_18004EE51
0x18004ee4d  mov     ecx, eax
0x18004ee4f  jmp     short loc_18004EE1E
0x18004ee51  mov     edx, [rbp+arg_10]
0x18004ee54  lea     r8, qword_1800B78E0
0x18004ee5b  xor     esi, esi
0x18004ee5d  xor     eax, eax
0x18004ee5f  cmp     eax, 5
0x18004ee62  jge     loc_18004EF84
0x18004ee68  movsxd  rcx, eax
0x18004ee6b  test    [r8+rcx*8], r12d
0x18004ee6f  jz      short loc_18004EE78
0x18004ee71  cmp     edx, [r8+rcx*8+4]
0x18004ee76  jz      short loc_18004EE7C
0x18004ee78  inc     eax
0x18004ee7a  jmp     short loc_18004EE5F
0x18004ee7c  mov     esi, 1
0x18004ee81  test    r14b, 2
0x18004ee85  jz      short loc_18004EEB0
0x18004ee87  mov     rax, [r15]
0x18004ee8a  lea     rdx, [rbp+arg_0]
0x18004ee8e  mov     rcx, r15
0x18004ee91  mov     rax, [rax+80h]
0x18004ee98  call    cs:__guard_dispatch_icall_fptr
0x18004ee9e  mov     ebx, eax
0x18004eea0  test    eax, eax
0x18004eea2  js      short loc_18004EE4D
0x18004eea4  mov     esi, dword ptr [rbp+arg_0]
0x18004eea7  and     esi, [rbp+arg_20]
0x18004eeaa  jz      loc_18004EF84
0x18004eeb0  test    edi, edi
0x18004eeb2  jz      short loc_18004EF2D
0x18004eeb4  mov     rax, [r15]
0x18004eeb7  lea     rdx, [rbp+var_10]
0x18004eebb  mov     rcx, r15
0x18004eebe  mov     rax, [rax+48h]
0x18004eec2  call    cs:__guard_dispatch_icall_fptr
0x18004eec8  mov     ebx, eax
0x18004eeca  test    eax, eax
0x18004eecc  js      loc_18004EE4D
0x18004eed2  mov     rdi, [rbp+var_10]
0x18004eed6  mov     rcx, [rbp+string]; string
0x18004eeda  mov     rax, [rdi]
0x18004eedd  mov     rbx, [rax+58h]
0x18004eee1  call    cs:WindowsDeleteString
0x18004eee7  lea     rdx, [rbp+string]
0x18004eeeb  mov     [rbp+string], 0
0x18004eef3  mov     rcx, rdi
0x18004eef6  mov     rax, rbx
0x18004eef9  call    cs:__guard_dispatch_icall_fptr
0x18004eeff  mov     ebx, eax
0x18004ef01  test    eax, eax
0x18004ef03  js      loc_18004EE4D
0x18004ef09  mov     rcx, [rbp+string]; string
0x18004ef0d  xor     edx, edx; length
0x18004ef0f  call    cs:WindowsGetStringRawBuffer
0x18004ef15  mov     rdx, [rbp+arg_28]
0x18004ef19  mov     rcx, rax
0x18004ef1c  call    sub_18004073C
0x18004ef21  test    eax, eax
0x18004ef23  jnz     short loc_18004EF29
0x18004ef25  xor     esi, esi
0x18004ef27  jmp     short loc_18004EF84
0x18004ef29  test    esi, esi
0x18004ef2b  jz      short loc_18004EF84
0x18004ef2d  test    r14b, 4
0x18004ef31  jz      short loc_18004EF84
0x18004ef33  mov     rax, [r15]
0x18004ef36  mov     rcx, [rbp+var_20]; string
0x18004ef3a  mov     rbx, [rax+70h]
0x18004ef3e  call    cs:WindowsDeleteString
0x18004ef44  lea     rdx, [rbp+var_20]
0x18004ef48  mov     [rbp+var_20], 0
0x18004ef50  mov     rcx, r15
0x18004ef53  mov     rax, rbx
0x18004ef56  call    cs:__guard_dispatch_icall_fptr
0x18004ef5c  mov     ebx, eax
0x18004ef5e  test    eax, eax
0x18004ef60  js      loc_18004EE4D
0x18004ef66  mov     rcx, [rbp+var_20]; string
0x18004ef6a  xor     edx, edx; length
0x18004ef6c  call    cs:WindowsGetStringRawBuffer
0x18004ef72  mov     rdx, [rbp+arg_28]
0x18004ef76  mov     rcx, rax
0x18004ef79  call    sub_18004073C
0x18004ef7e  neg     eax
0x18004ef80  sbb     ecx, ecx
0x18004ef82  and     esi, ecx
0x18004ef84  mov     rax, [rbp+arg_30]
0x18004ef88  mov     [rax], esi
0x18004ef8a  mov     ecx, ebx
0x18004ef8c  call    sub_18000E0C0
0x18004ef91  mov     rcx, [rbp+var_20]; string
0x18004ef95  call    cs:WindowsDeleteString
0x18004ef9b  mov     rcx, [rbp+string]; string
0x18004ef9f  mov     [rbp+var_20], 0
0x18004efa7  call    cs:WindowsDeleteString
0x18004efad  mov     rcx, [rbp+var_10]
0x18004efb1  mov     [rbp+string], 0
0x18004efb9  test    rcx, rcx
0x18004efbc  jz      short loc_18004EFCB
0x18004efbe  mov     rax, [rcx]
0x18004efc1  mov     rax, [rax+10h]
0x18004efc5  call    cs:__guard_dispatch_icall_fptr
0x18004efcb  lea     r11, [rsp+40h+var_s0]
0x18004efd0  mov     eax, ebx
0x18004efd2  mov     rbx, [r11+38h]
0x18004efd6  mov     rsi, [r11+48h]
0x18004efda  mov     rsp, r11
0x18004efdd  pop     r15
0x18004efdf  pop     r14
0x18004efe1  pop     r12
0x18004efe3  pop     rdi
0x18004efe4  pop     rbp
0x18004efe5  retn
```
