# NgscbpGetBcdIsSlateDevice

- ea: `0x180016c28`
- end: `0x180016da0`
- name: `NgscbpGetBcdIsSlateDevice`
- size: `376`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18004f318`

## callees

- `0x1800090c0`
- `0x180016c28`
- `0x180018b10`

## import_xrefs

- `bcd!BcdCloseObject` at `0x180016d6e`
- `bcd!BcdCloseObject` at `0x180016d6e`
- `bcd!BcdGetElementData` at `0x180016d15`
- `bcd!BcdGetElementData` at `0x180016d15`
- `bcd!BcdOpenObject` at `0x180016cbd`
- `bcd!BcdOpenObject` at `0x180016cbd`
- `bcd!BcdCloseStore` at `0x180016d83`
- `bcd!BcdCloseStore` at `0x180016d83`
- `bcd!BcdOpenSystemStore` at `0x180016c5c`
- `bcd!BcdOpenSystemStore` at `0x180016c5c`

## pseudocode

```c
__int64 __fastcall NgscbpGetBcdIsSlateDevice(bool *a1, __int64 a2)
{
  int v3; // eax
  unsigned int v4; // eax
  __int64 v5; // rdx
  int v6; // ebx
  int v7; // eax
  unsigned int v8; // eax
  int ElementData; // eax
  unsigned int v10; // eax
  __int64 v12; // [rsp+20h] [rbp-10h] BYREF
  __int16 v13; // [rsp+58h] [rbp+28h] BYREF
  int v14; // [rsp+60h] [rbp+30h] BYREF
  __int64 v15; // [rsp+68h] [rbp+38h] BYREF

  v12 = 0;
  v15 = 0;
  v13 = 0;
  v14 = 2;
  v3 = BcdOpenSystemStore(&v12, a2);
  v4 = FromNtStatus(v3);
  v6 = v4;
  if ( !v4 )
    goto LABEL_6;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v4);
  if ( v6 >= 0 )
  {
LABEL_6:
    v7 = BcdOpenObject(v12, &GUID_WINDOWS_BOOTMGR, &v15);
    v8 = FromNtStatus(v7);
    v6 = v8;
    if ( !v8 )
      goto LABEL_11;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v8);
    if ( v6 >= 0 )
    {
LABEL_11:
      ElementData = BcdGetElementData(v15, 369098866, &v13, &v14);
      v10 = FromNtStatus(ElementData);
      v6 = v10;
      if ( !v10 )
        goto LABEL_16;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v10);
      if ( v6 >= 0 )
LABEL_16:
        *a1 = (_BYTE)v13 != 0;
    }
  }
  if ( v15 )
    BcdCloseObject(v15);
  if ( v12 )
    BcdCloseStore(v12, v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180016c28  mov     [rsp-18h+arg_0], rbx
0x180016c2d  push    rbp
0x180016c2e  push    rdi
0x180016c2f  push    r15
0x180016c31  mov     rbp, rsp
0x180016c34  sub     rsp, 30h
0x180016c38  mov     rdi, rcx
0x180016c3b  mov     [rbp+var_10], 0
0x180016c43  xor     eax, eax
0x180016c45  mov     [rbp+arg_18], 0
0x180016c4d  lea     rcx, [rbp+var_10]
0x180016c51  mov     [rbp+arg_8], ax
0x180016c55  mov     [rbp+arg_10], 2
0x180016c5c  call    cs:__imp_BcdOpenSystemStore
0x180016c63  nop     dword ptr [rax+rax+00h]
0x180016c68  mov     ecx, eax; int
0x180016c6a  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180016c6f  lea     r15, WPP_GLOBAL_Control
0x180016c76  mov     ebx, eax
0x180016c78  test    eax, eax
0x180016c7a  jz      short loc_180016CAE
0x180016c7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c83  cmp     rcx, r15
0x180016c86  jz      short loc_180016CA6
0x180016c88  test    byte ptr [rcx+1Ch], 40h
0x180016c8c  jz      short loc_180016CA6
0x180016c8e  mov     rcx, [rcx+10h]
0x180016c92  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x180016c99  mov     edx, 11h
0x180016c9e  mov     r9d, eax
0x180016ca1  call    WPP_SF_d
0x180016ca6  test    ebx, ebx
0x180016ca8  js      loc_180016D65
0x180016cae  mov     rcx, [rbp+var_10]
0x180016cb2  lea     r8, [rbp+arg_18]
0x180016cb6  lea     rdx, GUID_WINDOWS_BOOTMGR
0x180016cbd  call    cs:__imp_BcdOpenObject
0x180016cc4  nop     dword ptr [rax+rax+00h]
0x180016cc9  mov     ecx, eax; int
0x180016ccb  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180016cd0  mov     ebx, eax
0x180016cd2  test    eax, eax
0x180016cd4  jz      short loc_180016D04
0x180016cd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180016cdd  cmp     rcx, r15
0x180016ce0  jz      short loc_180016D00
0x180016ce2  test    byte ptr [rcx+1Ch], 40h
0x180016ce6  jz      short loc_180016D00
0x180016ce8  mov     rcx, [rcx+10h]
0x180016cec  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x180016cf3  mov     edx, 12h
0x180016cf8  mov     r9d, eax
0x180016cfb  call    WPP_SF_d
0x180016d00  test    ebx, ebx
0x180016d02  js      short loc_180016D65
0x180016d04  mov     rcx, [rbp+arg_18]
0x180016d08  lea     r9, [rbp+arg_10]
0x180016d0c  lea     r8, [rbp+arg_8]
0x180016d10  mov     edx, 16000072h
0x180016d15  call    cs:__imp_BcdGetElementData
0x180016d1c  nop     dword ptr [rax+rax+00h]
0x180016d21  mov     ecx, eax; int
0x180016d23  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180016d28  mov     ebx, eax
0x180016d2a  test    eax, eax
0x180016d2c  jz      short loc_180016D5C
0x180016d2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d35  cmp     rcx, r15
0x180016d38  jz      short loc_180016D58
0x180016d3a  test    byte ptr [rcx+1Ch], 40h
0x180016d3e  jz      short loc_180016D58
0x180016d40  mov     rcx, [rcx+10h]
0x180016d44  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x180016d4b  mov     edx, 13h
0x180016d50  mov     r9d, eax
0x180016d53  call    WPP_SF_d
0x180016d58  test    ebx, ebx
0x180016d5a  js      short loc_180016D65
0x180016d5c  cmp     byte ptr [rbp+arg_8], 0
0x180016d60  setnz   al
0x180016d63  mov     [rdi], al
0x180016d65  mov     rcx, [rbp+arg_18]
0x180016d69  test    rcx, rcx
0x180016d6c  jz      short loc_180016D7A
0x180016d6e  call    cs:__imp_BcdCloseObject
0x180016d75  nop     dword ptr [rax+rax+00h]
0x180016d7a  mov     rcx, [rbp+var_10]
0x180016d7e  test    rcx, rcx
0x180016d81  jz      short loc_180016D8F
0x180016d83  call    cs:__imp_BcdCloseStore
0x180016d8a  nop     dword ptr [rax+rax+00h]
0x180016d8f  mov     eax, ebx
0x180016d91  mov     rbx, [rsp+30h+arg_0]
0x180016d96  add     rsp, 30h
0x180016d9a  pop     r15
0x180016d9c  pop     rdi
0x180016d9d  pop     rbp
0x180016d9e  retn
```
