# IASStoreFQUserName(IAttributesRaw *,DS_NAME_FORMAT,ushort const *)

- ea: `0x1800169e0`
- end: `0x180016b3e`
- name: `?IASStoreFQUserName@@YAJPEAUIAttributesRaw@@W4DS_NAME_FORMAT@@PEBG@Z`
- size: `350`
- prototype: `__int64 __fastcall(struct IAttributesRaw *, enum DS_NAME_FORMAT, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800213d0`
- `0x180022ae0`
- `0x180024890`
- `0x180024dcc`

## callees

- `0x180001f26`
- `0x18000ab90`
- `0x18000acf4`
- `0x1800169e0`
- `0x18002e010`

## import_xrefs

- `NTDSAPI!DsFreeNameResultW` at `0x180016b1b`
- `NTDSAPI!DsFreeNameResultW` at `0x180016b1b`
- `NTDSAPI!DsCrackNamesW` at `0x180016a3e`
- `NTDSAPI!DsCrackNamesW` at `0x180016a3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016a97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016a97`

## pseudocode

```c
__int64 __fastcall IASStoreFQUserName(struct IAttributesRaw *a1, enum DS_NAME_FORMAT a2, unsigned __int16 *a3)
{
  PDS_NAME_RESULT_ITEMW rItems; // rax
  __int64 v5; // rax
  unsigned int v6; // esi
  void *v7; // rax
  _QWORD *v8; // rdi
  unsigned int v9; // ebx
  _QWORD v11[2]; // [rsp+40h] [rbp-10h] BYREF
  DS_NAME_RESULTW *pResult; // [rsp+80h] [rbp+30h] BYREF
  void *Src; // [rsp+90h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+98h] [rbp+48h] BYREF

  Src = a3;
  if ( !a1 || !a3 )
    return 2147500035LL;
  pResult = 0;
  if ( a2 == DS_FQDN_1779_NAME
    && !DsCrackNamesW(
          0,
          DS_NAME_FLAG_SYNTACTICAL_ONLY,
          DS_FQDN_1779_NAME,
          DS_CANONICAL_NAME,
          1u,
          (const LPCWSTR *)&Src,
          &pResult)
    && pResult->cItems == 1 )
  {
    rItems = pResult->rItems;
    if ( !rItems->status )
      Src = rItems->pName;
  }
  pv = 0;
  if ( (unsigned int)IASAttributeAlloc(1, &pv) )
  {
    v9 = -2147024882;
  }
  else
  {
    v5 = -1;
    do
      ++v5;
    while ( *((_WORD *)Src + v5) );
    v6 = 2 * v5 + 2;
    v7 = CoTaskMemAlloc(v6);
    v8 = pv;
    *((_QWORD *)pv + 4) = v7;
    if ( v7 )
    {
      memcpy_0(v7, Src, v6);
      v8[3] = 0;
      *((_DWORD *)v8 + 4) = 5;
      *((_DWORD *)v8 + 2) = 4130;
      (*(void (__fastcall **)(struct IAttributesRaw *, __int64))(*(_QWORD *)a1 + 40LL))(a1, 1);
      v11[0] = 0;
      v11[1] = v8;
      v9 = (*(__int64 (__fastcall **)(struct IAttributesRaw *, __int64, _QWORD *))(*(_QWORD *)a1 + 24LL))(a1, 1, v11);
    }
    else
    {
      v9 = -2147024882;
    }
    IASAttributeRelease(v8);
  }
  DsFreeNameResultW(pResult);
  return v9;
}

```

## disassembly

