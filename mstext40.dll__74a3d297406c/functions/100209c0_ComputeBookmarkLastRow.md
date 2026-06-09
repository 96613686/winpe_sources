# ComputeBookmarkLastRow

- ea: `0x100209c0`
- end: `0x10020c08`
- name: `ComputeBookmarkLastRow`
- size: `584`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10022400`

## callees

- `0x10020780`
- `0x100209c0`
- `0x10020f50`
- `0x10029520`
- `0x100295f0`
- `0x1002b81a`
- `0x1002cce0`
- `0x1002d514`

## import_xrefs

- `KERNEL32!ReadFile` at `0x10020a45`
- `KERNEL32!ReadFile` at `0x10020aee`
- `KERNEL32!ReadFile` at `0x10020a45`
- `KERNEL32!ReadFile` at `0x10020aee`
- `KERNEL32!SetFilePointer` at `0x10020a24`
- `KERNEL32!SetFilePointer` at `0x10020ac7`
- `KERNEL32!SetFilePointer` at `0x10020bd0`
- `KERNEL32!SetFilePointer` at `0x10020a24`
- `KERNEL32!SetFilePointer` at `0x10020ac7`
- `KERNEL32!SetFilePointer` at `0x10020bd0`

## pseudocode

```c
int __stdcall ComputeBookmarkLastRow(int a1, int a2)
{
  int v2; // eax
  int v3; // ebp
  HANDLE *v4; // esi
  signed int v5; // ecx
  LONG v6; // eax
  int v7; // eax
  BOOL v8; // ebx
  ldiv_t v9; // rax
  DWORD v10; // eax
  int result; // eax
  _DWORD *v12; // ebx
  _WORD *v13; // ebp
  ldiv_t v14; // rax
  DWORD v15; // eax
  int v16; // [esp-8h] [ebp-1030h]
  int v17; // [esp-4h] [ebp-102Ch]
  DWORD nNumberOfBytesToRead; // [esp+10h] [ebp-1018h] BYREF
  DWORD NumberOfBytesRead; // [esp+14h] [ebp-1014h] BYREF
  int v20; // [esp+18h] [ebp-1010h]
  int rem; // [esp+20h] [ebp-1008h]
  char Buffer[4096]; // [esp+24h] [ebp-1004h] BYREF

  v2 = 4;
  v3 = *(_DWORD *)(a1 + 524);
  v4 = (HANDLE *)(a1 + 528);
  v20 = v3;
  v5 = *(_DWORD *)(a1 + 548);
  if ( a2 != 54936 )
    v2 = 2;
  if ( v5 > v2 )
    v5 = v2;
  v6 = *(_DWORD *)(a1 + 548) - v5;
  nNumberOfBytesToRead = v5;
  if ( SetFilePointer(*v4, v6, 0, 0) == -1 )
    return -1022;
  if ( ReadFile(*v4, Buffer, nNumberOfBytesToRead, &NumberOfBytesRead, 0)
    && NumberOfBytesRead == nNumberOfBytesToRead
    && !TextConvertToUnicode(
          a2,
          0,
          Buffer,
          &NumberOfBytesRead,
          (LPWSTR)(a1 + 564),
          (int)&nNumberOfBytesToRead,
          *(_DWORD *)(a1 + 544)) )
  {
    v7 = *((unsigned __int16 *)v4 + nNumberOfBytesToRead + 17);
    v8 = v7 == 10 || v7 == 13;
    v9 = ldiv(*(_DWORD *)(a1 + 548), 4096);
    v9.quot <<= 12;
    rem = v9.rem;
    *(_DWORD *)(a1 + 8848) = v9.quot;
    if ( SetFilePointer(*v4, v9.quot, 0, 0) != -1 )
    {
      while ( ReadFile(
                *(HANDLE *)(a1 + 528),
                Buffer,
                *(_DWORD *)(a1 + 548) - *(_DWORD *)(a1 + 8848),
                &NumberOfBytesRead,
                0)
           && NumberOfBytesRead == *(_DWORD *)(a1 + 548) - *(_DWORD *)(a1 + 8848) )
      {
        v17 = *(_DWORD *)(a1 + 544);
        v10 = 0;
        if ( a2 == 54936 )
          v10 = 4096;
        nNumberOfBytesToRead = v10;
        result = TextConvertToUnicode(
                   a2,
                   0,
                   Buffer,
                   &NumberOfBytesRead,
                   (LPWSTR)(a1 + 564),
                   (int)&nNumberOfBytesToRead,
                   v17);
        if ( result )
          break;
        *(_DWORD *)(a1 + 8852) = nNumberOfBytesToRead;
        if ( v8 )
          return result;
        *(_DWORD *)(a1 + 8764) = 0;
        v12 = (_DWORD *)(v3 + 68);
        v16 = *(_DWORD *)(v3 + 68);
        v13 = (_WORD *)(v3 + 58);
        result = AddToRowBuffer((int)v4, v13, v16, 0);
        if ( result < 0 )
          return result;
        result = PutFileData((DWORD)v4, a2, 0);
        if ( result < 0 )
          return result;
        nNumberOfBytesToRead = 0;
        result = TextConvertFromUnicode(a2, v13, v12, Buffer, (int)&nNumberOfBytesToRead);
        if ( result < 0 )
          return result;
        v8 = 1;
        *(_DWORD *)(a1 + 548) += nNumberOfBytesToRead;
        v14 = ldiv(*(_DWORD *)(a1 + 548), 4096);
        v14.quot <<= 12;
        *(_DWORD *)(a1 + 8848) = v14.quot;
        rem = v14.rem;
        v15 = SetFilePointer(*v4, v14.quot, 0, 0);
        v3 = v20;
        if ( v15 == -1 )
          return -1022;
      }
      return -1;
    }
    return -1022;
  }
  return -1;
}

