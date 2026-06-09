# CuiFreeContextInformation(_CREDUI_CONTEXT *)

- ea: `0x1400042e0`
- end: `0x140004412`
- name: `?CuiFreeContextInformation@@YAXPEAU_CREDUI_CONTEXT@@@Z`
- size: `306`
- prototype: `void __fastcall(struct _CREDUI_CONTEXT *)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140003040`
- `0x140003820`
- `0x140003b00`
- `0x14001a080`

## callees

- `0x1400042e0`
- `0x14001e050`

## import_xrefs

- `USER32!DestroyIcon` at `0x140004313`
- `USER32!DestroyIcon` at `0x140004313`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140004321`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000432f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000433d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140004403`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140004321`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000432f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000433d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140004403`
- `CRYPT32!CertFreeCertificateContext` at `0x140004358`
- `CRYPT32!CertFreeCertificateContext` at `0x140004358`
- `WINTRUST!WinVerifyTrust` at `0x1400043d8`
- `WINTRUST!WinVerifyTrust` at `0x1400043d8`

## pseudocode

```c
void __fastcall CuiFreeContextInformation(struct _CREDUI_CONTEXT *a1)
{
  HICON v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  __int64 v6; // rax
  __int128 pWVTData; // [rsp+20h] [rbp-29h] BYREF
  __int128 v8; // [rsp+30h] [rbp-19h]
  __int128 v9; // [rsp+40h] [rbp-9h]
  __int128 v10; // [rsp+50h] [rbp+7h]
  __int128 v11; // [rsp+60h] [rbp+17h]
  __int64 v12; // [rsp+70h] [rbp+27h]
  GUID pgActionID; // [rsp+80h] [rbp+37h] BYREF

  v2 = (HICON)*((_QWORD *)a1 + 1);
  if ( v2 )
  {
    DestroyIcon(v2);
    *((_QWORD *)a1 + 1) = 0;
  }
  CoTaskMemFree(*((LPVOID *)a1 + 2));
  v3 = (void *)*((_QWORD *)a1 + 3);
  *((_QWORD *)a1 + 2) = 0;
  CoTaskMemFree(v3);
  v4 = (void *)*((_QWORD *)a1 + 4);
  *((_QWORD *)a1 + 3) = 0;
  CoTaskMemFree(v4);
  v5 = (void *)*((_QWORD *)a1 + 5);
  *((_QWORD *)a1 + 4) = 0;
  if ( v5 )
  {
    CoTaskMemFree(v5);
    *((_QWORD *)a1 + 5) = 0;
  }
  CertFreeCertificateContext(*((PCCERT_CONTEXT *)a1 + 8));
  v6 = *((_QWORD *)a1 + 9);
  *((_QWORD *)a1 + 8) = 0;
  v12 = 0;
  pgActionID.Data1 = 11191659;
  *(_DWORD *)&pgActionID.Data2 = 298896708;
  *(_DWORD *)pgActionID.Data4 = -1073692020;
  *(_DWORD *)&pgActionID.Data4[4] = -292175281;
  pWVTData = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  if ( v6 )
  {
    LODWORD(pWVTData) = 88;
    *((_QWORD *)&v8 + 1) = 2;
    LODWORD(v9) = 3;
    *((_QWORD *)&v9 + 1) = 0;
    LODWORD(v10) = 2;
    *((_QWORD *)&v10 + 1) = v6;
    WinVerifyTrust(HWND_MESSAGE|0x2LL, &pgActionID, &pWVTData);
  }
  *((_QWORD *)a1 + 9) = 0;
}

```

## disassembly

