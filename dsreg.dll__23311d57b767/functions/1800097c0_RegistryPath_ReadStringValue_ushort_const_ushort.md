# RegistryPath::ReadStringValue(ushort const *,ushort * *)

- ea: `0x1800097c0`
- end: `0x180009a3c`
- name: `?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z`
- size: `636`
- prototype: `unsigned int(RegistryPath *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `8`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180004218`
- `0x180008d80`
- `0x180039290`
- `0x18005f7fc`
- `0x180096ad4`
- `0x180096d08`
- `0x18009716c`
- `0x1800b31f4`

## callees

- `0x180005ba0`
- `0x180006450`
- `0x180006750`
- `0x1800084f4`
- `0x180008530`
- `0x180009780`
- `0x1800097c0`
- `0x18003334c`
- `0x18008cf68`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009871`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009871`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009882`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009882`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180009843`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800098be`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180009843`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800098be`

## string_xrefs

- `0x180009926`: `RegReadStringValue`
- `0x18000995e`: `RegReadStringValue`
- `0x180009980`: `RegReadStringValue`
- `0x1800099a9`: `RegReadStringValue`
- `0x1800099f1`: `RegReadStringValue`
- `0x1800098eb`: `%s: This path object has not been properly initiliazed. Either root key or full path is NULL.`
- `0x18000992d`: `%s: The registry key value "%s@%s" is not of one of the specified types (flags = 0x%08x). Using default value NULL.`
- `0x1800098e4`: `RegistryPath::ReadStringValue`
- `0x180009965`: `%s: The registry key value "%s@%s" does not exist. Using default value NULL. Error code: 0x%08x.`
- `0x1800099f8`: `%s: Cannot read registry key value "%s@%s". Error code: 0x%08x.`

## pseudocode

```c
unsigned int __fastcall RegistryPath::ReadStringValue(
        RegistryPath *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  const unsigned __int16 *v5; // rdi
  HKEY v6; // rsi
  LSTATUS ValueW; // eax
  LSTATUS v8; // ebx
  unsigned int v9; // ebx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *pvData; // rax
  int v13; // eax
  const wchar_t *v14; // r9
  int v15; // eax
  const wchar_t *v16; // r9
  int v17; // eax
  const wchar_t *v18; // r9
  const WCHAR *v19; // rax
  HKEY v20; // r10
  LPDWORD pdwType; // [rsp+20h] [rbp-48h]
  SIZE_T dwBytes; // [rsp+70h] [rbp+8h] BYREF
  DWORD v23; // [rsp+88h] [rbp+20h] BYREF

  if ( *((_QWORD *)this + 4) && (v5 = *(const unsigned __int16 **)this) != 0 && *v5 )
  {
    v6 = (HKEY)*((_QWORD *)this + 5);
    if ( v6 )
    {
      v23 = 0;
      LODWORD(dwBytes) = 0;
      if ( !a3 )
      {
        Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegReadStringValue", L"pData");
        return 87;
      }
      *a3 = 0;
      ValueW = RegGetValueW(v6, 0, a2, 2u, &v23, 0, (LPDWORD)&dwBytes);
      v8 = ValueW;
      switch ( ValueW )
      {
        case 2:
          v15 = IsEmptyString(a2);
          LODWORD(pdwType) = 2;
          v16 = L"(default)";
          if ( !v15 )
            v16 = a2;
          Logger::TraceWarning(
            (wchar_t *)L"%s: The registry key value \"%s@%s\" does not exist. Using default value NULL. Error code: 0x%08x.",
            L"RegReadStringValue",
            v5,
            v16,
            pdwType);
          return 0;
        case 1630:
          v13 = IsEmptyString(a2);
          LODWORD(pdwType) = 2;
          v14 = L"(default)";
          if ( !v13 )
            v14 = a2;
          Logger::TraceWarning(
            (wchar_t *)L"%s: The registry key value \"%s@%s\" is not of one of the specified types (flags = 0x%08x). Using"
                        " default value NULL.",
            L"RegReadStringValue",
            v5,
            v14,
            pdwType);
          return 0;
        case 0:
        case 234:
          if ( (_DWORD)dwBytes )
          {
            v9 = dwBytes;
            ProcessHeap = GetProcessHeap();
            pvData = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v9);
            *a3 = pvData;
            if ( !pvData )
            {
              v8 = 14;
              Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"RegReadStringValue");
              break;
            }
            v8 = RegGetValueW(v6, 0, a2, 2u, &v23, pvData, (LPDWORD)&dwBytes);
          }
          if ( !v8 )
            return v8;
          break;
      }
      Logger::WriteRegistryFailureEvent(v8, L"RegGetValueW", v5, a2);
      v17 = IsEmptyString(a2);
      LODWORD(pdwType) = v8;
      v18 = L"(default)";
      if ( !v17 )
        v18 = a2;
      Logger::TraceWarning(
        (wchar_t *)L"%s: Cannot read registry key value \"%s@%s\". Error code: 0x%08x.",
        L"RegReadStringValue",
        v5,
        v18,
        pdwType);
      SafeFree(*a3);
      *a3 = 0;
      return v8;
    }
    v19 = RegistryPath::SubPath(this);
    return RegReadStringValue(v20, v19, a2, v5, 2u, a3);
  }
  else
  {
    Logger::TraceError(
      L"%s: This path object has not been properly initiliazed. Either root key or full path is NULL.",
      L"RegistryPath::ReadStringValue");
    return 87;
  }
}

```

