# ReplaceCertInList

- ea: `0x18002d740`
- end: `0x18002d830`
- name: `ReplaceCertInList`
- size: `240`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002d1a4`

## callees

- `0x18002cd54`
- `0x18002d740`
- `0x18003e582`

## import_xrefs

- `CRYPT32!CertFreeCertificateContext` at `0x18002d7dd`
- `CRYPT32!CertFreeCertificateContext` at `0x18002d7dd`
- `CRYPT32!CertCompareCertificate` at `0x18002d7d0`
- `CRYPT32!CertCompareCertificate` at `0x18002d7d0`
- `USER32!SendMessageA` at `0x18002d778`
- `USER32!SendMessageA` at `0x18002d7b2`
- `USER32!SendMessageA` at `0x18002d7f1`
- `USER32!SendMessageA` at `0x18002d809`
- `USER32!SendMessageA` at `0x18002d778`
- `USER32!SendMessageA` at `0x18002d7b2`
- `USER32!SendMessageA` at `0x18002d7f1`
- `USER32!SendMessageA` at `0x18002d809`

## pseudocode

```c
__int64 __fastcall ReplaceCertInList(HWND hWnd, __int64 a2, __int64 a3)
{
  int v3; // ebx
  const CERT_CONTEXT *v6; // rsi
  LPARAM lParam; // [rsp+20h] [rbp-88h] BYREF
  _BYTE v9[32]; // [rsp+28h] [rbp-80h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+48h] [rbp-60h]

  v3 = -1;
  memset_0(&lParam, 0, 0x58u);
  while ( 1 )
  {
    v3 = SendMessageA(hWnd, 0x100Cu, v3, 0);
    if ( v3 == -1 )
      break;
    memset_0(v9, 0, 0x50u);
    HIDWORD(lParam) = v3;
    LODWORD(lParam) = 4;
    if ( (unsigned int)SendMessageA(hWnd, 0x1005u, 0, (LPARAM)&lParam) )
    {
      v6 = pCertContext;
      if ( pCertContext->dwCertEncodingType == *(_DWORD *)a3 )
      {
        if ( CertCompareCertificate(*(_DWORD *)a3, *(PCERT_INFO *)(a3 + 24), pCertContext->pCertInfo) )
        {
          CertFreeCertificateContext(v6);
          SendMessageA(hWnd, 0x1008u, v3, 0);
          goto LABEL_8;
        }
      }
    }
  }
  SendMessageA(hWnd, 0x1004u, 0, 0);
LABEL_8:
  AddCertToList(hWnd);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002d740  push    rbx
0x18002d742  push    rbp
0x18002d743  push    rsi
0x18002d744  push    rdi
0x18002d745  push    r14
0x18002d747  sub     rsp, 80h
0x18002d74e  or      ebx, 0FFFFFFFFh
0x18002d751  mov     r14, r8
0x18002d754  mov     rbp, rdx
0x18002d757  mov     rdi, rcx
0x18002d75a  xor     edx, edx; Val
0x18002d75c  lea     rcx, [rsp+0A8h+lParam]; void *
0x18002d761  lea     r8d, [rbx+59h]; Size
0x18002d765  call    memset_0
0x18002d76a  movsxd  r8, ebx; wParam
0x18002d76d  xor     r9d, r9d; lParam
0x18002d770  mov     edx, 100Ch; Msg
0x18002d775  mov     rcx, rdi; hWnd
0x18002d778  call    cs:__imp_SendMessageA
0x18002d77e  mov     rbx, rax
0x18002d781  cmp     eax, 0FFFFFFFFh
0x18002d784  jz      short loc_18002D7FB
0x18002d786  xor     edx, edx; Val
0x18002d788  lea     rcx, [rsp+0A8h+var_80]; void *
0x18002d78d  lea     r8d, [rdx+50h]; Size
0x18002d791  call    memset_0
0x18002d796  lea     r9, [rsp+0A8h+lParam]; lParam
0x18002d79b  mov     dword ptr [rsp+0A8h+lParam+4], ebx
0x18002d79f  xor     r8d, r8d; wParam
0x18002d7a2  mov     dword ptr [rsp+0A8h+lParam], 4
0x18002d7aa  mov     edx, 1005h; Msg
0x18002d7af  mov     rcx, rdi; hWnd
0x18002d7b2  call    cs:__imp_SendMessageA
0x18002d7b8  test    eax, eax
0x18002d7ba  jz      short loc_18002D76A
0x18002d7bc  mov     rsi, [rsp+0A8h+pCertContext]
0x18002d7c1  mov     ecx, [r14]; dwCertEncodingType
0x18002d7c4  cmp     [rsi], ecx
0x18002d7c6  jnz     short loc_18002D76A
0x18002d7c8  mov     r8, [rsi+18h]; pCertId2
0x18002d7cc  mov     rdx, [r14+18h]; pCertId1
0x18002d7d0  call    cs:__imp_CertCompareCertificate
0x18002d7d6  test    eax, eax
0x18002d7d8  jz      short loc_18002D76A
0x18002d7da  mov     rcx, rsi; pCertContext
0x18002d7dd  call    cs:__imp_CertFreeCertificateContext
0x18002d7e3  movsxd  r8, ebx; wParam
0x18002d7e6  xor     r9d, r9d; lParam
0x18002d7e9  mov     edx, 1008h; Msg
0x18002d7ee  mov     rcx, rdi; hWnd
0x18002d7f1  call    cs:__imp_SendMessageA
0x18002d7f7  mov     eax, ebx
0x18002d7f9  jmp     short loc_18002D80F
0x18002d7fb  xor     r9d, r9d; lParam
0x18002d7fe  xor     r8d, r8d; wParam
0x18002d801  mov     edx, 1004h; Msg
0x18002d806  mov     rcx, rdi; hWnd
0x18002d809  call    cs:__imp_SendMessageA
0x18002d80f  mov     r9d, eax
0x18002d812  mov     r8, r14
0x18002d815  mov     rdx, rbp
0x18002d818  mov     rcx, rdi; hWnd
0x18002d81b  call    AddCertToList
0x18002d820  mov     eax, ebx
0x18002d822  add     rsp, 80h
0x18002d829  pop     r14
0x18002d82b  pop     rdi
0x18002d82c  pop     rsi
0x18002d82d  pop     rbp
0x18002d82e  pop     rbx
0x18002d82f  retn
```
