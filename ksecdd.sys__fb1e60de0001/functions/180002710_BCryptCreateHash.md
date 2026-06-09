# BCryptCreateHash

- ea: `0x180002710`
- end: `0x18000276f`
- name: `BCryptCreateHash`
- size: `95`
- prototype: `NTSTATUS __stdcall(BCRYPT_ALG_HANDLE hAlgorithm, BCRYPT_HASH_HANDLE *phHash, PUCHAR pbHashObject, ULONG cbHashObject, PUCHAR pbSecret, ULONG cbSecret, ULONG dwFlags)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180024034`

## callees

- `0x180002710`
- `0x180010980`

## pseudocode

```c
NTSTATUS __stdcall BCryptCreateHash(
        BCRYPT_ALG_HANDLE hAlgorithm,
        BCRYPT_HASH_HANDLE *phHash,
        PUCHAR pbHashObject,
        ULONG cbHashObject,
        PUCHAR pbSecret,
        ULONG cbSecret,
        ULONG dwFlags)
{
  __int64 (__fastcall *v7)(BCRYPT_ALG_HANDLE, BCRYPT_HASH_HANDLE *, PUCHAR, _QWORD, PUCHAR, ULONG, ULONG); // rax

  if ( *(_QWORD *)&WPP_MAIN_CB.SectorSize
    && (v7 = *(__int64 (__fastcall **)(BCRYPT_ALG_HANDLE, BCRYPT_HASH_HANDLE *, PUCHAR, _QWORD, PUCHAR, ULONG, ULONG))(*(_QWORD *)&WPP_MAIN_CB.SectorSize + 64LL)) != 0 )
  {
    return v7(hAlgorithm, phHash, pbHashObject, cbHashObject, pbSecret, cbSecret, dwFlags);
  }
  else
  {
    return -1073741822;
  }
}

```

## disassembly

```asm
0x180002710  push    rbx
0x180002712  sub     rsp, 40h
0x180002716  mov     rax, qword ptr cs:WPP_MAIN_CB.SectorSize
0x18000271d  mov     r10d, r9d
0x180002720  mov     r11, rdx
0x180002723  mov     rbx, rcx
0x180002726  test    rax, rax
0x180002729  jz      short loc_180002768
0x18000272b  mov     rax, [rax+40h]
0x18000272f  test    rax, rax
0x180002732  jz      short loc_180002768
0x180002734  mov     r9d, [rsp+48h+dwFlags]
0x18000273c  mov     edx, [rsp+48h+cbSecret]
0x180002740  mov     rcx, [rsp+48h+pbSecret]
0x180002745  mov     [rsp+48h+var_18], r9d
0x18000274a  mov     r9d, r10d
0x18000274d  mov     [rsp+48h+var_20], edx
0x180002751  mov     rdx, r11
0x180002754  mov     [rsp+48h+var_28], rcx
0x180002759  mov     rcx, rbx
0x18000275c  call    _guard_dispatch_icall
0x180002761  add     rsp, 40h
0x180002765  pop     rbx
0x180002766  retn
0x180002768  mov     eax, 0C0000002h
0x18000276d  jmp     short loc_180002761
```
