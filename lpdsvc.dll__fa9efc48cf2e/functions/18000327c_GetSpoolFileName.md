# GetSpoolFileName

- ea: `0x18000327c`
- end: `0x180003478`
- name: `GetSpoolFileName`
- size: `508`
- prototype: `__int64 __fastcall(HANDLE hPrinter, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003480`

## callees

- `0x180002e7c`
- `0x180002ea4`
- `0x18000327c`
- `0x180003cf0`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1800032dc`
- `KERNEL32!LocalAlloc` at `0x180003374`
- `KERNEL32!LocalAlloc` at `0x1800032dc`
- `KERNEL32!LocalAlloc` at `0x180003374`
- `KERNEL32!GetLastError` at `0x180003355`
- `KERNEL32!GetLastError` at `0x18000341e`
- `KERNEL32!GetLastError` at `0x180003355`
- `KERNEL32!GetLastError` at `0x18000341e`
- `KERNEL32!GetTempFileNameA` at `0x1800033fe`
- `KERNEL32!GetTempFileNameA` at `0x1800033fe`
- `KERNEL32!LocalFree` at `0x180003365`
- `KERNEL32!LocalFree` at `0x1800033ad`
- `KERNEL32!LocalFree` at `0x1800033b6`
- `KERNEL32!LocalFree` at `0x18000343f`
- `KERNEL32!LocalFree` at `0x180003365`
- `KERNEL32!LocalFree` at `0x1800033ad`
- `KERNEL32!LocalFree` at `0x1800033b6`
- `KERNEL32!LocalFree` at `0x18000343f`
- `WINSPOOL!GetPrinterDataA` at `0x18000333d`
- `WINSPOOL!GetPrinterDataA` at `0x18000333d`

## string_xrefs

- `0x18000332c`: `DefaultSpoolDirectory`

## pseudocode

```c
__int64 __fastcall GetSpoolFileName(HANDLE hPrinter, __int64 a2, _QWORD *a3)
{
  HLOCAL v5; // rsi
  SIZE_T nSize; // rbx
  BYTE *v7; // rdi
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v11; // rbx
  DWORD LastError; // eax
  DWORD pcbNeeded; // [rsp+68h] [rbp+10h] BYREF
  int v14; // [rsp+6Ch] [rbp+14h]

  v14 = HIDWORD(a2);
  pcbNeeded = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_bc5dfa190b42335729027cd8699dae89_Traceguids);
  v5 = LocalAlloc(0, 0x209u);
  if ( v5 )
  {
    for ( nSize = 522; ; nSize = pcbNeeded )
    {
      v7 = (BYTE *)LocalAlloc(0, nSize);
      if ( !v7 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            v9 = 41;
            goto LABEL_17;
          }
          goto LABEL_18;
        }
        goto LABEL_20;
      }
      if ( !GetPrinterDataA(hPrinter, (LPSTR)"DefaultSpoolDirectory", 0, v7, nSize, &pcbNeeded) )
        break;
      if ( pcbNeeded < (unsigned int)nSize || GetLastError() != 234 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v9 = 42;
LABEL_17:
          WPP_SF_(v8[2], v9, &WPP_bc5dfa190b42335729027cd8699dae89_Traceguids);
        }
LABEL_18:
        if ( v7 )
          LocalFree(v7);
LABEL_20:
        LocalFree(v5);
        return 0;
      }
      LocalFree(v7);
    }
    if ( !GetTempFileNameA((LPCSTR)v7, "LprSpl", 0, (LPSTR)v5) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v11 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        LastError = GetLastError();
        WPP_SF_d(v11, 43, &WPP_bc5dfa190b42335729027cd8699dae89_Traceguids, LastError);
      }
      goto LABEL_18;
    }
    LocalFree(v7);
    *a3 = v5;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_bc5dfa190b42335729027cd8699dae89_Traceguids, v5);
    return 1;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_bc5dfa190b42335729027cd8699dae89_Traceguids);
    return 0;
  }
}

