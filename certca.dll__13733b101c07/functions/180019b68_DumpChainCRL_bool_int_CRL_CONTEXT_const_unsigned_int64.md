# DumpChainCRL(bool,int,_CRL_CONTEXT const *,unsigned __int64)

- ea: `0x180019b68`
- end: `0x180019cf5`
- name: `?DumpChainCRL@@YAJ_NHPEBU_CRL_CONTEXT@@_K@Z`
- size: `397`
- prototype: `__int64 __fastcall(const char *, int, const struct _CRL_CONTEXT *, unsigned __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x18001b07c`

## callees

- `0x180007da0`
- `0x180008400`
- `0x180012450`
- `0x180019b28`
- `0x180019b68`
- `0x180019cfc`
- `0x180019d90`
- `0x180019f70`
- `0x18001aa28`
- `0x180021e30`
- `0x1800382c0`

## import_xrefs

- `CRYPT32!CertGetCRLContextProperty` at `0x180019c4b`
- `CRYPT32!CertGetCRLContextProperty` at `0x180019c4b`
- `OLEAUT32!__imp_SysFreeString` at `0x180019cd5`
- `OLEAUT32!__imp_SysFreeString` at `0x180019cd5`

## string_xrefs

- `0x180019c0f`: `    ThisUpdate`
- `0x180019c26`: `    NextUpdate`

## pseudocode

```c
__int64 __fastcall DumpChainCRL(const char *a1, int a2, const struct _CRL_CONTEXT *a3, unsigned __int64 a4)
{
  OLECHAR *v4; // rsi
  bool v8; // di
  const char *v9; // r8
  const char *v10; // rdx
  int v11; // eax
  unsigned int v12; // ecx
  int v13; // eax
  unsigned int v14; // ebx
  __int64 pcbData; // [rsp+20h] [rbp-58h] BYREF
  unsigned __int8 pvData[24]; // [rsp+28h] [rbp-50h] BYREF

  v4 = 0;
  v8 = (char)a1;
  if ( !a3 )
    goto LABEL_19;
  LODWORD(pcbData) = 20;
  v4 = myCRLNumber(a1, a3);
  if ( v8 )
  {
    v9 = "Delta ";
    if ( !a2 )
      v9 = (const char *)&dword_180061D54;
    DbgPrintf(0xFFFFFFFF, "    %hsCRL %ws:\n", v9, v4, pcbData);
  }
  else
  {
    v10 = "Delta ";
    if ( !a2 )
      v10 = (const char *)&dword_180061D54;
    myConsolePrintf(L"    %hsCRL %ws:\n", v10, v4);
  }
  DumpChainName(v8, "    Issuer", &a3->pCrlInfo->Issuer);
  DumpChainDate(v8, "    ThisUpdate", &a3->pCrlInfo->ThisUpdate);
  DumpChainDate(v8, "    NextUpdate", &a3->pCrlInfo->NextUpdate);
  if ( !CertGetCRLContextProperty(a3, 3u, pvData, (DWORD *)&pcbData) )
  {
    v11 = myHLastError();
    v12 = 329646499;
LABEL_16:
    CSPrintErrorLineFile(v12, v11);
    goto LABEL_17;
  }
  if ( v8 )
    DbgPrintf(0xFFFFFFFF, "  ");
  else
    myConsolePrintf(L"  ");
  v11 = DumpChainHash(v8, L"CRL", pvData, pcbData);
  if ( v11 )
  {
    v12 = 330039715;
    goto LABEL_16;
  }
LABEL_17:
  v13 = DumpChainAddHash(a4, a3->pbCrlEncoded, a3->cbCrlEncoded);
  v14 = v13;
  if ( !v13 )
  {
LABEL_19:
    v14 = 0;
    goto LABEL_20;
  }
  CSPrintErrorLineFile(0x13AF01A3u, v13);
LABEL_20:
  SysFreeString(v4);
  return v14;
}

```

## disassembly

