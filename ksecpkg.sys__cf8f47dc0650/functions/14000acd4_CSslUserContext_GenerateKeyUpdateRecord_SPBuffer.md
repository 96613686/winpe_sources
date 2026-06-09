# CSslUserContext::GenerateKeyUpdateRecord(SPBuffer *)

- ea: `0x14000acd4`
- end: `0x14000ad9c`
- name: `?GenerateKeyUpdateRecord@CSslUserContext@@QEAAJPEAUSPBuffer@@@Z`
- size: `200`
- prototype: `__int64 __fastcall(CSslUserContext *__hidden this, struct SPBuffer *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140002fc0`

## callees

- `0x14000acd4`
- `0x14000be38`
- `0x140010160`

## import_xrefs

- `cng!SslEncryptPacket` at `0x14000ad54`
- `cng!SslEncryptPacket` at `0x14000ad54`

## pseudocode

```c
__int64 __fastcall CSslUserContext::GenerateKeyUpdateRecord(CSslUserContext *this, struct SPBuffer *a2)
{
  __int64 result; // rax
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rdx
  int v7; // [rsp+28h] [rbp-40h]
  char *v8; // [rsp+30h] [rbp-38h]
  __int64 v9; // [rsp+38h] [rbp-30h]
  int v10; // [rsp+50h] [rbp-18h] BYREF
  __int16 v11; // [rsp+54h] [rbp-14h]

  if ( !a2 )
    return 2148074333LL;
  v9 = *((_QWORD *)this + 13);
  v8 = (char *)a2 + 4;
  v4 = *((_QWORD *)this + 11);
  v7 = *(_DWORD *)a2;
  v5 = *((_QWORD *)a2 + 1);
  v6 = *((_QWORD *)this + 6);
  v10 = 16777240;
  v11 = 5632;
  result = ((__int64 (__fastcall *)(__int64, __int64, int *, __int64, __int64, int, char *, __int64, int, _DWORD))SslEncryptPacket)(
             v4,
             v6,
             &v10,
             6,
             v5,
             v7,
             v8,
             v9,
             23,
             0);
  if ( !(_DWORD)result )
    return UpdateTrafficSecretAndDeriveNewKey(
             *((_QWORD *)this + 11),
             (unsigned __int64 *)this + 61,
             (unsigned __int64 *)this + 6,
             (unsigned __int64 *)this + 13);
  return result;
}

```

## disassembly

```asm
0x14000acd4  mov     [rsp+arg_10], rbx
0x14000acd9  mov     [rsp+arg_18], rsi
0x14000acde  push    rdi
0x14000acdf  sub     rsp, 60h
0x14000ace3  mov     rax, cs:__security_cookie
0x14000acea  xor     rax, rsp
0x14000aced  mov     [rsp+68h+var_10], rax
0x14000acf2  mov     rbx, rcx
0x14000acf5  test    rdx, rdx
0x14000acf8  jnz     short loc_14000AD01
0x14000acfa  mov     eax, 8009035Dh
0x14000acff  jmp     short loc_14000AD7C
0x14000ad01  mov     rax, [rbx+68h]
0x14000ad05  lea     rcx, [rdx+4]
0x14000ad09  mov     [rsp+68h+var_20], 0
0x14000ad11  lea     r8, [rsp+68h+var_18]
0x14000ad16  mov     [rsp+68h+var_28], 17h
0x14000ad1e  mov     r9d, 6
0x14000ad24  mov     [rsp+68h+var_30], rax
0x14000ad29  mov     eax, [rdx]
0x14000ad2b  mov     [rsp+68h+var_38], rcx
0x14000ad30  mov     rcx, [rbx+58h]
0x14000ad34  mov     [rsp+68h+var_40], eax
0x14000ad38  mov     rax, [rdx+8]
0x14000ad3c  mov     rdx, [rbx+30h]
0x14000ad40  mov     [rsp+68h+var_48], rax
0x14000ad45  mov     [rsp+68h+var_18], 1000018h
0x14000ad4d  mov     [rsp+68h+var_14], 1600h
0x14000ad54  call    cs:__imp_SslEncryptPacket
0x14000ad5b  nop     dword ptr [rax+rax+00h]
0x14000ad60  test    eax, eax
0x14000ad62  jnz     short loc_14000AD7C
0x14000ad64  mov     rcx, [rbx+58h]; unsigned __int64
0x14000ad68  lea     rdx, [rbx+1E8h]; unsigned __int64 *
0x14000ad6f  lea     r9, [rbx+68h]; unsigned __int64 *
0x14000ad73  lea     r8, [rbx+30h]; unsigned __int64 *
0x14000ad77  call    ?UpdateTrafficSecretAndDeriveNewKey@@YAJ_KPEA_K11@Z; UpdateTrafficSecretAndDeriveNewKey(unsigned __int64,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *)
0x14000ad7c  mov     rcx, [rsp+68h+var_10]
0x14000ad81  xor     rcx, rsp; StackCookie
0x14000ad84  call    __security_check_cookie
0x14000ad89  lea     r11, [rsp+68h+var_8]
0x14000ad8e  mov     rbx, [r11+20h]
0x14000ad92  mov     rsi, [r11+28h]
0x14000ad96  mov     rsp, r11
0x14000ad99  pop     rdi
0x14000ad9a  retn
```
