# GetCurrentDirectoryA

- ea: `0x180109b20`
- end: `0x180109cb9`
- name: `GetCurrentDirectoryA`
- size: `409`
- prototype: `DWORD __stdcall(DWORD nBufferLength, LPSTR lpBuffer)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18004b9d0`
- `0x180109b20`
- `0x180194f10`
- `0x1801a4010`

## import_xrefs

- `ntdll!RtlUnicodeToMultiByteSize` at `0x180109be8`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x180109be8`
- `ntdll!RtlFreeHeap` at `0x180109cab`
- `ntdll!RtlFreeHeap` at `0x1801a2a2f`
- `ntdll!RtlFreeHeap` at `0x1801a2a59`
- `ntdll!RtlFreeHeap` at `0x180109cab`
- `ntdll!RtlFreeHeap` at `0x1801a2a2f`
- `ntdll!RtlFreeHeap` at `0x1801a2a59`
- `ntdll!RtlGetCurrentDirectory_U` at `0x180109b78`
- `ntdll!RtlGetCurrentDirectory_U` at `0x1801a2a01`
- `ntdll!RtlGetCurrentDirectory_U` at `0x180109b78`
- `ntdll!RtlGetCurrentDirectory_U` at `0x1801a2a01`
- `ntdll!RtlAllocateHeap` at `0x180109c73`
- `ntdll!RtlAllocateHeap` at `0x180109c73`

## pseudocode

```c
DWORD __stdcall GetCurrentDirectoryA(DWORD nBufferLength, LPSTR lpBuffer)
{
  ULONG v2; // esi
  ULONG CurrentDirectory_U; // eax
  __int64 v5; // rcx
  ULONG v7; // edi
  WCHAR *v8; // rbx
  NTSTATUS v9; // eax
  DWORD v10; // edi
  WCHAR *Heap; // rax
  ULONG BytesInMultiByteString; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v13; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v14; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Buffer[128]; // [rsp+50h] [rbp-B0h] BYREF

  BytesInMultiByteString = 0;
  v2 = nBufferLength;
  if ( nBufferLength > 0xFFFD )
    v2 = 65533;
  v13 = 0;
  v14 = 0;
  CurrentDirectory_U = RtlGetCurrentDirectory_U(0x100u, Buffer);
  BytesInMultiByteString = CurrentDirectory_U;
  if ( !CurrentDirectory_U )
  {
LABEL_4:
    v5 = 3221225473LL;
LABEL_5:
    BaseSetLastNTError(v5);
    return 0;
  }
  v7 = CurrentDirectory_U + 2;
  if ( CurrentDirectory_U > 0x100 )
  {
    while ( v7 - 2 <= 0xFFFC )
    {
      Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
      v8 = Heap;
      if ( !Heap )
      {
        v5 = 3221225495LL;
        goto LABEL_5;
      }
      CurrentDirectory_U = RtlGetCurrentDirectory_U(v7, Heap);
      BytesInMultiByteString = CurrentDirectory_U;
      if ( !CurrentDirectory_U )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
        goto LABEL_4;
      }
      if ( CurrentDirectory_U < v7 )
        goto LABEL_8;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
      v7 = BytesInMultiByteString + 2;
    }
    v5 = 3221225734LL;
    goto LABEL_5;
  }
  v8 = Buffer;
LABEL_8:
  LOWORD(v14) = CurrentDirectory_U;
  WORD1(v14) = v7;
  *((_QWORD *)&v14 + 1) = v8;
  v9 = RtlUnicodeToMultiByteSize(&BytesInMultiByteString, v8, (unsigned __int16)CurrentDirectory_U);
  if ( v9 < 0 )
    goto LABEL_11;
  if ( v2 <= BytesInMultiByteString )
  {
    v10 = BytesInMultiByteString + 1;
    goto LABEL_12;
  }
  WORD1(v13) = v2;
  LOWORD(v13) = 0;
  *((_QWORD *)&v13 + 1) = lpBuffer;
  v9 = ((__int64 (__fastcall *)(__int128 *, __int128 *, _QWORD))pfnUnicodeStringToEightBitString)(&v13, &v14, 0);
  if ( v9 >= 0 )
  {
    v10 = (unsigned __int16)v13;
  }
  else
  {
LABEL_11:
    BaseSetLastNTError((unsigned int)v9);
    v10 = 0;
  }
