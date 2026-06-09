# CAepStoreAccess::SetProperties(ushort const *,ulong,_DEVPROPERTY const *)

- ea: `0x180007c20`
- end: `0x180008009`
- name: `?SetProperties@CAepStoreAccess@@UEAAJPEBGKPEBU_DEVPROPERTY@@@Z`
- size: `1001`
- prototype: `__int64 __fastcall(CAepStoreAccess *__hidden this, const unsigned __int16 *, unsigned int, const struct _DEVPROPERTY *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800068a0`
- `0x180007c20`
- `0x180009170`
- `0x180009220`
- `0x180009250`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007d0a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007d2a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007d0a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007d2a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007db2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007dd3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007db2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007dd3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007ded`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007f5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007ded`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007f5c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007dfb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007f6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007dfb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007f6a`
- `RPCRT4!RpcBindingSetOption` at `0x180007da0`
- `RPCRT4!RpcBindingSetOption` at `0x180007da0`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180007d83`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180007d83`
- `RPCRT4!RpcStringBindingComposeW` at `0x180007d6c`
- `RPCRT4!RpcStringBindingComposeW` at `0x180007d6c`
- `RPCRT4!RpcStringFreeW` at `0x180007dc5`
- `RPCRT4!RpcStringFreeW` at `0x180007dc5`

## pseudocode

```c
__int64 __fastcall CAepStoreAccess::SetProperties(
        CAepStoreAccess *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        const struct _DEVPROPERTY *a4)
{
  const unsigned __int16 *v7; // rsi
  unsigned __int16 *v8; // r14
  _WORD *v9; // rax
  __int64 v10; // rdx
  signed int v11; // ebx
  __int64 v12; // r8
  const unsigned __int16 *v13; // rcx
  __int64 v14; // r9
  __int64 v15; // rdx
  __int64 v16; // rbp
  RPC_STATUS v17; // eax
  HANDLE v18; // rax
  const unsigned __int16 *v20; // r8
  unsigned __int64 v21; // rbp
  unsigned __int16 *v22; // rax
  __int64 v23; // r9
  unsigned __int64 v24; // rcx
  unsigned __int16 *v25; // rax
  unsigned __int16 *v26; // r8
  unsigned __int64 v27; // rdx
  const unsigned __int16 *v28; // rdi
  unsigned __int16 *v29; // rcx
  HANDLE ProcessHeap; // rax
  const unsigned __int16 *v31; // rax
  __int64 v32; // rcx
  RPC_WSTR String; // [rsp+78h] [rbp+10h] BYREF
  unsigned int v34; // [rsp+80h] [rbp+18h]

  v34 = a3;
  if ( !a2 || !a3 || !a4 )
    return 2147942487LL;
  v7 = (const unsigned __int16 *)*((_QWORD *)this + 3);
  v8 = 0;
  if ( !v7 )
  {
    v11 = -2147024809;
    goto LABEL_15;
  }
  v9 = (_WORD *)*((_QWORD *)this + 3);
  v10 = 0x7FFFFFFF;
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v10;
  }
  while ( v10 );
  v11 = -2147024809;
  if ( v10 )
  {
    v12 = 0x7FFFFFFF;
    v13 = a2;
    v14 = 2 * (0x7FFFFFFF - v10);
    do
    {
      if ( !*v13 )
        break;
      ++v13;
      --v12;
    }
    while ( v12 );
    v11 = -2147024809;
    if ( v12 )
    {
      v11 = 0;
      v15 = 2 * (0x7FFFFFFF - v12);
    }
    else
    {
      v15 = 0;
    }
    if ( v12 )
    {
      v28 = L"#";
      v32 = 0x7FFFFFFF;
      v31 = L"#";
      do
      {
        if ( !*v31 )
          break;
        ++v31;
        --v32;
      }
      while ( v32 );
      v11 = -2147024809;
      if ( !v32 )
        goto LABEL_27;
      v21 = v15 + 2 + v14 + 2 * (0x7FFFFFFF - v32);
      v22 = (unsigned __int16 *)DAF_user_alloc(v21);
      v8 = v22;
      if ( !v22 )
      {
        v11 = -2147024882;
        goto LABEL_27;
      }
      v11 = StringCbCopyW(v22, v21, v7);
      if ( !v11 )
      {
        v23 = 2147483646;
        if ( (v21 >> 1) - 1 > 0x7FFFFFFE )
        {
          v11 = -2147024809;
        }
        else
        {
          v24 = v21 >> 1;
          v25 = v8;
          do
          {
            if ( !*v25 )
              break;
            ++v25;
            --v24;
          }
          while ( v24 );
          v11 = -2147024809;
          if ( v24 )
          {
            v26 = &v8[(v21 >> 1) - v24];
            v27 = v24;
            do
            {
              if ( !v23 )
                break;
              if ( !*v28 )
                break;
              *v26++ = *v28++;
              --v23;
              --v27;
            }
            while ( v27 );
            v29 = v26 - 1;
            v11 = -2147024774;
            if ( v27 )
            {
              v29 = v26;
              v11 = 0;
            }
            *v29 = 0;
            if ( v27 )
            {
              v11 = StringCbCatW(v8, v21, a2);
              if ( !v11 )
                goto LABEL_15;
            }
          }
        }
      }
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v8);
      v8 = 0;
    }
  }
