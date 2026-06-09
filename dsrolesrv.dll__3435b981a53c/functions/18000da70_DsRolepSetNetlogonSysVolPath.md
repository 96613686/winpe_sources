# DsRolepSetNetlogonSysVolPath

- ea: `0x18000da70`
- end: `0x18000de18`
- name: `DsRolepSetNetlogonSysVolPath`
- size: `936`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, const wchar_t *, char, _BYTE *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180011240`
- `0x180012460`

## callees

- `0x180008f24`
- `0x180008fd4`
- `0x18000d788`
- `0x18000da70`
- `0x18000de20`
- `0x180016374`
- `0x18001e204`
- `0x18001fe50`
- `0x180020dbc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000db57`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000db57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dde0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dde0`
- `ntdll!RtlAllocateHeap` at `0x18000dad4`
- `ntdll!RtlAllocateHeap` at `0x18000dc58`
- `ntdll!RtlAllocateHeap` at `0x18000dad4`
- `ntdll!RtlAllocateHeap` at `0x18000dc58`
- `ntdll!RtlFreeHeap` at `0x18000ddb0`
- `ntdll!RtlFreeHeap` at `0x18000ddc8`
- `ntdll!RtlFreeHeap` at `0x18000ddf8`
- `ntdll!RtlFreeHeap` at `0x18000ddb0`
- `ntdll!RtlFreeHeap` at `0x18000ddc8`
- `ntdll!RtlFreeHeap` at `0x18000ddf8`
- `ntdll!RtlInitUnicodeString` at `0x18000dd66`
- `ntdll!RtlInitUnicodeString` at `0x18000dd73`
- `ntdll!RtlInitUnicodeString` at `0x18000dd66`
- `ntdll!RtlInitUnicodeString` at `0x18000dd73`

## string_xrefs

