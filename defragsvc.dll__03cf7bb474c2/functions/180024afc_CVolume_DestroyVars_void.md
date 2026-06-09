# CVolume::_DestroyVars(void)

- ea: `0x180024afc`
- end: `0x180024c77`
- name: `?_DestroyVars@CVolume@@IEAAJXZ`
- size: `379`
- prototype: `__int64 __fastcall(CVolume *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002479c`
- `0x180024a30`
- `0x180062bd0`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180024afc`
- `0x180024c80`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024c48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024c48`

## pseudocode

```c
__int64 __fastcall CVolume::_DestroyVars(CVolume *this)
{
  __int64 v2; // rcx
  int v3; // edi
  __int16 v4; // ax
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v11; // [rsp+20h] [rbp-40h] BYREF
  __int16 v12; // [rsp+24h] [rbp-3Ch]
  __int16 v13; // [rsp+26h] [rbp-3Ah]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v11, "CVolume::_DestroyVars", 100, 1);
  v2 = *((_QWORD *)this + 28);
  if ( v2 )
  {
    v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 40LL))(v2);
    v11 = v3;
    v4 = 105;
    if ( v3 < 0 )
      goto LABEL_3;
    v12 = 105;
    v5 = *((_QWORD *)this + 28);
    if ( v5 )
    {
      *((_QWORD *)this + 28) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
  }
  v6 = *((_QWORD *)this + 27);
  if ( v6 )
  {
    v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 40LL))(v6);
    v11 = v3;
    v4 = 111;
    if ( v3 < 0 )
      goto LABEL_3;
    v12 = 111;
    v7 = *((_QWORD *)this + 27);
    if ( v7 )
    {
      *((_QWORD *)this + 27) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
  }
  v8 = *((_QWORD *)this + 29);
  if ( v8 )
  {
    v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 40LL))(v8);
    v11 = v3;
    v4 = 117;
    if ( v3 < 0 )
      goto LABEL_3;
    v12 = 117;
    v9 = *((_QWORD *)this + 29);
    if ( v9 )
    {
      *((_QWORD *)this + 29) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
  }
  v3 = CVolume::_DeleteExtentTables(this);
  v11 = v3;
  v4 = 122;
  if ( v3 >= 0 )
  {
    v12 = 122;
    CoTaskMemFree(*((LPVOID *)this + 20));
    *((_QWORD *)this + 20) = 0;
    v3 = v11;
    goto LABEL_16;
  }
LABEL_3:
  v13 = v4;
LABEL_16:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v11);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180024afc  mov     [rsp-8+arg_0], rbx
0x180024b01  mov     [rsp-8+arg_8], rdi
0x180024b06  push    rbp
0x180024b07  mov     rbp, rsp
0x180024b0a  sub     rsp, 60h
0x180024b0e  mov     rbx, rcx
0x180024b11  mov     r9d, 1; unsigned __int16
0x180024b17  lea     r8d, [r9+63h]; unsigned __int16
0x180024b1b  lea     rdx, aCvolumeDestroy; "CVolume::_DestroyVars"
0x180024b22  lea     rcx, [rbp+var_40]; this
0x180024b26  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180024b2b  nop
0x180024b2c  mov     rcx, [rbx+0E0h]
0x180024b33  test    rcx, rcx
0x180024b36  jz      short loc_180024B83
0x180024b38  mov     rax, [rcx]
0x180024b3b  mov     rax, [rax+28h]
0x180024b3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b44  mov     edi, eax
0x180024b46  mov     [rbp+var_40], eax
0x180024b49  test    eax, eax
0x180024b4b  mov     eax, 69h ; 'i'
0x180024b50  jns     short loc_180024B5B
0x180024b52  mov     [rbp+var_3A], ax
0x180024b56  jmp     loc_180024C5C
0x180024b5b  mov     [rbp+var_3C], ax
0x180024b5f  mov     rcx, [rbx+0E0h]
0x180024b66  test    rcx, rcx
0x180024b69  jz      short loc_180024B83
0x180024b6b  mov     qword ptr [rbx+0E0h], 0
0x180024b76  mov     rax, [rcx]
0x180024b79  mov     rax, [rax+10h]
0x180024b7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b82  nop
0x180024b83  mov     rcx, [rbx+0D8h]
0x180024b8a  test    rcx, rcx
0x180024b8d  jz      short loc_180024BD1
0x180024b8f  mov     rax, [rcx]
0x180024b92  mov     rax, [rax+28h]
0x180024b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b9b  mov     edi, eax
0x180024b9d  mov     [rbp+var_40], eax
0x180024ba0  test    eax, eax
0x180024ba2  mov     eax, 6Fh ; 'o'
0x180024ba7  js      short loc_180024B52
0x180024ba9  mov     [rbp+var_3C], ax
0x180024bad  mov     rcx, [rbx+0D8h]
0x180024bb4  test    rcx, rcx
0x180024bb7  jz      short loc_180024BD1
0x180024bb9  mov     qword ptr [rbx+0D8h], 0
0x180024bc4  mov     rax, [rcx]
0x180024bc7  mov     rax, [rax+10h]
0x180024bcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024bd0  nop
0x180024bd1  mov     rcx, [rbx+0E8h]
0x180024bd8  test    rcx, rcx
0x180024bdb  jz      short loc_180024C23
0x180024bdd  mov     rax, [rcx]
0x180024be0  mov     rax, [rax+28h]
0x180024be4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024be9  mov     edi, eax
0x180024beb  mov     [rbp+var_40], eax
0x180024bee  test    eax, eax
0x180024bf0  mov     eax, 75h ; 'u'
0x180024bf5  js      loc_180024B52
0x180024bfb  mov     [rbp+var_3C], ax
0x180024bff  mov     rcx, [rbx+0E8h]
0x180024c06  test    rcx, rcx
0x180024c09  jz      short loc_180024C23
0x180024c0b  mov     qword ptr [rbx+0E8h], 0
0x180024c16  mov     rax, [rcx]
0x180024c19  mov     rax, [rax+10h]
0x180024c1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c22  nop
0x180024c23  mov     rcx, rbx; this
0x180024c26  call    ?_DeleteExtentTables@CVolume@@IEAAJXZ; CVolume::_DeleteExtentTables(void)
0x180024c2b  mov     edi, eax
0x180024c2d  mov     [rbp+var_40], eax
0x180024c30  test    eax, eax
0x180024c32  mov     eax, 7Ah ; 'z'
0x180024c37  js      loc_180024B52
0x180024c3d  mov     [rbp+var_3C], ax
0x180024c41  mov     rcx, [rbx+0A0h]; pv
0x180024c48  call    cs:__imp_CoTaskMemFree
0x180024c4e  mov     qword ptr [rbx+0A0h], 0
0x180024c59  mov     edi, [rbp+var_40]
0x180024c5c  lea     rcx, [rbp+var_40]; this
0x180024c60  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180024c65  mov     eax, edi
0x180024c67  mov     rbx, [rsp+60h+arg_0]
0x180024c6c  mov     rdi, [rsp+60h+arg_8]
0x180024c71  add     rsp, 60h
0x180024c75  pop     rbp
0x180024c76  retn
```
