# DiscpChangeiqnNameForHBA

- ea: `0x180008960`
- end: `0x180008af1`
- name: `DiscpChangeiqnNameForHBA`
- size: `401`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18000ba10`
- `0x18000f7f8`

## callees

- `0x180001410`
- `0x180001cfe`
- `0x180008960`

## import_xrefs

- `ISCSIUM!DiscpCopyToCountedString` at `0x1800089e5`
- `ISCSIUM!DiscpCopyToCountedString` at `0x180008a56`
- `ISCSIUM!DiscpCopyToCountedString` at `0x1800089e5`
- `ISCSIUM!DiscpCopyToCountedString` at `0x180008a56`
- `ISCSIUM!DiscpExecuteMethod` at `0x180008a35`
- `ISCSIUM!DiscpExecuteMethod` at `0x180008aa9`
- `ISCSIUM!DiscpExecuteMethod` at `0x180008a35`
- `ISCSIUM!DiscpExecuteMethod` at `0x180008aa9`
- `ISCSIUM!DiscpAllocMemory` at `0x1800089b8`
- `ISCSIUM!DiscpAllocMemory` at `0x1800089b8`
- `ISCSIUM!DiscpFreeMemory` at `0x180008a44`
- `ISCSIUM!DiscpFreeMemory` at `0x180008abc`
- `ISCSIUM!DiscpFreeMemory` at `0x180008ac5`
- `ISCSIUM!DiscpFreeMemory` at `0x180008a44`
- `ISCSIUM!DiscpFreeMemory` at `0x180008abc`
- `ISCSIUM!DiscpFreeMemory` at `0x180008ac5`

## pseudocode

```c
__int64 __fastcall DiscpChangeiqnNameForHBA(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rdi
  __int64 v7; // r8
  __int64 v8; // r8
  unsigned int v9; // ebx
  int v11; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int *v12; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v13[448]; // [rsp+60h] [rbp-A0h] BYREF

  memset_0(v13, 0, sizeof(v13));
  v12 = 0;
  v11 = 0;
  v6 = DiscpAllocMemory(448);
  if ( v6 )
  {
    if ( a2 )
    {
      v11 = 260;
      DiscpCopyToCountedString(v13, a2, 223);
      v7 = *(_QWORD *)(a1 + 40);
      v12 = 0;
      if ( !(unsigned int)DiscpExecuteMethod(MSiSCSI_Operations_GUID, 0, v7, 91, v13, 448, &v12, &v11, 4) )
        DiscpFreeMemory(v12);
    }
    DiscpCopyToCountedString(v6, a3, 223);
    v8 = *(_QWORD *)(a1 + 40);
    v11 = 260;
    v12 = 0;
    v9 = DiscpExecuteMethod(MSiSCSI_Operations_GUID, 0, v8, 92, v6, 448, &v12, &v11, 4);
    if ( !v9 )
    {
      v9 = *v12;
      DiscpFreeMemory(v12);
    }
    DiscpFreeMemory(v6);
  }
  else
  {
    return 8;
  }
  return v9;
}