- `0x18000db49`: `System\CurrentControlSet\services\Netlogon\parameters\`
- `0x18000db66`: `System\CurrentControlSet\services\Netlogon\parameters\`
- `0x18000db6d`: `Failed to open %ws: %lu\n`
- `0x18000dd28`: `DsRolepTreeCopy from %ws to %ws failed with %lu\n`

## pseudocode

```c
__int64 __fastcall DsRolepSetNetlogonSysVolPath(STRSAFE_LPCWSTR pszSrc, const wchar_t *a2, char a3, _BYTE *a4)
{
  __int64 v8; // r14
  __int64 v9; // rax
  SIZE_T v10; // rbx
  wchar_t *Heap; // rax
  wchar_t *v12; // rdi
  unsigned int v13; // esi
  size_t v14; // rbx
  __int16 v15; // r11
  __int64 v16; // rax
  unsigned int v17; // eax
  int v18; // r8d
  unsigned int v19; // ebx
  __int64 v21; // rax
  wchar_t *v22; // rbx
  unsigned int v23; // eax
  WCHAR *v24; // r12
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r13
  PVOID ProcessHeap; // rcx
  unsigned __int64 v30; // r13
  wchar_t *v31; // rax
  size_t v32; // rsi
  unsigned int v33; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-30h]
  PCWSTR SourceString[2]; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+58h] BYREF

  hKey = 0;
  SourceString[0] = 0;
  if ( a4 )
    *a4 = 0;
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( pszSrc[v9] );
  v10 = 2 * v9 + 16;
  Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
  v12 = Heap;
  if ( Heap )
  {
    v14 = v10 >> 1;
    StringCchCopyW(Heap, v14, pszSrc);
    v16 = -1;
    do
      ++v16;
    while ( v12[v16] != v15 );
    if ( v12[v16 - 1] != 92 )
      StringCchCatW(v12, v14, L"\\");
    StringCchCatW(v12, v14, L"sysvol");
    v17 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\services\\Netlogon\\parameters\\",
            0,
            0x2001Fu,
            &hKey);
    v19 = v17;
    if ( v17 )
    {
      DsRolepLogPrintRoutine(
        1,
        "Failed to open %ws: %lu\n",
        L"System\\CurrentControlSet\\services\\Netlogon\\parameters\\",
        v17);
      return v19;
    }
    v21 = -1;
    v22 = 0;
    do
      ++v21;
    while ( v12[v21] );
    v23 = DsRolepRegSetValueEx((int)hKey, (int)L"SysVol", v18, 1, (int)v12, 2 * v21 + 2);
    v13 = v23;
    if ( v23 )
    {
      DsRolepLogPrintRoutine(1, "Failed to set %ws: %lu\n", L"SysVol", v23);
    }
    else if ( a3 )
    {
      v24 = (WCHAR *)SourceString[0];
      if ( (unsigned int)DsRolepGetNetlogonScriptsPath(hKey) )
        goto LABEL_36;
      v25 = -1;
      do
        ++v25;
      while ( a2[v25] );
      v26 = -1;
      do
        ++v26;
      while ( v12[v26] );
      v27 = v25 + v26;
      v28 = 16;
      ProcessHeap = NtCurrentPeb()->ProcessHeap;
      if ( (unsigned __int64)(v27 + 11) <= 0x104 )
        v28 = 11;
      v30 = v27 + v28;
      v31 = (wchar_t *)RtlAllocateHeap(ProcessHeap, 0, 2 * v30);
      v22 = v31;
      if ( !v31 )
        goto LABEL_36;
      v32 = (2 * v30) >> 1;
      if ( v30 <= 0x104 )
        *v31 = 0;
      else
        StringCchCopyW(v31, v32, L"\\\\?\\");
      StringCchCatW(v22, v32, v12);
      do
        ++v8;
      while ( v12[v8] );
      if ( v22[v8 - 1] != 92 )
        StringCchCatW(v22, v32, L"\\");
      StringCchCatW(v22, v32, a2);
      StringCchCatW(v22, v32, L"\\");
      StringCchCatW(v22, v32, L"Scripts");
      DsRolepSetCurrentOperationStatus(28725, v24, v22);
      v33 = DsRolepTreeCopy((__int64)v24, (__int64)v22, 0);
      v13 = v33;
      if ( v33 )
      {
        LODWORD(phkResult) = v33;
        DsRolepLogPrintRoutine(1, "DsRolepTreeCopy from %ws to %ws failed with %lu\n", v24, v22, phkResult);
      }
      DsRolepSetCurrentOperationStatus(28727, 0, 0);
      if ( v13 )
      {
LABEL_36:
        DestinationString = 0;
        *(_OWORD *)SourceString = 0;
        RtlInitUnicodeString(&DestinationString, v24);
        RtlInitUnicodeString((PUNICODE_STRING)SourceString, v22);
        DsRolepEventWrite(DSROLERES_FAIL_SCRIPT_COPY_EVENT, L"uu", &DestinationString, SourceString);
        dword_18004E218 |= 1u;
        v13 = 0;
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v24);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v22);
    }
  }
  else
  {
    v13 = 8;
  }
  if ( a4 )
    *a4 = 1;
  if ( hKey )
    RegCloseKey(hKey);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
  return v13;
}