```asm
0x1400042e0  mov     [rsp-8+arg_8], rbx
0x1400042e5  mov     [rsp-8+arg_10], rdi
0x1400042ea  push    rbp
0x1400042eb  lea     rbp, [rsp-57h]
0x1400042f0  sub     rsp, 0A0h
0x1400042f7  mov     rax, cs:__security_cookie
0x1400042fe  xor     rax, rsp
0x140004301  mov     [rbp+57h+var_10], rax
0x140004305  mov     rbx, rcx
0x140004308  xor     edi, edi
0x14000430a  mov     rcx, [rcx+8]; hIcon
0x14000430e  test    rcx, rcx
0x140004311  jz      short loc_14000431D
0x140004313  call    cs:__imp_DestroyIcon
0x140004319  mov     [rbx+8], rdi
0x14000431d  mov     rcx, [rbx+10h]; pv
0x140004321  call    cs:__imp_CoTaskMemFree
0x140004327  mov     rcx, [rbx+18h]; pv
0x14000432b  mov     [rbx+10h], rdi
0x14000432f  call    cs:__imp_CoTaskMemFree
0x140004335  mov     rcx, [rbx+20h]; pv
0x140004339  mov     [rbx+18h], rdi
0x14000433d  call    cs:__imp_CoTaskMemFree
0x140004343  mov     rcx, [rbx+28h]; pv
0x140004347  mov     [rbx+20h], rdi
0x14000434b  test    rcx, rcx
0x14000434e  jnz     loc_140004403
0x140004354  mov     rcx, [rbx+40h]; pCertContext
0x140004358  call    cs:__imp_CertFreeCertificateContext
0x14000435e  mov     rax, [rbx+48h]
0x140004362  xorps   xmm0, xmm0
0x140004365  xor     ecx, ecx
0x140004367  mov     [rbx+40h], rdi
0x14000436b  mov     [rbp+57h+var_30], rcx
0x14000436f  mov     [rbp+57h+pgActionID.Data1], 0AAC56Bh
0x140004376  mov     dword ptr [rbp+57h+pgActionID.Data2], 11D0CD44h
0x14000437d  mov     dword ptr [rbp+57h+pgActionID.Data4], 0C000C28Ch
0x140004384  mov     dword ptr [rbp+57h+pgActionID.Data4+4], 0EE95C24Fh
0x14000438b  movups  [rbp+57h+pWVTData], xmm0
0x14000438f  movups  [rbp+57h+var_70], xmm0
0x140004393  movups  [rbp+57h+var_60], xmm0
0x140004397  movups  [rbp+57h+var_50], xmm0
0x14000439b  movups  [rbp+57h+var_40], xmm0
0x14000439f  test    rax, rax
0x1400043a2  jz      short loc_1400043DE
0x1400043a4  lea     r8, [rbp+57h+pWVTData]; pWVTData
0x1400043a8  mov     dword ptr [rbp+57h+pWVTData], 58h ; 'X'
0x1400043af  lea     rdx, [rbp+57h+pgActionID]; pgActionID
0x1400043b3  mov     qword ptr [rbp+57h+var_70+8], 2
0x1400043bb  mov     rcx, 0FFFFFFFFFFFFFFFFh; hwnd
0x1400043c2  mov     dword ptr [rbp+57h+var_60], 3
0x1400043c9  mov     qword ptr [rbp+57h+var_60+8], rdi
0x1400043cd  mov     dword ptr [rbp+57h+var_50], 2
0x1400043d4  mov     qword ptr [rbp+57h+var_50+8], rax
0x1400043d8  call    cs:__imp_WinVerifyTrust
0x1400043de  mov     [rbx+48h], rdi
0x1400043e2  mov     rcx, [rbp+57h+var_10]
0x1400043e6  xor     rcx, rsp; StackCookie
0x1400043e9  call    __security_check_cookie
0x1400043ee  lea     r11, [rsp+0A0h+var_s0]
0x1400043f6  mov     rbx, [r11+18h]
0x1400043fa  mov     rdi, [r11+20h]
0x1400043fe  mov     rsp, r11
0x140004401  pop     rbp
0x140004402  retn
0x140004403  call    cs:__imp_CoTaskMemFree
0x140004409  mov     [rbx+28h], rdi
0x14000440d  jmp     loc_140004354
```