```

## disassembly

```asm
0x180008960  push    rbp
0x180008962  push    rbx
0x180008963  push    rsi
0x180008964  push    rdi
0x180008965  push    r14
0x180008967  lea     rbp, [rsp-130h]
0x18000896f  sub     rsp, 230h
0x180008976  mov     rax, cs:__security_cookie
0x18000897d  xor     rax, rsp
0x180008980  mov     [rbp+150h+var_30], rax
0x180008987  mov     r14, r8
0x18000898a  mov     rbx, rdx
0x18000898d  mov     rsi, rcx
0x180008990  xor     edx, edx; Val
0x180008992  mov     r8d, 1C0h; Size
0x180008998  lea     rcx, [rsp+250h+var_1F0]; void *
0x18000899d  call    memset_0
0x1800089a2  mov     ecx, 1C0h
0x1800089a7  mov     [rsp+250h+var_1F8], 0
0x1800089b0  mov     [rsp+250h+var_200], 0
0x1800089b8  call    cs:__imp_DiscpAllocMemory
0x1800089be  mov     rdi, rax
0x1800089c1  test    rax, rax
0x1800089c4  jz      loc_180008ACD
0x1800089ca  test    rbx, rbx
0x1800089cd  jz      short loc_180008A4A
0x1800089cf  mov     r8d, 0DFh
0x1800089d5  mov     [rsp+250h+var_200], 104h
0x1800089dd  mov     rdx, rbx
0x1800089e0  lea     rcx, [rsp+250h+var_1F0]
0x1800089e5  call    cs:__imp_DiscpCopyToCountedString
0x1800089eb  mov     r8, [rsi+28h]
0x1800089ef  lea     rax, [rsp+250h+var_200]
0x1800089f4  mov     [rsp+250h+var_210], 4
0x1800089fc  lea     rcx, MSiSCSI_Operations_GUID
0x180008a03  mov     [rsp+250h+var_218], rax
0x180008a08  mov     r9d, 5Bh ; '['
0x180008a0e  lea     rax, [rsp+250h+var_1F8]
0x180008a13  mov     [rsp+250h+var_1F8], 0
0x180008a1c  mov     [rsp+250h+var_220], rax
0x180008a21  xor     edx, edx
0x180008a23  lea     rax, [rsp+250h+var_1F0]
0x180008a28  mov     [rsp+250h+var_228], 1C0h
0x180008a30  mov     [rsp+250h+var_230], rax
0x180008a35  call    cs:__imp_DiscpExecuteMethod
0x180008a3b  test    eax, eax
0x180008a3d  jnz     short loc_180008A4A
0x180008a3f  mov     rcx, [rsp+250h+var_1F8]
0x180008a44  call    cs:__imp_DiscpFreeMemory
0x180008a4a  mov     r8d, 0DFh
0x180008a50  mov     rdx, r14
0x180008a53  mov     rcx, rdi
0x180008a56  call    cs:__imp_DiscpCopyToCountedString
0x180008a5c  mov     r8, [rsi+28h]
0x180008a60  lea     rax, [rsp+250h+var_200]
0x180008a65  mov     [rsp+250h+var_210], 4
0x180008a6d  lea     rcx, MSiSCSI_Operations_GUID
0x180008a74  mov     [rsp+250h+var_218], rax
0x180008a79  mov     r9d, 5Ch ; '\'
0x180008a7f  lea     rax, [rsp+250h+var_1F8]
0x180008a84  mov     [rsp+250h+var_200], 104h
0x180008a8c  mov     [rsp+250h+var_220], rax
0x180008a91  xor     edx, edx
0x180008a93  mov     [rsp+250h+var_228], 1C0h
0x180008a9b  mov     [rsp+250h+var_230], rdi
0x180008aa0  mov     [rsp+250h+var_1F8], 0
0x180008aa9  call    cs:__imp_DiscpExecuteMethod
0x180008aaf  mov     ebx, eax
0x180008ab1  test    eax, eax
0x180008ab3  jnz     short loc_180008AC2
0x180008ab5  mov     rcx, [rsp+250h+var_1F8]
0x180008aba  mov     ebx, [rcx]
0x180008abc  call    cs:__imp_DiscpFreeMemory
0x180008ac2  mov     rcx, rdi
0x180008ac5  call    cs:__imp_DiscpFreeMemory
0x180008acb  jmp     short loc_180008AD2
0x180008acd  mov     ebx, 8
0x180008ad2  mov     eax, ebx
0x180008ad4  mov     rcx, [rbp+150h+var_30]
0x180008adb  xor     rcx, rsp; StackCookie
0x180008ade  call    __security_check_cookie
0x180008ae3  add     rsp, 230h
0x180008aea  pop     r14
0x180008aec  pop     rdi
0x180008aed  pop     rsi
0x180008aee  pop     rbx
0x180008aef  pop     rbp
0x180008af0  retn
```