```

## disassembly

```asm
0x18000da70  mov     [rsp-38h+arg_0], rbx
0x18000da75  mov     [rsp-38h+pszSrc], rdx
0x18000da7a  push    rbp
0x18000da7b  push    rsi
0x18000da7c  push    rdi
0x18000da7d  push    r12
0x18000da7f  push    r13
0x18000da81  push    r14
0x18000da83  push    r15
0x18000da85  mov     rbp, rsp
0x18000da88  sub     rsp, 50h
0x18000da8c  mov     rsi, rcx
0x18000da8f  mov     r15, r9
0x18000da92  xor     ecx, ecx
0x18000da94  mov     r12b, r8b
0x18000da97  mov     [rbp+hKey], rcx
0x18000da9b  mov     r13, rdx
0x18000da9e  mov     [rbp+SourceString], rcx
0x18000daa2  test    r9, r9
0x18000daa5  jz      short loc_18000DAAA
0x18000daa7  mov     [r9], cl
0x18000daaa  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000daae  mov     rax, r14
0x18000dab1  inc     rax
0x18000dab4  cmp     [rsi+rax*2], cx
0x18000dab8  jnz     short loc_18000DAB1
0x18000daba  mov     rcx, gs:60h
0x18000dac3  lea     rbx, ds:10h[rax*2]
0x18000dacb  mov     r8, rbx; Size
0x18000dace  xor     edx, edx; Flags
0x18000dad0  mov     rcx, [rcx+30h]; HeapHandle
0x18000dad4  call    cs:__imp_RtlAllocateHeap
0x18000dada  xor     r11d, r11d
0x18000dadd  mov     rdi, rax
0x18000dae0  test    rax, rax
0x18000dae3  jnz     short loc_18000DAED
0x18000dae5  lea     esi, [rax+8]
0x18000dae8  jmp     loc_18000DDCE
0x18000daed  shr     rbx, 1
0x18000daf0  mov     r8, rsi; pszSrc
0x18000daf3  mov     rdx, rbx; cchDest
0x18000daf6  mov     rcx, rdi; pszDest
0x18000daf9  call    StringCchCopyW
0x18000dafe  mov     rax, r14
0x18000db01  inc     rax
0x18000db04  cmp     [rdi+rax*2], r11w
0x18000db09  jnz     short loc_18000DB01
0x18000db0b  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x18000db11  jz      short loc_18000DB25
0x18000db13  lea     r8, pszSrc; "\\"
0x18000db1a  mov     rdx, rbx; cchDest
0x18000db1d  mov     rcx, rdi; pszDest
0x18000db20  call    StringCchCatW
0x18000db25  lea     r8, aSysvol; "sysvol"
0x18000db2c  mov     rdx, rbx; cchDest
0x18000db2f  mov     rcx, rdi; pszDest
0x18000db32  call    StringCchCatW
0x18000db37  lea     rax, [rbp+hKey]
0x18000db3b  mov     r9d, 2001Fh; samDesired
0x18000db41  xor     r8d, r8d; ulOptions
0x18000db44  mov     [rsp+50h+phkResult], rax; phkResult
0x18000db49  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\services\\Ne"...
0x18000db50  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000db57  call    cs:__imp_RegOpenKeyExW
0x18000db5d  mov     ebx, eax
0x18000db5f  test    eax, eax
0x18000db61  jz      short loc_18000DB85
0x18000db63  mov     r9d, eax
0x18000db66  lea     r8, aSystemCurrentc; "System\\CurrentControlSet\\services\\Ne"...
0x18000db6d  lea     rdx, aFailedToOpenWs; "Failed to open %ws: %lu\n"
0x18000db74  mov     ecx, 1
0x18000db79  call    DsRolepLogPrintRoutine
0x18000db7e  mov     eax, ebx
0x18000db80  jmp     loc_18000DE00
0x18000db85  mov     rax, r14
0x18000db88  xor     ebx, ebx
0x18000db8a  inc     rax
0x18000db8d  cmp     [rdi+rax*2], bx
0x18000db91  jnz     short loc_18000DB8A
0x18000db93  mov     rcx, [rbp+hKey]; int
0x18000db97  lea     rax, ds:2[rax*2]
0x18000db9f  mov     [rsp+50h+ullOperand], rax; ullOperand
0x18000dba4  lea     rdx, aSysvol_1; "SysVol"
0x18000dbab  mov     r9d, 1; int
0x18000dbb1  mov     [rsp+50h+phkResult], rdi; int
0x18000dbb6  call    DsRolepRegSetValueEx
0x18000dbbb  mov     esi, eax
0x18000dbbd  test    eax, eax
0x18000dbbf  jz      short loc_18000DBE1
0x18000dbc1  mov     r9d, eax
0x18000dbc4  lea     r8, aSysvol_1; "SysVol"
0x18000dbcb  lea     rdx, aFailedToSetWsL; "Failed to set %ws: %lu\n"
0x18000dbd2  mov     ecx, 1
0x18000dbd7  call    DsRolepLogPrintRoutine
0x18000dbdc  jmp     loc_18000DDCE
0x18000dbe1  test    r12b, r12b
0x18000dbe4  jz      loc_18000DDCE
0x18000dbea  mov     rcx, [rbp+hKey]; hKey
0x18000dbee  lea     rdx, [rbp+SourceString]
0x18000dbf2  call    DsRolepGetNetlogonScriptsPath
0x18000dbf7  mov     r12, [rbp+SourceString]
0x18000dbfb  xor     edx, edx
0x18000dbfd  test    eax, eax
0x18000dbff  jnz     loc_18000DD4E
0x18000dc05  mov     rcx, r14
0x18000dc08  inc     rcx
0x18000dc0b  cmp     [r13+rcx*2+0], dx
0x18000dc11  jnz     short loc_18000DC08
0x18000dc13  mov     rax, r14
0x18000dc16  inc     rax
0x18000dc19  cmp     [rdi+rax*2], dx
0x18000dc1d  jnz     short loc_18000DC16
0x18000dc1f  lea     rdx, [rcx+rax]
0x18000dc23  mov     r13d, 10h
0x18000dc29  mov     rcx, gs:60h
0x18000dc32  lea     rax, [rdx+0Bh]
0x18000dc36  cmp     rax, 104h
0x18000dc3c  lea     r8d, [r13-5]
0x18000dc40  mov     rcx, [rcx+30h]; HeapHandle
0x18000dc44  cmovbe  r13d, r8d
0x18000dc48  add     r13, rdx
0x18000dc4b  xor     edx, edx; Flags
0x18000dc4d  lea     rsi, ds:0[r13*2]
0x18000dc55  mov     r8, rsi; Size
0x18000dc58  call    cs:__imp_RtlAllocateHeap
0x18000dc5e  mov     rbx, rax
0x18000dc61  test    rax, rax
0x18000dc64  jz      loc_18000DD4E
0x18000dc6a  shr     rsi, 1
0x18000dc6d  cmp     r13, 104h
0x18000dc74  jbe     short loc_18000DC8D
0x18000dc76  lea     r8, asc_18003D5B8; "\\\\?\\"
0x18000dc7d  mov     rdx, rsi; cchDest
0x18000dc80  mov     rcx, rax; pszDest
0x18000dc83  call    StringCchCopyW
0x18000dc88  xor     r13d, r13d
0x18000dc8b  jmp     short loc_18000DC94
0x18000dc8d  xor     r13d, r13d
0x18000dc90  mov     [rax], r13w
0x18000dc94  mov     r8, rdi; pszSrc
0x18000dc97  mov     rdx, rsi; cchDest
0x18000dc9a  mov     rcx, rbx; pszDest
0x18000dc9d  call    StringCchCatW
0x18000dca2  inc     r14
0x18000dca5  cmp     [rdi+r14*2], r13w
0x18000dcaa  jnz     short loc_18000DCA2
0x18000dcac  cmp     word ptr [rbx+r14*2-2], 5Ch ; '\'
0x18000dcb3  jz      short loc_18000DCC7
0x18000dcb5  lea     r8, pszSrc; "\\"
0x18000dcbc  mov     rdx, rsi; cchDest
0x18000dcbf  mov     rcx, rbx; pszDest
0x18000dcc2  call    StringCchCatW
0x18000dcc7  mov     r8, [rbp+pszSrc]; pszSrc
0x18000dccb  mov     rdx, rsi; cchDest
0x18000dcce  mov     rcx, rbx; pszDest
0x18000dcd1  call    StringCchCatW
0x18000dcd6  lea     r8, pszSrc; "\\"
0x18000dcdd  mov     rdx, rsi; cchDest
0x18000dce0  mov     rcx, rbx; pszDest
0x18000dce3  call    StringCchCatW
0x18000dce8  lea     r8, aScripts; "Scripts"
0x18000dcef  mov     rdx, rsi; cchDest
0x18000dcf2  mov     rcx, rbx; pszDest
0x18000dcf5  call    StringCchCatW
0x18000dcfa  mov     r8, rbx
0x18000dcfd  mov     rdx, r12
0x18000dd00  mov     ecx, 7035h
0x18000dd05  call    DsRolepSetCurrentOperationStatus
0x18000dd0a  xor     r8d, r8d
0x18000dd0d  mov     rdx, rbx
0x18000dd10  mov     rcx, r12
0x18000dd13  call    DsRolepTreeCopy
0x18000dd18  mov     esi, eax
0x18000dd1a  test    eax, eax
0x18000dd1c  jz      short loc_18000DD39
0x18000dd1e  mov     r9, rbx
0x18000dd21  mov     dword ptr [rsp+50h+phkResult], eax
0x18000dd25  mov     r8, r12
0x18000dd28  lea     rdx, aDsroleptreecop_0; "DsRolepTreeCopy from %ws to %ws failed "...
0x18000dd2f  mov     ecx, 1
0x18000dd34  call    DsRolepLogPrintRoutine
0x18000dd39  xor     r8d, r8d
0x18000dd3c  xor     edx, edx
0x18000dd3e  mov     ecx, 7037h
0x18000dd43  call    DsRolepSetCurrentOperationStatus
0x18000dd48  test    esi, esi
0x18000dd4a  jz      short loc_18000DD9E
0x18000dd4c  jmp     short loc_18000DD51
0x18000dd4e  xor     r13d, r13d
0x18000dd51  xorps   xmm0, xmm0
0x18000dd54  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000dd58  xorps   xmm1, xmm1
0x18000dd5b  mov     rdx, r12; SourceString
0x18000dd5e  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000dd62  movups  xmmword ptr [rbp+SourceString], xmm1
0x18000dd66  call    cs:__imp_RtlInitUnicodeString
0x18000dd6c  mov     rdx, rbx; SourceString
0x18000dd6f  lea     rcx, [rbp+SourceString]; DestinationString
0x18000dd73  call    cs:__imp_RtlInitUnicodeString
0x18000dd79  lea     r9, [rbp+SourceString]
0x18000dd7d  lea     r8, [rbp+DestinationString]
0x18000dd81  lea     rdx, aUu; "uu"
0x18000dd88  lea     rcx, DSROLERES_FAIL_SCRIPT_COPY_EVENT
0x18000dd8f  call    DsRolepEventWrite
0x18000dd94  or      cs:dword_18004E218, 1
0x18000dd9b  mov     esi, r13d
0x18000dd9e  mov     rcx, gs:60h
0x18000dda7  mov     r8, r12; P
0x18000ddaa  xor     edx, edx; Flags
0x18000ddac  mov     rcx, [rcx+30h]; HeapHandle
0x18000ddb0  call    cs:__imp_RtlFreeHeap
0x18000ddb6  mov     rcx, gs:60h
0x18000ddbf  mov     r8, rbx; P
0x18000ddc2  xor     edx, edx; Flags
0x18000ddc4  mov     rcx, [rcx+30h]; HeapHandle
0x18000ddc8  call    cs:__imp_RtlFreeHeap
0x18000ddce  test    r15, r15
0x18000ddd1  jz      short loc_18000DDD7
0x18000ddd3  mov     byte ptr [r15], 1
0x18000ddd7  mov     rcx, [rbp+hKey]; hKey
0x18000dddb  test    rcx, rcx
0x18000ddde  jz      short loc_18000DDE6
0x18000dde0  call    cs:__imp_RegCloseKey
0x18000dde6  mov     rcx, gs:60h
0x18000ddef  mov     r8, rdi; P
0x18000ddf2  xor     edx, edx; Flags
0x18000ddf4  mov     rcx, [rcx+30h]; HeapHandle
0x18000ddf8  call    cs:__imp_RtlFreeHeap
0x18000ddfe  mov     eax, esi
0x18000de00  mov     rbx, [rsp+50h+arg_0]
0x18000de08  add     rsp, 50h
0x18000de0c  pop     r15
0x18000de0e  pop     r14
0x18000de10  pop     r13
0x18000de12  pop     r12
0x18000de14  pop     rdi
0x18000de15  pop     rsi
0x18000de16  pop     rbp
0x18000de17  retn
```
