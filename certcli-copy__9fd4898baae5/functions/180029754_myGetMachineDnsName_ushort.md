# myGetMachineDnsName(ushort * *)

- ea: `0x180029754`
- end: `0x18002983b`
- name: `?myGetMachineDnsName@@YAJPEAPEAG@Z`
- size: `231`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010758`
- `0x18001e2a4`

## callees

- `0x180021438`
- `0x180029754`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800297db`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800297db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029822`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029822`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180029783`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180029801`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180029783`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180029801`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800297a4`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800297bc`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180029819`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800297a4`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800297bc`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180029819`

## pseudocode

```c
__int64 __fastcall myGetMachineDnsName(unsigned __int16 **a1)
{
  COMPUTER_NAME_FORMAT i; // esi
  unsigned int v3; // eax
  unsigned int v4; // ebx
  int v5; // edx
  unsigned int v6; // ecx
  DWORD v7; // eax
  WCHAR *v8; // rax
  unsigned __int16 *v9; // rdi
  DWORD nSize; // [rsp+50h] [rbp+8h] BYREF

  *a1 = 0;
  for ( i = ComputerNameDnsFullyQualified; ; i = ComputerNameNetBIOS )
  {
    nSize = 0;
    if ( GetComputerNameExW(i, 0, &nSize) )
    {
      v7 = ++nSize;
      goto LABEL_11;
    }
    v3 = myHLastError();
    v4 = v3;
    if ( v3 != -2147024894 )
      break;
    if ( i != ComputerNameDnsFullyQualified )
      goto LABEL_7;
    CSPrintErrorLineFile(0x76301C9u, -2147024894);
  }
  if ( v3 != -2147024662 )
  {
LABEL_7:
    v5 = v3;
    v6 = 124322249;
LABEL_8:
    CSPrintErrorLineFile(v6, v5);
    return v4;
  }
  v7 = nSize;
LABEL_11:
  v8 = (WCHAR *)LocalAlloc(0, 2LL * v7);
  v9 = v8;
  if ( !v8 )
  {
    v4 = -2147024882;
    v6 = 125174217;
    v5 = -2147024882;
    goto LABEL_8;
  }
  if ( GetComputerNameExW(i, v8, &nSize) )
  {
    *a1 = v9;
    return 0;
  }
  else
  {
    v4 = myHLastError();
    CSPrintErrorLineFile(0x77C01C9u, v4);
    LocalFree(v9);
  }
  return v4;
}

```

## disassembly

```asm
0x180029754  push    rbx
0x180029756  push    rsi
0x180029757  push    rdi
0x180029758  push    r14
0x18002975a  sub     rsp, 28h
0x18002975e  mov     r14, rcx
0x180029761  mov     qword ptr [rcx], 0
0x180029768  mov     esi, 3
0x18002976d  mov     edi, 80070002h
0x180029772  lea     r8, [rsp+48h+nSize]; nSize
0x180029777  mov     [rsp+48h+nSize], 0
0x18002977f  xor     edx, edx; lpBuffer
0x180029781  mov     ecx, esi; NameType
0x180029783  call    cs:__imp_GetComputerNameExW
0x180029789  test    eax, eax
0x18002978b  jnz     short loc_1800297CA
0x18002978d  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180029792  mov     ebx, eax
0x180029794  cmp     eax, edi
0x180029796  jnz     short loc_1800297AE
0x180029798  cmp     esi, 3
0x18002979b  jnz     short loc_1800297B5
0x18002979d  mov     edx, edi
0x18002979f  mov     ecx, 76301C9h
0x1800297a4  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800297aa  xor     esi, esi
0x1800297ac  jmp     short loc_180029772
0x1800297ae  cmp     eax, 800700EAh
0x1800297b3  jz      short loc_1800297C4
0x1800297b5  mov     edx, eax
0x1800297b7  mov     ecx, 76901C9h
0x1800297bc  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800297c2  jmp     short loc_18002982F
0x1800297c4  mov     eax, [rsp+48h+nSize]
0x1800297c8  jmp     short loc_1800297D4
0x1800297ca  mov     eax, [rsp+48h+nSize]
0x1800297ce  inc     eax
0x1800297d0  mov     [rsp+48h+nSize], eax
0x1800297d4  mov     edx, eax
0x1800297d6  xor     ecx, ecx; uFlags
0x1800297d8  add     rdx, rdx; uBytes
0x1800297db  call    cs:__imp_LocalAlloc
0x1800297e1  mov     rdi, rax
0x1800297e4  test    rax, rax
0x1800297e7  jnz     short loc_1800297F7
0x1800297e9  mov     ebx, 8007000Eh
0x1800297ee  mov     ecx, 77601C9h
0x1800297f3  mov     edx, ebx
0x1800297f5  jmp     short loc_1800297BC
0x1800297f7  lea     r8, [rsp+48h+nSize]; nSize
0x1800297fc  mov     rdx, rdi; lpBuffer
0x1800297ff  mov     ecx, esi; NameType
0x180029801  call    cs:__imp_GetComputerNameExW
0x180029807  test    eax, eax
0x180029809  jnz     short loc_18002982A
0x18002980b  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180029810  mov     edx, eax
0x180029812  mov     ecx, 77C01C9h
0x180029817  mov     ebx, eax
0x180029819  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002981f  mov     rcx, rdi; hMem
0x180029822  call    cs:__imp_LocalFree
0x180029828  jmp     short loc_18002982F
0x18002982a  mov     [r14], rdi
0x18002982d  xor     ebx, ebx
0x18002982f  mov     eax, ebx
0x180029831  add     rsp, 28h
0x180029835  pop     r14
0x180029837  pop     rdi
0x180029838  pop     rsi
0x180029839  pop     rbx
0x18002983a  retn
```
