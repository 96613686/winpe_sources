# SetFederatedSecurity

- ea: `0x18002c5cc`
- end: `0x18002c74f`
- name: `SetFederatedSecurity`
- size: `387`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002c808`

## callees

- `0x1800141b0`
- `0x18002b0ac`
- `0x18002c5cc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c688`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c737`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c688`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c737`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c674`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c723`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c674`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c723`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c6d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c6d5`
- `DMCmnUtils!EncodeBase64W` at `0x18002c6a7`
- `DMCmnUtils!EncodeBase64W` at `0x18002c6a7`
- `DMCmnUtils!UnicodeToMB` at `0x18002c64c`
- `DMCmnUtils!UnicodeToMB` at `0x18002c64c`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c6eb`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c6f9`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c6eb`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c6f9`

## string_xrefs

- `0x18002c5fd`: `SetFederatedSecurity`
- `0x18002c6be`: `//wsse:BinarySecurityToken`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SetFederatedSecurity(struct IXMLDOMDocument2 *a1, const unsigned __int16 *a2)
{
  void *v2; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int v4; // edi
  void *v5; // rbx
  HANDLE v6; // rax
  LPVOID lpMem[2]; // [rsp+20h] [rbp-40h] BYREF
  _QWORD v9[2]; // [rsp+30h] [rbp-30h] BYREF
  LPVOID *v10; // [rsp+40h] [rbp-20h]
  char *v11; // [rsp+48h] [rbp-18h] BYREF
  char v12; // [rsp+50h] [rbp-10h]
  struct IXMLDOMDocument2 *v13; // [rsp+80h] [rbp+20h] BYREF
  int v14; // [rsp+88h] [rbp+28h] BYREF
  unsigned int v15; // [rsp+90h] [rbp+30h] BYREF
  HLOCAL hMem; // [rsp+98h] [rbp+38h] BYREF

  v13 = a1;
  v14 = 0;
  lpMem[1] = 0;
  hMem = 0;
  lpMem[0] = 0;
  v9[0] = "SetFederatedSecurity";
  v9[1] = &v14;
  if ( a2 )
  {
    v15 = 0;
    v10 = lpMem;
    v11 = 0;
    v12 = 1;
    v14 = UnicodeToMB(a2, 0xFDE9u, &v11, &v15);
    if ( v12 )
    {
      v2 = *v10;
      *v10 = v11;
      if ( v2 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v2);
      }
    }
    if ( v14 >= 0 )
    {
      v14 = EncodeBase64W((const unsigned __int8 *)lpMem[0], v15 - 1, (unsigned __int16 **)&hMem);
      if ( v14 >= 0 )
        v14 = HlpSetNodeString(&v13, L"//wsse:BinarySecurityToken", (const unsigned __int16 *)hMem);
    }
  }
  else
  {
    v14 = -2147024809;
  }
  LocalFree(hMem);
  hMem = 0;
  SysFreeString(0);
  SysFreeString(0);
  v4 = v14;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v9);
  v5 = lpMem[0];
  lpMem[0] = 0;
  if ( v5 )
  {
    v6 = GetProcessHeap();
    HeapFree(v6, 0, v5);
  }
  return v4;
}