LABEL_15:
  if ( v11 >= 0 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    if ( !*((_DWORD *)this + 8) )
    {
      v11 = -2140930029;
LABEL_26:
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
      goto LABEL_27;
    }
    String = 0;
    v16 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    if ( !*((_DWORD *)this + 8) )
    {
      v11 = -2140930029;
      goto LABEL_23;
    }
    v11 = 0;
    if ( *((_QWORD *)this + 5) )
    {
      v16 = *((_QWORD *)this + 5);
    }
    else
    {
      v17 = RpcStringBindingComposeW(
              (RPC_WSTR)L"1475c123-1193-4379-81ac-302c4383421d",
              (RPC_WSTR)L"ncalrpc",
              0,
              0,
              0,
              &String);
      if ( v17 )
      {
        if ( v17 >= 0 )
        {
          v11 = (unsigned __int16)v17 | 0x80010000;
          goto LABEL_23;
        }
      }
      else
      {
        v17 = RpcBindingFromStringBindingW(String, (RPC_BINDING_HANDLE *)this + 5);
        if ( !v17 )
        {
          if ( !RpcBindingSetOption(*((RPC_BINDING_HANDLE *)this + 5), 0xDu, 1u) )
            v16 = *((_QWORD *)this + 5);
          goto LABEL_23;
        }
        if ( v17 >= 0 )
        {
          v11 = (unsigned __int16)v17 | 0x80010000;
          goto LABEL_23;
        }
      }
      v11 = v17;
    }
LABEL_23:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    if ( String )
      RpcStringFreeW(&String);
    if ( v11 >= 0 )
    {
      v20 = &dword_18008C97C;
      if ( *((_QWORD *)this + 2) )
        v20 = (const unsigned __int16 *)*((_QWORD *)this + 2);
      v11 = DasSetAepStoreAepProperties(v16, v8, v20, v34, a4);
    }
    goto LABEL_26;
  }
LABEL_27:
  if ( v8 )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v8);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180007c20  mov     [rsp+arg_10], r8d
