# SSI_INCLUDE_FILE::DoEchoDateGMT(void)

- ea: `0x180003d8c`
- end: `0x180003e93`
- name: `?DoEchoDateGMT@SSI_INCLUDE_FILE@@AEAAJXZ`
- size: `263`
- prototype: `__int64 __fastcall(SSI_INCLUDE_FILE *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180004afc`

## callees

- `0x180003a34`
- `0x180003d8c`
- `0x180005780`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180003e56`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180003e56`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180003e38`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180003e38`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180003dfd`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180003e18`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180003dfd`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180003e18`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003e73`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003e73`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180003dc3`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180003dc3`

## pseudocode

```c
__int64 __fastcall SSI_INCLUDE_FILE::DoEchoDateGMT(SSI_INCLUDE_FILE *this)
{
  __int64 v2; // rbx
  int v3; // edi
  __int64 v4; // rax
  int v6; // [rsp+20h] [rbp-39h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+28h] [rbp-31h] BYREF
  const char *v8[7]; // [rsp+38h] [rbp-21h] BYREF
  char v9[24]; // [rsp+70h] [rbp+17h] BYREF

  SystemTime = 0;
  STRA::STRA((STRA *)v8, v9, 0x15u);
  v2 = *((_QWORD *)this + 92);
  v6 = 5524807;
  while ( *(_BYTE *)v2 )
  {
    if ( *(_BYTE *)v2 == 37 )
    {
      if ( ((*(_BYTE *)(v2 + 1) - 90) & 0xDF) == 0 )
      {
        v3 = STRA::Append((STRA *)v8, (const char *)&v6);
        if ( v3 < 0 )
          goto LABEL_15;
        v4 = 2;
        goto LABEL_12;
      }
      if ( *(_BYTE *)(v2 + 1) == 35 && ((*(_BYTE *)(v2 + 2) - 90) & 0xDF) == 0 )
      {
        v3 = STRA::Append((STRA *)v8, (const char *)&v6);
        if ( v3 < 0 )
          goto LABEL_15;
        v4 = 3;
        goto LABEL_12;
      }
    }
    v3 = STRA::Append((STRA *)v8, (const char *)v2, 1u);
    if ( v3 < 0 )
      goto LABEL_15;
    v4 = 1;
LABEL_12:
    v2 += v4;
  }
  GetSystemTime(&SystemTime);
  v3 = SSI_REQUEST::SendDate(*((SSI_REQUEST **)this + 2), &SystemTime, v8);
LABEL_15:
  STRA::~STRA((STRA *)v8);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180003d8c  push    rbp
0x180003d8e  push    rbx
0x180003d8f  push    rsi
0x180003d90  push    rdi
0x180003d91  lea     rbp, [rsp-3Fh]
0x180003d96  sub     rsp, 98h
0x180003d9d  mov     rax, cs:__security_cookie
0x180003da4  xor     rax, rsp
0x180003da7  mov     [rbp+57h+var_28], rax
0x180003dab  mov     rsi, rcx
0x180003dae  lea     rdx, [rbp+57h+var_40]
0x180003db2  xorps   xmm0, xmm0
0x180003db5  lea     rcx, [rbp+57h+var_78]
0x180003db9  mov     r8d, 15h
0x180003dbf  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180003dc3  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180003dc9  mov     rbx, [rsi+2E0h]
0x180003dd0  mov     [rbp+57h+var_90], 544D47h
0x180003dd7  jmp     short loc_180003E4C
0x180003dd9  cmp     al, 25h ; '%'
0x180003ddb  jnz     short loc_180003E2B
0x180003ddd  mov     al, [rbx+1]
0x180003de0  sub     al, 5Ah ; 'Z'
0x180003de2  test    al, 0DFh
0x180003de4  jz      short loc_180003E10
0x180003de6  cmp     byte ptr [rbx+1], 23h ; '#'
0x180003dea  jnz     short loc_180003E2B
0x180003dec  mov     al, [rbx+2]
0x180003def  sub     al, 5Ah ; 'Z'
0x180003df1  test    al, 0DFh
0x180003df3  jnz     short loc_180003E2B
0x180003df5  lea     rdx, [rbp+57h+var_90]
0x180003df9  lea     rcx, [rbp+57h+var_78]
0x180003dfd  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180003e03  mov     edi, eax
0x180003e05  test    eax, eax
0x180003e07  js      short loc_180003E6F
0x180003e09  mov     eax, 3
0x180003e0e  jmp     short loc_180003E49
0x180003e10  lea     rdx, [rbp+57h+var_90]
0x180003e14  lea     rcx, [rbp+57h+var_78]
0x180003e18  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180003e1e  mov     edi, eax
0x180003e20  test    eax, eax
0x180003e22  js      short loc_180003E6F
0x180003e24  mov     eax, 2
0x180003e29  jmp     short loc_180003E49
0x180003e2b  mov     r8d, 1
0x180003e31  lea     rcx, [rbp+57h+var_78]
0x180003e35  mov     rdx, rbx
0x180003e38  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180003e3e  mov     edi, eax
0x180003e40  test    eax, eax
0x180003e42  js      short loc_180003E6F
0x180003e44  mov     eax, 1
0x180003e49  add     rbx, rax
0x180003e4c  mov     al, [rbx]
0x180003e4e  test    al, al
0x180003e50  jnz     short loc_180003DD9
0x180003e52  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180003e56  call    cs:__imp_GetSystemTime
0x180003e5c  mov     rcx, [rsi+10h]; this
0x180003e60  lea     r8, [rbp+57h+var_78]; struct STRA *
0x180003e64  lea     rdx, [rbp+57h+SystemTime]; struct _SYSTEMTIME *
0x180003e68  call    ?SendDate@SSI_REQUEST@@QEAAJPEAU_SYSTEMTIME@@PEAVSTRA@@@Z; SSI_REQUEST::SendDate(_SYSTEMTIME *,STRA *)
0x180003e6d  mov     edi, eax
0x180003e6f  lea     rcx, [rbp+57h+var_78]
0x180003e73  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180003e79  mov     eax, edi
0x180003e7b  mov     rcx, [rbp+57h+var_28]
0x180003e7f  xor     rcx, rsp; StackCookie
0x180003e82  call    __security_check_cookie
0x180003e87  add     rsp, 98h
0x180003e8e  pop     rdi
0x180003e8f  pop     rsi
0x180003e90  pop     rbx
0x180003e91  pop     rbp
0x180003e92  retn
```
