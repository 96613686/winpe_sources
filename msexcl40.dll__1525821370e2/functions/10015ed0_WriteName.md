# WriteName

- ea: `0x10015ed0`
- end: `0x1001605a`
- name: `WriteName`
- size: `394`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x10016060`

## callees

- `0x10015ed0`
- `0x1002580a`
- `0x10025ab7`
- `0x1002611f`
- `0x10035f40`
- `0x1003669c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10015f2a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10015f87`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10015f2a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10015f87`

## pseudocode

```c
int __fastcall WriteName(_DWORD *a1, const unsigned __int16 *a2, int a3, int a4, int a5)
{
  UINT v6; // edx
  int v7; // eax
  size_t v8; // ebx
  CHAR *v9; // edi
  int result; // eax
  UINT v11; // edx
  int v12; // esi
  int v13; // eax
  unsigned int v14; // esi
  int v15; // [esp-14h] [ebp-38h]
  int v16; // [esp-14h] [ebp-38h]
  int v17; // [esp+14h] [ebp-10h]
  _WORD *v19; // [esp+1Ch] [ebp-8h]
  __int16 v20; // [esp+20h] [ebp-4h] BYREF
  __int16 v21; // [esp+22h] [ebp-2h]

  v19 = pExcelRecordBuffer;
  v6 = a1[6];
  v17 = a1[2];
  v20 = 536;
  v15 = wcslen(a2);
  if ( v6 == 1200 )
    v7 = WideCharToMultiByte(0, 0, a2, v15, 0, 0, 0, 0);
  else
    v7 = WideCharToMultiByte(v6, 0, a2, v15, 0, 0, 0, 0);
  v8 = v7;
  v9 = (CHAR *)MemAllocate(v7 + 1);
  if ( !v9 )
    return -1011;
  v11 = a1[6];
  v16 = wcslen(a2);
  if ( v11 == 1200 )
    WideCharToMultiByte(0, 0, a2, v16, v9, v8, 0, 0);
  else
    WideCharToMultiByte(v11, 0, a2, v16, v9, v8, 0, 0);
  v21 = *(_WORD *)(v17 + 180) + v8 + 7;
  v12 = BFWriteFile(a1[5], (char *)&v20, 4u);
  if ( v12 )
  {
    MemFree(v9);
    v13 = v12;
  }
  else
  {
    v14 = v21;
    memset(v19, 0, v21);
    *v19 = 0;
    *((_BYTE *)v19 + 2) = 0;
    *((_BYTE *)v19 + 3) = v8;
    v19[2] = *(_WORD *)(v17 + 180) + 1;
    memcpy(v19 + 3, v9, v8);
    MemFree(v9);
    *(_WORD *)((char *)v19 + v8 + 7) = a4;
    *(_WORD *)((char *)v19 + v8 + 9) = a5;
    *((_BYTE *)v19 + v8 + 11) = BYTE2(a4);
    *((_BYTE *)v19 + v8 + 12) = BYTE2(a5);
    *((_BYTE *)v19 + v8 + 6) = 45;
    v13 = BFWriteFile(a1[5], (char *)v19, v14);
  }
  result = dword_10001970[abs32(v13)];
  if ( result == -10 )
    return -10;
  return result;
}

```

## disassembly

