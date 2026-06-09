# DhcpRegisterParameterChangeNotification

- ea: `0x180008c50`
- end: `0x180008dce`
- name: `DhcpRegisterParameterChangeNotification`
- size: `382`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800088d0`
- `0x180008aa0`

## callees

- `0x180006000`
- `0x180008c50`
- `0x180008dd4`
- `0x180012850`
- `0x180012e30`

## import_xrefs

- `api-ms-win-downlevel-kernel32-l1-1-0!CloseHandle` at `0x180008d88`
- `api-ms-win-downlevel-kernel32-l1-1-0!CloseHandle` at `0x180008d88`

## pseudocode

```c
__int64 __fastcall DhcpRegisterParameterChangeNotification(
        const wchar_t *a1,
        __int64 a2,
        int a3,
        __int64 a4,
        unsigned int a5,
        signed __int32 a6,
        _QWORD *a7)
{
  void *v7; // r10
  _QWORD *v12; // rdi
  unsigned int i; // eax
  __int64 v14; // rcx
  unsigned int v15; // edx
  unsigned int v16; // ebx
  __int64 v18; // [rsp+20h] [rbp-78h]
  void *v19; // [rsp+50h] [rbp-48h] BYREF

  v7 = 0;
  a6 = 0;
  v19 = 0;
  v12 = a7;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    WPP_SF_SqdqdLq((_DWORD)a1, a2, a3, (_DWORD)a1, a2, a3, a4, a5);
    v7 = v19;
  }
  if ( v12 && (*v12 = 0, (a2 == 0) == (a3 == 0)) && (a4 == 0) == (a5 == 0) )
  {
    for ( i = 0; i < a5; ++i )
    {
      v14 = 32LL * i;
      v15 = *(_DWORD *)(v14 + a4 + 24);
      if ( v15 > 0xFF || !*(_QWORD *)(v14 + a4 + 16) && v15 )
        goto LABEL_16;
    }
    v16 = DhcpCreateApiEventAndDescriptor(&v19, &a6);
    if ( v16 || (v16 = DhcpRegisterParameterChangeNotificationInternal((__int64)a1, a2, a3, a4, a5)) != 0 )
    {
      v7 = v19;
    }
    else
    {
      v7 = 0;
      *v12 = v19;
      v19 = 0;
    }
  }
  else
  {
LABEL_16:
    v16 = 87;
  }
  if ( v7 )
  {
    CloseHandle(v7);
    v19 = 0;
  }
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    LODWORD(v18) = v16;
    WPP_SF_SD(1028, 0x56u, (ULONGLONG)WPP_e15037783097355a5233924022d92169_Traceguids, a1, v18);
  }
  return v16;
}

