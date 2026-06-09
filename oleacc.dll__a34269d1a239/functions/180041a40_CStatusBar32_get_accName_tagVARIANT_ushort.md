# CStatusBar32::get_accName(tagVARIANT,ushort * *)

- ea: `0x180041a40`
- end: `0x180041c05`
- name: `?get_accName@CStatusBar32@@UEAAJUtagVARIANT@@PEAPEAG@Z`
- size: `453`
- prototype: `__int64 __fastcall(CStatusBar32 *__hidden this, struct tagVARIANT *__struct_ptr, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800056a4`
- `0x180006c58`
- `0x18000771c`
- `0x180041a40`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180041b8c`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180041b8c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041bbc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041bbc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180041b55`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180041b55`
- `OLEAUT32!__imp_SysAllocString` at `0x180041ba3`
- `OLEAUT32!__imp_SysAllocString` at `0x180041ba3`

## pseudocode

```c
signed int __fastcall CStatusBar32::get_accName(CStatusBar32 *this, struct tagVARIANT *a2, unsigned __int16 **a3)
{
  __int64 v5; // rax
  signed int result; // eax
  LONG lVal; // eax
  HWND v9; // r8
  LONG v10; // eax
  unsigned int v11; // esi
  void *v12; // rdi
  int v13; // ebx
  OLECHAR *v14; // rax
  OLECHAR *v15; // rbx
  HANDLE hProcess; // [rsp+70h] [rbp+8h] BYREF
  __int64 v17; // [rsp+80h] [rbp+18h] BYREF

  *a3 = 0;
  v5 = *(_QWORD *)this;
  hProcess = 0;
  if ( !(*(unsigned int (__fastcall **)(CStatusBar32 *))(v5 + 240))(this) )
    return -2147024809;
  lVal = a2->lVal;
  if ( !lVal )
    return 1;
  v9 = (HWND)*((_QWORD *)this + 10);
  v10 = lVal - 1;
  a2->lVal = v10;
  v17 = 0;
  result = CAccessible::AccSendMessageTimeout(this, 0, v9, 0x40Cu, v10, 0, &v17);
  if ( result < 0 )
    return result;
  if ( !(_WORD)v17 )
    return 1;
  v11 = (unsigned __int16)v17 + 1;
  v12 = SharedAlloc(2 * v11, *((HWND *)this + 10), &hProcess);
  if ( !v12 )
    return -2147024882;
  v13 = CAccessible::AccSendMessageTimeout(this, 0, *((HWND *)this + 10), 0x40Du, a2->lVal, (__int64)v12, &v17);
  if ( v13 < 0 )
  {
LABEL_11:
    SharedFree(v12, hProcess);
    return v13;
  }
  if ( !v17 )
  {
    SharedFree(v12, hProcess);
    return 1;
  }
  v14 = (OLECHAR *)LocalAlloc(0x40u, 2LL * v11);
  v15 = v14;
  if ( !v14 )
  {
    v13 = -2147024882;
    goto LABEL_11;
  }
  ReadProcessMemory(hProcess, v12, v14, 2 * v11, 0);
  if ( *v15 )
  {
    v15[v11 - 1] = 0;
    *a3 = SysAllocString(v15);
  }
  SharedFree(v12, hProcess);
  LocalFree(v15);
  return *a3 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x180041a40  mov     [rsp+arg_8], rbx
0x180041a45  mov     [rsp+arg_18], rbp
0x180041a4a  push    rsi
0x180041a4b  push    rdi
0x180041a4c  push    r12
0x180041a4e  push    r14
0x180041a50  push    r15
0x180041a52  sub     rsp, 40h
0x180041a56  xor     r12d, r12d
0x180041a59  mov     r14, r8
0x180041a5c  mov     [r8], r12
0x180041a5f  mov     rbp, rdx
0x180041a62  mov     rax, [rcx]
0x180041a65  mov     rbx, rcx
0x180041a68  mov     [rsp+68h+hProcess], r12
0x180041a6d  mov     rax, [rax+0F0h]
0x180041a74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041a79  test    eax, eax
0x180041a7b  jnz     short loc_180041A87
0x180041a7d  mov     eax, 80070057h
0x180041a82  jmp     loc_180041BE5
0x180041a87  mov     eax, [rbp+8]
0x180041a8a  test    eax, eax
0x180041a8c  jz      loc_180041BE0
0x180041a92  mov     r8, [rbx+50h]; HWND
0x180041a96  dec     eax
0x180041a98  movsxd  rcx, eax
0x180041a9b  mov     r9d, 40Ch; unsigned int
0x180041aa1  mov     [rbp+8], eax
0x180041aa4  xor     edx, edx; bool
0x180041aa6  lea     rax, [rsp+68h+arg_10]
0x180041aae  mov     [rsp+68h+arg_10], r12
0x180041ab6  mov     [rsp+68h+var_38], rax; __int64 *
0x180041abb  mov     [rsp+68h+var_40], r12; __int64
0x180041ac0  mov     [rsp+68h+lpNumberOfBytesRead], rcx; unsigned __int64
0x180041ac5  mov     rcx, rbx; this
0x180041ac8  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x180041acd  test    eax, eax
0x180041acf  js      loc_180041BE5
0x180041ad5  movzx   esi, word ptr [rsp+68h+arg_10]
0x180041add  test    esi, esi
0x180041adf  jz      loc_180041BE0
0x180041ae5  mov     rdx, [rbx+50h]; HWND
0x180041ae9  lea     r8, [rsp+68h+hProcess]; void **
0x180041aee  inc     esi
0x180041af0  lea     r15d, [rsi+rsi]
0x180041af4  mov     ecx, r15d; dwSize
0x180041af7  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x180041afc  mov     rdi, rax
0x180041aff  test    rax, rax
0x180041b02  jz      loc_180041BFE
0x180041b08  movsxd  rcx, dword ptr [rbp+8]
0x180041b0c  lea     rax, [rsp+68h+arg_10]
0x180041b14  mov     r8, [rbx+50h]; HWND
0x180041b18  mov     r9d, 40Dh; unsigned int
0x180041b1e  mov     [rsp+68h+var_38], rax; __int64 *
0x180041b23  xor     edx, edx; bool
0x180041b25  mov     [rsp+68h+var_40], rdi; __int64
0x180041b2a  mov     [rsp+68h+lpNumberOfBytesRead], rcx; unsigned __int64
0x180041b2f  mov     rcx, rbx; this
0x180041b32  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x180041b37  mov     ebx, eax
0x180041b39  test    eax, eax
0x180041b3b  js      short loc_180041B68
0x180041b3d  cmp     [rsp+68h+arg_10], r12
0x180041b45  jz      loc_180041BD3
0x180041b4b  mov     edx, esi
0x180041b4d  mov     ecx, 40h ; '@'; uFlags
0x180041b52  add     rdx, rdx; uBytes
0x180041b55  call    cs:__imp_LocalAlloc
0x180041b5b  mov     rbx, rax
0x180041b5e  test    rax, rax
0x180041b61  jnz     short loc_180041B79
0x180041b63  mov     ebx, 8007000Eh
0x180041b68  mov     rdx, [rsp+68h+hProcess]; hProcess
0x180041b6d  mov     rcx, rdi; lpAddress
0x180041b70  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x180041b75  mov     eax, ebx
0x180041b77  jmp     short loc_180041BE5
0x180041b79  mov     rcx, [rsp+68h+hProcess]; hProcess
0x180041b7e  mov     r8, rbx; lpBuffer
0x180041b81  mov     r9d, r15d; nSize
0x180041b84  mov     rdx, rdi; lpBaseAddress
0x180041b87  mov     [rsp+68h+lpNumberOfBytesRead], r12; lpNumberOfBytesRead
0x180041b8c  call    cs:__imp_ReadProcessMemory
0x180041b92  cmp     [rbx], r12w
0x180041b96  jz      short loc_180041BAC
0x180041b98  lea     eax, [rsi-1]
0x180041b9b  mov     rcx, rbx; psz
0x180041b9e  mov     [rbx+rax*2], r12w
0x180041ba3  call    cs:__imp_SysAllocString
0x180041ba9  mov     [r14], rax
0x180041bac  mov     rdx, [rsp+68h+hProcess]; hProcess
0x180041bb1  mov     rcx, rdi; lpAddress
0x180041bb4  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x180041bb9  mov     rcx, rbx; hMem
0x180041bbc  call    cs:__imp_LocalFree
0x180041bc2  mov     rax, [r14]
0x180041bc5  neg     rax
0x180041bc8  sbb     eax, eax
0x180041bca  not     eax
0x180041bcc  and     eax, 8007000Eh
0x180041bd1  jmp     short loc_180041BE5
0x180041bd3  mov     rdx, [rsp+68h+hProcess]; hProcess
0x180041bd8  mov     rcx, rdi; lpAddress
0x180041bdb  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x180041be0  mov     eax, 1
0x180041be5  lea     r11, [rsp+68h+var_28]
0x180041bea  mov     rbx, [r11+38h]
0x180041bee  mov     rbp, [r11+48h]
0x180041bf2  mov     rsp, r11
0x180041bf5  pop     r15
0x180041bf7  pop     r14
0x180041bf9  pop     r12
0x180041bfb  pop     rdi
0x180041bfc  pop     rsi
0x180041bfd  retn
0x180041bfe  mov     eax, 8007000Eh
0x180041c03  jmp     short loc_180041BE5
```
