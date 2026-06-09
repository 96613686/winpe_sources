# SSL_CERT_STORE::Open(STRU &)

- ea: `0x180030bf8`
- end: `0x180030cba`
- name: `?Open@SSL_CERT_STORE@@AEAAJAEAVSTRU@@@Z`
- size: `194`
- prototype: `__int64 __fastcall(PVOID Context, struct STRU *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180030cc0`

## callees

- `0x180030bf8`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180030c5b`
- `KERNEL32!CreateEventW` at `0x180030c5b`
- `KERNEL32!GetLastError` at `0x180030c3d`
- `KERNEL32!GetLastError` at `0x180030c3d`
- `KERNEL32!RegisterWaitForSingleObject` at `0x180030c8b`
- `KERNEL32!RegisterWaitForSingleObject` at `0x180030c8b`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180030c09`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180030c09`
- `CRYPT32!CertControlStore` at `0x180030ca3`
- `CRYPT32!CertControlStore` at `0x180030ca3`
- `CRYPT32!CertOpenStore` at `0x180030c2e`
- `CRYPT32!CertOpenStore` at `0x180030c2e`

## pseudocode

```c
signed int __fastcall SSL_CERT_STORE::Open(char *Context, struct STRU *a2)
{
  signed int result; // eax
  HCERTSTORE v4; // rax
  HANDLE EventW; // rax

  result = STRU::Copy((STRU *)(Context + 40), a2);
  if ( result >= 0 )
  {
    v4 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x20000u, *((const void **)Context + 9));
    *((_QWORD *)Context + 4) = v4;
    if ( v4
      && (EventW = CreateEventW(0, 0, 0, 0), (*((_QWORD *)Context + 12) = EventW) != 0)
      && RegisterWaitForSingleObject(
           (PHANDLE)Context + 13,
           EventW,
           (WAITORTIMERCALLBACK)SSL_CERT_STORE::CertStoreChangeRoutine,
           Context,
           0xFFFFFFFF,
           8u)
      && CertControlStore(*((HCERTSTORE *)Context + 4), 0, 2u, Context + 96) )
    {
      return 0;
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180030bf8  mov     [rsp+arg_0], rbx
0x180030bfd  push    rdi
0x180030bfe  sub     rsp, 30h
0x180030c02  mov     rbx, rcx
0x180030c05  add     rcx, 28h ; '('
0x180030c09  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180030c0f  test    eax, eax
0x180030c11  js      loc_180030CAF
0x180030c17  mov     rax, [rbx+48h]
0x180030c1b  xor     edx, edx; dwEncodingType
0x180030c1d  mov     r9d, 20000h; dwFlags
0x180030c23  mov     [rsp+38h+pvPara], rax; pvPara
0x180030c28  xor     r8d, r8d; hCryptProv
0x180030c2b  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x180030c2e  call    cs:__imp_CertOpenStore
0x180030c34  mov     [rbx+20h], rax
0x180030c38  test    rax, rax
0x180030c3b  jnz     short loc_180030C51
0x180030c3d  call    cs:__imp_GetLastError
0x180030c43  test    eax, eax
0x180030c45  jle     short loc_180030CAF
0x180030c47  movzx   eax, ax
0x180030c4a  or      eax, 80070000h
0x180030c4f  jmp     short loc_180030CAF
0x180030c51  xor     r9d, r9d; lpName
0x180030c54  xor     r8d, r8d; bInitialState
0x180030c57  xor     edx, edx; bManualReset
0x180030c59  xor     ecx, ecx; lpEventAttributes
0x180030c5b  call    cs:__imp_CreateEventW
0x180030c61  mov     [rbx+60h], rax
0x180030c65  test    rax, rax
0x180030c68  jz      short loc_180030C3D
0x180030c6a  lea     rcx, [rbx+68h]; phNewWaitObject
0x180030c6e  mov     [rsp+38h+dwFlags], 8; dwFlags
0x180030c76  mov     r9, rbx; Context
0x180030c79  mov     dword ptr [rsp+38h+pvPara], 0FFFFFFFFh; dwMilliseconds
0x180030c81  lea     r8, ?CertStoreChangeRoutine@SSL_CERT_STORE@@SAXPEAXE@Z; Callback
0x180030c88  mov     rdx, rax; hObject
0x180030c8b  call    cs:__imp_RegisterWaitForSingleObject
0x180030c91  test    eax, eax
0x180030c93  jz      short loc_180030C3D
0x180030c95  mov     rcx, [rbx+20h]; hCertStore
0x180030c99  lea     r9, [rbx+60h]; pvCtrlPara
0x180030c9d  xor     edx, edx; dwFlags
0x180030c9f  lea     r8d, [rdx+2]; dwCtrlType
0x180030ca3  call    cs:__imp_CertControlStore
0x180030ca9  test    eax, eax
0x180030cab  jz      short loc_180030C3D
0x180030cad  xor     eax, eax
0x180030caf  mov     rbx, [rsp+38h+arg_0]
0x180030cb4  add     rsp, 30h
0x180030cb8  pop     rdi
0x180030cb9  retn
```
