# GetSafeArrayDiscr(tagSAFEARRAY *,ulong *)

- ea: `0x18001c6e0`
- end: `0x18001c7cd`
- name: `?GetSafeArrayDiscr@@YA?AW4tagSF_TYPE@@PEAUtagSAFEARRAY@@PEAK@Z`
- size: `237`
- prototype: `enum tagSF_TYPE __fastcall(struct tagSAFEARRAY *, unsigned int *)`
- caller_count: `6`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001c7f0`
- `0x18001cfb0`
- `0x18002f3a0`
- `0x18003d540`
- `0x180045180`
- `0x180045620`

## callees

- `0x18001c6e0`

## import_xrefs

- `combase!__imp_CoDoesOtherSideSupportUDTMarshaling` at `0x18001c78f`
- `combase!__imp_CoDoesOtherSideSupportUDTMarshaling` at `0x18001c7af`
- `combase!__imp_CoDoesOtherSideSupportUDTMarshaling` at `0x18001c78f`
- `combase!__imp_CoDoesOtherSideSupportUDTMarshaling` at `0x18001c7af`
- `RPCRT4!RpcRaiseException` at `0x18001c7a5`
- `RPCRT4!RpcRaiseException` at `0x18001c7a5`

## pseudocode

```c
__int64 __fastcall GetSafeArrayDiscr(struct tagSAFEARRAY *a1, unsigned int *a2)
{
  USHORT fFeatures; // r8
  ULONG v3; // ecx
  ULONG v4; // ecx
  ULONG v5; // ecx
  ULONG v6; // ecx
  int v7; // r8d
  int v9; // r8d
  int v10; // r8d
  int v11; // r8d

  fFeatures = a1->fFeatures;
  if ( (fFeatures & 0x20) != 0 )
    return 36;
  v3 = a1->cbElements - 1;
  if ( !v3 )
    return 16;
  v4 = v3 - 1;
  if ( !v4 )
    return 2;
  v5 = v4 - 2;
  if ( !v5 )
    return 3;
  v6 = v5 - 4;
  if ( !v6 )
  {
    v7 = (fFeatures & 0xF40) - 256;
    if ( !v7 )
      return 8;
    v9 = v7 - 256;
    if ( v9 )
    {
      v10 = v9 - 64;
      if ( v10 )
      {
        v11 = v10 - 448;
        if ( !v11 )
          return 9;
        if ( v11 != 64 )
          return 20;
        if ( !(unsigned int)CoDoesOtherSideSupportUDTMarshaling(a2) )
          return 9;
        return 32781;
      }
      if ( (unsigned int)CoDoesOtherSideSupportUDTMarshaling(a2) )
        return 32781;
    }
    return 13;
  }
  if ( v6 != 16 || (fFeatures & 0xF00) != 0x800 )
    RpcRaiseException(-2147024809);
  return 12;
}

```

## disassembly

```asm
0x18001c6e0  sub     rsp, 28h
0x18001c6e4  movzx   r8d, word ptr [rcx+2]
0x18001c6e9  test    r8b, 20h
0x18001c6ed  jnz     loc_18001C77E
0x18001c6f3  mov     ecx, [rcx+4]
0x18001c6f6  sub     ecx, 1
0x18001c6f9  jz      loc_18001C785
0x18001c6ff  sub     ecx, 1
0x18001c702  jz      short loc_18001C753
0x18001c704  sub     ecx, 2
0x18001c707  jz      short loc_18001C727
0x18001c709  sub     ecx, 4
0x18001c70c  jnz     short loc_18001C75A
0x18001c70e  and     r8d, 0F40h
0x18001c715  mov     eax, 100h
0x18001c71a  sub     r8d, eax
0x18001c71d  jnz     short loc_18001C72E
0x18001c71f  lea     eax, [rcx+8]
0x18001c722  add     rsp, 28h
0x18001c726  retn
0x18001c727  mov     eax, 3
0x18001c72c  jmp     short loc_18001C722
0x18001c72e  sub     r8d, eax
0x18001c731  jz      loc_18001C7B9
0x18001c737  sub     r8d, 40h ; '@'
0x18001c73b  jz      short loc_18001C7AC
0x18001c73d  sub     r8d, 1C0h
0x18001c744  jz      short loc_18001C799
0x18001c746  cmp     r8d, 40h ; '@'
0x18001c74a  jz      short loc_18001C78C
0x18001c74c  mov     eax, 14h
0x18001c751  jmp     short loc_18001C722
0x18001c753  mov     eax, 2
0x18001c758  jmp     short loc_18001C722
0x18001c75a  mov     eax, 10h
0x18001c75f  cmp     ecx, eax
0x18001c761  jnz     short loc_18001C7A0
0x18001c763  mov     eax, 0F00h
0x18001c768  and     r8w, ax
0x18001c76c  mov     eax, 800h
0x18001c771  cmp     r8w, ax
0x18001c775  jnz     short loc_18001C7A0
0x18001c777  mov     eax, 0Ch
0x18001c77c  jmp     short loc_18001C722
0x18001c77e  mov     eax, 24h ; '$'
0x18001c783  jmp     short loc_18001C722
0x18001c785  mov     eax, 10h
0x18001c78a  jmp     short loc_18001C722
0x18001c78c  mov     rcx, rdx
0x18001c78f  call    cs:__imp_CoDoesOtherSideSupportUDTMarshaling
0x18001c795  test    eax, eax
0x18001c797  jnz     short loc_18001C7C3
0x18001c799  mov     eax, 9
0x18001c79e  jmp     short loc_18001C722
0x18001c7a0  mov     ecx, 80070057h; exception
0x18001c7a5  call    cs:__imp_RpcRaiseException
0x18001c7ab  int     3; Trap to Debugger
0x18001c7ac  mov     rcx, rdx
0x18001c7af  call    cs:__imp_CoDoesOtherSideSupportUDTMarshaling
0x18001c7b5  test    eax, eax
0x18001c7b7  jnz     short loc_18001C7C3
0x18001c7b9  mov     eax, 0Dh
0x18001c7be  jmp     loc_18001C722
0x18001c7c3  mov     eax, 800Dh
0x18001c7c8  jmp     loc_18001C722
```
