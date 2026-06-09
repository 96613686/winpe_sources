# RpcpBindRpc

- ea: `0x180011c10`
- end: `0x180011f5d`
- name: `RpcpBindRpc`
- size: `845`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ac60`

## callees

- `0x180011c10`
- `0x180012002`
- `0x180012040`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180011d21`
- `msvcrt!_wcsnicmp` at `0x180011d88`
- `msvcrt!_wcsnicmp` at `0x180011d21`
- `msvcrt!_wcsnicmp` at `0x180011d88`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180011d05`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180011d6d`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180011d05`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180011d6d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011cb9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011d42`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011dc2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011cb9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011d42`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011dc2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011d99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011dec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011dff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011f0a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011d99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011dec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011dff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011f0a`
- `RPCRT4!RpcStringFreeW` at `0x180011f2b`
- `RPCRT4!RpcStringFreeW` at `0x180011f2b`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180011f1f`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180011f1f`
- `RPCRT4!RpcStringBindingComposeW` at `0x180011eff`
- `RPCRT4!RpcStringBindingComposeW` at `0x180011eff`

## pseudocode

```c
__int64 __fastcall RpcpBindRpc(char *Src, unsigned __int16 *a2, unsigned __int16 *a3, RPC_BINDING_HANDLE *a4)
{
  char *v4; // rdi
  __int64 v5; // r14
  RPC_BINDING_HANDLE *v6; // rsi
  unsigned __int16 *v8; // r12
  size_t v9; // rbx
  unsigned int v10; // ebx
  unsigned __int64 v11; // r15
  unsigned __int16 *v12; // rax
  size_t v13; // rsi
  WCHAR *v14; // rax
  wchar_t *v15; // rbx
  unsigned __int16 *v16; // rax
  unsigned __int16 *v17; // rdi
  unsigned __int64 v18; // rbx
  __int64 v20; // r10
  const wchar_t *v21; // r8
  __int64 v22; // rcx
  unsigned __int64 v23; // rdx
  unsigned __int16 *v24; // rcx
  unsigned __int64 v25; // rax
  unsigned __int16 *v26; // rcx
  unsigned __int64 v27; // rcx
  unsigned __int16 *v28; // rax
  unsigned __int64 i; // rbx
  unsigned __int16 *v30; // rdx
  RPC_STATUS v31; // ebx
  RPC_STATUS v32; // ebx
  int v33; // ecx
  DWORD nSize; // [rsp+30h] [rbp-39h] BYREF
  RPC_WSTR String; // [rsp+38h] [rbp-31h] BYREF
  RPC_BINDING_HANDLE *v36; // [rsp+40h] [rbp-29h]
  RPC_WSTR Options; // [rsp+48h] [rbp-21h]
  WCHAR Buffer[16]; // [rsp+50h] [rbp-19h] BYREF

  v4 = Src;
  v36 = a4;
  Options = a3;
  v5 = -1;
  String = 0;
  nSize = 0;
  v6 = a4;
  *a4 = 0;
  v8 = 0;
  if ( !Src )
    goto LABEL_26;
  v9 = -1;
  do
    ++v9;
  while ( *(_WORD *)&Src[2 * v9] );
  if ( !*(_WORD *)Src )
    goto LABEL_26;
  if ( *(_WORD *)Src == 92 )
  {
    if ( *((_WORD *)Src + 1) != 92 )
      return (unsigned int)-1073741534;
    v9 -= 2LL;
    if ( !v9 )
      return (unsigned int)-1073741534;
    v11 = (unsigned __int64)Src;
    if ( Src == (char *)-4LL )
      goto LABEL_27;
    v4 = Src + 4;
  }
  else
  {
    v12 = (unsigned __int16 *)LocalAlloc(0, 2 * v9 + 6);
    v8 = v12;
    if ( !v12 )
      return (unsigned int)-1073741801;
    *(_DWORD *)v12 = 6029404;
    memcpy_0(v12 + 2, v4, 2 * v9 + 2);
    v11 = (unsigned __int64)v8;
  }
  if ( v9 <= 0xF )
  {
    nSize = 16;
    if ( GetComputerNameExW(ComputerNameNetBIOS, Buffer, &nSize) )
    {
      if ( v9 == nSize && !_wcsnicmp(Buffer, (const wchar_t *)v4, v9) )
      {
LABEL_26:
        v11 = 0;
        goto LABEL_27;
      }
    }
  }
  v13 = v9 - 1;
  if ( *(_WORD *)&v4[2 * v9 - 2] != 46 )
    v13 = v9;
  v14 = (WCHAR *)LocalAlloc(0, 0x20Au);
  v15 = v14;
  if ( !v14 )
    goto LABEL_21;
  nSize = 261;
  if ( GetComputerNameExW(ComputerNameDnsFullyQualified, v14, &nSize) && v13 == nSize )
    v11 &= -(__int64)(_wcsnicmp(v15, (const wchar_t *)v4, v13) != 0);
  LocalFree(v15);
  v6 = v36;
  do
LABEL_27:
    ++v5;
  while ( a2[v5] );
  v16 = (unsigned __int16 *)LocalAlloc(0, 2 * v5 + 16);
  v17 = v16;
  if ( !v16 )
  {
LABEL_21:
    v10 = -1073741801;
    goto LABEL_33;
  }
  v18 = (unsigned __int64)(2 * v5 + 16) >> 1;
  if ( v18 )
  {
    if ( v18 <= 0x7FFFFFFF )
    {
      v20 = 2147483646;
      v21 = L"\\PIPE\\";
      v22 = 2147483646;
      v23 = (unsigned __int64)(2 * v5 + 16) >> 1;
      do
      {
        if ( !v22 )
          break;
        if ( !*v21 )
          break;
        *v16++ = *v21++;
        --v22;
        --v23;
      }
      while ( v23 );
      v24 = v16 - 1;
      if ( v23 )
        v24 = v16;
      *v24 = 0;
      if ( v23 )
      {
        v25 = (unsigned __int64)(2 * v5 + 16) >> 1;
        v26 = v17;
        while ( *v26 )
        {
          ++v26;
          if ( !--v25 )
          {
            v27 = 0;
            goto LABEL_48;
          }
        }
        v27 = v18 - v25;
LABEL_48:
        if ( v25 )
        {
          v28 = &v17[v27];
          for ( i = v18 - v27; i; --i )
          {
            if ( !v20 )
              break;
            if ( !*a2 )
              break;
            *v28++ = *a2++;
            --v20;
          }
          v30 = v28 - 1;
          if ( i )
            v30 = v28;
          *v30 = 0;
          if ( i )
          {
            v31 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncacn_np", (RPC_WSTR)v11, v17, Options, &String);
            LocalFree(v17);
            if ( !v31 )
            {
              v32 = RpcBindingFromStringBindingW(String, v6);
              RpcStringFreeW(&String);
              if ( v32 )
              {
                *v6 = 0;
                v33 = -1073741534;
                if ( (unsigned int)(v32 - 1706) > 1 )
                  v33 = -1073741801;
                v10 = v33;
              }
              else
              {
                v10 = 0;
              }
              goto LABEL_33;
            }
            goto LABEL_21;
          }
        }
      }
    }
    else
    {
      *v16 = 0;
    }
  }
  LocalFree(v17);
  v10 = -1073741811;
LABEL_33:
  if ( v8 )
    LocalFree(v8);
  return v10;
}

```

