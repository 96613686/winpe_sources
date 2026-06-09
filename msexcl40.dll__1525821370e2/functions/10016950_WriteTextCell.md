# WriteTextCell

- ea: `0x10016950`
- end: `0x10016af2`
- name: `WriteTextCell`
- size: `418`
- prototype: `int __stdcall(int, __int16, LPCWCH lpWideCharStr)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x10016b00`

## callees

- `0x10016950`
- `0x1002580a`
- `0x10025ab7`
- `0x1002611f`
- `0x10035510`
- `0x10035f40`
- `0x1003669c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x100169cf`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10016a20`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x100169cf`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10016a20`

## pseudocode

```c
int __fastcall WriteTextCell(int a1, UINT a2, int a3, __int16 a4, LPCWCH lpWideCharStr)
{
  const WCHAR *v5; // ecx
  int v6; // esi
  CHAR *v7; // edi
  int v8; // ebx
  int v9; // eax
  int result; // eax
  int v11; // eax
  size_t v12; // esi
  int v13; // ecx
  int v14; // eax
  _WORD *v15; // [esp+10h] [ebp-404h]
  UINT v17; // [esp+18h] [ebp-3FCh]
  __int16 v18; // [esp+18h] [ebp-3FCh]
  LPCWCH v19; // [esp+1Ch] [ebp-3F8h] BYREF
  CHAR MultiByteStr[1004]; // [esp+20h] [ebp-3F4h] BYREF

  v5 = lpWideCharStr;
  v17 = a2;
  v19 = lpWideCharStr;
  v15 = pExcelRecordBuffer;
  v6 = wcslen(lpWideCharStr);
  if ( (unsigned int)(2 * v6) >= 0x3E8 )
  {
    if ( a2 == 1200 )
      v9 = WideCharToMultiByte(0, 0, lpWideCharStr, v6, 0, 0, 0, 0);
    else
      v9 = WideCharToMultiByte(a2, 0, lpWideCharStr, v6, 0, 0, 0, 0);
    v8 = v9;
    v7 = (CHAR *)MemAllocate(v9 + 1);
    if ( !v7 )
      return -1011;
    v5 = v19;
    a2 = v17;
  }
  else
  {
    v7 = MultiByteStr;
    v8 = 1000;
  }
  if ( a2 == 1200 )
    v11 = WideCharToMultiByte(0, 0, v5, v6, v7, v8, 0, 0);
  else
    v11 = WideCharToMultiByte(a2, 0, v5, v6, v7, v8, 0, 0);
  v12 = v11;
  LOWORD(v19) = 516;
  v13 = *(_DWORD *)(a1 + 20);
  v18 = v11;
  HIWORD(v19) = v11 + 8;
  v14 = BFWriteFile(v13, (char *)&v19, 4u);
  if ( !v14 )
  {
    memset(v15, 0, SHIWORD(v19));
    *(_DWORD *)v15 = a3;
    v15[2] = a4;
    v15[3] = v18;
    memcpy(v15 + 4, v7, v12);
    if ( v7 != MultiByteStr )
      MemFree(v7);
    v14 = BFWriteFile(*(_DWORD *)(a1 + 20), (char *)v15, SHIWORD(v19));
  }
  result = dword_10001970[abs32(v14)];
  if ( result == -10 )
    return -10;
  return result;
}