```asm
0x1800169e0  mov     r11, rsp
0x1800169e3  mov     [r11+10h], rbx
0x1800169e7  mov     [r11+18h], r8
0x1800169eb  push    rbp
0x1800169ec  push    rsi
0x1800169ed  push    rdi
0x1800169ee  push    r14
0x1800169f0  push    r15
0x1800169f2  mov     rbp, rsp
0x1800169f5  sub     rsp, 50h
0x1800169f9  mov     rbx, rcx
0x1800169fc  xor     r14d, r14d
0x1800169ff  test    rcx, rcx
0x180016a02  jz      loc_180016B25
0x180016a08  test    r8, r8
0x180016a0b  jz      loc_180016B25
0x180016a11  mov     [rbp+pResult], r14
0x180016a15  lea     r15d, [r14+1]
0x180016a19  cmp     edx, r15d
0x180016a1c  jnz     short loc_180016A62
0x180016a1e  lea     rax, [rbp+pResult]
0x180016a22  mov     [r11-48h], rax
0x180016a26  lea     rax, [rbp+Src]
0x180016a2a  mov     [r11-50h], rax
0x180016a2e  mov     [r11-58h], r15d
0x180016a32  lea     r9d, [r14+7]; formatDesired
0x180016a36  mov     r8d, r15d; formatOffered
0x180016a39  mov     edx, r15d; flags
0x180016a3c  xor     ecx, ecx; hDS
0x180016a3e  call    cs:__imp_DsCrackNamesW
0x180016a44  test    eax, eax
0x180016a46  jnz     short loc_180016A62
0x180016a48  mov     rax, [rbp+pResult]
0x180016a4c  cmp     [rax], r15d
0x180016a4f  jnz     short loc_180016A62
0x180016a51  mov     rax, [rax+8]
0x180016a55  cmp     [rax], r14d
0x180016a58  jnz     short loc_180016A62
0x180016a5a  mov     rax, [rax+10h]
0x180016a5e  mov     [rbp+Src], rax
0x180016a62  mov     [rbp+pv], r14
0x180016a66  lea     rdx, [rbp+pv]
0x180016a6a  mov     ecx, r15d
0x180016a6d  call    IASAttributeAlloc
0x180016a72  test    eax, eax
0x180016a74  jnz     loc_180016B12
0x180016a7a  mov     rcx, [rbp+Src]
0x180016a7e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016a82  inc     rax
0x180016a85  cmp     [rcx+rax*2], r14w
0x180016a8a  jnz     short loc_180016A82
0x180016a8c  lea     eax, ds:2[rax*2]
0x180016a93  mov     esi, eax
0x180016a95  mov     ecx, eax; cb
0x180016a97  call    cs:__imp_CoTaskMemAlloc
0x180016a9d  mov     rdi, [rbp+pv]
0x180016aa1  mov     [rdi+20h], rax
0x180016aa5  test    rax, rax
0x180016aa8  jz      short loc_180016B03
0x180016aaa  mov     r8d, esi; Size
0x180016aad  mov     rdx, [rbp+Src]; Src
0x180016ab1  mov     rcx, rax; void *
0x180016ab4  call    memcpy_0
0x180016ab9  mov     [rdi+18h], r14
0x180016abd  mov     dword ptr [rdi+10h], 5
0x180016ac4  lea     r8, [rdi+8]
0x180016ac8  mov     dword ptr [r8], 1022h
0x180016acf  mov     rax, [rbx]
0x180016ad2  mov     edx, r15d
0x180016ad5  mov     rcx, rbx
0x180016ad8  mov     rax, [rax+28h]
0x180016adc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ae1  mov     [rbp+var_10], r14
0x180016ae5  mov     [rbp+var_8], rdi
0x180016ae9  mov     rax, [rbx]
0x180016aec  lea     r8, [rbp+var_10]
0x180016af0  mov     edx, r15d
0x180016af3  mov     rcx, rbx
0x180016af6  mov     rax, [rax+18h]
0x180016afa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016aff  mov     ebx, eax
0x180016b01  jmp     short loc_180016B08
0x180016b03  mov     ebx, 8007000Eh
0x180016b08  mov     rcx, rdi; pv
0x180016b0b  call    IASAttributeRelease
0x180016b10  jmp     short loc_180016B17
0x180016b12  mov     ebx, 8007000Eh
0x180016b17  mov     rcx, [rbp+pResult]; pResult
0x180016b1b  call    cs:__imp_DsFreeNameResultW
0x180016b21  mov     eax, ebx
0x180016b23  jmp     short loc_180016B2A
0x180016b25  mov     eax, 80004003h
0x180016b2a  mov     rbx, [rsp+50h+arg_8]
0x180016b32  add     rsp, 50h
0x180016b36  pop     r15
0x180016b38  pop     r14
0x180016b3a  pop     rdi
0x180016b3b  pop     rsi
0x180016b3c  pop     rbp
0x180016b3d  retn
```
