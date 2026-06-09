# CADeleteLocalAutoEnrollmentObject

- ea: `0x18002f8e0`
- end: `0x18002fa0d`
- name: `CADeleteLocalAutoEnrollmentObject`
- size: `301`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, DWORD)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180008400`
- `0x180012450`
- `0x18002f8e0`

## import_xrefs

- `CRYPT32!CertOpenStore` at `0x18002f92e`
- `CRYPT32!CertOpenStore` at `0x18002f92e`
- `CRYPT32!CertCloseStore` at `0x18002f9f5`
- `CRYPT32!CertCloseStore` at `0x18002f9f5`
- `CRYPT32!CertFindCTLInStore` at `0x18002f9c6`
- `CRYPT32!CertFindCTLInStore` at `0x18002f9c6`
- `CRYPT32!CertDeleteCTLFromStore` at `0x18002f9db`
- `CRYPT32!CertDeleteCTLFromStore` at `0x18002f9db`

## pseudocode

```c
__int64 __fastcall CADeleteLocalAutoEnrollmentObject(__int64 a1, __int64 a2, __int64 a3, DWORD a4)
{
  HCERTSTORE v5; // rdi
  unsigned int v6; // ebx
  __int64 v7; // rax
  unsigned __int64 v8; // rax
  const CTL_CONTEXT *CTLInStore; // rax
  __int128 pvFindPara; // [rsp+30h] [rbp-38h] BYREF
  __int128 v12; // [rsp+40h] [rbp-28h]
  __int128 v13; // [rsp+50h] [rbp-18h]
  const char *v14; // [rsp+90h] [rbp+28h] BYREF

  v14 = 0;
  pvFindPara = 0;
  v12 = 0;
  v13 = 0;
  if ( !a1 || a2 || a3 )
  {
    return (unsigned int)-2147024809;
  }
  else
  {
    v5 = CertOpenStore((LPCSTR)0xD, 0, 0, a4, L"ACRS");
    if ( v5 )
    {
      LODWORD(pvFindPara) = 48;
      v14 = "1.3.6.1.4.1.311.20.1";
      DWORD2(pvFindPara) = 1;
      *(_QWORD *)&v12 = &v14;
      v7 = -1;
      do
        ++v7;
      while ( *(_WORD *)(a1 + 2 * v7) );
      v8 = 2 * v7 + 2;
      if ( v8 <= 0x10000 )
      {
        DWORD2(v12) = v8;
        *((_QWORD *)&v13 + 1) = -1;
        *(_QWORD *)&v13 = a1;
        CTLInStore = CertFindCTLInStore(v5, 0x10001u, 0, 3u, &pvFindPara, 0);
        if ( CTLInStore )
        {
          if ( CertDeleteCTLFromStore(CTLInStore) )
            v6 = 0;
          else
            v6 = myHLastError();
        }
        else
        {
          v6 = -2146885628;
        }
      }
      else
      {
        v6 = -2147024362;
        CSPrintErrorLineFile(0x1F10323u, -2147024362);
      }
      CertCloseStore(v5, 0);
    }
    else
    {
      return (unsigned int)myHLastError();
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18002f8e0  push    rbp
0x18002f8e2  push    rbx
0x18002f8e3  push    rsi
0x18002f8e4  push    rdi
0x18002f8e5  mov     rbp, rsp
0x18002f8e8  sub     rsp, 68h
0x18002f8ec  xorps   xmm0, xmm0
0x18002f8ef  xor     esi, esi
0x18002f8f1  mov     [rbp+arg_0], rsi
0x18002f8f5  mov     rbx, rcx
0x18002f8f8  movups  [rbp+pvFindPara], xmm0
0x18002f8fc  movups  [rbp+var_28], xmm0
0x18002f900  movups  [rbp+var_18], xmm0
0x18002f904  test    rcx, rcx
0x18002f907  jz      loc_18002F9FD
0x18002f90d  test    rdx, rdx
0x18002f910  jnz     loc_18002F9FD
0x18002f916  test    r8, r8
0x18002f919  jnz     loc_18002F9FD
0x18002f91f  lea     rax, aAcrs; "ACRS"
0x18002f926  lea     ecx, [rsi+0Dh]; lpszStoreProvider
0x18002f929  mov     [rsp+68h+pvPara], rax; pvPara
0x18002f92e  call    cs:__imp_CertOpenStore
0x18002f934  mov     rdi, rax
0x18002f937  test    rax, rax
0x18002f93a  jnz     short loc_18002F948
0x18002f93c  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18002f941  mov     ebx, eax
0x18002f943  jmp     loc_18002FA02
0x18002f948  lea     rax, a136141311201; "1.3.6.1.4.1.311.20.1"
0x18002f94f  mov     dword ptr [rbp+pvFindPara], 30h ; '0'
0x18002f956  mov     [rbp+arg_0], rax
0x18002f95a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002f95e  lea     rax, [rbp+arg_0]
0x18002f962  mov     dword ptr [rbp+pvFindPara+8], 1
0x18002f969  mov     qword ptr [rbp+var_28], rax
0x18002f96d  mov     rax, rcx
0x18002f970  inc     rax
0x18002f973  cmp     [rbx+rax*2], si
0x18002f977  jnz     short loc_18002F970
0x18002f979  lea     rax, ds:2[rax*2]
0x18002f981  cmp     rax, 10000h
0x18002f987  jbe     short loc_18002F99C
0x18002f989  mov     ebx, 80070216h
0x18002f98e  mov     ecx, 1F10323h; unsigned int
0x18002f993  mov     edx, ebx; int
0x18002f995  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002f99a  jmp     short loc_18002F9F0
0x18002f99c  mov     dword ptr [rbp+var_28+8], eax
0x18002f99f  mov     r9d, 3; dwFindType
0x18002f9a5  lea     rax, [rbp+pvFindPara]
0x18002f9a9  mov     qword ptr [rbp+var_18+8], rcx
0x18002f9ad  mov     [rsp+68h+pPrevCtlContext], rsi; pPrevCtlContext
0x18002f9b2  xor     r8d, r8d; dwFindFlags
0x18002f9b5  mov     edx, 10001h; dwMsgAndCertEncodingType
0x18002f9ba  mov     [rsp+68h+pvPara], rax; pvFindPara
0x18002f9bf  mov     rcx, rdi; hCertStore
0x18002f9c2  mov     qword ptr [rbp+var_18], rbx
0x18002f9c6  call    cs:__imp_CertFindCTLInStore
0x18002f9cc  test    rax, rax
0x18002f9cf  jnz     short loc_18002F9D8
0x18002f9d1  mov     ebx, 80092004h
0x18002f9d6  jmp     short loc_18002F9F0
0x18002f9d8  mov     rcx, rax; pCtlContext
0x18002f9db  call    cs:__imp_CertDeleteCTLFromStore
0x18002f9e1  test    eax, eax
0x18002f9e3  jnz     short loc_18002F9EE
0x18002f9e5  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18002f9ea  mov     ebx, eax
0x18002f9ec  jmp     short loc_18002F9F0
0x18002f9ee  mov     ebx, esi
0x18002f9f0  xor     edx, edx; dwFlags
0x18002f9f2  mov     rcx, rdi; hCertStore
0x18002f9f5  call    cs:__imp_CertCloseStore
0x18002f9fb  jmp     short loc_18002FA02
0x18002f9fd  mov     ebx, 80070057h
0x18002fa02  mov     eax, ebx
0x18002fa04  add     rsp, 68h
0x18002fa08  pop     rdi
0x18002fa09  pop     rsi
0x18002fa0a  pop     rbx
0x18002fa0b  pop     rbp
0x18002fa0c  retn
```
