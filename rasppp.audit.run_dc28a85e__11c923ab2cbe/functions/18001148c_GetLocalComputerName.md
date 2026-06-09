# GetLocalComputerName

- ea: `0x18001148c`
- end: `0x180011597`
- name: `GetLocalComputerName`
- size: `267`
- prototype: `__int64 __fastcall(STRSAFE_LPSTR pszDest)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180016260`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x18001148c`
- `0x180014ac0`
- `0x18002b0dc`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameA` at `0x1800114d7`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameA` at `0x1800114d7`

## string_xrefs

- `0x180011519`: `GetLocalComputerName: StringCchPrintfA Failed`

## pseudocode

```c
int __fastcall GetLocalComputerName(STRSAFE_LPSTR pszDest)
{
  int result; // eax
  DWORD nSize; // [rsp+30h] [rbp-848h] BYREF
  CHAR Buffer[40]; // [rsp+38h] [rbp-840h] BYREF
  int v5; // [rsp+60h] [rbp-818h] BYREF
  _BYTE v6[2044]; // [rsp+64h] [rbp-814h] BYREF

  v5 = 0;
  memset_0(v6, 0, sizeof(v6));
  *pszDest = 0;
  nSize = 25;
  result = GetComputerNameA(Buffer, &nSize);
  if ( !result )
    goto LABEL_5;
  result = StringCchPrintfA(pszDest, 0x19u, "%hs%hs", "MSRAS-0-", Buffer);
  if ( result < 0 )
  {
    if ( byte_18004DF33 < 0 )
      result = McTemplateU0z_EventWriteTransfer(
                 &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                 RasPppTraceError,
                 L"GetLocalComputerName: StringCchPrintfA Failed");
LABEL_5:
    *pszDest = 0;
    return result;
  }
  if ( (byte_18004DF34 & 1) != 0 )
  {
    LOWORD(v5) = 0;
    result = FormatRRASErrorString(&v5, L"Local identification = %hs", pszDest);
    if ( (byte_18004DF34 & 1) != 0 )
      return McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v5);
  }
  return result;
}

```

## disassembly

```asm
0x18001148c  push    rbx
0x18001148e  sub     rsp, 870h
0x180011495  mov     rax, cs:__security_cookie
0x18001149c  xor     rax, rsp
0x18001149f  mov     [rsp+878h+var_18], rax
0x1800114a7  mov     rbx, rcx
0x1800114aa  xor     eax, eax
0x1800114ac  lea     rcx, [rsp+878h+var_814]; void *
0x1800114b1  mov     [rsp+878h+var_818], eax
0x1800114b5  xor     edx, edx; Val
0x1800114b7  mov     r8d, 7FCh; Size
0x1800114bd  call    memset_0
0x1800114c2  lea     rdx, [rsp+878h+nSize]; nSize
0x1800114c7  mov     byte ptr [rbx], 0
0x1800114ca  lea     rcx, [rsp+878h+Buffer]; lpBuffer
0x1800114cf  mov     [rsp+878h+nSize], 19h
0x1800114d7  call    cs:__imp_GetComputerNameA
0x1800114de  nop     dword ptr [rax+rax+00h]
0x1800114e3  test    eax, eax
0x1800114e5  jz      short loc_180011533
0x1800114e7  lea     rax, [rsp+878h+Buffer]
0x1800114ec  mov     edx, 19h; cchDest
0x1800114f1  lea     r9, SubStr; "MSRAS-0-"
0x1800114f8  mov     [rsp+878h+var_858], rax
0x1800114fd  lea     r8, pszFormat; "%hs%hs"
0x180011504  mov     rcx, rbx; pszDest
0x180011507  call    StringCchPrintfA
0x18001150c  test    eax, eax
0x18001150e  jns     short loc_180011550
0x180011510  test    cs:byte_18004DF33, 80h
0x180011517  jz      short loc_180011533
0x180011519  lea     r8, aGetlocalcomput; "GetLocalComputerName: StringCchPrintfA "...
0x180011520  lea     rdx, RasPppTraceError
0x180011527  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001152e  call    McTemplateU0z_EventWriteTransfer
0x180011533  mov     byte ptr [rbx], 0
0x180011536  mov     rcx, [rsp+878h+var_18]
0x18001153e  xor     rcx, rsp; StackCookie
0x180011541  call    __security_check_cookie
0x180011546  add     rsp, 870h
0x18001154d  pop     rbx
0x18001154e  retn
0x180011550  test    cs:byte_18004DF34, 1
0x180011557  jz      short loc_180011536
0x180011559  xor     eax, eax
0x18001155b  lea     rdx, aLocalIdentific; "Local identification = %hs"
0x180011562  mov     r8, rbx
0x180011565  mov     word ptr [rsp+878h+var_818], ax
0x18001156a  lea     rcx, [rsp+878h+var_818]
0x18001156f  call    FormatRRASErrorString
0x180011574  test    cs:byte_18004DF34, 1
0x18001157b  jz      short loc_180011536
0x18001157d  lea     r8, [rsp+878h+var_818]
0x180011582  lea     rdx, RasPppTraceInfo
0x180011589  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180011590  call    McTemplateU0z_EventWriteTransfer
0x180011595  jmp     short loc_180011536
```
