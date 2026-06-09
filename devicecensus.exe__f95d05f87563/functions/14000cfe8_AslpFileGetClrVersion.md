# AslpFileGetClrVersion

- ea: `0x14000cfe8`
- end: `0x14000d189`
- name: `AslpFileGetClrVersion`
- size: `417`
- prototype: `__int64 __fastcall(_BYTE *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000d190`

## callees

- `0x140001fe6`
- `0x140007074`
- `0x14000cfe8`
- `0x14000dc74`
- `0x1400101cc`

## string_xrefs

- `0x14000d01a`: `AslpFileGetImageNtHeader failed [%x]`
- `0x14000d095`: `Invalid COM Descriptor virtual address encountered`

## pseudocode

```c
__int64 __fastcall AslpFileGetClrVersion(_BYTE *a1, __int64 a2)
{
  _DWORD *v4; // rdi
  int ImageNtHeader; // eax
  unsigned int v6; // ebx
  __int64 v7; // rbx
  __int64 v8; // rax
  const char *v9; // r9
  __int64 v10; // r8
  _DWORD *v11; // rax
  __int64 v12; // rbx
  __int64 v14; // [rsp+70h] [rbp+8h] BYREF

  v14 = 0;
  v4 = 0;
  *a1 = 0;
  ImageNtHeader = AslpFileGetImageNtHeader(&v14, a2);
  v6 = ImageNtHeader;
  if ( ImageNtHeader >= 0 )
  {
    v7 = v14;
    if ( *(_WORD *)(v14 + 24) == 267 )
    {
      v4 = (_DWORD *)(v14 + 232);
    }
    else if ( *(_WORD *)(v14 + 24) == 523 )
    {
      v4 = (_DWORD *)(v14 + 248);
    }
    if ( !v4 || !*v4 || v4[1] < 0x48u )
      return (unsigned int)-1073741701;
    v8 = AslpImageRvaToVa(v14, a2);
    if ( v8 )
    {
      if ( *(_WORD *)(v8 + 4) != 2 )
        return (unsigned int)-1073741637;
      v11 = (_DWORD *)AslpImageRvaToVa(v7, a2);
      if ( v11 )
      {
        if ( *v11 != 1112167234 )
        {
          v6 = -1073741637;
          v9 = "Invalid COR20 Metadata signature encountered";
          v10 = 5739;
          goto LABEL_13;
        }
        v12 = (unsigned int)v11[3];
        if ( (unsigned __int64)(v12 - 1) <= 0xFE )
        {
          memcpy_0(a1, v11 + 4, (unsigned int)v12);
          a1[v12] = 0;
          return 0;
        }
        v9 = "CLR version string null or too long";
        v10 = 5751;
      }
      else
      {
        v9 = "Invalid COR20 Metadata virtual address encountered";
        v10 = 5729;
      }
    }
    else
    {
      v9 = "Invalid COM Descriptor virtual address encountered";
      v10 = 5709;
    }
    v6 = -1073741701;
LABEL_13:
    AslLogCallPrintf(1, "AslpFileGetClrVersion", v10, v9);
    return v6;
  }
  AslLogCallPrintf(1, "AslpFileGetClrVersion", 5680, "AslpFileGetImageNtHeader failed [%x]", ImageNtHeader);
  return v6;
}

```

## disassembly