```

## disassembly

```asm
0x100209c0  mov     eax, 1018h
0x100209c5  call    __chkstk
0x100209ca  mov     eax, ___security_cookie
0x100209cf  xor     eax, esp
0x100209d1  mov     [esp+1018h+var_4], eax
0x100209d8  push    ebx
0x100209d9  push    ebp
0x100209da  push    esi
0x100209db  mov     esi, [esp+1024h+arg_0]
0x100209e2  mov     eax, 4
0x100209e7  push    edi
0x100209e8  mov     edi, [esp+1028h+arg_4]
0x100209ef  mov     ebp, [esi+20Ch]
0x100209f5  add     esi, 210h
0x100209fb  mov     [esp+1028h+var_1010], ebp
0x100209ff  mov     ecx, [esi+14h]
0x10020a02  cmp     edi, 0D698h
0x10020a08  jz      short loc_10020A0F
0x10020a0a  mov     eax, 2
0x10020a0f  cmp     ecx, eax
0x10020a11  push    0; dwMoveMethod
0x10020a13  cmovg   ecx, eax
0x10020a16  mov     eax, [esi+14h]
0x10020a19  push    0; lpDistanceToMoveHigh
0x10020a1b  sub     eax, ecx
0x10020a1d  mov     [esp+1030h+nNumberOfBytesToRead], ecx
0x10020a21  push    eax; lDistanceToMove
0x10020a22  push    dword ptr [esi]; hFile
0x10020a24  call    ds:__imp__SetFilePointer@16; SetFilePointer(x,x,x,x)
0x10020a2a  cmp     eax, 0FFFFFFFFh
0x10020a2d  jz      loc_10020BE3
0x10020a33  push    0; lpOverlapped
0x10020a35  lea     eax, [esp+102Ch+NumberOfBytesRead]
0x10020a39  push    eax; lpNumberOfBytesRead
0x10020a3a  push    [esp+1030h+nNumberOfBytesToRead]; nNumberOfBytesToRead
0x10020a3e  lea     eax, [esp+1034h+Buffer]
0x10020a42  push    eax; lpBuffer
0x10020a43  push    dword ptr [esi]; hFile
0x10020a45  call    ds:__imp__ReadFile@20; ReadFile(x,x,x,x,x)
0x10020a4b  test    eax, eax
0x10020a4d  jz      loc_10020BEA
0x10020a53  mov     eax, [esp+1028h+NumberOfBytesRead]
0x10020a57  cmp     eax, [esp+1028h+nNumberOfBytesToRead]
0x10020a5b  jnz     loc_10020BEA
0x10020a61  push    dword ptr [esi+10h]; int
0x10020a64  lea     ecx, [esp+102Ch+nNumberOfBytesToRead]
0x10020a68  push    ecx; int
0x10020a69  lea     eax, [esi+24h]
0x10020a6c  push    eax; lpWideCharStr
0x10020a6d  lea     eax, [esp+1034h+NumberOfBytesRead]
0x10020a71  push    eax; int
0x10020a72  lea     eax, [esp+1038h+Buffer]
0x10020a76  push    eax; Src
0x10020a77  push    0; int
0x10020a79  push    edi; int
0x10020a7a  call    _TextConvertToUnicode@28; TextConvertToUnicode(x,x,x,x,x,x,x)
0x10020a7f  test    eax, eax
0x10020a81  jnz     loc_10020BEA
0x10020a87  mov     eax, [esp+1028h+nNumberOfBytesToRead]
0x10020a8b  movzx   eax, word ptr [esi+eax*2+22h]
0x10020a90  cmp     eax, 0Ah
0x10020a93  jz      short loc_10020A9E
0x10020a95  cmp     eax, 0Dh
0x10020a98  jz      short loc_10020A9E
0x10020a9a  xor     ebx, ebx
0x10020a9c  jmp     short loc_10020AA3
0x10020a9e  mov     ebx, 1
0x10020aa3  push    1000h; Denominator
0x10020aa8  push    dword ptr [esi+14h]; Numerator
0x10020aab  call    _ldiv
0x10020ab0  add     esp, 8
0x10020ab3  shl     eax, 0Ch
0x10020ab6  mov     [esp+1028h+var_1008], edx
0x10020aba  mov     [esi+2080h], eax
0x10020ac0  push    0; dwMoveMethod
0x10020ac2  push    0; lpDistanceToMoveHigh
0x10020ac4  push    eax; lDistanceToMove
0x10020ac5  push    dword ptr [esi]; hFile
0x10020ac7  call    ds:__imp__SetFilePointer@16; SetFilePointer(x,x,x,x)
0x10020acd  cmp     eax, 0FFFFFFFFh
0x10020ad0  jz      loc_10020BE3
0x10020ad6  push    0; lpOverlapped
0x10020ad8  lea     eax, [esp+102Ch+NumberOfBytesRead]
0x10020adc  push    eax; lpNumberOfBytesRead
0x10020add  mov     eax, [esi+14h]
0x10020ae0  sub     eax, [esi+2080h]
0x10020ae6  push    eax; nNumberOfBytesToRead
0x10020ae7  lea     eax, [esp+1034h+Buffer]
0x10020aeb  push    eax; lpBuffer
0x10020aec  push    dword ptr [esi]; hFile
0x10020aee  call    ds:__imp__ReadFile@20; ReadFile(x,x,x,x,x)
0x10020af4  test    eax, eax
0x10020af6  jz      loc_10020BEA
0x10020afc  mov     eax, [esi+14h]
0x10020aff  sub     eax, [esi+2080h]
0x10020b05  cmp     [esp+1028h+NumberOfBytesRead], eax
0x10020b09  jnz     loc_10020BEA
0x10020b0f  push    dword ptr [esi+10h]; int
0x10020b12  xor     eax, eax
0x10020b14  mov     ecx, 1000h
0x10020b19  cmp     edi, 0D698h
0x10020b1f  cmovz   eax, ecx
0x10020b22  mov     [esp+102Ch+nNumberOfBytesToRead], eax
0x10020b26  lea     eax, [esp+102Ch+nNumberOfBytesToRead]
0x10020b2a  push    eax; int
0x10020b2b  lea     eax, [esi+24h]
0x10020b2e  push    eax; lpWideCharStr
0x10020b2f  lea     eax, [esp+1034h+NumberOfBytesRead]
0x10020b33  push    eax; int
0x10020b34  lea     eax, [esp+1038h+Buffer]
0x10020b38  push    eax; Src
0x10020b39  push    0; int
0x10020b3b  push    edi; int
0x10020b3c  call    _TextConvertToUnicode@28; TextConvertToUnicode(x,x,x,x,x,x,x)
0x10020b41  test    eax, eax
0x10020b43  jnz     loc_10020BEA
0x10020b49  mov     ecx, [esp+1028h+nNumberOfBytesToRead]
0x10020b4d  mov     [esi+2084h], ecx
0x10020b53  test    ebx, ebx
0x10020b55  jnz     loc_10020BED
0x10020b5b  mov     [esi+202Ch], ebx
0x10020b61  lea     ebx, [ebp+44h]
0x10020b64  push    eax; int
0x10020b65  push    dword ptr [ebx]; int
0x10020b67  add     ebp, 3Ah ; ':'
0x10020b6a  push    ebp; Src
0x10020b6b  push    esi; int
0x10020b6c  call    AddToRowBuffer
0x10020b71  test    eax, eax
0x10020b73  js      short loc_10020BED
0x10020b75  push    0; int
0x10020b77  push    edi; int
0x10020b78  push    esi; NumberOfBytesWritten
0x10020b79  call    PutFileData
0x10020b7e  test    eax, eax
0x10020b80  js      short loc_10020BED
0x10020b82  lea     eax, [esp+1028h+nNumberOfBytesToRead]
0x10020b86  mov     [esp+1028h+nNumberOfBytesToRead], 0
0x10020b8e  push    eax; int
0x10020b8f  lea     eax, [esp+102Ch+Buffer]
0x10020b93  push    eax; lpMultiByteStr
0x10020b94  push    ebx; int
0x10020b95  push    ebp; Src
0x10020b96  push    edi; int
0x10020b97  call    _TextConvertFromUnicode@20; TextConvertFromUnicode(x,x,x,x,x)
0x10020b9c  test    eax, eax
0x10020b9e  js      short loc_10020BED
0x10020ba0  mov     eax, [esp+1028h+nNumberOfBytesToRead]
0x10020ba4  mov     ebx, 1
0x10020ba9  add     [esi+14h], eax
0x10020bac  push    1000h; Denominator
0x10020bb1  push    dword ptr [esi+14h]; Numerator
0x10020bb4  call    _ldiv
0x10020bb9  add     esp, 8
0x10020bbc  shl     eax, 0Ch
0x10020bbf  mov     [esi+2080h], eax
0x10020bc5  mov     [esp+1028h+var_1008], edx
0x10020bc9  push    0; dwMoveMethod
0x10020bcb  push    0; lpDistanceToMoveHigh
0x10020bcd  push    eax; lDistanceToMove
0x10020bce  push    dword ptr [esi]; hFile
0x10020bd0  call    ds:__imp__SetFilePointer@16; SetFilePointer(x,x,x,x)
0x10020bd6  mov     ebp, [esp+1028h+var_1010]
0x10020bda  cmp     eax, 0FFFFFFFFh
0x10020bdd  jnz     loc_10020AD6
0x10020be3  mov     eax, 0FFFFFC02h
0x10020be8  jmp     short loc_10020BED
0x10020bea  or      eax, 0FFFFFFFFh
0x10020bed  mov     ecx, [esp+1028h+var_4]
0x10020bf4  pop     edi
0x10020bf5  pop     esi
0x10020bf6  pop     ebp
0x10020bf7  pop     ebx
0x10020bf8  xor     ecx, esp; StackCookie
0x10020bfa  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10020bff  add     esp, 1018h
0x10020c05  retn    8
```
