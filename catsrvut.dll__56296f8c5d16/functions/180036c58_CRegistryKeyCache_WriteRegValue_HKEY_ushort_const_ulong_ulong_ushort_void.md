# CRegistryKeyCache::WriteRegValue(HKEY__ *,ushort const *,ulong,ulong,ushort,void *)

- ea: `0x180036c58`
- end: `0x180036e21`
- name: `?WriteRegValue@CRegistryKeyCache@@QEAAJPEAUHKEY__@@PEBGKKGPEAX@Z`
- size: `457`
- prototype: `int(CRegistryKeyCache *__hidden this, HKEY, const unsigned __int16 *, unsigned int, unsigned int, unsigned __int16, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180036a60`

## callees

- `0x180001e60`
- `0x180036bfc`
- `0x180036c58`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036e00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036e00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180036d19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180036d19`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180036cc2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180036cc2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180036ddf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180036ddf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRegistryKeyCache::WriteRegValue(
        CRegistryKeyCache *this,
        HKEY a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        DWORD a5,
        unsigned __int16 a6,
        unsigned __int16 *a7)
{
  int v10; // r13d
  DWORD cbData; // edi
  __int16 v12; // dx
  unsigned int v13; // ebx
  LSTATUS v14; // eax
  __int64 v15; // rdi
  __int64 v16; // r14
  unsigned __int16 *v17; // rax
  unsigned __int16 *lpData; // rsi
  unsigned __int64 v19; // r14
  unsigned __int64 i; // rcx
  __int64 v21; // rdi
  unsigned int v22; // eax
  LSTATUS v23; // eax

  v10 = 0;
  if ( a2 )
  {
    cbData = a5;
    if ( a7 || !a5 )
    {
      v13 = CRegistryKeyCache::ValidateType(this, a6, a4);
      if ( (v13 & 0x80000000) != 0 )
        return v13;
      if ( !a5 )
      {
        v14 = RegDeleteValueW(a2, a3);
        v13 = v14;
        if ( v14 )
        {
          if ( v14 > 0 )
            return (unsigned __int16)v14 | 0x80070000;
        }
        else
        {
          return 0;
        }
        return v13;
      }
      if ( a4 == 7 )
      {
        v15 = -1;
        v16 = -1;
        do
          ++v16;
        while ( a7[v16] );
        v17 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v16 + 3, 2u));
        lpData = v17;
        if ( !v17 )
          return (unsigned int)-2147024882;
        v13 = StringCchCopyW(v17, v16 + 1, a7);
        if ( (v13 & 0x80000000) != 0 )
        {
LABEL_36:
          CoTaskMemFree(lpData);
          return v13;
        }
        v10 = 1;
        lpData[v16 + 1] = 0;
        v19 = v16 + 2;
        lpData[v19] = 0;
        do
          ++v15;
        while ( lpData[v15] );
        cbData = 2 * v15 + 6;
        for ( i = 0; i < v19; ++i )
        {
          if ( lpData[i] == 44 )
            lpData[i] = 0;
        }
      }
      else
      {
        lpData = a7;
        if ( a4 == 1 )
        {
          v21 = -1;
          do
            ++v21;
          while ( a7[v21] );
          cbData = 2 * v21 + 2;
        }
        else if ( v12 == 19 )
        {
          v22 = 4;
          if ( a4 != 4 )
            v22 = a5;
          cbData = v22;
        }
      }
      v23 = RegSetValueExW(a2, a3, 0, a4, (const BYTE *)lpData, cbData);
      if ( v23 )
      {
        if ( v23 > 0 )
          v13 = (unsigned __int16)v23 | 0x80070000;
        else
          v13 = v23;
      }
      if ( !v10 )
        return v13;
      goto LABEL_36;
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180036c58  mov     [rsp+lpValueName], r8
0x180036c5d  push    rbx
0x180036c5e  push    rbp
0x180036c5f  push    rsi
0x180036c60  push    rdi
0x180036c61  push    r12
0x180036c63  push    r13
0x180036c65  push    r14
0x180036c67  push    r15
0x180036c69  sub     rsp, 38h
0x180036c6d  mov     r15d, r9d
0x180036c70  mov     rsi, r8
0x180036c73  mov     r12, rdx
0x180036c76  xor     r13d, r13d
0x180036c79  test    rdx, rdx
0x180036c7c  jz      loc_180036E0B
0x180036c82  mov     edi, [rsp+78h+arg_20]
0x180036c89  mov     rbp, [rsp+78h+arg_30]
0x180036c91  test    rbp, rbp
0x180036c94  jnz     short loc_180036C9E
0x180036c96  test    edi, edi
0x180036c98  jnz     loc_180036E0B
0x180036c9e  mov     r8d, r15d; unsigned int
0x180036ca1  movzx   edx, [rsp+78h+arg_28]; unsigned __int16
0x180036ca9  call    ?ValidateType@CRegistryKeyCache@@AEAAJGK@Z; CRegistryKeyCache::ValidateType(ushort,ulong)
0x180036cae  mov     ebx, eax
0x180036cb0  test    eax, eax
0x180036cb2  js      loc_180036E07
0x180036cb8  test    edi, edi
0x180036cba  jnz     short loc_180036CEA
0x180036cbc  mov     rdx, rsi; lpValueName
0x180036cbf  mov     rcx, r12; hKey
0x180036cc2  call    cs:__imp_RegDeleteValueW
0x180036cc8  mov     ebx, eax
0x180036cca  test    eax, eax
0x180036ccc  jnz     short loc_180036CD6
0x180036cce  mov     ebx, r13d
0x180036cd1  jmp     loc_180036E07
0x180036cd6  jle     loc_180036E07
0x180036cdc  movzx   ebx, ax
0x180036cdf  or      ebx, 80070000h
0x180036ce5  jmp     loc_180036E07
0x180036cea  cmp     r15d, 7
0x180036cee  jnz     loc_180036D8E
0x180036cf4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180036cf8  mov     r14, rdi
0x180036cfb  inc     r14
0x180036cfe  cmp     [rbp+r14*2+0], r13w
0x180036d04  jnz     short loc_180036CFB
0x180036d06  lea     rcx, [r14+3]
0x180036d0a  mov     eax, 2
0x180036d0f  mul     rcx
0x180036d12  cmovb   rax, rdi
0x180036d16  mov     rcx, rax; cb
0x180036d19  call    cs:__imp_CoTaskMemAlloc
0x180036d1f  mov     rsi, rax
0x180036d22  test    rax, rax
0x180036d25  jnz     short loc_180036D31
0x180036d27  mov     ebx, 8007000Eh
0x180036d2c  jmp     loc_180036E07
0x180036d31  lea     rdx, [r14+1]; unsigned __int64
0x180036d35  mov     r8, rbp; unsigned __int16 *
0x180036d38  mov     rcx, rsi; unsigned __int16 *
0x180036d3b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180036d40  mov     ebx, eax
0x180036d42  test    eax, eax
0x180036d44  js      loc_180036DFD
0x180036d4a  xor     eax, eax
0x180036d4c  lea     r13d, [rax+1]
0x180036d50  mov     [rsi+r14*2+2], ax
0x180036d56  add     r14, 2
0x180036d5a  mov     [rsi+r14*2], ax
0x180036d5f  inc     rdi
0x180036d62  cmp     [rsi+rdi*2], ax
0x180036d66  jnz     short loc_180036D5F
0x180036d68  lea     edi, ds:6[rdi*2]
0x180036d6f  mov     rcx, rax
0x180036d72  test    r14, r14
0x180036d75  jz      short loc_180036DC5
0x180036d77  cmp     word ptr [rsi+rcx*2], 2Ch ; ','
0x180036d7c  jnz     short loc_180036D84
0x180036d7e  mov     [rsi+rcx*2], ax
0x180036d82  xor     eax, eax
0x180036d84  inc     rcx
0x180036d87  cmp     rcx, r14
0x180036d8a  jb      short loc_180036D77
0x180036d8c  jmp     short loc_180036DC5
0x180036d8e  mov     rsi, rbp
0x180036d91  cmp     r15d, 1
0x180036d95  jnz     short loc_180036DB2
0x180036d97  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180036d9b  xor     r14d, r14d
0x180036d9e  inc     rdi
0x180036da1  cmp     [rbp+rdi*2+0], r14w
0x180036da7  jnz     short loc_180036D9E
0x180036da9  lea     edi, ds:2[rdi*2]
0x180036db0  jmp     short loc_180036DC5
0x180036db2  cmp     dx, 13h
0x180036db6  jnz     short loc_180036DC5
0x180036db8  mov     eax, 4
0x180036dbd  cmp     r15d, eax
0x180036dc0  cmovnz  eax, edi
0x180036dc3  mov     edi, eax
0x180036dc5  mov     [rsp+78h+cbData], edi; cbData
0x180036dc9  mov     [rsp+78h+lpData], rsi; lpData
0x180036dce  mov     r9d, r15d; dwType
0x180036dd1  xor     r8d, r8d; Reserved
0x180036dd4  mov     rdx, [rsp+78h+lpValueName]; lpValueName
0x180036ddc  mov     rcx, r12; hKey
0x180036ddf  call    cs:__imp_RegSetValueExW
0x180036de5  test    eax, eax
0x180036de7  jz      short loc_180036DF8
0x180036de9  jg      short loc_180036DEF
0x180036deb  mov     ebx, eax
0x180036ded  jmp     short loc_180036DF8
0x180036def  movzx   ebx, ax
0x180036df2  or      ebx, 80070000h
0x180036df8  test    r13d, r13d
0x180036dfb  jz      short loc_180036E07
0x180036dfd  mov     rcx, rsi; pv
0x180036e00  call    cs:__imp_CoTaskMemFree
0x180036e06  nop
0x180036e07  mov     eax, ebx
0x180036e09  jmp     short loc_180036E10
0x180036e0b  mov     eax, 80070057h
0x180036e10  add     rsp, 38h
0x180036e14  pop     r15
0x180036e16  pop     r14
0x180036e18  pop     r13
0x180036e1a  pop     r12
0x180036e1c  pop     rdi
0x180036e1d  pop     rsi
0x180036e1e  pop     rbp
0x180036e1f  pop     rbx
0x180036e20  retn
```
