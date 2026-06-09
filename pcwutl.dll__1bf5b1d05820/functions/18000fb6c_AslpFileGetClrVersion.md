# AslpFileGetClrVersion

- ea: `0x18000fb6c`
- end: `0x18000fd0d`
- name: `AslpFileGetClrVersion`
- size: `417`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000fd14`

## callees

- `0x1800027d6`
- `0x18000e240`
- `0x18000fb6c`
- `0x1800107f8`
- `0x180013658`

## string_xrefs

- `0x18000fb9e`: `AslpFileGetImageNtHeader failed [%x]`
- `0x18000fc19`: `Invalid COM Descriptor virtual address encountered`

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
0x18000fb6c  push    rbx
0x18000fb6e  push    rsi
0x18000fb6f  push    rdi
0x18000fb70  push    r14
0x18000fb72  sub     rsp, 48h
0x18000fb76  mov     r14, rdx
0x18000fb79  mov     rsi, rcx
0x18000fb7c  mov     [rsp+68h+arg_0], 0
0x18000fb85  xor     edi, edi
0x18000fb87  mov     [rcx], dil
0x18000fb8a  lea     rcx, [rsp+68h+arg_0]
0x18000fb8f  call    AslpFileGetImageNtHeader
0x18000fb94  mov     ebx, eax
0x18000fb96  test    eax, eax
0x18000fb98  jns     short loc_18000FBBF
0x18000fb9a  mov     [rsp+68h+var_48], eax
0x18000fb9e  lea     r9, aAslpfilegetima_1; "AslpFileGetImageNtHeader failed [%x]"
0x18000fba5  mov     r8d, 1630h
0x18000fbab  lea     rdx, aAslpfilegetclr; "AslpFileGetClrVersion"
0x18000fbb2  lea     ecx, [rdi+1]
0x18000fbb5  call    AslLogCallPrintf
0x18000fbba  jmp     loc_18000FD01
0x18000fbbf  mov     rbx, [rsp+68h+arg_0]
0x18000fbc4  mov     eax, 10Bh
0x18000fbc9  cmp     [rbx+18h], ax
0x18000fbcd  jnz     short loc_18000FBD8
0x18000fbcf  lea     rdi, [rbx+0E8h]
0x18000fbd6  jmp     short loc_18000FBEA
0x18000fbd8  mov     eax, 20Bh
0x18000fbdd  cmp     [rbx+18h], ax
0x18000fbe1  jnz     short loc_18000FBEA
0x18000fbe3  lea     rdi, [rbx+0F8h]
0x18000fbea  test    rdi, rdi
0x18000fbed  jz      loc_18000FCCD
0x18000fbf3  mov     r8d, [rdi]
0x18000fbf6  test    r8d, r8d
0x18000fbf9  jz      loc_18000FCCD
0x18000fbff  cmp     dword ptr [rdi+4], 48h ; 'H'
0x18000fc03  jb      loc_18000FCCD
0x18000fc09  mov     rdx, r14
0x18000fc0c  mov     rcx, rbx
0x18000fc0f  call    AslpImageRvaToVa
0x18000fc14  test    rax, rax
0x18000fc17  jnz     short loc_18000FC45
0x18000fc19  lea     r9, aInvalidComDesc; "Invalid COM Descriptor virtual address "...
0x18000fc20  mov     r8d, 164Dh
0x18000fc26  mov     ebx, 0C000007Bh
0x18000fc2b  mov     [rsp+68h+var_38], ebx
0x18000fc2f  lea     rdx, aAslpfilegetclr; "AslpFileGetClrVersion"
0x18000fc36  mov     ecx, 1
0x18000fc3b  call    AslLogCallPrintf
0x18000fc40  jmp     loc_18000FCD6
0x18000fc45  cmp     word ptr [rax+4], 2
0x18000fc4a  jz      short loc_18000FC53
0x18000fc4c  mov     ebx, 0C00000BBh
0x18000fc51  jmp     short loc_18000FCD2
0x18000fc53  mov     r8d, [rax+8]
0x18000fc57  mov     rdx, r14
0x18000fc5a  mov     rcx, rbx
0x18000fc5d  call    AslpImageRvaToVa
0x18000fc62  mov     rdx, rax
0x18000fc65  test    rax, rax
0x18000fc68  jnz     short loc_18000FC79
0x18000fc6a  lea     r9, aInvalidCor20Me; "Invalid COR20 Metadata virtual address "...
0x18000fc71  mov     r8d, 1661h
0x18000fc77  jmp     short loc_18000FC26
0x18000fc79  cmp     dword ptr [rax], 424A5342h
0x18000fc7f  jz      short loc_18000FC95
0x18000fc81  mov     ebx, 0C00000BBh
0x18000fc86  lea     r9, aInvalidCor20Me_0; "Invalid COR20 Metadata signature encoun"...
0x18000fc8d  mov     r8d, 166Bh
0x18000fc93  jmp     short loc_18000FC2B
0x18000fc95  mov     ebx, [rax+0Ch]
0x18000fc98  lea     rax, [rbx-1]
0x18000fc9c  cmp     rax, 0FEh
0x18000fca2  ja      short loc_18000FCBB
0x18000fca4  add     rdx, 10h; Src
0x18000fca8  mov     r8d, ebx; Size
0x18000fcab  mov     rcx, rsi; void *
0x18000fcae  call    memcpy_0
0x18000fcb3  mov     byte ptr [rbx+rsi], 0
0x18000fcb7  xor     ebx, ebx
0x18000fcb9  jmp     short loc_18000FCD2
0x18000fcbb  lea     r9, aClrVersionStri; "CLR version string null or too long"
0x18000fcc2  mov     r8d, 1677h
0x18000fcc8  jmp     loc_18000FC26
0x18000fccd  mov     ebx, 0C000007Bh
0x18000fcd2  mov     [rsp+68h+var_38], ebx
0x18000fcd6  jmp     short loc_18000FD01
0x18000fcd8  mov     ebx, eax
0x18000fcda  mov     [rsp+68h+var_38], eax
0x18000fcde  mov     [rsp+68h+var_48], eax
0x18000fce2  lea     r9, aExceptionEncou; "Exception encountered [%x]"
0x18000fce9  mov     r8d, 168Eh
0x18000fcef  lea     rdx, aAslpfilegetclr; "AslpFileGetClrVersion"
0x18000fcf6  mov     ecx, 1
0x18000fcfb  call    AslLogCallPrintf
0x18000fd00  nop
0x18000fd01  mov     eax, ebx
0x18000fd03  add     rsp, 48h
0x18000fd07  pop     r14
0x18000fd09  pop     rdi
0x18000fd0a  pop     rsi
0x18000fd0b  pop     rbx
0x18000fd0c  retn
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
