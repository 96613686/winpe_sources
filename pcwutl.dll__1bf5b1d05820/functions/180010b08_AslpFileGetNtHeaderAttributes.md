# AslpFileGetNtHeaderAttributes

- ea: `0x180010b08`
- end: `0x180010c40`
- name: `AslpFileGetNtHeaderAttributes`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18001057c`

## callees

- `0x18000e240`
- `0x1800107f8`
- `0x180010b08`

## string_xrefs

- `0x180010b45`: `AslpFileGetImageNtHeader failed [%x]`

## pseudocode

```c
__int64 __fastcall AslpFileGetNtHeaderAttributes(
        _DWORD *a1,
        _DWORD *a2,
        _DWORD *a3,
        _DWORD *a4,
        _WORD *a5,
        _WORD *a6,
        _WORD *a7,
        _WORD *a8,
        __int64 a9)
{
  int ImageNtHeader; // eax
  unsigned int v14; // ebx
  __int64 v15; // r8
  __int16 v16; // dx
  __int16 v17; // cx
  _QWORD v19[6]; // [rsp+38h] [rbp-30h] BYREF

  v19[0] = 0;
  ImageNtHeader = AslpFileGetImageNtHeader(v19, a9);
  v14 = ImageNtHeader;
  if ( ImageNtHeader >= 0 )
  {
    v15 = v19[0];
    *a2 = (unsigned __int8)*(_WORD *)(v19[0] + 70LL) + ((unsigned __int8)*(_WORD *)(v19[0] + 68LL) << 16);
    *a3 = *(_DWORD *)(v15 + 8);
    v16 = *(_WORD *)(v15 + 24);
    *a7 = v16;
    *a5 = *(_WORD *)(v15 + 4);
    *a8 = *(_WORD *)(v15 + 22);
    if ( v16 == 267 || v16 == 523 )
    {
      *a1 = *(_DWORD *)(v15 + 88);
      *a4 = *(_DWORD *)(v15 + 80);
      v17 = *(_WORD *)(v15 + 92);
      v14 = 0;
    }
    else
    {
      *a1 = 0;
      *a4 = 0;
      v17 = 0;
      v14 = -1073741637;
    }
    *a6 = v17;
  }
  else
  {
    AslLogCallPrintf(1, "AslpFileGetNtHeaderAttributes", 3635, "AslpFileGetImageNtHeader failed [%x]", ImageNtHeader);
  }
  return v14;
}

```

## disassembly

```asm
0x180010b08  push    rbx
0x180010b0a  push    rsi
0x180010b0b  push    rdi
0x180010b0c  push    r14
0x180010b0e  push    r15
0x180010b10  sub     rsp, 40h
0x180010b14  mov     rdi, r9
0x180010b17  mov     r14, r8
0x180010b1a  mov     r15, rdx
0x180010b1d  mov     rsi, rcx
0x180010b20  mov     [rsp+68h+var_30], 0
0x180010b29  mov     rdx, [rsp+68h+arg_40]
0x180010b31  lea     rcx, [rsp+68h+var_30]
0x180010b36  call    AslpFileGetImageNtHeader
0x180010b3b  mov     ebx, eax
0x180010b3d  test    eax, eax
0x180010b3f  jns     short loc_180010B68
0x180010b41  mov     [rsp+68h+var_48], eax
0x180010b45  lea     r9, aAslpfilegetima_1; "AslpFileGetImageNtHeader failed [%x]"
0x180010b4c  mov     r8d, 0E33h
0x180010b52  lea     rdx, aAslpfilegetnth; "AslpFileGetNtHeaderAttributes"
0x180010b59  mov     ecx, 1
0x180010b5e  call    AslLogCallPrintf
0x180010b63  jmp     loc_180010C32
0x180010b68  mov     r8, [rsp+68h+var_30]
0x180010b6d  movzx   eax, word ptr [r8+44h]
0x180010b72  movzx   edx, al
0x180010b75  shl     edx, 10h
0x180010b78  movzx   eax, word ptr [r8+46h]
0x180010b7d  movzx   ecx, al
0x180010b80  add     edx, ecx
0x180010b82  mov     [r15], edx
0x180010b85  mov     eax, [r8+8]
0x180010b89  mov     [r14], eax
0x180010b8c  movzx   edx, word ptr [r8+18h]
0x180010b91  mov     rax, [rsp+68h+arg_30]
0x180010b99  mov     [rax], dx
0x180010b9c  movzx   ecx, word ptr [r8+4]
0x180010ba1  mov     rax, [rsp+68h+arg_20]
0x180010ba9  mov     [rax], cx
0x180010bac  movzx   ecx, word ptr [r8+16h]
0x180010bb1  mov     rax, [rsp+68h+arg_38]
0x180010bb9  mov     [rax], cx
0x180010bbc  mov     eax, 10Bh
0x180010bc1  cmp     dx, ax
0x180010bc4  jz      short loc_180010BE5
0x180010bc6  mov     eax, 20Bh
0x180010bcb  cmp     dx, ax
0x180010bce  jz      short loc_180010BE5
0x180010bd0  mov     dword ptr [rsi], 0
0x180010bd6  mov     dword ptr [rdi], 0
0x180010bdc  xor     ecx, ecx
0x180010bde  mov     ebx, 0C00000BBh
0x180010be3  jmp     short loc_180010BF8
0x180010be5  mov     eax, [r8+58h]
0x180010be9  mov     [rsi], eax
0x180010beb  mov     eax, [r8+50h]
0x180010bef  mov     [rdi], eax
0x180010bf1  movzx   ecx, word ptr [r8+5Ch]
0x180010bf6  xor     ebx, ebx
0x180010bf8  mov     rax, [rsp+68h+arg_28]
0x180010c00  mov     [rax], cx
0x180010c03  mov     [rsp+68h+var_38], ebx
0x180010c07  jmp     short loc_180010C32
0x180010c09  mov     ebx, eax
0x180010c0b  mov     [rsp+68h+var_38], eax
0x180010c0f  mov     [rsp+68h+var_48], eax
0x180010c13  lea     r9, aExceptionEncou; "Exception encountered [%x]"
0x180010c1a  mov     r8d, 0E8Ah
0x180010c20  lea     rdx, aAslpfilegetnth; "AslpFileGetNtHeaderAttributes"
0x180010c27  mov     ecx, 1
0x180010c2c  call    AslLogCallPrintf
0x180010c31  nop
0x180010c32  mov     eax, ebx
0x180010c34  add     rsp, 40h
0x180010c38  pop     r15
0x180010c3a  pop     r14
0x180010c3c  pop     rdi
0x180010c3d  pop     rsi
0x180010c3e  pop     rbx
0x180010c3f  retn
0x180019716  push    rbp
0x180019718  sub     rsp, 30h
0x18001971c  mov     rbp, rdx
0x18001971f  mov     rax, [rcx]
0x180019722  xor     ecx, ecx
0x180019724  cmp     dword ptr [rax], 0C00000FDh
0x18001972a  setnz   cl
0x18001972d  mov     [rbp+34h], ecx
0x180019730  mov     eax, [rbp+34h]
0x180019733  add     rsp, 30h
0x180019737  pop     rbp
0x180019738  retn
```
