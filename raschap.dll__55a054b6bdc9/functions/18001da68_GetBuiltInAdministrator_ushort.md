# GetBuiltInAdministrator(ushort * *)

- ea: `0x18001da68`
- end: `0x18001dbf3`
- name: `?GetBuiltInAdministrator@@YAKPEAPEAG@Z`
- size: `395`
- prototype: `unsigned int __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001dd0c`

## callees

- `0x18001da68`
- `0x180025efc`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001db41`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001db41`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001dbc5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001dbc5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001db6c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001db6c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001da8b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001da8b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001dab8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001dab8`

## pseudocode

```c
__int64 __fastcall GetBuiltInAdministrator(unsigned __int16 **a1)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  HRESULT v4; // eax
  int v5; // eax
  int v6; // eax
  __int64 v7; // rdi
  __int64 v8; // rax
  unsigned __int16 *v9; // rax
  _WORD *v10; // rdx
  void *Src[2]; // [rsp+30h] [rbp-20h] BYREF
  __int64 v13; // [rsp+40h] [rbp-10h]
  __int64 v14; // [rsp+78h] [rbp+28h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp+30h] BYREF

  ppv = 0;
  v2 = CoInitializeEx(0, 0);
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( (v2 & 0x1FFF0000) == 0x70000 )
      return (unsigned __int16)v2;
  }
  else
  {
    v4 = CoCreateInstance(&CLSID_LocalUserAccounts, 0, 1u, &GUID_3c708557_c99d_4fa3_9231_56518418b4e4, &ppv);
    v3 = v4;
    if ( v4 < 0 )
    {
      if ( (v4 & 0x1FFF0000) == 0x70000 )
        v3 = (unsigned __int16)v4;
    }
    else
    {
      v14 = 0;
      v5 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 80LL))(ppv, 500, &v14);
      v3 = v5;
      if ( v5 < 0 )
      {
        if ( (v5 & 0x1FFF0000) == 0x70000 )
          v3 = (unsigned __int16)v5;
      }
      else
      {
        v13 = 0;
        *(_OWORD *)Src = 0;
        v6 = (*(__int64 (__fastcall **)(__int64, __int64 *, void **))(*(_QWORD *)v14 + 40LL))(v14, PKEY_SAM_Name, Src);
        v3 = v6;
        if ( v6 < 0 )
        {
          if ( (v6 & 0x1FFF0000) == 0x70000 )
            v3 = (unsigned __int16)v6;
        }
        else
        {
          v7 = -1;
          v8 = -1;
          v3 = 0;
          do
            ++v8;
          while ( *((_WORD *)Src[1] + v8) );
          v9 = (unsigned __int16 *)LocalAlloc(0x40u, (unsigned int)(2 * v8 + 2));
          v10 = Src[1];
          *a1 = v9;
          do
            ++v7;
          while ( v10[v7] );
          memcpy_0(v9, v10, 2 * v7 + 2);
          PropVariantClear(Src);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    CoUninitialize();
  }
  return v3;
}

