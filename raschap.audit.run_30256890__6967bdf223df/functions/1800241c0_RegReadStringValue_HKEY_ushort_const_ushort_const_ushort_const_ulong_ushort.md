# RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)

- ea: `0x1800241c0`
- end: `0x180024364`
- name: `?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z`
- size: `420`
- prototype: `unsigned int __fastcall(HKEY hkey, LPCWSTR lpSubKey, const unsigned __int16 *, const unsigned __int16 *, DWORD, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800240ec`

## callees

- `0x180010218`
- `0x180010320`
- `0x1800135e4`
- `0x1800240c0`
- `0x1800241c0`
- `0x18002436c`
- `0x180025468`
- `0x1800254dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180024245`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800242ee`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180024245`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800242ee`

## string_xrefs

- `0x180024320`: `%s: Cannot read registry key value "%s@%s". Error code: 0x%08x.`
- `0x18002425a`: `%s: The registry key value "%s@%s" does not exist. Using default value NULL. Error code: 0x%08x.`
- `0x1800241fd`: `RegReadStringValue`
- `0x180024261`: `RegReadStringValue`
- `0x180024319`: `RegReadStringValue`
- `0x18002434a`: `RegReadStringValue`
- `0x180024291`: `%s: The registry key value "%s@%s" is not of one of the specified types (flags = 0x%08x). Using default value NULL.`

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
0x1800241c0  mov     rax, rsp
0x1800241c3  push    rbx
0x1800241c4  push    rbp
0x1800241c5  push    rsi
0x1800241c6  push    rdi
0x1800241c7  push    r14
0x1800241c9  push    r15
0x1800241cb  sub     rsp, 58h
0x1800241cf  mov     rsi, [rsp+88h+arg_28]
0x1800241d7  mov     rbp, r9
0x1800241da  mov     dword ptr [rax-48h], 0
0x1800241e1  mov     rdi, r8
0x1800241e4  mov     dword ptr [rax+28h], 0
0x1800241eb  mov     r14, rdx
0x1800241ee  mov     r15, rcx
0x1800241f1  test    rsi, rsi
0x1800241f4  jnz     short loc_180024218
0x1800241f6  lea     r8, aPdata; "pData"
0x1800241fd  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x180024204  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18002420b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180024210  lea     eax, [rsi+57h]
0x180024213  jmp     loc_18002433D
0x180024218  lea     rax, [rsp+88h+arg_20]
0x180024220  mov     qword ptr [rsi], 0
0x180024227  mov     [rsp+88h+pcbData], rax; pcbData
0x18002422c  mov     r9d, 2; dwFlags
0x180024232  lea     rax, [rsp+88h+var_48]
0x180024237  mov     [rsp+88h+pvData], 0; pvData
0x180024240  mov     [rsp+88h+pdwType], rax; pdwType
0x180024245  call    cs:__imp_RegGetValueW
0x18002424b  mov     ebx, eax
0x18002424d  cmp     eax, 2
0x180024250  jnz     short loc_180024282
0x180024252  mov     rcx, rdi; unsigned __int16 *
0x180024255  call    ?GetRegValueName@@YAPEAGPEBG@Z; GetRegValueName(ushort const *)
0x18002425a  lea     rcx, aSTheRegistryKe; "%s: The registry key value \"%s@%s\" do"...
0x180024261  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x180024268  mov     dword ptr [rsp+88h+pdwType], 2
0x180024270  mov     r8, rbp
0x180024273  mov     r9, rax
0x180024276  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18002427b  xor     ebx, ebx
0x18002427d  jmp     loc_18002433B
0x180024282  cmp     eax, 65Eh
0x180024287  jnz     short loc_18002429A
0x180024289  mov     rcx, rdi; unsigned __int16 *
0x18002428c  call    ?GetRegValueName@@YAPEAGPEBG@Z; GetRegValueName(ushort const *)
0x180024291  lea     rcx, aSTheRegistryKe_0; "%s: The registry key value \"%s@%s\" is"...
0x180024298  jmp     short loc_180024261
0x18002429a  test    eax, eax
0x18002429c  jz      short loc_1800242A5
0x18002429e  cmp     eax, 0EAh
0x1800242a3  jnz     short loc_1800242FA
0x1800242a5  mov     eax, [rsp+88h+arg_20]
0x1800242ac  test    eax, eax
0x1800242ae  jz      short loc_1800242F6
0x1800242b0  mov     ecx, eax; unsigned __int64
0x1800242b2  call    ?SafeAlloc@@YAPEAX_K@Z; SafeAlloc(unsigned __int64)
0x1800242b7  mov     [rsi], rax
0x1800242ba  test    rax, rax
0x1800242bd  jz      loc_18002434A
0x1800242c3  lea     rcx, [rsp+88h+arg_20]
0x1800242cb  mov     r9d, 2; dwFlags
0x1800242d1  mov     [rsp+88h+pcbData], rcx; pcbData
0x1800242d6  mov     r8, rdi; lpValue
0x1800242d9  mov     [rsp+88h+pvData], rax; pvData
0x1800242de  mov     rdx, r14; lpSubKey
0x1800242e1  lea     rax, [rsp+88h+var_48]
0x1800242e6  mov     rcx, r15; hkey
0x1800242e9  mov     [rsp+88h+pdwType], rax; pdwType
0x1800242ee  call    cs:__imp_RegGetValueW
0x1800242f4  mov     ebx, eax
0x1800242f6  test    ebx, ebx
0x1800242f8  jz      short loc_18002433B
0x1800242fa  mov     r9, rdi; unsigned __int16 *
0x1800242fd  mov     r8, rbp; unsigned __int16 *
0x180024300  mov     ecx, ebx; unsigned int
0x180024302  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG00@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *,ushort const *)
0x180024307  mov     rcx, rdi; unsigned __int16 *
0x18002430a  call    ?GetRegValueName@@YAPEAGPEBG@Z; GetRegValueName(ushort const *)
0x18002430f  mov     r9, rax
0x180024312  mov     dword ptr [rsp+88h+pdwType], ebx
0x180024316  mov     r8, rbp
0x180024319  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x180024320  lea     rcx, aSCannotReadReg; "%s: Cannot read registry key value \"%s"...
0x180024327  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18002432c  mov     rcx, [rsi]; void *
0x18002432f  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180024334  mov     qword ptr [rsi], 0
0x18002433b  mov     eax, ebx
0x18002433d  add     rsp, 58h
0x180024341  pop     r15
0x180024343  pop     r14
0x180024345  pop     rdi
0x180024346  pop     rsi
0x180024347  pop     rbp
0x180024348  pop     rbx
0x180024349  retn
0x18002434a  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x180024351  mov     ebx, 0Eh
0x180024356  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x18002435d  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x180024362  jmp     short loc_1800242FA
```
