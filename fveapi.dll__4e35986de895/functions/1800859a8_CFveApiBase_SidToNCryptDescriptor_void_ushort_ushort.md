# CFveApiBase::SidToNCryptDescriptor(void *,ushort,ushort * *)

- ea: `0x1800859a8`
- end: `0x180085be1`
- name: `?SidToNCryptDescriptor@CFveApiBase@@SAJPEAXGPEAPEAG@Z`
- size: `569`
- prototype: `__int64 __fastcall(void *, unsigned __int16, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800b58f8`

## callees

- `0x1800050c0`
- `0x180005410`
- `0x18000ba30`
- `0x18000ca50`
- `0x18002fea0`
- `0x18003a230`
- `0x180045ea0`
- `0x1800859a8`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180085b99`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180124472`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180085b99`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180124472`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180085b85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18012445e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180085b85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18012445e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180085baf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180124488`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180085baf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180124488`
- `ext-ms-win-feclient-encryptedfile-l1-1-3!DpQueryUserProtectorDescriptor` at `0x180085a22`
- `ext-ms-win-feclient-encryptedfile-l1-1-3!DpQueryUserProtectorDescriptor` at `0x180085a22`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800859e7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800859e7`

## pseudocode

```c
__int64 __fastcall CFveApiBase::SidToNCryptDescriptor(void *a1, char a2, unsigned __int16 **a3)
{
  unsigned __int16 *v5; // rdi
  int LastHresultError; // ebx
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // rax
  unsigned __int16 *v9; // rax
  int v10; // eax
  __int64 v11; // rcx
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rsi
  unsigned __int16 *v14; // rax
  void *v15; // rdi
  HANDLE ProcessHeap; // rax
  unsigned __int64 v18; // [rsp+28h] [rbp-40h] BYREF
  unsigned __int16 *v19; // [rsp+30h] [rbp-38h]
  HLOCAL hMem; // [rsp+38h] [rbp-30h] BYREF
  LPVOID lpMem; // [rsp+40h] [rbp-28h] BYREF

  v5 = 0;
  v19 = 0;
  lpMem = 0;
  hMem = 0;
  if ( !ConvertSidToStringSidW(a1, (LPWSTR *)&hMem) )
  {
    LastHresultError = GetLastHresultError();
    goto LABEL_26;
  }
  if ( (a2 & 2) == 0 )
  {
    v11 = -1;
    v12 = -1;
    do
      ++v12;
    while ( *((_WORD *)hMem + v12) );
    v18 = v12;
    v13 = v12 + 5;
    if ( v12 + 5 < v12 )
    {
      v13 = -1;
      v18 = -1;
      LastHresultError = -2147024362;
    }
    else
    {
      v18 = v12 + 5;
      LastHresultError = 0;
      v11 = v12 + 5;
    }
    if ( LastHresultError < 0 )
      goto LABEL_26;
    v14 = (unsigned __int16 *)CFveApiBase::FastAlloc(2 * v11);
    v5 = v14;
    v19 = v14;
    if ( v14 )
    {
      LastHresultError = StringCchCopyW(v14, v13, L"SID=");
      if ( LastHresultError < 0 )
        goto LABEL_26;
      v10 = StringCchCatW(v5, v13, (const unsigned __int16 *)hMem);
      goto LABEL_24;
    }
LABEL_21:
    LastHresultError = -2147024882;
    goto LABEL_26;
  }
  LastHresultError = DpQueryUserProtectorDescriptor(0, hMem, 1, &lpMem);
  if ( LastHresultError < 0 )
    goto LABEL_26;
  v7 = -1;
  do
    ++v7;
  while ( *((_WORD *)lpMem + v7) );
  v8 = v7 + 1;
  if ( v7 + 1 < v7 )
  {
    v8 = -1;
    v18 = -1;
    LastHresultError = -2147024362;
  }
  else
  {
    v18 = v7 + 1;
    LastHresultError = 0;
  }
  if ( LastHresultError < 0 )
    goto LABEL_26;
  LastHresultError = ULongLongMult(v8, 2u, &v18);
  if ( LastHresultError < 0 )
    goto LABEL_26;
  v9 = (unsigned __int16 *)CFveApiBase::FastAlloc(v18);
  v5 = v9;
  v19 = v9;
  if ( !v9 )
    goto LABEL_21;
  v10 = StringCbCopyW(v9, v18, (const unsigned __int16 *)lpMem);
LABEL_24:
  LastHresultError = v10;
  if ( v10 >= 0 )
  {
    *a3 = v5;
    v19 = 0;
    v5 = 0;
  }
LABEL_26:
  if ( v5 )
    CFveApiBase::FastFree(v5);
  v15 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v15);
  }
  if ( hMem )
    LocalFree(hMem);
  return (unsigned int)LastHresultError;
}