```

## disassembly

```asm
0x18002c5cc  mov     [rsp-18h+arg_0], rcx
0x18002c5d1  push    rbp
0x18002c5d2  push    rbx
0x18002c5d3  push    rdi
0x18002c5d4  mov     rbp, rsp
0x18002c5d7  sub     rsp, 60h
0x18002c5db  mov     rax, rdx
0x18002c5de  mov     [rbp+arg_8], 0
0x18002c5e5  mov     [rbp+var_38], 0
0x18002c5ed  mov     [rbp+hMem], 0
0x18002c5f5  mov     [rbp+lpMem], 0
0x18002c5fd  lea     rcx, aSetfederatedse; "SetFederatedSecurity"
0x18002c604  mov     [rbp+var_30], rcx
0x18002c608  lea     rcx, [rbp+arg_8]
0x18002c60c  mov     [rbp+var_28], rcx
0x18002c610  test    rdx, rdx
0x18002c613  jnz     short loc_18002C621
0x18002c615  mov     [rbp+arg_8], 80070057h
0x18002c61c  jmp     loc_18002C6D1
0x18002c621  mov     [rbp+arg_10], 0
0x18002c628  lea     rcx, [rbp+lpMem]
0x18002c62c  mov     [rbp+var_20], rcx
0x18002c630  mov     [rbp+var_18], 0
0x18002c638  mov     [rbp+var_10], 1
0x18002c63c  lea     r9, [rbp+arg_10]
0x18002c640  lea     r8, [rbp+var_18]
0x18002c644  mov     edx, 0FDE9h
0x18002c649  mov     rcx, rax
0x18002c64c  call    cs:__imp_?UnicodeToMB@@YAJPEBGIPEAPEADPEAK@Z; UnicodeToMB(ushort const *,uint,char * *,ulong *)
0x18002c653  nop     dword ptr [rax+rax+00h]
0x18002c658  mov     [rbp+arg_8], eax
0x18002c65b  cmp     [rbp+var_10], 0
0x18002c65f  jz      short loc_18002C694
0x18002c661  mov     rcx, [rbp+var_20]
0x18002c665  mov     rbx, [rcx]
0x18002c668  mov     rax, [rbp+var_18]
0x18002c66c  mov     [rcx], rax
0x18002c66f  test    rbx, rbx
0x18002c672  jz      short loc_18002C694
0x18002c674  call    cs:__imp_GetProcessHeap
0x18002c67b  nop     dword ptr [rax+rax+00h]
0x18002c680  mov     rcx, rax; hHeap
0x18002c683  mov     r8, rbx; lpMem
0x18002c686  xor     edx, edx; dwFlags
0x18002c688  call    cs:__imp_HeapFree
0x18002c68f  nop     dword ptr [rax+rax+00h]
0x18002c694  cmp     [rbp+arg_8], 0
0x18002c698  jl      short loc_18002C6D1
0x18002c69a  mov     edx, [rbp+arg_10]
0x18002c69d  dec     edx
0x18002c69f  lea     r8, [rbp+hMem]
0x18002c6a3  mov     rcx, [rbp+lpMem]
0x18002c6a7  call    cs:__imp_?EncodeBase64W@@YAJPEBEHPEAPEAG@Z; EncodeBase64W(uchar const *,int,ushort * *)
0x18002c6ae  nop     dword ptr [rax+rax+00h]
0x18002c6b3  mov     [rbp+arg_8], eax
0x18002c6b6  test    eax, eax
0x18002c6b8  js      short loc_18002C6D1
0x18002c6ba  mov     r8, [rbp+hMem]; unsigned __int16 *
0x18002c6be  lea     rdx, aWsseBinarysecu; "//wsse:BinarySecurityToken"
0x18002c6c5  lea     rcx, [rbp+arg_0]; struct IXMLDOMDocument2 **
0x18002c6c9  call    ?HlpSetNodeString@@YAJPEAPEAUIXMLDOMDocument2@@PEBG1@Z; HlpSetNodeString(IXMLDOMDocument2 * *,ushort const *,ushort const *)
0x18002c6ce  mov     [rbp+arg_8], eax
0x18002c6d1  mov     rcx, [rbp+hMem]; hMem
0x18002c6d5  call    cs:__imp_LocalFree
0x18002c6dc  nop     dword ptr [rax+rax+00h]
0x18002c6e1  mov     [rbp+hMem], 0
0x18002c6e9  xor     ecx, ecx; bstrString
0x18002c6eb  call    cs:__imp_SysFreeString
0x18002c6f2  nop     dword ptr [rax+rax+00h]
0x18002c6f7  xor     ecx, ecx; bstrString
0x18002c6f9  call    cs:__imp_SysFreeString
0x18002c700  nop     dword ptr [rax+rax+00h]
0x18002c705  mov     edi, [rbp+arg_8]
0x18002c708  lea     rcx, [rbp+var_30]; this
0x18002c70c  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18002c711  nop
0x18002c712  mov     rbx, [rbp+lpMem]
0x18002c716  mov     [rbp+lpMem], 0
0x18002c71e  test    rbx, rbx
0x18002c721  jz      short loc_18002C744
0x18002c723  call    cs:__imp_GetProcessHeap
0x18002c72a  nop     dword ptr [rax+rax+00h]
0x18002c72f  mov     rcx, rax; hHeap
0x18002c732  mov     r8, rbx; lpMem
0x18002c735  xor     edx, edx; dwFlags
0x18002c737  call    cs:__imp_HeapFree
0x18002c73e  nop     dword ptr [rax+rax+00h]
0x18002c743  nop
0x18002c744  mov     eax, edi
0x18002c746  add     rsp, 60h
0x18002c74a  pop     rdi
0x18002c74b  pop     rbx
0x18002c74c  pop     rbp
0x18002c74d  retn
```
