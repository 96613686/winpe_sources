# myRegOpenRelativeKey(ushort const *,ushort const *,ulong,ushort * *,ushort * *,HKEY__ * *,bool *)

- ea: `0x18002746c`
- end: `0x180027599`
- name: `?myRegOpenRelativeKey@@YAJPEBG0KPEAPEAG1PEAPEAUHKEY__@@PEA_N@Z`
- size: `301`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *Src@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, unsigned __int16 **@<r9>, unsigned __int16 **, HKEY *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000baf4`

## callees

- `0x18001e920`
- `0x1800213f0`
- `0x180026064`
- `0x1800260fc`
- `0x18002746c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027570`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027570`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027579`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027579`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800274dc`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180027559`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800274dc`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180027559`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180027513`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180027513`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x1800274fc`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x1800274fc`

## pseudocode

```c
__int64 __fastcall myRegOpenRelativeKey(
        const unsigned __int16 *Src,
        const unsigned __int16 *a2,
        int a3,
        unsigned __int16 **a4,
        const WCHAR *lpMachineName,
        HKEY *a6)
{
  unsigned __int16 *v6; // rdi
  int RootKey; // eax
  int v10; // ebx
  unsigned int v11; // ecx
  int IsConfigLocal; // eax
  LSTATUS v13; // eax
  HKEY phkResult; // [rsp+68h] [rbp+28h] BYREF
  int v16; // [rsp+70h] [rbp+30h] BYREF

  v16 = a3;
  v6 = 0;
  phkResult = HKEY_LOCAL_MACHINE;
  lpMachineName = 0;
  RootKey = _GetRootKey(Src, (unsigned int)a2, &phkResult);
  v10 = RootKey;
  if ( RootKey )
  {
    v11 = 27197908;
LABEL_11:
    CSPrintErrorLineFile(v11, RootKey);
    goto LABEL_12;
  }
  if ( Src )
  {
    v16 = 0;
    IsConfigLocal = myIsConfigLocal(Src, (unsigned __int16 **)&lpMachineName, &v16);
    v10 = IsConfigLocal;
    if ( IsConfigLocal )
    {
      CSPrintErrorLineFile(0x1A801D4u, IsConfigLocal);
      v6 = (unsigned __int16 *)lpMachineName;
      goto LABEL_12;
    }
    v6 = (unsigned __int16 *)lpMachineName;
    if ( !v16 )
    {
      v13 = RegConnectRegistryW(lpMachineName, phkResult, &phkResult);
      v10 = v13;
      if ( v13 )
      {
        CSPrintErrorLineFileData(v6, 0x1AD01D4u, v13);
        goto LABEL_12;
      }
    }
  }
  RootKey = _RegOpenRelativeKey((unsigned __int16 *)phkResult, L"ca", 0, a4, 0, a6);
  v10 = RootKey;
  if ( RootKey )
  {
    v11 = 28901844;
    goto LABEL_11;
  }
LABEL_12:
  if ( (unsigned __int64)phkResult + 0x7FFFFFFF > 2 )
    RegCloseKey(phkResult);
  LocalFree(v6);
  return myHError(v10);
}

```

## disassembly

