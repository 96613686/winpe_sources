# RpcpBindRpc

- ea: `0x180052ad0`
- end: `0x180052ddc`
- name: `RpcpBindRpc`
- size: `780`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180052a60`

## callees

- `0x180026ea0`
- `0x18003bc70`
- `0x18003c7ec`
- `0x180052ad0`
- `0x18005411c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180052bbe`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180052c33`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180052bbe`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180052c33`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180052b6c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180052c02`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180052c7c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180052b6c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180052c02`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180052c7c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052c64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052d2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052d90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052da9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052c64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052d2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052d90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052da9`
- `RPCRT4!RpcStringBindingComposeW` at `0x180052d1c`
- `RPCRT4!RpcStringBindingComposeW` at `0x180052d1c`
- `RPCRT4!RpcStringFreeW` at `0x180052d5a`
- `RPCRT4!RpcStringFreeW` at `0x180052d5a`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180052d48`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180052d48`

## pseudocode

```c
__int64 __fastcall RpcpBindRpc(char *Src, __int64 a2, __int64 a3, RPC_BINDING_HANDLE *a4)
{
  char *v5; // rdi
  unsigned __int16 *v6; // r14
  size_t v7; // rbx
  unsigned int v8; // ebx
  unsigned __int64 v9; // rsi
  unsigned __int16 *v10; // rax
  size_t v11; // r15
  WCHAR *v12; // rax
  wchar_t *v13; // rbx
  unsigned __int16 *v14; // rax
  __int64 v15; // r8
  unsigned __int16 *v16; // rdi
  __int64 v17; // r11
  unsigned __int64 v18; // r8
  unsigned __int16 *v19; // rax
  __int64 v20; // rdx
  RPC_STATUS v21; // ebx
  RPC_STATUS v22; // ebx
  int v23; // ecx
  DWORD nSize; // [rsp+30h] [rbp-40h] BYREF
  RPC_WSTR String; // [rsp+38h] [rbp-38h] BYREF
  WCHAR Buffer[16]; // [rsp+40h] [rbp-30h] BYREF

  String = 0;
  v5 = Src;
  nSize = 0;
  v6 = 0;
  *a4 = 0;
  if ( !Src )
    goto LABEL_26;
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)&Src[2 * v7] );
  if ( !*(_WORD *)Src )
    goto LABEL_26;
  if ( *(_WORD *)Src == 92 )
  {
    if ( *((_WORD *)Src + 1) != 92 )
      return (unsigned int)-1073741534;
    v7 -= 2LL;
    if ( !v7 )
      return (unsigned int)-1073741534;
    v9 = (unsigned __int64)Src;
    if ( Src == (char *)-4LL )
      goto LABEL_27;
    v5 = Src + 4;
  }
  else
  {
    v10 = (unsigned __int16 *)LocalAlloc(0, 2 * v7 + 6);
    v6 = v10;
    if ( !v10 )
      return (unsigned int)-1073741801;
    *(_DWORD *)v10 = 6029404;
    memcpy_0(v10 + 2, v5, 2 * v7 + 2);
    v9 = (unsigned __int64)v6;
  }
  if ( v7 <= 0xF )
  {
    nSize = 16;
    if ( GetComputerNameExW(ComputerNameNetBIOS, Buffer, &nSize) )
    {
      if ( v7 == nSize && !wcsnicmp(Buffer, (const wchar_t *)v5, v7) )
      {
LABEL_26:
        v9 = 0;
        goto LABEL_27;
      }
    }
  }
  v11 = v7 - 1;
  if ( *(_WORD *)&v5[2 * v7 - 2] != 46 )
    v11 = v7;
  v12 = (WCHAR *)LocalAlloc(0, 0x20Au);
  v13 = v12;
  if ( !v12 )
    goto LABEL_21;
  nSize = 261;
  if ( GetComputerNameExW(ComputerNameDnsFullyQualified, v12, &nSize) && v11 == nSize )
    v9 &= -(__int64)(wcsnicmp(v13, (const wchar_t *)v5, v11) != 0);
  LocalFree(v13);