```

## disassembly

```asm
0x18000327c  mov     rax, rsp
0x18000327f  mov     [rax+8], rbx
0x180003283  mov     [rax+18h], rbp
0x180003287  mov     [rax+10h], rdx
0x18000328b  push    rsi
0x18000328c  push    rdi
0x18000328d  push    r12
0x18000328f  push    r14
0x180003291  push    r15
0x180003293  sub     rsp, 30h
0x180003297  mov     r14, r8
0x18000329a  mov     dword ptr [rax+10h], 0
0x1800032a1  mov     rbp, rcx
0x1800032a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800032ab  lea     r15, WPP_GLOBAL_Control
0x1800032b2  lea     r12, WPP_bc5dfa190b42335729027cd8699dae89_Traceguids
0x1800032b9  cmp     rcx, r15
0x1800032bc  jz      short loc_1800032D5
0x1800032be  test    byte ptr [rcx+1Ch], 1
0x1800032c2  jz      short loc_1800032D5
0x1800032c4  mov     rcx, [rcx+10h]
0x1800032c8  mov     edx, 27h ; '''
0x1800032cd  mov     r8, r12
0x1800032d0  call    WPP_SF_
0x1800032d5  mov     edx, 209h; uBytes
0x1800032da  xor     ecx, ecx; uFlags
0x1800032dc  call    cs:__imp_LocalAlloc
0x1800032e2  mov     rsi, rax
0x1800032e5  test    rax, rax
0x1800032e8  jnz     short loc_180003318
0x1800032ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800032f1  cmp     rcx, r15
0x1800032f4  jz      loc_1800033BC
0x1800032fa  test    byte ptr [rcx+1Ch], 8
0x1800032fe  jz      loc_1800033BC
0x180003304  mov     rcx, [rcx+10h]
0x180003308  lea     edx, [rax+28h]
0x18000330b  mov     r8, r12
0x18000330e  call    WPP_SF_
0x180003313  jmp     loc_1800033BC
0x180003318  mov     ebx, 20Ah
0x18000331d  jmp     short loc_18000336F
0x18000331f  lea     rax, [rsp+58h+arg_8]
0x180003324  mov     r9, rdi; pData
0x180003327  mov     [rsp+58h+pcbNeeded], rax; pcbNeeded
0x18000332c  lea     rdx, pValueName; "DefaultSpoolDirectory"
0x180003333  xor     r8d, r8d; pType
0x180003336  mov     [rsp+58h+nSize], ebx; nSize
0x18000333a  mov     rcx, rbp; hPrinter
0x18000333d  call    cs:__imp_GetPrinterDataA
0x180003343  test    eax, eax
0x180003345  jz      loc_1800033EE
0x18000334b  cmp     [rsp+58h+arg_8], ebx
0x18000334f  jb      loc_1800033D5
0x180003355  call    cs:__imp_GetLastError
0x18000335b  cmp     eax, 0EAh
0x180003360  jnz     short loc_1800033D5
0x180003362  mov     rcx, rdi; hMem
0x180003365  call    cs:__imp_LocalFree
0x18000336b  mov     ebx, [rsp+58h+arg_8]
0x18000336f  mov     rdx, rbx; uBytes
0x180003372  xor     ecx, ecx; uFlags
0x180003374  call    cs:__imp_LocalAlloc
0x18000337a  mov     rdi, rax
0x18000337d  test    rax, rax
0x180003380  jnz     short loc_18000331F
0x180003382  mov     rcx, cs:WPP_GLOBAL_Control
0x180003389  cmp     rcx, r15
0x18000338c  jz      short loc_1800033B3
0x18000338e  test    byte ptr [rcx+1Ch], 8
0x180003392  jz      short loc_1800033A5
0x180003394  mov     edx, 29h ; ')'
0x180003399  mov     rcx, [rcx+10h]
0x18000339d  mov     r8, r12
0x1800033a0  call    WPP_SF_
0x1800033a5  test    rdi, rdi
0x1800033a8  jz      short loc_1800033B3
0x1800033aa  mov     rcx, rdi; hMem
0x1800033ad  call    cs:__imp_LocalFree
0x1800033b3  mov     rcx, rsi; hMem
0x1800033b6  call    cs:__imp_LocalFree
0x1800033bc  xor     eax, eax
0x1800033be  mov     rbx, [rsp+58h+arg_0]
0x1800033c3  mov     rbp, [rsp+58h+arg_10]
0x1800033c8  add     rsp, 30h
0x1800033cc  pop     r15
0x1800033ce  pop     r14
0x1800033d0  pop     r12
0x1800033d2  pop     rdi
0x1800033d3  pop     rsi
0x1800033d4  retn
0x1800033d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033dc  cmp     rcx, r15
0x1800033df  jz      short loc_1800033A5
0x1800033e1  test    byte ptr [rcx+1Ch], 8
0x1800033e5  jz      short loc_1800033A5
0x1800033e7  mov     edx, 2Ah ; '*'
0x1800033ec  jmp     short loc_180003399
0x1800033ee  mov     r9, rsi; lpTempFileName
0x1800033f1  lea     rdx, PrefixString; "LprSpl"
0x1800033f8  xor     r8d, r8d; uUnique
0x1800033fb  mov     rcx, rdi; lpPathName
0x1800033fe  call    cs:__imp_GetTempFileNameA
0x180003404  test    eax, eax
0x180003406  jnz     short loc_18000343C
0x180003408  mov     rbx, cs:WPP_GLOBAL_Control
0x18000340f  cmp     rbx, r15
0x180003412  jz      short loc_1800033A5
0x180003414  test    byte ptr [rbx+1Ch], 8
0x180003418  jz      short loc_1800033A5
0x18000341a  mov     rbx, [rbx+10h]
0x18000341e  call    cs:__imp_GetLastError
0x180003424  mov     edx, 2Bh ; '+'
0x180003429  mov     r8, r12
0x18000342c  mov     r9d, eax
0x18000342f  mov     rcx, rbx
0x180003432  call    WPP_SF_d
0x180003437  jmp     loc_1800033A5
0x18000343c  mov     rcx, rdi; hMem
0x18000343f  call    cs:__imp_LocalFree
0x180003445  mov     [r14], rsi
0x180003448  mov     rcx, cs:WPP_GLOBAL_Control
0x18000344f  cmp     rcx, r15
0x180003452  jz      short loc_18000346E
0x180003454  test    byte ptr [rcx+1Ch], 2
0x180003458  jz      short loc_18000346E
0x18000345a  mov     rcx, [rcx+10h]
0x18000345e  mov     edx, 2Ch ; ','
0x180003463  mov     r9, rsi
0x180003466  mov     r8, r12
0x180003469  call    WPP_SF_s
0x18000346e  mov     eax, 1
0x180003473  jmp     loc_1800033BE
```