## disassembly

```asm
0x1800097c0  mov     r11, rsp
0x1800097c3  push    rbx
0x1800097c4  push    rbp
0x1800097c5  push    rdi
0x1800097c6  push    r14
0x1800097c8  sub     rsp, 48h
0x1800097cc  mov     r10, [rcx+20h]
0x1800097d0  mov     r14, r8
0x1800097d3  mov     rbp, rdx
0x1800097d6  test    r10, r10
0x1800097d9  jz      loc_1800098E4
0x1800097df  mov     rdi, [rcx]
0x1800097e2  test    rdi, rdi
0x1800097e5  jz      loc_1800098E4
0x1800097eb  cmp     word ptr [rdi], 0
0x1800097ef  jz      loc_1800098E4
0x1800097f5  mov     [r11+10h], rsi
0x1800097f9  mov     rsi, [rcx+28h]
0x1800097fd  test    rsi, rsi
0x180009800  jz      loc_180009A14
0x180009806  mov     [r11-28h], r15
0x18000980a  xor     r15d, r15d
0x18000980d  mov     [r11+20h], r15d
0x180009811  mov     [r11+8], r15d
0x180009815  test    r8, r8
0x180009818  jz      loc_180009979
0x18000981e  lea     rax, [r11+8]
0x180009822  mov     [r8], r15
0x180009825  mov     [r11-38h], rax
0x180009829  mov     r8, rdx; lpValue
0x18000982c  lea     rax, [r11+20h]
0x180009830  mov     [r11-40h], r15
0x180009834  mov     r9d, 2; dwFlags
0x18000983a  mov     [r11-48h], rax
0x18000983e  xor     edx, edx; lpSubKey
0x180009840  mov     rcx, rsi; hkey
0x180009843  call    cs:__imp_RegGetValueW
0x180009849  mov     ebx, eax
0x18000984b  cmp     eax, 2
0x18000984e  jz      loc_18000993E
0x180009854  cmp     eax, 65Eh
0x180009859  jz      loc_180009906
0x18000985f  test    eax, eax
0x180009861  jnz     loc_18000999D
0x180009867  mov     eax, dword ptr [rsp+68h+dwBytes]
0x18000986b  test    eax, eax
0x18000986d  jz      short loc_1800098C6
0x18000986f  mov     ebx, eax
0x180009871  call    cs:__imp_GetProcessHeap
0x180009877  mov     r8d, ebx; dwBytes
0x18000987a  mov     edx, 8; dwFlags
0x18000987f  mov     rcx, rax; hHeap
0x180009882  call    cs:__imp_HeapAlloc
0x180009888  mov     [r14], rax
0x18000988b  test    rax, rax
0x18000988e  jz      loc_1800099A9
0x180009894  lea     rcx, [rsp+68h+dwBytes]
0x180009899  mov     r9d, 2; dwFlags
0x18000989f  mov     [rsp+68h+pcbData], rcx; pcbData
0x1800098a4  mov     r8, rbp; lpValue
0x1800098a7  mov     [rsp+68h+pvData], rax; pvData
0x1800098ac  xor     edx, edx; lpSubKey
0x1800098ae  lea     rax, [rsp+68h+arg_18]
0x1800098b6  mov     rcx, rsi; hkey
0x1800098b9  mov     [rsp+68h+pdwType], rax; pdwType
0x1800098be  call    cs:__imp_RegGetValueW
0x1800098c4  mov     ebx, eax
0x1800098c6  test    ebx, ebx
0x1800098c8  jnz     loc_1800099C1
0x1800098ce  mov     r15, [rsp+68h+var_28]
0x1800098d3  mov     eax, ebx
0x1800098d5  mov     rsi, [rsp+68h+arg_8]
0x1800098da  add     rsp, 48h
0x1800098de  pop     r14
0x1800098e0  pop     rdi
0x1800098e1  pop     rbp
0x1800098e2  pop     rbx
0x1800098e3  retn
0x1800098e4  lea     rdx, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x1800098eb  lea     rcx, aSThisPathObjec; "%s: This path object has not been prope"...
0x1800098f2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800098f7  mov     eax, 57h ; 'W'
0x1800098fc  add     rsp, 48h
0x180009900  pop     r14
0x180009902  pop     rdi
0x180009903  pop     rbp
0x180009904  pop     rbx
0x180009905  retn
0x180009906  mov     rcx, rbp; unsigned __int16 *
0x180009909  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18000990e  test    eax, eax
0x180009910  mov     dword ptr [rsp+68h+pdwType], 2
0x180009918  lea     r9, aDefault; "(default)"
0x18000991f  mov     r8, rdi
0x180009922  cmovz   r9, rbp
0x180009926  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x18000992d  lea     rcx, aSTheRegistryKe_6; "%s: The registry key value \"%s@%s\" is"...
0x180009934  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180009939  mov     ebx, r15d
0x18000993c  jmp     short loc_1800098CE
0x18000993e  mov     rcx, rbp; unsigned __int16 *
0x180009941  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180009946  test    eax, eax
0x180009948  mov     dword ptr [rsp+68h+pdwType], 2
0x180009950  lea     r9, aDefault; "(default)"
0x180009957  mov     r8, rdi
0x18000995a  cmovz   r9, rbp
0x18000995e  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x180009965  lea     rcx, aSTheRegistryKe; "%s: The registry key value \"%s@%s\" do"...
0x18000996c  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180009971  mov     ebx, r15d
0x180009974  jmp     loc_1800098CE
0x180009979  lea     r8, aPdata; "pData"
0x180009980  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x180009987  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18000998e  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180009993  mov     ebx, 57h ; 'W'
0x180009998  jmp     loc_1800098CE
0x18000999d  cmp     eax, 0EAh
0x1800099a2  jnz     short loc_1800099C1
0x1800099a4  jmp     loc_180009867
0x1800099a9  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x1800099b0  mov     ebx, 0Eh
0x1800099b5  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x1800099bc  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x1800099c1  mov     r9, rbp; unsigned __int16 *
0x1800099c4  lea     rdx, aReggetvaluew; "RegGetValueW"
0x1800099cb  mov     r8, rdi; unsigned __int16 *
0x1800099ce  mov     ecx, ebx; unsigned int
0x1800099d0  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG00@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *,ushort const *)
0x1800099d5  mov     rcx, rbp; unsigned __int16 *
0x1800099d8  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x1800099dd  test    eax, eax
0x1800099df  mov     dword ptr [rsp+68h+pdwType], ebx
0x1800099e3  lea     r9, aDefault; "(default)"
0x1800099ea  mov     r8, rdi
0x1800099ed  cmovz   r9, rbp
0x1800099f1  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x1800099f8  lea     rcx, aSCannotReadReg_0; "%s: Cannot read registry key value \"%s"...
0x1800099ff  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180009a04  mov     rcx, [r14]; lpMem
0x180009a07  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180009a0c  mov     [r14], r15
0x180009a0f  jmp     loc_1800098CE
0x180009a14  call    ?SubPath@RegistryPath@@QEBAPEBGXZ; RegistryPath::SubPath(void)
0x180009a19  mov     rdx, rax; lpSubKey
0x180009a1c  mov     [rsp+68h+pvData], r14; unsigned __int16 **
0x180009a21  mov     r9, rdi; unsigned __int16 *
0x180009a24  mov     dword ptr [rsp+68h+pdwType], 2; dwFlags
0x180009a2c  mov     r8, rbp; unsigned __int16 *
0x180009a2f  mov     rcx, r10; hkey
0x180009a32  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x180009a37  jmp     loc_1800098D5
```
