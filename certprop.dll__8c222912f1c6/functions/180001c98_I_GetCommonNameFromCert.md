# I_GetCommonNameFromCert

- ea: `0x180001c98`
- end: `0x180001e84`
- name: `I_GetCommonNameFromCert`
- size: `492`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, WCHAR **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002aa0`

## callees

- `0x180001c98`
- `0x180004600`
- `0x180018b58`
- `0x180018bb4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001d37`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001ded`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001d37`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001ded`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e2c`
- `CRYPT32!CertGetNameStringW` at `0x180001d11`
- `CRYPT32!CertGetNameStringW` at `0x180001da7`
- `CRYPT32!CertGetNameStringW` at `0x180001dd0`
- `CRYPT32!CertGetNameStringW` at `0x180001d11`
- `CRYPT32!CertGetNameStringW` at `0x180001da7`
- `CRYPT32!CertGetNameStringW` at `0x180001dd0`

## pseudocode

```c
__int64 __fastcall I_GetCommonNameFromCert(PCCERT_CONTEXT pCertContext, WCHAR **a2)
{
  DWORD NameStringW; // eax
  DWORD LastError; // ebx
  DWORD cchNameString; // esi
  WCHAR *pszNameString; // rax
  __int64 v8; // rcx
  STRSAFE_LPSTR v9; // rcx
  __int64 v10; // rdx
  DWORD v11; // edx
  DWORD v12; // eax
  __int64 v13; // rcx

  WppTraceIndent(pCertContext, 0);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  *a2 = 0;
  NameStringW = CertGetNameStringW(pCertContext, 4u, 0, 0, 0, 0);
  LastError = 8;
  cchNameString = NameStringW;
  if ( NameStringW != 1 )
  {
    pszNameString = (WCHAR *)HeapAlloc(hHeap, 8u, 2LL * (NameStringW + 1));
    *a2 = pszNameString;
    if ( !pszNameString )
    {
      WppTraceIndent(v8, 2);
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
      {
        v10 = 21;
LABEL_11:
        WPP_SF_s(*((_QWORD *)v9 + 2), v10, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
        goto LABEL_23;
      }
      goto LABEL_23;
    }
    v11 = 4;
    goto LABEL_13;
  }
  v12 = CertGetNameStringW(pCertContext, 8u, 0, 0, 0, 0);
  cchNameString = v12;
  if ( v12 == 1 )
    goto LABEL_22;
  pszNameString = (WCHAR *)HeapAlloc(hHeap, 8u, 2LL * (v12 + 1));
  *a2 = pszNameString;
  if ( pszNameString )
  {
    v11 = 8;
LABEL_13:
    if ( CertGetNameStringW(pCertContext, v11, 0, 0, pszNameString, cchNameString) != 1 )
    {
      LastError = 0;
      goto LABEL_23;
    }
LABEL_22:
    LastError = GetLastError();
    goto LABEL_23;
  }
  WppTraceIndent(v13, 2);
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
  {
    v10 = 22;
    goto LABEL_11;
  }
LABEL_23:
  WppTraceIndent(v9, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x180001c98  push    rbx
0x180001c9a  push    rsi
0x180001c9b  push    rdi
0x180001c9c  push    r13
0x180001c9e  push    r14
0x180001ca0  sub     rsp, 30h
0x180001ca4  mov     r14, rdx
0x180001ca7  mov     rdi, rcx
0x180001caa  xor     edx, edx
0x180001cac  call    WppTraceIndent
0x180001cb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180001cb8  lea     r13, WPP_GLOBAL_Control
0x180001cbf  cmp     rcx, r13
0x180001cc2  jz      short loc_180001CEC
0x180001cc4  test    byte ptr [rcx+1Ch], 2
0x180001cc8  jz      short loc_180001CEC
0x180001cca  cmp     byte ptr [rcx+19h], 5
0x180001cce  jb      short loc_180001CEC
0x180001cd0  mov     r9, cs:WPP_pszIndent
0x180001cd7  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180001cde  mov     rcx, [rcx+10h]
0x180001ce2  mov     edx, 14h
0x180001ce7  call    WPP_SF_s
0x180001cec  xor     r9d, r9d; pvTypePara
0x180001cef  mov     [rsp+58h+cchNameString], 0; cchNameString
0x180001cf7  xor     r8d, r8d; dwFlags
0x180001cfa  mov     qword ptr [r14], 0
0x180001d01  mov     rcx, rdi; pCertContext
0x180001d04  mov     [rsp+58h+pszNameString], 0; pszNameString
0x180001d0d  lea     edx, [r9+4]; dwType
0x180001d11  call    cs:__imp_CertGetNameStringW
0x180001d17  mov     ebx, 8
0x180001d1c  mov     esi, eax
0x180001d1e  mov     edx, ebx; dwType
0x180001d20  cmp     eax, 1
0x180001d23  jz      loc_180001DB6
0x180001d29  mov     rcx, cs:hHeap; hHeap
0x180001d30  lea     r8d, [rax+1]
0x180001d34  add     r8, r8; dwBytes
0x180001d37  call    cs:__imp_HeapAlloc
0x180001d3d  mov     [r14], rax
0x180001d40  test    rax, rax
0x180001d43  jnz     short loc_180001D90
0x180001d45  lea     edx, [rbx-6]
0x180001d48  call    WppTraceIndent
0x180001d4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180001d54  cmp     rcx, r13
0x180001d57  jz      loc_180001E34
0x180001d5d  test    byte ptr [rcx+1Ch], 1
0x180001d61  jz      loc_180001E34
0x180001d67  cmp     byte ptr [rcx+19h], 2
0x180001d6b  jb      loc_180001E34
0x180001d71  lea     edx, [rbx+0Dh]
0x180001d74  mov     r9, cs:WPP_pszIndent
0x180001d7b  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180001d82  mov     rcx, [rcx+10h]
0x180001d86  call    WPP_SF_s
0x180001d8b  jmp     loc_180001E34
0x180001d90  mov     edx, 4; dwType
0x180001d95  xor     r9d, r9d; pvTypePara
0x180001d98  mov     [rsp+58h+cchNameString], esi; cchNameString
0x180001d9c  xor     r8d, r8d; dwFlags
0x180001d9f  mov     [rsp+58h+pszNameString], rax; pszNameString
0x180001da4  mov     rcx, rdi; pCertContext
0x180001da7  call    cs:__imp_CertGetNameStringW
0x180001dad  cmp     eax, 1
0x180001db0  jz      short loc_180001E2C
0x180001db2  xor     ebx, ebx
0x180001db4  jmp     short loc_180001E34
0x180001db6  mov     [rsp+58h+cchNameString], 0; cchNameString
0x180001dbe  xor     r9d, r9d; pvTypePara
0x180001dc1  xor     r8d, r8d; dwFlags
0x180001dc4  mov     [rsp+58h+pszNameString], 0; pszNameString
0x180001dcd  mov     rcx, rdi; pCertContext
0x180001dd0  call    cs:__imp_CertGetNameStringW
0x180001dd6  mov     esi, eax
0x180001dd8  cmp     eax, 1
0x180001ddb  jz      short loc_180001E2C
0x180001ddd  mov     rcx, cs:hHeap; hHeap
0x180001de4  lea     r8d, [rax+1]
0x180001de8  add     r8, r8; dwBytes
0x180001deb  mov     edx, ebx; dwFlags
0x180001ded  call    cs:__imp_HeapAlloc
0x180001df3  mov     [r14], rax
0x180001df6  test    rax, rax
0x180001df9  jnz     short loc_180001E25
0x180001dfb  lea     edx, [rax+2]
0x180001dfe  call    WppTraceIndent
0x180001e03  mov     rcx, cs:WPP_GLOBAL_Control
0x180001e0a  cmp     rcx, r13
0x180001e0d  jz      short loc_180001E34
0x180001e0f  test    byte ptr [rcx+1Ch], 1
0x180001e13  jz      short loc_180001E34
0x180001e15  cmp     byte ptr [rcx+19h], 2
0x180001e19  jb      short loc_180001E34
0x180001e1b  mov     edx, 16h
0x180001e20  jmp     loc_180001D74
0x180001e25  mov     edx, ebx
0x180001e27  jmp     loc_180001D95
0x180001e2c  call    cs:__imp_GetLastError
0x180001e32  mov     ebx, eax
0x180001e34  mov     edx, 1
0x180001e39  call    WppTraceIndent
0x180001e3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180001e45  cmp     rcx, r13
0x180001e48  jz      short loc_180001E76
0x180001e4a  test    byte ptr [rcx+1Ch], 2
0x180001e4e  jz      short loc_180001E76
0x180001e50  cmp     byte ptr [rcx+19h], 5
0x180001e54  jb      short loc_180001E76
0x180001e56  mov     r9, cs:WPP_pszIndent
0x180001e5d  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180001e64  mov     rcx, [rcx+10h]
0x180001e68  mov     edx, 17h
0x180001e6d  mov     dword ptr [rsp+58h+pszNameString], ebx
0x180001e71  call    WPP_SF_sD
0x180001e76  mov     eax, ebx
0x180001e78  add     rsp, 30h
0x180001e7c  pop     r14
0x180001e7e  pop     r13
0x180001e80  pop     rdi
0x180001e81  pop     rsi
0x180001e82  pop     rbx
0x180001e83  retn
```