```

## disassembly

```asm
0x180008c50  mov     rax, rsp
0x180008c53  push    rbx
0x180008c54  push    rbp
0x180008c55  push    rsi
0x180008c56  push    rdi
0x180008c57  push    r12
0x180008c59  push    r14
0x180008c5b  push    r15
0x180008c5d  sub     rsp, 60h
0x180008c61  xor     r10d, r10d
0x180008c64  mov     dword ptr [rax+30h], 0
0x180008c6b  mov     [rax-48h], r10
0x180008c6f  mov     rsi, r9
0x180008c72  mov     r14d, r8d
0x180008c75  mov     r15, rdx
0x180008c78  mov     r12, rcx
0x180008c7b  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180008c82  mov     rdi, [rsp+98h+arg_30]
0x180008c8a  mov     ebp, [rsp+98h+arg_20]
0x180008c91  jz      short loc_180008CB3
0x180008c93  mov     [rax-50h], rdi
0x180008c97  mov     [rax-60h], ebp
0x180008c9a  mov     [rax-68h], r9
0x180008c9e  mov     r9, rcx
0x180008ca1  mov     [rax-70h], r8d
0x180008ca5  mov     [rax-78h], rdx
0x180008ca9  call    WPP_SF_SqdqdLq
0x180008cae  mov     r10, [rsp+98h+var_48]
0x180008cb3  test    rdi, rdi
0x180008cb6  jz      loc_180008D7B
0x180008cbc  xor     ecx, ecx
0x180008cbe  mov     qword ptr [rdi], 0
0x180008cc5  test    r15, r15
0x180008cc8  setz    cl
0x180008ccb  xor     eax, eax
0x180008ccd  test    r14d, r14d
0x180008cd0  setz    al
0x180008cd3  cmp     ecx, eax
0x180008cd5  jnz     loc_180008D7B
0x180008cdb  xor     ecx, ecx
0x180008cdd  test    rsi, rsi
0x180008ce0  setz    cl
0x180008ce3  xor     eax, eax
0x180008ce5  test    ebp, ebp
0x180008ce7  setz    al
0x180008cea  cmp     ecx, eax
0x180008cec  jnz     loc_180008D7B
0x180008cf2  xor     eax, eax
0x180008cf4  cmp     eax, ebp
0x180008cf6  jnb     short loc_180008D1A
0x180008cf8  mov     ecx, eax
0x180008cfa  shl     rcx, 5
0x180008cfe  mov     edx, [rcx+rsi+18h]
0x180008d02  cmp     edx, 0FFh
0x180008d08  ja      short loc_180008D7B
0x180008d0a  cmp     qword ptr [rcx+rsi+10h], 0
0x180008d10  jnz     short loc_180008D16
0x180008d12  test    edx, edx
0x180008d14  jnz     short loc_180008D7B
0x180008d16  inc     eax
0x180008d18  jmp     short loc_180008CF4
0x180008d1a  lea     rdx, [rsp+98h+arg_28]
0x180008d22  lea     rcx, [rsp+98h+var_48]
0x180008d27  call    DhcpCreateApiEventAndDescriptor
0x180008d2c  mov     ebx, eax
0x180008d2e  test    eax, eax
0x180008d30  jnz     short loc_180008D74
0x180008d32  mov     rax, [rsp+98h+var_48]
0x180008d37  mov     r9, rsi
0x180008d3a  mov     [rsp+98h+var_60], rax
0x180008d3f  mov     r8d, r14d
0x180008d42  mov     eax, [rsp+98h+arg_28]
0x180008d49  mov     rdx, r15
0x180008d4c  mov     [rsp+98h+var_68], eax
0x180008d50  mov     rcx, r12
0x180008d53  mov     [rsp+98h+var_78], ebp
0x180008d57  call    DhcpRegisterParameterChangeNotificationInternal
0x180008d5c  mov     ebx, eax
0x180008d5e  test    eax, eax
0x180008d60  jnz     short loc_180008D74
0x180008d62  mov     rax, [rsp+98h+var_48]
0x180008d67  xor     r10d, r10d
0x180008d6a  mov     [rdi], rax
0x180008d6d  mov     [rsp+98h+var_48], r10
0x180008d72  jmp     short loc_180008D80
0x180008d74  mov     r10, [rsp+98h+var_48]
0x180008d79  jmp     short loc_180008D80
0x180008d7b  mov     ebx, 57h ; 'W'
0x180008d80  test    r10, r10
0x180008d83  jz      short loc_180008D97
0x180008d85  mov     rcx, r10; hObject
0x180008d88  call    cs:__imp_CloseHandle
0x180008d8e  mov     [rsp+98h+var_48], 0
0x180008d97  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180008d9e  jz      short loc_180008DBD
0x180008da0  mov     edx, 56h ; 'V'
0x180008da5  mov     [rsp+98h+var_78], ebx
0x180008da9  mov     ecx, 404h
0x180008dae  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180008db5  mov     r9, r12
0x180008db8  call    WPP_SF_SD
0x180008dbd  mov     eax, ebx
0x180008dbf  add     rsp, 60h
0x180008dc3  pop     r15
0x180008dc5  pop     r14
0x180008dc7  pop     r12
0x180008dc9  pop     rdi
0x180008dca  pop     rsi
0x180008dcb  pop     rbp
0x180008dcc  pop     rbx
0x180008dcd  retn
```
