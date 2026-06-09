# DllSetCommitSig(ILockBytes *,ulong)

- ea: `0x1800397c4`
- end: `0x1800398c0`
- name: `?DllSetCommitSig@@YAJPEAUILockBytes@@K@Z`
- size: `252`
- prototype: `__int64 __fastcall(struct ILockBytes *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000745c`

## callees

- `0x18000cdd8`
- `0x1800397c4`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800397e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800397e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800398a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800398a5`

## pseudocode

```c
__int64 __fastcall DllSetCommitSig(struct ILockBytes *a1, int a2)
{
  unsigned int v3; // edi
  CMSFHeader *v5; // rsi
  int v6; // ebx
  struct ILockBytesVtbl *lpVtbl; // rax
  HRESULT (__stdcall *ReadAt)(ILockBytes *, ULARGE_INTEGER, void *, ULONG, ULONG *); // rax
  __int64 v9; // rdx
  int v10; // eax
  int v12; // [rsp+60h] [rbp+18h] BYREF
  __int64 v13; // [rsp+68h] [rbp+20h]

  v3 = 516;
  while ( 1 )
  {
    v5 = (CMSFHeader *)CoTaskMemAlloc(v3);
    if ( v5 )
      break;
    v3 >>= 1;
    if ( v3 < 0x204 )
    {
      v6 = -2147287032;
      goto LABEL_13;
    }
  }
  lpVtbl = a1->lpVtbl;
  v13 = 0;
  ReadAt = lpVtbl->ReadAt;
  v12 = 0;
  v6 = ((__int64 (__fastcall *)(struct ILockBytes *, _QWORD, CMSFHeader *, _QWORD, int *))ReadAt)(a1, 0, v5, v3, &v12);
  if ( v6 >= 0 )
  {
    if ( v12 == v3 )
    {
      v6 = CMSFHeader::Validate(v5);
      if ( v6 >= 0 )
      {
        v9 = v13;
        *((_DWORD *)v5 + 13) = a2;
        *((_DWORD *)v5 + 128) = 1;
        v10 = ((__int64 (__fastcall *)(struct ILockBytes *, __int64, CMSFHeader *, __int64, int *))a1->lpVtbl->WriteAt)(
                a1,
                v9,
                v5,
                512,
                &v12);
        v6 = v10;
        if ( v10 >= 0 )
        {
          if ( v12 != 512 )
            v10 = -2147286787;
          v6 = v10;
        }
      }
    }
    else
    {
      v6 = -2147286787;
    }
  }
LABEL_13:
  CoTaskMemFree(v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800397c4  mov     [rsp+arg_0], rbx
0x1800397c9  mov     [rsp+arg_8], rbp
0x1800397ce  push    rsi
0x1800397cf  push    rdi
0x1800397d0  push    r14
0x1800397d2  sub     rsp, 30h
0x1800397d6  mov     ebx, 204h
0x1800397db  mov     ebp, edx
0x1800397dd  mov     edi, ebx
0x1800397df  mov     r14, rcx
0x1800397e2  mov     ecx, edi; cb
0x1800397e4  call    cs:__imp_CoTaskMemAlloc
0x1800397ea  mov     rsi, rax
0x1800397ed  test    rax, rax
0x1800397f0  jnz     short loc_180039802
0x1800397f2  shr     edi, 1
0x1800397f4  cmp     edi, ebx
0x1800397f6  jnb     short loc_1800397E2
0x1800397f8  mov     ebx, 80030008h
0x1800397fd  jmp     loc_1800398A2
0x180039802  mov     rax, [r14]
0x180039805  lea     rcx, [rsp+48h+arg_10]
0x18003980a  mov     [rsp+48h+var_28], rcx
0x18003980f  mov     r9d, edi
0x180039812  mov     [rsp+48h+arg_18], 0
0x18003981b  mov     r8, rsi
0x18003981e  mov     rdx, [rsp+48h+arg_18]
0x180039823  mov     rcx, r14
0x180039826  mov     rax, [rax+18h]
0x18003982a  mov     [rsp+48h+arg_10], 0
0x180039832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039837  mov     ebx, eax
0x180039839  test    eax, eax
0x18003983b  js      short loc_1800398A2
0x18003983d  cmp     [rsp+48h+arg_10], edi
0x180039841  jz      short loc_18003984A
0x180039843  mov     ebx, 800300FDh
0x180039848  jmp     short loc_1800398A2
0x18003984a  mov     rcx, rsi; this
0x18003984d  call    ?Validate@CMSFHeader@@QEBAJXZ; CMSFHeader::Validate(void)
0x180039852  mov     ebx, eax
0x180039854  test    eax, eax
0x180039856  js      short loc_1800398A2
0x180039858  mov     rdx, [rsp+48h+arg_18]
0x18003985d  lea     rcx, [rsp+48h+arg_10]
0x180039862  mov     [rsi+34h], ebp
0x180039865  mov     edi, 200h
0x18003986a  mov     dword ptr [rsi+200h], 1
0x180039874  mov     r9d, edi
0x180039877  mov     rax, [r14]
0x18003987a  mov     r8, rsi
0x18003987d  mov     [rsp+48h+var_28], rcx
0x180039882  mov     rcx, r14
0x180039885  mov     rax, [rax+20h]
0x180039889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003988e  mov     ebx, eax
0x180039890  test    eax, eax
0x180039892  js      short loc_1800398A2
0x180039894  cmp     [rsp+48h+arg_10], edi
0x180039898  mov     ebx, 800300FDh
0x18003989d  cmovnz  eax, ebx
0x1800398a0  mov     ebx, eax
0x1800398a2  mov     rcx, rsi; pv
0x1800398a5  call    cs:__imp_CoTaskMemFree
0x1800398ab  mov     rbp, [rsp+48h+arg_8]
0x1800398b0  mov     eax, ebx
0x1800398b2  mov     rbx, [rsp+48h+arg_0]
0x1800398b7  add     rsp, 30h
0x1800398bb  pop     r14
0x1800398bd  pop     rdi
0x1800398be  pop     rsi
0x1800398bf  retn
```