```asm
0x14000cfe8  push    rbx
0x14000cfea  push    rsi
0x14000cfeb  push    rdi
0x14000cfec  push    r14
0x14000cfee  sub     rsp, 48h
0x14000cff2  mov     r14, rdx
0x14000cff5  mov     rsi, rcx
0x14000cff8  mov     [rsp+68h+arg_0], 0
0x14000d001  xor     edi, edi
0x14000d003  mov     [rcx], dil
0x14000d006  lea     rcx, [rsp+68h+arg_0]
0x14000d00b  call    AslpFileGetImageNtHeader
0x14000d010  mov     ebx, eax
0x14000d012  test    eax, eax
0x14000d014  jns     short loc_14000D03B
0x14000d016  mov     [rsp+68h+var_48], eax
0x14000d01a  lea     r9, aAslpfilegetima_1; "AslpFileGetImageNtHeader failed [%x]"
0x14000d021  mov     r8d, 1630h
0x14000d027  lea     rdx, aAslpfilegetclr; "AslpFileGetClrVersion"
0x14000d02e  lea     ecx, [rdi+1]
0x14000d031  call    AslLogCallPrintf
0x14000d036  jmp     loc_14000D17D
0x14000d03b  mov     rbx, [rsp+68h+arg_0]
0x14000d040  mov     eax, 10Bh
0x14000d045  cmp     [rbx+18h], ax
0x14000d049  jnz     short loc_14000D054
0x14000d04b  lea     rdi, [rbx+0E8h]
0x14000d052  jmp     short loc_14000D066
0x14000d054  mov     eax, 20Bh
0x14000d059  cmp     [rbx+18h], ax
0x14000d05d  jnz     short loc_14000D066
0x14000d05f  lea     rdi, [rbx+0F8h]
0x14000d066  test    rdi, rdi
0x14000d069  jz      loc_14000D149
0x14000d06f  mov     r8d, [rdi]
0x14000d072  test    r8d, r8d
0x14000d075  jz      loc_14000D149
0x14000d07b  cmp     dword ptr [rdi+4], 48h ; 'H'
0x14000d07f  jb      loc_14000D149
0x14000d085  mov     rdx, r14
0x14000d088  mov     rcx, rbx
0x14000d08b  call    AslpImageRvaToVa
0x14000d090  test    rax, rax
0x14000d093  jnz     short loc_14000D0C1
0x14000d095  lea     r9, aInvalidComDesc; "Invalid COM Descriptor virtual address "...
0x14000d09c  mov     r8d, 164Dh
0x14000d0a2  mov     ebx, 0C000007Bh
0x14000d0a7  mov     [rsp+68h+var_38], ebx
0x14000d0ab  lea     rdx, aAslpfilegetclr; "AslpFileGetClrVersion"
0x14000d0b2  mov     ecx, 1
0x14000d0b7  call    AslLogCallPrintf
0x14000d0bc  jmp     loc_14000D152
0x14000d0c1  cmp     word ptr [rax+4], 2
0x14000d0c6  jz      short loc_14000D0CF
0x14000d0c8  mov     ebx, 0C00000BBh
0x14000d0cd  jmp     short loc_14000D14E
0x14000d0cf  mov     r8d, [rax+8]
0x14000d0d3  mov     rdx, r14
0x14000d0d6  mov     rcx, rbx
0x14000d0d9  call    AslpImageRvaToVa
0x14000d0de  mov     rdx, rax
0x14000d0e1  test    rax, rax
0x14000d0e4  jnz     short loc_14000D0F5
0x14000d0e6  lea     r9, aInvalidCor20Me; "Invalid COR20 Metadata virtual address "...
0x14000d0ed  mov     r8d, 1661h
0x14000d0f3  jmp     short loc_14000D0A2
0x14000d0f5  cmp     dword ptr [rax], 424A5342h
0x14000d0fb  jz      short loc_14000D111
0x14000d0fd  mov     ebx, 0C00000BBh
0x14000d102  lea     r9, aInvalidCor20Me_0; "Invalid COR20 Metadata signature encoun"...
0x14000d109  mov     r8d, 166Bh
0x14000d10f  jmp     short loc_14000D0A7
0x14000d111  mov     ebx, [rax+0Ch]
0x14000d114  lea     rax, [rbx-1]
0x14000d118  cmp     rax, 0FEh
0x14000d11e  ja      short loc_14000D137
0x14000d120  add     rdx, 10h; Src
0x14000d124  mov     r8d, ebx; Size
0x14000d127  mov     rcx, rsi; void *
0x14000d12a  call    memcpy_0
0x14000d12f  mov     byte ptr [rbx+rsi], 0
0x14000d133  xor     ebx, ebx
0x14000d135  jmp     short loc_14000D14E
0x14000d137  lea     r9, aClrVersionStri; "CLR version string null or too long"
0x14000d13e  mov     r8d, 1677h
0x14000d144  jmp     loc_14000D0A2
0x14000d149  mov     ebx, 0C000007Bh
0x14000d14e  mov     [rsp+68h+var_38], ebx
0x14000d152  jmp     short loc_14000D17D
0x14000d154  mov     ebx, eax
0x14000d156  mov     [rsp+68h+var_38], eax
0x14000d15a  mov     [rsp+68h+var_48], eax
0x14000d15e  lea     r9, aExceptionEncou; "Exception encountered [%x]"
0x14000d165  mov     r8d, 168Eh
0x14000d16b  lea     rdx, aAslpfilegetclr; "AslpFileGetClrVersion"
0x14000d172  mov     ecx, 1
0x14000d177  call    AslLogCallPrintf
0x14000d17c  nop
0x14000d17d  mov     eax, ebx
0x14000d17f  add     rsp, 48h
0x14000d183  pop     r14
0x14000d185  pop     rdi
0x14000d186  pop     rsi
0x14000d187  pop     rbx
0x14000d188  retn
0x140011836  push    rbp
0x140011838  sub     rsp, 30h
0x14001183c  mov     rbp, rdx
0x14001183f  mov     rax, [rcx]
0x140011842  xor     ecx, ecx
0x140011844  cmp     dword ptr [rax], 0C00000FDh
0x14001184a  setnz   cl
0x14001184d  mov     [rbp+34h], ecx
0x140011850  mov     eax, [rbp+34h]
0x140011853  add     rsp, 30h
0x140011857  pop     rbp
0x140011858  retn
```