## disassembly

```asm
0x180011c10  push    rbp
0x180011c12  push    rbx
0x180011c13  push    rsi
0x180011c14  push    rdi
0x180011c15  push    r12
0x180011c17  push    r13
0x180011c19  push    r14
0x180011c1b  push    r15
0x180011c1d  lea     rbp, [rsp-1Fh]
0x180011c22  sub     rsp, 88h
0x180011c29  mov     rax, cs:__security_cookie
0x180011c30  xor     rax, rsp
0x180011c33  mov     [rbp+57h+var_50], rax
0x180011c37  mov     rdi, rcx
0x180011c3a  mov     [rbp+57h+var_80], r9
0x180011c3e  xor     ecx, ecx; uFlags
0x180011c40  mov     [rbp+57h+var_78], r8
0x180011c44  or      r14, 0FFFFFFFFFFFFFFFFh
0x180011c48  mov     [rbp+57h+String], rcx
0x180011c4c  mov     [rbp+57h+nSize], ecx
0x180011c4f  mov     rsi, r9
0x180011c52  mov     [r9], rcx
0x180011c55  mov     r13, rdx
0x180011c58  mov     r12d, ecx
0x180011c5b  test    rdi, rdi
0x180011c5e  jz      loc_180011DA7
0x180011c64  mov     rbx, r14
0x180011c67  inc     rbx
0x180011c6a  cmp     [rdi+rbx*2], cx
0x180011c6e  jnz     short loc_180011C67
0x180011c70  cmp     [rdi], cx
0x180011c73  jz      loc_180011DA7
0x180011c79  mov     r15d, 5Ch ; '\'
0x180011c7f  cmp     [rdi], r15w
0x180011c83  jnz     short loc_180011CB1
0x180011c85  cmp     [rdi+2], r15w
0x180011c8a  jnz     short loc_180011C92
0x180011c8c  add     rbx, 0FFFFFFFFFFFFFFFEh
0x180011c90  jnz     short loc_180011C9C
0x180011c92  mov     ebx, 0C0000122h
0x180011c97  jmp     loc_180011E05
0x180011c9c  lea     rax, [rdi+4]
0x180011ca0  mov     r15, rdi
0x180011ca3  test    rax, rax
0x180011ca6  jz      loc_180011DAA
0x180011cac  mov     rdi, rax
0x180011caf  jmp     short loc_180011CEE
0x180011cb1  lea     rdx, ds:6[rbx*2]; uBytes
0x180011cb9  call    cs:__imp_LocalAlloc
0x180011cbf  mov     r12, rax
0x180011cc2  test    rax, rax
0x180011cc5  jnz     short loc_180011CD1
0x180011cc7  mov     ebx, 0C0000017h
0x180011ccc  jmp     loc_180011E05
0x180011cd1  lea     r8, ds:2[rbx*2]; Size
0x180011cd9  mov     dword ptr [rax], 5C005Ch
0x180011cdf  lea     rcx, [rax+4]; void *
0x180011ce3  mov     rdx, rdi; Src
0x180011ce6  call    memcpy_0
0x180011ceb  mov     r15, r12
0x180011cee  cmp     rbx, 0Fh
0x180011cf2  ja      short loc_180011D2D
0x180011cf4  lea     r8, [rbp+57h+nSize]; nSize
0x180011cf8  mov     [rbp+57h+nSize], 10h
0x180011cff  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x180011d03  xor     ecx, ecx; NameType
0x180011d05  call    cs:__imp_GetComputerNameExW
0x180011d0b  test    eax, eax
0x180011d0d  jz      short loc_180011D2D
0x180011d0f  mov     eax, [rbp+57h+nSize]
0x180011d12  cmp     rbx, rax
0x180011d15  jnz     short loc_180011D2D
0x180011d17  mov     r8, rbx; MaxCount
0x180011d1a  lea     rcx, [rbp+57h+Buffer]; String1
0x180011d1e  mov     rdx, rdi; String2
0x180011d21  call    cs:__imp__wcsnicmp
0x180011d27  xor     ecx, ecx
0x180011d29  test    eax, eax
0x180011d2b  jz      short loc_180011DA7
0x180011d2d  cmp     word ptr [rdi+rbx*2-2], 2Eh ; '.'
0x180011d33  lea     rsi, [rbx-1]
0x180011d37  mov     edx, 20Ah; uBytes
0x180011d3c  cmovnz  rsi, rbx
0x180011d40  xor     ecx, ecx; uFlags
0x180011d42  call    cs:__imp_LocalAlloc
0x180011d48  mov     rbx, rax
0x180011d4b  test    rax, rax
0x180011d4e  jnz     short loc_180011D5A
0x180011d50  mov     ebx, 0C0000017h
0x180011d55  jmp     loc_180011DF7
0x180011d5a  lea     r8, [rbp+57h+nSize]; nSize
0x180011d5e  mov     [rbp+57h+nSize], 105h
0x180011d65  mov     rdx, rbx; lpBuffer
0x180011d68  mov     ecx, 3; NameType
0x180011d6d  call    cs:__imp_GetComputerNameExW
0x180011d73  test    eax, eax
0x180011d75  jz      short loc_180011D96
0x180011d77  mov     eax, [rbp+57h+nSize]
0x180011d7a  cmp     rsi, rax
0x180011d7d  jnz     short loc_180011D96
0x180011d7f  mov     r8, rsi; MaxCount
0x180011d82  mov     rdx, rdi; String2
0x180011d85  mov     rcx, rbx; String1
0x180011d88  call    cs:__imp__wcsnicmp
0x180011d8e  neg     eax
0x180011d90  sbb     rcx, rcx
0x180011d93  and     r15, rcx
0x180011d96  mov     rcx, rbx; hMem
0x180011d99  call    cs:__imp_LocalFree
0x180011d9f  mov     rsi, [rbp+57h+var_80]
0x180011da3  xor     ecx, ecx
0x180011da5  jmp     short loc_180011DAA
0x180011da7  mov     r15, rcx
0x180011daa  inc     r14
0x180011dad  cmp     [r13+r14*2+0], cx
0x180011db3  jnz     short loc_180011DAA
0x180011db5  lea     rbx, ds:10h[r14*2]
0x180011dbd  xor     ecx, ecx; uFlags
0x180011dbf  mov     rdx, rbx; uBytes
0x180011dc2  call    cs:__imp_LocalAlloc
0x180011dc8  xor     r14d, r14d
0x180011dcb  mov     rdi, rax
0x180011dce  test    rax, rax
0x180011dd1  jz      loc_180011D50
0x180011dd7  shr     rbx, 1
0x180011dda  jz      short loc_180011DE9
0x180011ddc  cmp     rbx, 7FFFFFFFh
0x180011de3  jbe     short loc_180011E27
0x180011de5  mov     [rax], r14w
0x180011de9  mov     rcx, rdi; hMem
0x180011dec  call    cs:__imp_LocalFree
0x180011df2  mov     ebx, 0C000000Dh
0x180011df7  test    r12, r12
0x180011dfa  jz      short loc_180011E05
0x180011dfc  mov     rcx, r12; hMem
0x180011dff  call    cs:__imp_LocalFree
0x180011e05  mov     eax, ebx
0x180011e07  mov     rcx, [rbp+57h+var_50]
0x180011e0b  xor     rcx, rsp; StackCookie
0x180011e0e  call    __security_check_cookie
0x180011e13  add     rsp, 88h
0x180011e1a  pop     r15
0x180011e1c  pop     r14
0x180011e1e  pop     r13
0x180011e20  pop     r12
0x180011e22  pop     rdi
0x180011e23  pop     rsi
0x180011e24  pop     rbx
0x180011e25  pop     rbp
0x180011e26  retn
0x180011e27  mov     r10d, 7FFFFFFEh
0x180011e2d  lea     r8, aPipe; "\\PIPE\\"
0x180011e34  mov     ecx, r10d
0x180011e37  mov     rdx, rbx
0x180011e3a  test    rcx, rcx
0x180011e3d  jz      short loc_180011E5E
0x180011e3f  movzx   r9d, word ptr [r8]
0x180011e43  test    r9w, r9w
0x180011e47  jz      short loc_180011E5E
0x180011e49  mov     [rax], r9w
0x180011e4d  add     r8, 2
0x180011e51  add     rax, 2
0x180011e55  dec     rcx
0x180011e58  sub     rdx, 1
0x180011e5c  jnz     short loc_180011E3A
0x180011e5e  test    rdx, rdx
0x180011e61  lea     rcx, [rax-2]
0x180011e65  cmovnz  rcx, rax
0x180011e69  mov     [rcx], r14w
0x180011e6d  jz      loc_180011DE9
0x180011e73  mov     rax, rbx
0x180011e76  mov     rcx, rdi
0x180011e79  cmp     [rcx], r14w
0x180011e7d  jz      short loc_180011E8E
0x180011e7f  add     rcx, 2
0x180011e83  sub     rax, 1
0x180011e87  jnz     short loc_180011E79
0x180011e89  mov     rcx, r14
0x180011e8c  jmp     short loc_180011E94
0x180011e8e  mov     rcx, rbx
0x180011e91  sub     rcx, rax
0x180011e94  test    rax, rax
0x180011e97  jz      loc_180011DE9
0x180011e9d  lea     rax, [rdi+rcx*2]
0x180011ea1  sub     rbx, rcx
0x180011ea4  jz      short loc_180011EC9
0x180011ea6  test    r10, r10
0x180011ea9  jz      short loc_180011EC9
0x180011eab  movzx   ecx, word ptr [r13+0]
0x180011eb0  test    cx, cx
0x180011eb3  jz      short loc_180011EC9
0x180011eb5  mov     [rax], cx
0x180011eb8  add     r13, 2
0x180011ebc  add     rax, 2
0x180011ec0  dec     r10
0x180011ec3  sub     rbx, 1
0x180011ec7  jnz     short loc_180011EA6
0x180011ec9  test    rbx, rbx
0x180011ecc  lea     rdx, [rax-2]
0x180011ed0  cmovnz  rdx, rax
0x180011ed4  mov     [rdx], r14w
0x180011ed8  jz      loc_180011DE9
0x180011ede  lea     rax, [rbp+57h+String]
0x180011ee2  mov     r9, rdi; Endpoint
0x180011ee5  mov     [rsp+0C0h+StringBinding], rax; StringBinding
0x180011eea  lea     rdx, ProtSeq; "ncacn_np"
0x180011ef1  mov     rax, [rbp+57h+var_78]
0x180011ef5  mov     r8, r15; NetworkAddr
0x180011ef8  xor     ecx, ecx; ObjUuid
0x180011efa  mov     [rsp+0C0h+Options], rax; Options
0x180011eff  call    cs:__imp_RpcStringBindingComposeW
0x180011f05  mov     rcx, rdi; hMem
0x180011f08  mov     ebx, eax
0x180011f0a  call    cs:__imp_LocalFree
0x180011f10  test    ebx, ebx
0x180011f12  jnz     loc_180011D50
0x180011f18  mov     rcx, [rbp+57h+String]; StringBinding
0x180011f1c  mov     rdx, rsi; Binding
0x180011f1f  call    cs:__imp_RpcBindingFromStringBindingW
0x180011f25  lea     rcx, [rbp+57h+String]; String
0x180011f29  mov     ebx, eax
0x180011f2b  call    cs:__imp_RpcStringFreeW
0x180011f31  test    ebx, ebx
0x180011f33  jz      short loc_180011F55
0x180011f35  lea     eax, [rbx-6AAh]
0x180011f3b  mov     [rsi], r14
0x180011f3e  mov     ebx, 0C0000017h
0x180011f43  cmp     eax, 1
0x180011f46  mov     ecx, 0C0000122h
0x180011f4b  cmova   ecx, ebx
0x180011f4e  mov     ebx, ecx
0x180011f50  jmp     loc_180011DF7
0x180011f55  mov     ebx, r14d
0x180011f58  jmp     loc_180011DF7
```
