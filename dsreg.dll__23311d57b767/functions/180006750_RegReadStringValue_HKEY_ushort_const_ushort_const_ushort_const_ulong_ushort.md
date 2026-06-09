# RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)

- ea: `0x180006750`
- end: `0x180006992`
- name: `?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z`
- size: `578`
- prototype: `unsigned int __fastcall(HKEY hkey, LPCWSTR lpSubKey, const unsigned __int16 *, const unsigned __int16 *, DWORD dwFlags, unsigned __int16 **)`
- caller_count: `8`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800049f0`
- `0x1800069a0`
- `0x1800097c0`
- `0x18003caac`
- `0x180041124`
- `0x18006dcfc`
- `0x18008b7c8`
- `0x180096214`

## callees

- `0x180005ba0`
- `0x180006750`
- `0x1800084f4`
- `0x180008530`
- `0x180009780`
- `0x18003334c`
- `0x18008cf68`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800067e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800067e3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800067f4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800067f4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800067b5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000682b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800067b5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000682b`

## string_xrefs

- `0x18000688d`: `RegReadStringValue`
- `0x1800068cb`: `RegReadStringValue`
- `0x1800068ed`: `RegReadStringValue`
- `0x180006927`: `RegReadStringValue`
- `0x18000696f`: `RegReadStringValue`
- `0x180006894`: `%s: The registry key value "%s@%s" is not of one of the specified types (flags = 0x%08x). Using default value NULL.`
- `0x1800068d2`: `%s: The registry key value "%s@%s" does not exist. Using default value NULL. Error code: 0x%08x.`
- `0x180006976`: `%s: Cannot read registry key value "%s@%s". Error code: 0x%08x.`

## pseudocode

```c
__int64 __fastcall RegReadStringValue(
        HKEY hkey,
        LPCWSTR lpSubKey,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        DWORD dwFlags,
        unsigned __int16 **a6)
{
  LSTATUS ValueW; // eax
  unsigned int v11; // ebx
  unsigned int v12; // ebx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *pvData; // rax
  BOOL v16; // eax
  const wchar_t *v17; // r9
  BOOL v18; // eax
  const wchar_t *v19; // r9
  int v20; // eax
  const wchar_t *v21; // r9
  LPDWORD pdwType; // [rsp+20h] [rbp-58h]
  SIZE_T dwBytes[7]; // [rsp+40h] [rbp-38h] BYREF

  dwBytes[0] = 0;
  if ( a6 )
  {
    *a6 = 0;
    ValueW = RegGetValueW(hkey, lpSubKey, a3, dwFlags, (LPDWORD)dwBytes + 1, 0, (LPDWORD)dwBytes);
    v11 = ValueW;
    if ( ValueW == 2 )
    {
      v18 = !a3 || !*a3;
      LODWORD(pdwType) = 2;
      v19 = L"(default)";
      if ( !v18 )
        v19 = a3;
      Logger::TraceWarning(
        (wchar_t *)L"%s: The registry key value \"%s@%s\" does not exist. Using default value NULL. Error code: 0x%08x.",
        L"RegReadStringValue",
        a4,
        v19,
        pdwType);
      return 0;
    }
    if ( ValueW == 1630 )
    {
      v16 = !a3 || !*a3;
      LODWORD(pdwType) = dwFlags;
      v17 = L"(default)";
      if ( !v16 )
        v17 = a3;
      Logger::TraceWarning(
        (wchar_t *)L"%s: The registry key value \"%s@%s\" is not of one of the specified types (flags = 0x%08x). Using def"
                    "ault value NULL.",
        L"RegReadStringValue",
        a4,
        v17,
        pdwType);
      return 0;
    }
    if ( ValueW && ValueW != 234 )
      goto LABEL_28;
    if ( LODWORD(dwBytes[0]) )
    {
      v12 = dwBytes[0];
      ProcessHeap = GetProcessHeap();
      pvData = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v12);
      *a6 = pvData;
      if ( !pvData )
      {
        v11 = 14;
        Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"RegReadStringValue");
        goto LABEL_28;
      }
      v11 = RegGetValueW(hkey, lpSubKey, a3, dwFlags, (LPDWORD)dwBytes + 1, pvData, (LPDWORD)dwBytes);
    }
    if ( !v11 )
      return v11;
LABEL_28:
    Logger::WriteRegistryFailureEvent(v11, L"RegGetValueW", a4, a3);
    v20 = IsEmptyString(a3);
    LODWORD(pdwType) = v11;
    v21 = L"(default)";
    if ( !v20 )
      v21 = a3;
    Logger::TraceWarning(
      (wchar_t *)L"%s: Cannot read registry key value \"%s@%s\". Error code: 0x%08x.",
      L"RegReadStringValue",
      a4,
      v21,
      pdwType);
    SafeFree(*a6);
    *a6 = 0;
    return v11;
  }
  Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegReadStringValue", L"pData");
  return 87;
}

```