0x180007c25  push    r12
0x180007c27  push    r13
0x180007c29  push    r15
0x180007c2b  sub     rsp, 50h
0x180007c2f  mov     r13, r9
0x180007c32  mov     eax, r8d
0x180007c35  mov     r12, rdx
0x180007c38  mov     r15, rcx
0x180007c3b  test    rdx, rdx
0x180007c3e  jz      loc_180007E18
0x180007c44  test    eax, eax
0x180007c46  jz      loc_180007E18
0x180007c4c  test    r9, r9
0x180007c4f  jz      loc_180007E18
0x180007c55  mov     [rsp+68h+var_28], rsi
0x180007c5a  mov     rsi, [rcx+18h]
0x180007c5e  mov     [rsp+68h+var_38], r14
0x180007c63  xor     r14d, r14d
0x180007c66  mov     [rsp+68h+arg_0], rbx
0x180007c6b  mov     [rsp+68h+var_20], rbp
0x180007c70  mov     [rsp+68h+var_30], rdi
0x180007c75  test    rsi, rsi
0x180007c78  jz      loc_180007E28
0x180007c7e  mov     r10d, 7FFFFFFFh
0x180007c84  mov     rax, rsi
0x180007c87  mov     edx, r10d
0x180007c8a  nop     word ptr [rax+rax+00h]
0x180007c90  cmp     [rax], r14w
0x180007c94  jz      short loc_180007CA0
0x180007c96  add     rax, 2
0x180007c9a  sub     rdx, 1
0x180007c9e  jnz     short loc_180007C90
0x180007ca0  xor     eax, eax
0x180007ca2  mov     ebx, 80070057h
0x180007ca7  test    rdx, rdx
0x180007caa  cmovnz  ebx, eax
0x180007cad  jz      short loc_180007CFE
0x180007caf  mov     r9, r10
0x180007cb2  mov     r8, r10
0x180007cb5  sub     r9, rdx
0x180007cb8  mov     rcx, r12
0x180007cbb  add     r9, r9
0x180007cbe  test    rdx, rdx
0x180007cc1  cmovz   r9, rax
0x180007cc5  cmp     [rcx], ax
0x180007cc8  jz      short loc_180007CD4
0x180007cca  add     rcx, 2
0x180007cce  sub     r8, 1
0x180007cd2  jnz     short loc_180007CC5
0x180007cd4  test    r8, r8
0x180007cd7  mov     ebx, 80070057h
0x180007cdc  cmovnz  ebx, eax
0x180007cdf  jz      loc_180007E6B
0x180007ce5  mov     rdx, r10
0x180007ce8  sub     rdx, r8
0x180007ceb  add     rdx, rdx
0x180007cee  test    r8, r8
0x180007cf1  cmovz   rdx, rax
0x180007cf5  test    r8, r8
0x180007cf8  jnz     loc_180007FC4
0x180007cfe  test    ebx, ebx
0x180007d00  js      loc_180007DD9
0x180007d06  lea     rcx, [r15+30h]; lpCriticalSection
0x180007d0a  call    cs:__imp_EnterCriticalSection
0x180007d10  cmp     dword ptr [r15+20h], 0
0x180007d15  jz      loc_180007FE7
0x180007d1b  lea     rcx, [r15+30h]; lpCriticalSection
0x180007d1f  mov     [rsp+68h+String], 0
0x180007d28  xor     ebp, ebp
0x180007d2a  call    cs:__imp_EnterCriticalSection
0x180007d30  cmp     [r15+20h], ebp
0x180007d34  jz      loc_180007FFF
0x180007d3a  mov     rax, [r15+28h]
0x180007d3e  xor     ebx, ebx
0x180007d40  test    rax, rax
0x180007d43  jnz     loc_180007E63
0x180007d49  lea     rax, [rsp+68h+String]
0x180007d4e  xor     r9d, r9d; Endpoint
0x180007d51  mov     [rsp+68h+StringBinding], rax; StringBinding
0x180007d56  lea     rdx, ProtSeq; "ncalrpc"
0x180007d5d  xor     r8d, r8d; NetworkAddr
0x180007d60  mov     [rsp+68h+Options], rbx; Options
0x180007d65  lea     rcx, ObjUuid; "1475c123-1193-4379-81ac-302c4383421d"
0x180007d6c  call    cs:__imp_RpcStringBindingComposeW
0x180007d72  test    eax, eax
0x180007d74  jnz     loc_180007FAB
0x180007d7a  mov     rcx, [rsp+68h+String]; StringBinding
0x180007d7f  lea     rdx, [r15+28h]; Binding
0x180007d83  call    cs:__imp_RpcBindingFromStringBindingW
0x180007d89  test    eax, eax
0x180007d8b  jnz     loc_180007FB4
0x180007d91  mov     rcx, [r15+28h]; hBinding
0x180007d95  mov     edx, 0Dh; option
0x180007d9a  mov     r8d, 1; optionValue
0x180007da0  call    cs:__imp_RpcBindingSetOption
0x180007da6  test    eax, eax
0x180007da8  jnz     short loc_180007DAE
0x180007daa  mov     rbp, [r15+28h]
0x180007dae  lea     rcx, [r15+30h]; lpCriticalSection
0x180007db2  call    cs:__imp_LeaveCriticalSection
0x180007db8  cmp     [rsp+68h+String], 0
0x180007dbe  jz      short loc_180007DCB
0x180007dc0  lea     rcx, [rsp+68h+String]; String
0x180007dc5  call    cs:__imp_RpcStringFreeW
0x180007dcb  test    ebx, ebx
0x180007dcd  jns     short loc_180007E32
0x180007dcf  lea     rcx, [r15+30h]; lpCriticalSection
0x180007dd3  call    cs:__imp_LeaveCriticalSection
0x180007dd9  mov     rdi, [rsp+68h+var_30]
0x180007dde  mov     rsi, [rsp+68h+var_28]
0x180007de3  mov     rbp, [rsp+68h+var_20]
0x180007de8  test    r14, r14
0x180007deb  jz      short loc_180007E01
0x180007ded  call    cs:__imp_GetProcessHeap
0x180007df3  mov     r8, r14; lpMem
0x180007df6  xor     edx, edx; dwFlags
0x180007df8  mov     rcx, rax; hHeap
0x180007dfb  call    cs:__imp_HeapFree
0x180007e01  mov     r14, [rsp+68h+var_38]
0x180007e06  mov     eax, ebx
0x180007e08  mov     rbx, [rsp+68h+arg_0]
0x180007e0d  add     rsp, 50h
0x180007e11  pop     r15
0x180007e13  pop     r13
0x180007e15  pop     r12
0x180007e17  retn
0x180007e18  mov     eax, 80070057h
0x180007e1d  add     rsp, 50h
0x180007e21  pop     r15
0x180007e23  pop     r13
0x180007e25  pop     r12
0x180007e27  retn
0x180007e28  mov     ebx, 80070057h
0x180007e2d  jmp     loc_180007CFE
0x180007e32  mov     rax, [r15+10h]
0x180007e36  lea     r8, dword_18008C97C
0x180007e3d  mov     r9d, [rsp+68h+arg_10]
0x180007e45  test    rax, rax
0x180007e48  mov     rdx, r14
0x180007e4b  mov     [rsp+68h+Options], r13
0x180007e50  cmovnz  r8, rax
0x180007e54  mov     rcx, rbp
0x180007e57  call    DasSetAepStoreAepProperties
0x180007e5c  mov     ebx, eax
0x180007e5e  jmp     loc_180007DCF
0x180007e63  mov     rbp, rax
0x180007e66  jmp     loc_180007DAE
0x180007e6b  xor     edx, edx
0x180007e6d  jmp     loc_180007CF5
0x180007e72  xor     eax, eax
0x180007e74  mov     ebx, 80070057h
0x180007e79  test    rcx, rcx
0x180007e7c  cmovnz  ebx, eax
0x180007e7f  jz      loc_180007DD9
0x180007e85  sub     r10, rcx
0x180007e88  test    rcx, rcx
0x180007e8b  lea     rbp, [r10+r10]
0x180007e8f  cmovz   rbp, rax
0x180007e93  add     rdx, 2
0x180007e97  add     rbp, r9
0x180007e9a  add     rbp, rdx
0x180007e9d  mov     rcx, rbp
0x180007ea0  call    DAF_user_alloc
0x180007ea5  mov     r14, rax
0x180007ea8  test    rax, rax
0x180007eab  jz      loc_180007FD3
0x180007eb1  mov     r8, rsi; unsigned __int16 *
0x180007eb4  mov     rdx, rbp; unsigned __int64
0x180007eb7  mov     rcx, rax; unsigned __int16 *
0x180007eba  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180007ebf  mov     ebx, eax
0x180007ec1  test    eax, eax
0x180007ec3  jnz     loc_180007F5C
0x180007ec9  mov     rdx, rbp
0x180007ecc  mov     r9d, 7FFFFFFEh
0x180007ed2  shr     rdx, 1
0x180007ed5  lea     rax, [rdx-1]
0x180007ed9  cmp     rax, r9
0x180007edc  ja      loc_180007FDD
0x180007ee2  mov     rcx, rdx
0x180007ee5  mov     rax, r14
0x180007ee8  cmp     word ptr [rax], 0
0x180007eec  jz      short loc_180007EF8
0x180007eee  add     rax, 2
0x180007ef2  sub     rcx, 1
0x180007ef6  jnz     short loc_180007EE8
0x180007ef8  xor     eax, eax
0x180007efa  mov     ebx, 80070057h
0x180007eff  test    rcx, rcx
0x180007f02  cmovnz  ebx, eax
0x180007f05  jz      short loc_180007F5C
0x180007f07  mov     rax, rdx
0x180007f0a  sub     rax, rcx
0x180007f0d  test    rcx, rcx
0x180007f10  jz      short loc_180007F5C
0x180007f12  lea     r8, [r14+rax*2]
0x180007f16  sub     rdx, rax
0x180007f19  jz      short loc_180007F42
0x180007f1b  nop     dword ptr [rax+rax+00h]
0x180007f20  test    r9, r9
0x180007f23  jz      short loc_180007F42
0x180007f25  movzx   eax, word ptr [rdi]
0x180007f28  test    ax, ax
0x180007f2b  jz      short loc_180007F42
0x180007f2d  mov     [r8], ax
0x180007f31  add     rdi, 2
0x180007f35  add     r8, 2
0x180007f39  dec     r9
0x180007f3c  sub     rdx, 1
0x180007f40  jnz     short loc_180007F20
0x180007f42  xor     eax, eax
0x180007f44  lea     rcx, [r8-2]
0x180007f48  test    rdx, rdx
0x180007f4b  mov     ebx, 8007007Ah
0x180007f50  cmovnz  rcx, r8
0x180007f54  cmovnz  ebx, eax
0x180007f57  mov     [rcx], ax
0x180007f5a  jnz     short loc_180007F78
0x180007f5c  call    cs:__imp_GetProcessHeap
0x180007f62  mov     r8, r14; lpMem
0x180007f65  xor     edx, edx; dwFlags
0x180007f67  mov     rcx, rax; hHeap
0x180007f6a  call    cs:__imp_HeapFree
0x180007f70  xor     r14d, r14d
0x180007f73  jmp     loc_180007CFE
0x180007f78  mov     r8, r12; unsigned __int16 *
0x180007f7b  mov     rdx, rbp; unsigned __int64
0x180007f7e  mov     rcx, r14; unsigned __int16 *
0x180007f81  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180007f86  mov     ebx, eax
0x180007f88  test    eax, eax
0x180007f8a  jz      loc_180007CFE
0x180007f90  jmp     short loc_180007F5C
0x180007f92  cmp     [rax], r14w
0x180007f96  jz      loc_180007E72
0x180007f9c  add     rax, 2
0x180007fa0  sub     rcx, 1
0x180007fa4  jnz     short loc_180007F92
0x180007fa6  jmp     loc_180007E72
0x180007fab  jns     short loc_180007FF1
0x180007fad  mov     ebx, eax
0x180007faf  jmp     loc_180007DAE
0x180007fb4  js      short loc_180007FAD
0x180007fb6  movzx   ebx, ax
0x180007fb9  or      ebx, 80010000h
0x180007fbf  jmp     loc_180007DAE
0x180007fc4  lea     rdi, asc_18008C788; "#"
0x180007fcb  mov     rcx, r10
0x180007fce  mov     rax, rdi
0x180007fd1  jmp     short loc_180007F92
0x180007fd3  mov     ebx, 8007000Eh
0x180007fd8  jmp     loc_180007DD9
0x180007fdd  mov     ebx, 80070057h
0x180007fe2  jmp     loc_180007F5C
0x180007fe7  mov     ebx, 80640013h
0x180007fec  jmp     loc_180007DCF
0x180007ff1  movzx   ebx, ax
0x180007ff4  or      ebx, 80010000h
0x180007ffa  jmp     loc_180007DAE
0x180007fff  mov     ebx, 80640013h
0x180008004  jmp     loc_180007DAE
```
