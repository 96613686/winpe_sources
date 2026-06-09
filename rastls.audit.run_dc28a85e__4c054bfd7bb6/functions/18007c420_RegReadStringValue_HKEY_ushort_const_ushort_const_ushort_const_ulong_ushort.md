# RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)

- ea: `0x18007c420`
- end: `0x18007c5d1`
- name: `?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z`
- size: `433`
- prototype: `unsigned int __fastcall(HKEY hkey, LPCWSTR lpSubKey, const unsigned __int16 *, const unsigned __int16 *, DWORD, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18007c340`

## callees

- `0x18002f1ac`
- `0x18002f324`
- `0x18007c314`
- `0x18007c420`
- `0x18007c5d8`
- `0x18007dd0c`
- `0x18007dd84`
- `0x18007ddc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007c4a5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007c554`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007c4a5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007c554`

## string_xrefs

- `0x18007c58c`: `%s: Cannot read registry key value "%s@%s". Error code: 0x%08x.`
- `0x18007c4c0`: `%s: The registry key value "%s@%s" does not exist. Using default value NULL. Error code: 0x%08x.`
- `0x18007c4f7`: `%s: The registry key value "%s@%s" is not of one of the specified types (flags = 0x%08x). Using default value NULL.`
- `0x18007c45d`: `RegReadStringValue`
- `0x18007c4c7`: `RegReadStringValue`
- `0x18007c585`: `RegReadStringValue`
- `0x18007c5b7`: `RegReadStringValue`

## pseudocode

```c
__int64 __fastcall RegReadStringValue(
        HKEY hkey,
        LPCWSTR lpSubKey,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        DWORD pcbData,
        unsigned __int16 **a6)
{
  void **v6; // rsi
  LSTATUS ValueW; // eax
  const unsigned __int16 *v13; // rdx
  unsigned int v14; // ebx
  unsigned __int16 *RegValueName; // rax
  const unsigned __int16 *v16; // rcx
  void *pvData; // rax
  unsigned __int16 *v18; // rax
  LPDWORD pdwType; // [rsp+20h] [rbp-68h]
  DWORD v20[18]; // [rsp+40h] [rbp-48h] BYREF

  v6 = (void **)a6;
  v20[0] = 0;
  pcbData = 0;
  if ( !a6 )
  {
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegReadStringValue", L"pData");
    return 87;
  }
  *a6 = 0;
  ValueW = RegGetValueW(hkey, lpSubKey, a3, 2u, v20, 0, &pcbData);
  v14 = ValueW;
  if ( ValueW != 2 )
  {
    if ( ValueW == 1630 )
    {
      RegValueName = GetRegValueName(a3);
      v16 = L"%s: The registry key value \"%s@%s\" is not of one of the specified types (flags = 0x%08x). Using default value NULL.";
      goto LABEL_5;
    }
    if ( !ValueW || ValueW == 234 )
    {
      if ( pcbData )
      {
        pvData = SafeAlloc(pcbData);
        *v6 = pvData;
        if ( !pvData )
        {
          v14 = 14;
          Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"RegReadStringValue");
          goto LABEL_14;
        }
        v14 = RegGetValueW(hkey, lpSubKey, a3, 2u, v20, pvData, &pcbData);
      }
      if ( !v14 )
        return v14;
    }
LABEL_14:
    Logger::WriteRegistryFailureEvent(v14, v13, a4, a3);
    v18 = GetRegValueName(a3);
    LODWORD(pdwType) = v14;
    Logger::TraceWarning(
      L"%s: Cannot read registry key value \"%s@%s\". Error code: 0x%08x.",
      L"RegReadStringValue",
      a4,
      v18,
      pdwType);
    SafeFree(*v6);
    *v6 = 0;
    return v14;
  }
  RegValueName = GetRegValueName(a3);
  v16 = L"%s: The registry key value \"%s@%s\" does not exist. Using default value NULL. Error code: 0x%08x.";
LABEL_5:
  LODWORD(pdwType) = 2;
  Logger::TraceWarning(v16, L"RegReadStringValue", a4, RegValueName, pdwType);
  return 0;
}

