# CxPlatHashCompute

- ea: `0x1400346f8`
- end: `0x14003477f`
- name: `CxPlatHashCompute`
- size: `135`
- prototype: `__int64 __usercall@<rax>(BCRYPT_HASH_HANDLE hHash@<rcx>, PUCHAR pbOutput)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140028658`
- `0x140038d74`
- `0x140038e38`

## callees

- `0x1400346f8`
- `0x14003e928`

## import_xrefs

- `cng!BCryptHashData` at `0x140034710`
- `cng!BCryptHashData` at `0x140034710`
- `cng!BCryptFinishHash` at `0x140034742`
- `cng!BCryptFinishHash` at `0x140034742`

## pseudocode

```c
__int64 __fastcall CxPlatHashCompute(BCRYPT_HASH_HANDLE hHash, UCHAR *a2, ULONG a3, ULONG a4, PUCHAR pbOutput)
{
  NTSTATUS v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  unsigned int v10; // ebx
  const char *v11; // r9

  v7 = BCryptHashData(hHash, a2, a3, 0);
  v10 = v7;
  if ( v7 >= 0 )
  {
    v7 = BCryptFinishHash(hHash, pbOutput, a4, 0);
    v10 = v7;
    if ( v7 < 0 && (Microsoft_QuicEnableBits & 4) != 0 )
    {
      v11 = "BCryptFinishHash";
      goto LABEL_7;
    }
  }
  else if ( (Microsoft_QuicEnableBits & 4) != 0 )
  {
    v11 = "BCryptHashData";
LABEL_7:
    McTemplateU0qs_EtwWriteTransfer(v9, v8, (unsigned int)v7, v11);
  }
  return v10;
}

```

## disassembly

```asm
0x1400346f8  mov     [rsp+arg_0], rbx
0x1400346fd  mov     [rsp+arg_8], rsi
0x140034702  push    rdi
0x140034703  sub     rsp, 20h
0x140034707  mov     esi, r9d
0x14003470a  mov     rdi, rcx
0x14003470d  xor     r9d, r9d; dwFlags
0x140034710  call    cs:__imp_BCryptHashData
0x140034717  nop     dword ptr [rax+rax+00h]
0x14003471c  mov     ebx, eax
0x14003471e  test    eax, eax
0x140034720  jns     short loc_140034734
0x140034722  test    cs:Microsoft_QuicEnableBits, 4
0x140034729  jz      short loc_14003476C
0x14003472b  lea     r9, aBcrypthashdata; "BCryptHashData"
0x140034732  jmp     short loc_140034764
0x140034734  mov     rdx, [rsp+28h+pbOutput]; pbOutput
0x140034739  xor     r9d, r9d; dwFlags
0x14003473c  mov     r8d, esi; cbOutput
0x14003473f  mov     rcx, rdi; hHash
0x140034742  call    cs:__imp_BCryptFinishHash
0x140034749  nop     dword ptr [rax+rax+00h]
0x14003474e  mov     ebx, eax
0x140034750  test    eax, eax
0x140034752  jns     short loc_14003476C
0x140034754  test    cs:Microsoft_QuicEnableBits, 4
0x14003475b  jz      short loc_14003476C
0x14003475d  lea     r9, aBcryptfinishha; "BCryptFinishHash"
0x140034764  mov     r8d, eax
0x140034767  call    McTemplateU0qs_EtwWriteTransfer
0x14003476c  mov     rsi, [rsp+28h+arg_8]
0x140034771  mov     eax, ebx
0x140034773  mov     rbx, [rsp+28h+arg_0]
0x140034778  add     rsp, 20h
0x14003477c  pop     rdi
0x14003477d  retn
```
