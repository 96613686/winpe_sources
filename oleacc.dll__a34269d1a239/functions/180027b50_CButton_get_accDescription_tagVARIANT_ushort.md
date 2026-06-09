# CButton::get_accDescription(tagVARIANT,ushort * *)

- ea: `0x180027b50`
- end: `0x180027d79`
- name: `?get_accDescription@CButton@@UEAAJUtagVARIANT@@PEAPEAG@Z`
- size: `553`
- prototype: `__int64 __fastcall(CButton *__hidden this, struct tagVARIANT *__struct_ptr, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180006c58`
- `0x18000771c`
- `0x18000b890`
- `0x18001cd40`
- `0x180027b50`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180027cf8`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180027cf8`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180027c79`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180027c79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027ccd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027d34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027ccd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027d34`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027c0b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027c0b`
- `OLEAUT32!__imp_SysAllocString` at `0x180027d0c`
- `OLEAUT32!__imp_SysAllocString` at `0x180027d0c`
- `USER32!GetWindowLongW` at `0x180027b9d`
- `USER32!GetWindowLongW` at `0x180027b9d`

## pseudocode

```c
int __fastcall CButton::get_accDescription(HWND *this, struct tagVARIANT *a2, unsigned __int16 **a3)
{
  struct tagVARIANT *v4; // rsi
  int result; // eax
  HWND v7; // rdx
  __int64 v8; // r14
  unsigned int v9; // r13d
  HLOCAL v10; // rdi
  HWND v11; // rdx
  void *v12; // rsi
  HWND v13; // rdx
  void *v14; // rax
  void *v15; // r15
  IRecordInfo *pRecInfo; // xmm1_8
  HANDLE hProcess; // [rsp+30h] [rbp-38h] BYREF
  HANDLE v18; // [rsp+38h] [rbp-30h] BYREF
  struct tagVARIANT v19; // [rsp+40h] [rbp-28h] BYREF
  int Buffer; // [rsp+B0h] [rbp+48h] BYREF
  struct tagVARIANT *v21; // [rsp+B8h] [rbp+50h]
  int v22; // [rsp+C0h] [rbp+58h] BYREF
  int v23; // [rsp+C4h] [rbp+5Ch]
  __int64 v24; // [rsp+C8h] [rbp+60h] BYREF

  v21 = a2;
  *a3 = 0;
  v4 = a2;
  if ( !(*((unsigned int (__fastcall **)(HWND *))*this + 30))(this) )
    return -2147024809;
  if ( (unsigned __int8)((GetWindowLongW(this[10], -16) & 0xF) - 14) > 1u )
    goto LABEL_20;
  v7 = this[10];
  v22 = *((_DWORD *)this + 25);
  v23 = *((_DWORD *)this + 17);
  v24 = 0;
  result = SendMessageTimeoutHelper((struct OLEACC_TIMEOUTDATA *)&v22, v7, 0x160Bu, 0, 0, &v24);
  if ( result < 0 )
    return result;
  v8 = (int)v24;
  if ( !(_DWORD)v24 )
    goto LABEL_20;
  v9 = 2 * (v24 + 1);
  Buffer = v24 + 1;
  v10 = LocalAlloc(0x40u, (int)v9);
  if ( v10 )
  {
    v11 = this[10];
    v18 = 0;
    v12 = SharedAlloc(v9, v11, &v18);
    if ( v12 )
    {
      v13 = this[10];
      hProcess = 0;
      v14 = SharedAlloc(4u, v13, &hProcess);
      v15 = v14;
      if ( v14 )
      {
        if ( WriteProcessMemory(hProcess, v14, &Buffer, 4u, 0) )
        {
          v22 = SendMessageTimeoutHelper(
                  (struct OLEACC_TIMEOUTDATA *)&v22,
                  this[10],
                  0x160Au,
                  (unsigned __int64)v15,
                  (__int64)v12,
                  &v24);
          if ( v22 < 0 )
          {
            SharedFree(v15, hProcess);
            SharedFree(v12, v18);
            LocalFree(v10);
            return v22;
          }
          if ( v24 )
          {
            if ( ReadProcessMemory(v18, v12, v10, v9, 0) )
            {
              *((_WORD *)v10 + v8) = 0;
              *a3 = SysAllocString((const OLECHAR *)v10);
            }
          }
        }
        SharedFree(v15, hProcess);
      }
      SharedFree(v12, v18);
    }
    LocalFree(v10);
    v4 = v21;
  }
  if ( *a3 )
    return 0;
LABEL_20:
  pRecInfo = v4->pRecInfo;
  *(_OWORD *)&v19.vt = *(_OWORD *)&v4->vt;
  v19.pRecInfo = pRecInfo;
  return CAccessible::get_accValue((CAccessible *)this, &v19, a3);
}