LABEL_27:
  v14 = (unsigned __int16 *)LocalAlloc(0, 0x1Cu);
  v16 = v14;
  if ( !v14 )
  {
LABEL_21:
    v8 = -1073741801;
    goto LABEL_41;
  }
  if ( (int)RtlStringCopyWorkerW(v14, 14, v15, L"\\PIPE\\") >= 0 )
  {
    v18 = (unsigned int)v17;
    v19 = v16;
    do
    {
      if ( !*v19 )
        break;
      ++v19;
      --v18;
    }
    while ( v18 );
    if ( v18 )
    {
      v20 = (v17 - v18) & ((unsigned __int128)-(__int128)v18 >> 64);
      if ( (int)RtlStringCopyWorkerW(&v16[v20], v17 - v20, v18, L"lsarpc") >= 0 )
      {
        v21 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncacn_np", (RPC_WSTR)v9, v16, 0, &String);
        LocalFree(v16);
        if ( !v21 )
        {
          v22 = RpcBindingFromStringBindingW(String, a4);
          RpcStringFreeW(&String);
          if ( v22 )
          {
            *a4 = 0;
            v23 = -1073741534;
            if ( (unsigned int)(v22 - 1706) > 1 )
              v23 = -1073741801;
            v8 = v23;
          }
          else
          {
            v8 = 0;
          }
          goto LABEL_41;
        }
        goto LABEL_21;
      }
    }
  }
  LocalFree(v16);
  v8 = -1073741811;
LABEL_41:
  if ( v6 )
    LocalFree(v6);
  return v8;
}