LABEL_12:
  if ( v8 != Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  return v10;
}

```

## disassembly

```asm
0x180109b20  mov     [rsp-8+arg_10], rbx
0x180109b25  mov     [rsp-8+arg_18], rsi
0x180109b2a  push    rbp
0x180109b2b  push    rdi
0x180109b2c  push    r14
0x180109b2e  lea     rbp, [rsp-60h]
0x180109b33  sub     rsp, 160h
0x180109b3a  mov     rax, cs:__security_cookie
0x180109b41  xor     rax, rsp
0x180109b44  mov     [rbp+70h+var_20], rax
0x180109b48  mov     eax, 0FFFDh
0x180109b4d  mov     [rsp+170h+BytesInMultiByteString], 0
0x180109b55  cmp     ecx, eax
0x180109b57  mov     esi, ecx
0x180109b59  xorps   xmm0, xmm0
0x180109b5c  mov     r14, rdx
0x180109b5f  mov     ebx, 100h
0x180109b64  lea     rdx, [rsp+170h+Buffer]; Buffer
0x180109b69  mov     ecx, ebx; MaximumLength
0x180109b6b  cmova   esi, eax
0x180109b6e  movups  [rsp+170h+var_148], xmm0
0x180109b73  movups  [rsp+170h+var_138], xmm0
0x180109b78  call    cs:__imp_RtlGetCurrentDirectory_U
0x180109b7f  nop     dword ptr [rax+rax+00h]
0x180109b84  mov     [rsp+170h+BytesInMultiByteString], eax
0x180109b88  test    eax, eax
0x180109b8a  jnz     short loc_180109BBD
0x180109b8c  mov     ecx, 0C0000001h
0x180109b91  call    BaseSetLastNTError
0x180109b96  xor     eax, eax
0x180109b98  mov     rcx, [rbp+70h+var_20]
0x180109b9c  xor     rcx, rsp; StackCookie
0x180109b9f  call    __security_check_cookie
0x180109ba4  lea     r11, [rsp+170h+var_10]
0x180109bac  mov     rbx, [r11+30h]
0x180109bb0  mov     rsi, [r11+38h]
0x180109bb4  mov     rsp, r11
0x180109bb7  pop     r14
0x180109bb9  pop     rdi
0x180109bba  pop     rbp
0x180109bbb  retn
0x180109bbd  lea     edi, [rax+2]
0x180109bc0  cmp     eax, ebx
0x180109bc2  ja      loc_180109C53
0x180109bc8  lea     rbx, [rsp+170h+Buffer]
0x180109bcd  movzx   r8d, ax; BytesInUnicodeString
0x180109bd1  lea     rcx, [rsp+170h+BytesInMultiByteString]; BytesInMultiByteString
0x180109bd6  mov     rdx, rbx; UnicodeString
0x180109bd9  mov     word ptr [rsp+170h+var_138], ax
0x180109bde  mov     word ptr [rsp+170h+var_138+2], di
0x180109be3  mov     qword ptr [rsp+170h+var_138+8], rbx
0x180109be8  call    cs:__imp_RtlUnicodeToMultiByteSize
0x180109bef  nop     dword ptr [rax+rax+00h]
0x180109bf4  test    eax, eax
0x180109bf6  js      short loc_180109C32
0x180109bf8  mov     edi, [rsp+170h+BytesInMultiByteString]
0x180109bfc  cmp     esi, edi
0x180109bfe  jbe     loc_180109C95
0x180109c04  xor     eax, eax
0x180109c06  mov     word ptr [rsp+170h+var_148+2], si
0x180109c0b  mov     word ptr [rsp+170h+var_148], ax
0x180109c10  lea     rdx, [rsp+170h+var_138]
0x180109c15  mov     rax, cs:pfnUnicodeStringToEightBitString
0x180109c1c  lea     rcx, [rsp+170h+var_148]
0x180109c21  xor     r8d, r8d
0x180109c24  mov     qword ptr [rsp+170h+var_148+8], r14
0x180109c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109c2e  test    eax, eax
0x180109c30  jns     short loc_180109C4C
0x180109c32  mov     ecx, eax
0x180109c34  call    BaseSetLastNTError
0x180109c39  xor     edi, edi
0x180109c3b  lea     rax, [rsp+170h+Buffer]
0x180109c40  cmp     rbx, rax
0x180109c43  jnz     short loc_180109C99
0x180109c45  mov     eax, edi
0x180109c47  jmp     loc_180109B98
0x180109c4c  movzx   edi, word ptr [rsp+170h+var_148]
0x180109c51  jmp     short loc_180109C3B
0x180109c53  lea     eax, [rdi-2]
0x180109c56  cmp     eax, 0FFFCh
0x180109c5b  ja      loc_1801A2A6B
0x180109c61  mov     rcx, gs:60h
0x180109c6a  xor     edx, edx; Flags
0x180109c6c  mov     r8d, edi; Size
0x180109c6f  mov     rcx, [rcx+30h]; HeapHandle
0x180109c73  call    cs:__imp_RtlAllocateHeap
0x180109c7a  nop     dword ptr [rax+rax+00h]
0x180109c7f  mov     rbx, rax
0x180109c82  test    rax, rax
0x180109c85  jnz     loc_1801A29FC
0x180109c8b  mov     ecx, 0C0000017h
0x180109c90  jmp     loc_180109B91
0x180109c95  inc     edi
0x180109c97  jmp     short loc_180109C3B
0x180109c99  mov     rcx, gs:60h
0x180109ca2  mov     r8, rbx; P
0x180109ca5  xor     edx, edx; Flags
0x180109ca7  mov     rcx, [rcx+30h]; HeapHandle
0x180109cab  call    cs:__imp_RtlFreeHeap
0x180109cb2  nop     dword ptr [rax+rax+00h]
0x180109cb7  jmp     short loc_180109C45
0x1801a29fc  mov     rdx, rbx; Buffer
0x1801a29ff  mov     ecx, edi; MaximumLength
0x1801a2a01  call    cs:__imp_RtlGetCurrentDirectory_U
0x1801a2a08  nop     dword ptr [rax+rax+00h]
0x1801a2a0d  mov     [rsp+170h+BytesInMultiByteString], eax
0x1801a2a11  test    eax, eax
0x1801a2a13  jz      short loc_1801A2A47
0x1801a2a15  cmp     eax, edi
0x1801a2a17  jb      loc_180109BCD
0x1801a2a1d  mov     rcx, gs:60h
0x1801a2a26  mov     r8, rbx; P
0x1801a2a29  xor     edx, edx; Flags
0x1801a2a2b  mov     rcx, [rcx+30h]; HeapHandle
0x1801a2a2f  call    cs:__imp_RtlFreeHeap
0x1801a2a36  nop     dword ptr [rax+rax+00h]
0x1801a2a3b  mov     edi, [rsp+170h+BytesInMultiByteString]
0x1801a2a3f  add     edi, 2
0x1801a2a42  jmp     loc_180109C53
0x1801a2a47  mov     rcx, gs:60h
0x1801a2a50  mov     r8, rbx; P
0x1801a2a53  xor     edx, edx; Flags
0x1801a2a55  mov     rcx, [rcx+30h]; HeapHandle
0x1801a2a59  call    cs:__imp_RtlFreeHeap
0x1801a2a60  nop     dword ptr [rax+rax+00h]
0x1801a2a65  nop
0x1801a2a66  jmp     loc_180109B8C
0x1801a2a6b  mov     ecx, 0C0000106h
0x1801a2a70  jmp     loc_180109B91
```
