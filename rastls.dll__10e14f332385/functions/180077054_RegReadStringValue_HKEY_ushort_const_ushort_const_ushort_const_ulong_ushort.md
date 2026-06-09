# RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)

- ea: `0x180077054`
- end: `0x1800771f8`
- name: `?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z`
- size: `420`
- prototype: `unsigned int __fastcall(HKEY hkey, LPCWSTR lpSubKey, const unsigned __int16 *, const unsigned __int16 *, DWORD, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180076f80`

## callees

- `0x18002cca4`
- `0x18002ce0c`
- `0x180076f54`
- `0x180077054`
- `0x180077200`
- `0x18007885c`
- `0x1800788d0`
- `0x18007890c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800770d9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180077182`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800770d9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180077182`

## string_xrefs

- `0x1800771b4`: `%s: Cannot read registry key value "%s@%s". Error code: 0x%08x.`
- `0x180077091`: `RegReadStringValue`
- `0x1800770f5`: `RegReadStringValue`
- `0x1800771ad`: `RegReadStringValue`
- `0x1800771de`: `RegReadStringValue`
- `0x180077125`: `%s: The registry key value "%s@%s" is not of one of the specified types (flags = 0x%08x). Using default value NULL.`
- `0x1800770ee`: `%s: The registry key value "%s@%s" does not exist. Using default value NULL. Error code: 0x%08x.`

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
0x180077054  mov     rax, rsp
0x180077057  push    rbx
0x180077058  push    rbp
0x180077059  push    rsi
0x18007705a  push    rdi
0x18007705b  push    r14
0x18007705d  push    r15
0x18007705f  sub     rsp, 58h
0x180077063  mov     rsi, [rsp+88h+arg_28]
0x18007706b  mov     rbp, r9
0x18007706e  mov     dword ptr [rax-48h], 0
0x180077075  mov     rdi, r8
0x180077078  mov     dword ptr [rax+28h], 0
0x18007707f  mov     r14, rdx
0x180077082  mov     r15, rcx
0x180077085  test    rsi, rsi
0x180077088  jnz     short loc_1800770AC
0x18007708a  lea     r8, aPdata; "pData"
0x180077091  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x180077098  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007709f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800770a4  lea     eax, [rsi+57h]
0x1800770a7  jmp     loc_1800771D1
0x1800770ac  lea     rax, [rsp+88h+arg_20]
0x1800770b4  mov     qword ptr [rsi], 0
0x1800770bb  mov     [rsp+88h+pcbData], rax; pcbData
0x1800770c0  mov     r9d, 2; dwFlags
0x1800770c6  lea     rax, [rsp+88h+var_48]
0x1800770cb  mov     [rsp+88h+pvData], 0; pvData
0x1800770d4  mov     [rsp+88h+pdwType], rax; pdwType
0x1800770d9  call    cs:__imp_RegGetValueW
0x1800770df  mov     ebx, eax
0x1800770e1  cmp     eax, 2
0x1800770e4  jnz     short loc_180077116
0x1800770e6  mov     rcx, rdi; unsigned __int16 *
0x1800770e9  call    ?GetRegValueName@@YAPEAGPEBG@Z; GetRegValueName(ushort const *)
0x1800770ee  lea     rcx, aSTheRegistryKe; "%s: The registry key value \"%s@%s\" do"...
0x1800770f5  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x1800770fc  mov     dword ptr [rsp+88h+pdwType], 2
0x180077104  mov     r8, rbp
0x180077107  mov     r9, rax
0x18007710a  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18007710f  xor     ebx, ebx
0x180077111  jmp     loc_1800771CF
0x180077116  cmp     eax, 65Eh
0x18007711b  jnz     short loc_18007712E
0x18007711d  mov     rcx, rdi; unsigned __int16 *
0x180077120  call    ?GetRegValueName@@YAPEAGPEBG@Z; GetRegValueName(ushort const *)
0x180077125  lea     rcx, aSTheRegistryKe_0; "%s: The registry key value \"%s@%s\" is"...
0x18007712c  jmp     short loc_1800770F5
0x18007712e  test    eax, eax
0x180077130  jz      short loc_180077139
0x180077132  cmp     eax, 0EAh
0x180077137  jnz     short loc_18007718E
0x180077139  mov     eax, [rsp+88h+arg_20]
0x180077140  test    eax, eax
0x180077142  jz      short loc_18007718A
0x180077144  mov     ecx, eax; unsigned __int64
0x180077146  call    ?SafeAlloc@@YAPEAX_K@Z; SafeAlloc(unsigned __int64)
0x18007714b  mov     [rsi], rax
0x18007714e  test    rax, rax
0x180077151  jz      loc_1800771DE
0x180077157  lea     rcx, [rsp+88h+arg_20]
0x18007715f  mov     r9d, 2; dwFlags
0x180077165  mov     [rsp+88h+pcbData], rcx; pcbData
0x18007716a  mov     r8, rdi; lpValue
0x18007716d  mov     [rsp+88h+pvData], rax; pvData
0x180077172  mov     rdx, r14; lpSubKey
0x180077175  lea     rax, [rsp+88h+var_48]
0x18007717a  mov     rcx, r15; hkey
0x18007717d  mov     [rsp+88h+pdwType], rax; pdwType
0x180077182  call    cs:__imp_RegGetValueW
0x180077188  mov     ebx, eax
0x18007718a  test    ebx, ebx
0x18007718c  jz      short loc_1800771CF
0x18007718e  mov     r9, rdi; unsigned __int16 *
0x180077191  mov     r8, rbp; unsigned __int16 *
0x180077194  mov     ecx, ebx; unsigned int
0x180077196  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG00@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *,ushort const *)
0x18007719b  mov     rcx, rdi; unsigned __int16 *
0x18007719e  call    ?GetRegValueName@@YAPEAGPEBG@Z; GetRegValueName(ushort const *)
0x1800771a3  mov     r9, rax
0x1800771a6  mov     dword ptr [rsp+88h+pdwType], ebx
0x1800771aa  mov     r8, rbp
0x1800771ad  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x1800771b4  lea     rcx, aSCannotReadReg; "%s: Cannot read registry key value \"%s"...
0x1800771bb  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x1800771c0  mov     rcx, [rsi]; void *
0x1800771c3  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800771c8  mov     qword ptr [rsi], 0
0x1800771cf  mov     eax, ebx
0x1800771d1  add     rsp, 58h
0x1800771d5  pop     r15
0x1800771d7  pop     r14
0x1800771d9  pop     rdi
0x1800771da  pop     rsi
0x1800771db  pop     rbp
0x1800771dc  pop     rbx
0x1800771dd  retn
0x1800771de  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x1800771e5  mov     ebx, 0Eh
0x1800771ea  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x1800771f1  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x1800771f6  jmp     short loc_18007718E
```
