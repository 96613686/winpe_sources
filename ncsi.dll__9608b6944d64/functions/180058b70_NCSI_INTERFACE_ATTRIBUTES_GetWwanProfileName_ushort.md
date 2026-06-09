# NCSI_INTERFACE_ATTRIBUTES::GetWwanProfileName(ushort *)

- ea: `0x180058b70`
- end: `0x180058cd3`
- name: `?GetWwanProfileName@NCSI_INTERFACE_ATTRIBUTES@@AEAAKPEAG@Z`
- size: `355`
- prototype: `unsigned int(NCSI_INTERFACE_ATTRIBUTES *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180021c38`

## callees

- `0x18002283c`
- `0x180047240`
- `0x1800490b4`
- `0x180058b70`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180058c96`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180058c96`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180058bd1`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180058bd1`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x180058c14`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x180058c14`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180058caf`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180058caf`

## pseudocode

```c
__int64 __fastcall NCSI_INTERFACE_ATTRIBUTES::GetWwanProfileName(NCSI_INTERFACE_ATTRIBUTES *this, unsigned __int16 *a2)
{
  unsigned int v5; // ebx
  unsigned __int64 v6; // r11
  int v7; // eax
  unsigned __int64 v8; // r11
  const unsigned __int16 *v9; // r8
  __int64 v10; // [rsp+40h] [rbp-20h] BYREF
  __int64 v11; // [rsp+48h] [rbp-18h] BYREF
  int v12; // [rsp+50h] [rbp-10h] BYREF
  int v13; // [rsp+54h] [rbp-Ch] BYREF

  if ( !(unsigned __int8)IsWwanOpenHandlePresent() )
    return 1168;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v10 = 0;
  v5 = WwanOpenHandle(1, 0, &v12, &v11);
  if ( !v5 )
  {
    v5 = WwanQueryInterface(v11, (char *)this + 8, 8, 0, &v13, &v10, 0, 0);
    if ( !v5 )
    {
      if ( v10 == -988 )
      {
        v5 = 1168;
      }
      else if ( (int)StringCchCopyW(a2, 0x101u, (const unsigned __int16 *)(v10 + 988)) < 0 )
      {
        v7 = StringCchCopyW(a2, v6, (const unsigned __int16 *)(v10 + 988));
        v9 = (const unsigned __int16 *)(v10 + 988);
        if ( (v7 & 0x1FFF0000) == 0x70000 )
          v5 = (unsigned __int16)StringCchCopyW(a2, v8, v9);
        else
          v5 = StringCchCopyW(a2, v8, v9);
      }
    }
  }
  if ( v10 )
  {
    WwanFreeMemory();
    v10 = 0;
  }
  if ( v11 )
    WwanCloseHandle(v11, 0);
  return v5;
}

```

## disassembly

```asm
0x180058b70  mov     [rsp-18h+arg_10], rbx
0x180058b75  push    rbp
0x180058b76  push    rsi
0x180058b77  push    rdi
0x180058b78  mov     rbp, rsp
0x180058b7b  sub     rsp, 60h
0x180058b7f  mov     rax, cs:__security_cookie
0x180058b86  xor     rax, rsp
0x180058b89  mov     [rbp+var_8], rax
0x180058b8d  mov     rdi, rdx
0x180058b90  mov     rsi, rcx
0x180058b93  call    IsWwanOpenHandlePresent
0x180058b98  test    al, al
0x180058b9a  jnz     short loc_180058BA6
0x180058b9c  mov     eax, 490h
0x180058ba1  jmp     loc_180058CB7
0x180058ba6  xor     edx, edx
0x180058ba8  mov     [rbp+var_18], 0
0x180058bb0  lea     r9, [rbp+var_18]
0x180058bb4  mov     [rbp+var_10], 0
0x180058bbb  lea     r8, [rbp+var_10]
0x180058bbf  mov     [rbp+var_C], 0
0x180058bc6  mov     [rbp+var_20], 0
0x180058bce  lea     ecx, [rdx+1]
0x180058bd1  call    cs:__imp_WwanOpenHandle
0x180058bd7  mov     ebx, eax
0x180058bd9  test    eax, eax
0x180058bdb  jnz     loc_180058C8D
0x180058be1  mov     rcx, [rbp+var_18]
0x180058be5  lea     rax, [rbp+var_20]
0x180058be9  mov     [rsp+60h+var_28], 0
0x180058bf2  lea     rdx, [rsi+8]
0x180058bf6  mov     [rsp+60h+var_30], 0
0x180058bff  lea     r8d, [rbx+8]
0x180058c03  mov     [rsp+60h+var_38], rax
0x180058c08  xor     r9d, r9d
0x180058c0b  lea     rax, [rbp+var_C]
0x180058c0f  mov     [rsp+60h+var_40], rax
0x180058c14  call    cs:__imp_WwanQueryInterface
0x180058c1a  mov     ebx, eax
0x180058c1c  test    eax, eax
0x180058c1e  jnz     short loc_180058C8D
0x180058c20  mov     r8, [rbp+var_20]
0x180058c24  add     r8, 3DCh; unsigned __int16 *
0x180058c2b  jz      short loc_180058C88
0x180058c2d  mov     r11d, 101h
0x180058c33  mov     rcx, rdi; unsigned __int16 *
0x180058c36  mov     edx, r11d; unsigned __int64
0x180058c39  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180058c3e  test    eax, eax
0x180058c40  jns     short loc_180058C8D
0x180058c42  mov     r8, [rbp+var_20]
0x180058c46  mov     rdx, r11; unsigned __int64
0x180058c49  add     r8, 3DCh; unsigned __int16 *
0x180058c50  mov     rcx, rdi; unsigned __int16 *
0x180058c53  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180058c58  mov     r8, [rbp+var_20]
0x180058c5c  and     eax, 1FFF0000h
0x180058c61  add     r8, 3DCh; unsigned __int16 *
0x180058c68  mov     rdx, r11; unsigned __int64
0x180058c6b  mov     rcx, rdi; unsigned __int16 *
0x180058c6e  cmp     eax, 70000h
0x180058c73  jnz     short loc_180058C7F
0x180058c75  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180058c7a  movzx   ebx, ax
0x180058c7d  jmp     short loc_180058C8D
0x180058c7f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180058c84  mov     ebx, eax
0x180058c86  jmp     short loc_180058C8D
0x180058c88  mov     ebx, 490h
0x180058c8d  mov     rcx, [rbp+var_20]
0x180058c91  test    rcx, rcx
0x180058c94  jz      short loc_180058CA4
0x180058c96  call    cs:__imp_WwanFreeMemory
0x180058c9c  mov     [rbp+var_20], 0
0x180058ca4  mov     rcx, [rbp+var_18]
0x180058ca8  test    rcx, rcx
0x180058cab  jz      short loc_180058CB5
0x180058cad  xor     edx, edx
0x180058caf  call    cs:__imp_WwanCloseHandle
0x180058cb5  mov     eax, ebx
0x180058cb7  mov     rcx, [rbp+var_8]
0x180058cbb  xor     rcx, rsp; StackCookie
0x180058cbe  call    __security_check_cookie
0x180058cc3  mov     rbx, [rsp+60h+arg_10]
0x180058ccb  add     rsp, 60h
0x180058ccf  pop     rdi
0x180058cd0  pop     rsi
0x180058cd1  pop     rbp
0x180058cd2  retn
```