```

## disassembly

```asm
0x18001da68  mov     [rsp-18h+arg_0], rbx
0x18001da6d  mov     [rsp-18h+arg_18], rsi
0x18001da72  push    rbp
0x18001da73  push    rdi
0x18001da74  push    r14
0x18001da76  mov     rbp, rsp
0x18001da79  sub     rsp, 50h
0x18001da7d  mov     rsi, rcx
0x18001da80  xor     r14d, r14d
0x18001da83  xor     ecx, ecx; pvReserved
0x18001da85  mov     [rbp+arg_10], r14
0x18001da89  xor     edx, edx; dwCoInit
0x18001da8b  call    cs:__imp_CoInitializeEx
0x18001da91  mov     ebx, eax
0x18001da93  test    eax, eax
0x18001da95  js      loc_18001DBCD
0x18001da9b  lea     rax, [rbp+arg_10]
0x18001da9f  xor     edx, edx; pUnkOuter
0x18001daa1  lea     r9, _GUID_3c708557_c99d_4fa3_9231_56518418b4e4; riid
0x18001daa8  mov     [rsp+50h+ppv], rax; ppv
0x18001daad  lea     r8d, [r14+1]; dwClsContext
0x18001dab1  lea     rcx, CLSID_LocalUserAccounts; rclsid
0x18001dab8  call    cs:__imp_CoCreateInstance
0x18001dabe  mov     ebx, eax
0x18001dac0  test    eax, eax
0x18001dac2  js      loc_18001DBB6
0x18001dac8  mov     rcx, [rbp+arg_10]
0x18001dacc  lea     r8, [rbp+arg_8]
0x18001dad0  mov     [rbp+arg_8], r14
0x18001dad4  mov     edx, 1F4h
0x18001dad9  mov     rax, [rcx]
0x18001dadc  mov     rax, [rax+50h]
0x18001dae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dae5  mov     ebx, eax
0x18001dae7  test    eax, eax
0x18001dae9  js      loc_18001DB95
0x18001daef  mov     rcx, [rbp+arg_8]
0x18001daf3  lea     r8, [rbp+Src]
0x18001daf7  xor     eax, eax
0x18001daf9  lea     rdx, PKEY_SAM_Name
0x18001db00  mov     [rbp+var_10], rax
0x18001db04  xorps   xmm0, xmm0
0x18001db07  movups  xmmword ptr [rbp+Src], xmm0
0x18001db0b  mov     rax, [rcx]
0x18001db0e  mov     rax, [rax+28h]
0x18001db12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db17  mov     ebx, eax
0x18001db19  test    eax, eax
0x18001db1b  js      short loc_18001DB74
0x18001db1d  mov     rcx, [rbp+Src+8]
0x18001db21  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001db25  mov     rax, rdi
0x18001db28  mov     ebx, r14d
0x18001db2b  inc     rax
0x18001db2e  cmp     [rcx+rax*2], r14w
0x18001db33  jnz     short loc_18001DB2B
0x18001db35  lea     edx, ds:2[rax*2]; uBytes
0x18001db3c  mov     ecx, 40h ; '@'; uFlags
0x18001db41  call    cs:__imp_LocalAlloc
0x18001db47  mov     rdx, [rbp+Src+8]; Src
0x18001db4b  mov     [rsi], rax
0x18001db4e  inc     rdi
0x18001db51  cmp     [rdx+rdi*2], r14w
0x18001db56  jnz     short loc_18001DB4E
0x18001db58  lea     r8, ds:2[rdi*2]; Size
0x18001db60  mov     rcx, rax; void *
0x18001db63  call    memcpy_0
0x18001db68  lea     rcx, [rbp+Src]; pvar
0x18001db6c  call    cs:__imp_PropVariantClear
0x18001db72  jmp     short loc_18001DB83
0x18001db74  and     eax, 1FFF0000h
0x18001db79  cmp     eax, 70000h
0x18001db7e  jnz     short loc_18001DB83
0x18001db80  movzx   ebx, bx
0x18001db83  mov     rcx, [rbp+arg_8]
0x18001db87  mov     rax, [rcx]
0x18001db8a  mov     rax, [rax+10h]
0x18001db8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db93  jmp     short loc_18001DBA4
0x18001db95  and     eax, 1FFF0000h
0x18001db9a  cmp     eax, 70000h
0x18001db9f  jnz     short loc_18001DBA4
0x18001dba1  movzx   ebx, bx
0x18001dba4  mov     rcx, [rbp+arg_10]
0x18001dba8  mov     rax, [rcx]
0x18001dbab  mov     rax, [rax+10h]
0x18001dbaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbb4  jmp     short loc_18001DBC5
0x18001dbb6  and     eax, 1FFF0000h
0x18001dbbb  cmp     eax, 70000h
0x18001dbc0  jnz     short loc_18001DBC5
0x18001dbc2  movzx   ebx, bx
0x18001dbc5  call    cs:__imp_CoUninitialize
0x18001dbcb  jmp     short loc_18001DBDC
0x18001dbcd  and     eax, 1FFF0000h
0x18001dbd2  cmp     eax, 70000h
0x18001dbd7  jnz     short loc_18001DBDC
0x18001dbd9  movzx   ebx, bx
0x18001dbdc  lea     r11, [rsp+50h+var_s0]
0x18001dbe1  mov     eax, ebx
0x18001dbe3  mov     rbx, [r11+20h]
0x18001dbe7  mov     rsi, [r11+38h]
0x18001dbeb  mov     rsp, r11
0x18001dbee  pop     r14
0x18001dbf0  pop     rdi
0x18001dbf1  pop     rbp
0x18001dbf2  retn
```