```asm
0x10015ed0  mov     edi, edi
0x10015ed2  push    ebp
0x10015ed3  mov     ebp, esp
0x10015ed5  sub     esp, 18h
0x10015ed8  mov     eax, ecx
0x10015eda  mov     ecx, _pExcelRecordBuffer
0x10015ee0  push    ebx
0x10015ee1  push    esi
0x10015ee2  mov     esi, edx
0x10015ee4  mov     [ebp+var_8], ecx
0x10015ee7  mov     ecx, [eax+8]
0x10015eea  mov     edx, [eax+18h]
0x10015eed  mov     [ebp+var_C], eax
0x10015ef0  mov     eax, esi
0x10015ef2  mov     [ebp+var_10], ecx
0x10015ef5  mov     ecx, 218h
0x10015efa  push    edi
0x10015efb  mov     [ebp+var_4], cx
0x10015eff  lea     edi, [eax+2]
0x10015f02  mov     cx, [eax]
0x10015f05  add     eax, 2
0x10015f08  test    cx, cx
0x10015f0b  jnz     short loc_10015F02
0x10015f0d  push    0; lpUsedDefaultChar
0x10015f0f  push    0; lpDefaultChar
0x10015f11  push    0; cbMultiByte
0x10015f13  sub     eax, edi
0x10015f15  push    0; lpMultiByteStr
0x10015f17  sar     eax, 1
0x10015f19  push    eax; cchWideChar
0x10015f1a  push    esi; lpWideCharStr
0x10015f1b  push    0; dwFlags
0x10015f1d  cmp     edx, 4B0h
0x10015f23  jz      short loc_10015F28
0x10015f25  push    edx
0x10015f26  jmp     short loc_10015F2A
0x10015f28  push    0; CodePage
0x10015f2a  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x10015f30  mov     ebx, eax
0x10015f32  lea     ecx, [ebx+1]
0x10015f35  call    _MemAllocate@4; MemAllocate(x)
0x10015f3a  mov     edi, eax
0x10015f3c  test    edi, edi
0x10015f3e  jnz     short loc_10015F4E
0x10015f40  mov     eax, 0FFFFFC0Dh
0x10015f45  pop     edi
0x10015f46  pop     esi
0x10015f47  pop     ebx
0x10015f48  mov     esp, ebp
0x10015f4a  pop     ebp
0x10015f4b  retn    0Ch
0x10015f4e  mov     eax, [ebp+var_C]
0x10015f51  mov     ecx, esi
0x10015f53  mov     edx, [eax+18h]
0x10015f56  lea     eax, [ecx+2]
0x10015f59  mov     [ebp+var_14], eax
0x10015f5c  nop     dword ptr [eax+00h]
0x10015f60  mov     ax, [ecx]
0x10015f63  add     ecx, 2
0x10015f66  test    ax, ax
0x10015f69  jnz     short loc_10015F60
0x10015f6b  sub     ecx, [ebp+var_14]
0x10015f6e  push    0; lpUsedDefaultChar
0x10015f70  push    0; lpDefaultChar
0x10015f72  push    ebx; cbMultiByte
0x10015f73  push    edi; lpMultiByteStr
0x10015f74  sar     ecx, 1
0x10015f76  push    ecx; cchWideChar
0x10015f77  push    esi; lpWideCharStr
0x10015f78  push    0; dwFlags
0x10015f7a  cmp     edx, 4B0h
0x10015f80  jz      short loc_10015F85
0x10015f82  push    edx
0x10015f83  jmp     short loc_10015F87
0x10015f85  push    0; CodePage
0x10015f87  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x10015f8d  mov     ecx, [ebp+var_10]
0x10015f90  lea     eax, [ebx+7]
0x10015f93  push    4
0x10015f95  lea     edx, [ebp+var_4]
0x10015f98  add     ax, [ecx+0B4h]
0x10015f9f  mov     [ebp+var_2], ax
0x10015fa3  mov     eax, [ebp+var_C]
0x10015fa6  mov     ecx, [eax+14h]
0x10015fa9  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x10015fae  mov     esi, eax
0x10015fb0  test    esi, esi
0x10015fb2  jz      short loc_10015FBF
0x10015fb4  mov     ecx, edi
0x10015fb6  call    _MemFree@4; MemFree(x)
0x10015fbb  mov     eax, esi
0x10015fbd  jmp     short loc_1001603A
0x10015fbf  movsx   esi, [ebp+var_2]
0x10015fc3  push    esi; Size
0x10015fc4  push    0; Val
0x10015fc6  push    [ebp+var_8]; void *
0x10015fc9  call    _memset
0x10015fce  mov     ecx, [ebp+var_8]
0x10015fd1  xor     eax, eax
0x10015fd3  add     esp, 0Ch
0x10015fd6  mov     [ecx], ax
0x10015fd9  mov     [ecx+2], al
0x10015fdc  mov     eax, [ebp+var_10]
0x10015fdf  mov     [ecx+3], bl
0x10015fe2  push    ebx; Size
0x10015fe3  push    edi; Src
0x10015fe4  movzx   eax, word ptr [eax+0B4h]
0x10015feb  inc     ax
0x10015fed  mov     [ecx+4], ax
0x10015ff1  lea     eax, [ecx+6]
0x10015ff4  push    eax; void *
0x10015ff5  call    _memcpy
0x10015ffa  add     esp, 0Ch
0x10015ffd  mov     ecx, edi
0x10015fff  call    _MemFree@4; MemFree(x)
0x10016004  mov     ecx, [ebp+var_8]
0x10016007  mov     edx, ecx
0x10016009  mov     ax, [ebp+arg_4]
0x1001600d  push    esi
0x1001600e  mov     [ebx+ecx+7], ax
0x10016013  mov     ax, [ebp+arg_8]
0x10016017  mov     [ebx+ecx+9], ax
0x1001601c  mov     al, [ebp+arg_6]
0x1001601f  mov     [ebx+ecx+0Bh], al
0x10016023  mov     al, [ebp+arg_A]
0x10016026  mov     [ebx+ecx+0Ch], al
0x1001602a  mov     eax, [ebp+var_C]
0x1001602d  mov     byte ptr [ebx+ecx+6], 2Dh ; '-'
0x10016032  mov     ecx, [eax+14h]
0x10016035  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x1001603a  cdq
0x1001603b  mov     ecx, 0FFFFFFF6h
0x10016040  xor     eax, edx
0x10016042  sub     eax, edx
0x10016044  pop     edi
0x10016045  pop     esi
0x10016046  pop     ebx
0x10016047  mov     eax, ds:dword_10001970[eax*4]
0x1001604e  cmp     eax, 0FFFFFFF6h
0x10016051  cmovz   eax, ecx
0x10016054  mov     esp, ebp
0x10016056  pop     ebp
0x10016057  retn    0Ch
```