```asm
0x18002746c  mov     rax, rsp
0x18002746f  mov     [rax+8], rbx
0x180027473  mov     [rax+20h], rsi
0x180027477  mov     [rax+18h], r8d
0x18002747b  mov     [rax+10h], rdx
0x18002747f  push    rbp
0x180027480  push    rdi
0x180027481  push    r14
0x180027483  mov     rbp, rsp
0x180027486  sub     rsp, 40h
0x18002748a  xor     edi, edi
0x18002748c  mov     [rbp+phkResult], 0FFFFFFFF80000002h
0x180027494  lea     r8, [rbp+phkResult]; HKEY *
0x180027498  mov     [rbp+lpMachineName], rdi
0x18002749c  mov     r14, r9
0x18002749f  mov     rsi, rcx
0x1800274a2  call    ?_GetRootKey@@YAJPEBGKPEAPEAUHKEY__@@@Z; _GetRootKey(ushort const *,ulong,HKEY__ * *)
0x1800274a7  mov     ebx, eax
0x1800274a9  test    eax, eax
0x1800274ab  jz      short loc_1800274B7
0x1800274ad  mov     ecx, 19F01D4h
0x1800274b2  jmp     loc_180027557
0x1800274b7  test    rsi, rsi
0x1800274ba  jz      short loc_18002751B
0x1800274bc  lea     r8, [rbp+arg_10]; int *
0x1800274c0  mov     [rbp+arg_10], edi
0x1800274c3  lea     rdx, [rbp+lpMachineName]; unsigned __int16 **
0x1800274c7  mov     rcx, rsi; Src
0x1800274ca  call    ?myIsConfigLocal@@YAJPEBGPEAPEAGPEAH@Z; myIsConfigLocal(ushort const *,ushort * *,int *)
0x1800274cf  mov     ebx, eax
0x1800274d1  test    eax, eax
0x1800274d3  jz      short loc_1800274E8
0x1800274d5  mov     edx, eax
0x1800274d7  mov     ecx, 1A801D4h
0x1800274dc  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800274e2  mov     rdi, [rbp+lpMachineName]
0x1800274e6  jmp     short loc_18002755F
0x1800274e8  cmp     [rbp+arg_10], edi
0x1800274eb  mov     rdi, [rbp+lpMachineName]
0x1800274ef  jnz     short loc_18002751B
0x1800274f1  mov     rdx, [rbp+phkResult]; hKey
0x1800274f5  lea     r8, [rbp+phkResult]; phkResult
0x1800274f9  mov     rcx, rdi; lpMachineName
0x1800274fc  call    cs:__imp_RegConnectRegistryW
0x180027502  mov     ebx, eax
0x180027504  test    eax, eax
0x180027506  jz      short loc_18002751B
0x180027508  mov     r8d, eax
0x18002750b  mov     edx, 1AD01D4h
0x180027510  mov     rcx, rdi
0x180027513  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x180027519  jmp     short loc_18002755F
0x18002751b  mov     rax, [rbp+arg_28]
0x18002751f  lea     rdx, aCa_0; "ca"
0x180027526  mov     rcx, [rbp+phkResult]; HKEY
0x18002752a  mov     r9, r14; unsigned __int16 **
0x18002752d  mov     [rsp+40h+var_10], 0; bool *
0x180027536  xor     r8d, r8d; unsigned int
0x180027539  mov     [rsp+40h+var_18], rax; HKEY *
0x18002753e  mov     [rsp+40h+var_20], 0; unsigned __int16 **
0x180027547  call    ?_RegOpenRelativeKey@@YAJPEAUHKEY__@@PEBGKPEAPEAG2PEAPEAU1@PEA_N@Z; _RegOpenRelativeKey(HKEY__ *,ushort const *,ulong,ushort * *,ushort * *,HKEY__ * *,bool *)
0x18002754c  mov     ebx, eax
0x18002754e  test    eax, eax
0x180027550  jz      short loc_18002755F
0x180027552  mov     ecx, 1B901D4h
0x180027557  mov     edx, eax
0x180027559  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002755f  mov     rcx, [rbp+phkResult]; hKey
0x180027563  lea     rax, [rcx+7FFFFFFFh]
0x18002756a  cmp     rax, 2
0x18002756e  jbe     short loc_180027576
0x180027570  call    cs:__imp_RegCloseKey
0x180027576  mov     rcx, rdi; hMem
0x180027579  call    cs:__imp_LocalFree
0x18002757f  mov     ecx, ebx; int
0x180027581  call    ?myHError@@YAJJ@Z; myHError(long)
0x180027586  mov     rbx, [rsp+40h+arg_0]
0x18002758b  mov     rsi, [rsp+40h+arg_18]
0x180027590  add     rsp, 40h
0x180027594  pop     r14
0x180027596  pop     rdi
0x180027597  pop     rbp
0x180027598  retn
```
