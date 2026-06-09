# I_ReaderListFreeItemCommon

- ea: `0x18000cba0`
- end: `0x18000ccda`
- name: `I_ReaderListFreeItemCommon`
- size: `314`
- prototype: `SECURITY_STATUS __fastcall(_QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001f9a0`

## callees

- `0x18000cba0`
- `0x18000cce0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cc2b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cc43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cc5b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cc73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cc8b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cca3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cc2b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cc43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cc5b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cc73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cc8b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cca3`
- `CRYPT32!CertCloseStore` at `0x18000cbf8`
- `CRYPT32!CertCloseStore` at `0x18000cc0c`
- `CRYPT32!CertCloseStore` at `0x18000cbf8`
- `CRYPT32!CertCloseStore` at `0x18000cc0c`
- `ncrypt!NCryptFreeObject` at `0x18000ccc9`
- `ncrypt!NCryptFreeObject` at `0x18000ccc9`
- `ADVAPI32!CryptReleaseContext` at `0x18000ccb7`
- `ADVAPI32!CryptReleaseContext` at `0x18000ccb7`

## pseudocode

```c
SECURITY_STATUS __fastcall I_ReaderListFreeItemCommon(_QWORD *a1, _DWORD *a2)
{
  __int64 v4; // rcx
  SECURITY_STATUS result; // eax
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // r8
  void *v9; // r8
  void *v10; // r8
  void *v11; // r8
  void *v12; // r8
  void *v13; // r8
  HCRYPTPROV v14; // rcx
  NCRYPT_HANDLE v15; // rcx

  if ( a2 )
    *a2 = 0;
  v4 = a1[29];
  while ( v4 )
  {
    a1[29] = *(_QWORD *)(v4 + 104);
    result = I_FreeCredListItem((LPVOID *)v4);
    v4 = a1[29];
    if ( a2 )
      ++*a2;
  }
  v6 = (void *)a1[21];
  if ( v6 )
    result = CertCloseStore(v6, 0);
  v7 = (void *)a1[22];
  if ( v7 )
  {
    result = CertCloseStore(v7, 0);
    if ( a2 )
      ++*a2;
  }
  v8 = (void *)a1[13];
  if ( v8 )
    result = HeapFree(hHeap, 0, v8);
  v9 = (void *)a1[14];
  if ( v9 )
    result = HeapFree(hHeap, 0, v9);
  v10 = (void *)a1[2];
  if ( v10 )
    result = HeapFree(hHeap, 0, v10);
  v11 = (void *)a1[10];
  if ( v11 )
    result = HeapFree(hHeap, 0, v11);
  v12 = (void *)a1[11];
  if ( v12 )
    result = HeapFree(hHeap, 0, v12);
  v13 = (void *)a1[12];
  if ( v13 )
    result = HeapFree(hHeap, 0, v13);
  v14 = a1[16];
  if ( v14 )
    result = CryptReleaseContext(v14, 0);
  v15 = a1[17];
  if ( v15 )
    return NCryptFreeObject(v15);
  return result;
}

```

## disassembly

