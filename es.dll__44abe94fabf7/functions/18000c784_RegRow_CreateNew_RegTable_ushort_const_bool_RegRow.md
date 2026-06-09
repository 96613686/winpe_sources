# RegRow::CreateNew(RegTable *,ushort const *,bool,RegRow * &)

- ea: `0x18000c784`
- end: `0x18000c903`
- name: `?CreateNew@RegRow@@SAJPEAVRegTable@@PEBG_NAEAPEAV1@@Z`
- size: `383`
- prototype: `__int64 __fastcall(struct RegTable *, const unsigned __int16 *, bool, struct RegRow **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b9a0`

## callees

- `0x180006194`
- `0x18000bbc8`
- `0x18000c784`
- `0x18000c910`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c8be`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c8be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c8d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c8d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c863`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c863`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c811`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c811`

## pseudocode

```c
__int64 __fastcall RegRow::CreateNew(struct RegTable *a1, const unsigned __int16 *a2, bool a3, struct RegRow **a4)
{
  bool v7; // si
  const unsigned __int16 *v8; // rdx
  int v9; // eax
  bool v10; // r8
  int v11; // r10d
  unsigned int v12; // r12d
  WCHAR *v13; // rdi
  int v14; // ebx
  unsigned __int16 *v16; // rax
  HKEY v17; // rcx
  LSTATUS v18; // eax
  HKEY hKey; // [rsp+80h] [rbp+8h] BYREF
  bool v20; // [rsp+90h] [rbp+18h]

  v20 = a3;
  v7 = 1;
  safe_lstrlenW((const unsigned __int16 *)a1 + 9);
  v9 = safe_lstrlenW(v8);
  v12 = v11 + v9 + 2;
  if ( v10 )
  {
    v13 = 0;
  }
  else
  {
    v16 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v12, 2u));
    v13 = v16;
    if ( !v16 )
      return (unsigned int)-2147024882;
    v14 = StringCchPrintfW(v16, v12, L"%s\\%s", (char *)a1 + 18, a2);
    if ( v14 < 0 )
      goto LABEL_7;
    v17 = (HKEY)*((_QWORD *)a1 + 1);
    hKey = 0;
    v18 = RegOpenKeyExW(v17, v13, 0, 0x20019u, &hKey);
    if ( v18 )
    {
      if ( v18 != 2 )
      {
        if ( v18 <= 0 )
          v14 = v18;
        else
          v14 = (unsigned __int16)v18 | 0x80070000;
      }
    }
    else
    {
      v7 = 0;
      RegCloseKey(hKey);
    }
    if ( v14 < 0 )
      goto LABEL_7;
    v10 = v20;
  }
  v14 = RegRow::Create(a1, v12, v13, a2, v7, v10, a4);
  if ( v14 < 0 )
  {
    if ( !v13 )
      return (unsigned int)v14;
LABEL_7:
    CoTaskMemFree(v13);
    return (unsigned int)v14;
  }
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a4 + 8LL))(*a4);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18000c784  mov     [rsp+arg_8], rbx
0x18000c789  mov     [rsp+arg_10], r8b
0x18000c78e  push    rbp
0x18000c78f  push    rsi
0x18000c790  push    rdi
0x18000c791  push    r12
0x18000c793  push    r13
0x18000c795  push    r14
0x18000c797  push    r15
0x18000c799  sub     rsp, 40h
0x18000c79d  mov     r13, rcx
0x18000c7a0  mov     r14, r9
0x18000c7a3  add     rcx, 12h; unsigned __int16 *
0x18000c7a7  mov     r15, rdx
0x18000c7aa  mov     esi, 1
0x18000c7af  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18000c7b4  mov     rcx, rdx; unsigned __int16 *
0x18000c7b7  mov     r10d, eax
0x18000c7ba  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18000c7bf  lea     r12d, [rax+2]
0x18000c7c3  add     r12d, r10d
0x18000c7c6  test    r8b, r8b
0x18000c7c9  jz      short loc_18000C84A
0x18000c7cb  xor     edi, edi
0x18000c7cd  mov     [rsp+78h+var_48], r14; struct RegRow **
0x18000c7d2  mov     r9, r15; unsigned __int16 *
0x18000c7d5  mov     [rsp+78h+var_50], r8b; bool
0x18000c7da  mov     edx, r12d; unsigned int
0x18000c7dd  mov     r8, rdi; unsigned __int16 *
0x18000c7e0  mov     byte ptr [rsp+78h+phkResult], sil; bool
0x18000c7e5  mov     rcx, r13; struct RegTable *
0x18000c7e8  call    ?Create@RegRow@@CAJPEAVRegTable@@KPEAGPEBG_N3AEAPEAV1@@Z; RegRow::Create(RegTable *,ulong,ushort *,ushort const *,bool,bool,RegRow * &)
0x18000c7ed  mov     ebx, eax
0x18000c7ef  test    eax, eax
0x18000c7f1  js      loc_18000C8F5
0x18000c7f7  mov     rcx, [r14]
0x18000c7fa  mov     rax, [rcx]
0x18000c7fd  mov     rax, [rax+8]
0x18000c801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c806  jmp     short loc_18000C817
0x18000c808  mov     ebx, eax
0x18000c80a  test    ebx, ebx
0x18000c80c  jns     short loc_18000C831
0x18000c80e  mov     rcx, rdi; pv
0x18000c811  call    cs:__imp_CoTaskMemFree
0x18000c817  mov     eax, ebx
0x18000c819  mov     rbx, [rsp+78h+arg_8]
0x18000c821  add     rsp, 40h
0x18000c825  pop     r15
0x18000c827  pop     r14
0x18000c829  pop     r13
0x18000c82b  pop     r12
0x18000c82d  pop     rdi
0x18000c82e  pop     rsi
0x18000c82f  pop     rbp
0x18000c830  retn
0x18000c831  mov     r8b, [rsp+78h+arg_10]
0x18000c839  jmp     short loc_18000C7CD
0x18000c83b  test    eax, eax
0x18000c83d  jle     short loc_18000C808
0x18000c83f  movzx   ebx, ax
0x18000c842  or      ebx, 80070000h
0x18000c848  jmp     short loc_18000C80A
0x18000c84a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c851  mov     ebx, r12d
0x18000c854  mov     eax, 2
0x18000c859  mul     rbx
0x18000c85c  cmovb   rax, rcx
0x18000c860  mov     rcx, rax; cb
0x18000c863  call    cs:__imp_CoTaskMemAlloc
0x18000c869  mov     rdi, rax
0x18000c86c  test    rax, rax
0x18000c86f  jz      short loc_18000C8EB
0x18000c871  lea     r9, [r13+12h]
0x18000c875  mov     [rsp+78h+phkResult], r15
0x18000c87a  lea     r8, aSS; "%s\\%s"
0x18000c881  mov     edx, ebx; unsigned __int64
0x18000c883  mov     rcx, rax; unsigned __int16 *
0x18000c886  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c88b  mov     ebx, eax
0x18000c88d  test    eax, eax
0x18000c88f  js      loc_18000C80E
0x18000c895  mov     rcx, [r13+8]; hKey
0x18000c899  lea     rax, [rsp+78h+hKey]
0x18000c8a1  mov     r9d, 20019h; samDesired
0x18000c8a7  mov     [rsp+78h+phkResult], rax; phkResult
0x18000c8ac  xor     r8d, r8d; ulOptions
0x18000c8af  mov     [rsp+78h+hKey], 0
0x18000c8bb  mov     rdx, rdi; lpSubKey
0x18000c8be  call    cs:__imp_RegOpenKeyExW
0x18000c8c4  test    eax, eax
0x18000c8c6  jnz     short loc_18000C8DD
0x18000c8c8  mov     rcx, [rsp+78h+hKey]; hKey
0x18000c8d0  xor     esi, esi
0x18000c8d2  call    cs:__imp_RegCloseKey
0x18000c8d8  jmp     loc_18000C80A
0x18000c8dd  cmp     eax, 2
0x18000c8e0  jz      loc_18000C80A
0x18000c8e6  jmp     loc_18000C83B
0x18000c8eb  mov     ebx, 8007000Eh
0x18000c8f0  jmp     loc_18000C817
0x18000c8f5  test    rdi, rdi
0x18000c8f8  jz      loc_18000C817
0x18000c8fe  jmp     loc_18000C80E
```
