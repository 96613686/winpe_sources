# bCheckBitmapInfo

- ea: `0x180097820`
- end: `0x180097953`
- name: `bCheckBitmapInfo`
- size: `307`
- prototype: `__int64 __usercall@<rax>(struct tagHANDLETABLE *@<rcx>, MR *this@<rdx>, int, __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180029440`
- `0x180034210`
- `0x180096de0`

## callees

- `0x1800360a0`
- `0x180043e80`
- `0x180043ec4`
- `0x18007f800`
- `0x180097820`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800978f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180097927`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800978f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180097927`
- `ntdll!RtlLogUnexpectedCodepath` at `0x1800978e3`
- `ntdll!RtlLogUnexpectedCodepath` at `0x1800978e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall bCheckBitmapInfo(
        struct tagHANDLETABLE *a1,
        MR *this,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6)
{
  HLOCAL v11; // rcx
  HLOCAL v12; // rbx
  HLOCAL hMem; // [rsp+30h] [rbp-38h] BYREF
  char v14; // [rsp+38h] [rbp-30h]
  int v15; // [rsp+40h] [rbp-28h] BYREF
  __int64 v16; // [rsp+44h] [rbp-24h]

  hMem = 0;
  v14 = 0;
  if ( !(unsigned int)IsValidEnhMetaRecordOffExt(a1, this) )
    return 0;
  if ( !(unsigned int)bCheckBitmapInfoHeader(this, a3, a4, a5, &hMem) )
  {
    v11 = hMem;
    if ( !hMem || !v14 )
      return 0;
    goto LABEL_15;
  }
  v12 = hMem;
  if ( *(_DWORD *)hMem == 124 && *((_DWORD *)hMem + 14) == 1296188740 )
  {
    if ( a3 + *((_DWORD *)hMem + 28) < a3 )
    {
LABEL_13:
      if ( !v14 )
        return 0;
      v11 = v12;
LABEL_15:
      LocalFree(v11);
      return 0;
    }
    if ( !(unsigned int)IsValidEnhMetaRecordOffExt(a1, this) )
    {
      if ( !*((_DWORD *)v12 + 28) )
      {
        v15 = 60430534;
        v16 = 2;
        RtlLogUnexpectedCodepath(&v15);
      }
      goto LABEL_13;
    }
  }
  BitmapInfoPtr::operator=(a6, &hMem);
  if ( hMem && v14 )
    LocalFree(hMem);
  return 1;
}

```

## disassembly

```asm
0x180097820  push    rbp
0x180097822  push    rbx
0x180097823  push    rsi
0x180097824  push    rdi
0x180097825  push    r14
0x180097827  push    r15
0x180097829  mov     rbp, rsp
0x18009782c  sub     rsp, 68h
0x180097830  mov     rax, cs:__security_cookie
0x180097837  xor     rax, rsp
0x18009783a  mov     [rbp+var_18], rax
0x18009783e  mov     ebx, r9d
0x180097841  mov     edi, r8d
0x180097844  mov     rsi, rdx
0x180097847  mov     r15, rcx
0x18009784a  mov     r14, [rbp+arg_28]
0x18009784e  mov     [rbp+hMem], 0
0x180097856  mov     [rbp+var_30], 0
0x18009785a  call    IsValidEnhMetaRecordOffExt
0x18009785f  test    eax, eax
0x180097861  jnz     short loc_18009786A
0x180097863  xor     eax, eax
0x180097865  jmp     loc_180097939
0x18009786a  lea     rax, [rbp+hMem]
0x18009786e  mov     [rsp+68h+var_48], rax
0x180097873  mov     r9d, [rbp+arg_20]
0x180097877  mov     r8d, ebx
0x18009787a  mov     edx, edi
0x18009787c  mov     rcx, rsi
0x18009787f  call    bCheckBitmapInfoHeader
0x180097884  test    eax, eax
0x180097886  jnz     short loc_180097898
0x180097888  mov     rcx, [rbp+hMem]
0x18009788c  test    rcx, rcx
0x18009788f  jz      short loc_180097906
0x180097891  cmp     [rbp+var_30], al
0x180097894  jz      short loc_180097906
0x180097896  jmp     short loc_1800978F9
0x180097898  mov     rbx, [rbp+hMem]
0x18009789c  cmp     dword ptr [rbx], 7Ch ; '|'
0x18009789f  jnz     short loc_18009790B
0x1800978a1  cmp     dword ptr [rbx+38h], 4D424544h
0x1800978a8  jnz     short loc_18009790B
0x1800978aa  mov     r8d, [rbx+70h]
0x1800978ae  add     r8d, edi
0x1800978b1  cmp     r8d, edi
0x1800978b4  jnb     short loc_1800978B8
0x1800978b6  jmp     short loc_1800978F0
0x1800978b8  mov     r9d, [rbx+74h]
0x1800978bc  mov     rdx, rsi; this
0x1800978bf  mov     rcx, r15; struct tagHANDLETABLE *
0x1800978c2  call    IsValidEnhMetaRecordOffExt
0x1800978c7  test    eax, eax
0x1800978c9  jnz     short loc_18009790B
0x1800978cb  cmp     [rbx+70h], eax
0x1800978ce  jnz     short loc_1800978F0
0x1800978d0  mov     [rbp+var_28], 39A18C6h
0x1800978d7  mov     [rbp+var_24], 2
0x1800978df  lea     rcx, [rbp+var_28]
0x1800978e3  call    cs:__imp_RtlLogUnexpectedCodepath
0x1800978ea  nop     dword ptr [rax+rax+00h]
0x1800978ef  nop
0x1800978f0  cmp     [rbp+var_30], 0
0x1800978f4  jz      short loc_180097906
0x1800978f6  mov     rcx, rbx; hMem
0x1800978f9  call    cs:__imp_LocalFree
0x180097900  nop     dword ptr [rax+rax+00h]
0x180097905  nop
0x180097906  jmp     loc_180097863
0x18009790b  lea     rdx, [rbp+hMem]
0x18009790f  mov     rcx, r14
0x180097912  call    ??4BitmapInfoPtr@@QEAAAEAV0@AEAV0@@Z; BitmapInfoPtr::operator=(BitmapInfoPtr &)
0x180097917  nop
0x180097918  mov     rcx, [rbp+hMem]; hMem
0x18009791c  test    rcx, rcx
0x18009791f  jz      short loc_180097934
0x180097921  cmp     [rbp+var_30], 0
0x180097925  jz      short loc_180097934
0x180097927  call    cs:__imp_LocalFree
0x18009792e  nop     dword ptr [rax+rax+00h]
0x180097933  nop
0x180097934  mov     eax, 1
0x180097939  mov     rcx, [rbp+var_18]
0x18009793d  xor     rcx, rsp; StackCookie
0x180097940  call    __security_check_cookie
0x180097945  add     rsp, 68h
0x180097949  pop     r15
0x18009794b  pop     r14
0x18009794d  pop     rdi
0x18009794e  pop     rsi
0x18009794f  pop     rbx
0x180097950  pop     rbp
0x180097951  retn
```