```asm
0x180019b68  push    rbx
0x180019b6a  push    rbp
0x180019b6b  push    rsi
0x180019b6c  push    rdi
0x180019b6d  push    r14
0x180019b6f  sub     rsp, 50h
0x180019b73  mov     rax, cs:__security_cookie
0x180019b7a  xor     rax, rsp
0x180019b7d  mov     [rsp+78h+var_38], rax
0x180019b82  xor     esi, esi
0x180019b84  mov     r14, r9
0x180019b87  mov     rbx, r8
0x180019b8a  mov     ebp, edx
0x180019b8c  mov     dil, cl
0x180019b8f  test    r8, r8
0x180019b92  jz      loc_180019CD0
0x180019b98  mov     rdx, rbx; struct _CRL_CONTEXT *
0x180019b9b  mov     dword ptr [rsp+78h+pcbData], 14h
0x180019ba3  call    ?myCRLNumber@@YAPEAGPEBDPEBU_CRL_CONTEXT@@@Z; myCRLNumber(char const *,_CRL_CONTEXT const *)
0x180019ba8  mov     rsi, rax
0x180019bab  lea     rax, dword_180061D54
0x180019bb2  test    dil, dil
0x180019bb5  jz      short loc_180019BD8
0x180019bb7  test    ebp, ebp
0x180019bb9  lea     r8, aDelta; "Delta "
0x180019bc0  mov     r9, rsi
0x180019bc3  lea     rdx, aHscrlWs; "    %hsCRL %ws:\n"
0x180019bca  cmovz   r8, rax
0x180019bce  or      ecx, 0FFFFFFFFh; unsigned int
0x180019bd1  call    ?DbgPrintf@@YAHKPEBDZZ; DbgPrintf(ulong,char const *,...)
0x180019bd6  jmp     short loc_180019BF4
0x180019bd8  test    ebp, ebp
0x180019bda  lea     rdx, aDelta; "Delta "
0x180019be1  mov     r8, rsi
0x180019be4  lea     rcx, aHscrlWs_0; "    %hsCRL %ws:\n"
0x180019beb  cmovz   rdx, rax
0x180019bef  call    ?myConsolePrintf@@YAHPEBGZZ; myConsolePrintf(ushort const *,...)
0x180019bf4  mov     r8, [rbx+18h]
0x180019bf8  lea     rdx, aIssuer_0; "    Issuer"
0x180019bff  add     r8, 20h ; ' '; struct _CRYPTOAPI_BLOB *
0x180019c03  mov     cl, dil; bool
0x180019c06  call    ?DumpChainName@@YAX_NPEBDPEBU_CRYPTOAPI_BLOB@@@Z; DumpChainName(bool,char const *,_CRYPTOAPI_BLOB const *)
0x180019c0b  mov     r8, [rbx+18h]
0x180019c0f  lea     rdx, aThisupdate; "    ThisUpdate"
0x180019c16  add     r8, 30h ; '0'; struct _FILETIME *
0x180019c1a  mov     cl, dil; bool
0x180019c1d  call    ?DumpChainDate@@YAX_NPEBDPEBU_FILETIME@@@Z; DumpChainDate(bool,char const *,_FILETIME const *)
0x180019c22  mov     r8, [rbx+18h]
0x180019c26  lea     rdx, aNextupdate; "    NextUpdate"
0x180019c2d  add     r8, 38h ; '8'; struct _FILETIME *
0x180019c31  mov     cl, dil; bool
0x180019c34  call    ?DumpChainDate@@YAX_NPEBDPEBU_FILETIME@@@Z; DumpChainDate(bool,char const *,_FILETIME const *)
0x180019c39  lea     r9, [rsp+78h+pcbData]; pcbData
0x180019c3e  mov     edx, 3; dwPropId
0x180019c43  lea     r8, [rsp+78h+pvData]; pvData
0x180019c48  mov     rcx, rbx; pCrlContext
0x180019c4b  call    cs:__imp_CertGetCRLContextProperty
0x180019c51  test    eax, eax
0x180019c53  jnz     short loc_180019C61
0x180019c55  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180019c5a  mov     ecx, 13A601A3h
0x180019c5f  jmp     short loc_180019CA5
0x180019c61  test    dil, dil
0x180019c64  jz      short loc_180019C77
0x180019c66  lea     rdx, asc_18006342C; "  "
0x180019c6d  or      ecx, 0FFFFFFFFh; unsigned int
0x180019c70  call    ?DbgPrintf@@YAHKPEBDZZ; DbgPrintf(ulong,char const *,...)
0x180019c75  jmp     short loc_180019C83
0x180019c77  lea     rcx, asc_180069ED0; "  "
0x180019c7e  call    ?myConsolePrintf@@YAHPEBGZZ; myConsolePrintf(ushort const *,...)
0x180019c83  mov     r9d, dword ptr [rsp+78h+pcbData]; unsigned int
0x180019c88  lea     r8, [rsp+78h+pvData]; unsigned __int8 *
0x180019c8d  lea     rdx, aCrl; "CRL"
0x180019c94  mov     cl, dil; bool
0x180019c97  call    ?DumpChainHash@@YAJ_NPEBGPEBEK@Z; DumpChainHash(bool,ushort const *,uchar const *,ulong)
0x180019c9c  test    eax, eax
0x180019c9e  jz      short loc_180019CAC
0x180019ca0  mov     ecx, 13AC01A3h; unsigned int
0x180019ca5  mov     edx, eax; int
0x180019ca7  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180019cac  mov     r8d, [rbx+10h]; unsigned int
0x180019cb0  mov     rcx, r14; unsigned __int64
0x180019cb3  mov     rdx, [rbx+8]; unsigned __int8 *
0x180019cb7  call    ?DumpChainAddHash@@YAJ_KPEBEK@Z; DumpChainAddHash(unsigned __int64,uchar const *,ulong)
0x180019cbc  mov     ebx, eax
0x180019cbe  test    eax, eax
0x180019cc0  jz      short loc_180019CD0
0x180019cc2  mov     edx, eax; int
0x180019cc4  mov     ecx, 13AF01A3h; unsigned int
0x180019cc9  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180019cce  jmp     short loc_180019CD2
0x180019cd0  xor     ebx, ebx
0x180019cd2  mov     rcx, rsi; bstrString
0x180019cd5  call    cs:__imp_SysFreeString
0x180019cdb  mov     eax, ebx
0x180019cdd  mov     rcx, [rsp+78h+var_38]
0x180019ce2  xor     rcx, rsp; StackCookie
0x180019ce5  call    __security_check_cookie
0x180019cea  add     rsp, 50h
0x180019cee  pop     r14
0x180019cf0  pop     rdi
0x180019cf1  pop     rsi
0x180019cf2  pop     rbp
0x180019cf3  pop     rbx
0x180019cf4  retn
```