```asm
0x18000cba0  mov     [rsp+arg_0], rbx
0x18000cba5  push    rdi
0x18000cba6  sub     rsp, 20h
0x18000cbaa  mov     rdi, rdx
0x18000cbad  mov     rbx, rcx
0x18000cbb0  test    rdx, rdx
0x18000cbb3  jz      short loc_18000CBBB
0x18000cbb5  mov     dword ptr [rdx], 0
0x18000cbbb  mov     rcx, [rcx+0E8h]; lpMem
0x18000cbc2  test    rcx, rcx
0x18000cbc5  jz      short loc_18000CBEA
0x18000cbc7  mov     rax, [rcx+68h]
0x18000cbcb  mov     [rbx+0E8h], rax
0x18000cbd2  call    I_FreeCredListItem
0x18000cbd7  mov     rcx, [rbx+0E8h]
0x18000cbde  test    rdi, rdi
0x18000cbe1  jz      short loc_18000CBE5
0x18000cbe3  inc     dword ptr [rdi]
0x18000cbe5  test    rcx, rcx
0x18000cbe8  jnz     short loc_18000CBC7
0x18000cbea  mov     rcx, [rbx+0A8h]; hCertStore
0x18000cbf1  test    rcx, rcx
0x18000cbf4  jz      short loc_18000CBFE
0x18000cbf6  xor     edx, edx; dwFlags
0x18000cbf8  call    cs:__imp_CertCloseStore
0x18000cbfe  mov     rcx, [rbx+0B0h]; hCertStore
0x18000cc05  test    rcx, rcx
0x18000cc08  jz      short loc_18000CC19
0x18000cc0a  xor     edx, edx; dwFlags
0x18000cc0c  call    cs:__imp_CertCloseStore
0x18000cc12  test    rdi, rdi
0x18000cc15  jz      short loc_18000CC19
0x18000cc17  inc     dword ptr [rdi]
0x18000cc19  mov     r8, [rbx+68h]; lpMem
0x18000cc1d  test    r8, r8
0x18000cc20  jz      short loc_18000CC31
0x18000cc22  mov     rcx, cs:hHeap; hHeap
0x18000cc29  xor     edx, edx; dwFlags
0x18000cc2b  call    cs:__imp_HeapFree
0x18000cc31  mov     r8, [rbx+70h]; lpMem
0x18000cc35  test    r8, r8
0x18000cc38  jz      short loc_18000CC49
0x18000cc3a  mov     rcx, cs:hHeap; hHeap
0x18000cc41  xor     edx, edx; dwFlags
0x18000cc43  call    cs:__imp_HeapFree
0x18000cc49  mov     r8, [rbx+10h]; lpMem
0x18000cc4d  test    r8, r8
0x18000cc50  jz      short loc_18000CC61
0x18000cc52  mov     rcx, cs:hHeap; hHeap
0x18000cc59  xor     edx, edx; dwFlags
0x18000cc5b  call    cs:__imp_HeapFree
0x18000cc61  mov     r8, [rbx+50h]; lpMem
0x18000cc65  test    r8, r8
0x18000cc68  jz      short loc_18000CC79
0x18000cc6a  mov     rcx, cs:hHeap; hHeap
0x18000cc71  xor     edx, edx; dwFlags
0x18000cc73  call    cs:__imp_HeapFree
0x18000cc79  mov     r8, [rbx+58h]; lpMem
0x18000cc7d  test    r8, r8
0x18000cc80  jz      short loc_18000CC91
0x18000cc82  mov     rcx, cs:hHeap; hHeap
0x18000cc89  xor     edx, edx; dwFlags
0x18000cc8b  call    cs:__imp_HeapFree
0x18000cc91  mov     r8, [rbx+60h]; lpMem
0x18000cc95  test    r8, r8
0x18000cc98  jz      short loc_18000CCA9
0x18000cc9a  mov     rcx, cs:hHeap; hHeap
0x18000cca1  xor     edx, edx; dwFlags
0x18000cca3  call    cs:__imp_HeapFree
0x18000cca9  mov     rcx, [rbx+80h]; hProv
0x18000ccb0  test    rcx, rcx
0x18000ccb3  jz      short loc_18000CCBD
0x18000ccb5  xor     edx, edx; dwFlags
0x18000ccb7  call    cs:__imp_CryptReleaseContext
0x18000ccbd  mov     rcx, [rbx+88h]; hObject
0x18000ccc4  test    rcx, rcx
0x18000ccc7  jz      short loc_18000CCCF
0x18000ccc9  call    cs:__imp_NCryptFreeObject
0x18000cccf  mov     rbx, [rsp+28h+arg_0]
0x18000ccd4  add     rsp, 20h
0x18000ccd8  pop     rdi
0x18000ccd9  retn
```