```

## disassembly

```asm
0x10016950  mov     edi, edi
0x10016952  push    ebp
0x10016953  mov     ebp, esp
0x10016955  sub     esp, 408h
0x1001695b  mov     eax, ___security_cookie
0x10016960  xor     eax, ebp
0x10016962  mov     [ebp+var_8], eax
0x10016965  mov     eax, _pExcelRecordBuffer
0x1001696a  push    ebx
0x1001696b  push    esi
0x1001696c  mov     [ebp+var_400], ecx
0x10016972  mov     ecx, [ebp+lpWideCharStr]
0x10016975  mov     esi, ecx
0x10016977  push    edi
0x10016978  mov     [ebp+var_3FC], edx
0x1001697e  mov     [ebp+var_3F8], ecx
0x10016984  mov     [ebp+var_404], eax
0x1001698a  lea     edi, [esi+2]
0x1001698d  nop     dword ptr [eax]
0x10016990  mov     ax, [esi]
0x10016993  add     esi, 2
0x10016996  test    ax, ax
0x10016999  jnz     short loc_10016990
0x1001699b  sub     esi, edi
0x1001699d  sar     esi, 1
0x1001699f  lea     eax, [esi+esi]
0x100169a2  cmp     eax, 3E8h
0x100169a7  jnb     short loc_100169B6
0x100169a9  lea     edi, [ebp+MultiByteStr]
0x100169af  mov     ebx, 3E8h
0x100169b4  jmp     short loc_10016A09
0x100169b6  push    0; lpUsedDefaultChar
0x100169b8  push    0; lpDefaultChar
0x100169ba  push    0; cbMultiByte
0x100169bc  push    0; lpMultiByteStr
0x100169be  push    esi; cchWideChar
0x100169bf  push    ecx; lpWideCharStr
0x100169c0  push    0; dwFlags
0x100169c2  cmp     edx, 4B0h
0x100169c8  jz      short loc_100169CD
0x100169ca  push    edx
0x100169cb  jmp     short loc_100169CF
0x100169cd  push    0; CodePage
0x100169cf  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x100169d5  mov     ebx, eax
0x100169d7  lea     ecx, [ebx+1]
0x100169da  call    _MemAllocate@4; MemAllocate(x)
0x100169df  mov     edi, eax
0x100169e1  test    edi, edi
0x100169e3  jnz     short loc_100169FD
0x100169e5  mov     eax, 0FFFFFC0Dh
0x100169ea  pop     edi
0x100169eb  pop     esi
0x100169ec  pop     ebx
0x100169ed  mov     ecx, [ebp+var_8]
0x100169f0  xor     ecx, ebp; StackCookie
0x100169f2  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100169f7  mov     esp, ebp
0x100169f9  pop     ebp
0x100169fa  retn    0Ch
0x100169fd  mov     ecx, [ebp+var_3F8]
0x10016a03  mov     edx, [ebp+var_3FC]
0x10016a09  push    0; lpUsedDefaultChar
0x10016a0b  push    0; lpDefaultChar
0x10016a0d  push    ebx; cbMultiByte
0x10016a0e  push    edi; lpMultiByteStr
0x10016a0f  push    esi; cchWideChar
0x10016a10  push    ecx; lpWideCharStr
0x10016a11  push    0; dwFlags
0x10016a13  cmp     edx, 4B0h
0x10016a19  jz      short loc_10016A1E
0x10016a1b  push    edx
0x10016a1c  jmp     short loc_10016A20
0x10016a1e  push    0; CodePage
0x10016a20  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x10016a26  mov     ecx, [ebp+var_400]
0x10016a2c  lea     edx, [ebp+var_3F8]
0x10016a32  mov     esi, eax
0x10016a34  mov     eax, 204h
0x10016a39  mov     word ptr [ebp+var_3F8], ax
0x10016a40  movzx   eax, si
0x10016a43  mov     ecx, [ecx+14h]
0x10016a46  mov     [ebp+var_3FC], eax
0x10016a4c  add     eax, 8
0x10016a4f  push    4
0x10016a51  mov     word ptr [ebp+var_3F8+2], ax
0x10016a58  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x10016a5d  test    eax, eax
0x10016a5f  jnz     short loc_10016AC8
0x10016a61  movsx   eax, word ptr [ebp+var_3F8+2]
0x10016a68  mov     ebx, [ebp+var_404]
0x10016a6e  push    eax; Size
0x10016a6f  push    0; Val
0x10016a71  push    ebx; void *
0x10016a72  call    _memset
0x10016a77  mov     eax, [ebp+arg_0]
0x10016a7a  add     esp, 0Ch
0x10016a7d  mov     [ebx], eax
0x10016a7f  mov     ax, [ebp+arg_4]
0x10016a83  mov     [ebx+4], ax
0x10016a87  mov     eax, [ebp+var_3FC]
0x10016a8d  push    esi; Size
0x10016a8e  mov     [ebx+6], ax
0x10016a92  lea     eax, [ebx+8]
0x10016a95  push    edi; Src
0x10016a96  push    eax; void *
0x10016a97  call    _memcpy
0x10016a9c  lea     eax, [ebp+MultiByteStr]
0x10016aa2  add     esp, 0Ch
0x10016aa5  cmp     edi, eax
0x10016aa7  jz      short loc_10016AB0
0x10016aa9  mov     ecx, edi
0x10016aab  call    _MemFree@4; MemFree(x)
0x10016ab0  movsx   eax, word ptr [ebp+var_3F8+2]
0x10016ab7  mov     edx, ebx
0x10016ab9  push    eax
0x10016aba  mov     eax, [ebp+var_400]
0x10016ac0  mov     ecx, [eax+14h]
0x10016ac3  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x10016ac8  cdq
0x10016ac9  mov     ecx, 0FFFFFFF6h
0x10016ace  xor     eax, edx
0x10016ad0  sub     eax, edx
0x10016ad2  pop     edi
0x10016ad3  pop     esi
0x10016ad4  pop     ebx
0x10016ad5  mov     eax, ds:dword_10001970[eax*4]
0x10016adc  cmp     eax, 0FFFFFFF6h
0x10016adf  cmovz   eax, ecx
0x10016ae2  mov     ecx, [ebp+var_8]
0x10016ae5  xor     ecx, ebp; StackCookie
0x10016ae7  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10016aec  mov     esp, ebp
0x10016aee  pop     ebp
0x10016aef  retn    0Ch
```