```

## disassembly

```asm
0x1800859a8  mov     r11, rsp
0x1800859ab  mov     [r11+10h], rbx
0x1800859af  mov     [r11+20h], rsi
0x1800859b3  push    rdi
0x1800859b4  push    r14
0x1800859b6  push    r15
0x1800859b8  sub     rsp, 50h
0x1800859bc  mov     rax, cs:__security_cookie
0x1800859c3  xor     rax, rsp
0x1800859c6  mov     [rsp+68h+var_20], rax
0x1800859cb  mov     r14, r8
0x1800859ce  movzx   ebx, dx
0x1800859d1  xor     r15d, r15d
0x1800859d4  mov     edi, r15d
0x1800859d7  mov     [r11-38h], r15
0x1800859db  mov     [r11-28h], r15
0x1800859df  mov     [r11-30h], r15
0x1800859e3  lea     rdx, [r11-30h]; StringSid
0x1800859e7  call    cs:__imp_ConvertSidToStringSidW
0x1800859ee  nop     dword ptr [rax+rax+00h]
0x1800859f3  test    eax, eax
0x1800859f5  jnz     short loc_180085A07
0x1800859f7  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x1800859fc  mov     ebx, eax
0x1800859fe  mov     [rsp+68h+var_48], eax
0x180085a02  jmp     loc_180085B6E
0x180085a07  mov     rdx, [rsp+68h+hMem]
0x180085a0c  test    bl, 2
0x180085a0f  jz      loc_180085ACC
0x180085a15  lea     r9, [rsp+68h+lpMem]
0x180085a1a  mov     r8d, 1
0x180085a20  xor     ecx, ecx
0x180085a22  call    cs:__imp_DpQueryUserProtectorDescriptor
0x180085a29  nop     dword ptr [rax+rax+00h]
0x180085a2e  mov     ebx, eax
0x180085a30  mov     [rsp+68h+var_48], eax
0x180085a34  test    eax, eax
0x180085a36  js      loc_180085B6E
0x180085a3c  mov     rax, [rsp+68h+lpMem]
0x180085a41  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180085a45  mov     rdx, rcx
0x180085a48  inc     rdx
0x180085a4b  cmp     [rax+rdx*2], r15w
0x180085a50  jnz     short loc_180085A48
0x180085a52  lea     rax, [rdx+1]
0x180085a56  cmp     rax, rdx
0x180085a59  jb      short loc_180085A65
0x180085a5b  mov     [rsp+68h+var_40], rax
0x180085a60  mov     ebx, r15d
0x180085a63  jmp     short loc_180085A72
0x180085a65  mov     rax, rcx
0x180085a68  mov     [rsp+68h+var_40], rcx
0x180085a6d  mov     ebx, 80070216h
0x180085a72  mov     [rsp+68h+var_48], ebx
0x180085a76  test    ebx, ebx
0x180085a78  js      loc_180085B6E
0x180085a7e  lea     r8, [rsp+68h+var_40]; unsigned __int64 *
0x180085a83  mov     edx, 2; unsigned __int64
0x180085a88  mov     rcx, rax; unsigned __int64
0x180085a8b  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180085a90  mov     ebx, eax
0x180085a92  mov     [rsp+68h+var_48], eax
0x180085a96  test    eax, eax
0x180085a98  js      loc_180085B6E
0x180085a9e  mov     rcx, [rsp+68h+var_40]; unsigned __int64
0x180085aa3  call    ?FastAlloc@CFveApiBase@@SAPEAX_K@Z; CFveApiBase::FastAlloc(unsigned __int64)
0x180085aa8  mov     rdi, rax
0x180085aab  mov     [rsp+68h+var_38], rax
0x180085ab0  test    rax, rax
0x180085ab3  jz      short loc_180085B22
0x180085ab5  mov     r8, [rsp+68h+lpMem]; unsigned __int16 *
0x180085aba  mov     rdx, [rsp+68h+var_40]; unsigned __int64
0x180085abf  mov     rcx, rax; unsigned __int16 *
0x180085ac2  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180085ac7  jmp     loc_180085B59
0x180085acc  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180085ad0  mov     rax, rcx
0x180085ad3  inc     rax
0x180085ad6  cmp     [rdx+rax*2], r15w
0x180085adb  jnz     short loc_180085AD3
0x180085add  mov     [rsp+68h+var_40], rax
0x180085ae2  lea     rsi, [rax+5]
0x180085ae6  cmp     rsi, rax
0x180085ae9  jb      short loc_180085AF8
0x180085aeb  mov     [rsp+68h+var_40], rsi
0x180085af0  mov     ebx, r15d
0x180085af3  mov     rcx, rsi
0x180085af6  jmp     short loc_180085B05
0x180085af8  mov     rsi, rcx
0x180085afb  mov     [rsp+68h+var_40], rcx
0x180085b00  mov     ebx, 80070216h
0x180085b05  mov     [rsp+68h+var_48], ebx
0x180085b09  test    ebx, ebx
0x180085b0b  js      short loc_180085B6E
0x180085b0d  add     rcx, rcx; unsigned __int64
0x180085b10  call    ?FastAlloc@CFveApiBase@@SAPEAX_K@Z; CFveApiBase::FastAlloc(unsigned __int64)
0x180085b15  mov     rdi, rax
0x180085b18  mov     [rsp+68h+var_38], rax
0x180085b1d  test    rax, rax
0x180085b20  jnz     short loc_180085B2D
0x180085b22  mov     ebx, 8007000Eh
0x180085b27  mov     [rsp+68h+var_48], ebx
0x180085b2b  jmp     short loc_180085B6E
0x180085b2d  lea     r8, aSid_0; "SID="
0x180085b34  mov     rdx, rsi; unsigned __int64
0x180085b37  mov     rcx, rdi; unsigned __int16 *
0x180085b3a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180085b3f  mov     ebx, eax
0x180085b41  mov     [rsp+68h+var_48], eax
0x180085b45  test    eax, eax
0x180085b47  js      short loc_180085B6E
0x180085b49  mov     r8, [rsp+68h+hMem]; unsigned __int16 *
0x180085b4e  mov     rdx, rsi; unsigned __int64
0x180085b51  mov     rcx, rdi; unsigned __int16 *
0x180085b54  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180085b59  test    eax, eax
0x180085b5b  mov     [rsp+68h+var_48], eax
0x180085b5f  mov     ebx, eax
0x180085b61  js      short loc_180085B6E
0x180085b63  mov     [r14], rdi
0x180085b66  mov     [rsp+68h+var_38], r15
0x180085b6b  mov     rdi, r15
0x180085b6e  test    rdi, rdi
0x180085b71  jz      short loc_180085B7B
0x180085b73  mov     rcx, rdi; lpMem
0x180085b76  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x180085b7b  mov     rdi, [rsp+68h+lpMem]
0x180085b80  test    rdi, rdi
0x180085b83  jz      short loc_180085BA5
0x180085b85  call    cs:__imp_GetProcessHeap
0x180085b8c  nop     dword ptr [rax+rax+00h]
0x180085b91  mov     r8, rdi; lpMem
0x180085b94  xor     edx, edx; dwFlags
0x180085b96  mov     rcx, rax; hHeap
0x180085b99  call    cs:__imp_HeapFree
0x180085ba0  nop     dword ptr [rax+rax+00h]
0x180085ba5  mov     rcx, [rsp+68h+hMem]; hMem
0x180085baa  test    rcx, rcx
0x180085bad  jz      short loc_180085BBB
0x180085baf  call    cs:__imp_LocalFree
0x180085bb6  nop     dword ptr [rax+rax+00h]
0x180085bbb  mov     eax, ebx
0x180085bbd  mov     rcx, [rsp+68h+var_20]
0x180085bc2  xor     rcx, rsp; StackCookie
0x180085bc5  call    __security_check_cookie
0x180085bca  lea     r11, [rsp+68h+var_18]
0x180085bcf  mov     rbx, [r11+28h]
0x180085bd3  mov     rsi, [r11+38h]
0x180085bd7  mov     rsp, r11
0x180085bda  pop     r15
0x180085bdc  pop     r14
0x180085bde  pop     rdi
0x180085bdf  retn
0x18012443c  push    rbx
0x18012443e  push    rbp
0x18012443f  sub     rsp, 28h
0x180124443  mov     rbp, rdx
0x180124446  mov     rcx, [rbp+30h]; lpMem
0x18012444a  test    rcx, rcx
0x18012444d  jz      short loc_180124455
0x18012444f  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x180124454  nop
0x180124455  mov     rbx, [rbp+40h]
0x180124459  test    rbx, rbx
0x18012445c  jz      short loc_18012447F
0x18012445e  call    cs:__imp_GetProcessHeap
0x180124465  nop     dword ptr [rax+rax+00h]
0x18012446a  mov     r8, rbx; lpMem
0x18012446d  xor     edx, edx; dwFlags
0x18012446f  mov     rcx, rax; hHeap
0x180124472  call    cs:__imp_HeapFree
0x180124479  nop     dword ptr [rax+rax+00h]
0x18012447e  nop
0x18012447f  mov     rcx, [rbp+38h]; hMem
0x180124483  test    rcx, rcx
0x180124486  jz      short loc_180124495
0x180124488  call    cs:__imp_LocalFree
0x18012448f  nop     dword ptr [rax+rax+00h]
0x180124494  nop
0x180124495  add     rsp, 28h
0x180124499  pop     rbp
0x18012449a  pop     rbx
0x18012449b  retn
```
