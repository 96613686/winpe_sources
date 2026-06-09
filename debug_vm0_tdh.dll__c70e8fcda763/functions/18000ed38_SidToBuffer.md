# SidToBuffer

- ea: `0x18000ed38`
- end: `0x18000ee21`
- name: `SidToBuffer`
- size: `233`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000dcb0`
- `0x18003e7c0`

## callees

- `0x18000ed38`
- `0x18000ee28`
- `0x1800207c0`
- `0x180021490`
- `0x180023b05`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ee14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ee14`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000edca`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000edca`

## pseudocode

```c
__int64 __fastcall SidToBuffer(void *Src, unsigned __int16 a2, __int64 a3)
{
  size_t v3; // rdi
  LPWSTR v7; // rdx
  __int64 v8; // rax
  __int64 v9; // r9
  unsigned int v10; // ecx
  unsigned int v11; // eax
  LPWSTR StringSid; // [rsp+20h] [rbp-88h] BYREF
  _BYTE Sid[80]; // [rsp+30h] [rbp-78h] BYREF

  v3 = a2;
  StringSid = 0;
  if ( a2 > 0x44u )
    return HexBinaryToBuffer(Src, (unsigned __int16)v3, a3);
  memset_0(Sid, 0, 0x44u);
  memcpy_0(Sid, Src, v3);
  ConvertSidToStringSidW(Sid, &StringSid);
  v7 = StringSid;
  if ( !StringSid )
    return HexBinaryToBuffer(Src, (unsigned __int16)v3, a3);
  v8 = -1;
  do
    ++v8;
  while ( StringSid[v8] );
  v9 = *(unsigned int *)(a3 + 12);
  v10 = v8 + 1;
  v11 = v9 + v8 + 1;
  *(_DWORD *)(a3 + 12) = v11;
  if ( v11 <= *(_DWORD *)(a3 + 8) )
  {
    memcpy_0((void *)(*(_QWORD *)a3 + 2 * v9), v7, 2LL * v10);
    v7 = StringSid;
  }
  LocalFree(v7);
  return 0;
}

```

## disassembly

```asm
0x18000ed38  mov     [rsp+arg_18], rbx
0x18000ed3d  push    rbp
0x18000ed3e  push    rsi
0x18000ed3f  push    rdi
0x18000ed40  sub     rsp, 90h
0x18000ed47  mov     rax, cs:__security_cookie
0x18000ed4e  xor     rax, rsp
0x18000ed51  mov     [rsp+0A8h+var_28], rax
0x18000ed59  xor     ebp, ebp
0x18000ed5b  movzx   edi, dx
0x18000ed5e  mov     rbx, r8
0x18000ed61  mov     [rsp+0A8h+StringSid], rbp
0x18000ed66  mov     rsi, rcx
0x18000ed69  lea     r8d, [rbp+44h]; Size
0x18000ed6d  cmp     di, r8w
0x18000ed71  jbe     short loc_18000EDA4
0x18000ed73  mov     r8, rbx
0x18000ed76  movzx   edx, di
0x18000ed79  mov     rcx, rsi
0x18000ed7c  call    HexBinaryToBuffer
0x18000ed81  mov     rcx, [rsp+0A8h+var_28]
0x18000ed89  xor     rcx, rsp; StackCookie
0x18000ed8c  call    __security_check_cookie
0x18000ed91  mov     rbx, [rsp+0A8h+arg_18]
0x18000ed99  add     rsp, 90h
0x18000eda0  pop     rdi
0x18000eda1  pop     rsi
0x18000eda2  pop     rbp
0x18000eda3  retn
0x18000eda4  xor     edx, edx; Val
0x18000eda6  lea     rcx, [rsp+0A8h+Sid]; void *
0x18000edab  call    memset_0
0x18000edb0  mov     r8, rdi; Size
0x18000edb3  lea     rcx, [rsp+0A8h+Sid]; void *
0x18000edb8  mov     rdx, rsi; Src
0x18000edbb  call    memcpy_0
0x18000edc0  lea     rdx, [rsp+0A8h+StringSid]; StringSid
0x18000edc5  lea     rcx, [rsp+0A8h+Sid]; Sid
0x18000edca  call    cs:__imp_ConvertSidToStringSidW
0x18000edd0  mov     rdx, [rsp+0A8h+StringSid]; Src
0x18000edd5  test    rdx, rdx
0x18000edd8  jz      short loc_18000ED73
0x18000edda  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000edde  inc     rax
0x18000ede1  cmp     [rdx+rax*2], bp
0x18000ede5  jnz     short loc_18000EDDE
0x18000ede7  mov     r9d, [rbx+0Ch]
0x18000edeb  lea     ecx, [rax+1]
0x18000edee  lea     eax, [r9+rcx]
0x18000edf2  mov     [rbx+0Ch], eax
0x18000edf5  cmp     eax, [rbx+8]
0x18000edf8  ja      short loc_18000EE11
0x18000edfa  mov     rax, [rbx]
0x18000edfd  mov     r8d, ecx
0x18000ee00  add     r8, r8; Size
0x18000ee03  lea     rcx, [rax+r9*2]; void *
0x18000ee07  call    memcpy_0
0x18000ee0c  mov     rdx, [rsp+0A8h+StringSid]
0x18000ee11  mov     rcx, rdx; hMem
0x18000ee14  call    cs:__imp_LocalFree
0x18000ee1a  xor     eax, eax
0x18000ee1c  jmp     loc_18000ED81
```
