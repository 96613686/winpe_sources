# DwRemoveLinkageKeys

- ea: `0x180098bcc`
- end: `0x180098f2d`
- name: `DwRemoveLinkageKeys`
- size: `865`
- prototype: ``
- caller_count: `6`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180040ddc`
- `0x180096c5c`
- `0x180096f30`
- `0x180097204`
- `0x1800973b0`
- `0x18009778c`

## callees

- `0x180097938`
- `0x180097e18`
- `0x180098bcc`
- `0x1800b3978`
- `0x1800e8e7e`
- `0x1800e8e96`
- `0x1800e8ef0`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098e2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098e2e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180098c71`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180098c71`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180098eb4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180098eb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180098ecc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180098ecc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180098e1a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180098e1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098ee0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098ef4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098ee0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098ef4`

## string_xrefs

- `0x180098c89`: `DwRemoveLinkageKeys: RegOpenKeyExW: failed %d`
- `0x180098d19`: `DwRemoveLinkageKeys: RegQueryValueWithAllocW: failed %d`
- `0x180098cad`: `DwRemoveLinkageKeys: RegOpenKeyExW: failed %d`
- `0x180098d38`: `DwRemoveLinkageKeys: RegQueryValueWithAllocW: failed %d`

## pseudocode

```c
__int64 __fastcall DwRemoveLinkageKeys(
        char *a1,
        const WCHAR *a2,
        const WCHAR *a3,
        __int64 a4,
        _DWORD *a5,
        unsigned int a6)
{
  void *v8; // rdi
  BYTE *v9; // r14
  __int64 v10; // r13
  LSTATUS v11; // eax
  unsigned int v12; // r8d
  unsigned int v13; // ebx
  unsigned int v14; // eax
  unsigned int v15; // r15d
  _WORD *v16; // rsi
  __int64 v17; // r12
  unsigned __int64 v18; // rax
  char *v19; // rcx
  char *v20; // rax
  char *v21; // rcx
  int v22; // edx
  int v23; // r8d
  unsigned int v24; // ebx
  SIZE_T v25; // rdx
  BYTE *v26; // rax
  DWORD LastError; // eax
  const WCHAR *v28; // rdx
  DWORD cbData; // [rsp+28h] [rbp-D8h]
  SIZE_T uBytes; // [rsp+40h] [rbp-C0h] BYREF
  void *Src; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v34; // [rsp+58h] [rbp-A8h] BYREF
  char *v35; // [rsp+60h] [rbp-A0h]
  __int64 v36; // [rsp+68h] [rbp-98h]
  _DWORD *v37; // [rsp+70h] [rbp-90h]
  LPCWSTR lpValueName; // [rsp+78h] [rbp-88h]
  int v39; // [rsp+80h] [rbp-80h] BYREF
  char v40[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  lpValueName = a3;
  v35 = a1;
  v37 = a5;
  Src = 0;
  hKey = 0;
  v8 = 0;
  LODWORD(uBytes) = 0;
  v9 = 0;
  v34 = 0;
  v39 = 0;
  v10 = a4;
  v36 = a4;
  memset_0(v40, 0, sizeof(v40));
  *a5 = 0;
  v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 3u, &hKey);
  v13 = v11;
  if ( v11 )
  {
    TraceIt(a6, "DwRemoveLinkageKeys: RegOpenKeyExW: failed %d", v11);
    if ( qword_18010FC00 )
    {
      LOWORD(v39) = 0;
      FormatRRASErrorString(&v39, L"DwRemoveLinkageKeys: RegOpenKeyExW: failed %d", v13);
      ((void (__fastcall *)(__int64, __int64, int *))gRegHelpTemplateFunc)(gRegHelpEtwContext, qword_18010FC00, &v39);
    }
  }
  else
  {
    v14 = RegQueryValueWithAllocW(hKey, a3, v12, (unsigned __int8 **)&Src, &v34, (unsigned int *)&uBytes, a6);
    v13 = v14;
    if ( v14 )
    {
      TraceIt(a6, "DwRemoveLinkageKeys: RegQueryValueWithAllocW: failed %d", v14);
      if ( qword_18010FC00 )
      {
        LOWORD(v39) = 0;
        FormatRRASErrorString(&v39, L"DwRemoveLinkageKeys: RegQueryValueWithAllocW: failed %d", v13);
        ((void (__fastcall *)(__int64, __int64, int *))gRegHelpTemplateFunc)(gRegHelpEtwContext, qword_18010FC00, &v39);
      }
      v8 = Src;
    }
    else
    {
      v8 = Src;
      v15 = 0;
      v16 = Src;
      if ( *(_WORD *)Src )
      {
        while ( 1 )
        {
          v17 = -1;
          do
            ++v17;
          while ( v16[v17] );
          v18 = -1;
          do
            ++v18;
          while ( *(_WORD *)(v10 + 2 * v18) );
          if ( (unsigned int)v17 >= v18 )
          {
            v19 = (char *)&v16[v18];
            if ( *(_WORD *)v19 == 123 )
            {
              v20 = v35;
              v21 = (char *)(v19 - v35);
              do
              {
                v22 = *(unsigned __int16 *)&v21[(_QWORD)v20];
                v23 = *(unsigned __int16 *)v20 - v22;
                if ( v23 )
                  break;
                v20 += 2;
              }
              while ( v22 );
              if ( !v23 )
                break;
            }
          }
          v15 += v17 + 1;
          v16 += (unsigned int)v17 + 1;
          if ( !*v16 )
            goto LABEL_29;
          v10 = v36;
        }
        v24 = uBytes;
        v25 = (unsigned int)uBytes;
        *v37 = 1;
        v26 = (BYTE *)LocalAlloc(0x40u, v25);
        v9 = v26;
        if ( v26 )
        {
          if ( v15 )
            memcpy_0(v26, v8, 2LL * v15);
          if ( (v24 >> 1) - v15 - (_DWORD)v17 != 1 )
            memcpy_0(&v9[2 * v15], &v16[(unsigned int)v17 + 1], 2LL * ((v24 >> 1) - v15 - (unsigned int)v17 - 1));
          v28 = lpValueName;
          cbData = v24 - 2 * v17 - 2;
          *(_WORD *)&v9[2 * ((unsigned __int64)cbData >> 1) - 2] = 0;
          LastError = RegSetValueExW(hKey, v28, 0, 7u, v9, cbData);
        }
        else
        {
          LastError = GetLastError();
        }
        v13 = LastError;
      }
    }
  }
LABEL_29:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v8 )
    LocalFree(v8);
  if ( v9 )
    LocalFree(v9);
  return v13;
}

```