```

## disassembly

```asm
0x180027b50  mov     [rsp-40h+arg_8], rdx
0x180027b55  push    rbp
0x180027b56  push    rbx
0x180027b57  push    rsi
0x180027b58  push    rdi
0x180027b59  push    r12
0x180027b5b  push    r13
0x180027b5d  push    r14
0x180027b5f  push    r15
0x180027b61  mov     rbp, rsp
0x180027b64  sub     rsp, 68h
0x180027b68  xor     r15d, r15d
0x180027b6b  mov     r12, r8
0x180027b6e  mov     [r8], r15
0x180027b71  mov     rsi, rdx
0x180027b74  mov     rax, [rcx]
0x180027b77  mov     rbx, rcx
0x180027b7a  mov     rax, [rax+0F0h]
0x180027b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b86  test    eax, eax
0x180027b88  jnz     short loc_180027B94
0x180027b8a  mov     eax, 80070057h
0x180027b8f  jmp     loc_180027D68
0x180027b94  mov     rcx, [rbx+50h]; hWnd
0x180027b98  mov     edx, 0FFFFFFF0h; nIndex
0x180027b9d  call    cs:__imp_GetWindowLongW
0x180027ba3  and     al, 0Fh
0x180027ba5  sub     al, 0Eh
0x180027ba7  cmp     al, 1
0x180027ba9  ja      loc_180027D48
0x180027baf  mov     eax, [rbx+64h]
0x180027bb2  lea     rcx, [rbp+arg_10]; struct OLEACC_TIMEOUTDATA *
0x180027bb6  mov     rdx, [rbx+50h]; HWND
0x180027bba  xor     r9d, r9d; unsigned __int64
0x180027bbd  mov     [rbp+arg_10], eax
0x180027bc0  mov     r8d, 160Bh; unsigned int
0x180027bc6  mov     eax, [rbx+44h]
0x180027bc9  mov     [rbp+arg_14], eax
0x180027bcc  lea     rax, [rbp+arg_18]
0x180027bd0  mov     [rsp+68h+var_40], rax; __int64 *
0x180027bd5  mov     [rsp+68h+lpNumberOfBytesWritten], r15; __int64
0x180027bda  mov     [rbp+arg_18], r15
0x180027bde  call    ?SendMessageTimeoutHelper@@YAJPEAUOLEACC_TIMEOUTDATA@@PEAUHWND__@@I_K_JPEA_J@Z; SendMessageTimeoutHelper(OLEACC_TIMEOUTDATA *,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x180027be3  test    eax, eax
0x180027be5  js      loc_180027D68
0x180027beb  movsxd  r14, dword ptr [rbp+arg_18]
0x180027bef  test    r14d, r14d
0x180027bf2  jz      loc_180027D48
0x180027bf8  lea     eax, [r14+1]
0x180027bfc  mov     ecx, 40h ; '@'; uFlags
0x180027c01  lea     r13d, [rax+rax]
0x180027c05  mov     [rbp+Buffer], eax
0x180027c08  movsxd  rdx, r13d; uBytes
0x180027c0b  call    cs:__imp_LocalAlloc
0x180027c11  mov     rdi, rax
0x180027c14  test    rax, rax
0x180027c17  jz      loc_180027D3E
0x180027c1d  mov     rdx, [rbx+50h]; HWND
0x180027c21  lea     r8, [rbp+var_30]; void **
0x180027c25  mov     ecx, r13d; dwSize
0x180027c28  mov     [rbp+var_30], r15
0x180027c2c  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x180027c31  mov     rsi, rax
0x180027c34  test    rax, rax
0x180027c37  jz      loc_180027D31
0x180027c3d  mov     rdx, [rbx+50h]; HWND
0x180027c41  lea     r8, [rbp+hProcess]; void **
0x180027c45  mov     ecx, 4; dwSize
0x180027c4a  mov     [rbp+hProcess], r15
0x180027c4e  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x180027c53  mov     r15, rax
0x180027c56  test    rax, rax
0x180027c59  jz      loc_180027D22
0x180027c5f  mov     rcx, [rbp+hProcess]; hProcess
0x180027c63  lea     r8, [rbp+Buffer]; lpBuffer
0x180027c67  mov     r9d, 4; nSize
0x180027c6d  mov     [rsp+68h+lpNumberOfBytesWritten], 0; lpNumberOfBytesWritten
0x180027c76  mov     rdx, rax; lpBaseAddress
0x180027c79  call    cs:__imp_WriteProcessMemory
0x180027c7f  test    eax, eax
0x180027c81  jz      loc_180027D16
0x180027c87  mov     rdx, [rbx+50h]; HWND
0x180027c8b  lea     rax, [rbp+arg_18]
0x180027c8f  mov     [rsp+68h+var_40], rax; __int64 *
0x180027c94  lea     rcx, [rbp+arg_10]; struct OLEACC_TIMEOUTDATA *
0x180027c98  mov     r9, r15; unsigned __int64
0x180027c9b  mov     [rsp+68h+lpNumberOfBytesWritten], rsi; __int64
0x180027ca0  mov     r8d, 160Ah; unsigned int
0x180027ca6  call    ?SendMessageTimeoutHelper@@YAJPEAUOLEACC_TIMEOUTDATA@@PEAUHWND__@@I_K_JPEA_J@Z; SendMessageTimeoutHelper(OLEACC_TIMEOUTDATA *,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x180027cab  mov     [rbp+arg_10], eax
0x180027cae  test    eax, eax
0x180027cb0  jns     short loc_180027CDB
0x180027cb2  mov     rdx, [rbp+hProcess]; hProcess
0x180027cb6  mov     rcx, r15; lpAddress
0x180027cb9  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x180027cbe  mov     rdx, [rbp+var_30]; hProcess
0x180027cc2  mov     rcx, rsi; lpAddress
0x180027cc5  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x180027cca  mov     rcx, rdi; hMem
0x180027ccd  call    cs:__imp_LocalFree
0x180027cd3  mov     eax, [rbp+arg_10]
0x180027cd6  jmp     loc_180027D68
0x180027cdb  cmp     [rbp+arg_18], 0
0x180027ce0  jz      short loc_180027D16
0x180027ce2  mov     rcx, [rbp+var_30]; hProcess
0x180027ce6  mov     r8, rdi; lpBuffer
0x180027ce9  mov     r9d, r13d; nSize
0x180027cec  mov     rdx, rsi; lpBaseAddress
0x180027cef  mov     [rsp+68h+lpNumberOfBytesWritten], 0; lpNumberOfBytesRead
0x180027cf8  call    cs:__imp_ReadProcessMemory
0x180027cfe  test    eax, eax
0x180027d00  jz      short loc_180027D16
0x180027d02  xor     eax, eax
0x180027d04  mov     rcx, rdi; psz
0x180027d07  mov     [rdi+r14*2], ax
0x180027d0c  call    cs:__imp_SysAllocString
0x180027d12  mov     [r12], rax
0x180027d16  mov     rdx, [rbp+hProcess]; hProcess
0x180027d1a  mov     rcx, r15; lpAddress
0x180027d1d  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x180027d22  mov     rdx, [rbp+var_30]; hProcess
0x180027d26  mov     rcx, rsi; lpAddress
0x180027d29  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x180027d2e  xor     r15d, r15d
0x180027d31  mov     rcx, rdi; hMem
0x180027d34  call    cs:__imp_LocalFree
0x180027d3a  mov     rsi, [rbp+arg_8]
0x180027d3e  cmp     [r12], r15
0x180027d42  jz      short loc_180027D48
0x180027d44  xor     eax, eax
0x180027d46  jmp     short loc_180027D68
0x180027d48  movups  xmm0, xmmword ptr [rsi]
0x180027d4b  lea     rdx, [rbp+var_28]; struct tagVARIANT
0x180027d4f  mov     r8, r12; unsigned __int16 **
0x180027d52  movsd   xmm1, qword ptr [rsi+10h]
0x180027d57  mov     rcx, rbx; this
0x180027d5a  movaps  xmmword ptr [rbp+var_28], xmm0
0x180027d5e  movsd   qword ptr [rbp+var_28+10h], xmm1
0x180027d63  call    ?get_accValue@CAccessible@@UEAAJUtagVARIANT@@PEAPEAG@Z; CAccessible::get_accValue(tagVARIANT,ushort * *)
0x180027d68  add     rsp, 68h
0x180027d6c  pop     r15
0x180027d6e  pop     r14
0x180027d70  pop     r13
0x180027d72  pop     r12
0x180027d74  pop     rdi
0x180027d75  pop     rsi
0x180027d76  pop     rbx
0x180027d77  pop     rbp
0x180027d78  retn
```
