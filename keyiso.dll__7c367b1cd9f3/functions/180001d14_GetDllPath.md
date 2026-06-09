# GetDllPath

- ea: `0x180001d14`
- end: `0x180001e01`
- name: `GetDllPath`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001c14`

## callees

- `0x180001aec`
- `0x180001d14`
- `0x18000204c`
- `0x180003cf0`
- `0x180004470`
- `0x180006280`

## string_xrefs

- `0x180001d6a`: `onecore\ds\security\cryptoapi\ncrypt\common\biopinhelper.c`
- `0x180001dab`: `onecore\ds\security\cryptoapi\ncrypt\common\biopinhelper.c`

## pseudocode

```c
__int64 __fastcall GetDllPath(__int64 a1, __int64 a2, _QWORD *a3)
{
  WCHAR *v4; // rdi
  int v5; // edx
  unsigned int ImagePathInReg; // ebx
  unsigned int FullPath; // eax
  WCHAR *v9; // [rsp+50h] [rbp+8h] BYREF
  LPCWSTR lpSrc; // [rsp+58h] [rbp+10h] BYREF

  lpSrc = 0;
  v4 = 0;
  v9 = 0;
  ImagePathInReg = GetImagePathInReg(a1, a2, (BYTE **)&lpSrc);
  if ( ImagePathInReg )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v5,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\biopinhelper.c",
        (unsigned int)"Status",
        ImagePathInReg,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\biopinhelper.c",
        177);
  }
  else
  {
    FullPath = GetFullPath(lpSrc, &v9);
    ImagePathInReg = FullPath;
    if ( FullPath )
    {
      DebugTraceError(FullPath, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\biopinhelper.c", 186);
      v4 = v9;
    }
    else
    {
      *a3 = v9;
    }
  }
  if ( lpSrc )
    MSCryptFree(lpSrc);
  if ( v4 )
    MSCryptFree(v4);
  return ImagePathInReg;
}

```

## disassembly

```asm
0x180001d14  mov     rax, rsp
0x180001d17  mov     [rax+18h], rbx
0x180001d1b  mov     [rax+20h], rdi
0x180001d1f  mov     [rax+10h], rdx
0x180001d23  mov     [rax+8], rcx
0x180001d27  push    r14
0x180001d29  sub     rsp, 40h
0x180001d2d  mov     r14, r8
0x180001d30  mov     qword ptr [rax+10h], 0
0x180001d38  xor     edi, edi
0x180001d3a  lea     r8, [rax+10h]
0x180001d3e  mov     [rax+8], rdi
0x180001d42  call    GetImagePathInReg
0x180001d47  mov     ebx, eax
0x180001d49  test    eax, eax
0x180001d4b  jz      short loc_180001D90
0x180001d4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180001d54  lea     rax, WPP_GLOBAL_Control
0x180001d5b  cmp     rcx, rax
0x180001d5e  jz      short loc_180001DCF
0x180001d60  test    byte ptr [rcx+1Ch], 1
0x180001d64  jz      short loc_180001DCF
0x180001d66  mov     rcx, [rcx+10h]
0x180001d6a  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001d71  mov     [rsp+48h+var_18], 0B1h
0x180001d79  lea     r9, aStatus; "Status"
0x180001d80  mov     [rsp+48h+var_20], r8
0x180001d85  mov     [rsp+48h+var_28], ebx
0x180001d89  call    WPP_SF_sDsd
0x180001d8e  jmp     short loc_180001DCF
0x180001d90  mov     rcx, [rsp+48h+lpSrc]; lpSrc
0x180001d95  lea     rdx, [rsp+48h+arg_0]
0x180001d9a  call    GetFullPath
0x180001d9f  mov     ebx, eax
0x180001da1  test    eax, eax
0x180001da3  jz      short loc_180001DC7
0x180001da5  mov     r9d, 0BAh
0x180001dab  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001db2  lea     rdx, aStatus; "Status"
0x180001db9  mov     ecx, eax
0x180001dbb  call    DebugTraceError
0x180001dc0  mov     rdi, [rsp+48h+arg_0]
0x180001dc5  jmp     short loc_180001DCF
0x180001dc7  mov     rax, [rsp+48h+arg_0]
0x180001dcc  mov     [r14], rax
0x180001dcf  cmp     [rsp+48h+lpSrc], 0
0x180001dd5  jz      short loc_180001DE1
0x180001dd7  mov     rcx, [rsp+48h+lpSrc]
0x180001ddc  call    MSCryptFree
0x180001de1  test    rdi, rdi
0x180001de4  jz      short loc_180001DEE
0x180001de6  mov     rcx, rdi
0x180001de9  call    MSCryptFree
0x180001dee  mov     rdi, [rsp+48h+arg_18]
0x180001df3  mov     eax, ebx
0x180001df5  mov     rbx, [rsp+48h+arg_10]
0x180001dfa  add     rsp, 40h
0x180001dfe  pop     r14
0x180001e00  retn
```