## disassembly

```asm
0x180006750  mov     r11, rsp
0x180006753  mov     [r11+18h], rbp
0x180006757  push    rsi
0x180006758  push    rdi
0x180006759  push    r12
0x18000675b  push    r13
0x18000675d  push    r14
0x18000675f  sub     rsp, 50h
0x180006763  mov     rdi, [rsp+78h+arg_28]
0x18000676b  xor     r13d, r13d
0x18000676e  mov     [r11-34h], r13d
0x180006772  mov     r12, r9
0x180006775  mov     [r11-38h], r13d
0x180006779  mov     rsi, r8
0x18000677c  mov     rbp, rdx
0x18000677f  mov     r14, rcx
0x180006782  test    rdi, rdi
0x180006785  jz      loc_1800068E6
0x18000678b  lea     rax, [r11-38h]
0x18000678f  mov     [r11+8], rbx
0x180006793  mov     [r11-48h], rax
0x180006797  lea     rax, [r11-34h]
0x18000679b  mov     [r11+10h], r15
0x18000679f  mov     r15d, [rsp+78h+dwFlags]
0x1800067a7  mov     r9d, r15d; dwFlags
0x1800067aa  mov     [r11-50h], r13
0x1800067ae  mov     [r11-58h], rax
0x1800067b2  mov     [rdi], r13
0x1800067b5  call    cs:__imp_RegGetValueW
0x1800067bb  mov     ebx, eax
0x1800067bd  cmp     eax, 2
0x1800067c0  jz      loc_1800068A5
0x1800067c6  cmp     eax, 65Eh
0x1800067cb  jz      loc_180006862
0x1800067d1  test    eax, eax
0x1800067d3  jnz     loc_18000691B
0x1800067d9  mov     eax, dword ptr [rsp+78h+dwBytes]
0x1800067dd  test    eax, eax
0x1800067df  jz      short loc_180006833
0x1800067e1  mov     ebx, eax
0x1800067e3  call    cs:__imp_GetProcessHeap
0x1800067e9  mov     r8d, ebx; dwBytes
0x1800067ec  mov     edx, 8; dwFlags
0x1800067f1  mov     rcx, rax; hHeap
0x1800067f4  call    cs:__imp_HeapAlloc
0x1800067fa  mov     [rdi], rax
0x1800067fd  test    rax, rax
0x180006800  jz      loc_180006927
0x180006806  lea     rcx, [rsp+78h+dwBytes]
0x18000680b  mov     r9d, r15d; dwFlags
0x18000680e  mov     [rsp+78h+pcbData], rcx; pcbData
0x180006813  mov     r8, rsi; lpValue
0x180006816  mov     [rsp+78h+pvData], rax; pvData
0x18000681b  mov     rdx, rbp; lpSubKey
0x18000681e  lea     rax, [rsp+78h+dwBytes+4]
0x180006823  mov     rcx, r14; hkey
0x180006826  mov     [rsp+78h+pdwType], rax; pdwType
0x18000682b  call    cs:__imp_RegGetValueW
0x180006831  mov     ebx, eax
0x180006833  test    ebx, ebx
0x180006835  jnz     loc_18000693F
0x18000683b  mov     r15, [rsp+78h+arg_8]
0x180006843  mov     eax, ebx
0x180006845  mov     rbx, [rsp+78h+arg_0]
0x18000684d  mov     rbp, [rsp+78h+arg_10]
0x180006855  add     rsp, 50h
0x180006859  pop     r14
0x18000685b  pop     r13
0x18000685d  pop     r12
0x18000685f  pop     rdi
0x180006860  pop     rsi
0x180006861  retn
0x180006862  test    rsi, rsi
0x180006865  jz      loc_180006911
0x18000686b  cmp     [rsi], r13w
0x18000686f  jz      loc_180006911
0x180006875  mov     eax, r13d
0x180006878  test    eax, eax
0x18000687a  mov     dword ptr [rsp+78h+pdwType], r15d
0x18000687f  lea     r9, aDefault; "(default)"
0x180006886  mov     r8, r12
0x180006889  cmovz   r9, rsi
0x18000688d  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x180006894  lea     rcx, aSTheRegistryKe_6; "%s: The registry key value \"%s@%s\" is"...
0x18000689b  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x1800068a0  mov     ebx, r13d
0x1800068a3  jmp     short loc_18000683B
0x1800068a5  test    rsi, rsi
0x1800068a8  jz      short loc_18000690A
0x1800068aa  cmp     [rsi], r13w
0x1800068ae  jz      short loc_18000690A
0x1800068b0  mov     eax, r13d
0x1800068b3  test    eax, eax
0x1800068b5  mov     dword ptr [rsp+78h+pdwType], 2
0x1800068bd  lea     r9, aDefault; "(default)"
0x1800068c4  mov     r8, r12
0x1800068c7  cmovz   r9, rsi
0x1800068cb  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x1800068d2  lea     rcx, aSTheRegistryKe; "%s: The registry key value \"%s@%s\" do"...
0x1800068d9  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x1800068de  mov     ebx, r13d
0x1800068e1  jmp     loc_18000683B
0x1800068e6  lea     r8, aPdata; "pData"
0x1800068ed  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x1800068f4  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800068fb  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180006900  mov     eax, 57h ; 'W'
0x180006905  jmp     loc_18000684D
0x18000690a  mov     eax, 1
0x18000690f  jmp     short loc_1800068B3
0x180006911  mov     eax, 1
0x180006916  jmp     loc_180006878
0x18000691b  cmp     eax, 0EAh
0x180006920  jnz     short loc_18000693F
0x180006922  jmp     loc_1800067D9
0x180006927  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x18000692e  mov     ebx, 0Eh
0x180006933  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x18000693a  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18000693f  mov     r9, rsi; unsigned __int16 *
0x180006942  lea     rdx, aReggetvaluew; "RegGetValueW"
0x180006949  mov     r8, r12; unsigned __int16 *
0x18000694c  mov     ecx, ebx; unsigned int
0x18000694e  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG00@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *,ushort const *)
0x180006953  mov     rcx, rsi; unsigned __int16 *
0x180006956  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18000695b  test    eax, eax
0x18000695d  mov     dword ptr [rsp+78h+pdwType], ebx
0x180006961  lea     r9, aDefault; "(default)"
0x180006968  mov     r8, r12
0x18000696b  cmovz   r9, rsi
0x18000696f  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x180006976  lea     rcx, aSCannotReadReg_0; "%s: Cannot read registry key value \"%s"...
0x18000697d  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180006982  mov     rcx, [rdi]; lpMem
0x180006985  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000698a  mov     [rdi], r13
0x18000698d  jmp     loc_18000683B
```
