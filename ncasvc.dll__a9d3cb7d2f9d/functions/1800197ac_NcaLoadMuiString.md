# NcaLoadMuiString

- ea: `0x1800197ac`
- end: `0x180019904`
- name: `NcaLoadMuiString`
- size: `344`
- prototype: `__int64 __fastcall(UINT uID, WCHAR **)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180005770`
- `0x180009b6c`
- `0x180012214`
- `0x18001990c`

## callees

- `0x180003770`
- `0x180004f04`
- `0x180004f34`
- `0x1800197ac`
- `0x18001abd4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019871`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019871`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001982b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001982b`

## pseudocode

```c
__int64 __fastcall NcaLoadMuiString(UINT uID, WCHAR **a2)
{
  WCHAR *v4; // rdi
  unsigned int v5; // ebx
  WCHAR *v6; // rax
  int StringW; // eax
  DWORD LastError; // eax
  PVOID *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_99360b57fc053e6d111dc188653e9d6e_Traceguids);
  v4 = 0;
  v5 = 64;
  while ( 1 )
  {
    NcaFree(v4);
    v5 *= 2;
    if ( v5 > 0x2000 )
      return 534;
    v6 = (WCHAR *)NcaAlloc(2LL * v5);
    v4 = v6;
    if ( !v6 )
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v10 = 11;
          v11 = 14;
LABEL_18:
          WPP_SF_d(v9[2], v10, WPP_99360b57fc053e6d111dc188653e9d6e_Traceguids, v11);
          v9 = (PVOID *)WPP_GLOBAL_Control;
        }
LABEL_19:
        if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 )
          WPP_SF_(v9[2], 14, WPP_99360b57fc053e6d111dc188653e9d6e_Traceguids);
      }
LABEL_22:
      *a2 = L"Unable to load string message";
      return 0;
    }
    StringW = LoadStringW(gNcaThisModuleHandle, uID, v6, v5);
    if ( !StringW )
    {
      LastError = GetLastError();
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v10 = 12;
          v11 = LastError;
          goto LABEL_18;
        }
        goto LABEL_19;
      }
      goto LABEL_22;
    }
    if ( StringW + 1 != v5 )
    {
      *a2 = v4;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_99360b57fc053e6d111dc188653e9d6e_Traceguids);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x1800197ac  push    rbx
0x1800197ae  push    rbp
0x1800197af  push    rsi
0x1800197b0  push    rdi
0x1800197b1  push    r14
0x1800197b3  push    r15
0x1800197b5  sub     rsp, 28h
0x1800197b9  mov     rsi, rdx
0x1800197bc  mov     ebp, ecx
0x1800197be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800197c5  lea     r14, WPP_GLOBAL_Control
0x1800197cc  lea     r15, WPP_99360b57fc053e6d111dc188653e9d6e_Traceguids
0x1800197d3  cmp     rcx, r14
0x1800197d6  jz      short loc_1800197EF
0x1800197d8  test    byte ptr [rcx+1Ch], 8
0x1800197dc  jz      short loc_1800197EF
0x1800197de  mov     rcx, [rcx+10h]
0x1800197e2  mov     edx, 0Ah
0x1800197e7  mov     r8, r15
0x1800197ea  call    WPP_SF_
0x1800197ef  xor     edi, edi
0x1800197f1  lea     ebx, [rdi+40h]
0x1800197f4  mov     rcx, rdi; lpMem
0x1800197f7  call    NcaFree
0x1800197fc  add     ebx, ebx
0x1800197fe  cmp     ebx, 2000h
0x180019804  ja      loc_1800198F1
0x18001980a  mov     ecx, ebx
0x18001980c  add     rcx, rcx
0x18001980f  call    NcaAlloc
0x180019814  mov     rdi, rax
0x180019817  test    rax, rax
0x18001981a  jz      short loc_180019899
0x18001981c  mov     rcx, cs:gNcaThisModuleHandle; hInstance
0x180019823  mov     r9d, ebx; cchBufferMax
0x180019826  mov     r8, rax; lpBuffer
0x180019829  mov     edx, ebp; uID
0x18001982b  call    cs:__imp_LoadStringW
0x180019832  nop     dword ptr [rax+rax+00h]
0x180019837  test    eax, eax
0x180019839  jz      short loc_180019871
0x18001983b  inc     eax
0x18001983d  cmp     eax, ebx
0x18001983f  jz      short loc_1800197F4
0x180019841  mov     [rsi], rdi
0x180019844  mov     rcx, cs:WPP_GLOBAL_Control
0x18001984b  cmp     rcx, r14
0x18001984e  jz      loc_1800198ED
0x180019854  test    byte ptr [rcx+1Ch], 8
0x180019858  jz      loc_1800198ED
0x18001985e  mov     rcx, [rcx+10h]
0x180019862  mov     edx, 0Dh
0x180019867  mov     r8, r15
0x18001986a  call    WPP_SF_
0x18001986f  jmp     short loc_1800198ED
0x180019871  call    cs:__imp_GetLastError
0x180019878  nop     dword ptr [rax+rax+00h]
0x18001987d  mov     rcx, cs:WPP_GLOBAL_Control
0x180019884  cmp     rcx, r14
0x180019887  jz      short loc_1800198E3
0x180019889  test    byte ptr [rcx+1Ch], 1
0x18001988d  jz      short loc_1800198C7
0x18001988f  mov     edx, 0Ch
0x180019894  mov     r9d, eax
0x180019897  jmp     short loc_1800198B4
0x180019899  mov     rcx, cs:WPP_GLOBAL_Control
0x1800198a0  cmp     rcx, r14
0x1800198a3  jz      short loc_1800198E3
0x1800198a5  test    byte ptr [rcx+1Ch], 1
0x1800198a9  jz      short loc_1800198C7
0x1800198ab  mov     edx, 0Bh
0x1800198b0  lea     r9d, [rdx+3]
0x1800198b4  mov     rcx, [rcx+10h]
0x1800198b8  mov     r8, r15
0x1800198bb  call    WPP_SF_d
0x1800198c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800198c7  cmp     rcx, r14
0x1800198ca  jz      short loc_1800198E3
0x1800198cc  test    byte ptr [rcx+1Ch], 8
0x1800198d0  jz      short loc_1800198E3
0x1800198d2  mov     rcx, [rcx+10h]
0x1800198d6  mov     edx, 0Eh
0x1800198db  mov     r8, r15
0x1800198de  call    WPP_SF_
0x1800198e3  lea     rax, aUnableToLoadSt; "Unable to load string message"
0x1800198ea  mov     [rsi], rax
0x1800198ed  xor     eax, eax
0x1800198ef  jmp     short loc_1800198F6
0x1800198f1  mov     eax, 216h
0x1800198f6  add     rsp, 28h
0x1800198fa  pop     r15
0x1800198fc  pop     r14
0x1800198fe  pop     rdi
0x1800198ff  pop     rsi
0x180019900  pop     rbp
0x180019901  pop     rbx
0x180019902  retn
```