```

## disassembly

```asm
0x180052ad0  mov     [rsp-38h+arg_8], rbx
0x180052ad5  push    rbp
0x180052ad6  push    rsi
0x180052ad7  push    rdi
0x180052ad8  push    r12
0x180052ada  push    r13
0x180052adc  push    r14
0x180052ade  push    r15
0x180052ae0  mov     rbp, rsp
0x180052ae3  sub     rsp, 70h
0x180052ae7  mov     rax, cs:__security_cookie
0x180052aee  xor     rax, rsp
0x180052af1  mov     [rbp+var_10], rax
0x180052af5  xor     r13d, r13d
0x180052af8  mov     r12, r9
0x180052afb  mov     [rbp+String], r13
0x180052aff  mov     rdi, rcx
0x180052b02  mov     [rbp+nSize], r13d
0x180052b06  mov     r14d, r13d
0x180052b09  mov     [r9], r13
0x180052b0c  test    rcx, rcx
0x180052b0f  jz      loc_180052C72
0x180052b15  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180052b19  inc     rbx
0x180052b1c  cmp     [rcx+rbx*2], r13w
0x180052b21  jnz     short loc_180052B19
0x180052b23  cmp     [rcx], r13w
0x180052b27  jz      loc_180052C72
0x180052b2d  mov     esi, 5Ch ; '\'
0x180052b32  cmp     [rcx], si
0x180052b35  jnz     short loc_180052B62
0x180052b37  cmp     [rcx+2], si
0x180052b3b  jnz     short loc_180052B43
0x180052b3d  add     rbx, 0FFFFFFFFFFFFFFFEh
0x180052b41  jnz     short loc_180052B4D
0x180052b43  mov     ebx, 0C0000122h
0x180052b48  jmp     loc_180052DB5
0x180052b4d  lea     rax, [rcx+4]
0x180052b51  mov     rsi, rdi
0x180052b54  test    rax, rax
0x180052b57  jz      loc_180052C75
0x180052b5d  mov     rdi, rax
0x180052b60  jmp     short loc_180052BA7
0x180052b62  lea     rdx, ds:6[rbx*2]; uBytes
0x180052b6a  xor     ecx, ecx; uFlags
0x180052b6c  call    cs:__imp_LocalAlloc
0x180052b73  nop     dword ptr [rax+rax+00h]
0x180052b78  mov     r14, rax
0x180052b7b  test    rax, rax
0x180052b7e  jnz     short loc_180052B8A
0x180052b80  mov     ebx, 0C0000017h
0x180052b85  jmp     loc_180052DB5
0x180052b8a  lea     r8, ds:2[rbx*2]; Size
0x180052b92  mov     dword ptr [rax], 5C005Ch
0x180052b98  lea     rcx, [rax+4]; void *
0x180052b9c  mov     rdx, rdi; Src
0x180052b9f  call    memcpy_0
0x180052ba4  mov     rsi, r14
0x180052ba7  cmp     rbx, 0Fh
0x180052bab  ja      short loc_180052BED
0x180052bad  lea     r8, [rbp+nSize]; nSize
0x180052bb1  mov     [rbp+nSize], 10h
0x180052bb8  lea     rdx, [rbp+Buffer]; lpBuffer
0x180052bbc  xor     ecx, ecx; NameType
0x180052bbe  call    cs:__imp_GetComputerNameExW
0x180052bc5  nop     dword ptr [rax+rax+00h]
0x180052bca  test    eax, eax
0x180052bcc  jz      short loc_180052BED
0x180052bce  mov     eax, [rbp+nSize]
0x180052bd1  cmp     rbx, rax
0x180052bd4  jnz     short loc_180052BED
0x180052bd6  mov     r8, rbx; MaxCount
0x180052bd9  lea     rcx, [rbp+Buffer]; String1
0x180052bdd  mov     rdx, rdi; String2
0x180052be0  call    _wcsnicmp
0x180052be5  test    eax, eax
0x180052be7  jz      loc_180052C72
0x180052bed  cmp     word ptr [rdi+rbx*2-2], 2Eh ; '.'
0x180052bf3  lea     r15, [rbx-1]
0x180052bf7  mov     edx, 20Ah; uBytes
0x180052bfc  cmovnz  r15, rbx
0x180052c00  xor     ecx, ecx; uFlags
0x180052c02  call    cs:__imp_LocalAlloc
0x180052c09  nop     dword ptr [rax+rax+00h]
0x180052c0e  mov     rbx, rax
0x180052c11  test    rax, rax
0x180052c14  jnz     short loc_180052C20
0x180052c16  mov     ebx, 0C0000017h
0x180052c1b  jmp     loc_180052DA1
0x180052c20  lea     r8, [rbp+nSize]; nSize
0x180052c24  mov     [rbp+nSize], 105h
0x180052c2b  mov     rdx, rbx; lpBuffer
0x180052c2e  mov     ecx, 3; NameType
0x180052c33  call    cs:__imp_GetComputerNameExW
0x180052c3a  nop     dword ptr [rax+rax+00h]
0x180052c3f  test    eax, eax
0x180052c41  jz      short loc_180052C61
0x180052c43  mov     eax, [rbp+nSize]
0x180052c46  cmp     r15, rax
0x180052c49  jnz     short loc_180052C61
0x180052c4b  mov     r8, r15; MaxCount
0x180052c4e  mov     rdx, rdi; String2
0x180052c51  mov     rcx, rbx; String1
0x180052c54  call    _wcsnicmp
0x180052c59  neg     eax
0x180052c5b  sbb     rcx, rcx
0x180052c5e  and     rsi, rcx
0x180052c61  mov     rcx, rbx; hMem
0x180052c64  call    cs:__imp_LocalFree
0x180052c6b  nop     dword ptr [rax+rax+00h]
0x180052c70  jmp     short loc_180052C75
0x180052c72  mov     rsi, r13
0x180052c75  mov     edx, 1Ch; uBytes
0x180052c7a  xor     ecx, ecx; uFlags
0x180052c7c  call    cs:__imp_LocalAlloc
0x180052c83  nop     dword ptr [rax+rax+00h]
0x180052c88  mov     rdi, rax
0x180052c8b  test    rax, rax
0x180052c8e  jz      short loc_180052C16
0x180052c90  mov     r11d, 0Eh
0x180052c96  lea     r9, aPipe; "\\PIPE\\"
0x180052c9d  mov     edx, r11d
0x180052ca0  mov     rcx, rax
0x180052ca3  call    RtlStringCopyWorkerW
0x180052ca8  test    eax, eax
0x180052caa  js      loc_180052D8D
0x180052cb0  mov     r8d, r11d
0x180052cb3  mov     rax, rdi
0x180052cb6  cmp     [rax], r13w
0x180052cba  jz      short loc_180052CC6
0x180052cbc  add     rax, 2
0x180052cc0  sub     r8, 1
0x180052cc4  jnz     short loc_180052CB6
0x180052cc6  mov     rcx, r11
0x180052cc9  mov     rax, r8
0x180052ccc  sub     rcx, r8
0x180052ccf  neg     rax
0x180052cd2  sbb     rdx, rdx
0x180052cd5  and     rdx, rcx
0x180052cd8  test    r8, r8
0x180052cdb  jz      loc_180052D8D
0x180052ce1  sub     r11, rdx
0x180052ce4  lea     rcx, [rdi+rdx*2]
0x180052ce8  mov     rdx, r11
0x180052ceb  lea     r9, aLsarpc; "lsarpc"
0x180052cf2  call    RtlStringCopyWorkerW
0x180052cf7  test    eax, eax
0x180052cf9  js      loc_180052D8D
0x180052cff  lea     rax, [rbp+String]
0x180052d03  mov     r9, rdi; Endpoint
0x180052d06  mov     [rsp+70h+StringBinding], rax; StringBinding
0x180052d0b  lea     rdx, ProtSeq; "ncacn_np"
0x180052d12  mov     r8, rsi; NetworkAddr
0x180052d15  mov     [rsp+70h+Options], r13; Options
0x180052d1a  xor     ecx, ecx; ObjUuid
0x180052d1c  call    cs:__imp_RpcStringBindingComposeW
0x180052d23  nop     dword ptr [rax+rax+00h]
0x180052d28  mov     rcx, rdi; hMem
0x180052d2b  mov     ebx, eax
0x180052d2d  call    cs:__imp_LocalFree
0x180052d34  nop     dword ptr [rax+rax+00h]
0x180052d39  test    ebx, ebx
0x180052d3b  jnz     loc_180052C16
0x180052d41  mov     rcx, [rbp+String]; StringBinding
0x180052d45  mov     rdx, r12; Binding
0x180052d48  call    cs:__imp_RpcBindingFromStringBindingW
0x180052d4f  nop     dword ptr [rax+rax+00h]
0x180052d54  lea     rcx, [rbp+String]; String
0x180052d58  mov     ebx, eax
0x180052d5a  call    cs:__imp_RpcStringFreeW
0x180052d61  nop     dword ptr [rax+rax+00h]
0x180052d66  test    ebx, ebx
0x180052d68  jz      short loc_180052D88
0x180052d6a  lea     eax, [rbx-6AAh]
0x180052d70  mov     [r12], r13
0x180052d74  mov     ebx, 0C0000017h
0x180052d79  cmp     eax, 1
0x180052d7c  mov     ecx, 0C0000122h
0x180052d81  cmova   ecx, ebx
0x180052d84  mov     ebx, ecx
0x180052d86  jmp     short loc_180052DA1
0x180052d88  mov     ebx, r13d
0x180052d8b  jmp     short loc_180052DA1
0x180052d8d  mov     rcx, rdi; hMem
0x180052d90  call    cs:__imp_LocalFree
0x180052d97  nop     dword ptr [rax+rax+00h]
0x180052d9c  mov     ebx, 0C000000Dh
0x180052da1  test    r14, r14
0x180052da4  jz      short loc_180052DB5
0x180052da6  mov     rcx, r14; hMem
0x180052da9  call    cs:__imp_LocalFree
0x180052db0  nop     dword ptr [rax+rax+00h]
0x180052db5  mov     eax, ebx
0x180052db7  mov     rcx, [rbp+var_10]
0x180052dbb  xor     rcx, rsp; StackCookie
0x180052dbe  call    __security_check_cookie
0x180052dc3  mov     rbx, [rsp+70h+arg_8]
0x180052dcb  add     rsp, 70h
0x180052dcf  pop     r15
0x180052dd1  pop     r14
0x180052dd3  pop     r13
0x180052dd5  pop     r12
0x180052dd7  pop     rdi
0x180052dd8  pop     rsi
0x180052dd9  pop     rbp
0x180052dda  retn
```
