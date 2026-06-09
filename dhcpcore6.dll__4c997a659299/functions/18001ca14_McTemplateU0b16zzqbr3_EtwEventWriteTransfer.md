# McTemplateU0b16zzqbr3_EtwEventWriteTransfer

- ea: `0x18001ca14`
- end: `0x18001cb03`
- name: `McTemplateU0b16zzqbr3_EtwEventWriteTransfer`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180011e04`

## callees

- `0x180001e78`
- `0x180019ad0`
- `0x18001ca14`

## pseudocode

```c
__int64 __fastcall McTemplateU0b16zzqbr3_EtwEventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4,
        const wchar_t *a5,
        int a6,
        __int64 a7)
{
  __int64 v7; // rax
  int v8; // edx
  __int64 v9; // rcx
  int v10; // ecx
  const wchar_t *v11; // rcx
  bool v12; // zf
  _BYTE v14[16]; // [rsp+30h] [rbp-31h] BYREF
  __int64 v15; // [rsp+40h] [rbp-21h]
  __int64 v16; // [rsp+48h] [rbp-19h]
  const wchar_t *v17; // [rsp+50h] [rbp-11h]
  int v18; // [rsp+58h] [rbp-9h]
  int v19; // [rsp+5Ch] [rbp-5h]
  const wchar_t *v20; // [rsp+60h] [rbp-1h]
  int v21; // [rsp+68h] [rbp+7h]
  int v22; // [rsp+6Ch] [rbp+Bh]
  int *v23; // [rsp+70h] [rbp+Fh]
  __int64 v24; // [rsp+78h] [rbp+17h]
  __int64 v25; // [rsp+80h] [rbp+1Fh]
  int v26; // [rsp+88h] [rbp+27h]
  int v27; // [rsp+8Ch] [rbp+2Bh]

  v15 = a3;
  v7 = -1;
  v16 = 16;
  v8 = 10;
  if ( a4 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a4[v9] );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v10 = 10;
  }
  v18 = v10;
  v11 = a5;
  if ( !a4 )
    a4 = L"NULL";
  v19 = 0;
  v17 = a4;
  v12 = a5 == 0;
  if ( a5 )
  {
    do
      ++v7;
    while ( a5[v7] );
    v8 = 2 * v7 + 2;
    v12 = a5 == 0;
  }
  if ( v12 )
    v11 = L"NULL";
  v21 = v8;
  v20 = v11;
  v23 = &a6;
  v25 = a7;
  v26 = a6;
  v22 = 0;
  v24 = 4;
  v27 = 0;
  return McGenEventWrite_EtwEventWriteTransfer(
           &Dhcpv6_Context,
           (__int64)DHCPv6NetworkHintStatefullConfig,
           0,
           6,
           (__int64)v14);
}

```

## disassembly

```asm
0x18001ca14  push    rbp
0x18001ca16  lea     rbp, [rsp-3Fh]
0x18001ca1b  sub     rsp, 0A0h
0x18001ca22  mov     rax, cs:__security_cookie
0x18001ca29  xor     rax, rsp
0x18001ca2c  mov     [rbp+3Fh+var_10], rax
0x18001ca30  mov     [rbp+3Fh+var_60], r8
0x18001ca34  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ca38  xor     r8d, r8d
0x18001ca3b  mov     [rbp+3Fh+var_58], 10h
0x18001ca43  lea     edx, [r8+0Ah]
0x18001ca47  test    r9, r9
0x18001ca4a  jz      short loc_18001CA62
0x18001ca4c  mov     rcx, rax
0x18001ca4f  inc     rcx
0x18001ca52  cmp     [r9+rcx*2], r8w
0x18001ca57  jnz     short loc_18001CA4F
0x18001ca59  lea     ecx, ds:2[rcx*2]
0x18001ca60  jmp     short loc_18001CA64
0x18001ca62  mov     ecx, edx
0x18001ca64  test    r9, r9
0x18001ca67  mov     [rbp+3Fh+var_48], ecx
0x18001ca6a  mov     rcx, [rbp+3Fh+arg_20]
0x18001ca6e  lea     r10, aNull_0; "NULL"
0x18001ca75  cmovz   r9, r10
0x18001ca79  mov     [rbp+3Fh+var_44], r8d
0x18001ca7d  mov     [rbp+3Fh+var_50], r9
0x18001ca81  test    rcx, rcx
0x18001ca84  jz      short loc_18001CA9A
0x18001ca86  inc     rax
0x18001ca89  cmp     [rcx+rax*2], r8w
0x18001ca8e  jnz     short loc_18001CA86
0x18001ca90  lea     edx, ds:2[rax*2]
0x18001ca97  test    rcx, rcx
0x18001ca9a  cmovz   rcx, r10
0x18001ca9e  mov     [rbp+3Fh+var_38], edx
0x18001caa1  lea     rax, [rbp+3Fh+arg_28]
0x18001caa5  mov     [rbp+3Fh+var_40], rcx
0x18001caa9  mov     [rbp+3Fh+var_30], rax
0x18001caad  lea     rdx, DHCPv6NetworkHintStatefullConfig
0x18001cab4  mov     rax, [rbp+3Fh+arg_30]
0x18001cab8  lea     rcx, Dhcpv6_Context
0x18001cabf  mov     [rbp+3Fh+var_20], rax
0x18001cac3  mov     r9d, 6
0x18001cac9  mov     eax, [rbp+3Fh+arg_28]
0x18001cacc  mov     [rbp+3Fh+var_18], eax
0x18001cacf  lea     rax, [rbp+3Fh+var_70]
0x18001cad3  mov     [rsp+0A0h+var_80], rax
0x18001cad8  mov     [rbp+3Fh+var_34], r8d
0x18001cadc  mov     [rbp+3Fh+var_28], 4
0x18001cae4  mov     [rbp+3Fh+var_14], r8d
0x18001cae8  call    McGenEventWrite_EtwEventWriteTransfer
0x18001caed  mov     rcx, [rbp+3Fh+var_10]
0x18001caf1  xor     rcx, rsp; StackCookie
0x18001caf4  call    __security_check_cookie
0x18001caf9  add     rsp, 0A0h
0x18001cb00  pop     rbp
0x18001cb01  retn
```
