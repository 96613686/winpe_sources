# GetAllSelectedItem(HWND__ *,ulong,void *)

- ea: `0x180020e0c`
- end: `0x180020f64`
- name: `?GetAllSelectedItem@@YAHPEAUHWND__@@KPEAX@Z`
- size: `344`
- prototype: `__int64 __fastcall(HWND hWnd, unsigned int, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001fda0`

## callees

- `0x180020e0c`
- `0x18003e582`

## import_xrefs

- `CRYPT32!CertDuplicateCertificateContext` at `0x180020ee7`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180020ee7`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180020edf`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180020edf`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x180020ef0`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x180020ef0`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180020f1b`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180020f1b`
- `USER32!SendMessageA` at `0x180020e7f`
- `USER32!SendMessageA` at `0x180020ea5`
- `USER32!SendMessageA` at `0x180020e7f`
- `USER32!SendMessageA` at `0x180020ea5`

## pseudocode

```c
__int64 __fastcall GetAllSelectedItem(HWND hWnd, int a2, HCERTSTORE *a3)
{
  unsigned int v3; // esi
  int v7; // ebp
  int v8; // r15d
  int v9; // eax
  const CERT_CONTEXT *v10; // rax
  int lParam; // [rsp+20h] [rbp-88h] BYREF
  int lParam_4; // [rsp+24h] [rbp-84h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+48h] [rbp-60h]
  DWORD pcbData; // [rsp+B0h] [rbp+8h] BYREF
  int pvData; // [rsp+C8h] [rbp+20h] BYREF

  v3 = 0;
  pcbData = 0;
  pvData = 0;
  if ( hWnd && (((a2 - 1) & 0xFFFFFFFD) != 0 || a3) )
  {
    v7 = 1;
    memset_0(&lParam_4, 0, 0x54u);
    v8 = -1;
    lParam = 4;
    while ( 1 )
    {
      v9 = SendMessageA(hWnd, 0x100Cu, v8, 2);
      v8 = v9;
      if ( v9 == -1 )
        break;
      lParam_4 = v9;
      if ( !(unsigned int)SendMessageA(hWnd, 0x1005u, 0, (LPARAM)&lParam) || !pCertContext )
        return v3;
      switch ( a2 )
      {
        case 1:
          pcbData = 4;
          if ( CertGetCertificateContextProperty(pCertContext, 0xEu, &pvData, &pcbData) && (pvData & 1) == 0 )
            v7 = 0;
          break;
        case 2:
          v10 = CertDuplicateCertificateContext(pCertContext);
          CertDeleteCertificateFromStore(v10);
          break;
        case 3:
          CertAddCertificateContextToStore(*a3, pCertContext, 4u, 0);
          break;
        default:
          return v3;
      }
    }
    if ( a2 == 1 )
      *(_DWORD *)a3 = v7;
    return 1;
  }
  return v3;
}

```

## disassembly

```asm
0x180020e0c  mov     rax, rsp
0x180020e0f  mov     [rax+10h], rbx
0x180020e13  push    rbp
0x180020e14  push    rsi
0x180020e15  push    rdi
0x180020e16  push    r14
0x180020e18  push    r15
0x180020e1a  sub     rsp, 80h
0x180020e21  xor     esi, esi
0x180020e23  mov     rdi, r8
0x180020e26  mov     [rax+8], esi
0x180020e29  mov     ebx, edx
0x180020e2b  mov     [rax+20h], esi
0x180020e2e  mov     r14, rcx
0x180020e31  test    rcx, rcx
0x180020e34  jz      loc_180020F4B
0x180020e3a  lea     eax, [rdx-1]
0x180020e3d  test    eax, 0FFFFFFFDh
0x180020e42  jnz     short loc_180020E4D
0x180020e44  test    r8, r8
0x180020e47  jz      loc_180020F4B
0x180020e4d  mov     ebp, 1
0x180020e52  lea     rcx, [rsp+0A8h+lParam+4]; void *
0x180020e57  xor     edx, edx; Val
0x180020e59  lea     r8d, [rbp+53h]; Size
0x180020e5d  call    memset_0
0x180020e62  or      r15d, 0FFFFFFFFh
0x180020e66  mov     dword ptr [rsp+0A8h+lParam], 4
0x180020e6e  movsxd  r8, r15d; wParam
0x180020e71  mov     edx, 100Ch; Msg
0x180020e76  mov     r9d, 2; lParam
0x180020e7c  mov     rcx, r14; hWnd
0x180020e7f  call    cs:__imp_SendMessageA
0x180020e85  mov     r15, rax
0x180020e88  cmp     eax, 0FFFFFFFFh
0x180020e8b  jz      loc_180020F3F
0x180020e91  lea     r9, [rsp+0A8h+lParam]; lParam
0x180020e96  mov     dword ptr [rsp+0A8h+lParam+4], eax
0x180020e9a  xor     r8d, r8d; wParam
0x180020e9d  mov     edx, 1005h; Msg
0x180020ea2  mov     rcx, r14; hWnd
0x180020ea5  call    cs:__imp_SendMessageA
0x180020eab  test    eax, eax
0x180020ead  jz      loc_180020F4B
0x180020eb3  mov     rcx, [rsp+0A8h+pCertContext]; pCertContext
0x180020eb8  test    rcx, rcx
0x180020ebb  jz      loc_180020F4B
0x180020ec1  mov     eax, ebx
0x180020ec3  sub     eax, 1
0x180020ec6  jz      short loc_180020EFB
0x180020ec8  sub     eax, 1
0x180020ecb  jz      short loc_180020EE7
0x180020ecd  cmp     eax, 1
0x180020ed0  jnz     short loc_180020F4B
0x180020ed2  mov     rdx, rcx; pCertContext
0x180020ed5  lea     r8d, [rax+3]; dwAddDisposition
0x180020ed9  mov     rcx, [rdi]; hCertStore
0x180020edc  xor     r9d, r9d; ppStoreContext
0x180020edf  call    cs:__imp_CertAddCertificateContextToStore
0x180020ee5  jmp     short loc_180020E6E
0x180020ee7  call    cs:__imp_CertDuplicateCertificateContext
0x180020eed  mov     rcx, rax; pCertContext
0x180020ef0  call    cs:__imp_CertDeleteCertificateFromStore
0x180020ef6  jmp     loc_180020E6E
0x180020efb  lea     r9, [rsp+0A8h+pcbData]; pcbData
0x180020f03  mov     [rsp+0A8h+pcbData], 4
0x180020f0e  lea     r8, [rsp+0A8h+pvData]; pvData
0x180020f16  mov     edx, 0Eh; dwPropId
0x180020f1b  call    cs:__imp_CertGetCertificateContextProperty
0x180020f21  test    eax, eax
0x180020f23  jz      loc_180020E6E
0x180020f29  mov     eax, [rsp+0A8h+pvData]
0x180020f30  test    al, 1
0x180020f32  jnz     loc_180020E6E
0x180020f38  xor     ebp, ebp
0x180020f3a  jmp     loc_180020E6E
0x180020f3f  cmp     ebx, 1
0x180020f42  jnz     short loc_180020F46
0x180020f44  mov     [rdi], ebp
0x180020f46  mov     esi, 1
0x180020f4b  mov     rbx, [rsp+0A8h+arg_8]
0x180020f53  mov     eax, esi
0x180020f55  add     rsp, 80h
0x180020f5c  pop     r15
0x180020f5e  pop     r14
0x180020f60  pop     rdi
0x180020f61  pop     rsi
0x180020f62  pop     rbp
0x180020f63  retn
```
