# NgscbpGetBcdIsSlateDevice

- ea: `0x180010b64`
- end: `0x180010cbd`
- name: `NgscbpGetBcdIsSlateDevice`
- size: `345`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180010dbc`

## callees

- `0x1800037a0`
- `0x18000ff64`
- `0x180010b64`

## import_xrefs

- `bcd!BcdOpenSystemStore` at `0x180010b98`
- `bcd!BcdOpenSystemStore` at `0x180010b98`
- `bcd!BcdOpenObject` at `0x180010bf3`
- `bcd!BcdOpenObject` at `0x180010bf3`
- `bcd!BcdGetElementData` at `0x180010c45`
- `bcd!BcdGetElementData` at `0x180010c45`
- `bcd!BcdCloseObject` at `0x180010c98`
- `bcd!BcdCloseObject` at `0x180010c98`
- `bcd!BcdCloseStore` at `0x180010ca7`
- `bcd!BcdCloseStore` at `0x180010ca7`

## pseudocode

```c
__int64 __fastcall NgscbpGetBcdIsSlateDevice(bool *a1, __int64 a2)
{
  NTSTATUS v3; // eax
  unsigned int v4; // eax
  int v5; // ebx
  NTSTATUS v6; // eax
  unsigned int v7; // eax
  NTSTATUS ElementData; // eax
  unsigned int v9; // eax
  __int64 v11; // [rsp+20h] [rbp-10h] BYREF
  __int16 v12; // [rsp+58h] [rbp+28h] BYREF
  int v13; // [rsp+60h] [rbp+30h] BYREF
  __int64 v14; // [rsp+68h] [rbp+38h] BYREF

  v11 = 0;
  v14 = 0;
  v12 = 0;
  v13 = 2;
  v3 = BcdOpenSystemStore(&v11, a2);
  v4 = FromNtStatus(v3);
  v5 = v4;
  if ( !v4 )
    goto LABEL_6;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v4);
  if ( v5 >= 0 )
  {
LABEL_6:
    v6 = BcdOpenObject(v11, &GUID_WINDOWS_BOOTMGR, &v14);
    v7 = FromNtStatus(v6);
    v5 = v7;
    if ( !v7 )
      goto LABEL_11;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v7);
    if ( v5 >= 0 )
    {
LABEL_11:
      ElementData = BcdGetElementData(v14, 369098866, &v12, &v13);
      v9 = FromNtStatus(ElementData);
      v5 = v9;
      if ( !v9 )
        goto LABEL_16;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v9);
      if ( v5 >= 0 )
LABEL_16:
        *a1 = (_BYTE)v12 != 0;
    }
  }
  if ( v14 )
    BcdCloseObject(v14);
  if ( v11 )
    BcdCloseStore(v11);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180010b64  mov     [rsp-18h+arg_0], rbx
0x180010b69  push    rbp
0x180010b6a  push    rdi
0x180010b6b  push    r15
0x180010b6d  mov     rbp, rsp
0x180010b70  sub     rsp, 30h
0x180010b74  mov     rdi, rcx
0x180010b77  mov     [rbp+var_10], 0
0x180010b7f  xor     eax, eax
0x180010b81  mov     [rbp+arg_18], 0
0x180010b89  lea     rcx, [rbp+var_10]
0x180010b8d  mov     [rbp+arg_8], ax
0x180010b91  mov     [rbp+arg_10], 2
0x180010b98  call    cs:__imp_BcdOpenSystemStore
0x180010b9e  mov     ecx, eax; int
0x180010ba0  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180010ba5  lea     r15, WPP_GLOBAL_Control
0x180010bac  mov     ebx, eax
0x180010bae  test    eax, eax
0x180010bb0  jz      short loc_180010BE4
0x180010bb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180010bb9  cmp     rcx, r15
0x180010bbc  jz      short loc_180010BDC
0x180010bbe  test    byte ptr [rcx+1Ch], 40h
0x180010bc2  jz      short loc_180010BDC
0x180010bc4  mov     rcx, [rcx+10h]
0x180010bc8  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x180010bcf  mov     edx, 11h
0x180010bd4  mov     r9d, eax
0x180010bd7  call    WPP_SF_d
0x180010bdc  test    ebx, ebx
0x180010bde  js      loc_180010C8F
0x180010be4  mov     rcx, [rbp+var_10]
0x180010be8  lea     r8, [rbp+arg_18]
0x180010bec  lea     rdx, GUID_WINDOWS_BOOTMGR
0x180010bf3  call    cs:__imp_BcdOpenObject
0x180010bf9  mov     ecx, eax; int
0x180010bfb  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180010c00  mov     ebx, eax
0x180010c02  test    eax, eax
0x180010c04  jz      short loc_180010C34
0x180010c06  mov     rcx, cs:WPP_GLOBAL_Control
0x180010c0d  cmp     rcx, r15
0x180010c10  jz      short loc_180010C30
0x180010c12  test    byte ptr [rcx+1Ch], 40h
0x180010c16  jz      short loc_180010C30
0x180010c18  mov     rcx, [rcx+10h]
0x180010c1c  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x180010c23  mov     edx, 12h
0x180010c28  mov     r9d, eax
0x180010c2b  call    WPP_SF_d
0x180010c30  test    ebx, ebx
0x180010c32  js      short loc_180010C8F
0x180010c34  mov     rcx, [rbp+arg_18]
0x180010c38  lea     r9, [rbp+arg_10]
0x180010c3c  lea     r8, [rbp+arg_8]
0x180010c40  mov     edx, 16000072h
0x180010c45  call    cs:__imp_BcdGetElementData
0x180010c4b  mov     ecx, eax; int
0x180010c4d  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180010c52  mov     ebx, eax
0x180010c54  test    eax, eax
0x180010c56  jz      short loc_180010C86
0x180010c58  mov     rcx, cs:WPP_GLOBAL_Control
0x180010c5f  cmp     rcx, r15
0x180010c62  jz      short loc_180010C82
0x180010c64  test    byte ptr [rcx+1Ch], 40h
0x180010c68  jz      short loc_180010C82
0x180010c6a  mov     rcx, [rcx+10h]
0x180010c6e  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x180010c75  mov     edx, 13h
0x180010c7a  mov     r9d, eax
0x180010c7d  call    WPP_SF_d
0x180010c82  test    ebx, ebx
0x180010c84  js      short loc_180010C8F
0x180010c86  cmp     byte ptr [rbp+arg_8], 0
0x180010c8a  setnz   al
0x180010c8d  mov     [rdi], al
0x180010c8f  mov     rcx, [rbp+arg_18]
0x180010c93  test    rcx, rcx
0x180010c96  jz      short loc_180010C9E
0x180010c98  call    cs:__imp_BcdCloseObject
0x180010c9e  mov     rcx, [rbp+var_10]
0x180010ca2  test    rcx, rcx
0x180010ca5  jz      short loc_180010CAD
0x180010ca7  call    cs:__imp_BcdCloseStore
0x180010cad  mov     eax, ebx
0x180010caf  mov     rbx, [rsp+30h+arg_0]
0x180010cb4  add     rsp, 30h
0x180010cb8  pop     r15
0x180010cba  pop     rdi
0x180010cbb  pop     rbp
0x180010cbc  retn
```
