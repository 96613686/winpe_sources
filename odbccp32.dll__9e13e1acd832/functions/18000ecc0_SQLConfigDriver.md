# SQLConfigDriver

- ea: `0x18000ecc0`
- end: `0x18000edfb`
- name: `SQLConfigDriver`
- size: `315`
- prototype: `BOOL __stdcall(HWND hwndParent, WORD fRequest, LPCSTR lpszDriver, LPCSTR lpszArgs, LPSTR lpszMsg, WORD cchMsgMax, WORD *pcchMsgOut)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180002940`
- `0x180008bf0`
- `0x18000ecc0`
- `0x1800138e4`
- `0x180013c2c`

## import_xrefs

- `msvcrt!calloc` at `0x18000ed62`
- `msvcrt!calloc` at `0x18000ed62`

## pseudocode

```c
BOOL __stdcall SQLConfigDriver(
        HWND hwndParent,
        WORD fRequest,
        LPCSTR lpszDriver,
        LPCSTR lpszArgs,
        LPSTR lpszMsg,
        WORD cchMsgMax,
        WORD *pcchMsgOut)
{
  LPSTR v7; // r15
  WORD *v8; // r14
  WCHAR *v11; // rsi
  WCHAR *v12; // rbx
  BOOL v13; // ebp
  unsigned int v15; // edi
  __int64 v16; // rcx
  __int16 v18; // [rsp+40h] [rbp-68h] BYREF
  LPCWSTR lpszArgsa; // [rsp+48h] [rbp-60h] BYREF
  LPCWSTR lpszDrivera; // [rsp+50h] [rbp-58h] BYREF

  v7 = lpszMsg;
  v8 = (WORD *)&v18;
  lpszDrivera = 0;
  lpszArgsa = 0;
  v18 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  if ( pcchMsgOut )
    v8 = pcchMsgOut;
  if ( (unsigned int)GWConvertToUnicode(lpszDriver, (WCHAR **)&lpszDrivera, 0xFFFFFFFD) )
  {
    if ( !(unsigned int)GWConvertToUnicode(lpszArgs, (WCHAR **)&lpszArgsa, 0xFFFFFFFD)
      || (v15 = cchMsgMax) != 0 && v7 && (*v7 = 0, (v12 = (WCHAR *)calloc(2LL * v15, 1u)) == 0) )
    {
      v11 = (WCHAR *)lpszArgsa;
    }
    else
    {
      v11 = (WCHAR *)lpszArgsa;
      v13 = SQLConfigDriverW(hwndParent, fRequest, lpszDrivera, lpszArgsa, v12, v15, v8);
      if ( v13 && v12 && *v8 )
        LConvertToAnsiWordLengths(v16, v12, *v8, &lpszMsg, v15, v8);
    }
  }
  OFree((void *)lpszDrivera);
  OFree(v11);
  OFree(v12);
  return v13;
}

```

## disassembly

