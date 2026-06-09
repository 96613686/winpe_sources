# ODBC_PARAMETER::CopyValue(ushort const *)

- ea: `0x18000daa0`
- end: `0x18000dbba`
- name: `?CopyValue@ODBC_PARAMETER@@QEAAHPEBG@Z`
- size: `282`
- prototype: `__int64 __fastcall(void **this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000daa0`
- `0x18000ec56`

## import_xrefs

- `IisRTL!PuDbgPrint` at `0x18000db59`
- `IisRTL!PuDbgPrint` at `0x18000db59`
- `KERNEL32!SetLastError` at `0x18000db92`
- `KERNEL32!SetLastError` at `0x18000db92`
- `KERNEL32!WideCharToMultiByte` at `0x18000db15`
- `KERNEL32!WideCharToMultiByte` at `0x18000db15`
- `KERNEL32!GetLastError` at `0x18000db28`
- `KERNEL32!GetLastError` at `0x18000db28`
- `KERNEL32!LocalFree` at `0x18000dba3`
- `KERNEL32!LocalFree` at `0x18000dba3`
- `KERNEL32!LocalAlloc` at `0x18000dae2`
- `KERNEL32!LocalAlloc` at `0x18000dae2`

## string_xrefs

- `0x18000db40`: `inetsrv\iis\svcs\infocomm\log\plugin\odbcconn.cxx`

## pseudocode

```c
__int64 __fastcall ODBC_PARAMETER::CopyValue(void **this, const unsigned __int16 *a2)
{
  unsigned int v4; // esi
  __int64 v5; // rdi
  __int64 v6; // rax
  unsigned int cbMultiByte; // r15d
  CHAR *lpMultiByteStr; // rax
  CHAR *v9; // rbx
  int v10; // eax
  DWORD LastError; // eax
  int v12; // eax
  __int64 v13; // rdi

  v4 = 0;
  if ( a2 )
  {
    v5 = -1;
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
    cbMultiByte = 2 * v6 + 2;
    lpMultiByteStr = (CHAR *)LocalAlloc(0, cbMultiByte);
    v9 = lpMultiByteStr;
    if ( lpMultiByteStr )
    {
      v10 = WideCharToMultiByte(0, 0x200u, a2, -1, lpMultiByteStr, cbMultiByte, 0, 0);
      if ( v10 )
      {
        v9[v10 - 1] = 0;
        do
          ++v5;
        while ( v9[v5] );
        v12 = v5 + 1;
        v13 = v12;
        if ( v12 > (__int64)this[3] )
          SetLastError(0x7Au);
        else
          memcpy_0(this[2], v9, v12);
        LOBYTE(v4) = v13 <= (__int64)this[3];
      }
      else if ( (g_dwDebugFlags & 3) != 0 )
      {
        LastError = GetLastError();
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\svcs\\infocomm\\log\\plugin\\odbcconn.cxx",
          1731,
          "ConvertUnicodeToAnsi",
          "WideCharToMultiByte failed with %d\n",
          LastError);
      }
      LocalFree(v9);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18000daa0  push    rbx
0x18000daa2  push    rbp
0x18000daa3  push    rsi
0x18000daa4  push    rdi
0x18000daa5  push    r12
0x18000daa7  push    r14
0x18000daa9  push    r15
0x18000daab  sub     rsp, 40h
0x18000daaf  xor     r12d, r12d
0x18000dab2  mov     rbp, rdx
0x18000dab5  mov     r14, rcx
0x18000dab8  mov     esi, r12d
0x18000dabb  test    rdx, rdx
0x18000dabe  jz      loc_18000DBA9
0x18000dac4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000dac8  mov     rax, rdi
0x18000dacb  inc     rax
0x18000dace  cmp     [rdx+rax*2], r12w
0x18000dad3  jnz     short loc_18000DACB
0x18000dad5  lea     r15d, ds:2[rax*2]
0x18000dadd  xor     ecx, ecx; uFlags
0x18000dadf  mov     edx, r15d; uBytes
0x18000dae2  call    cs:__imp_LocalAlloc
0x18000dae8  mov     rbx, rax
0x18000daeb  test    rax, rax
0x18000daee  jz      loc_18000DBA9
0x18000daf4  mov     [rsp+78h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x18000daf9  mov     r9d, edi; cchWideChar
0x18000dafc  mov     [rsp+78h+lpDefaultChar], r12; lpDefaultChar
0x18000db01  mov     r8, rbp; lpWideCharStr
0x18000db04  mov     [rsp+78h+cbMultiByte], r15d; cbMultiByte
0x18000db09  mov     edx, 200h; dwFlags
0x18000db0e  xor     ecx, ecx; CodePage
0x18000db10  mov     [rsp+78h+lpMultiByteStr], rax; lpMultiByteStr
0x18000db15  call    cs:__imp_WideCharToMultiByte
0x18000db1b  test    eax, eax
0x18000db1d  jnz     short loc_18000DB61
0x18000db1f  test    byte ptr cs:g_dwDebugFlags, 3
0x18000db26  jz      short loc_18000DBA0
0x18000db28  call    cs:__imp_GetLastError
0x18000db2e  mov     rcx, cs:g_pDebug
0x18000db35  lea     r9, aConvertunicode; "ConvertUnicodeToAnsi"
0x18000db3c  mov     [rsp+78h+cbMultiByte], eax
0x18000db40  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\infocomm\\log\\plug"...
0x18000db47  lea     rax, aWidechartomult; "WideCharToMultiByte failed with %d\n"
0x18000db4e  mov     r8d, 6C3h
0x18000db54  mov     [rsp+78h+lpMultiByteStr], rax
0x18000db59  call    cs:__imp_PuDbgPrint
0x18000db5f  jmp     short loc_18000DBA0
0x18000db61  dec     eax
0x18000db63  mov     [rax+rbx], r12b
0x18000db67  inc     rdi
0x18000db6a  cmp     [rbx+rdi], r12b
0x18000db6e  jnz     short loc_18000DB67
0x18000db70  lea     eax, [rdi+1]
0x18000db73  movsxd  rdi, eax
0x18000db76  cmp     rdi, [r14+18h]
0x18000db7a  jg      short loc_18000DB8D
0x18000db7c  mov     rcx, [r14+10h]; void *
0x18000db80  mov     r8, rdi; Size
0x18000db83  mov     rdx, rbx; Src
0x18000db86  call    memcpy_0
0x18000db8b  jmp     short loc_18000DB98
0x18000db8d  mov     ecx, 7Ah ; 'z'; dwErrCode
0x18000db92  call    cs:__imp_SetLastError
0x18000db98  cmp     rdi, [r14+18h]
0x18000db9c  setle   sil
0x18000dba0  mov     rcx, rbx; hMem
0x18000dba3  call    cs:__imp_LocalFree
0x18000dba9  mov     eax, esi
0x18000dbab  add     rsp, 40h
0x18000dbaf  pop     r15
0x18000dbb1  pop     r14
0x18000dbb3  pop     r12
0x18000dbb5  pop     rdi
0x18000dbb6  pop     rsi
0x18000dbb7  pop     rbp
0x18000dbb8  pop     rbx
0x18000dbb9  retn
```
