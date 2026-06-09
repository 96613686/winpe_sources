# CopyDispParam(tagDISPPARAMS *,tagDISPPARAMS const *)

- ea: `0x1801a3ba0`
- end: `0x1801a3dec`
- name: `?CopyDispParam@@YAJPEAUtagDISPPARAMS@@PEBU1@@Z`
- size: `588`
- prototype: `__int64 __fastcall(struct tagDISPPARAMS *, const struct tagDISPPARAMS *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1801a4590`
- `0x1801a4f80`

## callees

- `0x180003030`
- `0x180003090`
- `0x1801a3b10`
- `0x1801a3ba0`
- `0x1801a65e1`
- `0x1801a65f0`
- `0x1801ad6a0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1801a3d4d`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1801a3d60`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1801a3d4d`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1801a3d60`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1801a3d6c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1801a3d6c`
- `OLEAUT32!__imp_VariantInit` at `0x1801a3c62`
- `OLEAUT32!__imp_VariantInit` at `0x1801a3c62`
- `OLEAUT32!__imp_VariantCopy` at `0x1801a3c74`
- `OLEAUT32!__imp_VariantCopy` at `0x1801a3c74`

## pseudocode

```c
__int64 __fastcall CopyDispParam(struct tagDISPPARAMS *a1, const struct tagDISPPARAMS *a2)
{
  __int64 cArgs; // rax
  VARIANTARG *v5; // rax
  HRESULT v6; // ebx
  __int64 v7; // rsi
  __int64 cNamedArgs; // rax
  unsigned __int64 v9; // rax
  size_t v10; // rsi
  DISPID *v11; // rax
  __int64 v12; // rdx
  DISPID *rgdispidNamedArgs; // rbp
  unsigned __int64 v14; // rbx

  *(_OWORD *)&a1->rgvarg = 0;
  *(_QWORD *)&a1->cArgs = 0;
  cArgs = a2->cArgs;
  if ( !(_DWORD)cArgs )
  {
LABEL_10:
    cNamedArgs = a2->cNamedArgs;
    if ( !(_DWORD)cNamedArgs )
      return 0;
    v9 = 4 * cNamedArgs;
    if ( v9 <= 0xFFFFFFFF )
    {
      v10 = (unsigned int)v9;
      v11 = (DISPID *)((__int64 (__fastcall *)(LPMALLOC, _QWORD))g_pIMalloc->lpVtbl->Alloc)(
                        g_pIMalloc,
                        (unsigned int)v9);
      a1->rgdispidNamedArgs = v11;
      if ( !v11 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          v6 = bidTraceHR(off_180262718[0], 486409, 2147942414LL);
          goto LABEL_31;
        }
        goto LABEL_6;
      }
      rgdispidNamedArgs = a2->rgdispidNamedArgs;
      v14 = 4LL * a2->cNamedArgs;
      if ( !v14 )
        goto LABEL_26;
      if ( rgdispidNamedArgs && v10 >= v14 )
      {
        memcpy_0(v11, a2->rgdispidNamedArgs, 4LL * a2->cNamedArgs);
LABEL_26:
        a1->cNamedArgs = a2->cNamedArgs;
        return 0;
      }
      memset_0(v11, 0, v10);
      if ( rgdispidNamedArgs )
      {
        if ( v10 >= v14 )
          goto LABEL_26;
        *_errno() = 34;
      }
      else
      {
        *_errno() = 22;
      }
      _invalid_parameter_noinfo();
      goto LABEL_26;
    }
    v6 = -2147024362;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_31;
    v12 = 480265;
LABEL_30:
    bidTraceMark(off_180262718[0], v12);
    goto LABEL_31;
  }
  if ( (unsigned __int64)(24 * cArgs) > 0xFFFFFFFF )
  {
    v6 = -2147024362;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_31;
    v12 = 452617;
    goto LABEL_30;
  }
  v5 = (VARIANTARG *)((__int64 (__fastcall *)(LPMALLOC, _QWORD))g_pIMalloc->lpVtbl->Alloc)(
                       g_pIMalloc,
                       (unsigned int)(24 * cArgs));
  a1->rgvarg = v5;
  if ( v5 )
  {
    v7 = 0;
    if ( a2->cArgs )
    {
      while ( 1 )
      {
        VariantInit(&a1->rgvarg[v7]);
        v6 = VariantCopy(&a1->rgvarg[v7], &a2->rgvarg[v7]);
        if ( v6 < 0 )
          goto LABEL_31;
        ++a1->cArgs;
        v7 = (unsigned int)(v7 + 1);
        if ( (unsigned int)v7 >= a2->cArgs )
          goto LABEL_10;
      }
    }
    goto LABEL_10;
  }
  if ( (bidGblFlags & 2) == 0 )
  {
LABEL_6:
    v6 = -2147024882;
    goto LABEL_31;
  }
  v6 = bidTraceHR(off_180262718[0], 458761, 2147942414LL);
LABEL_31:
  ClearDispParams(a1);
  *(_OWORD *)&a1->rgvarg = 0;
  *(_QWORD *)&a1->cArgs = 0;
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(off_180262718[0], 502793, (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1801a3ba0  mov     [rsp+arg_0], rbx
0x1801a3ba5  mov     [rsp+arg_8], rbp
0x1801a3baa  mov     [rsp+arg_10], rsi
0x1801a3baf  mov     [rsp+arg_18], rdi
0x1801a3bb4  push    r14
0x1801a3bb6  sub     rsp, 20h
0x1801a3bba  xor     eax, eax
0x1801a3bbc  xorps   xmm0, xmm0
0x1801a3bbf  movups  xmmword ptr [rcx], xmm0
0x1801a3bc2  mov     [rcx+10h], rax
0x1801a3bc6  mov     r14, rdx
0x1801a3bc9  mov     eax, [rdx+10h]
0x1801a3bcc  mov     rdi, rcx
0x1801a3bcf  mov     ebp, 0FFFFFFFFh
0x1801a3bd4  test    eax, eax
0x1801a3bd6  jz      loc_1801A3C8F
0x1801a3bdc  lea     rdx, [rax+rax*2]
0x1801a3be0  shl     rdx, 3
0x1801a3be4  cmp     rdx, rbp
0x1801a3be7  ja      loc_1801A3CF4
0x1801a3bed  mov     rcx, cs:?g_pIMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pIMalloc
0x1801a3bf4  mov     edx, edx
0x1801a3bf6  mov     rax, [rcx]
0x1801a3bf9  mov     rax, [rax+18h]
0x1801a3bfd  call    cs:__guard_dispatch_icall_fptr
0x1801a3c03  mov     [rdi], rax
0x1801a3c06  test    rax, rax
0x1801a3c09  jnz     short loc_1801A3C3C
0x1801a3c0b  test    byte ptr cs:_bidGblFlags, 2
0x1801a3c12  jz      short loc_1801A3C32
0x1801a3c14  mov     rcx, cs:off_180262718; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1801a3c1b  mov     edx, 70009h
0x1801a3c20  mov     r8d, 8007000Eh
0x1801a3c26  call    _bidTraceHR
0x1801a3c2b  mov     ebx, eax
0x1801a3c2d  jmp     loc_1801A3DB5
0x1801a3c32  mov     ebx, 8007000Eh
0x1801a3c37  jmp     loc_1801A3DB5
0x1801a3c3c  xor     esi, esi
0x1801a3c3e  cmp     [r14+10h], esi
0x1801a3c42  jbe     short loc_1801A3C8F
0x1801a3c44  nop     dword ptr [rax+00h]
0x1801a3c48  nop     dword ptr [rax+rax+00000000h]
0x1801a3c50  lea     rcx, [rsi+rsi*2]
0x1801a3c54  lea     rbx, ds:0[rcx*8]
0x1801a3c5c  mov     rcx, [rdi]
0x1801a3c5f  add     rcx, rbx; pvarg
0x1801a3c62  call    cs:__imp_VariantInit
0x1801a3c68  mov     rdx, [r14]
0x1801a3c6b  mov     rcx, [rdi]
0x1801a3c6e  add     rdx, rbx; pvargSrc
0x1801a3c71  add     rcx, rbx; pvargDest
0x1801a3c74  call    cs:__imp_VariantCopy
0x1801a3c7a  mov     ebx, eax
0x1801a3c7c  test    eax, eax
0x1801a3c7e  js      loc_1801A3DB5
0x1801a3c84  inc     dword ptr [rdi+10h]
0x1801a3c87  inc     esi
0x1801a3c89  cmp     esi, [r14+10h]
0x1801a3c8d  jb      short loc_1801A3C50
0x1801a3c8f  mov     eax, [r14+14h]
0x1801a3c93  test    eax, eax
0x1801a3c95  jz      loc_1801A3D79
0x1801a3c9b  shl     rax, 2
0x1801a3c9f  cmp     rax, rbp
0x1801a3ca2  ja      loc_1801A3D96
0x1801a3ca8  mov     rcx, cs:?g_pIMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pIMalloc
0x1801a3caf  mov     esi, eax
0x1801a3cb1  mov     edx, esi
0x1801a3cb3  mov     rax, [rcx]
0x1801a3cb6  mov     rax, [rax+18h]
0x1801a3cba  call    cs:__guard_dispatch_icall_fptr
0x1801a3cc0  mov     [rdi+8], rax
0x1801a3cc4  test    rax, rax
0x1801a3cc7  jnz     short loc_1801A3D10
0x1801a3cc9  test    byte ptr cs:_bidGblFlags, 2
0x1801a3cd0  jz      loc_1801A3C32
0x1801a3cd6  mov     rcx, cs:off_180262718; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1801a3cdd  mov     edx, 76C09h
0x1801a3ce2  mov     r8d, 8007000Eh
0x1801a3ce8  call    _bidTraceHR
0x1801a3ced  mov     ebx, eax
0x1801a3cef  jmp     loc_1801A3DB5
0x1801a3cf4  test    byte ptr cs:_bidGblFlags, 2
0x1801a3cfb  mov     ebx, 80070216h
0x1801a3d00  jz      loc_1801A3DB5
0x1801a3d06  mov     edx, 6E809h
0x1801a3d0b  jmp     loc_1801A3DA9
0x1801a3d10  mov     ebx, [r14+14h]
0x1801a3d14  mov     rbp, [r14+8]
0x1801a3d18  shl     rbx, 2
0x1801a3d1c  test    rbx, rbx
0x1801a3d1f  jz      short loc_1801A3D72
0x1801a3d21  test    rbp, rbp
0x1801a3d24  jz      short loc_1801A3D3B
0x1801a3d26  cmp     rsi, rbx
0x1801a3d29  jb      short loc_1801A3D3B
0x1801a3d2b  mov     r8, rbx; Size
0x1801a3d2e  mov     rdx, rbp; Src
0x1801a3d31  mov     rcx, rax; void *
0x1801a3d34  call    memcpy_0
0x1801a3d39  jmp     short loc_1801A3D72
0x1801a3d3b  mov     r8, rsi; Size
0x1801a3d3e  xor     edx, edx; Val
0x1801a3d40  mov     rcx, rax; void *
0x1801a3d43  call    memset_0
0x1801a3d48  test    rbp, rbp
0x1801a3d4b  jnz     short loc_1801A3D5B
0x1801a3d4d  call    cs:__imp__errno
0x1801a3d53  mov     dword ptr [rax], 16h
0x1801a3d59  jmp     short loc_1801A3D6C
0x1801a3d5b  cmp     rsi, rbx
0x1801a3d5e  jnb     short loc_1801A3D72
0x1801a3d60  call    cs:__imp__errno
0x1801a3d66  mov     dword ptr [rax], 22h ; '"'
0x1801a3d6c  call    cs:__imp__invalid_parameter_noinfo
0x1801a3d72  mov     eax, [r14+14h]
0x1801a3d76  mov     [rdi+14h], eax
0x1801a3d79  xor     eax, eax
0x1801a3d7b  mov     rbx, [rsp+28h+arg_0]
0x1801a3d80  mov     rbp, [rsp+28h+arg_8]
0x1801a3d85  mov     rsi, [rsp+28h+arg_10]
0x1801a3d8a  mov     rdi, [rsp+28h+arg_18]
0x1801a3d8f  add     rsp, 20h
0x1801a3d93  pop     r14
0x1801a3d95  retn
0x1801a3d96  test    byte ptr cs:_bidGblFlags, 2
0x1801a3d9d  mov     ebx, 80070216h
0x1801a3da2  jz      short loc_1801A3DB5
0x1801a3da4  mov     edx, 75409h
0x1801a3da9  mov     rcx, cs:off_180262718; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1801a3db0  call    _bidTraceMark
0x1801a3db5  mov     rcx, rdi; struct tagDISPPARAMS *
0x1801a3db8  call    ?ClearDispParams@@YAXPEAUtagDISPPARAMS@@@Z; ClearDispParams(tagDISPPARAMS *)
0x1801a3dbd  xor     eax, eax
0x1801a3dbf  xorps   xmm0, xmm0
0x1801a3dc2  movups  xmmword ptr [rdi], xmm0
0x1801a3dc5  mov     [rdi+10h], rax
0x1801a3dc9  test    byte ptr cs:_bidGblFlags, 2
0x1801a3dd0  jz      short loc_1801A3DE8
0x1801a3dd2  mov     rcx, cs:off_180262718; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1801a3dd9  mov     r8d, ebx
0x1801a3ddc  mov     edx, 7AC09h
0x1801a3de1  call    _bidTraceHR
0x1801a3de6  mov     ebx, eax
0x1801a3de8  mov     eax, ebx
0x1801a3dea  jmp     short loc_1801A3D7B
```