```asm
0x18000ecc0  mov     rax, rsp
0x18000ecc3  push    rbx
0x18000ecc4  push    rbp
0x18000ecc5  push    rsi
0x18000ecc6  push    rdi
0x18000ecc7  push    r12
0x18000ecc9  push    r13
0x18000eccb  push    r14
0x18000eccd  push    r15
0x18000eccf  sub     rsp, 68h
0x18000ecd3  mov     r15, [rsp+0A8h+lpszMsg]
0x18000ecdb  lea     r14, [rax-68h]
0x18000ecdf  mov     r13, rcx
0x18000ece2  mov     [rax+28h], r15
0x18000ece6  xor     ecx, ecx
0x18000ece8  mov     r10, r8
0x18000eceb  mov     [rax-58h], rcx
0x18000ecef  movzx   r12d, dx
0x18000ecf3  mov     [rax-60h], rcx
0x18000ecf7  lea     rdx, [rsp+0A8h+lpszDriver]
0x18000ecfc  mov     [rax-68h], cx
0x18000ed00  mov     esi, ecx
0x18000ed02  mov     rax, [rsp+0A8h+pcchMsgOut]
0x18000ed0a  lea     r8d, [rcx-3]
0x18000ed0e  test    rax, rax
0x18000ed11  mov     ebx, ecx
0x18000ed13  mov     ebp, ecx
0x18000ed15  mov     rdi, r9
0x18000ed18  mov     rcx, r10; lpMultiByteStr
0x18000ed1b  cmovnz  r14, rax
0x18000ed1f  call    GWConvertToUnicode
0x18000ed24  test    eax, eax
0x18000ed26  jz      loc_18000EDCE
0x18000ed2c  lea     r8d, [rbx-3]
0x18000ed30  mov     rcx, rdi; lpMultiByteStr
0x18000ed33  lea     rdx, [rsp+0A8h+lpszArgs]
0x18000ed38  call    GWConvertToUnicode
0x18000ed3d  test    eax, eax
0x18000ed3f  jz      loc_18000EDC9
0x18000ed45  movzx   edi, [rsp+0A8h+cchMsgMax]
0x18000ed4d  test    di, di
0x18000ed50  jz      short loc_18000ED70
0x18000ed52  test    r15, r15
0x18000ed55  jz      short loc_18000ED70
0x18000ed57  mov     ecx, edi
0x18000ed59  mov     [r15], sil
0x18000ed5c  add     rcx, rcx; Count
0x18000ed5f  lea     edx, [rbx+1]; Size
0x18000ed62  call    cs:__imp_calloc
0x18000ed68  mov     rbx, rax
0x18000ed6b  test    rax, rax
0x18000ed6e  jz      short loc_18000EDC9
0x18000ed70  mov     rsi, [rsp+0A8h+lpszArgs]
0x18000ed75  movzx   edx, r12w; fRequest
0x18000ed79  mov     r8, [rsp+0A8h+lpszDriver]; lpszDriver
0x18000ed7e  mov     r9, rsi; lpszArgs
0x18000ed81  mov     [rsp+0A8h+var_78], r14; pcchMsgOut
0x18000ed86  mov     rcx, r13; hwndParent
0x18000ed89  mov     [rsp+0A8h+var_80], di; cchMsgMax
0x18000ed8e  mov     [rsp+0A8h+var_88], rbx; lpszMsg
0x18000ed93  call    SQLConfigDriverW
0x18000ed98  mov     ebp, eax
0x18000ed9a  test    eax, eax
0x18000ed9c  jz      short loc_18000EDCE
0x18000ed9e  test    rbx, rbx
0x18000eda1  jz      short loc_18000EDCE
0x18000eda3  movzx   r8d, word ptr [r14]
0x18000eda7  test    r8w, r8w
0x18000edab  jz      short loc_18000EDCE
0x18000edad  mov     qword ptr [rsp+0A8h+var_80], r14
0x18000edb2  lea     r9, [rsp+0A8h+lpszMsg]
0x18000edba  mov     rdx, rbx
0x18000edbd  mov     word ptr [rsp+0A8h+var_88], di
0x18000edc2  call    LConvertToAnsiWordLengths
0x18000edc7  jmp     short loc_18000EDCE
0x18000edc9  mov     rsi, [rsp+0A8h+lpszArgs]
0x18000edce  mov     rcx, [rsp+0A8h+lpszDriver]
0x18000edd3  call    OFree
0x18000edd8  mov     rcx, rsi
0x18000eddb  call    OFree
0x18000ede0  mov     rcx, rbx
0x18000ede3  call    OFree
0x18000ede8  mov     eax, ebp
0x18000edea  add     rsp, 68h
0x18000edee  pop     r15
0x18000edf0  pop     r14
0x18000edf2  pop     r13
0x18000edf4  pop     r12
0x18000edf6  pop     rdi
0x18000edf7  pop     rsi
0x18000edf8  pop     rbp
0x18000edf9  pop     rbx
0x18000edfa  retn
```