## disassembly

```asm
0x180098bcc  mov     [rsp-8+arg_0], rbx
0x180098bd1  push    rbp
0x180098bd2  push    rsi
0x180098bd3  push    rdi
0x180098bd4  push    r12
0x180098bd6  push    r13
0x180098bd8  push    r14
0x180098bda  push    r15
0x180098bdc  lea     rbp, [rsp-790h]
0x180098be4  sub     rsp, 890h
0x180098beb  mov     rax, cs:__security_cookie
0x180098bf2  xor     rax, rsp
0x180098bf5  mov     [rbp+7C0h+var_40], rax
0x180098bfc  mov     rsi, [rbp+7C0h+arg_20]
0x180098c03  xor     r12d, r12d
0x180098c06  mov     r15, r8
0x180098c09  mov     [rsp+8C0h+lpValueName], r8
0x180098c0e  mov     rbx, rdx
0x180098c11  mov     [rsp+8C0h+var_860], rcx
0x180098c16  xor     edx, edx; Val
0x180098c18  mov     [rsp+8C0h+var_850], rsi
0x180098c1d  mov     r8d, 7FCh; Size
0x180098c23  mov     [rsp+8C0h+Src], r12
0x180098c28  lea     rcx, [rbp+7C0h+var_83C]; void *
0x180098c2c  mov     [rsp+8C0h+hKey], r12
0x180098c31  mov     edi, r12d
0x180098c34  mov     dword ptr [rsp+8C0h+uBytes], r12d
0x180098c39  mov     r14d, r12d
0x180098c3c  mov     [rsp+8C0h+var_868], r12d
0x180098c41  mov     [rbp+7C0h+var_840], r12d
0x180098c45  mov     r13, r9
0x180098c48  mov     [rsp+8C0h+var_858], r9
0x180098c4d  call    memset_0
0x180098c52  lea     rax, [rsp+8C0h+hKey]
0x180098c57  mov     [rsi], r12d
0x180098c5a  lea     r9d, [r12+3]; samDesired
0x180098c5f  mov     [rsp+8C0h+phkResult], rax; phkResult
0x180098c64  xor     r8d, r8d; ulOptions
0x180098c67  mov     rdx, rbx; lpSubKey
0x180098c6a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180098c71  call    cs:__imp_RegOpenKeyExW
0x180098c78  nop     dword ptr [rax+rax+00h]
0x180098c7d  mov     ebx, eax
0x180098c7f  test    eax, eax
0x180098c81  jz      short loc_180098CE0
0x180098c83  mov     ecx, [rbp+7C0h+arg_28]; unsigned int
0x180098c89  lea     rdx, aDwremovelinkag; "DwRemoveLinkageKeys: RegOpenKeyExW: fai"...
0x180098c90  mov     r8d, eax
0x180098c93  call    ?TraceIt@@YAXKPEADZZ; TraceIt(ulong,char *,...)
0x180098c98  cmp     cs:qword_18010FC00, r12
0x180098c9f  jz      loc_180098EC2
0x180098ca5  mov     r8d, ebx
0x180098ca8  mov     word ptr [rbp+7C0h+var_840], r12w
0x180098cad  lea     rdx, aDwremovelinkag_1; "DwRemoveLinkageKeys: RegOpenKeyExW: fai"...
0x180098cb4  lea     rcx, [rbp+7C0h+var_840]
0x180098cb8  call    FormatRRASErrorString
0x180098cbd  mov     rdx, cs:qword_18010FC00
0x180098cc4  lea     r8, [rbp+7C0h+var_840]
0x180098cc8  mov     rcx, cs:gRegHelpEtwContext
0x180098ccf  mov     rax, cs:gRegHelpTemplateFunc
0x180098cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098cdb  jmp     loc_180098EC2
0x180098ce0  mov     edi, [rbp+7C0h+arg_28]
0x180098ce6  lea     rax, [rsp+8C0h+uBytes]
0x180098ceb  mov     rcx, [rsp+8C0h+hKey]; hKey
0x180098cf0  lea     r9, [rsp+8C0h+Src]; unsigned __int8 **
0x180098cf5  mov     [rsp+8C0h+var_890], edi; unsigned int
0x180098cf9  mov     rdx, r15; lpValueName
0x180098cfc  mov     qword ptr [rsp+8C0h+cbData], rax; unsigned int *
0x180098d01  lea     rax, [rsp+8C0h+var_868]
0x180098d06  mov     [rsp+8C0h+phkResult], rax; unsigned int *
0x180098d0b  call    ?RegQueryValueWithAllocW@@YAKPEAUHKEY__@@PEAGKPEAPEAEPEAK3K@Z; RegQueryValueWithAllocW(HKEY__ *,ushort *,ulong,uchar * *,ulong *,ulong *,ulong)
0x180098d10  mov     ebx, eax
0x180098d12  test    eax, eax
0x180098d14  jz      short loc_180098D70
0x180098d16  mov     r8d, eax
0x180098d19  lea     rdx, aDwremovelinkag_0; "DwRemoveLinkageKeys: RegQueryValueWithA"...
0x180098d20  mov     ecx, edi; unsigned int
0x180098d22  call    ?TraceIt@@YAXKPEADZZ; TraceIt(ulong,char *,...)
0x180098d27  cmp     cs:qword_18010FC00, r12
0x180098d2e  jz      short loc_180098D66
0x180098d30  mov     r8d, ebx
0x180098d33  mov     word ptr [rbp+7C0h+var_840], r12w
0x180098d38  lea     rdx, aDwremovelinkag_2; "DwRemoveLinkageKeys: RegQueryValueWithA"...
0x180098d3f  lea     rcx, [rbp+7C0h+var_840]
0x180098d43  call    FormatRRASErrorString
0x180098d48  mov     rdx, cs:qword_18010FC00
0x180098d4f  lea     r8, [rbp+7C0h+var_840]
0x180098d53  mov     rcx, cs:gRegHelpEtwContext
0x180098d5a  mov     rax, cs:gRegHelpTemplateFunc
0x180098d61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098d66  mov     rdi, [rsp+8C0h+Src]
0x180098d6b  jmp     loc_180098EC2
0x180098d70  mov     rdi, [rsp+8C0h+Src]
0x180098d75  mov     r15d, r12d
0x180098d78  mov     rsi, rdi
0x180098d7b  cmp     [rdi], r12w
0x180098d7f  jz      loc_180098EC2
0x180098d85  mov     r9, [rsp+8C0h+var_860]
0x180098d8a  or      r11, 0FFFFFFFFFFFFFFFFh
0x180098d8e  mov     r12, r11
0x180098d91  xor     r10d, r10d
0x180098d94  inc     r12
0x180098d97  cmp     [rsi+r12*2], r10w
0x180098d9c  jnz     short loc_180098D94
0x180098d9e  mov     rax, r11
0x180098da1  inc     rax
0x180098da4  cmp     [r13+rax*2+0], r10w
0x180098daa  jnz     short loc_180098DA1
0x180098dac  mov     r13d, r12d
0x180098daf  cmp     r13, rax
0x180098db2  jb      short loc_180098DE2
0x180098db4  lea     rcx, [rsi+rax*2]
0x180098db8  mov     eax, 7Bh ; '{'
0x180098dbd  cmp     ax, [rcx]
0x180098dc0  jnz     short loc_180098DE2
0x180098dc2  mov     rax, r9
0x180098dc5  sub     rcx, r9
0x180098dc8  movzx   r8d, word ptr [rax]
0x180098dcc  movzx   edx, word ptr [rax+rcx]
0x180098dd0  sub     r8d, edx
0x180098dd3  jnz     short loc_180098DDD
0x180098dd5  add     rax, 2
0x180098dd9  test    edx, edx
0x180098ddb  jnz     short loc_180098DC8
0x180098ddd  test    r8d, r8d
0x180098de0  jz      short loc_180098E04
0x180098de2  inc     r12d
0x180098de5  lea     rsi, [rsi+r13*2]
0x180098de9  add     r15d, r12d
0x180098dec  add     rsi, 2
0x180098df0  xor     r12d, r12d
0x180098df3  cmp     [rsi], r12w
0x180098df7  jz      loc_180098EC2
0x180098dfd  mov     r13, [rsp+8C0h+var_858]
0x180098e02  jmp     short loc_180098D8E
0x180098e04  mov     rax, [rsp+8C0h+var_850]
0x180098e09  mov     ecx, 40h ; '@'; uFlags
0x180098e0e  mov     ebx, dword ptr [rsp+8C0h+uBytes]
0x180098e12  mov     edx, ebx; uBytes
0x180098e14  mov     dword ptr [rax], 1
0x180098e1a  call    cs:__imp_LocalAlloc
0x180098e21  nop     dword ptr [rax+rax+00h]
0x180098e26  mov     r14, rax
0x180098e29  test    rax, rax
0x180098e2c  jnz     short loc_180098E3F
0x180098e2e  call    cs:__imp_GetLastError
0x180098e35  nop     dword ptr [rax+rax+00h]
0x180098e3a  jmp     loc_180098EC0
0x180098e3f  test    r15d, r15d
0x180098e42  jz      short loc_180098E55
0x180098e44  mov     r8d, r15d
0x180098e47  mov     rdx, rdi; Src
0x180098e4a  add     r8, r8; Size
0x180098e4d  mov     rcx, r14; void *
0x180098e50  call    memcpy_0
0x180098e55  mov     eax, ebx
0x180098e57  shr     eax, 1
0x180098e59  sub     eax, r15d
0x180098e5c  sub     eax, r12d
0x180098e5f  sub     eax, 1
0x180098e62  jz      short loc_180098E7E
0x180098e64  mov     r8d, eax
0x180098e67  lea     rdx, [r13+1]
0x180098e6b  mov     eax, r15d
0x180098e6e  lea     rdx, [rsi+rdx*2]; Src
0x180098e72  add     r8, r8; Size
0x180098e75  lea     rcx, [r14+rax*2]; void *
0x180098e79  call    memcpy_0
0x180098e7e  mov     rdx, [rsp+8C0h+lpValueName]; lpValueName
0x180098e83  lea     eax, [r12+r12]
0x180098e87  xor     r12d, r12d
0x180098e8a  sub     ebx, eax
0x180098e8c  sub     ebx, 2
0x180098e8f  mov     r8d, ebx
0x180098e92  mov     [rsp+8C0h+cbData], r8d; cbData
0x180098e97  xor     r8d, r8d; Reserved
0x180098e9a  mov     ecx, ebx
0x180098e9c  lea     r9d, [r12+7]; dwType
0x180098ea1  shr     rcx, 1
0x180098ea4  mov     [rsp+8C0h+phkResult], r14; lpData
0x180098ea9  mov     [r14+rcx*2-2], r12w
0x180098eaf  mov     rcx, [rsp+8C0h+hKey]; hKey
0x180098eb4  call    cs:__imp_RegSetValueExW
0x180098ebb  nop     dword ptr [rax+rax+00h]
0x180098ec0  mov     ebx, eax
0x180098ec2  mov     rcx, [rsp+8C0h+hKey]; hKey
0x180098ec7  test    rcx, rcx
0x180098eca  jz      short loc_180098ED8
0x180098ecc  call    cs:__imp_RegCloseKey
0x180098ed3  nop     dword ptr [rax+rax+00h]
0x180098ed8  test    rdi, rdi
0x180098edb  jz      short loc_180098EEC
0x180098edd  mov     rcx, rdi; hMem
0x180098ee0  call    cs:__imp_LocalFree
0x180098ee7  nop     dword ptr [rax+rax+00h]
0x180098eec  test    r14, r14
0x180098eef  jz      short loc_180098F00
0x180098ef1  mov     rcx, r14; hMem
0x180098ef4  call    cs:__imp_LocalFree
0x180098efb  nop     dword ptr [rax+rax+00h]
0x180098f00  mov     eax, ebx
0x180098f02  mov     rcx, [rbp+7C0h+var_40]
0x180098f09  xor     rcx, rsp; StackCookie
0x180098f0c  call    __security_check_cookie
0x180098f11  mov     rbx, [rsp+8C0h+arg_0]
0x180098f19  add     rsp, 890h
0x180098f20  pop     r15
0x180098f22  pop     r14
0x180098f24  pop     r13
0x180098f26  pop     r12
0x180098f28  pop     rdi
0x180098f29  pop     rsi
0x180098f2a  pop     rbp
0x180098f2b  retn
```