```

## disassembly

```asm
0x18007c420  mov     rax, rsp
0x18007c423  push    rbx
0x18007c424  push    rbp
0x18007c425  push    rsi
0x18007c426  push    rdi
0x18007c427  push    r14
0x18007c429  push    r15
0x18007c42b  sub     rsp, 58h
0x18007c42f  mov     rsi, [rsp+88h+arg_28]
0x18007c437  mov     rbp, r9
0x18007c43a  mov     dword ptr [rax-48h], 0
0x18007c441  mov     rdi, r8
0x18007c444  mov     dword ptr [rax+28h], 0
0x18007c44b  mov     r14, rdx
0x18007c44e  mov     r15, rcx
0x18007c451  test    rsi, rsi
0x18007c454  jnz     short loc_18007C478
0x18007c456  lea     r8, aPdata; "pData"
0x18007c45d  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x18007c464  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007c46b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007c470  lea     eax, [rsi+57h]
0x18007c473  jmp     loc_18007C5A9
0x18007c478  lea     rax, [rsp+88h+arg_20]
0x18007c480  mov     qword ptr [rsi], 0
0x18007c487  mov     [rsp+88h+pcbData], rax; pcbData
0x18007c48c  mov     r9d, 2; dwFlags
0x18007c492  lea     rax, [rsp+88h+var_48]
0x18007c497  mov     [rsp+88h+pvData], 0; pvData
0x18007c4a0  mov     [rsp+88h+pdwType], rax; pdwType
0x18007c4a5  call    cs:__imp_RegGetValueW
0x18007c4ac  nop     dword ptr [rax+rax+00h]
0x18007c4b1  mov     ebx, eax
0x18007c4b3  cmp     eax, 2
0x18007c4b6  jnz     short loc_18007C4E8
0x18007c4b8  mov     rcx, rdi; unsigned __int16 *
0x18007c4bb  call    ?GetRegValueName@@YAPEAGPEBG@Z; GetRegValueName(ushort const *)
0x18007c4c0  lea     rcx, aSTheRegistryKe; "%s: The registry key value \"%s@%s\" do"...
0x18007c4c7  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x18007c4ce  mov     dword ptr [rsp+88h+pdwType], 2
0x18007c4d6  mov     r8, rbp
0x18007c4d9  mov     r9, rax
0x18007c4dc  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18007c4e1  xor     ebx, ebx
0x18007c4e3  jmp     loc_18007C5A7
0x18007c4e8  cmp     eax, 65Eh
0x18007c4ed  jnz     short loc_18007C500
0x18007c4ef  mov     rcx, rdi; unsigned __int16 *
0x18007c4f2  call    ?GetRegValueName@@YAPEAGPEBG@Z; GetRegValueName(ushort const *)
0x18007c4f7  lea     rcx, aSTheRegistryKe_0; "%s: The registry key value \"%s@%s\" is"...
0x18007c4fe  jmp     short loc_18007C4C7
0x18007c500  test    eax, eax
0x18007c502  jz      short loc_18007C50B
0x18007c504  cmp     eax, 0EAh
0x18007c509  jnz     short loc_18007C566
0x18007c50b  mov     eax, [rsp+88h+arg_20]
0x18007c512  test    eax, eax
0x18007c514  jz      short loc_18007C562
0x18007c516  mov     ecx, eax; unsigned __int64
0x18007c518  call    ?SafeAlloc@@YAPEAX_K@Z; SafeAlloc(unsigned __int64)
0x18007c51d  mov     [rsi], rax
0x18007c520  test    rax, rax
0x18007c523  jz      loc_18007C5B7
0x18007c529  lea     rcx, [rsp+88h+arg_20]
0x18007c531  mov     r9d, 2; dwFlags
0x18007c537  mov     [rsp+88h+pcbData], rcx; pcbData
0x18007c53c  mov     r8, rdi; lpValue
0x18007c53f  mov     [rsp+88h+pvData], rax; pvData
0x18007c544  mov     rdx, r14; lpSubKey
0x18007c547  lea     rax, [rsp+88h+var_48]
0x18007c54c  mov     rcx, r15; hkey
0x18007c54f  mov     [rsp+88h+pdwType], rax; pdwType
0x18007c554  call    cs:__imp_RegGetValueW
0x18007c55b  nop     dword ptr [rax+rax+00h]
0x18007c560  mov     ebx, eax
0x18007c562  test    ebx, ebx
0x18007c564  jz      short loc_18007C5A7
0x18007c566  mov     r9, rdi; unsigned __int16 *
0x18007c569  mov     r8, rbp; unsigned __int16 *
0x18007c56c  mov     ecx, ebx; unsigned int
0x18007c56e  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG00@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *,ushort const *)
0x18007c573  mov     rcx, rdi; unsigned __int16 *
0x18007c576  call    ?GetRegValueName@@YAPEAGPEBG@Z; GetRegValueName(ushort const *)
0x18007c57b  mov     r9, rax
0x18007c57e  mov     dword ptr [rsp+88h+pdwType], ebx
0x18007c582  mov     r8, rbp
0x18007c585  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x18007c58c  lea     rcx, aSCannotReadReg; "%s: Cannot read registry key value \"%s"...
0x18007c593  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18007c598  mov     rcx, [rsi]; void *
0x18007c59b  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18007c5a0  mov     qword ptr [rsi], 0
0x18007c5a7  mov     eax, ebx
0x18007c5a9  add     rsp, 58h
0x18007c5ad  pop     r15
0x18007c5af  pop     r14
0x18007c5b1  pop     rdi
0x18007c5b2  pop     rsi
0x18007c5b3  pop     rbp
0x18007c5b4  pop     rbx
0x18007c5b5  retn
0x18007c5b7  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x18007c5be  mov     ebx, 0Eh
0x18007c5c3  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x18007c5ca  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18007c5cf  jmp     short loc_18007C566
```
