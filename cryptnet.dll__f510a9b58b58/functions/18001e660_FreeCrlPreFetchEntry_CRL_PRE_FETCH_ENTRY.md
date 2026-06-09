# FreeCrlPreFetchEntry(_CRL_PRE_FETCH_ENTRY *)

- ea: `0x18001e660`
- end: `0x18001e718`
- name: `?FreeCrlPreFetchEntry@@YAXPEAU_CRL_PRE_FETCH_ENTRY@@@Z`
- size: `184`
- prototype: `void __fastcall(_QWORD *hMem)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180008f80`
- `0x180012f60`
- `0x18001dde0`
- `0x18001e834`
- `0x18001ec20`

## callees

- `0x18000a990`
- `0x18001e660`
- `0x18001f310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e711`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e66d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e66d`
- `CRYPT32!CertFreeCertificateContext` at `0x18001e6cc`
- `CRYPT32!CertFreeCertificateContext` at `0x18001e6db`
- `CRYPT32!CertFreeCertificateContext` at `0x18001e6cc`
- `CRYPT32!CertFreeCertificateContext` at `0x18001e6db`
- `CRYPT32!CertFreeCRLContext` at `0x18001e6bd`
- `CRYPT32!CertFreeCRLContext` at `0x18001e6bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e690`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e690`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001e6ae`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001e6ae`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001e69f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001e69f`

## pseudocode

```c
void __fastcall FreeCrlPreFetchEntry(_QWORD *hMem)
{
  DWORD LastError; // edi
  void *v3; // rcx
  struct _TP_WORK *v4; // rcx
  struct _TP_TIMER *v5; // rcx
  const CRL_CONTEXT *v6; // rcx
  const CERT_CONTEXT *v7; // rcx
  const CERT_CONTEXT *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx

  LastError = GetLastError();
  LogCrlPreFetchEvent((__int64)"Free", (__int64)hMem, 0);
  v3 = (void *)hMem[1];
  if ( v3 )
    CloseHandle(v3);
  v4 = (struct _TP_WORK *)hMem[2];
  if ( v4 )
    CloseThreadpoolWork(v4);
  v5 = (struct _TP_TIMER *)hMem[3];
  if ( v5 )
    CloseThreadpoolTimer(v5);
  v6 = (const CRL_CONTEXT *)hMem[8];
  if ( v6 )
    CertFreeCRLContext(v6);
  v7 = (const CERT_CONTEXT *)hMem[9];
  if ( v7 )
    CertFreeCertificateContext(v7);
  v8 = (const CERT_CONTEXT *)hMem[10];
  if ( v8 )
    CertFreeCertificateContext(v8);
  v9 = (void *)hMem[11];
  if ( v9 )
    operator delete(v9);
  v10 = (void *)hMem[14];
  if ( v10 )
    operator delete(v10);
  operator delete(hMem);
  SetLastError(LastError);
}

```

## disassembly

```asm
0x18001e660  mov     [rsp+arg_0], rbx
0x18001e665  push    rdi
0x18001e666  sub     rsp, 20h
0x18001e66a  mov     rbx, rcx
0x18001e66d  call    cs:__imp_GetLastError
0x18001e673  xor     r8d, r8d
0x18001e676  lea     rcx, aFree; "Free"
0x18001e67d  mov     rdx, rbx
0x18001e680  mov     edi, eax
0x18001e682  call    _LogCrlPreFetchEvent
0x18001e687  mov     rcx, [rbx+8]; hObject
0x18001e68b  test    rcx, rcx
0x18001e68e  jz      short loc_18001E696
0x18001e690  call    cs:__imp_CloseHandle
0x18001e696  mov     rcx, [rbx+10h]; pwk
0x18001e69a  test    rcx, rcx
0x18001e69d  jz      short loc_18001E6A5
0x18001e69f  call    cs:__imp_CloseThreadpoolWork
0x18001e6a5  mov     rcx, [rbx+18h]; pti
0x18001e6a9  test    rcx, rcx
0x18001e6ac  jz      short loc_18001E6B4
0x18001e6ae  call    cs:__imp_CloseThreadpoolTimer
0x18001e6b4  mov     rcx, [rbx+40h]; pCrlContext
0x18001e6b8  test    rcx, rcx
0x18001e6bb  jz      short loc_18001E6C3
0x18001e6bd  call    cs:__imp_CertFreeCRLContext
0x18001e6c3  mov     rcx, [rbx+48h]; pCertContext
0x18001e6c7  test    rcx, rcx
0x18001e6ca  jz      short loc_18001E6D2
0x18001e6cc  call    cs:__imp_CertFreeCertificateContext
0x18001e6d2  mov     rcx, [rbx+50h]; pCertContext
0x18001e6d6  test    rcx, rcx
0x18001e6d9  jz      short loc_18001E6E1
0x18001e6db  call    cs:__imp_CertFreeCertificateContext
0x18001e6e1  mov     rcx, [rbx+58h]; hMem
0x18001e6e5  test    rcx, rcx
0x18001e6e8  jz      short loc_18001E6EF
0x18001e6ea  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001e6ef  mov     rcx, [rbx+70h]; hMem
0x18001e6f3  test    rcx, rcx
0x18001e6f6  jz      short loc_18001E6FD
0x18001e6f8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001e6fd  mov     rcx, rbx; hMem
0x18001e700  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001e705  mov     ecx, edi
0x18001e707  mov     rbx, [rsp+28h+arg_0]
0x18001e70c  add     rsp, 20h
0x18001e710  pop     rdi
0x18001e711  jmp     cs:__imp_SetLastError
```
